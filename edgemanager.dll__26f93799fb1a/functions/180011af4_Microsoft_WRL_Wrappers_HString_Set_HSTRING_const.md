# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x180011af4`
- end: `0x180011b3a`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011a10`
- `0x180011f08`
- `0x18004eda0`
- `0x18006afac`
- `0x180071674`

## callees

- `0x180011af4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180011b29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180011b29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011b16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011b16`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *newString, HSTRING *a2)
{
  HRESULT result; // eax

  if ( !*a2 || (result = 0, *a2 != *newString) )
  {
    WindowsDeleteString(*newString);
    *newString = 0;
    return WindowsDuplicateString(*a2, newString);
  }
  return result;
}

```

## disassembly

```asm
0x180011af4  mov     [rsp+arg_0], rbx
0x180011af9  push    rdi
0x180011afa  sub     rsp, 20h
0x180011afe  mov     rbx, rcx
0x180011b01  mov     rdi, rdx
0x180011b04  mov     rcx, [rdx]
0x180011b07  test    rcx, rcx
0x180011b0a  jz      short loc_180011B13
0x180011b0c  xor     eax, eax
0x180011b0e  cmp     rcx, [rbx]
0x180011b11  jz      short loc_180011B2F
0x180011b13  mov     rcx, [rbx]; string
0x180011b16  call    cs:__imp_WindowsDeleteString
0x180011b1c  mov     qword ptr [rbx], 0
0x180011b23  mov     rdx, rbx; newString
0x180011b26  mov     rcx, [rdi]; string
0x180011b29  call    cs:__imp_WindowsDuplicateString
0x180011b2f  mov     rbx, [rsp+28h+arg_0]
0x180011b34  add     rsp, 20h
0x180011b38  pop     rdi
0x180011b39  retn
```
