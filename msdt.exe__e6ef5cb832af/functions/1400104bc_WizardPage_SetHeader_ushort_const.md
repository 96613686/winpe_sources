# WizardPage::SetHeader(ushort const *)

- ea: `0x1400104bc`
- end: `0x14001055e`
- name: `?SetHeader@WizardPage@@IEAAJPEBG@Z`
- size: `162`
- prototype: `__int64 __fastcall(WizardPage *__hidden this, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140010564`
- `0x140016d90`
- `0x1400172e0`
- `0x140017920`
- `0x1400186b4`
- `0x14002f890`
- `0x14002fc60`
- `0x14003b960`
- `0x14003bc20`
- `0x14003bdf0`
- `0x14003bfc0`

## callees

- `0x1400104bc`
- `0x140020420`

## import_xrefs

- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400104d1`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400104d1`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x1400104eb`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140010535`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x1400104eb`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140010535`

## pseudocode

```c
__int64 __fastcall WizardPage::SetHeader(WizardPage *this, const unsigned __int16 *a2)
{
  HWND ParentHWND; // rax
  int v5; // eax
  int v6; // edi
  unsigned int v7; // ebx

  ParentHWND = DirectUI::TaskPage::GetParentHWND(this);
  v5 = DirectUI::TaskPage::PropSheet_SendMessage(this, 0x481u, (unsigned __int64)ParentHWND, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    DirectUI::TaskPage::PropSheet_SendMessage(this, 0x47Eu, v5, (__int64)a2);
    return (v6 >> 31) & 0x80004005;
  }
  else
  {
    v7 = -2147467259;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::SetHeader", 242, -2147467259);
  }
  return v7;
}

```

## disassembly

```asm
0x1400104bc  mov     [rsp+arg_0], rbx
0x1400104c1  mov     [rsp+arg_8], rsi
0x1400104c6  push    rdi
0x1400104c7  sub     rsp, 30h
0x1400104cb  mov     rsi, rdx
0x1400104ce  mov     rbx, rcx
0x1400104d1  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x1400104d8  nop     dword ptr [rax+rax+00h]
0x1400104dd  xor     r9d, r9d
0x1400104e0  mov     edx, 481h
0x1400104e5  mov     r8, rax
0x1400104e8  mov     rcx, rbx
0x1400104eb  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x1400104f2  nop     dword ptr [rax+rax+00h]
0x1400104f7  mov     rdi, rax
0x1400104fa  test    eax, eax
0x1400104fc  jns     short loc_140010527
0x1400104fe  mov     ebx, 80004005h
0x140010503  lea     r8, aWizardpageSeth_0; "WizardPage::SetHeader"
0x14001050a  mov     r9d, 0F2h
0x140010510  mov     [rsp+38h+var_18], ebx
0x140010514  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001051b  mov     ecx, 1; Level
0x140010520  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140010525  jmp     short loc_14001054B
0x140010527  movsxd  r8, edi
0x14001052a  mov     r9, rsi
0x14001052d  mov     edx, 47Eh
0x140010532  mov     rcx, rbx
0x140010535  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14001053c  nop     dword ptr [rax+rax+00h]
0x140010541  sar     edi, 1Fh
0x140010544  mov     ebx, 80004005h
0x140010549  and     ebx, edi
0x14001054b  mov     rsi, [rsp+38h+arg_8]
0x140010550  mov     eax, ebx
0x140010552  mov     rbx, [rsp+38h+arg_0]
0x140010557  add     rsp, 30h
0x14001055b  pop     rdi
0x14001055c  retn
```
