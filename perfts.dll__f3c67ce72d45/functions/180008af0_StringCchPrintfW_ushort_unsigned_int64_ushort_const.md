# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180008af0`
- end: `0x180008b74`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058b8`
- `0x180007668`
- `0x180009eb4`
- `0x180009fac`
- `0x18000a0e0`
- `0x18000a14b`

## callees

- `0x180008af0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180008b2f`
- `msvcrt!_vsnwprintf` at `0x180008b2f`

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
0x180008af0  mov     [rsp+arg_10], r8
0x180008af5  mov     qword ptr [rsp+Args], r9
0x180008afa  push    rbx
0x180008afb  push    rdi
0x180008afc  sub     rsp, 38h
0x180008b00  mov     rax, rdx
0x180008b03  mov     rdi, rcx
0x180008b06  test    rdx, rdx
0x180008b09  jz      short loc_180008B5C
0x180008b0b  cmp     rax, 7FFFFFFFh
0x180008b11  jbe     short loc_180008B1A
0x180008b13  mov     edx, 80070057h
0x180008b18  jmp     short loc_180008B66
0x180008b1a  lea     rbx, [rdx-1]
0x180008b1e  mov     [rsp+48h+var_28], 0
0x180008b27  mov     rdx, rbx; BufferCount
0x180008b2a  lea     r9, [rsp+48h+Args]; Args
0x180008b2f  call    cs:__imp__vsnwprintf
0x180008b35  test    eax, eax
0x180008b37  js      short loc_180008B4F
0x180008b39  cdqe
0x180008b3b  cmp     rax, rbx
0x180008b3e  ja      short loc_180008B4F
0x180008b40  xor     edx, edx
0x180008b42  cmp     rax, rbx
0x180008b45  jnz     short loc_180008B6B
0x180008b47  xor     eax, eax
0x180008b49  mov     [rdi+rbx*2], ax
0x180008b4d  jmp     short loc_180008B6B
0x180008b4f  xor     eax, eax
0x180008b51  mov     edx, 8007007Ah
0x180008b56  mov     [rdi+rbx*2], ax
0x180008b5a  jmp     short loc_180008B6B
0x180008b5c  mov     edx, 80070057h
0x180008b61  test    rax, rax
0x180008b64  jz      short loc_180008B6B
0x180008b66  xor     ecx, ecx
0x180008b68  mov     [rdi], cx
0x180008b6b  mov     eax, edx
0x180008b6d  add     rsp, 38h
0x180008b71  pop     rdi
0x180008b72  pop     rbx
0x180008b73  retn
```
