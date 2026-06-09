# CWMWriter::GetClassID(_GUID *)

- ea: `0x18000faa0`
- end: `0x18000fab6`
- name: `?GetClassID@CWMWriter@@UEAAJPEAU_GUID@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000fac0`

## callees

- `0x18000faa0`

## pseudocode

```c
__int64 __fastcall CWMWriter::GetClassID(CWMWriter *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = *(struct _GUID *)((char *)this + 40);
  return result;
}

```

## disassembly

```asm
0x18000faa0  test    rdx, rdx
0x18000faa3  jnz     short loc_18000FAAB
0x18000faa5  mov     eax, 80004003h
0x18000faaa  retn
0x18000faab  movups  xmm0, xmmword ptr [rcx+28h]
0x18000faaf  xor     eax, eax
0x18000fab1  movdqu  xmmword ptr [rdx], xmm0
0x18000fab5  retn
```
