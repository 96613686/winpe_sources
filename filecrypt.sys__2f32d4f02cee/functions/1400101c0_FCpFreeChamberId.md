# FCpFreeChamberId

- ea: `0x1400101c0`
- end: `0x14001023b`
- name: `FCpFreeChamberId`
- size: `123`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d010`
- `0x14000f2f0`
- `0x14000f9a0`
- `0x140011fe0`

## callees

- `0x14000f960`
- `0x1400101c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400101de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400101de`

## pseudocode

```c
void __fastcall FCpFreeChamberId(PVOID P)
{
  PVOID v1; // r9
  __int64 v2; // r9
  __int64 v3; // r9
  __int64 v4; // r9

  v1 = P;
  if ( (gFCFlags & 6) == 0
    || !(unsigned __int8)FCpEqualChamberIds(P, L"MusicChamber")
    && !(unsigned __int8)FCpEqualChamberIds(v2, L"PicturesChamber")
    && !(unsigned __int8)FCpEqualChamberIds(v3, L"VideosChamber")
    && !(unsigned __int8)FCpEqualChamberIds(v4, L"{0b7992da-c5e6-41e3-b24f-55419b997a15}") )
  {
    if ( v1 )
      ExFreePoolWithTag(v1, 0x70537453u);
  }
}

```

## disassembly

```asm
0x1400101c0  sub     rsp, 28h
0x1400101c4  mov     eax, cs:gFCFlags
0x1400101ca  mov     r9, rcx
0x1400101cd  test    al, 6
0x1400101cf  jnz     short loc_1400101F0
0x1400101d1  test    r9, r9
0x1400101d4  jz      short loc_1400101EA
0x1400101d6  mov     edx, 70537453h; Tag
0x1400101db  mov     rcx, r9; P
0x1400101de  call    cs:__imp_ExFreePoolWithTag
0x1400101e5  nop     dword ptr [rax+rax+00h]
0x1400101ea  add     rsp, 28h
0x1400101ee  retn
0x1400101f0  lea     rdx, aMusicchamber; "MusicChamber"
0x1400101f7  call    FCpEqualChamberIds
0x1400101fc  test    al, al
0x1400101fe  jnz     short loc_1400101EA
0x140010200  lea     rdx, aPictureschambe; "PicturesChamber"
0x140010207  mov     rcx, r9
0x14001020a  call    FCpEqualChamberIds
0x14001020f  test    al, al
0x140010211  jnz     short loc_1400101EA
0x140010213  lea     rdx, aVideoschamber; "VideosChamber"
0x14001021a  mov     rcx, r9
0x14001021d  call    FCpEqualChamberIds
0x140010222  test    al, al
0x140010224  jnz     short loc_1400101EA
0x140010226  lea     rdx, a0b7992daC5e641; "{0b7992da-c5e6-41e3-b24f-55419b997a15}"
0x14001022d  mov     rcx, r9
0x140010230  call    FCpEqualChamberIds
0x140010235  test    al, al
0x140010237  jnz     short loc_1400101EA
0x140010239  jmp     short loc_1400101D1
```
