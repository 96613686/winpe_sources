# RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800052d0`
- end: `0x180005354`
- name: `?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000461c`
- `0x1800066ac`

## callees

- `0x180001c98`
- `0x1800052d0`

## pseudocode

```c
__int64 RtlStringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
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
0x1800052d0  mov     [rsp+arg_10], r8
0x1800052d5  mov     qword ptr [rsp+Args], r9
0x1800052da  push    rbx
0x1800052db  push    rdi
0x1800052dc  sub     rsp, 38h
0x1800052e0  mov     rax, rdx
0x1800052e3  mov     rdi, rcx
0x1800052e6  test    rdx, rdx
0x1800052e9  jz      short loc_18000533B
0x1800052eb  cmp     rax, 7FFFFFFFh
0x1800052f1  jbe     short loc_1800052FA
0x1800052f3  mov     edx, 0C000000Dh
0x1800052f8  jmp     short loc_180005345
0x1800052fa  lea     rbx, [rdx-1]
0x1800052fe  mov     [rsp+48h+var_28], 0
0x180005307  mov     rdx, rbx; BufferCount
0x18000530a  lea     r9, [rsp+48h+Args]; Args
0x18000530f  call    _vsnwprintf
0x180005314  test    eax, eax
0x180005316  js      short loc_18000532E
0x180005318  cdqe
0x18000531a  cmp     rax, rbx
0x18000531d  ja      short loc_18000532E
0x18000531f  xor     edx, edx
0x180005321  cmp     rax, rbx
0x180005324  jnz     short loc_18000534A
0x180005326  xor     eax, eax
0x180005328  mov     [rdi+rbx*2], ax
0x18000532c  jmp     short loc_18000534A
0x18000532e  xor     eax, eax
0x180005330  mov     edx, 80000005h
0x180005335  mov     [rdi+rbx*2], ax
0x180005339  jmp     short loc_18000534A
0x18000533b  mov     edx, 0C000000Dh
0x180005340  test    rax, rax
0x180005343  jz      short loc_18000534A
0x180005345  xor     ecx, ecx
0x180005347  mov     [rdi], cx
0x18000534a  mov     eax, edx
0x18000534c  add     rsp, 38h
0x180005350  pop     rdi
0x180005351  pop     rbx
0x180005352  retn
```
