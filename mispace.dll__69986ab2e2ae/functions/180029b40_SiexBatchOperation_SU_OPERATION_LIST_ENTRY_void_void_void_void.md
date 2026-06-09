# SiexBatchOperation(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)

- ea: `0x180029b40`
- end: `0x180029e5a`
- name: `?SiexBatchOperation@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1801bbabc`

## callees

- `0x1800011c4`
- `0x180001534`
- `0x180006350`
- `0x180006dd4`
- `0x180029b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029da8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029da8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029c39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029c39`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029c54`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180029c54`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029df3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029df3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180029bc9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180029bc9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180029c8f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180029c8f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180029cbe`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180029cbe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180029cd7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180029cd7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180029de2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180029de2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029dce`

## pseudocode

```c
__int64 __fastcall SiexBatchOperation(int a1, _QWORD *a2, __int64 a3, __int128 *a4)
{
  unsigned int v8; // ebx
  __int128 v9; // xmm0
  _QWORD *i; // rax
  HANDLE CurrentThread; // rax
  struct _TP_WORK *v12; // rdi
  unsigned int v13; // esi
  unsigned int v14; // r15d
  unsigned int v15; // r12d
  _QWORD *j; // rbx
  int v17; // r8d
  int v18; // r9d
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  const char *v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  const char *v23; // [rsp+48h] [rbp-B8h] BYREF
  int pv; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+88h] [rbp-78h]
  void *TokenHandle[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+B0h] [rbp-50h]
  int v31; // [rsp+B8h] [rbp-48h]
  unsigned int v32; // [rsp+BCh] [rbp-44h]
  int v33; // [rsp+C0h] [rbp-40h]
  _BYTE v34[32]; // [rsp+D0h] [rbp-30h] BYREF
  const char **v35; // [rsp+F0h] [rbp-10h]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  const char **v37; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  int *v39; // [rsp+110h] [rbp+10h]
  __int64 v40; // [rsp+118h] [rbp+18h]
  int *v41; // [rsp+120h] [rbp+20h]
  __int64 v42; // [rsp+128h] [rbp+28h]

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v20 = 3045;
    v21 = "SiexBatchOperation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)word_180304CFA,
      a3,
      (_DWORD)a4,
      (__int64)&v21,
      (__int64)&v20);
  }
  v8 = 0;
  memset_0(&pv, 0, 0x78u);
  InitializeCriticalSection(&CriticalSection);
  pv = a1;
  if ( (unsigned int)(a1 - 1) <= 1 )
  {
    v26 = a3;
  }
  else if ( a1 == 3 )
  {
    v27 = a3;
  }
  TokenHandle[1] = a2;
  if ( a4 )
  {
    v9 = *a4;
    v30 = *((_QWORD *)a4 + 2);
    v29 = v9;
  }
  v33 = 0;
  if ( (unsigned int)(a1 - 1) <= 2 )
  {
    for ( i = (_QWORD *)*a2; i != a2; i = (_QWORD *)*i )
    {
      i[2] = 5023;
      ++v8;
    }
  }
  v31 = 0;
  v32 = v8;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 0, TokenHandle) && GetLastError() != 1008 )
  {
    v12 = 0;
LABEL_16:
    v13 = 0;
    goto LABEL_30;
  }
  v12 = CreateThreadpoolWork(_BatchOperationCallback, &pv, 0);
  if ( !v12 )
    goto LABEL_16;
  v13 = 1;
  v14 = 0;
  v15 = 32;
  if ( v8 > 0x20 || (v15 = v8) != 0 )
  {
    do
    {
      SubmitThreadpoolWork(v12);
      ++v14;
    }
    while ( v14 < v15 );
  }
  WaitForThreadpoolWorkCallbacks(v12, 0);
  for ( j = (_QWORD *)*a2; j != a2; j = (_QWORD *)*j )
  {
    if ( (unsigned int)(a1 - 1) <= 2 && *((_DWORD *)j + 4) )
    {
      if ( (unsigned int)dword_18039EB68 > 1 )
      {
        v20 = *((unsigned __int8 *)j + 2836);
        v22 = *((_DWORD *)j + 4);
        LODWORD(v23) = *((_DWORD *)j + 28);
        v41 = &v20;
        v39 = &v22;
        v37 = &v23;
        v35 = &v21;
        LODWORD(v21) = a1;
        v42 = 4;
        v40 = 4;
        v38 = 4;
        v36 = 4;
        tlgWriteTransfer_EventWriteTransfer(
          &dword_18039EB68,
          byte_1802FD789,
          0,
          0,
          6,
          v34,
          v20,
          v21,
          v22,
          (_DWORD)v23,
          pv);
      }
      if ( v13 )
      {
        SetLastError(*((_DWORD *)j + 4));
        v13 = 0;
      }
    }
  }
LABEL_30:
  if ( TokenHandle[0] )
    CloseHandle(TokenHandle[0]);
  if ( v12 )
    CloseThreadpoolWork(v12);
  DeleteCriticalSection(&CriticalSection);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v21) = 3199;
    v23 = "SiexBatchOperation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_18039EB68,
      (unsigned int)byte_1802FE2E1,
      v17,
      v18,
      (__int64)&v23,
      (__int64)&v21);
  }
  return v13;
}

```

