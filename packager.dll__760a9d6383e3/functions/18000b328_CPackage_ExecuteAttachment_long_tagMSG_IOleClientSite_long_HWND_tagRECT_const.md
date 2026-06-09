# CPackage::_ExecuteAttachment(long,tagMSG *,IOleClientSite *,long,HWND__ *,tagRECT const *)

- ea: `0x18000b328`
- end: `0x18000b79a`
- name: `?_ExecuteAttachment@CPackage@@IEAAJJPEAUtagMSG@@PEAUIOleClientSite@@JPEAUHWND__@@PEBUtagRECT@@@Z`
- size: `1138`
- prototype: `__int64 __fastcall(CPackage *__hidden this, int, struct tagMSG *, struct IOleClientSite *, int, HWND, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800050b0`

## callees

- `0x180005f5c`
- `0x18000ae84`
- `0x18000b328`
- `0x18000cbbe`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18000b705`
- `SHELL32!ShellExecuteExW` at `0x18000b705`
- `SHLWAPI!PathFindExtensionW` at `0x18000b5d8`
- `SHLWAPI!PathFindExtensionW` at `0x18000b5d8`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18000b40f`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18000b40f`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b73d`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18000b73d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b4aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b69c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b4aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b69c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b627`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b440`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b440`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b614`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b614`
- `USER32!DestroyWindow` at `0x18000b76f`
- `USER32!DestroyWindow` at `0x18000b76f`
- `USER32!MessageBoxW` at `0x18000b6c1`
- `USER32!MessageBoxW` at `0x18000b6c1`

## pseudocode

```c
__int64 __fastcall CPackage::_ExecuteAttachment(
        CPackage *this,
        int a2,
        struct tagMSG *a3,
        struct IOleClientSite *a4,
        int a5,
        HWND a6,
        const struct tagRECT *a7)
{
  HWND v11; // rbx
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v13; // rcx
  HRESULT Instance; // edi
  _DWORD *v15; // rax
  WCHAR *v16; // r8
  __int64 v17; // rcx
  WCHAR *v18; // rax
  __int64 v19; // rdx
  WCHAR *v20; // rcx
  LPWSTR ExtensionW; // rax
  char *FileW; // rax
  int v23; // eax
  bool v24; // zf
  struct IAttachmentExecute *v25; // rcx
  struct IAttachmentExecute *ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  HWND hWnd[2]; // [rsp+50h] [rbp-B0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[80]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszPath[264]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v33[240]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR Text[512]; // [rsp+560h] [rbp+460h] BYREF

  hWnd[0] = a6;
  v11 = 0;
  if ( !a6 )
  {
    if ( a3 && a3->hwnd )
    {
      hWnd[0] = a3->hwnd;
    }
    else
    {
      v12 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 22);
      if ( v12 )
      {
        v28 = 0;
        if ( (**v12)(v12, &GUID_00000114_0000_0000_c000_000000000046, &v28) >= 0 )
          (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v28 + 24LL))(v28, hWnd);
        v13 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
    }
    if ( !hWnd[0] )
    {
      v11 = (HWND)SHCreateWorkerWindowW(0, -3, 0);
      hWnd[0] = v11;
    }
  }
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_AttachmentServices,
               0,
               1u,
               &GUID_73db1241_1e85_4581_8e4f_a81e1d0f8c57,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IAttachmentExecute *, const wchar_t *))ppv->lpVtbl->SetReferrer)(
                 ppv,
                 L"about:internet");
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(struct IAttachmentExecute *, GUID *))ppv->lpVtbl->SetClientGuid)(
                   ppv,
                   &CLSID_CPackage);
      if ( Instance >= 0 )
      {
        if ( (unsigned int)(LoadStringW(g_hinst, 0xBC5u, Buffer, 80) - 1) > 0x4F )
        {
          Instance = -2147024774;
          goto LABEL_48;
        }
        Instance = ((__int64 (__fastcall *)(struct IAttachmentExecute *, WCHAR *))ppv->lpVtbl->SetClientTitle)(
                     ppv,
                     Buffer);
        if ( Instance < 0 )
          goto LABEL_48;
        if ( *((_DWORD *)this + 26) != 1 )
        {
          if ( *((_DWORD *)this + 26) == 3 )
          {
            if ( *((_QWORD *)this + 14) )
              Instance = CPackage::_ActivateEmbeddedFile(this, a2, a3, a4, a5, hWnd[0], a7, ppv);
            else
              Instance = 262529;
          }
          goto LABEL_48;
        }
        v15 = (_DWORD *)*((_QWORD *)this + 15);
        if ( !v15 || !*v15 && !gCmdLineOK )
        {
          Instance = -2147467259;
          ShellMessageBoxW(g_hinst, 0, (LPCWSTR)0xBBF, (LPCWSTR)0xBB8, 0x2010u);
          goto LABEL_48;
        }
        v16 = (WCHAR *)(v15 + 1);
        v17 = 2147483646;
        v18 = pszPath;
        v19 = 260;
        do
        {
          if ( !v17 )
            break;
          if ( !*v16 )
            break;
          *v18++ = *v16++;
          --v17;
          --v19;
        }
        while ( v19 );
        v20 = v18 - 1;
        if ( v19 )
          v20 = v18;
        *v20 = 0;
        PathSeparateArgs(pszPath, v33, 0xF0u);
        Instance = ((__int64 (__fastcall *)(struct IAttachmentExecute *, WCHAR *))ppv->lpVtbl->SetLocalPath)(
                     ppv,
                     pszPath);
        if ( Instance >= 0 )
        {
          ExtensionW = PathFindExtensionW(pszPath);
          if ( !ExtensionW || !*ExtensionW )
            goto LABEL_41;
          FileW = (char *)CreateFileW(pszPath, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            if ( FileW == (char *)-1LL )
              goto LABEL_41;
          }
          else
          {
            CloseHandle(FileW);
          }
          v23 = ((__int64 (__fastcall *)(struct IAttachmentExecute *))ppv->lpVtbl->CheckPolicy)(ppv);
          if ( v23 == 1 )
          {
            LODWORD(v28) = 0;
            if ( ((int (__fastcall *)(struct IAttachmentExecute *, HWND, __int64, __int64 *))ppv->lpVtbl->Prompt)(
                   ppv,
                   hWnd[0],
                   2,
                   &v28) < 0 )
              goto LABEL_45;
            v24 = (_DWORD)v28 == 2;
LABEL_43:
            if ( v24 )
              goto LABEL_44;
LABEL_45:
            Instance = 0;
            goto LABEL_48;
          }
          if ( !v23 )
          {
LABEL_44:
            pExecInfo.cbSize = 112;
            memset_0(&pExecInfo.fMask, 0, 0x6Cu);
            pExecInfo.fMask = 0;
            pExecInfo.lpFile = pszPath;
            pExecInfo.nShow = 1;
            pExecInfo.lpParameters = v33;
            Instance = !ShellExecuteExW(&pExecInfo) ? 0x80004005 : 0;
            goto LABEL_48;
          }
LABEL_41:
          if ( (unsigned int)(LoadStringW(g_hinst, 0xBC4u, Text, 512) - 1) > 0x1FF )
            goto LABEL_45;
          v24 = MessageBoxW(hWnd[0], Text, Buffer, 0x10131u) == 1;
          goto LABEL_43;
        }
      }
    }
  }
