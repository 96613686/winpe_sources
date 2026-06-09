# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005290`
- end: `0x18000530d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005290`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800052f0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800052f0`

## string_xrefs

- `0x1800052b3`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  FormatMessageW(0x1A00u, ModuleHandleW, dwMessageId, 0x400u, lpBuffer, nSize, 0);
}

```

## disassembly

```asm
0x180005290  mov     [rsp+arg_0], rbx
0x180005295  mov     [rsp+arg_8], rsi
0x18000529a  push    rdi
0x18000529b  sub     rsp, 40h
0x18000529f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800052a6  mov     ebx, r8d
0x1800052a9  mov     rdi, rdx
0x1800052ac  mov     esi, ecx
0x1800052ae  test    rax, rax
0x1800052b1  jnz     short loc_1800052CD
0x1800052b3  lea     rcx, ModuleName; "ntdll.dll"
0x1800052ba  call    cs:__imp_GetModuleHandleW
0x1800052c1  nop     dword ptr [rax+rax+00h]
0x1800052c6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800052cd  mov     [rsp+48h+Arguments], 0; Arguments
0x1800052d6  mov     r9d, 400h; dwLanguageId
0x1800052dc  mov     [rsp+48h+nSize], ebx; nSize
0x1800052e0  mov     r8d, esi; dwMessageId
0x1800052e3  mov     rdx, rax; lpSource
0x1800052e6  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800052eb  mov     ecx, 1A00h; dwFlags
0x1800052f0  call    cs:__imp_FormatMessageW
0x1800052f7  nop     dword ptr [rax+rax+00h]
0x1800052fc  mov     rbx, [rsp+48h+arg_0]
0x180005301  mov     rsi, [rsp+48h+arg_8]
0x180005306  add     rsp, 40h
0x18000530a  pop     rdi
0x18000530b  retn
```
