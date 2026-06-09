# CToc::OnBinaryTOCTVMsg(tagNMTREEVIEWA *)

- ea: `0x18001acc0`
- end: `0x18001b406`
- name: `?OnBinaryTOCTVMsg@CToc@@QEAA_JPEAUtagNMTREEVIEWA@@@Z`
- size: `1862`
- prototype: `__int64 __fastcall(CToc *__hidden this, struct tagNMTREEVIEWA *)`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b4e0`
- `0x180033700`

## callees

- `0x180001728`
- `0x1800095c8`
- `0x18000960c`
- `0x180011104`
- `0x180012cd0`
- `0x180012f60`
- `0x180013174`
- `0x18001341c`
- `0x1800196fc`
- `0x18001acc0`
- `0x18001b428`
- `0x18001d2bc`
- `0x18002fef8`
- `0x180033118`
- `0x180037448`
- `0x1800675c0`
- `0x180067798`
- `0x18006a480`
- `0x180075c42`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!ScreenToClient` at `0x18001af01`
- `USER32!ScreenToClient` at `0x18001b155`
- `USER32!ScreenToClient` at `0x18001af01`
- `USER32!ScreenToClient` at `0x18001b155`
- `USER32!AppendMenuW` at `0x18001b1fc`
- `USER32!AppendMenuW` at `0x18001b21a`
- `USER32!AppendMenuW` at `0x18001b248`
- `USER32!AppendMenuW` at `0x18001b360`
- `USER32!AppendMenuW` at `0x18001b37e`
- `USER32!AppendMenuW` at `0x18001b1fc`
- `USER32!AppendMenuW` at `0x18001b21a`
- `USER32!AppendMenuW` at `0x18001b248`
- `USER32!AppendMenuW` at `0x18001b360`
- `USER32!AppendMenuW` at `0x18001b37e`
- `USER32!TrackPopupMenu` at `0x18001b3b0`
- `USER32!TrackPopupMenu` at `0x18001b3b0`
- `USER32!GetKeyState` at `0x18001ae0a`
- `USER32!GetKeyState` at `0x18001ae0a`
- `USER32!CreatePopupMenu` at `0x18001b1a9`
- `USER32!CreatePopupMenu` at `0x18001b1a9`
- `USER32!SendMessageA` at `0x18001ae66`
- `USER32!SendMessageA` at `0x18001af1a`
- `USER32!SendMessageA` at `0x18001b008`
- `USER32!SendMessageA` at `0x18001b133`
- `USER32!SendMessageA` at `0x18001b16f`
- `USER32!SendMessageA` at `0x18001b191`
- `USER32!SendMessageA` at `0x18001ae66`
- `USER32!SendMessageA` at `0x18001af1a`
- `USER32!SendMessageA` at `0x18001b008`
- `USER32!SendMessageA` at `0x18001b133`
- `USER32!SendMessageA` at `0x18001b16f`
- `USER32!SendMessageA` at `0x18001b191`
- `USER32!GetParent` at `0x18001afbd`
- `USER32!GetParent` at `0x18001afbd`
- `USER32!DestroyMenu` at `0x18001b3b9`
- `USER32!DestroyMenu` at `0x18001b3b9`
- `USER32!ClientToScreen` at `0x18001b1a3`
- `USER32!ClientToScreen` at `0x18001b1a3`
- `USER32!GetCursorPos` at `0x18001aef0`
- `USER32!GetCursorPos` at `0x18001b143`
- `USER32!GetCursorPos` at `0x18001aef0`
- `USER32!GetCursorPos` at `0x18001b143`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CToc::OnBinaryTOCTVMsg(CToc *this, struct tagNMTVCUSTOMDRAW *a2)
{
  UINT code; // eax
  LPARAM lItemlParam; // rbx
  __int64 v6; // rax
  __int64 dwItemSpec_low; // r8
  __int64 v8; // rdx
  const unsigned __int16 *StringResourceW; // rax
  const char *StringResource; // rax
  HTREEITEM hItem; // r9
  UINT v12; // edx
  WPARAM v13; // r8
  struct CTreeNode *v14; // rsi
  CHtmlHelpControl *v15; // rcx
  HWND Parent; // rax
  __int64 v17; // rcx
  struct CTreeNode *v18; // r14
  __int64 v19; // rcx
  int *v20; // r9
  HWND v21; // rdx
  HHUrlSecurityManager::InternalSecurityManager *v22; // rcx
  HMENU PopupMenu; // rsi
  const WCHAR *v24; // rax
  const WCHAR *v25; // rax
  const WCHAR *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  CInfoType *v29; // rax
  CInfoType *v30; // rax
  const unsigned int *v31; // rdx
  CInfoType *v32; // rax
  CInfoType *v33; // rax
  const WCHAR *v34; // rax
  HWND hWnd; // rax
  LPARAM v37[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPARAM v38; // [rsp+50h] [rbp-B0h]
  struct tagTVITEMW lParam; // [rsp+58h] [rbp-A8h] BYREF
  struct tagPOINT Point[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _TREEITEM *v41; // [rsp+A0h] [rbp-60h]
  CInfoType *v42; // [rsp+A8h] [rbp-58h]
  char v43[2096]; // [rsp+B0h] [rbp-50h] BYREF

  memset(&lParam, 0, sizeof(lParam));
  *(_OWORD *)v37 = 0;
  v38 = 0;
  code = a2->nmcd.hdr.code;
  if ( code > 0xFFFFFE6E )
  {
    switch ( code )
    {
      case 0xFFFFFE6F:
        goto LABEL_81;
      case 0xFFFFFFF4:
        return CToc::OnCustomDraw(this, a2);
      case 0xFFFFFFFB:
        GetCursorPos((LPPOINT)v37);
        ScreenToClient(*((HWND *)this + 53), (LPPOINT)v37);
        SendMessageA(*((HWND *)this + 53), 0x1111u, 0, (LPARAM)v37);
        if ( v38 )
          SendMessageA(*((HWND *)this + 53), 0x110Bu, 9u, v38);
        goto LABEL_56;
    }
    if ( code != -4 && code != -3 )
    {
      if ( code != -2 )
        return 0;
      if ( *((_DWORD *)this + 102) )
        return 0;
      *(_OWORD *)&Point[0].x = 0;
      v41 = 0;
      GetCursorPos(Point);
      ScreenToClient(*((HWND *)this + 53), Point);
      SendMessageA(*((HWND *)this + 53), 0x1111u, 0, (LPARAM)Point);
      if ( (Point[1].x & 0x10) != 0 )
        return 0;
      lParam.hItem = v41;
      if ( !v41 )
        return 0;
      lParam.mask = 4;
      W_TreeView_GetItem_fn(*((HWND *)this + 53), &lParam);
      v14 = (struct CTreeNode *)lParam.lParam;
      if ( !lParam.lParam
        || !(*(unsigned int (__fastcall **)(LPARAM, char *, __int64, __int64))(*(_QWORD *)lParam.lParam + 72LL))(
              lParam.lParam,
              v43,
              2084,
              1) )
      {
        return 0;
      }
      *((_DWORD *)this + 133) = 1;
      v15 = (CHtmlHelpControl *)*((_QWORD *)this + 62);
      if ( !v15 )
      {
        CToc::UpdateTOCSlot(this, v14);
        Parent = GetParent(*((HWND *)this + 53));
        ChangeHtmlTopic(v43, Parent, 0);
        v17 = *((_QWORD *)this + 67);
        if ( v17 )
          *(_QWORD *)(v17 + 328) = *((_QWORD *)this + 53);
        return 0;
      }
      goto LABEL_36;
    }
    lParam.hItem = (HTREEITEM)SendMessageA(*((HWND *)this + 53), 0x110Au, 9u, 0);
    if ( !lParam.hItem )
      return 0;
    lParam.mask = 102;
    W_TreeView_GetItem_fn(*((HWND *)this + 53), &lParam);
    v18 = (struct CTreeNode *)lParam.lParam;
    if ( lParam.lParam
      && (*(unsigned int (__fastcall **)(LPARAM, char *, __int64, __int64))(*(_QWORD *)lParam.lParam + 72LL))(
           lParam.lParam,
           v43,
           2084,
           1) )
    {
      *((_DWORD *)this + 133) = 1;
      v15 = (CHtmlHelpControl *)*((_QWORD *)this + 62);
      if ( v15 )
      {
LABEL_36:
        CHtmlHelpControl::SendEvent(v15, v43);
        return 0;
      }
      CToc::UpdateTOCSlot(this, v18);
      ChangeHtmlTopic(v43, *((HWND *)this + 53), 0);
      v19 = *((_QWORD *)this + 67);
      if ( v19 )
        *(_QWORD *)(v19 + 328) = *((_QWORD *)this + 53);
    }
    if ( a2->nmcd.hdr.code != -4 || !(*(unsigned int (__fastcall **)(struct CTreeNode *))(*(_QWORD *)v18 + 56LL))(v18) )
      return 0;
    v20 = (int *)((char *)this + 532);
    v21 = (HWND)*((_QWORD *)this + 53);
    if ( (lParam.state & 0x20) != 0 )
    {
      if ( !HandleExpanding(&lParam, v21, 1u, v20) )
        return 0;
      v13 = 1;
    }
    else
    {
      if ( !HandleExpanding(&lParam, v21, 2u, v20) )
        return 0;
      v13 = 2;
    }
    v12 = 4354;
    hItem = lParam.hItem;
LABEL_53:
    SendMessageA(*((HWND *)this + 53), v12, v13, (LPARAM)hItem);
    return 0;
  }
  switch ( code )
  {
    case 0xFFFFFE6E:
LABEL_81:
      *((_QWORD *)this + 50) = a2[1].nmcd.hdr.hwndFrom;
      return 0;
    case 0xFFFFFE39:
LABEL_23:
      hItem = 0;
      v12 = 11;
      v13 = 1;
      goto LABEL_53;
    case 0xFFFFFE3A:
      goto LABEL_22;
    case 0xFFFFFE3C:
      goto LABEL_10;
  }
  if ( code != -412 )
  {
    if ( code != -406 )
    {
      if ( code != -405 )
      {
        if ( code == -403 )
        {
LABEL_10:
          lItemlParam = a2->nmcd.lItemlParam;
          if ( lItemlParam )
          {
            if ( (a2->nmcd.dwDrawStage & 0x40) != 0 )
            {
              lParam.cChildren = (*(__int64 (__fastcall **)(LPARAM))(*(_QWORD *)lItemlParam + 56LL))(a2->nmcd.lItemlParam) != 0;
              lParam.mask |= 0x40u;
            }
            if ( (a2->nmcd.dwDrawStage & 1) != 0 )
            {
              v6 = *(_QWORD *)lItemlParam;
              dwItemSpec_low = LODWORD(a2->nmcd.dwItemSpec);
              v8 = *(_QWORD *)&a2->nmcd.rc.right;
              if ( a2->nmcd.hdr.code == -452 )
              {
                if ( (*(int (__fastcall **)(LPARAM, __int64, __int64))(v6 + 16))(lItemlParam, v8, dwItemSpec_low) < 0 )
                {
                  StringResourceW = GetStringResourceW(0x412u);
                  StringCchCopyW(
                    *(unsigned __int16 **)&a2->nmcd.rc.right,
                    SLODWORD(a2->nmcd.dwItemSpec),
                    StringResourceW);
                }
              }
              else if ( (*(int (__fastcall **)(LPARAM, __int64, __int64))(v6 + 24))(lItemlParam, v8, dwItemSpec_low) < 0 )
              {
                StringResource = GetStringResource(0x412u);
                StringCchCopyA(*(char **)&a2->nmcd.rc.right, SLODWORD(a2->nmcd.dwItemSpec), StringResource);
              }
            }
          }
        }
        return 0;
      }
LABEL_22:
      SendMessageA(*((HWND *)this + 53), 0xBu, 0, 0);
      HandleExpanding((struct tagTVITEMW *)&a2->iLevel, *((HWND *)this + 53), a2->nmcd.dwDrawStage, (int *)this + 133);
      return 0;
    }
    goto LABEL_23;
  }
  if ( LOWORD(a2->nmcd.dwDrawStage) != 121 || GetKeyState(16) >= 0 )
    return 0;
  v37[0] = 0;
LABEL_56:
  ClientToScreen(*((HWND *)this + 53), (LPPOINT)v37);
  PopupMenu = CreatePopupMenu();
  if ( !PopupMenu )
    return 0;
  if ( (*((_DWORD *)this + 130) & 0x400) == 0 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 67) + 608LL) + 128LL) + 1096LL) )
    {
      v24 = GetStringResourceW(0x405u);
      AppendMenuW(PopupMenu, 0, 0xFAu, v24);
    }
    v25 = GetStringResourceW(0x406u);
    AppendMenuW(PopupMenu, 0, 0xFBu, v25);
  }
  if ( *(_QWORD *)(*((_QWORD *)this + 67) + 600LL) )
  {
    v26 = GetStringResourceW(0x407u);
    AppendMenuW(PopupMenu, 0, 0xFDu, v26);
  }
  if ( !*((_QWORD *)this + 70) )
  {
    v27 = *((_QWORD *)this + 67);
    if ( v27 && (v28 = *(_QWORD *)(v27 + 608)) != 0 && *(_QWORD *)(v28 + 24) )
    {
      v29 = (CInfoType *)operator new(0x70u);
      v42 = v29;
      if ( v29 )
        v30 = CInfoType::CInfoType(v29);
      else
        v30 = 0;
      *((_QWORD *)this + 70) = v30;
      CInfoType::CopyTo(v30, *(struct CHmData *const *)(*((_QWORD *)this + 67) + 608LL));
      v22 = *(HHUrlSecurityManager::InternalSecurityManager **)(*((_QWORD *)this + 67) + 608LL);
      v31 = (const unsigned int *)*((_QWORD *)v22 + 4);
      if ( v31 && CInfoType::AnyInfoTypes(*((CInfoType **)this + 70), v31) )
        memcpy_0(
          *(void **)(*((_QWORD *)this + 70) + 80LL),
          *(const void **)(*(_QWORD *)(*((_QWORD *)this + 67) + 608LL) + 32LL),
          4 * *(_DWORD *)(*((_QWORD *)this + 70) + 44LL));
    }
    else
    {
      v32 = (CInfoType *)operator new(0x70u);
      v42 = v32;
      if ( v32 )
        v33 = CInfoType::CInfoType(v32);
      else
        v33 = 0;
      *((_QWORD *)this + 70) = v33;
      CInfoType::operator=(v33);
    }
  }
  if ( !NoRun(v22) )
  {
    AppendMenuW(PopupMenu, 0x800u, 0, 0);
    v34 = GetStringResourceW(0x455u);
    AppendMenuW(PopupMenu, 0, 0xEFFFu, v34);
  }
  hWnd = FindMessageParent(*((HWND *)this + 53));
  TrackPopupMenu(PopupMenu, 2u, v37[0], SHIDWORD(v37[0]), 0, hWnd, 0);
  DestroyMenu(PopupMenu);
  return 1;
}

