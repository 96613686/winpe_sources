# BasepCopyEncryption

- ea: `0x18005a370`
- end: `0x18005a423`
- name: `BasepCopyEncryption`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18005a370`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a3c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a3e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a3c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a3e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a40f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b767`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a40f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b767`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a39f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a39f`

## string_xrefs

- `0x18005a398`: `advapi32.dll`

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
0x18005a370  push    rbx
0x18005a372  push    rsi
0x18005a373  push    rdi
0x18005a374  push    r14
0x18005a376  push    r15
0x18005a378  sub     rsp, 30h
0x18005a37c  mov     rsi, r8
0x18005a37f  mov     r14d, edx
0x18005a382  mov     r15, rcx
0x18005a385  mov     [rsp+58h+var_38], 0
0x18005a38e  xor     ebx, ebx
0x18005a390  xor     edx, edx; hFile
0x18005a392  mov     r8d, 800h; dwFlags
0x18005a398  lea     rcx, AdvapiDllString; "advapi32.dll"
0x18005a39f  call    cs:__imp_LoadLibraryExW
0x18005a3a5  mov     rdi, rax
0x18005a3a8  mov     [rsp+58h+var_38], rax
0x18005a3ad  test    rax, rax
0x18005a3b0  jz      short loc_18005A407
0x18005a3b2  mov     rcx, rax; hModule
0x18005a3b5  test    r14d, r14d
0x18005a3b8  jz      short loc_18005A3DE
0x18005a3ba  lea     rdx, ENCRYPTFILEW_NAME; "EncryptFileW"
0x18005a3c1  call    cs:__imp_GetProcAddress
0x18005a3c7  test    rax, rax
0x18005a3ca  jz      short loc_18005A407
0x18005a3cc  mov     rcx, r15
0x18005a3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3d4  test    eax, eax
0x18005a3d6  jz      short loc_18005A407
0x18005a3d8  bts     dword ptr [rsi], 0Eh
0x18005a3dc  jmp     short loc_18005A402
0x18005a3de  lea     rdx, DECRYPTFILEW_NAME; "DecryptFileW"
0x18005a3e5  call    cs:__imp_GetProcAddress
0x18005a3eb  test    rax, rax
0x18005a3ee  jz      short loc_18005A407
0x18005a3f0  xor     edx, edx
0x18005a3f2  mov     rcx, r15
0x18005a3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3fa  test    eax, eax
0x18005a3fc  jz      short loc_18005A407
0x18005a3fe  btr     dword ptr [rsi], 0Eh
0x18005a402  mov     ebx, 1
0x18005a407  test    rdi, rdi
0x18005a40a  jz      short loc_18005A415
0x18005a40c  mov     rcx, rdi; hLibModule
0x18005a40f  call    cs:__imp_FreeLibrary
0x18005a415  mov     eax, ebx
0x18005a417  add     rsp, 30h
0x18005a41b  pop     r15
0x18005a41d  pop     r14
0x18005a41f  pop     rdi
0x18005a420  pop     rsi
0x18005a421  pop     rbx
0x18005a422  retn
0x18007b755  push    rbp
0x18007b757  sub     rsp, 20h
0x18007b75b  mov     rbp, rdx
0x18007b75e  mov     rcx, [rbp+20h]; hLibModule
0x18007b762  test    rcx, rcx
0x18007b765  jz      short loc_18007B76E
0x18007b767  call    cs:__imp_FreeLibrary
0x18007b76d  nop
0x18007b76e  add     rsp, 20h
0x18007b772  pop     rbp
0x18007b773  retn
```
