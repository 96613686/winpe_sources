# W32DrDeviceAsync::AsyncMsgIrpCreateFunc(W32DRDEV_ASYNCIO_PARAMS *)

- ea: `0x180553660`
- end: `0x180554105`
- name: `?AsyncMsgIrpCreateFunc@W32DrDeviceAsync@@MEAAKPEAVW32DRDEV_ASYNCIO_PARAMS@@@Z`
- size: `2725`
- prototype: `__int64 __fastcall(ThreadPool **this, unsigned int **)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18007433c`
- `0x1800745a4`
- `0x1800ebae0`
- `0x1800f7748`
- `0x1800f95a8`
- `0x18012966c`
- `0x180548f44`
- `0x180553450`
- `0x180553660`
- `0x180554ec0`
- `0x1805550e4`
- `0x1805551fc`
- `0x1805557dc`
- `0x180556ba4`
- `0x180557778`
- `0x180557904`
- `0x180558ed0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180553c86`
- `KERNEL32!CloseHandle` at `0x180553d07`
- `KERNEL32!CloseHandle` at `0x180553c86`
- `KERNEL32!CloseHandle` at `0x180553d07`
- `KERNEL32!SetErrorMode` at `0x180553716`
- `KERNEL32!SetErrorMode` at `0x180553716`
- `KERNEL32!GetLastError` at `0x180553ae2`
- `KERNEL32!GetLastError` at `0x180553b1e`
- `KERNEL32!GetLastError` at `0x180553c47`
- `KERNEL32!GetLastError` at `0x180553c76`
- `KERNEL32!GetLastError` at `0x180553cf7`
- `KERNEL32!GetLastError` at `0x180553d71`
- `KERNEL32!GetLastError` at `0x180553ae2`
- `KERNEL32!GetLastError` at `0x180553b1e`
- `KERNEL32!GetLastError` at `0x180553c47`
- `KERNEL32!GetLastError` at `0x180553c76`
- `KERNEL32!GetLastError` at `0x180553cf7`
- `KERNEL32!GetLastError` at `0x180553d71`
- `KERNEL32!LocalAlloc` at `0x180553a01`
- `KERNEL32!LocalAlloc` at `0x180553e43`
- `KERNEL32!LocalAlloc` at `0x180553e91`
- `KERNEL32!LocalAlloc` at `0x180553a01`
- `KERNEL32!LocalAlloc` at `0x180553e43`
- `KERNEL32!LocalAlloc` at `0x180553e91`
- `KERNEL32!CreateDirectoryW` at `0x1805539bf`
- `KERNEL32!CreateDirectoryW` at `0x1805539bf`
- `KERNEL32!CreateFileW` at `0x180553b80`
- `KERNEL32!CreateFileW` at `0x180553b80`
- `KERNEL32!DeleteFileW` at `0x180553c96`
- `KERNEL32!DeleteFileW` at `0x180553d17`
- `KERNEL32!DeleteFileW` at `0x180553c96`
- `KERNEL32!DeleteFileW` at `0x180553d17`
- `KERNEL32!GetFileAttributesW` at `0x18055386e`
- `KERNEL32!GetFileAttributesW` at `0x18055386e`
- `KERNEL32!SetFileAttributesW` at `0x1805539d4`
- `KERNEL32!SetFileAttributesW` at `0x1805539d4`
- `KERNEL32!SetFilePointer` at `0x180553c6b`
- `KERNEL32!SetFilePointer` at `0x180553d5b`
- `KERNEL32!SetFilePointer` at `0x180553c6b`
- `KERNEL32!SetFilePointer` at `0x180553d5b`
- `KERNEL32!SetEndOfFile` at `0x180553ced`
- `KERNEL32!SetEndOfFile` at `0x180553ced`

## pseudocode

