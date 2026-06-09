# CMsftWriteEngine2::FinalConstruct(void)

- ea: `0x180032af0`
- end: `0x180033417`
- name: `?FinalConstruct@CMsftWriteEngine2@@QEAAJXZ`
- size: `2343`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800327e8`

## callees

- `0x18000908c`
- `0x18000f740`
- `0x1800140f4`
- `0x180016778`
- `0x180028ad8`
- `0x180032af0`

## import_xrefs

- `USER32!MsgWaitForMultipleObjects` at `0x180032fac`
- `USER32!MsgWaitForMultipleObjects` at `0x180032fd6`
- `USER32!MsgWaitForMultipleObjects` at `0x18003315f`
- `USER32!MsgWaitForMultipleObjects` at `0x1800332d3`
- `USER32!MsgWaitForMultipleObjects` at `0x180032fac`
- `USER32!MsgWaitForMultipleObjects` at `0x180032fd6`
- `USER32!MsgWaitForMultipleObjects` at `0x18003315f`
- `USER32!MsgWaitForMultipleObjects` at `0x1800332d3`
- `KERNEL32!GetExitCodeThread` at `0x1800331a2`
- `KERNEL32!GetExitCodeThread` at `0x1800332e5`
- `KERNEL32!GetExitCodeThread` at `0x1800331a2`
- `KERNEL32!GetExitCodeThread` at `0x1800332e5`
- `KERNEL32!ResumeThread` at `0x180032ed1`
- `KERNEL32!ResumeThread` at `0x180032f3e`
- `KERNEL32!ResumeThread` at `0x180032ed1`
- `KERNEL32!ResumeThread` at `0x180032f3e`
- `KERNEL32!CreateThread` at `0x180032d9d`
- `KERNEL32!CreateThread` at `0x180032e1a`
- `KERNEL32!CreateThread` at `0x180032d9d`
- `KERNEL32!CreateThread` at `0x180032e1a`
- `KERNEL32!SetEvent` at `0x180033145`
- `KERNEL32!SetEvent` at `0x1800332b9`
- `KERNEL32!SetEvent` at `0x180033145`
- `KERNEL32!SetEvent` at `0x1800332b9`
- `KERNEL32!CreateEventW` at `0x180032b87`
- `KERNEL32!CreateEventW` at `0x180032bd9`
- `KERNEL32!CreateEventW` at `0x180032bee`
- `KERNEL32!CreateEventW` at `0x180032c06`
- `KERNEL32!CreateEventW` at `0x180032c2f`
- `KERNEL32!CreateEventW` at `0x180032c86`
- `KERNEL32!CreateEventW` at `0x180032b87`
- `KERNEL32!CreateEventW` at `0x180032bd9`
- `KERNEL32!CreateEventW` at `0x180032bee`
- `KERNEL32!CreateEventW` at `0x180032c06`
- `KERNEL32!CreateEventW` at `0x180032c2f`
- `KERNEL32!CreateEventW` at `0x180032c86`

## pseudocode

```c
__int64 __fastcall CMsftWriteEngine2::FinalConstruct(HANDLE *this)
{
  void **v2; // rdx
  HANDLE v3; // rsi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  HANDLE v6; // r13
  HANDLE v7; // rax
  HANDLE v8; // r12
  void *v9; // r14
  signed int LastErrorAsHresultForceFailure; // ebx
  void *v11; // r15
  void **v12; // rdx
  void **v13; // rdx
  void **v14; // rdx
  void **v15; // rdx
  void **v16; // rdx
  void **v17; // rdx
  void **v18; // rdx
  int v20; // edx
  Imapi2Utility *v21; // rcx
  int v22; // edx
  HANDLE v23; // rcx
  int v24; // edx
  Imapi2Utility *v25; // rcx
  unsigned int v26; // eax
  int v27; // edx
  Imapi2Utility *v28; // rcx
  unsigned int v29; // eax
  DWORD v30; // eax
  int v31; // r14d
  DWORD v32; // esi
  PVOID *v33; // rcx
  Imapi2Utility *v34; // rcx
  unsigned int v35; // eax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  Imapi2Utility *v42; // rcx
  HANDLE v43; // [rsp+30h] [rbp-39h] BYREF
  HANDLE hThread; // [rsp+38h] [rbp-31h] BYREF
  HANDLE v45; // [rsp+40h] [rbp-29h] BYREF
  HANDLE v46; // [rsp+48h] [rbp-21h] BYREF
  HANDLE v47; // [rsp+50h] [rbp-19h] BYREF
  HANDLE v48; // [rsp+58h] [rbp-11h] BYREF
  HANDLE v49; // [rsp+60h] [rbp-9h] BYREF
  HANDLE EventW; // [rsp+68h] [rbp-1h] BYREF
  HANDLE pHandles[2]; // [rsp+70h] [rbp+7h] BYREF
  HANDLE v52[8]; // [rsp+80h] [rbp+17h] BYREF
  DWORD ExitCode; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD ThreadId; // [rsp+E0h] [rbp+77h] BYREF
  DWORD lpThreadId; // [rsp+E8h] [rbp+7Fh] BYREF

  v45 = 0;
  v49 = 0;
  v48 = 0;
  v46 = 0;
  v43 = 0;
  ThreadId = 0;
  v47 = 0;
  hThread = 0;
  lpThreadId = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 52, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, this);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = EventW;
  if ( EventW )
  {
    v45 = CreateEventW(0, 1, 0, 0);
    v49 = CreateEventW(0, 1, 0, 0);
    v6 = v49;
    v7 = CreateEventW(0, 1, 0, 0);
    v48 = v7;
    v8 = v7;
    if ( !v49 || !v7 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
      {
        goto LABEL_18;
      }
      v5 = 54;
      goto LABEL_17;
    }
    v46 = CreateEventW(0, 0, 0, 0);
    v9 = v46;
    if ( !v46 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
      {
        goto LABEL_18;
      }
      v5 = 55;
      goto LABEL_17;
    }
    v47 = CreateEventW(0, 0, 0, 0);
    v11 = v47;
    if ( !v47 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 56, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
      }
      LastErrorAsHresultForceFailure = -2147024882;
      goto LABEL_25;
    }
    LastErrorAsHresultForceFailure = 0;
    v43 = CreateThread(0, 0, KickOffWriteEngineReadThread, this, 4u, &ThreadId);
    if ( !v43 )
    {
      LastErrorAsHresultForceFailure = Imapi2Utility::GetLastErrorAsHresultForceFailure(v21, v20);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          57,
          WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids,
          (unsigned int)LastErrorAsHresultForceFailure);
      }
      if ( LastErrorAsHresultForceFailure < 0 )
        goto LABEL_25;
    }
    hThread = CreateThread(0, 0, KickOffWriteEngineWriteThread, this, 4u, &lpThreadId);
    v23 = hThread;
    if ( !hThread )
    {
      LastErrorAsHresultForceFailure = Imapi2Utility::GetLastErrorAsHresultForceFailure(0, v22);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          58,
          WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids,
          (unsigned int)LastErrorAsHresultForceFailure);
      }
      if ( LastErrorAsHresultForceFailure < 0 )
        goto LABEL_25;
      v23 = hThread;
    }
    this[22] = v45;
    this[25] = v43;
    *((_DWORD *)this + 54) = ThreadId;
    *((_DWORD *)this + 60) = lpThreadId;
    this[21] = v6;
    this[23] = v8;
    this[24] = v3;
    this[26] = v9;
    this[29] = v11;
    this[28] = v23;
    if ( ResumeThread(v23) == -1 )
    {
      v26 = Imapi2Utility::GetLastErrorAsHresultForceFailure(v25, v24);
      LastErrorAsHresultForceFailure = v26;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 59, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, v26);
      }
    }
    if ( ResumeThread(v43) == -1 )
    {
      v29 = Imapi2Utility::GetLastErrorAsHresultForceFailure(v28, v27);
      LastErrorAsHresultForceFailure = v29;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 60, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, v29);
      }
    }
    pHandles[0] = v9;
    pHandles[1] = v43;
    v30 = MsgWaitForMultipleObjects(2u, pHandles, 0, 0xFFFFFFFF, 0);
    v52[0] = v11;
    v52[1] = hThread;
    v31 = v30;
    v32 = MsgWaitForMultipleObjects(2u, v52, 0, 0xFFFFFFFF, 0);
    if ( v31 == 128 )
    {
      v33 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 61, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      v31 = 0;
    }
    else if ( v31 == 129 )
    {
      v33 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 62, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      v31 = 1;
    }
    else
    {
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v32 == 128 )
    {
      if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 228) & 4) != 0 && *((_BYTE *)v33 + 225) >= 2u )
      {
        WPP_SF_(v33[27], 63, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      v32 = 0;
    }
    else if ( v32 == 129 )
    {
      if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 228) & 4) != 0 && *((_BYTE *)v33 + 225) >= 2u )
      {
        WPP_SF_(v33[27], 64, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      v32 = 1;
    }
    if ( v31 == 1 )
    {
      if ( v32 == 1 )
      {
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 228) & 4) != 0 && *((_BYTE *)v33 + 225) >= 2u )
          WPP_SF_(v33[27], 66, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
      }
      else
      {
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 228) & 4) != 0 && *((_BYTE *)v33 + 225) >= 2u )
          WPP_SF_(v33[27], 65, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
        SetEvent(this[24]);
        MsgWaitForMultipleObjects(1u, &hThread, 0, 0xFFFFFFFF, 0);
      }
      ExitCode = 0;
      if ( !GetExitCodeThread(v43, &ExitCode) )
      {
        v35 = Imapi2Utility::GetLastErrorAsHresultForceFailure(v34, (int)v2);
        LastErrorAsHresultForceFailure = v35;
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
        {
          v37 = 67;
LABEL_91:
          WPP_SF_d(v36[27], v37, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, v35);
          goto LABEL_127;
        }
        goto LABEL_127;
      }
      LastErrorAsHresultForceFailure = ExitCode;
      if ( ExitCode == 259 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 225) )
        {
          goto LABEL_98;
        }
        v39 = 68;
