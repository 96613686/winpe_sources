# CRdpWindowTracker::UpdateAllGeometries(void)

- ea: `0x14005f470`
- end: `0x14005f881`
- name: `?UpdateAllGeometries@CRdpWindowTracker@@AEAAJXZ`
- size: `1041`
- prototype: `__int64 __fastcall(CRdpWindowTracker *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14005d16c`
- `0x14005f888`

## callees

- `0x140004b1c`
- `0x140004cf4`
- `0x140005750`
- `0x14000d350`
- `0x14000efb8`
- `0x14001094c`
- `0x140033cd4`
- `0x140035e34`
- `0x14005ca44`
- `0x14005f470`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `USER32!CopyRect` at `0x14005f662`
- `USER32!CopyRect` at `0x14005f679`
- `USER32!CopyRect` at `0x14005f662`
- `USER32!CopyRect` at `0x14005f679`
- `USER32!EqualRect` at `0x14005f6ba`
- `USER32!EqualRect` at `0x14005f6cd`
- `USER32!EqualRect` at `0x14005f6ba`
- `USER32!EqualRect` at `0x14005f6cd`
- `USER32!SetTimer` at `0x14005f4fd`
- `USER32!SetTimer` at `0x14005f4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f51b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f51b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14005f4a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14005f4a5`
- `GDI32!EqualRgn` at `0x14005f6a7`
- `GDI32!EqualRgn` at `0x14005f6a7`
- `GDI32!CreateRectRgn` at `0x14005f5b3`
- `GDI32!CreateRectRgn` at `0x14005f5b3`
- `GDI32!CombineRgn` at `0x14005f64b`
- `GDI32!CombineRgn` at `0x14005f64b`
- `GDI32!DeleteObject` at `0x14005f851`
- `GDI32!DeleteObject` at `0x14005f851`

## string_xrefs

- `0x14005f602`: `CreateRectRgn() failed`
- `0x14005f820`: `CombineRgn() failed`
- `0x14005f7b9`: `CopyRect() failed`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::UpdateAllGeometries(CRdpWindowTracker *this)
{
  signed int WindowGeometry; // edi
  CTSCriticalSection *v3; // rbx
  DWORD TickCount; // esi
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRGN RectRgn; // r14
  unsigned int v8; // eax
  __int64 v9; // rsi
  char *v10; // rax
  __int64 NextOf; // rax
  bool v12; // zf
  int v13; // r13d
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  CRdpWindowTracker *v19; // [rsp+30h] [rbp-88h] BYREF
  CTSCriticalSection *v20; // [rsp+38h] [rbp-80h] BYREF
  struct tagRECT rcDst; // [rsp+40h] [rbp-78h] BYREF
  RECT rc1; // [rsp+50h] [rbp-68h] BYREF

  rcDst = 0;
  WindowGeometry = 0;
  rc1 = 0;
  v3 = (CRdpWindowTracker *)((char *)this + 56);
  TickCount = GetTickCount();
  v20 = v3;
  CTSCriticalSection::Lock(v3);
  if ( *((_DWORD *)this + 74) )
    goto LABEL_50;
  if ( TickCount - *((_DWORD *)this + 73) < 0x64 )
  {
    CTSCriticalSection::UnLock((CRdpWindowTracker *)((char *)this + 56));
    *((_QWORD *)this + 38) = SetTimer(*((HWND *)this + 12), 1u, *((_DWORD *)this + 73) - TickCount + 100, 0);
    CTSCriticalSection::Lock((CRdpWindowTracker *)((char *)this + 56));
    if ( *((_QWORD *)this + 38) )
      goto LABEL_12;
    LastError = GetLastError();
    WindowGeometry = LastError;
    if ( LastError > 0 )
      WindowGeometry = (unsigned __int16)LastError | 0x80070000;
    if ( WindowGeometry >= 0 )
    {
LABEL_12:
      *((_DWORD *)this + 74) = 1;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"SetTimer() failed",
        WindowGeometry);
    }
    goto LABEL_50;
  }
  *((_DWORD *)this + 73) = TickCount;
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  if ( !RectRgn )
  {
    WindowGeometry = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v8,
        (__int64)"CreateRectRgn() failed",
        -2147467259);
    }
    goto LABEL_50;
  }
  v9 = 0;