## disassembly

```asm
0x180029b40  push    rbp
0x180029b42  push    rbx
0x180029b43  push    rsi
0x180029b44  push    rdi
0x180029b45  push    r12
0x180029b47  push    r13
0x180029b49  push    r14
0x180029b4b  push    r15
0x180029b4d  lea     rbp, [rsp-48h]
0x180029b52  sub     rsp, 148h
0x180029b59  mov     rax, cs:__security_cookie
0x180029b60  xor     rax, rsp
0x180029b63  mov     [rbp+80h+var_50], rax
0x180029b67  mov     eax, cs:dword_18039EB68
0x180029b6d  lea     r15, aSiexbatchopera; "SiexBatchOperation"
0x180029b74  mov     rdi, r9
0x180029b77  mov     rsi, r8
0x180029b7a  mov     r14, rdx
0x180029b7d  mov     r13d, ecx
0x180029b80  cmp     eax, 5
0x180029b83  jbe     short loc_180029BB2
0x180029b85  lea     rax, [rsp+180h+var_150]
0x180029b8a  mov     [rsp+180h+var_150], 0BE5h
0x180029b92  mov     [rsp+180h+var_158], rax
0x180029b97  lea     rdx, word_180304CFA
0x180029b9e  lea     rax, [rsp+180h+var_148]
0x180029ba3  mov     [rsp+180h+var_148], r15
0x180029ba8  mov     [rsp+180h+var_160], rax
0x180029bad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180029bb2  xor     ebx, ebx
0x180029bb4  lea     rcx, [rsp+180h+pv]; void *
0x180029bb9  xor     edx, edx; Val
0x180029bbb  lea     r8d, [rbx+78h]; Size
0x180029bbf  call    memset_0
0x180029bc4  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x180029bc9  call    cs:__imp_InitializeCriticalSection
0x180029bd0  nop     dword ptr [rax+rax+00h]
0x180029bd5  lea     eax, [r13-1]
0x180029bd9  mov     [rsp+180h+pv], r13d
0x180029bde  cmp     eax, 1
0x180029be1  jbe     short loc_180029BEF
0x180029be3  cmp     r13d, 3
0x180029be7  jnz     short loc_180029BF3
0x180029be9  mov     [rbp+80h+var_F8], rsi
0x180029bed  jmp     short loc_180029BF3
0x180029bef  mov     [rbp+80h+var_100], rsi
0x180029bf3  mov     [rbp+80h+var_E8], r14
0x180029bf7  test    rdi, rdi
0x180029bfa  jz      short loc_180029C0C
0x180029bfc  movups  xmm0, xmmword ptr [rdi]
0x180029bff  mov     rax, [rdi+10h]
0x180029c03  mov     [rbp+80h+var_D0], rax
0x180029c07  movdqu  [rbp+80h+var_E0], xmm0
0x180029c0c  lea     eax, [r13-1]
0x180029c10  mov     [rbp+80h+var_C0], ebx
0x180029c13  cmp     eax, 2
0x180029c16  ja      short loc_180029C2F
0x180029c18  mov     rax, [r14]
0x180029c1b  jmp     short loc_180029C2A
0x180029c1d  mov     qword ptr [rax+10h], 139Fh
0x180029c25  inc     ebx
0x180029c27  mov     rax, [rax]
0x180029c2a  cmp     rax, r14
0x180029c2d  jnz     short loc_180029C1D
0x180029c2f  mov     [rbp+80h+var_C8], 0
0x180029c36  mov     [rbp+80h+var_C4], ebx
0x180029c39  call    cs:__imp_GetCurrentThread
0x180029c40  nop     dword ptr [rax+rax+00h]
0x180029c45  lea     r9, [rbp+80h+TokenHandle]; TokenHandle
0x180029c49  xor     r8d, r8d; OpenAsSelf
0x180029c4c  mov     rcx, rax; ThreadHandle
0x180029c4f  mov     edx, 2000Ch; DesiredAccess
0x180029c54  call    cs:__imp_OpenThreadToken
0x180029c5b  nop     dword ptr [rax+rax+00h]
0x180029c60  test    eax, eax
0x180029c62  jnz     short loc_180029C80
0x180029c64  call    cs:__imp_GetLastError
0x180029c6b  nop     dword ptr [rax+rax+00h]
0x180029c70  cmp     eax, 3F0h
0x180029c75  jz      short loc_180029C80
0x180029c77  xor     edi, edi
0x180029c79  xor     esi, esi
0x180029c7b  jmp     loc_180029DC5
0x180029c80  xor     r8d, r8d; pcbe
0x180029c83  lea     rdx, [rsp+180h+pv]; pv
0x180029c88  lea     rcx, ?_BatchOperationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180029c8f  call    cs:__imp_CreateThreadpoolWork
0x180029c96  nop     dword ptr [rax+rax+00h]
0x180029c9b  mov     rdi, rax
0x180029c9e  test    rax, rax
0x180029ca1  jz      short loc_180029C79
0x180029ca3  mov     esi, 1
0x180029ca8  xor     r15d, r15d
0x180029cab  lea     r12d, [rsi+1Fh]
0x180029caf  cmp     ebx, r12d
0x180029cb2  ja      short loc_180029CBB
0x180029cb4  mov     r12d, ebx
0x180029cb7  test    ebx, ebx
0x180029cb9  jz      short loc_180029CD2
0x180029cbb  mov     rcx, rdi; pwk
0x180029cbe  call    cs:__imp_SubmitThreadpoolWork
0x180029cc5  nop     dword ptr [rax+rax+00h]
0x180029cca  inc     r15d
0x180029ccd  cmp     r15d, r12d
0x180029cd0  jb      short loc_180029CBB
0x180029cd2  xor     edx, edx; fCancelPendingCallbacks
0x180029cd4  mov     rcx, rdi; pwk
0x180029cd7  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180029cde  nop     dword ptr [rax+rax+00h]
0x180029ce3  mov     rbx, [r14]
0x180029ce6  cmp     rbx, r14
0x180029ce9  jz      loc_180029DBE
0x180029cef  lea     eax, [r13-1]
0x180029cf3  cmp     eax, 2
0x180029cf6  ja      loc_180029DB6
0x180029cfc  cmp     dword ptr [rbx+10h], 0
0x180029d00  jz      loc_180029DB6
0x180029d06  mov     eax, cs:dword_18039EB68
0x180029d0c  cmp     eax, 1
0x180029d0f  jbe     loc_180029DA1
0x180029d15  movzx   eax, byte ptr [rbx+0B14h]
0x180029d1c  lea     rdx, byte_1802FD789
0x180029d23  mov     [rsp+180h+var_150], eax
0x180029d27  lea     rcx, dword_18039EB68
0x180029d2e  mov     eax, [rbx+10h]
0x180029d31  xor     r9d, r9d
0x180029d34  mov     [rsp+180h+var_140], eax
0x180029d38  xor     r8d, r8d
0x180029d3b  mov     eax, [rbx+70h]
0x180029d3e  mov     dword ptr [rsp+180h+var_138], eax
0x180029d42  lea     rax, [rsp+180h+var_150]
0x180029d47  mov     [rbp+80h+var_60], rax
0x180029d4b  lea     rax, [rsp+180h+var_140]
0x180029d50  mov     [rbp+80h+var_70], rax
0x180029d54  lea     rax, [rsp+180h+var_138]
0x180029d59  mov     [rbp+80h+var_80], rax
0x180029d5d  lea     rax, [rsp+180h+var_148]
0x180029d62  mov     [rbp+80h+var_90], rax
0x180029d66  lea     rax, [rbp+80h+var_B0]
0x180029d6a  mov     [rsp+180h+var_158], rax
0x180029d6f  mov     dword ptr [rsp+180h+var_160], 6
0x180029d77  mov     dword ptr [rsp+180h+var_148], r13d
0x180029d7c  mov     [rbp+80h+var_58], 4
0x180029d84  mov     [rbp+80h+var_68], 4
0x180029d8c  mov     [rbp+80h+var_78], 4
0x180029d94  mov     [rbp+80h+var_88], 4
0x180029d9c  call    _tlgWriteTransfer_EventWriteTransfer
0x180029da1  test    esi, esi
0x180029da3  jz      short loc_180029DB6
0x180029da5  mov     ecx, [rbx+10h]; dwErrCode
0x180029da8  call    cs:__imp_SetLastError
0x180029daf  nop     dword ptr [rax+rax+00h]
0x180029db4  xor     esi, esi
0x180029db6  mov     rbx, [rbx]
0x180029db9  jmp     loc_180029CE6
0x180029dbe  lea     r15, aSiexbatchopera; "SiexBatchOperation"
0x180029dc5  mov     rcx, [rbp+80h+TokenHandle]; hObject
0x180029dc9  test    rcx, rcx
0x180029dcc  jz      short loc_180029DDA
0x180029dce  call    cs:__imp_CloseHandle
0x180029dd5  nop     dword ptr [rax+rax+00h]
0x180029dda  test    rdi, rdi
0x180029ddd  jz      short loc_180029DEE
0x180029ddf  mov     rcx, rdi; pwk
0x180029de2  call    cs:__imp_CloseThreadpoolWork
0x180029de9  nop     dword ptr [rax+rax+00h]
0x180029dee  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x180029df3  call    cs:__imp_DeleteCriticalSection
0x180029dfa  nop     dword ptr [rax+rax+00h]
0x180029dff  mov     ecx, cs:dword_18039EB68
0x180029e05  cmp     ecx, 5
0x180029e08  jbe     short loc_180029E37
0x180029e0a  lea     rax, [rsp+180h+var_148]
0x180029e0f  mov     dword ptr [rsp+180h+var_148], 0C7Fh
0x180029e17  mov     [rsp+180h+var_158], rax
0x180029e1c  lea     rdx, byte_1802FE2E1
0x180029e23  lea     rax, [rsp+180h+var_138]
0x180029e28  mov     [rsp+180h+var_138], r15
0x180029e2d  mov     [rsp+180h+var_160], rax
0x180029e32  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180029e37  mov     eax, esi
0x180029e39  mov     rcx, [rbp+80h+var_50]
0x180029e3d  xor     rcx, rsp; StackCookie
0x180029e40  call    __security_check_cookie
0x180029e45  add     rsp, 148h
0x180029e4c  pop     r15
0x180029e4e  pop     r14
0x180029e50  pop     r13
0x180029e52  pop     r12
0x180029e54  pop     rdi
0x180029e55  pop     rsi
0x180029e56  pop     rbx
0x180029e57  pop     rbp
0x180029e58  retn
```