LABEL_97:
        WPP_SF_(v38[27], v39, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
LABEL_98:
        LastErrorAsHresultForceFailure = -2147467259;
        goto LABEL_127;
      }
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 2u )
      {
        goto LABEL_127;
      }
      v41 = 69;
    }
    else
    {
      if ( v32 != 1 )
      {
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 228) & 4) != 0 && *((_BYTE *)v33 + 225) >= 4u )
          WPP_SF_(v33[27], 74, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
        goto LABEL_127;
      }
      if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 228) & 4) != 0 && *((_BYTE *)v33 + 225) >= 2u )
        WPP_SF_(v33[27], 70, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
      SetEvent(this[24]);
      MsgWaitForMultipleObjects(1u, &v43, 0, 0xFFFFFFFF, 0);
      ExitCode = 0;
      if ( !GetExitCodeThread(hThread, &ExitCode) )
      {
        v35 = Imapi2Utility::GetLastErrorAsHresultForceFailure(v42, (int)v2);
        LastErrorAsHresultForceFailure = v35;
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
        {
          v37 = 71;
          goto LABEL_91;
        }
LABEL_127:
        if ( LastErrorAsHresultForceFailure >= 0 )
          return (unsigned int)LastErrorAsHresultForceFailure;
        goto LABEL_25;
      }
      LastErrorAsHresultForceFailure = ExitCode;
      if ( ExitCode == 259 )
      {
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 225) )
        {
          goto LABEL_98;
        }
        v39 = 72;
        goto LABEL_97;
      }
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 2u )
      {
        goto LABEL_127;
      }
      v41 = 73;
    }
    WPP_SF_d(
      v40[27],
      v41,
      WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids,
      (unsigned int)LastErrorAsHresultForceFailure);
    LastErrorAsHresultForceFailure = ExitCode;
    goto LABEL_127;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
  {
    goto LABEL_18;
  }
  v5 = 53;
