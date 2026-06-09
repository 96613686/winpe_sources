# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007370`
- end: `0x1800073f3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003518`
- `0x180003e04`
- `0x180007be0`

## callees

- `0x1800020dc`
- `0x180007370`

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
0x180007370  mov     [rsp+arg_10], r8
0x180007375  mov     qword ptr [rsp+Args], r9
0x18000737a  push    rbx
0x18000737b  push    rdi
0x18000737c  sub     rsp, 38h
0x180007380  mov     rax, rdx
0x180007383  mov     rdi, rcx
0x180007386  test    rdx, rdx
0x180007389  jz      short loc_1800073DB
0x18000738b  cmp     rax, 7FFFFFFFh
0x180007391  jbe     short loc_18000739A
0x180007393  mov     edx, 80070057h
0x180007398  jmp     short loc_1800073E5
0x18000739a  lea     rbx, [rdx-1]
0x18000739e  mov     [rsp+48h+var_28], 0
0x1800073a7  mov     rdx, rbx; BufferCount
0x1800073aa  lea     r9, [rsp+48h+Args]; Args
0x1800073af  call    _vsnwprintf
0x1800073b4  test    eax, eax
0x1800073b6  js      short loc_1800073CE
0x1800073b8  cdqe
0x1800073ba  cmp     rax, rbx
0x1800073bd  ja      short loc_1800073CE
0x1800073bf  xor     edx, edx
0x1800073c1  cmp     rax, rbx
0x1800073c4  jnz     short loc_1800073EA
0x1800073c6  xor     eax, eax
0x1800073c8  mov     [rdi+rbx*2], ax
0x1800073cc  jmp     short loc_1800073EA
0x1800073ce  xor     eax, eax
0x1800073d0  mov     edx, 8007007Ah
0x1800073d5  mov     [rdi+rbx*2], ax
0x1800073d9  jmp     short loc_1800073EA
0x1800073db  mov     edx, 80070057h
0x1800073e0  test    rax, rax
0x1800073e3  jz      short loc_1800073EA
0x1800073e5  xor     ecx, ecx
0x1800073e7  mov     [rdi], cx
0x1800073ea  mov     eax, edx
0x1800073ec  add     rsp, 38h
0x1800073f0  pop     rdi
0x1800073f1  pop     rbx
0x1800073f2  retn
```
