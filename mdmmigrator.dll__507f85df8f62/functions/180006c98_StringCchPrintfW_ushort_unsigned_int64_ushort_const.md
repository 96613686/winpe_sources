# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006c98`
- end: `0x180006d1b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046a8`
- `0x18000ee18`
- `0x180010864`
- `0x180010dc0`
- `0x180012254`
- `0x180012b58`
- `0x180012d2c`
- `0x180019560`
- `0x180019904`
- `0x18001a1c4`
- `0x18001a25c`
- `0x18001a5c8`
- `0x18001b094`
- `0x18001ec2a`
- `0x18001ed22`
- `0x18001ee56`
- `0x18001eec1`

## callees

- `0x180002cc8`
- `0x180006c98`

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
0x180006c98  mov     [rsp+arg_10], r8
0x180006c9d  mov     qword ptr [rsp+Args], r9
0x180006ca2  push    rbx
0x180006ca3  push    rdi
0x180006ca4  sub     rsp, 38h
0x180006ca8  mov     rax, rdx
0x180006cab  mov     rdi, rcx
0x180006cae  test    rdx, rdx
0x180006cb1  jz      short loc_180006D03
0x180006cb3  cmp     rax, 7FFFFFFFh
0x180006cb9  jbe     short loc_180006CC2
0x180006cbb  mov     edx, 80070057h
0x180006cc0  jmp     short loc_180006D0D
0x180006cc2  lea     rbx, [rdx-1]
0x180006cc6  mov     [rsp+48h+var_28], 0
0x180006ccf  mov     rdx, rbx; BufferCount
0x180006cd2  lea     r9, [rsp+48h+Args]; Args
0x180006cd7  call    _vsnwprintf
0x180006cdc  test    eax, eax
0x180006cde  js      short loc_180006CF6
0x180006ce0  cdqe
0x180006ce2  cmp     rax, rbx
0x180006ce5  ja      short loc_180006CF6
0x180006ce7  xor     edx, edx
0x180006ce9  cmp     rax, rbx
0x180006cec  jnz     short loc_180006D12
0x180006cee  xor     eax, eax
0x180006cf0  mov     [rdi+rbx*2], ax
0x180006cf4  jmp     short loc_180006D12
0x180006cf6  xor     eax, eax
0x180006cf8  mov     edx, 8007007Ah
0x180006cfd  mov     [rdi+rbx*2], ax
0x180006d01  jmp     short loc_180006D12
0x180006d03  mov     edx, 80070057h
0x180006d08  test    rax, rax
0x180006d0b  jz      short loc_180006D12
0x180006d0d  xor     ecx, ecx
0x180006d0f  mov     [rdi], cx
0x180006d12  mov     eax, edx
0x180006d14  add     rsp, 38h
0x180006d18  pop     rdi
0x180006d19  pop     rbx
0x180006d1a  retn
```
