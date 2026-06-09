# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000f3d0`
- end: `0x18000f453`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009090`
- `0x18000dc30`
- `0x180011020`
- `0x180015b84`

## callees

- `0x18000a864`
- `0x18000f3d0`

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
0x18000f3d0  mov     [rsp+arg_10], r8
0x18000f3d5  mov     qword ptr [rsp+Args], r9
0x18000f3da  push    rbx
0x18000f3db  push    rdi
0x18000f3dc  sub     rsp, 38h
0x18000f3e0  mov     rax, rdx
0x18000f3e3  mov     rdi, rcx
0x18000f3e6  test    rdx, rdx
0x18000f3e9  jz      short loc_18000F43B
0x18000f3eb  cmp     rax, 7FFFFFFFh
0x18000f3f1  jbe     short loc_18000F3FA
0x18000f3f3  mov     edx, 80070057h
0x18000f3f8  jmp     short loc_18000F445
0x18000f3fa  lea     rbx, [rdx-1]
0x18000f3fe  mov     [rsp+48h+var_28], 0
0x18000f407  mov     rdx, rbx; BufferCount
0x18000f40a  lea     r9, [rsp+48h+Args]; Args
0x18000f40f  call    _vsnwprintf
0x18000f414  test    eax, eax
0x18000f416  js      short loc_18000F42E
0x18000f418  cdqe
0x18000f41a  cmp     rax, rbx
0x18000f41d  ja      short loc_18000F42E
0x18000f41f  xor     edx, edx
0x18000f421  cmp     rax, rbx
0x18000f424  jnz     short loc_18000F44A
0x18000f426  xor     eax, eax
0x18000f428  mov     [rdi+rbx*2], ax
0x18000f42c  jmp     short loc_18000F44A
0x18000f42e  xor     eax, eax
0x18000f430  mov     edx, 8007007Ah
0x18000f435  mov     [rdi+rbx*2], ax
0x18000f439  jmp     short loc_18000F44A
0x18000f43b  mov     edx, 80070057h
0x18000f440  test    rax, rax
0x18000f443  jz      short loc_18000F44A
0x18000f445  xor     ecx, ecx
0x18000f447  mov     [rdi], cx
0x18000f44a  mov     eax, edx
0x18000f44c  add     rsp, 38h
0x18000f450  pop     rdi
0x18000f451  pop     rbx
0x18000f452  retn
```
