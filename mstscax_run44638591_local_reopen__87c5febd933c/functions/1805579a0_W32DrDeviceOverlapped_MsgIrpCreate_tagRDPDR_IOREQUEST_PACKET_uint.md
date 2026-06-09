# W32DrDeviceOverlapped::MsgIrpCreate(tagRDPDR_IOREQUEST_PACKET *,uint)

- ea: `0x1805579a0`
- end: `0x1805581be`
- name: `?MsgIrpCreate@W32DrDeviceOverlapped@@MEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@I@Z`
- size: `2078`
- prototype: `void __fastcall(W32DrDeviceOverlapped *__hidden this, struct tagRDPDR_IOREQUEST_PACKET *, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800745a4`
- `0x1800ebae0`
- `0x1800f7748`
- `0x1800f95a8`
- `0x18012966c`
- `0x180548f44`
- `0x1805520c8`
- `0x180554ec0`
- `0x1805557dc`
- `0x180557778`
- `0x180557904`
- `0x1805579a0`
- `0x180558ed0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x1805579d7`
- `KERNEL32!SetErrorMode` at `0x1805579d7`
- `KERNEL32!GetLastError` at `0x180557e13`
- `KERNEL32!GetLastError` at `0x180557e72`
- `KERNEL32!GetLastError` at `0x180557ef0`
- `KERNEL32!GetLastError` at `0x180557e13`
- `KERNEL32!GetLastError` at `0x180557e72`
- `KERNEL32!GetLastError` at `0x180557ef0`
- `KERNEL32!LocalAlloc` at `0x180557d4c`
- `KERNEL32!LocalAlloc` at `0x180557f7a`
- `KERNEL32!LocalAlloc` at `0x180558014`
- `KERNEL32!LocalAlloc` at `0x180557d4c`
- `KERNEL32!LocalAlloc` at `0x180557f7a`
- `KERNEL32!LocalAlloc` at `0x180558014`
- `KERNEL32!CreateDirectoryW` at `0x180557d11`
- `KERNEL32!CreateDirectoryW` at `0x180557d11`
- `KERNEL32!CreateFileW` at `0x180557ed5`
- `KERNEL32!CreateFileW` at `0x180557ed5`
- `KERNEL32!GetFileAttributesW` at `0x180557b63`
- `KERNEL32!GetFileAttributesW` at `0x180557b63`
- `KERNEL32!SetFileAttributesW` at `0x180557d26`
- `KERNEL32!SetFileAttributesW` at `0x180557d26`

## pseudocode

