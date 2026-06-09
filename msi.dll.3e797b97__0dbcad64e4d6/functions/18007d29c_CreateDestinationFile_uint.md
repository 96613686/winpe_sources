# CreateDestinationFile(uint)

- ea: `0x18007d29c`
- end: `0x18007d671`
- name: `?CreateDestinationFile@@YA_JI@Z`
- size: `981`
- prototype: `__int64 __fastcall(LONG lDistanceToMove)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180079110`

## callees

- `0x180014528`
- `0x180016154`
- `0x180067fec`
- `0x18007d29c`
- `0x18007d678`
- `0x18007dc8c`
- `0x18007dd00`
- `0x18007ddf0`
- `0x18007de20`
- `0x180097608`
- `0x18020c928`
- `0x180263df8`
- `0x180263e3c`
- `0x180266010`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x18007d43f`
- `KERNEL32!SetEndOfFile` at `0x18007d43f`
- `KERNEL32!CloseHandle` at `0x18007d482`
- `KERNEL32!CloseHandle` at `0x18007d482`
- `KERNEL32!GetLastError` at `0x18007d3bf`
- `KERNEL32!GetLastError` at `0x18007d470`
- `KERNEL32!GetLastError` at `0x18007d3bf`
- `KERNEL32!GetLastError` at `0x18007d470`
- `KERNEL32!SetFilePointer` at `0x18007d40b`
- `KERNEL32!SetFilePointer` at `0x18007d42b`
- `KERNEL32!SetFilePointer` at `0x18007d45b`
- `KERNEL32!SetFilePointer` at `0x18007d40b`
- `KERNEL32!SetFilePointer` at `0x18007d42b`
- `KERNEL32!SetFilePointer` at `0x18007d45b`

## pseudocode

```c
__int64 __fastcall CreateDestinationFile(LONG lDistanceToMove)
{
  int found; // r15d
  struct FDIShared *v3; // rcx
  struct FDIShared *v4; // rdx
  const WCHAR *v5; // rax
  __int64 v6; // rcx
  char v7; // di
  __int64 v8; // rbx
  DWORD LastError; // r14d
  __int64 v10; // rcx
  LONG v11; // r14d
  unsigned int FileAttributes; // r14d
  __int64 v13; // rcx
  int v14; // eax
  bool v15; // zf
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v19; // r10
  int v20; // eax
  int v21; // eax
  struct _FILETIME *v22; // [rsp+20h] [rbp-20h]
  void *v23; // [rsp+78h] [rbp+38h] BYREF
  char v24; // [rsp+80h] [rbp+40h] BYREF

  found = FoundUnUsedHandle();
  if ( found <= 0 )
    return -1;
  v3 = g_pFDIs;
  if ( *((_QWORD *)g_pFDIs + 333) || *((_BYTE *)g_pFDIs + 2680) )
  {
    v23 = 0;
    while ( 1 )
    {
      v19 = *((_QWORD *)v3 + 333);
      if ( v19 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, bool, _DWORD, void **, _QWORD))(*(_QWORD *)v19 + 24LL))(
                v19,
                0,
                (__int64)v3 + 2088,
                *((_BYTE *)v3 + 2681) != 0,
                0,
                &v23,
                0);
      }
      else
      {
        if ( (int)CMsiCustomActionManager::URTCreateAssemblyFileStream(
                    *((CMsiCustomActionManager **)v3 + 334),
                    (const unsigned __int16 *)v3 + 1044,
                    *((_BYTE *)v3 + 2681) != 0) < 0 )
          goto LABEL_44;
        v20 = ((__int64 (__fastcall *)(_QWORD, __int64, void **))OLE32::CreateStreamOnHGlobal)(0, 1, &v23);
      }
      if ( v20 >= 0 )
      {
        v16 = (__int64)v23;
        v17 = 4;
        return (int)SetHandleMap((unsigned int)found, v17, v16);
      }
