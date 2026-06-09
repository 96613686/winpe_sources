# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000b5c4`
- end: `0x14000b648`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140004bd0`
- `0x1400076e4`
- `0x14000dd30`
- `0x14000e924`
- `0x14000fc30`
- `0x14000fe20`
- `0x140010050`
- `0x1400105d8`
- `0x140011c10`
- `0x140012a50`
- `0x140013330`
- `0x1400144a4`
- `0x140017094`
- `0x1400172c4`
- `0x1400175e8`

## callees

- `0x14000b5c4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14000b603`
- `msvcrt!_vsnwprintf` at `0x14000b603`

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
0x14000b5c4  mov     [rsp+arg_10], r8
0x14000b5c9  mov     qword ptr [rsp+Args], r9
0x14000b5ce  push    rbx
0x14000b5cf  push    rdi
0x14000b5d0  sub     rsp, 38h
0x14000b5d4  mov     rax, rdx
0x14000b5d7  mov     rdi, rcx
0x14000b5da  test    rdx, rdx
0x14000b5dd  jz      short loc_14000B630
0x14000b5df  cmp     rax, 7FFFFFFFh
0x14000b5e5  jbe     short loc_14000B5EE
0x14000b5e7  mov     edx, 80070057h
0x14000b5ec  jmp     short loc_14000B63A
0x14000b5ee  lea     rbx, [rdx-1]
0x14000b5f2  mov     [rsp+48h+var_28], 0
0x14000b5fb  mov     rdx, rbx; BufferCount
0x14000b5fe  lea     r9, [rsp+48h+Args]; Args
0x14000b603  call    cs:__imp__vsnwprintf
0x14000b609  test    eax, eax
0x14000b60b  js      short loc_14000B623
0x14000b60d  cdqe
0x14000b60f  cmp     rax, rbx
0x14000b612  ja      short loc_14000B623
0x14000b614  xor     edx, edx
0x14000b616  cmp     rax, rbx
0x14000b619  jnz     short loc_14000B63F
0x14000b61b  xor     eax, eax
0x14000b61d  mov     [rdi+rbx*2], ax
0x14000b621  jmp     short loc_14000B63F
0x14000b623  xor     eax, eax
0x14000b625  mov     edx, 8007007Ah
0x14000b62a  mov     [rdi+rbx*2], ax
0x14000b62e  jmp     short loc_14000B63F
0x14000b630  mov     edx, 80070057h
0x14000b635  test    rax, rax
0x14000b638  jz      short loc_14000B63F
0x14000b63a  xor     ecx, ecx
0x14000b63c  mov     [rdi], cx
0x14000b63f  mov     eax, edx
0x14000b641  add     rsp, 38h
0x14000b645  pop     rdi
0x14000b646  pop     rbx
0x14000b647  retn
```