LABEL_19:
  v10 = (char *)this + 248;
  while ( 1 )
  {
    do
    {
      NextOf = CTEntryList<RDP_TRACKED_WINDOW_NODE,0>::GetNextOfEx(v10, v9);
      v9 = NextOf;
      if ( !NextOf )
        goto LABEL_49;
      v12 = *(_DWORD *)(NextOf + 40) == 0;
      v10 = (char *)this + 248;
    }
    while ( v12 );
    if ( !CombineRgn(RectRgn, *(HRGN *)(v9 + 96), 0, 5) )
    {
      WindowGeometry = -2147467259;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 106;
      v17 = "CombineRgn() failed";
LABEL_48:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v15,
        (__int64)v17,
        -2147467259);
      goto LABEL_49;
    }
    if ( !CopyRect(&rcDst, (const RECT *)(v9 + 60)) )
    {
      WindowGeometry = -2147467259;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 107;
      goto LABEL_39;
    }
    if ( !CopyRect(&rc1, (const RECT *)(v9 + 76)) )
    {
      WindowGeometry = -2147467259;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 108;
LABEL_39:
      v17 = "CopyRect() failed";
      goto LABEL_48;
    }
    v13 = *(_DWORD *)(v9 + 104);
    WindowGeometry = CRdpWindowTracker::GetWindowGeometry(this, (struct RDP_TRACKED_WINDOW_NODE *)v9);
    if ( WindowGeometry < 0 )
      break;
    if ( EqualRgn(RectRgn, *(HRGN *)(v9 + 96)) )
    {
      if ( EqualRect(&rcDst, (const RECT *)(v9 + 60)) )
      {
        if ( EqualRect(&rc1, (const RECT *)(v9 + 76)) )
        {
          v10 = (char *)this + 248;
          if ( v13 == *(_DWORD *)(v9 + 104) )
            continue;
        }
      }
    }
    v19 = this;
    TCntPtr<CRdpWindowTracker>::SafeAddRef(&v19);
    CTSCriticalSection::UnLock((CRdpWindowTracker *)((char *)this + 56));
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 9) + 32LL))(
      *((_QWORD *)this + 9),
      ((unsigned __int64)this + 48) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
      *(_QWORD *)(v9 + 16));
    CTSCriticalSection::Lock((CRdpWindowTracker *)((char *)this + 56));
    TCntPtr<CRdpClipMainWnd>::SafeRelease(&v19);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
      v14,
      (__int64)"GetWindowGeometry() failed",
      WindowGeometry);
  }
LABEL_49:
  DeleteObject(RectRgn);
LABEL_50:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v20);
  return (unsigned int)WindowGeometry;
}

