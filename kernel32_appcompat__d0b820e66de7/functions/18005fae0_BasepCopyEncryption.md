# BasepCopyEncryption

- ea: `0x18005fae0`
- end: `0x18005fbac`
- name: `BasepCopyEncryption`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18005fae0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fb37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fb61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fb37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fb61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005fb91`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180083891`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005fb91`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180083891`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005fb0f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005fb0f`

## string_xrefs

- `0x18005fb08`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall BasepCopyEncryption(__int64 a1, int a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rax
  FARPROC v10; // rax

  v6 = 0;
  Library = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
  v8 = Library;
  if ( Library )
  {
    if ( a2 )
    {
      ProcAddress = GetProcAddress(Library, "EncryptFileW");
      if ( ProcAddress && ((unsigned int (__fastcall *)(__int64))ProcAddress)(a1) )
      {
        *a3 |= 0x4000u;
LABEL_9:
        v6 = 1;
      }
    }
    else
    {
      v10 = GetProcAddress(Library, "DecryptFileW");
      if ( v10 && ((unsigned int (__fastcall *)(__int64, _QWORD))v10)(a1, 0) )
      {
        *a3 &= ~0x4000u;
        goto LABEL_9;
      }
    }
  }
  if ( v8 )
    FreeLibrary(v8);
  return v6;
}

```

## disassembly

```asm
0x18005fae0  push    rbx
0x18005fae2  push    rsi
0x18005fae3  push    rdi
0x18005fae4  push    r14
0x18005fae6  push    r15
0x18005fae8  sub     rsp, 30h
0x18005faec  mov     rsi, r8
0x18005faef  mov     r14d, edx
0x18005faf2  mov     r15, rcx
0x18005faf5  mov     [rsp+58h+var_38], 0
0x18005fafe  xor     ebx, ebx
0x18005fb00  xor     edx, edx; hFile
0x18005fb02  mov     r8d, 800h; dwFlags
0x18005fb08  lea     rcx, AdvapiDllString; "advapi32.dll"
0x18005fb0f  call    cs:__imp_LoadLibraryExW
0x18005fb16  nop     dword ptr [rax+rax+00h]
0x18005fb1b  mov     rdi, rax
0x18005fb1e  mov     [rsp+58h+var_38], rax
0x18005fb23  test    rax, rax
0x18005fb26  jz      short loc_18005FB89
0x18005fb28  mov     rcx, rax; hModule
0x18005fb2b  test    r14d, r14d
0x18005fb2e  jz      short loc_18005FB5A
0x18005fb30  lea     rdx, ENCRYPTFILEW_NAME; "EncryptFileW"
0x18005fb37  call    cs:__imp_GetProcAddress
0x18005fb3e  nop     dword ptr [rax+rax+00h]
0x18005fb43  test    rax, rax
0x18005fb46  jz      short loc_18005FB89
0x18005fb48  mov     rcx, r15
0x18005fb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb50  test    eax, eax
0x18005fb52  jz      short loc_18005FB89
0x18005fb54  bts     dword ptr [rsi], 0Eh
0x18005fb58  jmp     short loc_18005FB84
0x18005fb5a  lea     rdx, DECRYPTFILEW_NAME; "DecryptFileW"
0x18005fb61  call    cs:__imp_GetProcAddress
0x18005fb68  nop     dword ptr [rax+rax+00h]
0x18005fb6d  test    rax, rax
0x18005fb70  jz      short loc_18005FB89
0x18005fb72  xor     edx, edx
0x18005fb74  mov     rcx, r15
0x18005fb77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb7c  test    eax, eax
0x18005fb7e  jz      short loc_18005FB89
0x18005fb80  btr     dword ptr [rsi], 0Eh
0x18005fb84  mov     ebx, 1
0x18005fb89  test    rdi, rdi
0x18005fb8c  jz      short loc_18005FB9D
0x18005fb8e  mov     rcx, rdi; hLibModule
0x18005fb91  call    cs:__imp_FreeLibrary
0x18005fb98  nop     dword ptr [rax+rax+00h]
0x18005fb9d  mov     eax, ebx
0x18005fb9f  add     rsp, 30h
0x18005fba3  pop     r15
0x18005fba5  pop     r14
0x18005fba7  pop     rdi
0x18005fba8  pop     rsi
0x18005fba9  pop     rbx
0x18005fbaa  retn
0x18008387f  push    rbp
0x180083881  sub     rsp, 20h
0x180083885  mov     rbp, rdx
0x180083888  mov     rcx, [rbp+20h]; hLibModule
0x18008388c  test    rcx, rcx
0x18008388f  jz      short loc_18008389E
0x180083891  call    cs:__imp_FreeLibrary
0x180083898  nop     dword ptr [rax+rax+00h]
0x18008389d  nop
0x18008389e  add     rsp, 20h
0x1800838a2  pop     rbp
0x1800838a3  retn
```
