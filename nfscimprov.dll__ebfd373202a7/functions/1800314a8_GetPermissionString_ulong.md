# GetPermissionString(ulong)

- ea: `0x1800314a8`
- end: `0x1800314d3`
- name: `?GetPermissionString@@YAPEAGK@Z`
- size: `43`
- prototype: `unsigned __int16 *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a668`

## callees

- `0x1800314a8`

## string_xrefs

- `0x1800314ad`: `no-access`
- `0x1800314ba`: `readonly`
- `0x1800314c4`: `readwrite`

## pseudocode

```c
unsigned __int16 *__fastcall GetPermissionString(int a1)
{
  unsigned __int16 *result; // rax

  if ( a1 == 1 )
    return L"no-access";
  if ( a1 == 2 )
    return L"readonly";
  result = 0;
  if ( a1 == 4 )
    return L"readwrite";
  return result;
}

```

## disassembly

```asm
0x1800314a8  cmp     ecx, 1
0x1800314ab  jnz     short loc_1800314B5
0x1800314ad  lea     rax, aNoAccess; "no-access"
0x1800314b4  retn
0x1800314b5  cmp     ecx, 2
0x1800314b8  jnz     short loc_1800314C2
0x1800314ba  lea     rax, aReadonly_0; "readonly"
0x1800314c1  retn
0x1800314c2  xor     eax, eax
0x1800314c4  lea     rdx, aReadwrite_0; "readwrite"
0x1800314cb  cmp     ecx, 4
0x1800314ce  cmovz   rax, rdx
0x1800314d2  retn
```
