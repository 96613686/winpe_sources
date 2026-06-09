# CdCommonFsControl

- ea: `0x140013a70`
- end: `0x140013ac0`
- name: `CdCommonFsControl`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x140013a70`
- `0x1400142d8`
- `0x140014e4c`
- `0x140015090`

## pseudocode

```c
__int64 __fastcall CdCommonFsControl(void *a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v3; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 0u:
      return (unsigned int)CdUserFsctl((__int64)a1, a2);
    case 1u:
      return (unsigned int)CdMountVolume((__int64)a1, (__int64)a2);
    case 2u:
      return (unsigned int)CdVerifyVolume((int)a1);
  }
  v3 = -1073741808;
  CdCompleteRequest(a1, a2, -1073741808);
  return v3;
}

```

## disassembly

```asm
0x140013a70  push    rbx
0x140013a72  sub     rsp, 20h
0x140013a76  mov     rax, [rdx+0B8h]
0x140013a7d  movzx   r8d, byte ptr [rax+1]
0x140013a82  test    r8d, r8d
0x140013a85  jz      short loc_140013AB0
0x140013a87  sub     r8d, 1
0x140013a8b  jz      short loc_140013AA9
0x140013a8d  cmp     r8d, 1
0x140013a91  jz      short loc_140013AA2
0x140013a93  mov     ebx, 0C0000010h
0x140013a98  mov     r8d, ebx
0x140013a9b  call    CdCompleteRequest
0x140013aa0  jmp     short loc_140013AB7
0x140013aa2  call    CdVerifyVolume
0x140013aa7  jmp     short loc_140013AB5
0x140013aa9  call    CdMountVolume
0x140013aae  jmp     short loc_140013AB5
0x140013ab0  call    CdUserFsctl
0x140013ab5  mov     ebx, eax
0x140013ab7  mov     eax, ebx
0x140013ab9  add     rsp, 20h
0x140013abd  pop     rbx
0x140013abe  retn
```
