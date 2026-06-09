# SiexBatchOperation(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *)

- ea: `0x180028fc0`
- end: `0x180029297`
- name: `?SiexBatchOperation@@YAHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX222@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1801b5714`

## callees

- `0x1800011b0`
- `0x180001518`
- `0x180006290`
- `0x180006cf4`
- `0x180028fc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800291fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800291fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800290b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800290b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800290c8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800290c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029237`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029237`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180029049`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180029049`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800290f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800290f7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180029120`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180029120`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180029133`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180029133`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002922c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002922c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002921e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002921e`

## pseudocode

```c
__int64 __fastcall SiexBatchOperation(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  int v7; // r13d
  unsigned int v8; // ebx
  __int128 v9; // xmm0
  _QWORD *i; // rax
  HANDLE CurrentThread; // rax
  struct _TP_WORK *v12; // rdi
  unsigned int v13; // esi
  unsigned int v14; // r15d
  unsigned int v15; // r12d
  _QWORD *j; // rbx
  __int64 v17; // r8
  __int64 v18; // r9
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
  const char **v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h]
  const char **v36; // [rsp+100h] [rbp+0h]
  __int64 v37; // [rsp+108h] [rbp+8h]
  int *v38; // [rsp+110h] [rbp+10h]
  __int64 v39; // [rsp+118h] [rbp+18h]
  int *v40; // [rsp+120h] [rbp+20h]
  __int64 v41; // [rsp+128h] [rbp+28h]

  v7 = a1;
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v20 = 3045;
    v21 = "SiexBatchOperation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)word_1802FDD72,
      a3,
      a4,
      &v21);
  }
  v8 = 0;
  memset_0(&pv, 0, 0x78u);
  InitializeCriticalSection(&CriticalSection);
  pv = v7;
  if ( (unsigned int)(v7 - 1) <= 1 )
  {
    v26 = a3;
  }
  else if ( v7 == 3 )
  {
    v27 = a3;
  }
  TokenHandle[1] = a2;
  if ( a4 )
  {
    v9 = *(_OWORD *)a4;
    v30 = *(_QWORD *)(a4 + 16);
    v29 = v9;
  }
  v33 = 0;
  if ( (unsigned int)(v7 - 1) <= 2 )
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
    if ( (unsigned int)(v7 - 1) <= 2 && *((_DWORD *)j + 4) )
    {
      if ( (unsigned int)dword_180397B68 > 1 )
      {
        v20 = *((unsigned __int8 *)j + 2836);
        v22 = *((_DWORD *)j + 4);
        LODWORD(v23) = *((_DWORD *)j + 28);
        v40 = &v20;
        v38 = &v22;
        v36 = &v23;
        v34 = &v21;
        LODWORD(v21) = v7;
        v41 = 4;
        v39 = 4;
        v37 = 4;
        v35 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180397B68, byte_1802F6801);
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
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v21) = 3199;
    v23 = "SiexBatchOperation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_180397B68,
      (__int64)byte_1802F7359,
      v17,
      v18,
      &v23);
  }
  return v13;
}

```

## disassembly

