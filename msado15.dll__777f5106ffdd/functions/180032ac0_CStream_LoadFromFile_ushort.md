# CStream::LoadFromFile(ushort *)

- ea: `0x180032ac0`
- end: `0x18003368e`
- name: `?LoadFromFile@CStream@@UEAAJPEAG@Z`
- size: `3022`
- prototype: `int(CStream *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009f9c0`

## callees

- `0x180020e20`
- `0x180020fc0`
- `0x180031760`
- `0x180032710`
- `0x180032ac0`
- `0x180042a04`
- `0x18005ce08`
- `0x18006a22c`
- `0x1800bc204`
- `0x1800bc238`
- `0x1800c1860`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800ca894`
- `0x1800caa28`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!GetFileTime` at `0x1800334b1`
- `KERNEL32!GetFileTime` at `0x1800334b1`
- `KERNEL32!GetFileType` at `0x180032f18`
- `KERNEL32!GetFileType` at `0x180032f18`
- `KERNEL32!CreateFileW` at `0x180032e9b`
- `KERNEL32!CreateFileW` at `0x180032e9b`
- `KERNEL32!ReadFile` at `0x180032fd1`
- `KERNEL32!ReadFile` at `0x180033247`
- `KERNEL32!ReadFile` at `0x180032fd1`
- `KERNEL32!ReadFile` at `0x180033247`
- `KERNEL32!CloseHandle` at `0x180033503`
- `KERNEL32!CloseHandle` at `0x180033503`
- `OLEAUT32!__imp_SysFreeString` at `0x180033512`
- `OLEAUT32!__imp_SysFreeString` at `0x180033512`
- `OLEAUT32!__imp_SysStringLen` at `0x180032b9a`
- `OLEAUT32!__imp_SysStringLen` at `0x180032b9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStream::LoadFromFile(CStream *this, unsigned __int16 *a2, __int64 a3, const char *a4)
{
  unsigned int v6; // r12d
  unsigned int BidObjectID; // eax
  OLECHAR *v8; // r13
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  unsigned __int16 *v14; // rdx
  HANDLE FileW; // r15
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rdx
  CStream *v20; // rcx
  int v21; // esi
  int v22; // eax
  __int64 v23; // r8
  DWORD v24; // r10d
  __int64 v25; // rcx
  unsigned int v26; // eax
  int v27; // ebx
  unsigned int v28; // eax
  unsigned int v29; // ebx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[40]; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+A0h] [rbp-60h]
  _FILETIME CreationTime; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+B8h] [rbp-48h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 Buffer[2048]; // [rsp+D0h] [rbp-30h] BYREF

  NumberOfBytesRead = 0;
  v37 = 0;
  v36 = 0;
  CXLockContext::CXLockContext(
    (CXLockContext *)v39,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    a4);
  v6 = 0;
  v35 = 0;
  v34 = 0;
  LastWriteTime = 0;
  CreationTime = 0;
  LastAccessTime = 0;
  v38 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AD98[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    bidScopeEnterW(&v38, off_18012AD98[0], BidObjectID, a2, dwCreationDisposition[0]);
  }
  if ( a2 && SysStringLen(a2) )
  {
    v8 = 0;
    if ( !*((_QWORD *)this + 21) )
    {
      v32 = -2146824584;
      if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_118;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v9 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          dwCreationDisposition[0] = 2557;
          v10 = 2618377;
LABEL_11:
          bidTraceW(
            off_18012A210[0],
            v10,
            L"<CStream::LoadFromFile|ADO|ERR> %u#, line %d\n",
            v9,
            *(_QWORD *)dwCreationDisposition);
          goto LABEL_118;
        }
        v11 = 2557;
        v12 = 2618377;
        goto LABEL_13;
      }
    }
    v13 = *((_DWORD *)this + 48);
    if ( (v13 & 2) == 0 && (v13 & 1) != 0 )
    {
      v32 = -2146825069;
      if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v9 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            dwCreationDisposition[0] = 2573;
            v10 = 2634761;
            goto LABEL_11;
          }
          v11 = 2573;
          v12 = 2634761;
          goto LABEL_13;
        }
LABEL_118:
        SysFreeString(v8);
        if ( v36 )
        {
          ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
          v36 = 0;
        }
        goto LABEL_124;
      }
    }
    (*(void (__fastcall **)(char *, GUID *, struct IUnknown **))(*((_QWORD *)this + 12) + 32LL))(
      (char *)this + 96,
      &IID_IUnknown,
      &v36);
    if ( (*((_BYTE *)this + 128) & 3) != 0 && !*((_QWORD *)this + 15)
      || (v14 = (unsigned __int16 *)*((_QWORD *)this + 15)) != 0
      && (int)SecurityCheck(a2, v14) < 0
      && (unsigned int)SecurityDialog(v36, *((unsigned __int16 **)this + 15), 1) )
    {
      v32 = -2146824572;
      if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_118;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v9 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          dwCreationDisposition[0] = 2581;
          v10 = 2642953;
          goto LABEL_11;
        }
        v11 = 2581;
        v12 = 2642953;
        goto LABEL_13;
      }
    }
    v8 = UNCEnable(a2);
    if ( !v8 )
    {
      v32 = -2147024882;
      if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_118;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v9 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          dwCreationDisposition[0] = 2588;
          v10 = 2650121;
          goto LABEL_11;
        }
        v11 = 2588;
        v12 = 2650121;
        goto LABEL_13;
      }
    }
    v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 40LL))(
            *((_QWORD *)this + 21),
            0,
            0,
            0);
    if ( v40 < 0 )
    {
      CContext::PushError((CContext *)v39);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_118;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v9 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        dwCreationDisposition[0] = 2592;
        v10 = 2654217;
        goto LABEL_11;
      }
      v11 = 2592;
      v12 = 2654217;
      goto LABEL_13;
    }
    FileW = CreateFileW(v8, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v32 = -2146825286;
      if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_118;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v9 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          dwCreationDisposition[0] = 2602;
          v10 = 2664457;
          goto LABEL_11;
        }
        v11 = 2602;
        v12 = 2664457;
LABEL_13:
        bidTraceW(off_18012A210[0], v12, L"<CStream::LoadFromFile|ADO|ERR>  line %d\n", v11);
        goto LABEL_118;
      }
    }
    if ( GetFileType(FileW) == 1
      || (v32 = -2146825069, !(unsigned int)CContext::FailedPushWarning((CContext *)v39, &v32)) )
    {
      if ( ReadFile(FileW, Buffer, 0x800u, &NumberOfBytesRead, 0)
        || (v32 = -2146825285, !(unsigned int)CContext::Failed((CContext *)v39, &v32)) )
      {
        v21 = 0;
        if ( *((_DWORD *)this + 46) != 2 )
          goto LABEL_82;
        v22 = *((_DWORD *)this + 54);
        if ( v22 == 1200 )
        {
          if ( NumberOfBytesRead >= 2 )
          {
            if ( CStream::CheckUnicodeByteOrderMark(v20, Buffer, (enum BYTEORDER *)&v35) )
              v21 = 2;
            v6 = v35;
          }
          v32 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))(**((_QWORD **)this + 21) + 32LL))(
                  *((_QWORD *)this + 21),
                  (char *)&g_ByteOrderMark + 2 * *((int *)this + 55),
                  2,
                  0);
          if ( !(unsigned int)CContext::Failed((CContext *)v39, &v32) )
            goto LABEL_82;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_117;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            dwCreationDisposition[0] = 2620;
            v17 = 2682889;
            goto LABEL_53;
          }
          v18 = 2620;
          v19 = 2682889;
        }
        else
        {
          if ( v22 != 65001 )
            goto LABEL_82;
          v23 = 3;
          if ( NumberOfBytesRead >= 3 && (unsigned int)CheckUTF8Mark(Buffer) )
            v21 = v23;
          v32 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 near **, __int64, _QWORD))(**((_QWORD **)this + 21)
                                                                                            + 32LL))(
                  *((_QWORD *)this + 21),
                  &g_ByteOrderUTF8Mark,
                  v23,
                  0);
          if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_117;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
            {
              v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
              dwCreationDisposition[0] = 2627;
              v17 = 2690057;
              goto LABEL_53;
            }
            v18 = 2627;
            v19 = 2690057;
          }
          else
          {
LABEL_82:
            while ( 1 )
            {
              v24 = NumberOfBytesRead - v21;
              if ( NumberOfBytesRead == v21 )
                break;
              if ( *((_DWORD *)this + 46) == 2 && *((_DWORD *)this + 54) == 1200 )
              {
                v25 = *((unsigned int *)this + 55);
                if ( v6 != (_DWORD)v25 )
                  CStream::TranslateByteOrder(v25, &Buffer[v21], v24, v6, *((_DWORD *)this + 55));
              }
              v40 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, int *))(**((_QWORD **)this + 21) + 32LL))(
                      *((_QWORD *)this + 21),
                      &Buffer[v21],
                      v24,
                      &v37);
              if ( v40 < 0 )
              {
                CContext::PushError((CContext *)v39);
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_117;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                {
                  v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  dwCreationDisposition[0] = 2635;
                  v17 = 2698249;
                  goto LABEL_53;
                }
                v18 = 2635;
                v19 = 2698249;
                goto LABEL_55;
              }
              if ( !ReadFile(FileW, Buffer, 0x800u, &NumberOfBytesRead, 0) )
              {
                v32 = -2146825285;
                if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_117;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                  {
                    v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                    dwCreationDisposition[0] = 2641;
                    v17 = 2704393;
                    goto LABEL_53;
                  }
                  v18 = 2641;
                  v19 = 2704393;
                  goto LABEL_55;
                }
              }
              v21 = 0;
            }
            v32 = (*(__int64 (__fastcall **)(CStream *))(*(_QWORD *)this + 200LL))(this);
            if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_117;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
              {
                v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                dwCreationDisposition[0] = 2647;
                v17 = 2710537;
                goto LABEL_53;
              }
              v18 = 2647;
              v19 = 2710537;
            }
            else
            {
              v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 40LL))(
                      *((_QWORD *)this + 21),
                      0,
                      0,
                      0);
              if ( (unsigned int)CContext::Failed((CContext *)v39, &v32) )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_117;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                {
                  v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  dwCreationDisposition[0] = 2652;
                  v17 = 2715657;
                  goto LABEL_53;
                }
                v18 = 2652;
                v19 = 2715657;
              }
              else
              {
                (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 21))(
                  *((_QWORD *)this + 21),
                  &IID_ICMemStreamProperties,
                  &v34);
                if ( !v34 )
                  goto LABEL_117;
                v32 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v34 + 24LL))(v34, a2);
                if ( !(unsigned int)CContext::Failed((CContext *)v39, &v32) )
                {
                  if ( GetFileTime(FileW, &CreationTime, &LastAccessTime, &LastWriteTime) )
                  {
                    (*(void (__fastcall **)(__int64, _FILETIME))(*(_QWORD *)v34 + 40LL))(v34, CreationTime);
                    (*(void (__fastcall **)(__int64, struct _FILETIME))(*(_QWORD *)v34 + 56LL))(v34, LastWriteTime);
                    (*(void (__fastcall **)(__int64, struct _FILETIME))(*(_QWORD *)v34 + 72LL))(v34, LastAccessTime);
                  }
                  goto LABEL_117;
                }
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_117;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
                {
                  v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
                  dwCreationDisposition[0] = 2658;
                  v17 = 2721801;
                  goto LABEL_53;
                }
                v18 = 2658;
                v19 = 2721801;
              }
            }
          }
        }
      }
      else
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_117;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          dwCreationDisposition[0] = 2611;
          v17 = 2673673;
          goto LABEL_53;
        }
        v18 = 2611;
        v19 = 2673673;
      }
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_117:
        CloseHandle(FileW);
        goto LABEL_118;
      }
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        v16 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        dwCreationDisposition[0] = 2606;
        v17 = 2668553;
LABEL_53:
        bidTraceW(
          off_18012A210[0],
          v17,
          L"<CStream::LoadFromFile|ADO|ERR> %u#, line %d\n",
          v16,
          *(_QWORD *)dwCreationDisposition);
        goto LABEL_117;
      }
      v18 = 2606;
      v19 = 2668553;
    }
LABEL_55:
    bidTraceW(off_18012A210[0], v19, L"<CStream::LoadFromFile|ADO|ERR>  line %d\n", v18);
    goto LABEL_117;
  }
  v40 = -2146825287;
  CContext::PushError((CContext *)v39);
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_127;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) == -1 )
  {
    bidTraceW(off_18012A210[0], 2612233, L"<CStream::LoadFromFile|ADO|ERR>  line %d\n", 2551);
  }
  else
  {
    v26 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    dwCreationDisposition[0] = 2551;
    bidTraceW(
      off_18012A210[0],
      2612233,
      L"<CStream::LoadFromFile|ADO|ERR> %u#, line %d\n",
      v26,
      *(_QWORD *)dwCreationDisposition);
  }
LABEL_124:
  if ( (bidGblFlags & 2) != 0 && off_18012A948[0] )
  {
    v27 = v40;
    v28 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
    dwCreationDisposition[0] = v27;
    bidTraceW(off_18012A210[0], 2737152, off_18012A948[0], v28, *(_QWORD *)dwCreationDisposition);
  }
LABEL_127:
  if ( (bidGblFlags & 4) != 0 && v38 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v38);
  v29 = v40;
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  CXLockContext::~CXLockContext((CXLockContext *)v39);
  return v29;
}

```

