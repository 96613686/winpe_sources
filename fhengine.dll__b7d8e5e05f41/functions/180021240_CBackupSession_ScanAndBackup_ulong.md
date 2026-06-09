# CBackupSession::ScanAndBackup(ulong)

- ea: `0x180021240`
- end: `0x180021b73`
- name: `?ScanAndBackup@CBackupSession@@UEAAJK@Z`
- size: `2355`
- prototype: `__int64 __fastcall(CBackupSession *this, int, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x1800077f0`
- `0x180007818`
- `0x180010de8`
- `0x180012b44`
- `0x180016da0`
- `0x1800196f8`
- `0x18001a4a8`
- `0x18001a4c8`
- `0x18001b4e0`
- `0x18001fee4`
- `0x180021240`
- `0x18002204c`
- `0x18002a678`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1800212e2`
- `ADVAPI32!SetThreadToken` at `0x180021883`
- `ADVAPI32!SetThreadToken` at `0x180021907`
- `ADVAPI32!SetThreadToken` at `0x180021ae4`
- `ADVAPI32!SetThreadToken` at `0x1800212e2`
- `ADVAPI32!SetThreadToken` at `0x180021883`
- `ADVAPI32!SetThreadToken` at `0x180021907`
- `ADVAPI32!SetThreadToken` at `0x180021ae4`
- `KERNEL32!GetLastError` at `0x1800212ec`
- `KERNEL32!GetLastError` at `0x1800214f5`
- `KERNEL32!GetLastError` at `0x18002189f`
- `KERNEL32!GetLastError` at `0x180021911`
- `KERNEL32!GetLastError` at `0x180021976`
- `KERNEL32!GetLastError` at `0x180021b00`
- `KERNEL32!GetLastError` at `0x1800212ec`
- `KERNEL32!GetLastError` at `0x1800214f5`
- `KERNEL32!GetLastError` at `0x18002189f`
- `KERNEL32!GetLastError` at `0x180021911`
- `KERNEL32!GetLastError` at `0x180021976`
- `KERNEL32!GetLastError` at `0x180021b00`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180021700`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002171a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800217ca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800217e4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180021700`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002171a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800217ca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800217e4`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180021965`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180021965`
- `KERNEL32!GetVolumeInformationW` at `0x1800214eb`
- `KERNEL32!GetVolumeInformationW` at `0x1800214eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::ScanAndBackup(CBackupSession *this, int a2, __int64 a3)
{
  signed int v5; // esi
  signed int LastError; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  CBackupSession *v11; // rcx
  int v12; // edx
  signed int v13; // eax
  signed int TargetVolumeRoot; // r14d
  LPCWSTR v15; // rbx
  signed int v16; // eax
  int v17; // eax
  PVOID *v18; // rcx
  char *v19; // rax
  int v20; // eax
  char *v21; // rax
  signed int v22; // eax
  signed int v23; // eax
  void (__fastcall *v24)(char *, _QWORD); // r14
  signed int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  signed int v29; // eax
  DWORD FileSystemFlags[2]; // [rsp+60h] [rbp-19h] BYREF
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+68h] [rbp-11h] BYREF
  LPCWSTR lpRootPathName[2]; // [rsp+70h] [rbp-9h] BYREF

  FreeBytesAvailableToCaller.QuadPart = 0;
  v5 = 0;
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, ScanAndBackupStart, a3, 1, lpRootPathName);
  *((_DWORD *)this + 86) = a2 & 0x3FFFFFF;
  if ( (a2 & 1) != 0 )
    (**((void (__fastcall ***)(char *, _QWORD))this + 1))((char *)this + 8, 0);
  if ( *((_DWORD *)this + 39) )
  {
    if ( !SetThreadToken(0, *((HANDLE *)this + 48)) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 27;
LABEL_12:
        v9 = (unsigned int)v5;
LABEL_147:
        WPP_SF_d(v7[2], v8, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v9);
        goto LABEL_148;
      }
      goto LABEL_148;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 224LL))(*((_QWORD *)this + 2));
    v5 = v10;
    if ( v10 == -2147220719 )
    {
      (**((void (__fastcall ***)(char *, __int64))this + 1))((char *)this + 8, 2147746577LL);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 28;
        v9 = 2147746577LL;
        goto LABEL_147;
      }
      goto LABEL_148;
    }
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v10);
      (**((void (__fastcall ***)(char *, _QWORD))this + 1))((char *)this + 8, (unsigned int)v5);
      v5 = 0;
      goto LABEL_48;
    }
    if ( (unsigned int)CBackupSession::IsDefaultTargetDirty(this) )
    {
      *((_DWORD *)this + 90) = 1;
    }
    else
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 152LL))(*((_QWORD *)this + 2));
      *((_DWORD *)this + 90) |= CBackupSession::IsChkDskRequired(v11, v5);
      v12 = *((_DWORD *)this + 90);
      *((_DWORD *)this + 91) |= v5 == -2147024891 || v5 == -2147023570;
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (unsigned int)v5);
          v12 = *((_DWORD *)this + 90);
        }
        v13 = *((_DWORD *)this + 206);
        if ( v13 == -1 )
          v13 = v5;
        *((_DWORD *)this + 206) = v13;
        v5 = 0;
      }
      if ( !v12 )
        goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    (**((void (__fastcall ***)(char *, __int64))this + 1))((char *)this + 8, 2147943793LL);
LABEL_37:
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(lpRootPathName);
    FileSystemFlags[0] = 0;
    TargetVolumeRoot = FhePathOperations::GetTargetVolumeRoot((char *)this + 72, lpRootPathName);
    v15 = lpRootPathName[0];
    if ( TargetVolumeRoot < 0 )
      goto LABEL_44;
    if ( GetVolumeInformationW(lpRootPathName[0], 0, 0, 0, 0, FileSystemFlags, 0, 0) )
      goto LABEL_42;
    v16 = GetLastError();
    TargetVolumeRoot = v16;
    if ( v16 > 0 )
      TargetVolumeRoot = (unsigned __int16)v16 | 0x80070000;
    if ( TargetVolumeRoot >= 0 )
    {
LABEL_42:
      *((_DWORD *)this + 92) = (FileSystemFlags[0] >> 17) & 1;
    }
    else
    {
LABEL_44:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      (**((void (__fastcall ***)(char *, _QWORD))this + 1))((char *)this + 8, (unsigned int)TargetVolumeRoot);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 12));
  }
LABEL_48:
  if ( !*((_DWORD *)this + 40) )
  {
    v17 = CBackupSession::PreviousActionsCleanup(this);
    v5 = v17;
    if ( v17 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_148;
      v8 = 33;
      goto LABEL_146;
    }
    goto LABEL_56;
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
LABEL_56:
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 39) && *((_BYTE *)this + 196) )
  {
    if ( !*((_DWORD *)this + 40) && (*((_DWORD *)this + 86) & 0x8000002) == 0 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        WPP_SF_d(v18[2], 35, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, *((unsigned int *)this + 48));
      CSessionBaseRW::RetireFileVersionsOnTarget(
        (CBackupSession *)((char *)this + 8),
        *((_QWORD *)this + 13),
        0,
        *((_DWORD *)this + 58),
        *((_DWORD *)this + 48) + 1,
        0,
        0,
        (int *)this + 269,
        (int *)this + 270,
        (int *)this + 268,
        (__int64 *)this + 136,
        0);
      goto LABEL_68;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
    {
      WPP_SF_d(v18[2], 36, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, *((unsigned int *)this + 48));
LABEL_68:
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( *((_DWORD *)this + 40) || (*((_DWORD *)this + 86) & 0x40000002) != 0 )
  {
    if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 8) == 0 )
    {
LABEL_84:
      if ( *((_DWORD *)this + 40) || (v20 = *((_DWORD *)this + 86), (v20 & 2) != 0) || v20 < 0 )
      {
        if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 8) == 0 )
          goto LABEL_102;
        WPP_SF_(v18[2], 42, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      }
      else
      {
        *(_QWORD *)FileSystemFlags = 0;
        lpRootPathName[0] = 0;
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
          WPP_SF_(v18[2], 40, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
        GetSystemTimeAsFileTime((LPFILETIME)FileSystemFlags);
        v5 = CBackupSession::BackupAllFiles(this);
        *((_DWORD *)this + 205) = v5;
        GetSystemTimeAsFileTime((LPFILETIME)lpRootPathName);
        v21 = (char *)lpRootPathName[0] - *(_QWORD *)FileSystemFlags;
        if ( (__int64)lpRootPathName[0] - *(_QWORD *)FileSystemFlags <= 0 )
          v21 = 0;
        *((_QWORD *)this + 101) += v21;
        if ( v5 == -2147023661 )
        {
          v5 = 0;
        }
        else if ( v5 < 0 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 41;
            goto LABEL_12;
          }
          goto LABEL_148;
        }
      }
      v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_102:
      if ( *((_DWORD *)this + 40) )
        goto LABEL_159;
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        WPP_SF_(v18[2], 43, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      if ( !SetThreadToken(0, 0)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = GetLastError();
        if ( v22 > 0 )
          v22 = (unsigned __int16)v22 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v22);
      }
      v17 = CBackupSession::CheckSourceVolumes(this);
      v5 = v17;
      if ( v17 >= 0 )
      {
LABEL_159:
        if ( !SetThreadToken(0, *((HANDLE *)this + 48)) )
        {
          v23 = GetLastError();
          v5 = v23;
          if ( v23 > 0 )
            v5 = (unsigned __int16)v23 | 0x80070000;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 46;
            goto LABEL_12;
          }
          goto LABEL_148;
        }
        if ( *((_DWORD *)this + 39) )
        {
          if ( !GetDiskFreeSpaceExW(*((LPCWSTR *)this + 9), &FreeBytesAvailableToCaller, 0, 0) )
          {
            v24 = (void (__fastcall *)(char *, _QWORD))**((_QWORD **)this + 1);
            v25 = GetLastError();
            if ( v25 > 0 )
              v25 = (unsigned __int16)v25 | 0x80070000;
            v24((char *)this + 8, (unsigned int)v25);
          }
          if ( *((_DWORD *)this + 39) && FreeBytesAvailableToCaller.QuadPart < *((_QWORD *)this + 60) )
          {
            if ( *((_DWORD *)this + 40) || (*((_DWORD *)this + 86) & 0x4000002) != 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
              if ( (unsigned int)CSessionBaseRW::RetireFileVersionsOnTarget(
                                   (CBackupSession *)((char *)this + 8),
                                   *((_QWORD *)this + 61),
                                   0,
                                   *((_DWORD *)this + 58),
                                   *((_DWORD *)this + 50),
                                   1,
                                   0,
                                   (int *)this + 269,
                                   (int *)this + 270,
                                   (int *)this + 268,
                                   (__int64 *)this + 136,
                                   0) != -2147024784
                || (v26 = 1, *((_DWORD *)this + 48) != *((_DWORD *)this + 50)) )
              {
                v26 = 0;
              }
              *((_DWORD *)this + 94) |= v26;
              v5 = 0;
            }
          }
        }
        if ( *((int *)this + 222) <= 0 )
          goto LABEL_148;
        v17 = CBackupSession::FlushTarget(this);
        v5 = v17;
        if ( v17 >= 0 )
          goto LABEL_148;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_148;
        v8 = 49;
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_148;
        v8 = 45;
      }
LABEL_146:
      v9 = (unsigned int)v17;
      goto LABEL_147;
    }
    WPP_SF_(v18[2], 39, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
LABEL_83:
    v18 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_84;
  }
  *(_QWORD *)FileSystemFlags = 0;
  lpRootPathName[0] = 0;
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
    WPP_SF_(v18[2], 37, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
  GetSystemTimeAsFileTime((LPFILETIME)FileSystemFlags);
  v5 = CBackupSession::ScanAllEvents(this);
  *((_DWORD *)this + 204) = v5;
  GetSystemTimeAsFileTime((LPFILETIME)lpRootPathName);
  v19 = (char *)lpRootPathName[0] - *(_QWORD *)FileSystemFlags;
  if ( (__int64)lpRootPathName[0] - *(_QWORD *)FileSystemFlags <= 0 )
    v19 = 0;
  *((_QWORD *)this + 100) += v19;
  if ( v5 >= 0 )
    goto LABEL_83;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 38;
    goto LABEL_12;
  }
LABEL_148:
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v29 = GetLastError();
    if ( v29 > 0 )
      v29 = (unsigned __int16)v29 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)v29);
  }
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v27, ScanAndBackupStop, v28, 1, lpRootPathName);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021240  push    rbp
0x180021242  push    rbx
0x180021243  push    rsi
0x180021244  push    rdi
0x180021245  push    r12
0x180021247  push    r13
0x180021249  push    r14
0x18002124b  push    r15
0x18002124d  lea     rbp, [rsp-1Fh]
0x180021252  sub     rsp, 98h
0x180021259  mov     rax, cs:__security_cookie
0x180021260  xor     rax, rsp
0x180021263  mov     [rbp+57h+var_50], rax
0x180021267  mov     ebx, edx
0x180021269  mov     rdi, rcx
0x18002126c  xor     r15d, r15d
0x18002126f  mov     qword ptr [rbp+57h+FreeBytesAvailableToCaller], r15
0x180021273  mov     esi, r15d
0x180021276  lea     r14d, [r15+1]
0x18002127a  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, r14b
0x180021281  jz      short loc_18002129B
0x180021283  lea     rax, [rbp+57h+lpRootPathName]
0x180021287  mov     [rsp+0D0h+lpMaximumComponentLength], rax
0x18002128c  mov     r9d, r14d
0x18002128f  lea     rdx, ScanAndBackupStart
0x180021296  call    McGenEventWrite_EventWriteTransfer
0x18002129b  mov     eax, ebx
0x18002129d  and     eax, 3FFFFFFh
0x1800212a2  mov     [rdi+158h], eax
0x1800212a8  test    r14b, bl
0x1800212ab  jz      short loc_1800212BE
0x1800212ad  lea     rcx, [rdi+8]
0x1800212b1  mov     rax, [rcx]
0x1800212b4  xor     edx, edx
0x1800212b6  mov     rax, [rax]
0x1800212b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212be  lea     r13, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x1800212c5  lea     r12, WPP_GLOBAL_Control
0x1800212cc  cmp     [rdi+9Ch], r15d
0x1800212d3  jz      loc_18002156D
0x1800212d9  mov     rdx, [rdi+180h]; Token
0x1800212e0  xor     ecx, ecx; Thread
0x1800212e2  call    cs:__imp_SetThreadToken
0x1800212e8  test    eax, eax
0x1800212ea  jnz     short loc_180021328
0x1800212ec  call    cs:__imp_GetLastError
0x1800212f2  mov     esi, eax
0x1800212f4  test    eax, eax
0x1800212f6  jle     short loc_180021301
0x1800212f8  movzx   esi, ax
0x1800212fb  or      esi, 80070000h
0x180021301  mov     rcx, cs:WPP_GLOBAL_Control
0x180021308  cmp     rcx, r12
0x18002130b  jz      loc_180021AE0
0x180021311  test    [rcx+1Ch], r14b
0x180021315  jz      loc_180021AE0
0x18002131b  mov     edx, 1Bh
0x180021320  mov     r9d, esi
0x180021323  jmp     loc_180021AD4
0x180021328  mov     rcx, [rdi+10h]
0x18002132c  mov     rax, [rcx]
0x18002132f  mov     rax, [rax+0E0h]
0x180021336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002133b  mov     esi, eax
0x18002133d  mov     ebx, 80040311h
0x180021342  cmp     eax, ebx
0x180021344  jnz     short loc_18002137F
0x180021346  mov     rcx, [rdi+8]
0x18002134a  mov     rax, [rcx]
0x18002134d  mov     edx, ebx
0x18002134f  lea     rcx, [rdi+8]
0x180021353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021358  mov     rcx, cs:WPP_GLOBAL_Control
0x18002135f  cmp     rcx, r12
0x180021362  jz      loc_180021AE0
0x180021368  test    [rcx+1Ch], r14b
0x18002136c  jz      loc_180021AE0
0x180021372  mov     edx, 1Ch
0x180021377  mov     r9d, ebx
0x18002137a  jmp     loc_180021AD4
0x18002137f  test    esi, esi
0x180021381  jns     short loc_1800213C2
0x180021383  mov     rcx, cs:WPP_GLOBAL_Control
0x18002138a  cmp     rcx, r12
0x18002138d  jz      short loc_1800213A9
0x18002138f  test    byte ptr [rcx+1Ch], 2
0x180021393  jz      short loc_1800213A9
0x180021395  mov     edx, 1Dh
0x18002139a  mov     r9d, esi
0x18002139d  mov     r8, r13
0x1800213a0  mov     rcx, [rcx+10h]
0x1800213a4  call    WPP_SF_d
0x1800213a9  lea     rcx, [rdi+8]
0x1800213ad  mov     rax, [rcx]
0x1800213b0  mov     edx, esi
0x1800213b2  mov     rax, [rax]
0x1800213b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213ba  mov     esi, r15d
0x1800213bd  jmp     loc_18002156D
0x1800213c2  mov     rcx, rdi; this
0x1800213c5  call    ?IsDefaultTargetDirty@CBackupSession@@AEAAHXZ; CBackupSession::IsDefaultTargetDirty(void)
0x1800213ca  test    eax, eax
0x1800213cc  jnz     loc_180021465
0x1800213d2  mov     rcx, [rdi+10h]
0x1800213d6  mov     rax, [rcx]
0x1800213d9  mov     rax, [rax+98h]
0x1800213e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213e5  mov     esi, eax
0x1800213e7  mov     edx, eax; int
0x1800213e9  call    ?IsChkDskRequired@CBackupSession@@AEAAHJ@Z; CBackupSession::IsChkDskRequired(long)
0x1800213ee  or      [rdi+168h], eax
0x1800213f4  mov     edx, [rdi+168h]
0x1800213fa  mov     ecx, r15d
0x1800213fd  cmp     esi, 8007052Eh
0x180021403  setz    cl
0x180021406  mov     eax, r15d
0x180021409  cmp     esi, 80070005h
0x18002140f  setz    al
0x180021412  or      ecx, eax
0x180021414  or      [rdi+16Ch], ecx
0x18002141a  test    esi, esi
0x18002141c  jns     short loc_18002145F
0x18002141e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021425  cmp     rcx, r12
0x180021428  jz      short loc_18002144A
0x18002142a  test    byte ptr [rcx+1Ch], 2
0x18002142e  jz      short loc_18002144A
0x180021430  mov     edx, 1Eh
0x180021435  mov     r9d, esi
0x180021438  mov     r8, r13
0x18002143b  mov     rcx, [rcx+10h]
0x18002143f  call    WPP_SF_d
0x180021444  mov     edx, [rdi+168h]
0x18002144a  mov     eax, [rdi+338h]
0x180021450  cmp     eax, 0FFFFFFFFh
0x180021453  cmovz   eax, esi
0x180021456  mov     [rdi+338h], eax
0x18002145c  mov     esi, r15d
0x18002145f  test    edx, edx
0x180021461  jnz     short loc_18002146C
0x180021463  jmp     short loc_1800214A3
0x180021465  mov     [rdi+168h], r14d
0x18002146c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021473  cmp     rcx, r12
0x180021476  jz      short loc_18002148F
0x180021478  test    byte ptr [rcx+1Ch], 2
0x18002147c  jz      short loc_18002148F
0x18002147e  mov     edx, 1Fh
0x180021483  mov     r8, r13
0x180021486  mov     rcx, [rcx+10h]
0x18002148a  call    WPP_SF_
0x18002148f  lea     rcx, [rdi+8]
0x180021493  mov     rax, [rcx]
0x180021496  mov     edx, 80070571h
0x18002149b  mov     rax, [rax]
0x18002149e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214a3  lea     rcx, [rbp+57h+lpRootPathName]
0x1800214a7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800214ac  mov     [rbp+57h+FileSystemFlags], r15d
0x1800214b0  lea     rcx, [rdi+48h]
0x1800214b4  lea     rdx, [rbp+57h+lpRootPathName]
0x1800214b8  call    ?GetTargetVolumeRoot@FhePathOperations@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; FhePathOperations::GetTargetVolumeRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800214bd  mov     r14d, eax
0x1800214c0  mov     rbx, [rbp+57h+lpRootPathName]
0x1800214c4  test    eax, eax
0x1800214c6  js      short loc_180021529
0x1800214c8  mov     [rsp+0D0h+nFileSystemNameSize], r15d; nFileSystemNameSize
0x1800214cd  mov     [rsp+0D0h+lpFileSystemNameBuffer], r15; lpFileSystemNameBuffer
0x1800214d2  lea     rax, [rbp+57h+FileSystemFlags]
0x1800214d6  mov     [rsp+0D0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1800214db  mov     [rsp+0D0h+lpMaximumComponentLength], r15; lpMaximumComponentLength
0x1800214e0  xor     r9d, r9d; lpVolumeSerialNumber
0x1800214e3  xor     r8d, r8d; nVolumeNameSize
0x1800214e6  xor     edx, edx; lpVolumeNameBuffer
0x1800214e8  mov     rcx, rbx; lpRootPathName
0x1800214eb  call    cs:__imp_GetVolumeInformationW
0x1800214f1  test    eax, eax
0x1800214f3  jnz     short loc_180021512
0x1800214f5  call    cs:__imp_GetLastError
0x1800214fb  mov     r14d, eax
0x1800214fe  test    eax, eax
0x180021500  jle     short loc_18002150D
0x180021502  movzx   r14d, ax
0x180021506  or      r14d, 80070000h
0x18002150d  test    r14d, r14d
0x180021510  js      short loc_180021529
0x180021512  mov     eax, [rbp+57h+FileSystemFlags]
0x180021515  shr     eax, 11h
0x180021518  mov     r14d, 1
0x18002151e  and     eax, r14d
0x180021521  mov     [rdi+170h], eax
0x180021527  jmp     short loc_180021564
0x180021529  mov     rcx, cs:WPP_GLOBAL_Control
0x180021530  cmp     rcx, r12
0x180021533  jz      short loc_18002154C
0x180021535  test    byte ptr [rcx+1Ch], 2
0x180021539  jz      short loc_18002154C
0x18002153b  mov     edx, 20h ; ' '
0x180021540  mov     r8, r13
0x180021543  mov     rcx, [rcx+10h]
0x180021547  call    WPP_SF_
0x18002154c  lea     rcx, [rdi+8]
0x180021550  mov     rax, [rcx]
0x180021553  mov     edx, r14d
0x180021556  mov     rax, [rax]
0x180021559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002155e  mov     r14d, 1
0x180021564  lea     rcx, [rbx-18h]; this
0x180021568  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002156d  mov     bl, 8
0x18002156f  cmp     [rdi+0A0h], r15d
0x180021576  jnz     short loc_1800215AA
0x180021578  mov     rcx, rdi; this
0x18002157b  call    ?PreviousActionsCleanup@CBackupSession@@AEAAJXZ; CBackupSession::PreviousActionsCleanup(void)
0x180021580  mov     esi, eax
0x180021582  test    eax, eax
0x180021584  jns     short loc_1800215CC
0x180021586  mov     rcx, cs:WPP_GLOBAL_Control
0x18002158d  cmp     rcx, r12
0x180021590  jz      loc_180021AE0
0x180021596  test    [rcx+1Ch], r14b
0x18002159a  jz      loc_180021AE0
0x1800215a0  mov     edx, 21h ; '!'
0x1800215a5  jmp     loc_180021AD1
0x1800215aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215b1  cmp     rcx, r12
0x1800215b4  jz      short loc_1800215D3
0x1800215b6  test    [rcx+1Ch], bl
0x1800215b9  jz      short loc_1800215D3
0x1800215bb  mov     edx, 22h ; '"'
0x1800215c0  mov     r8, r13
0x1800215c3  mov     rcx, [rcx+10h]
0x1800215c7  call    WPP_SF_
0x1800215cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215d3  cmp     [rdi+9Ch], r15d
0x1800215da  jz      loc_1800216BC
0x1800215e0  cmp     [rdi+0C4h], r15b
0x1800215e7  jz      loc_1800216BC
0x1800215ed  cmp     [rdi+0A0h], r15d
0x1800215f4  jnz     loc_180021693
0x1800215fa  test    dword ptr [rdi+158h], 8000002h
0x180021604  jnz     loc_180021693
0x18002160a  cmp     rcx, r12
0x18002160d  jz      short loc_18002162C
0x18002160f  test    [rcx+1Ch], bl
0x180021612  jz      short loc_18002162C
0x180021614  mov     edx, 23h ; '#'
0x180021619  mov     r9d, [rdi+0C0h]
0x180021620  mov     r8, r13
0x180021623  mov     rcx, [rcx+10h]
0x180021627  call    WPP_SF_d
0x18002162c  lea     rax, [rdi+440h]
0x180021633  lea     rdx, [rdi+430h]
0x18002163a  lea     r8, [rdi+438h]
0x180021641  lea     r9, [rdi+434h]
0x180021648  mov     r10d, [rdi+0C0h]
0x18002164f  add     r10d, r14d
0x180021652  lea     rcx, [rdi+8]; this
0x180021656  mov     [rsp+0D0h+var_78], r15; struct IFhEngineCleanupProgressEvent *
0x18002165b  mov     [rsp+0D0h+var_80], rax; __int64 *
0x180021660  mov     [rsp+0D0h+var_88], rdx; int *
0x180021665  mov     [rsp+0D0h+var_90], r8; int *
0x18002166a  mov     qword ptr [rsp+0D0h+nFileSystemNameSize], r9; int *
0x18002166f  mov     dword ptr [rsp+0D0h+lpFileSystemNameBuffer], r15d; int
0x180021674  mov     dword ptr [rsp+0D0h+lpFileSystemFlags], r15d; int
0x180021679  mov     dword ptr [rsp+0D0h+lpMaximumComponentLength], r10d; int
0x18002167e  mov     r9d, [rdi+0E8h]; unsigned int
0x180021685  xor     r8d, r8d; unsigned __int64
0x180021688  mov     rdx, [rdi+68h]; unsigned __int64
0x18002168c  call    ?RetireFileVersionsOnTarget@CSessionBaseRW@@IEAAJ_K0KJHHPEAJ11PEA_JPEAUIFhEngineCleanupProgressEvent@@@Z; CSessionBaseRW::RetireFileVersionsOnTarget(unsigned __int64,unsigned __int64,ulong,long,int,int,long *,long *,long *,__int64 *,IFhEngineCleanupProgressEvent *)
0x180021691  jmp     short loc_1800216B5
0x180021693  cmp     rcx, r12
0x180021696  jz      short loc_1800216BC
0x180021698  test    [rcx+1Ch], bl
0x18002169b  jz      short loc_1800216BC
0x18002169d  mov     edx, 24h ; '$'
0x1800216a2  mov     r9d, [rdi+0C0h]
0x1800216a9  mov     r8, r13
0x1800216ac  mov     rcx, [rcx+10h]
0x1800216b0  call    WPP_SF_d
0x1800216b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216bc  cmp     [rdi+0A0h], r15d
0x1800216c3  jnz     loc_18002175E
0x1800216c9  test    dword ptr [rdi+158h], 40000002h
0x1800216d3  jnz     loc_18002175E
0x1800216d9  mov     qword ptr [rbp+57h+FileSystemFlags], r15
0x1800216dd  mov     [rbp+57h+lpRootPathName], r15
0x1800216e1  cmp     rcx, r12
0x1800216e4  jz      short loc_1800216FC
0x1800216e6  test    [rcx+1Ch], bl
0x1800216e9  jz      short loc_1800216FC
0x1800216eb  mov     edx, 25h ; '%'
0x1800216f0  mov     r8, r13
0x1800216f3  mov     rcx, [rcx+10h]
0x1800216f7  call    WPP_SF_
0x1800216fc  lea     rcx, [rbp+57h+FileSystemFlags]; lpSystemTimeAsFileTime
0x180021700  call    cs:__imp_GetSystemTimeAsFileTime
0x180021706  mov     rcx, rdi; this
0x180021709  call    ?ScanAllEvents@CBackupSession@@AEAAJXZ; CBackupSession::ScanAllEvents(void)
0x18002170e  mov     esi, eax
  ... truncated ...
```
