# CSNOCplCore::OnWMSignatureMoved(tagNETPROFILE_EVENT_DATA * const)

- ea: `0x18000f430`
- end: `0x18000f506`
- name: `?OnWMSignatureMoved@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z`
- size: `214`
- prototype: `void __fastcall(CSNOCplCore *__hidden this, struct tagNETPROFILE_EVENT_DATA *const)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180006b70`
- `0x1800096d0`
- `0x18000a2e0`
- `0x18000b6cc`
- `0x18000b7d4`
- `0x18000f430`
- `0x18001ebfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f452`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f452`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f4b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f4b6`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000f471`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000f471`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSNOCplCore::OnWMSignatureMoved(CSNOCplCore *this, struct tagNETPROFILE_EVENT_DATA *const a2)
{
  const struct _GUID *v4; // rcx
  const struct _GUID *v5; // rcx
  DirectUI::Element *v6; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v7[4]; // [rsp+28h] [rbp-10h] BYREF

  if ( !(unsigned int)CSNOCplCore::DeferEvent(this) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    v6 = (DirectUI::Element *)*((_QWORD *)this + 40);
    v7[0] = 0;
    DirectUI::Element::StartDefer(v6, v7);
    if ( !(unsigned int)IsEmptyGUID((struct _GUID *)((char *)a2 + 4)) )
      CSNOCplCore::HandleSignatureDeleted(this, v4);
    if ( !(unsigned int)IsEmptyGUID((struct _GUID *)((char *)a2 + 20)) )
      CSNOCplCore::HandleSignatureAdded(this, v5);
    DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v6);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v6);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
}

```

## disassembly

```asm
0x18000f430  mov     [rsp+arg_0], rbx
0x18000f435  mov     [rsp+arg_8], rsi
0x18000f43a  push    rdi
0x18000f43b  sub     rsp, 30h
0x18000f43f  mov     rdi, rdx
0x18000f442  mov     rbx, rcx
0x18000f445  call    ?DeferEvent@CSNOCplCore@@AEAAHXZ; CSNOCplCore::DeferEvent(void)
0x18000f44a  test    eax, eax
0x18000f44c  jnz     short loc_18000F4C8
0x18000f44e  lea     rcx, [rbx+70h]; lpCriticalSection
0x18000f452  call    cs:__imp_EnterCriticalSection
0x18000f458  mov     rcx, [rbx+140h]
0x18000f45f  mov     [rsp+38h+var_18], rcx
0x18000f464  mov     [rsp+38h+var_10], 0
0x18000f46c  lea     rdx, [rsp+38h+var_10]
0x18000f471  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x18000f477  nop
0x18000f478  lea     rcx, [rdi+4]; struct _GUID *
0x18000f47c  call    ?IsEmptyGUID@@YAHAEAU_GUID@@@Z; IsEmptyGUID(_GUID &)
0x18000f481  test    eax, eax
0x18000f483  jnz     short loc_18000F490
0x18000f485  mov     rdx, rcx; struct _GUID *
0x18000f488  mov     rcx, rbx; this
0x18000f48b  call    ?HandleSignatureDeleted@CSNOCplCore@@AEAAJAEBU_GUID@@@Z; CSNOCplCore::HandleSignatureDeleted(_GUID const &)
0x18000f490  lea     rcx, [rdi+14h]; struct _GUID *
0x18000f494  call    ?IsEmptyGUID@@YAHAEAU_GUID@@@Z; IsEmptyGUID(_GUID &)
0x18000f499  test    eax, eax
0x18000f49b  jnz     short loc_18000F4A8
0x18000f49d  mov     rdx, rcx; struct _GUID *
0x18000f4a0  mov     rcx, rbx; this
0x18000f4a3  call    ?HandleSignatureAdded@CSNOCplCore@@AEAAJAEBU_GUID@@@Z; CSNOCplCore::HandleSignatureAdded(_GUID const &)
0x18000f4a8  lea     rcx, [rsp+38h+var_18]; this
0x18000f4ad  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x18000f4b2  lea     rcx, [rbx+70h]; lpCriticalSection
0x18000f4b6  call    cs:__imp_LeaveCriticalSection
0x18000f4bc  nop
0x18000f4bd  lea     rcx, [rsp+38h+var_18]; this
0x18000f4c2  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x18000f4c7  nop
0x18000f4c8  lea     rax, WPP_GLOBAL_Control
0x18000f4cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4d6  cmp     rcx, rax
0x18000f4d9  jz      short loc_18000F4F6
0x18000f4db  test    byte ptr [rcx+1Ch], 8
0x18000f4df  jz      short loc_18000F4F6
0x18000f4e1  mov     edx, 5Ch ; '\'
0x18000f4e6  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000f4ed  mov     rcx, [rcx+10h]
0x18000f4f1  call    WPP_SF_
0x18000f4f6  mov     rbx, [rsp+38h+arg_0]
0x18000f4fb  mov     rsi, [rsp+38h+arg_8]
0x18000f500  add     rsp, 30h
0x18000f504  pop     rdi
0x18000f505  retn
```
