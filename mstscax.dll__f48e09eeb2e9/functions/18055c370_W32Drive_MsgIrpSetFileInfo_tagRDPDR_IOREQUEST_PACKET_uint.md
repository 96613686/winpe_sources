# W32Drive::MsgIrpSetFileInfo(tagRDPDR_IOREQUEST_PACKET *,uint)

- ea: `0x18055c370`
- end: `0x18055cb7d`
- name: `?MsgIrpSetFileInfo@W32Drive@@UEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@I@Z`
- size: `2061`
- prototype: `void __fastcall(W32Drive *this, struct tagRDPDR_IOREQUEST_PACKET *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18007433c`
- `0x1800745a4`
- `0x180074644`
- `0x18007b16c`
- `0x18008a2c0`
- `0x1800cfa74`
- `0x1800ff850`
- `0x18012966c`
- `0x180554ec0`
- `0x18055c370`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18055c4c4`
- `ntdll!NtSetInformationFile` at `0x18055c4c4`
- `KERNEL32!MoveFileW` at `0x18055c8ae`
- `KERNEL32!MoveFileW` at `0x18055c8ae`
- `KERNEL32!SetFileTime` at `0x18055ca25`
- `KERNEL32!SetFileTime` at `0x18055ca25`
- `KERNEL32!GetLastError` at `0x18055c5da`
- `KERNEL32!GetLastError` at `0x18055c60d`
- `KERNEL32!GetLastError` at `0x18055c63d`
- `KERNEL32!GetLastError` at `0x18055c6d7`
- `KERNEL32!GetLastError` at `0x18055c72b`
- `KERNEL32!GetLastError` at `0x18055c8bc`
- `KERNEL32!GetLastError` at `0x18055c989`
- `KERNEL32!GetLastError` at `0x18055ca36`
- `KERNEL32!GetLastError` at `0x18055c5da`
- `KERNEL32!GetLastError` at `0x18055c60d`
- `KERNEL32!GetLastError` at `0x18055c63d`
- `KERNEL32!GetLastError` at `0x18055c6d7`
- `KERNEL32!GetLastError` at `0x18055c72b`
- `KERNEL32!GetLastError` at `0x18055c8bc`
- `KERNEL32!GetLastError` at `0x18055c989`
- `KERNEL32!GetLastError` at `0x18055ca36`
- `KERNEL32!DeleteFileW` at `0x18055c6c2`
- `KERNEL32!DeleteFileW` at `0x18055c89c`
- `KERNEL32!DeleteFileW` at `0x18055c6c2`
- `KERNEL32!DeleteFileW` at `0x18055c89c`
- `KERNEL32!SetFileAttributesW` at `0x18055c978`
- `KERNEL32!SetFileAttributesW` at `0x18055c978`
- `KERNEL32!SetFilePointer` at `0x18055c59f`
- `KERNEL32!SetFilePointer` at `0x18055c59f`
- `KERNEL32!RemoveDirectoryW` at `0x18055c71e`
- `KERNEL32!RemoveDirectoryW` at `0x18055c71e`
- `KERNEL32!SetEndOfFile` at `0x18055c5ad`
- `KERNEL32!SetEndOfFile` at `0x18055c5ad`

## pseudocode

```c
void __fastcall W32Drive::MsgIrpSetFileInfo(W32Drive *this, struct tagRDPDR_IOREQUEST_PACKET *a2, unsigned int a3)
{
  __int64 v4; // rcx
  LPCWSTR *v6; // rsi
  __int64 ObjectW; // rax
  __int64 v8; // r15
  __int64 v9; // r14
  int v10; // ebx
  PVOID *v11; // rdi
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int LastError; // ebx
  unsigned int v15; // eax
  __int64 v16; // rdx
  HKEY v17; // rax
  unsigned int v18; // eax
  DWORD v19; // ebx
  unsigned int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // eax
  const WCHAR *v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // eax
  unsigned __int64 v27; // rdx
  int v28; // ebx
  unsigned int v29; // eax
  DWORD v30; // edx
  _IO_STATUS_BLOCK *p_IoStatusBlock; // rdx
  const FILETIME *v32; // r8
  const FILETIME *v33; // r9
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v35; // eax
  _DWORD *v36; // rdx
  unsigned int v37; // eax
  __int64 v38; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = *((unsigned int *)a2 + 7);
  v6 = 0;
  if ( (unsigned int)v4 >= 0xFFFFFFC8 || a3 < (unsigned __int64)(v4 + 56) )
    goto LABEL_2;
  ObjectW = DrObjectMgr<DrFile>::GetObjectW(*((_QWORD *)this + 8), *((unsigned int *)a2 + 2));
  v6 = (LPCWSTR *)ObjectW;
  if ( !ObjectW )
  {
    LastError = 2;
    goto LABEL_123;
  }
  v8 = -1;
  v9 = -1;
  if ( !*(_DWORD *)(ObjectW + 48) )
    v9 = *(_QWORD *)(ObjectW + 32);
  v10 = *((_DWORD *)a2 + 6);
  v11 = (PVOID *)((char *)a2 + 56);
  v12 = *((unsigned int *)a2 + 7);
  if ( v10 == 4 )
  {
    IoStatusBlock.Pointer = 0;
    v38 = 0;
    v39 = 0;
    if ( (unsigned int)v12 < 0x24 )
      goto LABEL_2;
    v30 = *((_DWORD *)a2 + 22);
    if ( !v30 )
    {
      if ( *v11 )
      {
        p_IoStatusBlock = &IoStatusBlock;
        IoStatusBlock.Pointer = *v11;
      }
      else
      {
        p_IoStatusBlock = 0;
      }
      if ( *((_QWORD *)a2 + 8) )
      {
        v32 = (const FILETIME *)&v38;
        v38 = *((_QWORD *)a2 + 8);
      }
      else
      {
        v32 = 0;
      }
      if ( *((_QWORD *)a2 + 9) )
      {
        v33 = (const FILETIME *)&v39;
        v39 = *((_QWORD *)a2 + 9);
      }
      else
      {
        v33 = 0;
      }
      if ( v9 == -1 )
      {
        LastError = 0;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            73,
            &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        goto LABEL_123;
      }
      if ( SetFileTime((HANDLE)v9, (const FILETIME *)p_IoStatusBlock, v32, v33) )
        goto LABEL_53;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 72;
      goto LABEL_91;
    }
    if ( !SetFileAttributesW(*(LPCWSTR *)(ObjectW + 128), v30) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_123;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 71;
      goto LABEL_91;
    }
LABEL_53:
    LastError = 0;
    goto LABEL_123;
  }
  if ( *((_DWORD *)a2 + 6) == 10 )
  {
    if ( (unsigned int)v12 < 8 )
      goto LABEL_2;
    v26 = *(_DWORD *)((char *)a2 + 58);
    if ( v26 + 6 < v26 || (unsigned int)v12 < v26 + 6 )
      goto LABEL_2;
    if ( !v6[16] )
    {
      LastError = 2;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        v16 = 80;
        goto LABEL_24;
      }
      goto LABEL_123;
    }
    (*((void (__fastcall **)(LPCWSTR *, __int64, HKEY *))*v6 + 5))(v6, v12, &WPP_GLOBAL_Control);
    if ( *((_BYTE *)a2 + 57) )
      FileName[0] = 0;
    else
      StringCchCopyW(FileName, 0x104u, (const unsigned __int16 *)this + 44);
    do
      ++v8;
    while ( FileName[v8] );
    v27 = 2LL * (unsigned int)(259 - v8);
    if ( v27 >= (unsigned __int64)*(unsigned int *)((char *)a2 + 58) + 2 )
      v27 = *(unsigned int *)((char *)a2 + 58) + 2LL;
    v28 = StringCbCopyW(&FileName[v8], v27, (const unsigned __int16 *)a2 + 31);
    if ( v28 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v29, v28);
      }
      LastError = 122;
      goto LABEL_123;
    }
    if ( *(_BYTE *)v11 )
      DeleteFileW(FileName);
    if ( !MoveFileW(v6[16], FileName) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_123;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 79;
      goto LABEL_91;
    }
    goto LABEL_53;
  }
  if ( *((_DWORD *)a2 + 6) != 13 )
  {
    if ( *((_DWORD *)a2 + 6) != 19 )
    {
      if ( *((_DWORD *)a2 + 6) != 20 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v13, v10);
        }
        LastError = 1;
        goto LABEL_123;
      }
      if ( (unsigned int)v12 >= 8 )
      {
        if ( v9 != -1 )
        {
          IoStatusBlock = 0;
          LastError = NtSetInformationFile((HANDLE)v9, &IoStatusBlock, (char *)a2 + 56, 8u, FileEndOfFileInformation);
          goto LABEL_123;
        }
        LastError = 2;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          v16 = 74;
LABEL_24:
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v15, 2);
          goto LABEL_123;
        }
        goto LABEL_123;
      }
