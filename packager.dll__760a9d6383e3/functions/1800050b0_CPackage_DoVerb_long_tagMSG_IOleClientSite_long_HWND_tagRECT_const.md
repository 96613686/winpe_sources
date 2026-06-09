# CPackage::DoVerb(long,tagMSG *,IOleClientSite *,long,HWND__ *,tagRECT const *)

- ea: `0x1800050b0`
- end: `0x180005431`
- name: `?DoVerb@CPackage@@UEAAJJPEAUtagMSG@@PEAUIOleClientSite@@JPEAUHWND__@@PEBUtagRECT@@@Z`
- size: `897`
- prototype: `__int64 __fastcall(CPackage *__hidden this, int, struct tagMSG *, struct IOleClientSite *, int, HWND hWnd, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800050b0`
- `0x1800059e4`
- `0x18000642c`
- `0x180007934`
- `0x180008600`
- `0x180009144`
- `0x18000b328`
- `0x18000bda0`
- `0x18000cbbe`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005341`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000534f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005341`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000534f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000529e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000529e`
- `KERNEL32!lstrlenW` at `0x1800053f0`
- `KERNEL32!lstrlenW` at `0x1800053f0`
- `USER32!CreatePopupMenu` at `0x1800051ad`
- `USER32!CreatePopupMenu` at `0x1800051ad`
- `USER32!GetMenuItemInfoW` at `0x180005224`
- `USER32!GetMenuItemInfoW` at `0x180005224`
- `USER32!MessageBoxW` at `0x180005322`
- `USER32!MessageBoxW` at `0x180005322`
- `USER32!DestroyMenu` at `0x1800053ac`
- `USER32!DestroyMenu` at `0x1800053ac`

## pseudocode

```c
__int64 __fastcall CPackage::DoVerb(
        CPackage *this,
        int a2,
        struct tagMSG *a3,
        struct IOleClientSite *a4,
        int a5,
        HWND hWnd,
        const struct tagRECT *a7)
{
  int v8; // edi
  __int64 v10; // rax
  __int64 v11; // rax
  CPackage *v12; // r14
  signed int ContextMenu; // ebx
  HMENU PopupMenu; // rax
  __int64 v15; // r15
  HMENU v16; // r12
  LSTATUS ValueW; // eax
  __int64 v18; // rdx
  bool v19; // sf
  int v20; // eax
  __int64 v21; // rdx
  WCHAR *v22; // rsi
  int v23; // eax
  WCHAR *v24; // rdi
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpText; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h]
  _QWORD v30[3]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+80h] [rbp-80h]
  int v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+94h] [rbp-6Ch]
  int v34; // [rsp+9Ch] [rbp-64h]
  tagMENUITEMINFOW mii; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v36[520]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR String[524]; // [rsp+2F8h] [rbp+1F8h] BYREF

  v8 = a2;
  if ( a2 < -2 )
    return 2147500033LL;
  if ( a2 == -1 )
  {
    v10 = *((_QWORD *)this + 12);
    if ( v10 && *(_WORD *)(v10 + 72) || (v11 = *((_QWORD *)this + 13)) != 0 && v11 != -4 )
    {
      v12 = (CPackage *)((char *)this - 16);
      return CPackage::_ExecuteAttachment(v12, 0, a3, a4, a5, hWnd, a7);
    }
    goto LABEL_41;
  }
  if ( a2 == 2 && (v8 = *((_DWORD *)this + 56), v8 == -1) || v8 == -2 )
  {
LABEL_41:
    memset_0(v36, 0, 0x620u);
    PackWiz_CreateWizard(hWnd, (struct _packageInfo *)v36);
    if ( lstrlenW(String) )
      return CPackage::InitFromPackInfo((CPackage *)((char *)this - 16), (struct _packageInfo *)v36);
    else
      return 262529;
  }
  v12 = (CPackage *)((char *)this - 16);
  if ( v8 == 1 )
    return CPackage::_ChangePackageLabel((CPackage *)((char *)this - 16), hWnd);
  if ( !v8 )
    return CPackage::_ExecuteAttachment(v12, 0, a3, a4, a5, hWnd, a7);
  *(_QWORD *)pcbData = 0;
  ContextMenu = CPackage::GetContextMenu((CPackage *)((char *)this - 16), (struct IContextMenu **)pcbData);
  if ( ContextMenu >= 0 )
  {
    PopupMenu = CreatePopupMenu();
    v15 = *(_QWORD *)pcbData;
    v16 = PopupMenu;
    if ( PopupMenu )
    {
      ContextMenu = (*(__int64 (__fastcall **)(_QWORD, HMENU, _QWORD, __int64, int, _DWORD))(**(_QWORD **)pcbData + 24LL))(
                      *(_QWORD *)pcbData,
                      PopupMenu,
                      0,
                      2,
                      0xFFFF,
                      0);
      if ( ContextMenu >= 0 )
      {
        memset_0(&mii, 0, sizeof(mii));
        mii.cbSize = 80;
        mii.fMask = 2;
        if ( GetMenuItemInfoW(v16, v8 - 2, 1, &mii) )
        {
          if ( *((_DWORD *)this + 22) != 3
            || (ContextMenu = CPackage::CreateTempFile((CPackage *)((char *)this - 16)), ContextMenu >= 0) )
          {
            if ( v8 == *((_DWORD *)this + 56) )
              goto LABEL_35;
            pvData = 0;
            pcbData[0] = 4;
            ValueW = RegGetValueW(
                       HKEY_LOCAL_MACHINE,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Packager",
                       L"SkipPromptOnDoVerb",
                       0x10u,
                       0,
                       &pvData,
                       pcbData);
            v19 = ValueW < 0;
            if ( ValueW > 0 )
              v19 = 1;
            if ( !v19 && pvData == 1 )
              goto LABEL_35;
            lpText = 0;
            v28 = 0;
            v29 = 0;
            v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                    &lpText,
                    v18,
                    3013);
            v22 = (WCHAR *)lpText;
            ContextMenu = v20;
            if ( v20 >= 0 )
            {
              lpText = 0;
              v28 = 0;
              v29 = 0;
              v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                      &lpText,
                      v21,
                      3012);
              v24 = (WCHAR *)lpText;
              ContextMenu = v23;
              if ( v23 >= 0 )
                ContextMenu = MessageBoxW(hWnd, lpText, v22, 0x10131u) != 1 ? 0x800704C7 : 0;
              if ( v24 )
                CoTaskMemFree(v24);
            }
            if ( v22 )
              CoTaskMemFree(v22);
            if ( ContextMenu >= 0 )
            {
LABEL_35:
              v33 = 0;
              v30[2] = mii.wID - 2;
              v34 = 0;
              v30[0] = 56;
              v30[1] = 0;
              v31 = 0;
              v32 = 1;
              ContextMenu = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v15 + 32LL))(v15, v30);
            }
          }
        }
        else
        {
          ContextMenu = 262529;
        }
      }
      DestroyMenu(v16);
    }
    else
    {
      ContextMenu = -2147024882;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return (unsigned int)ContextMenu;
}

