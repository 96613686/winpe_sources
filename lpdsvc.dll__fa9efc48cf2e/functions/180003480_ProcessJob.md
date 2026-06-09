# ProcessJob

- ea: `0x180003480`
- end: `0x180003c96`
- name: `ProcessJob`
- size: `2070`
- prototype: `_UNKNOWN **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007354`

## callees

- `0x180002e7c`
- `0x180002ea4`
- `0x1800030c0`
- `0x18000327c`
- `0x180003480`
- `0x180003c9c`
- `0x180003d4c`
- `0x180004950`
- `0x180005058`
- `0x180005910`
- `0x180008eb8`
- `0x180009800`
- `0x1800099a8`
- `0x18000a038`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180003616`
- `KERNEL32!LocalAlloc` at `0x1800036ac`
- `KERNEL32!LocalAlloc` at `0x180003616`
- `KERNEL32!LocalAlloc` at `0x1800036ac`
- `KERNEL32!GetLastError` at `0x18000393c`
- `KERNEL32!GetLastError` at `0x1800039ad`
- `KERNEL32!GetLastError` at `0x180003a5b`
- `KERNEL32!GetLastError` at `0x180003aa9`
- `KERNEL32!GetLastError` at `0x180003c1f`
- `KERNEL32!GetLastError` at `0x18000393c`
- `KERNEL32!GetLastError` at `0x1800039ad`
- `KERNEL32!GetLastError` at `0x180003a5b`
- `KERNEL32!GetLastError` at `0x180003aa9`
- `KERNEL32!GetLastError` at `0x180003c1f`
- `KERNEL32!WriteFile` at `0x18000373b`
- `KERNEL32!WriteFile` at `0x18000373b`
- `KERNEL32!CloseHandle` at `0x180003a17`
- `KERNEL32!CloseHandle` at `0x180003a17`
- `KERNEL32!CreateFileA` at `0x180003675`
- `KERNEL32!CreateFileA` at `0x180003675`
- `KERNEL32!LocalFree` at `0x18000357d`
- `KERNEL32!LocalFree` at `0x180003683`
- `KERNEL32!LocalFree` at `0x180003774`
- `KERNEL32!LocalFree` at `0x180003a0d`
- `KERNEL32!LocalFree` at `0x180003a20`
- `KERNEL32!LocalFree` at `0x180003a32`
- `KERNEL32!LocalFree` at `0x180003bfc`
- `KERNEL32!LocalFree` at `0x18000357d`
- `KERNEL32!LocalFree` at `0x180003683`
- `KERNEL32!LocalFree` at `0x180003774`
- `KERNEL32!LocalFree` at `0x180003a0d`
- `KERNEL32!LocalFree` at `0x180003a20`
- `KERNEL32!LocalFree` at `0x180003a32`
- `KERNEL32!LocalFree` at `0x180003bfc`

## pseudocode

```c
_UNKNOWN **__fastcall ProcessJob(__int64 a1)
{
  HLOCAL v1; // rsi
  _UNKNOWN **result; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  void *v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rdx
  _QWORD *v9; // rdi
  unsigned int v10; // r15d
  void *v11; // rcx
  HANDLE FileA; // rax
  CHAR *v13; // rcx
  bool v14; // zf
  DWORD v15; // r14d
  unsigned int v16; // r13d
  unsigned int v17; // r12d
  void *v18; // rax
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rbx
  DWORD v23; // eax
  __int64 v24; // rbx
  DWORD v25; // eax
  void *v26; // rcx
  __int64 v27; // rbx
  DWORD v28; // eax
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rbx
  DWORD LastError; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  SOCKET v36; // rcx
  LPCSTR lpFileName; // [rsp+40h] [rbp-20h] BYREF
  void *v38; // [rsp+48h] [rbp-18h]
  __int64 v39; // [rsp+50h] [rbp-10h]
  char buf; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v41; // [rsp+B0h] [rbp+50h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp+58h] BYREF

  v1 = 0;
  v41 = 0;
  buf = 0;
  lpFileName = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
  if ( (unsigned int)InitializePrinter(a1) )
  {
    v38 = *(void **)(a1 + 88);
    v39 = a1 + 120;
    result = (_UNKNOWN **)LpdReportEvent(0xC0000FA9);
    *(_DWORD *)(a1 + 24) = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return result;
    v5 = 11;
    return (_UNKNOWN **)WPP_SF_(v4[2], v5, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
  }
  result = (_UNKNOWN **)ReplyToClient(a1, 0);
  if ( (_DWORD)result )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return result;
    v5 = 12;
    return (_UNKNOWN **)WPP_SF_(v4[2], v5, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v6 = *(void **)(a1 + 32);
      if ( v6 )
      {
        LocalFree(v6);
        *(_QWORD *)(a1 + 32) = 0;
      }
      result = (_UNKNOWN **)GetCmdFromClient(a1);
      v7 = (unsigned int)result;
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == 3 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
          v36 = *(_QWORD *)(a1 + 8);
          if ( v36 != -1 )
          {
            SureCloseSocket(v36);
            *(_QWORD *)(a1 + 8) = -1;
          }
          result = (_UNKNOWN **)PrintData(a1);
          *(_WORD *)(a1 + 20) = 10;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          LastError = GetLastError();
          return (_UNKNOWN **)WPP_SF_dD(v32, v34, v35, v7, LastError);
        }
        return result;
      }
      if ( **(_BYTE **)(a1 + 32) == 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
        result = (_UNKNOWN **)ReplyToClient(a1, 0);
        *(_WORD *)(a1 + 20) = 10;
        goto LABEL_112;
      }
      if ( **(_BYTE **)(a1 + 32) != 2 )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
      *(_WORD *)(a1 + 20) = 22;
      if ( (unsigned int)ParseSubCommand(a1, &v41, &lpFileName) )
      {
        v39 = 0;
        v38 = (void *)(a1 + 120);
        result = (_UNKNOWN **)LpdReportEvent(0xC0000FA8);
        *(_DWORD *)(a1 + 24) = 0;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v31 = 16;
LABEL_107:
          result = (_UNKNOWN **)WPP_SF_(v30[2], v31, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
        }
LABEL_112:
        if ( lpFileName )
          return (_UNKNOWN **)LocalFree((HLOCAL)lpFileName);
        return result;
      }
      result = (_UNKNOWN **)ReplyToClient(a1, 0);
      if ( (_DWORD)result )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v31 = 17;
          goto LABEL_107;
        }
        goto LABEL_112;
      }
      result = (_UNKNOWN **)GetControlFileFromClient(a1, v41, lpFileName);
      if ( (_DWORD)result )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v31 = 18;
          goto LABEL_107;
        }
        goto LABEL_112;
      }
      lpFileName = 0;
      *(_WORD *)(a1 + 20) = 23;
      result = (_UNKNOWN **)ReplyToClient(a1, 0);
      if ( (_DWORD)result )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v5 = 19;
          return (_UNKNOWN **)WPP_SF_(v4[2], v5, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
        }
        return result;
      }
    }
    if ( **(_BYTE **)(a1 + 32) != 3 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)result + 20),
        &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
    *(_WORD *)(a1 + 20) = 24;
    result = (_UNKNOWN **)ReplyToClient(a1, 0);
    if ( (_DWORD)result )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v5 = 21;
        return (_UNKNOWN **)WPP_SF_(v4[2], v5, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
      }
      return result;
    }
    if ( (unsigned int)ParseSubCommand(a1, &v41, &lpFileName) )
    {
      v39 = 0;
      v38 = (void *)(a1 + 120);
      result = (_UNKNOWN **)LpdReportEvent(0xC0000FA8);
      *(_DWORD *)(a1 + 24) = 0;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_112;
      v27 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v28 = GetLastError();
      v29 = 22;
LABEL_91:
      result = (_UNKNOWN **)WPP_SF_d(v27, v29, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids, v28);
      goto LABEL_112;
    }
    *(_WORD *)(a1 + 20) = 25;
    result = (_UNKNOWN **)LocalAlloc(0, 0x28u);
    v9 = result;
    if ( !result )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_112;
      v27 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v28 = GetLastError();
      v29 = 23;
      goto LABEL_91;
    }
    v10 = v41;
    *((_DWORD *)result + 6) = v41;
    result[2] = lpFileName;
    v11 = *(void **)(a1 + 96);
    lpFileName = 0;
    if ( !(unsigned int)GetSpoolFileName(v11, v8, &lpFileName) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v21 = 24;
LABEL_80:
        WPP_SF_(v20[2], v21, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
      }
LABEL_81:
      v26 = (void *)v9[2];
      if ( v26 )
        LocalFree(v26);
      CloseHandle((HANDLE)v9[4]);
      result = (_UNKNOWN **)LocalFree(v9);
      if ( v1 )
        result = (_UNKNOWN **)LocalFree(v1);
      goto LABEL_112;
    }
    FileA = CreateFileA(lpFileName, 0xC0000000, 1u, 0, 4u, 0xC000180u, 0);
    v13 = (CHAR *)lpFileName;
    v9[4] = FileA;
    LocalFree(v13);
    v14 = v9[4] == -1;
    lpFileName = 0;
    if ( v14 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v21 = 25;
        goto LABEL_80;
      }
      goto LABEL_81;
    }
    v15 = v10;
    if ( v10 > 0x7D00 )
      v15 = 32000;
    v1 = LocalAlloc(0, v15);
    if ( !v1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v25 = GetLastError();
        WPP_SF_d(v24, 26, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids, v25);
      }
      goto LABEL_81;
    }
    v16 = 0;
    v17 = v10;
    if ( v10 )
    {
      while ( !(unsigned int)ReadData(*(_QWORD *)(a1 + 8), (char *)v1, v15) )
      {
        v18 = (void *)v9[4];
        v38 = v18;
        NumberOfBytesWritten = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
          v18 = v38;
        }
        if ( !WriteFile(v18, v1, v15, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != v15 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
              v20 = WPP_GLOBAL_Control;
            }
            if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 )
            {
              v21 = 28;
              goto LABEL_80;
            }
          }
          goto LABEL_81;
        }
        v16 += v15;
        v17 -= v15;
        v15 = v17;
        if ( v17 > 0x7D00 )
          v15 = 32000;
        if ( v16 >= v10 )
          goto LABEL_40;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v21 = 27;
        goto LABEL_80;
      }
      goto LABEL_81;
    }
