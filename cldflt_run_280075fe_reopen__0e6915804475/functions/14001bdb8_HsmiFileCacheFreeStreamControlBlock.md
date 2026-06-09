# HsmiFileCacheFreeStreamControlBlock

- ea: `0x14001bdb8`
- end: `0x14001be81`
- name: `HsmiFileCacheFreeStreamControlBlock`
- size: `201`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001be90`

## callees

- `0x14000dee4`
- `0x1400105c4`
- `0x14001bdb8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001be04`
- `ntoskrnl!ObfDereferenceObject` at `0x14001be04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001be3b`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001be17`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001be27`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001be17`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001be27`

## pseudocode

```c
void __fastcall HsmiFileCacheFreeStreamControlBlock(char *P)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, P);
  }
  ObfDereferenceObject(*((PVOID *)P + 36));
  ExDeleteResourceLite((PERESOURCE)(P + 152));
  ExDeleteResourceLite((PERESOURCE)(P + 48));
  ExFreePoolWithTag(P, 0x63507348u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids);
  }
}

```

## disassembly

```asm
0x14001bdb8  mov     [rsp+arg_0], rbx
0x14001bdbd  push    rdi
0x14001bdbe  sub     rsp, 20h
0x14001bdc2  mov     rbx, rcx
0x14001bdc5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdcc  lea     rdi, WPP_GLOBAL_Control
0x14001bdd3  cmp     rcx, rdi
0x14001bdd6  jz      short loc_14001BDFD
0x14001bdd8  mov     eax, [rcx+2Ch]
0x14001bddb  test    al, 8
0x14001bddd  jz      short loc_14001BDFD
0x14001bddf  cmp     byte ptr [rcx+29h], 5
0x14001bde3  jb      short loc_14001BDFD
0x14001bde5  mov     rcx, [rcx+18h]
0x14001bde9  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001bdf0  mov     edx, 15h
0x14001bdf5  mov     r9, rbx
0x14001bdf8  call    WPP_SF_q
0x14001bdfd  mov     rcx, [rbx+120h]; Object
0x14001be04  call    cs:__imp_ObfDereferenceObject
0x14001be0b  nop     dword ptr [rax+rax+00h]
0x14001be10  lea     rcx, [rbx+98h]; Resource
0x14001be17  call    cs:__imp_ExDeleteResourceLite
0x14001be1e  nop     dword ptr [rax+rax+00h]
0x14001be23  lea     rcx, [rbx+30h]; Resource
0x14001be27  call    cs:__imp_ExDeleteResourceLite
0x14001be2e  nop     dword ptr [rax+rax+00h]
0x14001be33  mov     edx, 63507348h; Tag
0x14001be38  mov     rcx, rbx; P
0x14001be3b  call    cs:__imp_ExFreePoolWithTag
0x14001be42  nop     dword ptr [rax+rax+00h]
0x14001be47  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be4e  cmp     rcx, rdi
0x14001be51  jz      short loc_14001BE75
0x14001be53  mov     eax, [rcx+2Ch]
0x14001be56  test    al, 8
0x14001be58  jz      short loc_14001BE75
0x14001be5a  cmp     byte ptr [rcx+29h], 5
0x14001be5e  jb      short loc_14001BE75
0x14001be60  mov     rcx, [rcx+18h]
0x14001be64  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001be6b  mov     edx, 16h
0x14001be70  call    WPP_SF_
0x14001be75  mov     rbx, [rsp+28h+arg_0]
0x14001be7a  add     rsp, 20h
0x14001be7e  pop     rdi
0x14001be7f  retn
```
