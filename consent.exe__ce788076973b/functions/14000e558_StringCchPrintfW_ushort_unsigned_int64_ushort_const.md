# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000e558`
- end: `0x14000e5dc`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400029e0`
- `0x140004ab0`
- `0x14000e354`
- `0x14001287c`
- `0x140018d60`

## callees

- `0x14000e558`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14000e597`
- `msvcrt!_vsnwprintf` at `0x14000e597`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x14000e558  mov     [rsp+arg_10], r8
0x14000e55d  mov     qword ptr [rsp+Args], r9
0x14000e562  push    rbx
0x14000e563  push    rdi
0x14000e564  sub     rsp, 38h
0x14000e568  mov     rax, rdx
0x14000e56b  mov     rdi, rcx
0x14000e56e  test    rdx, rdx
0x14000e571  jz      short loc_14000E5C4
0x14000e573  cmp     rax, 7FFFFFFFh
0x14000e579  jbe     short loc_14000E582
0x14000e57b  mov     edx, 80070057h
0x14000e580  jmp     short loc_14000E5CE
0x14000e582  lea     rbx, [rdx-1]
0x14000e586  mov     [rsp+48h+var_28], 0
0x14000e58f  mov     rdx, rbx; BufferCount
0x14000e592  lea     r9, [rsp+48h+Args]; Args
0x14000e597  call    cs:__imp__vsnwprintf
0x14000e59d  test    eax, eax
0x14000e59f  js      short loc_14000E5B7
0x14000e5a1  cdqe
0x14000e5a3  cmp     rax, rbx
0x14000e5a6  ja      short loc_14000E5B7
0x14000e5a8  xor     edx, edx
0x14000e5aa  cmp     rax, rbx
0x14000e5ad  jnz     short loc_14000E5D3
0x14000e5af  xor     eax, eax
0x14000e5b1  mov     [rdi+rbx*2], ax
0x14000e5b5  jmp     short loc_14000E5D3
0x14000e5b7  xor     eax, eax
0x14000e5b9  mov     edx, 8007007Ah
0x14000e5be  mov     [rdi+rbx*2], ax
0x14000e5c2  jmp     short loc_14000E5D3
0x14000e5c4  mov     edx, 80070057h
0x14000e5c9  test    rax, rax
0x14000e5cc  jz      short loc_14000E5D3
0x14000e5ce  xor     ecx, ecx
0x14000e5d0  mov     [rdi], cx
0x14000e5d3  mov     eax, edx
0x14000e5d5  add     rsp, 38h
0x14000e5d9  pop     rdi
0x14000e5da  pop     rbx
0x14000e5db  retn
```
