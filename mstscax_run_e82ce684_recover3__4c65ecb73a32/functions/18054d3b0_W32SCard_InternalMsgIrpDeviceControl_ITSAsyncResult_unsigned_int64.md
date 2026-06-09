# W32SCard::InternalMsgIrpDeviceControl(ITSAsyncResult *,unsigned __int64)

- ea: `0x18054d3b0`
- end: `0x18054e27e`
- name: `?InternalMsgIrpDeviceControl@W32SCard@@MEAAJPEAVITSAsyncResult@@_K@Z`
- size: `3790`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct ITSAsyncResult *)`
- caller_count: `1`
- callee_count: `27`
- tags: ``

## callers

- `0x18054e290`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18007328c`
- `0x180073420`
- `0x18007344c`
- `0x180073de0`
- `0x1800d5ee8`
- `0x1800d6540`
- `0x1800ee8f8`
- `0x18012962c`
- `0x180548d28`
- `0x18054be0c`
- `0x18054c268`
- `0x18054c964`
- `0x18054ca6c`
- `0x18054ce78`
- `0x18054d3b0`
- `0x18054e2a4`
- `0x18054e678`
- `0x18054ea5c`
- `0x18054edbc`
- `0x18054f128`
- `0x18054f490`
- `0x18054f9bc`
- `0x18055193c`
- `0x18068c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18054d463`
- `msvcrt!memcpy_s` at `0x18054d463`
- `KERNEL32!WaitForSingleObject` at `0x18054e145`
- `KERNEL32!WaitForSingleObject` at `0x18054e145`
- `KERNEL32!CloseHandle` at `0x18054e14e`
- `KERNEL32!CloseHandle` at `0x18054e14e`
- `KERNEL32!GetLastError` at `0x18054e0d5`
- `KERNEL32!GetLastError` at `0x18054e0d5`
- `KERNEL32!FreeLibrary` at `0x18054e111`
- `KERNEL32!FreeLibrary` at `0x18054e111`
- `KERNEL32!LeaveCriticalSection` at `0x18054e108`
- `KERNEL32!LeaveCriticalSection` at `0x18054e130`
- `KERNEL32!LeaveCriticalSection` at `0x18054e172`
- `KERNEL32!LeaveCriticalSection` at `0x18054e108`
- `KERNEL32!LeaveCriticalSection` at `0x18054e130`
- `KERNEL32!LeaveCriticalSection` at `0x18054e172`
- `KERNEL32!EnterCriticalSection` at `0x18054e07a`
- `KERNEL32!EnterCriticalSection` at `0x18054e07a`
- `KERNEL32!CreateThread` at `0x18054e0a8`
- `KERNEL32!CreateThread` at `0x18054e0a8`
- `KERNEL32!ResumeThread` at `0x18054e139`
- `KERNEL32!ResumeThread` at `0x18054e17f`
- `KERNEL32!ResumeThread` at `0x18054e139`
- `KERNEL32!ResumeThread` at `0x18054e17f`

## pseudocode

