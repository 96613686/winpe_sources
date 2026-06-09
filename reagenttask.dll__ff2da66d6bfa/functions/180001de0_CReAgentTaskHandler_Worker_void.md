# CReAgentTaskHandler::Worker(void)

- ea: `0x180001de0`
- end: `0x180001e6e`
- name: `?Worker@CReAgentTaskHandler@@EEAAJXZ`
- size: `142`
- prototype: `__int64 __fastcall(const wchar_t **this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001de0`
- `0x18000200a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e16`
- `ReAgent!WinReValidateRecoveryWim` at `0x180001e06`
- `ReAgent!WinReValidateRecoveryWim` at `0x180001e06`
- `ReAgent!WinReConfigureTask` at `0x180001e3a`
- `ReAgent!WinReConfigureTask` at `0x180001e3a`

## pseudocode

```c
__int64 __fastcall CReAgentTaskHandler::Worker(const wchar_t **this)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  bool v4; // cc

  v2 = 0;
  if ( wcscmp_0(L"VerifyWinRE", this[1]) )
    return (unsigned int)-2147024809;
  *((_DWORD *)this + 14) = 0;
  if ( (unsigned int)WinReValidateRecoveryWim() )
  {
    LastError = WinReConfigureTask(L"\\Microsoft\\Windows\\RecoveryEnvironment", L"VerifyWinRE", 1);
    v4 = LastError <= 0;
    if ( !LastError )
      return v2;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError <= 0;
  }
  if ( v4 )
    return (unsigned int)LastError;
  else
    return (unsigned __int16)LastError | 0x80070000;
}

```

## disassembly

```asm
0x180001de0  mov     [rsp+arg_0], rbx
0x180001de5  push    rdi
0x180001de6  sub     rsp, 20h
0x180001dea  mov     rdx, [rcx+8]; String2
0x180001dee  mov     rdi, rcx
0x180001df1  lea     rcx, aVerifywinre; "VerifyWinRE"
0x180001df8  call    wcscmp_0
0x180001dfd  xor     ebx, ebx
0x180001dff  test    eax, eax
0x180001e01  jnz     short loc_180001E5B
0x180001e03  mov     [rdi+38h], ebx
0x180001e06  call    cs:__imp_WinReValidateRecoveryWim
0x180001e0d  nop     dword ptr [rax+rax+00h]
0x180001e12  test    eax, eax
0x180001e14  jnz     short loc_180001E26
0x180001e16  call    cs:__imp_GetLastError
0x180001e1d  nop     dword ptr [rax+rax+00h]
0x180001e22  test    eax, eax
0x180001e24  jmp     short loc_180001E4A
0x180001e26  mov     r8d, 1
0x180001e2c  lea     rdx, aVerifywinre; "VerifyWinRE"
0x180001e33  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\RecoveryEnvironme"...
0x180001e3a  call    cs:__imp_WinReConfigureTask
0x180001e41  nop     dword ptr [rax+rax+00h]
0x180001e46  test    eax, eax
0x180001e48  jz      short loc_180001E60
0x180001e4a  jg      short loc_180001E50
0x180001e4c  mov     ebx, eax
0x180001e4e  jmp     short loc_180001E60
0x180001e50  movzx   ebx, ax
0x180001e53  or      ebx, 80070000h
0x180001e59  jmp     short loc_180001E60
0x180001e5b  mov     ebx, 80070057h
0x180001e60  mov     eax, ebx
0x180001e62  mov     rbx, [rsp+28h+arg_0]
0x180001e67  add     rsp, 20h
0x180001e6b  pop     rdi
0x180001e6c  retn
```
