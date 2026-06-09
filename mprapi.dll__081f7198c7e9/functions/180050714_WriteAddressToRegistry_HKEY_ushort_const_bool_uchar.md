# WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)

- ea: `0x180050714`
- end: `0x18005091d`
- name: `?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z`
- size: `521`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, char, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18004a9dc`

## callees

- `0x180050714`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!malloc` at `0x1800507cd`
- `msvcrt!malloc` at `0x18005086e`
- `msvcrt!malloc` at `0x1800507cd`
- `msvcrt!malloc` at `0x18005086e`
- `msvcrt!free` at `0x1800508dd`
- `msvcrt!free` at `0x1800508dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800508cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800508cb`
- `ntdll!RtlIpv4AddressToStringW` at `0x180050852`
- `ntdll!RtlIpv4AddressToStringW` at `0x180050852`
- `ntdll!RtlIpv6AddressToStringW` at `0x180050898`
- `ntdll!RtlIpv6AddressToStringW` at `0x180050898`

## string_xrefs

- `0x1800507a8`: `WriteAddressToRegistry`
- `0x1800507ff`: `WriteAddressToRegistry`

## pseudocode

```c
__int64 __fastcall WriteAddressToRegistry(HKEY hKey, LPCWSTR lpValueName, char a3, unsigned __int8 *a4)
{
  BYTE *lpData; // rdi
  WCHAR *v9; // rbx
  void (*v10)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  __int64 v11; // rsi
  BYTE *v12; // rax
  __int64 v13; // r14
  BYTE *v14; // rax
  unsigned int v15; // r14d
  unsigned int v16; // ebx
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+6Ch] [rbp-94h]
  int v25; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v18 = 0;
  lpData = 0;
  v9 = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = -1;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v19, L"WriteAddressToRegistry", &v18, v10);
  v11 = *(unsigned int *)a4;
  if ( a3 )
  {
    if ( (_DWORD)v11 )
    {
      v12 = (BYTE *)malloc(100 * v11);
      lpData = v12;
      if ( !v12 )
        goto LABEL_6;
      v9 = (WCHAR *)v12;
    }
    v13 = 0;
    if ( (_DWORD)v11 )
    {
      do
      {
        v9 = RtlIpv4AddressToStringW((const struct in_addr *)(*((_QWORD *)a4 + 1) + 4 * v13), v9) + 1;
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < *(_DWORD *)a4 );
LABEL_17:
      *v9 = 0;
      v18 = RegSetValueExW(hKey, lpValueName, 0, 7u, lpData, (_DWORD)v9 + 2 - (_DWORD)lpData);
    }
  }
  else
  {
    if ( (_DWORD)v11 )
    {
      v14 = (BYTE *)malloc(100 * v11);
      lpData = v14;
      if ( !v14 )
      {
LABEL_6:
        v18 = 8;
        if ( (_QWORD)xmmword_180078C50 )
        {
          LOWORD(v25) = 0;
          FormatRRASErrorString(&v25, L"%s: malloc (%ws) failed: %d.", L"WriteAddressToRegistry", lpValueName, 8);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180078C50,
            &v25);
        }
        goto LABEL_20;
      }
      v9 = (WCHAR *)v14;
    }
    v15 = 0;
    if ( (_DWORD)v11 )
    {
      do
        v9 = RtlIpv6AddressToStringW((const struct in6_addr *)(*((_QWORD *)a4 + 1) + 16LL * v15++), v9) + 1;
      while ( v15 < *(_DWORD *)a4 );
      goto LABEL_17;
    }
  }
  if ( lpData )
    free(lpData);
LABEL_20:
  v16 = v18;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return v16;
}

```

## disassembly

