# CreateCrlPreFetchEntry(_TVO_CACHE_ENTRY *,_CERT_CONTEXT const *,_CERT_CONTEXT const *)

- ea: `0x18001dde0`
- end: `0x18001e072`
- name: `?CreateCrlPreFetchEntry@@YAPEAU_CRL_PRE_FETCH_ENTRY@@PEAU_TVO_CACHE_ENTRY@@PEBU_CERT_CONTEXT@@1@Z`
- size: `658`
- prototype: `struct _CRL_PRE_FETCH_ENTRY *__fastcall(struct _TVO_CACHE_ENTRY *, const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180008f80`

## callees

- `0x180003274`
- `0x180007c00`
- `0x18000a990`
- `0x18001dde0`
- `0x18001e660`
- `0x18001eee8`
- `0x18001f310`
- `0x180026552`
- `0x18002656a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e023`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001de56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001de56`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001de6c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001de6c`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001df28`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001df35`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001df28`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001df35`
- `CRYPT32!CertDuplicateCRLContext` at `0x18001df1b`
- `CRYPT32!CertDuplicateCRLContext` at `0x18001df1b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001dfa9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001dfa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001dead`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001dead`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ded4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ded4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001def4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001def4`

## string_xrefs

- `0x18001e00d`: `Create`
- `0x18001e032`: `CreateError`

## pseudocode

```c
struct _CRL_PRE_FETCH_ENTRY *__fastcall CreateCrlPreFetchEntry(
        struct _TVO_CACHE_ENTRY *a1,
        const struct _CERT_CONTEXT *a2,
        const struct _CERT_CONTEXT *a3)
{
  _WORD *v6; // r14
  __int64 v7; // rbx
  FILETIME *v8; // rsi
  void *v9; // rax
  __int64 v10; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v13; // ecx
  PTP_WORK ThreadpoolWork; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  void *v16; // rax
  size_t v17; // rbx
  const FILETIME *v18; // rax
  _WORD *v19; // rbx
  __int64 v20; // rcx
  unsigned __int64 v21; // r14
  void *v22; // rax
  DWORD v23; // eax
  HMODULE phModule; // [rsp+60h] [rbp+8h] BYREF
  void *Src; // [rsp+78h] [rbp+20h] BYREF

  v6 = *(_WORD **)(*(_QWORD *)(*((_QWORD *)a1 + 7) + 8LL) + 8LL * *((unsigned int *)a1 + 16));
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  Src = 0;
  v8 = 0;
  v9 = operator new(0x90u);
  v10 = (__int64)v9;
  if ( !v9 )
    goto LABEL_25;
  memset_0(v9, 0, 0x90u);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)(v10 + 8)) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      v13 = LastError;
LABEL_26:
      SetLastError(v13);
      goto LABEL_27;
    }
    *(_QWORD *)(v10 + 8) = 0;
  }
  if ( !qword_180032980 )
  {
    phModule = 0;
    if ( !GetModuleHandleExW(4u, (LPCWSTR)CreateCrlPreFetchEntry, &phModule) )
      goto LABEL_27;
    qword_180032980 = (__int64)phModule;
  }
  ThreadpoolWork = CreateThreadpoolWork(CleanupPreFetchWorkCallback, (PVOID)v10, 0);
  *(_QWORD *)(v10 + 16) = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)PreFetchTimerCallback, (PVOID)v10, 0);
    *(_QWORD *)(v10 + 24) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      *(_OWORD *)(v10 + 32) = *(_OWORD *)a1;
      *(_OWORD *)(v10 + 48) = *((_OWORD *)a1 + 1);
      *(_QWORD *)(v10 + 64) = CertDuplicateCRLContext(*((PCCRL_CONTEXT *)a1 + 5));
      *(_QWORD *)(v10 + 72) = CertDuplicateCertificateContext(a2);
      *(_QWORD *)(v10 + 80) = CertDuplicateCertificateContext(a3);
      v16 = operator new(saturated_mul((int)v7 + 1LL, 2u));
      *(_QWORD *)(v10 + 88) = v16;
      if ( v16 )
      {
        v17 = 2LL * (int)v7;
        memcpy_0(v16, v6, v17);
        *(_WORD *)(v17 + *(_QWORD *)(v10 + 88)) = 0;
        v18 = (const FILETIME *)SchemeRetrieveCacheMetaData(v6, &Src, 0);
        v8 = (FILETIME *)v18;
        if ( !v18 )
          goto LABEL_24;
        if ( CompareFileTime((const FILETIME *)((char *)a1 + 100), v18 + 2) )
          goto LABEL_24;
        v19 = Src;
        *(FILETIME *)(v10 + 104) = v8[11];
        if ( !v19 )
          goto LABEL_24;
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
        v21 = (int)v20 + 1;
        v22 = operator new(saturated_mul(v21, 2u));
        *(_QWORD *)(v10 + 112) = v22;
        if ( v22 )
        {
          memcpy_0(v22, v19, 2 * v21);
LABEL_24:
          GetCrlPreFetchScheduleParameters(v10 + 120);
          LogCrlPreFetchEvent((__int64)"Create", v10, 0);
          goto LABEL_29;
        }
      }
LABEL_25:
      v13 = -2147024882;
      goto LABEL_26;
    }
  }
LABEL_27:
  v23 = GetLastError();
  LogCrlPreFetchEvent((__int64)"CreateError", v10, v23);
  if ( v10 )
  {
    FreeCrlPreFetchEntry((HLOCAL)v10);
    v10 = 0;
  }
LABEL_29:
  operator delete(v8);
  return (struct _CRL_PRE_FETCH_ENTRY *)v10;
}

```

