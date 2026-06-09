# _CreateCngPublicKeyBlob

- ea: `0x180002d7c`
- end: `0x180002df8`
- name: `_CreateCngPublicKeyBlob`
- size: `124`
- prototype: `__int64 __fastcall(void *Src, size_t Size, __int64 *, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800029f4`
- `0x180002c44`

## callees

- `0x180002d7c`
- `0x180003320`
- `0x1800069c0`

## pseudocode

```c
__int64 __fastcall CreateCngPublicKeyBlob(void *Src, size_t Size, __int64 *a3, _DWORD *a4)
{
  unsigned int v5; // ebp
  __int64 v8; // rbx
  __int64 result; // rax

  v5 = Size;
  v8 = DevAuthAlloc(0x11Bu);
  result = 0;
  if ( v8 )
  {
    *(_DWORD *)v8 = 826364754;
    *(_DWORD *)(v8 + 4) = 2048;
    *(_DWORD *)(v8 + 8) = 3;
    *(_QWORD *)(v8 + 12) = 256;
    *(_DWORD *)(v8 + 20) = 0;
    *(_WORD *)(v8 + 24) = 1;
    *(_BYTE *)(v8 + 26) = 1;
    memmove((void *)(v8 + 27), Src, v5);
    result = 1;
    *a3 = v8;
    *a4 = 283;
  }
  return result;
}

```

## disassembly

```asm
0x180002d7c  push    rbx
0x180002d7e  push    rbp
0x180002d7f  push    rsi
0x180002d80  push    rdi
0x180002d81  push    r14
0x180002d83  sub     rsp, 20h
0x180002d87  mov     r14, rcx
0x180002d8a  mov     ebp, edx
0x180002d8c  mov     ecx, 11Bh; Size
0x180002d91  mov     rdi, r9
0x180002d94  mov     rsi, r8
0x180002d97  call    DevAuthAlloc
0x180002d9c  mov     rbx, rax
0x180002d9f  xor     eax, eax
0x180002da1  test    rbx, rbx
0x180002da4  jz      short loc_180002DEC
0x180002da6  mov     r8d, ebp; Size
0x180002da9  mov     dword ptr [rbx], 31415352h
0x180002daf  lea     rcx, [rbx+1Bh]; void *
0x180002db3  mov     dword ptr [rbx+4], 800h
0x180002dba  mov     rdx, r14; Src
0x180002dbd  mov     dword ptr [rbx+8], 3
0x180002dc4  mov     qword ptr [rbx+0Ch], 100h
0x180002dcc  mov     [rbx+14h], eax
0x180002dcf  mov     word ptr [rbx+18h], 1
0x180002dd5  mov     byte ptr [rbx+1Ah], 1
0x180002dd9  call    memmove
0x180002dde  mov     eax, 1
0x180002de3  mov     [rsi], rbx
0x180002de6  mov     dword ptr [rdi], 11Bh
0x180002dec  add     rsp, 20h
0x180002df0  pop     r14
0x180002df2  pop     rdi
0x180002df3  pop     rsi
0x180002df4  pop     rbp
0x180002df5  pop     rbx
0x180002df6  retn
```
