# BthServOpenLocalRadio(ushort const *)

- ea: `0x18000db08`
- end: `0x18000dfc5`
- name: `?BthServOpenLocalRadio@@YAHPEBG@Z`
- size: `1213`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000d498`
- `0x18000d958`

## callees

- `0x18000b498`
- `0x18000ba9c`
- `0x18000cf18`
- `0x18000db08`
- `0x18000ebac`
- `0x18000fb54`
- `0x180010128`
- `0x180011cfc`
- `0x180012004`
- `0x1800120b8`
- `0x180012384`
- `0x18001245c`
- `0x18001417c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dd27`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dd27`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ddd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ddd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dc16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dc16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dec9`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000dc93`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000dc93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dbfd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dbfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BthServOpenLocalRadio(LPCWSTR lpFileName)
{
  unsigned int v2; // ebp
  char v3; // di
  _BYTE *v4; // rcx
  bool v5; // dl
  _UNKNOWN **v6; // rax
  bool v7; // dl
  HANDLE FileW; // rbx
  int v9; // r8d
  void **v10; // r14
  bool v11; // bl
  bool v12; // si
  __int64 *v13; // rdx
  int v14; // r8d
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rax
  char v18; // dl
  unsigned __int64 v19; // rcx
  bool v20; // bl
  bool v21; // si
  int v22; // edx
  int v23; // r8d
  _BYTE *v24; // rcx
  bool v25; // bl
  bool v26; // si
  int v27; // r8d
  int v28; // edx
  int v29; // edx
  volatile signed __int32 *v30; // rbx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-68h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-60h]
  void **v34; // [rsp+50h] [rbp-38h] BYREF
  volatile signed __int32 *v35; // [rsp+58h] [rbp-30h]
  int v36; // [rsp+98h] [rbp+10h] BYREF
  RTL_SRWLOCK *v37; // [rsp+A0h] [rbp+18h]

  v2 = 0;
  v3 = 1;
  v4 = WPP_GLOBAL_Control;
  v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v6 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v4 = WPP_GLOBAL_Control;
    v6 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v7 = v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 5u;
  if ( v7 || v6 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sS(
      *((_QWORD *)v4 + 2),
      v7,
      v6 != &WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v4 + 5),
      dwCreationDisposition,
      dwFlagsAndAttributes,
      85,
      (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  AcquireSRWLockExclusive(&stru_180047010);
  v37 = &stru_180047010;
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
    qword_180047018,
    FileW);
  ReleaseSRWLockExclusive(&stru_180047010);
  BthServGlobals::GetSafeRadioHandle(&Globals, &v34);
  v10 = v34;
  if ( v34 && (char *)*v34 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( pv )
    {
      if ( !TrySubmitThreadpoolCallback(BthServUnregisterDeviceNotificationCallback, pv, 0) )
      {
        v11 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          GetLastError();
          v13 = WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids;
          LOBYTE(v14) = v12;
          LOBYTE(v13) = v11;
          WPP_RECORDER_AND_TRACE_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v13,
            v14,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        }
      }
      pv = 0;
    }
    v36 = 1;
    if ( !WaitForSingleObject(hMutex, 0xFFFFFFFF) )
    {
      v15 = (unsigned __int64)qword_180047088;
      if ( qword_180047088 )
      {
        while ( 1 )
        {
LABEL_47:
          if ( (int)BthAuthClientWalkFxn(v15, &v36) < 0 )
            goto LABEL_48;
          v16 = *(_QWORD *)v15;
          if ( !*(_QWORD *)v15 )
          {
            v16 = *(_QWORD *)(v15 + 8);
            if ( !v16 )
              break;
          }
          if ( (qword_180047090 & 1) != 0 )
            v15 ^= v16;
          else
            v15 = v16;
        }
        v17 = v15;
        v18 = qword_180047090 & 1;
        while ( 1 )
        {
          v17 = *(_QWORD *)(v17 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v18 )
          {
            if ( !v17 )
              break;
            v17 ^= v15;
          }
          if ( !v17 )
            break;
          v19 = *(_QWORD *)(v17 + 8);
          if ( v18 )
          {
            if ( !v19 )
              goto LABEL_44;
            v19 ^= v17;
          }
          if ( v19 && v19 != v15 )
          {
            v15 = v19;
            goto LABEL_47;
          }
LABEL_44:
          v15 = v17;
        }
      }
LABEL_48:
      ReleaseMutex(hMutex);
    }
    pv = BthServRegisterHandleNotifications(*v10);
    if ( pv )
    {
      v2 = BthServListenForAsyncEvents(hObject == 0);
    }
    else
    {
      v20 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        GetLastError();
        v22 = (int)WPP_GLOBAL_Control;
        LOBYTE(v23) = v21;
        LOBYTE(v22) = v20;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v23, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      BthServGlobals::CloseRadioHandle((BthServGlobals *)&Globals);
      wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
        &v34,
        -1);
    }
    BthServBluetoothControlPanelTasksSetState(1);
    BthServStartLEPrepairing();
    goto LABEL_67;
  }
  v24 = WPP_GLOBAL_Control;
  v25 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    GetLastError();
    LOBYTE(v27) = v26;
    LOBYTE(v28) = v25;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v27, *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_67:
    v24 = WPP_GLOBAL_Control;
  }
  v29 = (int)v35;
  if ( v35 )
  {
    if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
    {
      v30 = v35;
      (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
      if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
    }
    v24 = WPP_GLOBAL_Control;
  }
  if ( v24 == (_BYTE *)&WPP_GLOBAL_Control || v24[25] < 5u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v29) = v3;
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v24 + 2), v29, v9, *((_QWORD *)v24 + 5));
  }
  return v2;
}

