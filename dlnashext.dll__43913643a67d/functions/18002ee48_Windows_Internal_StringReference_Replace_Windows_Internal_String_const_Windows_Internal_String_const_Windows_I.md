# Windows::Internal::StringReference::Replace(Windows::Internal::String const &,Windows::Internal::String const &,Windows::Internal::String *)

- ea: `0x18002ee48`
- end: `0x18002ee83`
- name: `?Replace@StringReference@Internal@Windows@@QEBAJAEBVString@23@0PEAV423@@Z`
- size: `59`
- prototype: `int(Windows::Internal::StringReference *__hidden this, const struct Windows::Internal::String *, const struct Windows::Internal::String *, struct Windows::Internal::String *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c844`
- `0x18002f378`

## callees

- `0x18001b3b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsReplaceString` at `0x18002ee68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsReplaceString` at `0x18002ee68`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StringReference::Replace(HSTRING *this, HSTRING *a2, HSTRING *a3, HSTRING *a4)
{
  HSTRING v4; // r8
  HSTRING v6; // rdx
  HSTRING v7; // rcx
  HRESULT v8; // eax
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  v4 = *a3;
  v6 = *a2;
  v7 = *this;
  newString = 0;
  v8 = WindowsReplaceString(v7, v6, v4, &newString);
  return Windows::Internal::String::FreeAndAssignOnSuccess(v8, newString, a4);
}

```

## disassembly

```asm
0x18002ee48  push    rbx
0x18002ee4a  sub     rsp, 20h
0x18002ee4e  mov     r8, [r8]; stringReplaceWith
0x18002ee51  mov     rbx, r9
0x18002ee54  mov     rdx, [rdx]; stringReplaced
0x18002ee57  lea     r9, [rsp+28h+newString]; newString
0x18002ee5c  mov     rcx, [rcx]; string
0x18002ee5f  mov     [rsp+28h+newString], 0
0x18002ee68  call    cs:__imp_WindowsReplaceString
0x18002ee6e  mov     rdx, [rsp+28h+newString]; HSTRING
0x18002ee73  mov     r8, rbx; HSTRING *
0x18002ee76  mov     ecx, eax; int
0x18002ee78  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18002ee7d  add     rsp, 20h
0x18002ee81  pop     rbx
0x18002ee82  retn
```
