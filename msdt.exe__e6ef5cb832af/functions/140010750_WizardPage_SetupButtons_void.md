# WizardPage::SetupButtons(void)

- ea: `0x140010750`
- end: `0x1400108aa`
- name: `?SetupButtons@WizardPage@@IEAAXXZ`
- size: `346`
- prototype: `void __fastcall(WizardPage *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x14000f480`

## callees

- `0x140010750`
- `0x140020420`
- `0x140041c54`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140010798`
- `KERNEL32!HeapAlloc` at `0x140010798`
- `KERNEL32!HeapFree` at `0x14001088d`
- `KERNEL32!HeapFree` at `0x14001088d`
- `KERNEL32!GetProcessHeap` at `0x140010781`
- `KERNEL32!GetProcessHeap` at `0x140010879`
- `KERNEL32!GetProcessHeap` at `0x140010781`
- `KERNEL32!GetProcessHeap` at `0x140010879`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14001081e`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140010839`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140010868`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14001081e`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140010839`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140010868`

## pseudocode

```c
void __fastcall WizardPage::SetupButtons(WizardPage *this)
{
  UINT v2; // esi
  WCHAR *v3; // rbx
  __int64 v4; // r9
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rax
  int LocalString; // eax
  unsigned __int64 v8; // rax
  HANDLE v9; // rax

  v2 = (*(__int64 (__fastcall **)(WizardPage *))(*(_QWORD *)this + 216LL))(this);
  if ( !v2 )
  {
    v3 = 0;
    v4 = 0;
    goto LABEL_8;
  }
  ProcessHeap = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x200u);
  v3 = v6;
  if ( !v6 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::SetupButtons", 285, -2147024882);
    return;
  }
  LocalString = DwzLoadLocalString(v2, v6, 0x100u);
  if ( LocalString >= 0 )
  {
    v4 = (__int64)v3;
LABEL_8:
    DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Cu, 2u, v4);
    DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Cu, 0x10u, 0);
    v8 = (*(__int64 (__fastcall **)(WizardPage *))(*(_QWORD *)this + 200LL))(this);
    DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Au, v8, 19);
    if ( !v3 )
      return;
    goto LABEL_9;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::SetupButtons", 288, LocalString);
LABEL_9:
  v9 = GetProcessHeap();
  HeapFree(v9, 0, v3);
}

```

## disassembly

```asm
0x140010750  mov     [rsp+arg_0], rbx
0x140010755  mov     [rsp+arg_8], rsi
0x14001075a  push    rdi
0x14001075b  sub     rsp, 30h
0x14001075f  mov     rax, [rcx]
0x140010762  mov     rdi, rcx
0x140010765  mov     rax, [rax+0D8h]
0x14001076c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010771  mov     esi, eax
0x140010773  test    eax, eax
0x140010775  jnz     short loc_140010781
0x140010777  xor     ebx, ebx
0x140010779  xor     r9d, r9d
0x14001077c  jmp     loc_140010810
0x140010781  call    cs:__imp_GetProcessHeap
0x140010788  nop     dword ptr [rax+rax+00h]
0x14001078d  xor     edx, edx; dwFlags
0x14001078f  mov     r8d, 200h; dwBytes
0x140010795  mov     rcx, rax; hHeap
0x140010798  call    cs:__imp_HeapAlloc
0x14001079f  nop     dword ptr [rax+rax+00h]
0x1400107a4  mov     rbx, rax
0x1400107a7  test    rax, rax
0x1400107aa  jnz     short loc_1400107D5
0x1400107ac  mov     r9d, 11Dh
0x1400107b2  mov     [rsp+38h+var_18], 8007000Eh
0x1400107ba  lea     r8, aWizardpageSetu; "WizardPage::SetupButtons"
0x1400107c1  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400107c8  lea     ecx, [rax+1]; Level
0x1400107cb  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400107d0  jmp     loc_140010899
0x1400107d5  mov     r8d, 100h; cchBufferMax
0x1400107db  mov     rdx, rbx; lpBuffer
0x1400107de  mov     ecx, esi; uID
0x1400107e0  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x1400107e5  test    eax, eax
0x1400107e7  jns     short loc_14001080D
0x1400107e9  mov     r9d, 120h
0x1400107ef  mov     [rsp+38h+var_18], eax
0x1400107f3  lea     r8, aWizardpageSetu; "WizardPage::SetupButtons"
0x1400107fa  mov     ecx, 1; Level
0x1400107ff  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140010806  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001080b  jmp     short loc_140010879
0x14001080d  mov     r9, rbx
0x140010810  mov     r8d, 2
0x140010816  mov     edx, 48Ch
0x14001081b  mov     rcx, rdi
0x14001081e  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x140010825  nop     dword ptr [rax+rax+00h]
0x14001082a  xor     r9d, r9d
0x14001082d  mov     edx, 48Ch
0x140010832  mov     rcx, rdi
0x140010835  lea     r8d, [r9+10h]
0x140010839  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x140010840  nop     dword ptr [rax+rax+00h]
0x140010845  mov     rax, [rdi]
0x140010848  mov     rcx, rdi
0x14001084b  mov     rax, [rax+0C8h]
0x140010852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010857  mov     r8, rax
0x14001085a  mov     edx, 48Ah
0x14001085f  mov     r9d, 13h
0x140010865  mov     rcx, rdi
0x140010868  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14001086f  nop     dword ptr [rax+rax+00h]
0x140010874  test    rbx, rbx
0x140010877  jz      short loc_140010899
0x140010879  call    cs:__imp_GetProcessHeap
0x140010880  nop     dword ptr [rax+rax+00h]
0x140010885  mov     r8, rbx; lpMem
0x140010888  xor     edx, edx; dwFlags
0x14001088a  mov     rcx, rax; hHeap
0x14001088d  call    cs:__imp_HeapFree
0x140010894  nop     dword ptr [rax+rax+00h]
0x140010899  mov     rbx, [rsp+38h+arg_0]
0x14001089e  mov     rsi, [rsp+38h+arg_8]
0x1400108a3  add     rsp, 30h
0x1400108a7  pop     rdi
0x1400108a8  retn
```
