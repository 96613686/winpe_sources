# _QueryDriverAndServiceState

- ea: `0x1800052f0`
- end: `0x180005650`
- name: `_QueryDriverAndServiceState`
- size: `864`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800073f0`
- `0x180007950`

## callees

- `0x1800052f0`
- `0x180007dd4`
- `0x180007e54`
- `0x180007ee8`
- `0x180009490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000557c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000560a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000557c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000560a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005338`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800053e9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005338`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800053e9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000535e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000540d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000535e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000540d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000537a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800053b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005422`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000545b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000537a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800053b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005422`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000545b`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800053a6`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000544a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800053a6`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000544a`

## string_xrefs

- `0x180005401`: `CscService`
- `0x180005509`: `CscService`
- `0x180005636`: `CscService`

## pseudocode

```c
__int64 __fastcall QueryDriverAndServiceState(_DWORD *a1, _DWORD *a2)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  DWORD v6; // esi
  SC_HANDLE v7; // rdi
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rsi
  DWORD v10; // ebx
  SC_HANDLE v11; // rdi
  DWORD LastError; // eax
  int v14; // edx
  int v15; // r8d
  DWORD v16; // eax
  int v17; // edx
  int v18; // r8d
  DWORD v19; // eax
  __int64 v20; // r8
  DWORD v21; // eax
  int v22; // r8d
  DWORD v23; // eax
  __int64 v24; // r8
  DWORD v25; // eax
  int v26; // r8d
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-68h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v29; // [rsp+48h] [rbp-50h]
  int v30; // [rsp+58h] [rbp-40h]

  v30 = 0;
  *(_OWORD *)Buffer = 0;
  v29 = 0;
  v4 = OpenSCManagerW(0, 0, 0x80000000);
  v5 = v4;
  if ( v4 )
  {
    v6 = 0;
    v7 = OpenServiceW(v4, L"Csc", 0x80000000);
    if ( !v7 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 22), v14, v15, (unsigned int)L"Csc", 0, LastError);
    }
    CloseServiceHandle(v5);
  }
  else
  {
    v7 = 0;
    v19 = GetLastError();
    v6 = v19;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 10, v20, 0x80000000LL, v19);
  }
  if ( v6 )
    return v6;
  pcbBytesNeeded = 0;
  if ( !QueryServiceStatusEx(v7, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
  {
    v21 = GetLastError();
    v6 = v21;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), 12, v22, (unsigned int)L"Csc", v21);
  }
  CloseServiceHandle(v7);
  if ( v6 )
    return v6;
  *a1 = *(_DWORD *)&Buffer[4];
  v30 = 0;
  *(_OWORD *)Buffer = 0;
  v29 = 0;
  v8 = OpenSCManagerW(0, 0, 0x80000000);
  v9 = v8;
  if ( v8 )
  {
    v10 = 0;
    v11 = OpenServiceW(v8, L"CscService", 0x80000000);
    if ( !v11 )
    {
      v16 = GetLastError();
      v10 = v16;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 22), v17, v18, (unsigned int)L"CscService", 0, v16);
    }
    CloseServiceHandle(v9);
  }
  else
  {
    v11 = 0;
    v23 = GetLastError();
    v10 = v23;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 10, v24, 0x80000000LL, v23);
  }
  if ( !v10 )
  {
    pcbBytesNeeded = 0;
    if ( !QueryServiceStatusEx(v11, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    {
      v25 = GetLastError();
      v10 = v25;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), 12, v26, (unsigned int)L"CscService", v25);
    }
    CloseServiceHandle(v11);
    if ( !v10 )
      *a2 = *(_DWORD *)&Buffer[4];
  }
  return v10;
}

```

## disassembly

