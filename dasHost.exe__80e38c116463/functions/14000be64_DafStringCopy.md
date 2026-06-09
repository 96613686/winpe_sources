# DafStringCopy

- ea: `0x14000be64`
- end: `0x14000bee3`
- name: `DafStringCopy`
- size: `127`
- prototype: `__int64 __fastcall(unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000afa4`
- `0x14000b5d4`

## callees

- `0x140009060`
- `0x140009090`
- `0x14000a8ac`
- `0x14000be64`

## pseudocode

```c
__int64 __fastcall DafStringCopy(unsigned __int16 *a1, void **a2)
{
  __int64 v5; // rax
  SIZE_T v6; // rsi
  unsigned __int16 *v7; // rax
  unsigned int v8; // edi

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( !a1 )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  v6 = 2 * v5 + 2;
  v7 = (unsigned __int16 *)DAF_user_alloc(v6);
  *a2 = v7;
  if ( v7 )
  {
    v8 = StringCbCopyW(v7, v6, a1);
    if ( v8 )
    {
      MIDL_user_free(*a2);
      *a2 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x14000be64  push    rbx
0x14000be66  push    rbp
0x14000be67  push    rsi
0x14000be68  push    rdi
0x14000be69  sub     rsp, 28h
0x14000be6d  xor     ebp, ebp
0x14000be6f  mov     rbx, rdx
0x14000be72  mov     rdi, rcx
0x14000be75  test    rdx, rdx
0x14000be78  jnz     short loc_14000BE81
0x14000be7a  mov     eax, 80004003h
0x14000be7f  jmp     short loc_14000BEDA
0x14000be81  mov     [rdx], rbp
0x14000be84  test    rdi, rdi
0x14000be87  jnz     short loc_14000BE8D
0x14000be89  xor     eax, eax
0x14000be8b  jmp     short loc_14000BEDA
0x14000be8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000be91  inc     rax
0x14000be94  cmp     [rcx+rax*2], bp
0x14000be98  jnz     short loc_14000BE91
0x14000be9a  lea     rsi, ds:2[rax*2]
0x14000bea2  mov     rcx, rsi
0x14000bea5  call    DAF_user_alloc
0x14000beaa  mov     [rbx], rax
0x14000bead  test    rax, rax
0x14000beb0  jz      short loc_14000BED3
0x14000beb2  mov     r8, rdi; unsigned __int16 *
0x14000beb5  mov     rdx, rsi; unsigned __int64
0x14000beb8  mov     rcx, rax; unsigned __int16 *
0x14000bebb  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14000bec0  mov     edi, eax
0x14000bec2  test    eax, eax
0x14000bec4  jz      short loc_14000BED8
0x14000bec6  mov     rcx, [rbx]; void *
0x14000bec9  call    MIDL_user_free
0x14000bece  mov     [rbx], rbp
0x14000bed1  jmp     short loc_14000BED8
0x14000bed3  mov     edi, 8007000Eh
0x14000bed8  mov     eax, edi
0x14000beda  add     rsp, 28h
0x14000bede  pop     rdi
0x14000bedf  pop     rsi
0x14000bee0  pop     rbp
0x14000bee1  pop     rbx
0x14000bee2  retn
```
