# StringCchCopyWrapW

- ea: `0x18002c318`
- end: `0x18002c35c`
- name: `StringCchCopyWrapW`
- size: `68`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18002049c`
- `0x1800245f8`
- `0x180024b60`
- `0x180026cb0`
- `0x1800274f0`
- `0x180027b6c`
- `0x18002c850`

## callees

- `0x180021c04`
- `0x18002c318`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18002c34e`
- `rtutils!TracePrintfExA` at `0x18002c34e`

## string_xrefs

- `0x18002c342`: `StringCchCopy failed due to error 0x%x`

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
0x18002c318  push    rbx
0x18002c31a  sub     rsp, 30h
0x18002c31e  xor     ebx, ebx
0x18002c320  mov     [rsp+38h+dwFlags], 900h; dwFlags
0x18002c328  call    StringCchCopyExW
0x18002c32d  test    eax, eax
0x18002c32f  jns     short loc_18002C354
0x18002c331  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002c337  movzx   ebx, ax
0x18002c33a  cmp     ecx, 0FFFFFFFFh
0x18002c33d  jz      short loc_18002C354
0x18002c33f  mov     r9d, eax
0x18002c342  lea     r8, aStringcchcopyF; "StringCchCopy failed due to error 0x%x"
0x18002c349  mov     edx, 0Ch; dwFlags
0x18002c34e  call    cs:__imp_TracePrintfExA
0x18002c354  mov     eax, ebx
0x18002c356  add     rsp, 30h
0x18002c35a  pop     rbx
0x18002c35b  retn
```
