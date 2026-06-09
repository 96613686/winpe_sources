# C3DPrintShellExtension::SetParameters(ushort const *)

- ea: `0x180008c60`
- end: `0x180008c99`
- name: `?SetParameters@C3DPrintShellExtension@@UEAAJPEBG@Z`
- size: `57`
- prototype: `int(C3DPrintShellExtension *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008c60`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180008c75`
- `KERNEL32!OutputDebugStringW` at `0x180008c7e`
- `KERNEL32!OutputDebugStringW` at `0x180008c8b`
- `KERNEL32!OutputDebugStringW` at `0x180008c75`
- `KERNEL32!OutputDebugStringW` at `0x180008c7e`
- `KERNEL32!OutputDebugStringW` at `0x180008c8b`

## pseudocode

```c
__int64 __fastcall C3DPrintShellExtension::SetParameters(C3DPrintShellExtension *this, const unsigned __int16 *a2)
{
  if ( a2 )
  {
    OutputDebugStringW(L"parameters: ");
    OutputDebugStringW(a2);
    OutputDebugStringW(L"\r\n");
  }
  return 0;
}

```

## disassembly

```asm
0x180008c60  push    rbx
0x180008c62  sub     rsp, 20h
0x180008c66  mov     rbx, rdx
0x180008c69  test    rdx, rdx
0x180008c6c  jz      short loc_180008C91
0x180008c6e  lea     rcx, aParameters; "parameters: "
0x180008c75  call    cs:__imp_OutputDebugStringW
0x180008c7b  mov     rcx, rbx; lpOutputString
0x180008c7e  call    cs:__imp_OutputDebugStringW
0x180008c84  lea     rcx, asc_18000D37C; "\r\n"
0x180008c8b  call    cs:__imp_OutputDebugStringW
0x180008c91  xor     eax, eax
0x180008c93  add     rsp, 20h
0x180008c97  pop     rbx
0x180008c98  retn
```
