# CSNOCplCore::DeleteConnectionDUI(_GUID const &,tagNETCON_PROPERTIES *)

- ea: `0x18000981c`
- end: `0x18000992f`
- name: `?DeleteConnectionDUI@CSNOCplCore@@AEAAJAEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z`
- size: `275`
- prototype: `int(CSNOCplCore *__hidden this, const struct _GUID *, struct tagNETCON_PROPERTIES *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009c1c`
- `0x180012b6c`

## callees

- `0x180002270`
- `0x18000981c`
- `0x180012580`
- `0x180014274`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009852`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009852`
- `DUI70!StrToID` at `0x180009864`
- `DUI70!StrToID` at `0x180009885`
- `DUI70!StrToID` at `0x1800098b1`
- `DUI70!StrToID` at `0x180009864`
- `DUI70!StrToID` at `0x180009885`
- `DUI70!StrToID` at `0x1800098b1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009870`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009891`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800098bd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009870`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009891`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800098bd`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800098d1`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800098d1`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800098de`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800098de`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::DeleteConnectionDUI(
        CSNOCplCore *this,
        const struct _GUID *a2,
        struct tagNETCON_PROPERTIES *a3)
{
  unsigned int v5; // esi
  DirectUI::Element *v6; // rbx
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rbx
  unsigned __int16 v9; // ax
  DirectUI::Element *v10; // rbx
  unsigned int v11; // r8d
  unsigned __int16 v12; // ax
  struct DirectUI::Element *v13; // rax
  DirectUI::Element *v14; // rdi
  OLECHAR sz[40]; // [rsp+20h] [rbp-78h] BYREF

  v5 = -2147418113;
  StringFromGUID2(a2, sz, 39);
  v6 = (DirectUI::Element *)*((_QWORD *)this + 40);
  v7 = StrToID(sz);
  Descendent = DirectUI::Element::FindDescendent(v6, v7);
  if ( Descendent )
  {
    v9 = StrToID(L"connlist");
    v10 = DirectUI::Element::FindDescendent(Descendent, v9);
    if ( v10 )
    {
      StringFromGUID2(&a3->guidId, sz, v11);
      v12 = StrToID(sz);
      v13 = DirectUI::Element::FindDescendent(v10, v12);
      v14 = v13;
      if ( v13 )
      {
        v5 = DirectUI::Element::Remove(v10, v13);
        DirectUI::Element::Destroy(v14, 0);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000981c  push    rbx
0x18000981e  push    rsi
0x18000981f  push    rdi
0x180009820  sub     rsp, 80h
0x180009827  mov     rax, cs:__security_cookie
0x18000982e  xor     rax, rsp
0x180009831  mov     [rsp+98h+var_28], rax
0x180009836  mov     rax, rdx
0x180009839  mov     rdi, r8
0x18000983c  mov     rbx, rcx
0x18000983f  lea     rdx, [rsp+98h+sz]; lpsz
0x180009844  mov     rcx, rax; rguid
0x180009847  mov     r8d, 27h ; '''; cchMax
0x18000984d  mov     esi, 8000FFFFh
0x180009852  call    cs:__imp_StringFromGUID2
0x180009858  mov     rbx, [rbx+140h]
0x18000985f  lea     rcx, [rsp+98h+sz]
0x180009864  call    cs:__imp_StrToID
0x18000986a  movzx   edx, ax
0x18000986d  mov     rcx, rbx
0x180009870  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009876  mov     rbx, rax
0x180009879  test    rax, rax
0x18000987c  jz      short loc_1800098E4
0x18000987e  lea     rcx, aConnlist; "connlist"
0x180009885  call    cs:__imp_StrToID
0x18000988b  movzx   edx, ax
0x18000988e  mov     rcx, rbx
0x180009891  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009897  mov     rbx, rax
0x18000989a  test    rax, rax
0x18000989d  jz      short loc_1800098E4
0x18000989f  lea     rdx, [rsp+98h+sz]; unsigned __int16 *
0x1800098a4  mov     rcx, rdi; struct _GUID *
0x1800098a7  call    ?StringFromGUID2@@YAXAEAU_GUID@@PEAGK@Z; StringFromGUID2(_GUID &,ushort *,ulong)
0x1800098ac  lea     rcx, [rsp+98h+sz]
0x1800098b1  call    cs:__imp_StrToID
0x1800098b7  movzx   edx, ax
0x1800098ba  mov     rcx, rbx
0x1800098bd  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800098c3  mov     rdi, rax
0x1800098c6  test    rax, rax
0x1800098c9  jz      short loc_1800098E4
0x1800098cb  mov     rdx, rax
0x1800098ce  mov     rcx, rbx
0x1800098d1  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x1800098d7  xor     edx, edx
0x1800098d9  mov     rcx, rdi
0x1800098dc  mov     esi, eax
0x1800098de  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800098e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098eb  lea     rax, WPP_GLOBAL_Control
0x1800098f2  cmp     rcx, rax
0x1800098f5  jz      short loc_180009915
0x1800098f7  test    byte ptr [rcx+1Ch], 8
0x1800098fb  jz      short loc_180009915
0x1800098fd  mov     rcx, [rcx+10h]
0x180009901  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180009908  mov     edx, 92h
0x18000990d  mov     r9d, esi
0x180009910  call    WPP_SF_d
0x180009915  mov     eax, esi
0x180009917  mov     rcx, [rsp+98h+var_28]
0x18000991c  xor     rcx, rsp; StackCookie
0x18000991f  call    __security_check_cookie
0x180009924  add     rsp, 80h
0x18000992b  pop     rdi
0x18000992c  pop     rsi
0x18000992d  pop     rbx
0x18000992e  retn
```
