# CBasePlayer::OnGeometryInformation(tagGEO_INFO *,ulong,tagTS_RECT *,ulong)

- ea: `0x180612c90`
- end: `0x180613481`
- name: `?OnGeometryInformation@CBasePlayer@@UEAAJPEAUtagGEO_INFO@@KPEAUtagTS_RECT@@K@Z`
- size: `2033`
- prototype: `__int64 __usercall@<rax>(CBasePlayer *__hidden this@<rcx>, struct tagGEO_INFO *@<rdx>, unsigned int@<r8d>, struct tagTS_RECT *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001cdc0`
- `0x1800204e8`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800dcebc`
- `0x1800f47c8`
- `0x1800f5d9c`
- `0x180130604`
- `0x180154698`
- `0x180612a78`
- `0x180612c90`
- `0x1806154b0`
- `0x1806165cc`
- `0x180616660`
- `0x180616a3c`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180612feb`
- `KERNEL32!GetLastError` at `0x1806133b8`
- `KERNEL32!GetLastError` at `0x1806133e4`
- `KERNEL32!GetLastError` at `0x180612feb`
- `KERNEL32!GetLastError` at `0x1806133b8`
- `KERNEL32!GetLastError` at `0x1806133e4`
- `GDI32!CreateRectRgn` at `0x180612fc4`
- `GDI32!CreateRectRgn` at `0x1806131b7`
- `GDI32!CreateRectRgn` at `0x180612fc4`
- `GDI32!CreateRectRgn` at `0x1806131b7`
- `GDI32!CombineRgn` at `0x1806131d9`
- `GDI32!CombineRgn` at `0x1806131d9`
- `GDI32!DeleteObject` at `0x1806131ea`
- `GDI32!DeleteObject` at `0x1806132a9`
- `GDI32!DeleteObject` at `0x180613392`
- `GDI32!DeleteObject` at `0x180613400`
- `GDI32!DeleteObject` at `0x1806131ea`
- `GDI32!DeleteObject` at `0x1806132a9`
- `GDI32!DeleteObject` at `0x180613392`
- `GDI32!DeleteObject` at `0x180613400`
- `USER32!GetWindowRect` at `0x1806132f9`
- `USER32!GetWindowRect` at `0x1806132f9`
- `USER32!ShowWindow` at `0x180612e8c`
- `USER32!ShowWindow` at `0x180612f84`
- `USER32!ShowWindow` at `0x180612e8c`
- `USER32!ShowWindow` at `0x180612f84`
- `USER32!SetWindowPos` at `0x180612e35`
- `USER32!SetWindowPos` at `0x180612e35`
- `USER32!SetWindowRgn` at `0x1806132a0`
- `USER32!SetWindowRgn` at `0x1806132a0`

## pseudocode

