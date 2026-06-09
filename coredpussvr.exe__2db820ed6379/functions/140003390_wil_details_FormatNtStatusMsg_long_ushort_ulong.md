# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140003390`
- end: `0x14000340d`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003390`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400033ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400033ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400033f0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400033f0`

## string_xrefs

- `0x1400033b3`: `ntdll.dll`

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
0x140003390  mov     [rsp+arg_0], rbx
0x140003395  mov     [rsp+arg_8], rsi
0x14000339a  push    rdi
0x14000339b  sub     rsp, 40h
0x14000339f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400033a6  mov     ebx, r8d
0x1400033a9  mov     rdi, rdx
0x1400033ac  mov     esi, ecx
0x1400033ae  test    rax, rax
0x1400033b1  jnz     short loc_1400033CD
0x1400033b3  lea     rcx, ModuleName; "ntdll.dll"
0x1400033ba  call    cs:__imp_GetModuleHandleW
0x1400033c1  nop     dword ptr [rax+rax+00h]
0x1400033c6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400033cd  mov     [rsp+48h+Arguments], 0; Arguments
0x1400033d6  mov     r9d, 400h; dwLanguageId
0x1400033dc  mov     [rsp+48h+nSize], ebx; nSize
0x1400033e0  mov     r8d, esi; dwMessageId
0x1400033e3  mov     rdx, rax; lpSource
0x1400033e6  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400033eb  mov     ecx, 1A00h; dwFlags
0x1400033f0  call    cs:__imp_FormatMessageW
0x1400033f7  nop     dword ptr [rax+rax+00h]
0x1400033fc  mov     rbx, [rsp+48h+arg_0]
0x140003401  mov     rsi, [rsp+48h+arg_8]
0x140003406  add     rsp, 40h
0x14000340a  pop     rdi
0x14000340b  retn
```
