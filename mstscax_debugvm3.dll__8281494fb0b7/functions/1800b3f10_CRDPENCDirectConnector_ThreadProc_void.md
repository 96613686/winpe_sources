# CRDPENCDirectConnector::ThreadProc(void)

- ea: `0x1800b3f10`
- end: `0x1800b4721`
- name: `?ThreadProc@CRDPENCDirectConnector@@IEAAXXZ`
- size: `2065`
- prototype: `void __fastcall(CRDPENCDirectConnector *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180360ab0`

## callees

- `0x1800011f4`
- `0x1800186a0`
- `0x1800186d0`
- `0x180039c98`
- `0x180039ce4`
- `0x1800829d4`
- `0x1800b3f10`
- `0x1800e9b1c`
- `0x1800f489c`
- `0x18010215c`
- `0x18012962c`
- `0x18035f9a0`
- `0x18035fd4c`
- `0x180360228`
- `0x1803604a8`
- `0x18036faa0`
- `0x180370090`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800b45aa`
- `KERNEL32!CloseHandle` at `0x1800b45aa`
- `KERNEL32!GetLastError` at `0x1800b3fcb`
- `KERNEL32!GetLastError` at `0x1800b4268`
- `KERNEL32!GetLastError` at `0x1800b42c5`
- `KERNEL32!GetLastError` at `0x1800b4374`
- `KERNEL32!GetLastError` at `0x1800b3fcb`
- `KERNEL32!GetLastError` at `0x1800b4268`
- `KERNEL32!GetLastError` at `0x1800b42c5`
- `KERNEL32!GetLastError` at `0x1800b4374`
- `KERNEL32!CreateEventW` at `0x1800b3fb9`
- `KERNEL32!CreateEventW` at `0x1800b4256`
- `KERNEL32!CreateEventW` at `0x1800b3fb9`
- `KERNEL32!CreateEventW` at `0x1800b4256`
- `KERNEL32!SetWaitableTimer` at `0x1800b436a`
- `KERNEL32!SetWaitableTimer` at `0x1800b436a`
- `KERNEL32!CancelWaitableTimer` at `0x1800b43f6`
- `KERNEL32!CancelWaitableTimer` at `0x1800b43f6`
- `KERNEL32!CreateWaitableTimerExW` at `0x1800b42b7`
- `KERNEL32!CreateWaitableTimerExW` at `0x1800b42b7`
- `ADVAPI32!EventActivityIdControl` at `0x1800b3f6c`
- `ADVAPI32!EventActivityIdControl` at `0x1800b45eb`
- `ADVAPI32!EventActivityIdControl` at `0x1800b3f6c`
- `ADVAPI32!EventActivityIdControl` at `0x1800b45eb`

## string_xrefs

- `0x1800b4101`: `ThreadProc`
- `0x1800b43dc`: `ThreadProc`
- `0x1800b4696`: `Failed to complete the connection`
- `0x1800b4570`: `Failed to create a new connection`

## pseudocode

```c
void __fastcall CRDPENCDirectConnector::ThreadProc(CRDPENCDirectConnector *this)
{
  GUID v2; // xmm0
  HANDLE WaitableTimer; // r13
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rdi
  HANDLE EventW; // rax
  signed int LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // edx
  const char *v13; // rcx
  unsigned int started; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // edi
  char *v19; // rax
  char *v20; // rsi
  char *v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // r15d
  __int64 v26; // rcx
  HANDLE v27; // rax
  int v28; // r8d
  int v29; // r9d
  LONG v30; // r8d
  unsigned int v31; // edx
  __int64 v32; // rcx
  int v33; // eax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  int v37; // [rsp+50h] [rbp-59h] BYREF
  int v38; // [rsp+54h] [rbp-55h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-51h]
  const char *v40; // [rsp+60h] [rbp-49h] BYREF
  __int64 v41; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int64 v42; // [rsp+70h] [rbp-39h] BYREF
  const char *v43; // [rsp+78h] [rbp-31h] BYREF
  LARGE_INTEGER DueTime; // [rsp+80h] [rbp-29h] BYREF
  const char *v45; // [rsp+88h] [rbp-21h] BYREF
  __int128 v46; // [rsp+90h] [rbp-19h] BYREF
  GUID ActivityId; // [rsp+A0h] [rbp-9h] BYREF

  v39 = 0;
  v46 = 0;
  v2 = *(GUID *)((char *)this + 244);
  DueTime.QuadPart = 0;
  WaitableTimer = 0;
  v42 = -1;
  ActivityId = v2;
  EventActivityIdControl(4u, &ActivityId);
  v4 = *((_QWORD *)this + 27);
  v5 = 0;
  v41 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
  if ( v6 )
  {
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v41);
    v5 = v6;
    v41 = v6;
    TCntPtr<IPin>::SafeAddRef(&v41);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 37) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 29;
