# _CATDBConstructWSTRPath(ushort const *,ushort const *)

- ea: `0x180003d48`
- end: `0x180003dde`
- name: `?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z`
- size: `150`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `16`
- callee_count: `4`
- tags: ``

## callers

- `0x180002410`
- `0x180004824`
- `0x180004b98`
- `0x1800130a0`
- `0x18001344c`
- `0x180017a04`
- `0x180019314`
- `0x18001966c`
- `0x18001b6d8`
- `0x18001b8f4`
- `0x18001c03c`
- `0x18001cca0`
- `0x18001d4dc`
- `0x18001d62c`
- `0x18001da60`
- `0x18001db50`

## callees

- `0x180003538`
- `0x180003d48`
- `0x180004170`
- `0x1800041ec`

## pseudocode

```c
unsigned __int16 *__fastcall _CATDBConstructWSTRPath(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  __int64 v4; // rdi
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx

  v2 = -1;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  do
    ++v2;
  while ( a2[v2] );
  v6 = (unsigned int)(v4 + v2 + 2);
  v7 = (unsigned int)v6;
  v8 = (unsigned __int16 *)_CatDBAlloc(2 * v6);
  v9 = v8;
  if ( v8 )
  {
    StringCchCopyW(v8, v7, a1);
    if ( a1[(unsigned int)(v4 - 1)] != 92 )
    {
      v9[(unsigned int)v4] = 92;
      v9[(unsigned int)(v4 + 1)] = 0;
    }
    StringCchCatW(v9, v7, a2);
  }
  return v9;
}

```

## disassembly

```asm
0x180003d48  push    rbx
0x180003d4a  push    rbp
0x180003d4b  push    rsi
0x180003d4c  push    rdi
0x180003d4d  push    r14
0x180003d4f  push    r15
0x180003d51  sub     rsp, 28h
0x180003d55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d59  mov     r14, rdx
0x180003d5c  mov     rdi, rax
0x180003d5f  xor     r15d, r15d
0x180003d62  mov     rbp, rcx
0x180003d65  inc     rdi
0x180003d68  cmp     [rcx+rdi*2], r15w
0x180003d6d  jnz     short loc_180003D65
0x180003d6f  inc     rax
0x180003d72  cmp     [rdx+rax*2], r15w
0x180003d77  jnz     short loc_180003D6F
0x180003d79  add     eax, 2
0x180003d7c  add     eax, edi
0x180003d7e  mov     esi, eax
0x180003d80  lea     rcx, [rax+rax]; uBytes
0x180003d84  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x180003d89  mov     rbx, rax
0x180003d8c  test    rax, rax
0x180003d8f  jnz     short loc_180003DA1
0x180003d91  mov     rax, rbx
0x180003d94  add     rsp, 28h
0x180003d98  pop     r15
0x180003d9a  pop     r14
0x180003d9c  pop     rdi
0x180003d9d  pop     rsi
0x180003d9e  pop     rbp
0x180003d9f  pop     rbx
0x180003da0  retn
0x180003da1  mov     r8, rbp; unsigned __int16 *
0x180003da4  mov     rdx, rsi; unsigned __int64
0x180003da7  mov     rcx, rbx; unsigned __int16 *
0x180003daa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003daf  lea     r8d, [rdi-1]
0x180003db3  mov     ecx, 5Ch ; '\'
0x180003db8  cmp     [rbp+r8*2+0], cx
0x180003dbe  jz      short loc_180003DCE
0x180003dc0  mov     eax, edi
0x180003dc2  mov     [rbx+rax*2], cx
0x180003dc6  lea     eax, [rdi+1]
0x180003dc9  mov     [rbx+rax*2], r15w
0x180003dce  mov     r8, r14; unsigned __int16 *
0x180003dd1  mov     rdx, rsi; unsigned __int64
0x180003dd4  mov     rcx, rbx; unsigned __int16 *
0x180003dd7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003ddc  jmp     short loc_180003D91
```
