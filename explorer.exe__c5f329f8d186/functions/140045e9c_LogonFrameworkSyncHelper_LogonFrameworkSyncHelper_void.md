# LogonFrameworkSyncHelper::LogonFrameworkSyncHelper(void)

- ea: `0x140045e9c`
- end: `0x140045f6a`
- name: `??0LogonFrameworkSyncHelper@@QEAA@XZ`
- size: `206`
- prototype: `LogonFrameworkSyncHelper *__fastcall(LogonFrameworkSyncHelper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140046440`
- `0x14015a5c8`

## callees

- `0x140045e9c`
- `0x140045f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140045f12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140045f3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140045f12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140045f3e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140045ebc`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140045ee4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140045ebc`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140045ee4`

## string_xrefs

- `0x140045eae`: `FSIAorRestoreUIReady`
- `0x140045f04`: `FSIAorRestoreUIReady`

## pseudocode

```c
LogonFrameworkSyncHelper *__fastcall LogonFrameworkSyncHelper::LogonFrameworkSyncHelper(LogonFrameworkSyncHelper *this)
{
  HANDLE v2; // rax
  HANDLE EventW; // rax
  HANDLE v4; // rax

  *((_QWORD *)this + 1) = OpenEventW(0x100002u, 0, L"FSIAorRestoreUIReady");
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  v2 = OpenEventW(0x100002u, 0, L"RestoreOptinUIExiting");
  *((_QWORD *)this + 2) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  *((_QWORD *)this + 3) = v2;
  if ( !*((_QWORD *)this + 1) )
  {
    EventW = CreateEventW(0, 1, 0, L"FSIAorRestoreUIReady");
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(this, EventW);
  }
  if ( !*((_QWORD *)this + 3) )
  {
    v4 = CreateEventW(0, 1, 0, L"RestoreOptinUIExiting");
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      (char *)this + 16,
      v4);
  }
  return this;
}

```

## disassembly

```asm
0x140045e9c  mov     [rsp+arg_0], rbx
0x140045ea1  mov     [rsp+arg_8], rsi
0x140045ea6  push    rdi
0x140045ea7  sub     rsp, 20h
0x140045eab  mov     rbx, rcx
0x140045eae  lea     r8, aFsiaorrestoreu; "FSIAorRestoreUIReady"
0x140045eb5  mov     ecx, 100002h; dwDesiredAccess
0x140045eba  xor     edx, edx; bInheritHandle
0x140045ebc  call    cs:__imp_OpenEventW
0x140045ec3  nop     dword ptr [rax+rax+00h]
0x140045ec8  lea     rsi, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x140045ecf  xor     edx, edx; bInheritHandle
0x140045ed1  lea     r8, aRestoreoptinui; "RestoreOptinUIExiting"
0x140045ed8  mov     [rbx+8], rax
0x140045edc  mov     ecx, 100002h; dwDesiredAccess
0x140045ee1  mov     [rbx], rsi
0x140045ee4  call    cs:__imp_OpenEventW
0x140045eeb  nop     dword ptr [rax+rax+00h]
0x140045ef0  mov     [rbx+10h], rsi
0x140045ef4  mov     esi, 1
0x140045ef9  mov     [rbx+18h], rax
0x140045efd  cmp     qword ptr [rbx+8], 0
0x140045f02  jnz     short loc_140045F29
0x140045f04  lea     r9, aFsiaorrestoreu; "FSIAorRestoreUIReady"
0x140045f0b  xor     r8d, r8d; bInitialState
0x140045f0e  mov     edx, esi; bManualReset
0x140045f10  xor     ecx, ecx; lpEventAttributes
0x140045f12  call    cs:__imp_CreateEventW
0x140045f19  nop     dword ptr [rax+rax+00h]
0x140045f1e  mov     rdx, rax
0x140045f21  mov     rcx, rbx
0x140045f24  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x140045f29  cmp     qword ptr [rbx+18h], 0
0x140045f2e  jnz     short loc_140045F56
0x140045f30  lea     r9, aRestoreoptinui; "RestoreOptinUIExiting"
0x140045f37  xor     r8d, r8d; bInitialState
0x140045f3a  mov     edx, esi; bManualReset
0x140045f3c  xor     ecx, ecx; lpEventAttributes
0x140045f3e  call    cs:__imp_CreateEventW
0x140045f45  nop     dword ptr [rax+rax+00h]
0x140045f4a  mov     rdx, rax
0x140045f4d  lea     rcx, [rbx+10h]
0x140045f51  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x140045f56  mov     rsi, [rsp+28h+arg_8]
0x140045f5b  mov     rax, rbx
0x140045f5e  mov     rbx, [rsp+28h+arg_0]
0x140045f63  add     rsp, 20h
0x140045f67  pop     rdi
0x140045f68  retn
```