```c
void __fastcall W32DrDeviceOverlapped::MsgIrpCreate(
        W32DrDeviceOverlapped *this,
        struct tagRDPDR_IOREQUEST_PACKET *a2,
        unsigned int a3)
{
  unsigned __int64 v4; // rbx
  DWORD LastError; // r12d
  int v7; // r14d
  int v8; // ebx
  unsigned int v9; // eax
  __int64 (__fastcall *v10)(W32DrDeviceOverlapped *, char *, __int64, int *); // rbx
  __int64 v11; // r8
  WCHAR *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rcx
  DWORD FileAttributesW; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  struct tagRDPDR_IOCOMPLETION_PACKET *v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rax
  HKEY v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // eax
  DrFSFile *v27; // rax
  DrFSFile *v28; // rax
  DrFSFile *v29; // rbx
  unsigned int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rdx
  unsigned int v33; // eax
  __int64 v34; // rdx
  unsigned int v35; // eax
  unsigned int v36; // eax
  __int64 v37; // rcx
  DrFSFile *v38; // rcx
  DrFSFile *v39; // rax
  unsigned int v40; // edx
  unsigned int v41; // eax
  __int64 v42; // rdx
  unsigned int v43; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD dwCreationDisposition; // [rsp+40h] [rbp-58h]
  char v46; // [rsp+44h] [rbp-54h]
  DWORD dwDesiredAccess; // [rsp+48h] [rbp-50h]
  int v48; // [rsp+4Ch] [rbp-4Ch] BYREF
  void *FileW; // [rsp+50h] [rbp-48h]
  void *Block; // [rsp+58h] [rbp-40h]
  DWORD dwFlagsAndAttributes; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int UniqueObjectID; // [rsp+B0h] [rbp+18h]
  void *v53; // [rsp+B8h] [rbp+20h]

  v4 = a3;
  dwFlagsAndAttributes = *((_DWORD *)a2 + 9) | 0x40000000;
  v48 = 0;
  SetErrorMode(0x8001u);
  if ( *((_DWORD *)a2 + 13) > (unsigned int)v4 || (unsigned __int64)*((unsigned int *)a2 + 13) + 56 > v4 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
  else
  {
    LastError = 5;
    if ( (*(unsigned int (__fastcall **)(W32DrDeviceOverlapped *))(*(_QWORD *)this + 216LL))(this) != 8 )
    {
      v7 = *((_DWORD *)a2 + 13);
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v8 = (*(__int64 (__fastcall **)(W32DrDeviceOverlapped *))(*(_QWORD *)this + 216LL))(this);
          v9 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DLD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids,
            v9,
            v8,
            v7);
        }
      }
    }
    v10 = *(__int64 (__fastcall **)(W32DrDeviceOverlapped *, char *, __int64, int *))(*(_QWORD *)this + 272LL);
    if ( (*(unsigned int (__fastcall **)(W32DrDeviceOverlapped *))(*(_QWORD *)this + 216LL))(this) == 8 )
      v11 = *((unsigned int *)a2 + 13);
    else
      v11 = 0;
    Block = (void *)v10(this, (char *)a2 + 56, v11, &v48);
    v12 = (WCHAR *)Block;
    if ( Block )
    {
      v13 = *(_QWORD *)this;
      v14 = *((unsigned int *)a2 + 6);
      UniqueObjectID = 0;
      LODWORD(v53) = 0;
      dwDesiredAccess = (*(__int64 (__fastcall **)(W32DrDeviceOverlapped *, __int64))(v13 + 288))(this, v14);
      dwCreationDisposition = (*(__int64 (__fastcall **)(W32DrDeviceOverlapped *, _QWORD))(*(_QWORD *)this + 280LL))(
                                this,
                                *((unsigned int *)a2 + 11));
      v15 = (*(__int64 (__fastcall **)(W32DrDeviceOverlapped *, _QWORD))(*(_QWORD *)this + 296LL))(
              this,
              *((unsigned int *)a2 + 12));
      v16 = *(_QWORD *)this;
      dwFlagsAndAttributes |= v15;
      v46 = 3;
      if ( (*(unsigned int (__fastcall **)(W32DrDeviceOverlapped *))(v16 + 216))(this) == 8 )
      {
        FileAttributesW = GetFileAttributesW(v12);
        v18 = *(_QWORD *)this;
        v19 = *((unsigned int *)a2 + 12);
        LODWORD(FileW) = FileAttributesW;
        LODWORD(v53) = (*(__int64 (__fastcall **)(W32DrDeviceOverlapped *, _QWORD, __int64, _QWORD, DWORD *))(v18 + 304))(
                         this,
                         dwDesiredAccess,
                         v19,
                         FileAttributesW,
                         &dwFlagsAndAttributes);
        if ( (unsigned int)IsDosDevice(v12) || (unsigned int)IsNTFSReservedFileName(v12) )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
          {
            if ( ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v25 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids, v25);
              v24 = WPP_GLOBAL_Control;
            }
            if ( v24 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v24[7] & 1) != 0 && *((_BYTE *)v24 + 25) >= 3u )
            {
              v26 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                (unsigned int)WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids,
                v26,
                (__int64)v12);
            }
          }
LABEL_20:
          if ( dwCreationDisposition == 2 )
            goto LABEL_22;
          goto LABEL_21;
        }
        if ( (_DWORD)FileW != -1 && ((unsigned __int8)FileW & 0x10) == 0 && (_DWORD)v53 )
        {
          LastError = 267;
          goto LABEL_20;
        }
      }
      LastError = 0;
      if ( (*((_BYTE *)a2 + 48) & 1) != 0 && dwCreationDisposition == 1 )
      {
        if ( CreateDirectoryW(v12, 0) )
        {
          if ( SetFileAttributesW(v12, *((_DWORD *)a2 + 9)) )
          {
            UniqueObjectID = DrObjectMgr<DrFile>::GetUniqueObjectID(*((_QWORD *)this + 8));
            v27 = (DrFSFile *)LocalAlloc(0x40u, 0x90u);
            if ( v27 )
            {
              v28 = DrFSFile::DrFSFile(v27, this, UniqueObjectID, (void *)0xFFFFFFFFFFFFFFFFLL, 1, v12);
              v29 = v28;
              if ( v28 )
              {
                if ( (unsigned int)DrObjectMgr<DrDevice>::AddObject(*((_QWORD *)this + 8), v28) )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      21,
                      WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids,
                      v30);
                  }
                  goto LABEL_77;
                }
LABEL_21:
                v46 = dwCreationDisposition == 4;
                goto LABEL_22;
              }
            }
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v31 = RdpWppGetCurrentThreadActivityIdPrefix();
              v32 = 22;
LABEL_71:
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids, v31);
              goto LABEL_72;
            }
            goto LABEL_72;
          }
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_21;
          }
          v33 = RdpWppGetCurrentThreadActivityIdPrefix();
          v34 = 23;
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_21;
          }
          v33 = RdpWppGetCurrentThreadActivityIdPrefix();
          v34 = 24;
        }
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v34,
          WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids,
          v33,
          LastError);
        v46 = 0;
LABEL_22:
        v20 = DrUTL_AllocIOCompletePacket(a2, 0x15u);
        v53 = v20;
        if ( v20 )
        {
          *((_DWORD *)v20 + 4) = UniqueObjectID;
          *((_BYTE *)v20 + 20) = v46;
          v21 = TranslateWinError(LastError);
          *(_DWORD *)(v22 + 12) = v21;
          v23 = (*(__int64 (__fastcall **)(W32DrDeviceOverlapped *))(*(_QWORD *)this + 240LL))(this);
          VCManager::ChannelWriteEx(*(VCManager **)(v23 + 224), v53, 0x15u);
        }
        else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
               && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v43 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids, v43, 21);
        }
        goto LABEL_72;
      }
      FileW = CreateFileW(
                v12,
                dwDesiredAccess,
                *((_DWORD *)a2 + 10) & 0xFFFFFFFB,
                0,
                dwCreationDisposition,
                dwFlagsAndAttributes,
                0);
      if ( FileW == (void *)-1LL && !(_DWORD)v53 )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v35 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids,
            v35,
            LastError);
        }
        goto LABEL_20;
      }
      v36 = DrObjectMgr<DrFile>::GetUniqueObjectID(*((_QWORD *)this + 8));
      v37 = *(_QWORD *)this;
      UniqueObjectID = v36;
      if ( (*(unsigned int (__fastcall **)(W32DrDeviceOverlapped *))(v37 + 216))(this) == 8 )
      {
        v38 = (DrFSFile *)LocalAlloc(0x40u, 0x90u);
        if ( v38 )
          v29 = DrFSFile::DrFSFile(v38, this, UniqueObjectID, FileW, (int)v53, v12);
        else
          v29 = 0;
        if ( !v29 )
        {
LABEL_67:
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v31 = RdpWppGetCurrentThreadActivityIdPrefix();
            v32 = 19;
            goto LABEL_71;
          }
LABEL_72:
          if ( v48 )
            operator delete(Block);
          goto LABEL_97;
        }
      }
      else
      {
        v39 = (DrFSFile *)LocalAlloc(0x40u, 0x68u);
        v29 = v39;
        if ( !v39 )
          goto LABEL_67;
        v40 = UniqueObjectID;
        *((_DWORD *)v39 + 2) = 1;
        *((_DWORD *)v39 + 4) = 0;
        *(_QWORD *)v39 = &DrFile::`vftable';
        *((_QWORD *)v39 + 4) = FileW;
        *((_DWORD *)v39 + 6) = v40;
        *((_QWORD *)v39 + 5) = this;
        *((_DWORD *)v39 + 12) = 0;
        *((_DWORD *)v39 + 24) = 0;
      }
      if ( !(unsigned int)DrFile::Initialize(v29) )
      {
LABEL_77:
        (**(void (__fastcall ***)(DrFSFile *, __int64))v29)(v29, 1);
        goto LABEL_72;
      }
      if ( (*(unsigned int (__fastcall **)(W32DrDeviceOverlapped *, DrFSFile *))(*(_QWORD *)this + 312LL))(this, v29) )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v41 = RdpWppGetCurrentThreadActivityIdPrefix();
        v42 = 17;
      }
      else
      {
        if ( !(unsigned int)DrObjectMgr<DrDevice>::AddObject(*((_QWORD *)this + 8), v29) )
          goto LABEL_20;
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v41 = RdpWppGetCurrentThreadActivityIdPrefix();
        v42 = 18;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v42, WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids, v41);
      goto LABEL_77;
    }
  }
