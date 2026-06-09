# CDynamicArray::Remove(ulong)

- ea: `0x180005da0`
- end: `0x180005e28`
- name: `?Remove@CDynamicArray@@UEAAHK@Z`
- size: `136`
- prototype: `__int64 __fastcall(CDynamicArray *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005ee0`

## callees

- `0x180001956`
- `0x180001962`
- `0x180005da0`

## pseudocode

```c
__int64 __fastcall CDynamicArray::Remove(CDynamicArray *this, unsigned int a2)
{
  unsigned int v3; // esi
  _BYTE *v4; // rcx
  unsigned int v5; // r8d
  __int64 v6; // r10
  char *v7; // r9
  _BYTE *v8; // rbx

  v3 = 0;
  v4 = (_BYTE *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    v5 = *((_DWORD *)this + 4);
    if ( a2 < v5 )
    {
      v6 = *((_QWORD *)this + 1);
      v3 = 1;
      v7 = &v4[v6 * a2];
      if ( v5 <= 1 )
        v8 = v4;
      else
        v8 = &v4[v6 * (v5 - 1)];
      if ( v8 > v7 )
        memmove_0(v7, &v7[v6], v8 - v7);
      memset_0(v8, 0, *((_QWORD *)this + 1));
      --*((_DWORD *)this + 4);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180005da0  mov     [rsp+arg_0], rbx
0x180005da5  mov     [rsp+arg_8], rsi
0x180005daa  push    rdi
0x180005dab  sub     rsp, 20h
0x180005daf  mov     rdi, rcx
0x180005db2  xor     esi, esi
0x180005db4  mov     rcx, [rcx+18h]
0x180005db8  test    rcx, rcx
0x180005dbb  jz      short loc_180005E16
0x180005dbd  mov     r8d, [rdi+10h]
0x180005dc1  cmp     edx, r8d
0x180005dc4  jnb     short loc_180005E16
0x180005dc6  mov     r10, [rdi+8]
0x180005dca  mov     esi, 1
0x180005dcf  mov     r9d, edx
0x180005dd2  imul    r9, r10
0x180005dd6  add     r9, rcx
0x180005dd9  cmp     r8d, esi
0x180005ddc  jbe     short loc_180005DEB
0x180005dde  lea     ebx, [r8-1]
0x180005de2  imul    rbx, r10
0x180005de6  add     rbx, rcx
0x180005de9  jmp     short loc_180005DEE
0x180005deb  mov     rbx, rcx
0x180005dee  cmp     rbx, r9
0x180005df1  jbe     short loc_180005E05
0x180005df3  mov     r8, rbx
0x180005df6  lea     rdx, [r9+r10]; Src
0x180005dfa  sub     r8, r9; Size
0x180005dfd  mov     rcx, r9; void *
0x180005e00  call    memmove_0
0x180005e05  mov     r8, [rdi+8]; Size
0x180005e09  xor     edx, edx; Val
0x180005e0b  mov     rcx, rbx; void *
0x180005e0e  call    memset_0
0x180005e13  dec     dword ptr [rdi+10h]
0x180005e16  mov     rbx, [rsp+28h+arg_0]
0x180005e1b  mov     eax, esi
0x180005e1d  mov     rsi, [rsp+28h+arg_8]
0x180005e22  add     rsp, 20h
0x180005e26  pop     rdi
0x180005e27  retn
```
