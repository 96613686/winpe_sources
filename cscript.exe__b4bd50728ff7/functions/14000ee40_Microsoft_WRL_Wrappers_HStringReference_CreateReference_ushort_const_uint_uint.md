# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x14000ee40`
- end: `0x14000ee76`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `54`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ec30`
- `0x14000ec9c`
- `0x14000f464`

## callees

- `0x14000ee40`
- `0x14000f44c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000ee5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000ee5f`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  HRESULT StringReference; // eax
  int v6; // edx
  unsigned int v7; // r8d

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v6, v7);
    JUMPOUT(0x14000EE75LL);
  }
}

```

## disassembly

```asm
0x14000ee40  sub     rsp, 28h
0x14000ee44  mov     eax, r9d
0x14000ee47  mov     r10, rdx
0x14000ee4a  cmp     r9d, r8d
0x14000ee4d  jb      short loc_14000EE53
0x14000ee4f  lea     eax, [r8-1]
0x14000ee53  lea     r9, [rcx+18h]; string
0x14000ee57  mov     r8, rcx; hstringHeader
0x14000ee5a  mov     rcx, r10; sourceString
0x14000ee5d  mov     edx, eax; length
0x14000ee5f  call    cs:__imp_WindowsCreateStringReference
0x14000ee65  test    eax, eax
0x14000ee67  js      short loc_14000EE6E
0x14000ee69  add     rsp, 28h
0x14000ee6d  retn
0x14000ee6e  mov     ecx, eax; this
0x14000ee70  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
