# CRdpWindowTracker::InitializeInstance(IRdpWindowTrackerEventSink *)

- ea: `0x14005d874`
- end: `0x14005dc37`
- name: `?InitializeInstance@CRdpWindowTracker@@AEAAJPEAVIRdpWindowTrackerEventSink@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(CRdpWindowTracker *__hidden this, struct IRdpWindowTrackerEventSink *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14005bdcc`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x14000ea3c`
- `0x140011054`
- `0x14005b400`
- `0x14005d874`
- `0x14005e17c`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dbc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005dbc0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14005dba1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14005dba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005d949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005d949`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14005daa5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14005daa5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005db19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005db19`
- `GDI32!CreateRectRgn` at `0x14005d9e7`
- `GDI32!CreateRectRgn` at `0x14005d9e7`

## string_xrefs

- `0x14005d97f`: `"CoTaskMemAlloc( RGNDATA )"`
- `0x14005da3b`: `CreateRectRgn() failed`
- `0x14005db49`: `CoCreateInstance (CLSID_VirtualDesktopManager) failed - Not fatal, only necessary to detect Virtaul Desktop changes`
- `0x14005dbfb`: `CreateThread() failed`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::InitializeInstance(
        CRdpWindowTracker *this,
        struct IRdpWindowTrackerEventSink *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // ebx
  unsigned int v6; // eax
  void *v7; // rax
  unsigned int v8; // eax
  HRGN RectRgn; // rax
  unsigned int v10; // eax
  CRdpWindowTracker *v11; // rcx
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  HRESULT Instance; // ebx
  unsigned int v16; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  LPDWORD lpThreadId; // [rsp+28h] [rbp-10h]

  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pCallback");
    }
    return (unsigned int)-2147467261;
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRdpWindowTracker *)((char *)this + 56)) )
  {
    v5 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v6,
        (__int64)"m_csLock.Initialize() failed",
        -2147467259);
    }
    return (unsigned int)v5;
  }
  v7 = CoTaskMemAlloc(0x424u);
  *((_QWORD *)this + 35) = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v8,
        (__int64)"\"CoTaskMemAlloc( RGNDATA )\"");
    }
    return (unsigned int)-2147024882;
  }
  memset_0(v7, 0, 0x424u);
  if ( a2 != *((struct IRdpWindowTrackerEventSink **)this + 9) )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 72);
    *((_QWORD *)this + 9) = a2;
    TCntPtr<IRdrVirtualChannel>::SafeAddRef((char *)this + 72);
  }
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  *((_QWORD *)this + 16) = RectRgn;
  if ( !RectRgn )
  {
    v5 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v10,
        (__int64)"CreateRectRgn() failed",
        -2147467259);
    }
    return (unsigned int)v5;
  }
  v5 = CRdpWindowTracker::BuildMonitorClipRegion(this);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v5;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 21;
    v14 = "BuildMonitorClipRegion() failed";
    goto LABEL_50;
  }
  *((_DWORD *)this + 60) = CRdpWindowTracker::IsDefaultDesktopInteractive(v11);
  v5 = CoInitializeEx(0, 0);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v5;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 22;
    v14 = "CoInitializeEx() failed";
LABEL_50:
    LODWORD(lpThreadId) = v5;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
      v12,
      (__int64)v14,
      lpThreadId);
    return (unsigned int)v5;
  }
  if ( !v5 )
    *((_DWORD *)this + 22) = 1;
  Instance = CoCreateInstance(&CLSID_VirtualDesktopManager, 0, 1u, &IID_IVirtualDesktopManager, (LPVOID *)this + 10);
  if ( Instance < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
      v16,
      (__int64)"CoCreateInstance (CLSID_VirtualDesktopManager) failed - Not fatal, only necessary to detect Virtaul Desktop changes",
      Instance);
  }
  v5 = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
  Thread = CreateThread(0, 0, CRdpWindowTracker::STATIC_WorkerThreadProc, this, 0, 0);
  *((_QWORD *)this + 13) = Thread;
  if ( !Thread )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 24;
      v14 = "CreateThread() failed";
      goto LABEL_50;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14005d874  mov     [rsp+arg_0], rbx
0x14005d879  mov     [rsp+arg_8], rsi
0x14005d87e  push    rdi
0x14005d87f  sub     rsp, 30h
0x14005d883  mov     rdi, rdx
0x14005d886  mov     rsi, rcx
0x14005d889  test    rdx, rdx
0x14005d88c  jnz     short loc_14005D8E7
0x14005d88e  mov     rax, cs:WPP_GLOBAL_Control
0x14005d895  lea     rdi, WPP_GLOBAL_Control
0x14005d89c  cmp     rax, rdi
0x14005d89f  jz      short loc_14005D8DD
0x14005d8a1  test    byte ptr [rax+1Ch], 8
0x14005d8a5  jz      short loc_14005D8DD
0x14005d8a7  cmp     byte ptr [rax+19h], 2
0x14005d8ab  jb      short loc_14005D8DD
0x14005d8ad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005d8b2  lea     rcx, aPcallback; "pCallback"
0x14005d8b9  mov     edx, 11h
0x14005d8be  mov     [rsp+38h+ppv], rcx
0x14005d8c3  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005d8ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d8d1  mov     r9d, eax
0x14005d8d4  mov     rcx, [rcx+10h]
0x14005d8d8  call    WPP_SF_Ds
0x14005d8dd  mov     ebx, 80004003h
0x14005d8e2  jmp     loc_14005DC25
0x14005d8e7  add     rcx, 38h ; '8'; this
0x14005d8eb  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x14005d8f0  test    eax, eax
0x14005d8f2  jnz     short loc_14005D942
0x14005d8f4  mov     ebx, 80004005h
0x14005d8f9  mov     rax, cs:WPP_GLOBAL_Control
0x14005d900  lea     rdi, WPP_GLOBAL_Control
0x14005d907  cmp     rax, rdi
0x14005d90a  jz      loc_14005DC25
0x14005d910  test    byte ptr [rax+1Ch], 8
0x14005d914  jz      loc_14005DC25
0x14005d91a  cmp     byte ptr [rax+19h], 2
0x14005d91e  jb      loc_14005DC25
0x14005d924  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005d929  mov     edx, 12h
0x14005d92e  mov     dword ptr [rsp+38h+lpThreadId], 80004005h
0x14005d936  lea     rcx, aMCslockInitial; "m_csLock.Initialize() failed"
0x14005d93d  jmp     loc_14005DC06
0x14005d942  mov     ebx, 424h
0x14005d947  mov     ecx, ebx; cb
0x14005d949  call    cs:__imp_CoTaskMemAlloc
0x14005d94f  mov     [rsi+118h], rax
0x14005d956  test    rax, rax
0x14005d959  jnz     short loc_14005D9B4
0x14005d95b  mov     rax, cs:WPP_GLOBAL_Control
0x14005d962  lea     rdi, WPP_GLOBAL_Control
0x14005d969  cmp     rax, rdi
0x14005d96c  jz      short loc_14005D9AA
0x14005d96e  test    byte ptr [rax+1Ch], 8
0x14005d972  jz      short loc_14005D9AA
0x14005d974  cmp     byte ptr [rax+19h], 2
0x14005d978  jb      short loc_14005D9AA
0x14005d97a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005d97f  lea     rcx, aCotaskmemalloc; "\"CoTaskMemAlloc( RGNDATA )\""
0x14005d986  mov     edx, 13h
0x14005d98b  mov     [rsp+38h+ppv], rcx
0x14005d990  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005d997  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d99e  mov     r9d, eax
0x14005d9a1  mov     rcx, [rcx+10h]
0x14005d9a5  call    WPP_SF_Ds
0x14005d9aa  mov     ebx, 8007000Eh
0x14005d9af  jmp     loc_14005DC25
0x14005d9b4  mov     r8, rbx; Size
0x14005d9b7  xor     edx, edx; Val
0x14005d9b9  mov     rcx, rax; void *
0x14005d9bc  call    memset_0
0x14005d9c1  lea     rbx, [rsi+48h]
0x14005d9c5  cmp     rdi, [rbx]
0x14005d9c8  jz      short loc_14005D9DD
0x14005d9ca  mov     rcx, rbx
0x14005d9cd  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005d9d2  mov     rcx, rbx
0x14005d9d5  mov     [rbx], rdi
0x14005d9d8  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14005d9dd  xor     r9d, r9d; y2
0x14005d9e0  xor     r8d, r8d; x2
0x14005d9e3  xor     edx, edx; y1
0x14005d9e5  xor     ecx, ecx; x1
0x14005d9e7  call    cs:__imp_CreateRectRgn
0x14005d9ed  mov     [rsi+80h], rax
0x14005d9f4  test    rax, rax
0x14005d9f7  jnz     short loc_14005DA47
0x14005d9f9  mov     ebx, 80004005h
0x14005d9fe  mov     rax, cs:WPP_GLOBAL_Control
0x14005da05  lea     rdi, WPP_GLOBAL_Control
0x14005da0c  cmp     rax, rdi
0x14005da0f  jz      loc_14005DC25
0x14005da15  test    byte ptr [rax+1Ch], 8
0x14005da19  jz      loc_14005DC25
0x14005da1f  cmp     byte ptr [rax+19h], 2
0x14005da23  jb      loc_14005DC25
0x14005da29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005da2e  mov     edx, 14h
0x14005da33  mov     dword ptr [rsp+38h+lpThreadId], 80004005h
0x14005da3b  lea     rcx, aCreaterectrgnF; "CreateRectRgn() failed"
0x14005da42  jmp     loc_14005DC06
0x14005da47  mov     rcx, rsi; this
0x14005da4a  call    ?BuildMonitorClipRegion@CRdpWindowTracker@@AEAAJXZ; CRdpWindowTracker::BuildMonitorClipRegion(void)
0x14005da4f  mov     ebx, eax
0x14005da51  test    eax, eax
0x14005da53  jns     short loc_14005DA96
0x14005da55  mov     rax, cs:WPP_GLOBAL_Control
0x14005da5c  lea     rdi, WPP_GLOBAL_Control
0x14005da63  cmp     rax, rdi
0x14005da66  jz      loc_14005DC25
0x14005da6c  test    byte ptr [rax+1Ch], 8
0x14005da70  jz      loc_14005DC25
0x14005da76  cmp     byte ptr [rax+19h], 2
0x14005da7a  jb      loc_14005DC25
0x14005da80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005da85  mov     edx, 15h
0x14005da8a  lea     rcx, aBuildmonitorcl; "BuildMonitorClipRegion() failed"
0x14005da91  jmp     loc_14005DC02
0x14005da96  call    ?IsDefaultDesktopInteractive@CRdpWindowTracker@@AEAAHXZ; CRdpWindowTracker::IsDefaultDesktopInteractive(void)
0x14005da9b  xor     edx, edx; dwCoInit
0x14005da9d  mov     [rsi+0F0h], eax
0x14005daa3  xor     ecx, ecx; pvReserved
0x14005daa5  call    cs:__imp_CoInitializeEx
0x14005daab  mov     ebx, eax
0x14005daad  test    eax, eax
0x14005daaf  jns     short loc_14005DAF2
0x14005dab1  mov     rax, cs:WPP_GLOBAL_Control
0x14005dab8  lea     rdi, WPP_GLOBAL_Control
0x14005dabf  cmp     rax, rdi
0x14005dac2  jz      loc_14005DC25
0x14005dac8  test    byte ptr [rax+1Ch], 8
0x14005dacc  jz      loc_14005DC25
0x14005dad2  cmp     byte ptr [rax+19h], 2
0x14005dad6  jb      loc_14005DC25
0x14005dadc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005dae1  mov     edx, 16h
0x14005dae6  lea     rcx, aCoinitializeex; "CoInitializeEx() failed"
0x14005daed  jmp     loc_14005DC02
0x14005daf2  mov     r8d, 1; dwClsContext
0x14005daf8  test    ebx, ebx
0x14005dafa  jnz     short loc_14005DB00
0x14005dafc  mov     [rsi+58h], r8d
0x14005db00  lea     rax, [rsi+50h]
0x14005db04  xor     edx, edx; pUnkOuter
0x14005db06  lea     r9, IID_IVirtualDesktopManager; riid
0x14005db0d  mov     [rsp+38h+ppv], rax; ppv
0x14005db12  lea     rcx, CLSID_VirtualDesktopManager; rclsid
0x14005db19  call    cs:__imp_CoCreateInstance
0x14005db1f  lea     rdi, WPP_GLOBAL_Control
0x14005db26  mov     ebx, eax
0x14005db28  test    eax, eax
0x14005db2a  jns     short loc_14005DB78
0x14005db2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005db33  cmp     rcx, rdi
0x14005db36  jz      short loc_14005DB78
0x14005db38  test    byte ptr [rcx+1Ch], 8
0x14005db3c  jz      short loc_14005DB78
0x14005db3e  cmp     byte ptr [rcx+19h], 2
0x14005db42  jb      short loc_14005DB78
0x14005db44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005db49  lea     rcx, aCocreateinstan_0; "CoCreateInstance (CLSID_VirtualDesktopM"...
0x14005db50  mov     dword ptr [rsp+38h+lpThreadId], ebx
0x14005db54  mov     [rsp+38h+ppv], rcx
0x14005db59  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005db60  mov     rcx, cs:WPP_GLOBAL_Control
0x14005db67  mov     edx, 17h
0x14005db6c  mov     r9d, eax
0x14005db6f  mov     rcx, [rcx+10h]
0x14005db73  call    WPP_SF_DsD
0x14005db78  mov     rcx, [rsi+20h]
0x14005db7c  xor     ebx, ebx
0x14005db7e  mov     rax, [rcx]
0x14005db81  mov     rax, [rax+8]
0x14005db85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005db8a  mov     r9, rsi; lpParameter
0x14005db8d  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x14005db92  lea     r8, ?STATIC_WorkerThreadProc@CRdpWindowTracker@@CAKPEAX@Z; lpStartAddress
0x14005db99  mov     dword ptr [rsp+38h+ppv], ebx; dwCreationFlags
0x14005db9d  xor     edx, edx; dwStackSize
0x14005db9f  xor     ecx, ecx; lpThreadAttributes
0x14005dba1  call    cs:__imp_CreateThread
0x14005dba7  mov     [rsi+68h], rax
0x14005dbab  test    rax, rax
0x14005dbae  jnz     short loc_14005DC25
0x14005dbb0  mov     rcx, [rsi+20h]
0x14005dbb4  mov     rax, [rcx]
0x14005dbb7  mov     rax, [rax+10h]
0x14005dbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005dbc0  call    cs:__imp_GetLastError
0x14005dbc6  mov     ebx, eax
0x14005dbc8  test    eax, eax
0x14005dbca  jle     short loc_14005DBD5
0x14005dbcc  movzx   ebx, ax
0x14005dbcf  or      ebx, 80070000h
0x14005dbd5  test    ebx, ebx
0x14005dbd7  jns     short loc_14005DC25
0x14005dbd9  mov     rax, cs:WPP_GLOBAL_Control
0x14005dbe0  cmp     rax, rdi
0x14005dbe3  jz      short loc_14005DC25
0x14005dbe5  test    byte ptr [rax+1Ch], 8
0x14005dbe9  jz      short loc_14005DC25
0x14005dbeb  cmp     byte ptr [rax+19h], 2
0x14005dbef  jb      short loc_14005DC25
0x14005dbf1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005dbf6  mov     edx, 18h
0x14005dbfb  lea     rcx, aCreatethreadFa_0; "CreateThread() failed"
0x14005dc02  mov     dword ptr [rsp+38h+lpThreadId], ebx
0x14005dc06  mov     [rsp+38h+ppv], rcx
0x14005dc0b  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005dc12  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dc19  mov     r9d, eax
0x14005dc1c  mov     rcx, [rcx+10h]
0x14005dc20  call    WPP_SF_DsD
0x14005dc25  mov     rsi, [rsp+38h+arg_8]
0x14005dc2a  mov     eax, ebx
0x14005dc2c  mov     rbx, [rsp+38h+arg_0]
0x14005dc31  add     rsp, 30h
0x14005dc35  pop     rdi
0x14005dc36  retn
```
