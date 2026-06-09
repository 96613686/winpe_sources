# StringCchCopyWrapW

- ea: `0x180026f3c`
- end: `0x180026f87`
- name: `StringCchCopyWrapW`
- size: `75`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180024290`
- `0x180025bf8`
- `0x1800263d4`
- `0x180026884`
- `0x180026dd8`

## callees

- `0x180026058`
- `0x180026f3c`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180026f72`
- `rtutils!TracePrintfExA` at `0x180026f72`

## string_xrefs

- `0x180026f66`: `StringCchCopy failed due to error 0x%x`

## pseudocode

```c
__int64 __fastcall StringCchCopyWrapW(wchar_t *a1, size_t a2, const wchar_t *a3, STRSAFE_LPWSTR *a4)
{
  unsigned int v4; // ebx
  HRESULT v5; // eax
  size_t *v7; // [rsp+20h] [rbp-18h]

  v4 = 0;
  v5 = StringCchCopyExW(a1, a2, a3, a4, v7, 0x900u);
  if ( v5 < 0 )
  {
    v4 = (unsigned __int16)v5;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180026f3c  push    rbx
0x180026f3e  sub     rsp, 30h
0x180026f42  xor     ebx, ebx
0x180026f44  mov     [rsp+38h+dwFlags], 900h; dwFlags
0x180026f4c  call    StringCchCopyExW
0x180026f51  test    eax, eax
0x180026f53  jns     short loc_180026F7E
0x180026f55  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180026f5b  movzx   ebx, ax
0x180026f5e  cmp     ecx, 0FFFFFFFFh
0x180026f61  jz      short loc_180026F7E
0x180026f63  mov     r9d, eax
0x180026f66  lea     r8, aStringcchcopyF; "StringCchCopy failed due to error 0x%x"
0x180026f6d  mov     edx, 0Ch; dwFlags
0x180026f72  call    cs:__imp_TracePrintfExA
0x180026f79  nop     dword ptr [rax+rax+00h]
0x180026f7e  mov     eax, ebx
0x180026f80  add     rsp, 30h
0x180026f84  pop     rbx
0x180026f85  retn
```
