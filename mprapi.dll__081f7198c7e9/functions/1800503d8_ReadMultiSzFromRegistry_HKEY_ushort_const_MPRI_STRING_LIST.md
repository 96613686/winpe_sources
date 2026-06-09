# ReadMultiSzFromRegistry(HKEY__ *,ushort const *,_MPRI_STRING_LIST *)

- ea: `0x1800503d8`
- end: `0x18005070e`
- name: `?ReadMultiSzFromRegistry@@YAKPEAUHKEY__@@PEBGPEAU_MPRI_STRING_LIST@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(HKEY hkey, const unsigned __int16 *, struct _MPRI_STRING_LIST *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004bf80`

## callees

- `0x1800503d8`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!malloc` at `0x180050513`
- `msvcrt!malloc` at `0x1800505ea`
- `msvcrt!malloc` at `0x180050513`
- `msvcrt!malloc` at `0x1800505ea`
- `msvcrt!free` at `0x1800506c0`
- `msvcrt!free` at `0x1800506ce`
- `msvcrt!free` at `0x1800506c0`
- `msvcrt!free` at `0x1800506ce`
- `msvcrt!wcscpy_s` at `0x180050634`
- `msvcrt!wcscpy_s` at `0x180050634`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800504af`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005059a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800504af`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005059a`

## string_xrefs

- `0x18005046a`: `ReadMultiSzFromRegistry`
- `0x1800504d2`: `ReadMultiSzFromRegistry`
- `0x180050541`: `ReadMultiSzFromRegistry`
- `0x180050673`: `ReadMultiSzFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadMultiSzFromRegistry(HKEY hkey, const unsigned __int16 *a2, struct _MPRI_STRING_LIST *a3)
{
  wchar_t *v5; // rsi
  void (*v6)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS ValueW; // eax
  char *pvData; // rbx
  unsigned int v9; // edi
  char *v10; // rcx
  __int64 v11; // rax
  const wchar_t *v12; // r14
  unsigned int i; // r15d
  __int64 v14; // rax
  unsigned int v15; // ebx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int64 v23; // [rsp+70h] [rbp-90h]
  int v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+7Ch] [rbp-84h]
  int v26; // [rsp+80h] [rbp-80h] BYREF
  char v27[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v18 = 0;
  pcbData = 0;
  v5 = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v24 = -1;
  v25 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v20, L"ReadMultiSzFromRegistry", &v18, v6);
  *(_OWORD *)a3 = 0;
  ValueW = RegGetValueW(hkey, 0, L"TenantIDs", 0x20u, 0, 0, &pcbData);
  v18 = ValueW;
  if ( !ValueW )
  {
    pvData = (char *)malloc(pcbData);
    if ( !pvData )
    {
      v18 = 8;
      if ( !(_QWORD)xmmword_180078C50 )
        goto LABEL_33;
      goto LABEL_9;
    }
    v18 = RegGetValueW(hkey, 0, L"TenantIDs", 0x20u, 0, pvData, &pcbData);
    v9 = 0;
    if ( v18 )
    {
      if ( (_QWORD)xmmword_180078C50 )
      {
        LOWORD(v26) = 0;
        LODWORD(pdwType) = v18;
        FormatRRASErrorString(
          &v26,
          L"%s: RegGetValue (%ws) failed: %d.",
          L"ReadMultiSzFromRegistry",
          L"TenantIDs",
          pdwType);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C50,
          &v26);
      }
    }
    else
    {
      v10 = pvData;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&pvData[2 * v11] );
      while ( v11 )
      {
        ++v9;
        v10 += 2 * v11 + 2;
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v10[2 * v11] );
      }
      v5 = (wchar_t *)malloc(1026LL * v9);
      if ( !v5 )
      {
        v18 = 8;
        if ( !(_QWORD)xmmword_180078C50 )
        {
LABEL_32:
          free(pvData);
          goto LABEL_33;
        }
LABEL_9:
        LOWORD(v26) = 0;
        LODWORD(pdwType) = 8;
        FormatRRASErrorString(&v26, L"%s: malloc (%ws) failed: %d.", L"ReadMultiSzFromRegistry", L"TenantIDs", pdwType);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C50,
          &v26);
        goto LABEL_28;
      }
      v12 = (const wchar_t *)pvData;
      for ( i = 0; i < v9; ++i )
      {
        wcscpy_s(&v5[513 * i], 0x201u, v12);
        v14 = -1;
        do
          ++v14;
        while ( v12[v14] );
        v12 += v14 + 1;
      }
    }
    *(_DWORD *)a3 = v9;
    *((_QWORD *)a3 + 1) = v5;
    goto LABEL_28;
  }
  if ( (_QWORD)xmmword_180078C50 )
  {
    LOWORD(v26) = 0;
    LODWORD(pdwType) = ValueW;
    FormatRRASErrorString(&v26, L"%s: RegGetValue (%ws) failed: %d.", L"ReadMultiSzFromRegistry", L"TenantIDs", pdwType);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v26);
  }
  pvData = 0;
LABEL_28:
  if ( v18 && v5 )
    free(v5);
  if ( pvData )
    goto LABEL_32;
LABEL_33:
  v15 = v18;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v20);
  return v15;
}

```

