# DfscNetUseTableDelete

- ea: `0x140017fb8`
- end: `0x140018061`
- name: `DfscNetUseTableDelete`
- size: `169`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2, ULONG_PTR BugCheckParameter3)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140018130`
- `0x14001f8a0`
- `0x14002545c`

## callees

- `0x140004718`
- `0x140017fb8`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001800c`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001800c`
- `ntoskrnl!KeBugCheckEx` at `0x140018035`
- `ntoskrnl!KeBugCheckEx` at `0x140018035`

## pseudocode

```c
BOOLEAN __fastcall DfscNetUseTableDelete(struct _RTL_AVL_TABLE *BugCheckParameter2, ULONG_PTR BugCheckParameter3)
{
  BOOLEAN result; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_Zq(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_4cbf8115eb6f3bebf2b1c99b588386c6_Traceguids,
      BugCheckParameter3 + 88,
      BugCheckParameter3);
  result = RtlDeleteElementGenericTableAvl(BugCheckParameter2, *(PVOID *)(BugCheckParameter3 + 128));
  if ( !result )
    KeBugCheckEx(0x10Bu, 1u, (ULONG_PTR)BugCheckParameter2, BugCheckParameter3, BugCheckParameter3 + 88);
  *(_QWORD *)(BugCheckParameter3 + 120) = 0;
  *(_QWORD *)(BugCheckParameter3 + 128) = 0;
  return result;
}

```

## disassembly

```asm
0x140017fb8  mov     [rsp+arg_0], rbx
0x140017fbd  push    rdi
0x140017fbe  sub     rsp, 30h
0x140017fc2  mov     rbx, rdx
0x140017fc5  mov     rdi, rcx
0x140017fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fcf  lea     rax, WPP_GLOBAL_Control
0x140017fd6  cmp     rcx, rax
0x140017fd9  jz      short loc_140018002
0x140017fdb  test    dword ptr [rcx+2Ch], 400000h
0x140017fe2  jz      short loc_140018002
0x140017fe4  mov     rcx, [rcx+18h]
0x140017fe8  lea     r9, [rdx+58h]
0x140017fec  mov     edx, 0Bh
0x140017ff1  mov     [rsp+38h+BugCheckParameter4], rbx
0x140017ff6  lea     r8, WPP_4cbf8115eb6f3bebf2b1c99b588386c6_Traceguids
0x140017ffd  call    WPP_SF_Zq
0x140018002  mov     rdx, [rbx+80h]; Buffer
0x140018009  mov     rcx, rdi; Table
0x14001800c  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140018013  nop     dword ptr [rax+rax+00h]
0x140018018  test    al, al
0x14001801a  jnz     short loc_140018042
0x14001801c  lea     rax, [rbx+58h]
0x140018020  mov     r9, rbx; BugCheckParameter3
0x140018023  mov     r8, rdi; BugCheckParameter2
0x140018026  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x14001802b  mov     edx, 1; BugCheckParameter1
0x140018030  mov     ecx, 10Bh; BugCheckCode
0x140018035  call    cs:__imp_KeBugCheckEx
0x140018042  mov     qword ptr [rbx+78h], 0
0x14001804a  mov     qword ptr [rbx+80h], 0
0x140018055  mov     rbx, [rsp+38h+arg_0]
0x14001805a  add     rsp, 30h
0x14001805e  pop     rdi
0x14001805f  retn
```
