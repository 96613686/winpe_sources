# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000bccc`
- end: `0x14000bd4f`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ce8`
- `0x1400060b8`
- `0x14000fffd`
- `0x14001012b`
- `0x14001025f`
- `0x1400102ca`

## callees

- `0x140002c44`
- `0x14000bccc`

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
0x14000bccc  mov     [rsp+arg_10], r8
0x14000bcd1  mov     qword ptr [rsp+Args], r9
0x14000bcd6  push    rbx
0x14000bcd7  push    rdi
0x14000bcd8  sub     rsp, 38h
0x14000bcdc  mov     rax, rdx
0x14000bcdf  mov     rdi, rcx
0x14000bce2  test    rdx, rdx
0x14000bce5  jz      short loc_14000BD37
0x14000bce7  cmp     rax, 7FFFFFFFh
0x14000bced  jbe     short loc_14000BCF6
0x14000bcef  mov     edx, 80070057h
0x14000bcf4  jmp     short loc_14000BD41
0x14000bcf6  lea     rbx, [rdx-1]
0x14000bcfa  mov     [rsp+48h+var_28], 0
0x14000bd03  mov     rdx, rbx; BufferCount
0x14000bd06  lea     r9, [rsp+48h+Args]; Args
0x14000bd0b  call    _vsnwprintf
0x14000bd10  test    eax, eax
0x14000bd12  js      short loc_14000BD2A
0x14000bd14  cdqe
0x14000bd16  cmp     rax, rbx
0x14000bd19  ja      short loc_14000BD2A
0x14000bd1b  xor     edx, edx
0x14000bd1d  cmp     rax, rbx
0x14000bd20  jnz     short loc_14000BD46
0x14000bd22  xor     eax, eax
0x14000bd24  mov     [rdi+rbx*2], ax
0x14000bd28  jmp     short loc_14000BD46
0x14000bd2a  xor     eax, eax
0x14000bd2c  mov     edx, 8007007Ah
0x14000bd31  mov     [rdi+rbx*2], ax
0x14000bd35  jmp     short loc_14000BD46
0x14000bd37  mov     edx, 80070057h
0x14000bd3c  test    rax, rax
0x14000bd3f  jz      short loc_14000BD46
0x14000bd41  xor     ecx, ecx
0x14000bd43  mov     [rdi], cx
0x14000bd46  mov     eax, edx
0x14000bd48  add     rsp, 38h
0x14000bd4c  pop     rdi
0x14000bd4d  pop     rbx
0x14000bd4e  retn
```
