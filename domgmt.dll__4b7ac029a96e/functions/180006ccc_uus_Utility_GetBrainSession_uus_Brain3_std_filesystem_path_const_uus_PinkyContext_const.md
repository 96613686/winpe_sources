# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x180006ccc`
- end: `0x180006dd0`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800084c8`

## callees

- `0x180006ccc`
- `0x18000a408`
- `0x18000a8d0`
- `0x18000a918`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006da4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006da4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006d14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006d14`

## string_xrefs

- `0x180006d5e`: `DllGetSessionForPinky`
- `0x180006d4c`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`
- `0x180006db8`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetBrainSession<uus::Brain3>(char *a1, __int64 a2)
{
  char *v3; // rbx
  int v4; // eax
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rbx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF
  HMODULE v16; // [rsp+60h] [rbp+18h]

  v3 = a1;
  if ( a2 )
    v4 = (*(_DWORD *)(a2 + 12) & 4) == 0;
  else
    v4 = 1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  Library = LoadLibraryExW((LPCWSTR)a1, 0, (v4 << 7) + 8);
  v16 = Library;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(char **)v3;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x164,
    (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
    (const char *)(Library == 0),
    (bool)"Error loading library %s",
    v3);
  ProcAddress = GetProcAddress(Library, "DllGetSessionForPinky");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v7, v8, v9);
  v15 = 0;
  v10 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v15, a2);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
      (const char *)(unsigned int)v10,
      v13);
  v11 = v15;
  if ( Library )
    FreeLibrary(Library);
  return v11;
}

```

## disassembly

```asm
0x180006ccc  push    rbx
0x180006cce  push    rsi
0x180006ccf  push    rdi
0x180006cd0  sub     rsp, 30h
0x180006cd4  mov     rsi, rdx
0x180006cd7  mov     rbx, rcx
0x180006cda  mov     [rsp+48h+arg_0], 0
0x180006ce2  test    rdx, rdx
0x180006ce5  jz      short loc_180006CF4
0x180006ce7  mov     eax, [rdx+0Ch]
0x180006cea  shr     eax, 2
0x180006ced  not     eax
0x180006cef  and     eax, 1
0x180006cf2  jmp     short loc_180006CF9
0x180006cf4  mov     eax, 1
0x180006cf9  shl     eax, 7
0x180006cfc  lea     r8d, [rax+8]; dwFlags
0x180006d00  mov     [rsp+48h+arg_0], 2
0x180006d08  cmp     qword ptr [rcx+18h], 7
0x180006d0d  jbe     short loc_180006D12
0x180006d0f  mov     rcx, [rcx]; lpLibFileName
0x180006d12  xor     edx, edx; hFile
0x180006d14  call    cs:__imp_LoadLibraryExW
0x180006d1a  mov     rdi, rax
0x180006d1d  mov     [rsp+48h+arg_10], rax
0x180006d22  cmp     qword ptr [rbx+18h], 7
0x180006d27  jbe     short loc_180006D2C
0x180006d29  mov     rbx, [rbx]
0x180006d2c  test    rdi, rdi
0x180006d2f  setz    al
0x180006d32  mov     rcx, [rsp+48h]; this
0x180006d37  mov     [rsp+48h+var_20], rbx; char *
0x180006d3c  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180006d43  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180006d48  movzx   r9d, al; char *
0x180006d4c  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x180006d53  mov     edx, 164h; void *
0x180006d58  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180006d5d  nop
0x180006d5e  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x180006d65  mov     rcx, rdi; hModule
0x180006d68  call    cs:__imp_GetProcAddress
0x180006d6e  mov     rcx, [rsp+48h]; this
0x180006d73  test    rax, rax
0x180006d76  jz      short loc_180006DCA
0x180006d78  mov     [rsp+48h+arg_8], 0
0x180006d81  mov     rdx, rsi
0x180006d84  lea     rcx, [rsp+48h+arg_8]
0x180006d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d8e  mov     rcx, [rsp+48h]; this
0x180006d93  test    eax, eax
0x180006d95  js      short loc_180006DB5
0x180006d97  mov     rbx, [rsp+48h+arg_8]
0x180006d9c  test    rdi, rdi
0x180006d9f  jz      short loc_180006DAA
0x180006da1  mov     rcx, rdi; hLibModule
0x180006da4  call    cs:__imp_FreeLibrary
0x180006daa  mov     rax, rbx
0x180006dad  add     rsp, 30h
0x180006db1  pop     rdi
0x180006db2  pop     rsi
0x180006db3  pop     rbx
0x180006db4  retn
0x180006db5  mov     r9d, eax; char *
0x180006db8  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x180006dbf  mov     edx, 177h; void *
0x180006dc4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006dca  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