LABEL_2:
      VCManager::ChannelClose(*(VCManager **)(*((_QWORD *)this + 7) + 224LL));
      goto LABEL_129;
    }
    if ( (unsigned int)v12 < 8 )
      goto LABEL_2;
    LastError = 0;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v18);
      v17 = WPP_GLOBAL_Control;
    }
    if ( *v11 )
      goto LABEL_123;
    if ( v9 == -1 )
    {
      if ( v17 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v17[7] & 1) != 0 && *((_BYTE *)v17 + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v22);
      }
      LastError = 2;
      goto LABEL_123;
    }
    if ( SetFilePointer((HANDLE)v9, 0, 0, 0) == -1 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v19 = GetLastError();
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 83;
    }
    else
    {
      if ( SetEndOfFile((HANDLE)v9) )
        goto LABEL_123;
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v19 = GetLastError();
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 82;
    }
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v20, v19);
LABEL_43:
    LastError = GetLastError();
    goto LABEL_123;
  }
  v23 = *(const WCHAR **)(ObjectW + 128);
  if ( v23 )
  {
    if ( !*(_DWORD *)(ObjectW + 120) )
    {
      (*(void (__fastcall **)(__int64, __int64, HKEY *))(*(_QWORD *)ObjectW + 40LL))(ObjectW, v12, &WPP_GLOBAL_Control);
      if ( (*((_DWORD *)this + 154) & 0x4000000) != 0 || DeleteFileW(v6[16]) )
        goto LABEL_53;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 75;
LABEL_91:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids,
        v24,
        LastError);
      goto LABEL_123;
    }
    if ( !RemoveDirectoryW(v23) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 76;
      goto LABEL_91;
    }
    goto LABEL_53;
  }
  LastError = 2;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 77;
    goto LABEL_24;
  }
