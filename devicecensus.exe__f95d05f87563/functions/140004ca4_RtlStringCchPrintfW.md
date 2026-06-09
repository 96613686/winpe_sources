# RtlStringCchPrintfW

- ea: `0x140004ca4`
- end: `0x140004d28`
- name: `RtlStringCchPrintfW`
- size: `132`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004dd4`
- `0x1400050a0`
- `0x14000fb14`

## callees

- `0x140004ca4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140004ce3`
- `msvcrt!_vsnwprintf` at `0x140004ce3`

## pseudocode

```c
__int64 RtlStringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
        v4 = -2147483643;
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
      v4 = -1073741811;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x140004ca4  mov     [rsp+arg_10], r8
0x140004ca9  mov     qword ptr [rsp+Args], r9
0x140004cae  push    rbx
0x140004caf  push    rdi
0x140004cb0  sub     rsp, 38h
0x140004cb4  mov     rax, rdx
0x140004cb7  mov     rdi, rcx
0x140004cba  test    rdx, rdx
0x140004cbd  jz      short loc_140004D10
0x140004cbf  cmp     rax, 7FFFFFFFh
0x140004cc5  jbe     short loc_140004CCE
0x140004cc7  mov     edx, 0C000000Dh
0x140004ccc  jmp     short loc_140004D1A
0x140004cce  lea     rbx, [rdx-1]
0x140004cd2  mov     [rsp+48h+var_28], 0
0x140004cdb  mov     rdx, rbx; BufferCount
0x140004cde  lea     r9, [rsp+48h+Args]; Args
0x140004ce3  call    cs:__imp__vsnwprintf
0x140004ce9  test    eax, eax
0x140004ceb  js      short loc_140004D03
0x140004ced  cdqe
0x140004cef  cmp     rax, rbx
0x140004cf2  ja      short loc_140004D03
0x140004cf4  xor     edx, edx
0x140004cf6  cmp     rax, rbx
0x140004cf9  jnz     short loc_140004D1F
0x140004cfb  xor     eax, eax
0x140004cfd  mov     [rdi+rbx*2], ax
0x140004d01  jmp     short loc_140004D1F
0x140004d03  xor     eax, eax
0x140004d05  mov     edx, 80000005h
0x140004d0a  mov     [rdi+rbx*2], ax
0x140004d0e  jmp     short loc_140004D1F
0x140004d10  mov     edx, 0C000000Dh
0x140004d15  test    rax, rax
0x140004d18  jz      short loc_140004D1F
0x140004d1a  xor     ecx, ecx
0x140004d1c  mov     [rdi], cx
0x140004d1f  mov     eax, edx
0x140004d21  add     rsp, 38h
0x140004d25  pop     rdi
0x140004d26  pop     rbx
0x140004d27  retn
```