LABEL_8:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
LABEL_9:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_83;
  }
  LastError = CRDPENCDirectConnector::AsyncResolveServerName(this);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 30;
    v13 = "Failed to resolve server name asynchronously";
    goto LABEL_82;
  }
  LastError = CRDPENCONResolver::SortAddresses((CRDPENCDirectConnector *)((char *)this + 56));
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 31;
    v13 = "Failed to sort the address list";
    goto LABEL_82;
  }
  started = CRDPENCONResolver::StartEnum((CRDPENCDirectConnector *)((char *)this + 56));
  v18 = started;
  if ( started )
  {
    v19 = (char *)operator new(saturated_mul(started, 8u));
    v20 = (char *)this + 304;
    v21 = v19;
    *((_QWORD *)this + 38) = v19;
    if ( v19 )
    {
      if ( v18 )
      {
        v23 = 0;
        if ( v18 < 2 || v19 <= v20 && &v19[8 * v18 - 8] >= v20 )
          goto LABEL_109;
        v24 = v18 & 0xFFFFFFFE;
        do
        {
          v23 += 2;
          v25 = v23;
        }
        while ( v23 < v24 );
        memset_0(v21, -1, 16 * ((unsigned __int64)v24 >> 1));
        v23 = v25;
        if ( v25 < v18 )
        {
LABEL_109:
          do
          {
            v26 = v23++;
            *(_QWORD *)(*(_QWORD *)v20 + 8 * v26) = -1;
          }
          while ( v23 < v18 );
        }
      }
      *((_DWORD *)this + 78) = v18;
      *((_DWORD *)this + 79) = 0;
      v27 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 36) = v27;
      if ( !v27 )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 33;
        goto LABEL_8;
      }
      WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
      if ( !WaitableTimer )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 34;
        goto LABEL_8;
      }
      if ( (unsigned int)dword_1808B5850 > 5 )
      {
        v37 = *((_DWORD *)this + 65);
        v40 = "Trying to connection using Conn Q Interval: %d";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1808B5850,
          (unsigned int)&dword_18086CBE4,
          v28,
          v29,
          (__int64)&v40,
          (__int64)&v37);
      }
      v30 = *((_DWORD *)this + 65);
      DueTime.QuadPart = 0;
      if ( !SetWaitableTimer(WaitableTimer, &DueTime, v30, 0, 0, 0) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 35;
        goto LABEL_8;
      }
      *((_QWORD *)&v46 + 1) = *((_QWORD *)this + 36);
      *(_QWORD *)&v46 = WaitableTimer;
      LastError = CRDPENCDirectConnector::CreatePendingConnection(this);
      if ( LastError < 0 )
      {
LABEL_78:
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_83;
        }
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 36;
        v13 = "Failed to create a new connection";
