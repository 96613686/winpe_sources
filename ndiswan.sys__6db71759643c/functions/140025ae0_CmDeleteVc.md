# CmDeleteVc

- ea: `0x140025ae0`
- end: `0x140025b78`
- name: `CmDeleteVc`
- size: `152`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14000a290`
- `0x140025ae0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025b2e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025b2e`

## pseudocode

```c
__int64 __fastcall CmDeleteVc(PVOID Entry)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
  }
  ExFreeToNPagedLookasideList(&AfSapVcCBList, Entry);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140025ae0  mov     [rsp+arg_0], rbx
0x140025ae5  push    rsi
0x140025ae6  sub     rsp, 20h
0x140025aea  mov     rbx, rcx
0x140025aed  mov     rcx, cs:WPP_GLOBAL_Control
0x140025af4  lea     rsi, WPP_GLOBAL_Control
0x140025afb  cmp     rcx, rsi
0x140025afe  jz      short loc_140025B24
0x140025b00  test    dword ptr [rcx+2Ch], 10000h
0x140025b07  jz      short loc_140025B24
0x140025b09  cmp     byte ptr [rcx+29h], 5
0x140025b0d  jb      short loc_140025B24
0x140025b0f  mov     rcx, [rcx+18h]
0x140025b13  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025b1a  mov     edx, 0Ch
0x140025b1f  call    WPP_SF_
0x140025b24  mov     rdx, rbx; Entry
0x140025b27  lea     rcx, AfSapVcCBList; Lookaside
0x140025b2e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025b35  nop     dword ptr [rax+rax+00h]
0x140025b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025b41  cmp     rcx, rsi
0x140025b44  jz      short loc_140025B6A
0x140025b46  test    dword ptr [rcx+2Ch], 10000h
0x140025b4d  jz      short loc_140025B6A
0x140025b4f  cmp     byte ptr [rcx+29h], 5
0x140025b53  jb      short loc_140025B6A
0x140025b55  mov     rcx, [rcx+18h]
0x140025b59  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025b60  mov     edx, 0Dh
0x140025b65  call    WPP_SF_
0x140025b6a  mov     rbx, [rsp+28h+arg_0]
0x140025b6f  xor     eax, eax
0x140025b71  add     rsp, 20h
0x140025b75  pop     rsi
0x140025b76  retn
```
