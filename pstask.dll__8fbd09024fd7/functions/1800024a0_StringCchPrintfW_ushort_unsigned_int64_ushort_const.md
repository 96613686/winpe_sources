# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800024a0`
- end: `0x180002524`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cac`
- `0x180002980`

## callees

- `0x1800024a0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800024df`
- `msvcrt!_vsnwprintf` at `0x1800024df`

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
0x1800024a0  mov     [rsp+arg_10], r8
0x1800024a5  mov     qword ptr [rsp+Args], r9
0x1800024aa  push    rbx
0x1800024ab  push    rdi
0x1800024ac  sub     rsp, 38h
0x1800024b0  mov     rax, rdx
0x1800024b3  mov     rdi, rcx
0x1800024b6  test    rdx, rdx
0x1800024b9  jz      short loc_18000250C
0x1800024bb  cmp     rax, 7FFFFFFFh
0x1800024c1  jbe     short loc_1800024CA
0x1800024c3  mov     edx, 80070057h
0x1800024c8  jmp     short loc_180002516
0x1800024ca  lea     rbx, [rdx-1]
0x1800024ce  mov     [rsp+48h+var_28], 0
0x1800024d7  mov     rdx, rbx; BufferCount
0x1800024da  lea     r9, [rsp+48h+Args]; Args
0x1800024df  call    cs:__imp__vsnwprintf
0x1800024e5  test    eax, eax
0x1800024e7  js      short loc_1800024FF
0x1800024e9  cdqe
0x1800024eb  cmp     rax, rbx
0x1800024ee  ja      short loc_1800024FF
0x1800024f0  xor     edx, edx
0x1800024f2  cmp     rax, rbx
0x1800024f5  jnz     short loc_18000251B
0x1800024f7  xor     eax, eax
0x1800024f9  mov     [rdi+rbx*2], ax
0x1800024fd  jmp     short loc_18000251B
0x1800024ff  xor     eax, eax
0x180002501  mov     edx, 8007007Ah
0x180002506  mov     [rdi+rbx*2], ax
0x18000250a  jmp     short loc_18000251B
0x18000250c  mov     edx, 80070057h
0x180002511  test    rax, rax
0x180002514  jz      short loc_18000251B
0x180002516  xor     ecx, ecx
0x180002518  mov     [rdi], cx
0x18000251b  mov     eax, edx
0x18000251d  add     rsp, 38h
0x180002521  pop     rdi
0x180002522  pop     rbx
0x180002523  retn
```