## disassembly

```asm
0x18001dde0  mov     [rsp+arg_8], rbx
0x18001dde5  push    rbp
0x18001dde6  push    rsi
0x18001dde7  push    rdi
0x18001dde8  push    r12
0x18001ddea  push    r13
0x18001ddec  push    r14
0x18001ddee  push    r15
0x18001ddf0  sub     rsp, 20h
0x18001ddf4  mov     rax, [rcx+38h]
0x18001ddf8  xor     r15d, r15d
0x18001ddfb  mov     r10d, [rcx+40h]
0x18001ddff  mov     r12, r8
0x18001de02  mov     r13, rdx
0x18001de05  mov     rbp, rcx
0x18001de08  mov     r9, [rax+8]
0x18001de0c  mov     r14, [r9+r10*8]
0x18001de10  test    r14, r14
0x18001de13  jz      short loc_18001DE25
0x18001de15  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001de19  inc     rbx
0x18001de1c  cmp     [r14+rbx*2], r15w
0x18001de21  jnz     short loc_18001DE19
0x18001de23  jmp     short loc_18001DE28
0x18001de25  mov     ebx, r15d
0x18001de28  mov     ecx, 90h; uBytes
0x18001de2d  mov     [rsp+58h+Src], r15
0x18001de32  mov     rsi, r15
0x18001de35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001de3a  mov     rdi, rax
0x18001de3d  test    rax, rax
0x18001de40  jz      loc_18001E01E
0x18001de46  xor     edx, edx; Val
0x18001de48  mov     r8d, 90h; Size
0x18001de4e  mov     rcx, rax; void *
0x18001de51  call    memset_0
0x18001de56  call    cs:__imp_GetCurrentThread
0x18001de5c  mov     edx, 0Ch; DesiredAccess
0x18001de61  lea     r9, [rdi+8]; TokenHandle
0x18001de65  mov     rcx, rax; ThreadHandle
0x18001de68  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001de6c  call    cs:__imp_OpenThreadToken
0x18001de72  test    eax, eax
0x18001de74  jnz     short loc_18001DE8E
0x18001de76  call    cs:__imp_GetLastError
0x18001de7c  cmp     eax, 3F0h
0x18001de81  jz      short loc_18001DE8A
0x18001de83  mov     ecx, eax
0x18001de85  jmp     loc_18001E023
0x18001de8a  mov     [rdi+8], rsi
0x18001de8e  cmp     cs:qword_180032980, r15
0x18001de95  jnz     short loc_18001DEC7
0x18001de97  lea     r8, [rsp+58h+phModule]; phModule
0x18001de9c  mov     [rsp+58h+phModule], r15
0x18001dea1  lea     rdx, ?CreateCrlPreFetchEntry@@YAPEAU_CRL_PRE_FETCH_ENTRY@@PEAU_TVO_CACHE_ENTRY@@PEBU_CERT_CONTEXT@@1@Z; lpModuleName
0x18001dea8  mov     ecx, 4; dwFlags
0x18001dead  call    cs:__imp_GetModuleHandleExW
0x18001deb3  test    eax, eax
0x18001deb5  jz      loc_18001E029
0x18001debb  mov     rax, [rsp+58h+phModule]
0x18001dec0  mov     cs:qword_180032980, rax
0x18001dec7  xor     r8d, r8d; pcbe
0x18001deca  lea     rcx, _CleanupPreFetchWorkCallback; pfnwk
0x18001ded1  mov     rdx, rdi; pv
0x18001ded4  call    cs:__imp_CreateThreadpoolWork
0x18001deda  mov     [rdi+10h], rax
0x18001dede  test    rax, rax
0x18001dee1  jz      loc_18001E029
0x18001dee7  xor     r8d, r8d; pcbe
0x18001deea  lea     rcx, _PreFetchTimerCallback; pfnti
0x18001def1  mov     rdx, rdi; pv
0x18001def4  call    cs:__imp_CreateThreadpoolTimer
0x18001defa  mov     [rdi+18h], rax
0x18001defe  test    rax, rax
0x18001df01  jz      loc_18001E029
0x18001df07  movups  xmm0, xmmword ptr [rbp+0]
0x18001df0b  movups  xmmword ptr [rdi+20h], xmm0
0x18001df0f  movups  xmm1, xmmword ptr [rbp+10h]
0x18001df13  movups  xmmword ptr [rdi+30h], xmm1
0x18001df17  mov     rcx, [rbp+28h]; pCrlContext
0x18001df1b  call    cs:__imp_CertDuplicateCRLContext
0x18001df21  mov     rcx, r13; pCertContext
0x18001df24  mov     [rdi+40h], rax
0x18001df28  call    cs:__imp_CertDuplicateCertificateContext
0x18001df2e  mov     rcx, r12; pCertContext
0x18001df31  mov     [rdi+48h], rax
0x18001df35  call    cs:__imp_CertDuplicateCertificateContext
0x18001df3b  mov     r13d, 2
0x18001df41  movsxd  rbx, ebx
0x18001df44  mov     [rdi+50h], rax
0x18001df48  mov     eax, r13d
0x18001df4b  lea     rcx, [rbx+1]
0x18001df4f  mul     rcx
0x18001df52  lea     r12, [r13-3]
0x18001df56  cmovb   rax, r12
0x18001df5a  mov     rcx, rax; uBytes
0x18001df5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001df62  mov     [rdi+58h], rax
0x18001df66  test    rax, rax
0x18001df69  jz      loc_18001E01E
0x18001df6f  add     rbx, rbx
0x18001df72  mov     rdx, r14; Src
0x18001df75  mov     r8, rbx; Size
0x18001df78  mov     rcx, rax; void *
0x18001df7b  call    memcpy_0
0x18001df80  mov     rdx, [rdi+58h]
0x18001df84  xor     r8d, r8d
0x18001df87  mov     rcx, r14
0x18001df8a  mov     [rbx+rdx], r15w
0x18001df8f  lea     rdx, [rsp+58h+Src]
0x18001df94  call    SchemeRetrieveCacheMetaData
0x18001df99  mov     rsi, rax
0x18001df9c  test    rax, rax
0x18001df9f  jz      short loc_18001E001
0x18001dfa1  lea     rdx, [rax+10h]; lpFileTime2
0x18001dfa5  lea     rcx, [rbp+64h]; lpFileTime1
0x18001dfa9  call    cs:__imp_CompareFileTime
0x18001dfaf  test    eax, eax
0x18001dfb1  jnz     short loc_18001E001
0x18001dfb3  mov     rbx, [rsp+58h+Src]
0x18001dfb8  mov     rcx, [rsi+58h]
0x18001dfbc  mov     [rdi+68h], rcx
0x18001dfc0  test    rbx, rbx
0x18001dfc3  jz      short loc_18001E001
0x18001dfc5  mov     rcx, r12
0x18001dfc8  inc     rcx
0x18001dfcb  cmp     [rbx+rcx*2], r15w
0x18001dfd0  jnz     short loc_18001DFC8
0x18001dfd2  inc     ecx
0x18001dfd4  mov     rax, r13
0x18001dfd7  movsxd  r14, ecx
0x18001dfda  mul     r14
0x18001dfdd  cmovb   rax, r12
0x18001dfe1  mov     rcx, rax; uBytes
0x18001dfe4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dfe9  mov     [rdi+70h], rax
0x18001dfed  test    rax, rax
0x18001dff0  jz      short loc_18001E01E
0x18001dff2  lea     r8, [r14+r14]; Size
0x18001dff6  mov     rdx, rbx; Src
0x18001dff9  mov     rcx, rax; void *
0x18001dffc  call    memcpy_0
0x18001e001  lea     rcx, [rdi+78h]
0x18001e005  call    _GetCrlPreFetchScheduleParameters
0x18001e00a  xor     r8d, r8d
0x18001e00d  lea     rcx, aCreate; "Create"
0x18001e014  mov     rdx, rdi
0x18001e017  call    _LogCrlPreFetchEvent
0x18001e01c  jmp     short loc_18001E052
0x18001e01e  mov     ecx, 8007000Eh; dwErrCode
0x18001e023  call    cs:__imp_SetLastError
0x18001e029  call    cs:__imp_GetLastError
0x18001e02f  mov     rdx, rdi
0x18001e032  lea     rcx, aCreateerror; "CreateError"
0x18001e039  mov     r8d, eax
0x18001e03c  call    _LogCrlPreFetchEvent
0x18001e041  xor     ebx, ebx
0x18001e043  test    rdi, rdi
0x18001e046  jz      short loc_18001E052
0x18001e048  mov     rcx, rdi; hMem
0x18001e04b  call    ?FreeCrlPreFetchEntry@@YAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z; FreeCrlPreFetchEntry(_CRL_PRE_FETCH_ENTRY *)
0x18001e050  mov     edi, ebx
0x18001e052  mov     rcx, rsi; hMem
0x18001e055  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e05a  mov     rbx, [rsp+58h+arg_8]
0x18001e05f  mov     rax, rdi
0x18001e062  add     rsp, 20h
0x18001e066  pop     r15
0x18001e068  pop     r14
0x18001e06a  pop     r13
0x18001e06c  pop     r12
0x18001e06e  pop     rdi
0x18001e06f  pop     rsi
0x18001e070  pop     rbp
0x18001e071  retn
```
