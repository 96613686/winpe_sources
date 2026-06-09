# CscEnpFieldUpdateRelease

- ea: `0x14000fc60`
- end: `0x14000fcc0`
- name: `CscEnpFieldUpdateRelease`
- size: `96`
- prototype: `void __fastcall(__int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002a61c`
- `0x14002b1a8`
- `0x140048148`
- `0x14005f150`
- `0x14005f944`
- `0x1400691f8`
- `0x14006999c`
- `0x140072310`
- `0x140073330`
- `0x140073aa0`
- `0x14007a500`
- `0x14007dc34`
- `0x140082ccc`
- `0x140089a40`

## callees

- `0x14000fc60`
- `0x14001b568`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000fc89`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fc89`

## pseudocode

```c
void __fastcall CscEnpFieldUpdateRelease(__int64 a1)
{
  void *retaddr; // [rsp+38h] [rbp+0h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a1, retaddr);
  ExReleaseResourceLite(*(PERESOURCE *)(a1 + 120));
}

```

## disassembly

```asm
0x14000fc60  push    rbx
0x14000fc62  sub     rsp, 30h
0x14000fc66  mov     rbx, rcx
0x14000fc69  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc70  lea     rax, WPP_GLOBAL_Control
0x14000fc77  cmp     rcx, rax
0x14000fc7a  jz      short loc_14000FC85
0x14000fc7c  test    dword ptr [rcx+2Ch], 40000h
0x14000fc83  jnz     short loc_14000FC9C
0x14000fc85  mov     rcx, [rbx+78h]; Resource
0x14000fc89  call    cs:__imp_ExReleaseResourceLite
0x14000fc90  nop     dword ptr [rax+rax+00h]
0x14000fc95  add     rsp, 30h
0x14000fc99  pop     rbx
0x14000fc9a  retn
0x14000fc9c  mov     rax, [rsp+38h]
0x14000fca1  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000fca8  mov     rcx, [rcx+18h]
0x14000fcac  mov     edx, 0Ch
0x14000fcb1  mov     r9, rbx
0x14000fcb4  mov     [rsp+38h+var_18], rax
0x14000fcb9  call    WPP_SF_qq
0x14000fcbe  jmp     short loc_14000FC85
```
