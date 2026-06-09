# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005c20`
- end: `0x180005ca3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003734`
- `0x18000c877`
- `0x18000c96f`
- `0x18000caa3`
- `0x18000cb0e`

## callees

- `0x18000273c`
- `0x180005c20`

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
0x180005c20  mov     [rsp+arg_10], r8
0x180005c25  mov     qword ptr [rsp+Args], r9
0x180005c2a  push    rbx
0x180005c2b  push    rdi
0x180005c2c  sub     rsp, 38h
0x180005c30  mov     rax, rdx
0x180005c33  mov     rdi, rcx
0x180005c36  test    rdx, rdx
0x180005c39  jz      short loc_180005C8B
0x180005c3b  cmp     rax, 7FFFFFFFh
0x180005c41  jbe     short loc_180005C4A
0x180005c43  mov     edx, 80070057h
0x180005c48  jmp     short loc_180005C95
0x180005c4a  lea     rbx, [rdx-1]
0x180005c4e  mov     [rsp+48h+var_28], 0
0x180005c57  mov     rdx, rbx; BufferCount
0x180005c5a  lea     r9, [rsp+48h+Args]; Args
0x180005c5f  call    _vsnwprintf
0x180005c64  test    eax, eax
0x180005c66  js      short loc_180005C7E
0x180005c68  cdqe
0x180005c6a  cmp     rax, rbx
0x180005c6d  ja      short loc_180005C7E
0x180005c6f  xor     edx, edx
0x180005c71  cmp     rax, rbx
0x180005c74  jnz     short loc_180005C9A
0x180005c76  xor     eax, eax
0x180005c78  mov     [rdi+rbx*2], ax
0x180005c7c  jmp     short loc_180005C9A
0x180005c7e  xor     eax, eax
0x180005c80  mov     edx, 8007007Ah
0x180005c85  mov     [rdi+rbx*2], ax
0x180005c89  jmp     short loc_180005C9A
0x180005c8b  mov     edx, 80070057h
0x180005c90  test    rax, rax
0x180005c93  jz      short loc_180005C9A
0x180005c95  xor     ecx, ecx
0x180005c97  mov     [rdi], cx
0x180005c9a  mov     eax, edx
0x180005c9c  add     rsp, 38h
0x180005ca0  pop     rdi
0x180005ca1  pop     rbx
0x180005ca2  retn
```
