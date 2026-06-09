# ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)

- ea: `0x180050004`
- end: `0x1800503cf`
- name: `?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z`
- size: `971`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, char, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18004bf80`

## callees

- `0x180050004`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!malloc` at `0x180050139`
- `msvcrt!malloc` at `0x180050223`
- `msvcrt!malloc` at `0x180050139`
- `msvcrt!malloc` at `0x180050223`
- `msvcrt!free` at `0x180050381`
- `msvcrt!free` at `0x18005038f`
- `msvcrt!free` at `0x180050381`
- `msvcrt!free` at `0x18005038f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800500d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800501c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800500d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800501c6`
- `ntdll!RtlIpv6StringToAddressW` at `0x1800502c6`
- `ntdll!RtlIpv6StringToAddressW` at `0x1800502c6`
- `ntdll!RtlIpv4StringToAddressW` at `0x180050289`
- `ntdll!RtlIpv4StringToAddressW` at `0x180050289`

## string_xrefs

- `0x18005009a`: `ReadAddressFromRegistry`
- `0x1800500f8`: `ReadAddressFromRegistry`
- `0x180050171`: `ReadAddressFromRegistry`
- `0x18005024c`: `ReadAddressFromRegistry`
- `0x180050334`: `ReadAddressFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadAddressFromRegistry(HKEY hkey, LPCWSTR lpValue, char a3, unsigned __int8 *a4)
{
  int v8; // r15d
  struct in_addr *v9; // rdi
  void (*v10)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS ValueW; // eax
  char *pvData; // rbx
  unsigned int v13; // esi
  char *v14; // rcx
  __int64 v15; // rax
  size_t v16; // rcx
  const WCHAR *v17; // r14
  LONG v18; // eax
  __int64 v19; // rax
  unsigned int v20; // ebx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR Terminator; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+58h] [rbp-A8h]
  __int128 v29; // [rsp+68h] [rbp-98h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  int v31; // [rsp+80h] [rbp-80h]
  int v32; // [rsp+84h] [rbp-7Ch]
  int v33; // [rsp+90h] [rbp-70h] BYREF
  char v34[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v8 = 0;
  v24 = 0;
  pcbData = 0;
  v9 = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v31 = -1;
  v32 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v27, L"ReadAddressFromRegistry", &v24, v10);
  *(_OWORD *)a4 = 0;
  ValueW = RegGetValueW(hkey, 0, lpValue, 0x20u, 0, 0, &pcbData);
  v24 = ValueW;
  if ( ValueW )
  {
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v33) = 0;
      LODWORD(pdwType) = ValueW;
      FormatRRASErrorString(&v33, L"%s: RegGetValue (%ws) failed: %d.", L"ReadAddressFromRegistry", lpValue, pdwType);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v33);
    }
    pvData = 0;
    goto LABEL_39;
  }
  pvData = (char *)malloc(pcbData);
  if ( !pvData )
  {
    v24 = 8;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v33) = 0;
      LODWORD(pdwType) = 8;
      FormatRRASErrorString(&v33, L"%s: malloc (%ws) failed: %d.", L"ReadAddressFromRegistry", lpValue, pdwType);
      goto LABEL_10;
    }
    goto LABEL_44;
  }
  v24 = RegGetValueW(hkey, 0, lpValue, 0x20u, 0, pvData, &pcbData);
  v13 = 0;
  if ( v24 )
  {
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v33) = 0;
      LODWORD(pdwTypea) = v24;
      FormatRRASErrorString(&v33, L"%s: RegGetValue (%ws) failed: %d.", L"ReadAddressFromRegistry", lpValue, pdwTypea);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v33);
    }
    goto LABEL_38;
  }
  Terminator = 0;
  v14 = pvData;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)&pvData[2 * v15] );
  while ( v15 )
  {
    ++v13;
    v14 += 2 * v15 + 2;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v14[2 * v15] );
  }
  if ( a3 )
    v16 = 4LL * v13;
  else
    v16 = 16LL * v13;
  v9 = (struct in_addr *)malloc(v16);
  if ( !v9 )
  {
    v24 = 8;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, L"%s: malloc failed. %d.", L"ReadAddressFromRegistry");
      goto LABEL_10;
    }
    goto LABEL_43;
  }
  v17 = (const WCHAR *)pvData;
  if ( !v13 )
  {
LABEL_38:
    *(_DWORD *)a4 = v13;
    *((_QWORD *)a4 + 1) = v9;
    goto LABEL_39;
  }
  while ( a3 )
  {
    v18 = RtlIpv4StringToAddressW(v17, 1u, &Terminator, &v9[v8]);
    v24 = v18;
    if ( v18 )
    {
      if ( !(_QWORD)xmmword_180078C50 )
        goto LABEL_39;
      LOWORD(v33) = 0;
      LODWORD(pdwTypea) = v18;
      FormatRRASErrorString(
        &v33,
        L"%s: RtlIpv4StringToAddress failed for (%ws) : %d.",
        L"ReadAddressFromRegistry",
        v17,
        pdwTypea);
      goto LABEL_10;
    }
LABEL_30:
    v19 = -1;
    do
      ++v19;
    while ( v17[v19] );
    v17 += v19 + 1;
    if ( ++v8 >= v13 )
      goto LABEL_38;
  }
  v24 = RtlIpv6StringToAddressW(v17, &Terminator, (struct in6_addr *)&v9[4 * v8]);
  if ( !v24 )
    goto LABEL_30;
  if ( !(_QWORD)xmmword_180078C50 )
    goto LABEL_39;
  LOWORD(v33) = 0;
  LODWORD(pdwTypea) = v24;
  FormatRRASErrorString(
    &v33,
    L"%s: RtlIpv6StringToAddress failed for (%ws) : %d.",
    L"ReadAddressFromRegistry",
    v17,
    pdwTypea);
LABEL_10:
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_180078C50,
    &v33);
LABEL_39:
  if ( v24 && v9 )
    free(v9);
  if ( pvData )
LABEL_43:
    free(pvData);
LABEL_44:
  v20 = v24;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v27);
  return v20;
}

```

