# IsServiceDisabled

- ea: `0x180006290`
- end: `0x1800064ef`
- name: `IsServiceDisabled`
- size: `607`
- prototype: `__int64 __fastcall(__int64, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180004340`
- `0x180007ad0`

## callees

- `0x180006290`
- `0x180010a14`
- `0x180010be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006438`
- `KERNEL32!LocalAlloc` at `0x1800063db`
- `KERNEL32!LocalAlloc` at `0x1800063db`
- `KERNEL32!LocalFree` at `0x180006479`
- `KERNEL32!LocalFree` at `0x180006479`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006487`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000649a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006487`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000649a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800062ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800062ce`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180006325`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180006325`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000637f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000642e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000637f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000642e`

## pseudocode

```c
__int64 __fastcall IsServiceDisabled(__int64 a1, bool *a2)
{
  unsigned int v3; // ebp
  SC_HANDLE v4; // rbx
  DWORD LastError; // eax
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rsi
  DWORD v8; // eax
  DWORD v9; // eax
  struct _QUERY_SERVICE_CONFIGW *v10; // rax
  struct _QUERY_SERVICE_CONFIGW *v11; // r15
  DWORD v12; // eax
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp+8h] BYREF
  int v15; // [rsp+44h] [rbp+Ch]

  v15 = HIDWORD(a1);
  pcbBytesNeeded = 0;
  if ( a2 )
  {
    v3 = 0;
    *a2 = 0;
    v4 = OpenSCManagerW(0, 0, 1u);
    if ( !v4 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
    }
    v6 = OpenServiceW(v4, L"Webclient", 1u);
    v7 = v6;
    if ( v6 )
    {
      if ( QueryServiceConfigW(v6, 0, 0, &pcbBytesNeeded) || (v9 = GetLastError(), v9 == 122) )
      {
        v10 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
        v11 = v10;
        if ( v10 )
        {
          if ( QueryServiceConfigW(v7, v10, pcbBytesNeeded, &pcbBytesNeeded) )
          {
            *a2 = v11->dwStartType == 4;
          }
          else
          {
            v12 = GetLastError();
            v3 = v12;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v12);
          }
          LocalFree(v11);
        }
        else
        {
          v3 = 8;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, 8);
        }
      }
      else
      {
        v3 = v9;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v9);
      }
      CloseServiceHandle(v7);
    }
    else
    {
      v8 = GetLastError();
      v3 = v8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v8);
    }
    if ( v4 )
      CloseServiceHandle(v4);
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x180006290  mov     qword ptr [rsp+pcbBytesNeeded], rcx
0x180006295  push    rdi
0x180006296  push    r14
0x180006298  sub     rsp, 28h
0x18000629c  mov     [rsp+38h+pcbBytesNeeded], 0
0x1800062a4  mov     rdi, rdx
0x1800062a7  test    rdx, rdx
0x1800062aa  jz      loc_1800064B4
0x1800062b0  mov     [rsp+38h+arg_8], rbx
0x1800062b5  xor     ecx, ecx; lpMachineName
0x1800062b7  mov     [rsp+38h+arg_10], rbp
0x1800062bc  mov     r8d, 1; dwDesiredAccess
0x1800062c2  xor     ebp, ebp
0x1800062c4  mov     [rsp+38h+arg_18], rsi
0x1800062c9  mov     [rdx], bpl
0x1800062cc  xor     edx, edx; lpDatabaseName
0x1800062ce  call    cs:__imp_OpenSCManagerW
0x1800062d4  lea     r14, WPP_GLOBAL_Control
0x1800062db  mov     rbx, rax
0x1800062de  test    rax, rax
0x1800062e1  jnz     short loc_180006315
0x1800062e3  call    cs:__imp_GetLastError
0x1800062e9  mov     ebp, eax
0x1800062eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062f2  cmp     rcx, r14
0x1800062f5  jz      short loc_180006315
0x1800062f7  test    byte ptr [rcx+1Ch], 1
0x1800062fb  jz      short loc_180006315
0x1800062fd  mov     rcx, [rcx+10h]
0x180006301  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180006308  mov     edx, 0Dh
0x18000630d  mov     r9d, eax
0x180006310  call    WPP_SF_d
0x180006315  mov     r8d, 1; dwDesiredAccess
0x18000631b  lea     rdx, ServiceName; "Webclient"
0x180006322  mov     rcx, rbx; hSCManager
0x180006325  call    cs:__imp_OpenServiceW
0x18000632b  mov     rsi, rax
0x18000632e  test    rax, rax
0x180006331  jnz     short loc_180006372
0x180006333  call    cs:__imp_GetLastError
0x180006339  mov     ebp, eax
0x18000633b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006342  cmp     rcx, r14
0x180006345  jz      loc_18000648D
0x18000634b  test    byte ptr [rcx+1Ch], 1
0x18000634f  jz      loc_18000648D
0x180006355  mov     rcx, [rcx+10h]
0x180006359  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180006360  mov     edx, 0Eh
0x180006365  mov     r9d, eax
0x180006368  call    WPP_SF_d
0x18000636d  jmp     loc_18000648D
0x180006372  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x180006377  xor     r8d, r8d; cbBufSize
0x18000637a  xor     edx, edx; lpServiceConfig
0x18000637c  mov     rcx, rsi; hService
0x18000637f  call    cs:__imp_QueryServiceConfigW
0x180006385  test    eax, eax
0x180006387  jnz     short loc_1800063CD
0x180006389  call    cs:__imp_GetLastError
0x18000638f  cmp     eax, 7Ah ; 'z'
0x180006392  jz      short loc_1800063CD
0x180006394  mov     ebp, eax
0x180006396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000639d  cmp     rcx, r14
0x1800063a0  jz      loc_180006484
0x1800063a6  test    byte ptr [rcx+1Ch], 1
0x1800063aa  jz      loc_180006484
0x1800063b0  mov     rcx, [rcx+10h]
0x1800063b4  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x1800063bb  mov     edx, 0Fh
0x1800063c0  mov     r9d, eax
0x1800063c3  call    WPP_SF_d
0x1800063c8  jmp     loc_180006484
0x1800063cd  mov     edx, [rsp+38h+pcbBytesNeeded]; uBytes
0x1800063d1  mov     ecx, 40h ; '@'; uFlags
0x1800063d6  mov     [rsp+38h+var_18], r15
0x1800063db  call    cs:__imp_LocalAlloc
0x1800063e1  mov     r15, rax
0x1800063e4  test    rax, rax
0x1800063e7  jnz     short loc_18000641E
0x1800063e9  mov     ebp, 8
0x1800063ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063f5  cmp     rcx, r14
0x1800063f8  jz      loc_18000647F
0x1800063fe  test    byte ptr [rcx+1Ch], 1
0x180006402  jz      short loc_18000647F
0x180006404  mov     rcx, [rcx+10h]
0x180006408  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000640f  mov     edx, 10h
0x180006414  mov     r9d, ebp
0x180006417  call    WPP_SF_d
0x18000641c  jmp     short loc_18000647F
0x18000641e  mov     r8d, [rsp+38h+pcbBytesNeeded]; cbBufSize
0x180006423  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x180006428  mov     rdx, r15; lpServiceConfig
0x18000642b  mov     rcx, rsi; hService
0x18000642e  call    cs:__imp_QueryServiceConfigW
0x180006434  test    eax, eax
0x180006436  jnz     short loc_18000646C
0x180006438  call    cs:__imp_GetLastError
0x18000643e  mov     ebp, eax
0x180006440  mov     rcx, cs:WPP_GLOBAL_Control
0x180006447  cmp     rcx, r14
0x18000644a  jz      short loc_180006476
0x18000644c  test    byte ptr [rcx+1Ch], 1
0x180006450  jz      short loc_180006476
0x180006452  mov     rcx, [rcx+10h]
0x180006456  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000645d  mov     edx, 11h
0x180006462  mov     r9d, eax
0x180006465  call    WPP_SF_d
0x18000646a  jmp     short loc_180006476
0x18000646c  cmp     dword ptr [r15+4], 4
0x180006471  setz    al
0x180006474  mov     [rdi], al
0x180006476  mov     rcx, r15; hMem
0x180006479  call    cs:__imp_LocalFree
0x18000647f  mov     r15, [rsp+38h+var_18]
0x180006484  mov     rcx, rsi; hSCObject
0x180006487  call    cs:__imp_CloseServiceHandle
0x18000648d  mov     rsi, [rsp+38h+arg_18]
0x180006492  test    rbx, rbx
0x180006495  jz      short loc_1800064A0
0x180006497  mov     rcx, rbx; hSCObject
0x18000649a  call    cs:__imp_CloseServiceHandle
0x1800064a0  mov     rbx, [rsp+38h+arg_8]
0x1800064a5  mov     eax, ebp
0x1800064a7  mov     rbp, [rsp+38h+arg_10]
0x1800064ac  add     rsp, 28h
0x1800064b0  pop     r14
0x1800064b2  pop     rdi
0x1800064b3  retn
0x1800064b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064bb  lea     r14, WPP_GLOBAL_Control
0x1800064c2  cmp     rcx, r14
0x1800064c5  jz      short loc_1800064E2
0x1800064c7  test    byte ptr [rcx+1Ch], 1
0x1800064cb  jz      short loc_1800064E2
0x1800064cd  mov     rcx, [rcx+10h]
0x1800064d1  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x1800064d8  mov     edx, 0Ch
0x1800064dd  call    WPP_SF_
0x1800064e2  mov     eax, 57h ; 'W'
0x1800064e7  add     rsp, 28h
0x1800064eb  pop     r14
0x1800064ed  pop     rdi
0x1800064ee  retn
```
