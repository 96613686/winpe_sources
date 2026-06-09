# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800073e0`
- end: `0x180007463`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044f8`
- `0x18000a558`
- `0x18000d4ff`
- `0x18000d5f7`
- `0x18000d72b`
- `0x18000d796`

## callees

- `0x18000207c`
- `0x1800073e0`

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
0x1800073e0  mov     [rsp+arg_10], r8
0x1800073e5  mov     qword ptr [rsp+Args], r9
0x1800073ea  push    rbx
0x1800073eb  push    rdi
0x1800073ec  sub     rsp, 38h
0x1800073f0  mov     rax, rdx
0x1800073f3  mov     rdi, rcx
0x1800073f6  test    rdx, rdx
0x1800073f9  jz      short loc_18000744B
0x1800073fb  cmp     rax, 7FFFFFFFh
0x180007401  jbe     short loc_18000740A
0x180007403  mov     edx, 80070057h
0x180007408  jmp     short loc_180007455
0x18000740a  lea     rbx, [rdx-1]
0x18000740e  mov     [rsp+48h+var_28], 0
0x180007417  mov     rdx, rbx; BufferCount
0x18000741a  lea     r9, [rsp+48h+Args]; Args
0x18000741f  call    _vsnwprintf
0x180007424  test    eax, eax
0x180007426  js      short loc_18000743E
0x180007428  cdqe
0x18000742a  cmp     rax, rbx
0x18000742d  ja      short loc_18000743E
0x18000742f  xor     edx, edx
0x180007431  cmp     rax, rbx
0x180007434  jnz     short loc_18000745A
0x180007436  xor     eax, eax
0x180007438  mov     [rdi+rbx*2], ax
0x18000743c  jmp     short loc_18000745A
0x18000743e  xor     eax, eax
0x180007440  mov     edx, 8007007Ah
0x180007445  mov     [rdi+rbx*2], ax
0x180007449  jmp     short loc_18000745A
0x18000744b  mov     edx, 80070057h
0x180007450  test    rax, rax
0x180007453  jz      short loc_18000745A
0x180007455  xor     ecx, ecx
0x180007457  mov     [rdi], cx
0x18000745a  mov     eax, edx
0x18000745c  add     rsp, 38h
0x180007460  pop     rdi
0x180007461  pop     rbx
0x180007462  retn
```
