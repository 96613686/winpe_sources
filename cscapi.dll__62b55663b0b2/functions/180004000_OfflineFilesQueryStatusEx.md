# OfflineFilesQueryStatusEx

- ea: `0x180004000`
- end: `0x1800045a9`
- name: `OfflineFilesQueryStatusEx`
- size: `1449`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180003f50`

## callees

- `0x180004000`
- `0x1800045b0`
- `0x180007bcc`
- `0x180007bf4`
- `0x180007c34`
- `0x180007dd4`
- `0x180007e54`
- `0x180007ee8`
- `0x180007fa4`
- `0x180009490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000440a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000440a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004497`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000412c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800041d5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000412c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800041d5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000414e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800041f7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000414e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800041f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004163`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041a7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000420c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004251`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004163`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041a7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000420c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004251`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180004196`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180004240`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180004196`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180004240`

## string_xrefs

- `0x1800041ed`: `CscService`
- `0x18000434c`: `CscService`
- `0x1800044c3`: `CscService`

## pseudocode

```c
__int64 __fastcall OfflineFilesQueryStatusEx(_DWORD *a1, _DWORD *a2, _DWORD *a3)
{
  unsigned int CscEnabledState; // ebx
  _QWORD *v7; // rcx
  __int64 result; // rax
  __int64 v9; // r8
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rbp
  SC_HANDLE v12; // r14
  SC_HANDLE v13; // rax
  SC_HANDLE v14; // r14
  SC_HANDLE v15; // rbp
  __int64 v16; // r8
  __int64 v17; // rcx
  const wchar_t *v18; // r9
  DWORD LastError; // eax
  int v20; // edx
  int v21; // r8d
  DWORD v22; // eax
  int v23; // edx
  int v24; // r8d
  DWORD v25; // eax
  __int64 v26; // r8
  DWORD v27; // eax
  int v28; // r8d
  DWORD v29; // eax
  __int64 v30; // r8
  DWORD v31; // eax
  int v32; // r8d
  __int64 v33; // r8
  const wchar_t *v34; // r9
  const wchar_t *v35; // r9
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-98h] BYREF
  BYTE v37[16]; // [rsp+38h] [rbp-90h] BYREF
  __int128 v38; // [rsp+48h] [rbp-80h]
  int v39; // [rsp+58h] [rbp-70h]
  BYTE Buffer[16]; // [rsp+60h] [rbp-68h] BYREF
  __int128 v41; // [rsp+70h] [rbp-58h]
  int v42; // [rsp+80h] [rbp-48h]

  CscEnabledState = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 20, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
    goto LABEL_5;
  *a1 = 0;
  v42 = 0;
  *(_OWORD *)Buffer = 0;
  v41 = 0;
  v10 = OpenSCManagerW(0, 0, 0x80000000);
  v11 = v10;
  if ( v10 )
  {
    v12 = OpenServiceW(v10, L"Csc", 0x80000000);
    if ( !v12 )
    {
      LastError = GetLastError();
      CscEnabledState = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 22), v20, v21, (unsigned int)L"Csc", 0, LastError);
    }
    CloseServiceHandle(v11);
    goto LABEL_18;
  }
  v12 = 0;
  v25 = GetLastError();
  CscEnabledState = v25;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 10, v26, 0x80000000LL, v25);
LABEL_18:
    v7 = WPP_GLOBAL_Control;
  }
  if ( CscEnabledState )
    goto LABEL_44;
  pcbBytesNeeded = 0;
  if ( !QueryServiceStatusEx(v12, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
  {
    v27 = GetLastError();
    CscEnabledState = v27;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), 12, v28, (unsigned int)L"Csc", v27);
  }
  CloseServiceHandle(v12);
  if ( CscEnabledState )
    goto LABEL_43;
  v39 = 0;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v13 = OpenSCManagerW(0, 0, 0x80000000);
  v14 = v13;
  if ( v13 )
  {
    v15 = OpenServiceW(v13, L"CscService", 0x80000000);
    if ( !v15 )
    {
      v22 = GetLastError();
      CscEnabledState = v22;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 22), v23, v24, (unsigned int)L"CscService", 0, v22);
    }
    CloseServiceHandle(v14);
    goto LABEL_25;
  }
  v15 = 0;
  v29 = GetLastError();
  CscEnabledState = v29;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 10, v30, 0x80000000LL, v29);
