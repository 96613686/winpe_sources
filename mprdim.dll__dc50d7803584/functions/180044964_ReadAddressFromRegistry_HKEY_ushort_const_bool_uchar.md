# ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)

- ea: `0x180044964`
- end: `0x180044d03`
- name: `?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z`
- size: `927`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpValue, bool, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800409ac`

## callees

- `0x180044924`
- `0x180044964`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!malloc` at `0x180044a99`
- `msvcrt!malloc` at `0x180044b59`
- `msvcrt!malloc` at `0x180044a99`
- `msvcrt!malloc` at `0x180044b59`
- `msvcrt!free` at `0x180044cb5`
- `msvcrt!free` at `0x180044cc3`
- `msvcrt!free` at `0x180044cb5`
- `msvcrt!free` at `0x180044cc3`
- `ntdll!RtlIpv6StringToAddressW` at `0x180044bfd`
- `ntdll!RtlIpv6StringToAddressW` at `0x180044bfd`
- `ntdll!RtlIpv4StringToAddressW` at `0x180044bc0`
- `ntdll!RtlIpv4StringToAddressW` at `0x180044bc0`
- `KERNEL32!RegGetValueW` at `0x180044a35`
- `KERNEL32!RegGetValueW` at `0x180044b26`
- `KERNEL32!RegGetValueW` at `0x180044a35`
- `KERNEL32!RegGetValueW` at `0x180044b26`

## string_xrefs

