# CRdpWindowTracker::GetWindowGeometry(RDP_TRACKED_WINDOW_NODE *)

- ea: `0x14005ca44`
- end: `0x14005cdea`
- name: `?GetWindowGeometry@CRdpWindowTracker@@AEAAJPEAURDP_TRACKED_WINDOW_NODE@@@Z`
- size: `934`
- prototype: `__int64 __fastcall(CRdpWindowTracker *__hidden this, struct RDP_TRACKED_WINDOW_NODE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14005f470`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x14005b750`
- `0x14005c2b4`
- `0x14005c788`
- `0x14005ca44`
- `0x14005e158`
- `0x14005ebd0`
- `0x14005fe84`
- `0x14006b010`

## import_xrefs

- `USER32!EnumChildWindows` at `0x14005cc3a`
- `USER32!EnumChildWindows` at `0x14005cc3a`
- `USER32!EnumWindows` at `0x14005cc4b`
- `USER32!EnumWindows` at `0x14005cc4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cc55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cc55`
- `GDI32!CreateRectRgn` at `0x14005caee`
- `GDI32!CreateRectRgn` at `0x14005caee`
- `GDI32!CombineRgn` at `0x14005cd16`
- `GDI32!CombineRgn` at `0x14005cd16`
- `GDI32!DeleteObject` at `0x14005cdca`
- `GDI32!DeleteObject` at `0x14005cdca`

## string_xrefs

- `0x14005cd57`: `CombineRgn() failed`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::GetWindowGeometry(HRGN *this, struct RDP_TRACKED_WINDOW_NODE *a2)
{
  HWND v2; // r15
  HWND TopLevelParent; // r14
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int WindowRegionOrBounds; // ebx
  HRGN v8; // r12
  HRGN RectRgn; // r13
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  HRGN v13; // rcx
  int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // r8
  CRdpWindowTracker *v17; // rcx
  signed int LastError; // eax
  CRdpWindowTracker *v19; // rcx
  unsigned int v20; // eax
  struct tagRECT *v22; // [rsp+28h] [rbp-38h]
  LPARAM lParam[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v24; // [rsp+50h] [rbp-10h]
  int v26; // [rsp+A8h] [rbp+48h] BYREF

  v2 = (HWND)*((_QWORD *)a2 + 2);
  v26 = 1;
  *(_OWORD *)lParam = 0;
  v24 = 0;
  TopLevelParent = CRdpWindowTracker::GetTopLevelParent((CRdpWindowTracker *)this, v2);
  if ( !TopLevelParent )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147418113);
    }
    return (unsigned int)-2147418113;
  }
  v8 = (HRGN)*((_QWORD *)a2 + 12);
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  WindowRegionOrBounds = CRdpWindowTracker::STATIC_GetWindowRegionOrBounds(v2, v8);
  if ( WindowRegionOrBounds < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 42;
      v12 = "CRdpWindowTracker::STATIC_GetWindowRegionOrBounds() failed";
LABEL_12:
      LODWORD(v22) = WindowRegionOrBounds;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v10,
        (__int64)v12,
        v22);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v13 = this[10];
  lParam[0] = (LPARAM)v2;
  lParam[1] = (LPARAM)TopLevelParent;
  *(_QWORD *)&v24 = v8;
  *((_QWORD *)&v24 + 1) = RectRgn;
  if ( !v13 )
  {
LABEL_24:
    EnumChildWindows(TopLevelParent, CRdpWindowTracker::STATIC_EnumChildWindowsProc, (LPARAM)lParam);
    if ( EnumWindows(CRdpWindowTracker::STATIC_EnumWindowsProc, (LPARAM)lParam) )
      goto LABEL_54;
    LastError = GetLastError();
    WindowRegionOrBounds = LastError;
    if ( LastError > 0 )
      WindowRegionOrBounds = (unsigned __int16)LastError | 0x80070000;
    if ( WindowRegionOrBounds >= 0 )
    {
LABEL_54:
      if ( CRdpWindowTracker::IsChildStyleSet(v17, v2)
        && (WindowRegionOrBounds = CRdpWindowTracker::ClipParentClientRgn(v19, v2, v8), WindowRegionOrBounds < 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          v11 = 46;
          v12 = "ClipParentClientRgn() failed";
          goto LABEL_12;
        }
      }
      else
      {
        if ( !CombineRgn(v8, v8, this[16], 1) )
        {
          WindowRegionOrBounds = -2147467259;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(v22) = -2147467259;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              47,
              (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
              v20,
              (__int64)"CombineRgn() failed",
              v22);
          }
          goto LABEL_49;
        }
        WindowRegionOrBounds = CRdpWindowTracker::GetBounds(
                                 (struct RDP_TRACKED_WINDOW_NODE *)((char *)a2 + 76),
                                 v2,
                                 TopLevelParent,
                                 (struct tagRECT *)((char *)a2 + 60),
                                 (struct tagRECT *)((char *)a2 + 76),
                                 (struct tagRECT *)((char *)a2 + 44));
        if ( WindowRegionOrBounds >= 0 )
        {
          *((_DWORD *)a2 + 26) = v26;
          *((_QWORD *)a2 + 4) = TopLevelParent;
          goto LABEL_49;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          v11 = 48;
          v12 = "GetBounds() failed";
          goto LABEL_12;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 45;
      v12 = "EnumWindows(STATIC_EnumWindowsProc) failed";
      goto LABEL_12;
    }
    goto LABEL_49;
  }
  WindowRegionOrBounds = (*(__int64 (__fastcall **)(HRGN, HWND, int *))(*(_QWORD *)v13 + 24LL))(
                           v13,
                           TopLevelParent,
                           &v26);
  if ( WindowRegionOrBounds >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v14 = v26;
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Diid(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v16, v15, v2, TopLevelParent, v14);
    }
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 43;
    v12 = "IsWindowOnCurrentVirtualDesktop() failed";
    goto LABEL_12;
  }
LABEL_49:
  if ( RectRgn )
    DeleteObject(RectRgn);
  return (unsigned int)WindowRegionOrBounds;
}

```

