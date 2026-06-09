# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000440c`
- end: `0x180004490`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bc0`
- `0x180003ae8`

## callees

- `0x18000440c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000444b`
- `msvcrt!_vsnwprintf` at `0x18000444b`

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
0x18000440c  mov     [rsp+arg_10], r8
0x180004411  mov     qword ptr [rsp+Args], r9
0x180004416  push    rbx
0x180004417  push    rdi
0x180004418  sub     rsp, 38h
0x18000441c  mov     rax, rdx
0x18000441f  mov     rdi, rcx
0x180004422  test    rdx, rdx
0x180004425  jz      short loc_180004478
0x180004427  cmp     rax, 7FFFFFFFh
0x18000442d  jbe     short loc_180004436
0x18000442f  mov     edx, 80070057h
0x180004434  jmp     short loc_180004482
0x180004436  lea     rbx, [rdx-1]
0x18000443a  mov     [rsp+48h+var_28], 0
0x180004443  mov     rdx, rbx; BufferCount
0x180004446  lea     r9, [rsp+48h+Args]; Args
0x18000444b  call    cs:__imp__vsnwprintf
0x180004451  test    eax, eax
0x180004453  js      short loc_18000446B
0x180004455  cdqe
0x180004457  cmp     rax, rbx
0x18000445a  ja      short loc_18000446B
0x18000445c  xor     edx, edx
0x18000445e  cmp     rax, rbx
0x180004461  jnz     short loc_180004487
0x180004463  xor     eax, eax
0x180004465  mov     [rdi+rbx*2], ax
0x180004469  jmp     short loc_180004487
0x18000446b  xor     eax, eax
0x18000446d  mov     edx, 8007007Ah
0x180004472  mov     [rdi+rbx*2], ax
0x180004476  jmp     short loc_180004487
0x180004478  mov     edx, 80070057h
0x18000447d  test    rax, rax
0x180004480  jz      short loc_180004487
0x180004482  xor     ecx, ecx
0x180004484  mov     [rdi], cx
0x180004487  mov     eax, edx
0x180004489  add     rsp, 38h
0x18000448d  pop     rdi
0x18000448e  pop     rbx
0x18000448f  retn
```