```c
__int64 __fastcall W32DrDeviceAsync::AsyncMsgIrpCreateFunc(ThreadPool **this, unsigned int **a2)
{
  unsigned int *v2; // r15
  struct W32DRDEV_ASYNCIO_PARAMS *v3; // rbx
  WCHAR *v5; // r13
  unsigned int v6; // eax
  DWORD LastError; // r14d
  char v8; // r15
  unsigned int v9; // r13d
  int v10; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 (__fastcall *v12)(ThreadPool **, __int64, __int64, int *); // r13
  __int64 v13; // r8
  DWORD v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  HKEY v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v22; // r15d
  DrFSFile *v23; // rax
  DrFSFile *v24; // rax
  DrFSFile *v25; // r15
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rdx
  HANDLE FileW; // rax
  char v31; // bl
  unsigned int v32; // edi
  unsigned int v33; // eax
  int v34; // edx
  int v35; // r8d
  unsigned int v36; // ecx
  LONG v37; // edx
  LONG *v38; // r8
  HANDLE v39; // r15
  char v40; // bl
  unsigned int v41; // edi
  unsigned int v42; // eax
  int v43; // edx
  int v44; // r8d
  unsigned int v45; // eax
  ThreadPool *v46; // rcx
  DrFSFile *v47; // rax
  _DWORD *v48; // rbx
  struct W32DRDEV_ASYNCIO_PARAMS *v49; // r15
  __int64 v50; // rax
  unsigned int v51; // eax
  __int64 v52; // rdx
  struct tagRDPDR_IOCOMPLETION_PACKET *v53; // rdi
  int v54; // eax
  __int64 v55; // rax
  unsigned int v56; // eax
  unsigned int v57; // eax
  void *v58; // rdx
  void *v59; // rcx
  DWORD dwDesiredAccess; // [rsp+60h] [rbp-68h]
  DWORD dwDesiredAccessa; // [rsp+60h] [rbp-68h]
  int v63; // [rsp+64h] [rbp-64h]
  DWORD FileAttributesW; // [rsp+68h] [rbp-60h]
  BOOL v65; // [rsp+6Ch] [rbp-5Ch]
  int v66; // [rsp+70h] [rbp-58h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp-50h]
  DWORD dwFlagsAndAttributes; // [rsp+D0h] [rbp+8h] BYREF
  struct W32DRDEV_ASYNCIO_PARAMS *v69; // [rsp+D8h] [rbp+10h]
  DWORD dwCreationDisposition; // [rsp+E0h] [rbp+18h]
  unsigned int UniqueObjectID; // [rsp+E8h] [rbp+20h]

  v69 = (struct W32DRDEV_ASYNCIO_PARAMS *)a2;
  v2 = a2[3];
  dwFlagsAndAttributes = 0;
  v3 = (struct W32DRDEV_ASYNCIO_PARAMS *)a2;
  v66 = 0;
  UniqueObjectID = 0;
  v65 = 0;
  dwFlagsAndAttributes = v2[9] & 0xBFFFFFFF;
  if ( (*((unsigned int (__fastcall **)(ThreadPool **))*this + 27))(this) != 32 )
  {
    LastError = 0;
    SetErrorMode(0x8001u);
    if ( (*((unsigned int (__fastcall **)(ThreadPool **))*this + 27))(this) != 8 )
    {
      v9 = v2[13];
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v10 = (*((__int64 (__fastcall **)(ThreadPool **))*this + 27))(this);
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DLD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids,
            CurrentThreadActivityIdPrefix,
            v10,
            v9);
          v3 = v69;
        }
      }
    }
    v12 = (__int64 (__fastcall *)(ThreadPool **, __int64, __int64, int *))*((_QWORD *)*this + 34);
    if ( (*((unsigned int (__fastcall **)(ThreadPool **))*this + 27))(this) == 8 )
      v13 = v2[13];
    else
      v13 = 0;
    v5 = (WCHAR *)v12(this, *((_QWORD *)v3 + 3) + 56LL, v13, &v66);
    if ( !v5 )
      goto LABEL_143;
    dwDesiredAccess = (*((__int64 (__fastcall **)(ThreadPool **, _QWORD))*this + 36))(this, v2[6]);
    v14 = (*((__int64 (__fastcall **)(ThreadPool **, _QWORD))*this + 35))(this, v2[11]);
    v15 = v2[12];
    dwCreationDisposition = v14;
    v16 = (*((__int64 (__fastcall **)(ThreadPool **, __int64))*this + 37))(this, v15);
    dwFlagsAndAttributes |= v16;
    if ( (*((unsigned int (__fastcall **)(ThreadPool **))*this + 27))(this) == 8 )
    {
      FileAttributesW = GetFileAttributesW(v5);
      v63 = (*((__int64 (__fastcall **)(ThreadPool **, _QWORD, _QWORD, _QWORD, DWORD *))*this + 38))(
              this,
              dwDesiredAccess,
              v2[12],
              FileAttributesW,
              &dwFlagsAndAttributes);
      if ( (unsigned int)IsDosDevice(v5) || (unsigned int)IsNTFSReservedFileName(v5) )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
        {
          if ( ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids, v19);
            v18 = WPP_GLOBAL_Control;
          }
          if ( v18 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v18[7] & 1) != 0 && *((_BYTE *)v18 + 25) >= 3u )
          {
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              37,
              (unsigned int)&WPP_b2038507c5143dd517d306a84fe7a284_Traceguids,
              v20,
              (__int64)v5);
          }
        }
        LastError = 5;
        goto LABEL_24;
      }
      v17 = FileAttributesW;
      if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 && v63 )
      {
        LastError = 267;
        goto LABEL_24;
      }
    }
    else
    {
      v63 = 0;
      v17 = -1;
      FileAttributesW = -1;
    }
    if ( (v2[12] & 1) != 0 && (dwCreationDisposition == 4 ? v17 == -1 : dwCreationDisposition == 1) )
    {
      if ( !CreateDirectoryW(v5, 0) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_24;
        }
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 48;
        goto LABEL_84;
      }
      if ( SetFileAttributesW(v5, v2[9]) )
      {
        UniqueObjectID = DrObjectMgr<DrFile>::GetUniqueObjectID(*(_QWORD *)(*((_QWORD *)v3 + 2) + 64LL));
        v22 = UniqueObjectID;
        v23 = (DrFSFile *)LocalAlloc(0x40u, 0x90u);
        if ( !v23
          || (v24 = DrFSFile::DrFSFile(v23, *((struct DrDevice **)v3 + 2), v22, (void *)0xFFFFFFFFFFFFFFFFLL, 1, v5),
              (v25 = v24) == 0) )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids, v27);
          }
          goto LABEL_141;
        }
        if ( (unsigned int)DrObjectMgr<DrDevice>::AddObject(*(_QWORD *)(*((_QWORD *)v3 + 2) + 64LL), v24) )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids, v26);
          }
          (**(void (__fastcall ***)(DrFSFile *, __int64))v25)(v25, 1);
          goto LABEL_141;
        }
        goto LABEL_24;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 47;
LABEL_84:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v29,
          &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids,
          v28,
          LastError);
      }
LABEL_24:
      v3 = v69;
      if ( dwCreationDisposition == 2 )
        v8 = 3;
      else
        v8 = dwCreationDisposition == 4;
      goto LABEL_125;
    }
    FileW = CreateFileW(v5, dwDesiredAccess, v2[10] & 0xFFFFFFFB, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
    hFile = FileW;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v31 = dwFlagsAndAttributes;
      v32 = v2[10] & 0xFFFFFFFB;
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DDSDDDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v34,
        v35,
        v33,
        (char)hFile,
        (__int64)v5,
        dwDesiredAccess,
        v32,
        dwCreationDisposition,
        v31);
      FileW = hFile;
      v3 = v69;
    }
    if ( FileW == (HANDLE)-1LL )
    {
      if ( !v63 )
      {
        LastError = GetLastError();
        if ( LastError == 5 && FileAttributesW != -1 )
          v65 = (FileAttributesW & 0x10) != 0;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v40 = dwFlagsAndAttributes;
          v41 = v2[10] & 0xFFFFFFFB;
          v42 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSDDDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v43,
            v44,
            v42,
            (__int64)v5,
            dwDesiredAccess,
            v41,
            dwCreationDisposition,
            v40,
            LastError);
        }
        goto LABEL_24;
      }
    }
    else if ( v2[7] || v2[8] )
    {
      v36 = v2[11];
      if ( (v36 & 6) != 0 && (v2[12] & 1) == 0 )
      {
        if ( (v36 & 2) != 0 || (dwDesiredAccessa = 0, (v36 & 4) != 0) && GetLastError() != 183 )
          dwDesiredAccessa = 1;
        v37 = v2[7];
        v38 = (LONG *)(v2 + 8);
        v39 = hFile;
        if ( SetFilePointer(hFile, v37, v38, 0) == -1 )
        {
          LastError = GetLastError();
          if ( LastError )
          {
            CloseHandle(v39);
            if ( dwDesiredAccessa )
              DeleteFileW(v5);
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            {
              goto LABEL_24;
            }
            v28 = RdpWppGetCurrentThreadActivityIdPrefix();
            v29 = 39;
            goto LABEL_84;
          }
        }
        if ( !SetEndOfFile(v39) )
        {
          LastError = GetLastError();
          if ( LastError )
          {
            CloseHandle(v39);
            if ( dwDesiredAccessa )
              DeleteFileW(v5);
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            {
              goto LABEL_24;
            }
            v28 = RdpWppGetCurrentThreadActivityIdPrefix();
            v29 = 40;
            goto LABEL_84;
          }
        }
        SetFilePointer(v39, 0, 0, 0);
LABEL_103:
        v45 = DrObjectMgr<DrFile>::GetUniqueObjectID(*(_QWORD *)(*((_QWORD *)v3 + 2) + 64LL));
        v46 = *this;
        UniqueObjectID = v45;
        if ( (*((unsigned int (__fastcall **)(ThreadPool **))v46 + 27))(this) == 8 )
        {
          v47 = (DrFSFile *)LocalAlloc(0x40u, 0x90u);
          if ( v47 )
            v48 = DrFSFile::DrFSFile(v47, *((struct DrDevice **)v3 + 2), UniqueObjectID, v39, v63, v5);
          else
            v48 = 0;
          if ( v48 )
          {
            v49 = v69;
            goto LABEL_111;
          }
        }
        else
        {
          v48 = LocalAlloc(0x40u, 0x68u);
          if ( v48 )
          {
            v49 = v69;
            v50 = *((_QWORD *)v69 + 2);
            *(_QWORD *)v48 = &DrFile::`vftable';
            v48[6] = UniqueObjectID;
            *((_QWORD *)v48 + 4) = hFile;
            v48[2] = 1;
            v48[4] = 0;
            *((_QWORD *)v48 + 5) = v50;
            v48[12] = 0;
            v48[24] = 0;
