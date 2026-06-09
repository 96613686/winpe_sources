# DimsRoamEntry

- ea: `0x180003300`
- end: `0x18000355c`
- name: `DimsRoamEntry`
- size: `604`
- prototype: `void __fastcall(__int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x1800024e4`
- `0x1800025d8`
- `0x1800027d8`
- `0x180002f60`
- `0x180003300`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800034dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800034dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000349b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000349b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034cf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000332f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000332f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000333c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000333c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003539`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003539`
- `ntdll!EtwEventWrite` at `0x180003470`
- `ntdll!EtwEventWrite` at `0x180003470`
- `ntdll!EtwEventUnregister` at `0x1800034ee`
- `ntdll!EtwEventUnregister` at `0x1800034ee`
- `ntdll!EtwEventEnabled` at `0x180003435`
- `ntdll!EtwEventEnabled` at `0x180003435`
- `ntdll!EtwUnregisterTraceGuids` at `0x180003519`
- `ntdll!EtwUnregisterTraceGuids` at `0x180003519`
- `ntdll!EtwEventRegister` at `0x1800033e1`
- `ntdll!EtwEventRegister` at `0x1800033e1`
- `ntdll!EtwRegisterTraceGuidsW` at `0x1800033c0`
- `ntdll!EtwRegisterTraceGuidsW` at `0x1800033c0`
- `CRYPTSP!CryptReleaseContext` at `0x18000348e`
- `CRYPTSP!CryptReleaseContext` at `0x18000348e`

## pseudocode

```c
void __fastcall DimsRoamEntry(__int16 a1)
{
  __int64 *v1; // rbx
  __int64 *v2; // rdi
  int *v3; // r8
  _QWORD *v4; // rbx
  int inited; // [rsp+40h] [rbp-28h] BYREF
  int *p_inited; // [rsp+48h] [rbp-20h] BYREF
  __int64 v7; // [rsp+50h] [rbp-18h]

  inited = 0;
  if ( (a1 & 0x1000) != 0 )
    Sleep(0x2710u);
  EnterCriticalSection(&DimsRoam);
  qword_1800138A8 = 0;
  v1 = &WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v2 = &WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  qword_1800138B0 = 1;
  do
  {
    v3 = (int *)*v2;
    p_inited = v3;
    ++v2;
    v7 = 0;
    v1[4] = (__int64)v3;
    ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, int *, __int64, int **, _QWORD, _QWORD, __int64 *, int))EtwRegisterTraceGuidsW)(
      WppControlCallback,
      v1,
      v3,
      1,
      &p_inited,
      0,
      0,
      v1 + 1,
      inited);
    v1 = (__int64 *)*v1;
  }
  while ( v1 );
  if ( (unsigned int)EtwEventRegister(DIMS_ROAM_LOG, 0, 0, &qword_1800138C8) )
    qword_1800138C8 = 0;
  inited = DRR_InitRoaming();
  if ( !inited )
  {
    if ( !(unsigned int)DRR_GetStateFile() )
    {
      inited = DRR_ProcRoaming();
      if ( inited )
      {
        if ( (unsigned int)g_dwLoglevel > 1
          && qword_1800138C8
          && (unsigned __int8)EtwEventEnabled(qword_1800138C8, DRR_LOG_ERROR_FAILED) )
        {
          p_inited = &inited;
          v7 = 4;
          if ( qword_1800138C8 )
            EtwEventWrite(qword_1800138C8, DRR_LOG_ERROR_FAILED, 1, &p_inited);
          LocalFree(0);
        }
      }
      else
      {
        drr_UpdateLastSucceedTime();
      }
    }
    CryptReleaseContext(hProv, 0);
    LocalFree(Src);
    LocalFree(StringSid);
    LocalFree(xmmword_180013840);
    LocalFree(hMem);
    CloseHandle(*(&xmmword_180013840 + 1));
    RegCloseKey(hKey);
  }
  if ( qword_1800138C8 )
  {
    EtwEventUnregister();
    qword_1800138C8 = 0;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    while ( v4 )
    {
      if ( v4[1] )
      {
        EtwUnregisterTraceGuids();
        v4[1] = 0;
      }
      v4 = (_QWORD *)*v4;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  LeaveCriticalSection(&DimsRoam);
}

```

## disassembly

