# HsmiFileCacheFreeStreamControlBlock

- ea: `0x14001be38`
- end: `0x14001bf01`
- name: `HsmiFileCacheFreeStreamControlBlock`
- size: `201`
- prototype: `void __fastcall(char *P)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bf10`

## callees

- `0x14000dee4`
- `0x140010644`
- `0x14001be38`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001be84`
- `ntoskrnl!ObfDereferenceObject` at `0x14001be84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bebb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bebb`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001be97`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001bea7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001be97`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001bea7`

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
0x14001be38  mov     [rsp+arg_0], rbx
0x14001be3d  push    rdi
0x14001be3e  sub     rsp, 20h
0x14001be42  mov     rbx, rcx
0x14001be45  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be4c  lea     rdi, WPP_GLOBAL_Control
0x14001be53  cmp     rcx, rdi
0x14001be56  jz      short loc_14001BE7D
0x14001be58  mov     eax, [rcx+2Ch]
0x14001be5b  test    al, 8
0x14001be5d  jz      short loc_14001BE7D
0x14001be5f  cmp     byte ptr [rcx+29h], 5
0x14001be63  jb      short loc_14001BE7D
0x14001be65  mov     rcx, [rcx+18h]
0x14001be69  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001be70  mov     edx, 15h
0x14001be75  mov     r9, rbx
0x14001be78  call    WPP_SF_q
0x14001be7d  mov     rcx, [rbx+120h]; Object
0x14001be84  call    cs:__imp_ObfDereferenceObject
0x14001be8b  nop     dword ptr [rax+rax+00h]
0x14001be90  lea     rcx, [rbx+98h]; Resource
0x14001be97  call    cs:__imp_ExDeleteResourceLite
0x14001be9e  nop     dword ptr [rax+rax+00h]
0x14001bea3  lea     rcx, [rbx+30h]; Resource
0x14001bea7  call    cs:__imp_ExDeleteResourceLite
0x14001beae  nop     dword ptr [rax+rax+00h]
0x14001beb3  mov     edx, 63507348h; Tag
0x14001beb8  mov     rcx, rbx; P
0x14001bebb  call    cs:__imp_ExFreePoolWithTag
0x14001bec2  nop     dword ptr [rax+rax+00h]
0x14001bec7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bece  cmp     rcx, rdi
0x14001bed1  jz      short loc_14001BEF5
0x14001bed3  mov     eax, [rcx+2Ch]
0x14001bed6  test    al, 8
0x14001bed8  jz      short loc_14001BEF5
0x14001beda  cmp     byte ptr [rcx+29h], 5
0x14001bede  jb      short loc_14001BEF5
0x14001bee0  mov     rcx, [rcx+18h]
0x14001bee4  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001beeb  mov     edx, 16h
0x14001bef0  call    WPP_SF_
0x14001bef5  mov     rbx, [rsp+28h+arg_0]
0x14001befa  add     rsp, 20h
0x14001befe  pop     rdi
0x14001beff  retn
```
