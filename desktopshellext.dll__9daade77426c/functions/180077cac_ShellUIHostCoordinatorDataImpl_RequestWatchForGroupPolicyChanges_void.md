# ShellUIHostCoordinatorDataImpl::RequestWatchForGroupPolicyChanges(void)

- ea: `0x180077cac`
- end: `0x180077d79`
- name: `?RequestWatchForGroupPolicyChanges@ShellUIHostCoordinatorDataImpl@@AEAAXXZ`
- size: `205`
- prototype: `void __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001ae24`

## callees

- `0x18001a18c`
- `0x1800217d0`
- `0x18006b854`
- `0x18007490c`
- `0x180077cac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180077ce0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180077ce0`
- `USERENV!RegisterGPNotification` at `0x180077d17`
- `USERENV!RegisterGPNotification` at `0x180077d17`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180077d45`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180077d45`

## pseudocode

```c
void __fastcall ShellUIHostCoordinatorDataImpl::RequestWatchForGroupPolicyChanges(char *Context)
{
  AIXPolicyHelper *v2; // rcx
  HANDLE EventW; // rax
  const char *v4; // r9
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    Context[496] = AIXPolicyHelper::IsAllowedOnDeviceByPolicy();
    Context[497] = AIXPolicyHelper::IsA9DataAnalysisDisabledByGroupPolicy(v2);
    EventW = CreateEventW(0, 0, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      Context + 504,
      EventW);
    if ( !*((_QWORD *)Context + 63) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1B8,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\shelluihostcoordinatordata.cpp",
        v4);
    if ( RegisterGPNotification(*((HANDLE *)Context + 63), 1) )
    {
      if ( !RegisterWaitForSingleObject(
              (PHANDLE)Context + 64,
              *((HANDLE *)Context + 63),
              lambda_3ea4f28ea04135eff44d4038d794b758_::_lambda_invoker_cdecl_,
              Context,
              0xFFFFFFFF,
              0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1C6,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\shelluihostcoordinatordata.cpp",
          v5);
      Context[498] = 1;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\shelluihostcoordinatordata.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x180077cac  mov     [rsp+arg_0], rbx
0x180077cb1  push    rdi
0x180077cb2  sub     rsp, 30h
0x180077cb6  mov     rbx, rcx
0x180077cb9  call    ?IsAllowedOnDeviceByPolicy@AIXPolicyHelper@@YA_NW4AllowedOnDeviceByPolicyFlags@@@Z; AIXPolicyHelper::IsAllowedOnDeviceByPolicy(AllowedOnDeviceByPolicyFlags)
0x180077cbe  mov     [rbx+1F0h], al
0x180077cc4  call    ?IsA9DataAnalysisDisabledByGroupPolicy@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsA9DataAnalysisDisabledByGroupPolicy(void)
0x180077cc9  mov     [rbx+1F1h], al
0x180077ccf  lea     rdi, [rbx+1F8h]
0x180077cd6  xor     r9d, r9d; lpName
0x180077cd9  xor     r8d, r8d; bInitialState
0x180077cdc  xor     edx, edx; bManualReset
0x180077cde  xor     ecx, ecx; lpEventAttributes
0x180077ce0  call    cs:__imp_CreateEventW
0x180077ce6  mov     rdx, rax
0x180077ce9  mov     rcx, rdi
0x180077cec  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180077cf1  mov     rcx, [rdi]; hEvent
0x180077cf4  mov     rax, [rsp+38h]
0x180077cf9  test    rcx, rcx
0x180077cfc  jnz     short loc_180077D12
0x180077cfe  lea     r8, aShellOnecoreDe_10; "shell\\onecore\\desktopshellext\\lib\\s"...
0x180077d05  mov     edx, 1B8h; void *
0x180077d0a  mov     rcx, rax; this
0x180077d0d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180077d12  mov     edx, 1; bMachine
0x180077d17  call    cs:__imp_RegisterGPNotification
0x180077d1d  test    eax, eax
0x180077d1f  jz      short loc_180077D6C
0x180077d21  lea     rcx, [rbx+200h]; phNewWaitObject
0x180077d28  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180077d30  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180077d38  mov     r9, rbx; Context
0x180077d3b  lea     r8, _lambda_3ea4f28ea04135eff44d4038d794b758____lambda_invoker_cdecl_; Callback
0x180077d42  mov     rdx, [rdi]; hObject
0x180077d45  call    cs:__imp_RegisterWaitForSingleObject
0x180077d4b  mov     rcx, [rsp+38h]; this
0x180077d50  test    eax, eax
0x180077d52  jnz     short loc_180077D65
0x180077d54  lea     r8, aShellOnecoreDe_10; "shell\\onecore\\desktopshellext\\lib\\s"...
0x180077d5b  mov     edx, 1C6h; void *
0x180077d60  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180077d65  mov     byte ptr [rbx+1F2h], 1
0x180077d6c  jmp     short $+2
0x180077d6e  mov     rbx, [rsp+38h+arg_0]
0x180077d73  add     rsp, 30h
0x180077d77  pop     rdi
0x180077d78  retn
```
