# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180013510`
- end: `0x180013593`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180005454`
- `0x180008cc8`
- `0x180009098`
- `0x180020d98`
- `0x180020ec6`
- `0x180020ffa`
- `0x180021065`
- `0x180021889`
- `0x180021b0c`
- `0x180021b6b`
- `0x180021bca`
- `0x180021ccf`
- `0x180021f52`
- `0x180021fb1`
- `0x180022010`
- `0x18002206f`

## callees

- `0x180003970`
- `0x180013510`

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
0x180013510  mov     [rsp+arg_10], r8
0x180013515  mov     qword ptr [rsp+Args], r9
0x18001351a  push    rbx
0x18001351b  push    rdi
0x18001351c  sub     rsp, 38h
0x180013520  mov     rax, rdx
0x180013523  mov     rdi, rcx
0x180013526  test    rdx, rdx
0x180013529  jz      short loc_18001357B
0x18001352b  cmp     rax, 7FFFFFFFh
0x180013531  jbe     short loc_18001353A
0x180013533  mov     edx, 80070057h
0x180013538  jmp     short loc_180013585
0x18001353a  lea     rbx, [rdx-1]
0x18001353e  mov     [rsp+48h+var_28], 0
0x180013547  mov     rdx, rbx; BufferCount
0x18001354a  lea     r9, [rsp+48h+Args]; Args
0x18001354f  call    _vsnwprintf
0x180013554  test    eax, eax
0x180013556  js      short loc_18001356E
0x180013558  cdqe
0x18001355a  cmp     rax, rbx
0x18001355d  ja      short loc_18001356E
0x18001355f  xor     edx, edx
0x180013561  cmp     rax, rbx
0x180013564  jnz     short loc_18001358A
0x180013566  xor     eax, eax
0x180013568  mov     [rdi+rbx*2], ax
0x18001356c  jmp     short loc_18001358A
0x18001356e  xor     eax, eax
0x180013570  mov     edx, 8007007Ah
0x180013575  mov     [rdi+rbx*2], ax
0x180013579  jmp     short loc_18001358A
0x18001357b  mov     edx, 80070057h
0x180013580  test    rax, rax
0x180013583  jz      short loc_18001358A
0x180013585  xor     ecx, ecx
0x180013587  mov     [rdi], cx
0x18001358a  mov     eax, edx
0x18001358c  add     rsp, 38h
0x180013590  pop     rdi
0x180013591  pop     rbx
0x180013592  retn
```