LABEL_123:
  if ( DrUTL_AllocIOCompletePacket(a2, 0x15u) )
  {
    v35 = TranslateWinError(LastError);
    v36[3] = v35;
    v36[4] = *((_DWORD *)a2 + 7);
    VCManager::ChannelWrite(*(VCManager **)(*((_QWORD *)this + 7) + 224LL), v36, 0x15u);
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v37 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v37, 21);
  }
LABEL_129:
  operator delete(a2);
  if ( v6 )
    RefCount::Release((RefCount *)v6);
}

```

## disassembly

```asm
0x18055c370  mov     [rsp-8+arg_10], rbx
0x18055c375  push    rbp
0x18055c376  push    rsi
0x18055c377  push    rdi
0x18055c378  push    r12
0x18055c37a  push    r13
0x18055c37c  push    r14
0x18055c37e  push    r15
0x18055c380  lea     rbp, [rsp-170h]
0x18055c388  sub     rsp, 270h
0x18055c38f  mov     rax, cs:__security_cookie
0x18055c396  xor     rax, rsp
0x18055c399  mov     [rbp+1A0h+var_40], rax
0x18055c3a0  xor     r14d, r14d
0x18055c3a3  mov     r13, rcx
0x18055c3a6  mov     ecx, [rdx+1Ch]
0x18055c3a9  mov     r12, rdx
0x18055c3ac  mov     esi, r14d
0x18055c3af  lea     eax, [rcx+38h]
0x18055c3b2  cmp     eax, 38h ; '8'
0x18055c3b5  jnb     short loc_18055C3CC
0x18055c3b7  mov     rcx, [r13+38h]
0x18055c3bb  mov     rcx, [rcx+0E0h]; this
0x18055c3c2  call    ?ChannelClose@VCManager@@QEAAIXZ; VCManager::ChannelClose(void)
0x18055c3c7  jmp     loc_18055CB3E
0x18055c3cc  add     rcx, 38h ; '8'
0x18055c3d0  mov     eax, r8d
0x18055c3d3  cmp     rax, rcx
0x18055c3d6  jb      short loc_18055C3B7
0x18055c3d8  mov     edx, [rdx+8]
0x18055c3db  mov     rcx, [r13+40h]
0x18055c3df  call    ?GetObjectW@?$DrObjectMgr@VDrFile@@@@QEAAPEAVDrFile@@K@Z; DrObjectMgr<DrFile>::GetObjectW(ulong)
0x18055c3e4  xor     r10d, r10d
0x18055c3e7  lea     r8, WPP_GLOBAL_Control
0x18055c3ee  mov     rsi, rax
0x18055c3f1  mov     r11d, 2
0x18055c3f7  test    rax, rax
0x18055c3fa  jz      loc_18055CAB3
0x18055c400  or      r15, 0FFFFFFFFFFFFFFFFh
0x18055c404  mov     r14, r15
0x18055c407  cmp     [rax+30h], r10d
0x18055c40b  jnz     short loc_18055C411
0x18055c40d  mov     r14, [rax+20h]
0x18055c411  mov     ebx, [r12+18h]
0x18055c416  lea     rdi, [r12+38h]
0x18055c41b  mov     edx, [r12+1Ch]
0x18055c420  mov     ecx, ebx
0x18055c422  sub     ecx, 4
0x18055c425  jz      loc_18055C952
0x18055c42b  sub     ecx, 6
0x18055c42e  jz      loc_18055C7A2
0x18055c434  sub     ecx, 3
0x18055c437  jz      loc_18055C689
0x18055c43d  sub     ecx, 6
0x18055c440  jz      loc_18055C525
0x18055c446  cmp     ecx, 1
0x18055c449  jz      short loc_18055C495
0x18055c44b  mov     rax, cs:WPP_GLOBAL_Control
0x18055c452  cmp     rax, r8
0x18055c455  jz      short loc_18055C48B
0x18055c457  test    byte ptr [rax+1Ch], 1
0x18055c45b  jz      short loc_18055C48B
0x18055c45d  cmp     [rax+19h], r11b
0x18055c461  jb      short loc_18055C48B
0x18055c463  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c468  mov     rcx, cs:WPP_GLOBAL_Control
0x18055c46f  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055c476  mov     edx, 55h ; 'U'
0x18055c47b  mov     [rsp+2A0h+FileInformationClass], ebx
0x18055c47f  mov     r9d, eax
0x18055c482  mov     rcx, [rcx+10h]
0x18055c486  call    WPP_SF_Dd
0x18055c48b  mov     ebx, 1
0x18055c490  jmp     loc_18055CAB6
0x18055c495  cmp     edx, 8
0x18055c498  jb      loc_18055C3B7
0x18055c49e  cmp     r14, r15
0x18055c4a1  jz      short loc_18055C4D1
0x18055c4a3  xorps   xmm0, xmm0
0x18055c4a6  mov     [rsp+2A0h+FileInformationClass], 14h; FileInformationClass
0x18055c4ae  mov     r9d, 8; Length
0x18055c4b4  lea     rdx, [rsp+2A0h+IoStatusBlock]; IoStatusBlock
0x18055c4b9  mov     r8, rdi; FileInformation
0x18055c4bc  mov     rcx, r14; FileHandle
0x18055c4bf  movups  xmmword ptr [rsp+2A0h+IoStatusBlock], xmm0
0x18055c4c4  call    cs:__imp_NtSetInformationFile
0x18055c4ca  mov     ebx, eax
0x18055c4cc  jmp     loc_18055CAB6
0x18055c4d1  mov     ebx, r11d
0x18055c4d4  mov     rax, cs:WPP_GLOBAL_Control
0x18055c4db  cmp     rax, r8
0x18055c4de  jz      loc_18055CAB6
0x18055c4e4  test    byte ptr [rax+1Ch], 1
0x18055c4e8  jz      loc_18055CAB6
0x18055c4ee  cmp     [rax+19h], r11b
0x18055c4f2  jb      loc_18055CAB6
0x18055c4f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c4fd  mov     edx, 4Ah ; 'J'
0x18055c502  mov     rcx, cs:WPP_GLOBAL_Control
0x18055c509  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055c510  mov     r9d, eax
0x18055c513  mov     [rsp+2A0h+FileInformationClass], ebx
0x18055c517  mov     rcx, [rcx+10h]
0x18055c51b  call    WPP_SF_Dd
0x18055c520  jmp     loc_18055CAB6
0x18055c525  cmp     edx, 8
0x18055c528  jb      loc_18055C3B7
0x18055c52e  mov     ebx, r10d
0x18055c531  mov     rax, cs:WPP_GLOBAL_Control
0x18055c538  cmp     rax, r8
0x18055c53b  jz      short loc_18055C582
0x18055c53d  test    byte ptr [rax+1Ch], 1
0x18055c541  jz      short loc_18055C582
0x18055c543  cmp     byte ptr [rax+19h], 4
0x18055c547  jb      short loc_18055C582
0x18055c549  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c54e  mov     rcx, cs:WPP_GLOBAL_Control
0x18055c555  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055c55c  mov     edx, 51h ; 'Q'
0x18055c561  mov     r9d, eax
0x18055c564  mov     rcx, [rcx+10h]
0x18055c568  call    WPP_SF_d
0x18055c56d  mov     rax, cs:WPP_GLOBAL_Control
0x18055c574  lea     r8, WPP_GLOBAL_Control
0x18055c57b  xor     r10d, r10d
0x18055c57e  lea     r11d, [r10+2]
0x18055c582  cmp     [rdi], r10
0x18055c585  jnz     loc_18055CAB6
0x18055c58b  cmp     r14, r15
0x18055c58e  jz      loc_18055C64A
0x18055c594  xor     r9d, r9d; dwMoveMethod
0x18055c597  xor     r8d, r8d; lpDistanceToMoveHigh
0x18055c59a  xor     edx, edx; lDistanceToMove
0x18055c59c  mov     rcx, r14; hFile
0x18055c59f  call    cs:__imp_SetFilePointer
0x18055c5a5  cmp     eax, 0FFFFFFFFh
0x18055c5a8  jz      short loc_18055C5EE
0x18055c5aa  mov     rcx, r14; hFile
0x18055c5ad  call    cs:__imp_SetEndOfFile
0x18055c5b3  test    eax, eax
0x18055c5b5  jnz     loc_18055CAB6
0x18055c5bb  mov     rax, cs:WPP_GLOBAL_Control
0x18055c5c2  lea     rdi, WPP_GLOBAL_Control
0x18055c5c9  cmp     rax, rdi
0x18055c5cc  jz      short loc_18055C63D
0x18055c5ce  test    byte ptr [rax+1Ch], 1
0x18055c5d2  jz      short loc_18055C63D
0x18055c5d4  cmp     byte ptr [rax+19h], 2
0x18055c5d8  jb      short loc_18055C63D
0x18055c5da  call    cs:__imp_GetLastError
0x18055c5e0  mov     ebx, eax
0x18055c5e2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c5e7  mov     edx, 52h ; 'R'
0x18055c5ec  jmp     short loc_18055C61F
0x18055c5ee  mov     rax, cs:WPP_GLOBAL_Control
0x18055c5f5  lea     rdi, WPP_GLOBAL_Control
0x18055c5fc  cmp     rax, rdi
0x18055c5ff  jz      short loc_18055C63D
0x18055c601  test    byte ptr [rax+1Ch], 1
0x18055c605  jz      short loc_18055C63D
0x18055c607  cmp     byte ptr [rax+19h], 2
0x18055c60b  jb      short loc_18055C63D
0x18055c60d  call    cs:__imp_GetLastError
0x18055c613  mov     ebx, eax
0x18055c615  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c61a  mov     edx, 53h ; 'S'
0x18055c61f  mov     rcx, cs:WPP_GLOBAL_Control
0x18055c626  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055c62d  mov     r9d, eax
0x18055c630  mov     [rsp+2A0h+FileInformationClass], ebx
0x18055c634  mov     rcx, [rcx+10h]
0x18055c638  call    WPP_SF_Dd
0x18055c63d  call    cs:__imp_GetLastError
0x18055c643  mov     ebx, eax
0x18055c645  jmp     loc_18055CABD
0x18055c64a  cmp     rax, r8
0x18055c64d  jz      short loc_18055C67F
0x18055c64f  test    byte ptr [rax+1Ch], 1
0x18055c653  jz      short loc_18055C67F
0x18055c655  cmp     [rax+19h], r11b
0x18055c659  jb      short loc_18055C67F
0x18055c65b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c660  mov     rcx, cs:WPP_GLOBAL_Control
0x18055c667  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055c66e  mov     edx, 54h ; 'T'
0x18055c673  mov     r9d, eax
0x18055c676  mov     rcx, [rcx+10h]
0x18055c67a  call    WPP_SF_d
0x18055c67f  mov     ebx, 2
0x18055c684  jmp     loc_18055CAB6
0x18055c689  mov     rcx, [rax+80h]; lpPathName
0x18055c690  test    rcx, rcx
0x18055c693  jz      loc_18055C76C
0x18055c699  cmp     [rax+78h], r10d
0x18055c69d  jnz     short loc_18055C71E
0x18055c69f  mov     rax, [rax]
0x18055c6a2  mov     rcx, rsi
0x18055c6a5  mov     rax, [rax+28h]
0x18055c6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055c6ae  test    dword ptr [r13+268h], 4000000h
0x18055c6b9  jnz     short loc_18055C719
0x18055c6bb  mov     rcx, [rsi+80h]; lpFileName
0x18055c6c2  call    cs:__imp_DeleteFileW
0x18055c6c8  xor     r14d, r14d
0x18055c6cb  test    eax, eax
0x18055c6cd  jz      short loc_18055C6D7
0x18055c6cf  mov     ebx, r14d
0x18055c6d2  jmp     loc_18055CAB6
0x18055c6d7  call    cs:__imp_GetLastError
0x18055c6dd  mov     ebx, eax
0x18055c6df  mov     rax, cs:WPP_GLOBAL_Control
0x18055c6e6  lea     rdi, WPP_GLOBAL_Control
0x18055c6ed  cmp     rax, rdi
0x18055c6f0  jz      loc_18055CABD
0x18055c6f6  test    byte ptr [rax+1Ch], 1
0x18055c6fa  jz      loc_18055CABD
0x18055c700  cmp     byte ptr [rax+19h], 2
0x18055c704  jb      loc_18055CABD
0x18055c70a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c70f  mov     edx, 4Bh ; 'K'
0x18055c714  jmp     loc_18055C8F9
0x18055c719  xor     r14d, r14d
0x18055c71c  jmp     short loc_18055C6CF
0x18055c71e  call    cs:__imp_RemoveDirectoryW
0x18055c724  xor     r14d, r14d
0x18055c727  test    eax, eax
0x18055c729  jnz     short loc_18055C6CF
0x18055c72b  call    cs:__imp_GetLastError
0x18055c731  mov     ebx, eax
0x18055c733  mov     rax, cs:WPP_GLOBAL_Control
0x18055c73a  lea     rdi, WPP_GLOBAL_Control
0x18055c741  cmp     rax, rdi
0x18055c744  jz      loc_18055CABD
0x18055c74a  test    byte ptr [rax+1Ch], 1
0x18055c74e  jz      loc_18055CABD
0x18055c754  cmp     byte ptr [rax+19h], 2
0x18055c758  jb      loc_18055CABD
0x18055c75e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c763  lea     edx, [r14+4Ch]
0x18055c767  jmp     loc_18055C8F9
0x18055c76c  mov     ebx, r11d
0x18055c76f  mov     rax, cs:WPP_GLOBAL_Control
0x18055c776  cmp     rax, r8
0x18055c779  jz      loc_18055CAB6
0x18055c77f  test    byte ptr [rax+1Ch], 1
0x18055c783  jz      loc_18055CAB6
0x18055c789  cmp     [rax+19h], r11b
0x18055c78d  jb      loc_18055CAB6
0x18055c793  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055c798  mov     edx, 4Dh ; 'M'
0x18055c79d  jmp     loc_18055C502
0x18055c7a2  cmp     edx, 8
0x18055c7a5  jb      loc_18055C3B7
0x18055c7ab  mov     eax, [rdi+2]
0x18055c7ae  lea     ecx, [rax+6]
0x18055c7b1  cmp     ecx, eax
0x18055c7b3  jb      loc_18055C3B7
0x18055c7b9  cmp     edx, ecx
0x18055c7bb  jb      loc_18055C3B7
0x18055c7c1  cmp     [rsi+80h], r10
0x18055c7c8  jz      loc_18055C91C
0x18055c7ce  mov     rax, [rsi]
0x18055c7d1  mov     rcx, rsi
0x18055c7d4  mov     rax, [rax+28h]
0x18055c7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055c7dd  xor     r14d, r14d
0x18055c7e0  cmp     [rdi+1], r14b
0x18055c7e4  jnz     short loc_18055C7FB
0x18055c7e6  lea     r8, [r13+58h]; unsigned __int16 *
0x18055c7ea  mov     edx, 104h; unsigned __int64
0x18055c7ef  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x18055c7f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18055c7f9  jmp     short loc_18055C801
0x18055c7fb  mov     [rsp+2A0h+FileName], r14w
0x18055c801  lea     rax, [rsp+2A0h+FileName]
0x18055c806  inc     r15
0x18055c809  cmp     [rax+r15*2], r14w
0x18055c80e  jnz     short loc_18055C806
0x18055c810  mov     ecx, [rdi+2]
0x18055c813  lea     r8, [rdi+6]; unsigned __int16 *
0x18055c817  add     rcx, 2
0x18055c81b  mov     edx, 103h
0x18055c820  sub     edx, r15d
0x18055c823  add     rdx, rdx
0x18055c826  cmp     rdx, rcx
0x18055c829  cmovnb  rdx, rcx; unsigned __int64
0x18055c82d  lea     rcx, [rsp+2A0h+FileName]
0x18055c832  lea     rcx, [rcx+r15*2]; unsigned __int16 *
0x18055c836  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18055c83b  mov     ebx, eax
0x18055c83d  test    eax, eax
0x18055c83f  jns     short loc_18055C892
0x18055c841  mov     rcx, cs:WPP_GLOBAL_Control
0x18055c848  lea     rdi, WPP_GLOBAL_Control
0x18055c84f  cmp     rcx, rdi
0x18055c852  jz      short loc_18055C888
0x18055c854  test    byte ptr [rcx+1Ch], 1
0x18055c858  jz      short loc_18055C888
0x18055c85a  cmp     byte ptr [rcx+19h], 2
0x18055c85e  jb      short loc_18055C888
  ... truncated ...
```
