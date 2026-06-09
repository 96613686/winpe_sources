# WizardPage::GetNamedHandle(ushort const *,HWND__ * *)

- ea: `0x14000e72c`
- end: `0x14000e7f6`
- name: `?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(WizardPage *__hidden this, const unsigned __int16 *, HWND *)`
- caller_count: `26`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140016520`
- `0x140016ab0`
- `0x140016d90`
- `0x140017920`
- `0x140017af0`
- `0x1400182a0`
- `0x1400186b4`
- `0x140018f6c`
- `0x14002a72c`
- `0x14002add0`
- `0x14002b2b0`
- `0x14002b5a0`
- `0x14002b910`
- `0x14002ea60`
- `0x14002edb0`
- `0x14002eed0`
- `0x14002f270`
- `0x14002f5f0`
- `0x14002f890`
- `0x140030410`
- `0x1400309e0`
- `0x1400322d0`
- `0x140039ea8`
- `0x14003a610`
- `0x14003bfc0`
- `0x14003c9f0`

## callees

- `0x14000e72c`
- `0x140020420`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000e7a6`
- `KERNEL32!GetLastError` at `0x14000e7a6`
- `DUI70!StrToID` at `0x14000e753`
- `DUI70!StrToID` at `0x14000e753`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14000e765`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14000e765`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14000e741`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14000e741`

## pseudocode

```c
__int64 __fastcall WizardPage::GetNamedHandle(WizardPage *this, const unsigned __int16 *a2, HWND *a3)
{
  DirectUI::Element *Element; // rbx
  unsigned __int16 v6; // ax
  struct DirectUI::Element *Descendent; // rax
  unsigned int v8; // ebx
  int v9; // r9d
  HWND v10; // rax
  signed int LastError; // eax

  Element = DirectUI::TaskPage::GetElement(this);
  v6 = StrToID(a2);
  Descendent = DirectUI::Element::FindDescendent(Element, v6);
  if ( !Descendent )
  {
    v8 = -2147418113;
    v9 = 719;
LABEL_8:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::GetNamedHandle", v9, v8);
    return v8;
  }
  v10 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 360LL))(Descendent);
  if ( (unsigned __int64)v10 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = 722;
    goto LABEL_8;
  }
  v8 = 0;
  *a3 = v10;
  return v8;
}

```

## disassembly

```asm
0x14000e72c  mov     [rsp+arg_0], rbx
0x14000e731  mov     [rsp+arg_8], rsi
0x14000e736  push    rdi
0x14000e737  sub     rsp, 30h
0x14000e73b  mov     rsi, r8
0x14000e73e  mov     rdi, rdx
0x14000e741  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14000e748  nop     dword ptr [rax+rax+00h]
0x14000e74d  mov     rcx, rdi
0x14000e750  mov     rbx, rax
0x14000e753  call    cs:__imp_StrToID
0x14000e75a  nop     dword ptr [rax+rax+00h]
0x14000e75f  movzx   edx, ax
0x14000e762  mov     rcx, rbx
0x14000e765  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14000e76c  nop     dword ptr [rax+rax+00h]
0x14000e771  mov     rcx, rax
0x14000e774  test    rax, rax
0x14000e777  jnz     short loc_14000E786
0x14000e779  mov     ebx, 8000FFFFh
0x14000e77e  mov     r9d, 2CFh
0x14000e784  jmp     short loc_14000E7C7
0x14000e786  mov     rax, [rax]
0x14000e789  mov     rax, [rax+168h]
0x14000e790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e795  lea     rcx, [rax-1]
0x14000e799  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000e79d  ja      short loc_14000E7A6
0x14000e79f  xor     ebx, ebx
0x14000e7a1  mov     [rsi], rax
0x14000e7a4  jmp     short loc_14000E7E3
0x14000e7a6  call    cs:__imp_GetLastError
0x14000e7ad  nop     dword ptr [rax+rax+00h]
0x14000e7b2  mov     ebx, eax
0x14000e7b4  test    eax, eax
0x14000e7b6  jle     short loc_14000E7C1
0x14000e7b8  movzx   ebx, ax
0x14000e7bb  or      ebx, 80070000h
0x14000e7c1  mov     r9d, 2D2h
0x14000e7c7  lea     r8, aWizardpageGetn; "WizardPage::GetNamedHandle"
0x14000e7ce  mov     [rsp+38h+var_18], ebx
0x14000e7d2  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14000e7d9  mov     ecx, 1; Level
0x14000e7de  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14000e7e3  mov     rsi, [rsp+38h+arg_8]
0x14000e7e8  mov     eax, ebx
0x14000e7ea  mov     rbx, [rsp+38h+arg_0]
0x14000e7ef  add     rsp, 30h
0x14000e7f3  pop     rdi
0x14000e7f4  retn
```