```c
__int64 __fastcall CBasePlayer::OnGeometryInformation(
        CBasePlayer *this,
        struct tagGEO_INFO *a2,
        __int64 a3,
        struct tagTS_RECT *a4,
        unsigned int a5)
{
  CTSCriticalSection *v5; // rbx
  unsigned __int64 v8; // r14
  __int64 v9; // rdi
  unsigned int v10; // eax
  signed int updated; // r12d
  HKEY v12; // r8
  unsigned int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  unsigned int v16; // eax
  HWND v17; // rcx
  __int64 v18; // rdi
  unsigned int v19; // eax
  int IsVideoPlaying; // eax
  HKEY v21; // r8
  __int64 v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // eax
  DWORD v25; // ebx
  unsigned int v26; // eax
  HKEY v27; // rbx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // ecx
  __int64 v31; // rax
  int v32; // ecx
  unsigned int v33; // eax
  unsigned int v34; // eax
  HRGN RectRgn; // rax
  HRGN v36; // rbx
  unsigned int v37; // eax
  HRGN v38; // rbx
  __int64 v39; // rbx
  unsigned int v40; // eax
  HWND v41; // rcx
  LONG v42; // r15d
  int v43; // edx
  int v44; // r13d
  LONG v45; // ebx
  LONG v46; // edi
  LONG v47; // r13d
  unsigned int v48; // eax
  DWORD LastError; // ebx
  unsigned int v50; // eax
  signed int v51; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int x1; // [rsp+40h] [rbp-51h]
  int x1a; // [rsp+40h] [rbp-51h]
  int y1; // [rsp+44h] [rbp-4Dh]
  int y1a; // [rsp+44h] [rbp-4Dh]
  HRGN hrgnDst; // [rsp+48h] [rbp-49h] BYREF
  int y2; // [rsp+50h] [rbp-41h]
  int x2; // [rsp+54h] [rbp-3Dh]
  struct tagRECT v61; // [rsp+58h] [rbp-39h] BYREF
  unsigned int v62; // [rsp+68h] [rbp-29h]
  struct tagGEO_INFO *v63; // [rsp+70h] [rbp-21h] BYREF
  struct tagRECT v64; // [rsp+80h] [rbp-11h] BYREF
  struct tagTS_RECT *v65; // [rsp+90h] [rbp-1h]
  struct tagRECT Rect; // [rsp+98h] [rbp+7h] BYREF
  unsigned int v67; // [rsp+110h] [rbp+7Fh]

  v5 = (CBasePlayer *)((char *)this + 320);
  v65 = a4;
  v63 = a2;
  hrgnDst = (HRGN)((char *)this + 320);
  CTSCriticalSection::Lock((CBasePlayer *)((char *)this + 320));
  v8 = *((_QWORD *)this + 58);
  v9 = *((_QWORD *)this + 57);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&hrgnDst);
  if ( *(_QWORD *)a2 != v9 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        161,
        &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids, v10);
  }
  updated = CBasePlayer::UpdateVideoParentServerPos(this, v8);
  if ( updated < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        162,
        &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
        v13,
        updated);
      v12 = WPP_GLOBAL_Control;
    }
    updated = 0;
  }
  else
  {
    *((_DWORD *)this + 104) = 0;
    v12 = WPP_GLOBAL_Control;
  }
  v14 = *((_DWORD *)v63 + 2);
  x1 = v14;
  if ( (v14 & 2) != 0 )
  {
    if ( v12 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v12[7] & 1) != 0 && *((_BYTE *)v12 + 25) >= 2u )
    {
      v15 = *((_QWORD *)this + 54);
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        163,
        &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
        v16,
        x1,
        v15);
    }
    v17 = (HWND)*((_QWORD *)this + 54);
    if ( v17 )
    {
      SetWindowPos(v17, 0, 0, 0, 0, 0, 0x210u);
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = *((_QWORD *)this + 54);
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids, v19, v18);
      }
      ShowWindow(*((HWND *)this + 54), 0);
      *((_QWORD *)this + 66) = 0;
    }
    v63 = v5;
    CTSCriticalSection::Lock(v5);
    *((_DWORD *)this + 112) = 0;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v63);
    return 0;
  }
  if ( (v14 & 1) != 0 )
  {
    IsVideoPlaying = CBasePlayer::IsVideoPlaying(this);
    y1 = IsVideoPlaying;
    if ( v21 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v21[7] & 1) != 0 && *((_BYTE *)v21 + 25) >= 2u )
    {
      v22 = *((_QWORD *)this + 54);
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        165,
        &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
        v23,
        x1,
        v22,
        y1);
      v21 = WPP_GLOBAL_Control;
      IsVideoPlaying = y1;
    }
    hrgnDst = (HRGN)*((_QWORD *)this + 54);
    if ( hrgnDst && IsVideoPlaying )
    {
      if ( v21 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v21[7] & 1) != 0 && *((_BYTE *)v21 + 25) >= 2u )
      {
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          166,
          &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
          v24,
          hrgnDst);
      }
      ShowWindow(*((HWND *)this + 54), 1);
    }
    hrgnDst = (HRGN)v5;
    CTSCriticalSection::Lock(v5);
    *((_DWORD *)this + 112) = 1;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&hrgnDst);
    LOWORD(v14) = x1;
  }
  if ( (v14 & 0x1000) != 0 )
  {
    v64 = 0;
    hrgnDst = CreateRectRgn(0, 0, 0, 0);
    if ( hrgnDst )
    {
      v27 = WPP_GLOBAL_Control;
      v28 = a5 >> 4;
      v67 = a5 >> 4;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ddq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          169,
          &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
          v29,
          v67,
          this);
        v28 = v67;
        v27 = WPP_GLOBAL_Control;
      }
      v30 = 0;
      v62 = 0;
      if ( v28 )
      {
        while ( 1 )
        {
          v31 = 2LL * v30;
          v61 = 0;
          y1a = *((_DWORD *)v65 + 4 * v30);
          v61.top = y1a;
          x1a = *((_DWORD *)v65 + 4 * v30 + 1);
          v61.left = x1a;
          v32 = *((_DWORD *)v65 + 4 * v30 + 2);
          x2 = *((_DWORD *)v65 + 2 * v31 + 3);
          v61.right = x2;
          y2 = v32;
          v61.bottom = v32;
          if ( v27 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v27[7] & 1) != 0 && *((_BYTE *)v27 + 25) >= 5u )
          {
            v33 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ddddd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              170,
              &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
              v33,
              y1a,
              x1a,
              y2,
              x2);
            v27 = WPP_GLOBAL_Control;
          }
          if ( *((_DWORD *)this + 128) || *((_DWORD *)this + 131) != 100 )
          {
            CBasePlayer::TransformFromDesktopToClientWnd(this, &v61);
            if ( v27 == (HKEY)&WPP_GLOBAL_Control || ((_BYTE)v27[7] & 1) == 0 || *((_BYTE *)v27 + 25) < 5u )
            {
              y2 = v61.bottom;
              x2 = v61.right;
              x1a = v61.left;
              y1a = v61.top;
            }
            else
            {
              v34 = RdpWppGetCurrentThreadActivityIdPrefix();
              x2 = v61.right;
              y2 = v61.bottom;
              x1a = v61.left;
              y1a = v61.top;
              WPP_SF_Ddddd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                171,
                &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
                v34,
                v61.top,
                v61.left,
                v61.bottom,
                v61.right);
            }
          }
          RectRgn = CreateRectRgn(x1a, y1a, x2, y2);
          v36 = RectRgn;
          if ( !RectRgn )
            break;
          if ( !CombineRgn(hrgnDst, hrgnDst, RectRgn, 2) )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v48 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids, v48);
            }
            DeleteObject(v36);
            updated = -2147467259;
            goto LABEL_93;
          }
          DeleteObject(v36);
          v27 = WPP_GLOBAL_Control;
          v30 = v62 + 1;
          v62 = v30;
          if ( v30 >= v67 )
            goto LABEL_64;
        }
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v50 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            172,
            &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
            v50,
            LastError);
        }
        v51 = GetLastError();
        updated = v51;
        if ( v51 > 0 )
          updated = (unsigned __int16)v51 | 0x80070000;
LABEL_93:
        DeleteObject(hrgnDst);
      }
      else
      {
LABEL_64:
        if ( v27 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v27[7] & 1) != 0 && *((_BYTE *)v27 + 25) >= 5u )
        {
          v37 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids, v37);
        }
        v38 = hrgnDst;
        PrintRegion(hrgnDst);
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v39 = *((_QWORD *)this + 54);
          v40 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dqq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            175,
            &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids,
            v40,
            this,
            v39);
          v38 = hrgnDst;
        }
        SetWindowRgn(*((HWND *)this + 54), v38, 1);
        DeleteObject(v38);
        v41 = (HWND)*((_QWORD *)this + 55);
        Rect = 0;
        v42 = *((_DWORD *)v63 + 9);
        v43 = v42 - *((_DWORD *)v63 + 5);
        v44 = *((_DWORD *)v63 + 3);
        v45 = *((_DWORD *)v63 + 10);
        v46 = *((_DWORD *)v63 + 4) + *((_DWORD *)v63 + 6) - v43;
        v64.left = v42;
        v64.top = v45;
        v47 = v42 + v44 - 2 * v43;
        v64.bottom = v46;
        v64.right = v47;
        if ( GetWindowRect(v41, &Rect) && v42 == Rect.left && v45 == Rect.top && v47 == Rect.right && v46 == Rect.bottom )
          v64.top = v45 + 1;
        if ( *((_DWORD *)this + 128) || *((_DWORD *)this + 131) != 100 )
          CBasePlayer::TransformFromDesktopToClientWnd(this, &v64);
        CBasePlayer::UpdateVideoWindowPosition(this, &v64);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = GetLastError();
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_6346c49aa73435086f7baf16af3313b5_Traceguids, v26, v25);
      }
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180612c90  mov     [rsp-8+arg_10], rbx
0x180612c95  push    rbp
0x180612c96  push    rsi
0x180612c97  push    rdi
0x180612c98  push    r12
0x180612c9a  push    r13
0x180612c9c  push    r14
0x180612c9e  push    r15
0x180612ca0  lea     rbp, [rsp-1Fh]
0x180612ca5  sub     rsp, 0B0h
0x180612cac  mov     rax, cs:__security_cookie
0x180612cb3  xor     rax, rsp
0x180612cb6  mov     [rbp+4Fh+var_38], rax
0x180612cba  lea     rbx, [rcx+140h]
0x180612cc1  mov     [rbp+4Fh+var_50], r9
0x180612cc5  mov     rsi, rcx
0x180612cc8  mov     [rbp+4Fh+var_70], rdx
0x180612ccc  mov     rcx, rbx; this
0x180612ccf  mov     [rbp+4Fh+hrgnDst], rbx
0x180612cd3  mov     r15, rdx
0x180612cd6  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180612cdb  mov     r14, [rsi+1D0h]
0x180612ce2  lea     rcx, [rbp+4Fh+hrgnDst]; this
0x180612ce6  mov     rdi, [rsi+1C8h]
0x180612ced  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180612cf2  cmp     [r15], rdi
0x180612cf5  jnz     loc_180613408
0x180612cfb  mov     rax, cs:WPP_GLOBAL_Control
0x180612d02  lea     r13, WPP_GLOBAL_Control
0x180612d09  lea     rdi, WPP_6346c49aa73435086f7baf16af3313b5_Traceguids
0x180612d10  mov     r15d, 1
0x180612d16  cmp     rax, r13
0x180612d19  jz      short loc_180612D47
0x180612d1b  test    [rax+1Ch], r15b
0x180612d1f  jz      short loc_180612D47
0x180612d21  cmp     byte ptr [rax+19h], 5
0x180612d25  jb      short loc_180612D47
0x180612d27  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180612d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180612d33  mov     edx, 0A0h
0x180612d38  mov     r9d, eax
0x180612d3b  mov     r8, rdi
0x180612d3e  mov     rcx, [rcx+10h]
0x180612d42  call    WPP_SF_d
0x180612d47  mov     rdx, r14; unsigned __int64
0x180612d4a  mov     rcx, rsi; this
0x180612d4d  call    ?UpdateVideoParentServerPos@CBasePlayer@@IEAAJ_K@Z; CBasePlayer::UpdateVideoParentServerPos(unsigned __int64)
0x180612d52  xor     r14d, r14d
0x180612d55  mov     r12d, eax
0x180612d58  test    eax, eax
0x180612d5a  js      short loc_180612D6C
0x180612d5c  mov     [rsi+1A0h], r14d
0x180612d63  mov     r8, cs:WPP_GLOBAL_Control
0x180612d6a  jmp     short loc_180612DB4
0x180612d6c  mov     r8, cs:WPP_GLOBAL_Control
0x180612d73  cmp     r8, r13
0x180612d76  jz      short loc_180612DB1
0x180612d78  test    [r8+1Ch], r15b
0x180612d7c  jz      short loc_180612DB1
0x180612d7e  cmp     byte ptr [r8+19h], 2
0x180612d83  jb      short loc_180612DB1
0x180612d85  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180612d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180612d91  mov     edx, 0A2h
0x180612d96  mov     r9d, eax
0x180612d99  mov     [rsp+0E0h+var_C0], r12d
0x180612d9e  mov     r8, rdi
0x180612da1  mov     rcx, [rcx+10h]
0x180612da5  call    WPP_SF_Dd
0x180612daa  mov     r8, cs:WPP_GLOBAL_Control
0x180612db1  mov     r12d, r14d
0x180612db4  mov     rax, [rbp+4Fh+var_70]
0x180612db8  mov     eax, [rax+8]
0x180612dbb  mov     [rbp+4Fh+x1], eax
0x180612dbe  test    al, 2
0x180612dc0  jz      loc_180612EBA
0x180612dc6  cmp     r8, r13
0x180612dc9  jz      short loc_180612E0F
0x180612dcb  test    [r8+1Ch], r15b
0x180612dcf  jz      short loc_180612E0F
0x180612dd1  cmp     byte ptr [r8+19h], 2
0x180612dd6  jb      short loc_180612E0F
0x180612dd8  mov     rdi, [rsi+1B0h]
0x180612ddf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180612de4  mov     ecx, [rbp+4Fh+x1]
0x180612de7  lea     r8, WPP_6346c49aa73435086f7baf16af3313b5_Traceguids
0x180612dee  mov     qword ptr [rsp+0E0h+cy], rdi
0x180612df3  mov     edx, 0A3h
0x180612df8  mov     [rsp+0E0h+var_C0], ecx
0x180612dfc  mov     r9d, eax
0x180612dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180612e06  mov     rcx, [rcx+10h]
0x180612e0a  call    WPP_SF_Ddq
0x180612e0f  mov     rcx, [rsi+1B0h]; hWnd
0x180612e16  test    rcx, rcx
0x180612e19  jz      short loc_180612E99
0x180612e1b  mov     [rsp+0E0h+uFlags], 210h; uFlags
0x180612e23  xor     r9d, r9d; Y
0x180612e26  mov     [rsp+0E0h+cy], r14d; cy
0x180612e2b  xor     r8d, r8d; X
0x180612e2e  xor     edx, edx; hWndInsertAfter
0x180612e30  mov     [rsp+0E0h+var_C0], r14d; cx
0x180612e35  call    cs:__imp_SetWindowPos
0x180612e3b  mov     rax, cs:WPP_GLOBAL_Control
0x180612e42  cmp     rax, r13
0x180612e45  jz      short loc_180612E83
0x180612e47  test    [rax+1Ch], r15b
0x180612e4b  jz      short loc_180612E83
0x180612e4d  cmp     byte ptr [rax+19h], 2
0x180612e51  jb      short loc_180612E83
0x180612e53  mov     rdi, [rsi+1B0h]
0x180612e5a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180612e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180612e66  lea     r8, WPP_6346c49aa73435086f7baf16af3313b5_Traceguids
0x180612e6d  mov     edx, 0A4h
0x180612e72  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x180612e77  mov     r9d, eax
0x180612e7a  mov     rcx, [rcx+10h]
0x180612e7e  call    WPP_SF_Dq
0x180612e83  mov     rcx, [rsi+1B0h]; hWnd
0x180612e8a  xor     edx, edx; nCmdShow
0x180612e8c  call    cs:__imp_ShowWindow
0x180612e92  mov     [rsi+210h], r14
0x180612e99  mov     rcx, rbx; this
0x180612e9c  mov     [rbp+4Fh+var_70], rbx
0x180612ea0  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180612ea5  lea     rcx, [rbp+4Fh+var_70]; this
0x180612ea9  mov     [rsi+1C0h], r14d
0x180612eb0  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180612eb5  jmp     loc_180613454
0x180612eba  test    r15b, al
0x180612ebd  jz      loc_180612FA9
0x180612ec3  mov     rcx, rsi; this
0x180612ec6  call    ?IsVideoPlaying@CBasePlayer@@IEAAHXZ; CBasePlayer::IsVideoPlaying(void)
0x180612ecb  mov     [rbp+4Fh+y1], eax
0x180612ece  cmp     r8, r13
0x180612ed1  jz      short loc_180612F2B
0x180612ed3  test    [r8+1Ch], r15b
0x180612ed7  jz      short loc_180612F2B
0x180612ed9  cmp     byte ptr [r8+19h], 2
0x180612ede  jb      short loc_180612F2B
0x180612ee0  mov     rdi, [rsi+1B0h]
0x180612ee7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180612eec  mov     ecx, [rbp+4Fh+y1]
0x180612eef  mov     edx, 0A5h
0x180612ef4  mov     [rsp+0E0h+uFlags], ecx
0x180612ef8  mov     r9d, eax
0x180612efb  mov     ecx, [rbp+4Fh+x1]
0x180612efe  mov     qword ptr [rsp+0E0h+cy], rdi
0x180612f03  lea     rdi, WPP_6346c49aa73435086f7baf16af3313b5_Traceguids
0x180612f0a  mov     [rsp+0E0h+var_C0], ecx
0x180612f0e  mov     r8, rdi
0x180612f11  mov     rcx, cs:WPP_GLOBAL_Control
0x180612f18  mov     rcx, [rcx+10h]
0x180612f1c  call    WPP_SF_Ddqd
0x180612f21  mov     r8, cs:WPP_GLOBAL_Control
0x180612f28  mov     eax, [rbp+4Fh+y1]
0x180612f2b  mov     rcx, [rsi+1B0h]
0x180612f32  mov     [rbp+4Fh+hrgnDst], rcx
0x180612f36  test    rcx, rcx
0x180612f39  jz      short loc_180612F8A
0x180612f3b  test    eax, eax
0x180612f3d  jz      short loc_180612F8A
0x180612f3f  cmp     r8, r13
0x180612f42  jz      short loc_180612F7A
0x180612f44  test    [r8+1Ch], r15b
0x180612f48  jz      short loc_180612F7A
0x180612f4a  cmp     byte ptr [r8+19h], 2
0x180612f4f  jb      short loc_180612F7A
0x180612f51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180612f56  mov     rcx, [rbp+4Fh+hrgnDst]
0x180612f5a  mov     edx, 0A6h
0x180612f5f  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x180612f64  mov     r9d, eax
0x180612f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180612f6e  mov     r8, rdi
0x180612f71  mov     rcx, [rcx+10h]
0x180612f75  call    WPP_SF_Dq
0x180612f7a  mov     rcx, [rsi+1B0h]; hWnd
0x180612f81  mov     edx, r15d; nCmdShow
0x180612f84  call    cs:__imp_ShowWindow
0x180612f8a  mov     rcx, rbx; this
0x180612f8d  mov     [rbp+4Fh+hrgnDst], rbx
0x180612f91  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180612f96  lea     rcx, [rbp+4Fh+hrgnDst]; this
0x180612f9a  mov     [rsi+1C0h], r15d
0x180612fa1  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180612fa6  mov     eax, [rbp+4Fh+x1]
0x180612fa9  bt      eax, 0Ch
0x180612fad  jnb     loc_180613457
0x180612fb3  xorps   xmm0, xmm0
0x180612fb6  xor     r9d, r9d; y2
0x180612fb9  xor     r8d, r8d; x2
0x180612fbc  xor     edx, edx; y1
0x180612fbe  xor     ecx, ecx; x1
0x180612fc0  movups  xmmword ptr [rbp+4Fh+var_60.left], xmm0
0x180612fc4  call    cs:__imp_CreateRectRgn
0x180612fca  mov     [rbp+4Fh+hrgnDst], rax
0x180612fce  test    rax, rax
0x180612fd1  jnz     short loc_180613022
0x180612fd3  mov     rax, cs:WPP_GLOBAL_Control
0x180612fda  cmp     rax, r13
0x180612fdd  jz      short loc_180613017
0x180612fdf  test    [rax+1Ch], r15b
0x180612fe3  jz      short loc_180613017
0x180612fe5  cmp     byte ptr [rax+19h], 2
0x180612fe9  jb      short loc_180613017
0x180612feb  call    cs:__imp_GetLastError
0x180612ff1  mov     ebx, eax
0x180612ff3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180612ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180612fff  mov     edx, 0A7h
0x180613004  mov     r9d, eax
0x180613007  mov     [rsp+0E0h+var_C0], ebx
0x18061300b  mov     r8, rdi
0x18061300e  mov     rcx, [rcx+10h]
0x180613012  call    WPP_SF_Dd
0x180613017  mov     r12d, 80004005h
0x18061301d  jmp     loc_180613457
0x180613022  mov     eax, [rbp+4Fh+arg_20]
0x180613025  mov     rbx, cs:WPP_GLOBAL_Control
0x18061302c  shr     eax, 4
0x18061302f  mov     [rbp+4Fh+arg_20], eax
0x180613032  cmp     rbx, r13
0x180613035  jz      short loc_180613079
0x180613037  test    [rbx+1Ch], r15b
0x18061303b  jz      short loc_180613079
0x18061303d  cmp     byte ptr [rbx+19h], 5
0x180613041  jb      short loc_180613079
0x180613043  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180613048  mov     ecx, [rbp+4Fh+arg_20]
0x18061304b  mov     edx, 0A9h
0x180613050  mov     qword ptr [rsp+0E0h+cy], rsi
0x180613055  mov     r9d, eax
0x180613058  mov     [rsp+0E0h+var_C0], ecx
0x18061305c  mov     r8, rdi
0x18061305f  mov     rcx, cs:WPP_GLOBAL_Control
0x180613066  mov     rcx, [rcx+10h]
0x18061306a  call    WPP_SF_Ddq
0x18061306f  mov     eax, [rbp+4Fh+arg_20]
0x180613072  mov     rbx, cs:WPP_GLOBAL_Control
0x180613079  mov     ecx, r14d
0x18061307c  mov     [rbp+4Fh+var_78], ecx
0x18061307f  test    eax, eax
0x180613081  jz      loc_180613209
0x180613087  mov     rdx, [rbp+4Fh+var_50]
0x18061308b  xorps   xmm0, xmm0
0x18061308e  mov     eax, ecx
0x180613090  add     rax, rax
0x180613093  movups  xmmword ptr [rbp+4Fh+var_88.left], xmm0
0x180613097  mov     ecx, [rdx+rax*8]
0x18061309a  mov     [rbp+4Fh+y1], ecx
0x18061309d  mov     [rbp+4Fh+var_88.top], ecx
0x1806130a0  mov     ecx, [rdx+rax*8+4]
0x1806130a4  mov     [rbp+4Fh+x1], ecx
0x1806130a7  mov     [rbp+4Fh+var_88.left], ecx
0x1806130aa  mov     ecx, [rdx+rax*8+8]
0x1806130ae  mov     eax, [rdx+rax*8+0Ch]
0x1806130b2  mov     [rbp+4Fh+x2], eax
0x1806130b5  mov     [rbp+4Fh+var_88.right], eax
0x1806130b8  mov     [rbp+4Fh+y2], ecx
0x1806130bb  mov     [rbp+4Fh+var_88.bottom], ecx
0x1806130be  cmp     rbx, r13
0x1806130c1  jz      short loc_180613112
0x1806130c3  test    [rbx+1Ch], r15b
0x1806130c7  jz      short loc_180613112
0x1806130c9  cmp     byte ptr [rbx+19h], 5
0x1806130cd  jb      short loc_180613112
0x1806130cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1806130d4  mov     ecx, [rbp+4Fh+x2]
0x1806130d7  mov     edx, 0AAh
0x1806130dc  mov     [rsp+0E0h+var_A8], ecx
0x1806130e0  mov     r9d, eax
0x1806130e3  mov     ecx, [rbp+4Fh+y2]
0x1806130e6  mov     r8, rdi
0x1806130e9  mov     [rsp+0E0h+uFlags], ecx
0x1806130ed  mov     ecx, [rbp+4Fh+x1]
0x1806130f0  mov     [rsp+0E0h+cy], ecx
0x1806130f4  mov     ecx, [rbp+4Fh+y1]
0x1806130f7  mov     [rsp+0E0h+var_C0], ecx
0x1806130fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180613102  mov     rcx, [rcx+10h]
0x180613106  call    WPP_SF_Ddddd
0x18061310b  mov     rbx, cs:WPP_GLOBAL_Control
0x180613112  cmp     [rsi+200h], r14d
0x180613119  jnz     short loc_180613128
0x18061311b  cmp     dword ptr [rsi+20Ch], 64h ; 'd'
0x180613122  jz      loc_1806131A9
0x180613128  lea     rdx, [rbp+4Fh+var_88]; struct tagRECT *
0x18061312c  mov     rcx, rsi; this
0x18061312f  call    ?TransformFromDesktopToClientWnd@CBasePlayer@@IEAAXPEAUtagRECT@@@Z; CBasePlayer::TransformFromDesktopToClientWnd(tagRECT *)
0x180613134  cmp     rbx, r13
0x180613137  jz      short loc_18061318F
0x180613139  test    [rbx+1Ch], r15b
0x18061313d  jz      short loc_18061318F
0x18061313f  cmp     byte ptr [rbx+19h], 5
0x180613143  jb      short loc_18061318F
0x180613145  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18061314a  mov     ecx, [rbp+4Fh+var_88.right]
0x18061314d  mov     edx, 0ABh
  ... truncated ...
```
