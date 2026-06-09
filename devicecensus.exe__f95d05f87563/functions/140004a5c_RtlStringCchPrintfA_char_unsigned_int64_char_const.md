# RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x140004a5c`
- end: `0x140004ad6`
- name: `?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002db0`
- `0x1400042c0`
- `0x140004780`
- `0x1400050a0`
- `0x140006ef4`

## callees

- `0x140004a5c`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x140004a99`
- `msvcrt!_vsnprintf` at `0x140004a99`

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
0x140004a5c  mov     [rsp+arg_10], r8
0x140004a61  mov     qword ptr [rsp+ArgList], r9
0x140004a66  push    rbx
0x140004a67  push    rdi
0x140004a68  sub     rsp, 38h
0x140004a6c  mov     rdi, rcx
0x140004a6f  test    rdx, rdx
0x140004a72  jz      short loc_140004AC2
0x140004a74  cmp     rdx, 7FFFFFFFh
0x140004a7b  jbe     short loc_140004A84
0x140004a7d  mov     eax, 0C000000Dh
0x140004a82  jmp     short loc_140004ACC
0x140004a84  lea     rbx, [rdx-1]
0x140004a88  mov     [rsp+48h+var_28], 0
0x140004a91  mov     rdx, rbx; BufferCount
0x140004a94  lea     r9, [rsp+48h+ArgList]; ArgList
0x140004a99  call    cs:__imp__vsnprintf
0x140004a9f  test    eax, eax
0x140004aa1  js      short loc_140004AB7
0x140004aa3  movsxd  rcx, eax
0x140004aa6  cmp     rcx, rbx
0x140004aa9  ja      short loc_140004AB7
0x140004aab  xor     eax, eax
0x140004aad  cmp     rcx, rbx
0x140004ab0  jnz     short loc_140004ACF
0x140004ab2  mov     [rbx+rdi], al
0x140004ab5  jmp     short loc_140004ACF
0x140004ab7  mov     byte ptr [rbx+rdi], 0
0x140004abb  mov     eax, 80000005h
0x140004ac0  jmp     short loc_140004ACF
0x140004ac2  mov     eax, 0C000000Dh
0x140004ac7  test    rdx, rdx
0x140004aca  jz      short loc_140004ACF
0x140004acc  mov     byte ptr [rcx], 0
0x140004acf  add     rsp, 38h
0x140004ad3  pop     rdi
0x140004ad4  pop     rbx
0x140004ad5  retn
```
