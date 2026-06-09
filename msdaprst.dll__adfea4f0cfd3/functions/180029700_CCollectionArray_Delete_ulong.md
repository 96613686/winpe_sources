# CCollectionArray::Delete(ulong)

- ea: `0x180029700`
- end: `0x18002973f`
- name: `?Delete@CCollectionArray@@QEAAJK@Z`
- size: `63`
- prototype: `__int64 __fastcall(CCollectionArray *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002748c`
- `0x180029748`
- `0x1800297d4`
- `0x180029aa4`

## callees

- `0x180029700`
- `0x18002f09e`

## pseudocode

```c
__int64 __fastcall CCollectionArray::Delete(CCollectionArray *this, unsigned int a2)
{
  int v2; // r9d
  __int64 v4; // rcx

  v2 = *((_DWORD *)this + 4);
  if ( a2 != v2 - 1 )
  {
    v4 = *((_QWORD *)this + 1) + 8LL * a2;
    memmove_0((void *)v4, (const void *)(v4 + 8), 8LL * (v2 + ~a2));
  }
  --*((_DWORD *)this + 4);
  return 0;
}

```

## disassembly

```asm
0x180029700  push    rbx
0x180029702  sub     rsp, 20h
0x180029706  mov     r9d, [rcx+10h]
0x18002970a  mov     rbx, rcx
0x18002970d  lea     eax, [r9-1]
0x180029711  cmp     edx, eax
0x180029713  jz      short loc_180029733
0x180029715  mov     rax, [rcx+8]
0x180029719  mov     r8d, edx
0x18002971c  not     edx
0x18002971e  lea     rcx, [rax+r8*8]; void *
0x180029722  lea     r8d, [r9+rdx]
0x180029726  shl     r8, 3; Size
0x18002972a  lea     rdx, [rcx+8]; Src
0x18002972e  call    memmove_0
0x180029733  dec     dword ptr [rbx+10h]
0x180029736  xor     eax, eax
0x180029738  add     rsp, 20h
0x18002973c  pop     rbx
0x18002973d  retn
```
