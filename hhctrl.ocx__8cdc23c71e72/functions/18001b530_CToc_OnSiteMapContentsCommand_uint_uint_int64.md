# CToc::OnSiteMapContentsCommand(uint,uint,__int64)

- ea: `0x18001b530`
- end: `0x18001bc80`
- name: `?OnSiteMapContentsCommand@CToc@@QEAA_JII_J@Z`
- size: `1872`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b410`

## callees

- `0x1800038f4`
- `0x180003fc0`
- `0x180011104`
- `0x180011e94`
- `0x1800123d0`
- `0x180018dec`
- `0x1800197c8`
- `0x18001b530`
- `0x18001c6f4`
- `0x18001d270`
- `0x18001d394`
- `0x18001f1cc`
- `0x18001f4b8`
- `0x180020100`
- `0x18002dd44`
- `0x18002f3e8`
- `0x18002f6d8`
- `0x18002fef8`
- `0x1800301f8`
- `0x180030704`
- `0x180033118`
- `0x180037448`
- `0x1800535d0`
- `0x18006e4b8`
- `0x18007225c`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!RemovePropA` at `0x18001b965`
- `USER32!RemovePropA` at `0x18001b965`
- `USER32!SetCursor` at `0x18001bc4f`
- `USER32!SetCursor` at `0x18001bc4f`
- `USER32!DestroyWindow` at `0x18001b972`
- `USER32!DestroyWindow` at `0x18001b972`
- `USER32!SendMessageA` at `0x18001b6ef`
- `USER32!SendMessageA` at `0x18001b9aa`
- `USER32!SendMessageA` at `0x18001b9cb`
- `USER32!SendMessageA` at `0x18001ba60`
- `USER32!SendMessageA` at `0x18001baae`
- `USER32!SendMessageA` at `0x18001bad1`
- `USER32!SendMessageA` at `0x18001bafc`
- `USER32!SendMessageA` at `0x18001bb9f`
- `USER32!SendMessageA` at `0x18001bbf3`
- `USER32!SendMessageA` at `0x18001bc25`
- `USER32!SendMessageA` at `0x18001bc3e`
- `USER32!SendMessageA` at `0x18001b6ef`
- `USER32!SendMessageA` at `0x18001b9aa`
- `USER32!SendMessageA` at `0x18001b9cb`
- `USER32!SendMessageA` at `0x18001ba60`
- `USER32!SendMessageA` at `0x18001baae`
- `USER32!SendMessageA` at `0x18001bad1`
- `USER32!SendMessageA` at `0x18001bafc`
- `USER32!SendMessageA` at `0x18001bb9f`
- `USER32!SendMessageA` at `0x18001bbf3`
- `USER32!SendMessageA` at `0x18001bc25`
- `USER32!SendMessageA` at `0x18001bc3e`
- `USER32!GetParent` at `0x18001b608`
- `USER32!GetParent` at `0x18001b6ad`
- `USER32!GetParent` at `0x18001b883`
- `USER32!GetParent` at `0x18001b94e`
- `USER32!GetParent` at `0x18001b608`
- `USER32!GetParent` at `0x18001b6ad`
- `USER32!GetParent` at `0x18001b883`
- `USER32!GetParent` at `0x18001b94e`
- `urlmon!HlinkSimpleNavigateToString` at `0x18001b69e`
- `urlmon!HlinkSimpleNavigateToString` at `0x18001b69e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CToc::OnSiteMapContentsCommand(LONG_PTR dwNewLong, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  CHtmlHelpControl *v9; // rcx
  char *v10; // rbx
  HWND Parent; // rax
  unsigned __int64 v12; // r9
  HWND v13; // rax
  struct _tagSiteMapEntry *v14; // rdi
  struct CHtmlHelpControl *v15; // rbx
  HWND MessageParent; // rax
  __int64 v17; // r14
  CHtmlHelpControl *v18; // rcx
  __int64 v19; // rcx
  CHHWinType *v20; // rcx
  HWND v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  CHHWinType *v25; // rcx
  HWND v26; // rbx
  int j; // edi
  __int64 v28; // r13
  unsigned __int8 v29; // al
  int i; // edi
  unsigned __int8 v31; // al
  LPARAM v32; // r9
  char *v34; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR szTarget; // [rsp+48h] [rbp-B8h] BYREF
  struct tagTVITEMW v36; // [rsp+50h] [rbp-B0h] BYREF
  char v37[2184]; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+918h] [rbp+818h]

  v3 = a2 - 250;
  if ( !v3 )
  {
    *(_QWORD *)(dwNewLong + 400) = SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 9u, 0);
    CHourGlass::CHourGlass((CHourGlass *)&szTarget);
    SendMessageA(*(HWND *)(dwNewLong + 424), 0xBu, 0, 0);
    for ( i = 1; i <= *(_DWORD *)(dwNewLong + 64) - 1; ++i )
    {
      v34 = *(char **)(*(_QWORD *)(dwNewLong + 48) + 8LL * i);
      memset(&v36, 0, sizeof(v36));
      v36.hItem = *(HTREEITEM *)(*(_QWORD *)(dwNewLong + 384) + 8LL * i);
      v36.mask = 8;
      W_TreeView_GetItem_fn(*(HWND *)(dwNewLong + 424), &v36);
      if ( (v34[27] & 1) == 0 && (v36.state & 0x20) == 0 )
      {
        *(_DWORD *)(dwNewLong + 512) = 1;
        SendMessageA(*(HWND *)(dwNewLong + 424), 0x1102u, 2u, *(_QWORD *)(*(_QWORD *)(dwNewLong + 384) + 8LL * i));
        v31 = v34[24];
        if ( v31 < 8u )
          v34[24] = ++v31;
        Tree_SetImage(*(HWND *)(dwNewLong + 424), v31, *(struct _TREEITEM **)(*(_QWORD *)(dwNewLong + 384) + 8LL * i));
      }
    }
    SendMessageA(*(HWND *)(dwNewLong + 424), 0xBu, 1u, 0);
    v32 = *(_QWORD *)(dwNewLong + 400);
    if ( v32 )
    {
      *(_DWORD *)(dwNewLong + 408) = 1;
      *(_DWORD *)(dwNewLong + 512) = 1;
      SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 5u, v32);
      SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 9u, *(_QWORD *)(dwNewLong + 400));
      *(_DWORD *)(dwNewLong + 408) = 0;
    }
    SetCursor((HCURSOR)szTarget);
    goto LABEL_60;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    *(_QWORD *)(dwNewLong + 400) = SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 9u, 0);
    SendMessageA(*(HWND *)(dwNewLong + 424), 0xBu, 0, 0);
    for ( j = 1; j <= *(_DWORD *)(dwNewLong + 64) - 1; ++j )
    {
      v28 = *(_QWORD *)(*(_QWORD *)(dwNewLong + 48) + 8LL * j);
      memset(&v36, 0, sizeof(v36));
      v36.hItem = *(HTREEITEM *)(*(_QWORD *)(dwNewLong + 384) + 8LL * j);
      v36.mask = 8;
      W_TreeView_GetItem_fn(*(HWND *)(dwNewLong + 424), &v36);
      if ( (*(_BYTE *)(v28 + 27) & 1) == 0 && (v36.state & 0x20) != 0 )
      {
        *(_DWORD *)(dwNewLong + 512) = 1;
        SendMessageA(*(HWND *)(dwNewLong + 424), 0x1102u, 1u, *(_QWORD *)(*(_QWORD *)(dwNewLong + 384) + 8LL * j));
        v29 = *(_BYTE *)(v28 + 24);
        if ( v29 <= 8u )
          *(_BYTE *)(v28 + 24) = --v29;
        Tree_SetImage(*(HWND *)(dwNewLong + 424), v29, *(struct _TREEITEM **)(*(_QWORD *)(dwNewLong + 384) + 8LL * j));
      }
    }
    SendMessageA(*(HWND *)(dwNewLong + 424), 0xBu, 1u, 0);
LABEL_60:
    *(_DWORD *)(dwNewLong + 512) = 0;
    return 0;
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 3;
      if ( v7 )
      {
        v8 = v7 - 61182;
        if ( v8 )
        {
          if ( v8 == 1 )
          {
            v34 = 0;
            v9 = *(CHtmlHelpControl **)(dwNewLong + 496);
            if ( v9 )
              CHtmlHelpControl::GetCurrentUrl(v9, (struct CStr *)&v34);
            else
              COleDispatchDriver::InvokeHelper(
                *(COleDispatchDriver **)(*(_QWORD *)(*(_QWORD *)(dwNewLong + 536) + 600LL) + 152LL),
                211,
                2u,
                8u,
                &v34,
                0);
            v10 = v34;
            Parent = GetParent(*(HWND *)(dwNewLong + 424));
            if ( (unsigned int)doJumpUrl(Parent, v10, v37, v12) && v37[0] )
            {
              if ( *(_QWORD *)(dwNewLong + 496) )
              {
                szTarget = 0;
                CWStr::operator=(&szTarget, v37);
                if ( !(unsigned int)CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(
                                      *(CHtmlHelpControl **)(dwNewLong + 496),
                                      szTarget,
                                      *(struct IUnknown **)(*(_QWORD *)(dwNewLong + 496) + 8LL)) )
                  HlinkSimpleNavigateToString(
                    szTarget,
                    0,
                    0,
                    *(IUnknown **)(*(_QWORD *)(dwNewLong + 496) + 8LL),
                    0,
                    0,
                    0,
                    0);
                CWStr::~CWStr((CWStr *)&szTarget);
              }
              else
              {
                v13 = GetParent(*(HWND *)(dwNewLong + 424));
                ChangeHtmlTopic(v37, v13, 0);
              }
            }
            CWStr::~CWStr((CWStr *)&v34);
          }
        }
        else
        {
          memset(&v36, 0, sizeof(v36));
          v36.hItem = (HTREEITEM)SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 9u, 0);
          if ( v36.hItem )
          {
            v36.mask = 4;
            W_TreeView_GetItem_fn(*(HWND *)(dwNewLong + 424), &v36);
            v14 = *(struct _tagSiteMapEntry **)(*(_QWORD *)(dwNewLong + 48) + 8LL * SLODWORD(v36.lParam));
            v15 = *(struct CHtmlHelpControl **)(dwNewLong + 496);
            MessageParent = FindMessageParent(*(HWND *)(dwNewLong + 424));
            DisplayAuthorInfo(
              *(struct CInfoType **)(dwNewLong + 560),
              (struct CSiteMap *)(dwNewLong + 32),
              v14,
              MessageParent,
              v15);
          }
        }
      }
      else
      {
        memset(&v36, 0, sizeof(v36));
        v36.mask = 4;
        if ( *(_QWORD *)(dwNewLong + 400) )
        {
          v36.hItem = *(HTREEITEM *)(dwNewLong + 400);
          W_TreeView_GetItem_fn(*(HWND *)(dwNewLong + 424), &v36);
          v17 = *(_QWORD *)(*(_QWORD *)(dwNewLong + 48) + 8LL * SLODWORD(v36.lParam));
          if ( *(_QWORD *)(v17 + 32) )
          {
            *(_DWORD *)(dwNewLong + 412) = 1;
            *(_DWORD *)(dwNewLong + 532) = 1;
            if ( (*(_BYTE *)(v17 + 27) & 0x20) != 0 && (v18 = *(CHtmlHelpControl **)(dwNewLong + 496)) != 0 )
            {
              CHtmlHelpControl::SendEvent(v18, *(const char **)(*(_QWORD *)(v17 + 32) + 8LL));
            }
            else
            {
              CToc::SaveCurUrl((CToc *)dwNewLong);
              JumpToUrl(
                *(struct IUnknown **)(dwNewLong + 504),
                *(HWND *)(dwNewLong + 424),
                (struct _tagSiteMapEntry *)v17,
                *(struct CInfoType **)(dwNewLong + 560),
                (PCSTR *)(dwNewLong + 32),
                0,
                0,
                *(struct CHtmlHelpControl **)(dwNewLong + 496));
            }
          }
          v19 = *(_QWORD *)(dwNewLong + 536);
          if ( v19 )
            *(_QWORD *)(v19 + 328) = *(_QWORD *)(dwNewLong + 424);
        }
      }
    }
    else
    {
      v20 = *(CHHWinType **)(dwNewLong + 536);
      if ( v20 )
      {
        if ( !(unsigned int)CHHWinType::OnTrackNotifyCaller(v20, 14) )
          CHHWinType::OnPrint(*(CHHWinType **)(dwNewLong + 536));
      }
      else
      {
        v21 = GetParent(*(HWND *)(dwNewLong + 424));
        CPrint::CPrint((CPrint *)v37, v21);
        v38 = 1;
        if ( (unsigned int)CDlg::DoModal((LPARAM)v37) )
          PrintTopics(
            v38,
            (struct CToc *)dwNewLong,
            *(struct IWebBrowserAppImpl **)(*(_QWORD *)(dwNewLong + 496) + 496LL),
            *(HWND *)(*(_QWORD *)(dwNewLong + 496) + 448LL));
        CDlg::~CDlg((CDlg *)v37);
      }
    }
  }
  else
  {
    v22 = *(_QWORD *)(dwNewLong + 536);
    if ( v22 )
    {
      v23 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v22 + 608) + 128LL) + 40LL);
      v24 = *(_QWORD *)(v23 + 88);
      if ( v24 )
        *(_QWORD *)(v23 + 120) = v24;
    }
    if ( (unsigned int)ChooseInformationTypes(
                         *(struct CInfoType **)(dwNewLong + 560),
                         (struct CSiteMap *)(dwNewLong + 32),
                         *(HWND *)(dwNewLong + 424),
                         *(struct CHtmlHelpControl **)(dwNewLong + 496)) )
    {
      v25 = *(CHHWinType **)(dwNewLong + 536);
      if ( v25 )
      {
        CHHWinType::UpdateInformationTypes(v25);
      }
      else
      {
        v26 = GetParent(*(HWND *)(dwNewLong + 424));
        RemovePropA(*(HWND *)(dwNewLong + 424), "HHDefProc");
        DestroyWindow(*(HWND *)(dwNewLong + 424));
        (*(void (__fastcall **)(LONG_PTR, HWND))(*(_QWORD *)dwNewLong + 8LL))(dwNewLong, v26);
        CToc::InitTreeView(dwNewLong);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001b530  push    rbp
0x18001b532  push    rbx
0x18001b533  push    rsi
0x18001b534  push    rdi
0x18001b535  push    r12
0x18001b537  push    r13
0x18001b539  push    r14
0x18001b53b  push    r15
0x18001b53d  lea     rbp, [rsp-838h]
0x18001b545  sub     rsp, 938h
0x18001b54c  mov     rax, cs:__security_cookie
0x18001b553  xor     rax, rsp
0x18001b556  mov     [rbp+870h+var_50], rax
0x18001b55d  mov     rsi, rcx
0x18001b560  sub     edx, 0FAh
0x18001b566  jz      loc_18001BABB
0x18001b56c  sub     edx, 1
0x18001b56f  jz      loc_18001B997
0x18001b575  sub     edx, 1
0x18001b578  jz      loc_18001B8E0
0x18001b57e  sub     edx, 1
0x18001b581  jz      loc_18001B84D
0x18001b587  sub     edx, 3
0x18001b58a  jz      loc_18001B75B
0x18001b590  sub     edx, 0EEFEh
0x18001b596  jz      loc_18001B6C4
0x18001b59c  cmp     edx, 1
0x18001b59f  jnz     loc_18001BC5B
0x18001b5a5  xor     edi, edi
0x18001b5a7  mov     [rsp+970h+var_930], rdi
0x18001b5ac  mov     rcx, [rcx+1F0h]; this
0x18001b5b3  test    rcx, rcx
0x18001b5b6  jz      short loc_18001B5C4
0x18001b5b8  lea     rdx, [rsp+970h+var_930]; struct CStr *
0x18001b5bd  call    ?GetCurrentUrl@CHtmlHelpControl@@QEAA_NAEAVCStr@@@Z; CHtmlHelpControl::GetCurrentUrl(CStr &)
0x18001b5c2  jmp     short loc_18001B5FC
0x18001b5c4  mov     r9d, 8; unsigned __int16
0x18001b5ca  lea     r8d, [r9-6]; unsigned __int16
0x18001b5ce  mov     rax, [rsi+218h]
0x18001b5d5  mov     rcx, [rax+258h]
0x18001b5dc  mov     [rsp+970h+var_948], rdi; unsigned __int8 *
0x18001b5e1  lea     rax, [rsp+970h+var_930]
0x18001b5e6  mov     [rsp+970h+pbc], rax; void *
0x18001b5eb  mov     edx, 0D3h; int
0x18001b5f0  mov     rcx, [rcx+98h]; this
0x18001b5f7  call    ?InvokeHelper@COleDispatchDriver@@QEAAXJGGPEAXPEBEZZ; COleDispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x18001b5fc  mov     rbx, [rsp+970h+var_930]
0x18001b601  mov     rcx, [rsi+1A8h]; hWnd
0x18001b608  call    cs:__imp_GetParent
0x18001b60e  lea     r8, [rbp+870h+var_8E0]; char *
0x18001b612  mov     rdx, rbx; char *
0x18001b615  mov     rcx, rax; HWND
0x18001b618  call    ?doJumpUrl@@YAHPEAUHWND__@@PEBDPEAD_K@Z; doJumpUrl(HWND__ *,char const *,char *,unsigned __int64)
0x18001b61d  test    eax, eax
0x18001b61f  jz      short loc_18001B668
0x18001b621  cmp     [rbp+870h+var_8E0], dil
0x18001b625  jz      short loc_18001B668
0x18001b627  cmp     [rsi+1F0h], rdi
0x18001b62e  jz      short loc_18001B6A6
0x18001b630  mov     [rsp+970h+szTarget], rdi
0x18001b635  lea     rdx, [rbp+870h+var_8E0]
0x18001b639  lea     rcx, [rsp+970h+szTarget]
0x18001b63e  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x18001b643  nop
0x18001b644  mov     rcx, [rsi+1F0h]; this
0x18001b64b  mov     r8, [rcx+8]; struct IUnknown *
0x18001b64f  mov     rdx, [rsp+970h+szTarget]; unsigned __int16 *
0x18001b654  call    ?CheckDestUrlSafetyThruMoniker@CHtmlHelpControl@@QEAAJPEBGPEAUIUnknown@@@Z; CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(ushort const *,IUnknown *)
0x18001b659  test    eax, eax
0x18001b65b  jz      short loc_18001B677
0x18001b65d  lea     rcx, [rsp+970h+szTarget]; this
0x18001b662  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18001b667  nop
0x18001b668  lea     rcx, [rsp+970h+var_930]; this
0x18001b66d  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18001b672  jmp     loc_18001BC5B
0x18001b677  mov     r9, [rsi+1F0h]
0x18001b67e  mov     [rsp+970h+dwReserved], edi; dwReserved
0x18001b682  mov     [rsp+970h+grfHLNF], edi; grfHLNF
0x18001b686  mov     [rsp+970h+var_948], rdi; IBindStatusCallback *
0x18001b68b  mov     [rsp+970h+pbc], rdi; pbc
0x18001b690  mov     r9, [r9+8]; pUnk
0x18001b694  xor     r8d, r8d; szTargetFrameName
0x18001b697  xor     edx, edx; szLocation
0x18001b699  mov     rcx, [rsp+970h+szTarget]; szTarget
0x18001b69e  call    cs:__imp_HlinkSimpleNavigateToString
0x18001b6a4  jmp     short loc_18001B65D
0x18001b6a6  mov     rcx, [rsi+1A8h]; hWnd
0x18001b6ad  call    cs:__imp_GetParent
0x18001b6b3  mov     rdx, rax; hWnd
0x18001b6b6  xor     r8d, r8d; int
0x18001b6b9  lea     rcx, [rbp+870h+var_8E0]; char *
0x18001b6bd  call    ?ChangeHtmlTopic@@YAPEAUHWND__@@PEBDPEAU1@H@Z; ChangeHtmlTopic(char const *,HWND__ *,int)
0x18001b6c2  jmp     short loc_18001B668
0x18001b6c4  xorps   xmm0, xmm0
0x18001b6c7  xor     eax, eax
0x18001b6c9  movups  xmmword ptr [rsp+970h+var_920.mask], xmm0
0x18001b6ce  movups  xmmword ptr [rsp+970h+var_920.state], xmm0
0x18001b6d3  movups  xmmword ptr [rsp+970h+var_920.cchTextMax], xmm0
0x18001b6d8  mov     [rbp+870h+var_920.lParam], rax
0x18001b6dc  xor     r9d, r9d; lParam
0x18001b6df  mov     edx, 110Ah; Msg
0x18001b6e4  lea     r8d, [rax+9]; wParam
0x18001b6e8  mov     rcx, [rcx+1A8h]; hWnd
0x18001b6ef  call    cs:__imp_SendMessageA
0x18001b6f5  mov     [rsp+970h+var_920.hItem], rax
0x18001b6fa  test    rax, rax
0x18001b6fd  jz      loc_18001BC5B
0x18001b703  mov     [rsp+970h+var_920.mask], 4
0x18001b70b  lea     rdx, [rsp+970h+var_920]; struct tagTVITEMW *
0x18001b710  mov     rcx, [rsi+1A8h]; HWND
0x18001b717  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001b71c  movsxd  rdx, dword ptr [rbp+870h+var_920.lParam]
0x18001b720  mov     rax, [rsi+30h]
0x18001b724  mov     rdi, [rax+rdx*8]
0x18001b728  mov     rbx, [rsi+1F0h]
0x18001b72f  mov     rcx, [rsi+1A8h]; HWND
0x18001b736  call    ?FindMessageParent@@YAPEAUHWND__@@PEAU1@@Z; FindMessageParent(HWND__ *)
0x18001b73b  lea     rdx, [rsi+20h]; struct CSiteMap *
0x18001b73f  mov     [rsp+970h+pbc], rbx; struct CHtmlHelpControl *
0x18001b744  mov     r9, rax; HWND
0x18001b747  mov     r8, rdi; struct _tagSiteMapEntry *
0x18001b74a  mov     rcx, [rsi+230h]; struct CInfoType *
0x18001b751  call    ?DisplayAuthorInfo@@YAXPEAVCInfoType@@PEAVCSiteMap@@PEAU_tagSiteMapEntry@@PEAUHWND__@@PEAVCHtmlHelpControl@@@Z; DisplayAuthorInfo(CInfoType *,CSiteMap *,_tagSiteMapEntry *,HWND__ *,CHtmlHelpControl *)
0x18001b756  jmp     loc_18001BC5B
0x18001b75b  xorps   xmm0, xmm0
0x18001b75e  xor     eax, eax
0x18001b760  movups  xmmword ptr [rsp+970h+var_920.mask], xmm0
0x18001b765  movups  xmmword ptr [rsp+970h+var_920.state], xmm0
0x18001b76a  movups  xmmword ptr [rsp+970h+var_920.cchTextMax], xmm0
0x18001b76f  mov     [rbp+870h+var_920.lParam], rax
0x18001b773  mov     [rsp+970h+var_920.mask], 4
0x18001b77b  mov     rax, [rcx+190h]
0x18001b782  xor     edi, edi
0x18001b784  test    rax, rax
0x18001b787  jz      loc_18001BC5B
0x18001b78d  mov     [rsp+970h+var_920.hItem], rax
0x18001b792  lea     rdx, [rsp+970h+var_920]; struct tagTVITEMW *
0x18001b797  mov     rcx, [rcx+1A8h]; HWND
0x18001b79e  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001b7a3  movsxd  rcx, dword ptr [rbp+870h+var_920.lParam]
0x18001b7a7  mov     rax, [rsi+30h]
0x18001b7ab  mov     r14, [rax+rcx*8]
0x18001b7af  cmp     [r14+20h], rdi
0x18001b7b3  jz      short loc_18001B82A
0x18001b7b5  lea     ebx, [rdi+1]
0x18001b7b8  mov     [rsi+19Ch], ebx
0x18001b7be  mov     [rsi+214h], ebx
0x18001b7c4  test    byte ptr [r14+1Bh], 20h
0x18001b7c9  jz      short loc_18001B7E6
0x18001b7cb  mov     rcx, [rsi+1F0h]; this
0x18001b7d2  test    rcx, rcx
0x18001b7d5  jz      short loc_18001B7E6
0x18001b7d7  mov     rdx, [r14+20h]
0x18001b7db  mov     rdx, [rdx+8]; char *
0x18001b7df  call    ?SendEvent@CHtmlHelpControl@@QEAAJPEBD@Z; CHtmlHelpControl::SendEvent(char const *)
0x18001b7e4  jmp     short loc_18001B82A
0x18001b7e6  mov     rcx, rsi; this
0x18001b7e9  call    ?SaveCurUrl@CToc@@QEAAXXZ; CToc::SaveCurUrl(void)
0x18001b7ee  lea     rcx, [rsi+20h]
0x18001b7f2  mov     rax, [rsi+1F0h]
0x18001b7f9  mov     qword ptr [rsp+970h+dwReserved], rax; struct CHtmlHelpControl *
0x18001b7fe  mov     qword ptr [rsp+970h+grfHLNF], rdi; struct IWebBrowserAppImpl *
0x18001b803  mov     [rsp+970h+var_948], rdi; struct SITE_ENTRY_URL *
0x18001b808  mov     [rsp+970h+pbc], rcx; struct CSiteMap *
0x18001b80d  mov     r9, [rsi+230h]; struct CInfoType *
0x18001b814  mov     r8, r14; struct _tagSiteMapEntry *
0x18001b817  mov     rdx, [rsi+1A8h]; HWND
0x18001b81e  mov     rcx, [rsi+1F8h]; struct IUnknown *
0x18001b825  call    ?JumpToUrl@@YAPEAUHWND__@@PEAUIUnknown@@PEAU1@PEAU_tagSiteMapEntry@@PEAVCInfoType@@PEAVCSiteMap@@PEAUSITE_ENTRY_URL@@PEAVIWebBrowserAppImpl@@PEAVCHtmlHelpControl@@@Z; JumpToUrl(IUnknown *,HWND__ *,_tagSiteMapEntry *,CInfoType *,CSiteMap *,SITE_ENTRY_URL *,IWebBrowserAppImpl *,CHtmlHelpControl *)
0x18001b82a  mov     rcx, [rsi+218h]
0x18001b831  test    rcx, rcx
0x18001b834  jz      loc_18001BC5B
0x18001b83a  mov     rax, [rsi+1A8h]
0x18001b841  mov     [rcx+148h], rax
0x18001b848  jmp     loc_18001BC5B
0x18001b84d  mov     rcx, [rcx+218h]; this
0x18001b854  test    rcx, rcx
0x18001b857  jz      short loc_18001B87C
0x18001b859  mov     edx, 0Eh; int
0x18001b85e  call    ?OnTrackNotifyCaller@CHHWinType@@QEAAHH@Z; CHHWinType::OnTrackNotifyCaller(int)
0x18001b863  test    eax, eax
0x18001b865  jnz     loc_18001BC5B
0x18001b86b  mov     rcx, [rsi+218h]; this
0x18001b872  call    ?OnPrint@CHHWinType@@QEAAXXZ; CHHWinType::OnPrint(void)
0x18001b877  jmp     loc_18001BC5B
0x18001b87c  mov     rcx, [rsi+1A8h]; hWnd
0x18001b883  call    cs:__imp_GetParent
0x18001b889  mov     rdx, rax; HWND
0x18001b88c  lea     rcx, [rbp+870h+var_8E0]; this
0x18001b890  call    ??0CPrint@@QEAA@PEAUHWND__@@@Z; CPrint::CPrint(HWND__ *)
0x18001b895  nop
0x18001b896  mov     ebx, 1
0x18001b89b  mov     [rbp+870h+var_58], ebx
0x18001b8a1  lea     rcx, [rbp+870h+var_8E0]; this
0x18001b8a5  call    ?DoModal@CDlg@@QEAAHXZ; CDlg::DoModal(void)
0x18001b8aa  test    eax, eax
0x18001b8ac  jz      short loc_18001B8D2
0x18001b8ae  mov     r8, [rsi+1F0h]
0x18001b8b5  mov     r9, [r8+1C0h]; HWND
0x18001b8bc  mov     r8, [r8+1F0h]; this
0x18001b8c3  mov     rdx, rsi; struct CToc *
0x18001b8c6  mov     ecx, [rbp+870h+var_58]; int
0x18001b8cc  call    ?PrintTopics@@YAXHPEAVCToc@@PEAVIWebBrowserAppImpl@@PEAUHWND__@@@Z; PrintTopics(int,CToc *,IWebBrowserAppImpl *,HWND__ *)
0x18001b8d1  nop
0x18001b8d2  lea     rcx, [rbp+870h+var_8E0]; this
0x18001b8d6  call    ??1CDlg@@QEAA@XZ; CDlg::~CDlg(void)
0x18001b8db  jmp     loc_18001BC5B
0x18001b8e0  mov     rax, [rcx+218h]
0x18001b8e7  test    rax, rax
0x18001b8ea  jz      short loc_18001B90B
0x18001b8ec  mov     rax, [rax+260h]
0x18001b8f3  mov     rcx, [rax+80h]
0x18001b8fa  mov     rax, [rcx+28h]
0x18001b8fe  mov     rcx, [rax+58h]
0x18001b902  test    rcx, rcx
0x18001b905  jz      short loc_18001B90B
0x18001b907  mov     [rax+78h], rcx
0x18001b90b  lea     rdx, [rsi+20h]; struct CSiteMap *
0x18001b90f  mov     r9, [rsi+1F0h]; struct CHtmlHelpControl *
0x18001b916  mov     r8, [rsi+1A8h]; HWND
0x18001b91d  mov     rcx, [rsi+230h]; struct CInfoType *
0x18001b924  call    ?ChooseInformationTypes@@YAHPEAVCInfoType@@PEAVCSiteMap@@PEAUHWND__@@PEAVCHtmlHelpControl@@@Z; ChooseInformationTypes(CInfoType *,CSiteMap *,HWND__ *,CHtmlHelpControl *)
0x18001b929  test    eax, eax
0x18001b92b  jz      loc_18001BC5B
0x18001b931  mov     rcx, [rsi+218h]; this
0x18001b938  test    rcx, rcx
0x18001b93b  jz      short loc_18001B947
0x18001b93d  call    ?UpdateInformationTypes@CHHWinType@@QEAAXXZ; CHHWinType::UpdateInformationTypes(void)
0x18001b942  jmp     loc_18001BC5B
0x18001b947  mov     rcx, [rsi+1A8h]; hWnd
0x18001b94e  call    cs:__imp_GetParent
0x18001b954  mov     rbx, rax
0x18001b957  lea     rdx, aHhdefproc; "HHDefProc"
0x18001b95e  mov     rcx, [rsi+1A8h]; hWnd
0x18001b965  call    cs:__imp_RemovePropA
0x18001b96b  mov     rcx, [rsi+1A8h]; hWnd
0x18001b972  call    cs:__imp_DestroyWindow
0x18001b978  mov     rcx, [rsi]
0x18001b97b  mov     rax, [rcx+8]
0x18001b97f  mov     rdx, rbx
0x18001b982  mov     rcx, rsi
0x18001b985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b98a  mov     rcx, rsi; dwNewLong
0x18001b98d  call    ?InitTreeView@CToc@@QEAAHXZ; CToc::InitTreeView(void)
0x18001b992  jmp     loc_18001BC5B
0x18001b997  xor     r9d, r9d; lParam
0x18001b99a  mov     edx, 110Ah; Msg
0x18001b99f  lea     r8d, [r9+9]; wParam
0x18001b9a3  mov     rcx, [rcx+1A8h]; hWnd
0x18001b9aa  call    cs:__imp_SendMessageA
0x18001b9b0  mov     [rsi+190h], rax
0x18001b9b7  xor     r9d, r9d; lParam
0x18001b9ba  xor     r8d, r8d; wParam
0x18001b9bd  lea     r12d, [r9+0Bh]
0x18001b9c1  mov     edx, r12d; Msg
0x18001b9c4  mov     rcx, [rsi+1A8h]; hWnd
0x18001b9cb  call    cs:__imp_SendMessageA
0x18001b9d1  lea     ebx, [r12-0Ah]
0x18001b9d6  mov     edi, ebx
0x18001b9d8  mov     eax, [rsi+40h]
0x18001b9db  sub     eax, ebx
0x18001b9dd  cmp     eax, ebx
0x18001b9df  jl      loc_18001BA9E
0x18001b9e5  lea     r14d, [r12-3]
0x18001b9ea  movsxd  r15, edi
0x18001b9ed  mov     rax, [rsi+30h]
0x18001b9f1  mov     r13, [rax+r15*8]
0x18001b9f5  xorps   xmm0, xmm0
0x18001b9f8  xor     eax, eax
0x18001b9fa  movups  xmmword ptr [rsp+970h+var_920.mask], xmm0
0x18001b9ff  movups  xmmword ptr [rsp+970h+var_920.state], xmm0
0x18001ba04  movups  xmmword ptr [rsp+970h+var_920.cchTextMax], xmm0
0x18001ba09  mov     [rbp+870h+var_920.lParam], rax
0x18001ba0d  mov     rax, [rsi+180h]
0x18001ba14  mov     rcx, [rax+r15*8]
0x18001ba18  mov     [rsp+970h+var_920.hItem], rcx
0x18001ba1d  mov     [rsp+970h+var_920.mask], r14d
0x18001ba22  lea     rdx, [rsp+970h+var_920]; struct tagTVITEMW *
0x18001ba27  mov     rcx, [rsi+1A8h]; HWND
0x18001ba2e  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001ba33  test    [r13+1Bh], bl
0x18001ba37  jnz     short loc_18001BA8F
0x18001ba39  test    byte ptr [rsp+970h+var_920.state], 20h
0x18001ba3e  jz      short loc_18001BA8F
0x18001ba40  mov     [rsi+200h], ebx
0x18001ba46  mov     r9, [rsi+180h]
0x18001ba4d  mov     r9, [r9+r15*8]; lParam
0x18001ba51  mov     r8, rbx; wParam
0x18001ba54  mov     edx, 1102h; Msg
0x18001ba59  mov     rcx, [rsi+1A8h]; hWnd
0x18001ba60  call    cs:__imp_SendMessageA
0x18001ba66  mov     al, [r13+18h]
0x18001ba6a  cmp     al, r14b
0x18001ba6d  ja      short loc_18001BA75
0x18001ba6f  sub     al, bl
0x18001ba71  mov     [r13+18h], al
0x18001ba75  mov     r8, [rsi+180h]
0x18001ba7c  movzx   edx, al; int
0x18001ba7f  mov     r8, [r8+r15*8]; struct _TREEITEM *
  ... truncated ...
```