```asm
0x180050714  mov     [rsp-8+arg_10], rbx
0x180050719  push    rbp
0x18005071a  push    rsi
0x18005071b  push    rdi
0x18005071c  push    r12
0x18005071e  push    r13
0x180050720  push    r14
0x180050722  push    r15
0x180050724  lea     rbp, [rsp-790h]
0x18005072c  sub     rsp, 890h
0x180050733  mov     rax, cs:__security_cookie
0x18005073a  xor     rax, rsp
0x18005073d  mov     [rbp+7C0h+var_40], rax
0x180050744  mov     r15, r9
0x180050747  mov     r14b, r8b
0x18005074a  mov     r12, rdx
0x18005074d  mov     r13, rcx
0x180050750  mov     [rsp+8C0h+var_890], 0
0x180050758  xor     edi, edi
0x18005075a  xor     ebx, ebx
0x18005075c  xor     eax, eax
0x18005075e  mov     [rbp+7C0h+var_840], eax
0x180050761  xor     edx, edx; Val
0x180050763  mov     r8d, 7FCh; Size
0x180050769  lea     rcx, [rbp+7C0h+var_83C]; void *
0x18005076d  call    memset_0
0x180050772  xorps   xmm0, xmm0
0x180050775  movdqu  [rsp+8C0h+var_880], xmm0
0x18005077b  mov     [rsp+8C0h+var_888], rbx
0x180050780  xorps   xmm1, xmm1
0x180050783  movdqu  [rsp+8C0h+var_870], xmm1
0x180050789  mov     [rsp+8C0h+var_860], rbx
0x18005078e  mov     [rsp+8C0h+var_858], 0FFFFFFFFh
0x180050796  mov     [rsp+8C0h+var_854], ebx
0x18005079a  cmp     qword ptr cs:xmmword_180078C50+8, rbx
0x1800507a1  jz      short loc_1800507B9
0x1800507a3  lea     r8, [rsp+8C0h+var_890]; unsigned int *
0x1800507a8  lea     rdx, aWriteaddressto; "WriteAddressToRegistry"
0x1800507af  lea     rcx, [rsp+8C0h+var_888]; this
0x1800507b4  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800507b9  mov     esi, [r15]
0x1800507bc  test    r14b, r14b
0x1800507bf  jz      loc_180050866
0x1800507c5  test    esi, esi
0x1800507c7  jz      short loc_18005083C
0x1800507c9  imul    rcx, rsi, 64h ; 'd'; Size
0x1800507cd  call    cs:__imp_malloc
0x1800507d3  mov     rdi, rax
0x1800507d6  test    rax, rax
0x1800507d9  jnz     short loc_180050839
0x1800507db  mov     ecx, 8
0x1800507e0  mov     [rsp+8C0h+var_890], ecx
0x1800507e4  cmp     qword ptr cs:xmmword_180078C50, 0
0x1800507ec  jz      loc_1800508E3
0x1800507f2  xor     eax, eax
0x1800507f4  mov     word ptr [rbp+7C0h+var_840], ax
0x1800507f8  mov     dword ptr [rsp+8C0h+lpData], ecx
0x1800507fc  mov     r9, r12
0x1800507ff  lea     r8, aWriteaddressto; "WriteAddressToRegistry"
0x180050806  lea     rdx, aSMallocWsFaile; "%s: malloc (%ws) failed: %d."
0x18005080d  lea     rcx, [rbp+7C0h+var_840]
0x180050811  call    FormatRRASErrorString
0x180050816  lea     r8, [rbp+7C0h+var_840]
0x18005081a  mov     rdx, qword ptr cs:xmmword_180078C50
0x180050821  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180050828  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005082f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050834  jmp     loc_1800508E3
0x180050839  mov     rbx, rax
0x18005083c  xor     r14d, r14d
0x18005083f  test    esi, esi
0x180050841  jz      loc_1800508D5
0x180050847  mov     rax, [r15+8]
0x18005084b  lea     rcx, [rax+r14*4]; Addr
0x18005084f  mov     rdx, rbx; S
0x180050852  call    cs:__imp_RtlIpv4AddressToStringW
0x180050858  lea     rbx, [rax+2]
0x18005085c  inc     r14d
0x18005085f  cmp     r14d, [r15]
0x180050862  jb      short loc_180050847
0x180050864  jmp     short loc_1800508AA
0x180050866  test    esi, esi
0x180050868  jz      short loc_180050883
0x18005086a  imul    rcx, rsi, 64h ; 'd'; Size
0x18005086e  call    cs:__imp_malloc
0x180050874  mov     rdi, rax
0x180050877  test    rax, rax
0x18005087a  jz      loc_1800507DB
0x180050880  mov     rbx, rax
0x180050883  xor     r14d, r14d
0x180050886  test    esi, esi
0x180050888  jz      short loc_1800508D5
0x18005088a  mov     ecx, r14d
0x18005088d  shl     rcx, 4
0x180050891  add     rcx, [r15+8]; Addr
0x180050895  mov     rdx, rbx; S
0x180050898  call    cs:__imp_RtlIpv6AddressToStringW
0x18005089e  lea     rbx, [rax+2]
0x1800508a2  inc     r14d
0x1800508a5  cmp     r14d, [r15]
0x1800508a8  jb      short loc_18005088A
0x1800508aa  xor     eax, eax
0x1800508ac  mov     [rbx], ax
0x1800508af  add     rbx, 2
0x1800508b3  sub     ebx, edi
0x1800508b5  mov     [rsp+8C0h+cbData], ebx; cbData
0x1800508b9  mov     [rsp+8C0h+lpData], rdi; lpData
0x1800508be  lea     r9d, [rax+7]; dwType
0x1800508c2  xor     r8d, r8d; Reserved
0x1800508c5  mov     rdx, r12; lpValueName
0x1800508c8  mov     rcx, r13; hKey
0x1800508cb  call    cs:__imp_RegSetValueExW
0x1800508d1  mov     [rsp+8C0h+var_890], eax
0x1800508d5  test    rdi, rdi
0x1800508d8  jz      short loc_1800508E3
0x1800508da  mov     rcx, rdi; Block
0x1800508dd  call    cs:__imp_free
0x1800508e3  mov     ebx, [rsp+8C0h+var_890]
0x1800508e7  lea     rcx, [rsp+8C0h+var_888]; this
0x1800508ec  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800508f1  mov     eax, ebx
0x1800508f3  mov     rcx, [rbp+7C0h+var_40]
0x1800508fa  xor     rcx, rsp; StackCookie
0x1800508fd  call    __security_check_cookie
0x180050902  mov     rbx, [rsp+8C0h+arg_10]
0x18005090a  add     rsp, 890h
0x180050911  pop     r15
0x180050913  pop     r14
0x180050915  pop     r13
0x180050917  pop     r12
0x180050919  pop     rdi
0x18005091a  pop     rsi
0x18005091b  pop     rbp
0x18005091c  retn
```
