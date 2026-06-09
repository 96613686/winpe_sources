# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002130`
- end: `0x1800021b4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ca4`
- `0x1800024b0`

## callees

- `0x180002130`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000216f`
- `msvcrt!_vsnwprintf` at `0x18000216f`

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
0x180002130  mov     [rsp+arg_10], r8
0x180002135  mov     qword ptr [rsp+Args], r9
0x18000213a  push    rbx
0x18000213b  push    rdi
0x18000213c  sub     rsp, 38h
0x180002140  mov     rax, rdx
0x180002143  mov     rdi, rcx
0x180002146  test    rdx, rdx
0x180002149  jz      short loc_18000219C
0x18000214b  cmp     rax, 7FFFFFFFh
0x180002151  jbe     short loc_18000215A
0x180002153  mov     edx, 80070057h
0x180002158  jmp     short loc_1800021A6
0x18000215a  lea     rbx, [rdx-1]
0x18000215e  mov     [rsp+48h+var_28], 0
0x180002167  mov     rdx, rbx; BufferCount
0x18000216a  lea     r9, [rsp+48h+Args]; Args
0x18000216f  call    cs:__imp__vsnwprintf
0x180002175  test    eax, eax
0x180002177  js      short loc_18000218F
0x180002179  cdqe
0x18000217b  cmp     rax, rbx
0x18000217e  ja      short loc_18000218F
0x180002180  xor     edx, edx
0x180002182  cmp     rax, rbx
0x180002185  jnz     short loc_1800021AB
0x180002187  xor     eax, eax
0x180002189  mov     [rdi+rbx*2], ax
0x18000218d  jmp     short loc_1800021AB
0x18000218f  xor     eax, eax
0x180002191  mov     edx, 8007007Ah
0x180002196  mov     [rdi+rbx*2], ax
0x18000219a  jmp     short loc_1800021AB
0x18000219c  mov     edx, 80070057h
0x1800021a1  test    rax, rax
0x1800021a4  jz      short loc_1800021AB
0x1800021a6  xor     ecx, ecx
0x1800021a8  mov     [rdi], cx
0x1800021ab  mov     eax, edx
0x1800021ad  add     rsp, 38h
0x1800021b1  pop     rdi
0x1800021b2  pop     rbx
0x1800021b3  retn
```