## disassembly

```asm
0x180050004  mov     [rsp-8+arg_10], rbx
0x180050009  push    rbp
0x18005000a  push    rsi
0x18005000b  push    rdi
0x18005000c  push    r12
0x18005000e  push    r13
0x180050010  push    r14
0x180050012  push    r15
0x180050014  lea     rbp, [rsp-7A0h]
0x18005001c  sub     rsp, 8A0h
0x180050023  mov     rax, cs:__security_cookie
0x18005002a  xor     rax, rsp
0x18005002d  mov     [rbp+7D0h+var_40], rax
0x180050034  mov     r12, r9
0x180050037  mov     r13b, r8b
0x18005003a  mov     r14, rdx
0x18005003d  mov     rsi, rcx
0x180050040  xor     r15d, r15d
0x180050043  mov     [rsp+8D0h+var_890], r15d
0x180050048  mov     [rsp+8D0h+var_88C], r15d
0x18005004d  mov     edi, r15d
0x180050050  mov     [rbp+7D0h+var_840], r15d
0x180050054  xor     edx, edx; Val
0x180050056  mov     r8d, 7FCh; Size
0x18005005c  lea     rcx, [rbp+7D0h+var_83C]; void *
0x180050060  call    memset_0
0x180050065  xorps   xmm0, xmm0
0x180050068  movdqu  [rsp+8D0h+var_878], xmm0
0x18005006e  mov     [rsp+8D0h+var_880], r15
0x180050073  xorps   xmm1, xmm1
0x180050076  movdqu  [rsp+8D0h+var_868], xmm1
0x18005007c  mov     [rsp+8D0h+var_858], r15
0x180050081  mov     [rbp+7D0h+var_850], 0FFFFFFFFh
0x180050088  mov     [rbp+7D0h+var_84C], r15d
0x18005008c  cmp     qword ptr cs:xmmword_180078C50+8, r15
0x180050093  jz      short loc_1800500AB
0x180050095  lea     r8, [rsp+8D0h+var_890]; unsigned int *
0x18005009a  lea     rdx, aReadaddressfro; "ReadAddressFromRegistry"
0x1800500a1  lea     rcx, [rsp+8D0h+var_880]; this
0x1800500a6  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800500ab  xorps   xmm0, xmm0
0x1800500ae  movups  xmmword ptr [r12], xmm0
0x1800500b3  lea     rax, [rsp+8D0h+var_88C]
0x1800500b8  mov     [rsp+8D0h+pcbData], rax; pcbData
0x1800500bd  mov     [rsp+8D0h+pvData], r15; pvData
0x1800500c2  mov     [rsp+8D0h+pdwType], r15; pdwType
0x1800500c7  mov     r9d, 20h ; ' '; dwFlags
0x1800500cd  mov     r8, r14; lpValue
0x1800500d0  xor     edx, edx; lpSubKey
0x1800500d2  mov     rcx, rsi; hkey
0x1800500d5  call    cs:__imp_RegGetValueW
0x1800500db  mov     [rsp+8D0h+var_890], eax
0x1800500df  test    eax, eax
0x1800500e1  jz      short loc_180050135
0x1800500e3  cmp     qword ptr cs:xmmword_180078C50, r15
0x1800500ea  jz      short loc_18005012D
0x1800500ec  mov     word ptr [rbp+7D0h+var_840], r15w
0x1800500f1  mov     dword ptr [rsp+8D0h+pdwType], eax
0x1800500f5  mov     r9, r14
0x1800500f8  lea     r8, aReadaddressfro; "ReadAddressFromRegistry"
0x1800500ff  lea     rdx, aSReggetvalueWs; "%s: RegGetValue (%ws) failed: %d."
0x180050106  lea     rcx, [rbp+7D0h+var_840]
0x18005010a  call    FormatRRASErrorString
0x18005010f  lea     r8, [rbp+7D0h+var_840]
0x180050113  mov     rdx, qword ptr cs:xmmword_180078C50
0x18005011a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180050121  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005012d  mov     rbx, r15
0x180050130  jmp     loc_180050372
0x180050135  mov     ecx, [rsp+8D0h+var_88C]; Size
0x180050139  call    cs:__imp_malloc
0x18005013f  mov     rbx, rax
0x180050142  test    rax, rax
0x180050145  jnz     short loc_1800501A4
0x180050147  lea     r9d, [rax+8]
0x18005014b  mov     [rsp+8D0h+var_890], r9d
0x180050150  cmp     qword ptr cs:xmmword_180078C50, r15
0x180050157  jz      loc_180050395
0x18005015d  mov     word ptr [rbp+7D0h+var_840], r15w
0x180050162  mov     dword ptr [rsp+8D0h+pdwType], r9d
0x180050167  lea     rdx, aSMallocWsFaile; "%s: malloc (%ws) failed: %d."
0x18005016e  mov     r9, r14
0x180050171  lea     r8, aReadaddressfro; "ReadAddressFromRegistry"
0x180050178  lea     rcx, [rbp+7D0h+var_840]
0x18005017c  call    FormatRRASErrorString
0x180050181  lea     r8, [rbp+7D0h+var_840]
0x180050185  mov     rdx, qword ptr cs:xmmword_180078C50
0x18005018c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180050193  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005019a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005019f  jmp     loc_180050372
0x1800501a4  lea     rax, [rsp+8D0h+var_88C]
0x1800501a9  mov     [rsp+8D0h+pcbData], rax; pcbData
0x1800501ae  mov     [rsp+8D0h+pvData], rbx; pvData
0x1800501b3  mov     [rsp+8D0h+pdwType], r15; pdwType
0x1800501b8  mov     r9d, 20h ; ' '; dwFlags
0x1800501be  mov     r8, r14; lpValue
0x1800501c1  xor     edx, edx; lpSubKey
0x1800501c3  mov     rcx, rsi; hkey
0x1800501c6  call    cs:__imp_RegGetValueW
0x1800501cc  mov     [rsp+8D0h+var_890], eax
0x1800501d0  mov     esi, r15d
0x1800501d3  test    eax, eax
0x1800501d5  jnz     loc_18005031B
0x1800501db  mov     [rsp+8D0h+Terminator], r15
0x1800501e0  mov     rcx, rbx
0x1800501e3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800501e7  mov     rax, rdx
0x1800501ea  inc     rax
0x1800501ed  cmp     [rbx+rax*2], r15w
0x1800501f2  jnz     short loc_1800501EA
0x1800501f4  jmp     short loc_18005020D
0x1800501f6  inc     esi
0x1800501f8  lea     rcx, [rcx+rax*2]
0x1800501fc  lea     rcx, [rcx+2]
0x180050200  mov     rax, rdx
0x180050203  inc     rax
0x180050206  cmp     [rcx+rax*2], r15w
0x18005020b  jnz     short loc_180050203
0x18005020d  test    rax, rax
0x180050210  jnz     short loc_1800501F6
0x180050212  mov     ecx, esi
0x180050214  test    r13b, r13b
0x180050217  jz      short loc_18005021F
0x180050219  shl     rcx, 2
0x18005021d  jmp     short loc_180050223
0x18005021f  shl     rcx, 4; Size
0x180050223  call    cs:__imp_malloc
0x180050229  mov     rdi, rax
0x18005022c  test    rax, rax
0x18005022f  jnz     short loc_180050268
0x180050231  lea     r9d, [rax+8]
0x180050235  mov     [rsp+8D0h+var_890], r9d
0x18005023a  cmp     qword ptr cs:xmmword_180078C50, r15
0x180050241  jz      loc_18005038C
0x180050247  mov     word ptr [rbp+7D0h+var_840], r15w
0x18005024c  lea     r8, aReadaddressfro; "ReadAddressFromRegistry"
0x180050253  lea     rdx, aSMallocFailedD; "%s: malloc failed. %d."
0x18005025a  lea     rcx, [rbp+7D0h+var_840]
0x18005025e  call    FormatRRASErrorString
0x180050263  jmp     loc_180050181
0x180050268  mov     r14, rbx
0x18005026b  test    esi, esi
0x18005026d  jz      loc_180050369
0x180050273  mov     r8d, r15d
0x180050276  mov     rcx, r14; S
0x180050279  test    r13b, r13b
0x18005027c  jz      short loc_1800502BA
0x18005027e  lea     r9, [rdi+r8*4]; Addr
0x180050282  lea     r8, [rsp+8D0h+Terminator]; Terminator
0x180050287  mov     dl, 1; Strict
0x180050289  call    cs:__imp_RtlIpv4StringToAddressW
0x18005028f  mov     [rsp+8D0h+var_890], eax
0x180050293  xor     ecx, ecx
0x180050295  test    eax, eax
0x180050297  jz      short loc_1800502D6
0x180050299  cmp     qword ptr cs:xmmword_180078C50, rcx
0x1800502a0  jz      loc_180050372
0x1800502a6  mov     word ptr [rbp+7D0h+var_840], cx
0x1800502aa  mov     dword ptr [rsp+8D0h+pdwType], eax
0x1800502ae  lea     rdx, aSRtlipv4string; "%s: RtlIpv4StringToAddress failed for ("...
0x1800502b5  jmp     loc_18005016E
0x1800502ba  shl     r8, 4
0x1800502be  add     r8, rdi; Addr
0x1800502c1  lea     rdx, [rsp+8D0h+Terminator]; Terminator
0x1800502c6  call    cs:__imp_RtlIpv6StringToAddressW
0x1800502cc  mov     [rsp+8D0h+var_890], eax
0x1800502d0  xor     ecx, ecx
0x1800502d2  test    eax, eax
0x1800502d4  jnz     short loc_1800502FA
0x1800502d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800502da  inc     rax
0x1800502dd  cmp     [r14+rax*2], cx
0x1800502e2  jnz     short loc_1800502DA
0x1800502e4  lea     r14, [r14+rax*2]
0x1800502e8  add     r14, 2
0x1800502ec  inc     r15d
0x1800502ef  cmp     r15d, esi
0x1800502f2  jb      loc_180050273
0x1800502f8  jmp     short loc_180050369
0x1800502fa  cmp     qword ptr cs:xmmword_180078C50, rcx
0x180050301  jz      short loc_180050372
0x180050303  mov     word ptr [rbp+7D0h+var_840], cx
0x180050307  mov     eax, [rsp+8D0h+var_890]
0x18005030b  mov     dword ptr [rsp+8D0h+pdwType], eax
0x18005030f  lea     rdx, aSRtlipv6string; "%s: RtlIpv6StringToAddress failed for ("...
0x180050316  jmp     loc_18005016E
0x18005031b  cmp     qword ptr cs:xmmword_180078C50, r15
0x180050322  jz      short loc_180050369
0x180050324  mov     word ptr [rbp+7D0h+var_840], r15w
0x180050329  mov     eax, [rsp+8D0h+var_890]
0x18005032d  mov     dword ptr [rsp+8D0h+pdwType], eax
0x180050331  mov     r9, r14
0x180050334  lea     r8, aReadaddressfro; "ReadAddressFromRegistry"
0x18005033b  lea     rdx, aSReggetvalueWs; "%s: RegGetValue (%ws) failed: %d."
0x180050342  lea     rcx, [rbp+7D0h+var_840]
0x180050346  call    FormatRRASErrorString
0x18005034b  lea     r8, [rbp+7D0h+var_840]
0x18005034f  mov     rdx, qword ptr cs:xmmword_180078C50
0x180050356  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18005035d  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050369  mov     [r12], esi
0x18005036d  mov     [r12+8], rdi
0x180050372  cmp     [rsp+8D0h+var_890], 0
0x180050377  jz      short loc_180050387
0x180050379  test    rdi, rdi
0x18005037c  jz      short loc_180050387
0x18005037e  mov     rcx, rdi; Block
0x180050381  call    cs:__imp_free
0x180050387  test    rbx, rbx
0x18005038a  jz      short loc_180050395
0x18005038c  mov     rcx, rbx; Block
0x18005038f  call    cs:__imp_free
0x180050395  mov     ebx, [rsp+8D0h+var_890]
0x180050399  lea     rcx, [rsp+8D0h+var_880]; this
0x18005039e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800503a3  mov     eax, ebx
0x1800503a5  mov     rcx, [rbp+7D0h+var_40]
0x1800503ac  xor     rcx, rsp; StackCookie
0x1800503af  call    __security_check_cookie
0x1800503b4  mov     rbx, [rsp+8D0h+arg_10]
0x1800503bc  add     rsp, 8A0h
0x1800503c3  pop     r15
0x1800503c5  pop     r14
0x1800503c7  pop     r13
0x1800503c9  pop     r12
0x1800503cb  pop     rdi
0x1800503cc  pop     rsi
0x1800503cd  pop     rbp
0x1800503ce  retn
```
