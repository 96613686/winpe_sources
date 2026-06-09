# CEfsClient::WaitForServiceReady_Notify(SC_HANDLE__ *,ulong,ulong)

- ea: `0x18000ab34`
- end: `0x18000ac57`
- name: `?WaitForServiceReady_Notify@CEfsClient@@KAKPEAUSC_HANDLE__@@KK@Z`
- size: `291`
- prototype: `unsigned int __fastcall(SC_HANDLE hService, DWORD dwMilliseconds, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a974`

## callees

- `0x18000ab34`
- `0x18001200e`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000aba8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000aba8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000abbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000abbd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000abeb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000abeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac2a`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000abfc`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000abfc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000abc7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000abc7`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000ab97`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000abdc`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000ab97`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000abdc`

## pseudocode

```c
__int64 __fastcall CEfsClient::WaitForServiceReady_Notify(SC_HANDLE hService, DWORD dwMilliseconds)
{
  DWORD v4; // eax
  DWORD v5; // ebx
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+20h] [rbp-78h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+30h] [rbp-68h] BYREF

  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  TokenHandle = 0;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)CEfsClient::NotifyServiceReady;
  pNotifyBuffer.dwVersion = 2;
  v4 = NotifyServiceStatusChangeW(hService, 8u, &pNotifyBuffer);
  v5 = v4;
  if ( !v4
    || v4 == 5
    && (CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, v5 + 7, v5 - 4, &TokenHandle))
    && RevertToSelf()
    && (v5 = NotifyServiceStatusChangeW(hService, v5 + 3, &pNotifyBuffer), SetThreadToken(0, TokenHandle), !v5) )
  {
    if ( SleepEx(dwMilliseconds, 1) == 192
      && !pNotifyBuffer.dwNotificationStatus
      && pNotifyBuffer.ServiceStatus.dwCurrentState == 4 )
    {
      v5 = 0;
    }
    else
    {
      v5 = 1062;
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18000ab34  mov     [rsp+arg_10], rbx
0x18000ab39  mov     [rsp+arg_18], rsi
0x18000ab3e  push    rdi
0x18000ab3f  sub     rsp, 90h
0x18000ab46  mov     rax, cs:__security_cookie
0x18000ab4d  xor     rax, rsp
0x18000ab50  mov     [rsp+98h+var_18], rax
0x18000ab58  mov     esi, edx
0x18000ab5a  mov     rdi, rcx
0x18000ab5d  xor     edx, edx; Val
0x18000ab5f  lea     rcx, [rsp+98h+pNotifyBuffer]; void *
0x18000ab64  lea     r8d, [rdx+50h]; Size
0x18000ab68  call    memset_0
0x18000ab6d  lea     rax, ?NotifyServiceReady@CEfsClient@@KAXPEAX@Z; CEfsClient::NotifyServiceReady(void *)
0x18000ab74  mov     [rsp+98h+TokenHandle], 0
0x18000ab7d  lea     r8, [rsp+98h+pNotifyBuffer]; pNotifyBuffer
0x18000ab82  mov     [rsp+98h+pNotifyBuffer.pfnNotifyCallback], rax
0x18000ab87  mov     edx, 8; dwNotifyMask
0x18000ab8c  mov     [rsp+98h+pNotifyBuffer.dwVersion], 2
0x18000ab94  mov     rcx, rdi; hService
0x18000ab97  call    cs:__imp_NotifyServiceStatusChangeW
0x18000ab9d  mov     ebx, eax
0x18000ab9f  test    eax, eax
0x18000aba1  jz      short loc_18000ABF5
0x18000aba3  cmp     eax, 5
0x18000aba6  jnz     short loc_18000AC20
0x18000aba8  call    cs:__imp_GetCurrentThread
0x18000abae  mov     rcx, rax; ThreadHandle
0x18000abb1  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x18000abb6  lea     edx, [rbx+7]; DesiredAccess
0x18000abb9  lea     r8d, [rbx-4]; OpenAsSelf
0x18000abbd  call    cs:__imp_OpenThreadToken
0x18000abc3  test    eax, eax
0x18000abc5  jz      short loc_18000AC20
0x18000abc7  call    cs:__imp_RevertToSelf
0x18000abcd  test    eax, eax
0x18000abcf  jz      short loc_18000AC20
0x18000abd1  lea     r8, [rsp+98h+pNotifyBuffer]; pNotifyBuffer
0x18000abd6  mov     rcx, rdi; hService
0x18000abd9  lea     edx, [rbx+3]; dwNotifyMask
0x18000abdc  call    cs:__imp_NotifyServiceStatusChangeW
0x18000abe2  mov     rdx, [rsp+98h+TokenHandle]; Token
0x18000abe7  xor     ecx, ecx; Thread
0x18000abe9  mov     ebx, eax
0x18000abeb  call    cs:__imp_SetThreadToken
0x18000abf1  test    ebx, ebx
0x18000abf3  jnz     short loc_18000AC20
0x18000abf5  mov     edx, 1; bAlertable
0x18000abfa  mov     ecx, esi; dwMilliseconds
0x18000abfc  call    cs:__imp_SleepEx
0x18000ac02  cmp     eax, 0C0h
0x18000ac07  jnz     short loc_18000AC1B
0x18000ac09  cmp     [rsp+98h+pNotifyBuffer.dwNotificationStatus], 0
0x18000ac0e  jnz     short loc_18000AC1B
0x18000ac10  cmp     [rsp+98h+pNotifyBuffer.ServiceStatus.dwCurrentState], 4
0x18000ac15  jnz     short loc_18000AC1B
0x18000ac17  xor     ebx, ebx
0x18000ac19  jmp     short loc_18000AC20
0x18000ac1b  mov     ebx, 426h
0x18000ac20  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x18000ac25  test    rcx, rcx
0x18000ac28  jz      short loc_18000AC30
0x18000ac2a  call    cs:__imp_CloseHandle
0x18000ac30  mov     eax, ebx
0x18000ac32  mov     rcx, [rsp+98h+var_18]
0x18000ac3a  xor     rcx, rsp; StackCookie
0x18000ac3d  call    __security_check_cookie
0x18000ac42  lea     r11, [rsp+98h+var_8]
0x18000ac4a  mov     rbx, [r11+20h]
0x18000ac4e  mov     rsi, [r11+28h]
0x18000ac52  mov     rsp, r11
0x18000ac55  pop     rdi
0x18000ac56  retn
```
