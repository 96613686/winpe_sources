# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400028f4`
- end: `0x140002978`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1400029f0`
- `0x1400031c0`
- `0x1400033b4`
- `0x140003534`
- `0x140003624`
- `0x1400037ac`
- `0x140003c50`
- `0x1400040dc`
- `0x140004640`
- `0x140005560`

## callees

- `0x1400028f4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140002933`
- `msvcrt!_vsnwprintf` at `0x140002933`

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
0x1400028f4  mov     [rsp+arg_10], r8
0x1400028f9  mov     qword ptr [rsp+Args], r9
0x1400028fe  push    rbx
0x1400028ff  push    rdi
0x140002900  sub     rsp, 38h
0x140002904  mov     rax, rdx
0x140002907  mov     rdi, rcx
0x14000290a  test    rdx, rdx
0x14000290d  jz      short loc_140002960
0x14000290f  cmp     rax, 7FFFFFFFh
0x140002915  jbe     short loc_14000291E
0x140002917  mov     edx, 80070057h
0x14000291c  jmp     short loc_14000296A
0x14000291e  lea     rbx, [rdx-1]
0x140002922  mov     [rsp+48h+var_28], 0
0x14000292b  mov     rdx, rbx; BufferCount
0x14000292e  lea     r9, [rsp+48h+Args]; Args
0x140002933  call    cs:__imp__vsnwprintf
0x140002939  test    eax, eax
0x14000293b  js      short loc_140002953
0x14000293d  cdqe
0x14000293f  cmp     rax, rbx
0x140002942  ja      short loc_140002953
0x140002944  xor     edx, edx
0x140002946  cmp     rax, rbx
0x140002949  jnz     short loc_14000296F
0x14000294b  xor     eax, eax
0x14000294d  mov     [rdi+rbx*2], ax
0x140002951  jmp     short loc_14000296F
0x140002953  xor     eax, eax
0x140002955  mov     edx, 8007007Ah
0x14000295a  mov     [rdi+rbx*2], ax
0x14000295e  jmp     short loc_14000296F
0x140002960  mov     edx, 80070057h
0x140002965  test    rax, rax
0x140002968  jz      short loc_14000296F
0x14000296a  xor     ecx, ecx
0x14000296c  mov     [rdi], cx
0x14000296f  mov     eax, edx
0x140002971  add     rsp, 38h
0x140002975  pop     rdi
0x140002976  pop     rbx
0x140002977  retn
```
