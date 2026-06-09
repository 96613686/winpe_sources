# ValidatePasswordPolicy

- ea: `0x180005464`
- end: `0x180005587`
- name: `ValidatePasswordPolicy`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180003e20`

## callees

- `0x1800050ac`
- `0x180005464`
- `0x18003e582`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005543`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005573`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005573`

## string_xrefs

- `0x180005487`: `NETAPI32.DLL`

## pseudocode

```c
__int64 __fastcall ValidatePasswordPolicy(__int64 a1, __int64 a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rbx
  FARPROC v6; // rax
  void (__fastcall *v7)(__int64 *); // rsi
  DWORD v8; // eax
  DWORD LastError; // ebx
  _BYTE v11[48]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v12; // [rsp+60h] [rbp-58h]
  __int64 v13; // [rsp+C0h] [rbp+8h] BYREF

  v13 = a1;
  memset_0(v11, 0, 0x58u);
  v13 = 0;
  LibraryW = IsolationAwareLoadLibraryW(L"NETAPI32.DLL");
  v4 = LibraryW;
  if ( !LibraryW )
  {
    v7 = 0;
    LastError = GetLastError();
    goto LABEL_12;
  }
  ProcAddress = GetProcAddress(LibraryW, "NetValidatePasswordPolicy");
  v6 = GetProcAddress(v4, "NetValidatePasswordPolicyFree");
  v7 = (void (__fastcall *)(__int64 *))v6;
  if ( !ProcAddress || !v6 )
    goto LABEL_10;
  memset_0(v11, 0, 0x58u);
  v12 = a2;
  v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _BYTE *, __int64 *))ProcAddress)(0, 0, 3, v11, &v13);
  LastError = v8;
  if ( !v8 )
  {
    if ( v13 )
      LastError = *(_DWORD *)(v13 + 48);
    else
      LastError = 1450;
    goto LABEL_12;
  }
  if ( v8 == 50 || v8 == 1745 )
LABEL_10:
    LastError = 0;
LABEL_12:
  if ( v13 && v7 )
    v7(&v13);
  if ( v4 )
    FreeLibrary(v4);
  return LastError;
}

```

## disassembly

```asm
0x180005464  mov     [rsp+arg_0], rcx
0x180005469  push    rbx
0x18000546a  push    rbp
0x18000546b  push    rsi
0x18000546c  push    rdi
0x18000546d  sub     rsp, 98h
0x180005474  mov     rbp, rdx
0x180005477  lea     rcx, [rsp+0B8h+var_88]; void *
0x18000547c  xor     edx, edx; Val
0x18000547e  lea     r8d, [rdx+58h]; Size
0x180005482  call    memset_0
0x180005487  lea     rcx, aNetapi32Dll; "NETAPI32.DLL"
0x18000548e  mov     [rsp+0B8h+arg_0], 0
0x18000549a  call    IsolationAwareLoadLibraryW
0x18000549f  mov     rdi, rax
0x1800054a2  test    rax, rax
0x1800054a5  jz      loc_180005541
0x1800054ab  lea     rdx, ProcName; "NetValidatePasswordPolicy"
0x1800054b2  mov     rcx, rax; hModule
0x1800054b5  call    cs:__imp_GetProcAddress
0x1800054bb  lea     rdx, aNetvalidatepas; "NetValidatePasswordPolicyFree"
0x1800054c2  mov     rcx, rdi; hModule
0x1800054c5  mov     rbx, rax
0x1800054c8  call    cs:__imp_GetProcAddress
0x1800054ce  mov     rsi, rax
0x1800054d1  test    rbx, rbx
0x1800054d4  jz      short loc_18000553D
0x1800054d6  test    rax, rax
0x1800054d9  jz      short loc_18000553D
0x1800054db  xor     edx, edx; Val
0x1800054dd  lea     rcx, [rsp+0B8h+var_88]; void *
0x1800054e2  lea     r8d, [rdx+58h]; Size
0x1800054e6  call    memset_0
0x1800054eb  xor     edx, edx
0x1800054ed  mov     [rsp+0B8h+var_58], rbp
0x1800054f2  lea     rax, [rsp+0B8h+arg_0]
0x1800054fa  xor     ecx, ecx
0x1800054fc  mov     [rsp+0B8h+var_98], rax
0x180005501  lea     r9, [rsp+0B8h+var_88]
0x180005506  mov     rax, rbx
0x180005509  lea     r8d, [rdx+3]
0x18000550d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005512  mov     ebx, eax
0x180005514  test    eax, eax
0x180005516  jnz     short loc_180005531
0x180005518  mov     rbx, [rsp+0B8h+arg_0]
0x180005520  test    rbx, rbx
0x180005523  jz      short loc_18000552A
0x180005525  mov     ebx, [rbx+30h]
0x180005528  jmp     short loc_18000554B
0x18000552a  mov     ebx, 5AAh
0x18000552f  jmp     short loc_18000554B
0x180005531  cmp     eax, 32h ; '2'
0x180005534  jz      short loc_18000553D
0x180005536  cmp     eax, 6D1h
0x18000553b  jnz     short loc_18000554B
0x18000553d  xor     ebx, ebx
0x18000553f  jmp     short loc_18000554B
0x180005541  xor     esi, esi
0x180005543  call    cs:__imp_GetLastError
0x180005549  mov     ebx, eax
0x18000554b  cmp     [rsp+0B8h+arg_0], 0
0x180005554  jz      short loc_18000556B
0x180005556  test    rsi, rsi
0x180005559  jz      short loc_18000556B
0x18000555b  lea     rcx, [rsp+0B8h+arg_0]
0x180005563  mov     rax, rsi
0x180005566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000556b  test    rdi, rdi
0x18000556e  jz      short loc_180005579
0x180005570  mov     rcx, rdi; hLibModule
0x180005573  call    cs:__imp_FreeLibrary
0x180005579  mov     eax, ebx
0x18000557b  add     rsp, 98h
0x180005582  pop     rdi
0x180005583  pop     rsi
0x180005584  pop     rbp
0x180005585  pop     rbx
0x180005586  retn
```
