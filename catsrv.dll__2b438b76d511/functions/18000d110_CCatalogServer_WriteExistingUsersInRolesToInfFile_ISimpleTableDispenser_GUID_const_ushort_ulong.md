# CCatalogServer::WriteExistingUsersInRolesToInfFile(ISimpleTableDispenser *,_GUID const &,ushort *,ulong *)

- ea: `0x18000d110`
- end: `0x18000d5da`
- name: `?WriteExistingUsersInRolesToInfFile@CCatalogServer@@UEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAGPEAK@Z`
- size: `1226`
- prototype: `int(CCatalogServer *__hidden this, struct ISimpleTableDispenser *, const struct _GUID *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18000d110`
- `0x180055526`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d56e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d56e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d565`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d565`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d1e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d21f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d51d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d21f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d51d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d548`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000d4d6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000d4d6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d1c9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d1c9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000d502`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000d502`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000d24b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000d24b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d210`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d210`

## string_xrefs

- `0x18000d531`: `Failed to write role %s to the catalog - Error code 0x%08x`
- `0x18000d1bf`: `ComSetup.dll`

## pseudocode

```c
__int64 __fastcall CCatalogServer::WriteExistingUsersInRolesToInfFile(
        CCatalogServer *this,
        struct ISimpleTableDispenser *a2,
        const struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned int *a5)
{
  FARPROC ProcAddress; // r12
  HMODULE LibraryW; // rax
  HMODULE v9; // rsi
  HANDLE FileW; // rax
  void *v11; // r15
  signed int LastError; // eax
  signed int v13; // ebx
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // r8
  signed int v18; // eax
  signed int v19; // eax
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-A0h]
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-98h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  _QWORD v27[2]; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+90h] [rbp-70h]
  int v29; // [rsp+94h] [rbp-6Ch]
  wchar_t *v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+A0h] [rbp-60h]
  int v32; // [rsp+A4h] [rbp-5Ch]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  _QWORD v34[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v35; // [rsp+C0h] [rbp-40h]
  int v36; // [rsp+C4h] [rbp-3Ch]
  CHAR MultiByteStr[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR WideCharStr[1024]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v34[0] = a3;
  v34[1] = 0;
  v27[0] = a3;
  v27[1] = 0;
  v35 = 72;
  v36 = 16;
  v28 = 72;
  v29 = 16;
  v30 = 0;
  v31 = 0;
  v32 = 1;
  v33 = 130;
  v21 = 0;
  v22 = 0;
  String1 = 0;
  v26 = 0;
  v25 = 0;
  NumberOfBytesWritten = 0;
  if ( !a5 || !a2 || !a4 )
    return 2147500035LL;
  ProcAddress = 0;
  LibraryW = LoadLibraryW(L"ComSetup.dll");
  v9 = LibraryW;
  if ( LibraryW )
    ProcAddress = GetProcAddress(LibraryW, "SetupPrintLog");
  *a5 = 0;
  FileW = CreateFileW(a4, 0xC0000000, 0, 0, 3u, 0x80u, 0);
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL || SetFilePointer(FileW, 0, 0, 2u) == -1 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int64 *, _QWORD *, __int64, int, _DWORD, __int64 *))(*(_QWORD *)a2 + 24LL))(
            a2,
            didCOMSERVICES,
            tidCOMSERVICES_LT_ROLEDEFINITION,
            v34,
            1,
            1,
            0,
            &v21);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21);
        if ( v13 >= 0 )
        {
          while ( 1 )
          {
            v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21);
            v13 = v14;
            if ( v14 == -2146367487 )
              break;
            if ( v14 < 0 )
              goto LABEL_40;
            v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v21 + 64LL))(v21, 1, 0);
            if ( v13 < 0 )
              goto LABEL_40;
            if ( !String1 || wcscmp_0(String1, L"IMDB Trusted User") )
            {
              v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v21 + 64LL))(v21, 2, 0);
              if ( v13 < 0 )
                goto LABEL_40;
              v15 = -1;
              v30 = String1;
              do
                ++v15;
              while ( String1[v15] );
              HIDWORD(v33) = 2 * v15 + 2;
              v13 = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int64 *, _QWORD *, __int64, int, _DWORD, __int64 *))(*(_QWORD *)a2 + 24LL))(
                      a2,
                      didCOMSERVICES,
                      tidCOMSERVICES_LT_ROLECONFIG,
                      v27,
                      2,
                      1,
                      0,
                      &v22);
              if ( v13 < 0 )
                goto LABEL_40;
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
              if ( v13 < 0 )
                goto LABEL_40;
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 32LL))(v22);
              if ( v13 < 0 )
                goto LABEL_40;
              while ( 1 )
              {
                v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 40LL))(v22);
                v13 = v16;
                if ( v16 == -2146367487 )
                  break;
                if ( v16 < 0 )
                  goto LABEL_40;
                v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v22 + 64LL))(v22, 2, 0);
                if ( v13 < 0 )
                  goto LABEL_40;
                v13 = StringCchPrintfW(
                        WideCharStr,
                        0x400u,
                        L"%s, \"\"\"%s\"\"\", \"\"\"%s\"\"\",\"\"\"\"\"\",0x00000100, System Application\r\n",
                        String1,
                        v26,
                        v25);
                if ( v13 < 0 )
                  goto LABEL_40;
                if ( WideCharToMultiByte(0, 0, WideCharStr, -1, MultiByteStr, 1024, 0, 0) )
                {
                  v17 = -1;
                  do
                    ++v17;
                  while ( MultiByteStr[v17] );
                  if ( !WriteFile(v11, MultiByteStr, v17, &NumberOfBytesWritten, 0) )
                  {
                    v19 = GetLastError();
                    v13 = v19;
                    if ( v19 > 0 )
                      v13 = (unsigned __int16)v19 | 0x80070000;
                    goto LABEL_40;
                  }
                  ++*a5;
                }
                else if ( ProcAddress )
                {
                  v18 = GetLastError();
                  if ( v18 > 0 )
                    v18 = (unsigned __int16)v18 | 0x80070000;
                  ((void (*)(const wchar_t *, ...))ProcAddress)(
                    L"Failed to write role %s to the catalog - Error code 0x%08x",
                    String1,
                    (unsigned int)v18);
                }
              }
            }
          }
          v13 = 0;
        }
      }
    }
  }
