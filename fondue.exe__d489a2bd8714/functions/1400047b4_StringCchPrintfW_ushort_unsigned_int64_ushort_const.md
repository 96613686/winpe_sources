# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400047b4`
- end: `0x140004838`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002ab8`

## callees

- `0x1400047b4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400047f3`
- `msvcrt!_vsnwprintf` at `0x1400047f3`

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
0x1400047b4  mov     [rsp+arg_10], r8
0x1400047b9  mov     qword ptr [rsp+Args], r9
0x1400047be  push    rbx
0x1400047bf  push    rdi
0x1400047c0  sub     rsp, 38h
0x1400047c4  mov     rax, rdx
0x1400047c7  mov     rdi, rcx
0x1400047ca  test    rdx, rdx
0x1400047cd  jz      short loc_140004820
0x1400047cf  cmp     rax, 7FFFFFFFh
0x1400047d5  jbe     short loc_1400047DE
0x1400047d7  mov     edx, 80070057h
0x1400047dc  jmp     short loc_14000482A
0x1400047de  lea     rbx, [rdx-1]
0x1400047e2  mov     [rsp+48h+var_28], 0
0x1400047eb  mov     rdx, rbx; BufferCount
0x1400047ee  lea     r9, [rsp+48h+Args]; Args
0x1400047f3  call    cs:__imp__vsnwprintf
0x1400047f9  test    eax, eax
0x1400047fb  js      short loc_140004813
0x1400047fd  cdqe
0x1400047ff  cmp     rax, rbx
0x140004802  ja      short loc_140004813
0x140004804  xor     edx, edx
0x140004806  cmp     rax, rbx
0x140004809  jnz     short loc_14000482F
0x14000480b  xor     eax, eax
0x14000480d  mov     [rdi+rbx*2], ax
0x140004811  jmp     short loc_14000482F
0x140004813  xor     eax, eax
0x140004815  mov     edx, 8007007Ah
0x14000481a  mov     [rdi+rbx*2], ax
0x14000481e  jmp     short loc_14000482F
0x140004820  mov     edx, 80070057h
0x140004825  test    rax, rax
0x140004828  jz      short loc_14000482F
0x14000482a  xor     ecx, ecx
0x14000482c  mov     [rdi], cx
0x14000482f  mov     eax, edx
0x140004831  add     rsp, 38h
0x140004835  pop     rdi
0x140004836  pop     rbx
0x140004837  retn
```
