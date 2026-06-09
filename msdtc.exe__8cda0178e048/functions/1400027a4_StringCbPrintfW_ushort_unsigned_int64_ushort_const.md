# StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400027a4`
- end: `0x140002828`
- name: `?StringCbPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006a7c`
- `0x140006b68`

## callees

- `0x1400027a4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400027e3`
- `msvcrt!_vsnwprintf` at `0x1400027e3`

## pseudocode

```c
__int64 StringCbPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rax
  unsigned int v5; // edx
  unsigned __int64 v6; // rbx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  v4 = a2 >> 1;
  if ( a2 >> 1 )
  {
    if ( v4 <= 0x7FFFFFFF )
    {
      v6 = v4 - 1;
      v7 = _vsnwprintf(a1, v4 - 1, a3, Args);
      if ( v7 < 0 || v7 > v6 )
      {
        v5 = -2147024774;
        a1[v6] = 0;
      }
      else
      {
        v5 = 0;
        if ( v7 == v6 )
          a1[v6] = 0;
      }
    }
    else
    {
      v5 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x1400027a4  mov     [rsp+arg_10], r8
0x1400027a9  mov     qword ptr [rsp+Args], r9
0x1400027ae  push    rbx
0x1400027af  push    rdi
0x1400027b0  sub     rsp, 38h
0x1400027b4  mov     rax, rdx
0x1400027b7  mov     rdi, rcx
0x1400027ba  shr     rax, 1
0x1400027bd  jz      short loc_140002810
0x1400027bf  cmp     rax, 7FFFFFFFh
0x1400027c5  jbe     short loc_1400027CE
0x1400027c7  mov     edx, 80070057h
0x1400027cc  jmp     short loc_14000281A
0x1400027ce  lea     rbx, [rax-1]
0x1400027d2  mov     [rsp+48h+var_28], 0
0x1400027db  mov     rdx, rbx; BufferCount
0x1400027de  lea     r9, [rsp+48h+Args]; Args
0x1400027e3  call    cs:__imp__vsnwprintf
0x1400027e9  test    eax, eax
0x1400027eb  js      short loc_140002803
0x1400027ed  cdqe
0x1400027ef  cmp     rax, rbx
0x1400027f2  ja      short loc_140002803
0x1400027f4  xor     edx, edx
0x1400027f6  cmp     rax, rbx
0x1400027f9  jnz     short loc_14000281F
0x1400027fb  xor     eax, eax
0x1400027fd  mov     [rdi+rbx*2], ax
0x140002801  jmp     short loc_14000281F
0x140002803  xor     eax, eax
0x140002805  mov     edx, 8007007Ah
0x14000280a  mov     [rdi+rbx*2], ax
0x14000280e  jmp     short loc_14000281F
0x140002810  mov     edx, 80070057h
0x140002815  test    rax, rax
0x140002818  jz      short loc_14000281F
0x14000281a  xor     ecx, ecx
0x14000281c  mov     [rdi], cx
0x14000281f  mov     eax, edx
0x140002821  add     rsp, 38h
0x140002825  pop     rdi
0x140002826  pop     rbx
0x140002827  retn
```
