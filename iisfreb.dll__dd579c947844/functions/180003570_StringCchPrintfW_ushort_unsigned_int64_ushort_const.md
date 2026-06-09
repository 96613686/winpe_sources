# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003570`
- end: `0x1800035f4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023cc`
- `0x1800047a4`
- `0x180008178`

## callees

- `0x180003570`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800035af`
- `msvcrt!_vsnwprintf` at `0x1800035af`

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
0x180003570  mov     [rsp+arg_10], r8
0x180003575  mov     qword ptr [rsp+Args], r9
0x18000357a  push    rbx
0x18000357b  push    rdi
0x18000357c  sub     rsp, 38h
0x180003580  mov     rax, rdx
0x180003583  mov     rdi, rcx
0x180003586  test    rdx, rdx
0x180003589  jz      short loc_1800035DC
0x18000358b  cmp     rax, 7FFFFFFFh
0x180003591  jbe     short loc_18000359A
0x180003593  mov     edx, 80070057h
0x180003598  jmp     short loc_1800035E6
0x18000359a  lea     rbx, [rdx-1]
0x18000359e  mov     [rsp+48h+var_28], 0
0x1800035a7  mov     rdx, rbx; BufferCount
0x1800035aa  lea     r9, [rsp+48h+Args]; Args
0x1800035af  call    cs:__imp__vsnwprintf
0x1800035b5  test    eax, eax
0x1800035b7  js      short loc_1800035CF
0x1800035b9  cdqe
0x1800035bb  cmp     rax, rbx
0x1800035be  ja      short loc_1800035CF
0x1800035c0  xor     edx, edx
0x1800035c2  cmp     rax, rbx
0x1800035c5  jnz     short loc_1800035EB
0x1800035c7  xor     eax, eax
0x1800035c9  mov     [rdi+rbx*2], ax
0x1800035cd  jmp     short loc_1800035EB
0x1800035cf  xor     eax, eax
0x1800035d1  mov     edx, 8007007Ah
0x1800035d6  mov     [rdi+rbx*2], ax
0x1800035da  jmp     short loc_1800035EB
0x1800035dc  mov     edx, 80070057h
0x1800035e1  test    rax, rax
0x1800035e4  jz      short loc_1800035EB
0x1800035e6  xor     ecx, ecx
0x1800035e8  mov     [rdi], cx
0x1800035eb  mov     eax, edx
0x1800035ed  add     rsp, 38h
0x1800035f1  pop     rdi
0x1800035f2  pop     rbx
0x1800035f3  retn
```