LABEL_111:
            if ( (unsigned int)DrFile::Initialize((DrFile *)v48) )
            {
              if ( (*((unsigned int (__fastcall **)(ThreadPool **, _DWORD *))*this + 39))(this, v48) )
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_112;
                }
                v51 = RdpWppGetCurrentThreadActivityIdPrefix();
                v52 = 41;
              }
              else
              {
                if ( !(unsigned int)DrObjectMgr<DrDevice>::AddObject(*(_QWORD *)(*((_QWORD *)v49 + 2) + 64LL), v48) )
                  goto LABEL_24;
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_112;
                }
                v51 = RdpWppGetCurrentThreadActivityIdPrefix();
                v52 = 42;
              }
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v52, &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids, v51);
            }
LABEL_112:
            (**(void (__fastcall ***)(void *, __int64))v48)(v48, 1);
LABEL_140:
            v3 = v69;
LABEL_141:
            if ( v66 )
              operator delete(v5);
            goto LABEL_143;
          }
        }
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v57 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids, v57);
        }
        goto LABEL_140;
      }
    }
    v39 = hFile;
    goto LABEL_103;
  }
  v5 = 0;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids, v6);
  }
  LastError = 5;
  v8 = 0;
LABEL_125:
  v53 = DrUTL_AllocIOCompletePacket(*((struct tagRDPDR_IOREQUEST_PACKET *const *)v3 + 3), 0x15u);
  if ( v53 )
  {
    *((_DWORD *)v53 + 4) = UniqueObjectID;
    *((_BYTE *)v53 + 20) = v8;
    if ( v65 )
      v54 = -1073741638;
    else
      v54 = TranslateWinError(LastError);
    *((_DWORD *)v53 + 3) = v54;
    v55 = (*((__int64 (__fastcall **)(ThreadPool **))*this + 30))(this);
    VCManager::ChannelWrite(*(VCManager **)(v55 + 224), v53, 0x15u);
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v56 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_b2038507c5143dd517d306a84fe7a284_Traceguids, v56, 21);
  }
  if ( v5 )
    goto LABEL_141;