```asm
0x180003300  mov     [rsp+arg_0], rbx
0x180003305  mov     [rsp+arg_8], rsi
0x18000330a  push    rdi
0x18000330b  sub     rsp, 60h
0x18000330f  mov     rax, cs:__security_cookie
0x180003316  xor     rax, rsp
0x180003319  mov     [rsp+68h+var_10], rax
0x18000331e  xor     esi, esi
0x180003320  mov     [rsp+68h+var_28], esi
0x180003324  bt      ecx, 0Ch
0x180003328  jnb     short loc_180003335
0x18000332a  mov     ecx, 2710h; dwMilliseconds
0x18000332f  call    cs:__imp_Sleep
0x180003335  lea     rcx, DimsRoam; lpCriticalSection
0x18000333c  call    cs:__imp_EnterCriticalSection
0x180003342  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180003349  mov     cs:qword_1800138A8, rsi
0x180003350  lea     rbx, WPP_MAIN_CB
0x180003357  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000335e  mov     cs:WPP_GLOBAL_Control, rbx
0x180003365  lea     rdi, WPP_REGISTRATION_GUIDS
0x18000336c  mov     cs:WPP_MAIN_CB, rsi
0x180003373  mov     cs:qword_1800138B0, 1
0x18000337e  mov     r8, [rdi]
0x180003381  lea     rax, [rbx+8]
0x180003385  mov     [rsp+68h+var_30], rax
0x18000338a  lea     rcx, WppControlCallback
0x180003391  mov     [rsp+68h+var_38], rsi
0x180003396  lea     rax, [rsp+68h+var_20]
0x18000339b  mov     [rsp+68h+var_20], r8
0x1800033a0  lea     rdi, [rdi+8]
0x1800033a4  mov     [rsp+68h+var_18], rsi
0x1800033a9  mov     r9d, 1
0x1800033af  mov     [rsp+68h+var_40], rsi
0x1800033b4  mov     rdx, rbx
0x1800033b7  mov     [rsp+68h+var_48], rax
0x1800033bc  mov     [rbx+20h], r8
0x1800033c0  call    cs:__imp_EtwRegisterTraceGuidsW
0x1800033c6  mov     rbx, [rbx]
0x1800033c9  test    rbx, rbx
0x1800033cc  jnz     short loc_18000337E
0x1800033ce  lea     r9, qword_1800138C8
0x1800033d5  xor     r8d, r8d
0x1800033d8  xor     edx, edx
0x1800033da  lea     rcx, DIMS_ROAM_LOG
0x1800033e1  call    cs:__imp_EtwEventRegister
0x1800033e7  test    eax, eax
0x1800033e9  jz      short loc_1800033F2
0x1800033eb  mov     cs:qword_1800138C8, rsi
0x1800033f2  call    DRR_InitRoaming
0x1800033f7  mov     [rsp+68h+var_28], eax
0x1800033fb  test    eax, eax
0x1800033fd  jnz     loc_1800034E2
0x180003403  call    DRR_GetStateFile
0x180003408  test    eax, eax
0x18000340a  jnz     short loc_180003485
0x18000340c  call    DRR_ProcRoaming
0x180003411  mov     [rsp+68h+var_28], eax
0x180003415  test    eax, eax
0x180003417  jz      short loc_180003480
0x180003419  cmp     cs:g_dwLoglevel, 1
0x180003420  jbe     short loc_180003485
0x180003422  mov     rcx, cs:qword_1800138C8
0x180003429  test    rcx, rcx
0x18000342c  jz      short loc_180003485
0x18000342e  lea     rdx, DRR_LOG_ERROR_FAILED
0x180003435  call    cs:__imp_EtwEventEnabled
0x18000343b  test    al, al
0x18000343d  jz      short loc_180003485
0x18000343f  mov     rcx, cs:qword_1800138C8
0x180003446  lea     rax, [rsp+68h+var_28]
0x18000344b  mov     [rsp+68h+var_20], rax
0x180003450  mov     [rsp+68h+var_18], 4
0x180003459  test    rcx, rcx
0x18000345c  jz      short loc_180003476
0x18000345e  lea     r9, [rsp+68h+var_20]
0x180003463  mov     r8d, 1
0x180003469  lea     rdx, DRR_LOG_ERROR_FAILED
0x180003470  call    cs:__imp_EtwEventWrite
0x180003476  xor     ecx, ecx; hMem
0x180003478  call    cs:__imp_LocalFree
0x18000347e  jmp     short loc_180003485
0x180003480  call    _drr_UpdateLastSucceedTime
0x180003485  mov     rcx, cs:hProv; hProv
0x18000348c  xor     edx, edx; dwFlags
0x18000348e  call    cs:__imp_CryptReleaseContext
0x180003494  mov     rcx, cs:Src; hMem
0x18000349b  call    cs:__imp_LocalFree
0x1800034a1  mov     rcx, cs:StringSid; hMem
0x1800034a8  call    cs:__imp_LocalFree
0x1800034ae  mov     rcx, qword ptr cs:xmmword_180013840; hMem
0x1800034b5  call    cs:__imp_LocalFree
0x1800034bb  mov     rcx, cs:hMem; hMem
0x1800034c2  call    cs:__imp_LocalFree
0x1800034c8  mov     rcx, qword ptr cs:xmmword_180013840+8; hObject
0x1800034cf  call    cs:__imp_CloseHandle
0x1800034d5  mov     rcx, cs:hKey; hKey
0x1800034dc  call    cs:__imp_RegCloseKey
0x1800034e2  mov     rcx, cs:qword_1800138C8
0x1800034e9  test    rcx, rcx
0x1800034ec  jz      short loc_1800034FB
0x1800034ee  call    cs:__imp_EtwEventUnregister
0x1800034f4  mov     cs:qword_1800138C8, rsi
0x1800034fb  mov     rbx, cs:WPP_GLOBAL_Control
0x180003502  lea     rdi, WPP_GLOBAL_Control
0x180003509  cmp     rbx, rdi
0x18000350c  jz      short loc_180003532
0x18000350e  jmp     short loc_180003526
0x180003510  mov     rcx, [rbx+8]
0x180003514  test    rcx, rcx
0x180003517  jz      short loc_180003523
0x180003519  call    cs:__imp_EtwUnregisterTraceGuids
0x18000351f  mov     [rbx+8], rsi
0x180003523  mov     rbx, [rbx]
0x180003526  test    rbx, rbx
0x180003529  jnz     short loc_180003510
0x18000352b  mov     cs:WPP_GLOBAL_Control, rdi
0x180003532  lea     rcx, DimsRoam; lpCriticalSection
0x180003539  call    cs:__imp_LeaveCriticalSection
0x18000353f  mov     rcx, [rsp+68h+var_10]
0x180003544  xor     rcx, rsp; StackCookie
0x180003547  call    __security_check_cookie
0x18000354c  mov     rbx, [rsp+68h+arg_0]
0x180003551  mov     rsi, [rsp+68h+arg_8]
0x180003556  add     rsp, 60h
0x18000355a  pop     rdi
0x18000355b  retn
```