LABEL_17:
  WPP_SF_(v4[27], v5, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
LABEL_18:
  LastErrorAsHresultForceFailure = -2147024882;
LABEL_25:
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v46, v2);
  this[26] = 0;
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v43, v12);
  this[25] = 0;
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v47, v13);
  this[29] = 0;
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&hThread, v14);
  this[28] = 0;
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v48, v15);
  this[23] = 0;
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v45, v16);
  this[22] = 0;
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v49, v17);
  this[21] = 0;
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&EventW, v18);
  this[24] = 0;
  *((_DWORD *)this + 54) = 0;
  return (unsigned int)LastErrorAsHresultForceFailure;
}

```

## disassembly

```asm
0x180032af0  mov     [rsp-8+arg_0], rbx
0x180032af5  push    rbp
0x180032af6  push    rsi
0x180032af7  push    rdi
0x180032af8  push    r12
0x180032afa  push    r13
0x180032afc  push    r14
0x180032afe  push    r15
0x180032b00  lea     rbp, [rsp-27h]
0x180032b05  sub     rsp, 90h
0x180032b0c  xor     r15d, r15d
0x180032b0f  mov     rdi, rcx
0x180032b12  mov     [rbp+57h+var_80], r15
0x180032b16  mov     [rbp+57h+var_60], r15
0x180032b1a  mov     [rbp+57h+var_68], r15
0x180032b1e  mov     [rbp+57h+var_78], r15
0x180032b22  mov     [rbp+57h+var_90], r15
0x180032b26  mov     [rbp+57h+ThreadId], r15d
0x180032b2a  mov     [rbp+57h+var_70], r15
0x180032b2e  mov     [rbp+57h+hThread], r15
0x180032b32  mov     [rbp+57h+arg_18], r15d
0x180032b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b3d  lea     rbx, WPP_GLOBAL_Control
0x180032b44  lea     r14, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180032b4b  lea     r12d, [r15+1]
0x180032b4f  cmp     rcx, rbx
0x180032b52  jz      short loc_180032B7C
0x180032b54  test    [rcx+0E4h], r12b
0x180032b5b  jz      short loc_180032B7C
0x180032b5d  cmp     byte ptr [rcx+0E1h], 4
0x180032b64  jb      short loc_180032B7C
0x180032b66  mov     rcx, [rcx+0D8h]
0x180032b6d  lea     edx, [r15+34h]
0x180032b71  mov     r9, rdi
0x180032b74  mov     r8, r14
0x180032b77  call    WPP_SF_q
0x180032b7c  xor     r9d, r9d; lpName
0x180032b7f  xor     r8d, r8d; bInitialState
0x180032b82  mov     edx, r12d; bManualReset
0x180032b85  xor     ecx, ecx; lpEventAttributes
0x180032b87  call    cs:__imp_CreateEventW
0x180032b8d  mov     [rbp+57h+var_58], rax
0x180032b91  mov     rsi, rax
0x180032b94  test    rax, rax
0x180032b97  jnz     short loc_180032BCE
0x180032b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ba0  cmp     rcx, rbx
0x180032ba3  jz      loc_180032C75
0x180032ba9  test    byte ptr [rcx+0E4h], 4
0x180032bb0  jz      loc_180032C75
0x180032bb6  cmp     byte ptr [rcx+0E1h], 3
0x180032bbd  jb      loc_180032C75
0x180032bc3  lea     edx, [rax+35h]
0x180032bc6  mov     r8, r14
0x180032bc9  jmp     loc_180032C69
0x180032bce  xor     r9d, r9d; lpName
0x180032bd1  xor     r8d, r8d; bInitialState
0x180032bd4  mov     edx, r12d; bManualReset
0x180032bd7  xor     ecx, ecx; lpEventAttributes
0x180032bd9  call    cs:__imp_CreateEventW
0x180032bdf  xor     r9d, r9d; lpName
0x180032be2  xor     r8d, r8d; bInitialState
0x180032be5  mov     edx, r12d; bManualReset
0x180032be8  mov     [rbp+57h+var_80], rax
0x180032bec  xor     ecx, ecx; lpEventAttributes
0x180032bee  call    cs:__imp_CreateEventW
0x180032bf4  xor     r9d, r9d; lpName
0x180032bf7  xor     r8d, r8d; bInitialState
0x180032bfa  mov     edx, r12d; bManualReset
0x180032bfd  mov     [rbp+57h+var_60], rax
0x180032c01  xor     ecx, ecx; lpEventAttributes
0x180032c03  mov     r13, rax
0x180032c06  call    cs:__imp_CreateEventW
0x180032c0c  mov     [rbp+57h+var_68], rax
0x180032c10  mov     r12, rax
0x180032c13  test    r13, r13
0x180032c16  jz      loc_1800333E3
0x180032c1c  test    rax, rax
0x180032c1f  jz      loc_1800333E3
0x180032c25  xor     r9d, r9d; lpName
0x180032c28  xor     r8d, r8d; bInitialState
0x180032c2b  xor     edx, edx; bManualReset
0x180032c2d  xor     ecx, ecx; lpEventAttributes
0x180032c2f  call    cs:__imp_CreateEventW
0x180032c35  mov     [rbp+57h+var_78], rax
0x180032c39  mov     r14, rax
0x180032c3c  test    rax, rax
0x180032c3f  jnz     short loc_180032C7C
0x180032c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c48  cmp     rcx, rbx
0x180032c4b  jz      short loc_180032C75
0x180032c4d  test    byte ptr [rcx+0E4h], 4
0x180032c54  jz      short loc_180032C75
0x180032c56  cmp     byte ptr [rcx+0E1h], 3
0x180032c5d  jb      short loc_180032C75
0x180032c5f  lea     edx, [rax+37h]
0x180032c62  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180032c69  mov     rcx, [rcx+0D8h]
0x180032c70  call    WPP_SF_
0x180032c75  mov     ebx, 8007000Eh
0x180032c7a  jmp     short loc_180032CD8
0x180032c7c  xor     r9d, r9d; lpName
0x180032c7f  xor     r8d, r8d; bInitialState
0x180032c82  xor     edx, edx; bManualReset
0x180032c84  xor     ecx, ecx; lpEventAttributes
0x180032c86  call    cs:__imp_CreateEventW
0x180032c8c  mov     [rbp+57h+var_70], rax
0x180032c90  mov     r15, rax
0x180032c93  test    rax, rax
0x180032c96  jnz     loc_180032D7C
0x180032c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ca3  cmp     rcx, rbx
0x180032ca6  jz      short loc_180032CD0
0x180032ca8  test    byte ptr [rcx+0E4h], 4
0x180032caf  jz      short loc_180032CD0
0x180032cb1  cmp     byte ptr [rcx+0E1h], 3
0x180032cb8  jb      short loc_180032CD0
0x180032cba  mov     rcx, [rcx+0D8h]
0x180032cc1  lea     edx, [rax+38h]
0x180032cc4  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180032ccb  call    WPP_SF_
0x180032cd0  mov     ebx, 8007000Eh
0x180032cd5  xor     r15d, r15d
0x180032cd8  lea     rcx, [rbp+57h+var_78]; this
0x180032cdc  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180032ce1  lea     rcx, [rbp+57h+var_90]; this
0x180032ce5  mov     [rdi+0D0h], r15
0x180032cec  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180032cf1  lea     rcx, [rbp+57h+var_70]; this
0x180032cf5  mov     [rdi+0C8h], r15
0x180032cfc  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180032d01  lea     rcx, [rbp+57h+hThread]; this
0x180032d05  mov     [rdi+0E8h], r15
0x180032d0c  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180032d11  lea     rcx, [rbp+57h+var_68]; this
0x180032d15  mov     [rdi+0E0h], r15
0x180032d1c  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180032d21  lea     rcx, [rbp+57h+var_80]; this
0x180032d25  mov     [rdi+0B8h], r15
0x180032d2c  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180032d31  lea     rcx, [rbp+57h+var_60]; this
0x180032d35  mov     [rdi+0B0h], r15
0x180032d3c  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180032d41  lea     rcx, [rbp+57h+var_58]; this
0x180032d45  mov     [rdi+0A8h], r15
0x180032d4c  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180032d51  mov     [rdi+0C0h], r15
0x180032d58  mov     [rdi+0D8h], r15d
0x180032d5f  mov     eax, ebx
0x180032d61  mov     rbx, [rsp+0C0h+arg_0]
0x180032d69  add     rsp, 90h
0x180032d70  pop     r15
0x180032d72  pop     r14
0x180032d74  pop     r13
0x180032d76  pop     r12
0x180032d78  pop     rdi
0x180032d79  pop     rsi
0x180032d7a  pop     rbp
0x180032d7b  retn
0x180032d7c  lea     rax, [rbp+57h+ThreadId]
0x180032d80  mov     r9, rdi; lpParameter
0x180032d83  mov     [rsp+0C0h+lpThreadId], rax; lpThreadId
0x180032d88  lea     r8, ?KickOffWriteEngineReadThread@@YAKPEAX@Z; lpStartAddress
0x180032d8f  xor     edx, edx; dwStackSize
0x180032d91  mov     [rsp+0C0h+dwCreationFlags], 4; dwCreationFlags
0x180032d99  xor     ecx, ecx; lpThreadAttributes
0x180032d9b  xor     ebx, ebx
0x180032d9d  call    cs:__imp_CreateThread
0x180032da3  mov     [rbp+57h+var_90], rax
0x180032da7  test    rax, rax
0x180032daa  jnz     short loc_180032DFB
0x180032dac  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x180032db1  mov     ebx, eax
0x180032db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180032dba  lea     rax, WPP_GLOBAL_Control
0x180032dc1  cmp     rcx, rax
0x180032dc4  jz      short loc_180032DF3
0x180032dc6  test    byte ptr [rcx+0E4h], 4
0x180032dcd  jz      short loc_180032DF3
0x180032dcf  cmp     byte ptr [rcx+0E1h], 3
0x180032dd6  jb      short loc_180032DF3
0x180032dd8  mov     rcx, [rcx+0D8h]
0x180032ddf  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180032de6  mov     edx, 39h ; '9'
0x180032deb  mov     r9d, ebx
0x180032dee  call    WPP_SF_d
0x180032df3  test    ebx, ebx
0x180032df5  js      loc_180032CD5
0x180032dfb  lea     rax, [rbp+57h+arg_18]
0x180032dff  mov     r9, rdi; lpParameter
0x180032e02  mov     [rsp+0C0h+lpThreadId], rax; lpThreadId
0x180032e07  lea     r8, ?KickOffWriteEngineWriteThread@@YAKPEAX@Z; lpStartAddress
0x180032e0e  xor     edx, edx; dwStackSize
0x180032e10  mov     [rsp+0C0h+dwCreationFlags], 4; dwCreationFlags
0x180032e18  xor     ecx, ecx; lpThreadAttributes
0x180032e1a  call    cs:__imp_CreateThread
0x180032e20  mov     [rbp+57h+hThread], rax
0x180032e24  mov     rcx, rax; this
0x180032e27  test    rax, rax
0x180032e2a  jnz     short loc_180032E7F
0x180032e2c  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x180032e31  mov     ebx, eax
0x180032e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e3a  lea     rax, WPP_GLOBAL_Control
0x180032e41  cmp     rcx, rax
0x180032e44  jz      short loc_180032E73
0x180032e46  test    byte ptr [rcx+0E4h], 4
0x180032e4d  jz      short loc_180032E73
0x180032e4f  cmp     byte ptr [rcx+0E1h], 3
0x180032e56  jb      short loc_180032E73
0x180032e58  mov     rcx, [rcx+0D8h]
0x180032e5f  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180032e66  mov     edx, 3Ah ; ':'
0x180032e6b  mov     r9d, ebx
0x180032e6e  call    WPP_SF_d
0x180032e73  test    ebx, ebx
0x180032e75  js      loc_180032CD5
0x180032e7b  mov     rcx, [rbp+57h+hThread]; hThread
0x180032e7f  mov     rax, [rbp+57h+var_80]
0x180032e83  mov     [rdi+0B0h], rax
0x180032e8a  mov     rax, [rbp+57h+var_90]
0x180032e8e  mov     [rdi+0C8h], rax
0x180032e95  mov     eax, [rbp+57h+ThreadId]
0x180032e98  mov     [rdi+0D8h], eax
0x180032e9e  mov     eax, [rbp+57h+arg_18]
0x180032ea1  mov     [rdi+0F0h], eax
0x180032ea7  mov     [rdi+0A8h], r13
0x180032eae  mov     [rdi+0B8h], r12
0x180032eb5  mov     [rdi+0C0h], rsi
0x180032ebc  mov     [rdi+0D0h], r14
0x180032ec3  mov     [rdi+0E8h], r15
0x180032eca  mov     [rdi+0E0h], rcx
0x180032ed1  call    cs:__imp_ResumeThread
0x180032ed7  or      esi, 0FFFFFFFFh
0x180032eda  cmp     eax, esi
0x180032edc  jnz     short loc_180032F2D
0x180032ede  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x180032ee3  mov     ebx, eax
0x180032ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180032eec  lea     r13, WPP_GLOBAL_Control
0x180032ef3  mov     r12d, 4
0x180032ef9  cmp     rcx, r13
0x180032efc  jz      short loc_180032F3A
0x180032efe  test    [rcx+0E4h], r12b
0x180032f05  jz      short loc_180032F3A
0x180032f07  cmp     byte ptr [rcx+0E1h], 3
0x180032f0e  jb      short loc_180032F3A
0x180032f10  mov     rcx, [rcx+0D8h]
0x180032f17  lea     edx, [r12+37h]
0x180032f1c  mov     r9d, eax
0x180032f1f  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180032f26  call    WPP_SF_d
0x180032f2b  jmp     short loc_180032F3A
0x180032f2d  mov     r12d, 4
0x180032f33  lea     r13, WPP_GLOBAL_Control
0x180032f3a  mov     rcx, [rbp+57h+var_90]; hThread
0x180032f3e  call    cs:__imp_ResumeThread
0x180032f44  cmp     eax, esi
0x180032f46  jnz     short loc_180032F88
0x180032f48  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x180032f4d  mov     ebx, eax
0x180032f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f56  cmp     rcx, r13
0x180032f59  jz      short loc_180032F88
0x180032f5b  test    [rcx+0E4h], r12b
0x180032f62  jz      short loc_180032F88
0x180032f64  cmp     byte ptr [rcx+0E1h], 3
0x180032f6b  jb      short loc_180032F88
0x180032f6d  mov     rcx, [rcx+0D8h]
0x180032f74  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180032f7b  mov     edx, 3Ch ; '<'
0x180032f80  mov     r9d, eax
0x180032f83  call    WPP_SF_d
0x180032f88  mov     rax, [rbp+57h+var_90]
0x180032f8c  lea     rdx, [rbp+57h+pHandles]; pHandles
0x180032f90  xor     r8d, r8d; fWaitAll
0x180032f93  mov     [rbp+57h+pHandles], r14
0x180032f97  mov     r9d, esi; dwMilliseconds
0x180032f9a  mov     [rbp+57h+var_48], rax
0x180032f9e  mov     [rsp+0C0h+dwCreationFlags], 0; dwWakeMask
0x180032fa6  lea     esi, [r8+2]
0x180032faa  mov     ecx, esi; nCount
0x180032fac  call    cs:__imp_MsgWaitForMultipleObjects
0x180032fb2  mov     rcx, [rbp+57h+hThread]
0x180032fb6  lea     rdx, [rbp+57h+var_40]; pHandles
0x180032fba  mov     [rbp+57h+var_40], r15
0x180032fbe  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180032fc2  mov     [rbp+57h+var_38], rcx
0x180032fc6  xor     r15d, r15d
0x180032fc9  mov     ecx, esi; nCount
0x180032fcb  mov     [rsp+0C0h+dwCreationFlags], r15d; dwWakeMask
0x180032fd0  xor     r8d, r8d; fWaitAll
0x180032fd3  mov     r14d, eax
0x180032fd6  call    cs:__imp_MsgWaitForMultipleObjects
0x180032fdc  mov     esi, eax
0x180032fde  cmp     r14d, 80h
0x180032fe5  jz      short loc_18003303D
0x180032fe7  cmp     r14d, 81h
0x180032fee  jnz     short loc_180033034
0x180032ff0  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
