# GetEncryptedFileVersionExt

- ea: `0x18000a880`
- end: `0x18000a96d`
- name: `GetEncryptedFileVersionExt`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000acc0`

## callees

- `0x18000a880`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8f4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a94b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a94b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a8ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a8ae`

## string_xrefs

- `0x18000a89a`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall GetEncryptedFileVersionExt(__int64 a1, _DWORD *a2)
{
  void (*v4)(void); // rsi
  HMODULE Library; // rax
  HMODULE v6; // rdi
  ULONG LastErrorValue; // ebx
  FARPROC ProcAddress; // rbx
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  v10 = 0;
  Library = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
  v6 = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "EncryptedFileKeyInfo")) != 0
    && (v4 = (void (*)(void))GetProcAddress(v6, "FreeEncryptedFileKeyInfo")) != 0 )
  {
    LastErrorValue = ((__int64 (__fastcall *)(__int64, __int64, __int64 *))ProcAddress)(a1, 2, &v10);
    if ( !LastErrorValue )
      *a2 = **(_DWORD **)(v10 + 8);
  }
  else
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
  }
  if ( v10 )
    v4();
  if ( v6 )
    FreeLibrary(v6);
  return LastErrorValue;
}

```

## disassembly

```asm
0x18000a880  mov     [rsp+arg_0], rbx
0x18000a885  mov     [rsp+arg_8], rbp
0x18000a88a  push    rsi
0x18000a88b  push    rdi
0x18000a88c  push    r14
0x18000a88e  sub     rsp, 20h
0x18000a892  mov     r14, rdx
0x18000a895  mov     rbp, rcx
0x18000a898  xor     esi, esi
0x18000a89a  lea     rcx, AdvapiDllString; "advapi32.dll"
0x18000a8a1  xor     edx, edx; hFile
0x18000a8a3  mov     [rsp+38h+arg_10], rsi
0x18000a8a8  mov     r8d, 800h; dwFlags
0x18000a8ae  call    cs:__imp_LoadLibraryExW
0x18000a8b5  nop     dword ptr [rax+rax+00h]
0x18000a8ba  mov     rdi, rax
0x18000a8bd  test    rax, rax
0x18000a8c0  jnz     short loc_18000A8CC
0x18000a8c2  mov     ebx, gs:68h
0x18000a8ca  jmp     short loc_18000A931
0x18000a8cc  lea     rdx, ENCRYPTEDFILEKEYINFO_NAME; "EncryptedFileKeyInfo"
0x18000a8d3  mov     rcx, rdi; hModule
0x18000a8d6  call    cs:__imp_GetProcAddress
0x18000a8dd  nop     dword ptr [rax+rax+00h]
0x18000a8e2  mov     rbx, rax
0x18000a8e5  test    rax, rax
0x18000a8e8  jz      short loc_18000A8C2
0x18000a8ea  lea     rdx, FREEFILEKEYINFO_NAME; "FreeEncryptedFileKeyInfo"
0x18000a8f1  mov     rcx, rdi; hModule
0x18000a8f4  call    cs:__imp_GetProcAddress
0x18000a8fb  nop     dword ptr [rax+rax+00h]
0x18000a900  mov     rsi, rax
0x18000a903  test    rax, rax
0x18000a906  jz      short loc_18000A8C2
0x18000a908  lea     r8, [rsp+38h+arg_10]
0x18000a90d  mov     edx, 2
0x18000a912  mov     rcx, rbp
0x18000a915  mov     rax, rbx
0x18000a918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a91d  mov     ebx, eax
0x18000a91f  test    eax, eax
0x18000a921  jnz     short loc_18000A931
0x18000a923  mov     rcx, [rsp+38h+arg_10]
0x18000a928  mov     rdx, [rcx+8]
0x18000a92c  mov     ecx, [rdx]
0x18000a92e  mov     [r14], ecx
0x18000a931  mov     rcx, [rsp+38h+arg_10]
0x18000a936  test    rcx, rcx
0x18000a939  jz      short loc_18000A943
0x18000a93b  mov     rax, rsi
0x18000a93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a943  test    rdi, rdi
0x18000a946  jz      short loc_18000A957
0x18000a948  mov     rcx, rdi; hLibModule
0x18000a94b  call    cs:__imp_FreeLibrary
0x18000a952  nop     dword ptr [rax+rax+00h]
0x18000a957  mov     rbp, [rsp+38h+arg_8]
0x18000a95c  mov     eax, ebx
0x18000a95e  mov     rbx, [rsp+38h+arg_0]
0x18000a963  add     rsp, 20h
0x18000a967  pop     r14
0x18000a969  pop     rdi
0x18000a96a  pop     rsi
0x18000a96b  retn
```
