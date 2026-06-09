# FatMarkEaRangeDirty

- ea: `0x1400367d8`
- end: `0x140036853`
- name: `FatMarkEaRangeDirty`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140034678`
- `0x140035234`
- `0x1400356f0`
- `0x140035e50`
- `0x14003abc8`

## callees

- `0x1400367d8`

## import_xrefs

- `ntoskrnl!CcSetDirtyPinnedData` at `0x140036833`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x140036833`
- `ntoskrnl!CcCopyWrite` at `0x140036811`
- `ntoskrnl!CcCopyWrite` at `0x140036811`

## pseudocode

```c
void __fastcall FatMarkEaRangeDirty(union _LARGE_INTEGER a1, struct _FILE_OBJECT *a2, __int64 a3)
{
  PVOID *v4; // rdi
  int i; // ebx
  union _LARGE_INTEGER v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = a1;
  if ( *(_BYTE *)(a3 + 18) == 1 )
  {
    v6.QuadPart = *(unsigned int *)(a3 + 8);
    CcCopyWrite(a2, &v6, *(_DWORD *)(a3 + 12), 1u, *(PVOID *)a3);
  }
  v4 = *(PVOID **)(a3 + 24);
  for ( i = *(unsigned __int16 *)(a3 + 16); i; --i )
  {
    if ( *v4 )
      CcSetDirtyPinnedData(*v4, 0);
    ++v4;
  }
}

```

## disassembly

```asm
0x1400367d8  mov     r11, rsp
0x1400367db  mov     [r11+10h], rbx
0x1400367df  mov     [r11+8], rcx
0x1400367e3  push    rdi
0x1400367e4  sub     rsp, 30h
0x1400367e8  mov     r9b, 1; Wait
0x1400367eb  mov     rbx, r8
0x1400367ee  mov     r10, rdx
0x1400367f1  cmp     [r8+12h], r9b
0x1400367f5  jnz     short loc_14003681D
0x1400367f7  mov     eax, [r8+8]
0x1400367fb  lea     rdx, [r11+8]; FileOffset
0x1400367ff  mov     [r11+8], rax
0x140036803  mov     rcx, r10; FileObject
0x140036806  mov     rax, [r8]
0x140036809  mov     r8d, [r8+0Ch]; Length
0x14003680d  mov     [r11-18h], rax
0x140036811  call    cs:__imp_CcCopyWrite
0x140036818  nop     dword ptr [rax+rax+00h]
0x14003681d  mov     rdi, [rbx+18h]
0x140036821  movzx   ebx, word ptr [rbx+10h]
0x140036825  jmp     short loc_140036843
0x140036827  mov     rcx, [rdi]; BcbVoid
0x14003682a  dec     ebx
0x14003682c  test    rcx, rcx
0x14003682f  jz      short loc_14003683F
0x140036831  xor     edx, edx; Lsn
0x140036833  call    cs:__imp_CcSetDirtyPinnedData
0x14003683a  nop     dword ptr [rax+rax+00h]
0x14003683f  add     rdi, 8
0x140036843  test    ebx, ebx
0x140036845  jnz     short loc_140036827
0x140036847  mov     rbx, [rsp+38h+arg_8]
0x14003684c  add     rsp, 30h
0x140036850  pop     rdi
0x140036851  retn
```
