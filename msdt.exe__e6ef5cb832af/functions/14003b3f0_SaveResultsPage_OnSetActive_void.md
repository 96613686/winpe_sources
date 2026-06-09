# SaveResultsPage::OnSetActive(void)

- ea: `0x14003b3f0`
- end: `0x14003b4ee`
- name: `?OnSetActive@SaveResultsPage@@MEAA_JXZ`
- size: `254`
- prototype: `__int64 __fastcall(SaveResultsPage *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x14000f480`
- `0x140020420`
- `0x14003b3f0`
- `0x140041c54`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14003b442`
- `KERNEL32!HeapAlloc` at `0x14003b442`
- `KERNEL32!GetProcessHeap` at `0x14003b42b`
- `KERNEL32!GetProcessHeap` at `0x14003b42b`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14003b4d3`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14003b4d3`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003b3fd`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003b3fd`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14003b41e`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14003b41e`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003b4b9`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003b4b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SaveResultsPage::OnSetActive(SaveResultsPage *this)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v3; // rdi
  int LocalString; // eax
  DirectUI::Element *Element; // [rsp+30h] [rbp-18h]
  unsigned int v7[4]; // [rsp+38h] [rbp-10h] BYREF

  Element = DirectUI::TaskPage::GetElement(this);
  v7[0] = 0;
  DirectUI::Element::StartDefer(Element, v7);
  ProcessHeap = GetProcessHeap();
  v3 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x200u);
  if ( v3 )
  {
    WizardPage::OnSetActive(this);
    LocalString = DwzLoadLocalString(0x155u, v3, 0x100u);
    if ( LocalString >= 0 )
      DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Cu, 2u, (__int64)v3);
    else
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SaveResultsPage::OnSetActive", 1738, LocalString);
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SaveResultsPage::OnSetActive", 1733, -2147024882);
  }
  if ( v7[0] )
    DirectUI::Element::EndDefer(Element, v7[0]);
  return 0;
}

```

## disassembly

```asm
0x14003b3f0  mov     [rsp+arg_0], rbx
0x14003b3f5  push    rdi
0x14003b3f6  sub     rsp, 40h
0x14003b3fa  mov     rbx, rcx
0x14003b3fd  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14003b404  nop     dword ptr [rax+rax+00h]
0x14003b409  mov     [rsp+48h+var_18], rax
0x14003b40e  mov     [rsp+48h+var_10], 0
0x14003b416  lea     rdx, [rsp+48h+var_10]
0x14003b41b  mov     rcx, rax
0x14003b41e  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14003b425  nop     dword ptr [rax+rax+00h]
0x14003b42a  nop
0x14003b42b  call    cs:__imp_GetProcessHeap
0x14003b432  nop     dword ptr [rax+rax+00h]
0x14003b437  mov     rcx, rax; hHeap
0x14003b43a  xor     edx, edx; dwFlags
0x14003b43c  mov     r8d, 200h; dwBytes
0x14003b442  call    cs:__imp_HeapAlloc
0x14003b449  nop     dword ptr [rax+rax+00h]
0x14003b44e  mov     rdi, rax
0x14003b451  test    rax, rax
0x14003b454  jnz     short loc_14003B47E
0x14003b456  mov     [rsp+48h+var_28], 8007000Eh
0x14003b45e  mov     r9d, 6C5h
0x14003b464  lea     r8, aSaveresultspag; "SaveResultsPage::OnSetActive"
0x14003b46b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003b472  mov     ecx, 1; Level
0x14003b477  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003b47c  jmp     short loc_14003B4C6
0x14003b47e  mov     rcx, rbx; this
0x14003b481  call    ?OnSetActive@WizardPage@@MEAA_JXZ; WizardPage::OnSetActive(void)
0x14003b486  mov     r8d, 100h; cchBufferMax
0x14003b48c  mov     rdx, rdi; lpBuffer
0x14003b48f  lea     ecx, [r8+55h]; uID
0x14003b493  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14003b498  test    eax, eax
0x14003b49a  jns     short loc_14003B4A8
0x14003b49c  mov     [rsp+48h+var_28], eax
0x14003b4a0  mov     r9d, 6CAh
0x14003b4a6  jmp     short loc_14003B464
0x14003b4a8  mov     r9, rdi
0x14003b4ab  mov     edx, 48Ch
0x14003b4b0  mov     r8d, 2
0x14003b4b6  mov     rcx, rbx
0x14003b4b9  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14003b4c0  nop     dword ptr [rax+rax+00h]
0x14003b4c5  nop
0x14003b4c6  mov     edx, [rsp+48h+var_10]
0x14003b4ca  test    edx, edx
0x14003b4cc  jz      short loc_14003B4E0
0x14003b4ce  mov     rcx, [rsp+48h+var_18]
0x14003b4d3  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14003b4da  nop     dword ptr [rax+rax+00h]
0x14003b4df  nop
0x14003b4e0  xor     eax, eax
0x14003b4e2  mov     rbx, [rsp+48h+arg_0]
0x14003b4e7  add     rsp, 40h
0x14003b4eb  pop     rdi
0x14003b4ec  retn
```
