# CHtmlIFilter::GetClassID(_GUID *)

- ea: `0x18001db20`
- end: `0x18001db2e`
- name: `?GetClassID@CHtmlIFilter@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CHtmlIFilter *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001db40`

## pseudocode

```c
__int64 __fastcall CHtmlIFilter::GetClassID(CHtmlIFilter *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_HtmlIFilter;
  return result;
}

```

## disassembly

```asm
0x18001db20  movups  xmm0, xmmword ptr cs:CLSID_HtmlIFilter.Data1
0x18001db27  xor     eax, eax
0x18001db29  movdqu  xmmword ptr [rdx], xmm0
0x18001db2d  retn
```
