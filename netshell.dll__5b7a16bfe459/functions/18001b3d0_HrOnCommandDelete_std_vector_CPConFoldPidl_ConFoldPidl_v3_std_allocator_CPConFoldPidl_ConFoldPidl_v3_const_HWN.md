# HrOnCommandDelete(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x18001b3d0`
- end: `0x18001bc0a`
- name: `?HrOnCommandDelete@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `2106`
- prototype: `__int64 __fastcall(ConFoldPidl_v3 ***, HWND, __int64)`
- caller_count: `0`
- callee_count: `25`
- tags: `broker_com_uri`

## callees

- `0x180001fd0`
- `0x1800020b0`
- `0x180005c8c`
- `0x180007de0`
- `0x180015268`
- `0x180018d74`
- `0x180019d24`
- `0x18001b3d0`
- `0x18001bc10`
- `0x18001d0bc`
- `0x18001d580`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x180034fdc`
- `0x180040a5c`
- `0x18004154c`
- `0x180044eec`
- `0x180046358`
- `0x180049e0c`
- `0x18004a540`
- `0x18004a7b8`
- `0x18004bf00`
- `0x1800617f0`
- `0x180061824`
- `0x180065010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18001b45a`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18001b45a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bb32`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bb32`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001bb15`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001bb15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bb3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bb3b`
- `ole32!StringFromGUID2` at `0x18001bb00`
- `ole32!StringFromGUID2` at `0x18001bb00`
- `RASAPI32!RasIsSharedConnection` at `0x18001b765`
- `RASAPI32!RasIsSharedConnection` at `0x18001b765`

## pseudocode

