# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002c00`
- end: `0x180002c84`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002770`
- `0x180002e20`
- `0x180003d40`
- `0x180007e80`

## callees

- `0x180002c00`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002c3f`
- `msvcrt!_vsnwprintf` at `0x180002c3f`

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
0x180002c00  mov     [rsp+arg_10], r8
0x180002c05  mov     qword ptr [rsp+Args], r9
0x180002c0a  push    rbx
0x180002c0b  push    rdi
0x180002c0c  sub     rsp, 38h
0x180002c10  mov     rax, rdx
0x180002c13  mov     rdi, rcx
0x180002c16  test    rdx, rdx
0x180002c19  jz      short loc_180002C6C
0x180002c1b  cmp     rax, 7FFFFFFFh
0x180002c21  jbe     short loc_180002C2A
0x180002c23  mov     edx, 80070057h
0x180002c28  jmp     short loc_180002C76
0x180002c2a  lea     rbx, [rdx-1]
0x180002c2e  mov     [rsp+48h+var_28], 0
0x180002c37  mov     rdx, rbx; BufferCount
0x180002c3a  lea     r9, [rsp+48h+Args]; Args
0x180002c3f  call    cs:__imp__vsnwprintf
0x180002c45  test    eax, eax
0x180002c47  js      short loc_180002C5F
0x180002c49  cdqe
0x180002c4b  cmp     rax, rbx
0x180002c4e  ja      short loc_180002C5F
0x180002c50  xor     edx, edx
0x180002c52  cmp     rax, rbx
0x180002c55  jnz     short loc_180002C7B
0x180002c57  xor     eax, eax
0x180002c59  mov     [rdi+rbx*2], ax
0x180002c5d  jmp     short loc_180002C7B
0x180002c5f  xor     eax, eax
0x180002c61  mov     edx, 8007007Ah
0x180002c66  mov     [rdi+rbx*2], ax
0x180002c6a  jmp     short loc_180002C7B
0x180002c6c  mov     edx, 80070057h
0x180002c71  test    rax, rax
0x180002c74  jz      short loc_180002C7B
0x180002c76  xor     ecx, ecx
0x180002c78  mov     [rdi], cx
0x180002c7b  mov     eax, edx
0x180002c7d  add     rsp, 38h
0x180002c81  pop     rdi
0x180002c82  pop     rbx
0x180002c83  retn
```
