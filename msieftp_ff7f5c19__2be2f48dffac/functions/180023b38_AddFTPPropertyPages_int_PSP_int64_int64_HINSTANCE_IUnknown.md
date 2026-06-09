# AddFTPPropertyPages(int (*)(_PSP *,__int64),__int64,HINSTANCE__ * *,IUnknown *)

- ea: `0x180023b38`
- end: `0x180023bd9`
- name: `?AddFTPPropertyPages@@YAJP6AHPEAU_PSP@@_J@Z1PEAPEAUHINSTANCE__@@PEAUIUnknown@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(int (*)(struct _PSP *, __int64), __int64, HINSTANCE *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015e10`
- `0x180025e30`

## callees

- `0x180002b60`
- `0x180023b38`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023b76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023b76`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180023b5e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180023b5e`

## pseudocode

```c
__int64 __fastcall AddFTPPropertyPages(
        int (*a1)(struct _PSP *, __int64),
        __int64 a2,
        HINSTANCE *a3,
        struct IUnknown *a4)
{
  HMODULE LibraryW; // rax
  unsigned int v8; // esi
  FARPROC ProcAddress; // rbx
  __int64 result; // rax
  _DWORD v11[26]; // [rsp+30h] [rbp-68h] BYREF

  LibraryW = *a3;
  v8 = -2147467259;
  if ( *a3 || (LibraryW = LoadLibraryW(L"inetcpl.cpl"), (*a3 = LibraryW) != 0) )
  {
    ProcAddress = GetProcAddress(LibraryW, "AddInternetPropertySheetsEx");
    if ( ProcAddress )
    {
      memset_0(v11, 0, 0x40u);
      v11[0] = 64;
      v11[1] = -1;
      v8 = ((__int64 (__fastcall *)(int (*)(struct _PSP *, __int64), __int64, _QWORD, _QWORD, _DWORD *))ProcAddress)(
             a1,
             a2,
             0,
             0,
             v11);
    }
  }
  result = 1;
  if ( *(_DWORD *)(a2 + 40) )
    return v8;
  return result;
}

```

## disassembly

```asm
0x180023b38  push    rbx
0x180023b3a  push    rbp
0x180023b3b  push    rsi
0x180023b3c  push    rdi
0x180023b3d  sub     rsp, 78h
0x180023b41  mov     rax, [r8]
0x180023b44  mov     rbx, r8
0x180023b47  mov     rdi, rdx
0x180023b4a  mov     rbp, rcx
0x180023b4d  mov     esi, 80004005h
0x180023b52  test    rax, rax
0x180023b55  jnz     short loc_180023B6C
0x180023b57  lea     rcx, aInetcplCpl; "inetcpl.cpl"
0x180023b5e  call    cs:__imp_LoadLibraryW
0x180023b64  mov     [rbx], rax
0x180023b67  test    rax, rax
0x180023b6a  jz      short loc_180023BC4
0x180023b6c  lea     rdx, aAddinternetpro; "AddInternetPropertySheetsEx"
0x180023b73  mov     rcx, rax; hModule
0x180023b76  call    cs:__imp_GetProcAddress
0x180023b7c  mov     rbx, rax
0x180023b7f  test    rax, rax
0x180023b82  jz      short loc_180023BC4
0x180023b84  mov     esi, 40h ; '@'
0x180023b89  lea     rcx, [rsp+98h+var_68]; void *
0x180023b8e  mov     r8d, esi; Size
0x180023b91  xor     edx, edx; Val
0x180023b93  call    memset_0
0x180023b98  lea     rax, [rsp+98h+var_68]
0x180023b9d  mov     [rsp+98h+var_68], esi
0x180023ba1  mov     [rsp+98h+var_78], rax
0x180023ba6  xor     r9d, r9d
0x180023ba9  mov     rax, rbx
0x180023bac  mov     [rsp+98h+var_64], 0FFFFFFFFh
0x180023bb4  xor     r8d, r8d
0x180023bb7  mov     rdx, rdi
0x180023bba  mov     rcx, rbp
0x180023bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bc2  mov     esi, eax
0x180023bc4  cmp     dword ptr [rdi+28h], 0
0x180023bc8  mov     eax, 1
0x180023bcd  cmova   eax, esi
0x180023bd0  add     rsp, 78h
0x180023bd4  pop     rdi
0x180023bd5  pop     rsi
0x180023bd6  pop     rbp
0x180023bd7  pop     rbx
0x180023bd8  retn
```