```

## disassembly

```asm
0x14005f470  push    rbx
0x14005f472  push    rbp
0x14005f473  push    rsi
0x14005f474  push    rdi
0x14005f475  push    r12
0x14005f477  push    r13
0x14005f479  push    r14
0x14005f47b  push    r15
0x14005f47d  sub     rsp, 78h
0x14005f481  mov     rax, cs:__security_cookie
0x14005f488  xor     rax, rsp
0x14005f48b  mov     [rsp+0B8h+var_58], rax
0x14005f490  xorps   xmm0, xmm0
0x14005f493  xorps   xmm1, xmm1
0x14005f496  movups  xmmword ptr [rsp+0B8h+rcDst.left], xmm0
0x14005f49b  mov     rbp, rcx
0x14005f49e  xor     edi, edi
0x14005f4a0  movups  xmmword ptr [rsp+0B8h+rc1.left], xmm1
0x14005f4a5  call    cs:__imp_GetTickCount
0x14005f4ab  lea     rbx, [rbp+38h]
0x14005f4af  mov     esi, eax
0x14005f4b1  mov     rcx, rbx; this
0x14005f4b4  mov     [rsp+0B8h+var_80], rbx
0x14005f4b9  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14005f4be  cmp     [rbp+128h], edi
0x14005f4c4  jnz     loc_14005F857
0x14005f4ca  mov     eax, esi
0x14005f4cc  sub     eax, [rbp+124h]
0x14005f4d2  cmp     eax, 64h ; 'd'
0x14005f4d5  jnb     loc_14005F5A3
0x14005f4db  mov     rcx, rbx; this
0x14005f4de  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x14005f4e3  mov     r8d, [rbp+124h]
0x14005f4ea  xor     r9d, r9d; lpTimerFunc
0x14005f4ed  mov     rcx, [rbp+60h]; hWnd
0x14005f4f1  sub     r8d, esi
0x14005f4f4  lea     esi, [rdi+1]
0x14005f4f7  add     r8d, 64h ; 'd'; uElapse
0x14005f4fb  mov     edx, esi; nIDEvent
0x14005f4fd  call    cs:__imp_SetTimer
0x14005f503  mov     rcx, rbx; this
0x14005f506  mov     [rbp+130h], rax
0x14005f50d  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14005f512  cmp     [rbp+130h], rdi
0x14005f519  jnz     short loc_14005F598
0x14005f51b  call    cs:__imp_GetLastError
0x14005f521  mov     edi, eax
0x14005f523  test    eax, eax
0x14005f525  jle     short loc_14005F530
0x14005f527  movzx   edi, ax
0x14005f52a  or      edi, 80070000h
0x14005f530  test    edi, edi
0x14005f532  jns     short loc_14005F598
0x14005f534  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f53b  lea     rax, WPP_GLOBAL_Control
0x14005f542  cmp     rcx, rax
0x14005f545  jz      loc_14005F857
0x14005f54b  test    byte ptr [rcx+1Ch], 8
0x14005f54f  jz      loc_14005F857
0x14005f555  cmp     byte ptr [rcx+19h], 2
0x14005f559  jb      loc_14005F857
0x14005f55f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005f564  mov     edx, 68h ; 'h'
0x14005f569  mov     [rsp+0B8h+var_90], edi
0x14005f56d  lea     rcx, aSettimerFailed_0; "SetTimer() failed"
0x14005f574  mov     [rsp+0B8h+var_98], rcx
0x14005f579  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005f580  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f587  mov     r9d, eax
0x14005f58a  mov     rcx, [rcx+10h]
0x14005f58e  call    WPP_SF_DsD
0x14005f593  jmp     loc_14005F857
0x14005f598  mov     [rbp+128h], esi
0x14005f59e  jmp     loc_14005F857
0x14005f5a3  xor     r9d, r9d; y2
0x14005f5a6  mov     [rbp+124h], esi
0x14005f5ac  xor     r8d, r8d; x2
0x14005f5af  xor     edx, edx; y1
0x14005f5b1  xor     ecx, ecx; x1
0x14005f5b3  call    cs:__imp_CreateRectRgn
0x14005f5b9  mov     r14, rax
0x14005f5bc  test    rax, rax
0x14005f5bf  jnz     short loc_14005F60E
0x14005f5c1  mov     edi, 80004005h
0x14005f5c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f5cd  lea     rax, WPP_GLOBAL_Control
0x14005f5d4  cmp     rcx, rax
0x14005f5d7  jz      loc_14005F857
0x14005f5dd  test    byte ptr [rcx+1Ch], 8
0x14005f5e1  jz      loc_14005F857
0x14005f5e7  cmp     byte ptr [rcx+19h], 2
0x14005f5eb  jb      loc_14005F857
0x14005f5f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005f5f6  lea     edx, [r14+69h]
0x14005f5fa  mov     [rsp+0B8h+var_90], 80004005h
0x14005f602  lea     rcx, aCreaterectrgnF; "CreateRectRgn() failed"
0x14005f609  jmp     loc_14005F574
0x14005f60e  xor     esi, esi
0x14005f610  lea     rax, [rbp+0F8h]
0x14005f617  mov     rdx, rsi
0x14005f61a  mov     rcx, rax
0x14005f61d  call    ?GetNextOfEx@?$CTEntryList@URDP_TRACKED_WINDOW_NODE@@$0A@@@QEAAPEAURDP_TRACKED_WINDOW_NODE@@PEAU2@@Z; CTEntryList<RDP_TRACKED_WINDOW_NODE,0>::GetNextOfEx(RDP_TRACKED_WINDOW_NODE *)
0x14005f622  mov     rsi, rax
0x14005f625  test    rax, rax
0x14005f628  jz      loc_14005F84E
0x14005f62e  cmp     dword ptr [rax+28h], 0
0x14005f632  lea     rax, [rbp+0F8h]
0x14005f639  jz      short loc_14005F617
0x14005f63b  mov     rdx, [rsi+60h]; hrgnSrc1
0x14005f63f  mov     r9d, 5; iMode
0x14005f645  xor     r8d, r8d; hrgnSrc2
0x14005f648  mov     rcx, r14; hrgnDst
0x14005f64b  call    cs:__imp_CombineRgn
0x14005f651  test    eax, eax
0x14005f653  jz      loc_14005F7F2
0x14005f659  lea     rdx, [rsi+3Ch]; lprcSrc
0x14005f65d  lea     rcx, [rsp+0B8h+rcDst]; lprcDst
0x14005f662  call    cs:__imp_CopyRect
0x14005f668  test    eax, eax
0x14005f66a  jz      loc_14005F7C2
0x14005f670  lea     rdx, [rsi+4Ch]; lprcSrc
0x14005f674  lea     rcx, [rsp+0B8h+rc1]; lprcDst
0x14005f679  call    cs:__imp_CopyRect
0x14005f67f  test    eax, eax
0x14005f681  jz      loc_14005F77F
0x14005f687  mov     r13d, [rsi+68h]
0x14005f68b  mov     rdx, rsi; struct RDP_TRACKED_WINDOW_NODE *
0x14005f68e  mov     rcx, rbp; this
0x14005f691  call    ?GetWindowGeometry@CRdpWindowTracker@@AEAAJPEAURDP_TRACKED_WINDOW_NODE@@@Z; CRdpWindowTracker::GetWindowGeometry(RDP_TRACKED_WINDOW_NODE *)
0x14005f696  mov     edi, eax
0x14005f698  test    eax, eax
0x14005f69a  js      loc_14005F73A
0x14005f6a0  mov     rdx, [rsi+60h]; hrgn2
0x14005f6a4  mov     rcx, r14; hrgn1
0x14005f6a7  call    cs:__imp_EqualRgn
0x14005f6ad  test    eax, eax
0x14005f6af  jz      short loc_14005F6E8
0x14005f6b1  lea     rdx, [rsi+3Ch]; lprc2
0x14005f6b5  lea     rcx, [rsp+0B8h+rcDst]; lprc1
0x14005f6ba  call    cs:__imp_EqualRect
0x14005f6c0  test    eax, eax
0x14005f6c2  jz      short loc_14005F6E8
0x14005f6c4  lea     rdx, [rsi+4Ch]; lprc2
0x14005f6c8  lea     rcx, [rsp+0B8h+rc1]; lprc1
0x14005f6cd  call    cs:__imp_EqualRect
0x14005f6d3  test    eax, eax
0x14005f6d5  jz      short loc_14005F6E8
0x14005f6d7  lea     rax, [rbp+0F8h]
0x14005f6de  cmp     r13d, [rsi+68h]
0x14005f6e2  jz      loc_14005F617
0x14005f6e8  lea     rcx, [rsp+0B8h+var_88]
0x14005f6ed  mov     [rsp+0B8h+var_88], rbp
0x14005f6f2  call    ?SafeAddRef@?$TCntPtr@VCRdpWindowTracker@@@@AEAAXXZ; TCntPtr<CRdpWindowTracker>::SafeAddRef(void)
0x14005f6f7  mov     rcx, rbx; this
0x14005f6fa  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x14005f6ff  mov     rcx, [rbp+48h]
0x14005f703  lea     r8, [rbp+30h]
0x14005f707  mov     rax, rbp
0x14005f70a  neg     rax
0x14005f70d  mov     r9, [rcx]
0x14005f710  sbb     rdx, rdx
0x14005f713  and     rdx, r8
0x14005f716  mov     r8, [rsi+10h]
0x14005f71a  mov     rax, [r9+20h]
0x14005f71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005f723  mov     rcx, rbx; this
0x14005f726  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14005f72b  lea     rcx, [rsp+0B8h+var_88]
0x14005f730  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x14005f735  jmp     loc_14005F610
0x14005f73a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f741  lea     rax, WPP_GLOBAL_Control
0x14005f748  cmp     rcx, rax
0x14005f74b  jz      loc_14005F84E
0x14005f751  test    byte ptr [rcx+1Ch], 8
0x14005f755  jz      loc_14005F84E
0x14005f75b  cmp     byte ptr [rcx+19h], 2
0x14005f75f  jb      loc_14005F84E
0x14005f765  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005f76a  mov     edx, 6Dh ; 'm'
0x14005f76f  mov     [rsp+0B8h+var_90], edi
0x14005f773  lea     rcx, aGetwindowgeome; "GetWindowGeometry() failed"
0x14005f77a  jmp     loc_14005F82F
0x14005f77f  mov     edi, 80004005h
0x14005f784  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f78b  lea     rax, WPP_GLOBAL_Control
0x14005f792  cmp     rcx, rax
0x14005f795  jz      loc_14005F84E
0x14005f79b  test    byte ptr [rcx+1Ch], 8
0x14005f79f  jz      loc_14005F84E
0x14005f7a5  cmp     byte ptr [rcx+19h], 2
0x14005f7a9  jb      loc_14005F84E
0x14005f7af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005f7b4  mov     edx, 6Ch ; 'l'
0x14005f7b9  lea     rcx, aCopyrectFailed; "CopyRect() failed"
0x14005f7c0  jmp     short loc_14005F827
0x14005f7c2  mov     edi, 80004005h
0x14005f7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f7ce  lea     rax, WPP_GLOBAL_Control
0x14005f7d5  cmp     rcx, rax
0x14005f7d8  jz      short loc_14005F84E
0x14005f7da  test    byte ptr [rcx+1Ch], 8
0x14005f7de  jz      short loc_14005F84E
0x14005f7e0  cmp     byte ptr [rcx+19h], 2
0x14005f7e4  jb      short loc_14005F84E
0x14005f7e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005f7eb  mov     edx, 6Bh ; 'k'
0x14005f7f0  jmp     short loc_14005F7B9
0x14005f7f2  mov     edi, 80004005h
0x14005f7f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f7fe  lea     rax, WPP_GLOBAL_Control
0x14005f805  cmp     rcx, rax
0x14005f808  jz      short loc_14005F84E
0x14005f80a  test    byte ptr [rcx+1Ch], 8
0x14005f80e  jz      short loc_14005F84E
0x14005f810  cmp     byte ptr [rcx+19h], 2
0x14005f814  jb      short loc_14005F84E
0x14005f816  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005f81b  mov     edx, 6Ah ; 'j'
0x14005f820  lea     rcx, aCombinergnFail; "CombineRgn() failed"
0x14005f827  mov     [rsp+0B8h+var_90], 80004005h
0x14005f82f  mov     [rsp+0B8h+var_98], rcx
0x14005f834  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005f83b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f842  mov     r9d, eax
0x14005f845  mov     rcx, [rcx+10h]
0x14005f849  call    WPP_SF_DsD
0x14005f84e  mov     rcx, r14; ho
0x14005f851  call    cs:__imp_DeleteObject
0x14005f857  lea     rcx, [rsp+0B8h+var_80]; this
0x14005f85c  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14005f861  mov     eax, edi
0x14005f863  mov     rcx, [rsp+0B8h+var_58]
0x14005f868  xor     rcx, rsp; StackCookie
0x14005f86b  call    __security_check_cookie
0x14005f870  add     rsp, 78h
0x14005f874  pop     r15
0x14005f876  pop     r14
0x14005f878  pop     r13
0x14005f87a  pop     r12
0x14005f87c  pop     rdi
0x14005f87d  pop     rsi
0x14005f87e  pop     rbp
0x14005f87f  pop     rbx
0x14005f880  retn
```
