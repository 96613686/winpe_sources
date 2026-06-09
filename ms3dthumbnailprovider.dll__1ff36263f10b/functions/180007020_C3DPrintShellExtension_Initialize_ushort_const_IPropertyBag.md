# C3DPrintShellExtension::Initialize(ushort const *,IPropertyBag *)

- ea: `0x180007020`
- end: `0x180007054`
- name: `?Initialize@C3DPrintShellExtension@@UEAAJPEBGPEAUIPropertyBag@@@Z`
- size: `52`
- prototype: `int(C3DPrintShellExtension *__hidden this, const unsigned __int16 *, struct IPropertyBag *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180007030`
- `KERNEL32!OutputDebugStringW` at `0x180007039`
- `KERNEL32!OutputDebugStringW` at `0x180007046`
- `KERNEL32!OutputDebugStringW` at `0x180007030`
- `KERNEL32!OutputDebugStringW` at `0x180007039`
- `KERNEL32!OutputDebugStringW` at `0x180007046`

## string_xrefs

- `0x180007026`: `Command: `

## pseudocode

```c
__int64 __fastcall C3DPrintShellExtension::Initialize(
        C3DPrintShellExtension *this,
        const unsigned __int16 *a2,
        struct IPropertyBag *a3)
{
  OutputDebugStringW(L"Command: ");
  OutputDebugStringW(a2);
  OutputDebugStringW(L"\r\n");
  return 0;
}

```

## disassembly

```asm
0x180007020  push    rbx
0x180007022  sub     rsp, 20h
0x180007026  lea     rcx, OutputString; "Command: "
0x18000702d  mov     rbx, rdx
0x180007030  call    cs:__imp_OutputDebugStringW
0x180007036  mov     rcx, rbx; lpOutputString
0x180007039  call    cs:__imp_OutputDebugStringW
0x18000703f  lea     rcx, asc_18000D37C; "\r\n"
0x180007046  call    cs:__imp_OutputDebugStringW
0x18000704c  xor     eax, eax
0x18000704e  add     rsp, 20h
0x180007052  pop     rbx
0x180007053  retn
```
