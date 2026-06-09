# CMediaWrapperFilter::GetClassID(_GUID *)

- ea: `0x180016a60`
- end: `0x180016a79`
- name: `?GetClassID@CMediaWrapperFilter@@UEAAJPEAU_GUID@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(CMediaWrapperFilter *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016a80`

## callees

- `0x180016a60`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::GetClassID(CMediaWrapperFilter *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = CLSID_DMOWrapperFilter;
  return result;
}

```

## disassembly

```asm
0x180016a60  test    rdx, rdx
0x180016a63  jnz     short loc_180016A6B
0x180016a65  mov     eax, 80004003h
0x180016a6a  retn
0x180016a6b  movups  xmm0, xmmword ptr cs:CLSID_DMOWrapperFilter.Data1
0x180016a72  xor     eax, eax
0x180016a74  movdqu  xmmword ptr [rdx], xmm0
0x180016a78  retn
```
