# SupportKeyPage::OnMessage(uint,unsigned __int64,__int64,__int64 *)

- ea: `0x14003b260`
- end: `0x14003b3e9`
- name: `?OnMessage@SupportKeyPage@@MEAA_NI_K_JPEA_J@Z`
- size: `393`
- prototype: `bool __fastcall(SupportKeyPage *__hidden this, unsigned int, unsigned __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x14000e6bc`
- `0x14000f1a0`
- `0x140020420`
- `0x14003b260`
- `0x14003cd40`
- `0x140063010`

## import_xrefs

- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14003b347`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x14003b347`
- `DUI70!StrToID` at `0x14003b306`
- `DUI70!StrToID` at `0x14003b306`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14003b318`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14003b318`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14003b3cd`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14003b3cd`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003b282`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003b2f0`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003b282`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003b2f0`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14003b2a3`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14003b2a3`

## string_xrefs

- `0x14003b375`: `linkPrivacy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall SupportKeyPage::OnMessage(
        SupportKeyPage *this,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 *a5)
{
  bool v9; // di
  DirectUI::Element *v10; // rbx
  unsigned __int16 v11; // ax
  DirectUI::Element *Descendent; // rax
  int NamedElement; // eax
  int v14; // r9d
  struct DirectUI::Element *v16; // [rsp+30h] [rbp-48h] BYREF
  DirectUI::Element *Element; // [rsp+38h] [rbp-40h]
  unsigned int v18[14]; // [rsp+40h] [rbp-38h] BYREF

  v9 = 0;
  v16 = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v18[0] = 0;
  DirectUI::Element::StartDefer(Element, v18);
  if ( a2 == 2532 )
  {
    NamedElement = WizardPage::GetNamedElement(this, L"linkPrivacy", &v16);
    if ( NamedElement < 0 )
    {
      v14 = 419;
      goto LABEL_13;
    }
    (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v16 + 168LL))(v16);
    goto LABEL_16;
  }
  if ( a2 == 2533 )
  {
    NamedElement = SupportKeyPage::SetupNextButton(this);
    if ( NamedElement < 0 )
    {
      v14 = 442;
      goto LABEL_13;
    }
LABEL_16:
    v9 = 1;
    goto LABEL_17;
  }
  if ( a2 != 2537 )
  {
    v9 = WizardPage::OnMessage(this, a2, a3, a4, a5);
    goto LABEL_17;
  }
  v10 = DirectUI::TaskPage::GetElement(this);
  v11 = StrToID(L"edit");
  Descendent = DirectUI::Element::FindDescendent(v10, v11);
  if ( !Descendent )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SupportKeyPage::OnMessage", 432, -2147418113);
    goto LABEL_17;
  }
  NamedElement = DirectUI::Element::SetContentString(Descendent, *((const unsigned __int16 **)Config + 14));
  if ( NamedElement >= 0 )
    goto LABEL_16;
  v14 = 435;
LABEL_13:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SupportKeyPage::OnMessage", v14, NamedElement);
LABEL_17:
  if ( v18[0] )
    DirectUI::Element::EndDefer(Element, v18[0]);
  return v9;
}

```

## disassembly

