# ReadResourceContents(ushort const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18005f01c`
- end: `0x18005f0f6`
- name: `?ReadResourceContents@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18007b750`
- `0x18007b860`

## callees

- `0x180042f78`
- `0x180044608`
- `0x180044df8`
- `0x18004ca90`
- `0x18005f01c`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!FindResourceW` at `0x18005f072`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FindResourceW` at `0x18005f072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f052`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f044`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f044`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18005f094`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18005f094`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18005f086`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18005f086`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18005f0a8`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18005f0a8`

## string_xrefs

- `0x18005f03d`: `energy.dll`

## pseudocode

```c
signed int __fastcall ReadResourceContents(LPCWSTR lpName, __int64 a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v5; // rbx
  signed int result; // eax
  HRSRC ResourceW; // rax
  HRSRC v8; // rdi
  HGLOBAL Resource; // rax
  LPVOID v10; // rsi
  DWORD v11; // eax
  __int64 v12; // rax
  _BYTE v13[32]; // [rsp+20h] [rbp-48h] BYREF

  ModuleHandleW = GetModuleHandleW(L"energy.dll");
  v5 = ModuleHandleW;
  if ( ModuleHandleW
    && (ResourceW = FindResourceW(ModuleHandleW, lpName, (LPCWSTR)0x17), (v8 = ResourceW) != 0)
    && (Resource = LoadResource(v5, ResourceW)) != 0
    && (v10 = LockResource(Resource)) != 0
    && (v11 = SizeofResource(v5, v8)) != 0 )
  {
    v12 = std::string::string(v13, v10, v11);
    std::string::operator=(a2, v12);
    std::string::_Tidy_deallocate(v13);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18005f01c  mov     [rsp+arg_10], rbx
0x18005f021  push    rbp
0x18005f022  push    rsi
0x18005f023  push    rdi
0x18005f024  sub     rsp, 50h
0x18005f028  mov     rax, cs:__security_cookie
0x18005f02f  xor     rax, rsp
0x18005f032  mov     [rsp+68h+var_28], rax
0x18005f037  mov     rdi, rcx
0x18005f03a  mov     rbp, rdx
0x18005f03d  lea     rcx, aEnergyDll_0; "energy.dll"
0x18005f044  call    cs:__imp_GetModuleHandleW
0x18005f04a  mov     rbx, rax
0x18005f04d  test    rax, rax
0x18005f050  jnz     short loc_18005F066
0x18005f052  call    cs:__imp_GetLastError
0x18005f058  test    eax, eax
0x18005f05a  jle     short loc_18005F0D9
0x18005f05c  movzx   eax, ax
0x18005f05f  or      eax, 80070000h
0x18005f064  jmp     short loc_18005F0D9
0x18005f066  mov     r8d, 17h; lpType
0x18005f06c  mov     rdx, rdi; lpName
0x18005f06f  mov     rcx, rbx; hModule
0x18005f072  call    cs:__imp_FindResourceW
0x18005f078  mov     rdi, rax
0x18005f07b  test    rax, rax
0x18005f07e  jz      short loc_18005F052
0x18005f080  mov     rdx, rax; hResInfo
0x18005f083  mov     rcx, rbx; hModule
0x18005f086  call    cs:__imp_LoadResource
0x18005f08c  test    rax, rax
0x18005f08f  jz      short loc_18005F052
0x18005f091  mov     rcx, rax; hResData
0x18005f094  call    cs:__imp_LockResource
0x18005f09a  mov     rsi, rax
0x18005f09d  test    rax, rax
0x18005f0a0  jz      short loc_18005F052
0x18005f0a2  mov     rdx, rdi; hResInfo
0x18005f0a5  mov     rcx, rbx; hModule
0x18005f0a8  call    cs:__imp_SizeofResource
0x18005f0ae  test    eax, eax
0x18005f0b0  jz      short loc_18005F052
0x18005f0b2  mov     r8d, eax
0x18005f0b5  lea     rcx, [rsp+68h+var_48]
0x18005f0ba  mov     rdx, rsi
0x18005f0bd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD_K@Z; std::string::string(char const * const,unsigned __int64)
0x18005f0c2  mov     rdx, rax
0x18005f0c5  mov     rcx, rbp
0x18005f0c8  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18005f0cd  lea     rcx, [rsp+68h+var_48]
0x18005f0d2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005f0d7  xor     eax, eax
0x18005f0d9  mov     rcx, [rsp+68h+var_28]
0x18005f0de  xor     rcx, rsp; StackCookie
0x18005f0e1  call    __security_check_cookie
0x18005f0e6  mov     rbx, [rsp+68h+arg_10]
0x18005f0ee  add     rsp, 50h
0x18005f0f2  pop     rdi
0x18005f0f3  pop     rsi
0x18005f0f4  pop     rbp
0x18005f0f5  retn
```