LABEL_25:
    v7 = WPP_GLOBAL_Control;
  }
  if ( CscEnabledState )
    goto LABEL_44;
  pcbBytesNeeded = 0;
  if ( !QueryServiceStatusEx(v15, SC_STATUS_PROCESS_INFO, v37, 0x24u, &pcbBytesNeeded) )
  {
    v31 = GetLastError();
    CscEnabledState = v31;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), 12, v32, (unsigned int)L"CscService", v31);
  }
  CloseServiceHandle(v15);
  v7 = WPP_GLOBAL_Control;
  if ( CscEnabledState )
    goto LABEL_44;
  if ( *(_DWORD *)&v37[4] == 4 && *(_DWORD *)&Buffer[4] == 4 )
  {
    *a1 = 1;
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 188) & 1) != 0 )
  {
    v17 = v7[22];
    v18 = L"active";
    if ( !*a1 )
      v18 = L"inactive";
    WPP_SF_S(v17, 21, v16, v18);
    v7 = WPP_GLOBAL_Control;
  }
LABEL_5:
  if ( !a2 )
    goto LABEL_6;
  CscEnabledState = QueryCscEnabledState(a2);
  if ( CscEnabledState )
  {
LABEL_43:
    v7 = WPP_GLOBAL_Control;
LABEL_44:
    if ( CscEnabledState == 1060 )
    {
      if ( a2 )
      {
        *a2 = 0;
        v7 = WPP_GLOBAL_Control;
      }
      if ( a1 )
      {
        *a1 = 0;
        v7 = WPP_GLOBAL_Control;
      }
      if ( a3 )
      {
        *a3 = 0;
        v7 = WPP_GLOBAL_Control;
      }
      CscEnabledState = 0;
    }
    goto LABEL_10;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
  {
    v34 = L"enabled";
    if ( *a2 == CscEnabledState )
      v34 = L"disabled";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 22), 22, v33, v34);
    v7 = WPP_GLOBAL_Control;
  }
LABEL_6:
  if ( !a3 )
    goto LABEL_10;
  result = QueryCscAvailableState(a3);
  CscEnabledState = result;
  if ( (_DWORD)result )
    goto LABEL_43;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
  {
    v35 = L"available";
    if ( !*a3 )
      v35 = L"unavailable";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 22), 23, v9, v35);
    v7 = WPP_GLOBAL_Control;
  }
LABEL_10:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 188) & 2) != 0 )
    WPP_SF_d(v7[22], 24, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids, CscEnabledState);
  return CscEnabledState;
}