LABEL_40:
  if ( v9 )
    FreeLibrary(v9);
  CloseHandle(v11);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000d110  mov     [rsp-8+arg_0], rbx
0x18000d115  push    rbp
0x18000d116  push    rsi
0x18000d117  push    rdi
0x18000d118  push    r12
0x18000d11a  push    r13
0x18000d11c  push    r14
0x18000d11e  push    r15
0x18000d120  lea     rbp, [rsp-0BE0h]
0x18000d128  sub     rsp, 0CE0h
0x18000d12f  mov     rax, cs:__security_cookie
0x18000d136  xor     rax, rsp
0x18000d139  mov     [rbp+0C10h+var_40], rax
0x18000d140  mov     r14, [rbp+0C10h+arg_20]
0x18000d147  xor     edi, edi
0x18000d149  mov     [rbp+0C10h+var_C60], r8
0x18000d14d  mov     rbx, r9
0x18000d150  mov     [rbp+0C10h+var_C58], rdi
0x18000d154  mov     r13, rdx
0x18000d157  mov     [rbp+0C10h+var_C90], r8
0x18000d15b  mov     [rbp+0C10h+var_C88], rdi
0x18000d15f  lea     ecx, [rdi+48h]
0x18000d162  mov     [rbp+0C10h+var_C50], ecx
0x18000d165  lea     eax, [rdi+10h]
0x18000d168  mov     [rbp+0C10h+var_C4C], eax
0x18000d16b  mov     [rbp+0C10h+var_C80], ecx
0x18000d16e  mov     [rbp+0C10h+var_C7C], eax
0x18000d171  mov     [rbp+0C10h+var_C78], rdi
0x18000d175  mov     [rbp+0C10h+var_C70], edi
0x18000d178  mov     [rbp+0C10h+var_C6C], 1
0x18000d17f  mov     [rbp+0C10h+var_C68], 82h
0x18000d187  mov     [rsp+0D10h+var_CC0], rdi
0x18000d18c  mov     [rsp+0D10h+var_CB8], rdi
0x18000d191  mov     [rsp+0D10h+String1], rdi
0x18000d196  mov     [rsp+0D10h+var_C98], rdi
0x18000d19b  mov     [rsp+0D10h+var_CA0], rdi
0x18000d1a0  mov     [rsp+0D10h+NumberOfBytesWritten], edi
0x18000d1a4  test    r14, r14
0x18000d1a7  jz      loc_18000D5AB
0x18000d1ad  test    rdx, rdx
0x18000d1b0  jz      loc_18000D5AB
0x18000d1b6  test    rbx, rbx
0x18000d1b9  jz      loc_18000D5AB
0x18000d1bf  lea     rcx, aComsetupDll; "ComSetup.dll"
0x18000d1c6  mov     r12d, edi
0x18000d1c9  call    cs:__imp_LoadLibraryW
0x18000d1cf  mov     rsi, rax
0x18000d1d2  test    rax, rax
0x18000d1d5  jz      short loc_18000D1EA
0x18000d1d7  lea     rdx, ProcName; "SetupPrintLog"
0x18000d1de  mov     rcx, rax; hModule
0x18000d1e1  call    cs:__imp_GetProcAddress
0x18000d1e7  mov     r12, rax
0x18000d1ea  mov     [rsp+0D10h+hTemplateFile], rdi; hTemplateFile
0x18000d1ef  xor     r9d, r9d; lpSecurityAttributes
0x18000d1f2  mov     [rsp+0D10h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000d1fa  xor     r8d, r8d; dwShareMode
0x18000d1fd  mov     edx, 0C0000000h; dwDesiredAccess
0x18000d202  mov     [rsp+0D10h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d20a  mov     rcx, rbx; lpFileName
0x18000d20d  mov     [r14], edi
0x18000d210  call    cs:__imp_CreateFileW
0x18000d216  mov     r15, rax
0x18000d219  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d21d  jnz     short loc_18000D23D
0x18000d21f  call    cs:__imp_GetLastError
0x18000d225  mov     ebx, eax
0x18000d227  test    eax, eax
0x18000d229  jle     loc_18000D55D
0x18000d22f  movzx   ebx, ax
0x18000d232  or      ebx, 80070000h
0x18000d238  jmp     loc_18000D55D
0x18000d23d  mov     r9d, 2; dwMoveMethod
0x18000d243  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000d246  xor     edx, edx; lDistanceToMove
0x18000d248  mov     rcx, r15; hFile
0x18000d24b  call    cs:__imp_SetFilePointer
0x18000d251  cmp     eax, 0FFFFFFFFh
0x18000d254  jz      short loc_18000D21F
0x18000d256  mov     rax, [r13+0]
0x18000d25a  lea     rcx, [rsp+0D10h+var_CC0]
0x18000d25f  mov     [rsp+0D10h+lpUsedDefaultChar], rcx
0x18000d264  lea     r9, [rbp+0C10h+var_C60]
0x18000d268  mov     ecx, 1
0x18000d26d  mov     dword ptr [rsp+0D10h+hTemplateFile], edi
0x18000d271  mov     [rsp+0D10h+dwFlagsAndAttributes], ecx
0x18000d275  lea     r8, tidCOMSERVICES_LT_ROLEDEFINITION
0x18000d27c  mov     rax, [rax+18h]
0x18000d280  lea     rdx, didCOMSERVICES
0x18000d287  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rcx
0x18000d28c  mov     rcx, r13
0x18000d28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d294  mov     ebx, eax
0x18000d296  test    eax, eax
0x18000d298  js      loc_18000D55D
0x18000d29e  mov     rcx, [rsp+0D10h+var_CC0]
0x18000d2a3  mov     rax, [rcx]
0x18000d2a6  mov     rax, [rax+18h]
0x18000d2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2af  mov     ebx, eax
0x18000d2b1  test    eax, eax
0x18000d2b3  js      loc_18000D55D
0x18000d2b9  mov     rcx, [rsp+0D10h+var_CC0]
0x18000d2be  mov     rax, [rcx]
0x18000d2c1  mov     rax, [rax+20h]
0x18000d2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2ca  mov     ebx, eax
0x18000d2cc  test    eax, eax
0x18000d2ce  js      loc_18000D55D
0x18000d2d4  mov     edi, 80070000h
0x18000d2d9  mov     rcx, [rsp+0D10h+var_CC0]
0x18000d2de  mov     rax, [rcx]
0x18000d2e1  mov     rax, [rax+28h]
0x18000d2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2ea  mov     ebx, eax
0x18000d2ec  cmp     eax, 80110801h
0x18000d2f1  jz      loc_18000D55B
0x18000d2f7  test    eax, eax
0x18000d2f9  js      loc_18000D55D
0x18000d2ff  mov     rcx, [rsp+0D10h+var_CC0]
0x18000d304  lea     rdx, [rsp+0D10h+String1]
0x18000d309  xor     r9d, r9d
0x18000d30c  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rdx
0x18000d311  xor     r8d, r8d
0x18000d314  mov     rax, [rcx]
0x18000d317  lea     edx, [r9+1]
0x18000d31b  mov     rax, [rax+40h]
0x18000d31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d324  mov     ebx, eax
0x18000d326  test    eax, eax
0x18000d328  js      loc_18000D55D
0x18000d32e  mov     rcx, [rsp+0D10h+String1]; String1
0x18000d333  test    rcx, rcx
0x18000d336  jz      short loc_18000D348
0x18000d338  lea     rdx, aImdbTrustedUse; "IMDB Trusted User"
0x18000d33f  call    wcscmp_0
0x18000d344  test    eax, eax
0x18000d346  jz      short loc_18000D2D9
0x18000d348  mov     rcx, [rsp+0D10h+var_CC0]
0x18000d34d  lea     rdx, [rsp+0D10h+var_C98]
0x18000d352  xor     r9d, r9d
0x18000d355  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rdx
0x18000d35a  xor     r8d, r8d
0x18000d35d  mov     rax, [rcx]
0x18000d360  lea     edx, [r9+2]
0x18000d364  mov     rax, [rax+40h]
0x18000d368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d36d  mov     ebx, eax
0x18000d36f  test    eax, eax
0x18000d371  js      loc_18000D55D
0x18000d377  mov     rcx, [rsp+0D10h+String1]
0x18000d37c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d380  mov     [rbp+0C10h+var_C78], rcx
0x18000d384  xor     ebx, ebx
0x18000d386  inc     rax
0x18000d389  cmp     [rcx+rax*2], bx
0x18000d38d  jnz     short loc_18000D386
0x18000d38f  lea     eax, ds:2[rax*2]
0x18000d396  mov     dword ptr [rbp+0C10h+var_C68+4], eax
0x18000d399  lea     rcx, [rsp+0D10h+var_CB8]
0x18000d39e  mov     rax, [r13+0]
0x18000d3a2  lea     r9, [rbp+0C10h+var_C90]
0x18000d3a6  mov     [rsp+0D10h+lpUsedDefaultChar], rcx
0x18000d3ab  lea     r8, tidCOMSERVICES_LT_ROLECONFIG
0x18000d3b2  mov     dword ptr [rsp+0D10h+hTemplateFile], ebx
0x18000d3b6  lea     rdx, didCOMSERVICES
0x18000d3bd  mov     [rsp+0D10h+dwFlagsAndAttributes], 1
0x18000d3c5  mov     rcx, r13
0x18000d3c8  mov     rax, [rax+18h]
0x18000d3cc  mov     qword ptr [rsp+0D10h+dwCreationDisposition], 2
0x18000d3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3da  mov     ebx, eax
0x18000d3dc  test    eax, eax
0x18000d3de  js      loc_18000D55D
0x18000d3e4  mov     rcx, [rsp+0D10h+var_CB8]
0x18000d3e9  mov     rax, [rcx]
0x18000d3ec  mov     rax, [rax+18h]
0x18000d3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3f5  mov     ebx, eax
0x18000d3f7  test    eax, eax
0x18000d3f9  js      loc_18000D55D
0x18000d3ff  mov     rcx, [rsp+0D10h+var_CB8]
0x18000d404  mov     rax, [rcx]
0x18000d407  mov     rax, [rax+20h]
0x18000d40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d410  mov     ebx, eax
0x18000d412  test    eax, eax
0x18000d414  js      loc_18000D55D
0x18000d41a  mov     rcx, [rsp+0D10h+var_CB8]
0x18000d41f  mov     rax, [rcx]
0x18000d422  mov     rax, [rax+28h]
0x18000d426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d42b  mov     ebx, eax
0x18000d42d  cmp     eax, 80110801h
0x18000d432  jz      loc_18000D2D9
0x18000d438  test    eax, eax
0x18000d43a  js      loc_18000D55D
0x18000d440  mov     rcx, [rsp+0D10h+var_CB8]
0x18000d445  lea     rdx, [rsp+0D10h+var_CA0]
0x18000d44a  xor     r9d, r9d
0x18000d44d  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rdx
0x18000d452  xor     r8d, r8d
0x18000d455  mov     rax, [rcx]
0x18000d458  lea     edx, [r9+2]
0x18000d45c  mov     rax, [rax+40h]
0x18000d460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d465  mov     ebx, eax
0x18000d467  test    eax, eax
0x18000d469  js      loc_18000D55D
0x18000d46f  mov     rax, [rsp+0D10h+var_CA0]
0x18000d474  lea     r8, aSSS0x00000100S; "%s, \"\"\"%s\"\"\", \"\"\"%s\"\"\",\"\""...
0x18000d47b  mov     r9, [rsp+0D10h+String1]
0x18000d480  lea     rcx, [rbp+0C10h+WideCharStr]; unsigned __int16 *
0x18000d487  mov     qword ptr [rsp+0D10h+dwFlagsAndAttributes], rax
0x18000d48c  mov     edx, 400h; unsigned __int64
0x18000d491  mov     rax, [rsp+0D10h+var_C98]
0x18000d496  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax
0x18000d49b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d4a0  mov     ebx, eax
0x18000d4a2  test    eax, eax
0x18000d4a4  js      loc_18000D55D
0x18000d4aa  xor     ebx, ebx
0x18000d4ac  lea     rax, [rbp+0C10h+MultiByteStr]
0x18000d4b0  mov     [rsp+0D10h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x18000d4b5  lea     r8, [rbp+0C10h+WideCharStr]; lpWideCharStr
0x18000d4bc  mov     [rsp+0D10h+hTemplateFile], rbx; lpDefaultChar
0x18000d4c1  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000d4c5  mov     [rsp+0D10h+dwFlagsAndAttributes], 400h; cbMultiByte
0x18000d4cd  xor     edx, edx; dwFlags
0x18000d4cf  xor     ecx, ecx; CodePage
0x18000d4d1  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rax; lpMultiByteStr
0x18000d4d6  call    cs:__imp_WideCharToMultiByte
0x18000d4dc  test    eax, eax
0x18000d4de  jz      short loc_18000D514
0x18000d4e0  lea     rax, [rbp+0C10h+MultiByteStr]
0x18000d4e4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d4e8  inc     r8; nNumberOfBytesToWrite
0x18000d4eb  cmp     [rax+r8], bl
0x18000d4ef  jnz     short loc_18000D4E8
0x18000d4f1  lea     r9, [rsp+0D10h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000d4f6  mov     qword ptr [rsp+0D10h+dwCreationDisposition], rbx; lpOverlapped
0x18000d4fb  lea     rdx, [rbp+0C10h+MultiByteStr]; lpBuffer
0x18000d4ff  mov     rcx, r15; hFile
0x18000d502  call    cs:__imp_WriteFile
0x18000d508  test    eax, eax
0x18000d50a  jz      short loc_18000D548
0x18000d50c  inc     dword ptr [r14]
0x18000d50f  jmp     loc_18000D41A
0x18000d514  test    r12, r12
0x18000d517  jz      loc_18000D41A
0x18000d51d  call    cs:__imp_GetLastError
0x18000d523  test    eax, eax
0x18000d525  jle     short loc_18000D52C
0x18000d527  movzx   eax, ax
0x18000d52a  or      eax, edi
0x18000d52c  mov     rdx, [rsp+0D10h+String1]
0x18000d531  lea     rcx, aFailedToWriteR; "Failed to write role %s to the catalog "...
0x18000d538  mov     r8d, eax
0x18000d53b  mov     rax, r12
0x18000d53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d543  jmp     loc_18000D41A
0x18000d548  call    cs:__imp_GetLastError
0x18000d54e  mov     ebx, eax
0x18000d550  test    eax, eax
0x18000d552  jle     short loc_18000D55D
0x18000d554  movzx   ebx, ax
0x18000d557  or      ebx, edi
0x18000d559  jmp     short loc_18000D55D
0x18000d55b  xor     ebx, ebx
0x18000d55d  test    rsi, rsi
0x18000d560  jz      short loc_18000D56B
0x18000d562  mov     rcx, rsi; hLibModule
0x18000d565  call    cs:__imp_FreeLibrary
0x18000d56b  mov     rcx, r15; hObject
0x18000d56e  call    cs:__imp_CloseHandle
0x18000d574  mov     rcx, [rsp+0D10h+var_CC0]
0x18000d579  xor     esi, esi
0x18000d57b  test    rcx, rcx
0x18000d57e  jz      short loc_18000D591
0x18000d580  mov     rax, [rcx]
0x18000d583  mov     rax, [rax+10h]
0x18000d587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d58c  mov     [rsp+0D10h+var_CC0], rsi
0x18000d591  mov     rcx, [rsp+0D10h+var_CB8]
0x18000d596  test    rcx, rcx
0x18000d599  jz      short loc_18000D5A7
0x18000d59b  mov     rax, [rcx]
0x18000d59e  mov     rax, [rax+10h]
0x18000d5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5a7  mov     eax, ebx
0x18000d5a9  jmp     short loc_18000D5B0
0x18000d5ab  mov     eax, 80004003h
0x18000d5b0  mov     rcx, [rbp+0C10h+var_40]
0x18000d5b7  xor     rcx, rsp; StackCookie
0x18000d5ba  call    __security_check_cookie
0x18000d5bf  mov     rbx, [rsp+0D10h+arg_0]
0x18000d5c7  add     rsp, 0CE0h
0x18000d5ce  pop     r15
0x18000d5d0  pop     r14
0x18000d5d2  pop     r13
  ... truncated ...
```
