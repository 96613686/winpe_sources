# CreateDestinationFile(uint)

- ea: `0x18007f080`
- end: `0x18007f426`
- name: `?CreateDestinationFile@@YA_JI@Z`
- size: `934`
- prototype: `__int64 __fastcall(LONG lDistanceToMove)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007b088`

## callees

- `0x180025904`
- `0x180026ffc`
- `0x180068680`
- `0x180071494`
- `0x18007f080`
- `0x18007f42c`
- `0x18007f9c0`
- `0x18007fa28`
- `0x18007fb08`
- `0x18007fb34`
- `0x180203600`
- `0x180259868`
- `0x1802598ac`
- `0x18025c010`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x18007f20d`
- `KERNEL32!SetEndOfFile` at `0x18007f20d`
- `KERNEL32!CloseHandle` at `0x18007f23e`
- `KERNEL32!CloseHandle` at `0x18007f23e`
- `KERNEL32!GetLastError` at `0x18007f1a3`
- `KERNEL32!GetLastError` at `0x18007f232`
- `KERNEL32!GetLastError` at `0x18007f1a3`
- `KERNEL32!GetLastError` at `0x18007f232`
- `KERNEL32!SetFilePointer` at `0x18007f1e5`
- `KERNEL32!SetFilePointer` at `0x18007f1ff`
- `KERNEL32!SetFilePointer` at `0x18007f223`
- `KERNEL32!SetFilePointer` at `0x18007f1e5`
- `KERNEL32!SetFilePointer` at `0x18007f1ff`
- `KERNEL32!SetFilePointer` at `0x18007f223`

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
0x18007f080  mov     [rsp-28h+arg_0], rbx
0x18007f085  push    rbp
0x18007f086  push    rdi
0x18007f087  push    r12
0x18007f089  push    r14
0x18007f08b  push    r15
0x18007f08d  mov     rbp, rsp
0x18007f090  sub     rsp, 40h
0x18007f094  mov     r12d, ecx
0x18007f097  call    FoundUnUsedHandle
0x18007f09c  mov     r15d, eax
0x18007f09f  test    eax, eax
0x18007f0a1  jle     loc_18007F410
0x18007f0a7  mov     rcx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007f0ae  cmp     qword ptr [rcx+0A68h], 0
0x18007f0b6  jnz     loc_18007F323
0x18007f0bc  cmp     byte ptr [rcx+0A78h], 0
0x18007f0c3  jnz     loc_18007F323
0x18007f0c9  mov     dl, [rcx+0AA0h]; bool
0x18007f0cf  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18007f0d6  lea     rcx, [rbp+arg_10]; this
0x18007f0da  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18007f0df  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18007f0e6  lea     r8, [rbp+arg_8]
0x18007f0ea  mov     rdx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007f0f1  mov     rcx, rbx
0x18007f0f4  add     rdx, 828h
0x18007f0fb  mov     [rbp+arg_8], rbx
0x18007f0ff  mov     rax, [rax+60h]
0x18007f103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f108  mov     rcx, [rbp+arg_8]
0x18007f10c  lea     r9, [rbp+arg_8]
0x18007f110  mov     edx, 6
0x18007f115  mov     rax, [rcx]
0x18007f118  lea     r8d, [rdx+56h]
0x18007f11c  mov     rax, [rax+0C0h]
0x18007f123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f128  mov     rdx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007f12f  cmp     byte ptr [rdx+0AA0h], 0
0x18007f136  jnz     short loc_18007F178
0x18007f138  cmp     dword ptr [rdx+0A50h], 2
0x18007f13f  jz      short loc_18007F178
0x18007f141  mov     rcx, [rbp+arg_8]
0x18007f145  mov     rax, [rcx]
0x18007f148  mov     rax, [rax+50h]
0x18007f14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f151  mov     rcx, rax; lpFileName
0x18007f154  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x18007f159  test    al, al
0x18007f15b  jz      short loc_18007F171
0x18007f15d  mov     dil, 1
0x18007f160  mov     cl, dil
0x18007f163  call    ?StartFdiImpersonating@@YA?AW4Bool@@_N@Z; StartFdiImpersonating(bool)
0x18007f168  mov     rdx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007f16f  jmp     short loc_18007F17B
0x18007f171  mov     rdx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007f178  xor     dil, dil
0x18007f17b  mov     r8d, [rdx+0A30h]
0x18007f182  lea     rcx, [rdx+828h]
0x18007f189  mov     rdx, [rdx+0A98h]
0x18007f190  mov     r9b, dil
0x18007f193  mov     dword ptr [rsp+40h+var_20], 0; struct _FILETIME *
0x18007f19b  call    ?MsiCreateFileWithUserAccessCheck@@YAPEAXPEBGPEAU_SECURITY_ATTRIBUTES@@K_NW4ielfEnum@@@Z; MsiCreateFileWithUserAccessCheck(ushort const *,_SECURITY_ATTRIBUTES *,ulong,bool,ielfEnum)
0x18007f1a0  mov     rbx, rax
0x18007f1a3  call    cs:__imp_GetLastError
0x18007f1a9  mov     r14d, eax
0x18007f1ac  test    dil, dil
0x18007f1af  jz      short loc_18007F1B8
0x18007f1b1  mov     cl, 1; bool
0x18007f1b3  call    ?StopFdiImpersonating@@YAX_N@Z; StopFdiImpersonating(bool)
0x18007f1b8  mov     rcx, [rbp+arg_8]
0x18007f1bc  mov     rax, [rcx]
0x18007f1bf  mov     rax, [rax+10h]
0x18007f1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f1c8  lea     rcx, [rbp+arg_10]; this
0x18007f1cc  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18007f1d1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007f1d5  jz      short loc_18007F248
0x18007f1d7  mov     r9d, 1; dwMoveMethod
0x18007f1dd  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007f1e0  xor     edx, edx; lDistanceToMove
0x18007f1e2  mov     rcx, rbx; hFile
0x18007f1e5  call    cs:__imp_SetFilePointer
0x18007f1eb  mov     r14d, eax
0x18007f1ee  cmp     eax, 0FFFFFFFFh
0x18007f1f1  jz      short loc_18007F232
0x18007f1f3  xor     r9d, r9d; dwMoveMethod
0x18007f1f6  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007f1f9  mov     edx, r12d; lDistanceToMove
0x18007f1fc  mov     rcx, rbx; hFile
0x18007f1ff  call    cs:__imp_SetFilePointer
0x18007f205  cmp     eax, 0FFFFFFFFh
0x18007f208  jz      short loc_18007F232
0x18007f20a  mov     rcx, rbx; hFile
0x18007f20d  call    cs:__imp_SetEndOfFile
0x18007f213  test    eax, eax
0x18007f215  jz      short loc_18007F232
0x18007f217  xor     r9d, r9d; dwMoveMethod
0x18007f21a  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007f21d  mov     edx, r14d; lDistanceToMove
0x18007f220  mov     rcx, rbx; hFile
0x18007f223  call    cs:__imp_SetFilePointer
0x18007f229  cmp     eax, 0FFFFFFFFh
0x18007f22c  jnz     loc_18007F2D7
0x18007f232  call    cs:__imp_GetLastError
0x18007f238  mov     rcx, rbx; hObject
0x18007f23b  mov     r14d, eax
0x18007f23e  call    cs:__imp_CloseHandle
0x18007f244  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007f248  cmp     r14d, 5
0x18007f24c  jnz     short loc_18007F2A7
0x18007f24e  test    dil, dil
0x18007f251  jz      short loc_18007F25A
0x18007f253  mov     cl, 1
0x18007f255  call    ?StartFdiImpersonating@@YA?AW4Bool@@_N@Z; StartFdiImpersonating(bool)
0x18007f25a  mov     rcx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007f261  xor     r9d, r9d; struct _FILETIME *
0x18007f264  add     rcx, 828h; lpFileName
0x18007f26b  mov     [rsp+40h+var_18], 0; struct _FILETIME *
0x18007f274  xor     r8d, r8d; unsigned __int64 *
0x18007f277  xor     edx, edx; unsigned int *
0x18007f279  call    ?MsiGetFileAttributesEx@@YAKPEBGPEAKPEA_KPEAU_FILETIME@@33@Z; MsiGetFileAttributesEx(ushort const *,ulong *,unsigned __int64 *,_FILETIME *,_FILETIME *,_FILETIME *)
0x18007f27e  mov     r14d, eax
0x18007f281  test    dil, dil
0x18007f284  jz      short loc_18007F28D
0x18007f286  mov     cl, 1; bool
0x18007f288  call    ?StopFdiImpersonating@@YAX_N@Z; StopFdiImpersonating(bool)
0x18007f28d  cmp     r14d, 0FFFFFFFFh
0x18007f291  jz      short loc_18007F2A0
0x18007f293  test    r14b, 10h
0x18007f297  jz      short loc_18007F2A0
0x18007f299  mov     ecx, 1Bh
0x18007f29e  jmp     short loc_18007F2B6
0x18007f2a0  mov     ecx, 12h
0x18007f2a5  jmp     short loc_18007F2B6
0x18007f2a7  mov     ecx, 12h
0x18007f2ac  cmp     r14d, 70h ; 'p'
0x18007f2b0  lea     eax, [rcx+7]
0x18007f2b3  cmovz   ecx, eax
0x18007f2b6  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, ecx; FDIServerResponse g_fdirCallbackError
0x18007f2bc  call    ?WaitCommand@@YA?AW4FDIServerCommand@@W4FDIServerResponse@@@Z; WaitCommand(FDIServerResponse)
0x18007f2c1  cmp     eax, 5
0x18007f2c4  jz      short loc_18007F2F8
0x18007f2c6  cmp     eax, 6
0x18007f2c9  jz      short loc_18007F2E3
0x18007f2cb  mov     rcx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007f2d2  jmp     loc_18007F0C9
0x18007f2d7  mov     rcx, rbx
0x18007f2da  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x18007f2df  test    eax, eax
0x18007f2e1  jmp     short loc_18007F306
0x18007f2e3  xor     ecx, ecx
0x18007f2e5  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 1Ch; FDIServerResponse g_fdirCallbackError
0x18007f2ef  call    ?WaitCommand@@YA?AW4FDIServerCommand@@W4FDIServerResponse@@@Z; WaitCommand(FDIServerResponse)
0x18007f2f4  xor     ebx, ebx
0x18007f2f6  jmp     short loc_18007F30C
0x18007f2f8  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 0Eh; FDIServerResponse g_fdirCallbackError
0x18007f302  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007f306  jz      loc_18007F410
0x18007f30c  mov     r8, rbx
0x18007f30f  mov     edx, 3
0x18007f314  mov     ecx, r15d
0x18007f317  call    SetHandleMap
0x18007f31c  cdqe
0x18007f31e  jmp     loc_18007F414
0x18007f323  mov     [rbp+arg_8], 0
0x18007f32b  mov     r10, [rcx+0A68h]
0x18007f332  test    r10, r10
0x18007f335  jz      short loc_18007F379
0x18007f337  mov     rax, [r10]
0x18007f33a  lea     r8, [rcx+828h]
0x18007f341  xor     r9d, r9d
0x18007f344  mov     [rsp+40h+var_10], 0
0x18007f34d  cmp     [rcx+0A79h], r9b
0x18007f354  lea     rcx, [rbp+arg_8]
0x18007f358  mov     [rsp+40h+var_18], rcx
0x18007f35d  mov     rcx, r10
0x18007f360  mov     rax, [rax+18h]
0x18007f364  setnz   r9b
0x18007f368  xor     edx, edx
0x18007f36a  mov     dword ptr [rsp+40h+var_20], 0
0x18007f372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f377  jmp     short loc_18007F3B5
0x18007f379  xor     r8d, r8d
0x18007f37c  lea     rdx, [rcx+828h]; unsigned __int16 *
0x18007f383  cmp     [rcx+0A79h], r8b
0x18007f38a  mov     rcx, [rcx+0A70h]; this
0x18007f391  setnz   r8b; int
0x18007f395  call    ?URTCreateAssemblyFileStream@CMsiCustomActionManager@@QEAAJPEBGH@Z; CMsiCustomActionManager::URTCreateAssemblyFileStream(ushort const *,int)
0x18007f39a  test    eax, eax
0x18007f39c  js      short loc_18007F3B9
0x18007f39e  mov     rax, cs:?CreateStreamOnHGlobal@OLE32@@3P6AJPEAXHPEAPEAUIStream@@@ZEA; long (*OLE32::CreateStreamOnHGlobal)(void *,int,IStream * *)
0x18007f3a5  lea     r8, [rbp+arg_8]
0x18007f3a9  mov     edx, 1
0x18007f3ae  xor     ecx, ecx
0x18007f3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3b5  test    eax, eax
0x18007f3b7  jns     short loc_18007F3E3
0x18007f3b9  mov     ecx, 12h
0x18007f3be  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 12h; FDIServerResponse g_fdirCallbackError
0x18007f3c8  call    ?WaitCommand@@YA?AW4FDIServerCommand@@W4FDIServerResponse@@@Z; WaitCommand(FDIServerResponse)
0x18007f3cd  cmp     eax, 5
0x18007f3d0  jz      short loc_18007F406
0x18007f3d2  cmp     eax, 6
0x18007f3d5  jz      short loc_18007F3F1
0x18007f3d7  mov     rcx, cs:?g_pFDIs@@3PEAUFDIShared@@EA; FDIShared * g_pFDIs
0x18007f3de  jmp     loc_18007F32B
0x18007f3e3  mov     r8, [rbp+arg_8]
0x18007f3e7  mov     edx, 4
0x18007f3ec  jmp     loc_18007F314
0x18007f3f1  xor     ecx, ecx
0x18007f3f3  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 1Ch; FDIServerResponse g_fdirCallbackError
0x18007f3fd  call    ?WaitCommand@@YA?AW4FDIServerCommand@@W4FDIServerResponse@@@Z; WaitCommand(FDIServerResponse)
0x18007f402  xor     eax, eax
0x18007f404  jmp     short loc_18007F414
0x18007f406  mov     cs:?g_fdirCallbackError@@3W4FDIServerResponse@@A, 0Eh; FDIServerResponse g_fdirCallbackError
0x18007f410  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007f414  mov     rbx, [rsp+40h+arg_0]
0x18007f419  add     rsp, 40h
0x18007f41d  pop     r15
0x18007f41f  pop     r14
0x18007f421  pop     r12
0x18007f423  pop     rdi
0x18007f424  pop     rbp
0x18007f425  retn
```
