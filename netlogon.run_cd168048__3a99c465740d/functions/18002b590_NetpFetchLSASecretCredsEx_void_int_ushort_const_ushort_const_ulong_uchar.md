# NetpFetchLSASecretCredsEx(void *,int,ushort const *,ushort const *,ulong *,uchar * *)

- ea: `0x18002b590`
- end: `0x18002b84a`
- name: `?NetpFetchLSASecretCredsEx@@YAJPEAXHPEBG1PEAKPEAPEAE@Z`
- size: `698`
- prototype: `__int64 __fastcall(void *, int, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b560`
- `0x18002c310`

## callees

- `0x180007518`
- `0x18002b590`
- `0x18002bbe0`
- `0x180090204`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b600`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b600`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b7d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b7d9`
- `LSASRV!LsarClose` at `0x18002b7c5`
- `LSASRV!LsarClose` at `0x18002b7c5`
- `LSASRV!LsarOpenSecret` at `0x18002b69e`
- `LSASRV!LsarOpenSecret` at `0x18002b69e`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18002b80f`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18002b80f`
- `LSASRV!LsarQuerySecret` at `0x18002b6df`
- `LSASRV!LsarQuerySecret` at `0x18002b6df`
- `ntdll!RtlAcquireResourceShared` at `0x18002b61d`
- `ntdll!RtlAcquireResourceShared` at `0x18002b61d`
- `ntdll!RtlInitUnicodeString` at `0x18002b67d`
- `ntdll!RtlInitUnicodeString` at `0x18002b67d`
- `ntdll!RtlReleaseResource` at `0x18002b70c`
- `ntdll!RtlReleaseResource` at `0x18002b7a9`
- `ntdll!RtlReleaseResource` at `0x18002b70c`
- `ntdll!RtlReleaseResource` at `0x18002b7a9`

## string_xrefs

- `0x18002b6b3`: `LsarOpenSecret failed 0x%08X\n`

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
  if ( a2 && GetCurrentThreadId() != dword_1800F7D10 )
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
0x18002b590  mov     [rsp-38h+arg_8], rbx
0x18002b595  mov     [rsp-38h+arg_18], r9
0x18002b59a  mov     [rsp-38h+arg_10], r8
0x18002b59f  push    rbp
0x18002b5a0  push    rsi
0x18002b5a1  push    rdi
0x18002b5a2  push    r12
0x18002b5a4  push    r13
0x18002b5a6  push    r14
0x18002b5a8  push    r15
0x18002b5aa  mov     rbp, rsp
0x18002b5ad  sub     rsp, 50h
0x18002b5b1  xor     r13d, r13d
0x18002b5b4  mov     r12d, edx
0x18002b5b7  mov     rbx, rcx
0x18002b5ba  mov     [rbp+SourceString], r13
0x18002b5be  xorps   xmm0, xmm0
0x18002b5c1  mov     [rbp+var_20], r13
0x18002b5c5  lea     rdx, aEnteringNetpfe; "Entering NetpFetchLSASecretCredsEx\n"
0x18002b5cc  mov     [rbp+arg_0], r13
0x18002b5d0  lea     ecx, [r13+40h]; unsigned int
0x18002b5d4  mov     r15d, r13d
0x18002b5d7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002b5db  mov     esi, r13d
0x18002b5de  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b5e3  mov     r14, [rbp+arg_20]
0x18002b5e7  test    r14, r14
0x18002b5ea  jz      short loc_18002B5EF
0x18002b5ec  mov     [r14], r13d
0x18002b5ef  mov     rdi, [rbp+arg_28]
0x18002b5f3  test    rdi, rdi
0x18002b5f6  jz      short loc_18002B5FB
0x18002b5f8  mov     [rdi], r13
0x18002b5fb  test    r12d, r12d
0x18002b5fe  jz      short loc_18002B62F
0x18002b600  call    cs:__imp_GetCurrentThreadId
0x18002b607  nop     dword ptr [rax+rax+00h]
0x18002b60c  cmp     eax, cs:dword_1800F7D10
0x18002b612  jz      short loc_18002B62F
0x18002b614  mov     dl, 1; Wait
0x18002b616  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002b61d  call    cs:__imp_RtlAcquireResourceShared
0x18002b624  nop     dword ptr [rax+rax+00h]
0x18002b629  mov     r15d, 1
0x18002b62f  test    rbx, rbx
0x18002b632  jnz     loc_18002B6C5
0x18002b638  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18002b63c  lea     r9, [rbp+SourceString]; unsigned __int16 **
0x18002b640  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18002b644  lea     r13d, [rbx+1]
0x18002b648  mov     ecx, r12d; int
0x18002b64b  call    ?NetpGetSecretName@@YAJHPEBG0PEAPEAG@Z; NetpGetSecretName(int,ushort const *,ushort const *,ushort * *)
0x18002b650  mov     ebx, eax
0x18002b652  test    eax, eax
0x18002b654  jns     short loc_18002B672
0x18002b656  mov     r8d, eax
0x18002b659  lea     rdx, aNetpgetsecretn; "NetpGetSecretName failed 0x%08X\n"
0x18002b660  lea     ecx, [r13+3Fh]; unsigned int
0x18002b664  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b669  mov     rsi, [rbp+SourceString]
0x18002b66d  jmp     loc_18002B79D
0x18002b672  mov     rsi, [rbp+SourceString]
0x18002b676  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002b67a  mov     rdx, rsi; SourceString
0x18002b67d  call    cs:__imp_RtlInitUnicodeString
0x18002b684  nop     dword ptr [rax+rax+00h]
0x18002b689  mov     rcx, cs:?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x18002b690  lea     r9, [rbp+var_20]
0x18002b694  mov     r8d, 2
0x18002b69a  lea     rdx, [rbp+DestinationString]
0x18002b69e  call    cs:__imp_LsarOpenSecret
0x18002b6a5  nop     dword ptr [rax+rax+00h]
0x18002b6aa  mov     ebx, eax
0x18002b6ac  test    eax, eax
0x18002b6ae  jns     short loc_18002B6BF
0x18002b6b0  mov     r8d, eax
0x18002b6b3  lea     rdx, aLsaropensecret; "LsarOpenSecret failed 0x%08X\n"
0x18002b6ba  jmp     loc_18002B793
0x18002b6bf  mov     rbx, [rbp+var_20]
0x18002b6c3  jmp     short loc_18002B6C9
0x18002b6c5  mov     [rbp+var_20], rbx
0x18002b6c9  xor     r9d, r9d
0x18002b6cc  mov     [rsp+50h+var_30], 0
0x18002b6d5  xor     r8d, r8d
0x18002b6d8  lea     rdx, [rbp+arg_0]
0x18002b6dc  mov     rcx, rbx
0x18002b6df  call    cs:__imp_LsarQuerySecret
0x18002b6e6  nop     dword ptr [rax+rax+00h]
0x18002b6eb  mov     ebx, eax
0x18002b6ed  test    eax, eax
0x18002b6ef  jns     short loc_18002B700
0x18002b6f1  mov     r8d, eax
0x18002b6f4  lea     rdx, aLsarquerysecre; "LsarQuerySecret failed 0x%08X\n"
0x18002b6fb  jmp     loc_18002B793
0x18002b700  test    r15d, r15d
0x18002b703  jz      short loc_18002B71B
0x18002b705  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002b70c  call    cs:__imp_RtlReleaseResource
0x18002b713  nop     dword ptr [rax+rax+00h]
0x18002b718  xor     r15d, r15d
0x18002b71b  mov     rax, [rbp+arg_0]
0x18002b71f  test    rax, rax
0x18002b722  jz      short loc_18002B784
0x18002b724  cmp     qword ptr [rax+8], 0
0x18002b729  jz      short loc_18002B784
0x18002b72b  mov     ecx, [rax]
0x18002b72d  test    ecx, ecx
0x18002b72f  jz      short loc_18002B784
0x18002b731  test    rdi, rdi
0x18002b734  jz      short loc_18002B772
0x18002b736  mov     rax, cs:?g_pLsaFunctions@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pLsaFunctions
0x18002b73d  mov     rax, [rax+80h]
0x18002b744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b749  mov     [rdi], rax
0x18002b74c  test    rax, rax
0x18002b74f  jnz     short loc_18002B75F
0x18002b751  mov     ebx, 0C0000017h
0x18002b756  lea     rdx, aLsaifallocatel; "LsaIfAllocateLsaHeap failed 0x%08X\n"
0x18002b75d  jmp     short loc_18002B790
0x18002b75f  mov     rdx, [rbp+arg_0]
0x18002b763  mov     rcx, rax; void *
0x18002b766  mov     r8d, [rdx]; Size
0x18002b769  mov     rdx, [rdx+8]; Src
0x18002b76d  call    memcpy_0
0x18002b772  test    r14, r14
0x18002b775  jz      short loc_18002B780
0x18002b777  mov     rax, [rbp+arg_0]
0x18002b77b  mov     ecx, [rax]
0x18002b77d  mov     [r14], ecx
0x18002b780  xor     ebx, ebx
0x18002b782  jmp     short loc_18002B79D
0x18002b784  mov     ebx, 0C0000371h
0x18002b789  lea     rdx, aLsarquerysecre_0; "LsarQuerySecret return NULL data 0x%08X"...
0x18002b790  mov     r8d, ebx
0x18002b793  mov     ecx, 40h ; '@'; unsigned int
0x18002b798  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b79d  test    r15d, r15d
0x18002b7a0  jz      short loc_18002B7B5
0x18002b7a2  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18002b7a9  call    cs:__imp_RtlReleaseResource
0x18002b7b0  nop     dword ptr [rax+rax+00h]
0x18002b7b5  test    r13d, r13d
0x18002b7b8  jz      short loc_18002B7D1
0x18002b7ba  cmp     [rbp+var_20], 0
0x18002b7bf  jz      short loc_18002B7D1
0x18002b7c1  lea     rcx, [rbp+var_20]
0x18002b7c5  call    cs:__imp_LsarClose
0x18002b7cc  nop     dword ptr [rax+rax+00h]
0x18002b7d1  test    rsi, rsi
0x18002b7d4  jz      short loc_18002B7E5
0x18002b7d6  mov     rcx, rsi; hMem
0x18002b7d9  call    cs:__imp_LocalFree
0x18002b7e0  nop     dword ptr [rax+rax+00h]
0x18002b7e5  mov     rax, [rbp+arg_0]
0x18002b7e9  test    rax, rax
0x18002b7ec  jz      short loc_18002B81B
0x18002b7ee  mov     rdx, [rax+8]
0x18002b7f2  test    rdx, rdx
0x18002b7f5  jz      short loc_18002B80B
0x18002b7f7  mov     r8d, [rax]
0x18002b7fa  test    r8, r8
0x18002b7fd  jz      short loc_18002B80B
0x18002b7ff  mov     byte ptr [rdx], 0
0x18002b802  inc     rdx
0x18002b805  sub     r8, 1
0x18002b809  jnz     short loc_18002B7FF
0x18002b80b  mov     rcx, [rbp+arg_0]
0x18002b80f  call    cs:__imp_LsaIFree_LSAPR_CR_CIPHER_VALUE
0x18002b816  nop     dword ptr [rax+rax+00h]
0x18002b81b  mov     r8d, ebx
0x18002b81e  lea     rdx, aExitingNetpfet; "Exiting NetpFetchLSASecretCredsEx with "...
0x18002b825  mov     ecx, 40h ; '@'; unsigned int
0x18002b82a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b82f  mov     eax, ebx
0x18002b831  mov     rbx, [rsp+50h+arg_8]
0x18002b839  add     rsp, 50h
0x18002b83d  pop     r15
0x18002b83f  pop     r14
0x18002b841  pop     r13
0x18002b843  pop     r12
0x18002b845  pop     rdi
0x18002b846  pop     rsi
0x18002b847  pop     rbp
0x18002b848  retn
```
