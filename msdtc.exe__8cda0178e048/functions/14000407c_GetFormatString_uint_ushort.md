# GetFormatString(uint,ushort *)

- ea: `0x14000407c`
- end: `0x1400040d5`
- name: `?GetFormatString@@YAXIPEAG@Z`
- size: `89`
- prototype: `void __fastcall(UINT, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003094`
- `0x1400031c0`
- `0x1400033b4`
- `0x1400034b0`
- `0x140003534`
- `0x140003624`

## callees

- `0x14000407c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400040ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400040a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400040a9`

## string_xrefs

- `0x1400040a2`: `comres.dll`

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
0x14000407c  mov     [rsp+arg_0], rbx
0x140004081  push    rdi
0x140004082  sub     rsp, 20h
0x140004086  xor     eax, eax
0x140004088  mov     rbx, rdx
0x14000408b  mov     [rdx], ax
0x14000408e  mov     edi, ecx
0x140004090  mov     rax, cs:?g_hModCOMRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModCOMRes
0x140004097  test    rax, rax
0x14000409a  jnz     short loc_1400040B6
0x14000409c  xor     edx, edx; hFile
0x14000409e  lea     r8d, [rax+2]; dwFlags
0x1400040a2  lea     rcx, aComresDll; "comres.dll"
0x1400040a9  call    cs:__imp_LoadLibraryExW
0x1400040af  mov     cs:?g_hModCOMRes@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hModCOMRes
0x1400040b6  mov     r9d, 80h
0x1400040bc  mov     r8, rbx
0x1400040bf  mov     edx, edi
0x1400040c1  mov     rcx, rax
0x1400040c4  mov     rbx, [rsp+28h+arg_0]
0x1400040c9  add     rsp, 20h
0x1400040cd  pop     rdi
0x1400040ce  jmp     cs:__imp_LoadStringW
```