```

## disassembly

```asm
0x18001acc0  mov     [rsp-8+arg_10], rbx
0x18001acc5  mov     [rsp-8+arg_18], rsi
0x18001acca  push    rbp
0x18001accb  push    rdi
0x18001accc  push    r14
0x18001acce  lea     rbp, [rsp-7F0h]
0x18001acd6  sub     rsp, 8F0h
0x18001acdd  mov     rax, cs:__security_cookie
0x18001ace4  xor     rax, rsp
0x18001ace7  mov     [rbp+800h+var_20], rax
0x18001acee  mov     rsi, rdx
0x18001acf1  mov     rbx, rcx
0x18001acf4  xorps   xmm0, xmm0
0x18001acf7  xor     eax, eax
0x18001acf9  movups  xmmword ptr [rsp+900h+lParam], xmm0
0x18001acfe  movups  [rsp+900h+var_898], xmm0
0x18001ad03  movups  [rsp+900h+var_888], xmm0
0x18001ad08  mov     [rbp+800h+var_878], rax
0x18001ad0c  movups  xmmword ptr [rsp+900h+var_8C0], xmm0
0x18001ad11  mov     [rsp+900h+var_8B0], rax
0x18001ad16  mov     eax, [rdx+10h]
0x18001ad19  mov     ecx, 0FFFFFE6Eh
0x18001ad1e  cmp     eax, ecx
0x18001ad20  ja      loc_18001AE9C
0x18001ad26  jz      loc_18001B3D2
0x18001ad2c  cmp     eax, 0FFFFFE39h
0x18001ad31  jz      loc_18001AE8C
0x18001ad37  cmp     eax, 0FFFFFE3Ah
0x18001ad3c  jz      loc_18001AE55
0x18001ad42  mov     r14d, 0FFFFFE3Ch
0x18001ad48  cmp     eax, r14d
0x18001ad4b  jz      short loc_18001AD79
0x18001ad4d  cmp     eax, 0FFFFFE64h
0x18001ad52  jz      loc_18001ADFA
0x18001ad58  cmp     eax, 0FFFFFE6Ah
0x18001ad5d  jz      loc_18001AE8C
0x18001ad63  cmp     eax, 0FFFFFE6Bh
0x18001ad68  jz      loc_18001AE55
0x18001ad6e  cmp     eax, 0FFFFFE6Dh
0x18001ad73  jnz     loc_18001B3DD
0x18001ad79  mov     rbx, [rdx+48h]
0x18001ad7d  xor     edi, edi
0x18001ad7f  test    rbx, rbx
0x18001ad82  jz      loc_18001B3DD
0x18001ad88  test    byte ptr [rdx+18h], 40h
0x18001ad8c  jz      short loc_18001ADAC
0x18001ad8e  mov     rax, [rbx]
0x18001ad91  mov     rcx, rbx
0x18001ad94  mov     rax, [rax+38h]
0x18001ad98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad9d  mov     ecx, edi
0x18001ad9f  test    eax, eax
0x18001ada1  setnz   cl
0x18001ada4  mov     dword ptr [rbp+800h+var_888+0Ch], ecx
0x18001ada7  or      dword ptr [rsp+900h+lParam], 40h
0x18001adac  test    byte ptr [rsi+18h], 1
0x18001adb0  jz      loc_18001B3DD
0x18001adb6  mov     rax, [rbx]
0x18001adb9  mov     r8d, [rsi+38h]
0x18001adbd  mov     rdx, [rsi+30h]
0x18001adc1  mov     rcx, rbx
0x18001adc4  cmp     [rsi+10h], r14d
0x18001adc8  jnz     short loc_18001AE25
0x18001adca  mov     rax, [rax+10h]
0x18001adce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001add3  test    eax, eax
0x18001add5  jns     loc_18001B3DD
0x18001addb  mov     ecx, 412h; uID
0x18001ade0  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18001ade5  movsxd  rdx, dword ptr [rsi+38h]; unsigned __int64
0x18001ade9  mov     r8, rax; unsigned __int16 *
0x18001adec  mov     rcx, [rsi+30h]; unsigned __int16 *
0x18001adf0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001adf5  jmp     loc_18001B3DD
0x18001adfa  cmp     word ptr [rdx+18h], 79h ; 'y'
0x18001adff  jnz     loc_18001B3DD
0x18001ae05  mov     ecx, 10h; nVirtKey
0x18001ae0a  call    cs:__imp_GetKeyState
0x18001ae10  xor     edi, edi
0x18001ae12  test    ax, ax
0x18001ae15  jns     loc_18001B3DD
0x18001ae1b  mov     [rsp+900h+var_8C0], rdi
0x18001ae20  jmp     loc_18001B197
0x18001ae25  mov     rax, [rax+18h]
0x18001ae29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae2e  test    eax, eax
0x18001ae30  jns     loc_18001B3DD
0x18001ae36  mov     ecx, 412h; uID
0x18001ae3b  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x18001ae40  movsxd  rdx, dword ptr [rsi+38h]; unsigned __int64
0x18001ae44  mov     r8, rax; char *
0x18001ae47  mov     rcx, [rsi+30h]; char *
0x18001ae4b  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001ae50  jmp     loc_18001B3DD
0x18001ae55  xor     r9d, r9d; lParam
0x18001ae58  xor     r8d, r8d; wParam
0x18001ae5b  lea     edx, [r9+0Bh]; Msg
0x18001ae5f  mov     rcx, [rbx+1A8h]; hWnd
0x18001ae66  call    cs:__imp_SendMessageA
0x18001ae6c  lea     r9, [rbx+214h]; int *
0x18001ae73  lea     rcx, [rsi+58h]; struct tagTVITEMW *
0x18001ae77  mov     r8d, [rsi+18h]; unsigned int
0x18001ae7b  mov     rdx, [rbx+1A8h]; HWND
0x18001ae82  call    ?HandleExpanding@@YAHPEAUtagTVITEMW@@PEAUHWND__@@IPEAH@Z; HandleExpanding(tagTVITEMW *,HWND__ *,uint,int *)
0x18001ae87  jmp     loc_18001B3DD
0x18001ae8c  xor     r9d, r9d
0x18001ae8f  lea     edx, [r9+0Bh]
0x18001ae93  lea     r8d, [r9+1]
0x18001ae97  jmp     loc_18001B12C
0x18001ae9c  cmp     eax, 0FFFFFE6Fh
0x18001aea1  jz      loc_18001B3D2
0x18001aea7  cmp     eax, 0FFFFFFF4h
0x18001aeaa  jz      loc_18001B3C6
0x18001aeb0  cmp     eax, 0FFFFFFFBh
0x18001aeb3  jz      loc_18001B13E
0x18001aeb9  cmp     eax, 0FFFFFFFCh
0x18001aebc  jz      loc_18001AFF5
0x18001aec2  cmp     eax, 0FFFFFFFDh
0x18001aec5  jz      loc_18001AFF5
0x18001aecb  cmp     eax, 0FFFFFFFEh
0x18001aece  jnz     loc_18001B3DD
0x18001aed4  xor     edi, edi
0x18001aed6  cmp     [rbx+198h], edi
0x18001aedc  jnz     loc_18001B3DD
0x18001aee2  xor     eax, eax
0x18001aee4  movups  xmmword ptr [rbp+800h+Point.x], xmm0
0x18001aee8  mov     [rbp+800h+var_860], rax
0x18001aeec  lea     rcx, [rbp+800h+Point]; lpPoint
0x18001aef0  call    cs:__imp_GetCursorPos
0x18001aef6  lea     rdx, [rbp+800h+Point]; lpPoint
0x18001aefa  mov     rcx, [rbx+1A8h]; hWnd
0x18001af01  call    cs:__imp_ScreenToClient
0x18001af07  lea     r9, [rbp+800h+Point]; lParam
0x18001af0b  xor     r8d, r8d; wParam
0x18001af0e  mov     edx, 1111h; Msg
0x18001af13  mov     rcx, [rbx+1A8h]; hWnd
0x18001af1a  call    cs:__imp_SendMessageA
0x18001af20  test    byte ptr [rbp+800h+Point.x+8], 10h
0x18001af24  jnz     loc_18001B3DD
0x18001af2a  mov     rax, [rbp+800h+var_860]
0x18001af2e  mov     [rsp+900h+lParam+8], rax
0x18001af33  test    rax, rax
0x18001af36  jz      loc_18001B3DD
0x18001af3c  mov     dword ptr [rsp+900h+lParam], 4
0x18001af44  lea     rdx, [rsp+900h+lParam]; struct tagTVITEMW *
0x18001af49  mov     rcx, [rbx+1A8h]; HWND
0x18001af50  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001af55  mov     rsi, [rbp+800h+var_878]
0x18001af59  test    rsi, rsi
0x18001af5c  jz      loc_18001B3DD
0x18001af62  mov     rax, [rsi]
0x18001af65  lea     r9d, [rdi+1]
0x18001af69  mov     r8d, 824h
0x18001af6f  lea     rdx, [rbp+800h+var_850]
0x18001af73  mov     rcx, rsi
0x18001af76  mov     rax, [rax+48h]
0x18001af7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af7f  test    eax, eax
0x18001af81  jz      loc_18001B3DD
0x18001af87  mov     dword ptr [rbx+214h], 1
0x18001af91  mov     rcx, [rbx+1F0h]; this
0x18001af98  test    rcx, rcx
0x18001af9b  jz      short loc_18001AFAB
0x18001af9d  lea     rdx, [rbp+800h+var_850]; char *
0x18001afa1  call    ?SendEvent@CHtmlHelpControl@@QEAAJPEBD@Z; CHtmlHelpControl::SendEvent(char const *)
0x18001afa6  jmp     loc_18001B3DD
0x18001afab  mov     rdx, rsi; struct CTreeNode *
0x18001afae  mov     rcx, rbx; this
0x18001afb1  call    ?UpdateTOCSlot@CToc@@AEAAXPEAVCTreeNode@@@Z; CToc::UpdateTOCSlot(CTreeNode *)
0x18001afb6  mov     rcx, [rbx+1A8h]; hWnd
0x18001afbd  call    cs:__imp_GetParent
0x18001afc3  mov     rdx, rax; hWnd
0x18001afc6  xor     r8d, r8d; int
0x18001afc9  lea     rcx, [rbp+800h+var_850]; char *
0x18001afcd  call    ?ChangeHtmlTopic@@YAPEAUHWND__@@PEBDPEAU1@H@Z; ChangeHtmlTopic(char const *,HWND__ *,int)
0x18001afd2  mov     rcx, [rbx+218h]
0x18001afd9  test    rcx, rcx
0x18001afdc  jz      loc_18001B3DD
0x18001afe2  mov     rax, [rbx+1A8h]
0x18001afe9  mov     [rcx+148h], rax
0x18001aff0  jmp     loc_18001B3DD
0x18001aff5  xor     r9d, r9d; lParam
0x18001aff8  mov     edx, 110Ah; Msg
0x18001affd  lea     r8d, [r9+9]; wParam
0x18001b001  mov     rcx, [rbx+1A8h]; hWnd
0x18001b008  call    cs:__imp_SendMessageA
0x18001b00e  mov     [rsp+900h+lParam+8], rax
0x18001b013  test    rax, rax
0x18001b016  jz      loc_18001B3DD
0x18001b01c  mov     dword ptr [rsp+900h+lParam], 66h ; 'f'
0x18001b024  lea     rdx, [rsp+900h+lParam]; struct tagTVITEMW *
0x18001b029  mov     rcx, [rbx+1A8h]; HWND
0x18001b030  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001b035  mov     r14, [rbp+800h+var_878]
0x18001b039  test    r14, r14
0x18001b03c  jz      short loc_18001B0B3
0x18001b03e  mov     rax, [r14]
0x18001b041  mov     r9d, 1
0x18001b047  mov     r8d, 824h
0x18001b04d  lea     rdx, [rbp+800h+var_850]
0x18001b051  mov     rcx, r14
0x18001b054  mov     rax, [rax+48h]
0x18001b058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b05d  test    eax, eax
0x18001b05f  jz      short loc_18001B0B3
0x18001b061  mov     dword ptr [rbx+214h], 1
0x18001b06b  mov     rcx, [rbx+1F0h]
0x18001b072  test    rcx, rcx
0x18001b075  jnz     loc_18001AF9D
0x18001b07b  mov     rdx, r14; struct CTreeNode *
0x18001b07e  mov     rcx, rbx; this
0x18001b081  call    ?UpdateTOCSlot@CToc@@AEAAXPEAVCTreeNode@@@Z; CToc::UpdateTOCSlot(CTreeNode *)
0x18001b086  xor     r8d, r8d; int
0x18001b089  mov     rdx, [rbx+1A8h]; hWnd
0x18001b090  lea     rcx, [rbp+800h+var_850]; char *
0x18001b094  call    ?ChangeHtmlTopic@@YAPEAUHWND__@@PEBDPEAU1@H@Z; ChangeHtmlTopic(char const *,HWND__ *,int)
0x18001b099  mov     rcx, [rbx+218h]
0x18001b0a0  test    rcx, rcx
0x18001b0a3  jz      short loc_18001B0B3
0x18001b0a5  mov     rax, [rbx+1A8h]
0x18001b0ac  mov     [rcx+148h], rax
0x18001b0b3  cmp     dword ptr [rsi+10h], 0FFFFFFFCh
0x18001b0b7  jnz     loc_18001B3DD
0x18001b0bd  mov     rax, [r14]
0x18001b0c0  mov     rcx, r14
0x18001b0c3  mov     rax, [rax+38h]
0x18001b0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0cc  test    eax, eax
0x18001b0ce  jz      loc_18001B3DD
0x18001b0d4  lea     r9, [rbx+214h]; int *
0x18001b0db  mov     rdx, [rbx+1A8h]; HWND
0x18001b0e2  lea     rcx, [rsp+900h+lParam]; struct tagTVITEMW *
0x18001b0e7  test    byte ptr [rsp+900h+var_898], 20h
0x18001b0ec  jz      short loc_18001B109
0x18001b0ee  mov     r8d, 1; unsigned int
0x18001b0f4  call    ?HandleExpanding@@YAHPEAUtagTVITEMW@@PEAUHWND__@@IPEAH@Z; HandleExpanding(tagTVITEMW *,HWND__ *,uint,int *)
0x18001b0f9  test    eax, eax
0x18001b0fb  jz      loc_18001B3DD
0x18001b101  mov     r8d, 1
0x18001b107  jmp     short loc_18001B122
0x18001b109  mov     r8d, 2; unsigned int
0x18001b10f  call    ?HandleExpanding@@YAHPEAUtagTVITEMW@@PEAUHWND__@@IPEAH@Z; HandleExpanding(tagTVITEMW *,HWND__ *,uint,int *)
0x18001b114  test    eax, eax
0x18001b116  jz      loc_18001B3DD
0x18001b11c  mov     r8d, 2; wParam
0x18001b122  mov     edx, 1102h; Msg
0x18001b127  mov     r9, [rsp+900h+lParam+8]; lParam
0x18001b12c  mov     rcx, [rbx+1A8h]; hWnd
0x18001b133  call    cs:__imp_SendMessageA
0x18001b139  jmp     loc_18001B3DD
0x18001b13e  lea     rcx, [rsp+900h+var_8C0]; lpPoint
0x18001b143  call    cs:__imp_GetCursorPos
0x18001b149  lea     rdx, [rsp+900h+var_8C0]; lpPoint
0x18001b14e  mov     rcx, [rbx+1A8h]; hWnd
0x18001b155  call    cs:__imp_ScreenToClient
0x18001b15b  lea     r9, [rsp+900h+var_8C0]; lParam
0x18001b160  xor     r8d, r8d; wParam
0x18001b163  mov     edx, 1111h; Msg
0x18001b168  mov     rcx, [rbx+1A8h]; hWnd
0x18001b16f  call    cs:__imp_SendMessageA
0x18001b175  mov     r9, [rsp+900h+var_8B0]; lParam
0x18001b17a  xor     edi, edi
0x18001b17c  test    r9, r9
0x18001b17f  jz      short loc_18001B197
0x18001b181  mov     edx, 110Bh; Msg
0x18001b186  lea     r8d, [rdi+9]; wParam
0x18001b18a  mov     rcx, [rbx+1A8h]; hWnd
0x18001b191  call    cs:__imp_SendMessageA
0x18001b197  lea     rdx, [rsp+900h+var_8C0]; lpPoint
0x18001b19c  mov     rcx, [rbx+1A8h]; hWnd
0x18001b1a3  call    cs:__imp_ClientToScreen
0x18001b1a9  call    cs:__imp_CreatePopupMenu
0x18001b1af  mov     rsi, rax
0x18001b1b2  test    rax, rax
0x18001b1b5  jz      loc_18001B3DD
0x18001b1bb  test    dword ptr [rbx+208h], 400h
0x18001b1c5  jnz     short loc_18001B220
0x18001b1c7  mov     rcx, [rbx+218h]
0x18001b1ce  mov     rdx, [rcx+260h]
0x18001b1d5  mov     rcx, [rdx+80h]
0x18001b1dc  cmp     [rcx+448h], edi
0x18001b1e2  jz      short loc_18001B202
0x18001b1e4  mov     ecx, 405h; uID
0x18001b1e9  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18001b1ee  mov     r9, rax; lpNewItem
0x18001b1f1  xor     edx, edx; uFlags
0x18001b1f3  mov     r8d, 0FAh; uIDNewItem
0x18001b1f9  mov     rcx, rsi; hMenu
0x18001b1fc  call    cs:__imp_AppendMenuW
0x18001b202  mov     ecx, 406h; uID
0x18001b207  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18001b20c  mov     r9, rax; lpNewItem
0x18001b20f  xor     edx, edx; uFlags
0x18001b211  mov     r8d, 0FBh; uIDNewItem
0x18001b217  mov     rcx, rsi; hMenu
0x18001b21a  call    cs:__imp_AppendMenuW
0x18001b220  mov     rax, [rbx+218h]
0x18001b227  cmp     [rax+258h], rdi
0x18001b22e  jz      short loc_18001B24E
0x18001b230  mov     ecx, 407h; uID
  ... truncated ...
```
