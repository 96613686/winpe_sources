# GetFormatString(uint,ushort *)

- ea: `0x18000f6e4`
- end: `0x18000f73d`
- name: `?GetFormatString@@YAXIPEAG@Z`
- size: `89`
- prototype: `void __fastcall(UINT, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e6fc`
- `0x18000e828`
- `0x18000ea1c`
- `0x18000eb18`
- `0x18000eb9c`
- `0x18000ec8c`

## callees

- `0x18000f6e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f736`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f711`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f711`

## string_xrefs

- `0x18000f70a`: `comres.dll`

## pseudocode

```c
void __fastcall GetFormatString(UINT a1, unsigned __int16 *a2)
{
  HMODULE Library; // rax

  *a2 = 0;
  Library = g_hModCOMRes;
  if ( !g_hModCOMRes )
  {
    Library = LoadLibraryExW(L"comres.dll", 0, 2u);
    g_hModCOMRes = Library;
  }
  LoadStringW(Library, a1, a2, 128);
}

```

## disassembly

```asm
0x18000f6e4  mov     [rsp+arg_0], rbx
0x18000f6e9  push    rdi
0x18000f6ea  sub     rsp, 20h
0x18000f6ee  xor     eax, eax
0x18000f6f0  mov     rbx, rdx
0x18000f6f3  mov     [rdx], ax
0x18000f6f6  mov     edi, ecx
0x18000f6f8  mov     rax, cs:?g_hModCOMRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModCOMRes
0x18000f6ff  test    rax, rax
0x18000f702  jnz     short loc_18000F71E
0x18000f704  xor     edx, edx; hFile
0x18000f706  lea     r8d, [rax+2]; dwFlags
0x18000f70a  lea     rcx, aComresDll; "comres.dll"
0x18000f711  call    cs:__imp_LoadLibraryExW
0x18000f717  mov     cs:?g_hModCOMRes@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hModCOMRes
0x18000f71e  mov     r9d, 80h
0x18000f724  mov     r8, rbx
0x18000f727  mov     edx, edi
0x18000f729  mov     rcx, rax
0x18000f72c  mov     rbx, [rsp+28h+arg_0]
0x18000f731  add     rsp, 20h
0x18000f735  pop     rdi
0x18000f736  jmp     cs:__imp_LoadStringW
```
