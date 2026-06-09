# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x180002420`
- end: `0x180002527`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `263`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800087c0`

## callees

- `0x180002420`
- `0x180002530`
- `0x18000a090`
- `0x18000a0ac`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000246a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000246a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002511`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002511`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800024be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800024be`

## string_xrefs

- `0x1800024a2`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`
- `0x1800024f2`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`
- `0x1800024b4`: `DllGetSessionForPinky`

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
0x180002420  mov     [rsp+arg_18], rbx
0x180002425  push    rbp
0x180002426  push    rsi
0x180002427  push    rdi
0x180002428  sub     rsp, 30h
0x18000242c  mov     rsi, rdx
0x18000242f  mov     rbx, rcx
0x180002432  xor     ebp, ebp
0x180002434  mov     [rsp+48h+arg_0], ebp
0x180002438  test    rdx, rdx
0x18000243b  jz      short loc_18000244A
0x18000243d  mov     eax, [rdx+0Ch]
0x180002440  shr     eax, 2
0x180002443  not     eax
0x180002445  and     eax, 1
0x180002448  jmp     short loc_18000244F
0x18000244a  mov     eax, 1
0x18000244f  shl     eax, 7
0x180002452  lea     r8d, [rax+8]; dwFlags
0x180002456  mov     [rsp+48h+arg_0], 2
0x18000245e  cmp     qword ptr [rcx+18h], 7
0x180002463  jbe     short loc_180002468
0x180002465  mov     rcx, [rcx]; lpLibFileName
0x180002468  xor     edx, edx; hFile
0x18000246a  call    cs:__imp_LoadLibraryExW
0x180002470  mov     rdi, rax
0x180002473  mov     [rsp+48h+arg_10], rax
0x180002478  cmp     qword ptr [rbx+18h], 7
0x18000247d  jbe     short loc_180002482
0x18000247f  mov     rbx, [rbx]
0x180002482  test    rdi, rdi
0x180002485  setz    al
0x180002488  mov     rcx, [rsp+48h]; this
0x18000248d  mov     [rsp+48h+var_20], rbx; char *
0x180002492  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180002499  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18000249e  movzx   r9d, al; char *
0x1800024a2  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x1800024a9  mov     edx, 164h; void *
0x1800024ae  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800024b3  nop
0x1800024b4  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x1800024bb  mov     rcx, rdi; hModule
0x1800024be  call    cs:__imp_GetProcAddress
0x1800024c4  mov     rcx, [rsp+48h]; this
0x1800024c9  test    rax, rax
0x1800024cc  jnz     short loc_1800024D4
0x1800024ce  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800024d4  mov     [rsp+48h+arg_8], rbp
0x1800024d9  mov     rdx, rsi
0x1800024dc  lea     rcx, [rsp+48h+arg_8]
0x1800024e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e6  mov     rcx, [rsp+48h]; this
0x1800024eb  test    eax, eax
0x1800024ed  jns     short loc_180002504
0x1800024ef  mov     r9d, eax; char *
0x1800024f2  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x1800024f9  mov     edx, 177h; void *
0x1800024fe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180002504  mov     rbx, [rsp+48h+arg_8]
0x180002509  test    rdi, rdi
0x18000250c  jz      short loc_180002517
0x18000250e  mov     rcx, rdi; hLibModule
0x180002511  call    cs:__imp_FreeLibrary
0x180002517  mov     rax, rbx
0x18000251a  mov     rbx, [rsp+48h+arg_18]
0x18000251f  add     rsp, 30h
0x180002523  pop     rdi
0x180002524  pop     rsi
0x180002525  pop     rbp
0x180002526  retn
```
