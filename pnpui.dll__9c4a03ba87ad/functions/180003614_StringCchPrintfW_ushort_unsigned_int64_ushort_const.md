# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003614`
- end: `0x180003698`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036a0`
- `0x180003950`
- `0x180004d1c`
- `0x1800050c0`
- `0x180007080`
- `0x18000c008`

## callees

- `0x180003614`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180003653`
- `msvcrt!_vsnwprintf` at `0x180003653`

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
0x180003614  mov     [rsp+arg_10], r8
0x180003619  mov     qword ptr [rsp+Args], r9
0x18000361e  push    rbx
0x18000361f  push    rdi
0x180003620  sub     rsp, 38h
0x180003624  mov     rax, rdx
0x180003627  mov     rdi, rcx
0x18000362a  test    rdx, rdx
0x18000362d  jz      short loc_180003680
0x18000362f  cmp     rax, 7FFFFFFFh
0x180003635  jbe     short loc_18000363E
0x180003637  mov     edx, 80070057h
0x18000363c  jmp     short loc_18000368A
0x18000363e  lea     rbx, [rdx-1]
0x180003642  mov     [rsp+48h+var_28], 0
0x18000364b  mov     rdx, rbx; BufferCount
0x18000364e  lea     r9, [rsp+48h+Args]; Args
0x180003653  call    cs:__imp__vsnwprintf
0x180003659  test    eax, eax
0x18000365b  js      short loc_180003673
0x18000365d  cdqe
0x18000365f  cmp     rax, rbx
0x180003662  ja      short loc_180003673
0x180003664  xor     edx, edx
0x180003666  cmp     rax, rbx
0x180003669  jnz     short loc_18000368F
0x18000366b  xor     eax, eax
0x18000366d  mov     [rdi+rbx*2], ax
0x180003671  jmp     short loc_18000368F
0x180003673  xor     eax, eax
0x180003675  mov     edx, 8007007Ah
0x18000367a  mov     [rdi+rbx*2], ax
0x18000367e  jmp     short loc_18000368F
0x180003680  mov     edx, 80070057h
0x180003685  test    rax, rax
0x180003688  jz      short loc_18000368F
0x18000368a  xor     ecx, ecx
0x18000368c  mov     [rdi], cx
0x18000368f  mov     eax, edx
0x180003691  add     rsp, 38h
0x180003695  pop     rdi
0x180003696  pop     rbx
0x180003697  retn
```