```

## disassembly

```asm
0x180004000  push    rbx
0x180004002  push    rsi
0x180004003  push    rdi
0x180004004  push    r12
0x180004006  push    r13
0x180004008  sub     rsp, 0A0h
0x18000400f  mov     rax, cs:__security_cookie
0x180004016  xor     rax, rsp
0x180004019  mov     [rsp+0C8h+var_40], rax
0x180004021  mov     rdi, r8
0x180004024  mov     r12, rdx
0x180004027  mov     rsi, rcx
0x18000402a  xor     ebx, ebx
0x18000402c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004033  lea     r13, WPP_GLOBAL_Control
0x18000403a  cmp     rcx, r13
0x18000403d  jz      short loc_18000404C
0x18000403f  test    byte ptr [rcx+0BCh], 1
0x180004046  jnz     loc_18000439E
0x18000404c  mov     [rsp+0C8h+arg_18], rbp
0x180004054  mov     [rsp+0C8h+var_30], r14
0x18000405c  mov     [rsp+0C8h+var_38], r15
0x180004064  test    rsi, rsi
0x180004067  jnz     loc_18000410A
0x18000406d  test    r12, r12
0x180004070  jnz     loc_1800044DD
0x180004076  test    rdi, rdi
0x180004079  jz      short loc_1800040A6
0x18000407b  mov     rcx, rdi
0x18000407e  call    _QueryCscAvailableState
0x180004083  mov     ebx, eax
0x180004085  test    eax, eax
0x180004087  jnz     loc_180004369
0x18000408d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004094  cmp     rcx, r13
0x180004097  jz      short loc_1800040AD
0x180004099  test    byte ptr [rcx+0BCh], 1
0x1800040a0  jnz     loc_18000453F
0x1800040a6  cmp     rcx, r13
0x1800040a9  jnz     short loc_1800040E4
0x1800040ab  mov     eax, ebx
0x1800040ad  mov     r15, [rsp+0C8h+var_38]
0x1800040b5  mov     r14, [rsp+0C8h+var_30]
0x1800040bd  mov     rbp, [rsp+0C8h+arg_18]
0x1800040c5  mov     rcx, [rsp+0C8h+var_40]
0x1800040cd  xor     rcx, rsp; StackCookie
0x1800040d0  call    __security_check_cookie
0x1800040d5  add     rsp, 0A0h
0x1800040dc  pop     r13
0x1800040de  pop     r12
0x1800040e0  pop     rdi
0x1800040e1  pop     rsi
0x1800040e2  pop     rbx
0x1800040e3  retn
0x1800040e4  test    byte ptr [rcx+0BCh], 2
0x1800040eb  jz      short loc_1800040AB
0x1800040ed  mov     rcx, [rcx+0B0h]
0x1800040f4  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x1800040fb  mov     edx, 18h
0x180004100  mov     r9d, ebx
0x180004103  call    WPP_SF_d
0x180004108  jmp     short loc_1800040AB
0x18000410a  xorps   xmm0, xmm0
0x18000410d  mov     [rsi], ebx
0x18000410f  xor     eax, eax
0x180004111  xor     edx, edx; lpDatabaseName
0x180004113  xor     ecx, ecx; lpMachineName
0x180004115  mov     [rsp+0C8h+var_48], eax
0x18000411c  mov     r8d, 80000000h; dwDesiredAccess
0x180004122  movups  xmmword ptr [rsp+0C8h+Buffer], xmm0
0x180004127  movups  [rsp+0C8h+var_58], xmm0
0x18000412c  call    cs:__imp_OpenSCManagerW
0x180004132  mov     rbp, rax
0x180004135  test    rax, rax
0x180004138  jz      loc_1800043C2
0x18000413e  mov     r8d, 80000000h; dwDesiredAccess
0x180004144  lea     rdx, g_szCscDriverName; "Csc"
0x18000414b  mov     rcx, rax; hSCManager
0x18000414e  call    cs:__imp_OpenServiceW
0x180004154  mov     r14, rax
0x180004157  test    rax, rax
0x18000415a  jz      loc_1800042D7
0x180004160  mov     rcx, rbp; hSCObject
0x180004163  call    cs:__imp_CloseServiceHandle
0x180004169  mov     rcx, cs:WPP_GLOBAL_Control
0x180004170  test    ebx, ebx
0x180004172  jnz     loc_180004370
0x180004178  lea     rax, [rsp+0C8h+var_98]
0x18000417d  mov     [rsp+0C8h+var_98], ebx
0x180004181  mov     r9d, 24h ; '$'; cbBufSize
0x180004187  mov     [rsp+0C8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000418c  lea     r8, [rsp+0C8h+Buffer]; lpBuffer
0x180004191  xor     edx, edx; InfoLevel
0x180004193  mov     rcx, r14; hService
0x180004196  call    cs:__imp_QueryServiceStatusEx
0x18000419c  test    eax, eax
0x18000419e  jz      loc_18000440A
0x1800041a4  mov     rcx, r14; hSCObject
0x1800041a7  call    cs:__imp_CloseServiceHandle
0x1800041ad  test    ebx, ebx
0x1800041af  jnz     loc_180004369
0x1800041b5  xorps   xmm0, xmm0
0x1800041b8  xor     eax, eax
0x1800041ba  xor     edx, edx; lpDatabaseName
0x1800041bc  mov     [rsp+0C8h+var_70], eax
0x1800041c0  xor     ecx, ecx; lpMachineName
0x1800041c2  mov     r8d, 80000000h; dwDesiredAccess
0x1800041c8  movups  xmmword ptr [rsp+0C8h+var_90], xmm0
0x1800041cd  xor     r15d, r15d
0x1800041d0  movups  [rsp+0C8h+var_80], xmm0
0x1800041d5  call    cs:__imp_OpenSCManagerW
0x1800041db  mov     r14, rax
0x1800041de  test    rax, rax
0x1800041e1  jz      loc_180004450
0x1800041e7  mov     r8d, 80000000h; dwDesiredAccess
0x1800041ed  lea     rdx, g_szCscServiceName; "CscService"
0x1800041f4  mov     rcx, rax; hSCManager
0x1800041f7  call    cs:__imp_OpenServiceW
0x1800041fd  mov     rbp, rax
0x180004200  test    rax, rax
0x180004203  jz      loc_180004320
0x180004209  mov     rcx, r14; hSCObject
0x18000420c  call    cs:__imp_CloseServiceHandle
0x180004212  mov     rcx, cs:WPP_GLOBAL_Control
0x180004219  test    ebx, ebx
0x18000421b  jnz     loc_180004370
0x180004221  lea     rax, [rsp+0C8h+var_98]
0x180004226  mov     [rsp+0C8h+var_98], r15d
0x18000422b  mov     r9d, 24h ; '$'; cbBufSize
0x180004231  mov     [rsp+0C8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180004236  lea     r8, [rsp+0C8h+var_90]; lpBuffer
0x18000423b  xor     edx, edx; InfoLevel
0x18000423d  mov     rcx, rbp; hService
0x180004240  call    cs:__imp_QueryServiceStatusEx
0x180004246  test    eax, eax
0x180004248  jz      loc_180004497
0x18000424e  mov     rcx, rbp; hSCObject
0x180004251  call    cs:__imp_CloseServiceHandle
0x180004257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000425e  test    ebx, ebx
0x180004260  jnz     loc_180004370
0x180004266  mov     r15d, dword ptr [rsp+0C8h+var_90+4]
0x18000426b  cmp     r15d, 4
0x18000426f  jnz     short loc_180004287
0x180004271  cmp     dword ptr [rsp+0C8h+Buffer+4], r15d
0x180004276  jnz     short loc_180004287
0x180004278  mov     dword ptr [rsi], 1
0x18000427e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004285  jmp     short loc_18000428F
0x180004287  test    ebx, ebx
0x180004289  jnz     loc_180004370
0x18000428f  cmp     rcx, r13
0x180004292  jz      loc_18000406D
0x180004298  test    byte ptr [rcx+0BCh], 1
0x18000429f  jz      loc_18000406D
0x1800042a5  cmp     dword ptr [rsi], 0
0x1800042a8  lea     rax, aInactive; "inactive"
0x1800042af  mov     rcx, [rcx+0B0h]
0x1800042b6  lea     r9, aActive; "active"
0x1800042bd  cmovz   r9, rax
0x1800042c1  mov     edx, 15h
0x1800042c6  call    WPP_SF_S
0x1800042cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042d2  jmp     loc_18000406D
0x1800042d7  call    cs:__imp_GetLastError
0x1800042dd  mov     ebx, eax
0x1800042df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042e6  cmp     rcx, r13
0x1800042e9  jz      loc_180004160
0x1800042ef  test    byte ptr [rcx+0BCh], 1
0x1800042f6  jz      loc_180004160
0x1800042fc  mov     rcx, [rcx+0B0h]
0x180004303  lea     r9, g_szCscDriverName; "Csc"
0x18000430a  mov     [rsp+0C8h+var_A0], eax
0x18000430e  mov     dword ptr [rsp+0C8h+pcbBytesNeeded], 80000000h
0x180004316  call    WPP_SF_Sdd
0x18000431b  jmp     loc_180004160
0x180004320  call    cs:__imp_GetLastError
0x180004326  mov     ebx, eax
0x180004328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000432f  cmp     rcx, r13
0x180004332  jz      loc_180004209
0x180004338  test    byte ptr [rcx+0BCh], 1
0x18000433f  jz      loc_180004209
0x180004345  mov     rcx, [rcx+0B0h]
0x18000434c  lea     r9, g_szCscServiceName; "CscService"
0x180004353  mov     [rsp+0C8h+var_A0], eax
0x180004357  mov     dword ptr [rsp+0C8h+pcbBytesNeeded], 80000000h
0x18000435f  call    WPP_SF_Sdd
0x180004364  jmp     loc_180004209
0x180004369  mov     rcx, cs:WPP_GLOBAL_Control
0x180004370  cmp     ebx, 424h
0x180004376  jnz     loc_1800040A6
0x18000437c  test    r12, r12
0x18000437f  jnz     loc_180004571
0x180004385  test    rsi, rsi
0x180004388  jnz     loc_180004585
0x18000438e  test    rdi, rdi
0x180004391  jnz     loc_180004597
0x180004397  xor     ebx, ebx
0x180004399  jmp     loc_1800040A6
0x18000439e  mov     rcx, [rcx+0B0h]
0x1800043a5  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x1800043ac  mov     edx, 14h
0x1800043b1  call    WPP_SF_
0x1800043b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043bd  jmp     loc_18000404C
0x1800043c2  xor     r14d, r14d
0x1800043c5  call    cs:__imp_GetLastError
0x1800043cb  mov     ebx, eax
0x1800043cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043d4  cmp     rcx, r13
0x1800043d7  jz      loc_180004170
0x1800043dd  test    byte ptr [rcx+0BCh], 1
0x1800043e4  jz      loc_180004170
0x1800043ea  mov     rcx, [rcx+0B0h]
0x1800043f1  mov     edx, 0Ah
0x1800043f6  mov     r9d, 80000000h
0x1800043fc  mov     dword ptr [rsp+0C8h+pcbBytesNeeded], eax
0x180004400  call    WPP_SF_dd
0x180004405  jmp     loc_180004169
0x18000440a  call    cs:__imp_GetLastError
0x180004410  mov     ebx, eax
0x180004412  mov     rcx, cs:WPP_GLOBAL_Control
0x180004419  cmp     rcx, r13
0x18000441c  jz      loc_1800041A4
0x180004422  test    byte ptr [rcx+0BCh], 1
0x180004429  jz      loc_1800041A4
0x18000442f  mov     rcx, [rcx+0B0h]
0x180004436  lea     r9, g_szCscDriverName; "Csc"
0x18000443d  mov     edx, 0Ch
0x180004442  mov     dword ptr [rsp+0C8h+pcbBytesNeeded], eax
0x180004446  call    WPP_SF_Sd
0x18000444b  jmp     loc_1800041A4
0x180004450  xor     ebp, ebp
0x180004452  call    cs:__imp_GetLastError
0x180004458  mov     ebx, eax
0x18000445a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004461  cmp     rcx, r13
0x180004464  jz      loc_180004219
0x18000446a  test    byte ptr [rcx+0BCh], 1
0x180004471  jz      loc_180004219
0x180004477  mov     rcx, [rcx+0B0h]
0x18000447e  mov     edx, 0Ah
0x180004483  mov     r9d, 80000000h
0x180004489  mov     dword ptr [rsp+0C8h+pcbBytesNeeded], eax
0x18000448d  call    WPP_SF_dd
0x180004492  jmp     loc_180004212
0x180004497  call    cs:__imp_GetLastError
0x18000449d  mov     ebx, eax
0x18000449f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044a6  cmp     rcx, r13
0x1800044a9  jz      loc_18000424E
0x1800044af  test    byte ptr [rcx+0BCh], 1
0x1800044b6  jz      loc_18000424E
0x1800044bc  mov     rcx, [rcx+0B0h]
0x1800044c3  lea     r9, g_szCscServiceName; "CscService"
0x1800044ca  mov     edx, 0Ch
0x1800044cf  mov     dword ptr [rsp+0C8h+pcbBytesNeeded], eax
0x1800044d3  call    WPP_SF_Sd
0x1800044d8  jmp     loc_18000424E
0x1800044dd  mov     rcx, r12
0x1800044e0  call    _QueryCscEnabledState
0x1800044e5  mov     ebx, eax
0x1800044e7  test    eax, eax
0x1800044e9  jnz     loc_180004369
0x1800044ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044f6  cmp     rcx, r13
0x1800044f9  jz      loc_180004076
0x1800044ff  test    byte ptr [rcx+0BCh], 1
0x180004506  jz      loc_180004076
0x18000450c  cmp     [r12], ebx
0x180004510  lea     rax, aDisabled; "disabled"
0x180004517  mov     rcx, [rcx+0B0h]
0x18000451e  lea     r9, aEnabled; "enabled"
0x180004525  cmovz   r9, rax
0x180004529  mov     edx, 16h
0x18000452e  call    WPP_SF_S
0x180004533  mov     rcx, cs:WPP_GLOBAL_Control
0x18000453a  jmp     loc_180004076
0x18000453f  cmp     dword ptr [rdi], 0
0x180004542  lea     rax, aUnavailable; "unavailable"
0x180004549  mov     rcx, [rcx+0B0h]
0x180004550  lea     r9, aAvailable; "available"
0x180004557  cmovz   r9, rax
0x18000455b  mov     edx, 17h
0x180004560  call    WPP_SF_S
0x180004565  mov     rcx, cs:WPP_GLOBAL_Control
0x18000456c  jmp     loc_1800040A6
0x180004571  mov     dword ptr [r12], 0
0x180004579  mov     rcx, cs:WPP_GLOBAL_Control
0x180004580  jmp     loc_180004385
0x180004585  mov     dword ptr [rsi], 0
0x18000458b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004592  jmp     loc_18000438E
0x180004597  mov     dword ptr [rdi], 0
0x18000459d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045a4  jmp     loc_180004397
```