- `0x1800449fa`: `ReadAddressFromRegistry`
- `0x180044a58`: `ReadAddressFromRegistry`
- `0x180044ad1`: `ReadAddressFromRegistry`
- `0x180044b82`: `ReadAddressFromRegistry`
- `0x180044c67`: `ReadAddressFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadAddressFromRegistry(HKEY hkey, LPCWSTR lpValue, char a3, unsigned __int8 *a4)
{
  unsigned int v8; // r15d
  struct in_addr *v9; // rdi
  void (*v10)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS ValueW; // eax
  void *pvData; // rbx
  unsigned int MultiSzElementCount; // eax
  unsigned int v14; // r14d
  size_t v15; // rcx
  const WCHAR *v16; // rsi
  LONG v17; // eax
  __int64 v18; // rax
  unsigned int v19; // ebx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR Terminator; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+58h] [rbp-A8h]
  __int128 v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+84h] [rbp-7Ch]
  int v32; // [rsp+90h] [rbp-70h] BYREF
  char v33[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v8 = 0;
  v23 = 0;
  pcbData = 0;
  v9 = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v27 = 0;
  v26 = 0;
  v28 = 0;
  v29 = 0;
  v30 = -1;
  v31 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v26, L"ReadAddressFromRegistry", &v23, v10);
  *(_OWORD *)a4 = 0;
  ValueW = RegGetValueW(hkey, 0, lpValue, 0x20u, 0, 0, &pcbData);
  v23 = ValueW;
  if ( !ValueW )
  {
    pvData = malloc(pcbData);
    if ( !pvData )
    {
      v23 = 8;
      if ( !(_QWORD)xmmword_180071090 )
        goto LABEL_38;
      LOWORD(v32) = 0;
      LODWORD(pdwType) = 8;
      FormatRRASErrorString(&v32, L"%s: malloc (%ws) failed: %d.", L"ReadAddressFromRegistry", lpValue, pdwType);
      goto LABEL_10;
    }
    v23 = RegGetValueW(hkey, 0, lpValue, 0x20u, 0, pvData, &pcbData);
    if ( v23 )
    {
      v14 = 0;
      if ( (_QWORD)xmmword_180071090 )
      {
        LOWORD(v32) = 0;
        LODWORD(pdwTypea) = v23;
        FormatRRASErrorString(&v32, L"%s: RegGetValue (%ws) failed: %d.", L"ReadAddressFromRegistry", lpValue, pdwTypea);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180071090,
          &v32);
      }
    }
    else
    {
      Terminator = 0;
      MultiSzElementCount = GetMultiSzElementCount((unsigned __int16 *)pvData);
      v14 = MultiSzElementCount;
      if ( a3 )
        v15 = 4LL * MultiSzElementCount;
      else
        v15 = 16LL * MultiSzElementCount;
      v9 = (struct in_addr *)malloc(v15);
      if ( !v9 )
      {
        v23 = 8;
        if ( !(_QWORD)xmmword_180071090 )
        {
LABEL_37:
          free(pvData);
          goto LABEL_38;
        }
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v32, L"%s: malloc failed. %d.", L"ReadAddressFromRegistry");
LABEL_10:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180071090,
          &v32);
        goto LABEL_33;
      }
      v16 = (const WCHAR *)pvData;
      while ( v8 < v14 )
      {
        if ( a3 )
        {
          v17 = RtlIpv4StringToAddressW(v16, 1u, &Terminator, &v9[v8]);
          v23 = v17;
          if ( v17 )
          {
            if ( !(_QWORD)xmmword_180071090 )
              goto LABEL_33;
            LOWORD(v32) = 0;
            LODWORD(pdwTypea) = v17;
            FormatRRASErrorString(
              &v32,
              L"%s: RtlIpv4StringToAddress failed for (%ws) : %d.",
              L"ReadAddressFromRegistry",
              v16,
              pdwTypea);
            goto LABEL_10;
          }
        }
        else
        {
          v23 = RtlIpv6StringToAddressW(v16, &Terminator, (struct in6_addr *)&v9[4 * v8]);
          if ( v23 )
          {
            if ( !(_QWORD)xmmword_180071090 )
              goto LABEL_33;
            LOWORD(v32) = 0;
            LODWORD(pdwTypea) = v23;
            FormatRRASErrorString(
              &v32,
              L"%s: RtlIpv6StringToAddress failed for (%ws) : %d.",
              L"ReadAddressFromRegistry",
              v16,
              pdwTypea);
            goto LABEL_10;
          }
        }
        v18 = -1;
        do
          ++v18;
        while ( v16[v18] );
        v16 += v18 + 1;
        ++v8;
      }
    }
    *(_DWORD *)a4 = v14;
    *((_QWORD *)a4 + 1) = v9;
    goto LABEL_33;
  }
  if ( (_QWORD)xmmword_180071090 )
  {
    LOWORD(v32) = 0;
    LODWORD(pdwType) = ValueW;
    FormatRRASErrorString(&v32, L"%s: RegGetValue (%ws) failed: %d.", L"ReadAddressFromRegistry", lpValue, pdwType);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v32);
  }
  pvData = 0;
LABEL_33:
  if ( v23 && v9 )
    free(v9);
  if ( pvData )
    goto LABEL_37;
LABEL_38:
  v19 = v23;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v26);
  return v19;
}

```

## disassembly

