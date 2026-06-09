# StringCchCopyNWrapW

- ea: `0x18002c2d4`
- end: `0x18002c310`
- name: `StringCchCopyNWrapW`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c850`

## callees

- `0x18002c1ec`
- `0x18002c2d4`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18002c302`
- `rtutils!TracePrintfExA` at `0x18002c302`

## string_xrefs

- `0x18002c2f6`: `StringCchCopyN failed due to error 0x%x`

## pseudocode

```c
__int64 __fastcall StringCchCopyNWrapW(wchar_t *a1, size_t a2, const wchar_t *a3, size_t a4)
{
  unsigned int v4; // ebx
  HRESULT v5; // eax
  STRSAFE_LPWSTR *v7; // [rsp+20h] [rbp-28h]
  size_t *v8; // [rsp+28h] [rbp-20h]
  DWORD v9; // [rsp+30h] [rbp-18h]

  v4 = 0;
  v5 = StringCchCopyNExW(a1, a2, a3, a4, v7, v8, v9);
  if ( v5 < 0 )
  {
    v4 = (unsigned __int16)v5;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopyN failed due to error 0x%x", v5);
  }
  return v4;
}

```

## disassembly

```asm
0x18002c2d4  push    rbx
0x18002c2d6  sub     rsp, 40h
0x18002c2da  xor     ebx, ebx
0x18002c2dc  call    StringCchCopyNExW
0x18002c2e1  test    eax, eax
0x18002c2e3  jns     short loc_18002C308
0x18002c2e5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002c2eb  movzx   ebx, ax
0x18002c2ee  cmp     ecx, 0FFFFFFFFh
0x18002c2f1  jz      short loc_18002C308
0x18002c2f3  mov     r9d, eax
0x18002c2f6  lea     r8, aStringcchcopyn; "StringCchCopyN failed due to error 0x%x"
0x18002c2fd  mov     edx, 0Ch; dwFlags
0x18002c302  call    cs:__imp_TracePrintfExA
0x18002c308  mov     eax, ebx
0x18002c30a  add     rsp, 40h
0x18002c30e  pop     rbx
0x18002c30f  retn
```
