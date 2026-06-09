# DlnaUrlHelpers::IsDlnaPlaySingleUrl(HSTRING__ *)

- ea: `0x18000a4d0`
- end: `0x18000a521`
- name: `?IsDlnaPlaySingleUrl@DlnaUrlHelpers@@YA_NPEAUHSTRING__@@@Z`
- size: `81`
- prototype: `bool __fastcall(DlnaUrlHelpers *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010af0`

## callees

- `0x18000a4d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a509`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a4e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a4e1`

## pseudocode

```c
bool __fastcall DlnaUrlHelpers::IsDlnaPlaySingleUrl(DlnaUrlHelpers *this, HSTRING a2)
{
  const WCHAR *StringRawBuffer; // rax
  UINT32 length; // [rsp+48h] [rbp+10h] BYREF

  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)this, &length);
  return length > 0x10 && CompareStringOrdinal(StringRawBuffer, 16, L"dlna-playsingle:", 16, 1) == 2;
}

```

## disassembly

```asm
0x18000a4d0  sub     rsp, 38h
0x18000a4d4  lea     rdx, [rsp+38h+length]; length
0x18000a4d9  mov     [rsp+38h+length], 0
0x18000a4e1  call    cs:__imp_WindowsGetStringRawBuffer
0x18000a4e7  cmp     [rsp+38h+length], 10h
0x18000a4ec  jbe     short loc_18000A51A
0x18000a4ee  mov     r9d, 10h; cchCount2
0x18000a4f4  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000a4fc  mov     edx, r9d; cchCount1
0x18000a4ff  lea     r8, String2; "dlna-playsingle:"
0x18000a506  mov     rcx, rax; lpString1
0x18000a509  call    cs:__imp_CompareStringOrdinal
0x18000a50f  cmp     eax, 2
0x18000a512  setz    al
0x18000a515  add     rsp, 38h
0x18000a519  retn
0x18000a51a  xor     al, al
0x18000a51c  add     rsp, 38h
0x18000a520  retn
```
