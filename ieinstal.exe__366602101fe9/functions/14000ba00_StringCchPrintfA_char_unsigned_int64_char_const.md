# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x14000ba00`
- end: `0x14000ba81`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `129`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a6b8`
- `0x14000a798`
- `0x14000abd4`

## callees

- `0x14000ba00`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x14000ba3d`
- `msvcrt!_vsnprintf` at `0x14000ba3d`

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
0x14000ba00  mov     [rsp+arg_10], r8
0x14000ba05  mov     qword ptr [rsp+ArgList], r9
0x14000ba0a  push    rbx
0x14000ba0b  push    rdi
0x14000ba0c  sub     rsp, 38h
0x14000ba10  mov     rdi, rcx
0x14000ba13  test    rdx, rdx
0x14000ba16  jz      short loc_14000BA6C
0x14000ba18  cmp     rdx, 7FFFFFFFh
0x14000ba1f  jbe     short loc_14000BA28
0x14000ba21  mov     eax, 80070057h
0x14000ba26  jmp     short loc_14000BA76
0x14000ba28  lea     rbx, [rdx-1]
0x14000ba2c  mov     [rsp+48h+var_28], 0
0x14000ba35  mov     rdx, rbx; BufferCount
0x14000ba38  lea     r9, [rsp+48h+ArgList]; ArgList
0x14000ba3d  call    cs:__imp__vsnprintf
0x14000ba44  nop     dword ptr [rax+rax+00h]
0x14000ba49  test    eax, eax
0x14000ba4b  js      short loc_14000BA61
0x14000ba4d  movsxd  rcx, eax
0x14000ba50  cmp     rcx, rbx
0x14000ba53  ja      short loc_14000BA61
0x14000ba55  xor     eax, eax
0x14000ba57  cmp     rcx, rbx
0x14000ba5a  jnz     short loc_14000BA79
0x14000ba5c  mov     [rbx+rdi], al
0x14000ba5f  jmp     short loc_14000BA79
0x14000ba61  mov     byte ptr [rbx+rdi], 0
0x14000ba65  mov     eax, 8007007Ah
0x14000ba6a  jmp     short loc_14000BA79
0x14000ba6c  mov     eax, 80070057h
0x14000ba71  test    rdx, rdx
0x14000ba74  jz      short loc_14000BA79
0x14000ba76  mov     byte ptr [rcx], 0
0x14000ba79  add     rsp, 38h
0x14000ba7d  pop     rdi
0x14000ba7e  pop     rbx
0x14000ba7f  retn
```
