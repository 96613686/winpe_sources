# CDynamicArray::Remove(void const *)

- ea: `0x180005e30`
- end: `0x180005ed3`
- name: `?Remove@CDynamicArray@@UEAAHPEBX@Z`
- size: `163`
- prototype: `__int64 __fastcall(CDynamicArray *this, char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001956`
- `0x180001962`
- `0x180005e30`

## pseudocode

```c
__int64 __fastcall CDynamicArray::Remove(CDynamicArray *this, char *a2)
{
  unsigned __int64 v2; // r8
  unsigned int v3; // esi
  unsigned int v5; // r10d
  unsigned __int64 v6; // rcx
  _BYTE *v7; // rbx

  v2 = *((_QWORD *)this + 3);
  v3 = 0;
  if ( v2 )
  {
    if ( a2 )
    {
      if ( (unsigned __int64)a2 >= v2 )
      {
        v5 = *((_DWORD *)this + 4);
        v6 = *((_QWORD *)this + 1);
        if ( (unsigned __int64)a2 <= v2 + v6 * *((unsigned int *)this + 4) && !((unsigned __int64)&a2[-v2] % v6) )
        {
          v3 = 1;
          if ( v5 <= 1 )
            v7 = (_BYTE *)v2;
          else
            v7 = (_BYTE *)(v2 + v6 * (v5 - 1));
          if ( v7 > a2 )
            memmove_0(a2, &a2[v6], v7 - a2);
          memset_0(v7, 0, *((_QWORD *)this + 1));
          --*((_DWORD *)this + 4);
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180005e30  mov     [rsp+arg_0], rbx
0x180005e35  mov     [rsp+arg_8], rsi
0x180005e3a  push    rdi
0x180005e3b  sub     rsp, 20h
0x180005e3f  mov     r8, [rcx+18h]
0x180005e43  xor     esi, esi
0x180005e45  mov     r9, rdx
0x180005e48  mov     rdi, rcx
0x180005e4b  test    r8, r8
0x180005e4e  jz      short loc_180005EC1
0x180005e50  test    rdx, rdx
0x180005e53  jz      short loc_180005EC1
0x180005e55  cmp     rdx, r8
0x180005e58  jb      short loc_180005EC1
0x180005e5a  mov     r10d, [rdi+10h]
0x180005e5e  mov     rcx, [rcx+8]
0x180005e62  mov     eax, r10d
0x180005e65  imul    rax, rcx
0x180005e69  add     rax, r8
0x180005e6c  cmp     rdx, rax
0x180005e6f  ja      short loc_180005EC1
0x180005e71  mov     rax, rdx
0x180005e74  xor     edx, edx
0x180005e76  sub     rax, r8
0x180005e79  div     rcx
0x180005e7c  test    rdx, rdx
0x180005e7f  jnz     short loc_180005EC1
0x180005e81  lea     esi, [rdx+1]
0x180005e84  cmp     r10d, esi
0x180005e87  jbe     short loc_180005E96
0x180005e89  lea     ebx, [r10-1]
0x180005e8d  imul    rbx, rcx
0x180005e91  add     rbx, r8
0x180005e94  jmp     short loc_180005E99
0x180005e96  mov     rbx, r8
0x180005e99  cmp     rbx, r9
0x180005e9c  jbe     short loc_180005EB0
0x180005e9e  lea     rdx, [rcx+r9]; Src
0x180005ea2  mov     r8, rbx
0x180005ea5  sub     r8, r9; Size
0x180005ea8  mov     rcx, r9; void *
0x180005eab  call    memmove_0
0x180005eb0  mov     r8, [rdi+8]; Size
0x180005eb4  xor     edx, edx; Val
0x180005eb6  mov     rcx, rbx; void *
0x180005eb9  call    memset_0
0x180005ebe  dec     dword ptr [rdi+10h]
0x180005ec1  mov     rbx, [rsp+28h+arg_0]
0x180005ec6  mov     eax, esi
0x180005ec8  mov     rsi, [rsp+28h+arg_8]
0x180005ecd  add     rsp, 20h
0x180005ed1  pop     rdi
0x180005ed2  retn
```