## disassembly

```asm
0x180032ac0  mov     [rsp-8+arg_10], rbx
0x180032ac5  push    rbp
0x180032ac6  push    rsi
0x180032ac7  push    rdi
0x180032ac8  push    r12
0x180032aca  push    r13
0x180032acc  push    r14
0x180032ace  push    r15
0x180032ad0  lea     rbp, [rsp-7E0h]
0x180032ad8  sub     rsp, 8E0h
0x180032adf  mov     rax, cs:__security_cookie
0x180032ae6  xor     rax, rsp
0x180032ae9  mov     [rbp+810h+var_40], rax
0x180032af0  mov     r14, rdx
0x180032af3  mov     rdi, rcx
0x180032af6  mov     [rsp+910h+NumberOfBytesRead], 0
0x180032afe  mov     [rsp+910h+var_8A8], 0
0x180032b06  mov     [rsp+910h+var_8B0], 0
0x180032b0f  mov     r8, [rcx+90h]
0x180032b16  add     r8, 8; struct CCriticalSection **
0x180032b1a  mov     rax, rcx
0x180032b1d  add     rcx, 20h ; ' '
0x180032b21  neg     rax
0x180032b24  sbb     rdx, rdx
0x180032b27  and     rdx, rcx; struct CStdComObjectRoot *
0x180032b2a  lea     rcx, [rsp+910h+var_898]; this
0x180032b2f  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x180032b34  xor     r12d, r12d
0x180032b37  mov     [rsp+910h+var_8B8], r12d
0x180032b3c  mov     [rsp+910h+var_8C0], r12
0x180032b41  mov     qword ptr [rbp+810h+LastWriteTime.dwLowDateTime], r12
0x180032b45  mov     qword ptr [rbp+810h+CreationTime.dwLowDateTime], r12
0x180032b49  mov     qword ptr [rbp+810h+LastAccessTime.dwLowDateTime], r12
0x180032b4d  mov     [rsp+910h+var_8A0], 0FFFFFFFFFFFFFFFFh
0x180032b56  test    byte ptr cs:_bidGblFlags, 4
0x180032b5d  jz      short loc_180032B8E
0x180032b5f  mov     rax, cs:off_18012AD98; "<CStream::LoadFromFile|API|ADO> %u#, bs"...
0x180032b66  test    rax, rax
0x180032b69  jz      short loc_180032B8E
0x180032b6b  lea     rcx, [rdi+98h]; this
0x180032b72  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032b77  mov     rdx, cs:off_18012AD98; "<CStream::LoadFromFile|API|ADO> %u#, bs"...
0x180032b7e  mov     r9, r14
0x180032b81  mov     r8d, eax
0x180032b84  lea     rcx, [rsp+910h+var_8A0]
0x180032b89  call    _bidScopeEnterW
0x180032b8e  test    r14, r14
0x180032b91  jz      loc_180033546
0x180032b97  mov     rcx, r14; pbstr
0x180032b9a  call    cs:__imp_SysStringLen
0x180032ba1  nop     dword ptr [rax+rax+00h]
0x180032ba6  test    eax, eax
0x180032ba8  jz      loc_180033546
0x180032bae  xor     r13d, r13d
0x180032bb1  cmp     [rdi+0A8h], r12
0x180032bb8  jnz     loc_180032C50
0x180032bbe  mov     [rsp+910h+var_8D0], 800A0E78h
0x180032bc6  lea     rdx, [rsp+910h+var_8D0]; int *
0x180032bcb  lea     rcx, [rsp+910h+var_898]; this
0x180032bd0  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180032bd5  test    eax, eax
0x180032bd7  jz      short loc_180032C50
0x180032bd9  lea     ebx, [r13+2]
0x180032bdd  test    byte ptr cs:_bidGblFlags, bl
0x180032be3  jz      loc_18003350F
0x180032be9  lea     rsi, [rdi+98h]
0x180032bf0  mov     rcx, rsi; this
0x180032bf3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032bf8  cmp     eax, 0FFFFFFFFh
0x180032bfb  jz      short loc_180032C2D
0x180032bfd  mov     rcx, rsi; this
0x180032c00  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032c05  mov     [rsp+910h+dwCreationDisposition], 9FDh
0x180032c0d  mov     edx, 27F409h
0x180032c12  lea     r8, aCstreamLoadfro_0; "<CStream::LoadFromFile|ADO|ERR> %u#, li"...
0x180032c19  mov     r9d, eax
0x180032c1c  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180032c23  call    _bidTraceW
0x180032c28  jmp     loc_18003350F
0x180032c2d  mov     r9d, 9FDh
0x180032c33  mov     edx, 27F409h
0x180032c38  lea     r8, aCstreamLoadfro; "<CStream::LoadFromFile|ADO|ERR>  line %"...
0x180032c3f  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180032c46  call    _bidTraceW
0x180032c4b  jmp     loc_18003350F
0x180032c50  mov     eax, [rdi+0C0h]
0x180032c56  mov     esi, 1
0x180032c5b  lea     ebx, [rsi+1]
0x180032c5e  test    bl, al
0x180032c60  jnz     short loc_180032CCC
0x180032c62  test    sil, al
0x180032c65  jz      short loc_180032CCC
0x180032c67  mov     [rsp+910h+var_8D0], 800A0C93h
0x180032c6f  lea     rdx, [rsp+910h+var_8D0]; int *
0x180032c74  lea     rcx, [rsp+910h+var_898]; this
0x180032c79  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180032c7e  test    eax, eax
0x180032c80  jz      short loc_180032CCC
0x180032c82  test    byte ptr cs:_bidGblFlags, bl
0x180032c88  jz      loc_18003350F
0x180032c8e  lea     rsi, [rdi+98h]
0x180032c95  mov     rcx, rsi; this
0x180032c98  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032c9d  cmp     eax, 0FFFFFFFFh
0x180032ca0  jz      short loc_180032CBC
0x180032ca2  mov     rcx, rsi; this
0x180032ca5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032caa  mov     [rsp+910h+dwCreationDisposition], 0A0Dh
0x180032cb2  mov     edx, 283409h
0x180032cb7  jmp     loc_180032C12
0x180032cbc  mov     r9d, 0A0Dh
0x180032cc2  mov     edx, 283409h
0x180032cc7  jmp     loc_180032C38
0x180032ccc  lea     rcx, [rdi+60h]
0x180032cd0  mov     rax, [rcx]
0x180032cd3  lea     r8, [rsp+910h+var_8B0]
0x180032cd8  lea     rdx, IID_IUnknown
0x180032cdf  mov     rax, [rax+20h]
0x180032ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ce8  mov     r15d, 3
0x180032cee  test    [rdi+80h], r15b
0x180032cf5  jz      short loc_180032CFD
0x180032cf7  cmp     [rdi+78h], r12
0x180032cfb  jz      short loc_180032D2B
0x180032cfd  mov     rdx, [rdi+78h]; unsigned __int16 *
0x180032d01  test    rdx, rdx
0x180032d04  jz      loc_180032D90
0x180032d0a  mov     rcx, r14; unsigned __int16 *
0x180032d0d  call    ?SecurityCheck@@YAJPEBGPEAG@Z; SecurityCheck(ushort const *,ushort *)
0x180032d12  test    eax, eax
0x180032d14  jns     short loc_180032D90
0x180032d16  mov     r8d, esi; int
0x180032d19  mov     rdx, [rdi+78h]; unsigned __int16 *
0x180032d1d  mov     rcx, [rsp+910h+var_8B0]; struct IUnknown *
0x180032d22  call    ?SecurityDialog@@YAJPEAUIUnknown@@PEAGH@Z; SecurityDialog(IUnknown *,ushort *,int)
0x180032d27  test    eax, eax
0x180032d29  jz      short loc_180032D90
0x180032d2b  mov     [rsp+910h+var_8D0], 800A0E84h
0x180032d33  lea     rdx, [rsp+910h+var_8D0]; int *
0x180032d38  lea     rcx, [rsp+910h+var_898]; this
0x180032d3d  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180032d42  test    eax, eax
0x180032d44  jz      short loc_180032D90
0x180032d46  test    byte ptr cs:_bidGblFlags, bl
0x180032d4c  jz      loc_18003350F
0x180032d52  lea     rsi, [rdi+98h]
0x180032d59  mov     rcx, rsi; this
0x180032d5c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032d61  cmp     eax, 0FFFFFFFFh
0x180032d64  jz      short loc_180032D80
0x180032d66  mov     rcx, rsi; this
0x180032d69  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032d6e  mov     [rsp+910h+dwCreationDisposition], 0A15h
0x180032d76  mov     edx, 285409h
0x180032d7b  jmp     loc_180032C12
0x180032d80  mov     r9d, 0A15h
0x180032d86  mov     edx, 285409h
0x180032d8b  jmp     loc_180032C38
0x180032d90  mov     rcx, r14; String2
0x180032d93  call    ?UNCEnable@@YAPEAGPEAG@Z; UNCEnable(ushort *)
0x180032d98  mov     r13, rax
0x180032d9b  test    rax, rax
0x180032d9e  jnz     short loc_180032E05
0x180032da0  mov     [rsp+910h+var_8D0], 8007000Eh
0x180032da8  lea     rdx, [rsp+910h+var_8D0]; int *
0x180032dad  lea     rcx, [rsp+910h+var_898]; this
0x180032db2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180032db7  test    eax, eax
0x180032db9  jz      short loc_180032E05
0x180032dbb  test    byte ptr cs:_bidGblFlags, bl
0x180032dc1  jz      loc_18003350F
0x180032dc7  lea     rsi, [rdi+98h]
0x180032dce  mov     rcx, rsi; this
0x180032dd1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032dd6  cmp     eax, 0FFFFFFFFh
0x180032dd9  jz      short loc_180032DF5
0x180032ddb  mov     rcx, rsi; this
0x180032dde  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032de3  mov     [rsp+910h+dwCreationDisposition], 0A1Ch
0x180032deb  mov     edx, 287009h
0x180032df0  jmp     loc_180032C12
0x180032df5  mov     r9d, 0A1Ch
0x180032dfb  mov     edx, 287009h
0x180032e00  jmp     loc_180032C38
0x180032e05  xor     edx, edx
0x180032e07  mov     rcx, [rdi+0A8h]
0x180032e0e  mov     rax, [rcx]
0x180032e11  xor     r9d, r9d
0x180032e14  xor     r8d, r8d
0x180032e17  mov     rax, [rax+28h]
0x180032e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e20  mov     [rbp+810h+var_870], eax
0x180032e23  test    eax, eax
0x180032e25  jns     short loc_180032E7B
0x180032e27  lea     rcx, [rsp+910h+var_898]; this
0x180032e2c  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180032e31  test    byte ptr cs:_bidGblFlags, bl
0x180032e37  jz      loc_18003350F
0x180032e3d  lea     rsi, [rdi+98h]
0x180032e44  mov     rcx, rsi; this
0x180032e47  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032e4c  cmp     eax, 0FFFFFFFFh
0x180032e4f  jz      short loc_180032E6B
0x180032e51  mov     rcx, rsi; this
0x180032e54  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032e59  mov     [rsp+910h+dwCreationDisposition], 0A20h
0x180032e61  mov     edx, 288009h
0x180032e66  jmp     loc_180032C12
0x180032e6b  mov     r9d, 0A20h
0x180032e71  mov     edx, 288009h
0x180032e76  jmp     loc_180032C38
0x180032e7b  mov     [rsp+910h+hTemplateFile], r12; hTemplateFile
0x180032e80  mov     [rsp+910h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180032e88  mov     [rsp+910h+dwCreationDisposition], r15d; dwCreationDisposition
0x180032e8d  xor     r9d, r9d; lpSecurityAttributes
0x180032e90  mov     r8d, esi; dwShareMode
0x180032e93  mov     edx, 80000000h; dwDesiredAccess
0x180032e98  mov     rcx, r13; lpFileName
0x180032e9b  call    cs:__imp_CreateFileW
0x180032ea2  nop     dword ptr [rax+rax+00h]
0x180032ea7  mov     r15, rax
0x180032eaa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032eae  jnz     short loc_180032F15
0x180032eb0  mov     [rsp+910h+var_8D0], 800A0BBAh
0x180032eb8  lea     rdx, [rsp+910h+var_8D0]; int *
0x180032ebd  lea     rcx, [rsp+910h+var_898]; this
0x180032ec2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180032ec7  test    eax, eax
0x180032ec9  jz      short loc_180032F15
0x180032ecb  test    byte ptr cs:_bidGblFlags, bl
0x180032ed1  jz      loc_18003350F
0x180032ed7  lea     rsi, [rdi+98h]
0x180032ede  mov     rcx, rsi; this
0x180032ee1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032ee6  cmp     eax, 0FFFFFFFFh
0x180032ee9  jz      short loc_180032F05
0x180032eeb  mov     rcx, rsi; this
0x180032eee  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032ef3  mov     [rsp+910h+dwCreationDisposition], 0A2Ah
0x180032efb  mov     edx, 28A809h
0x180032f00  jmp     loc_180032C12
0x180032f05  mov     r9d, 0A2Ah
0x180032f0b  mov     edx, 28A809h
0x180032f10  jmp     loc_180032C38
0x180032f15  mov     rcx, r15; hFile
0x180032f18  call    cs:__imp_GetFileType
0x180032f1f  nop     dword ptr [rax+rax+00h]
0x180032f24  cmp     eax, esi
0x180032f26  jz      loc_180032FBA
0x180032f2c  mov     [rsp+910h+var_8D0], 800A0C93h
0x180032f34  lea     rdx, [rsp+910h+var_8D0]; int *
0x180032f39  lea     rcx, [rsp+910h+var_898]; this
0x180032f3e  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180032f43  test    eax, eax
0x180032f45  jz      short loc_180032FBA
0x180032f47  test    byte ptr cs:_bidGblFlags, bl
0x180032f4d  jz      loc_180033500
0x180032f53  lea     rsi, [rdi+98h]
0x180032f5a  mov     rcx, rsi; this
0x180032f5d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032f62  cmp     eax, 0FFFFFFFFh
0x180032f65  jz      short loc_180032F97
0x180032f67  mov     rcx, rsi; this
0x180032f6a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180032f6f  mov     [rsp+910h+dwCreationDisposition], 0A2Eh
0x180032f77  mov     edx, 28B809h
0x180032f7c  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180032f83  mov     r9d, eax
0x180032f86  lea     r8, aCstreamLoadfro_0; "<CStream::LoadFromFile|ADO|ERR> %u#, li"...
0x180032f8d  call    _bidTraceW
0x180032f92  jmp     loc_180033500
0x180032f97  mov     r9d, 0A2Eh
0x180032f9d  mov     edx, 28B809h
0x180032fa2  lea     r8, aCstreamLoadfro; "<CStream::LoadFromFile|ADO|ERR>  line %"...
0x180032fa9  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180032fb0  call    _bidTraceW
0x180032fb5  jmp     loc_180033500
0x180032fba  mov     qword ptr [rsp+910h+dwCreationDisposition], r12; lpOverlapped
0x180032fbf  lea     r9, [rsp+910h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032fc4  mov     r8d, 800h; nNumberOfBytesToRead
0x180032fca  lea     rdx, [rbp+810h+Buffer]; lpBuffer
0x180032fce  mov     rcx, r15; hFile
0x180032fd1  call    cs:__imp_ReadFile
0x180032fd8  nop     dword ptr [rax+rax+00h]
0x180032fdd  test    eax, eax
0x180032fdf  jnz     short loc_180033046
0x180032fe1  mov     [rsp+910h+var_8D0], 800A0BBBh
0x180032fe9  lea     rdx, [rsp+910h+var_8D0]; int *
0x180032fee  lea     rcx, [rsp+910h+var_898]; this
0x180032ff3  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180032ff8  test    eax, eax
0x180032ffa  jz      short loc_180033046
0x180032ffc  test    byte ptr cs:_bidGblFlags, bl
0x180033002  jz      loc_180033500
0x180033008  lea     rsi, [rdi+98h]
0x18003300f  mov     rcx, rsi; this
0x180033012  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180033017  cmp     eax, 0FFFFFFFFh
0x18003301a  jz      short loc_180033036
0x18003301c  mov     rcx, rsi; this
  ... truncated ...
```
