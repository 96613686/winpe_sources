# ShellHandwriting::DelegationManager::DelegateThreadProc(void)

- ea: `0x18007bc7c`
- end: `0x18007bd0b`
- name: `?DelegateThreadProc@DelegationManager@ShellHandwriting@@AEAAKXZ`
- size: `143`
- prototype: `unsigned int __fastcall(ShellHandwriting::DelegationManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1801019f0`

## callees

- `0x18007bc7c`
- `0x18007c2bc`
- `0x18007dbc0`
- `0x1800fec4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007bc92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007bc92`
- `USER32!IsGUIThread` at `0x18007bcb7`
- `USER32!IsGUIThread` at `0x18007bcb7`
- `USER32!SetThreadDesktop` at `0x18007bca8`
- `USER32!SetThreadDesktop` at `0x18007bca8`
- `USER32!GetThreadDesktop` at `0x18007bc9a`
- `USER32!GetThreadDesktop` at `0x18007bc9a`
- `USER32!DestroyWindow` at `0x18007bce7`
- `USER32!DestroyWindow` at `0x18007bce7`

## pseudocode

```c
__int64 __fastcall ShellHandwriting::DelegationManager::DelegateThreadProc(ShellHandwriting::DelegationManager *this)
{
  HDESK v1; // rdi
  DWORD CurrentThreadId; // eax
  void *v4; // rdx
  HWND v5; // rcx

  v1 = (HDESK)*((_QWORD *)this + 1);
  if ( !v1 || (CurrentThreadId = GetCurrentThreadId(), v1 == GetThreadDesktop(CurrentThreadId)) || SetThreadDesktop(v1) )
  {
    if ( IsGUIThread(1) && (int)ShellHandwriting::DelegationManager::CreateWorkerHwnd(this) >= 0 )
    {
      wil::details::SetEvent(*((wil::details **)this + 4), v4);
      ShellHandwriting::DelegationManager::RunDelegateThread(this);
    }
    v5 = (HWND)*((_QWORD *)this + 3);
    if ( v5 )
    {
      DestroyWindow(v5);
      *((_QWORD *)this + 3) = 0;
    }
    wil::details::SetEvent(*((wil::details **)this + 5), v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18007bc7c  mov     [rsp+arg_0], rbx
0x18007bc81  push    rdi
0x18007bc82  sub     rsp, 20h
0x18007bc86  mov     rdi, [rcx+8]
0x18007bc8a  mov     rbx, rcx
0x18007bc8d  test    rdi, rdi
0x18007bc90  jz      short loc_18007BCB2
0x18007bc92  call    cs:__imp_GetCurrentThreadId
0x18007bc98  mov     ecx, eax; dwThreadId
0x18007bc9a  call    cs:__imp_GetThreadDesktop
0x18007bca0  cmp     rdi, rax
0x18007bca3  jz      short loc_18007BCB2
0x18007bca5  mov     rcx, rdi; hDesktop
0x18007bca8  call    cs:__imp_SetThreadDesktop
0x18007bcae  test    eax, eax
0x18007bcb0  jz      short loc_18007BCFE
0x18007bcb2  mov     ecx, 1; bConvert
0x18007bcb7  call    cs:__imp_IsGUIThread
0x18007bcbd  test    eax, eax
0x18007bcbf  jz      short loc_18007BCDE
0x18007bcc1  mov     rcx, rbx; this
0x18007bcc4  call    ?CreateWorkerHwnd@DelegationManager@ShellHandwriting@@AEAAJXZ; ShellHandwriting::DelegationManager::CreateWorkerHwnd(void)
0x18007bcc9  test    eax, eax
0x18007bccb  js      short loc_18007BCDE
0x18007bccd  mov     rcx, [rbx+20h]; this
0x18007bcd1  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18007bcd6  mov     rcx, rbx; this
0x18007bcd9  call    ?RunDelegateThread@DelegationManager@ShellHandwriting@@AEAAXXZ; ShellHandwriting::DelegationManager::RunDelegateThread(void)
0x18007bcde  mov     rcx, [rbx+18h]; hWnd
0x18007bce2  test    rcx, rcx
0x18007bce5  jz      short loc_18007BCF5
0x18007bce7  call    cs:__imp_DestroyWindow
0x18007bced  mov     qword ptr [rbx+18h], 0
0x18007bcf5  mov     rcx, [rbx+28h]; this
0x18007bcf9  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18007bcfe  mov     rbx, [rsp+28h+arg_0]
0x18007bd03  xor     eax, eax
0x18007bd05  add     rsp, 20h
0x18007bd09  pop     rdi
0x18007bd0a  retn
```