LABEL_48:
  v25 = ppv;
  if ( ppv )
  {
    ppv = 0;
    ((void (__fastcall *)(struct IAttachmentExecute *))v25->lpVtbl->Release)(v25);
  }
  if ( v11 )
    DestroyWindow(v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000b328  push    rbp
0x18000b32a  push    rbx
0x18000b32b  push    rsi
0x18000b32c  push    rdi
0x18000b32d  push    r12
0x18000b32f  push    r13
0x18000b331  push    r14
0x18000b333  push    r15
0x18000b335  lea     rbp, [rsp-878h]
0x18000b33d  sub     rsp, 978h
0x18000b344  mov     rax, cs:__security_cookie
0x18000b34b  xor     rax, rsp
0x18000b34e  mov     [rbp+8B0h+var_50], rax
0x18000b355  mov     rax, [rbp+8B0h+arg_28]
0x18000b35c  xor     edi, edi
0x18000b35e  mov     r13, [rbp+8B0h+arg_30]
0x18000b365  mov     r12, r9
0x18000b368  mov     [rsp+9B0h+hWnd], rax
0x18000b36d  mov     r14, r8
0x18000b370  mov     r15d, edx
0x18000b373  mov     rsi, rcx
0x18000b376  mov     ebx, edi
0x18000b378  test    rax, rax
0x18000b37b  jnz     loc_18000B41D
0x18000b381  test    r8, r8
0x18000b384  jz      short loc_18000B395
0x18000b386  mov     rax, [r8]
0x18000b389  test    rax, rax
0x18000b38c  jz      short loc_18000B395
0x18000b38e  mov     [rsp+9B0h+hWnd], rax
0x18000b393  jmp     short loc_18000B3F2
0x18000b395  mov     rcx, [rcx+0B0h]
0x18000b39c  test    rcx, rcx
0x18000b39f  jz      short loc_18000B3F2
0x18000b3a1  mov     [rsp+9B0h+var_968], rdi
0x18000b3a6  lea     r8, [rsp+9B0h+var_968]
0x18000b3ab  mov     rax, [rcx]
0x18000b3ae  lea     rdx, _GUID_00000114_0000_0000_c000_000000000046
0x18000b3b5  mov     rax, [rax]
0x18000b3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3bd  test    eax, eax
0x18000b3bf  js      short loc_18000B3D7
0x18000b3c1  mov     rcx, [rsp+9B0h+var_968]
0x18000b3c6  lea     rdx, [rsp+9B0h+hWnd]
0x18000b3cb  mov     rax, [rcx]
0x18000b3ce  mov     rax, [rax+18h]
0x18000b3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3d7  mov     rcx, [rsp+9B0h+var_968]
0x18000b3dc  test    rcx, rcx
0x18000b3df  jz      short loc_18000B3F2
0x18000b3e1  mov     [rsp+9B0h+var_968], rdi
0x18000b3e6  mov     rax, [rcx]
0x18000b3e9  mov     rax, [rax+10h]
0x18000b3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3f2  cmp     [rsp+9B0h+hWnd], rdi
0x18000b3f7  jnz     short loc_18000B41D
0x18000b3f9  xor     r9d, r9d
0x18000b3fc  mov     qword ptr [rsp+9B0h+dwFlagsAndAttributes], rdi
0x18000b401  xor     r8d, r8d
0x18000b404  mov     [rsp+9B0h+ppv], rdi
0x18000b409  xor     ecx, ecx
0x18000b40b  lea     rdx, [r9-3]
0x18000b40f  call    cs:__imp_SHCreateWorkerWindowW
0x18000b415  mov     rbx, rax
0x18000b418  mov     [rsp+9B0h+hWnd], rax
0x18000b41d  xor     edx, edx; pUnkOuter
0x18000b41f  mov     [rsp+9B0h+var_970], rdi
0x18000b424  lea     rax, [rsp+9B0h+var_970]
0x18000b429  lea     r9, _GUID_73db1241_1e85_4581_8e4f_a81e1d0f8c57; riid
0x18000b430  mov     [rsp+9B0h+ppv], rax; ppv
0x18000b435  lea     rcx, CLSID_AttachmentServices; rclsid
0x18000b43c  lea     r8d, [rdx+1]; dwClsContext
0x18000b440  call    cs:__imp_CoCreateInstance
0x18000b446  mov     edi, eax
0x18000b448  test    eax, eax
0x18000b44a  js      loc_18000B74A
0x18000b450  mov     rcx, [rsp+9B0h+var_970]
0x18000b455  lea     rdx, aAboutInternet; "about:internet"
0x18000b45c  mov     rax, [rcx]
0x18000b45f  mov     rax, [rax+40h]
0x18000b463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b468  mov     edi, eax
0x18000b46a  test    eax, eax
0x18000b46c  js      loc_18000B74A
0x18000b472  mov     rcx, [rsp+9B0h+var_970]
0x18000b477  lea     rdx, CLSID_CPackage
0x18000b47e  mov     rax, [rcx]
0x18000b481  mov     rax, [rax+20h]
0x18000b485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b48a  mov     edi, eax
0x18000b48c  test    eax, eax
0x18000b48e  js      loc_18000B74A
0x18000b494  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b49b  lea     r8, [rbp+8B0h+Buffer]; lpBuffer
0x18000b49f  mov     r9d, 50h ; 'P'; cchBufferMax
0x18000b4a5  mov     edx, 0BC5h; uID
0x18000b4aa  call    cs:__imp_LoadStringW
0x18000b4b0  dec     eax
0x18000b4b2  cmp     eax, 4Fh ; 'O'
0x18000b4b5  ja      loc_18000B745
0x18000b4bb  mov     rcx, [rsp+9B0h+var_970]
0x18000b4c0  lea     rdx, [rbp+8B0h+Buffer]
0x18000b4c4  mov     rax, [rcx]
0x18000b4c7  mov     rax, [rax+18h]
0x18000b4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4d0  mov     edi, eax
0x18000b4d2  test    eax, eax
0x18000b4d4  js      loc_18000B74A
0x18000b4da  mov     ecx, [rsi+68h]
0x18000b4dd  sub     ecx, 1
0x18000b4e0  jz      short loc_18000B537
0x18000b4e2  cmp     ecx, 2
0x18000b4e5  jnz     loc_18000B74A
0x18000b4eb  cmp     qword ptr [rsi+70h], 0
0x18000b4f0  jz      short loc_18000B52D
0x18000b4f2  mov     rax, [rsp+9B0h+var_970]
0x18000b4f7  mov     r9, r12; struct IOleClientSite *
0x18000b4fa  mov     r10, [rsp+9B0h+hWnd]
0x18000b4ff  mov     r8, r14; struct tagMSG *
0x18000b502  mov     [rsp+9B0h+var_978], rax; struct IAttachmentExecute *
0x18000b507  mov     edx, r15d; int
0x18000b50a  mov     eax, [rbp+8B0h+arg_20]
0x18000b510  mov     rcx, rsi; this
0x18000b513  mov     [rsp+9B0h+hTemplateFile], r13; struct tagRECT *
0x18000b518  mov     qword ptr [rsp+9B0h+dwFlagsAndAttributes], r10; HWND
0x18000b51d  mov     dword ptr [rsp+9B0h+ppv], eax; int
0x18000b521  call    ?_ActivateEmbeddedFile@CPackage@@IEAAJJPEAUtagMSG@@PEAUIOleClientSite@@JPEAUHWND__@@PEBUtagRECT@@PEAUIAttachmentExecute@@@Z; CPackage::_ActivateEmbeddedFile(long,tagMSG *,IOleClientSite *,long,HWND__ *,tagRECT const *,IAttachmentExecute *)
0x18000b526  mov     edi, eax
0x18000b528  jmp     loc_18000B74A
0x18000b52d  mov     edi, 40181h
0x18000b532  jmp     loc_18000B74A
0x18000b537  mov     rax, [rsi+78h]
0x18000b53b  xor     esi, esi
0x18000b53d  test    rax, rax
0x18000b540  jz      loc_18000B71D
0x18000b546  cmp     [rax], esi
0x18000b548  jnz     short loc_18000B556
0x18000b54a  cmp     cs:?gCmdLineOK@@3HA, esi; int gCmdLineOK
0x18000b550  jz      loc_18000B71D
0x18000b556  lea     r8, [rax+4]
0x18000b55a  mov     ecx, 7FFFFFFEh
0x18000b55f  lea     rax, [rbp+8B0h+pszPath]
0x18000b563  mov     edx, 104h
0x18000b568  mov     r14d, 1
0x18000b56e  test    rcx, rcx
0x18000b571  jz      short loc_18000B591
0x18000b573  movzx   r9d, word ptr [r8]
0x18000b577  test    r9w, r9w
0x18000b57b  jz      short loc_18000B591
0x18000b57d  mov     [rax], r9w
0x18000b581  add     r8, 2
0x18000b585  add     rax, 2
0x18000b589  sub     rcx, r14
0x18000b58c  sub     rdx, r14
0x18000b58f  jnz     short loc_18000B56E
0x18000b591  test    rdx, rdx
0x18000b594  lea     rcx, [rax-2]
0x18000b598  mov     r8d, 0F0h; unsigned int
0x18000b59e  lea     rdx, [rbp+8B0h+var_630]; unsigned __int16 *
0x18000b5a5  cmovnz  rcx, rax
0x18000b5a9  mov     [rcx], si
0x18000b5ac  lea     rcx, [rbp+8B0h+pszPath]; lpsz
0x18000b5b0  call    ?PathSeparateArgs@@YAHPEAG0K@Z; PathSeparateArgs(ushort *,ushort *,ulong)
0x18000b5b5  mov     rcx, [rsp+9B0h+var_970]
0x18000b5ba  lea     rdx, [rbp+8B0h+pszPath]
0x18000b5be  mov     rax, [rcx]
0x18000b5c1  mov     rax, [rax+28h]
0x18000b5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ca  mov     edi, eax
0x18000b5cc  test    eax, eax
0x18000b5ce  js      loc_18000B74C
0x18000b5d4  lea     rcx, [rbp+8B0h+pszPath]; pszPath
0x18000b5d8  call    cs:__imp_PathFindExtensionW
0x18000b5de  test    rax, rax
0x18000b5e1  jz      loc_18000B683
0x18000b5e7  cmp     [rax], si
0x18000b5ea  jz      loc_18000B683
0x18000b5f0  mov     [rsp+9B0h+hTemplateFile], rsi; hTemplateFile
0x18000b5f5  lea     rcx, [rbp+8B0h+pszPath]; lpFileName
0x18000b5f9  mov     [rsp+9B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000b601  xor     r9d, r9d; lpSecurityAttributes
0x18000b604  mov     r8d, r14d; dwShareMode
0x18000b607  mov     dword ptr [rsp+9B0h+ppv], 3; dwCreationDisposition
0x18000b60f  mov     edx, 80000000h; dwDesiredAccess
0x18000b614  call    cs:__imp_CreateFileW
0x18000b61a  lea     rcx, [rax-1]
0x18000b61e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000b622  ja      short loc_18000B62F
0x18000b624  mov     rcx, rax; hObject
0x18000b627  call    cs:__imp_CloseHandle
0x18000b62d  jmp     short loc_18000B635
0x18000b62f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b633  jz      short loc_18000B683
0x18000b635  mov     rcx, [rsp+9B0h+var_970]
0x18000b63a  mov     rax, [rcx]
0x18000b63d  mov     rax, [rax+48h]
0x18000b641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b646  cmp     eax, r14d
0x18000b649  jnz     short loc_18000B67F
0x18000b64b  mov     rcx, [rsp+9B0h+var_970]
0x18000b650  lea     r9, [rsp+9B0h+var_968]
0x18000b655  mov     rdx, [rsp+9B0h+hWnd]
0x18000b65a  mov     r8d, 2
0x18000b660  mov     dword ptr [rsp+9B0h+var_968], esi
0x18000b664  mov     rax, [rcx]
0x18000b667  mov     rax, [rax+50h]
0x18000b66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b670  test    eax, eax
0x18000b672  js      loc_18000B719
0x18000b678  cmp     dword ptr [rsp+9B0h+var_968], 2
0x18000b67d  jmp     short loc_18000B6CA
0x18000b67f  test    eax, eax
0x18000b681  jz      short loc_18000B6CC
0x18000b683  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b68a  lea     r8, [rbp+8B0h+Text]; lpBuffer
0x18000b691  mov     r9d, 200h; cchBufferMax
0x18000b697  mov     edx, 0BC4h; uID
0x18000b69c  call    cs:__imp_LoadStringW
0x18000b6a2  dec     eax
0x18000b6a4  cmp     eax, 1FFh
0x18000b6a9  ja      short loc_18000B719
0x18000b6ab  mov     rcx, [rsp+9B0h+hWnd]; hWnd
0x18000b6b0  lea     r8, [rbp+8B0h+Buffer]; lpCaption
0x18000b6b4  mov     r9d, 10131h; uType
0x18000b6ba  lea     rdx, [rbp+8B0h+Text]; lpText
0x18000b6c1  call    cs:__imp_MessageBoxW
0x18000b6c7  cmp     eax, r14d
0x18000b6ca  jnz     short loc_18000B719
0x18000b6cc  xor     edx, edx; Val
0x18000b6ce  mov     [rsp+9B0h+pExecInfo.cbSize], 70h ; 'p'
0x18000b6d6  lea     rcx, [rsp+9B0h+pExecInfo.fMask]; void *
0x18000b6db  lea     r8d, [rdx+6Ch]; Size
0x18000b6df  call    memset_0
0x18000b6e4  lea     rax, [rbp+8B0h+pszPath]
0x18000b6e8  mov     [rsp+9B0h+pExecInfo.fMask], esi
0x18000b6ec  mov     [rsp+9B0h+pExecInfo.lpFile], rax
0x18000b6f1  lea     rcx, [rsp+9B0h+pExecInfo]; pExecInfo
0x18000b6f6  lea     rax, [rbp+8B0h+var_630]
0x18000b6fd  mov     [rbp+8B0h+pExecInfo.nShow], r14d
0x18000b701  mov     [rbp+8B0h+pExecInfo.lpParameters], rax
0x18000b705  call    cs:__imp_ShellExecuteExW
0x18000b70b  neg     eax
0x18000b70d  sbb     edi, edi
0x18000b70f  not     edi
0x18000b711  and     edi, 80004005h
0x18000b717  jmp     short loc_18000B74C
0x18000b719  mov     edi, esi
0x18000b71b  jmp     short loc_18000B74C
0x18000b71d  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hAppInst
0x18000b724  mov     r9d, 0BB8h; lpcTitle
0x18000b72a  xor     edx, edx; hWnd
0x18000b72c  mov     dword ptr [rsp+9B0h+ppv], 2010h; fuStyle
0x18000b734  mov     edi, 80004005h
0x18000b739  lea     r8d, [r9+7]; lpcText
0x18000b73d  call    cs:__imp_ShellMessageBoxW
0x18000b743  jmp     short loc_18000B74C
0x18000b745  mov     edi, 8007007Ah
0x18000b74a  xor     esi, esi
0x18000b74c  mov     rcx, [rsp+9B0h+var_970]
0x18000b751  test    rcx, rcx
0x18000b754  jz      short loc_18000B767
0x18000b756  mov     [rsp+9B0h+var_970], rsi
0x18000b75b  mov     rax, [rcx]
0x18000b75e  mov     rax, [rax+10h]
0x18000b762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b767  test    rbx, rbx
0x18000b76a  jz      short loc_18000B775
0x18000b76c  mov     rcx, rbx; hWnd
0x18000b76f  call    cs:__imp_DestroyWindow
0x18000b775  mov     eax, edi
0x18000b777  mov     rcx, [rbp+8B0h+var_50]
0x18000b77e  xor     rcx, rsp; StackCookie
0x18000b781  call    __security_check_cookie
0x18000b786  add     rsp, 978h
0x18000b78d  pop     r15
0x18000b78f  pop     r14
0x18000b791  pop     r13
0x18000b793  pop     r12
0x18000b795  pop     rdi
0x18000b796  pop     rsi
0x18000b797  pop     rbx
0x18000b798  pop     rbp
0x18000b799  retn
```
