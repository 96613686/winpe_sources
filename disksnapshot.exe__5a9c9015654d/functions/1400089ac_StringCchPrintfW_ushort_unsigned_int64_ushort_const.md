# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400089ac`
- end: `0x140008a2f`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140006b20`
- `0x140007c84`
- `0x14000a854`
- `0x14000ac0c`
- `0x14000ba74`

## callees

- `0x1400028cc`
- `0x1400089ac`

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
0x1400089ac  mov     [rsp+arg_10], r8
0x1400089b1  mov     qword ptr [rsp+Args], r9
0x1400089b6  push    rbx
0x1400089b7  push    rdi
0x1400089b8  sub     rsp, 38h
0x1400089bc  mov     rax, rdx
0x1400089bf  mov     rdi, rcx
0x1400089c2  test    rdx, rdx
0x1400089c5  jz      short loc_140008A17
0x1400089c7  cmp     rax, 7FFFFFFFh
0x1400089cd  jbe     short loc_1400089D6
0x1400089cf  mov     edx, 80070057h
0x1400089d4  jmp     short loc_140008A21
0x1400089d6  lea     rbx, [rdx-1]
0x1400089da  mov     [rsp+48h+var_28], 0
0x1400089e3  mov     rdx, rbx; BufferCount
0x1400089e6  lea     r9, [rsp+48h+Args]; Args
0x1400089eb  call    _vsnwprintf
0x1400089f0  test    eax, eax
0x1400089f2  js      short loc_140008A0A
0x1400089f4  cdqe
0x1400089f6  cmp     rax, rbx
0x1400089f9  ja      short loc_140008A0A
0x1400089fb  xor     edx, edx
0x1400089fd  cmp     rax, rbx
0x140008a00  jnz     short loc_140008A26
0x140008a02  xor     eax, eax
0x140008a04  mov     [rdi+rbx*2], ax
0x140008a08  jmp     short loc_140008A26
0x140008a0a  xor     eax, eax
0x140008a0c  mov     edx, 8007007Ah
0x140008a11  mov     [rdi+rbx*2], ax
0x140008a15  jmp     short loc_140008A26
0x140008a17  mov     edx, 80070057h
0x140008a1c  test    rax, rax
0x140008a1f  jz      short loc_140008A26
0x140008a21  xor     ecx, ecx
0x140008a23  mov     [rdi], cx
0x140008a26  mov     eax, edx
0x140008a28  add     rsp, 38h
0x140008a2c  pop     rdi
0x140008a2d  pop     rbx
0x140008a2e  retn
```
