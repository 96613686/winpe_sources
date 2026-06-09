# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180009894`
- end: `0x1800098ca`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `54`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800073fc`
- `0x18000e11c`
- `0x18000f0f4`

## callees

- `0x180009894`
- `0x18000c470`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800098b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800098b3`

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
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180009894  sub     rsp, 28h
0x180009898  mov     eax, r9d
0x18000989b  mov     r10, rdx
0x18000989e  cmp     r9d, r8d
0x1800098a1  jb      short loc_1800098A7
0x1800098a3  lea     eax, [r8-1]
0x1800098a7  lea     r9, [rcx+18h]; string
0x1800098ab  mov     r8, rcx; hstringHeader
0x1800098ae  mov     rcx, r10; sourceString
0x1800098b1  mov     edx, eax; length
0x1800098b3  call    cs:__imp_WindowsCreateStringReference
0x1800098b9  test    eax, eax
0x1800098bb  jns     short loc_1800098C5
0x1800098bd  mov     ecx, eax; this
0x1800098bf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800098c4  int     3; Trap to Debugger
0x1800098c5  add     rsp, 28h
0x1800098c9  retn
```