## disassembly

```asm
0x14005ca44  mov     [rsp-38h+arg_10], rbx
0x14005ca49  mov     [rsp-38h+arg_0], rcx
0x14005ca4e  push    rbp
0x14005ca4f  push    rsi
0x14005ca50  push    rdi
0x14005ca51  push    r12
0x14005ca53  push    r13
0x14005ca55  push    r14
0x14005ca57  push    r15
0x14005ca59  mov     rbp, rsp
0x14005ca5c  sub     rsp, 60h
0x14005ca60  mov     r15, [rdx+10h]
0x14005ca64  xorps   xmm0, xmm0
0x14005ca67  mov     rsi, rdx
0x14005ca6a  mov     [rbp+arg_8], 1
0x14005ca71  mov     rdx, r15; HWND
0x14005ca74  mov     rdi, rcx
0x14005ca77  movups  xmmword ptr [rbp+lParam], xmm0
0x14005ca7b  movups  [rbp+var_10], xmm0
0x14005ca7f  call    ?GetTopLevelParent@CRdpWindowTracker@@AEAAPEAUHWND__@@PEAU2@@Z; CRdpWindowTracker::GetTopLevelParent(HWND__ *)
0x14005ca84  mov     r14, rax
0x14005ca87  test    rax, rax
0x14005ca8a  jnz     short loc_14005CAE0
0x14005ca8c  mov     rax, cs:WPP_GLOBAL_Control
0x14005ca93  lea     rdi, WPP_GLOBAL_Control
0x14005ca9a  cmp     rax, rdi
0x14005ca9d  jz      short loc_14005CAD6
0x14005ca9f  test    byte ptr [rax+1Ch], 8
0x14005caa3  jz      short loc_14005CAD6
0x14005caa5  cmp     byte ptr [rax+19h], 2
0x14005caa9  jb      short loc_14005CAD6
0x14005caab  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cab0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cab7  lea     edx, [r14+29h]
0x14005cabb  mov     r9d, eax
0x14005cabe  mov     dword ptr [rsp+60h+var_40], 8000FFFFh
0x14005cac6  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005cacd  mov     rcx, [rcx+10h]
0x14005cad1  call    WPP_SF_Dd
0x14005cad6  mov     ebx, 8000FFFFh
0x14005cadb  jmp     loc_14005CDD0
0x14005cae0  mov     r12, [rsi+60h]
0x14005cae4  xor     r9d, r9d; y2
0x14005cae7  xor     r8d, r8d; x2
0x14005caea  xor     edx, edx; y1
0x14005caec  xor     ecx, ecx; x1
0x14005caee  call    cs:__imp_CreateRectRgn
0x14005caf4  mov     rdx, r12; hrgn
0x14005caf7  mov     rcx, r15; hWnd
0x14005cafa  mov     r13, rax
0x14005cafd  call    ?STATIC_GetWindowRegionOrBounds@CRdpWindowTracker@@CAJPEAUHWND__@@PEAUHRGN__@@@Z; CRdpWindowTracker::STATIC_GetWindowRegionOrBounds(HWND__ *,HRGN__ *)
0x14005cb02  mov     ebx, eax
0x14005cb04  test    eax, eax
0x14005cb06  jns     short loc_14005CB6C
0x14005cb08  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb0f  lea     rdi, WPP_GLOBAL_Control
0x14005cb16  cmp     rcx, rdi
0x14005cb19  jz      loc_14005CDC2
0x14005cb1f  test    byte ptr [rcx+1Ch], 8
0x14005cb23  jz      loc_14005CDC2
0x14005cb29  cmp     byte ptr [rcx+19h], 2
0x14005cb2d  jb      loc_14005CDC2
0x14005cb33  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cb38  mov     edx, 2Ah ; '*'
0x14005cb3d  lea     rcx, aCrdpwindowtrac_0; "CRdpWindowTracker::STATIC_GetWindowRegi"...
0x14005cb44  mov     dword ptr [rsp+60h+var_38], ebx
0x14005cb48  mov     [rsp+60h+var_40], rcx
0x14005cb4d  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005cb54  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb5b  mov     r9d, eax
0x14005cb5e  mov     rcx, [rcx+10h]
0x14005cb62  call    WPP_SF_DsD
0x14005cb67  jmp     loc_14005CDC2
0x14005cb6c  mov     rcx, [rdi+50h]
0x14005cb70  lea     rdi, WPP_GLOBAL_Control
0x14005cb77  mov     [rbp+lParam], r15
0x14005cb7b  mov     [rbp+lParam+8], r14
0x14005cb7f  mov     qword ptr [rbp+var_10], r12
0x14005cb83  mov     qword ptr [rbp+var_10+8], r13
0x14005cb87  test    rcx, rcx
0x14005cb8a  jz      loc_14005CC2C
0x14005cb90  mov     rax, [rcx]
0x14005cb93  lea     r8, [rbp+arg_8]
0x14005cb97  mov     rdx, r14
0x14005cb9a  mov     rax, [rax+18h]
0x14005cb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cba3  mov     ebx, eax
0x14005cba5  test    eax, eax
0x14005cba7  jns     short loc_14005CBE3
0x14005cba9  mov     rax, cs:WPP_GLOBAL_Control
0x14005cbb0  cmp     rax, rdi
0x14005cbb3  jz      loc_14005CDC2
0x14005cbb9  test    byte ptr [rax+1Ch], 8
0x14005cbbd  jz      loc_14005CDC2
0x14005cbc3  cmp     byte ptr [rax+19h], 2
0x14005cbc7  jb      loc_14005CDC2
0x14005cbcd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cbd2  mov     edx, 2Bh ; '+'
0x14005cbd7  lea     rcx, aIswindowoncurr; "IsWindowOnCurrentVirtualDesktop() faile"...
0x14005cbde  jmp     loc_14005CB44
0x14005cbe3  mov     rax, cs:WPP_GLOBAL_Control
0x14005cbea  cmp     rax, rdi
0x14005cbed  jz      short loc_14005CC2C
0x14005cbef  test    dword ptr [rax+1Ch], 200h
0x14005cbf6  jz      short loc_14005CC2C
0x14005cbf8  cmp     byte ptr [rax+19h], 5
0x14005cbfc  jb      short loc_14005CC2C
0x14005cbfe  mov     ebx, [rbp+arg_8]
0x14005cc01  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cc06  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc0d  mov     edx, 2Ch ; ','
0x14005cc12  mov     [rsp+60h+var_30], ebx
0x14005cc16  mov     r9d, eax
0x14005cc19  mov     [rsp+60h+var_38], r14
0x14005cc1e  mov     [rsp+60h+var_40], r15
0x14005cc23  mov     rcx, [rcx+10h]
0x14005cc27  call    WPP_SF_Diid
0x14005cc2c  lea     r8, [rbp+lParam]; lParam
0x14005cc30  mov     rcx, r14; hWndParent
0x14005cc33  lea     rdx, ?STATIC_EnumChildWindowsProc@CRdpWindowTracker@@CAHPEAUHWND__@@_J@Z; lpEnumFunc
0x14005cc3a  call    cs:__imp_EnumChildWindows
0x14005cc40  lea     rdx, [rbp+lParam]; lParam
0x14005cc44  lea     rcx, ?STATIC_EnumWindowsProc@CRdpWindowTracker@@CAHPEAUHWND__@@_J@Z; lpEnumFunc
0x14005cc4b  call    cs:__imp_EnumWindows
0x14005cc51  test    eax, eax
0x14005cc53  jnz     short loc_14005CCA8
0x14005cc55  call    cs:__imp_GetLastError
0x14005cc5b  mov     ebx, eax
0x14005cc5d  test    eax, eax
0x14005cc5f  jle     short loc_14005CC6A
0x14005cc61  movzx   ebx, ax
0x14005cc64  or      ebx, 80070000h
0x14005cc6a  test    ebx, ebx
0x14005cc6c  jns     short loc_14005CCA8
0x14005cc6e  mov     rax, cs:WPP_GLOBAL_Control
0x14005cc75  cmp     rax, rdi
0x14005cc78  jz      loc_14005CDC2
0x14005cc7e  test    byte ptr [rax+1Ch], 8
0x14005cc82  jz      loc_14005CDC2
0x14005cc88  cmp     byte ptr [rax+19h], 2
0x14005cc8c  jb      loc_14005CDC2
0x14005cc92  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cc97  mov     edx, 2Dh ; '-'
0x14005cc9c  lea     rcx, aEnumwindowsSta; "EnumWindows(STATIC_EnumWindowsProc) fai"...
0x14005cca3  jmp     loc_14005CB44
0x14005cca8  mov     rdx, r15; HWND
0x14005ccab  call    ?IsChildStyleSet@CRdpWindowTracker@@AEAAHPEAUHWND__@@@Z; CRdpWindowTracker::IsChildStyleSet(HWND__ *)
0x14005ccb0  test    eax, eax
0x14005ccb2  jz      short loc_14005CCFF
0x14005ccb4  mov     r8, r12; HRGN
0x14005ccb7  mov     rdx, r15; HWND
0x14005ccba  call    ?ClipParentClientRgn@CRdpWindowTracker@@AEAAJPEAUHWND__@@PEAUHRGN__@@@Z; CRdpWindowTracker::ClipParentClientRgn(HWND__ *,HRGN__ *)
0x14005ccbf  mov     ebx, eax
0x14005ccc1  test    eax, eax
0x14005ccc3  jns     short loc_14005CCFF
0x14005ccc5  mov     rax, cs:WPP_GLOBAL_Control
0x14005cccc  cmp     rax, rdi
0x14005cccf  jz      loc_14005CDC2
0x14005ccd5  test    byte ptr [rax+1Ch], 8
0x14005ccd9  jz      loc_14005CDC2
0x14005ccdf  cmp     byte ptr [rax+19h], 2
0x14005cce3  jb      loc_14005CDC2
0x14005cce9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ccee  mov     edx, 2Eh ; '.'
0x14005ccf3  lea     rcx, aClipparentclie; "ClipParentClientRgn() failed"
0x14005ccfa  jmp     loc_14005CB44
0x14005ccff  mov     r8, [rbp+arg_0]
0x14005cd03  mov     r9d, 1; iMode
0x14005cd09  mov     rdx, r12; hrgnSrc1
0x14005cd0c  mov     rcx, r12; hrgnDst
0x14005cd0f  mov     r8, [r8+80h]; hrgnSrc2
0x14005cd16  call    cs:__imp_CombineRgn
0x14005cd1c  test    eax, eax
0x14005cd1e  jnz     short loc_14005CD63
0x14005cd20  mov     ebx, 80004005h
0x14005cd25  mov     rax, cs:WPP_GLOBAL_Control
0x14005cd2c  cmp     rax, rdi
0x14005cd2f  jz      loc_14005CDC2
0x14005cd35  test    byte ptr [rax+1Ch], 8
0x14005cd39  jz      loc_14005CDC2
0x14005cd3f  cmp     byte ptr [rax+19h], 2
0x14005cd43  jb      short loc_14005CDC2
0x14005cd45  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cd4a  mov     edx, 2Fh ; '/'
0x14005cd4f  mov     dword ptr [rsp+60h+var_38], 80004005h
0x14005cd57  lea     rcx, aCombinergnFail; "CombineRgn() failed"
0x14005cd5e  jmp     loc_14005CB48
0x14005cd63  lea     rax, [rsi+2Ch]
0x14005cd67  mov     r8, r14; HWND
0x14005cd6a  lea     rcx, [rsi+4Ch]; this
0x14005cd6e  mov     [rsp+60h+var_38], rax; struct tagRECT *
0x14005cd73  lea     r9, [rsi+3Ch]; struct tagRECT *
0x14005cd77  mov     [rsp+60h+var_40], rcx; struct tagRECT *
0x14005cd7c  mov     rdx, r15; HWND
0x14005cd7f  call    ?GetBounds@CRdpWindowTracker@@AEAAJPEAUHWND__@@0PEAUtagRECT@@11@Z; CRdpWindowTracker::GetBounds(HWND__ *,HWND__ *,tagRECT *,tagRECT *,tagRECT *)
0x14005cd84  mov     ebx, eax
0x14005cd86  test    eax, eax
0x14005cd88  jns     short loc_14005CDB8
0x14005cd8a  mov     rax, cs:WPP_GLOBAL_Control
0x14005cd91  cmp     rax, rdi
0x14005cd94  jz      short loc_14005CDC2
0x14005cd96  test    byte ptr [rax+1Ch], 8
0x14005cd9a  jz      short loc_14005CDC2
0x14005cd9c  cmp     byte ptr [rax+19h], 2
0x14005cda0  jb      short loc_14005CDC2
0x14005cda2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cda7  mov     edx, 30h ; '0'
0x14005cdac  lea     rcx, aGetboundsFaile; "GetBounds() failed"
0x14005cdb3  jmp     loc_14005CB44
0x14005cdb8  mov     eax, [rbp+arg_8]
0x14005cdbb  mov     [rsi+68h], eax
0x14005cdbe  mov     [rsi+20h], r14
0x14005cdc2  test    r13, r13
0x14005cdc5  jz      short loc_14005CDD0
0x14005cdc7  mov     rcx, r13; ho
0x14005cdca  call    cs:__imp_DeleteObject
0x14005cdd0  mov     eax, ebx
0x14005cdd2  mov     rbx, [rsp+60h+arg_10]
0x14005cdda  add     rsp, 60h
0x14005cdde  pop     r15
0x14005cde0  pop     r14
0x14005cde2  pop     r13
0x14005cde4  pop     r12
0x14005cde6  pop     rdi
0x14005cde7  pop     rsi
0x14005cde8  pop     rbp
0x14005cde9  retn
```
