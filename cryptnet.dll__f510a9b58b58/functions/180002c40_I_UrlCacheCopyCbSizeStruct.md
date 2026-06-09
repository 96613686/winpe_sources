# I_UrlCacheCopyCbSizeStruct

- ea: `0x180002c40`
- end: `0x180002ca1`
- name: `I_UrlCacheCopyCbSizeStruct`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001460`
- `0x180002460`
- `0x180003ef0`
- `0x180006d40`

## callees

- `0x180002c40`
- `0x180026552`
- `0x18002656a`

## pseudocode

```c
void *__fastcall I_UrlCacheCopyCbSizeStruct(unsigned int *a1, unsigned int *a2)
{
  __int64 v2; // rbx
  unsigned int v4; // edi
  void *result; // rax

  v2 = *a1;
  v4 = *a2;
  if ( (unsigned int)v2 >= *a2 )
    v2 = v4;
  if ( (unsigned int)v2 > 4 )
  {
    result = memcpy_0(a2 + 1, a1 + 1, v2 - 4);
    if ( v4 > (unsigned int)v2 )
      return memset_0((char *)a2 + v2, 0, v4 - (unsigned int)v2);
  }
  return result;
}

```

## disassembly

```asm
0x180002c40  mov     [rsp+arg_8], rbx
0x180002c45  mov     [rsp+arg_10], rsi
0x180002c4a  push    rdi
0x180002c4b  sub     rsp, 20h
0x180002c4f  mov     ebx, [rcx]
0x180002c51  mov     rsi, rdx
0x180002c54  mov     edi, [rdx]
0x180002c56  cmp     ebx, edi
0x180002c58  cmovnb  ebx, edi
0x180002c5b  cmp     ebx, 4
0x180002c5e  jbe     short loc_180002C7F
0x180002c60  lea     rdx, [rcx+4]; Src
0x180002c64  mov     [rsp+28h+arg_0], r14
0x180002c69  lea     rcx, [rsi+4]; void *
0x180002c6d  lea     r8, [rbx-4]; Size
0x180002c71  call    memcpy_0
0x180002c76  cmp     edi, ebx
0x180002c78  ja      short loc_180002C8F
0x180002c7a  mov     r14, [rsp+28h+arg_0]
0x180002c7f  mov     rbx, [rsp+28h+arg_8]
0x180002c84  mov     rsi, [rsp+28h+arg_10]
0x180002c89  add     rsp, 20h
0x180002c8d  pop     rdi
0x180002c8e  retn
0x180002c8f  sub     edi, ebx
0x180002c91  lea     rcx, [rbx+rsi]; void *
0x180002c95  mov     r8d, edi; Size
0x180002c98  xor     edx, edx; Val
0x180002c9a  call    memset_0
0x180002c9f  jmp     short loc_180002C7A
```