```

## disassembly

```asm
0x18000db08  mov     [rsp+arg_0], rbx
0x18000db0d  mov     [rsp+arg_18], rbp
0x18000db12  push    rsi
0x18000db13  push    rdi
0x18000db14  push    r12
0x18000db16  push    r13
0x18000db18  push    r14
0x18000db1a  sub     rsp, 60h
0x18000db1e  mov     rbx, rcx
0x18000db21  xor     ebp, ebp
0x18000db23  lea     r12, WPP_GLOBAL_Control
0x18000db2a  lea     edi, [rbp+1]
0x18000db2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db34  cmp     rcx, r12
0x18000db37  jz      short loc_18000DB44
0x18000db39  cmp     byte ptr [rcx+19h], 5
0x18000db3d  jb      short loc_18000DB44
0x18000db3f  mov     dl, dil
0x18000db42  jmp     short loc_18000DB46
0x18000db44  xor     dl, dl
0x18000db46  lea     r13, WPP_RECORDER_INITIALIZED
0x18000db4d  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000db54  cmp     rax, r13
0x18000db57  setnz   r8b
0x18000db5b  lea     r9, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000db62  test    dl, dl
0x18000db64  jnz     short loc_18000DB6B
0x18000db66  test    r8b, r8b
0x18000db69  jz      short loc_18000DB99
0x18000db6b  mov     [rsp+88h+var_50], r9
0x18000db70  mov     word ptr [rsp+88h+hTemplateFile], 54h ; 'T'
0x18000db77  mov     r9, [rcx+28h]
0x18000db7b  mov     rcx, [rcx+10h]
0x18000db7f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000db84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db8b  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000db92  lea     r9, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000db99  cmp     rcx, r12
0x18000db9c  jz      short loc_18000DBA9
0x18000db9e  cmp     byte ptr [rcx+19h], 5
0x18000dba2  jb      short loc_18000DBA9
0x18000dba4  mov     dl, dil
0x18000dba7  jmp     short loc_18000DBAB
0x18000dba9  xor     dl, dl
0x18000dbab  cmp     rax, r13
0x18000dbae  setnz   r8b
0x18000dbb2  test    dl, dl
0x18000dbb4  jnz     short loc_18000DBBB
0x18000dbb6  test    r8b, r8b
0x18000dbb9  jz      short loc_18000DBD9
0x18000dbbb  mov     [rsp+88h+var_40], rbx
0x18000dbc0  mov     [rsp+88h+var_50], r9
0x18000dbc5  mov     word ptr [rsp+88h+hTemplateFile], 55h ; 'U'; hTemplateFile
0x18000dbcc  mov     r9, [rcx+28h]
0x18000dbd0  mov     rcx, [rcx+10h]
0x18000dbd4  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18000dbd9  and     [rsp+88h+hTemplateFile], rbp
0x18000dbde  mov     [rsp+88h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18000dbe6  mov     eax, 3
0x18000dbeb  mov     [rsp+88h+dwCreationDisposition], eax; dwCreationDisposition
0x18000dbef  xor     r9d, r9d; lpSecurityAttributes
0x18000dbf2  mov     r8d, eax; dwShareMode
0x18000dbf5  mov     edx, 0C0000000h; dwDesiredAccess
0x18000dbfa  mov     rcx, rbx; lpFileName
0x18000dbfd  call    cs:__imp_CreateFileW
0x18000dc04  nop     dword ptr [rax+rax+00h]
0x18000dc09  mov     rbx, rax
0x18000dc0c  lea     rsi, stru_180047010
0x18000dc13  mov     rcx, rsi; SRWLock
0x18000dc16  call    cs:__imp_AcquireSRWLockExclusive
0x18000dc1d  nop     dword ptr [rax+rax+00h]
0x18000dc22  mov     [rsp+88h+arg_10], rsi
0x18000dc2a  mov     rdx, rbx
0x18000dc2d  lea     rcx, qword_180047018
0x18000dc34  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18000dc39  nop
0x18000dc3a  mov     rcx, rsi; SRWLock
0x18000dc3d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dc44  nop     dword ptr [rax+rax+00h]
0x18000dc49  lea     rdx, [rsp+88h+var_38]
0x18000dc4e  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18000dc55  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18000dc5a  nop
0x18000dc5b  mov     r14, [rsp+88h+var_38]
0x18000dc60  test    r14, r14
0x18000dc63  jz      loc_18000DE9C
0x18000dc69  mov     rax, [r14]
0x18000dc6c  dec     rax
0x18000dc6f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dc73  ja      loc_18000DE9C
0x18000dc79  mov     rdx, qword ptr cs:pv; pv
0x18000dc80  test    rdx, rdx
0x18000dc83  jz      loc_18000DD16
0x18000dc89  xor     r8d, r8d; pcbe
0x18000dc8c  lea     rcx, ?BthServUnregisterDeviceNotificationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000dc93  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000dc9a  nop     dword ptr [rax+rax+00h]
0x18000dc9f  test    eax, eax
0x18000dca1  jnz     short loc_18000DD0E
0x18000dca3  mov     rax, cs:WPP_GLOBAL_Control
0x18000dcaa  cmp     rax, r12
0x18000dcad  jz      short loc_18000DCBA
0x18000dcaf  cmp     byte ptr [rax+19h], 3
0x18000dcb3  jb      short loc_18000DCBA
0x18000dcb5  mov     bl, dil
0x18000dcb8  jmp     short loc_18000DCBC
0x18000dcba  xor     bl, bl
0x18000dcbc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000dcc3  setnz   sil
0x18000dcc7  test    bl, bl
0x18000dcc9  jnz     short loc_18000DCD0
0x18000dccb  test    sil, sil
0x18000dcce  jz      short loc_18000DD0E
0x18000dcd0  call    cs:__imp_GetLastError
0x18000dcd7  nop     dword ptr [rax+rax+00h]
0x18000dcdc  mov     edx, eax
0x18000dcde  mov     rax, cs:WPP_GLOBAL_Control
0x18000dce5  mov     dword ptr [rsp+88h+var_40], edx
0x18000dce9  lea     rdx, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000dcf0  mov     [rsp+88h+var_50], rdx
0x18000dcf5  mov     word ptr [rsp+88h+hTemplateFile], 56h ; 'V'
0x18000dcfc  mov     r9, [rax+28h]
0x18000dd00  mov     r8b, sil
0x18000dd03  mov     dl, bl
0x18000dd05  mov     rcx, [rax+10h]
0x18000dd09  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000dd0e  and     qword ptr cs:pv, 0
0x18000dd16  mov     [rsp+88h+arg_8], edi
0x18000dd1d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000dd20  mov     rcx, cs:hMutex; hHandle
0x18000dd27  call    cs:__imp_WaitForSingleObject
0x18000dd2e  nop     dword ptr [rax+rax+00h]
0x18000dd33  test    eax, eax
0x18000dd35  jnz     loc_18000DDDF
0x18000dd3b  mov     rbx, cs:qword_180047088
0x18000dd42  test    rbx, rbx
0x18000dd45  jz      loc_18000DDCC
0x18000dd4b  jmp     short loc_18000DDB8
0x18000dd4d  mov     rax, [rbx]
0x18000dd50  test    rax, rax
0x18000dd53  jz      short loc_18000DD63
0x18000dd55  test    byte ptr cs:qword_180047090, dil
0x18000dd5c  jz      short loc_18000DDB0
0x18000dd5e  xor     rbx, rax
0x18000dd61  jmp     short loc_18000DDB8
0x18000dd63  mov     rax, [rbx+8]
0x18000dd67  test    rax, rax
0x18000dd6a  jnz     short loc_18000DD55
0x18000dd6c  mov     rax, rbx
0x18000dd6f  mov     dl, byte ptr cs:qword_180047090
0x18000dd75  and     dl, dil
0x18000dd78  mov     rax, [rax+10h]
0x18000dd7c  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000dd80  test    dl, dl
0x18000dd82  jz      short loc_18000DD8C
0x18000dd84  test    rax, rax
0x18000dd87  jz      short loc_18000DDCC
0x18000dd89  xor     rax, rbx
0x18000dd8c  test    rax, rax
0x18000dd8f  jz      short loc_18000DDCC
0x18000dd91  mov     rcx, [rax+8]
0x18000dd95  test    dl, dl
0x18000dd97  jz      short loc_18000DDA1
0x18000dd99  test    rcx, rcx
0x18000dd9c  jz      short loc_18000DDAB
0x18000dd9e  xor     rcx, rax
0x18000dda1  test    rcx, rcx
0x18000dda4  jz      short loc_18000DDAB
0x18000dda6  cmp     rcx, rbx
0x18000dda9  jnz     short loc_18000DDB5
0x18000ddab  mov     rbx, rax
0x18000ddae  jmp     short loc_18000DD78
0x18000ddb0  mov     rbx, rax
0x18000ddb3  jmp     short loc_18000DDB8
0x18000ddb5  mov     rbx, rcx
0x18000ddb8  lea     rdx, [rsp+88h+arg_8]
0x18000ddc0  mov     rcx, rbx
0x18000ddc3  call    BthAuthClientWalkFxn
0x18000ddc8  test    eax, eax
0x18000ddca  jns     short loc_18000DD4D
0x18000ddcc  mov     rcx, cs:hMutex; hMutex
0x18000ddd3  call    cs:__imp_ReleaseMutex
0x18000ddda  nop     dword ptr [rax+rax+00h]
0x18000dddf  mov     rcx, [r14]; void *
0x18000dde2  call    ?BthServRegisterHandleNotifications@@YAPEAUHCMNOTIFICATION__@@PEAX@Z; BthServRegisterHandleNotifications(void *)
0x18000dde7  mov     qword ptr cs:pv, rax
0x18000ddee  test    rax, rax
0x18000ddf1  jz      short loc_18000DE0B
0x18000ddf3  xor     ecx, ecx
0x18000ddf5  cmp     qword ptr cs:hObject, rcx
0x18000ddfc  setz    cl; int
0x18000ddff  call    ?BthServListenForAsyncEvents@@YAHH@Z; BthServListenForAsyncEvents(int)
0x18000de04  mov     ebp, eax
0x18000de06  jmp     loc_18000DE8E
0x18000de0b  mov     rax, cs:WPP_GLOBAL_Control
0x18000de12  cmp     rax, r12
0x18000de15  jz      short loc_18000DE22
0x18000de17  cmp     byte ptr [rax+19h], 3
0x18000de1b  jb      short loc_18000DE22
0x18000de1d  mov     bl, dil
0x18000de20  jmp     short loc_18000DE24
0x18000de22  xor     bl, bl
0x18000de24  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000de2b  setnz   sil
0x18000de2f  test    bl, bl
0x18000de31  jnz     short loc_18000DE38
0x18000de33  test    sil, sil
0x18000de36  jz      short loc_18000DE74
0x18000de38  call    cs:__imp_GetLastError
0x18000de3f  nop     dword ptr [rax+rax+00h]
0x18000de44  mov     rdx, cs:WPP_GLOBAL_Control
0x18000de4b  mov     rcx, [rdx+10h]
0x18000de4f  mov     dword ptr [rsp+88h+var_40], eax
0x18000de53  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000de5a  mov     [rsp+88h+var_50], rax
0x18000de5f  mov     word ptr [rsp+88h+hTemplateFile], 57h ; 'W'
0x18000de66  mov     r9, [rdx+28h]
0x18000de6a  mov     r8b, sil
0x18000de6d  mov     dl, bl
0x18000de6f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000de74  lea     rcx, ?Globals@@3VBthServGlobals@@A; this
0x18000de7b  call    ?CloseRadioHandle@BthServGlobals@@QEAAXXZ; BthServGlobals::CloseRadioHandle(void)
0x18000de80  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000de84  lea     rcx, [rsp+88h+var_38]
0x18000de89  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18000de8e  mov     ecx, edi; int
0x18000de90  call    ?BthServBluetoothControlPanelTasksSetState@@YAXH@Z; BthServBluetoothControlPanelTasksSetState(int)
0x18000de95  call    ?BthServStartLEPrepairing@@YAXXZ; BthServStartLEPrepairing(void)
0x18000de9a  jmp     short loc_18000DF05
0x18000de9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dea3  cmp     rcx, r12
0x18000dea6  jz      short loc_18000DEB3
0x18000dea8  cmp     byte ptr [rcx+19h], 3
0x18000deac  jb      short loc_18000DEB3
0x18000deae  mov     bl, dil
0x18000deb1  jmp     short loc_18000DEB5
0x18000deb3  xor     bl, bl
0x18000deb5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000debc  setnz   sil
0x18000dec0  test    bl, bl
0x18000dec2  jnz     short loc_18000DEC9
0x18000dec4  test    sil, sil
0x18000dec7  jz      short loc_18000DF0C
0x18000dec9  call    cs:__imp_GetLastError
0x18000ded0  nop     dword ptr [rax+rax+00h]
0x18000ded5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dedc  mov     dword ptr [rsp+88h+var_40], eax
0x18000dee0  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000dee7  mov     [rsp+88h+var_50], rax
0x18000deec  mov     word ptr [rsp+88h+hTemplateFile], 58h ; 'X'
0x18000def3  mov     r9, [rcx+28h]
0x18000def7  mov     r8b, sil
0x18000defa  mov     dl, bl
0x18000defc  mov     rcx, [rcx+10h]
0x18000df00  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000df05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df0c  mov     rdx, [rsp+88h+var_30]
0x18000df11  test    rdx, rdx
0x18000df14  jz      short loc_18000DF5B
0x18000df16  or      eax, 0FFFFFFFFh
0x18000df19  lock xadd [rdx+8], eax
0x18000df1e  cmp     eax, 1
0x18000df21  jnz     short loc_18000DF54
0x18000df23  mov     rbx, [rsp+88h+var_30]
0x18000df28  mov     rax, [rbx]
0x18000df2b  mov     rcx, rbx
0x18000df2e  mov     rax, [rax]
0x18000df31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df36  or      eax, 0FFFFFFFFh
0x18000df39  lock xadd [rbx+0Ch], eax
0x18000df3e  cmp     eax, 1
0x18000df41  jnz     short loc_18000DF54
0x18000df43  mov     rcx, [rsp+88h+var_30]
0x18000df48  mov     rax, [rcx]
0x18000df4b  mov     rax, [rax+8]
0x18000df4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df5b  cmp     rcx, r12
0x18000df5e  jz      short loc_18000DF66
0x18000df60  cmp     byte ptr [rcx+19h], 5
0x18000df64  jnb     short loc_18000DF69
0x18000df66  xor     dil, dil
0x18000df69  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000df70  setnz   r8b
0x18000df74  test    dil, dil
0x18000df77  jnz     short loc_18000DF7E
0x18000df79  test    r8b, r8b
0x18000df7c  jz      short loc_18000DFA9
0x18000df7e  movsxd  rax, ebp
0x18000df81  mov     [rsp+88h+var_40], rax
0x18000df86  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000df8d  mov     [rsp+88h+var_50], rax
0x18000df92  mov     word ptr [rsp+88h+hTemplateFile], 59h ; 'Y'
0x18000df99  mov     r9, [rcx+28h]
0x18000df9d  mov     dl, dil
0x18000dfa0  mov     rcx, [rcx+10h]
0x18000dfa4  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000dfa9  mov     eax, ebp
0x18000dfab  lea     r11, [rsp+88h+var_28]
0x18000dfb0  mov     rbx, [r11+30h]
  ... truncated ...
```