```asm
0x180028fc0  push    rbp
0x180028fc2  push    rbx
0x180028fc3  push    rsi
0x180028fc4  push    rdi
0x180028fc5  push    r12
0x180028fc7  push    r13
0x180028fc9  push    r14
0x180028fcb  push    r15
0x180028fcd  lea     rbp, [rsp-48h]
0x180028fd2  sub     rsp, 148h
0x180028fd9  mov     rax, cs:__security_cookie
0x180028fe0  xor     rax, rsp
0x180028fe3  mov     [rbp+80h+var_50], rax
0x180028fe7  mov     eax, cs:dword_180397B68
0x180028fed  lea     r15, aSiexbatchopera; "SiexBatchOperation"
0x180028ff4  mov     rdi, r9
0x180028ff7  mov     rsi, r8
0x180028ffa  mov     r14, rdx
0x180028ffd  mov     r13d, ecx
0x180029000  cmp     eax, 5
0x180029003  jbe     short loc_180029032
0x180029005  lea     rax, [rsp+180h+var_150]
0x18002900a  mov     [rsp+180h+var_150], 0BE5h
0x180029012  mov     [rsp+180h+var_158], rax
0x180029017  lea     rdx, word_1802FDD72
0x18002901e  lea     rax, [rsp+180h+var_148]
0x180029023  mov     [rsp+180h+var_148], r15
0x180029028  mov     [rsp+180h+var_160], rax
0x18002902d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180029032  xor     ebx, ebx
0x180029034  lea     rcx, [rsp+180h+pv]; void *
0x180029039  xor     edx, edx; Val
0x18002903b  lea     r8d, [rbx+78h]; Size
0x18002903f  call    memset_0
0x180029044  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x180029049  call    cs:__imp_InitializeCriticalSection
0x18002904f  lea     eax, [r13-1]
0x180029053  mov     [rsp+180h+pv], r13d
0x180029058  cmp     eax, 1
0x18002905b  jbe     short loc_180029069
0x18002905d  cmp     r13d, 3
0x180029061  jnz     short loc_18002906D
0x180029063  mov     [rbp+80h+var_F8], rsi
0x180029067  jmp     short loc_18002906D
0x180029069  mov     [rbp+80h+var_100], rsi
0x18002906d  mov     [rbp+80h+var_E8], r14
0x180029071  test    rdi, rdi
0x180029074  jz      short loc_180029086
0x180029076  movups  xmm0, xmmword ptr [rdi]
0x180029079  mov     rax, [rdi+10h]
0x18002907d  mov     [rbp+80h+var_D0], rax
0x180029081  movdqu  [rbp+80h+var_E0], xmm0
0x180029086  lea     eax, [r13-1]
0x18002908a  mov     [rbp+80h+var_C0], ebx
0x18002908d  cmp     eax, 2
0x180029090  ja      short loc_1800290A9
0x180029092  mov     rax, [r14]
0x180029095  jmp     short loc_1800290A4
0x180029097  mov     qword ptr [rax+10h], 139Fh
0x18002909f  inc     ebx
0x1800290a1  mov     rax, [rax]
0x1800290a4  cmp     rax, r14
0x1800290a7  jnz     short loc_180029097
0x1800290a9  mov     [rbp+80h+var_C8], 0
0x1800290b0  mov     [rbp+80h+var_C4], ebx
0x1800290b3  call    cs:__imp_GetCurrentThread
0x1800290b9  lea     r9, [rbp+80h+TokenHandle]; TokenHandle
0x1800290bd  xor     r8d, r8d; OpenAsSelf
0x1800290c0  mov     rcx, rax; ThreadHandle
0x1800290c3  mov     edx, 2000Ch; DesiredAccess
0x1800290c8  call    cs:__imp_OpenThreadToken
0x1800290ce  test    eax, eax
0x1800290d0  jnz     short loc_1800290E8
0x1800290d2  call    cs:__imp_GetLastError
0x1800290d8  cmp     eax, 3F0h
0x1800290dd  jz      short loc_1800290E8
0x1800290df  xor     edi, edi
0x1800290e1  xor     esi, esi
0x1800290e3  jmp     loc_180029215
0x1800290e8  xor     r8d, r8d; pcbe
0x1800290eb  lea     rdx, [rsp+180h+pv]; pv
0x1800290f0  lea     rcx, ?_BatchOperationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800290f7  call    cs:__imp_CreateThreadpoolWork
0x1800290fd  mov     rdi, rax
0x180029100  test    rax, rax
0x180029103  jz      short loc_1800290E1
0x180029105  mov     esi, 1
0x18002910a  xor     r15d, r15d
0x18002910d  lea     r12d, [rsi+1Fh]
0x180029111  cmp     ebx, r12d
0x180029114  ja      short loc_18002911D
0x180029116  mov     r12d, ebx
0x180029119  test    ebx, ebx
0x18002911b  jz      short loc_18002912E
0x18002911d  mov     rcx, rdi; pwk
0x180029120  call    cs:__imp_SubmitThreadpoolWork
0x180029126  inc     r15d
0x180029129  cmp     r15d, r12d
0x18002912c  jb      short loc_18002911D
0x18002912e  xor     edx, edx; fCancelPendingCallbacks
0x180029130  mov     rcx, rdi; pwk
0x180029133  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180029139  mov     rbx, [r14]
0x18002913c  cmp     rbx, r14
0x18002913f  jz      loc_18002920E
0x180029145  lea     eax, [r13-1]
0x180029149  cmp     eax, 2
0x18002914c  ja      loc_180029206
0x180029152  cmp     dword ptr [rbx+10h], 0
0x180029156  jz      loc_180029206
0x18002915c  mov     eax, cs:dword_180397B68
0x180029162  cmp     eax, 1
0x180029165  jbe     loc_1800291F7
0x18002916b  movzx   eax, byte ptr [rbx+0B14h]
0x180029172  lea     rdx, byte_1802F6801
0x180029179  mov     [rsp+180h+var_150], eax
0x18002917d  lea     rcx, dword_180397B68
0x180029184  mov     eax, [rbx+10h]
0x180029187  xor     r9d, r9d
0x18002918a  mov     [rsp+180h+var_140], eax
0x18002918e  xor     r8d, r8d
0x180029191  mov     eax, [rbx+70h]
0x180029194  mov     dword ptr [rsp+180h+var_138], eax
0x180029198  lea     rax, [rsp+180h+var_150]
0x18002919d  mov     [rbp+80h+var_60], rax
0x1800291a1  lea     rax, [rsp+180h+var_140]
0x1800291a6  mov     [rbp+80h+var_70], rax
0x1800291aa  lea     rax, [rsp+180h+var_138]
0x1800291af  mov     [rbp+80h+var_80], rax
0x1800291b3  lea     rax, [rsp+180h+var_148]
0x1800291b8  mov     [rbp+80h+var_90], rax
0x1800291bc  lea     rax, [rbp+80h+var_B0]
0x1800291c0  mov     [rsp+180h+var_158], rax
0x1800291c5  mov     dword ptr [rsp+180h+var_160], 6
0x1800291cd  mov     dword ptr [rsp+180h+var_148], r13d
0x1800291d2  mov     [rbp+80h+var_58], 4
0x1800291da  mov     [rbp+80h+var_68], 4
0x1800291e2  mov     [rbp+80h+var_78], 4
0x1800291ea  mov     [rbp+80h+var_88], 4
0x1800291f2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800291f7  test    esi, esi
0x1800291f9  jz      short loc_180029206
0x1800291fb  mov     ecx, [rbx+10h]; dwErrCode
0x1800291fe  call    cs:__imp_SetLastError
0x180029204  xor     esi, esi
0x180029206  mov     rbx, [rbx]
0x180029209  jmp     loc_18002913C
0x18002920e  lea     r15, aSiexbatchopera; "SiexBatchOperation"
0x180029215  mov     rcx, [rbp+80h+TokenHandle]; hObject
0x180029219  test    rcx, rcx
0x18002921c  jz      short loc_180029224
0x18002921e  call    cs:__imp_CloseHandle
0x180029224  test    rdi, rdi
0x180029227  jz      short loc_180029232
0x180029229  mov     rcx, rdi; pwk
0x18002922c  call    cs:__imp_CloseThreadpoolWork
0x180029232  lea     rcx, [rsp+180h+CriticalSection]; lpCriticalSection
0x180029237  call    cs:__imp_DeleteCriticalSection
0x18002923d  mov     ecx, cs:dword_180397B68
0x180029243  cmp     ecx, 5
0x180029246  jbe     short loc_180029275
0x180029248  lea     rax, [rsp+180h+var_148]
0x18002924d  mov     dword ptr [rsp+180h+var_148], 0C7Fh
0x180029255  mov     [rsp+180h+var_158], rax
0x18002925a  lea     rdx, byte_1802F7359
0x180029261  lea     rax, [rsp+180h+var_138]
0x180029266  mov     [rsp+180h+var_138], r15
0x18002926b  mov     [rsp+180h+var_160], rax
0x180029270  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180029275  mov     eax, esi
0x180029277  mov     rcx, [rbp+80h+var_50]
0x18002927b  xor     rcx, rsp; StackCookie
0x18002927e  call    __security_check_cookie
0x180029283  add     rsp, 148h
0x18002928a  pop     r15
0x18002928c  pop     r14
0x18002928e  pop     r13
0x180029290  pop     r12
0x180029292  pop     rdi
0x180029293  pop     rsi
0x180029294  pop     rbx
0x180029295  pop     rbp
0x180029296  retn
```
