# Old_IsRNGWinNT

- ea: `0x18004b584`
- end: `0x18004b630`
- name: `Old_IsRNGWinNT`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004a97c`

## callees

- `0x18004b584`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004b5a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004b5a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b5c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b5ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b60b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b5c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b5ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b60b`

## string_xrefs

- `0x18004b59d`: `ntdll.dll`
- `0x18004b5e4`: `NtOpenFile`

## pseudocode

```c
__int64 Old_IsRNGWinNT()
{
  __int64 result; // rax
  HMODULE ModuleHandleW; // rax
  HMODULE v2; // rbx

  if ( dword_1800ADBE8 )
    return 1;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  v2 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    __NtQuerySystemInformationRNG = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                      ModuleHandleW,
                                                                                      "NtQuerySystemInformation");
    if ( __NtQuerySystemInformationRNG )
      dword_1800AD39C = 0x4000;
    __NtOpenFileRNG = (__int64)GetProcAddress(v2, "NtOpenFile");
    __RtlInitUnicodeStringRNG = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(v2, "RtlInitUnicodeString");
  }
  result = 1;
  dword_1800ADBE8 = 1;
  return result;
}

```

## disassembly

```asm
0x18004b584  push    rbx
0x18004b586  sub     rsp, 20h
0x18004b58a  cmp     cs:dword_1800ADBE8, 0
0x18004b591  jz      short loc_18004B59D
0x18004b593  mov     eax, 1
0x18004b598  jmp     loc_18004B629
0x18004b59d  lea     rcx, ModuleName; "ntdll.dll"
0x18004b5a4  call    cs:__imp_GetModuleHandleW
0x18004b5ab  nop     dword ptr [rax+rax+00h]
0x18004b5b0  mov     rbx, rax
0x18004b5b3  test    rax, rax
0x18004b5b6  jz      short loc_18004B61E
0x18004b5b8  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x18004b5bf  mov     rcx, rax; hModule
0x18004b5c2  call    cs:__imp_GetProcAddress
0x18004b5c9  nop     dword ptr [rax+rax+00h]
0x18004b5ce  mov     cs:___NtQuerySystemInformationRNG, rax
0x18004b5d5  test    rax, rax
0x18004b5d8  jz      short loc_18004B5E4
0x18004b5da  mov     cs:dword_1800AD39C, 4000h
0x18004b5e4  lea     rdx, aNtopenfile; "NtOpenFile"
0x18004b5eb  mov     rcx, rbx; hModule
0x18004b5ee  call    cs:__imp_GetProcAddress
0x18004b5f5  nop     dword ptr [rax+rax+00h]
0x18004b5fa  lea     rdx, aRtlinitunicode; "RtlInitUnicodeString"
0x18004b601  mov     rcx, rbx; hModule
0x18004b604  mov     cs:___NtOpenFileRNG, rax
0x18004b60b  call    cs:__imp_GetProcAddress
0x18004b612  nop     dword ptr [rax+rax+00h]
0x18004b617  mov     cs:___RtlInitUnicodeStringRNG, rax
0x18004b61e  mov     eax, 1
0x18004b623  mov     cs:dword_1800ADBE8, eax
0x18004b629  add     rsp, 20h
0x18004b62d  pop     rbx
0x18004b62e  retn
```