LABEL_40:
    LocalFree(v1);
    v19 = *(_QWORD **)(a1 + 72);
    if ( *v19 != a1 + 64 )
      __fastfail(3u);
    *v9 = a1 + 64;
    v9[1] = v19;
    *v19 = v9;
    *(_QWORD *)(a1 + 72) = v9;
    v1 = 0;
    if ( (unsigned int)ReadData(*(_QWORD *)(a1 + 8), &buf, 1) || buf )
    {
      v4 = WPP_GLOBAL_Control;
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v5 = 29;
        return (_UNKNOWN **)WPP_SF_(v4[2], v5, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
      }
      return result;
    }
    if ( (unsigned int)ReplyToClient(a1, 0) )
    {
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v22 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v23 = GetLastError();
        return (_UNKNOWN **)WPP_SF_d(v22, 30, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids, v23);
      }
      return result;
    }
  }
  v39 = 0;
  v38 = (void *)(a1 + 120);
  result = (_UNKNOWN **)LpdReportEvent(0xC0000FA5);
  *(_DWORD *)(a1 + 24) = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v5 = 32;
    return (_UNKNOWN **)WPP_SF_(v4[2], v5, &WPP_bc5dfa190b42335729027cd8699dae89_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180003480  mov     [rsp-38h+arg_0], rbx
0x180003485  push    rbp
0x180003486  push    rsi
0x180003487  push    rdi
0x180003488  push    r12
0x18000348a  push    r13
0x18000348c  push    r14
0x18000348e  push    r15
0x180003490  mov     rbp, rsp
0x180003493  sub     rsp, 60h
0x180003497  xor     esi, esi
0x180003499  mov     rbx, rcx
0x18000349c  mov     [rbp+arg_10], esi
0x18000349f  mov     [rbp+buf], sil
0x1800034a3  mov     [rbp+lpFileName], rsi
0x1800034a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034ae  lea     r12, WPP_GLOBAL_Control
0x1800034b5  lea     r14d, [rsi+1]
0x1800034b9  lea     r13, WPP_bc5dfa190b42335729027cd8699dae89_Traceguids
0x1800034c0  cmp     rcx, r12
0x1800034c3  jz      short loc_1800034DA
0x1800034c5  test    [rcx+1Ch], r14b
0x1800034c9  jz      short loc_1800034DA
0x1800034cb  mov     rcx, [rcx+10h]
0x1800034cf  lea     edx, [rsi+0Ah]
0x1800034d2  mov     r8, r13
0x1800034d5  call    WPP_SF_
0x1800034da  mov     rcx, rbx
0x1800034dd  call    InitializePrinter
0x1800034e2  test    eax, eax
0x1800034e4  jz      short loc_18000353F
0x1800034e6  mov     rax, [rbx+58h]
0x1800034ea  lea     r8, [rbp+var_18]
0x1800034ee  mov     [rbp+var_18], rax
0x1800034f2  mov     edx, 2
0x1800034f7  lea     rax, [rbx+78h]
0x1800034fb  xor     r9d, r9d
0x1800034fe  mov     ecx, 0C0000FA9h; dwEventID
0x180003503  mov     [rbp+var_10], rax
0x180003507  call    LpdReportEvent
0x18000350c  mov     [rbx+18h], esi
0x18000350f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003516  cmp     rcx, r12
0x180003519  jz      loc_180003C7E
0x18000351f  test    byte ptr [rcx+1Ch], 8
0x180003523  jz      loc_180003C7E
0x180003529  mov     edx, 0Bh
0x18000352e  mov     r8, r13
0x180003531  mov     rcx, [rcx+10h]
0x180003535  call    WPP_SF_
0x18000353a  jmp     loc_180003C7E
0x18000353f  xor     edx, edx
0x180003541  mov     rcx, rbx
0x180003544  call    ReplyToClient
0x180003549  test    eax, eax
0x18000354b  jz      short loc_18000356E
0x18000354d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003554  cmp     rcx, r12
0x180003557  jz      loc_180003C7E
0x18000355d  test    byte ptr [rcx+1Ch], 8
0x180003561  jz      loc_180003C7E
0x180003567  mov     edx, 0Ch
0x18000356c  jmp     short loc_18000352E
0x18000356e  mov     r15d, 18h
0x180003574  mov     rcx, [rbx+20h]; hMem
0x180003578  test    rcx, rcx
0x18000357b  jz      short loc_180003587
0x18000357d  call    cs:__imp_LocalFree
0x180003583  mov     [rbx+20h], rsi
0x180003587  mov     rcx, rbx
0x18000358a  call    GetCmdFromClient
0x18000358f  mov     edi, eax
0x180003591  test    eax, eax
0x180003593  jnz     loc_180003C04
0x180003599  mov     rax, [rbx+20h]
0x18000359d  movsx   ecx, byte ptr [rax]
0x1800035a0  sub     ecx, 1
0x1800035a3  jz      loc_180003BBC
0x1800035a9  sub     ecx, 1
0x1800035ac  jz      loc_1800037E8
0x1800035b2  cmp     ecx, 1
0x1800035b5  jnz     loc_180003AEB
0x1800035bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035c2  cmp     rcx, r12
0x1800035c5  jz      short loc_1800035DC
0x1800035c7  test    byte ptr [rcx+1Ch], 2
0x1800035cb  jz      short loc_1800035DC
0x1800035cd  mov     rcx, [rcx+10h]
0x1800035d1  lea     edx, [rdi+14h]
0x1800035d4  mov     r8, r13
0x1800035d7  call    WPP_SF_
0x1800035dc  xor     edx, edx
0x1800035de  mov     [rbx+14h], r15w
0x1800035e3  mov     rcx, rbx
0x1800035e6  call    ReplyToClient
0x1800035eb  test    eax, eax
0x1800035ed  jnz     loc_180003AC7
0x1800035f3  lea     r8, [rbp+lpFileName]
0x1800035f7  mov     rcx, rbx
0x1800035fa  lea     rdx, [rbp+arg_10]
0x1800035fe  call    ParseSubCommand
0x180003603  test    eax, eax
0x180003605  jnz     loc_180003A68
0x18000360b  lea     edx, [rax+28h]; uBytes
0x18000360e  mov     word ptr [rbx+14h], 19h
0x180003614  xor     ecx, ecx; uFlags
0x180003616  call    cs:__imp_LocalAlloc
0x18000361c  mov     rdi, rax
0x18000361f  test    rax, rax
0x180003622  jz      loc_180003A3D
0x180003628  mov     r15d, [rbp+arg_10]
0x18000362c  lea     r8, [rbp+lpFileName]
0x180003630  mov     [rax+18h], r15d
0x180003634  mov     rax, [rbp+lpFileName]
0x180003638  mov     [rdi+10h], rax
0x18000363c  mov     rcx, [rbx+60h]; hPrinter
0x180003640  mov     [rbp+lpFileName], rsi
0x180003644  call    GetSpoolFileName
0x180003649  test    eax, eax
0x18000364b  jz      loc_1800039E1
0x180003651  mov     rcx, [rbp+lpFileName]; lpFileName
0x180003655  xor     r9d, r9d; lpSecurityAttributes
0x180003658  mov     [rsp+60h+hTemplateFile], rsi; hTemplateFile
0x18000365d  mov     r8d, r14d; dwShareMode
0x180003660  mov     [rsp+60h+dwFlagsAndAttributes], 0C000180h; dwFlagsAndAttributes
0x180003668  mov     edx, 0C0000000h; dwDesiredAccess
0x18000366d  mov     [rsp+60h+dwCreationDisposition], 4; dwCreationDisposition
0x180003675  call    cs:__imp_CreateFileA
0x18000367b  mov     rcx, [rbp+lpFileName]; hMem
0x18000367f  mov     [rdi+20h], rax
0x180003683  call    cs:__imp_LocalFree
0x180003689  cmp     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x18000368e  mov     [rbp+lpFileName], rsi
0x180003692  jz      loc_1800039C8
0x180003698  mov     eax, 7D00h
0x18000369d  mov     r14d, r15d
0x1800036a0  cmp     r15d, eax
0x1800036a3  cmova   r14d, eax
0x1800036a7  xor     ecx, ecx; uFlags
0x1800036a9  mov     edx, r14d; uBytes
0x1800036ac  call    cs:__imp_LocalAlloc
0x1800036b2  mov     rsi, rax
0x1800036b5  test    rax, rax
0x1800036b8  jz      loc_180003997
0x1800036be  xor     r13d, r13d
0x1800036c1  mov     r12d, r15d
0x1800036c4  test    r15d, r15d
0x1800036c7  jz      loc_180003771
0x1800036cd  mov     rcx, [rbx+8]; s
0x1800036d1  mov     r8d, r14d; len
0x1800036d4  mov     rdx, rsi; buf
0x1800036d7  call    ReadData
0x1800036dc  test    eax, eax
0x1800036de  jnz     loc_1800038EF
0x1800036e4  mov     rax, [rdi+20h]
0x1800036e8  mov     [rbp+var_18], rax
0x1800036ec  mov     [rbp+NumberOfBytesWritten], 0
0x1800036f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036fa  lea     rdx, WPP_GLOBAL_Control
0x180003701  cmp     rcx, rdx
0x180003704  jz      short loc_180003725
0x180003706  test    byte ptr [rcx+1Ch], 1
0x18000370a  jz      short loc_180003725
0x18000370c  mov     rcx, [rcx+10h]
0x180003710  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180003717  mov     edx, 35h ; '5'
0x18000371c  call    WPP_SF_
0x180003721  mov     rax, [rbp+var_18]
0x180003725  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003729  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x180003732  mov     r8d, r14d; nNumberOfBytesToWrite
0x180003735  mov     rdx, rsi; lpBuffer
0x180003738  mov     rcx, rax; hFile
0x18000373b  call    cs:__imp_WriteFile
0x180003741  test    eax, eax
0x180003743  jz      loc_180003892
0x180003749  cmp     [rbp+NumberOfBytesWritten], r14d
0x18000374d  jnz     loc_180003892
0x180003753  add     r13d, r14d
0x180003756  sub     r12d, r14d
0x180003759  mov     eax, 7D00h
0x18000375e  mov     r14d, r12d
0x180003761  cmp     r12d, eax
0x180003764  cmova   r14d, eax
0x180003768  cmp     r13d, r15d
0x18000376b  jb      loc_1800036CD
0x180003771  mov     rcx, rsi; hMem
0x180003774  call    cs:__imp_LocalFree
0x18000377a  lea     rax, [rbx+40h]
0x18000377e  mov     rcx, [rax+8]
0x180003782  cmp     [rcx], rax
0x180003785  jnz     loc_180003990
0x18000378b  mov     [rdi], rax
0x18000378e  lea     rdx, [rbp+buf]; buf
0x180003792  mov     [rdi+8], rcx
0x180003796  mov     r14d, 1
0x18000379c  mov     [rcx], rdi
0x18000379f  mov     r8d, r14d; len
0x1800037a2  mov     [rax+8], rdi
0x1800037a6  mov     rcx, [rbx+8]; s
0x1800037aa  call    ReadData
0x1800037af  xor     esi, esi
0x1800037b1  test    eax, eax
0x1800037b3  jnz     loc_18000395E
0x1800037b9  cmp     [rbp+buf], sil
0x1800037bd  jnz     loc_18000395E
0x1800037c3  xor     edx, edx
0x1800037c5  mov     rcx, rbx
0x1800037c8  call    ReplyToClient
0x1800037cd  test    eax, eax
0x1800037cf  jnz     loc_180003917
0x1800037d5  lea     r12, WPP_GLOBAL_Control
0x1800037dc  lea     r13, WPP_bc5dfa190b42335729027cd8699dae89_Traceguids
0x1800037e3  jmp     loc_18000356E
0x1800037e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037ef  cmp     rcx, r12
0x1800037f2  jz      short loc_18000380B
0x1800037f4  test    byte ptr [rcx+1Ch], 2
0x1800037f8  jz      short loc_18000380B
0x1800037fa  mov     rcx, [rcx+10h]
0x1800037fe  mov     edx, 0Fh
0x180003803  mov     r8, r13
0x180003806  call    WPP_SF_
0x18000380b  lea     r8, [rbp+lpFileName]
0x18000380f  mov     word ptr [rbx+14h], 16h
0x180003815  lea     rdx, [rbp+arg_10]
0x180003819  mov     rcx, rbx
0x18000381c  call    ParseSubCommand
0x180003821  test    eax, eax
0x180003823  jnz     loc_180003B74
0x180003829  xor     edx, edx
0x18000382b  mov     rcx, rbx
0x18000382e  call    ReplyToClient
0x180003833  test    eax, eax
0x180003835  jnz     loc_180003B53
0x18000383b  mov     r8, [rbp+lpFileName]
0x18000383f  mov     rcx, rbx
0x180003842  mov     edx, [rbp+arg_10]
0x180003845  call    GetControlFileFromClient
0x18000384a  test    eax, eax
0x18000384c  jnz     loc_180003B32
0x180003852  xor     edx, edx
0x180003854  mov     [rbp+lpFileName], rsi
0x180003858  mov     rcx, rbx
0x18000385b  mov     word ptr [rbx+14h], 17h
0x180003861  call    ReplyToClient
0x180003866  test    eax, eax
0x180003868  jz      loc_180003574
0x18000386e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003875  cmp     rcx, r12
0x180003878  jz      loc_180003C7E
0x18000387e  test    byte ptr [rcx+1Ch], 8
0x180003882  jz      loc_180003C7E
0x180003888  mov     edx, 13h
0x18000388d  jmp     loc_18000352E
0x180003892  mov     rcx, cs:WPP_GLOBAL_Control
0x180003899  lea     rbx, WPP_GLOBAL_Control
0x1800038a0  cmp     rcx, rbx
0x1800038a3  jz      loc_180003A04
0x1800038a9  test    byte ptr [rcx+1Ch], 8
0x1800038ad  jz      short loc_1800038CB
0x1800038af  mov     rcx, [rcx+10h]
0x1800038b3  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x1800038ba  mov     edx, 36h ; '6'
0x1800038bf  call    WPP_SF_
0x1800038c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038cb  cmp     rcx, rbx
0x1800038ce  jz      loc_180003A04
0x1800038d4  test    byte ptr [rcx+1Ch], 8
0x1800038d8  jz      loc_180003A04
0x1800038de  mov     edx, 1Ch
0x1800038e3  lea     r8, WPP_bc5dfa190b42335729027cd8699dae89_Traceguids
0x1800038ea  jmp     loc_1800039FB
0x1800038ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038f6  lea     rax, WPP_GLOBAL_Control
0x1800038fd  cmp     rcx, rax
0x180003900  jz      loc_180003A04
0x180003906  test    byte ptr [rcx+1Ch], 8
0x18000390a  jz      loc_180003A04
0x180003910  mov     edx, 1Bh
0x180003915  jmp     short loc_1800038E3
0x180003917  mov     rbx, cs:WPP_GLOBAL_Control
0x18000391e  lea     rax, WPP_GLOBAL_Control
0x180003925  cmp     rbx, rax
0x180003928  jz      loc_180003C7E
0x18000392e  test    byte ptr [rbx+1Ch], 8
0x180003932  jz      loc_180003C7E
0x180003938  mov     rbx, [rbx+10h]
0x18000393c  call    cs:__imp_GetLastError
0x180003942  mov     edx, 1Eh
0x180003947  lea     r8, WPP_bc5dfa190b42335729027cd8699dae89_Traceguids
0x18000394e  mov     r9d, eax
0x180003951  mov     rcx, rbx
0x180003954  call    WPP_SF_d
0x180003959  jmp     loc_180003C7E
0x18000395e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003965  lea     rax, WPP_GLOBAL_Control
0x18000396c  cmp     rcx, rax
0x18000396f  jz      loc_180003C7E
0x180003975  test    byte ptr [rcx+1Ch], 8
  ... truncated ...
```
