# CRailContWndExt::~CRailContWndExt(void)

- ea: `0x14001ec9c`
- end: `0x14001ee7e`
- name: `??1CRailContWndExt@@UEAA@XZ`
- size: `482`
- prototype: `void __fastcall(CRailContWndExt *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14001eef0`

## callees

- `0x140003b14`
- `0x14000b7d8`
- `0x14000c7d0`
- `0x14000c7f8`
- `0x14000cf70`
- `0x14000fa48`
- `0x14001ec9c`
- `0x140020c48`

## import_xrefs

- `USER32!DestroyIcon` at `0x14001ed25`
- `USER32!DestroyIcon` at `0x14001ed25`
- `USER32!SetWindowLongPtrW` at `0x14001ed49`
- `USER32!SetWindowLongPtrW` at `0x14001ed5d`
- `USER32!SetWindowLongPtrW` at `0x14001ed71`
- `USER32!SetWindowLongPtrW` at `0x14001ed88`
- `USER32!SetWindowLongPtrW` at `0x14001ed49`
- `USER32!SetWindowLongPtrW` at `0x14001ed5d`
- `USER32!SetWindowLongPtrW` at `0x14001ed71`
- `USER32!SetWindowLongPtrW` at `0x14001ed88`
- `GDI32!DeleteObject` at `0x14001ed9a`
- `GDI32!DeleteObject` at `0x14001edac`
- `GDI32!DeleteObject` at `0x14001ed9a`
- `GDI32!DeleteObject` at `0x14001edac`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x14001edd2`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x14001edd2`

## pseudocode