LABEL_143:
  v58 = (void *)*((_QWORD *)v3 + 7);
  if ( v58 )
  {
    ThreadPool::CloseRequest(this[78], v58);
    *((_QWORD *)v3 + 7) = 0;
  }
  v59 = (void *)*((_QWORD *)v3 + 3);
  if ( v59 )
  {
    operator delete(v59);
    *((_QWORD *)v3 + 3) = 0;
  }
  W32DRDEV_ASYNCIO_PARAMS::`vector deleting destructor'(v3, 1u);
  return LastError;
}

```

## disassembly

```asm
0x180553660  mov     r11, rsp
0x180553663  mov     [r11+10h], rdx
0x180553667  push    rbx
0x180553668  push    rbp
0x180553669  push    rsi
0x18055366a  push    rdi
0x18055366b  push    r12
0x18055366d  push    r13
0x18055366f  push    r14
0x180553671  push    r15
0x180553673  sub     rsp, 88h
0x18055367a  mov     r15, [rdx+18h]
0x18055367e  xor     edi, edi
0x180553680  mov     [r11+8], edi
0x180553684  mov     rbx, rdx
0x180553687  mov     [rsp+0C8h+var_58], edi
0x18055368b  mov     r12, rcx
0x18055368e  mov     [rsp+0C8h+arg_18], edi
0x180553695  mov     eax, [r15+24h]
0x180553699  btr     eax, 1Eh
0x18055369d  mov     [rsp+0C8h+var_5C], edi
0x1805536a1  mov     [r11+8], eax
0x1805536a5  mov     rax, [rcx]
0x1805536a8  mov     rax, [rax+0D8h]
0x1805536af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805536b4  cmp     eax, 20h ; ' '
0x1805536b7  jnz     short loc_18055370E
0x1805536b9  mov     r13d, edi
0x1805536bc  mov     rax, cs:WPP_GLOBAL_Control
0x1805536c3  lea     rbp, WPP_GLOBAL_Control
0x1805536ca  lea     esi, [rdi+1]
0x1805536cd  cmp     rax, rbp
0x1805536d0  jz      short loc_180553700
0x1805536d2  test    [rax+1Ch], sil
0x1805536d6  jz      short loc_180553700
0x1805536d8  cmp     byte ptr [rax+19h], 2
0x1805536dc  jb      short loc_180553700
0x1805536de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805536e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1805536ea  lea     edx, [rdi+22h]
0x1805536ed  mov     r9d, eax
0x1805536f0  lea     r8, WPP_b2038507c5143dd517d306a84fe7a284_Traceguids
0x1805536f7  mov     rcx, [rcx+10h]
0x1805536fb  call    WPP_SF_d
0x180553700  mov     r14d, 5
0x180553706  mov     r15d, edi
0x180553709  jmp     loc_180553FAF
0x18055370e  mov     ecx, 8001h; uMode
0x180553713  mov     r14d, edi
0x180553716  call    cs:__imp_SetErrorMode
0x18055371c  mov     rax, [r12]
0x180553720  mov     rcx, r12
0x180553723  mov     rax, [rax+0D8h]
0x18055372a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055372f  lea     rdi, WPP_b2038507c5143dd517d306a84fe7a284_Traceguids
0x180553736  mov     esi, 1
0x18055373b  lea     rbp, WPP_GLOBAL_Control
0x180553742  cmp     eax, 8
0x180553745  jz      short loc_1805537AC
0x180553747  mov     r13d, [r15+34h]
0x18055374b  test    r13d, r13d
0x18055374e  jz      short loc_1805537AC
0x180553750  mov     rax, cs:WPP_GLOBAL_Control
0x180553757  cmp     rax, rbp
0x18055375a  jz      short loc_1805537AC
0x18055375c  test    [rax+1Ch], sil
0x180553760  jz      short loc_1805537AC
0x180553762  cmp     byte ptr [rax+19h], 5
0x180553766  jb      short loc_1805537AC
0x180553768  mov     rax, [r12]
0x18055376c  mov     rcx, r12
0x18055376f  mov     rax, [rax+0D8h]
0x180553776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055377b  mov     ebx, eax
0x18055377d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180553782  mov     rcx, cs:WPP_GLOBAL_Control
0x180553789  lea     edx, [rsi+22h]
0x18055378c  mov     [rsp+0C8h+dwFlagsAndAttributes], r13d
0x180553791  mov     r9d, eax
0x180553794  mov     r8, rdi
0x180553797  mov     [rsp+0C8h+dwCreationDisposition], ebx
0x18055379b  mov     rcx, [rcx+10h]
0x18055379f  call    WPP_SF_DLD
0x1805537a4  mov     rbx, [rsp+0C8h+arg_8]
0x1805537ac  mov     rax, [r12]
0x1805537b0  mov     rcx, r12
0x1805537b3  mov     r13, [rax+110h]
0x1805537ba  mov     rax, [rax+0D8h]
0x1805537c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805537c6  cmp     eax, 8
0x1805537c9  jnz     short loc_1805537D1
0x1805537cb  mov     r8d, [r15+34h]
0x1805537cf  jmp     short loc_1805537D4
0x1805537d1  xor     r8d, r8d
0x1805537d4  mov     rdx, [rbx+18h]
0x1805537d8  lea     r9, [rsp+0C8h+var_58]
0x1805537dd  add     rdx, 38h ; '8'
0x1805537e1  mov     rcx, r12
0x1805537e4  mov     rax, r13
0x1805537e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805537ec  mov     r13, rax
0x1805537ef  test    rax, rax
0x1805537f2  jz      loc_1805540B0
0x1805537f8  mov     rax, [r12]
0x1805537fc  mov     rcx, r12
0x1805537ff  mov     edx, [r15+18h]
0x180553803  mov     rax, [rax+120h]
0x18055380a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055380f  mov     edx, [r15+2Ch]
0x180553813  mov     rcx, r12
0x180553816  mov     [rsp+0C8h+dwDesiredAccess], eax
0x18055381a  mov     rax, [r12]
0x18055381e  mov     rax, [rax+118h]
0x180553825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055382a  mov     edx, [r15+30h]
0x18055382e  mov     rcx, r12
0x180553831  mov     [rsp+0C8h+arg_10], eax
0x180553838  mov     rax, [r12]
0x18055383c  mov     rax, [rax+128h]
0x180553843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180553848  or      [rsp+0C8h+arg_0], eax
0x18055384f  mov     rcx, r12
0x180553852  mov     rax, [r12]
0x180553856  mov     rax, [rax+0D8h]
0x18055385d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180553862  cmp     eax, 8
0x180553865  jnz     loc_18055398A
0x18055386b  mov     rcx, r13; lpFileName
0x18055386e  call    cs:__imp_GetFileAttributesW
0x180553874  mov     r8d, [r15+30h]
0x180553878  lea     rdx, [rsp+0C8h+arg_0]
0x180553880  mov     ecx, eax
0x180553882  mov     [rsp+0C8h+var_60], eax
0x180553886  mov     rax, [r12]
0x18055388a  mov     r9d, ecx
0x18055388d  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rdx
0x180553892  mov     rcx, r12
0x180553895  mov     edx, [rsp+0C8h+dwDesiredAccess]
0x180553899  mov     rax, [rax+130h]
0x1805538a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805538a5  mov     rcx, r13; unsigned __int16 *
0x1805538a8  mov     [rsp+0C8h+var_64], eax
0x1805538ac  call    ?IsDosDevice@@YAHPEAG@Z; IsDosDevice(ushort *)
0x1805538b1  test    eax, eax
0x1805538b3  jnz     short loc_18055390A
0x1805538b5  mov     rcx, r13; unsigned __int16 *
0x1805538b8  call    ?IsNTFSReservedFileName@@YAHPEAG@Z; IsNTFSReservedFileName(ushort *)
0x1805538bd  test    eax, eax
0x1805538bf  jnz     short loc_18055390A
0x1805538c1  mov     eax, [rsp+0C8h+var_60]
0x1805538c5  or      ecx, 0FFFFFFFFh
0x1805538c8  cmp     eax, ecx
0x1805538ca  jz      loc_180553998
0x1805538d0  test    al, 10h
0x1805538d2  jnz     loc_180553998
0x1805538d8  cmp     [rsp+0C8h+var_64], r14d
0x1805538dd  jz      loc_180553998
0x1805538e3  mov     r14d, 10Bh
0x1805538e9  mov     eax, [rsp+0C8h+arg_10]
0x1805538f0  mov     rbx, [rsp+0C8h+arg_8]
0x1805538f8  cmp     eax, 2
0x1805538fb  jnz     loc_180553FA5
0x180553901  lea     r15d, [rax+1]
0x180553905  jmp     loc_180553FAF
0x18055390a  mov     rax, cs:WPP_GLOBAL_Control
0x180553911  cmp     rax, rbp
0x180553914  jz      short loc_18055397F
0x180553916  test    [rax+1Ch], sil
0x18055391a  jz      short loc_180553949
0x18055391c  cmp     byte ptr [rax+19h], 2
0x180553920  jb      short loc_180553949
0x180553922  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180553927  mov     rcx, cs:WPP_GLOBAL_Control
0x18055392e  mov     edx, 24h ; '$'
0x180553933  mov     r9d, eax
0x180553936  mov     r8, rdi
0x180553939  mov     rcx, [rcx+10h]
0x18055393d  call    WPP_SF_d
0x180553942  mov     rax, cs:WPP_GLOBAL_Control
0x180553949  cmp     rax, rbp
0x18055394c  jz      short loc_18055397F
0x18055394e  test    [rax+1Ch], sil
0x180553952  jz      short loc_18055397F
0x180553954  cmp     byte ptr [rax+19h], 3
0x180553958  jb      short loc_18055397F
0x18055395a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055395f  mov     rcx, cs:WPP_GLOBAL_Control
0x180553966  mov     edx, 25h ; '%'
0x18055396b  mov     r9d, eax
0x18055396e  mov     qword ptr [rsp+0C8h+dwCreationDisposition], r13
0x180553973  mov     r8, rdi
0x180553976  mov     rcx, [rcx+10h]
0x18055397a  call    WPP_SF_DS
0x18055397f  mov     r14d, 5
0x180553985  jmp     loc_1805538E9
0x18055398a  or      ecx, 0FFFFFFFFh
0x18055398d  mov     [rsp+0C8h+var_64], r14d
0x180553992  mov     eax, ecx
0x180553994  mov     [rsp+0C8h+var_60], ecx
0x180553998  mov     edx, [rsp+0C8h+arg_10]
0x18055399f  test    [r15+30h], sil
0x1805539a3  jz      loc_180553B5A
0x1805539a9  cmp     edx, 4
0x1805539ac  jnz     short loc_1805539B2
0x1805539ae  cmp     eax, ecx
0x1805539b0  jmp     short loc_1805539B4
0x1805539b2  cmp     edx, esi
0x1805539b4  jnz     loc_180553B5A
0x1805539ba  xor     edx, edx; lpSecurityAttributes
0x1805539bc  mov     rcx, r13; lpPathName
0x1805539bf  call    cs:__imp_CreateDirectoryW
0x1805539c5  test    eax, eax
0x1805539c7  jz      loc_180553B1E
0x1805539cd  mov     edx, [r15+24h]; dwFileAttributes
0x1805539d1  mov     rcx, r13; lpFileName
0x1805539d4  call    cs:__imp_SetFileAttributesW
0x1805539da  test    eax, eax
0x1805539dc  jz      loc_180553AE2
0x1805539e2  mov     rcx, [rbx+10h]
0x1805539e6  mov     rcx, [rcx+40h]
0x1805539ea  call    ?GetUniqueObjectID@?$DrObjectMgr@VDrFile@@@@QEAAKXZ; DrObjectMgr<DrFile>::GetUniqueObjectID(void)
0x1805539ef  mov     edx, 90h; uBytes
0x1805539f4  mov     [rsp+0C8h+arg_18], eax
0x1805539fb  mov     r15d, eax
0x1805539fe  lea     ecx, [rdx-50h]; uFlags
0x180553a01  call    cs:__imp_LocalAlloc
0x180553a07  test    rax, rax
0x180553a0a  jz      loc_180553A99
0x180553a10  mov     rdx, [rbx+10h]; struct DrDevice *
0x180553a14  or      r9, 0FFFFFFFFFFFFFFFFh; void *
0x180553a18  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180553a1d  mov     r8d, r15d; unsigned int
0x180553a20  mov     rcx, rax; this
0x180553a23  mov     [rsp+0C8h+dwCreationDisposition], esi; int
0x180553a27  call    ??0DrFSFile@@QEAA@PEAVDrDevice@@KPEAXHPEBG@Z; DrFSFile::DrFSFile(DrDevice *,ulong,void *,int,ushort const *)
0x180553a2c  mov     r15, rax
0x180553a2f  test    rax, rax
0x180553a32  jz      short loc_180553A99
0x180553a34  mov     rcx, [rbx+10h]
0x180553a38  mov     rdx, rax
0x180553a3b  mov     rcx, [rcx+40h]
0x180553a3f  call    ?AddObject@?$DrObjectMgr@VDrDevice@@@@QEAAKPEAVDrDevice@@@Z; DrObjectMgr<DrDevice>::AddObject(DrDevice *)
0x180553a44  test    eax, eax
0x180553a46  jz      loc_1805538E9
0x180553a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180553a53  cmp     rcx, rbp
0x180553a56  jz      short loc_180553A84
0x180553a58  test    [rcx+1Ch], sil
0x180553a5c  jz      short loc_180553A84
0x180553a5e  cmp     byte ptr [rcx+19h], 2
0x180553a62  jb      short loc_180553A84
0x180553a64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180553a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180553a70  mov     edx, 2Dh ; '-'
0x180553a75  mov     r9d, eax
0x180553a78  mov     r8, rdi
0x180553a7b  mov     rcx, [rcx+10h]
0x180553a7f  call    WPP_SF_d
0x180553a84  mov     rax, [r15]
0x180553a87  mov     edx, esi
0x180553a89  mov     rcx, r15
0x180553a8c  mov     rax, [rax]
0x180553a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180553a94  jmp     loc_1805540A1
0x180553a99  mov     rax, cs:WPP_GLOBAL_Control
0x180553aa0  cmp     rax, rbp
0x180553aa3  jz      loc_1805540A1
0x180553aa9  test    [rax+1Ch], sil
0x180553aad  jz      loc_1805540A1
0x180553ab3  cmp     byte ptr [rax+19h], 2
0x180553ab7  jb      loc_1805540A1
0x180553abd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180553ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x180553ac9  mov     edx, 2Eh ; '.'
0x180553ace  mov     r9d, eax
0x180553ad1  mov     r8, rdi
0x180553ad4  mov     rcx, [rcx+10h]
0x180553ad8  call    WPP_SF_d
0x180553add  jmp     loc_1805540A1
0x180553ae2  call    cs:__imp_GetLastError
0x180553ae8  mov     r14d, eax
0x180553aeb  mov     rax, cs:WPP_GLOBAL_Control
0x180553af2  cmp     rax, rbp
0x180553af5  jz      loc_1805538E9
0x180553afb  test    [rax+1Ch], sil
0x180553aff  jz      loc_1805538E9
0x180553b05  cmp     byte ptr [rax+19h], 4
0x180553b09  jb      loc_1805538E9
0x180553b0f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180553b14  mov     edx, 2Fh ; '/'
0x180553b19  jmp     loc_180553CCA
0x180553b1e  call    cs:__imp_GetLastError
0x180553b24  mov     r14d, eax
0x180553b27  mov     rax, cs:WPP_GLOBAL_Control
0x180553b2e  cmp     rax, rbp
0x180553b31  jz      loc_1805538E9
0x180553b37  test    [rax+1Ch], sil
0x180553b3b  jz      loc_1805538E9
0x180553b41  cmp     byte ptr [rax+19h], 4
0x180553b45  jb      loc_1805538E9
  ... truncated ...
```
