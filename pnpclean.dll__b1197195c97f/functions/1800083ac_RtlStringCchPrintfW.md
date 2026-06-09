# RtlStringCchPrintfW

- ea: `0x1800083ac`
- end: `0x180008430`
- name: `RtlStringCchPrintfW`
- size: `132`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c00`
- `0x180008438`

## callees

- `0x1800083ac`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800083eb`
- `msvcrt!_vsnwprintf` at `0x1800083eb`

## pseudocode

```c
__int64 RtlStringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
        v4 = -2147483643;
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
      v4 = -1073741811;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x1800083ac  mov     [rsp+arg_10], r8
0x1800083b1  mov     qword ptr [rsp+Args], r9
0x1800083b6  push    rbx
0x1800083b7  push    rdi
0x1800083b8  sub     rsp, 38h
0x1800083bc  mov     rax, rdx
0x1800083bf  mov     rdi, rcx
0x1800083c2  test    rdx, rdx
0x1800083c5  jz      short loc_180008418
0x1800083c7  cmp     rax, 7FFFFFFFh
0x1800083cd  jbe     short loc_1800083D6
0x1800083cf  mov     edx, 0C000000Dh
0x1800083d4  jmp     short loc_180008422
0x1800083d6  lea     rbx, [rdx-1]
0x1800083da  mov     [rsp+48h+var_28], 0
0x1800083e3  mov     rdx, rbx; BufferCount
0x1800083e6  lea     r9, [rsp+48h+Args]; Args
0x1800083eb  call    cs:__imp__vsnwprintf
0x1800083f1  test    eax, eax
0x1800083f3  js      short loc_18000840B
0x1800083f5  cdqe
0x1800083f7  cmp     rax, rbx
0x1800083fa  ja      short loc_18000840B
0x1800083fc  xor     edx, edx
0x1800083fe  cmp     rax, rbx
0x180008401  jnz     short loc_180008427
0x180008403  xor     eax, eax
0x180008405  mov     [rdi+rbx*2], ax
0x180008409  jmp     short loc_180008427
0x18000840b  xor     eax, eax
0x18000840d  mov     edx, 80000005h
0x180008412  mov     [rdi+rbx*2], ax
0x180008416  jmp     short loc_180008427
0x180008418  mov     edx, 0C000000Dh
0x18000841d  test    rax, rax
0x180008420  jz      short loc_180008427
0x180008422  xor     ecx, ecx
0x180008424  mov     [rdi], cx
0x180008427  mov     eax, edx
0x180008429  add     rsp, 38h
0x18000842d  pop     rdi
0x18000842e  pop     rbx
0x18000842f  retn
```