LABEL_44:
      g_fdirCallbackError = 18;
      v21 = WaitCommand(18);
      if ( v21 == 5 )
      {
        g_fdirCallbackError = 14;
        return -1;
      }
      if ( v21 == 6 )
      {
        g_fdirCallbackError = 28;
        WaitCommand(0);
        return 0;
      }
      v3 = g_pFDIs;
    }
  }
  while ( 1 )
  {
    CElevate::CElevate((CElevate *)&v24, *((_BYTE *)v3 + 2720));
    v23 = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *, char *, void **))(MsiString::s_NullString + 96LL))(
      &MsiString::s_NullString,
      (char *)g_pFDIs + 2088,
      &v23);
    (*(void (__fastcall **)(void *, __int64, __int64, void **))(*(_QWORD *)v23 + 192LL))(v23, 6, 92, &v23);
    v4 = g_pFDIs;
    if ( !*((_BYTE *)g_pFDIs + 2720) && *((_DWORD *)g_pFDIs + 660) != 2 )
    {
      v5 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 80LL))(v23);
      if ( GetImpersonationFromPath(v5) )
      {
        v7 = 1;
        LOBYTE(v6) = 1;
        StartFdiImpersonating(v6);
        v4 = g_pFDIs;
        goto LABEL_10;
      }
      v4 = g_pFDIs;
    }
    v7 = 0;
LABEL_10:
    v8 = MsiCreateFileWithUserAccessCheck((const WCHAR *)v4 + 1044, *((_QWORD *)v4 + 339), *((_DWORD *)v4 + 652), v7, 0);
    LastError = GetLastError();
    if ( v7 )
      StopFdiImpersonating(1);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
    CElevate::~CElevate((CElevate *)&v24);
    if ( v8 != -1 )
    {
      v11 = SetFilePointer((HANDLE)v8, 0, 0, 1u);
      if ( v11 != -1
        && SetFilePointer((HANDLE)v8, lDistanceToMove, 0, 0) != -1
        && SetEndOfFile((HANDLE)v8)
        && SetFilePointer((HANDLE)v8, v11, 0, 0) != -1 )
      {
        v15 = (unsigned int)MsiRegisterSysHandle(v8) == 0;
        goto LABEL_35;
      }
      LastError = GetLastError();
      CloseHandle((HANDLE)v8);
      v8 = -1;
    }
    if ( LastError == 5 )
    {
      if ( v7 )
      {
        LOBYTE(v10) = 1;
        StartFdiImpersonating(v10);
      }
      FileAttributes = MsiGetFileAttributesEx((LPCWSTR)g_pFDIs + 1044, 0, 0, 0, v22, 0);
      if ( v7 )
        StopFdiImpersonating(1);
      v13 = FileAttributes == -1 || (FileAttributes & 0x10) == 0 ? 18LL : 27LL;
    }
    else
    {
      v13 = 18;
      if ( LastError == 112 )
        v13 = 25;
    }
    g_fdirCallbackError = v13;
    v14 = WaitCommand(v13);
    if ( v14 == 5 )
      break;
    if ( v14 == 6 )
    {
      g_fdirCallbackError = 28;
      WaitCommand(0);
      v8 = 0;
      goto LABEL_36;
    }
    v3 = g_pFDIs;
  }
  g_fdirCallbackError = 14;
  v15 = v8 == -1;
LABEL_35:
  if ( v15 )
    return -1;
LABEL_36:
  v16 = v8;
  v17 = 3;
  return (int)SetHandleMap((unsigned int)found, v17, v16);
}

