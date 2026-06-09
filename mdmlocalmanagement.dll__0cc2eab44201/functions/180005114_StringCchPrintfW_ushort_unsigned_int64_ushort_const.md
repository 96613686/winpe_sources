# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005114`
- end: `0x180005198`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f5c`
- `0x180006000`

## callees

- `0x180001ff8`
- `0x180005114`

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
0x180005114  mov     [rsp+arg_10], r8
0x180005119  mov     qword ptr [rsp+Args], r9
0x18000511e  push    rbx
0x18000511f  push    rdi
0x180005120  sub     rsp, 38h
0x180005124  mov     rax, rdx
0x180005127  mov     rdi, rcx
0x18000512a  test    rdx, rdx
0x18000512d  jz      short loc_18000517F
0x18000512f  cmp     rax, 7FFFFFFFh
0x180005135  jbe     short loc_18000513E
0x180005137  mov     edx, 80070057h
0x18000513c  jmp     short loc_180005189
0x18000513e  lea     rbx, [rdx-1]
0x180005142  mov     [rsp+48h+var_28], 0
0x18000514b  mov     rdx, rbx; BufferCount
0x18000514e  lea     r9, [rsp+48h+Args]; Args
0x180005153  call    _vsnwprintf
0x180005158  test    eax, eax
0x18000515a  js      short loc_180005172
0x18000515c  cdqe
0x18000515e  cmp     rax, rbx
0x180005161  ja      short loc_180005172
0x180005163  xor     edx, edx
0x180005165  cmp     rax, rbx
0x180005168  jnz     short loc_18000518E
0x18000516a  xor     eax, eax
0x18000516c  mov     [rdi+rbx*2], ax
0x180005170  jmp     short loc_18000518E
0x180005172  xor     eax, eax
0x180005174  mov     edx, 8007007Ah
0x180005179  mov     [rdi+rbx*2], ax
0x18000517d  jmp     short loc_18000518E
0x18000517f  mov     edx, 80070057h
0x180005184  test    rax, rax
0x180005187  jz      short loc_18000518E
0x180005189  xor     ecx, ecx
0x18000518b  mov     [rdi], cx
0x18000518e  mov     eax, edx
0x180005190  add     rsp, 38h
0x180005194  pop     rdi
0x180005195  pop     rbx
0x180005196  retn
```