```c
__int64 __fastcall HrOnCommandDelete(ConFoldPidl_v3 ***a1, HWND a2, __int64 a3)
{
  __int64 v3; // r14
  ConFoldPidl_v3 ***v5; // rdi
  int v6; // r13d
  int NetCon; // esi
  int v8; // r15d
  ConFoldPidl_v3 **v9; // rbx
  unsigned __int64 v10; // rcx
  ConFoldPidl_v3 **i; // rbx
  CConnectionList *v12; // rcx
  int v13; // eax
  OLECHAR *v14; // rcx
  ConFoldPidl_v3 *v15; // rcx
  int v16; // eax
  CConnectionList *v17; // rcx
  OLECHAR *v18; // rcx
  int v19; // eax
  unsigned int IsSharedConnection; // eax
  unsigned int v21; // r9d
  __int64 v22; // rax
  __int64 FolderRoot; // rdx
  unsigned int v24; // r14d
  ConFoldPidl_v3 **j; // rbx
  ConFoldPidl_v3 **v26; // rax
  unsigned int v27; // r9d
  enum tagNETCON_MEDIATYPE v28; // r15d
  char v29; // r14
  unsigned int v30; // r9d
  unsigned int v31; // r8d
  HANDLE MutexW; // r14
  DWORD LastError; // edi
  __int64 v35; // [rsp+28h] [rbp-580h]
  unsigned int v36; // [rsp+30h] [rbp-578h] BYREF
  struct IUnknown *v37; // [rsp+38h] [rbp-570h] BYREF
  int v38; // [rsp+40h] [rbp-568h] BYREF
  __int64 v39; // [rsp+48h] [rbp-560h] BYREF
  ConFoldPidl_v3 ***v40; // [rsp+50h] [rbp-558h]
  __int64 v41; // [rsp+58h] [rbp-550h]
  __int64 v42; // [rsp+60h] [rbp-548h]
  unsigned int v43; // [rsp+68h] [rbp-540h] BYREF
  void **v44; // [rsp+70h] [rbp-538h] BYREF
  __int64 v45; // [rsp+78h] [rbp-530h] BYREF
  void **v46; // [rsp+88h] [rbp-520h] BYREF
  __int64 v47; // [rsp+90h] [rbp-518h] BYREF
  GUID rguid; // [rsp+A0h] [rbp-508h] BYREF
  OLECHAR sz[4]; // [rsp+B0h] [rbp-4F8h] BYREF
  int v50; // [rsp+B8h] [rbp-4F0h]
  __int64 v51; // [rsp+E8h] [rbp-4C0h]
  __int64 v52; // [rsp+F0h] [rbp-4B8h]
  _DWORD v53[10]; // [rsp+140h] [rbp-468h] BYREF
  GUID v54; // [rsp+168h] [rbp-440h]
  char v55; // [rsp+178h] [rbp-430h]

  v3 = a3;
  v42 = a3;
  v5 = a1;
  v40 = a1;
  v6 = 0;
  NetCon = 0;
  v37 = 0;
  v8 = 0;
  v38 = 0;
  v9 = *a1;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    while ( v9 != v5[1] )
    {
      CConFoldEntry::CConFoldEntry((CConFoldEntry *)v53);
      if ( *v9 )
        NetCon = ConFoldPidl_v3::ConvertToConFoldEntry(*v9, (struct CConFoldEntry *)v53);
      else
        NetCon = -2147418113;
      rguid = v54;
      StringFromGUID2(&rguid, sz, 39);
      MutexW = CreateMutexW(0, 1, sz);
      if ( !MutexW )
        goto LABEL_117;
      LastError = GetLastError();
      ReleaseMutex(MutexW);
      CloseHandle(MutexW);
      if ( LastError == 183 )
      {
        NcMsgBox(hInst, a2, 0x441u, 0x453u, 0x30u);
        NetCon = CConFoldEntry::HrGetNetCon((CConFoldEntry *)v53, &IID_INetConnection, (void **)&v37, 1);
        if ( NetCon >= 0 )
        {
          SetLUAParent(v37, a2);
          ActivateDialog(0, v37);
LABEL_117:
          NetCon = -2147024891;
        }
        v18 = (OLECHAR *)v53;
LABEL_119:
        CConFoldEntry::~CConFoldEntry((CConFoldEntry *)v18);
        return (unsigned int)NetCon;
      }
      CConFoldEntry::~CConFoldEntry((CConFoldEntry *)v53);
      ++v9;
      v5 = v40;
      v3 = v42;
    }
    if ( NetCon < 0 )
      return (unsigned int)NetCon;
    v10 = v5[1] - *v5;
    if ( v10 > 1 )
    {
      _o__itow_s(v10, &rguid, 8);
      v8 = NcMsgBox(hInst, a2, 0x439u, 0x43Bu, 0x34u, &rguid);
      if ( v8 != 6 )
        return (unsigned int)NetCon;
      for ( i = *v5; i != v5[1]; ++i )
      {
        CConFoldEntry::CConFoldEntry((CConFoldEntry *)v53);
        if ( *i )
        {
          NetCon = ConFoldPidl_v3::ConvertToConFoldEntry(*i, (struct CConFoldEntry *)v53);
          if ( NetCon >= 0 && (v55 & 0x20) != 0 && !v53[0] )
          {
            v36 = 0;
            if ( (int)CConnectionList::HasActiveIncomingConnections(v12, &v36) >= 0 && v36 )
            {
              if ( v36 == 1 )
              {
                v13 = NcMsgBox(hInst, a2, 0x439u, 0x43Cu, 0x34u);
              }
              else
              {
                LODWORD(v35) = v36;
                v13 = NcMsgBox(hInst, a2, 0x439u, 0x43Du, 0x34u, v35);
              }
              v8 = v13;
            }
            v14 = (OLECHAR *)v53;
            goto LABEL_55;
          }
        }
        else
        {
          NetCon = -2147418113;
        }
        CConFoldEntry::~CConFoldEntry((CConFoldEntry *)v53);
      }
      goto LABEL_56;
    }
    if ( (char *)v5[1] - (char *)*v5 != 8 )
      return (unsigned int)NetCon;
    CConFoldEntry::CConFoldEntry((CConFoldEntry *)sz);
    v15 = **v5;
    if ( !v15 )
    {
      NetCon = -2147418113;
LABEL_37:
      v18 = sz;
      goto LABEL_119;
    }
    NetCon = ConFoldPidl_v3::ConvertToConFoldEntry(v15, (struct CConFoldEntry *)sz);
    if ( NetCon < 0 )
      goto LABEL_37;
    v39 = 0;
    v16 = HrCheckForActivation(&v39, sz, &v38);
    NetCon = v16;
    if ( v16 )
    {
      if ( v16 == 1 )
        goto LABEL_36;
    }
    else
    {
      if ( v38
        || *(_DWORD *)sz != 7
        && (v50 == 1
         || v50 == 2
         || v50 == 8
         || v50 == 9
         || (v17 = (CConnectionList *)(unsigned int)(v50 - 10), v50 == 10)
         || v50 == 12
         || v50 == 3) )
      {
        NcMsgBox(hInst, a2, 0x441u, 0x442u, 0x30u);
LABEL_36:
        CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(&v39);
        goto LABEL_37;
      }
      if ( (v51 & 0x20) != 0 && !*(_DWORD *)sz )
      {
        v36 = 0;
        if ( (int)CConnectionList::HasActiveIncomingConnections(v17, &v36) >= 0 && v36 )
        {
          if ( v36 == 1 )
            v19 = NcMsgBox(hInst, a2, 0x438u, 0x43Cu, 0x34u);
          else
            v19 = NcMsgBox(hInst, a2, 0x438u, 0x43Du, 0x34u, v36);
          goto LABEL_45;
        }
LABEL_46:
        v19 = NcMsgBox(hInst, a2, 0x438u, 0x43Au, 0x34u, v52);
LABEL_45:
        v8 = v19;
        goto LABEL_54;
      }
      memset_0(v53, 0, 0x420u);
      NetCon = CConFoldEntry::HrGetNetCon((CConFoldEntry *)sz, &IID_INetConnection, (void **)&v37, 1);
      if ( NetCon >= 0 )
      {
        SetLUAParent(v37, a2);
        NetCon = HrNetConToSharedConnection((struct INetConnection *)v37, (struct _RASSHARECONN *)v53);
        if ( NetCon >= 0 )
        {
          v36 = 0;
          IsSharedConnection = RasIsSharedConnection(v53, &v36);
          NetCon = HrFromRasError(IsSharedConnection);
          if ( NetCon < 0 || (v21 = 1077, v36 != 1) )
            v21 = 1082;
          v19 = NcMsgBox(hInst, a2, 0x438u, v21, 0x34u, v52);
          goto LABEL_45;
        }
        goto LABEL_46;
      }
    }
LABEL_54:
    CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(&v39);
    v14 = sz;
LABEL_55:
    CConFoldEntry::~CConFoldEntry((CConFoldEntry *)v14);
    if ( v8 != 6 )
      return (unsigned int)NetCon;
LABEL_56:
    v22 = v3 - 16;
    if ( !v3 )
      v22 = 0;
    v41 = v22;
    v39 = 0;
    if ( v22 )
    {
      FolderRoot = CConnectionFolder::PidlGetFolderRoot(v22);
      CPConFoldPidl<ConFoldPidlFolder>::operator=(&v39, FolderRoot);
    }
    v24 = 0;
    v36 = 0;
    for ( j = *v5; ; ++j )
    {
      v26 = v40[1];
      if ( j == v26 )
      {
        if ( v6 )
        {
          v27 = ((char *)v26 - (char *)*v40 != 8) + 1078;
          goto LABEL_66;
        }
        if ( v24 )
        {
          v27 = ((char *)v26 - (char *)*v40 != 8) + 1090;
LABEL_66:
          NcMsgBox(hInst, a2, 0x441u, v27, 0x30u);
        }
        CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(&v39);
        return (unsigned int)NetCon;
      }
      CConFoldEntry::CConFoldEntry((CConFoldEntry *)sz);
      if ( !*j )
      {
        NetCon = -2147418113;
        goto LABEL_107;
      }
      NetCon = ConFoldPidl_v3::ConvertToConFoldEntry(*j, (struct CConFoldEntry *)sz);
      if ( NetCon >= 0 )
        break;
LABEL_107:
      CConFoldEntry::~CConFoldEntry((CConFoldEntry *)sz);
    }
    v28 = *(_DWORD *)sz;
    if ( *(_DWORD *)sz == 3 || *(_DWORD *)sz == 7 && !(unsigned int)IsBridgeAllowed() )
      goto LABEL_72;
    if ( (unsigned int)IsMediaRASType(v28) )
    {
      if ( !(unsigned int)FHasPermission(5u) )
        goto LABEL_72;
      v29 = v51;
      if ( (v51 & 1) != 0 && !(unsigned int)FHasPermission(6u) )
      {
        v24 = v36;
LABEL_72:
        v6 = 1;
        goto LABEL_107;
      }
    }
    else
    {
      v29 = v51;
    }
    *(_QWORD *)&rguid.Data1 = 0;
    NetCon = HrCheckForActivation(&rguid, sz, &v38);
    if ( NetCon )
      goto LABEL_105;
    if ( v38
      || v28 != NCM_BRIDGE && (v50 == 1 || v50 == 2 || v50 == 8 || v50 == 9 || v50 == 10 || v50 == 12 || v50 == 3) )
    {
      v24 = 1;
      v36 = 1;
      goto LABEL_106;
    }
    if ( (v29 & 4) == 0 )
    {
      v6 = 1;
      goto LABEL_105;
    }
    NetCon = HrNetConFromPidl(j, &v37, 1);
    if ( NetCon < 0 )
    {
LABEL_105:
      v24 = v36;
LABEL_106:
      CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(&rguid);
      goto LABEL_107;
    }
    SetLUAParent(v37, a2);
    if ( v28 == NCM_BRIDGE )
      NetCon = HrOnCommandBridgeRemoveConnections(v40, a2, v42, 0);
    else
      NetCon = ((__int64 (__fastcall *)(struct IUnknown *))v37->lpVtbl[1].Release)(v37);
    if ( NetCon < 0 || !v41 )
    {
      if ( NetCon == -2147024891 && v28 == NCM_BRIDGE )
      {
        v30 = 1105;
        v31 = 1089;
LABEL_103:
        NcMsgBox(hInst, a2, v31, v30, 0x30u);
        goto LABEL_104;
      }
      if ( (unsigned int)HR_NO_ACCESS(NetCon) )
      {
        v30 = 1096;
        v31 = 1060;
        goto LABEL_103;
      }
    }
LABEL_104:
    ReleaseObj(v37);
    goto LABEL_105;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', (std::bad_alloc *)&v44) )
    {
      v36 = -2147024882;
      v44 = &std::bad_alloc::`vftable';
      o___std_exception_destroy_0(&v45);
      NetCon = v36;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001BBDD);
      return (unsigned int)NetCon;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', (std::exception *)&v46) )
    {
      v36 = -2147467259;
      v46 = &std::bad_alloc::`vftable';
      o___std_exception_destroy_0(&v47);
      NetCon = v36;
      __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_18001BBDF);
      return (unsigned int)NetCon;
    }
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v43) )
    {
      NetCon = v43;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18001BBE1);
    }
  }
  return (unsigned int)NetCon;
}

```

## disassembly

```asm
0x18001b3d0  push    rbx
0x18001b3d2  push    rsi
0x18001b3d3  push    rdi
0x18001b3d4  push    r12
0x18001b3d6  push    r13
0x18001b3d8  push    r14
0x18001b3da  push    r15
0x18001b3dc  sub     rsp, 570h
0x18001b3e3  mov     rax, cs:__security_cookie
0x18001b3ea  xor     rax, rsp
0x18001b3ed  mov     [rsp+5A8h+var_48], rax
0x18001b3f5  mov     r14, r8
0x18001b3f8  mov     [rsp+5A8h+var_548], r8
0x18001b3fd  mov     r12, rdx
0x18001b400  mov     rdi, rcx
0x18001b403  mov     [rsp+5A8h+var_558], rcx
0x18001b408  xor     r13d, r13d
0x18001b40b  mov     esi, r13d
0x18001b40e  mov     [rsp+5A8h+var_570], r13
0x18001b413  mov     r15d, r13d
0x18001b416  mov     [rsp+5A8h+var_568], r13d
0x18001b41b  mov     rbx, [rcx]
0x18001b41e  cmp     rbx, [rdi+8]
0x18001b422  jnz     loc_18001BAAD
0x18001b428  test    esi, esi
0x18001b42a  js      loc_18001BBBB
0x18001b430  mov     rax, [rdi+8]
0x18001b434  sub     rax, [rdi]
0x18001b437  mov     rcx, rax
0x18001b43a  sar     rcx, 3
0x18001b43e  cmp     rcx, 1
0x18001b442  jbe     loc_18001B567
0x18001b448  mov     r9d, 0Ah
0x18001b44e  lea     r8d, [r9-2]
0x18001b452  lea     rdx, [rsp+5A8h+rguid]
0x18001b45a  call    cs:__imp__o__itow_s
0x18001b460  lea     rax, [rsp+5A8h+rguid]
0x18001b468  mov     [rsp+5A8h+var_580], rax
0x18001b46d  mov     [rsp+5A8h+uType], 34h ; '4'; uType
0x18001b475  mov     r9d, 43Bh; unsigned int
0x18001b47b  lea     r8d, [r9-2]; unsigned int
0x18001b47f  mov     rdx, r12; hWnd
0x18001b482  mov     rcx, cs:hInst; hModule
0x18001b489  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001b48e  mov     r15d, eax
0x18001b491  cmp     eax, 6
0x18001b494  jnz     loc_18001BBBB
0x18001b49a  mov     rbx, [rdi]
0x18001b49d  cmp     rbx, [rdi+8]
0x18001b4a1  jz      loc_18001B7D8
0x18001b4a7  lea     rcx, [rsp+5A8h+var_468]; this
0x18001b4af  call    ??0CConFoldEntry@@QEAA@XZ; CConFoldEntry::CConFoldEntry(void)
0x18001b4b4  mov     rcx, [rbx]; this
0x18001b4b7  test    rcx, rcx
0x18001b4ba  jnz     short loc_18001B4C3
0x18001b4bc  mov     esi, 8000FFFFh
0x18001b4c1  jmp     short loc_18001B4EA
0x18001b4c3  lea     rdx, [rsp+5A8h+var_468]; struct CConFoldEntry *
0x18001b4cb  call    ?ConvertToConFoldEntry@ConFoldPidl_v3@@QEBAJAEAVCConFoldEntry@@@Z; ConFoldPidl_v3::ConvertToConFoldEntry(CConFoldEntry &)
0x18001b4d0  mov     esi, eax
0x18001b4d2  test    eax, eax
0x18001b4d4  js      short loc_18001B4EA
0x18001b4d6  test    [rsp+5A8h+var_430], 20h
0x18001b4de  jz      short loc_18001B4EA
0x18001b4e0  cmp     [rsp+5A8h+var_468], r13d
0x18001b4e8  jz      short loc_18001B4FD
0x18001b4ea  lea     rcx, [rsp+5A8h+var_468]; this
0x18001b4f2  call    ??1CConFoldEntry@@QEAA@XZ; CConFoldEntry::~CConFoldEntry(void)
0x18001b4f7  add     rbx, 8
0x18001b4fb  jmp     short loc_18001B49D
0x18001b4fd  mov     [rsp+5A8h+var_578], r13d
0x18001b502  lea     rdx, [rsp+5A8h+var_578]; unsigned int *
0x18001b507  call    ?HasActiveIncomingConnections@CConnectionList@@QEAAJPEAK@Z; CConnectionList::HasActiveIncomingConnections(ulong *)
0x18001b50c  test    eax, eax
0x18001b50e  js      short loc_18001B55A
0x18001b510  mov     eax, [rsp+5A8h+var_578]
0x18001b514  test    eax, eax
0x18001b516  jz      short loc_18001B55A
0x18001b518  mov     r8d, 439h; unsigned int
0x18001b51e  mov     rdx, r12; hWnd
0x18001b521  mov     rcx, cs:hInst; hModule
0x18001b528  cmp     eax, 1
0x18001b52b  jnz     short loc_18001B540
0x18001b52d  mov     [rsp+5A8h+uType], 34h ; '4'; uType
0x18001b535  lea     r9d, [r8+3]; unsigned int
0x18001b539  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001b53e  jmp     short loc_18001B557
0x18001b540  mov     dword ptr [rsp+5A8h+var_580], eax
0x18001b544  mov     [rsp+5A8h+uType], 34h ; '4'; uType
0x18001b54c  mov     r9d, 43Dh; unsigned int
0x18001b552  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001b557  mov     r15d, eax
0x18001b55a  lea     rcx, [rsp+5A8h+var_468]
0x18001b562  jmp     loc_18001B7C9
0x18001b567  cmp     rax, 8
0x18001b56b  jnz     loc_18001BBBB
0x18001b571  lea     rcx, [rsp+5A8h+sz]; this
0x18001b579  call    ??0CConFoldEntry@@QEAA@XZ; CConFoldEntry::CConFoldEntry(void)
0x18001b57e  nop
0x18001b57f  mov     rax, [rdi]
0x18001b582  mov     rcx, [rax]; this
0x18001b585  test    rcx, rcx
0x18001b588  jnz     short loc_18001B594
0x18001b58a  mov     esi, 8000FFFFh
0x18001b58f  jmp     loc_18001B643
0x18001b594  lea     rdx, [rsp+5A8h+sz]; struct CConFoldEntry *
0x18001b59c  call    ?ConvertToConFoldEntry@ConFoldPidl_v3@@QEBAJAEAVCConFoldEntry@@@Z; ConFoldPidl_v3::ConvertToConFoldEntry(CConFoldEntry &)
0x18001b5a1  mov     esi, eax
0x18001b5a3  test    eax, eax
0x18001b5a5  js      loc_18001B643
0x18001b5ab  mov     [rsp+5A8h+var_560], r13
0x18001b5b0  lea     r8, [rsp+5A8h+var_568]
0x18001b5b5  lea     rdx, [rsp+5A8h+sz]
0x18001b5bd  lea     rcx, [rsp+5A8h+var_560]
0x18001b5c2  call    ?HrCheckForActivation@@YAJAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@AEBVCConFoldEntry@@PEAH@Z; HrCheckForActivation(CPConFoldPidl<ConFoldPidl_v3> const &,CConFoldEntry const &,int *)
0x18001b5c7  mov     esi, eax
0x18001b5c9  test    eax, eax
0x18001b5cb  jnz     loc_18001B7AD
0x18001b5d1  cmp     [rsp+5A8h+var_568], r13d
0x18001b5d6  jnz     short loc_18001B616
0x18001b5d8  mov     r9d, dword ptr [rsp+5A8h+sz]
0x18001b5e0  cmp     r9d, 7
0x18001b5e4  jz      short loc_18001B650
0x18001b5e6  mov     r8d, [rsp+5A8h+var_4F0]
0x18001b5ee  cmp     r8d, 1
0x18001b5f2  jz      short loc_18001B616
0x18001b5f4  mov     ecx, r8d
0x18001b5f7  sub     ecx, 2
0x18001b5fa  jz      short loc_18001B616
0x18001b5fc  sub     ecx, 6
0x18001b5ff  jz      short loc_18001B616
0x18001b601  sub     ecx, 1
0x18001b604  jz      short loc_18001B616
0x18001b606  sub     ecx, 1
0x18001b609  jz      short loc_18001B616
0x18001b60b  cmp     ecx, 2
0x18001b60e  jz      short loc_18001B616
0x18001b610  cmp     r8d, 3
0x18001b614  jnz     short loc_18001B650
0x18001b616  mov     [rsp+5A8h+uType], 30h ; '0'; uType
0x18001b61e  mov     r9d, 442h; unsigned int
0x18001b624  lea     r8d, [r9-1]; unsigned int
0x18001b628  mov     rdx, r12; hWnd
0x18001b62b  mov     rcx, cs:hInst; hModule
0x18001b632  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001b637  nop
0x18001b638  lea     rcx, [rsp+5A8h+var_560]
0x18001b63d  call    ?FreePIDLIfRequired@?$CPConFoldPidl@VConFoldPidlFolder@@@@AEAAJXZ; CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(void)
0x18001b642  nop
0x18001b643  lea     rcx, [rsp+5A8h+sz]
0x18001b64b  jmp     loc_18001BBB5
0x18001b650  test    byte ptr [rsp+5A8h+var_4C0], 20h
0x18001b658  jz      loc_18001B6EC
0x18001b65e  test    r9d, r9d
0x18001b661  jnz     loc_18001B6EC
0x18001b667  mov     [rsp+5A8h+var_578], r13d
0x18001b66c  lea     rdx, [rsp+5A8h+var_578]; unsigned int *
0x18001b671  call    ?HasActiveIncomingConnections@CConnectionList@@QEAAJPEAK@Z; CConnectionList::HasActiveIncomingConnections(ulong *)
0x18001b676  test    eax, eax
0x18001b678  js      short loc_18001B6C9
0x18001b67a  mov     eax, [rsp+5A8h+var_578]
0x18001b67e  test    eax, eax
0x18001b680  jz      short loc_18001B6C9
0x18001b682  mov     r8d, 438h; unsigned int
0x18001b688  mov     rdx, r12; hWnd
0x18001b68b  mov     rcx, cs:hInst; hModule
0x18001b692  cmp     eax, 1
0x18001b695  jnz     short loc_18001B6AA
0x18001b697  mov     [rsp+5A8h+uType], 34h ; '4'; uType
0x18001b69f  lea     r9d, [r8+4]; unsigned int
0x18001b6a3  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001b6a8  jmp     short loc_18001B6C1
0x18001b6aa  mov     dword ptr [rsp+5A8h+var_580], eax
0x18001b6ae  mov     r9d, 43Dh; unsigned int
0x18001b6b4  mov     [rsp+5A8h+uType], 34h ; '4'; uType
0x18001b6bc  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001b6c1  mov     r15d, eax
0x18001b6c4  jmp     loc_18001B7B6
0x18001b6c9  mov     rax, [rsp+5A8h+var_4B8]
0x18001b6d1  mov     [rsp+5A8h+var_580], rax
0x18001b6d6  mov     r9d, 43Ah
0x18001b6dc  lea     r8d, [r9-2]
0x18001b6e0  mov     rdx, r12
0x18001b6e3  mov     rcx, cs:hInst
0x18001b6ea  jmp     short loc_18001B6B4
0x18001b6ec  xor     edx, edx; Val
0x18001b6ee  mov     r8d, 420h; Size
0x18001b6f4  lea     rcx, [rsp+5A8h+var_468]; void *
0x18001b6fc  call    memset_0
0x18001b701  mov     r9d, 1; int
0x18001b707  lea     r8, [rsp+5A8h+var_570]; void **
0x18001b70c  lea     rdx, IID_INetConnection; struct _GUID *
0x18001b713  lea     rcx, [rsp+5A8h+sz]; this
0x18001b71b  call    ?HrGetNetCon@CConFoldEntry@@QEBAJAEBU_GUID@@PEAPEAXH@Z; CConFoldEntry::HrGetNetCon(_GUID const &,void * *,int)
0x18001b720  mov     esi, eax
0x18001b722  test    eax, eax
0x18001b724  js      loc_18001B7B6
0x18001b72a  mov     rdx, r12; HWND
0x18001b72d  mov     rcx, [rsp+5A8h+var_570]; struct IUnknown *
0x18001b732  call    ?SetLUAParent@@YAXPEAUIUnknown@@PEAUHWND__@@@Z; SetLUAParent(IUnknown *,HWND__ *)
0x18001b737  lea     rdx, [rsp+5A8h+var_468]; struct _RASSHARECONN *
0x18001b73f  mov     rcx, [rsp+5A8h+var_570]; struct INetConnection *
0x18001b744  call    ?HrNetConToSharedConnection@@YAJPEAUINetConnection@@PEAU_RASSHARECONN@@@Z; HrNetConToSharedConnection(INetConnection *,_RASSHARECONN *)
0x18001b749  mov     esi, eax
0x18001b74b  test    eax, eax
0x18001b74d  js      loc_18001B6C9
0x18001b753  mov     [rsp+5A8h+var_578], r13d
0x18001b758  lea     rdx, [rsp+5A8h+var_578]
0x18001b75d  lea     rcx, [rsp+5A8h+var_468]
0x18001b765  call    cs:__imp_RasIsSharedConnection
0x18001b76b  mov     ecx, eax; unsigned int
0x18001b76d  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18001b772  mov     esi, eax
0x18001b774  test    eax, eax
0x18001b776  js      short loc_18001B785
0x18001b778  cmp     [rsp+5A8h+var_578], 1
0x18001b77d  mov     r9d, 435h
0x18001b783  jz      short loc_18001B78B
0x18001b785  mov     r9d, 43Ah
0x18001b78b  mov     rax, [rsp+5A8h+var_4B8]
0x18001b793  mov     rcx, cs:hInst
0x18001b79a  mov     [rsp+5A8h+var_580], rax
0x18001b79f  mov     r8d, 438h
0x18001b7a5  mov     rdx, r12
0x18001b7a8  jmp     loc_18001B6B4
0x18001b7ad  cmp     eax, 1
0x18001b7b0  jz      loc_18001B638
0x18001b7b6  lea     rcx, [rsp+5A8h+var_560]
0x18001b7bb  call    ?FreePIDLIfRequired@?$CPConFoldPidl@VConFoldPidlFolder@@@@AEAAJXZ; CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(void)
0x18001b7c0  nop
0x18001b7c1  lea     rcx, [rsp+5A8h+sz]; this
0x18001b7c9  call    ??1CConFoldEntry@@QEAA@XZ; CConFoldEntry::~CConFoldEntry(void)
0x18001b7ce  cmp     r15d, 6
0x18001b7d2  jnz     loc_18001BBBB
0x18001b7d8  test    r14, r14
0x18001b7db  lea     rax, [r14-10h]
0x18001b7df  jnz     short loc_18001B7E4
0x18001b7e1  mov     rax, r13
0x18001b7e4  mov     [rsp+5A8h+var_550], rax
0x18001b7e9  mov     [rsp+5A8h+var_560], r13
0x18001b7ee  test    rax, rax
0x18001b7f1  jz      short loc_18001B808
0x18001b7f3  mov     rcx, rax
0x18001b7f6  call    ?PidlGetFolderRoot@CConnectionFolder@@QEAAAEAV?$CPConFoldPidl@VConFoldPidlFolder@@@@XZ; CConnectionFolder::PidlGetFolderRoot(void)
0x18001b7fb  mov     rdx, rax
0x18001b7fe  lea     rcx, [rsp+5A8h+var_560]
0x18001b803  call    ??4?$CPConFoldPidl@VConFoldPidlFolder@@@@QEAAAEAV0@AEBV0@@Z; CPConFoldPidl<ConFoldPidlFolder>::operator=(CPConFoldPidl<ConFoldPidlFolder> const &)
0x18001b808  mov     r14d, r13d
0x18001b80b  mov     [rsp+5A8h+var_578], r13d
0x18001b810  mov     rbx, [rdi]
0x18001b813  mov     edi, 30h ; '0'
0x18001b818  mov     rcx, [rsp+5A8h+var_558]
0x18001b81d  mov     rax, [rcx+8]
0x18001b821  cmp     rbx, rax
0x18001b824  jnz     short loc_18001B885
0x18001b826  test    r13d, r13d
0x18001b829  jz      short loc_18001B842
0x18001b82b  sub     rax, [rcx]
0x18001b82e  xor     r9d, r9d
0x18001b831  cmp     rax, 8
0x18001b835  setnz   r9b
0x18001b839  add     r9d, 436h
0x18001b840  jmp     short loc_18001B85C
0x18001b842  test    r14d, r14d
0x18001b845  jz      short loc_18001B876
0x18001b847  sub     rax, [rcx]
0x18001b84a  xor     r9d, r9d
0x18001b84d  cmp     rax, 8
0x18001b851  setnz   r9b
0x18001b855  add     r9d, 442h; unsigned int
0x18001b85c  mov     [rsp+5A8h+uType], edi; uType
0x18001b860  mov     r8d, 441h; unsigned int
0x18001b866  mov     rdx, r12; hWnd
0x18001b869  mov     rcx, cs:hInst; hModule
0x18001b870  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001b875  nop
0x18001b876  lea     rcx, [rsp+5A8h+var_560]
0x18001b87b  call    ?FreePIDLIfRequired@?$CPConFoldPidl@VConFoldPidlFolder@@@@AEAAJXZ; CPConFoldPidl<ConFoldPidlFolder>::FreePIDLIfRequired(void)
0x18001b880  jmp     loc_18001BBBB
0x18001b885  lea     rcx, [rsp+5A8h+sz]; this
0x18001b88d  call    ??0CConFoldEntry@@QEAA@XZ; CConFoldEntry::CConFoldEntry(void)
0x18001b892  nop
0x18001b893  mov     rcx, [rbx]; this
0x18001b896  test    rcx, rcx
0x18001b899  jnz     short loc_18001B8A5
0x18001b89b  mov     esi, 8000FFFFh
0x18001b8a0  jmp     loc_18001BA82
0x18001b8a5  lea     rdx, [rsp+5A8h+sz]; struct CConFoldEntry *
0x18001b8ad  call    ?ConvertToConFoldEntry@ConFoldPidl_v3@@QEBAJAEAVCConFoldEntry@@@Z; ConFoldPidl_v3::ConvertToConFoldEntry(CConFoldEntry &)
0x18001b8b2  mov     esi, eax
0x18001b8b4  test    eax, eax
0x18001b8b6  js      loc_18001BA82
0x18001b8bc  mov     r15d, dword ptr [rsp+5A8h+sz]
0x18001b8c4  cmp     r15d, 3
0x18001b8c8  jnz     short loc_18001B8D5
0x18001b8ca  mov     r13d, 1
0x18001b8d0  jmp     loc_18001BA82
0x18001b8d5  cmp     r15d, 7
0x18001b8d9  jnz     short loc_18001B8E4
0x18001b8db  call    ?IsBridgeAllowed@@YAHXZ; IsBridgeAllowed(void)
  ... truncated ...
```
