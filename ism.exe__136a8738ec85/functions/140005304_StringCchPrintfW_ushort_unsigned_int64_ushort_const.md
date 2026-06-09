# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140005304`
- end: `0x140005387`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002164`
- `0x140002e78`

## callees

- `0x140001e64`
- `0x140005304`

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
      v6 = vsnwprintf(a1, a2 - 1, a3, Args);
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
0x140005304  mov     [rsp+arg_10], r8
0x140005309  mov     qword ptr [rsp+Args], r9
0x14000530e  push    rbx
0x14000530f  push    rdi
0x140005310  sub     rsp, 38h
0x140005314  mov     rax, rdx
0x140005317  mov     rdi, rcx
0x14000531a  test    rdx, rdx
0x14000531d  jz      short loc_14000536F
0x14000531f  cmp     rax, 7FFFFFFFh
0x140005325  jbe     short loc_14000532E
0x140005327  mov     edx, 80070057h
0x14000532c  jmp     short loc_140005379
0x14000532e  lea     rbx, [rdx-1]
0x140005332  mov     [rsp+48h+var_28], 0
0x14000533b  mov     rdx, rbx; BufferCount
0x14000533e  lea     r9, [rsp+48h+Args]; Args
0x140005343  call    _vsnwprintf
0x140005348  test    eax, eax
0x14000534a  js      short loc_140005362
0x14000534c  cdqe
0x14000534e  cmp     rax, rbx
0x140005351  ja      short loc_140005362
0x140005353  xor     edx, edx
0x140005355  cmp     rax, rbx
0x140005358  jnz     short loc_14000537E
0x14000535a  xor     eax, eax
0x14000535c  mov     [rdi+rbx*2], ax
0x140005360  jmp     short loc_14000537E
0x140005362  xor     eax, eax
0x140005364  mov     edx, 8007007Ah
0x140005369  mov     [rdi+rbx*2], ax
0x14000536d  jmp     short loc_14000537E
0x14000536f  mov     edx, 80070057h
0x140005374  test    rax, rax
0x140005377  jz      short loc_14000537E
0x140005379  xor     ecx, ecx
0x14000537b  mov     [rdi], cx
0x14000537e  mov     eax, edx
0x140005380  add     rsp, 38h
0x140005384  pop     rdi
0x140005385  pop     rbx
0x140005386  retn
```