LABEL_82:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          (unsigned int)WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
          v11,
          (__int64)v13,
          LastError);
        goto LABEL_83;
      }
      while ( 1 )
      {
        if ( LastError == 1 )
        {
          CancelWaitableTimer(WaitableTimer);
          v31 = *((_DWORD *)this + 79);
          if ( !v31 )
          {
LABEL_65:
            LastError = CRDPENCDirectConnector::FireConnectionCompleted(this, 0xFFFFFFFFFFFFFFFFuLL);
            if ( LastError < 0
              && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v11 = RdpWppGetCurrentThreadActivityIdPrefix();
              v12 = 37;
LABEL_70:
              v13 = "Failed to fire the event";
              goto LABEL_82;
            }
            goto LABEL_83;
          }
          v32 = 0;
          while ( *(_QWORD *)(*((_QWORD *)this + 38) + 8 * v32) == -1 )
          {
            v32 = (unsigned int)(v32 + 1);
            if ( (unsigned int)v32 >= v31 )
              goto LABEL_65;
          }
        }
        LastError = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v5 + 80LL))(v5, 2, &v46);
        if ( LastError < 0 )
          break;
        if ( v39 > 1 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids);
          }
          LastError = -2147418113;
          goto LABEL_83;
        }
        v33 = CRDPENCDirectConnector::CompletePendingConnection(this, &v42);
        LastError = v33;
        if ( v33 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = RdpWppGetCurrentThreadActivityIdPrefix();
            v12 = 39;
            v13 = "Failed to complete the connection";
            goto LABEL_82;
          }
          goto LABEL_83;
        }
        if ( !v33 )
        {
          LastError = CRDPENCDirectConnector::FireConnectionCompleted(this, v42);
          if ( LastError < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = RdpWppGetCurrentThreadActivityIdPrefix();
            v12 = 40;
            goto LABEL_70;
          }
          goto LABEL_83;
        }
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v40 = "ThreadProc";
          v45 = "Trying the next connector";
          v37 = 623;
          v43 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
          v38 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v34,
            (unsigned int)&dword_18086CB4C,
            v35,
            v36,
            (__int64)&v45,
            (__int64)&v38,
            (__int64)&v43,
            (__int64)&v37,
            (__int64)&v40);
        }
        LastError = CRDPENCDirectConnector::CreatePendingConnection(this);
        if ( LastError < 0 )
          goto LABEL_78;
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 38;
        v13 = "Wait failed";
        goto LABEL_82;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
          v22,
          -2147024882);
      }
      LastError = -2147024882;
    }
  }
  else
  {
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v38 = 523;
      v40 = "Failed to resolve any IPS";
      v42 = (unsigned __int64)"ThreadProc";
      v43 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
      v37 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)qword_18086CC18,
        v16,
        v17,
        (__int64)&v40,
        (__int64)&v37,
        (__int64)&v43,
        (__int64)&v38,
        (__int64)&v42);
    }
    LastError = -2092621306;
  }
