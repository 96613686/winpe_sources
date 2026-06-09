# WizardPage::CloseButton(void)

- ea: `0x14000e0f0`
- end: `0x14000e201`
- name: `?CloseButton@WizardPage@@IEAAJXZ`
- size: `273`
- prototype: `__int64 __fastcall(WizardPage *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400177b0`
- `0x140017920`
- `0x14001af10`
- `0x14003b960`

## callees

- `0x14000e0f0`
- `0x140020420`
- `0x140041c54`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000e119`
- `KERNEL32!HeapAlloc` at `0x14000e119`
- `KERNEL32!HeapFree` at `0x14000e1e2`
- `KERNEL32!HeapFree` at `0x14000e1e2`
- `KERNEL32!GetProcessHeap` at `0x14000e102`
- `KERNEL32!GetProcessHeap` at `0x14000e1ce`
- `KERNEL32!GetProcessHeap` at `0x14000e102`
- `KERNEL32!GetProcessHeap` at `0x14000e1ce`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14000e1a5`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14000e1c2`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14000e1a5`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14000e1c2`

## pseudocode

```c
__int64 __fastcall WizardPage::CloseButton(WizardPage *this)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v3; // rax
  WCHAR *v4; // rdi
  unsigned int v5; // ebx
  int LocalString; // eax
  HANDLE v7; // rax

  ProcessHeap = GetProcessHeap();
  v3 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x200u);
  v4 = v3;
  if ( v3 )
  {
    LocalString = DwzLoadLocalString(0x154u, v3, 0x100u);
    v5 = LocalString;
    if ( LocalString >= 0 )
    {
      DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Au, 0x10u, 18);
      DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Cu, 0x10u, (__int64)v4);
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::CloseButton", 1305, LocalString);
    }
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v4);
  }
  else
  {
    v5 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::CloseButton", 1302, -2147024882);
  }
  return v5;
}

```

## disassembly

```asm
0x14000e0f0  mov     [rsp+arg_0], rbx
0x14000e0f5  mov     [rsp+arg_8], rsi
0x14000e0fa  push    rdi
0x14000e0fb  sub     rsp, 30h
0x14000e0ff  mov     rsi, rcx
0x14000e102  call    cs:__imp_GetProcessHeap
0x14000e109  nop     dword ptr [rax+rax+00h]
0x14000e10e  xor     edx, edx; dwFlags
0x14000e110  mov     r8d, 200h; dwBytes
0x14000e116  mov     rcx, rax; hHeap
0x14000e119  call    cs:__imp_HeapAlloc
0x14000e120  nop     dword ptr [rax+rax+00h]
0x14000e125  mov     rdi, rax
0x14000e128  test    rax, rax
0x14000e12b  jnz     short loc_14000E157
0x14000e12d  mov     ebx, 8007000Eh
0x14000e132  lea     r8, aWizardpageClos; "WizardPage::CloseButton"
0x14000e139  mov     r9d, 516h
0x14000e13f  mov     [rsp+38h+var_18], ebx
0x14000e143  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14000e14a  lea     ecx, [rax+1]; Level
0x14000e14d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14000e152  jmp     loc_14000E1EE
0x14000e157  mov     r8d, 100h; cchBufferMax
0x14000e15d  mov     rdx, rdi; lpBuffer
0x14000e160  lea     ecx, [r8+54h]; uID
0x14000e164  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14000e169  mov     ebx, eax
0x14000e16b  test    eax, eax
0x14000e16d  jns     short loc_14000E193
0x14000e16f  mov     r9d, 519h
0x14000e175  mov     [rsp+38h+var_18], eax
0x14000e179  lea     r8, aWizardpageClos; "WizardPage::CloseButton"
0x14000e180  mov     ecx, 1; Level
0x14000e185  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14000e18c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14000e191  jmp     short loc_14000E1CE
0x14000e193  mov     r9d, 12h
0x14000e199  mov     edx, 48Ah
0x14000e19e  mov     rcx, rsi
0x14000e1a1  lea     r8d, [r9-2]
0x14000e1a5  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14000e1ac  nop     dword ptr [rax+rax+00h]
0x14000e1b1  mov     r9, rdi
0x14000e1b4  mov     edx, 48Ch
0x14000e1b9  mov     r8d, 10h
0x14000e1bf  mov     rcx, rsi
0x14000e1c2  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14000e1c9  nop     dword ptr [rax+rax+00h]
0x14000e1ce  call    cs:__imp_GetProcessHeap
0x14000e1d5  nop     dword ptr [rax+rax+00h]
0x14000e1da  mov     r8, rdi; lpMem
0x14000e1dd  xor     edx, edx; dwFlags
0x14000e1df  mov     rcx, rax; hHeap
0x14000e1e2  call    cs:__imp_HeapFree
0x14000e1e9  nop     dword ptr [rax+rax+00h]
0x14000e1ee  mov     rsi, [rsp+38h+arg_8]
0x14000e1f3  mov     eax, ebx
0x14000e1f5  mov     rbx, [rsp+38h+arg_0]
0x14000e1fa  add     rsp, 30h
0x14000e1fe  pop     rdi
0x14000e1ff  retn
```
