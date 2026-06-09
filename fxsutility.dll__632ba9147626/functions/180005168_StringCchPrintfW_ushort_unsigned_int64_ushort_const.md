# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005168`
- end: `0x1800051ec`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800052b0`
- `0x180006354`
- `0x180008828`
- `0x180008bcc`
- `0x18000dfe4`
- `0x18000f3e4`

## callees

- `0x180005168`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800051a7`
- `msvcrt!_vsnwprintf` at `0x1800051a7`

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
0x180005168  mov     [rsp+arg_10], r8
0x18000516d  mov     qword ptr [rsp+Args], r9
0x180005172  push    rbx
0x180005173  push    rdi
0x180005174  sub     rsp, 38h
0x180005178  mov     rax, rdx
0x18000517b  mov     rdi, rcx
0x18000517e  test    rdx, rdx
0x180005181  jz      short loc_1800051D4
0x180005183  cmp     rax, 7FFFFFFFh
0x180005189  jbe     short loc_180005192
0x18000518b  mov     edx, 80070057h
0x180005190  jmp     short loc_1800051DE
0x180005192  lea     rbx, [rdx-1]
0x180005196  mov     [rsp+48h+var_28], 0
0x18000519f  mov     rdx, rbx; BufferCount
0x1800051a2  lea     r9, [rsp+48h+Args]; Args
0x1800051a7  call    cs:__imp__vsnwprintf
0x1800051ad  test    eax, eax
0x1800051af  js      short loc_1800051C7
0x1800051b1  cdqe
0x1800051b3  cmp     rax, rbx
0x1800051b6  ja      short loc_1800051C7
0x1800051b8  xor     edx, edx
0x1800051ba  cmp     rax, rbx
0x1800051bd  jnz     short loc_1800051E3
0x1800051bf  xor     eax, eax
0x1800051c1  mov     [rdi+rbx*2], ax
0x1800051c5  jmp     short loc_1800051E3
0x1800051c7  xor     eax, eax
0x1800051c9  mov     edx, 8007007Ah
0x1800051ce  mov     [rdi+rbx*2], ax
0x1800051d2  jmp     short loc_1800051E3
0x1800051d4  mov     edx, 80070057h
0x1800051d9  test    rax, rax
0x1800051dc  jz      short loc_1800051E3
0x1800051de  xor     ecx, ecx
0x1800051e0  mov     [rdi], cx
0x1800051e3  mov     eax, edx
0x1800051e5  add     rsp, 38h
0x1800051e9  pop     rdi
0x1800051ea  pop     rbx
0x1800051eb  retn
```
