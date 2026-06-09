# RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180015e60`
- end: `0x180015eda`
- name: `?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f90`
- `0x180015020`
- `0x1800154e0`
- `0x180016880`
- `0x180017eec`

## callees

- `0x180015e60`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180015e9d`
- `msvcrt!_vsnprintf` at `0x180015e9d`

## pseudocode

```c
__int64 RtlStringCchPrintfA(char *a1, unsigned __int64 a2, const char *a3, ...)
{
  __int64 result; // rax
  unsigned __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  if ( !a2 )
    return 3221225485LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = a2 - 1;
    v6 = _vsnprintf(a1, a2 - 1, a3, ArgList);
    if ( v6 < 0 || (v7 = v6, v6 > v5) )
    {
      a1[v5] = 0;
      return 2147483653LL;
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
    result = 3221225485LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015e60  mov     [rsp+arg_10], r8
0x180015e65  mov     qword ptr [rsp+ArgList], r9
0x180015e6a  push    rbx
0x180015e6b  push    rdi
0x180015e6c  sub     rsp, 38h
0x180015e70  mov     rdi, rcx
0x180015e73  test    rdx, rdx
0x180015e76  jz      short loc_180015EC6
0x180015e78  cmp     rdx, 7FFFFFFFh
0x180015e7f  jbe     short loc_180015E88
0x180015e81  mov     eax, 0C000000Dh
0x180015e86  jmp     short loc_180015ED0
0x180015e88  lea     rbx, [rdx-1]
0x180015e8c  mov     [rsp+48h+var_28], 0
0x180015e95  mov     rdx, rbx; BufferCount
0x180015e98  lea     r9, [rsp+48h+ArgList]; ArgList
0x180015e9d  call    cs:__imp__vsnprintf
0x180015ea3  test    eax, eax
0x180015ea5  js      short loc_180015EBB
0x180015ea7  movsxd  rcx, eax
0x180015eaa  cmp     rcx, rbx
0x180015ead  ja      short loc_180015EBB
0x180015eaf  xor     eax, eax
0x180015eb1  cmp     rcx, rbx
0x180015eb4  jnz     short loc_180015ED3
0x180015eb6  mov     [rbx+rdi], al
0x180015eb9  jmp     short loc_180015ED3
0x180015ebb  mov     byte ptr [rbx+rdi], 0
0x180015ebf  mov     eax, 80000005h
0x180015ec4  jmp     short loc_180015ED3
0x180015ec6  mov     eax, 0C000000Dh
0x180015ecb  test    rdx, rdx
0x180015ece  jz      short loc_180015ED3
0x180015ed0  mov     byte ptr [rcx], 0
0x180015ed3  add     rsp, 38h
0x180015ed7  pop     rdi
0x180015ed8  pop     rbx
0x180015ed9  retn
```
