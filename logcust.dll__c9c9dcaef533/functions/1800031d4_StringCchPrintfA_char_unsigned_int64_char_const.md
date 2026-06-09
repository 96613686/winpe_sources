# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x1800031d4`
- end: `0x18000324e`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002844`

## callees

- `0x1800031d4`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180003211`
- `msvcrt!_vsnprintf` at `0x180003211`

## pseudocode

```c
__int64 StringCchPrintfA(char *a1, unsigned __int64 a2, const char *a3, ...)
{
  __int64 result; // rax
  unsigned __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = a2 - 1;
    v6 = _vsnprintf(a1, a2 - 1, a3, ArgList);
    if ( v6 < 0 || (v7 = v6, v6 > v5) )
    {
      a1[v5] = 0;
      return 2147942522LL;
    }
    else
    {
      result = 0;
      if ( v7 == v5 )
        a1[v5] = 0;
    }
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800031d4  mov     [rsp+arg_10], r8
0x1800031d9  mov     qword ptr [rsp+ArgList], r9
0x1800031de  push    rbx
0x1800031df  push    rdi
0x1800031e0  sub     rsp, 38h
0x1800031e4  mov     rdi, rcx
0x1800031e7  test    rdx, rdx
0x1800031ea  jz      short loc_18000323A
0x1800031ec  cmp     rdx, 7FFFFFFFh
0x1800031f3  jbe     short loc_1800031FC
0x1800031f5  mov     eax, 80070057h
0x1800031fa  jmp     short loc_180003244
0x1800031fc  lea     rbx, [rdx-1]
0x180003200  mov     [rsp+48h+var_28], 0
0x180003209  mov     rdx, rbx; BufferCount
0x18000320c  lea     r9, [rsp+48h+ArgList]; ArgList
0x180003211  call    cs:__imp__vsnprintf
0x180003217  test    eax, eax
0x180003219  js      short loc_18000322F
0x18000321b  movsxd  rcx, eax
0x18000321e  cmp     rcx, rbx
0x180003221  ja      short loc_18000322F
0x180003223  xor     eax, eax
0x180003225  cmp     rcx, rbx
0x180003228  jnz     short loc_180003247
0x18000322a  mov     [rbx+rdi], al
0x18000322d  jmp     short loc_180003247
0x18000322f  mov     byte ptr [rbx+rdi], 0
0x180003233  mov     eax, 8007007Ah
0x180003238  jmp     short loc_180003247
0x18000323a  mov     eax, 80070057h
0x18000323f  test    rdx, rdx
0x180003242  jz      short loc_180003247
0x180003244  mov     byte ptr [rcx], 0
0x180003247  add     rsp, 38h
0x18000324b  pop     rdi
0x18000324c  pop     rbx
0x18000324d  retn
```
