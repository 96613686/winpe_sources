# DetailsPage::OnMessage(uint,unsigned __int64,__int64,__int64 *)

- ea: `0x140016c80`
- end: `0x140016d7b`
- name: `?OnMessage@DetailsPage@@MEAA_NI_K_JPEA_J@Z`
- size: `251`
- prototype: `bool __fastcall(DetailsPage *__hidden this, unsigned int, unsigned __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000a340`
- `0x14000e6bc`
- `0x14000f1a0`
- `0x140016c80`
- `0x140020420`

## import_xrefs

- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140016d62`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140016d62`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140016c9d`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140016c9d`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140016cbe`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140016cbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall DetailsPage::OnMessage(
        DetailsPage *this,
        unsigned int a2,
        unsigned __int64 a3,
        OLECHAR *a4,
        __int64 *a5)
{
  char v9; // bl
  int NamedElement; // eax
  int v11; // r9d
  struct DirectUI::Element *v13; // [rsp+30h] [rbp-48h] BYREF
  DirectUI::Element *Element; // [rsp+38h] [rbp-40h]
  unsigned int v15[14]; // [rsp+40h] [rbp-38h] BYREF

  v13 = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v15[0] = 0;
  DirectUI::Element::StartDefer(Element, v15);
  if ( a2 != 2536 )
  {
    v9 = WizardPage::OnMessage(this, a2, a3, a4, a5);
    goto LABEL_9;
  }
  v9 = 0;
  NamedElement = WizardPage::GetNamedElement(this, L"details", &v13);
  if ( NamedElement < 0 )
  {
    v11 = 3256;
LABEL_5:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DetailsPage::OnMessage", v11, NamedElement);
    goto LABEL_9;
  }
  NamedElement = WebBrowser::LoadURL(v13, *((const unsigned __int16 **)Config + 28));
  if ( NamedElement < 0 )
  {
    v11 = 3259;
    goto LABEL_5;
  }
  v9 = 1;
LABEL_9:
  if ( v15[0] )
    DirectUI::Element::EndDefer(Element, v15[0]);
  return v9;
}

```

## disassembly

```asm
0x140016c80  push    rbx
0x140016c82  push    rbp
0x140016c83  push    rsi
0x140016c84  push    rdi
0x140016c85  sub     rsp, 58h
0x140016c89  mov     rsi, r9
0x140016c8c  mov     rbp, r8
0x140016c8f  mov     ebx, edx
0x140016c91  mov     rdi, rcx
0x140016c94  mov     [rsp+78h+var_48], 0
0x140016c9d  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x140016ca4  nop     dword ptr [rax+rax+00h]
0x140016ca9  mov     [rsp+78h+var_40], rax
0x140016cae  mov     [rsp+78h+var_38], 0
0x140016cb6  lea     rdx, [rsp+78h+var_38]
0x140016cbb  mov     rcx, rax
0x140016cbe  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x140016cc5  nop     dword ptr [rax+rax+00h]
0x140016cca  nop
0x140016ccb  mov     rcx, rdi; this
0x140016cce  cmp     ebx, 9E8h
0x140016cd4  jz      short loc_140016CF4
0x140016cd6  mov     rax, [rsp+78h+arg_20]
0x140016cde  mov     [rsp+78h+var_58], rax; __int64 *
0x140016ce3  mov     r9, rsi; __int64
0x140016ce6  mov     r8, rbp; unsigned __int64
0x140016ce9  mov     edx, ebx; unsigned int
0x140016ceb  call    ?OnMessage@WizardPage@@MEAA_NI_K_JPEA_J@Z; WizardPage::OnMessage(uint,unsigned __int64,__int64,__int64 *)
0x140016cf0  mov     bl, al
0x140016cf2  jmp     short loc_140016D55
0x140016cf4  xor     bl, bl
0x140016cf6  lea     r8, [rsp+78h+var_48]; struct DirectUI::Element **
0x140016cfb  lea     rdx, aDetails; "details"
0x140016d02  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140016d07  test    eax, eax
0x140016d09  jns     short loc_140016D2F
0x140016d0b  mov     r9d, 0CB8h
0x140016d11  mov     dword ptr [rsp+78h+var_58], eax
0x140016d15  lea     r8, aDetailspageOnm; "DetailsPage::OnMessage"
0x140016d1c  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140016d23  mov     ecx, 1; Level
0x140016d28  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140016d2d  jmp     short loc_140016D55
0x140016d2f  mov     rdx, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140016d36  mov     rdx, [rdx+0E0h]; unsigned __int16 *
0x140016d3d  mov     rcx, [rsp+78h+var_48]; this
0x140016d42  call    ?LoadURL@WebBrowser@@QEAAJPEBG@Z; WebBrowser::LoadURL(ushort const *)
0x140016d47  test    eax, eax
0x140016d49  jns     short loc_140016D53
0x140016d4b  mov     r9d, 0CBBh
0x140016d51  jmp     short loc_140016D11
0x140016d53  mov     bl, 1
0x140016d55  mov     edx, [rsp+78h+var_38]
0x140016d59  test    edx, edx
0x140016d5b  jz      short loc_140016D6F
0x140016d5d  mov     rcx, [rsp+78h+var_40]
0x140016d62  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x140016d69  nop     dword ptr [rax+rax+00h]
0x140016d6e  nop
0x140016d6f  mov     al, bl
0x140016d71  add     rsp, 58h
0x140016d75  pop     rdi
0x140016d76  pop     rsi
0x140016d77  pop     rbp
0x140016d78  pop     rbx
0x140016d79  retn
```
