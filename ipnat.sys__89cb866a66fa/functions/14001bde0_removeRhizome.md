# removeRhizome

- ea: `0x14001bde0`
- end: `0x14001be89`
- name: `removeRhizome`
- size: `169`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400179cc`
- `0x140019cec`
- `0x14001a9a0`
- `0x14001b314`

## callees

- `0x14000218c`
- `0x14001bb24`
- `0x14001bde0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001be3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be3e`

## pseudocode

```c
void __fastcall removeRhizome(__int64 a1, char *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids);
  }
  node_remove((_DWORD *)a1, a2, (char **)(a1 + 8));
  ExFreePoolWithTag(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids);
  }
}

```

## disassembly

```asm
0x14001bde0  mov     [rsp+arg_0], rbx
0x14001bde5  mov     [rsp+arg_8], rsi
0x14001bdea  push    rdi
0x14001bdeb  sub     rsp, 20h
0x14001bdef  mov     rbx, rdx
0x14001bdf2  mov     rdi, rcx
0x14001bdf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdfc  lea     rsi, WPP_GLOBAL_Control
0x14001be03  cmp     rcx, rsi
0x14001be06  jz      short loc_14001BE2A
0x14001be08  mov     eax, [rcx+2Ch]
0x14001be0b  test    al, 1
0x14001be0d  jz      short loc_14001BE2A
0x14001be0f  cmp     byte ptr [rcx+29h], 6
0x14001be13  jb      short loc_14001BE2A
0x14001be15  mov     rcx, [rcx+18h]
0x14001be19  lea     r8, WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids
0x14001be20  mov     edx, 19h
0x14001be25  call    WPP_SF_
0x14001be2a  lea     r8, [rdi+8]
0x14001be2e  mov     rdx, rbx
0x14001be31  mov     rcx, rdi
0x14001be34  call    node_remove
0x14001be39  xor     edx, edx; Tag
0x14001be3b  mov     rcx, rbx; P
0x14001be3e  call    cs:__imp_ExFreePoolWithTag
0x14001be45  nop     dword ptr [rax+rax+00h]
0x14001be4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be51  cmp     rcx, rsi
0x14001be54  jz      short loc_14001BE78
0x14001be56  mov     eax, [rcx+2Ch]
0x14001be59  test    al, 1
0x14001be5b  jz      short loc_14001BE78
0x14001be5d  cmp     byte ptr [rcx+29h], 6
0x14001be61  jb      short loc_14001BE78
0x14001be63  mov     rcx, [rcx+18h]
0x14001be67  lea     r8, WPP_98f60eb7cbd035eae084edec7fd78373_Traceguids
0x14001be6e  mov     edx, 1Ah
0x14001be73  call    WPP_SF_
0x14001be78  mov     rbx, [rsp+28h+arg_0]
0x14001be7d  mov     rsi, [rsp+28h+arg_8]
0x14001be82  add     rsp, 20h
0x14001be86  pop     rdi
0x14001be87  retn
```