```

## disassembly

```asm
0x1800050b0  push    rbp
0x1800050b2  push    rbx
0x1800050b3  push    rsi
0x1800050b4  push    rdi
0x1800050b5  push    r12
0x1800050b7  push    r13
0x1800050b9  push    r14
0x1800050bb  push    r15
0x1800050bd  lea     rbp, [rsp-628h]
0x1800050c5  sub     rsp, 728h
0x1800050cc  mov     rax, cs:__security_cookie
0x1800050d3  xor     rax, rsp
0x1800050d6  mov     [rbp+660h+var_50], rax
0x1800050dd  mov     r13, [rbp+660h+hWnd]
0x1800050e4  mov     rsi, rcx
0x1800050e7  mov     rcx, [rbp+660h+arg_30]
0x1800050ee  mov     edi, edx
0x1800050f0  cmp     edx, 0FFFFFFFEh
0x1800050f3  jge     short loc_1800050FF
0x1800050f5  mov     eax, 80004001h
0x1800050fa  jmp     loc_18000540E
0x1800050ff  xor     r15d, r15d
0x180005102  cmp     edx, 0FFFFFFFFh
0x180005105  jnz     short loc_180005134
0x180005107  mov     rax, [rsi+60h]
0x18000510b  test    rax, rax
0x18000510e  jz      short loc_180005117
0x180005110  cmp     [rax+48h], r15w
0x180005115  jnz     short loc_18000512E
0x180005117  mov     rax, [rsi+68h]
0x18000511b  test    rax, rax
0x18000511e  jz      loc_1800053CC
0x180005124  add     rax, 4
0x180005128  jz      loc_1800053CC
0x18000512e  lea     r14, [rsi-10h]
0x180005132  jmp     short loc_18000516E
0x180005134  cmp     edx, 2
0x180005137  jnz     short loc_180005148
0x180005139  mov     edi, [rsi+0E0h]
0x18000513f  cmp     edi, 0FFFFFFFFh
0x180005142  jz      loc_1800053CC
0x180005148  cmp     edi, 0FFFFFFFEh
0x18000514b  jz      loc_1800053CC
0x180005151  lea     r14, [rsi-10h]
0x180005155  cmp     edi, 1
0x180005158  jnz     short loc_18000516A
0x18000515a  mov     rdx, r13; hWndParent
0x18000515d  mov     rcx, r14; this
0x180005160  call    ?_ChangePackageLabel@CPackage@@IEAAJPEAUHWND__@@@Z; CPackage::_ChangePackageLabel(HWND__ *)
0x180005165  jmp     loc_18000540E
0x18000516a  test    edi, edi
0x18000516c  jnz     short loc_180005191
0x18000516e  mov     eax, [rbp+660h+arg_20]
0x180005174  xor     edx, edx; int
0x180005176  mov     [rsp+760h+pcbData], rcx; struct tagRECT *
0x18000517b  mov     rcx, r14; this
0x18000517e  mov     [rsp+760h+pvData], r13; HWND
0x180005183  mov     dword ptr [rsp+760h+pdwType], eax; int
0x180005187  call    ?_ExecuteAttachment@CPackage@@IEAAJJPEAUtagMSG@@PEAUIOleClientSite@@JPEAUHWND__@@PEBUtagRECT@@@Z; CPackage::_ExecuteAttachment(long,tagMSG *,IOleClientSite *,long,HWND__ *,tagRECT const *)
0x18000518c  jmp     loc_18000540E
0x180005191  lea     rdx, [rsp+760h+var_718]; struct IContextMenu **
0x180005196  mov     qword ptr [rsp+760h+var_718], r15
0x18000519b  mov     rcx, r14; this
0x18000519e  call    ?GetContextMenu@CPackage@@IEAAJPEAPEAUIContextMenu@@@Z; CPackage::GetContextMenu(IContextMenu * *)
0x1800051a3  mov     ebx, eax
0x1800051a5  test    eax, eax
0x1800051a7  js      loc_1800053C8
0x1800051ad  call    cs:__imp_CreatePopupMenu
0x1800051b3  mov     r15, qword ptr [rsp+760h+var_718]
0x1800051b8  mov     r12, rax
0x1800051bb  test    rax, rax
0x1800051be  jz      loc_1800053B4
0x1800051c4  mov     rcx, [r15]
0x1800051c7  mov     r9d, 2
0x1800051cd  mov     dword ptr [rsp+760h+pvData], 0
0x1800051d5  xor     r8d, r8d
0x1800051d8  mov     rdx, r12
0x1800051db  mov     dword ptr [rsp+760h+pdwType], 0FFFFh
0x1800051e3  mov     rax, [rcx+18h]
0x1800051e7  mov     rcx, r15
0x1800051ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ef  mov     ebx, eax
0x1800051f1  test    eax, eax
0x1800051f3  js      loc_1800053A9
0x1800051f9  mov     ebx, 50h ; 'P'
0x1800051fe  lea     rcx, [rbp+660h+mii]; void *
0x180005202  mov     r8d, ebx; Size
0x180005205  xor     edx, edx; Val
0x180005207  call    memset_0
0x18000520c  lea     edx, [rdi-2]; item
0x18000520f  mov     [rbp+660h+mii.cbSize], ebx
0x180005212  lea     r9, [rbp+660h+mii]; lpmii
0x180005216  mov     [rbp+660h+mii.fMask], 2
0x18000521d  lea     r8d, [rbx-4Fh]; fByPosition
0x180005221  mov     rcx, r12; hmenu
0x180005224  call    cs:__imp_GetMenuItemInfoW
0x18000522a  test    eax, eax
0x18000522c  jz      loc_1800053A4
0x180005232  cmp     dword ptr [rsi+58h], 3
0x180005236  jnz     short loc_18000524E
0x180005238  mov     rcx, r14; this
0x18000523b  call    ?CreateTempFile@CPackage@@IEAAJ_N@Z; CPackage::CreateTempFile(bool)
0x180005240  xor     r14d, r14d
0x180005243  mov     ebx, eax
0x180005245  test    eax, eax
0x180005247  jns     short loc_180005251
0x180005249  jmp     loc_1800053A9
0x18000524e  xor     r14d, r14d
0x180005251  cmp     edi, [rsi+0E0h]
0x180005257  jz      loc_180005359
0x18000525d  lea     rax, [rsp+760h+var_718]
0x180005262  mov     [rsp+760h+var_720], r14d
0x180005267  mov     [rsp+760h+pcbData], rax; pcbData
0x18000526c  lea     r8, Value; "SkipPromptOnDoVerb"
0x180005273  lea     rax, [rsp+760h+var_720]
0x180005278  mov     [rsp+760h+var_718], 4
0x180005280  mov     [rsp+760h+pvData], rax; pvData
0x180005285  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000528c  mov     r9d, 10h; dwFlags
0x180005292  mov     [rsp+760h+pdwType], r14; pdwType
0x180005297  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000529e  call    cs:__imp_RegGetValueW
0x1800052a4  test    eax, eax
0x1800052a6  jle     short loc_1800052B2
0x1800052a8  movzx   eax, ax
0x1800052ab  or      eax, 80070000h
0x1800052b0  test    eax, eax
0x1800052b2  js      short loc_1800052BF
0x1800052b4  cmp     [rsp+760h+var_720], 1
0x1800052b9  jz      loc_180005359
0x1800052bf  mov     r8d, 0BC5h
0x1800052c5  mov     [rsp+760h+lpText], r14
0x1800052ca  lea     rcx, [rsp+760h+lpText]
0x1800052cf  mov     [rsp+760h+var_708], r14
0x1800052d4  mov     [rsp+760h+var_700], r14
0x1800052d9  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x1800052de  mov     rsi, [rsp+760h+lpText]
0x1800052e3  mov     ebx, eax
0x1800052e5  test    eax, eax
0x1800052e7  js      short loc_180005347
0x1800052e9  mov     r8d, 0BC4h
0x1800052ef  mov     [rsp+760h+lpText], r14
0x1800052f4  lea     rcx, [rsp+760h+lpText]
0x1800052f9  mov     [rsp+760h+var_708], r14
0x1800052fe  mov     [rsp+760h+var_700], r14
0x180005303  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x180005308  mov     rdi, [rsp+760h+lpText]
0x18000530d  mov     ebx, eax
0x18000530f  test    eax, eax
0x180005311  js      short loc_180005339
0x180005313  mov     r9d, 10131h; uType
0x180005319  mov     r8, rsi; lpCaption
0x18000531c  mov     rdx, rdi; lpText
0x18000531f  mov     rcx, r13; hWnd
0x180005322  call    cs:__imp_MessageBoxW
0x180005328  mov     edx, 1
0x18000532d  sub     edx, eax
0x18000532f  neg     edx
0x180005331  sbb     ebx, ebx
0x180005333  and     ebx, 800704C7h
0x180005339  test    rdi, rdi
0x18000533c  jz      short loc_180005347
0x18000533e  mov     rcx, rdi; pv
0x180005341  call    cs:__imp_CoTaskMemFree
0x180005347  test    rsi, rsi
0x18000534a  jz      short loc_180005355
0x18000534c  mov     rcx, rsi; pv
0x18000534f  call    cs:__imp_CoTaskMemFree
0x180005355  test    ebx, ebx
0x180005357  js      short loc_1800053A9
0x180005359  mov     eax, [rbp+660h+mii.wID]
0x18000535c  lea     rdx, [rsp+760h+var_6F8]
0x180005361  add     eax, 0FFFFFFFEh
0x180005364  mov     [rbp+660h+var_6CC], r14
0x180005368  movsxd  rcx, eax
0x18000536b  xorps   xmm0, xmm0
0x18000536e  mov     [rsp+760h+var_6E8], rcx
0x180005373  mov     rcx, r15
0x180005376  mov     [rbp+660h+var_6C4], r14d
0x18000537a  mov     [rsp+760h+var_6F8], 38h ; '8'
0x180005383  mov     [rsp+760h+var_6F0], r14
0x180005388  movdqu  [rbp+660h+var_6E0], xmm0
0x18000538d  mov     [rbp+660h+var_6D0], 1
0x180005394  mov     rax, [r15]
0x180005397  mov     rax, [rax+20h]
0x18000539b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053a0  mov     ebx, eax
0x1800053a2  jmp     short loc_1800053A9
0x1800053a4  mov     ebx, 40181h
0x1800053a9  mov     rcx, r12; hMenu
0x1800053ac  call    cs:__imp_DestroyMenu
0x1800053b2  jmp     short loc_1800053B9
0x1800053b4  mov     ebx, 8007000Eh
0x1800053b9  mov     rax, [r15]
0x1800053bc  mov     rcx, r15
0x1800053bf  mov     rax, [rax+10h]
0x1800053c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053c8  mov     eax, ebx
0x1800053ca  jmp     short loc_18000540E
0x1800053cc  xor     edx, edx; Val
0x1800053ce  lea     rcx, [rbp+660h+var_670]; void *
0x1800053d2  mov     r8d, 620h; Size
0x1800053d8  call    memset_0
0x1800053dd  lea     rdx, [rbp+660h+var_670]; struct _packageInfo *
0x1800053e1  mov     rcx, r13; HWND
0x1800053e4  call    ?PackWiz_CreateWizard@@YAHPEAUHWND__@@PEAU_packageInfo@@@Z; PackWiz_CreateWizard(HWND__ *,_packageInfo *)
0x1800053e9  lea     rcx, [rbp+660h+String]; lpString
0x1800053f0  call    cs:__imp_lstrlenW
0x1800053f6  test    eax, eax
0x1800053f8  jnz     short loc_180005401
0x1800053fa  mov     eax, 40181h
0x1800053ff  jmp     short loc_18000540E
0x180005401  lea     rcx, [rsi-10h]; this
0x180005405  lea     rdx, [rbp+660h+var_670]; struct _packageInfo *
0x180005409  call    ?InitFromPackInfo@CPackage@@IEAAJPEAU_packageInfo@@@Z; CPackage::InitFromPackInfo(_packageInfo *)
0x18000540e  mov     rcx, [rbp+660h+var_50]
0x180005415  xor     rcx, rsp; StackCookie
0x180005418  call    __security_check_cookie
0x18000541d  add     rsp, 728h
0x180005424  pop     r15
0x180005426  pop     r14
0x180005428  pop     r13
0x18000542a  pop     r12
0x18000542c  pop     rdi
0x18000542d  pop     rsi
0x18000542e  pop     rbx
0x18000542f  pop     rbp
0x180005430  retn
```
