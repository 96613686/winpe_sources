# CSNOCplCore::UpdateConnectionIcon(DirectUI::Element *,_GUID const &,tagNETCON_PROPERTIES *)

- ea: `0x180012a84`
- end: `0x180012b65`
- name: `?UpdateConnectionIcon@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct DirectUI::Element *, const struct _GUID *, struct tagNETCON_PROPERTIES *)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008b7c`
- `0x18000c36c`
- `0x180012978`

## callees

- `0x180011504`
- `0x180012a84`

## import_xrefs

- `DUI70!StrToID` at `0x180012aa3`
- `DUI70!StrToID` at `0x180012aa3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012aaf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012aaf`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::UpdateConnectionIcon(
        CSNOCplCore *this,
        struct DirectUI::Element *a2,
        const struct _GUID *a3,
        struct tagNETCON_PROPERTIES *a4)
{
  unsigned int v7; // esi
  unsigned __int16 v8; // ax
  CSNOCplCore *v9; // rcx
  struct DirectUI::Element *Descendent; // r10
  int v11; // r8d
  _QWORD *v12; // r9
  _QWORD *v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // r9
  _QWORD *v16; // rax
  __int64 v17; // rdx

  v7 = -2147467259;
  v8 = StrToID(L"connectionicon");
  Descendent = DirectUI::Element::FindDescendent(a2, v8);
  if ( Descendent )
  {
    v11 = 28;
    if ( *((_QWORD *)this + 28) )
    {
      v12 = (_QWORD *)*((_QWORD *)this + 27);
      v13 = (_QWORD *)*v12;
      while ( v13 != v12 )
      {
        v14 = v13[2];
        v9 = (CSNOCplCore *)(*(_QWORD *)&a4->guidId.Data1 - *(_QWORD *)v14);
        if ( *(_QWORD *)&a4->guidId.Data1 == *(_QWORD *)v14 )
          v9 = (CSNOCplCore *)(*(_QWORD *)a4->guidId.Data4 - *(_QWORD *)(v14 + 8));
        if ( !v9 )
          v11 = *(_DWORD *)(v14 + 16) + 14;
        v13 = (_QWORD *)*v13;
        if ( v11 != 28 )
          return (unsigned int)CSNOCplCore::SetIconFromRes(v9, Descendent, v11);
      }
    }
    if ( *((_QWORD *)this + 30) )
    {
      v15 = (_QWORD *)*((_QWORD *)this + 29);
      v16 = (_QWORD *)*v15;
      do
      {
        if ( v16 == v15 )
          break;
        v17 = v16[2];
        v9 = (CSNOCplCore *)(*(_QWORD *)&a4->guidId.Data1 - *(_QWORD *)v17);
        if ( *(_QWORD *)&a4->guidId.Data1 == *(_QWORD *)v17 )
          v9 = (CSNOCplCore *)(*(_QWORD *)a4->guidId.Data4 - *(_QWORD *)(v17 + 8));
        if ( !v9 )
          v11 = *(_DWORD *)(v17 + 16) + 14;
        v16 = (_QWORD *)*v16;
      }
      while ( v11 == 28 );
    }
    return (unsigned int)CSNOCplCore::SetIconFromRes(v9, Descendent, v11);
  }
  return v7;
}

```

## disassembly

```asm
0x180012a84  push    rbx
0x180012a86  push    rsi
0x180012a87  push    rdi
0x180012a88  push    r14
0x180012a8a  sub     rsp, 28h
0x180012a8e  mov     rdi, rcx
0x180012a91  mov     r14, r9
0x180012a94  lea     rcx, aConnectionicon; "connectionicon"
0x180012a9b  mov     rbx, rdx
0x180012a9e  mov     esi, 80004005h
0x180012aa3  call    cs:__imp_StrToID
0x180012aa9  movzx   edx, ax
0x180012aac  mov     rcx, rbx
0x180012aaf  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012ab5  mov     r10, rax
0x180012ab8  test    rax, rax
0x180012abb  jz      loc_180012B59
0x180012ac1  cmp     qword ptr [rdi+0E0h], 0
0x180012ac9  mov     r8d, 1Ch
0x180012acf  jz      short loc_180012B0C
0x180012ad1  mov     r9, [rdi+0D8h]
0x180012ad8  mov     rax, [r9]
0x180012adb  cmp     rax, r9
0x180012ade  jz      short loc_180012B0C
0x180012ae0  mov     rdx, [rax+10h]
0x180012ae4  mov     rcx, [r14]
0x180012ae7  sub     rcx, [rdx]
0x180012aea  jnz     short loc_180012AF4
0x180012aec  mov     rcx, [r14+8]
0x180012af0  sub     rcx, [rdx+8]
0x180012af4  test    rcx, rcx
0x180012af7  jnz     short loc_180012B01
0x180012af9  mov     r8d, [rdx+10h]
0x180012afd  add     r8d, 0Eh
0x180012b01  mov     rax, [rax]
0x180012b04  cmp     r8d, 1Ch
0x180012b08  jz      short loc_180012ADB
0x180012b0a  jmp     short loc_180012B4F
0x180012b0c  cmp     qword ptr [rdi+0F0h], 0
0x180012b14  jz      short loc_180012B4F
0x180012b16  mov     r9, [rdi+0E8h]
0x180012b1d  mov     rax, [r9]
0x180012b20  cmp     rax, r9
0x180012b23  jz      short loc_180012B4F
0x180012b25  mov     rdx, [rax+10h]
0x180012b29  mov     rcx, [r14]
0x180012b2c  sub     rcx, [rdx]
0x180012b2f  jnz     short loc_180012B39
0x180012b31  mov     rcx, [r14+8]
0x180012b35  sub     rcx, [rdx+8]; this
0x180012b39  test    rcx, rcx
0x180012b3c  jnz     short loc_180012B46
0x180012b3e  mov     r8d, [rdx+10h]
0x180012b42  add     r8d, 0Eh; unsigned int
0x180012b46  mov     rax, [rax]
0x180012b49  cmp     r8d, 1Ch
0x180012b4d  jz      short loc_180012B20
0x180012b4f  mov     rdx, r10; struct DirectUI::Element *
0x180012b52  call    ?SetIconFromRes@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@I@Z; CSNOCplCore::SetIconFromRes(DirectUI::Element *,uint)
0x180012b57  mov     esi, eax
0x180012b59  mov     eax, esi
0x180012b5b  add     rsp, 28h
0x180012b5f  pop     r14
0x180012b61  pop     rdi
0x180012b62  pop     rsi
0x180012b63  pop     rbx
0x180012b64  retn
```
