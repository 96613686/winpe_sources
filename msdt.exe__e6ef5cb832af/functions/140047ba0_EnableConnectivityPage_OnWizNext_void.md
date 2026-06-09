# EnableConnectivityPage::OnWizNext(void)

- ea: `0x140047ba0`
- end: `0x140047c26`
- name: `?OnWizNext@EnableConnectivityPage@@MEAA_JXZ`
- size: `134`
- prototype: `__int64 __fastcall(EnableConnectivityPage *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140020420`
- `0x140047ba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140047bc0`
- `KERNEL32!GetLastError` at `0x140047bc0`
- `KERNEL32!SetEvent` at `0x140047bb0`
- `KERNEL32!SetEvent` at `0x140047bb0`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140047c0f`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140047c0f`

## pseudocode

```c
__int64 __fastcall EnableConnectivityPage::OnWizNext(EnableConnectivityPage *this)
{
  signed int LastError; // eax
  bool v3; // sf

  if ( SetEvent(qword_140080070) )
    goto LABEL_6;
  LastError = GetLastError();
  v3 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v3 = LastError < 0;
  }
  if ( !v3 )
LABEL_6:
    DirectUI::TaskPage::PropSheet_SendMessage(this, 0x471u, 5u, 0);
  else
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EnableConnectivityPage::OnWizNext", 289, LastError);
  return -1;
}

```

## disassembly

```asm
0x140047ba0  push    rbx
0x140047ba2  sub     rsp, 30h
0x140047ba6  mov     rbx, rcx
0x140047ba9  mov     rcx, cs:qword_140080070; hEvent
0x140047bb0  call    cs:__imp_SetEvent
0x140047bb7  nop     dword ptr [rax+rax+00h]
0x140047bbc  test    eax, eax
0x140047bbe  jnz     short loc_140047C00
0x140047bc0  call    cs:__imp_GetLastError
0x140047bc7  nop     dword ptr [rax+rax+00h]
0x140047bcc  test    eax, eax
0x140047bce  jle     short loc_140047BDA
0x140047bd0  movzx   eax, ax
0x140047bd3  or      eax, 80070000h
0x140047bd8  test    eax, eax
0x140047bda  jns     short loc_140047C00
0x140047bdc  mov     r9d, 121h
0x140047be2  mov     [rsp+38h+var_18], eax
0x140047be6  lea     r8, aEnableconnecti_2; "EnableConnectivityPage::OnWizNext"
0x140047bed  mov     ecx, 1; Level
0x140047bf2  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140047bf9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140047bfe  jmp     short loc_140047C1B
0x140047c00  xor     r9d, r9d
0x140047c03  mov     edx, 471h
0x140047c08  mov     rcx, rbx
0x140047c0b  lea     r8d, [r9+5]
0x140047c0f  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x140047c16  nop     dword ptr [rax+rax+00h]
0x140047c1b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140047c1f  add     rsp, 30h
0x140047c23  pop     rbx
0x140047c24  retn
```
