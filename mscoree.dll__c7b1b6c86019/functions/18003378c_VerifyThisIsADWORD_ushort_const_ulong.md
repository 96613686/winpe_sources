# VerifyThisIsADWORD(ushort const *,ulong)

- ea: `0x18003378c`
- end: `0x1800337b5`
- name: `?VerifyThisIsADWORD@@YAJPEBGK@Z`
- size: `41`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800325d4`

## callees

- `0x18000b1f0`
- `0x18003378c`

## string_xrefs

- `0x18003379f`: `%s was not a DWORD in the registry! It's type is %d.`

## pseudocode

```c
__int64 __fastcall VerifyThisIsADWORD(const unsigned __int16 *a1, unsigned int a2)
{
  if ( a2 == 4 )
    return 0;
  ReportAppCompatError((wchar_t *)L"%s was not a DWORD in the registry! It's type is %d.", a1, a2);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18003378c  sub     rsp, 28h
0x180033790  cmp     edx, 4
0x180033793  jnz     short loc_180033799
0x180033795  xor     eax, eax
0x180033797  jmp     short loc_1800337B0
0x180033799  mov     r8d, edx
0x18003379c  mov     rdx, rcx
0x18003379f  lea     rcx, aSWasNotADwordI; "%s was not a DWORD in the registry! It'"...
0x1800337a6  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x1800337ab  mov     eax, 80004005h
0x1800337b0  add     rsp, 28h
0x1800337b4  retn
```
