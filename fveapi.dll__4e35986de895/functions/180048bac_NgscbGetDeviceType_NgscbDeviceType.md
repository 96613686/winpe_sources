# NgscbGetDeviceType(NgscbDeviceType *)

- ea: `0x180048bac`
- end: `0x180048cbf`
- name: `?NgscbGetDeviceType@@YAJPEAW4NgscbDeviceType@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(enum NgscbDeviceType *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800b998c`

## callees

- `0x1800090c0`
- `0x180048bac`
- `0x18004f318`
- `0x18004fddc`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180048bdc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180048bdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048c3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048c3a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180048ca0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180048ca0`

## string_xrefs

- `0x180048bcf`: `powrprof.dll`

## pseudocode

```c
__int64 __fastcall NgscbGetDeviceType(enum NgscbDeviceType *a1)
{
  unsigned int KnownLastErrorHR; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  int v6; // eax
  int v7; // ecx

  KnownLastErrorHR = 0;
  if ( !(unsigned __int8)NgscbpGetDeviceType_TEST_Override() )
  {
    Library = LoadLibraryExW(L"powrprof.dll", 0, 0x800u);
    v4 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "PowerDeterminePlatformRoleEx");
      if ( ProcAddress )
      {
        v6 = ((__int64 (__fastcall *)(__int64))ProcAddress)(2);
        v7 = -1;
        if ( v6 == 8 )
          v7 = 1;
        *(_DWORD *)a1 = v7;
      }
      else
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            KnownLastErrorHR);
      }
      FreeLibrary(v4);
    }
    else
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          KnownLastErrorHR);
    }
  }
  return KnownLastErrorHR;
}

```

## disassembly

```asm
0x180048bac  mov     [rsp+arg_0], rbx
0x180048bb1  mov     [rsp+arg_8], rsi
0x180048bb6  push    rdi
0x180048bb7  sub     rsp, 20h
0x180048bbb  mov     rsi, rcx
0x180048bbe  xor     ebx, ebx
0x180048bc0  call    NgscbpGetDeviceType_TEST_Override
0x180048bc5  test    al, al
0x180048bc7  jnz     loc_180048CAC
0x180048bcd  xor     edx, edx; hFile
0x180048bcf  lea     rcx, LibFileName; "powrprof.dll"
0x180048bd6  mov     r8d, 800h; dwFlags
0x180048bdc  call    cs:__imp_LoadLibraryExW
0x180048be3  nop     dword ptr [rax+rax+00h]
0x180048be8  mov     rdi, rax
0x180048beb  test    rax, rax
0x180048bee  jnz     short loc_180048C30
0x180048bf0  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180048bf5  mov     ebx, eax
0x180048bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180048bfe  lea     rax, WPP_GLOBAL_Control
0x180048c05  cmp     rcx, rax
0x180048c08  jz      loc_180048CAC
0x180048c0e  test    byte ptr [rcx+1Ch], 40h
0x180048c12  jz      loc_180048CAC
0x180048c18  mov     rcx, [rcx+10h]
0x180048c1c  lea     edx, [rdi+15h]
0x180048c1f  mov     r9d, ebx
0x180048c22  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180048c29  call    WPP_SF_d
0x180048c2e  jmp     short loc_180048CAC
0x180048c30  lea     rdx, aPowerdetermine; "PowerDeterminePlatformRoleEx"
0x180048c37  mov     rcx, rdi; hModule
0x180048c3a  call    cs:__imp_GetProcAddress
0x180048c41  nop     dword ptr [rax+rax+00h]
0x180048c46  test    rax, rax
0x180048c49  jnz     short loc_180048C85
0x180048c4b  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180048c50  mov     ebx, eax
0x180048c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c59  lea     rax, WPP_GLOBAL_Control
0x180048c60  cmp     rcx, rax
0x180048c63  jz      short loc_180048C9D
0x180048c65  test    byte ptr [rcx+1Ch], 40h
0x180048c69  jz      short loc_180048C9D
0x180048c6b  mov     rcx, [rcx+10h]
0x180048c6f  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180048c76  mov     edx, 16h
0x180048c7b  mov     r9d, ebx
0x180048c7e  call    WPP_SF_d
0x180048c83  jmp     short loc_180048C9D
0x180048c85  mov     ecx, 2
0x180048c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c8f  or      ecx, 0FFFFFFFFh
0x180048c92  cmp     eax, 8
0x180048c95  lea     edx, [rcx+2]
0x180048c98  cmovz   ecx, edx
0x180048c9b  mov     [rsi], ecx
0x180048c9d  mov     rcx, rdi; hLibModule
0x180048ca0  call    cs:__imp_FreeLibrary
0x180048ca7  nop     dword ptr [rax+rax+00h]
0x180048cac  mov     rsi, [rsp+28h+arg_8]
0x180048cb1  mov     eax, ebx
0x180048cb3  mov     rbx, [rsp+28h+arg_0]
0x180048cb8  add     rsp, 20h
0x180048cbc  pop     rdi
0x180048cbd  retn
```
