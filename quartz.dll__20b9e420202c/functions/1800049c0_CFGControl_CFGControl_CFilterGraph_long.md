# CFGControl::CFGControl(CFilterGraph *,long *)

- ea: `0x1800049c0`
- end: `0x180005201`
- name: `??0CFGControl@@AEAA@PEAVCFilterGraph@@PEAJ@Z`
- size: `2113`
- prototype: `CFGControl *__fastcall(CFGControl *__hidden this, struct CFilterGraph *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029690`

## callees

- `0x180004060`
- `0x1800049c0`
- `0x18000aa30`
- `0x1800135b0`
- `0x1800274d0`
- `0x180139f68`
- `0x18015e010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180004d3e`
- `KERNEL32!CreateEventW` at `0x1800050dd`
- `KERNEL32!CreateEventW` at `0x180004d3e`
- `KERNEL32!CreateEventW` at `0x1800050dd`
- `KERNEL32!InitializeCriticalSection` at `0x180004a16`
- `KERNEL32!InitializeCriticalSection` at `0x180004aae`
- `KERNEL32!InitializeCriticalSection` at `0x180004c08`
- `KERNEL32!InitializeCriticalSection` at `0x180004c22`
- `KERNEL32!InitializeCriticalSection` at `0x180004d25`
- `KERNEL32!InitializeCriticalSection` at `0x180005076`
- `KERNEL32!InitializeCriticalSection` at `0x180004a16`
- `KERNEL32!InitializeCriticalSection` at `0x180004aae`
- `KERNEL32!InitializeCriticalSection` at `0x180004c08`
- `KERNEL32!InitializeCriticalSection` at `0x180004c22`
- `KERNEL32!InitializeCriticalSection` at `0x180004d25`
- `KERNEL32!InitializeCriticalSection` at `0x180005076`
- `KERNEL32!LeaveCriticalSection` at `0x180004ea6`
- `KERNEL32!LeaveCriticalSection` at `0x180004ea6`
- `KERNEL32!EnterCriticalSection` at `0x180004e30`
- `KERNEL32!EnterCriticalSection` at `0x180004e30`
- `KERNEL32!GetProcAddress` at `0x1800051c9`
- `KERNEL32!GetProcAddress` at `0x1800051e3`
- `KERNEL32!GetProcAddress` at `0x1800051c9`
- `KERNEL32!GetProcAddress` at `0x1800051e3`
- `KERNEL32!GetModuleHandleW` at `0x1800051b0`
- `KERNEL32!GetModuleHandleW` at `0x1800051b0`
- `KERNEL32!GetCurrentProcessId` at `0x180004b9d`
- `KERNEL32!GetCurrentProcessId` at `0x180004b9d`
- `USER32!GetWindowThreadProcessId` at `0x180005197`
- `USER32!GetWindowThreadProcessId` at `0x180005197`

## string_xrefs

- `0x1800051a3`: `user32.dll`

## pseudocode