## disassembly

```asm
0x1800503d8  mov     [rsp-8+arg_8], rbx
0x1800503dd  push    rbp
0x1800503de  push    rsi
0x1800503df  push    rdi
0x1800503e0  push    r12
0x1800503e2  push    r13
0x1800503e4  push    r14
0x1800503e6  push    r15
0x1800503e8  lea     rbp, [rsp-790h]
0x1800503f0  sub     rsp, 890h
0x1800503f7  mov     rax, cs:__security_cookie
0x1800503fe  xor     rax, rsp
0x180050401  mov     [rbp+7C0h+var_40], rax
0x180050408  mov     r12, r8
0x18005040b  mov     rdi, rcx
0x18005040e  xor     r13d, r13d
0x180050411  mov     [rsp+8C0h+var_880], r13d
0x180050416  mov     [rsp+8C0h+var_87C], r13d
0x18005041b  mov     esi, r13d
0x18005041e  mov     [rbp+7C0h+var_840], r13d
0x180050422  xor     edx, edx; Val
0x180050424  mov     r8d, 7FCh; Size
0x18005042a  lea     rcx, [rbp+7C0h+var_83C]; void *
0x18005042e  call    memset_0
0x180050433  xorps   xmm0, xmm0
0x180050436  movdqu  [rsp+8C0h+var_870], xmm0
0x18005043c  mov     [rsp+8C0h+var_878], r13
0x180050441  xorps   xmm1, xmm1
0x180050444  movdqu  [rsp+8C0h+var_860], xmm1
0x18005044a  mov     [rsp+8C0h+var_850], r13
0x18005044f  mov     [rsp+8C0h+var_848], 0FFFFFFFFh
0x180050457  mov     [rsp+8C0h+var_844], r13d
0x18005045c  cmp     qword ptr cs:xmmword_180078C50+8, r13
0x180050463  jz      short loc_18005047B
0x180050465  lea     r8, [rsp+8C0h+var_880]; unsigned int *
0x18005046a  lea     rdx, aReadmultiszfro; "ReadMultiSzFromRegistry"
0x180050471  lea     rcx, [rsp+8C0h+var_878]; this
0x180050476  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005047b  xorps   xmm0, xmm0
0x18005047e  movups  xmmword ptr [r12], xmm0
0x180050483  lea     rax, [rsp+8C0h+var_87C]
0x180050488  mov     [rsp+8C0h+pcbData], rax; pcbData
0x18005048d  mov     [rsp+8C0h+pvData], r13; pvData
0x180050492  mov     [rsp+8C0h+pdwType], r13; pdwType
0x180050497  mov     r15d, 20h ; ' '
0x18005049d  mov     r9d, r15d; dwFlags
0x1800504a0  lea     r14, aTenantids; "TenantIDs"
0x1800504a7  mov     r8, r14; lpValue
0x1800504aa  xor     edx, edx; lpSubKey
0x1800504ac  mov     rcx, rdi; hkey
0x1800504af  call    cs:__imp_RegGetValueW
0x1800504b5  mov     [rsp+8C0h+var_880], eax
0x1800504b9  test    eax, eax
0x1800504bb  jz      short loc_18005050F
0x1800504bd  cmp     qword ptr cs:xmmword_180078C50, r13
0x1800504c4  jz      short loc_180050507
0x1800504c6  mov     word ptr [rbp+7C0h+var_840], r13w
0x1800504cb  mov     dword ptr [rsp+8C0h+pdwType], eax
0x1800504cf  mov     r9, r14
0x1800504d2  lea     r8, aReadmultiszfro; "ReadMultiSzFromRegistry"
0x1800504d9  lea     rdx, aSReggetvalueWs; "%s: RegGetValue (%ws) failed: %d."
0x1800504e0  lea     rcx, [rbp+7C0h+var_840]
0x1800504e4  call    FormatRRASErrorString
0x1800504e9  lea     r8, [rbp+7C0h+var_840]
0x1800504ed  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800504f4  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800504fb  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050507  mov     rbx, r13
0x18005050a  jmp     loc_1800506B1
0x18005050f  mov     ecx, [rsp+8C0h+var_87C]; Size
0x180050513  call    cs:__imp_malloc
0x180050519  mov     rbx, rax
0x18005051c  test    rax, rax
0x18005051f  jnz     short loc_18005057B
0x180050521  lea     edx, [rax+8]
0x180050524  mov     [rsp+8C0h+var_880], edx
0x180050528  cmp     qword ptr cs:xmmword_180078C50, r13
0x18005052f  jz      loc_1800506D4
0x180050535  mov     word ptr [rbp+7C0h+var_840], r13w
0x18005053a  mov     dword ptr [rsp+8C0h+pdwType], edx
0x18005053e  mov     r9, r14
0x180050541  lea     r8, aReadmultiszfro; "ReadMultiSzFromRegistry"
0x180050548  lea     rdx, aSMallocWsFaile; "%s: malloc (%ws) failed: %d."
0x18005054f  lea     rcx, [rbp+7C0h+var_840]
0x180050553  call    FormatRRASErrorString
0x180050558  lea     r8, [rbp+7C0h+var_840]
0x18005055c  mov     rdx, qword ptr cs:xmmword_180078C50
0x180050563  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18005056a  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050576  jmp     loc_1800506B1
0x18005057b  lea     rax, [rsp+8C0h+var_87C]
0x180050580  mov     [rsp+8C0h+pcbData], rax; pcbData
0x180050585  mov     [rsp+8C0h+pvData], rbx; pvData
0x18005058a  mov     [rsp+8C0h+pdwType], r13; pdwType
0x18005058f  mov     r9d, r15d; dwFlags
0x180050592  mov     r8, r14; lpValue
0x180050595  xor     edx, edx; lpSubKey
0x180050597  mov     rcx, rdi; hkey
0x18005059a  call    cs:__imp_RegGetValueW
0x1800505a0  mov     [rsp+8C0h+var_880], eax
0x1800505a4  mov     edi, r13d
0x1800505a7  test    eax, eax
0x1800505a9  jnz     loc_18005065A
0x1800505af  mov     rcx, rbx
0x1800505b2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800505b6  mov     rax, rdx
0x1800505b9  inc     rax
0x1800505bc  cmp     [rbx+rax*2], r13w
0x1800505c1  jnz     short loc_1800505B9
0x1800505c3  jmp     short loc_1800505DC
0x1800505c5  inc     edi
0x1800505c7  lea     rcx, [rcx+rax*2]
0x1800505cb  lea     rcx, [rcx+2]
0x1800505cf  mov     rax, rdx
0x1800505d2  inc     rax
0x1800505d5  cmp     [rcx+rax*2], r13w
0x1800505da  jnz     short loc_1800505D2
0x1800505dc  test    rax, rax
0x1800505df  jnz     short loc_1800505C5
0x1800505e1  mov     eax, edi
0x1800505e3  imul    rcx, rax, 402h; Size
0x1800505ea  call    cs:__imp_malloc
0x1800505f0  mov     rsi, rax
0x1800505f3  test    rax, rax
0x1800505f6  jnz     short loc_180050611
0x1800505f8  lea     edx, [rax+8]
0x1800505fb  mov     [rsp+8C0h+var_880], edx
0x1800505ff  cmp     qword ptr cs:xmmword_180078C50, r13
0x180050606  jz      loc_1800506CB
0x18005060c  jmp     loc_180050535
0x180050611  mov     r14, rbx
0x180050614  mov     r15d, r13d
0x180050617  test    edi, edi
0x180050619  jz      loc_1800506A8
0x18005061f  mov     eax, r15d
0x180050622  imul    rcx, rax, 402h
0x180050629  add     rcx, rsi; Destination
0x18005062c  mov     r8, r14; Source
0x18005062f  mov     edx, 201h; SizeInWords
0x180050634  call    cs:__imp_wcscpy_s
0x18005063a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005063e  inc     rax
0x180050641  cmp     [r14+rax*2], r13w
0x180050646  jnz     short loc_18005063E
0x180050648  lea     r14, [r14+rax*2]
0x18005064c  add     r14, 2
0x180050650  inc     r15d
0x180050653  cmp     r15d, edi
0x180050656  jb      short loc_18005061F
0x180050658  jmp     short loc_1800506A8
0x18005065a  cmp     qword ptr cs:xmmword_180078C50, r13
0x180050661  jz      short loc_1800506A8
0x180050663  mov     word ptr [rbp+7C0h+var_840], r13w
0x180050668  mov     eax, [rsp+8C0h+var_880]
0x18005066c  mov     dword ptr [rsp+8C0h+pdwType], eax
0x180050670  mov     r9, r14
0x180050673  lea     r8, aReadmultiszfro; "ReadMultiSzFromRegistry"
0x18005067a  lea     rdx, aSReggetvalueWs; "%s: RegGetValue (%ws) failed: %d."
0x180050681  lea     rcx, [rbp+7C0h+var_840]
0x180050685  call    FormatRRASErrorString
0x18005068a  lea     r8, [rbp+7C0h+var_840]
0x18005068e  mov     rdx, qword ptr cs:xmmword_180078C50
0x180050695  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18005069c  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800506a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506a8  mov     [r12], edi
0x1800506ac  mov     [r12+8], rsi
0x1800506b1  cmp     [rsp+8C0h+var_880], r13d
0x1800506b6  jz      short loc_1800506C6
0x1800506b8  test    rsi, rsi
0x1800506bb  jz      short loc_1800506C6
0x1800506bd  mov     rcx, rsi; Block
0x1800506c0  call    cs:__imp_free
0x1800506c6  test    rbx, rbx
0x1800506c9  jz      short loc_1800506D4
0x1800506cb  mov     rcx, rbx; Block
0x1800506ce  call    cs:__imp_free
0x1800506d4  mov     ebx, [rsp+8C0h+var_880]
0x1800506d8  lea     rcx, [rsp+8C0h+var_878]; this
0x1800506dd  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800506e2  mov     eax, ebx
0x1800506e4  mov     rcx, [rbp+7C0h+var_40]
0x1800506eb  xor     rcx, rsp; StackCookie
0x1800506ee  call    __security_check_cookie
0x1800506f3  mov     rbx, [rsp+8C0h+arg_8]
0x1800506fb  add     rsp, 890h
0x180050702  pop     r15
0x180050704  pop     r14
0x180050706  pop     r13
0x180050708  pop     r12
0x18005070a  pop     rdi
0x18005070b  pop     rsi
0x18005070c  pop     rbp
0x18005070d  retn
```
