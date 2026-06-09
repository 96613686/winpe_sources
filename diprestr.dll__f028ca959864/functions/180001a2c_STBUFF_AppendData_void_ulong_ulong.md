# STBUFF::AppendData(void *,ulong,ulong)

- ea: `0x180001a2c`
- end: `0x180001ab2`
- name: `?AppendData@STBUFF@@QEAAJPEAXKK@Z`
- size: `134`
- prototype: `__int64 __fastcall(STBUFF *this, _BYTE *, int, unsigned int)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180001af4`
- `0x180001cd4`
- `0x180001dc8`
- `0x180002428`
- `0x180002604`
- `0x180004f8c`
- `0x180005168`
- `0x1800057cc`
- `0x180005ab8`
- `0x180005d74`

## callees

- `0x180001a2c`
- `0x180001fa4`
- `0x180006782`

## pseudocode

```c
__int64 __fastcall STBUFF::AppendData(STBUFF *this, _BYTE *a2, int a3, unsigned int a4)
{
  unsigned int v4; // esi
  __int64 v5; // rbx
  __int64 v8; // r14
  int v9; // ebp
  __int64 v10; // rax

  v4 = a4;
  LODWORD(v5) = a3;
  if ( a3 == -1 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
  }
  if ( a4 == -1 )
    v4 = *((_DWORD *)this + 4);
  v8 = (unsigned int)v5 + v4;
  v9 = STBUFF::Resize(this, (unsigned int)v5 + v4);
  if ( v9 >= 0 )
  {
    if ( (_DWORD)v5 )
      memcpy_0((void *)(*((_QWORD *)this + 1) + v4), a2, (unsigned int)v5);
    v10 = *((_QWORD *)this + 1);
    *((_DWORD *)this + 4) = v8;
    *(_BYTE *)(v8 + v10) = 0;
    *(_BYTE *)((unsigned int)(*((_DWORD *)this + 4) + 1) + *((_QWORD *)this + 1)) = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180001a2c  push    rbx
0x180001a2e  push    rbp
0x180001a2f  push    rsi
0x180001a30  push    rdi
0x180001a31  push    r14
0x180001a33  push    r15
0x180001a35  sub     rsp, 28h
0x180001a39  or      eax, 0FFFFFFFFh
0x180001a3c  mov     esi, r9d
0x180001a3f  mov     ebx, r8d
0x180001a42  mov     r15, rdx
0x180001a45  mov     rdi, rcx
0x180001a48  cmp     r8d, eax
0x180001a4b  jnz     short loc_180001A5A
0x180001a4d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180001a51  inc     rbx
0x180001a54  cmp     byte ptr [rdx+rbx], 0
0x180001a58  jnz     short loc_180001A51
0x180001a5a  cmp     r9d, eax
0x180001a5d  jnz     short loc_180001A62
0x180001a5f  mov     esi, [rcx+10h]
0x180001a62  lea     r14d, [rbx+rsi]
0x180001a66  mov     edx, r14d; unsigned int
0x180001a69  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x180001a6e  mov     ebp, eax
0x180001a70  test    eax, eax
0x180001a72  js      short loc_180001AA3
0x180001a74  test    ebx, ebx
0x180001a76  jz      short loc_180001A89
0x180001a78  mov     ecx, esi
0x180001a7a  mov     rdx, r15; Src
0x180001a7d  add     rcx, [rdi+8]; void *
0x180001a81  mov     r8d, ebx; Size
0x180001a84  call    memcpy_0
0x180001a89  mov     rax, [rdi+8]
0x180001a8d  mov     [rdi+10h], r14d
0x180001a91  mov     byte ptr [r14+rax], 0
0x180001a96  mov     ecx, [rdi+10h]
0x180001a99  mov     rax, [rdi+8]
0x180001a9d  inc     ecx
0x180001a9f  mov     byte ptr [rcx+rax], 0
0x180001aa3  mov     eax, ebp
0x180001aa5  add     rsp, 28h
0x180001aa9  pop     r15
0x180001aab  pop     r14
0x180001aad  pop     rdi
0x180001aae  pop     rsi
0x180001aaf  pop     rbp
0x180001ab0  pop     rbx
0x180001ab1  retn
```