```asm
0x180044964  mov     [rsp-8+arg_10], rbx
0x180044969  push    rbp
0x18004496a  push    rsi
0x18004496b  push    rdi
0x18004496c  push    r12
0x18004496e  push    r13
0x180044970  push    r14
0x180044972  push    r15
0x180044974  lea     rbp, [rsp-7A0h]
0x18004497c  sub     rsp, 8A0h
0x180044983  mov     rax, cs:__security_cookie
0x18004498a  xor     rax, rsp
0x18004498d  mov     [rbp+7D0h+var_40], rax
0x180044994  mov     r12, r9
0x180044997  mov     r13b, r8b
0x18004499a  mov     rsi, rdx
0x18004499d  mov     r14, rcx
0x1800449a0  xor     r15d, r15d
0x1800449a3  mov     [rsp+8D0h+var_890], r15d
0x1800449a8  mov     [rsp+8D0h+var_88C], r15d
0x1800449ad  mov     edi, r15d
0x1800449b0  mov     [rbp+7D0h+var_840], r15d
0x1800449b4  xor     edx, edx; Val
0x1800449b6  mov     r8d, 7FCh; Size
0x1800449bc  lea     rcx, [rbp+7D0h+var_83C]; void *
0x1800449c0  call    memset_0
0x1800449c5  xorps   xmm0, xmm0
0x1800449c8  movdqu  [rsp+8D0h+var_878], xmm0
0x1800449ce  mov     [rsp+8D0h+var_880], r15
0x1800449d3  xorps   xmm1, xmm1
0x1800449d6  movdqu  [rsp+8D0h+var_868], xmm1
0x1800449dc  mov     [rsp+8D0h+var_858], r15
0x1800449e1  mov     [rbp+7D0h+var_850], 0FFFFFFFFh
0x1800449e8  mov     [rbp+7D0h+var_84C], r15d
0x1800449ec  cmp     qword ptr cs:xmmword_180071090+8, r15
0x1800449f3  jz      short loc_180044A0B
0x1800449f5  lea     r8, [rsp+8D0h+var_890]; unsigned int *
0x1800449fa  lea     rdx, aReadaddressfro; "ReadAddressFromRegistry"
0x180044a01  lea     rcx, [rsp+8D0h+var_880]; this
0x180044a06  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180044a0b  xorps   xmm0, xmm0
0x180044a0e  movups  xmmword ptr [r12], xmm0
0x180044a13  lea     rax, [rsp+8D0h+var_88C]
0x180044a18  mov     [rsp+8D0h+pcbData], rax; pcbData
0x180044a1d  mov     [rsp+8D0h+pvData], r15; pvData
0x180044a22  mov     [rsp+8D0h+pdwType], r15; pdwType
0x180044a27  mov     r9d, 20h ; ' '; dwFlags
0x180044a2d  mov     r8, rsi; lpValue
0x180044a30  xor     edx, edx; lpSubKey
0x180044a32  mov     rcx, r14; hkey
0x180044a35  call    cs:__imp_RegGetValueW
0x180044a3b  mov     [rsp+8D0h+var_890], eax
0x180044a3f  test    eax, eax
0x180044a41  jz      short loc_180044A95
0x180044a43  cmp     qword ptr cs:xmmword_180071090, r15
0x180044a4a  jz      short loc_180044A8D
0x180044a4c  mov     word ptr [rbp+7D0h+var_840], r15w
0x180044a51  mov     dword ptr [rsp+8D0h+pdwType], eax
0x180044a55  mov     r9, rsi
0x180044a58  lea     r8, aReadaddressfro; "ReadAddressFromRegistry"
0x180044a5f  lea     rdx, aSReggetvalueWs; "%s: RegGetValue (%ws) failed: %d."
0x180044a66  lea     rcx, [rbp+7D0h+var_840]
0x180044a6a  call    FormatRRASErrorString
0x180044a6f  lea     r8, [rbp+7D0h+var_840]
0x180044a73  mov     rdx, qword ptr cs:xmmword_180071090
0x180044a7a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044a81  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180044a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a8d  mov     rbx, r15
0x180044a90  jmp     loc_180044CA5
0x180044a95  mov     ecx, [rsp+8D0h+var_88C]; Size
0x180044a99  call    cs:__imp_malloc
0x180044a9f  mov     rbx, rax
0x180044aa2  test    rax, rax
0x180044aa5  jnz     short loc_180044B04
0x180044aa7  lea     r9d, [rax+8]
0x180044aab  mov     [rsp+8D0h+var_890], r9d
0x180044ab0  cmp     qword ptr cs:xmmword_180071090, r15
0x180044ab7  jz      loc_180044CC9
0x180044abd  mov     word ptr [rbp+7D0h+var_840], r15w
0x180044ac2  mov     dword ptr [rsp+8D0h+pdwType], r9d
0x180044ac7  lea     rdx, aSMallocWsFaile; "%s: malloc (%ws) failed: %d."
0x180044ace  mov     r9, rsi
0x180044ad1  lea     r8, aReadaddressfro; "ReadAddressFromRegistry"
0x180044ad8  lea     rcx, [rbp+7D0h+var_840]
0x180044adc  call    FormatRRASErrorString
0x180044ae1  lea     r8, [rbp+7D0h+var_840]
0x180044ae5  mov     rdx, qword ptr cs:xmmword_180071090
0x180044aec  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044af3  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180044afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044aff  jmp     loc_180044CA5
0x180044b04  lea     rax, [rsp+8D0h+var_88C]
0x180044b09  mov     [rsp+8D0h+pcbData], rax; pcbData
0x180044b0e  mov     [rsp+8D0h+pvData], rbx; pvData
0x180044b13  mov     [rsp+8D0h+pdwType], r15; pdwType
0x180044b18  mov     r9d, 20h ; ' '; dwFlags
0x180044b1e  mov     r8, rsi; lpValue
0x180044b21  xor     edx, edx; lpSubKey
0x180044b23  mov     rcx, r14; hkey
0x180044b26  call    cs:__imp_RegGetValueW
0x180044b2c  mov     [rsp+8D0h+var_890], eax
0x180044b30  test    eax, eax
0x180044b32  jnz     loc_180044C4B
0x180044b38  mov     [rsp+8D0h+Terminator], r15
0x180044b3d  mov     rcx, rbx; unsigned __int16 *
0x180044b40  call    ?GetMultiSzElementCount@@YAKPEAG@Z; GetMultiSzElementCount(ushort *)
0x180044b45  mov     r14d, eax
0x180044b48  mov     ecx, eax
0x180044b4a  test    r13b, r13b
0x180044b4d  jz      short loc_180044B55
0x180044b4f  shl     rcx, 2
0x180044b53  jmp     short loc_180044B59
0x180044b55  shl     rcx, 4; Size
0x180044b59  call    cs:__imp_malloc
0x180044b5f  mov     rdi, rax
0x180044b62  test    rax, rax
0x180044b65  jnz     short loc_180044B9E
0x180044b67  lea     r9d, [rax+8]
0x180044b6b  mov     [rsp+8D0h+var_890], r9d
0x180044b70  cmp     qword ptr cs:xmmword_180071090, r15
0x180044b77  jz      loc_180044CC0
0x180044b7d  mov     word ptr [rbp+7D0h+var_840], r15w
0x180044b82  lea     r8, aReadaddressfro; "ReadAddressFromRegistry"
0x180044b89  lea     rdx, aSMallocFailedD; "%s: malloc failed. %d."
0x180044b90  lea     rcx, [rbp+7D0h+var_840]
0x180044b94  call    FormatRRASErrorString
0x180044b99  jmp     loc_180044AE1
0x180044b9e  mov     rsi, rbx
0x180044ba1  cmp     r15d, r14d
0x180044ba4  jnb     loc_180044C9C
0x180044baa  mov     r8d, r15d
0x180044bad  mov     rcx, rsi; S
0x180044bb0  test    r13b, r13b
0x180044bb3  jz      short loc_180044BF1
0x180044bb5  lea     r9, [rdi+r8*4]; Addr
0x180044bb9  lea     r8, [rsp+8D0h+Terminator]; Terminator
0x180044bbe  mov     dl, 1; Strict
0x180044bc0  call    cs:__imp_RtlIpv4StringToAddressW
0x180044bc6  mov     [rsp+8D0h+var_890], eax
0x180044bca  xor     ecx, ecx
0x180044bcc  test    eax, eax
0x180044bce  jz      short loc_180044C0D
0x180044bd0  cmp     qword ptr cs:xmmword_180071090, rcx
0x180044bd7  jz      loc_180044CA5
0x180044bdd  mov     word ptr [rbp+7D0h+var_840], cx
0x180044be1  mov     dword ptr [rsp+8D0h+pdwType], eax
0x180044be5  lea     rdx, aSRtlipv4string; "%s: RtlIpv4StringToAddress failed for ("...
0x180044bec  jmp     loc_180044ACE
0x180044bf1  shl     r8, 4
0x180044bf5  add     r8, rdi; Addr
0x180044bf8  lea     rdx, [rsp+8D0h+Terminator]; Terminator
0x180044bfd  call    cs:__imp_RtlIpv6StringToAddressW
0x180044c03  mov     [rsp+8D0h+var_890], eax
0x180044c07  xor     ecx, ecx
0x180044c09  test    eax, eax
0x180044c0b  jnz     short loc_180044C2A
0x180044c0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044c11  inc     rax
0x180044c14  cmp     [rsi+rax*2], cx
0x180044c18  jnz     short loc_180044C11
0x180044c1a  lea     rsi, [rsi+rax*2]
0x180044c1e  add     rsi, 2
0x180044c22  inc     r15d
0x180044c25  jmp     loc_180044BA1
0x180044c2a  cmp     qword ptr cs:xmmword_180071090, rcx
0x180044c31  jz      short loc_180044CA5
0x180044c33  mov     word ptr [rbp+7D0h+var_840], cx
0x180044c37  mov     eax, [rsp+8D0h+var_890]
0x180044c3b  mov     dword ptr [rsp+8D0h+pdwType], eax
0x180044c3f  lea     rdx, aSRtlipv6string; "%s: RtlIpv6StringToAddress failed for ("...
0x180044c46  jmp     loc_180044ACE
0x180044c4b  mov     r14d, r15d
0x180044c4e  cmp     qword ptr cs:xmmword_180071090, r15
0x180044c55  jz      short loc_180044C9C
0x180044c57  mov     word ptr [rbp+7D0h+var_840], r15w
0x180044c5c  mov     eax, [rsp+8D0h+var_890]
0x180044c60  mov     dword ptr [rsp+8D0h+pdwType], eax
0x180044c64  mov     r9, rsi
0x180044c67  lea     r8, aReadaddressfro; "ReadAddressFromRegistry"
0x180044c6e  lea     rdx, aSReggetvalueWs; "%s: RegGetValue (%ws) failed: %d."
0x180044c75  lea     rcx, [rbp+7D0h+var_840]
0x180044c79  call    FormatRRASErrorString
0x180044c7e  lea     r8, [rbp+7D0h+var_840]
0x180044c82  mov     rdx, qword ptr cs:xmmword_180071090
0x180044c89  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044c90  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180044c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c9c  mov     [r12], r14d
0x180044ca0  mov     [r12+8], rdi
0x180044ca5  xor     esi, esi
0x180044ca7  cmp     [rsp+8D0h+var_890], esi
0x180044cab  jz      short loc_180044CBB
0x180044cad  test    rdi, rdi
0x180044cb0  jz      short loc_180044CBB
0x180044cb2  mov     rcx, rdi; Block
0x180044cb5  call    cs:__imp_free
0x180044cbb  test    rbx, rbx
0x180044cbe  jz      short loc_180044CC9
0x180044cc0  mov     rcx, rbx; Block
0x180044cc3  call    cs:__imp_free
0x180044cc9  mov     ebx, [rsp+8D0h+var_890]
0x180044ccd  lea     rcx, [rsp+8D0h+var_880]; this
0x180044cd2  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180044cd7  mov     eax, ebx
0x180044cd9  mov     rcx, [rbp+7D0h+var_40]
0x180044ce0  xor     rcx, rsp; StackCookie
0x180044ce3  call    __security_check_cookie
0x180044ce8  mov     rbx, [rsp+8D0h+arg_10]
0x180044cf0  add     rsp, 8A0h
0x180044cf7  pop     r15
0x180044cf9  pop     r14
0x180044cfb  pop     r13
0x180044cfd  pop     r12
0x180044cff  pop     rdi
0x180044d00  pop     rsi
0x180044d01  pop     rbp
0x180044d02  retn
```
