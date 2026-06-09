# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800026b0`
- end: `0x180002733`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002218`
- `0x180002c30`

## callees

- `0x180001da4`
- `0x1800026b0`

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
0x1800026b0  mov     [rsp+arg_10], r8
0x1800026b5  mov     qword ptr [rsp+Args], r9
0x1800026ba  push    rbx
0x1800026bb  push    rdi
0x1800026bc  sub     rsp, 38h
0x1800026c0  mov     rax, rdx
0x1800026c3  mov     rdi, rcx
0x1800026c6  test    rdx, rdx
0x1800026c9  jz      short loc_18000271B
0x1800026cb  cmp     rax, 7FFFFFFFh
0x1800026d1  jbe     short loc_1800026DA
0x1800026d3  mov     edx, 80070057h
0x1800026d8  jmp     short loc_180002725
0x1800026da  lea     rbx, [rdx-1]
0x1800026de  mov     [rsp+48h+var_28], 0
0x1800026e7  mov     rdx, rbx; BufferCount
0x1800026ea  lea     r9, [rsp+48h+Args]; Args
0x1800026ef  call    _vsnwprintf
0x1800026f4  test    eax, eax
0x1800026f6  js      short loc_18000270E
0x1800026f8  cdqe
0x1800026fa  cmp     rax, rbx
0x1800026fd  ja      short loc_18000270E
0x1800026ff  xor     edx, edx
0x180002701  cmp     rax, rbx
0x180002704  jnz     short loc_18000272A
0x180002706  xor     eax, eax
0x180002708  mov     [rdi+rbx*2], ax
0x18000270c  jmp     short loc_18000272A
0x18000270e  xor     eax, eax
0x180002710  mov     edx, 8007007Ah
0x180002715  mov     [rdi+rbx*2], ax
0x180002719  jmp     short loc_18000272A
0x18000271b  mov     edx, 80070057h
0x180002720  test    rax, rax
0x180002723  jz      short loc_18000272A
0x180002725  xor     ecx, ecx
0x180002727  mov     [rdi], cx
0x18000272a  mov     eax, edx
0x18000272c  add     rsp, 38h
0x180002730  pop     rdi
0x180002731  pop     rbx
0x180002732  retn
```
