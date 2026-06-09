# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400088c0`
- end: `0x140008944`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011e4`
- `0x140004768`
- `0x1400049a4`
- `0x140006e10`
- `0x140007110`
- `0x140008300`

## callees

- `0x1400088c0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400088ff`
- `msvcrt!_vsnwprintf` at `0x1400088ff`

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
0x1400088c0  mov     [rsp+arg_10], r8
0x1400088c5  mov     qword ptr [rsp+Args], r9
0x1400088ca  push    rbx
0x1400088cb  push    rdi
0x1400088cc  sub     rsp, 38h
0x1400088d0  mov     rax, rdx
0x1400088d3  mov     rdi, rcx
0x1400088d6  test    rdx, rdx
0x1400088d9  jz      short loc_14000892C
0x1400088db  cmp     rax, 7FFFFFFFh
0x1400088e1  jbe     short loc_1400088EA
0x1400088e3  mov     edx, 80070057h
0x1400088e8  jmp     short loc_140008936
0x1400088ea  lea     rbx, [rdx-1]
0x1400088ee  mov     [rsp+48h+var_28], 0
0x1400088f7  mov     rdx, rbx; BufferCount
0x1400088fa  lea     r9, [rsp+48h+Args]; Args
0x1400088ff  call    cs:__imp__vsnwprintf
0x140008905  test    eax, eax
0x140008907  js      short loc_14000891F
0x140008909  cdqe
0x14000890b  cmp     rax, rbx
0x14000890e  ja      short loc_14000891F
0x140008910  xor     edx, edx
0x140008912  cmp     rax, rbx
0x140008915  jnz     short loc_14000893B
0x140008917  xor     eax, eax
0x140008919  mov     [rdi+rbx*2], ax
0x14000891d  jmp     short loc_14000893B
0x14000891f  xor     eax, eax
0x140008921  mov     edx, 8007007Ah
0x140008926  mov     [rdi+rbx*2], ax
0x14000892a  jmp     short loc_14000893B
0x14000892c  mov     edx, 80070057h
0x140008931  test    rax, rax
0x140008934  jz      short loc_14000893B
0x140008936  xor     ecx, ecx
0x140008938  mov     [rdi], cx
0x14000893b  mov     eax, edx
0x14000893d  add     rsp, 38h
0x140008941  pop     rdi
0x140008942  pop     rbx
0x140008943  retn
```