```c
void __fastcall CRailContWndExt::~CRailContWndExt(CRailContWndExt *this)
{
  _QWORD *v2; // rsi
  __int64 i; // rdi
  void *v4; // rcx
  HICON v5; // rcx
  HWND v6; // rcx
  HWND v7; // rcx
  HWND v8; // rcx
  HWND v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v2 = (_QWORD *)((char *)this + 48);
  *(_QWORD *)this = &CRailContWndExt::`vftable';
  if ( *((_QWORD *)this + 6) )
  {
    TCntPtr<CTSCoreEventSink>::SafeRelease((char *)this + 48);
    *v2 = 0;
    TCntPtr<CTscSettings>::SafeAddRef(v2);
  }
  if ( *((_QWORD *)this + 260) )
  {
    TCntPtr<CTSCoreEventSink>::SafeRelease((char *)this + 2080);
    *((_QWORD *)this + 260) = 0;
  }
  for ( i = 0; i != 32; ++i )
  {
    v4 = (void *)*((_QWORD *)this + i + 19);
    if ( v4 )
    {
      operator delete(v4);
      *((_QWORD *)this + i + 19) = 0;
    }
  }
  v5 = (HICON)*((_QWORD *)this + 185);
  if ( v5 )
  {
    DestroyIcon(v5);
    *((_QWORD *)this + 185) = 0;
  }
  v6 = (HWND)*((_QWORD *)this + 9);
  if ( v6 )
    SetWindowLongPtrW(v6, -21, 0);
  v7 = (HWND)*((_QWORD *)this + 10);
  if ( v7 )
    SetWindowLongPtrW(v7, -21, 0);
  v8 = (HWND)*((_QWORD *)this + 11);
  if ( v8 )
    SetWindowLongPtrW(v8, -21, 0);
  v9 = (HWND)*((_QWORD *)this + 16);
  if ( v9 )
    SetWindowLongPtrW(v9, -21, 0);
  v10 = (void *)*((_QWORD *)this + 254);
  if ( v10 )
    DeleteObject(v10);
  v11 = (void *)*((_QWORD *)this + 255);
  if ( v11 )
    DeleteObject(v11);
  if ( (*((_DWORD *)this + 517) & 0x100) != 0
    && !RemoveWindowSubclass(*((HWND *)this + 16), CRailContWndExt::ConQueueListViewSubProc, 0x3390u)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  CRailContWndExt::DestroyBrandingBar(this);
  if ( *((char *)this + 2068) >= 0 && qword_1401519A0 )
  {
    CTscRemoteSessionsManager::AppInitializationCompleted(qword_1401519A0, 0);
    *((_DWORD *)this + 517) |= 0x80u;
  }
  TCntPtr<CTSCoreEventSink>::SafeRelease((char *)this + 2080);
  TCntPtr<CTSCoreEventSink>::SafeRelease((char *)this + 2072);
  TCntPtr<CTSCoreEventSink>::SafeRelease(v2);
  *(_QWORD *)this = &CContWndExt::`vftable';
}

```

## disassembly

```asm
0x14001ec9c  push    rbx
0x14001ec9e  push    rsi
0x14001ec9f  push    rdi
0x14001eca0  push    r14
0x14001eca2  sub     rsp, 28h
0x14001eca6  lea     rax, ??_7CRailContWndExt@@6B@; const CRailContWndExt::`vftable'
0x14001ecad  mov     rbx, rcx
0x14001ecb0  lea     rsi, [rcx+30h]
0x14001ecb4  mov     [rcx], rax
0x14001ecb7  cmp     qword ptr [rsi], 0
0x14001ecbb  jz      short loc_14001ECD4
0x14001ecbd  mov     rcx, rsi
0x14001ecc0  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14001ecc5  mov     rcx, rsi
0x14001ecc8  mov     qword ptr [rsi], 0
0x14001eccf  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x14001ecd4  lea     r14, [rbx+820h]
0x14001ecdb  cmp     qword ptr [r14], 0
0x14001ecdf  jz      short loc_14001ECF0
0x14001ece1  mov     rcx, r14
0x14001ece4  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14001ece9  mov     qword ptr [r14], 0
0x14001ecf0  xor     edi, edi
0x14001ecf2  mov     rcx, [rbx+rdi*8+98h]; Block
0x14001ecfa  test    rcx, rcx
0x14001ecfd  jz      short loc_14001ED10
0x14001ecff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001ed04  mov     qword ptr [rbx+rdi*8+98h], 0
0x14001ed10  inc     rdi
0x14001ed13  cmp     rdi, 20h ; ' '
0x14001ed17  jnz     short loc_14001ECF2
0x14001ed19  mov     rcx, [rbx+5C8h]; hIcon
0x14001ed20  test    rcx, rcx
0x14001ed23  jz      short loc_14001ED36
0x14001ed25  call    cs:__imp_DestroyIcon
0x14001ed2b  mov     qword ptr [rbx+5C8h], 0
0x14001ed36  mov     rcx, [rbx+48h]; hWnd
0x14001ed3a  mov     edi, 0FFFFFFEBh
0x14001ed3f  test    rcx, rcx
0x14001ed42  jz      short loc_14001ED4F
0x14001ed44  xor     r8d, r8d; dwNewLong
0x14001ed47  mov     edx, edi; nIndex
0x14001ed49  call    cs:__imp_SetWindowLongPtrW
0x14001ed4f  mov     rcx, [rbx+50h]; hWnd
0x14001ed53  test    rcx, rcx
0x14001ed56  jz      short loc_14001ED63
0x14001ed58  xor     r8d, r8d; dwNewLong
0x14001ed5b  mov     edx, edi; nIndex
0x14001ed5d  call    cs:__imp_SetWindowLongPtrW
0x14001ed63  mov     rcx, [rbx+58h]; hWnd
0x14001ed67  test    rcx, rcx
0x14001ed6a  jz      short loc_14001ED77
0x14001ed6c  xor     r8d, r8d; dwNewLong
0x14001ed6f  mov     edx, edi; nIndex
0x14001ed71  call    cs:__imp_SetWindowLongPtrW
0x14001ed77  mov     rcx, [rbx+80h]; hWnd
0x14001ed7e  test    rcx, rcx
0x14001ed81  jz      short loc_14001ED8E
0x14001ed83  xor     r8d, r8d; dwNewLong
0x14001ed86  mov     edx, edi; nIndex
0x14001ed88  call    cs:__imp_SetWindowLongPtrW
0x14001ed8e  mov     rcx, [rbx+7F0h]; ho
0x14001ed95  test    rcx, rcx
0x14001ed98  jz      short loc_14001EDA0
0x14001ed9a  call    cs:__imp_DeleteObject
0x14001eda0  mov     rcx, [rbx+7F8h]; ho
0x14001eda7  test    rcx, rcx
0x14001edaa  jz      short loc_14001EDB2
0x14001edac  call    cs:__imp_DeleteObject
0x14001edb2  test    dword ptr [rbx+814h], 100h
0x14001edbc  jz      short loc_14001EE22
0x14001edbe  mov     rcx, [rbx+80h]; hWnd
0x14001edc5  lea     rdx, ?ConQueueListViewSubProc@CRailContWndExt@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x14001edcc  mov     r8d, 3390h; uIdSubclass
0x14001edd2  call    cs:__imp_RemoveWindowSubclass
0x14001edd8  test    eax, eax
0x14001edda  jnz     short loc_14001EE22
0x14001eddc  mov     rax, cs:WPP_GLOBAL_Control
0x14001ede3  lea     rcx, WPP_GLOBAL_Control
0x14001edea  cmp     rax, rcx
0x14001eded  jz      short loc_14001EE22
0x14001edef  test    dword ptr [rax+1Ch], 1000h
0x14001edf6  jz      short loc_14001EE22
0x14001edf8  cmp     byte ptr [rax+19h], 2
0x14001edfc  jb      short loc_14001EE22
0x14001edfe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001ee03  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee0a  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001ee11  mov     edx, 10h
0x14001ee16  mov     r9d, eax
0x14001ee19  mov     rcx, [rcx+10h]
0x14001ee1d  call    WPP_SF_d
0x14001ee22  mov     rcx, rbx; this
0x14001ee25  call    ?DestroyBrandingBar@CRailContWndExt@@AEAAXXZ; CRailContWndExt::DestroyBrandingBar(void)
0x14001ee2a  test    byte ptr [rbx+814h], 80h
0x14001ee31  jnz     short loc_14001EE4E
0x14001ee33  mov     rcx, cs:qword_1401519A0; this
0x14001ee3a  test    rcx, rcx
0x14001ee3d  jz      short loc_14001EE4E
0x14001ee3f  xor     edx, edx; int
0x14001ee41  call    ?AppInitializationCompleted@CTscRemoteSessionsManager@@QEAAHH@Z; CTscRemoteSessionsManager::AppInitializationCompleted(int)
0x14001ee46  bts     dword ptr [rbx+814h], 7
0x14001ee4e  mov     rcx, r14
0x14001ee51  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14001ee56  lea     rcx, [rbx+818h]
0x14001ee5d  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14001ee62  mov     rcx, rsi
0x14001ee65  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14001ee6a  lea     rax, ??_7CContWndExt@@6B@; const CContWndExt::`vftable'
0x14001ee71  mov     [rbx], rax
0x14001ee74  add     rsp, 28h
0x14001ee78  pop     r14
0x14001ee7a  pop     rdi
0x14001ee7b  pop     rsi
0x14001ee7c  pop     rbx
0x14001ee7d  retn
```