LABEL_83:
  CRDPENCDirectConnector::ClearPendingConnections(this);
  if ( WaitableTimer )
    CloseHandle(WaitableTimer);
  if ( (int)(LastError + 0x80000000) >= 0 && LastError != -2092629996 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 29) + 32LL))(
      *((_QWORD *)this + 29),
      (unsigned int)LastError);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v41);
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x1800b3f10  push    rbp
0x1800b3f12  push    rbx
0x1800b3f13  push    rsi
0x1800b3f14  push    rdi
0x1800b3f15  push    r12
0x1800b3f17  push    r13
0x1800b3f19  push    r14
0x1800b3f1b  push    r15
0x1800b3f1d  lea     rbp, [rsp-1Fh]
0x1800b3f22  sub     rsp, 0C8h
0x1800b3f29  mov     rax, cs:__security_cookie
0x1800b3f30  xor     rax, rsp
0x1800b3f33  mov     [rbp+57h+var_50], rax
0x1800b3f37  xor     r12d, r12d
0x1800b3f3a  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800b3f3e  xorps   xmm0, xmm0
0x1800b3f41  mov     [rbp+57h+var_A8], r12d
0x1800b3f45  movups  [rbp+57h+var_70], xmm0
0x1800b3f49  mov     r14, rcx
0x1800b3f4c  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800b3f50  movups  xmm0, xmmword ptr [rcx+0F4h]
0x1800b3f57  lea     ecx, [r12+4]; ControlCode
0x1800b3f5c  mov     qword ptr [rbp+57h+DueTime], r12
0x1800b3f60  mov     r13d, r12d
0x1800b3f63  mov     [rbp+57h+var_90], r15
0x1800b3f67  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1800b3f6c  call    cs:__imp_EventActivityIdControl
0x1800b3f72  mov     rcx, [r14+0D8h]
0x1800b3f79  mov     ebx, r12d
0x1800b3f7c  mov     [rbp+57h+var_98], rbx
0x1800b3f80  mov     rax, [rcx]
0x1800b3f83  mov     rax, [rax+40h]
0x1800b3f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3f8c  mov     rdi, rax
0x1800b3f8f  test    rax, rax
0x1800b3f92  jz      short loc_1800B3FAD
0x1800b3f94  lea     rcx, [rbp+57h+var_98]; void *
0x1800b3f98  call    ?SafeRelease@?$TCntPtr@VITSViewerRecorder@@@@AEAAXXZ; TCntPtr<ITSViewerRecorder>::SafeRelease(void)
0x1800b3f9d  mov     rbx, rdi
0x1800b3fa0  lea     rcx, [rbp+57h+var_98]
0x1800b3fa4  mov     [rbp+57h+var_98], rbx
0x1800b3fa8  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ; TCntPtr<IPin>::SafeAddRef(void)
0x1800b3fad  xor     r9d, r9d; lpName
0x1800b3fb0  xor     r8d, r8d; bInitialState
0x1800b3fb3  xor     ecx, ecx; lpEventAttributes
0x1800b3fb5  lea     edx, [r9+1]; bManualReset
0x1800b3fb9  call    cs:__imp_CreateEventW
0x1800b3fbf  mov     [r14+128h], rax
0x1800b3fc6  test    rax, rax
0x1800b3fc9  jnz     short loc_1800B4036
0x1800b3fcb  call    cs:__imp_GetLastError
0x1800b3fd1  mov     edi, eax
0x1800b3fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3fda  lea     rax, WPP_GLOBAL_Control
0x1800b3fe1  cmp     rcx, rax
0x1800b3fe4  jz      short loc_1800B401A
0x1800b3fe6  test    byte ptr [rcx+1Ch], 8
0x1800b3fea  jz      short loc_1800B401A
0x1800b3fec  cmp     byte ptr [rcx+19h], 2
0x1800b3ff0  jb      short loc_1800B401A
0x1800b3ff2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b3ff7  mov     edx, 1Dh
0x1800b3ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4003  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1800b400a  mov     r9d, eax
0x1800b400d  mov     dword ptr [rsp+100h+lpArgToCompletionRoutine], edi
0x1800b4011  mov     rcx, [rcx+10h]
0x1800b4015  call    WPP_SF_Dd
0x1800b401a  test    edi, edi
0x1800b401c  jle     short loc_1800B4027
0x1800b401e  movzx   edi, di
0x1800b4021  or      edi, 80070000h
0x1800b4027  test    edi, edi
0x1800b4029  mov     esi, 80004005h
0x1800b402e  cmovns  edi, esi
0x1800b4031  jmp     loc_1800B459A
0x1800b4036  mov     rcx, r14; this
0x1800b4039  call    ?AsyncResolveServerName@CRDPENCDirectConnector@@IEAAJXZ; CRDPENCDirectConnector::AsyncResolveServerName(void)
0x1800b403e  mov     edi, eax
0x1800b4040  test    eax, eax
0x1800b4042  jns     short loc_1800B4085
0x1800b4044  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b404b  lea     rax, WPP_GLOBAL_Control
0x1800b4052  cmp     rcx, rax
0x1800b4055  jz      loc_1800B459A
0x1800b405b  test    byte ptr [rcx+1Ch], 8
0x1800b405f  jz      loc_1800B459A
0x1800b4065  cmp     byte ptr [rcx+19h], 2
0x1800b4069  jb      loc_1800B459A
0x1800b406f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b4074  mov     edx, 1Eh
0x1800b4079  lea     rcx, aFailedToResolv; "Failed to resolve server name asynchron"...
0x1800b4080  jmp     loc_1800B4577
0x1800b4085  lea     rcx, [r14+38h]; this
0x1800b4089  call    ?SortAddresses@CRDPENCONResolver@@QEAAJXZ; CRDPENCONResolver::SortAddresses(void)
0x1800b408e  mov     edi, eax
0x1800b4090  test    eax, eax
0x1800b4092  jns     short loc_1800B40D5
0x1800b4094  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b409b  lea     rax, WPP_GLOBAL_Control
0x1800b40a2  cmp     rcx, rax
0x1800b40a5  jz      loc_1800B459A
0x1800b40ab  test    byte ptr [rcx+1Ch], 8
0x1800b40af  jz      loc_1800B459A
0x1800b40b5  cmp     byte ptr [rcx+19h], 2
0x1800b40b9  jb      loc_1800B459A
0x1800b40bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b40c4  mov     edx, 1Fh
0x1800b40c9  lea     rcx, aFailedToSortTh; "Failed to sort the address list"
0x1800b40d0  jmp     loc_1800B4577
0x1800b40d5  lea     rcx, [r14+38h]; this
0x1800b40d9  call    ?StartEnum@CRDPENCONResolver@@QEAAIXZ; CRDPENCONResolver::StartEnum(void)
0x1800b40de  mov     edi, eax
0x1800b40e0  test    eax, eax
0x1800b40e2  jnz     short loc_1800B4162
0x1800b40e4  mov     eax, cs:dword_1808B5850
0x1800b40ea  cmp     eax, 2
0x1800b40ed  jbe     short loc_1800B4158
0x1800b40ef  lea     rax, aFailedToResolv_0; "Failed to resolve any IPS"
0x1800b40f6  mov     [rbp+57h+var_AC], 20Bh
0x1800b40fd  mov     [rbp+57h+var_A0], rax
0x1800b4101  lea     r15, aThreadproc; "ThreadProc"
0x1800b4108  lea     rax, [rbp+57h+var_90]
0x1800b410c  mov     [rbp+57h+var_90], r15
0x1800b4110  mov     [rsp+100h+var_C0], rax
0x1800b4115  lea     r12, aOnecoreTermsrv_45; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800b411c  lea     rax, [rbp+57h+var_AC]
0x1800b4120  mov     [rbp+57h+var_88], r12
0x1800b4124  mov     [rsp+100h+var_C8], rax
0x1800b4129  lea     rdx, qword_18086CC18
0x1800b4130  lea     rax, [rbp+57h+var_88]
0x1800b4134  mov     esi, 80004005h
0x1800b4139  mov     [rsp+100h+var_D0], rax
0x1800b413e  lea     rax, [rbp+57h+var_B0]
0x1800b4142  mov     qword ptr [rsp+100h+fResume], rax
0x1800b4147  lea     rax, [rbp+57h+var_A0]
0x1800b414b  mov     [rsp+100h+lpArgToCompletionRoutine], rax
0x1800b4150  mov     [rbp+57h+var_B0], esi
0x1800b4153  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800b4158  mov     edi, 83452206h
0x1800b415d  jmp     loc_1800B459A
0x1800b4162  mov     eax, 8
0x1800b4167  mul     rdi
0x1800b416a  cmovb   rax, r15
0x1800b416e  mov     rcx, rax; Size
0x1800b4171  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b4176  lea     rsi, [r14+130h]
0x1800b417d  mov     r9, rax
0x1800b4180  mov     [rsi], rax
0x1800b4183  test    rax, rax
0x1800b4186  jnz     short loc_1800B41DD
0x1800b4188  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b418f  lea     rax, WPP_GLOBAL_Control
0x1800b4196  cmp     rcx, rax
0x1800b4199  jz      short loc_1800B41D3
0x1800b419b  test    byte ptr [rcx+1Ch], 8
0x1800b419f  jz      short loc_1800B41D3
0x1800b41a1  cmp     byte ptr [rcx+19h], 2
0x1800b41a5  jb      short loc_1800B41D3
0x1800b41a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b41ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b41b3  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1800b41ba  mov     edx, 20h ; ' '
0x1800b41bf  mov     dword ptr [rsp+100h+lpArgToCompletionRoutine], 8007000Eh
0x1800b41c7  mov     r9d, eax
0x1800b41ca  mov     rcx, [rcx+10h]
0x1800b41ce  call    WPP_SF_Dd
0x1800b41d3  mov     edi, 8007000Eh
0x1800b41d8  jmp     loc_1800B459A
0x1800b41dd  test    edi, edi
0x1800b41df  jz      short loc_1800B423E
0x1800b41e1  mov     edx, r12d
0x1800b41e4  cmp     edi, 2
0x1800b41e7  jb      short loc_1800B422F
0x1800b41e9  cmp     r9, rsi
0x1800b41ec  ja      short loc_1800B41FA
0x1800b41ee  lea     eax, [rdi-1]
0x1800b41f1  lea     rax, [r9+rax*8]
0x1800b41f5  cmp     rax, rsi
0x1800b41f8  jnb     short loc_1800B422F
0x1800b41fa  mov     eax, edi
0x1800b41fc  and     eax, 0FFFFFFFEh
0x1800b41ff  add     edx, 2
0x1800b4202  mov     r15d, edx
0x1800b4205  cmp     edx, eax
0x1800b4207  jb      short loc_1800B41FF
0x1800b4209  mov     r8d, eax
0x1800b420c  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x1800b4210  shr     r8, 1
0x1800b4213  mov     rcx, r9; void *
0x1800b4216  shl     r8, 4
0x1800b421a  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1800b421e  call    memset_0
0x1800b4223  mov     edx, r15d
0x1800b4226  cmp     r15d, edi
0x1800b4229  jnb     short loc_1800B423E
0x1800b422b  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800b422f  mov     rax, [rsi]
0x1800b4232  mov     ecx, edx
0x1800b4234  inc     edx
0x1800b4236  mov     [rax+rcx*8], r15
0x1800b423a  cmp     edx, edi
0x1800b423c  jb      short loc_1800B422F
0x1800b423e  xor     r9d, r9d; lpName
0x1800b4241  mov     [r14+138h], edi
0x1800b4248  xor     r8d, r8d; bInitialState
0x1800b424b  mov     [r14+13Ch], r12d
0x1800b4252  xor     edx, edx; bManualReset
0x1800b4254  xor     ecx, ecx; lpEventAttributes
0x1800b4256  call    cs:__imp_CreateEventW
0x1800b425c  mov     [r14+120h], rax
0x1800b4263  test    rax, rax
0x1800b4266  jnz     short loc_1800B42AA
0x1800b4268  call    cs:__imp_GetLastError
0x1800b426e  mov     edi, eax
0x1800b4270  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4277  lea     rax, WPP_GLOBAL_Control
0x1800b427e  cmp     rcx, rax
0x1800b4281  jz      loc_1800B401A
0x1800b4287  test    byte ptr [rcx+1Ch], 8
0x1800b428b  jz      loc_1800B401A
0x1800b4291  cmp     byte ptr [rcx+19h], 2
0x1800b4295  jb      loc_1800B401A
0x1800b429b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b42a0  mov     edx, 21h ; '!'
0x1800b42a5  jmp     loc_1800B3FFC
0x1800b42aa  mov     r9d, 1F0003h; dwDesiredAccess
0x1800b42b0  xor     r8d, r8d; dwFlags
0x1800b42b3  xor     edx, edx; lpTimerName
0x1800b42b5  xor     ecx, ecx; lpTimerAttributes
0x1800b42b7  call    cs:__imp_CreateWaitableTimerExW
0x1800b42bd  mov     r13, rax
0x1800b42c0  test    rax, rax
0x1800b42c3  jnz     short loc_1800B4306
0x1800b42c5  call    cs:__imp_GetLastError
0x1800b42cb  mov     edi, eax
0x1800b42cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b42d4  lea     rax, WPP_GLOBAL_Control
0x1800b42db  cmp     rcx, rax
0x1800b42de  jz      loc_1800B401A
0x1800b42e4  test    byte ptr [rcx+1Ch], 8
0x1800b42e8  jz      loc_1800B401A
0x1800b42ee  cmp     byte ptr [rcx+19h], 2
0x1800b42f2  jb      loc_1800B401A
0x1800b42f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b42fd  lea     edx, [r13+22h]
0x1800b4301  jmp     loc_1800B3FFC
0x1800b4306  mov     eax, cs:dword_1808B5850
0x1800b430c  cmp     eax, 5
0x1800b430f  jbe     short loc_1800B434B
0x1800b4311  mov     eax, [r14+104h]
0x1800b4318  lea     rdx, dword_18086CBE4
0x1800b431f  mov     [rbp+57h+var_B0], eax
0x1800b4322  lea     rcx, dword_1808B5850
0x1800b4329  lea     rax, aTryingToConnec; "Trying to connection using Conn Q Inter"...
0x1800b4330  mov     [rbp+57h+var_A0], rax
0x1800b4334  lea     rax, [rbp+57h+var_B0]
0x1800b4338  mov     qword ptr [rsp+100h+fResume], rax
0x1800b433d  lea     rax, [rbp+57h+var_A0]
0x1800b4341  mov     [rsp+100h+lpArgToCompletionRoutine], rax
0x1800b4346  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800b434b  mov     r8d, [r14+104h]; lPeriod
0x1800b4352  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x1800b4356  mov     [rsp+100h+fResume], r12d; fResume
0x1800b435b  xor     r9d, r9d; pfnCompletionRoutine
0x1800b435e  mov     rcx, r13; hTimer
0x1800b4361  mov     [rsp+100h+lpArgToCompletionRoutine], r12; lpArgToCompletionRoutine
0x1800b4366  mov     qword ptr [rbp+57h+DueTime], r12
0x1800b436a  call    cs:__imp_SetWaitableTimer
0x1800b4370  test    eax, eax
0x1800b4372  jnz     short loc_1800B43B6
0x1800b4374  call    cs:__imp_GetLastError
0x1800b437a  mov     edi, eax
0x1800b437c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4383  lea     rax, WPP_GLOBAL_Control
0x1800b438a  cmp     rcx, rax
0x1800b438d  jz      loc_1800B401A
0x1800b4393  test    byte ptr [rcx+1Ch], 8
0x1800b4397  jz      loc_1800B401A
0x1800b439d  cmp     byte ptr [rcx+19h], 2
0x1800b43a1  jb      loc_1800B401A
0x1800b43a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b43ac  mov     edx, 23h ; '#'
0x1800b43b1  jmp     loc_1800B3FFC
0x1800b43b6  mov     rax, [r14+120h]
0x1800b43bd  mov     rcx, r14; this
0x1800b43c0  mov     qword ptr [rbp+57h+var_70+8], rax
0x1800b43c4  mov     qword ptr [rbp+57h+var_70], r13
0x1800b43c8  call    ?CreatePendingConnection@CRDPENCDirectConnector@@IEAAJXZ; CRDPENCDirectConnector::CreatePendingConnection(void)
0x1800b43cd  mov     edi, eax
0x1800b43cf  test    eax, eax
0x1800b43d1  js      loc_1800B4547
0x1800b43d7  mov     esi, 80004005h
0x1800b43dc  lea     r15, aThreadproc; "ThreadProc"
0x1800b43e3  lea     r12, aOnecoreTermsrv_45; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800b43ea  cmp     edi, 1
0x1800b43ed  jnz     loc_1800B4474
0x1800b43f3  mov     rcx, r13; hTimer
0x1800b43f6  call    cs:__imp_CancelWaitableTimer
0x1800b43fc  mov     edx, [r14+13Ch]
  ... truncated ...
```