```c
__int64 __fastcall W32SCard::InternalMsgIrpDeviceControl(struct _RTL_CRITICAL_SECTION *this, struct ITSAsyncResult *a2)
{
  struct tagRDPDR_IOREQUEST_PACKET *v3; // rax
  struct tagRDPDR_IOREQUEST_PACKET *v4; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // r8d
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // r8d
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rdx
  unsigned int v34; // r8d
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // r8d
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  __int64 v53; // rcx
  bool v54; // zf
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  HMODULE v59; // r15
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // r8d
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  unsigned int v75; // eax
  unsigned int v76; // eax
  _QWORD *v77; // rax
  _QWORD *v78; // r14
  unsigned int v79; // eax
  HANDLE v80; // rax
  void *v81; // rbx
  DWORD LastError; // ebx
  unsigned int v83; // eax
  int v84; // eax
  struct _RTL_CRITICAL_SECTION *v85; // rcx
  unsigned int v86; // eax
  unsigned int v87; // r8d
  unsigned int v88; // eax
  void *Source; // [rsp+30h] [rbp-38h] BYREF
  rsize_t SourceSize; // [rsp+78h] [rbp+10h] BYREF
  DWORD ThreadId; // [rsp+88h] [rbp+20h] BYREF

  ThreadId = 0;
  Source = 0;
  LODWORD(SourceSize) = 0;
  if ( (*(int (__fastcall **)(struct ITSAsyncResult *, rsize_t *, void **))(*(_QWORD *)a2 + 48LL))(
         a2,
         &SourceSize,
         &Source) < 0
    || !Source )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 57;
      goto LABEL_257;
    }
    return 0;
  }
  v3 = (struct tagRDPDR_IOREQUEST_PACKET *)operator new((unsigned int)SourceSize);
  v4 = v3;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 58;
LABEL_257:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids,
        CurrentThreadActivityIdPrefix);
      return 0;
    }
    return 0;
  }
  memcpy_s(v3, (unsigned int)SourceSize, Source, (unsigned int)SourceSize);
  v7 = *((_DWORD *)v4 + 8);
  if ( v7 > 0x900A8 )
  {
    v53 = 590040;
    if ( v7 <= 0x900D8 )
    {
      if ( v7 == 590040 )
        goto LABEL_170;
      v53 = 590016;
      if ( v7 > 0x900C0 )
      {
        v55 = v7 - 590020;
        v54 = v55 == 0;
      }
      else
      {
        if ( v7 == 590016 )
          goto LABEL_170;
        v55 = v7 - 589996;
        v54 = v55 == 0;
      }
      if ( !v54 )
      {
        v56 = v55 - 4;
        if ( v56 )
        {
          v57 = v56 - 4;
          if ( v57 )
          {
            v58 = v57 - 4;
            if ( v58 )
            {
              if ( v58 != 4 )
                return 0;
            }
          }
        }
      }
LABEL_170:
      v59 = W32SCard::AddRefCurrentModule((W32SCard *)v53);
      if ( !v59 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v60 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v60);
        }
        goto LABEL_240;
      }
      v77 = MIDL_user_allocate(0x28u);
      v78 = v77;
      if ( v77 )
      {
        *v77 = this;
        *((_DWORD *)v77 + 2) = *((_DWORD *)v4 + 8);
        v77[2] = v4;
        v77[3] = v59;
        v77[4] = 0;
        EnterCriticalSection(this + 18);
        if ( !LODWORD(this[20].DebugInfo) )
        {
          v80 = CreateThread(0, 0, W32SCard::SCardHandleCall_ThreadProc, v78, 4u, &ThreadId);
          v81 = v80;
          if ( v80 )
          {
            v84 = W32SCard::AddThreadToList((W32SCard *)this, v80);
            v85 = this + 18;
            if ( v84 )
            {
              LeaveCriticalSection(v85);
              v78[4] = v81;
              ResumeThread(v81);
              return 0;
            }
            LeaveCriticalSection(v85);
            ResumeThread(v81);
            WaitForSingleObject(v81, 0xFFFFFFFF);
            CloseHandle(v81);
            goto LABEL_239;
          }
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v83 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              93,
              WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids,
              v83,
              LastError);
          }
        }
        LeaveCriticalSection(this + 18);
      }
      else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
             && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v79 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v79, 40);
      }
      FreeLibrary(v59);
      if ( !v78 )
      {
LABEL_240:
        W32SCard::DefaultIORequestMsgHandleWrapper((W32SCard *)this, v4, -1073741801);
        return 0;
      }
LABEL_239:
      MIDL_user_free(v78);
      goto LABEL_240;
    }
    if ( v7 <= 0x900F4 )
    {
      if ( v7 == 590068 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v70 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v70);
        }
        v66 = 590068;
      }
      else
      {
        v61 = v7 - 590044;
        if ( !v61 )
          goto LABEL_170;
        v62 = v61 - 4;
        if ( !v62 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v69 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v69);
          }
          W32SCard::AccessStartedEvent((W32SCard *)this, v4);
          return 0;
        }
        v63 = v62 - 8;
        if ( !v63 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v68 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v68);
          }
          W32SCard::LocateCardsByATRA((W32SCard *)this, v4);
          return 0;
        }
        v64 = v63 - 4;
        if ( !v64 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v67 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v67);
          }
          W32SCard::LocateCardsByATRW((W32SCard *)this, v4);
          return 0;
        }
        if ( v64 != 4 )
          return 0;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v65 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v65);
        }
        v66 = 590064;
      }
      W32SCard::ReadCache((W32SCard *)this, v4, v66);
      return 0;
    }
    v71 = v7 - 590072;
    if ( v71 )
    {
      v72 = v71 - 4;
      if ( v72 )
      {
        v73 = v72 - 4;
        if ( v73 )
        {
          v74 = v73 - 4;
          if ( v74 )
          {
            if ( v74 == 4 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v75 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v75);
              }
              W32SCard::GetDeviceTypeId((W32SCard *)this, v4);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v76 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v76);
            }
            W32SCard::GetReaderIcon((W32SCard *)this, v4);
          }
          return 0;
        }
        goto LABEL_170;
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v86 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v86);
      }
      v87 = 590076;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v88 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v88);
      }
      v87 = 590072;
    }
    W32SCard::WriteCache((W32SCard *)this, v4, v87);
    return 0;
  }
  if ( v7 == 589992 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v52 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v52);
    }
    v18 = 589992;
    goto LABEL_40;
  }
  v8 = 589920;
  if ( v7 <= 0x90060 )
  {
    if ( v7 != 589920 )
    {
      v9 = 589864;
      if ( v7 <= 0x90028 )
      {
        if ( v7 != 589864 )
        {
          v10 = v7 - 589844;
          if ( !v10 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v20 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v20);
            }
            W32SCard::EstablishContext((W32SCard *)this, v4);
            return 0;
          }
          v11 = v10 - 4;
          if ( v11 )
          {
            v12 = v11 - 4;
            if ( v12 )
            {
              v13 = v12 - 4;
              if ( v13 )
              {
                if ( v13 != 4 )
                  return 0;
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v14 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    63,
                    WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids,
                    v14);
                }
                v15 = 589860;
              }
              else
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v16 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    62,
                    WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids,
                    v16);
                }
                v15 = 589856;
              }
              W32SCard::ListReaderGroups((W32SCard *)this, v4, v15);
              return 0;
            }
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v17 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v17);
            }
            v18 = 589852;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v19 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v19);
            }
            v18 = 589848;
          }
LABEL_40:
          W32SCard::HandleContextCallWithLongReturn((W32SCard *)this, v4, v18);
          return 0;
        }
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
LABEL_51:
          W32SCard::ListReaders((W32SCard *)this, v4, v9);
          return 0;
        }
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        v22 = 64;
LABEL_50:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v21);
        goto LABEL_51;
      }
      v9 = 589868;
      v23 = v7 - 589868;
      if ( !v23 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_51;
        }
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        v22 = 65;
        goto LABEL_50;
      }
      v24 = v23 - 36;
      if ( v24 )
      {
        v25 = v24 - 4;
        if ( v25 )
        {
          v26 = v25 - 4;
          if ( v26 )
          {
            if ( v26 != 4 )
              return 0;
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v27 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v27);
            }
            v28 = 589916;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v29 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v29);
            }
            v28 = 589912;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v30 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v30);
          }
          v28 = 589908;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v31 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v31);
        }
        v28 = 589904;
      }
LABEL_77:
      W32SCard::HandleContextAndStringCallWithLongReturn((W32SCard *)this, v4, v28);
      return 0;
    }
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      goto LABEL_87;
    }
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    v33 = 70;
    goto LABEL_86;
  }
  v8 = 589944;
  if ( v7 <= 0x90078 )
  {
    if ( v7 == 589944 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_87;
      }
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      v33 = 76;
    }
    else
    {
      v8 = 589924;
      v35 = v7 - 589924;
      if ( v35 )
      {
        v36 = v35 - 4;
        if ( !v36 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v42 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v42);
          }
          v28 = 589928;
          goto LABEL_77;
        }
        v37 = v36 - 4;
        if ( !v37 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v41 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v41);
          }
          v28 = 589932;
          goto LABEL_77;
        }
        v38 = v37 - 4;
        if ( v38 )
        {
          if ( v38 != 4 )
            return 0;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v39 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v39);
          }
          v34 = 589940;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v40 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v40);
          }
          v34 = 589936;
        }
LABEL_88:
        W32SCard::HandleContextAndTwoStringCallWithLongReturn((W32SCard *)this, v4, v34);
        return 0;
      }
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
LABEL_87:
        v34 = v8;
        goto LABEL_88;
      }
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      v33 = 71;
    }
LABEL_86:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v32);
    goto LABEL_87;
  }
  v8 = 589948;
  v43 = v7 - 589948;
  if ( !v43 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      goto LABEL_87;
    }
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    v33 = 77;
    goto LABEL_86;
  }
  v44 = v43 - 28;
  if ( v44 )
  {
    v45 = v44 - 4;
    if ( v45 )
    {
      v46 = v45 - 4;
      if ( v46 )
      {
        if ( v46 != 4 )
          return 0;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v47 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v47);
        }
        v48 = 589988;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v49 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v49);
        }
        v48 = 589984;
      }
      W32SCard::GetStatusChangeWrapper((W32SCard *)this, v4, v48);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v50 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v50);
    }
    W32SCard::LocateCardsW((W32SCard *)this, v4);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v51 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids, v51);
    }
    W32SCard::LocateCardsA((W32SCard *)this, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18054d3b0  mov     rax, rsp
0x18054d3b3  mov     [rax+8], rbx
0x18054d3b7  push    rbp
0x18054d3b8  push    rsi
0x18054d3b9  push    rdi
0x18054d3ba  push    r14
0x18054d3bc  push    r15
0x18054d3be  sub     rsp, 40h
0x18054d3c2  mov     dword ptr [rax+20h], 0
0x18054d3c9  lea     r8, [rsp+68h+Source]
0x18054d3ce  mov     qword ptr [rax-38h], 0
0x18054d3d6  mov     r9, rdx
0x18054d3d9  mov     dword ptr [rax+10h], 0
0x18054d3e0  mov     rsi, rcx
0x18054d3e3  mov     rax, [rdx]
0x18054d3e6  mov     rcx, r9
0x18054d3e9  lea     rdx, [rsp+68h+SourceSize]
0x18054d3ee  mov     rax, [rax+30h]
0x18054d3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18054d3f7  test    eax, eax
0x18054d3f9  js      loc_18054E228
0x18054d3ff  cmp     [rsp+68h+Source], 0
0x18054d405  jz      loc_18054E228
0x18054d40b  mov     ecx, dword ptr [rsp+68h+SourceSize]; Size
0x18054d40f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18054d414  mov     rdi, rax
0x18054d417  test    rax, rax
0x18054d41a  jnz     short loc_18054D454
0x18054d41c  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d423  lea     rax, WPP_GLOBAL_Control
0x18054d42a  cmp     rcx, rax
0x18054d42d  jz      loc_18054E26B
0x18054d433  test    byte ptr [rcx+1Ch], 1
0x18054d437  jz      loc_18054E26B
0x18054d43d  cmp     byte ptr [rcx+19h], 2
0x18054d441  jb      loc_18054E26B
0x18054d447  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d44c  lea     edx, [rdi+3Ah]
0x18054d44f  jmp     loc_18054E251
0x18054d454  mov     edx, dword ptr [rsp+68h+SourceSize]; DestinationSize
0x18054d458  mov     rcx, rdi; Destination
0x18054d45b  mov     r8, [rsp+68h+Source]; Source
0x18054d460  mov     r9d, edx; SourceSize
0x18054d463  call    cs:__imp_memcpy_s
0x18054d469  mov     eax, [rdi+20h]
0x18054d46c  mov     ebx, 900A8h
0x18054d471  cmp     eax, ebx
0x18054d473  ja      loc_18054DCA4
0x18054d479  jz      loc_18054DC59
0x18054d47f  mov     ebx, 90060h
0x18054d484  cmp     eax, ebx
0x18054d486  ja      loc_18054D8BD
0x18054d48c  jz      loc_18054D867
0x18054d492  mov     ebx, 90028h
0x18054d497  cmp     eax, ebx
0x18054d499  ja      loc_18054D6C0
0x18054d49f  jz      loc_18054D66A
0x18054d4a5  sub     eax, 90014h
0x18054d4aa  jz      loc_18054D617
0x18054d4b0  mov     ebx, 4
0x18054d4b5  sub     eax, ebx
0x18054d4b7  jz      loc_18054D5BE
0x18054d4bd  sub     eax, ebx
0x18054d4bf  jz      loc_18054D573
0x18054d4c5  sub     eax, ebx
0x18054d4c7  jz      short loc_18054D51A
0x18054d4c9  cmp     eax, ebx
0x18054d4cb  jnz     loc_18054E26B
0x18054d4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d4d8  lea     rax, WPP_GLOBAL_Control
0x18054d4df  cmp     rcx, rax
0x18054d4e2  jz      short loc_18054D512
0x18054d4e4  test    byte ptr [rcx+1Ch], 1
0x18054d4e8  jz      short loc_18054D512
0x18054d4ea  cmp     byte ptr [rcx+19h], 5
0x18054d4ee  jb      short loc_18054D512
0x18054d4f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d4fc  lea     edx, [rbx+3Bh]
0x18054d4ff  mov     r9d, eax
0x18054d502  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d509  mov     rcx, [rcx+10h]
0x18054d50d  call    WPP_SF_d
0x18054d512  mov     r8d, 90024h
0x18054d518  jmp     short loc_18054D563
0x18054d51a  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d521  lea     rax, WPP_GLOBAL_Control
0x18054d528  cmp     rcx, rax
0x18054d52b  jz      short loc_18054D55D
0x18054d52d  test    byte ptr [rcx+1Ch], 1
0x18054d531  jz      short loc_18054D55D
0x18054d533  cmp     byte ptr [rcx+19h], 5
0x18054d537  jb      short loc_18054D55D
0x18054d539  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d545  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d54c  mov     edx, 3Eh ; '>'
0x18054d551  mov     r9d, eax
0x18054d554  mov     rcx, [rcx+10h]
0x18054d558  call    WPP_SF_d
0x18054d55d  mov     r8d, 90020h; unsigned int
0x18054d563  mov     rdx, rdi; struct tagRDPDR_IOREQUEST_PACKET *
0x18054d566  mov     rcx, rsi; this
0x18054d569  call    ?ListReaderGroups@W32SCard@@IEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@K@Z; W32SCard::ListReaderGroups(tagRDPDR_IOREQUEST_PACKET *,ulong)
0x18054d56e  jmp     loc_18054E26B
0x18054d573  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d57a  lea     rax, WPP_GLOBAL_Control
0x18054d581  cmp     rcx, rax
0x18054d584  jz      short loc_18054D5B6
0x18054d586  test    byte ptr [rcx+1Ch], 1
0x18054d58a  jz      short loc_18054D5B6
0x18054d58c  cmp     byte ptr [rcx+19h], 5
0x18054d590  jb      short loc_18054D5B6
0x18054d592  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d597  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d59e  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d5a5  mov     edx, 3Dh ; '='
0x18054d5aa  mov     r9d, eax
0x18054d5ad  mov     rcx, [rcx+10h]
0x18054d5b1  call    WPP_SF_d
0x18054d5b6  mov     r8d, 9001Ch
0x18054d5bc  jmp     short loc_18054D607
0x18054d5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d5c5  lea     rax, WPP_GLOBAL_Control
0x18054d5cc  cmp     rcx, rax
0x18054d5cf  jz      short loc_18054D601
0x18054d5d1  test    byte ptr [rcx+1Ch], 1
0x18054d5d5  jz      short loc_18054D601
0x18054d5d7  cmp     byte ptr [rcx+19h], 5
0x18054d5db  jb      short loc_18054D601
0x18054d5dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d5e9  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d5f0  mov     edx, 3Ch ; '<'
0x18054d5f5  mov     r9d, eax
0x18054d5f8  mov     rcx, [rcx+10h]
0x18054d5fc  call    WPP_SF_d
0x18054d601  mov     r8d, 90018h; unsigned int
0x18054d607  mov     rdx, rdi; struct tagRDPDR_IOREQUEST_PACKET *
0x18054d60a  mov     rcx, rsi; this
0x18054d60d  call    ?HandleContextCallWithLongReturn@W32SCard@@IEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@K@Z; W32SCard::HandleContextCallWithLongReturn(tagRDPDR_IOREQUEST_PACKET *,ulong)
0x18054d612  jmp     loc_18054E26B
0x18054d617  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d61e  lea     rax, WPP_GLOBAL_Control
0x18054d625  cmp     rcx, rax
0x18054d628  jz      short loc_18054D65A
0x18054d62a  test    byte ptr [rcx+1Ch], 1
0x18054d62e  jz      short loc_18054D65A
0x18054d630  cmp     byte ptr [rcx+19h], 5
0x18054d634  jb      short loc_18054D65A
0x18054d636  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d63b  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d642  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d649  mov     edx, 3Bh ; ';'
0x18054d64e  mov     r9d, eax
0x18054d651  mov     rcx, [rcx+10h]
0x18054d655  call    WPP_SF_d
0x18054d65a  mov     rdx, rdi; struct tagRDPDR_IOREQUEST_PACKET *
0x18054d65d  mov     rcx, rsi; this
0x18054d660  call    ?EstablishContext@W32SCard@@IEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@@Z; W32SCard::EstablishContext(tagRDPDR_IOREQUEST_PACKET *)
0x18054d665  jmp     loc_18054E26B
0x18054d66a  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d671  lea     rax, WPP_GLOBAL_Control
0x18054d678  cmp     rcx, rax
0x18054d67b  jz      short loc_18054D6AD
0x18054d67d  test    byte ptr [rcx+1Ch], 1
0x18054d681  jz      short loc_18054D6AD
0x18054d683  cmp     byte ptr [rcx+19h], 5
0x18054d687  jb      short loc_18054D6AD
0x18054d689  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d68e  mov     edx, 40h ; '@'
0x18054d693  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d69a  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d6a1  mov     r9d, eax
0x18054d6a4  mov     rcx, [rcx+10h]
0x18054d6a8  call    WPP_SF_d
0x18054d6ad  mov     r8d, ebx; unsigned int
0x18054d6b0  mov     rdx, rdi; struct tagRDPDR_IOREQUEST_PACKET *
0x18054d6b3  mov     rcx, rsi; this
0x18054d6b6  call    ?ListReaders@W32SCard@@IEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@K@Z; W32SCard::ListReaders(tagRDPDR_IOREQUEST_PACKET *,ulong)
0x18054d6bb  jmp     loc_18054E26B
0x18054d6c0  mov     ebx, 9002Ch
0x18054d6c5  sub     eax, ebx
0x18054d6c7  jz      loc_18054D82D
0x18054d6cd  sub     eax, 24h ; '$'
0x18054d6d0  jz      loc_18054D7D4
0x18054d6d6  mov     ebx, 4
0x18054d6db  sub     eax, ebx
0x18054d6dd  jz      loc_18054D789
0x18054d6e3  sub     eax, ebx
0x18054d6e5  jz      short loc_18054D73B
0x18054d6e7  cmp     eax, ebx
0x18054d6e9  jnz     loc_18054E26B
0x18054d6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d6f6  lea     rax, WPP_GLOBAL_Control
0x18054d6fd  cmp     rcx, rax
0x18054d700  jz      short loc_18054D730
0x18054d702  test    byte ptr [rcx+1Ch], 1
0x18054d706  jz      short loc_18054D730
0x18054d708  cmp     byte ptr [rcx+19h], 5
0x18054d70c  jb      short loc_18054D730
0x18054d70e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d713  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d71a  lea     edx, [rbx+41h]
0x18054d71d  mov     r9d, eax
0x18054d720  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d727  mov     rcx, [rcx+10h]
0x18054d72b  call    WPP_SF_d
0x18054d730  mov     r8d, 9005Ch
0x18054d736  jmp     loc_18054D81D
0x18054d73b  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d742  lea     rax, WPP_GLOBAL_Control
0x18054d749  cmp     rcx, rax
0x18054d74c  jz      short loc_18054D77E
0x18054d74e  test    byte ptr [rcx+1Ch], 1
0x18054d752  jz      short loc_18054D77E
0x18054d754  cmp     byte ptr [rcx+19h], 5
0x18054d758  jb      short loc_18054D77E
0x18054d75a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d75f  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d766  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d76d  mov     edx, 44h ; 'D'
0x18054d772  mov     r9d, eax
0x18054d775  mov     rcx, [rcx+10h]
0x18054d779  call    WPP_SF_d
0x18054d77e  mov     r8d, 90058h
0x18054d784  jmp     loc_18054D81D
0x18054d789  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d790  lea     rax, WPP_GLOBAL_Control
0x18054d797  cmp     rcx, rax
0x18054d79a  jz      short loc_18054D7CC
0x18054d79c  test    byte ptr [rcx+1Ch], 1
0x18054d7a0  jz      short loc_18054D7CC
0x18054d7a2  cmp     byte ptr [rcx+19h], 5
0x18054d7a6  jb      short loc_18054D7CC
0x18054d7a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d7ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d7b4  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d7bb  mov     edx, 43h ; 'C'
0x18054d7c0  mov     r9d, eax
0x18054d7c3  mov     rcx, [rcx+10h]
0x18054d7c7  call    WPP_SF_d
0x18054d7cc  mov     r8d, 90054h
0x18054d7d2  jmp     short loc_18054D81D
0x18054d7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d7db  lea     rax, WPP_GLOBAL_Control
0x18054d7e2  cmp     rcx, rax
0x18054d7e5  jz      short loc_18054D817
0x18054d7e7  test    byte ptr [rcx+1Ch], 1
0x18054d7eb  jz      short loc_18054D817
0x18054d7ed  cmp     byte ptr [rcx+19h], 5
0x18054d7f1  jb      short loc_18054D817
0x18054d7f3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d7f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d7ff  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d806  mov     edx, 42h ; 'B'
0x18054d80b  mov     r9d, eax
0x18054d80e  mov     rcx, [rcx+10h]
0x18054d812  call    WPP_SF_d
0x18054d817  mov     r8d, 90050h; unsigned int
0x18054d81d  mov     rdx, rdi; struct tagRDPDR_IOREQUEST_PACKET *
0x18054d820  mov     rcx, rsi; this
0x18054d823  call    ?HandleContextAndStringCallWithLongReturn@W32SCard@@IEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@K@Z; W32SCard::HandleContextAndStringCallWithLongReturn(tagRDPDR_IOREQUEST_PACKET *,ulong)
0x18054d828  jmp     loc_18054E26B
0x18054d82d  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d834  lea     rax, WPP_GLOBAL_Control
0x18054d83b  cmp     rcx, rax
0x18054d83e  jz      loc_18054D6AD
0x18054d844  test    byte ptr [rcx+1Ch], 1
0x18054d848  jz      loc_18054D6AD
0x18054d84e  cmp     byte ptr [rcx+19h], 5
0x18054d852  jb      loc_18054D6AD
0x18054d858  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d85d  mov     edx, 41h ; 'A'
0x18054d862  jmp     loc_18054D693
0x18054d867  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d86e  lea     rax, WPP_GLOBAL_Control
0x18054d875  cmp     rcx, rax
0x18054d878  jz      short loc_18054D8AA
0x18054d87a  test    byte ptr [rcx+1Ch], 1
0x18054d87e  jz      short loc_18054D8AA
0x18054d880  cmp     byte ptr [rcx+19h], 5
0x18054d884  jb      short loc_18054D8AA
0x18054d886  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054d88b  mov     edx, 46h ; 'F'
0x18054d890  mov     rcx, cs:WPP_GLOBAL_Control
0x18054d897  lea     r8, WPP_242a4bb6c63c37d52bfc1b379beb170a_Traceguids
0x18054d89e  mov     r9d, eax
0x18054d8a1  mov     rcx, [rcx+10h]
0x18054d8a5  call    WPP_SF_d
0x18054d8aa  mov     r8d, ebx; unsigned int
0x18054d8ad  mov     rdx, rdi; struct tagRDPDR_IOREQUEST_PACKET *
0x18054d8b0  mov     rcx, rsi; this
0x18054d8b3  call    ?HandleContextAndTwoStringCallWithLongReturn@W32SCard@@IEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@K@Z; W32SCard::HandleContextAndTwoStringCallWithLongReturn(tagRDPDR_IOREQUEST_PACKET *,ulong)
0x18054d8b8  jmp     loc_18054E26B
0x18054d8bd  mov     ebx, 90078h
0x18054d8c2  cmp     eax, ebx
0x18054d8c4  ja      loc_18054DAA8
0x18054d8ca  jz      loc_18054DA6E
0x18054d8d0  mov     ebx, 90064h
  ... truncated ...
```