```asm
0x14003b260  push    rbx
0x14003b262  push    rbp
0x14003b263  push    rsi
0x14003b264  push    rdi
0x14003b265  push    r14
0x14003b267  sub     rsp, 50h
0x14003b26b  mov     rbp, r9
0x14003b26e  mov     r14, r8
0x14003b271  mov     esi, edx
0x14003b273  mov     rbx, rcx
0x14003b276  xor     dil, dil
0x14003b279  mov     [rsp+78h+var_48], 0
0x14003b282  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14003b289  nop     dword ptr [rax+rax+00h]
0x14003b28e  mov     [rsp+78h+var_40], rax
0x14003b293  mov     [rsp+78h+var_38], 0
0x14003b29b  lea     rdx, [rsp+78h+var_38]
0x14003b2a0  mov     rcx, rax
0x14003b2a3  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14003b2aa  nop     dword ptr [rax+rax+00h]
0x14003b2af  nop
0x14003b2b0  mov     eax, esi
0x14003b2b2  sub     eax, 9E4h
0x14003b2b7  mov     rcx, rbx; this
0x14003b2ba  jz      loc_14003B370
0x14003b2c0  sub     eax, 1
0x14003b2c3  jz      loc_14003B35F
0x14003b2c9  cmp     eax, 4
0x14003b2cc  jz      short loc_14003B2F0
0x14003b2ce  mov     rax, [rsp+78h+arg_20]
0x14003b2d6  mov     [rsp+78h+var_58], rax; __int64 *
0x14003b2db  mov     r9, rbp; __int64
0x14003b2de  mov     r8, r14; unsigned __int64
0x14003b2e1  mov     edx, esi; unsigned int
0x14003b2e3  call    ?OnMessage@WizardPage@@MEAA_NI_K_JPEA_J@Z; WizardPage::OnMessage(uint,unsigned __int64,__int64,__int64 *)
0x14003b2e8  mov     dil, al
0x14003b2eb  jmp     loc_14003B3C0
0x14003b2f0  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14003b2f7  nop     dword ptr [rax+rax+00h]
0x14003b2fc  mov     rbx, rax
0x14003b2ff  lea     rcx, ClassName; "edit"
0x14003b306  call    cs:__imp_StrToID
0x14003b30d  nop     dword ptr [rax+rax+00h]
0x14003b312  movzx   edx, ax
0x14003b315  mov     rcx, rbx
0x14003b318  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14003b31f  nop     dword ptr [rax+rax+00h]
0x14003b324  test    rax, rax
0x14003b327  jnz     short loc_14003B339
0x14003b329  mov     dword ptr [rsp+78h+var_58], 8000FFFFh
0x14003b331  mov     r9d, 1B0h
0x14003b337  jmp     short loc_14003B38F
0x14003b339  mov     rdx, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003b340  mov     rdx, [rdx+70h]
0x14003b344  mov     rcx, rax
0x14003b347  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x14003b34e  nop     dword ptr [rax+rax+00h]
0x14003b353  test    eax, eax
0x14003b355  jns     short loc_14003B3BD
0x14003b357  mov     r9d, 1B3h
0x14003b35d  jmp     short loc_14003B38B
0x14003b35f  call    ?SetupNextButton@SupportKeyPage@@IEAAJXZ; SupportKeyPage::SetupNextButton(void)
0x14003b364  test    eax, eax
0x14003b366  jns     short loc_14003B3BD
0x14003b368  mov     r9d, 1BAh
0x14003b36e  jmp     short loc_14003B38B
0x14003b370  lea     r8, [rsp+78h+var_48]; struct DirectUI::Element **
0x14003b375  lea     rdx, aLinkprivacy; "linkPrivacy"
0x14003b37c  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14003b381  test    eax, eax
0x14003b383  jns     short loc_14003B3A9
0x14003b385  mov     r9d, 1A3h
0x14003b38b  mov     dword ptr [rsp+78h+var_58], eax
0x14003b38f  lea     r8, aSupportkeypage_3; "SupportKeyPage::OnMessage"
0x14003b396  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003b39d  mov     ecx, 1; Level
0x14003b3a2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003b3a7  jmp     short loc_14003B3C0
0x14003b3a9  mov     rcx, [rsp+78h+var_48]
0x14003b3ae  mov     rax, [rcx]
0x14003b3b1  mov     rax, [rax+0A8h]
0x14003b3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b3bd  mov     dil, 1
0x14003b3c0  mov     edx, [rsp+78h+var_38]
0x14003b3c4  test    edx, edx
0x14003b3c6  jz      short loc_14003B3DA
0x14003b3c8  mov     rcx, [rsp+78h+var_40]
0x14003b3cd  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14003b3d4  nop     dword ptr [rax+rax+00h]
0x14003b3d9  nop
0x14003b3da  mov     al, dil
0x14003b3dd  add     rsp, 50h
0x14003b3e1  pop     r14
0x14003b3e3  pop     rdi
0x14003b3e4  pop     rsi
0x14003b3e5  pop     rbp
0x14003b3e6  pop     rbx
0x14003b3e7  retn
```
