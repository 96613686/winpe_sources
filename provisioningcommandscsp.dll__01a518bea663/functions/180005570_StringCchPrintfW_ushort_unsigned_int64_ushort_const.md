# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005570`
- end: `0x1800055f4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003140`
- `0x18000cac1`
- `0x18000cbb9`
- `0x18000cced`
- `0x18000cd58`

## callees

- `0x180005570`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800055af`
- `msvcrt!_vsnwprintf` at `0x1800055af`

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
0x180005570  mov     [rsp+arg_10], r8
0x180005575  mov     qword ptr [rsp+Args], r9
0x18000557a  push    rbx
0x18000557b  push    rdi
0x18000557c  sub     rsp, 38h
0x180005580  mov     rax, rdx
0x180005583  mov     rdi, rcx
0x180005586  test    rdx, rdx
0x180005589  jz      short loc_1800055DC
0x18000558b  cmp     rax, 7FFFFFFFh
0x180005591  jbe     short loc_18000559A
0x180005593  mov     edx, 80070057h
0x180005598  jmp     short loc_1800055E6
0x18000559a  lea     rbx, [rdx-1]
0x18000559e  mov     [rsp+48h+var_28], 0
0x1800055a7  mov     rdx, rbx; BufferCount
0x1800055aa  lea     r9, [rsp+48h+Args]; Args
0x1800055af  call    cs:__imp__vsnwprintf
0x1800055b5  test    eax, eax
0x1800055b7  js      short loc_1800055CF
0x1800055b9  cdqe
0x1800055bb  cmp     rax, rbx
0x1800055be  ja      short loc_1800055CF
0x1800055c0  xor     edx, edx
0x1800055c2  cmp     rax, rbx
0x1800055c5  jnz     short loc_1800055EB
0x1800055c7  xor     eax, eax
0x1800055c9  mov     [rdi+rbx*2], ax
0x1800055cd  jmp     short loc_1800055EB
0x1800055cf  xor     eax, eax
0x1800055d1  mov     edx, 8007007Ah
0x1800055d6  mov     [rdi+rbx*2], ax
0x1800055da  jmp     short loc_1800055EB
0x1800055dc  mov     edx, 80070057h
0x1800055e1  test    rax, rax
0x1800055e4  jz      short loc_1800055EB
0x1800055e6  xor     ecx, ecx
0x1800055e8  mov     [rdi], cx
0x1800055eb  mov     eax, edx
0x1800055ed  add     rsp, 38h
0x1800055f1  pop     rdi
0x1800055f2  pop     rbx
0x1800055f3  retn
```
