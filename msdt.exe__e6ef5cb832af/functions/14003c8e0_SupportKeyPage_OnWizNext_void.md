# SupportKeyPage::OnWizNext(void)

- ea: `0x14003c8e0`
- end: `0x14003c9e9`
- name: `?OnWizNext@SupportKeyPage@@MEAA_JXZ`
- size: `265`
- prototype: `__int64 __fastcall(SupportKeyPage *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x14000f720`
- `0x140020420`
- `0x140020ec4`
- `0x140029d38`
- `0x14003c8e0`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14003c9c9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14003c9c9`
- `DUI70!StrToID` at `0x14003c91d`
- `DUI70!StrToID` at `0x14003c91d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14003c92f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14003c92f`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003c907`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003c907`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x14003c970`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x14003c970`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x14003c981`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x14003c981`

## pseudocode

```c
__int64 __fastcall SupportKeyPage::OnWizNext(SupportKeyPage *this)
{
  __int64 v2; // rdi
  DirectUI::Element *Element; // rbx
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  const unsigned __int16 *String; // rax
  int v7; // eax
  Configuration *v8; // rcx
  struct DirectUI::Value *v10; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int16 *v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  v2 = -1;
  v10 = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v4 = StrToID(L"edit");
  Descendent = DirectUI::Element::FindDescendent(Element, v4);
  if ( Descendent )
  {
    DirectUI::Element::GetContentString(Descendent, &v10);
    String = DirectUI::Value::GetString(v10);
    v7 = DwzStringTrim(String, &v11);
    if ( v7 >= 0 )
    {
      Configuration::SupportKey(v8, v11);
      v2 = WizardPage::OnWizNext(this);
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SupportKeyPage::OnWizNext", 194, v7);
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SupportKeyPage::OnWizNext", 188, -2147418113);
  }
  if ( v10 )
    DirectUI::Value::Release(v10);
  return v2;
}

```

## disassembly

```asm
0x14003c8e0  mov     rax, rsp
0x14003c8e3  mov     [rax+8], rbx
0x14003c8e7  mov     [rax+20h], rsi
0x14003c8eb  push    rdi
0x14003c8ec  sub     rsp, 30h
0x14003c8f0  mov     rsi, rcx
0x14003c8f3  mov     qword ptr [rax+18h], 0
0x14003c8fb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003c8ff  mov     qword ptr [rax+10h], 0
0x14003c907  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14003c90e  nop     dword ptr [rax+rax+00h]
0x14003c913  lea     rcx, ClassName; "edit"
0x14003c91a  mov     rbx, rax
0x14003c91d  call    cs:__imp_StrToID
0x14003c924  nop     dword ptr [rax+rax+00h]
0x14003c929  movzx   edx, ax
0x14003c92c  mov     rcx, rbx
0x14003c92f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14003c936  nop     dword ptr [rax+rax+00h]
0x14003c93b  test    rax, rax
0x14003c93e  jnz     short loc_14003C968
0x14003c940  mov     [rsp+38h+var_18], 8000FFFFh
0x14003c948  mov     r9d, 0BCh
0x14003c94e  lea     r8, aSupportkeypage_4; "SupportKeyPage::OnWizNext"
0x14003c955  mov     ecx, 1; Level
0x14003c95a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003c961  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003c966  jmp     short loc_14003C9BF
0x14003c968  lea     rdx, [rsp+38h+arg_8]
0x14003c96d  mov     rcx, rax
0x14003c970  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x14003c977  nop     dword ptr [rax+rax+00h]
0x14003c97c  mov     rcx, [rsp+38h+arg_8]
0x14003c981  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x14003c988  nop     dword ptr [rax+rax+00h]
0x14003c98d  mov     rcx, rax; unsigned __int16 *
0x14003c990  lea     rdx, [rsp+38h+arg_10]; unsigned __int16 **
0x14003c995  call    ?DwzStringTrim@@YAJPEBGPEAPEAG@Z; DwzStringTrim(ushort const *,ushort * *)
0x14003c99a  test    eax, eax
0x14003c99c  jns     short loc_14003C9AA
0x14003c99e  mov     [rsp+38h+var_18], eax
0x14003c9a2  mov     r9d, 0C2h
0x14003c9a8  jmp     short loc_14003C94E
0x14003c9aa  mov     rdx, [rsp+38h+arg_10]; unsigned __int16 *
0x14003c9af  call    ?SupportKey@Configuration@@QEAAXPEAG@Z; Configuration::SupportKey(ushort *)
0x14003c9b4  mov     rcx, rsi; this
0x14003c9b7  call    ?OnWizNext@WizardPage@@MEAA_JXZ; WizardPage::OnWizNext(void)
0x14003c9bc  mov     rdi, rax
0x14003c9bf  mov     rcx, [rsp+38h+arg_8]
0x14003c9c4  test    rcx, rcx
0x14003c9c7  jz      short loc_14003C9D5
0x14003c9c9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x14003c9d0  nop     dword ptr [rax+rax+00h]
0x14003c9d5  mov     rbx, [rsp+38h+arg_0]
0x14003c9da  mov     rax, rdi
0x14003c9dd  mov     rsi, [rsp+38h+arg_18]
0x14003c9e2  add     rsp, 30h
0x14003c9e6  pop     rdi
0x14003c9e7  retn
```
