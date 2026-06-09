# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180005464`
- end: `0x1800054de`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800040ec`

## callees

- `0x180005464`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x1800054a1`
- `msvcrt!_vsnprintf` at `0x1800054a1`

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
0x180005464  mov     [rsp+arg_10], r8
0x180005469  mov     qword ptr [rsp+ArgList], r9
0x18000546e  push    rbx
0x18000546f  push    rdi
0x180005470  sub     rsp, 38h
0x180005474  mov     rdi, rcx
0x180005477  test    rdx, rdx
0x18000547a  jz      short loc_1800054CA
0x18000547c  cmp     rdx, 7FFFFFFFh
0x180005483  jbe     short loc_18000548C
0x180005485  mov     eax, 80070057h
0x18000548a  jmp     short loc_1800054D4
0x18000548c  lea     rbx, [rdx-1]
0x180005490  mov     [rsp+48h+var_28], 0
0x180005499  mov     rdx, rbx; BufferCount
0x18000549c  lea     r9, [rsp+48h+ArgList]; ArgList
0x1800054a1  call    cs:__imp__vsnprintf
0x1800054a7  test    eax, eax
0x1800054a9  js      short loc_1800054BF
0x1800054ab  movsxd  rcx, eax
0x1800054ae  cmp     rcx, rbx
0x1800054b1  ja      short loc_1800054BF
0x1800054b3  xor     eax, eax
0x1800054b5  cmp     rcx, rbx
0x1800054b8  jnz     short loc_1800054D7
0x1800054ba  mov     [rbx+rdi], al
0x1800054bd  jmp     short loc_1800054D7
0x1800054bf  mov     byte ptr [rbx+rdi], 0
0x1800054c3  mov     eax, 8007007Ah
0x1800054c8  jmp     short loc_1800054D7
0x1800054ca  mov     eax, 80070057h
0x1800054cf  test    rdx, rdx
0x1800054d2  jz      short loc_1800054D7
0x1800054d4  mov     byte ptr [rcx], 0
0x1800054d7  add     rsp, 38h
0x1800054db  pop     rdi
0x1800054dc  pop     rbx
0x1800054dd  retn
```
