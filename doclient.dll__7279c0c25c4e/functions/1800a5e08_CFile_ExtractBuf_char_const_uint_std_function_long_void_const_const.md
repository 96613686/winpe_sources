# CFile::ExtractBuf(char const *,uint,std::function<long (void const *)> const &)

- ea: `0x1800a5e08`
- end: `0x1800a5f0e`
- name: `?ExtractBuf@CFile@@QEAAJPEBDIAEBV?$function@$$A6AJPEBX@Z@std@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180021a04`

## callees

- `0x180008618`
- `0x1800196f0`
- `0x1800a5e08`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5eeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5eeb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x1800a5e3e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x1800a5e3e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800a5ed7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800a5ed7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a5e83`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a5e83`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFile::ExtractBuf(HANDLE *a1, __int64 a2, DWORD dwMaximumSizeLow, __int64 a4)
{
  SIZE_T v5; // rbx
  char *FileMappingA; // rdi
  const char *v7; // r9
  unsigned int v8; // esi
  const void *v9; // rax
  const char *v10; // r9
  const void *v11; // rbx
  unsigned int LastError; // eax
  __int64 v13; // rcx
  const void *v15; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = dwMaximumSizeLow;
  FileMappingA = (char *)CreateFileMappingA(*a1, 0, 2u, 0, dwMaximumSizeLow, 0);
  if ( ((unsigned __int64)(FileMappingA + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v9 = MapViewOfFile(FileMappingA, 4u, 0, 0, v5);
    v11 = v9;
    if ( v9 )
    {
      v15 = v9;
      v13 = *(_QWORD *)(a4 + 56);
      if ( !v13 )
        std::_Xbad_function_call();
      LastError = (*(__int64 (__fastcall **)(__int64, const void **))(*(_QWORD *)v13 + 16LL))(v13, &v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x17E,
                    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
                    v10);
    }
    v8 = LastError;
    if ( v11 )
      UnmapViewOfFile(v11);
  }
  else
  {
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x17B,
           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
           v7);
  }
  if ( (unsigned __int64)(FileMappingA - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileMappingA);
  return v8;
}

```

## disassembly

```asm
0x1800a5e08  push    rbx
0x1800a5e0a  push    rsi
0x1800a5e0b  push    rdi
0x1800a5e0c  sub     rsp, 50h
0x1800a5e10  mov     rax, cs:__security_cookie
0x1800a5e17  xor     rax, rsp
0x1800a5e1a  mov     [rsp+68h+var_20], rax
0x1800a5e1f  mov     rsi, r9
0x1800a5e22  mov     ebx, r8d
0x1800a5e25  mov     [rsp+68h+lpName], 0; lpName
0x1800a5e2e  mov     [rsp+68h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x1800a5e32  xor     r9d, r9d; dwMaximumSizeHigh
0x1800a5e35  xor     edx, edx; lpFileMappingAttributes
0x1800a5e37  lea     r8d, [r9+2]; flProtect
0x1800a5e3b  mov     rcx, [rcx]; hFile
0x1800a5e3e  call    cs:__imp_CreateFileMappingA
0x1800a5e44  mov     rdi, rax
0x1800a5e47  mov     [rsp+68h+var_38], rax
0x1800a5e4c  inc     rax
0x1800a5e4f  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800a5e55  jnz     short loc_1800A5E71
0x1800a5e57  mov     rcx, [rsp+68h]; this
0x1800a5e5c  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a5e63  mov     edx, 17Bh; void *
0x1800a5e68  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a5e6d  mov     esi, eax
0x1800a5e6f  jmp     short loc_1800A5EDE
0x1800a5e71  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x1800a5e76  xor     r9d, r9d; dwFileOffsetLow
0x1800a5e79  xor     r8d, r8d; dwFileOffsetHigh
0x1800a5e7c  lea     edx, [r9+4]; dwDesiredAccess
0x1800a5e80  mov     rcx, rdi; hFileMappingObject
0x1800a5e83  call    cs:__imp_MapViewOfFile
0x1800a5e89  mov     rbx, rax
0x1800a5e8c  mov     [rsp+68h+var_30], rax
0x1800a5e91  test    rax, rax
0x1800a5e94  jnz     short loc_1800A5EAE
0x1800a5e96  mov     rcx, [rsp+68h]; this
0x1800a5e9b  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a5ea2  mov     edx, 17Eh; void *
0x1800a5ea7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a5eac  jmp     short loc_1800A5ECD
0x1800a5eae  mov     [rsp+68h+var_28], rbx
0x1800a5eb3  mov     rcx, [rsi+38h]
0x1800a5eb7  test    rcx, rcx
0x1800a5eba  jz      short loc_1800A5F08
0x1800a5ebc  mov     rax, [rcx]
0x1800a5ebf  lea     rdx, [rsp+68h+var_28]
0x1800a5ec4  mov     rax, [rax+10h]
0x1800a5ec8  call    _guard_dispatch_icall
0x1800a5ecd  mov     esi, eax
0x1800a5ecf  test    rbx, rbx
0x1800a5ed2  jz      short loc_1800A5EDE
0x1800a5ed4  mov     rcx, rbx; lpBaseAddress
0x1800a5ed7  call    cs:__imp_UnmapViewOfFile
0x1800a5edd  nop
0x1800a5ede  lea     rax, [rdi-1]
0x1800a5ee2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a5ee6  ja      short loc_1800A5EF1
0x1800a5ee8  mov     rcx, rdi; hObject
0x1800a5eeb  call    cs:__imp_CloseHandle
0x1800a5ef1  mov     eax, esi
0x1800a5ef3  mov     rcx, [rsp+68h+var_20]
0x1800a5ef8  xor     rcx, rsp; StackCookie
0x1800a5efb  call    __security_check_cookie
0x1800a5f00  add     rsp, 50h
0x1800a5f04  pop     rdi
0x1800a5f05  pop     rsi
0x1800a5f06  pop     rbx
0x1800a5f07  retn
0x1800a5f08  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