```c
CFGControl *__fastcall CFGControl::CFGControl(CFGControl *this, struct CFilterGraph *a2, int *a3)
{
  char *v5; // rax
  char *v6; // rax
  char *v7; // rax
  char *v8; // rax
  CBaseList *v9; // rcx
  void *NextI; // rbp
  struct __POSITION *v11; // r8
  char *v12; // rax
  char *v13; // rax
  char *v14; // rax
  char *v15; // rax
  char *v16; // rax
  char *v17; // rax
  int v18; // eax
  __int64 v19; // rbx
  HWND v20; // rcx
  HMODULE ModuleHandleW; // rbx
  struct __POSITION *v23; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 2) = (char *)a2 + 256;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 4;
  *((_QWORD *)this + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_DWORD *)this + 33) = 0;
  *((_DWORD *)this + 34) = 0;
  *(_QWORD *)((char *)this + 140) = 0;
  *(_QWORD *)((char *)this + 148) = 0;
  *((_DWORD *)this + 39) = 0;
  *((_DWORD *)this + 40) = -1;
  *((_DWORD *)this + 41) = 0;
  *((_DWORD *)this + 42) = 0;
  *((_DWORD *)this + 43) = 0;
  *((_DWORD *)this + 44) = 0;
  *((_DWORD *)this + 46) = -1;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 28) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 39) = 10;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_DWORD *)this + 86) = 0;
  *((_QWORD *)this + 44) = 10;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 96) = 0;
  *((_QWORD *)this + 49) = 10;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_DWORD *)this + 106) = 0;
  *((_QWORD *)this + 54) = 10;
  *((_QWORD *)this + 55) = 0;
  v5 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v5 )
    v5 = (char *)this + 456;
  *((_QWORD *)this + 58) = v5;
  *((_DWORD *)this + 118) = 0;
  *((_QWORD *)this + 56) = &CResourceManager::`vftable'{for `IResourceManager'};
  *((_QWORD *)this + 57) = &CResourceManager::`vftable'{for `CUnknown'};
  *((_DWORD *)this + 120) = GetCurrentProcessId();
  CResourceManager::ProcessAttach(1);
  if ( !CResourceManager::m_pData )
    *a3 = -2147024882;
  *((_QWORD *)this + 62) = g_hInst;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_DWORD *)this + 132) = 0;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_DWORD *)this + 140) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_WORD *)this + 292) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 592));
  *((_BYTE *)this + 636) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 16);
  *((_DWORD *)this + 158) = 0;
  *((_QWORD *)this + 61) = &CFGControl::CGraphWindow::`vftable';
  *((_QWORD *)this + 85) = this;
  *((_DWORD *)this + 172) = 0;
  v6 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v6 )
    v6 = (char *)this + 704;
  *((_QWORD *)this + 89) = v6;
  *((_DWORD *)this + 180) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 87) = &CFGControl::CImplMediaControl::`vftable'{for `IMediaControl'};
  *((_QWORD *)this + 88) = &CFGControl::CImplMediaControl::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 92) = this;
  v7 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v7 )
    v7 = (char *)this + 760;
  *((_QWORD *)this + 96) = v7;
  *((_DWORD *)this + 194) = 0;
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 94) = &CImplMediaEvent::`vftable'{for `IMediaEventEx'};
  *((_QWORD *)this + 95) = &CImplMediaEvent::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 99) = &CImplMediaEvent::`vftable';
  *((_QWORD *)this + 100) = this;
  *((_QWORD *)this + 101) = 0;
  *((_DWORD *)this + 210) = 0;
  *((_QWORD *)this + 106) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_DWORD *)this + 216) = 0;
  *((_QWORD *)this + 109) = 10;
  *((_QWORD *)this + 110) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  *((_QWORD *)this + 104) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 116) = 0;
  *((_QWORD *)this + 117) = 0x2032001000LL;
  *((_QWORD *)this + 118) = 0x4001000F80022LL;
  *((_QWORD *)this + 119) = 0;
  *((_DWORD *)this + 240) = 0;
  v8 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v8 )
    v8 = (char *)this + 976;
  *((_QWORD *)this + 123) = v8;
  *((_DWORD *)this + 248) = 0;
  *((_QWORD *)this + 121) = &CFGControl::CImplMediaSeeking::`vftable'{for `IMediaSeeking'};
  *((_QWORD *)this + 122) = &CFGControl::CImplMediaSeeking::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 125) = this;
  *((_QWORD *)this + 129) = 0x3FF0000000000000LL;
  *((_QWORD *)this + 131) = 0x7FFFFFFFFFFFFFFFLL;
  *((GUID *)this + 63) = TIME_FORMAT_MEDIA_TIME;
  *((_QWORD *)this + 128) = 0;
  *((_QWORD *)this + 132) = 0;
  *((_QWORD *)this + 133) = 0;
  *((_QWORD *)this + 137) = 0;
  *((_QWORD *)this + 130) = 0;
  *((_BYTE *)this + 1072) = 0;
  *((_QWORD *)this + 136) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v23 = (struct __POSITION *)*((_QWORD *)this + 106);
  while ( v23 )
  {
    NextI = CBaseList::GetNextI(v9, &v23);
    if ( *(_DWORD *)NextI == 28 )
    {
      CBaseList::RemoveI((CFGControl *)((char *)this + 848), v11);
      CImplMediaEvent::RealFreeEventParams(*(_DWORD *)NextI, *((_QWORD *)NextI + 1), *((_QWORD *)NextI + 2));
      operator delete(NextI);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v12 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v12 )
    v12 = (char *)this + 1112;
  *((_QWORD *)this + 140) = v12;
  *((_DWORD *)this + 282) = 0;
  *((_QWORD *)this + 142) = 0;
  *((_QWORD *)this + 138) = &CFGControl::CImplMediaPosition::`vftable'{for `IMediaPosition'};
  *((_QWORD *)this + 139) = &CFGControl::CImplMediaPosition::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 143) = this;
  v13 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v13 )
    v13 = (char *)this + 1160;
  *((_QWORD *)this + 146) = v13;
  *((_DWORD *)this + 294) = 0;
  *((_QWORD *)this + 148) = 0;
  *((_QWORD *)this + 144) = &CFGControl::CImplVideoWindow::`vftable'{for `IVideoWindow'};
  *((_QWORD *)this + 145) = &CFGControl::CImplVideoWindow::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 149) = this;
  *((_QWORD *)this + 150) = 0;
  *((_QWORD *)this + 151) = 0;
  *((_DWORD *)this + 304) = 0;
  *((_QWORD *)this + 153) = 0;
  *((_QWORD *)this + 154) = 0;
  *((_QWORD *)this + 155) = 0;
  *((_QWORD *)this + 156) = 0;
  *((_QWORD *)this + 157) = 0;
  *((_QWORD *)this + 158) = 0;
  *((_QWORD *)this + 159) = 0;
  v14 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v14 )
    v14 = (char *)this + 1392;
  *((_QWORD *)this + 175) = v14;
  *((_DWORD *)this + 352) = 0;
  *((_QWORD *)this + 177) = 0;
  *((_QWORD *)this + 173) = &CFGControl::CImplBasicVideo::`vftable'{for `IBasicVideo2'};
  *((_QWORD *)this + 174) = &CFGControl::CImplBasicVideo::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 178) = this;
  v15 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v15 )
    v15 = (char *)this + 1440;
  *((_QWORD *)this + 181) = v15;
  *((_DWORD *)this + 364) = 0;
  *((_QWORD *)this + 183) = 0;
  *((_QWORD *)this + 179) = &CFGControl::CImplBasicAudio::`vftable'{for `IBasicAudio'};
  *((_QWORD *)this + 180) = &CFGControl::CImplBasicAudio::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 184) = this;
  v16 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 189) = this;
  if ( !v16 )
    v16 = (char *)this + 1480;
  *((_QWORD *)this + 186) = v16;
  *((_QWORD *)this + 185) = &CFGControl::CImplMediaFilter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 188) = &CFGControl::CImplMediaFilter::`vftable'{for `IMediaFilter'};
  *((_DWORD *)this + 374) = 0;
  v17 = (char *)*((_QWORD *)this + 1);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !v17 )
    v17 = (char *)this + 1528;
  *((_QWORD *)this + 192) = v17;
  *((_DWORD *)this + 386) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 39);
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_DWORD *)this + 404) = 0;
  *((_QWORD *)this + 203) = 10;
  *((_QWORD *)this + 204) = 0;
  *((_QWORD *)this + 205) = 0;
  *((_QWORD *)this + 206) = 0;
  *((_DWORD *)this + 414) = 0;
  *((_QWORD *)this + 208) = 10;
  *((_QWORD *)this + 209) = 0;
  *((_QWORD *)this + 210) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 211) = 0;
  *((_QWORD *)this + 212) = 0;
  *((_QWORD *)this + 213) = 0;
  *((_DWORD *)this + 428) = 0;
  *((_QWORD *)this + 215) = 0;
  *((_QWORD *)this + 190) = &CFGControl::CImplQueueCommand::`vftable'{for `IQueueCommand'};
  *((_QWORD *)this + 191) = &CFGControl::CImplQueueCommand::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 218) = 0;
  *((_QWORD *)this + 194) = &CFGControl::CImplQueueCommand::`vftable'{for `CCmdQueue'};
  *((_QWORD *)this + 216) = this;
  *((_DWORD *)this + 438) = 0;
  if ( *a3 >= 0 )
  {
    v18 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 61) + 16LL))((char *)this + 488);
    if ( v18 >= 0 )
    {
      v19 = *(_QWORD *)this;
      v20 = (HWND)*((_QWORD *)this + 63);
      *(_QWORD *)(v19 + 272) = v20;
      *(_DWORD *)(v19 + 280) = 1034;
      *(_DWORD *)(v19 + 284) = GetWindowThreadProcessId(v20, 0);
      ModuleHandleW = GetModuleHandleW(L"user32.dll");
      *((_QWORD *)this + 14) = GetProcAddress(ModuleHandleW, "UnregisterDeviceNotification");
      *((_QWORD *)this + 15) = GetProcAddress(ModuleHandleW, "RegisterDeviceNotificationW");
    }
    else
    {
      *a3 = v18;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800049c0  push    rbx
0x1800049c2  push    rsi
0x1800049c3  push    rdi
0x1800049c4  push    r14
0x1800049c6  sub     rsp, 28h
0x1800049ca  mov     [rcx], rdx
0x1800049cd  mov     rdi, rcx
0x1800049d0  mov     rax, [rdx+88h]
0x1800049d7  mov     r14, r8
0x1800049da  mov     [rcx+8], rax
0x1800049de  lea     rax, [rdx+100h]
0x1800049e5  mov     [rcx+10h], rax
0x1800049e9  mov     [rsp+48h+arg_10], r12
0x1800049ee  xor     r12d, r12d
0x1800049f1  mov     [rcx+18h], r12
0x1800049f5  mov     [rcx+20h], r12
0x1800049f9  mov     [rcx+28h], r12
0x1800049fd  mov     [rcx+30h], r12d
0x180004a01  mov     qword ptr [rcx+38h], 4
0x180004a09  mov     [rcx+40h], r12
0x180004a0d  add     rcx, 48h ; 'H'; lpCriticalSection
0x180004a11  mov     [rsp+48h+var_28], r15
0x180004a16  call    cs:__imp_InitializeCriticalSection
0x180004a1d  nop     dword ptr [rax+rax+00h]
0x180004a22  mov     [rdi+70h], r12
0x180004a26  lea     rcx, [rdi+0E8h]; lpCriticalSection
0x180004a2d  mov     [rdi+78h], r12
0x180004a31  mov     [rdi+80h], r12d
0x180004a38  mov     [rdi+84h], r12d
0x180004a3f  mov     [rdi+88h], r12d
0x180004a46  mov     [rdi+8Ch], r12
0x180004a4d  mov     [rdi+94h], r12
0x180004a54  mov     [rdi+9Ch], r12d
0x180004a5b  mov     dword ptr [rdi+0A0h], 0FFFFFFFFh
0x180004a65  mov     [rdi+0A4h], r12d
0x180004a6c  mov     [rdi+0A8h], r12d
0x180004a73  mov     [rdi+0ACh], r12d
0x180004a7a  mov     [rdi+0B0h], r12d
0x180004a81  mov     dword ptr [rdi+0B8h], 0FFFFFFFFh
0x180004a8b  mov     [rdi+0C0h], r12
0x180004a92  mov     [rdi+0C8h], r12
0x180004a99  mov     [rdi+0D0h], r12
0x180004aa0  mov     [rdi+0D8h], r12d
0x180004aa7  mov     [rdi+0E0h], r12
0x180004aae  call    cs:__imp_InitializeCriticalSection
0x180004ab5  nop     dword ptr [rax+rax+00h]
0x180004aba  mov     [rdi+110h], r12
0x180004ac1  lea     rcx, [rdi+1C8h]
0x180004ac8  mov     [rdi+118h], r12
0x180004acf  mov     [rdi+120h], r12
0x180004ad6  mov     [rdi+128h], r12
0x180004add  mov     [rdi+130h], r12d
0x180004ae4  mov     qword ptr [rdi+138h], 0Ah
0x180004aef  mov     [rdi+140h], r12
0x180004af6  mov     [rdi+148h], r12
0x180004afd  mov     [rdi+150h], r12
0x180004b04  mov     [rdi+158h], r12d
0x180004b0b  mov     qword ptr [rdi+160h], 0Ah
0x180004b16  mov     [rdi+168h], r12
0x180004b1d  mov     [rdi+170h], r12
0x180004b24  mov     [rdi+178h], r12
0x180004b2b  mov     [rdi+180h], r12d
0x180004b32  mov     qword ptr [rdi+188h], 0Ah
0x180004b3d  mov     [rdi+190h], r12
0x180004b44  mov     [rdi+198h], r12
0x180004b4b  mov     [rdi+1A0h], r12
0x180004b52  mov     [rdi+1A8h], r12d
0x180004b59  mov     qword ptr [rdi+1B0h], 0Ah
0x180004b64  mov     [rdi+1B8h], r12
0x180004b6b  mov     rax, [rdi+8]
0x180004b6f  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180004b76  test    rax, rax
0x180004b79  cmovz   rax, rcx
0x180004b7d  mov     [rcx+8], rax
0x180004b81  lea     rax, ??_7CResourceManager@@6BIResourceManager@@@; const CResourceManager::`vftable'{for `IResourceManager'}
0x180004b88  mov     [rcx+10h], r12d
0x180004b8c  mov     [rdi+1C0h], rax
0x180004b93  lea     rax, ??_7CResourceManager@@6BCUnknown@@@; const CResourceManager::`vftable'{for `CUnknown'}
0x180004b9a  mov     [rcx], rax
0x180004b9d  call    cs:__imp_GetCurrentProcessId
0x180004ba4  nop     dword ptr [rax+rax+00h]
0x180004ba9  mov     ecx, 1; int
0x180004bae  mov     [rdi+1E0h], eax
0x180004bb4  call    ?ProcessAttach@CResourceManager@@SAXH@Z; CResourceManager::ProcessAttach(int)
0x180004bb9  cmp     cs:?m_pData@CResourceManager@@2PEAVCResourceData@@EA, r12; CResourceData * CResourceManager::m_pData
0x180004bc0  jnz     short loc_180004BC9
0x180004bc2  mov     dword ptr [r14], 8007000Eh
0x180004bc9  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180004bd0  lea     rsi, [rdi+1E8h]
0x180004bd7  lea     rcx, [rsi+68h]; lpCriticalSection
0x180004bdb  mov     [rsi+8], rax
0x180004bdf  mov     [rsi+10h], r12
0x180004be3  mov     [rsi+18h], r12
0x180004be7  mov     [rsi+28h], r12d
0x180004beb  mov     [rsi+30h], r12
0x180004bef  mov     [rsi+38h], r12
0x180004bf3  mov     [rsi+40h], r12
0x180004bf7  mov     [rsi+48h], r12d
0x180004bfb  mov     [rsi+50h], r12
0x180004bff  mov     [rsi+58h], r12
0x180004c03  mov     [rsi+60h], r12w
0x180004c08  call    cs:__imp_InitializeCriticalSection
0x180004c0f  nop     dword ptr [rax+rax+00h]
0x180004c14  lea     rcx, [rsi+98h]; lpCriticalSection
0x180004c1b  mov     byte ptr [rsi+94h], 1
0x180004c22  call    cs:__imp_InitializeCriticalSection
0x180004c29  nop     dword ptr [rax+rax+00h]
0x180004c2e  lea     rax, ??_7CGraphWindow@CFGControl@@6B@; const CFGControl::CGraphWindow::`vftable'
0x180004c35  mov     [rsi+90h], r12d
0x180004c3c  mov     [rsi], rax
0x180004c3f  lea     rcx, [rdi+2C0h]
0x180004c46  mov     [rsi+0C0h], rdi
0x180004c4d  mov     [rsi+0C8h], r12d
0x180004c54  mov     rax, [rdi+8]
0x180004c58  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180004c5f  test    rax, rax
0x180004c62  cmovz   rax, rcx
0x180004c66  mov     [rcx+8], rax
0x180004c6a  lea     rax, ??_7CImplMediaControl@CFGControl@@6BIMediaControl@@@; const CFGControl::CImplMediaControl::`vftable'{for `IMediaControl'}
0x180004c71  mov     [rcx+10h], r12d
0x180004c75  mov     [rdi+2D8h], r12
0x180004c7c  mov     [rdi+2B8h], rax
0x180004c83  lea     rax, ??_7CImplMediaControl@CFGControl@@6BCUnknown@@@; const CFGControl::CImplMediaControl::`vftable'{for `CUnknown'}
0x180004c8a  mov     [rcx], rax
0x180004c8d  lea     rcx, [rdi+2F8h]
0x180004c94  mov     [rdi+2E0h], rdi
0x180004c9b  mov     rax, [rdi+8]
0x180004c9f  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180004ca6  test    rax, rax
0x180004ca9  cmovz   rax, rcx
0x180004cad  mov     [rcx+8], rax
0x180004cb1  lea     rax, ??_7CImplMediaEvent@@6BIMediaEventEx@@@; const CImplMediaEvent::`vftable'{for `IMediaEventEx'}
0x180004cb8  mov     [rcx+10h], r12d
0x180004cbc  mov     [rdi+310h], r12
0x180004cc3  mov     [rdi+2F0h], rax
0x180004cca  lea     rax, ??_7CImplMediaEvent@@6BCUnknown@@@; const CImplMediaEvent::`vftable'{for `CUnknown'}
0x180004cd1  mov     [rcx], rax
0x180004cd4  lea     rax, ??_7CImplMediaEvent@@6B@; const CImplMediaEvent::`vftable'
0x180004cdb  mov     [rdi+318h], rax
0x180004ce2  lea     rcx, [rdi+378h]; lpCriticalSection
0x180004ce9  mov     [rdi+320h], rdi
0x180004cf0  mov     [rdi+328h], r12
0x180004cf7  mov     [rdi+348h], r12d
0x180004cfe  mov     [rdi+350h], r12
0x180004d05  mov     [rdi+358h], r12
0x180004d0c  mov     [rdi+360h], r12d
0x180004d13  mov     qword ptr [rdi+368h], 0Ah
0x180004d1e  mov     [rdi+370h], r12
0x180004d25  call    cs:__imp_InitializeCriticalSection
0x180004d2c  nop     dword ptr [rax+rax+00h]
0x180004d31  xor     r9d, r9d; lpName
0x180004d34  xor     r8d, r8d; bInitialState
0x180004d37  mov     edx, 1; bManualReset
0x180004d3c  xor     ecx, ecx; lpEventAttributes
0x180004d3e  call    cs:__imp_CreateEventW
0x180004d45  nop     dword ptr [rax+rax+00h]
0x180004d4a  mov     [rdi+340h], rax
0x180004d51  lea     rcx, [rdi+3D0h]
0x180004d58  mov     [rdi+3A0h], r12
0x180004d5f  mov     rax, 2032001000h
0x180004d69  mov     [rdi+3A8h], rax
0x180004d70  mov     rax, 4001000F80022h
0x180004d7a  mov     [rdi+3B0h], rax
0x180004d81  mov     [rdi+3B8h], r12
0x180004d88  mov     [rdi+3C0h], r12d
0x180004d8f  mov     rax, [rdi+8]
0x180004d93  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180004d9a  test    rax, rax
0x180004d9d  cmovz   rax, rcx
0x180004da1  mov     [rcx+8], rax
0x180004da5  lea     rax, ??_7CImplMediaSeeking@CFGControl@@6BIMediaSeeking@@@; const CFGControl::CImplMediaSeeking::`vftable'{for `IMediaSeeking'}
0x180004dac  mov     [rcx+10h], r12d
0x180004db0  mov     [rdi+3C8h], rax
0x180004db7  lea     rax, ??_7CImplMediaSeeking@CFGControl@@6BCUnknown@@@; const CFGControl::CImplMediaSeeking::`vftable'{for `CUnknown'}
0x180004dbe  mov     [rcx], rax
0x180004dc1  mov     rax, 3FF0000000000000h
0x180004dcb  mov     [rdi+3E8h], rdi
0x180004dd2  lea     rcx, [rdi+378h]; lpCriticalSection
0x180004dd9  movups  xmm0, xmmword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x180004de0  mov     [rdi+408h], rax
0x180004de7  mov     rax, 7FFFFFFFFFFFFFFFh
0x180004df1  mov     [rdi+418h], rax
0x180004df8  movups  xmmword ptr [rdi+3F0h], xmm0
0x180004dff  mov     [rdi+400h], r12
0x180004e06  mov     [rdi+420h], r12
0x180004e0d  mov     [rdi+428h], r12
0x180004e14  mov     [rdi+448h], r12
0x180004e1b  mov     [rdi+410h], r12
0x180004e22  mov     [rdi+430h], r12b
0x180004e29  mov     [rdi+440h], r12
0x180004e30  call    cs:__imp_EnterCriticalSection
0x180004e37  nop     dword ptr [rax+rax+00h]
0x180004e3c  mov     r8, [rdi+350h]
0x180004e43  mov     [rsp+48h+arg_0], r8
0x180004e48  test    r8, r8
0x180004e4b  jz      short loc_180004E9F
0x180004e4d  mov     [rsp+48h+arg_8], rbp
0x180004e52  lea     rdx, [rsp+48h+arg_0]; struct __POSITION **
0x180004e57  call    ?GetNextI@CBaseList@@IEBAPEAXAEAPEAU__POSITION@@@Z; CBaseList::GetNextI(__POSITION * &)
0x180004e5c  mov     rbp, rax
0x180004e5f  cmp     dword ptr [rax], 1Ch
0x180004e62  jnz     short loc_180004E90
0x180004e64  mov     rdx, r8; struct __POSITION *
0x180004e67  lea     rcx, [rdi+350h]; this
0x180004e6e  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x180004e73  mov     r8, [rbp+10h]; __int64
0x180004e77  mov     rdx, [rbp+8]; __int64
0x180004e7b  mov     ecx, [rbp+0]; int
0x180004e7e  call    ?RealFreeEventParams@CImplMediaEvent@@SAJJ_J0@Z; CImplMediaEvent::RealFreeEventParams(long,__int64,__int64)
0x180004e83  mov     edx, 18h
0x180004e88  mov     rcx, rbp; Block
0x180004e8b  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180004e90  mov     r8, [rsp+48h+arg_0]
0x180004e95  test    r8, r8
0x180004e98  jnz     short loc_180004E52
0x180004e9a  mov     rbp, [rsp+48h+arg_8]
0x180004e9f  lea     rcx, [rdi+378h]; lpCriticalSection
0x180004ea6  call    cs:__imp_LeaveCriticalSection
0x180004ead  nop     dword ptr [rax+rax+00h]
0x180004eb2  mov     rax, [rdi+8]
0x180004eb6  lea     rcx, [rdi+458h]
0x180004ebd  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180004ec4  test    rax, rax
0x180004ec7  cmovz   rax, rcx
0x180004ecb  mov     [rcx+8], rax
0x180004ecf  lea     rax, ??_7CImplMediaPosition@CFGControl@@6BIMediaPosition@@@; const CFGControl::CImplMediaPosition::`vftable'{for `IMediaPosition'}
0x180004ed6  mov     [rcx+10h], r12d
0x180004eda  mov     [rdi+470h], r12
0x180004ee1  mov     [rdi+450h], rax
0x180004ee8  lea     rax, ??_7CImplMediaPosition@CFGControl@@6BCUnknown@@@; const CFGControl::CImplMediaPosition::`vftable'{for `CUnknown'}
0x180004eef  mov     [rcx], rax
0x180004ef2  lea     rcx, [rdi+488h]
0x180004ef9  mov     [rdi+478h], rdi
0x180004f00  mov     rax, [rdi+8]
0x180004f04  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180004f0b  test    rax, rax
0x180004f0e  cmovz   rax, rcx
0x180004f12  mov     [rcx+8], rax
0x180004f16  lea     rax, ??_7CImplVideoWindow@CFGControl@@6BIVideoWindow@@@; const CFGControl::CImplVideoWindow::`vftable'{for `IVideoWindow'}
0x180004f1d  mov     [rcx+10h], r12d
0x180004f21  mov     [rdi+4A0h], r12
0x180004f28  mov     [rdi+480h], rax
0x180004f2f  lea     rax, ??_7CImplVideoWindow@CFGControl@@6BCUnknown@@@; const CFGControl::CImplVideoWindow::`vftable'{for `CUnknown'}
0x180004f36  mov     [rcx], rax
0x180004f39  lea     rcx, [rdi+570h]
0x180004f40  mov     [rdi+4A8h], rdi
0x180004f47  mov     [rdi+4B0h], r12
0x180004f4e  mov     [rdi+4B8h], r12
0x180004f55  mov     [rdi+4C0h], r12d
0x180004f5c  mov     [rdi+4C8h], r12
0x180004f63  mov     [rdi+4D0h], r12
0x180004f6a  mov     [rdi+4D8h], r12
0x180004f71  mov     [rdi+4E0h], r12
0x180004f78  mov     [rdi+4E8h], r12
0x180004f7f  mov     [rdi+4F0h], r12
0x180004f86  mov     [rdi+4F8h], r12
0x180004f8d  mov     rax, [rdi+8]
0x180004f91  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180004f98  test    rax, rax
0x180004f9b  cmovz   rax, rcx
0x180004f9f  mov     [rcx+8], rax
0x180004fa3  lea     rax, ??_7CImplBasicVideo@CFGControl@@6BIBasicVideo2@@@; const CFGControl::CImplBasicVideo::`vftable'{for `IBasicVideo2'}
0x180004faa  mov     [rcx+10h], r12d
0x180004fae  mov     [rdi+588h], r12
0x180004fb5  mov     [rdi+568h], rax
0x180004fbc  lea     rax, ??_7CImplBasicVideo@CFGControl@@6BCUnknown@@@; const CFGControl::CImplBasicVideo::`vftable'{for `CUnknown'}
0x180004fc3  mov     [rcx], rax
0x180004fc6  lea     rcx, [rdi+5A0h]
0x180004fcd  mov     [rdi+590h], rdi
0x180004fd4  mov     rax, [rdi+8]
0x180004fd8  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180004fdf  test    rax, rax
0x180004fe2  cmovz   rax, rcx
0x180004fe6  mov     [rcx+8], rax
0x180004fea  lea     rax, ??_7CImplBasicAudio@CFGControl@@6BIBasicAudio@@@; const CFGControl::CImplBasicAudio::`vftable'{for `IBasicAudio'}
0x180004ff1  mov     [rcx+10h], r12d
0x180004ff5  mov     [rdi+5B8h], r12
0x180004ffc  mov     [rdi+598h], rax
0x180005003  lea     rax, ??_7CImplBasicAudio@CFGControl@@6BCUnknown@@@; const CFGControl::CImplBasicAudio::`vftable'{for `CUnknown'}
0x18000500a  mov     [rcx], rax
0x18000500d  lea     rcx, [rdi+5C8h]
0x180005014  mov     [rdi+5C0h], rdi
0x18000501b  mov     rax, [rdi+8]
0x18000501f  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180005026  test    rax, rax
0x180005029  mov     [rcx+20h], rdi
0x18000502d  lea     rbx, [rdi+5F8h]
0x180005034  cmovz   rax, rcx
0x180005038  mov     [rcx+8], rax
0x18000503c  lea     rax, ??_7CImplMediaFilter@CFGControl@@6BCUnknown@@@; const CFGControl::CImplMediaFilter::`vftable'{for `CUnknown'}
0x180005043  mov     [rcx], rax
0x180005046  lea     rax, ??_7CImplMediaFilter@CFGControl@@6BIMediaFilter@@@; const CFGControl::CImplMediaFilter::`vftable'{for `IMediaFilter'}
0x18000504d  mov     [rcx+18h], rax
0x180005051  mov     [rcx+10h], r12d
0x180005055  mov     rax, [rdi+8]
0x180005059  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180005060  test    rax, rax
0x180005063  lea     rcx, [rdi+618h]; lpCriticalSection
0x18000506a  cmovz   rax, rbx
0x18000506e  mov     [rbx+8], rax
  ... truncated ...
```
