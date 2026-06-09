# StringCchCopyWrapW

- ea: `0x1800090f4`
- end: `0x180009140`
- name: `StringCchCopyWrapW`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016e0`
- `0x1800088b8`

## callees

- `0x180008c5c`
- `0x1800090f4`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180009132`
- `rtutils!TracePrintfExA` at `0x180009132`

## string_xrefs

- `0x180009126`: `StringCchCopy failed due to error 0x%x`

## pseudocode

```c
__int64 __fastcall StringCchCopyWrapW(wchar_t *a1, size_t a2, const wchar_t *a3)
{
  unsigned int v3; // ebx
  HRESULT v4; // eax

  v3 = 0;
  v4 = StringCchCopyExW(a1, a2, a3, 0, 0, 0x900u);
  if ( v4 < 0 )
  {
    v3 = (unsigned __int16)v4;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v4);
  }
  return v3;
}

```

## disassembly

```asm
0x1800090f4  push    rbx
0x1800090f6  sub     rsp, 30h
0x1800090fa  xor     ebx, ebx
0x1800090fc  mov     [rsp+38h+dwFlags], 900h; dwFlags
0x180009104  xor     r9d, r9d; ppszDestEnd
0x180009107  mov     [rsp+38h+pcchRemaining], rbx; pcchRemaining
0x18000910c  call    StringCchCopyExW
0x180009111  test    eax, eax
0x180009113  jns     short loc_180009138
0x180009115  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000911b  movzx   ebx, ax
0x18000911e  cmp     ecx, 0FFFFFFFFh
0x180009121  jz      short loc_180009138
0x180009123  mov     r9d, eax
0x180009126  lea     r8, aStringcchcopyF; "StringCchCopy failed due to error 0x%x"
0x18000912d  mov     edx, 0Ch; dwFlags
0x180009132  call    cs:__imp_TracePrintfExA
0x180009138  mov     eax, ebx
0x18000913a  add     rsp, 30h
0x18000913e  pop     rbx
0x18000913f  retn
```
