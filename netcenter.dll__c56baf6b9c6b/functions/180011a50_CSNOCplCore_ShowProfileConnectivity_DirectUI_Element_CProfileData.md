# CSNOCplCore::ShowProfileConnectivity(DirectUI::Element *,CProfileData *)

- ea: `0x180011a50`
- end: `0x180011ac4`
- name: `?ShowProfileConnectivity@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEAVCProfileData@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct DirectUI::Element *, struct CProfileData *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c7e8`
- `0x180012ec4`

## callees

- `0x180011188`
- `0x180011a50`

## import_xrefs

- `DUI70!StrToID` at `0x180011a71`
- `DUI70!StrToID` at `0x180011a71`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011a7d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011a7d`

## string_xrefs

- `0x180011a5f`: `accessTypeValue`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::ShowProfileConnectivity(
        CSNOCplCore *this,
        struct DirectUI::Element *a2,
        struct CProfileData *a3)
{
  unsigned int v5; // edi
  unsigned __int16 v6; // ax
  struct DirectUI::Element *Descendent; // rdx
  CSNOCplCore *v8; // rcx
  int v9; // eax
  unsigned int v10; // r8d

  v5 = -2147418113;
  v6 = StrToID(L"accessTypeValue");
  Descendent = DirectUI::Element::FindDescendent(a2, v6);
  if ( Descendent )
  {
    v9 = *((_DWORD *)a3 + 12);
    if ( (v9 & 0x28) != 0 )
      v10 = 93;
    else
      v10 = 95 - ((v9 & 0x14) != 0);
    return (unsigned int)CSNOCplCore::SetContentAndAccNameFromRes(v8, Descendent, v10, 0xC0u);
  }
  return v5;
}

```

## disassembly

```asm
0x180011a50  mov     [rsp+arg_0], rbx
0x180011a55  mov     [rsp+arg_8], rsi
0x180011a5a  push    rdi
0x180011a5b  sub     rsp, 20h
0x180011a5f  lea     rcx, aAccesstypevalu; "accessTypeValue"
0x180011a66  mov     rsi, r8
0x180011a69  mov     rbx, rdx
0x180011a6c  mov     edi, 8000FFFFh
0x180011a71  call    cs:__imp_StrToID
0x180011a77  movzx   edx, ax
0x180011a7a  mov     rcx, rbx
0x180011a7d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180011a83  mov     rdx, rax; struct DirectUI::Element *
0x180011a86  test    rax, rax
0x180011a89  jz      short loc_180011AB2
0x180011a8b  mov     eax, [rsi+30h]
0x180011a8e  test    al, 28h
0x180011a90  jz      short loc_180011A9A
0x180011a92  mov     r8d, 5Dh ; ']'
0x180011a98  jmp     short loc_180011AA5
0x180011a9a  and     al, 14h
0x180011a9c  neg     al
0x180011a9e  sbb     r8d, r8d
0x180011aa1  add     r8d, 5Fh ; '_'; unsigned int
0x180011aa5  mov     r9d, 0C0h; unsigned int
0x180011aab  call    ?SetContentAndAccNameFromRes@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@II@Z; CSNOCplCore::SetContentAndAccNameFromRes(DirectUI::Element *,uint,uint)
0x180011ab0  mov     edi, eax
0x180011ab2  mov     rbx, [rsp+28h+arg_0]
0x180011ab7  mov     eax, edi
0x180011ab9  mov     rsi, [rsp+28h+arg_8]
0x180011abe  add     rsp, 20h
0x180011ac2  pop     rdi
0x180011ac3  retn
```
