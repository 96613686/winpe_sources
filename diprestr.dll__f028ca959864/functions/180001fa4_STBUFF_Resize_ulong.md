# STBUFF::Resize(ulong)

- ea: `0x180001fa4`
- end: `0x180002035`
- name: `?Resize@STBUFF@@QEAAJK@Z`
- size: `145`
- prototype: `__int64 __fastcall(const void **this, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180001a2c`
- `0x180001af4`
- `0x180001dc8`
- `0x180002604`
- `0x180002efc`
- `0x180003244`
- `0x180004f8c`

## callees

- `0x180001fa4`
- `0x180006782`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001fdc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001fdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000200c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000200c`

## pseudocode

```c
__int64 __fastcall STBUFF::Resize(const void **this, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 v4; // rsi
  HLOCAL v5; // rax
  HLOCAL v6; // rbp
  char *v7; // rcx

  v2 = 0;
  if ( a2 >= *((_DWORD *)this + 5) )
  {
    v4 = *((unsigned int *)this + 6);
    if ( a2 > (unsigned int)v4 )
      return (unsigned int)-2147024882;
    if ( (a2 & 0x3F) != 0 )
      a2 = (a2 & 0xFFFFFFC0) + 64;
    if ( a2 <= (unsigned int)v4 )
      v4 = a2;
    v5 = LocalAlloc(0x40u, (unsigned int)(v4 + 2));
    v6 = v5;
    if ( v5 )
    {
      if ( *((_DWORD *)this + 4) )
        memcpy_0(v5, this[1], *((unsigned int *)this + 4));
      v7 = (char *)this[1];
      if ( v7 != (char *)this + 28 )
        LocalFree(v7);
      this[1] = v6;
      *((_DWORD *)this + 5) = v4;
      *((_BYTE *)v6 + v4) = 0;
      *((_BYTE *)this[1] + (unsigned int)(*((_DWORD *)this + 5) + 1)) = 0;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180001fa4  push    rbx
0x180001fa6  push    rbp
0x180001fa7  push    rsi
0x180001fa8  push    rdi
0x180001fa9  sub     rsp, 28h
0x180001fad  xor     edi, edi
0x180001faf  mov     rbx, rcx
0x180001fb2  cmp     edx, [rcx+14h]
0x180001fb5  jb      short loc_18000202A
0x180001fb7  mov     esi, [rcx+18h]
0x180001fba  cmp     edx, esi
0x180001fbc  jbe     short loc_180001FC5
0x180001fbe  mov     edi, 8007000Eh
0x180001fc3  jmp     short loc_18000202A
0x180001fc5  mov     ecx, 40h ; '@'; uFlags
0x180001fca  test    dl, 3Fh
0x180001fcd  jz      short loc_180001FD4
0x180001fcf  and     edx, 0FFFFFFC0h
0x180001fd2  add     edx, ecx
0x180001fd4  cmp     edx, esi
0x180001fd6  cmovbe  esi, edx
0x180001fd9  lea     edx, [rsi+2]; uBytes
0x180001fdc  call    cs:__imp_LocalAlloc
0x180001fe2  mov     rbp, rax
0x180001fe5  test    rax, rax
0x180001fe8  jz      short loc_180001FBE
0x180001fea  cmp     [rbx+10h], edi
0x180001fed  jz      short loc_180001FFF
0x180001fef  mov     r8d, [rbx+10h]; Size
0x180001ff3  mov     rcx, rax; void *
0x180001ff6  mov     rdx, [rbx+8]; Src
0x180001ffa  call    memcpy_0
0x180001fff  mov     rcx, [rbx+8]; hMem
0x180002003  lea     rax, [rbx+1Ch]
0x180002007  cmp     rcx, rax
0x18000200a  jz      short loc_180002012
0x18000200c  call    cs:__imp_LocalFree
0x180002012  mov     [rbx+8], rbp
0x180002016  mov     [rbx+14h], esi
0x180002019  mov     [rsi+rbp], dil
0x18000201d  mov     edx, [rbx+14h]
0x180002020  mov     rcx, [rbx+8]
0x180002024  inc     edx
0x180002026  mov     [rdx+rcx], dil
0x18000202a  mov     eax, edi
0x18000202c  add     rsp, 28h
0x180002030  pop     rdi
0x180002031  pop     rsi
0x180002032  pop     rbp
0x180002033  pop     rbx
0x180002034  retn
```