```asm
0x1800052f0  mov     [rsp+arg_10], rbx
0x1800052f5  mov     [rsp+arg_18], rbp
0x1800052fa  push    rsi
0x1800052fb  push    rdi
0x1800052fc  push    r12
0x1800052fe  push    r14
0x180005300  push    r15
0x180005302  sub     rsp, 70h
0x180005306  mov     rax, cs:__security_cookie
0x18000530d  xor     rax, rsp
0x180005310  mov     [rsp+98h+var_38], rax
0x180005315  xorps   xmm0, xmm0
0x180005318  mov     r14, rdx
0x18000531b  mov     r15, rcx
0x18000531e  xor     eax, eax
0x180005320  xor     edx, edx; lpDatabaseName
0x180005322  mov     [rsp+98h+var_40], eax
0x180005326  xor     ecx, ecx; lpMachineName
0x180005328  mov     r8d, 80000000h; dwDesiredAccess
0x18000532e  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x180005333  movups  [rsp+98h+var_50], xmm0
0x180005338  call    cs:__imp_OpenSCManagerW
0x18000533e  xor     ebp, ebp
0x180005340  mov     rbx, rax
0x180005343  test    rax, rax
0x180005346  jz      loc_18000552D
0x18000534c  mov     r8d, 80000000h; dwDesiredAccess
0x180005352  lea     rdx, g_szCscDriverName; "Csc"
0x180005359  mov     rcx, rax; hSCManager
0x18000535c  mov     esi, ebp
0x18000535e  call    cs:__imp_OpenServiceW
0x180005364  lea     r12, WPP_GLOBAL_Control
0x18000536b  mov     rdi, rax
0x18000536e  test    rax, rax
0x180005371  jz      loc_180005494
0x180005377  mov     rcx, rbx; hSCObject
0x18000537a  call    cs:__imp_CloseServiceHandle
0x180005380  test    esi, esi
0x180005382  jnz     loc_180005526
0x180005388  lea     rax, [rsp+98h+var_68]
0x18000538d  mov     [rsp+98h+var_68], ebp
0x180005391  mov     r9d, 24h ; '$'; cbBufSize
0x180005397  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000539c  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x1800053a1  xor     edx, edx; InfoLevel
0x1800053a3  mov     rcx, rdi; hService
0x1800053a6  call    cs:__imp_QueryServiceStatusEx
0x1800053ac  test    eax, eax
0x1800053ae  jz      loc_18000557C
0x1800053b4  mov     rcx, rdi; hSCObject
0x1800053b7  call    cs:__imp_CloseServiceHandle
0x1800053bd  test    esi, esi
0x1800053bf  jnz     loc_180005526
0x1800053c5  mov     eax, dword ptr [rsp+98h+Buffer+4]
0x1800053c9  xorps   xmm0, xmm0
0x1800053cc  mov     [r15], eax
0x1800053cf  xor     edx, edx; lpDatabaseName
0x1800053d1  xor     eax, eax
0x1800053d3  xor     ecx, ecx; lpMachineName
0x1800053d5  mov     r8d, 80000000h; dwDesiredAccess
0x1800053db  mov     [rsp+98h+var_40], eax
0x1800053df  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x1800053e4  movups  [rsp+98h+var_50], xmm0
0x1800053e9  call    cs:__imp_OpenSCManagerW
0x1800053ef  mov     rsi, rax
0x1800053f2  test    rax, rax
0x1800053f5  jz      loc_1800055C2
0x1800053fb  mov     r8d, 80000000h; dwDesiredAccess
0x180005401  lea     rdx, g_szCscServiceName; "CscService"
0x180005408  mov     rcx, rax; hSCManager
0x18000540b  mov     ebx, ebp
0x18000540d  call    cs:__imp_OpenServiceW
0x180005413  mov     rdi, rax
0x180005416  test    rax, rax
0x180005419  jz      loc_1800054DD
0x18000541f  mov     rcx, rsi; hSCObject
0x180005422  call    cs:__imp_CloseServiceHandle
0x180005428  test    ebx, ebx
0x18000542a  jnz     short loc_18000546C
0x18000542c  lea     rax, [rsp+98h+var_68]
0x180005431  mov     [rsp+98h+var_68], ebp
0x180005435  mov     r9d, 24h ; '$'; cbBufSize
0x18000543b  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180005440  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x180005445  xor     edx, edx; InfoLevel
0x180005447  mov     rcx, rdi; hService
0x18000544a  call    cs:__imp_QueryServiceStatusEx
0x180005450  test    eax, eax
0x180005452  jz      loc_18000560A
0x180005458  mov     rcx, rdi; hSCObject
0x18000545b  call    cs:__imp_CloseServiceHandle
0x180005461  test    ebx, ebx
0x180005463  jnz     short loc_18000546C
0x180005465  mov     eax, dword ptr [rsp+98h+Buffer+4]
0x180005469  mov     [r14], eax
0x18000546c  mov     eax, ebx
0x18000546e  mov     rcx, [rsp+98h+var_38]
0x180005473  xor     rcx, rsp; StackCookie
0x180005476  call    __security_check_cookie
0x18000547b  lea     r11, [rsp+98h+var_28]
0x180005480  mov     rbx, [r11+40h]
0x180005484  mov     rbp, [r11+48h]
0x180005488  mov     rsp, r11
0x18000548b  pop     r15
0x18000548d  pop     r14
0x18000548f  pop     r12
0x180005491  pop     rdi
0x180005492  pop     rsi
0x180005493  retn
0x180005494  call    cs:__imp_GetLastError
0x18000549a  mov     esi, eax
0x18000549c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054a3  cmp     rcx, r12
0x1800054a6  jz      loc_180005377
0x1800054ac  test    byte ptr [rcx+0BCh], 1
0x1800054b3  jz      loc_180005377
0x1800054b9  mov     rcx, [rcx+0B0h]
0x1800054c0  lea     r9, g_szCscDriverName; "Csc"
0x1800054c7  mov     [rsp+98h+var_70], eax
0x1800054cb  mov     dword ptr [rsp+98h+pcbBytesNeeded], 80000000h
0x1800054d3  call    WPP_SF_Sdd
0x1800054d8  jmp     loc_180005377
0x1800054dd  call    cs:__imp_GetLastError
0x1800054e3  mov     ebx, eax
0x1800054e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054ec  cmp     rcx, r12
0x1800054ef  jz      loc_18000541F
0x1800054f5  test    byte ptr [rcx+0BCh], 1
0x1800054fc  jz      loc_18000541F
0x180005502  mov     rcx, [rcx+0B0h]
0x180005509  lea     r9, g_szCscServiceName; "CscService"
0x180005510  mov     [rsp+98h+var_70], eax
0x180005514  mov     dword ptr [rsp+98h+pcbBytesNeeded], 80000000h
0x18000551c  call    WPP_SF_Sdd
0x180005521  jmp     loc_18000541F
0x180005526  mov     eax, esi
0x180005528  jmp     loc_18000546E
0x18000552d  mov     rdi, rbp
0x180005530  call    cs:__imp_GetLastError
0x180005536  mov     esi, eax
0x180005538  mov     rcx, cs:WPP_GLOBAL_Control
0x18000553f  lea     r12, WPP_GLOBAL_Control
0x180005546  cmp     rcx, r12
0x180005549  jz      loc_180005380
0x18000554f  test    byte ptr [rcx+0BCh], 1
0x180005556  jz      loc_180005380
0x18000555c  mov     rcx, [rcx+0B0h]
0x180005563  mov     edx, 0Ah
0x180005568  mov     r9d, 80000000h
0x18000556e  mov     dword ptr [rsp+98h+pcbBytesNeeded], eax
0x180005572  call    WPP_SF_dd
0x180005577  jmp     loc_180005380
0x18000557c  call    cs:__imp_GetLastError
0x180005582  mov     esi, eax
0x180005584  mov     rcx, cs:WPP_GLOBAL_Control
0x18000558b  cmp     rcx, r12
0x18000558e  jz      loc_1800053B4
0x180005594  test    byte ptr [rcx+0BCh], 1
0x18000559b  jz      loc_1800053B4
0x1800055a1  mov     rcx, [rcx+0B0h]
0x1800055a8  lea     r9, g_szCscDriverName; "Csc"
0x1800055af  mov     edx, 0Ch
0x1800055b4  mov     dword ptr [rsp+98h+pcbBytesNeeded], eax
0x1800055b8  call    WPP_SF_Sd
0x1800055bd  jmp     loc_1800053B4
0x1800055c2  mov     rdi, rbp
0x1800055c5  call    cs:__imp_GetLastError
0x1800055cb  mov     ebx, eax
0x1800055cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055d4  cmp     rcx, r12
0x1800055d7  jz      loc_180005428
0x1800055dd  test    byte ptr [rcx+0BCh], 1
0x1800055e4  jz      loc_180005428
0x1800055ea  mov     rcx, [rcx+0B0h]
0x1800055f1  mov     edx, 0Ah
0x1800055f6  mov     r9d, 80000000h
0x1800055fc  mov     dword ptr [rsp+98h+pcbBytesNeeded], eax
0x180005600  call    WPP_SF_dd
0x180005605  jmp     loc_180005428
0x18000560a  call    cs:__imp_GetLastError
0x180005610  mov     ebx, eax
0x180005612  mov     rcx, cs:WPP_GLOBAL_Control
0x180005619  cmp     rcx, r12
0x18000561c  jz      loc_180005458
0x180005622  test    byte ptr [rcx+0BCh], 1
0x180005629  jz      loc_180005458
0x18000562f  mov     rcx, [rcx+0B0h]
0x180005636  lea     r9, g_szCscServiceName; "CscService"
0x18000563d  mov     edx, 0Ch
0x180005642  mov     dword ptr [rsp+98h+pcbBytesNeeded], eax
0x180005646  call    WPP_SF_Sd
0x18000564b  jmp     loc_180005458
```
