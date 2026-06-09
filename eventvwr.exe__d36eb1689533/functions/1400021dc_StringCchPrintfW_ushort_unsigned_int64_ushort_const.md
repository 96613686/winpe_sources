# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400021dc`
- end: `0x140002260`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001c68`

## callees

- `0x1400021dc`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14000221b`
- `msvcrt!_vsnwprintf` at `0x14000221b`

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
0x1400021dc  mov     [rsp+arg_10], r8
0x1400021e1  mov     qword ptr [rsp+Args], r9
0x1400021e6  push    rbx
0x1400021e7  push    rdi
0x1400021e8  sub     rsp, 38h
0x1400021ec  mov     rax, rdx
0x1400021ef  mov     rdi, rcx
0x1400021f2  test    rdx, rdx
0x1400021f5  jz      short loc_140002248
0x1400021f7  cmp     rax, 7FFFFFFFh
0x1400021fd  jbe     short loc_140002206
0x1400021ff  mov     edx, 80070057h
0x140002204  jmp     short loc_140002252
0x140002206  lea     rbx, [rdx-1]
0x14000220a  mov     [rsp+48h+var_28], 0
0x140002213  mov     rdx, rbx; BufferCount
0x140002216  lea     r9, [rsp+48h+Args]; Args
0x14000221b  call    cs:__imp__vsnwprintf
0x140002221  test    eax, eax
0x140002223  js      short loc_14000223B
0x140002225  cdqe
0x140002227  cmp     rax, rbx
0x14000222a  ja      short loc_14000223B
0x14000222c  xor     edx, edx
0x14000222e  cmp     rax, rbx
0x140002231  jnz     short loc_140002257
0x140002233  xor     eax, eax
0x140002235  mov     [rdi+rbx*2], ax
0x140002239  jmp     short loc_140002257
0x14000223b  xor     eax, eax
0x14000223d  mov     edx, 8007007Ah
0x140002242  mov     [rdi+rbx*2], ax
0x140002246  jmp     short loc_140002257
0x140002248  mov     edx, 80070057h
0x14000224d  test    rax, rax
0x140002250  jz      short loc_140002257
0x140002252  xor     ecx, ecx
0x140002254  mov     [rdi], cx
0x140002257  mov     eax, edx
0x140002259  add     rsp, 38h
0x14000225d  pop     rdi
0x14000225e  pop     rbx
0x14000225f  retn
```
