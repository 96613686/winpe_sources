# EnableBWCPage::OnWizNext(void)

- ea: `0x140047b10`
- end: `0x140047b95`
- name: `?OnWizNext@EnableBWCPage@@MEAA_JXZ`
- size: `133`
- prototype: `__int64 __fastcall(EnableBWCPage *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140020420`
- `0x140047b10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140047b30`
- `KERNEL32!GetLastError` at `0x140047b30`
- `KERNEL32!SetEvent` at `0x140047b20`
- `KERNEL32!SetEvent` at `0x140047b20`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140047b7e`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140047b7e`

## pseudocode

```c
__int64 __fastcall EnableBWCPage::OnWizNext(EnableBWCPage *this)
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
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EnableBWCPage::OnWizNext", 110, LastError);
  return -1;
}

```

## disassembly

```asm
0x140047b10  push    rbx
0x140047b12  sub     rsp, 30h
0x140047b16  mov     rbx, rcx
0x140047b19  mov     rcx, cs:qword_140080070; hEvent
0x140047b20  call    cs:__imp_SetEvent
0x140047b27  nop     dword ptr [rax+rax+00h]
0x140047b2c  test    eax, eax
0x140047b2e  jnz     short loc_140047B6F
0x140047b30  call    cs:__imp_GetLastError
0x140047b37  nop     dword ptr [rax+rax+00h]
0x140047b3c  test    eax, eax
0x140047b3e  jle     short loc_140047B4A
0x140047b40  movzx   eax, ax
0x140047b43  or      eax, 80070000h
0x140047b48  test    eax, eax
0x140047b4a  jns     short loc_140047B6F
0x140047b4c  mov     r9d, 6Eh ; 'n'
0x140047b52  mov     [rsp+38h+var_18], eax
0x140047b56  lea     r8, aEnablebwcpageO_0; "EnableBWCPage::OnWizNext"
0x140047b5d  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140047b64  lea     ecx, [r9-6Dh]; Level
0x140047b68  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140047b6d  jmp     short loc_140047B8A
0x140047b6f  xor     r9d, r9d
0x140047b72  mov     edx, 471h
0x140047b77  mov     rcx, rbx
0x140047b7a  lea     r8d, [r9+5]
0x140047b7e  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x140047b85  nop     dword ptr [rax+rax+00h]
0x140047b8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x140047b8e  add     rsp, 30h
0x140047b92  pop     rbx
0x140047b93  retn
```
