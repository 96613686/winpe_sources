# DWMForceIconic

- ea: `0x18014d400`
- end: `0x18014d575`
- name: `DWMForceIconic`
- size: `373`
- prototype: `__int64 __fastcall(HWND hwnd)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a7250`

## callees

- `0x1800388a0`
- `0x18014d400`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18014d470`
- `KERNEL32!LoadLibraryExA` at `0x18014d470`
- `KERNEL32!GetProcAddress` at `0x18014d49c`
- `KERNEL32!GetProcAddress` at `0x18014d4c6`
- `KERNEL32!GetProcAddress` at `0x18014d49c`
- `KERNEL32!GetProcAddress` at `0x18014d4c6`
- `USER32!GetAncestor` at `0x18014d4f1`
- `USER32!GetAncestor` at `0x18014d4f1`

## string_xrefs

- `0x18014d44b`: `dwmapi.DLL`
- `0x18014d4bf`: `DwmIsCompositionEnabled`

## pseudocode

```c
__int64 __fastcall DWMForceIconic(HWND hwnd, int a2)
{
  __int64 (__fastcall *v4)(HWND, __int64, int *); // rbx
  HMODULE Library; // rax
  HWND Ancestor; // rax
  int v7; // ebx
  int v8; // [rsp+30h] [rbp-38h] BYREF
  int v9; // [rsp+38h] [rbp-30h] BYREF
  CHAR LibFileName[16]; // [rsp+40h] [rbp-28h] BYREF

  v9 = a2;
  if ( !hwnd )
    return 2147500037LL;
  v4 = (__int64 (__fastcall *)(HWND, __int64, int *))qword_1801A2428;
  if ( !qword_1801A2428 )
  {
    Library = qword_1801A2418;
    if ( !qword_1801A2418 )
    {
      strcpy(LibFileName, "dwmapi.DLL");
      Library = LoadLibraryExA(LibFileName, 0, 0x800u);
      qword_1801A2418 = Library;
      if ( !Library )
        return 1;
    }
    qword_1801A2428 = (__int64)GetProcAddress(Library, "DwmSetWindowAttribute");
    if ( !qword_1801A2428 )
      return 2147500037LL;
    qword_1801A2420 = (__int64)GetProcAddress(qword_1801A2418, "DwmIsCompositionEnabled");
    if ( !qword_1801A2420 )
      return 2147500037LL;
    v4 = (__int64 (__fastcall *)(HWND, __int64, int *))qword_1801A2428;
  }
  Ancestor = GetAncestor(hwnd, 2u);
  v7 = v4(Ancestor, 7, &v9);
  if ( v7 < 0 )
  {
    v8 = 0;
    if ( (int)((__int64 (__fastcall *)(int *))qword_1801A2420)(&v8) < 0 || !v8 )
      return 1;
  }
  if ( v7 == -2144980991 )
    return 1;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18014d400  mov     [rsp+arg_10], rbx
0x18014d405  push    rdi
0x18014d406  sub     rsp, 60h
0x18014d40a  mov     rax, cs:__security_cookie
0x18014d411  xor     rax, rsp
0x18014d414  mov     [rsp+68h+var_18], rax
0x18014d419  mov     [rsp+68h+var_30], edx
0x18014d41d  mov     rdi, rcx
0x18014d420  test    rcx, rcx
0x18014d423  jnz     short loc_18014D42F
0x18014d425  mov     eax, 80004005h
0x18014d42a  jmp     loc_18014D559
0x18014d42f  mov     rbx, cs:qword_1801A2428
0x18014d436  test    rbx, rbx
0x18014d439  jnz     loc_18014D4E9
0x18014d43f  mov     rax, cs:qword_1801A2418
0x18014d446  test    rax, rax
0x18014d449  jnz     short loc_18014D492
0x18014d44b  movsd   xmm0, qword ptr cs:aDwmapiDll; "dwmapi.DLL"
0x18014d453  lea     rcx, [rsp+68h+LibFileName]; lpLibFileName
0x18014d458  mov     eax, dword ptr cs:aDwmapiDll+7; "DLL"
0x18014d45e  xor     edx, edx; hFile
0x18014d460  movsd   qword ptr [rsp+68h+LibFileName], xmm0
0x18014d466  mov     r8d, 800h; dwFlags
0x18014d46c  mov     dword ptr [rsp+68h+LibFileName+7], eax
0x18014d470  call    cs:__imp_LoadLibraryExA
0x18014d477  nop     dword ptr [rax+rax+00h]
0x18014d47c  mov     cs:qword_1801A2418, rax
0x18014d483  test    rax, rax
0x18014d486  jnz     short loc_18014D492
0x18014d488  mov     eax, 1
0x18014d48d  jmp     loc_18014D559
0x18014d492  lea     rdx, aDwmsetwindowat; "DwmSetWindowAttribute"
0x18014d499  mov     rcx, rax; hModule
0x18014d49c  call    cs:__imp_GetProcAddress
0x18014d4a3  nop     dword ptr [rax+rax+00h]
0x18014d4a8  mov     cs:qword_1801A2428, rax
0x18014d4af  test    rax, rax
0x18014d4b2  jz      loc_18014D425
0x18014d4b8  mov     rcx, cs:qword_1801A2418; hModule
0x18014d4bf  lea     rdx, aDwmiscompositi; "DwmIsCompositionEnabled"
0x18014d4c6  call    cs:__imp_GetProcAddress
0x18014d4cd  nop     dword ptr [rax+rax+00h]
0x18014d4d2  mov     cs:qword_1801A2420, rax
0x18014d4d9  test    rax, rax
0x18014d4dc  jz      loc_18014D425
0x18014d4e2  mov     rbx, cs:qword_1801A2428
0x18014d4e9  mov     edx, 2; gaFlags
0x18014d4ee  mov     rcx, rdi; hwnd
0x18014d4f1  call    cs:__imp_GetAncestor
0x18014d4f8  nop     dword ptr [rax+rax+00h]
0x18014d4fd  mov     r9d, 4
0x18014d503  lea     r8, [rsp+68h+var_30]
0x18014d508  mov     rcx, rax
0x18014d50b  mov     rax, rbx
0x18014d50e  lea     edx, [r9+3]
0x18014d512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d517  mov     ebx, eax
0x18014d519  test    eax, eax
0x18014d51b  jns     short loc_18014D549
0x18014d51d  mov     rax, cs:qword_1801A2420
0x18014d524  lea     rcx, [rsp+68h+var_38]
0x18014d529  mov     [rsp+68h+var_38], 0
0x18014d531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d536  test    eax, eax
0x18014d538  js      loc_18014D488
0x18014d53e  cmp     [rsp+68h+var_38], 0
0x18014d543  jz      loc_18014D488
0x18014d549  mov     eax, 1
0x18014d54e  cmp     ebx, 80263001h
0x18014d554  cmovz   ebx, eax
0x18014d557  mov     eax, ebx
0x18014d559  mov     rcx, [rsp+68h+var_18]
0x18014d55e  xor     rcx, rsp; StackCookie
0x18014d561  call    __security_check_cookie
0x18014d566  mov     rbx, [rsp+68h+arg_10]
0x18014d56e  add     rsp, 60h
0x18014d572  pop     rdi
0x18014d573  retn
```
