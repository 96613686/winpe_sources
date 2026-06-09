# NetpFetchLSASecretCredsEx(void *,int,ushort const *,ushort const *,ulong *,uchar * *)

- ea: `0x180029e00`
- end: `0x18002a07d`
- name: `?NetpFetchLSASecretCredsEx@@YAJPEAXHPEBG1PEAKPEAPEAE@Z`
- size: `637`
- prototype: `__int64 __fastcall(void *, int, unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180029dd0`
- `0x18002aa50`

## callees

- `0x180007278`
- `0x180029e00`
- `0x18002a3b0`
- `0x180089ab4`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029e70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029e70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a019`
- `LSASRV!LsarClose` at `0x18002a00b`
- `LSASRV!LsarClose` at `0x18002a00b`
- `LSASRV!LsarOpenSecret` at `0x180029efc`
- `LSASRV!LsarOpenSecret` at `0x180029efc`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18002a049`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18002a049`
- `LSASRV!LsarQuerySecret` at `0x180029f37`
- `LSASRV!LsarQuerySecret` at `0x180029f37`
- `ntdll!RtlAcquireResourceShared` at `0x180029e87`
- `ntdll!RtlAcquireResourceShared` at `0x180029e87`
- `ntdll!RtlInitUnicodeString` at `0x180029ee1`
- `ntdll!RtlInitUnicodeString` at `0x180029ee1`
- `ntdll!RtlReleaseResource` at `0x180029f5e`
- `ntdll!RtlReleaseResource` at `0x180029ff5`
- `ntdll!RtlReleaseResource` at `0x180029f5e`
- `ntdll!RtlReleaseResource` at `0x180029ff5`

## string_xrefs

- `0x180029f0b`: `LsarOpenSecret failed 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NetpFetchLSASecretCredsEx(
        void *a1,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  int v6; // r13d
  int v9; // r15d
  WCHAR *v10; // rsi
  unsigned int *v11; // r14
  unsigned __int8 **v12; // rdi
  int SecretName; // eax
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // eax
  unsigned __int8 *v17; // rax
  unsigned __int16 *v18; // rdx
  _BYTE *v19; // rdx
  __int64 v20; // r8
  void *v22; // [rsp+30h] [rbp-20h] BYREF
  PCWSTR SourceString; // [rsp+38h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  unsigned int *v25; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 *v26; // [rsp+A0h] [rbp+50h]
  unsigned __int16 *v27; // [rsp+A8h] [rbp+58h]

  v27 = a4;
  v26 = a3;
  v6 = 0;
  SourceString = 0;
  v22 = 0;
  v25 = 0;
  v9 = 0;
  DestinationString = 0;
  v10 = 0;
  NlPrintRoutine(0x40u, L"Entering NetpFetchLSASecretCredsEx\n");
  v11 = a5;
  if ( a5 )
    *a5 = 0;
  v12 = a6;
  if ( a6 )
    *a6 = 0;
  if ( a2 && GetCurrentThreadId() != dword_1800F0D10 )
  {
    RtlAcquireResourceShared(&NlGlobalGMSADPAPILock, 1u);
    v9 = 1;
  }
  if ( a1 )
  {
    v22 = a1;
  }
  else
  {
    v6 = 1;
    SecretName = NetpGetSecretName(a2, v26, v27, (unsigned __int16 **)&SourceString);
    v14 = SecretName;
    if ( SecretName < 0 )
    {
      NlPrintRoutine(0x40u, L"NetpGetSecretName failed 0x%08X\n", (unsigned int)SecretName);
      v10 = (WCHAR *)SourceString;
      goto LABEL_31;
    }
    v10 = (WCHAR *)SourceString;
    RtlInitUnicodeString(&DestinationString, SourceString);
    v15 = LsarOpenSecret(NlGlobalLsaPolicyHandle, &DestinationString, 2, &v22);
    v14 = v15;
    if ( v15 < 0 )
    {
      NlPrintRoutine(0x40u, L"LsarOpenSecret failed 0x%08X\n", (unsigned int)v15);
      goto LABEL_31;
    }
    a1 = v22;
  }
  v16 = LsarQuerySecret(a1, &v25, 0, 0, 0);
  v14 = v16;
  if ( v16 < 0 )
  {
    NlPrintRoutine(0x40u, L"LsarQuerySecret failed 0x%08X\n", (unsigned int)v16);
    goto LABEL_31;
  }
  if ( v9 )
  {
    RtlReleaseResource(&NlGlobalGMSADPAPILock);
    v9 = 0;
  }
  if ( !v25 || !*((_QWORD *)v25 + 1) || !*v25 )
  {
    v14 = -1073740943;
    v18 = L"LsarQuerySecret return NULL data 0x%08X\n";
    goto LABEL_30;
  }
  if ( v12 )
  {
    v17 = (unsigned __int8 *)(*((__int64 (**)(void))g_pLsaFunctions + 16))();
    *v12 = v17;
    if ( !v17 )
    {
      v14 = -1073741801;
      v18 = L"LsaIfAllocateLsaHeap failed 0x%08X\n";
LABEL_30:
      NlPrintRoutine(0x40u, v18, v14);
      goto LABEL_31;
    }
    memcpy_0(v17, *((const void **)v25 + 1), *v25);
  }
  if ( v11 )
    *v11 = *v25;
  v14 = 0;
LABEL_31:
  if ( v9 )
    RtlReleaseResource(&NlGlobalGMSADPAPILock);
  if ( v6 && v22 )
    LsarClose(&v22);
  if ( v10 )
    LocalFree(v10);
  if ( v25 )
  {
    v19 = (_BYTE *)*((_QWORD *)v25 + 1);
    if ( v19 )
    {
      v20 = *v25;
      if ( *v25 )
      {
        do
        {
          *v19++ = 0;
          --v20;
        }
        while ( v20 );
      }
    }
    LsaIFree_LSAPR_CR_CIPHER_VALUE(v25, v19);
  }
  NlPrintRoutine(0x40u, L"Exiting NetpFetchLSASecretCredsEx with Status 0x%08X\n", v14);
  return v14;
}