```

## disassembly

```asm
0x18007d29c  mov     [rsp-28h+arg_0], rbx
0x18007d2a1  push    rbp
0x18007d2a2  push    rdi
0x18007d2a3  push    r12
0x18007d2a5  push    r14
0x18007d2a7  push    r15
0x18007d2a9  mov     rbp, rsp
0x18007d2ac  sub     rsp, 40h
0x18007d2b0  mov     r12d, ecx
0x18007d2b3  call    FoundUnUsedHandle
0x18007d2b8  mov     r15d, eax
0x18007d2bb  test    eax, eax
0x18007d2bd  jle     loc_18007D65A
0x18007d2c3  mov     rcx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007d2ca  cmp     qword ptr [rcx+0A68h], 0
0x18007d2d2  jnz     loc_18007D56D
0x18007d2d8  cmp     byte ptr [rcx+0A78h], 0
0x18007d2df  jnz     loc_18007D56D
0x18007d2e5  mov     dl, [rcx+0AA0h]; bool
0x18007d2eb  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18007d2f2  lea     rcx, [rbp+arg_10]; this
0x18007d2f6  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18007d2fb  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18007d302  lea     r8, [rbp+arg_8]
0x18007d306  mov     rdx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007d30d  mov     rcx, rbx
0x18007d310  add     rdx, 828h
0x18007d317  mov     [rbp+arg_8], rbx
0x18007d31b  mov     rax, [rax+60h]
0x18007d31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d324  mov     rcx, [rbp+arg_8]
0x18007d328  lea     r9, [rbp+arg_8]
0x18007d32c  mov     edx, 6
0x18007d331  mov     rax, [rcx]
0x18007d334  lea     r8d, [rdx+56h]
0x18007d338  mov     rax, [rax+0C0h]
0x18007d33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d344  mov     rdx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007d34b  cmp     byte ptr [rdx+0AA0h], 0
0x18007d352  jnz     short loc_18007D394
0x18007d354  cmp     dword ptr [rdx+0A50h], 2
0x18007d35b  jz      short loc_18007D394
0x18007d35d  mov     rcx, [rbp+arg_8]
0x18007d361  mov     rax, [rcx]
0x18007d364  mov     rax, [rax+50h]
0x18007d368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d36d  mov     rcx, rax; lpFileName
0x18007d370  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x18007d375  test    al, al
0x18007d377  jz      short loc_18007D38D
0x18007d379  mov     dil, 1
0x18007d37c  mov     cl, dil
0x18007d37f  call    ?StartFdiImpersonating@@YA?AW4Bool@@_N@Z; StartFdiImpersonating(bool)
0x18007d384  mov     rdx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007d38b  jmp     short loc_18007D397
0x18007d38d  mov     rdx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007d394  xor     dil, dil
0x18007d397  mov     r8d, [rdx+0A30h]
0x18007d39e  lea     rcx, [rdx+828h]
0x18007d3a5  mov     rdx, [rdx+0A98h]
0x18007d3ac  mov     r9b, dil
0x18007d3af  mov     dword ptr [rsp+40h+var_20], 0; struct _FILETIME *
0x18007d3b7  call    ?MsiCreateFileWithUserAccessCheck@@YAPEAXPEBGPEAU_SECURITY_ATTRIBUTES@@K_NW4ielfEnum@@@Z; MsiCreateFileWithUserAccessCheck(ushort const *,_SECURITY_ATTRIBUTES *,ulong,bool,ielfEnum)
0x18007d3bc  mov     rbx, rax
0x18007d3bf  call    cs:__imp_GetLastError
0x18007d3c6  nop     dword ptr [rax+rax+00h]
0x18007d3cb  mov     r14d, eax
0x18007d3ce  test    dil, dil
0x18007d3d1  jz      short loc_18007D3DA
0x18007d3d3  mov     cl, 1; bool
0x18007d3d5  call    ?StopFdiImpersonating@@YAX_N@Z; StopFdiImpersonating(bool)
0x18007d3da  mov     rcx, [rbp+arg_8]
0x18007d3de  mov     rax, [rcx]
0x18007d3e1  mov     rax, [rax+10h]
0x18007d3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d3ea  lea     rcx, [rbp+arg_10]; this
0x18007d3ee  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18007d3f3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007d3f7  jz      loc_18007D492
0x18007d3fd  mov     r9d, 1; dwMoveMethod
0x18007d403  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007d406  xor     edx, edx; lDistanceToMove
0x18007d408  mov     rcx, rbx; hFile
0x18007d40b  call    cs:__imp_SetFilePointer
0x18007d412  nop     dword ptr [rax+rax+00h]
0x18007d417  mov     r14d, eax
0x18007d41a  cmp     eax, 0FFFFFFFFh
0x18007d41d  jz      short loc_18007D470
0x18007d41f  xor     r9d, r9d; dwMoveMethod
0x18007d422  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007d425  mov     edx, r12d; lDistanceToMove
0x18007d428  mov     rcx, rbx; hFile
0x18007d42b  call    cs:__imp_SetFilePointer
0x18007d432  nop     dword ptr [rax+rax+00h]
0x18007d437  cmp     eax, 0FFFFFFFFh
0x18007d43a  jz      short loc_18007D470
0x18007d43c  mov     rcx, rbx; hFile
0x18007d43f  call    cs:__imp_SetEndOfFile
0x18007d446  nop     dword ptr [rax+rax+00h]
0x18007d44b  test    eax, eax
0x18007d44d  jz      short loc_18007D470
0x18007d44f  xor     r9d, r9d; dwMoveMethod
0x18007d452  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007d455  mov     edx, r14d; lDistanceToMove
0x18007d458  mov     rcx, rbx; hFile
0x18007d45b  call    cs:__imp_SetFilePointer
0x18007d462  nop     dword ptr [rax+rax+00h]
0x18007d467  cmp     eax, 0FFFFFFFFh
0x18007d46a  jnz     loc_18007D521
0x18007d470  call    cs:__imp_GetLastError
0x18007d477  nop     dword ptr [rax+rax+00h]
0x18007d47c  mov     rcx, rbx; hObject
0x18007d47f  mov     r14d, eax
0x18007d482  call    cs:__imp_CloseHandle
0x18007d489  nop     dword ptr [rax+rax+00h]
0x18007d48e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007d492  cmp     r14d, 5
0x18007d496  jnz     short loc_18007D4F1
0x18007d498  test    dil, dil
0x18007d49b  jz      short loc_18007D4A4
0x18007d49d  mov     cl, 1
0x18007d49f  call    ?StartFdiImpersonating@@YA?AW4Bool@@_N@Z; StartFdiImpersonating(bool)
0x18007d4a4  mov     rcx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007d4ab  xor     r9d, r9d; struct _FILETIME *
0x18007d4ae  add     rcx, 828h; lpFileName
0x18007d4b5  mov     [rsp+40h+var_18], 0; struct _FILETIME *
0x18007d4be  xor     r8d, r8d; unsigned __int64 *
0x18007d4c1  xor     edx, edx; unsigned int *
0x18007d4c3  call    ?MsiGetFileAttributesEx@@YAKPEBGPEAKPEA_KPEAU_FILETIME@@33@Z; MsiGetFileAttributesEx(ushort const *,ulong *,unsigned __int64 *,_FILETIME *,_FILETIME *,_FILETIME *)
0x18007d4c8  mov     r14d, eax
0x18007d4cb  test    dil, dil
0x18007d4ce  jz      short loc_18007D4D7
0x18007d4d0  mov     cl, 1; bool
0x18007d4d2  call    ?StopFdiImpersonating@@YAX_N@Z; StopFdiImpersonating(bool)
0x18007d4d7  cmp     r14d, 0FFFFFFFFh
0x18007d4db  jz      short loc_18007D4EA
0x18007d4dd  test    r14b, 10h
0x18007d4e1  jz      short loc_18007D4EA
0x18007d4e3  mov     ecx, 1Bh
0x18007d4e8  jmp     short loc_18007D500
0x18007d4ea  mov     ecx, 12h
0x18007d4ef  jmp     short loc_18007D500
0x18007d4f1  mov     ecx, 12h
0x18007d4f6  cmp     r14d, 70h ; 'p'
0x18007d4fa  lea     eax, [rcx+7]
0x18007d4fd  cmovz   ecx, eax
0x18007d500  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, ecx; FDIServerResponse g_fdirCallbackError
0x18007d506  call    ?WaitCommand@@YA?AW4FDIServerCommand@@W4FDIServerResponse@@@Z; WaitCommand(FDIServerResponse)
0x18007d50b  cmp     eax, 5
0x18007d50e  jz      short loc_18007D542
0x18007d510  cmp     eax, 6
0x18007d513  jz      short loc_18007D52D
0x18007d515  mov     rcx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007d51c  jmp     loc_18007D2E5
0x18007d521  mov     rcx, rbx
0x18007d524  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x18007d529  test    eax, eax
0x18007d52b  jmp     short loc_18007D550
0x18007d52d  xor     ecx, ecx
0x18007d52f  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 1Ch; FDIServerResponse g_fdirCallbackError
0x18007d539  call    ?WaitCommand@@YA?AW4FDIServerCommand@@W4FDIServerResponse@@@Z; WaitCommand(FDIServerResponse)
0x18007d53e  xor     ebx, ebx
0x18007d540  jmp     short loc_18007D556
0x18007d542  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 0Eh; FDIServerResponse g_fdirCallbackError
0x18007d54c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007d550  jz      loc_18007D65A
0x18007d556  mov     r8, rbx
0x18007d559  mov     edx, 3
0x18007d55e  mov     ecx, r15d
0x18007d561  call    SetHandleMap
0x18007d566  cdqe
0x18007d568  jmp     loc_18007D65E
0x18007d56d  mov     [rbp+arg_8], 0
0x18007d575  mov     r10, [rcx+0A68h]
0x18007d57c  test    r10, r10
0x18007d57f  jz      short loc_18007D5C3
0x18007d581  mov     rax, [r10]
0x18007d584  lea     r8, [rcx+828h]
0x18007d58b  xor     r9d, r9d
0x18007d58e  mov     [rsp+40h+var_10], 0
0x18007d597  cmp     [rcx+0A79h], r9b
0x18007d59e  lea     rcx, [rbp+arg_8]
0x18007d5a2  mov     [rsp+40h+var_18], rcx
0x18007d5a7  mov     rcx, r10
0x18007d5aa  mov     rax, [rax+18h]
0x18007d5ae  setnz   r9b
0x18007d5b2  xor     edx, edx
0x18007d5b4  mov     dword ptr [rsp+40h+var_20], 0
0x18007d5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d5c1  jmp     short loc_18007D5FF
0x18007d5c3  xor     r8d, r8d
0x18007d5c6  lea     rdx, [rcx+828h]; unsigned __int16 *
0x18007d5cd  cmp     [rcx+0A79h], r8b
0x18007d5d4  mov     rcx, [rcx+0A70h]; this
0x18007d5db  setnz   r8b; int
0x18007d5df  call    ?URTCreateAssemblyFileStream@CMsiCustomActionManager@@QEAAJPEBGH@Z; CMsiCustomActionManager::URTCreateAssemblyFileStream(ushort const *,int)
0x18007d5e4  test    eax, eax
0x18007d5e6  js      short loc_18007D603
0x18007d5e8  mov     rax, cs:?CreateStreamOnHGlobal@OLE32@@3P6AJPEAXHPEAPEAUIStream@@@ZEA; long (*OLE32::CreateStreamOnHGlobal)(void *,int,IStream * *)
0x18007d5ef  lea     r8, [rbp+arg_8]
0x18007d5f3  mov     edx, 1
0x18007d5f8  xor     ecx, ecx
0x18007d5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d5ff  test    eax, eax
0x18007d601  jns     short loc_18007D62D
0x18007d603  mov     ecx, 12h
0x18007d608  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 12h; FDIServerResponse g_fdirCallbackError
0x18007d612  call    ?WaitCommand@@YA?AW4FDIServerCommand@@W4FDIServerResponse@@@Z; WaitCommand(FDIServerResponse)
0x18007d617  cmp     eax, 5
0x18007d61a  jz      short loc_18007D650
0x18007d61c  cmp     eax, 6
0x18007d61f  jz      short loc_18007D63B
0x18007d621  mov     rcx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007d628  jmp     loc_18007D575
0x18007d62d  mov     r8, [rbp+arg_8]
0x18007d631  mov     edx, 4
0x18007d636  jmp     loc_18007D55E
0x18007d63b  xor     ecx, ecx
0x18007d63d  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 1Ch; FDIServerResponse g_fdirCallbackError
0x18007d647  call    ?WaitCommand@@YA?AW4FDIServerCommand@@W4FDIServerResponse@@@Z; WaitCommand(FDIServerResponse)
0x18007d64c  xor     eax, eax
0x18007d64e  jmp     short loc_18007D65E
0x18007d650  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 0Eh; FDIServerResponse g_fdirCallbackError
0x18007d65a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007d65e  mov     rbx, [rsp+40h+arg_0]
0x18007d663  add     rsp, 40h
0x18007d667  pop     r15
0x18007d669  pop     r14
0x18007d66b  pop     r12
0x18007d66d  pop     rdi
0x18007d66e  pop     rbp
0x18007d66f  retn
```
