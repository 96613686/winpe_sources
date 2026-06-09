# PutLocalRequestInQueue

- ea: `0x180011010`
- end: `0x1800111ef`
- name: `PutLocalRequestInQueue`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002f80`

## callees

- `0x180011010`
- `0x180011200`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800110a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800110a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800110be`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800110be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001114f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001119e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001114f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001119e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800110cc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800110cc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011190`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011190`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800110fa`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800110fa`
- `rtutils!TracePrintfExA` at `0x18001112e`
- `rtutils!TracePrintfExA` at `0x180011175`
- `rtutils!TracePrintfExA` at `0x1800111c4`
- `rtutils!TracePrintfExA` at `0x18001112e`
- `rtutils!TracePrintfExA` at `0x180011175`
- `rtutils!TracePrintfExA` at `0x1800111c4`

## string_xrefs

- `0x180011169`: `PutLocalRequestInQueue: OpenThreadToken Failed 0x%.8x`
- `0x180011122`: `PutLocalRequestInQueue: DuplicateToken Failed 0x%.8x`
- `0x1800111b8`: `PutLocalRequestInQueue: ImpersonateLoggedOnUser failed 0x%.8x`

## pseudocode

```c
__int64 __fastcall PutLocalRequestInQueue(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx
  DWORD v5; // eax
  HANDLE CurrentThread; // rax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD LastError; // eax
  void *DuplicateTokenHandle; // [rsp+40h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+20h] BYREF

  v2 = 0;
  TokenHandle = 0;
  DuplicateTokenHandle = 0;
  if ( !g_fRasmanService || !g_fnRasmanServiceInitialized || !g_fnRasmanServiceInitialized() )
  {
    v5 = RemoteSubmitRequestLocal(a1, a2);
    goto LABEL_3;
  }
  if ( !g_fnServiceRequest )
  {
    v2 = 711;
    goto LABEL_4;
  }
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    ((void (__fastcall *)(__int64, _QWORD))g_fnServiceRequest)(a1, a2);
    goto LABEL_4;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    if ( RevertToSelf() )
    {
      ((void (__fastcall *)(__int64, _QWORD))g_fnServiceRequest)(a1, a2);
      if ( DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
      {
        if ( !ImpersonateLoggedOnUser(DuplicateTokenHandle) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "PutLocalRequestInQueue: ImpersonateLoggedOnUser failed 0x%.8x",
              LastError);
        }
      }
      else
      {
        v8 = GetLastError();
        v2 = v8;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "PutLocalRequestInQueue: DuplicateToken Failed 0x%.8x", v8);
      }
      goto LABEL_4;
    }
    v5 = GetLastError();
LABEL_3:
    v2 = v5;
    goto LABEL_4;
  }
  v9 = GetLastError();
  v2 = v9;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "PutLocalRequestInQueue: OpenThreadToken Failed 0x%.8x", v9);
LABEL_4:
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x180011010  mov     [rsp+arg_0], rbx
0x180011015  mov     [rsp+arg_8], rsi
0x18001101a  push    rdi
0x18001101b  sub     rsp, 20h
0x18001101f  xor     ebx, ebx
0x180011021  mov     edi, edx
0x180011023  cmp     cs:g_fRasmanService, ebx
0x180011029  mov     rsi, rcx
0x18001102c  mov     [rsp+28h+TokenHandle], rbx
0x180011031  mov     [rsp+28h+DuplicateTokenHandle], rbx
0x180011036  jnz     short loc_180011072
0x180011038  mov     edx, edi
0x18001103a  mov     rcx, rsi
0x18001103d  call    RemoteSubmitRequestLocal
0x180011042  mov     ebx, eax
0x180011044  mov     rcx, [rsp+28h+DuplicateTokenHandle]; hObject
0x180011049  test    rcx, rcx
0x18001104c  jnz     loc_1800111D9
0x180011052  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180011057  test    rcx, rcx
0x18001105a  jnz     loc_1800111E4
0x180011060  mov     rsi, [rsp+28h+arg_8]
0x180011065  mov     eax, ebx
0x180011067  mov     rbx, [rsp+28h+arg_0]
0x18001106c  add     rsp, 20h
0x180011070  pop     rdi
0x180011071  retn
0x180011072  mov     rax, cs:g_fnRasmanServiceInitialized
0x180011079  test    rax, rax
0x18001107c  jz      short loc_180011038
0x18001107e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011083  test    rax, rax
0x180011086  jz      short loc_180011038
0x180011088  cmp     cs:g_fnServiceRequest, rbx
0x18001108f  jz      loc_1800111CF
0x180011095  mov     eax, gs:179Ch
0x18001109d  test    eax, eax
0x18001109f  jz      loc_180011139
0x1800110a5  call    cs:__imp_GetCurrentThread
0x1800110ab  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800110b0  mov     edx, 0F01FFh; DesiredAccess
0x1800110b5  mov     rcx, rax; ThreadHandle
0x1800110b8  mov     r8d, 1; OpenAsSelf
0x1800110be  call    cs:__imp_OpenThreadToken
0x1800110c4  test    eax, eax
0x1800110c6  jz      loc_18001114F
0x1800110cc  call    cs:__imp_RevertToSelf
0x1800110d2  test    eax, eax
0x1800110d4  jz      loc_180011180
0x1800110da  mov     rax, cs:g_fnServiceRequest
0x1800110e1  mov     edx, edi
0x1800110e3  mov     rcx, rsi
0x1800110e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110eb  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x1800110f0  lea     r8, [rsp+28h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800110f5  mov     edx, 2; ImpersonationLevel
0x1800110fa  call    cs:__imp_DuplicateToken
0x180011100  test    eax, eax
0x180011102  jnz     loc_18001118B
0x180011108  call    cs:__imp_GetLastError
0x18001110e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180011114  mov     ebx, eax
0x180011116  cmp     ecx, 0FFFFFFFFh
0x180011119  jz      loc_180011044
0x18001111f  mov     r9d, eax
0x180011122  lea     r8, aPutlocalreques_0; "PutLocalRequestInQueue: DuplicateToken "...
0x180011129  mov     edx, 0Ch; dwFlags
0x18001112e  call    cs:__imp_TracePrintfExA
0x180011134  jmp     loc_180011044
0x180011139  mov     rax, cs:g_fnServiceRequest
0x180011140  mov     edx, edi
0x180011142  mov     rcx, rsi
0x180011145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114a  jmp     loc_180011044
0x18001114f  call    cs:__imp_GetLastError
0x180011155  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001115b  mov     ebx, eax
0x18001115d  cmp     ecx, 0FFFFFFFFh
0x180011160  jz      loc_180011044
0x180011166  mov     r9d, eax
0x180011169  lea     r8, aPutlocalreques_1; "PutLocalRequestInQueue: OpenThreadToken"...
0x180011170  mov     edx, 0Ch; dwFlags
0x180011175  call    cs:__imp_TracePrintfExA
0x18001117b  jmp     loc_180011044
0x180011180  call    cs:__imp_GetLastError
0x180011186  jmp     loc_180011042
0x18001118b  mov     rcx, [rsp+28h+DuplicateTokenHandle]; hToken
0x180011190  call    cs:__imp_ImpersonateLoggedOnUser
0x180011196  test    eax, eax
0x180011198  jnz     loc_180011044
0x18001119e  call    cs:__imp_GetLastError
0x1800111a4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800111aa  mov     ebx, eax
0x1800111ac  cmp     ecx, 0FFFFFFFFh
0x1800111af  jz      loc_180011044
0x1800111b5  mov     r9d, eax
0x1800111b8  lea     r8, aPutlocalreques; "PutLocalRequestInQueue: ImpersonateLogg"...
0x1800111bf  mov     edx, 0Ch; dwFlags
0x1800111c4  call    cs:__imp_TracePrintfExA
0x1800111ca  jmp     loc_180011044
0x1800111cf  mov     ebx, 2C7h
0x1800111d4  jmp     loc_180011044
0x1800111d9  call    cs:__imp_CloseHandle
0x1800111df  jmp     loc_180011052
0x1800111e4  call    cs:__imp_CloseHandle
0x1800111ea  jmp     loc_180011060
```