```

## disassembly

```asm
0x180029e00  mov     [rsp-38h+arg_8], rbx
0x180029e05  mov     [rsp-38h+arg_18], r9
0x180029e0a  mov     [rsp-38h+arg_10], r8
0x180029e0f  push    rbp
0x180029e10  push    rsi
0x180029e11  push    rdi
0x180029e12  push    r12
0x180029e14  push    r13
0x180029e16  push    r14
0x180029e18  push    r15
0x180029e1a  mov     rbp, rsp
0x180029e1d  sub     rsp, 50h
0x180029e21  xor     r13d, r13d
0x180029e24  mov     r12d, edx
0x180029e27  mov     rbx, rcx
0x180029e2a  mov     [rbp+SourceString], r13
0x180029e2e  xorps   xmm0, xmm0
0x180029e31  mov     [rbp+var_20], r13
0x180029e35  lea     rdx, aEnteringNetpfe; "Entering NetpFetchLSASecretCredsEx\n"
0x180029e3c  mov     [rbp+arg_0], r13
0x180029e40  lea     ecx, [r13+40h]; unsigned int
0x180029e44  mov     r15d, r13d
0x180029e47  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180029e4b  mov     esi, r13d
0x180029e4e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029e53  mov     r14, [rbp+arg_20]
0x180029e57  test    r14, r14
0x180029e5a  jz      short loc_180029E5F
0x180029e5c  mov     [r14], r13d
0x180029e5f  mov     rdi, [rbp+arg_28]
0x180029e63  test    rdi, rdi
0x180029e66  jz      short loc_180029E6B
0x180029e68  mov     [rdi], r13
0x180029e6b  test    r12d, r12d
0x180029e6e  jz      short loc_180029E93
0x180029e70  call    cs:__imp_GetCurrentThreadId
0x180029e76  cmp     eax, cs:dword_1800F0D10
0x180029e7c  jz      short loc_180029E93
0x180029e7e  mov     dl, 1; Wait
0x180029e80  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x180029e87  call    cs:__imp_RtlAcquireResourceShared
0x180029e8d  mov     r15d, 1
0x180029e93  test    rbx, rbx
0x180029e96  jnz     loc_180029F1D
0x180029e9c  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x180029ea0  lea     r9, [rbp+SourceString]; unsigned __int16 **
0x180029ea4  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x180029ea8  lea     r13d, [rbx+1]
0x180029eac  mov     ecx, r12d; int
0x180029eaf  call    ?NetpGetSecretName@@YAJHPEBG0PEAPEAG@Z; NetpGetSecretName(int,ushort const *,ushort const *,ushort * *)
0x180029eb4  mov     ebx, eax
0x180029eb6  test    eax, eax
0x180029eb8  jns     short loc_180029ED6
0x180029eba  mov     r8d, eax
0x180029ebd  lea     rdx, aNetpgetsecretn; "NetpGetSecretName failed 0x%08X\n"
0x180029ec4  lea     ecx, [r13+3Fh]; unsigned int
0x180029ec8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029ecd  mov     rsi, [rbp+SourceString]
0x180029ed1  jmp     loc_180029FE9
0x180029ed6  mov     rsi, [rbp+SourceString]
0x180029eda  lea     rcx, [rbp+DestinationString]; DestinationString
0x180029ede  mov     rdx, rsi; SourceString
0x180029ee1  call    cs:__imp_RtlInitUnicodeString
0x180029ee7  mov     rcx, cs:?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x180029eee  lea     r9, [rbp+var_20]
0x180029ef2  mov     r8d, 2
0x180029ef8  lea     rdx, [rbp+DestinationString]
0x180029efc  call    cs:__imp_LsarOpenSecret
0x180029f02  mov     ebx, eax
0x180029f04  test    eax, eax
0x180029f06  jns     short loc_180029F17
0x180029f08  mov     r8d, eax
0x180029f0b  lea     rdx, aLsaropensecret; "LsarOpenSecret failed 0x%08X\n"
0x180029f12  jmp     loc_180029FDF
0x180029f17  mov     rbx, [rbp+var_20]
0x180029f1b  jmp     short loc_180029F21
0x180029f1d  mov     [rbp+var_20], rbx
0x180029f21  xor     r9d, r9d
0x180029f24  mov     [rsp+50h+var_30], 0
0x180029f2d  xor     r8d, r8d
0x180029f30  lea     rdx, [rbp+arg_0]
0x180029f34  mov     rcx, rbx
0x180029f37  call    cs:__imp_LsarQuerySecret
0x180029f3d  mov     ebx, eax
0x180029f3f  test    eax, eax
0x180029f41  jns     short loc_180029F52
0x180029f43  mov     r8d, eax
0x180029f46  lea     rdx, aLsarquerysecre; "LsarQuerySecret failed 0x%08X\n"
0x180029f4d  jmp     loc_180029FDF
0x180029f52  test    r15d, r15d
0x180029f55  jz      short loc_180029F67
0x180029f57  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x180029f5e  call    cs:__imp_RtlReleaseResource
0x180029f64  xor     r15d, r15d
0x180029f67  mov     rax, [rbp+arg_0]
0x180029f6b  test    rax, rax
0x180029f6e  jz      short loc_180029FD0
0x180029f70  cmp     qword ptr [rax+8], 0
0x180029f75  jz      short loc_180029FD0
0x180029f77  mov     ecx, [rax]
0x180029f79  test    ecx, ecx
0x180029f7b  jz      short loc_180029FD0
0x180029f7d  test    rdi, rdi
0x180029f80  jz      short loc_180029FBE
0x180029f82  mov     rax, cs:?g_pLsaFunctions@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pLsaFunctions
0x180029f89  mov     rax, [rax+80h]
0x180029f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f95  mov     [rdi], rax
0x180029f98  test    rax, rax
0x180029f9b  jnz     short loc_180029FAB
0x180029f9d  mov     ebx, 0C0000017h
0x180029fa2  lea     rdx, aLsaifallocatel; "LsaIfAllocateLsaHeap failed 0x%08X\n"
0x180029fa9  jmp     short loc_180029FDC
0x180029fab  mov     rdx, [rbp+arg_0]
0x180029faf  mov     rcx, rax; void *
0x180029fb2  mov     r8d, [rdx]; Size
0x180029fb5  mov     rdx, [rdx+8]; Src
0x180029fb9  call    memcpy_0
0x180029fbe  test    r14, r14
0x180029fc1  jz      short loc_180029FCC
0x180029fc3  mov     rax, [rbp+arg_0]
0x180029fc7  mov     ecx, [rax]
0x180029fc9  mov     [r14], ecx
0x180029fcc  xor     ebx, ebx
0x180029fce  jmp     short loc_180029FE9
0x180029fd0  mov     ebx, 0C0000371h
0x180029fd5  lea     rdx, aLsarquerysecre_0; "LsarQuerySecret return NULL data 0x%08X"...
0x180029fdc  mov     r8d, ebx
0x180029fdf  mov     ecx, 40h ; '@'; unsigned int
0x180029fe4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029fe9  test    r15d, r15d
0x180029fec  jz      short loc_180029FFB
0x180029fee  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x180029ff5  call    cs:__imp_RtlReleaseResource
0x180029ffb  test    r13d, r13d
0x180029ffe  jz      short loc_18002A011
0x18002a000  cmp     [rbp+var_20], 0
0x18002a005  jz      short loc_18002A011
0x18002a007  lea     rcx, [rbp+var_20]
0x18002a00b  call    cs:__imp_LsarClose
0x18002a011  test    rsi, rsi
0x18002a014  jz      short loc_18002A01F
0x18002a016  mov     rcx, rsi; hMem
0x18002a019  call    cs:__imp_LocalFree
0x18002a01f  mov     rax, [rbp+arg_0]
0x18002a023  test    rax, rax
0x18002a026  jz      short loc_18002A04F
0x18002a028  mov     rdx, [rax+8]
0x18002a02c  test    rdx, rdx
0x18002a02f  jz      short loc_18002A045
0x18002a031  mov     r8d, [rax]
0x18002a034  test    r8, r8
0x18002a037  jz      short loc_18002A045
0x18002a039  mov     byte ptr [rdx], 0
0x18002a03c  inc     rdx
0x18002a03f  sub     r8, 1
0x18002a043  jnz     short loc_18002A039
0x18002a045  mov     rcx, [rbp+arg_0]
0x18002a049  call    cs:__imp_LsaIFree_LSAPR_CR_CIPHER_VALUE
0x18002a04f  mov     r8d, ebx
0x18002a052  lea     rdx, aExitingNetpfet; "Exiting NetpFetchLSASecretCredsEx with "...
0x18002a059  mov     ecx, 40h ; '@'; unsigned int
0x18002a05e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002a063  mov     eax, ebx
0x18002a065  mov     rbx, [rsp+50h+arg_8]
0x18002a06d  add     rsp, 50h
0x18002a071  pop     r15
0x18002a073  pop     r14
0x18002a075  pop     r13
0x18002a077  pop     r12
0x18002a079  pop     rdi
0x18002a07a  pop     rsi
0x18002a07b  pop     rbp
0x18002a07c  retn
```