LABEL_97:
  operator delete(a2);
}

```

## disassembly

```asm
0x1805579a0  mov     r11, rsp
0x1805579a3  mov     [r11+8], rbx
0x1805579a7  push    rbp
0x1805579a8  push    rsi
0x1805579a9  push    rdi
0x1805579aa  push    r12
0x1805579ac  push    r13
0x1805579ae  push    r14
0x1805579b0  push    r15
0x1805579b2  sub     rsp, 60h
0x1805579b6  mov     eax, [rdx+24h]
0x1805579b9  mov     rsi, rcx
0x1805579bc  bts     eax, 1Eh
0x1805579c0  mov     ebx, r8d
0x1805579c3  mov     ecx, 8001h; uMode
0x1805579c8  mov     [r11+10h], eax
0x1805579cc  mov     r13, rdx
0x1805579cf  mov     [rsp+98h+var_4C], 0
0x1805579d7  call    cs:__imp_SetErrorMode
0x1805579dd  cmp     [r13+34h], ebx
0x1805579e1  ja      loc_180558154
0x1805579e7  mov     ecx, [r13+34h]
0x1805579eb  add     rcx, 38h ; '8'
0x1805579ef  cmp     rcx, rbx
0x1805579f2  ja      loc_180558154
0x1805579f8  mov     rax, [rsi]
0x1805579fb  mov     rcx, rsi
0x1805579fe  mov     rax, [rax+0D8h]
0x180557a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557a0a  lea     r15, WPP_4a6975e56b8c30cd998da9eeb3054435_Traceguids
0x180557a11  mov     r12d, 5
0x180557a17  lea     rbp, WPP_GLOBAL_Control
0x180557a1e  lea     edi, [r12-4]
0x180557a23  cmp     eax, 8
0x180557a26  jz      short loc_180557A84
0x180557a28  mov     r14d, [r13+34h]
0x180557a2c  test    r14d, r14d
0x180557a2f  jz      short loc_180557A84
0x180557a31  mov     rax, cs:WPP_GLOBAL_Control
0x180557a38  cmp     rax, rbp
0x180557a3b  jz      short loc_180557A84
0x180557a3d  test    [rax+1Ch], dil
0x180557a41  jz      short loc_180557A84
0x180557a43  cmp     [rax+19h], r12b
0x180557a47  jb      short loc_180557A84
0x180557a49  mov     rax, [rsi]
0x180557a4c  mov     rcx, rsi
0x180557a4f  mov     rax, [rax+0D8h]
0x180557a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557a5b  mov     ebx, eax
0x180557a5d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180557a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180557a69  lea     edx, [rdi+0Dh]
0x180557a6c  mov     [rsp+98h+dwFlagsAndAttributes], r14d
0x180557a71  mov     r9d, eax
0x180557a74  mov     r8, r15
0x180557a77  mov     [rsp+98h+dwCreationDisposition], ebx
0x180557a7b  mov     rcx, [rcx+10h]
0x180557a7f  call    WPP_SF_DLD
0x180557a84  mov     rax, [rsi]
0x180557a87  mov     rcx, rsi
0x180557a8a  mov     rbx, [rax+110h]
0x180557a91  mov     rax, [rax+0D8h]
0x180557a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557a9d  cmp     eax, 8
0x180557aa0  jnz     short loc_180557AA8
0x180557aa2  mov     r8d, [r13+34h]
0x180557aa6  jmp     short loc_180557AAB
0x180557aa8  xor     r8d, r8d
0x180557aab  lea     rdx, [r13+38h]
0x180557aaf  mov     rcx, rsi
0x180557ab2  lea     r9, [rsp+98h+var_4C]
0x180557ab7  mov     rax, rbx
0x180557aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557abf  mov     [rsp+98h+Block], rax
0x180557ac4  mov     rbx, rax
0x180557ac7  test    rax, rax
0x180557aca  jz      loc_18055819E
0x180557ad0  mov     rcx, [rsi]
0x180557ad3  mov     edx, [r13+18h]
0x180557ad7  mov     [rsp+98h+arg_10], 0
0x180557ae2  mov     dword ptr [rsp+98h+arg_18], 0
0x180557aed  mov     rax, [rcx+120h]
0x180557af4  mov     rcx, rsi
0x180557af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557afc  mov     rcx, [rsi]
0x180557aff  mov     edx, [r13+2Ch]
0x180557b03  mov     [rsp+98h+dwDesiredAccess], eax
0x180557b07  mov     rax, [rcx+118h]
0x180557b0e  mov     rcx, rsi
0x180557b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557b16  mov     rcx, [rsi]
0x180557b19  mov     edx, [r13+30h]
0x180557b1d  mov     [rsp+98h+var_58], eax
0x180557b21  mov     rax, [rcx+128h]
0x180557b28  mov     rcx, rsi
0x180557b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557b30  mov     rcx, [rsi]
0x180557b33  or      [rsp+98h+arg_8], eax
0x180557b3a  mov     rax, [rcx+0D8h]
0x180557b41  mov     rcx, rsi
0x180557b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557b49  mov     [rsp+98h+var_54], 3
0x180557b51  mov     r14d, 2
0x180557b57  cmp     eax, 8
0x180557b5a  jnz     loc_180557CF5
0x180557b60  mov     rcx, rbx; lpFileName
0x180557b63  call    cs:__imp_GetFileAttributesW
0x180557b69  mov     rcx, [rsi]
0x180557b6c  mov     edx, eax
0x180557b6e  mov     r8d, [r13+30h]
0x180557b72  mov     r9d, edx
0x180557b75  mov     edx, [rsp+98h+dwDesiredAccess]
0x180557b79  mov     dword ptr [rsp+98h+var_48], eax
0x180557b7d  mov     rax, [rcx+130h]
0x180557b84  lea     rcx, [rsp+98h+arg_8]
0x180557b8c  mov     qword ptr [rsp+98h+dwCreationDisposition], rcx
0x180557b91  mov     rcx, rsi
0x180557b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557b99  mov     rcx, rbx; unsigned __int16 *
0x180557b9c  mov     dword ptr [rsp+98h+arg_18], eax
0x180557ba3  call    ?IsDosDevice@@YAHPEAG@Z; IsDosDevice(ushort *)
0x180557ba8  test    eax, eax
0x180557baa  jnz     loc_180557C6B
0x180557bb0  mov     rcx, rbx; unsigned __int16 *
0x180557bb3  call    ?IsNTFSReservedFileName@@YAHPEAG@Z; IsNTFSReservedFileName(ushort *)
0x180557bb8  test    eax, eax
0x180557bba  jnz     loc_180557C6B
0x180557bc0  mov     eax, dword ptr [rsp+98h+var_48]
0x180557bc4  cmp     eax, 0FFFFFFFFh
0x180557bc7  jz      loc_180557CF5
0x180557bcd  test    al, 10h
0x180557bcf  jnz     loc_180557CF5
0x180557bd5  cmp     dword ptr [rsp+98h+arg_18], 0
0x180557bdd  jz      loc_180557CF5
0x180557be3  mov     r12d, 10Bh
0x180557be9  cmp     [rsp+98h+var_58], r14d
0x180557bee  jz      short loc_180557BFE
0x180557bf0  xor     eax, eax
0x180557bf2  cmp     [rsp+98h+var_58], 4
0x180557bf7  cmovz   eax, edi
0x180557bfa  mov     [rsp+98h+var_54], eax
0x180557bfe  mov     ebx, 15h
0x180557c03  mov     rcx, r13; struct tagRDPDR_IOREQUEST_PACKET *
0x180557c06  mov     edx, ebx; unsigned int
0x180557c08  call    ?DrUTL_AllocIOCompletePacket@@YAPEAUtagRDPDR_IOCOMPLETION_PACKET@@QEAUtagRDPDR_IOREQUEST_PACKET@@K@Z; DrUTL_AllocIOCompletePacket(tagRDPDR_IOREQUEST_PACKET * const,ulong)
0x180557c0d  mov     [rsp+98h+arg_18], rax
0x180557c15  mov     rdx, rax
0x180557c18  test    rax, rax
0x180557c1b  jz      loc_180558107
0x180557c21  mov     eax, [rsp+98h+arg_10]
0x180557c28  mov     ecx, r12d; unsigned int
0x180557c2b  mov     [rdx+10h], eax
0x180557c2e  mov     eax, [rsp+98h+var_54]
0x180557c32  mov     [rdx+14h], al
0x180557c35  call    ?TranslateWinError@@YAJK@Z; TranslateWinError(ulong)
0x180557c3a  mov     [rdx+0Ch], eax
0x180557c3d  mov     rcx, [rsi]
0x180557c40  mov     rax, [rcx+0F0h]
0x180557c47  mov     rcx, rsi
0x180557c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180557c4f  mov     rdx, [rsp+98h+arg_18]; void *
0x180557c57  mov     r8d, ebx; unsigned int
0x180557c5a  mov     rcx, [rax+0E0h]; this
0x180557c61  call    ?ChannelWriteEx@VCManager@@QEAAIPEAXI@Z; VCManager::ChannelWriteEx(void *,uint)
0x180557c66  jmp     loc_180557FF5
0x180557c6b  mov     rax, cs:WPP_GLOBAL_Control
0x180557c72  cmp     rax, rbp
0x180557c75  jz      loc_180557BE9
0x180557c7b  test    [rax+1Ch], dil
0x180557c7f  jz      short loc_180557CAE
0x180557c81  cmp     [rax+19h], r14b
0x180557c85  jb      short loc_180557CAE
0x180557c87  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180557c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180557c93  mov     edx, 0Fh
0x180557c98  mov     r9d, eax
0x180557c9b  mov     r8, r15
0x180557c9e  mov     rcx, [rcx+10h]
0x180557ca2  call    WPP_SF_d
0x180557ca7  mov     rax, cs:WPP_GLOBAL_Control
0x180557cae  cmp     rax, rbp
0x180557cb1  jz      loc_180557BE9
0x180557cb7  test    [rax+1Ch], dil
0x180557cbb  jz      loc_180557BE9
0x180557cc1  cmp     byte ptr [rax+19h], 3
0x180557cc5  jb      loc_180557BE9
0x180557ccb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180557cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180557cd7  mov     edx, 10h
0x180557cdc  mov     r9d, eax
0x180557cdf  mov     qword ptr [rsp+98h+dwCreationDisposition], rbx
0x180557ce4  mov     r8, r15
0x180557ce7  mov     rcx, [rcx+10h]
0x180557ceb  call    WPP_SF_DS
0x180557cf0  jmp     loc_180557BE9
0x180557cf5  xor     r12d, r12d
0x180557cf8  test    [r13+30h], dil
0x180557cfc  jz      loc_180557EAB
0x180557d02  cmp     [rsp+98h+var_58], edi
0x180557d06  jnz     loc_180557EAB
0x180557d0c  xor     edx, edx; lpSecurityAttributes
0x180557d0e  mov     rcx, rbx; lpPathName
0x180557d11  call    cs:__imp_CreateDirectoryW
0x180557d17  test    eax, eax
0x180557d19  jz      loc_180557E72
0x180557d1f  mov     edx, [r13+24h]; dwFileAttributes
0x180557d23  mov     rcx, rbx; lpFileName
0x180557d26  call    cs:__imp_SetFileAttributesW
0x180557d2c  test    eax, eax
0x180557d2e  jz      loc_180557E13
0x180557d34  mov     rcx, [rsi+40h]
0x180557d38  call    ?GetUniqueObjectID@?$DrObjectMgr@VDrFile@@@@QEAAKXZ; DrObjectMgr<DrFile>::GetUniqueObjectID(void)
0x180557d3d  mov     edx, 90h; uBytes
0x180557d42  mov     [rsp+98h+arg_10], eax
0x180557d49  lea     ecx, [rdx-50h]; uFlags
0x180557d4c  call    cs:__imp_LocalAlloc
0x180557d52  test    rax, rax
0x180557d55  jz      loc_180557DE0
0x180557d5b  mov     r8d, [rsp+98h+arg_10]; unsigned int
0x180557d63  or      r9, 0FFFFFFFFFFFFFFFFh; void *
0x180557d67  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rbx; unsigned __int16 *
0x180557d6c  mov     rdx, rsi; struct DrDevice *
0x180557d6f  mov     rcx, rax; this
0x180557d72  mov     [rsp+98h+dwCreationDisposition], edi; int
0x180557d76  call    ??0DrFSFile@@QEAA@PEAVDrDevice@@KPEAXHPEBG@Z; DrFSFile::DrFSFile(DrDevice *,ulong,void *,int,ushort const *)
0x180557d7b  mov     rbx, rax
0x180557d7e  test    rax, rax
0x180557d81  jz      short loc_180557DE0
0x180557d83  mov     rcx, [rsi+40h]
0x180557d87  mov     rdx, rax
0x180557d8a  call    ?AddObject@?$DrObjectMgr@VDrDevice@@@@QEAAKPEAVDrDevice@@@Z; DrObjectMgr<DrDevice>::AddObject(DrDevice *)
0x180557d8f  test    eax, eax
0x180557d91  jz      loc_180557BF0
0x180557d97  mov     rax, cs:WPP_GLOBAL_Control
0x180557d9e  cmp     rax, rbp
0x180557da1  jz      loc_18055805E
0x180557da7  test    [rax+1Ch], dil
0x180557dab  jz      loc_18055805E
0x180557db1  cmp     [rax+19h], r14b
0x180557db5  jb      loc_18055805E
0x180557dbb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180557dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180557dc7  lea     edx, [r12+15h]
0x180557dcc  mov     r9d, eax
0x180557dcf  mov     r8, r15
0x180557dd2  mov     rcx, [rcx+10h]
0x180557dd6  call    WPP_SF_d
0x180557ddb  jmp     loc_18055805E
0x180557de0  mov     rax, cs:WPP_GLOBAL_Control
0x180557de7  cmp     rax, rbp
0x180557dea  jz      loc_180557FF5
0x180557df0  test    [rax+1Ch], dil
0x180557df4  jz      loc_180557FF5
0x180557dfa  cmp     [rax+19h], r14b
0x180557dfe  jb      loc_180557FF5
0x180557e04  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180557e09  mov     edx, 16h
0x180557e0e  jmp     loc_180557FDF
0x180557e13  call    cs:__imp_GetLastError
0x180557e19  mov     r12d, eax
0x180557e1c  mov     rax, cs:WPP_GLOBAL_Control
0x180557e23  cmp     rax, rbp
0x180557e26  jz      loc_180557BF0
0x180557e2c  test    [rax+1Ch], dil
0x180557e30  jz      loc_180557BF0
0x180557e36  cmp     [rax+19h], r14b
0x180557e3a  jb      loc_180557BF0
0x180557e40  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180557e45  mov     edx, 17h
0x180557e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180557e51  mov     r9d, eax
0x180557e54  mov     r8, r15
0x180557e57  mov     [rsp+98h+dwCreationDisposition], r12d
0x180557e5c  mov     rcx, [rcx+10h]
0x180557e60  call    WPP_SF_Dd
0x180557e65  mov     [rsp+98h+var_54], 0
0x180557e6d  jmp     loc_180557BFE
0x180557e72  call    cs:__imp_GetLastError
0x180557e78  mov     r12d, eax
0x180557e7b  mov     rax, cs:WPP_GLOBAL_Control
0x180557e82  cmp     rax, rbp
0x180557e85  jz      loc_180557BF0
0x180557e8b  test    [rax+1Ch], dil
0x180557e8f  jz      loc_180557BF0
0x180557e95  cmp     [rax+19h], r14b
0x180557e99  jb      loc_180557BF0
0x180557e9f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180557ea4  mov     edx, 18h
0x180557ea9  jmp     short loc_180557E4A
0x180557eab  mov     eax, [rsp+98h+arg_8]
0x180557eb2  xor     r9d, r9d; lpSecurityAttributes
0x180557eb5  mov     r8d, [r13+28h]
0x180557eb9  mov     rcx, rbx; lpFileName
0x180557ebc  mov     edx, [rsp+98h+dwDesiredAccess]; dwDesiredAccess
0x180557ec0  and     r8d, 0FFFFFFFBh; dwShareMode
0x180557ec4  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x180557ec9  mov     [rsp+98h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180557ecd  mov     eax, [rsp+98h+var_58]
0x180557ed1  mov     [rsp+98h+dwCreationDisposition], eax; dwCreationDisposition
  ... truncated ...
```
