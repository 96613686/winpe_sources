# VerifyThisIsAString(ushort const *,ulong)

- ea: `0x1800337bc`
- end: `0x1800337e5`
- name: `?VerifyThisIsAString@@YAJPEBGK@Z`
- size: `41`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800325d4`

## callees

- `0x18000b1f0`
- `0x1800337bc`

## string_xrefs

- `0x1800337cf`: `%s was not a string in the registry! It's type is %d.`

## pseudocode

```c
__int64 __fastcall VerifyThisIsAString(const unsigned __int16 *a1, unsigned int a2)
{
  if ( a2 == 1 )
    return 0;
  ReportAppCompatError((wchar_t *)L"%s was not a string in the registry! It's type is %d.", a1, a2);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800337bc  sub     rsp, 28h
0x1800337c0  cmp     edx, 1
0x1800337c3  jnz     short loc_1800337C9
0x1800337c5  xor     eax, eax
0x1800337c7  jmp     short loc_1800337E0
0x1800337c9  mov     r8d, edx
0x1800337cc  mov     rdx, rcx
0x1800337cf  lea     rcx, aSWasNotAString; "%s was not a string in the registry! It"...
0x1800337d6  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x1800337db  mov     eax, 80004005h
0x1800337e0  add     rsp, 28h
0x1800337e4  retn
```
