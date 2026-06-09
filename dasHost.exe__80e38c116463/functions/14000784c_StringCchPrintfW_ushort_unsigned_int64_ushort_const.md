# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000784c`
- end: `0x1400078cf`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400039d8`
- `0x140003da8`
- `0x140008d7c`
- `0x140012b58`
- `0x14001a9e4`
- `0x14001ab12`
- `0x14001ac46`
- `0x14001acb1`

## callees

- `0x1400020e8`
- `0x14000784c`

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
0x14000784c  mov     [rsp+arg_10], r8
0x140007851  mov     qword ptr [rsp+Args], r9
0x140007856  push    rbx
0x140007857  push    rdi
0x140007858  sub     rsp, 38h
0x14000785c  mov     rax, rdx
0x14000785f  mov     rdi, rcx
0x140007862  test    rdx, rdx
0x140007865  jz      short loc_1400078B7
0x140007867  cmp     rax, 7FFFFFFFh
0x14000786d  jbe     short loc_140007876
0x14000786f  mov     edx, 80070057h
0x140007874  jmp     short loc_1400078C1
0x140007876  lea     rbx, [rdx-1]
0x14000787a  mov     [rsp+48h+var_28], 0
0x140007883  mov     rdx, rbx; BufferCount
0x140007886  lea     r9, [rsp+48h+Args]; Args
0x14000788b  call    _vsnwprintf
0x140007890  test    eax, eax
0x140007892  js      short loc_1400078AA
0x140007894  cdqe
0x140007896  cmp     rax, rbx
0x140007899  ja      short loc_1400078AA
0x14000789b  xor     edx, edx
0x14000789d  cmp     rax, rbx
0x1400078a0  jnz     short loc_1400078C6
0x1400078a2  xor     eax, eax
0x1400078a4  mov     [rdi+rbx*2], ax
0x1400078a8  jmp     short loc_1400078C6
0x1400078aa  xor     eax, eax
0x1400078ac  mov     edx, 8007007Ah
0x1400078b1  mov     [rdi+rbx*2], ax
0x1400078b5  jmp     short loc_1400078C6
0x1400078b7  mov     edx, 80070057h
0x1400078bc  test    rax, rax
0x1400078bf  jz      short loc_1400078C6
0x1400078c1  xor     ecx, ecx
0x1400078c3  mov     [rdi], cx
0x1400078c6  mov     eax, edx
0x1400078c8  add     rsp, 38h
0x1400078cc  pop     rdi
0x1400078cd  pop     rbx
0x1400078ce  retn
```
