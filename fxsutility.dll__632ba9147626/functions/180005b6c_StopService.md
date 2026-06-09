# StopService

- ea: `0x180005b6c`
- end: `0x180005ea4`
- name: `StopService`
- size: `824`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180004e20`
- `0x180005b6c`

## callees

- `0x1800055a0`
- `0x18000568c`
- `0x180005838`
- `0x180005b6c`
- `0x180005eac`
- `0x180005ed4`
- `0x180005f14`
- `0x180006270`
- `0x180006318`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180005e60`
- `KERNEL32!SetLastError` at `0x180005e60`
- `KERNEL32!GetLastError` at `0x180005c96`
- `KERNEL32!GetLastError` at `0x180005d30`
- `KERNEL32!GetLastError` at `0x180005da7`
- `KERNEL32!GetLastError` at `0x180005e21`
- `KERNEL32!GetLastError` at `0x180005c96`
- `KERNEL32!GetLastError` at `0x180005d30`
- `KERNEL32!GetLastError` at `0x180005da7`
- `KERNEL32!GetLastError` at `0x180005e21`
- `ADVAPI32!ControlService` at `0x180005df8`
- `ADVAPI32!ControlService` at `0x180005df8`
- `ADVAPI32!EnumDependentServicesW` at `0x180005c88`
- `ADVAPI32!EnumDependentServicesW` at `0x180005d72`
- `ADVAPI32!EnumDependentServicesW` at `0x180005c88`
- `ADVAPI32!EnumDependentServicesW` at `0x180005d72`

## pseudocode

```c
__int64 __fastcall StopService(__int64 a1, const WCHAR *a2, int a3, unsigned int a4)
{
  unsigned int v4; // esi
  struct _ENUM_SERVICE_STATUSW *v8; // r14
  DWORD v9; // eax
  SC_HANDLE v10; // rdi
  DWORD v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rbx
  DWORD LastError; // eax
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-60h]
  DWORD cbBufSize; // [rsp+40h] [rbp-40h] BYREF
  SC_HANDLE hService; // [rsp+48h] [rbp-38h] BYREF
  SC_HANDLE hSCObject; // [rsp+50h] [rbp-30h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+58h] [rbp-28h] BYREF

  v4 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  hSCObject = 0;
  hService = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v9 = FaxOpenService(0, a2, &hSCObject, &hService, pcbBytesNeeded, 0x2Cu, &ServiceStatus.dwCurrentState);
  v10 = hService;
  if ( v9 )
    goto LABEL_40;
  if ( ServiceStatus.dwCurrentState == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_db036311db36307996a98c23702218b2_Traceguids);
    }
    goto LABEL_11;
  }
  if ( !a3 )
  {
LABEL_34:
    if ( !ControlService(v10, 1u, &ServiceStatus) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      }
      goto LABEL_41;
    }
    v9 = WaitForServiceStopOrStart(v10, 1, a4);
    if ( !v9 )
    {
LABEL_11:
      v4 = 1;
      goto LABEL_41;
    }
LABEL_40:
    SetLastError(v9);
    goto LABEL_41;
  }
  LODWORD(hService) = 0;
  cbBufSize = 0;
  if ( !EnumDependentServicesW(v10, 1u, 0, 0, &cbBufSize, (LPDWORD)&hService) )
  {
    v11 = GetLastError();
    if ( v11 != 234 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v13 = 34;
LABEL_19:
        WPP_SF_d(v12[2], v13, &WPP_db036311db36307996a98c23702218b2_Traceguids, v11);
        goto LABEL_41;
      }
      goto LABEL_41;
    }
    if ( !cbBufSize )
      goto LABEL_34;
    v8 = (struct _ENUM_SERVICE_STATUSW *)pMemAlloc(cbBufSize);
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v14 = GetLastError();
        WPP_SF_ll(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, cbBufSize, v14);
      }
      goto LABEL_41;
    }
  }
  if ( EnumDependentServicesW(v10, 1u, v8, cbBufSize, &cbBufSize, (LPDWORD)&hService) )
  {
    v17 = 0;
    if ( (_DWORD)hService )
    {
      while ( (unsigned int)StopService(0, v8[v17].lpServiceName, 0, 0xFFFFFFFFLL) )
      {
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= (unsigned int)hService )
          goto LABEL_34;
      }
      goto LABEL_41;
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v11 = GetLastError();
    v12 = WPP_GLOBAL_Control;
    v13 = 36;
    goto LABEL_19;
  }
LABEL_41:
  pMemFree(v8);
  FaxCloseService(hSCObject, v10);
  return v4;
}

```

## disassembly

```asm
0x180005b6c  mov     [rsp-28h+arg_0], rbx
0x180005b71  mov     [rsp-28h+arg_10], rsi
0x180005b76  push    rbp
0x180005b77  push    rdi
0x180005b78  push    r13
0x180005b7a  push    r14
0x180005b7c  push    r15
0x180005b7e  mov     rbp, rsp
0x180005b81  sub     rsp, 80h
0x180005b88  mov     rax, cs:__security_cookie
0x180005b8f  xor     rax, rsp
0x180005b92  mov     [rbp+var_8], rax
0x180005b96  xor     esi, esi
0x180005b98  xorps   xmm0, xmm0
0x180005b9b  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180005b9f  mov     r15d, r9d
0x180005ba2  mov     ebx, r8d
0x180005ba5  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180005ba9  mov     rdi, rdx
0x180005bac  mov     [rbp+hSCObject], rsi
0x180005bb0  mov     [rbp+hService], rsi
0x180005bb4  xor     r14d, r14d
0x180005bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bbe  lea     rax, WPP_GLOBAL_Control
0x180005bc5  cmp     rcx, rax
0x180005bc8  jz      short loc_180005BE9
0x180005bca  test    byte ptr [rcx+1Ch], 2
0x180005bce  jz      short loc_180005BE9
0x180005bd0  cmp     byte ptr [rcx+19h], 5
0x180005bd4  jb      short loc_180005BE9
0x180005bd6  mov     rcx, [rcx+10h]
0x180005bda  lea     edx, [rsi+20h]
0x180005bdd  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180005be4  call    WPP_SF_
0x180005be9  lea     rax, [rbp+ServiceStatus.dwCurrentState]
0x180005bed  mov     rdx, rdi; lpServiceName
0x180005bf0  mov     [rsp+80h+var_50], rax; unsigned int *
0x180005bf5  lea     r9, [rbp+hService]; struct SC_HANDLE__ **
0x180005bf9  lea     r8, [rbp+hSCObject]; struct SC_HANDLE__ **
0x180005bfd  mov     dword ptr [rsp+80h+lpServicesReturned], 2Ch ; ','; unsigned int
0x180005c05  xor     ecx, ecx; lpMachineName
0x180005c07  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x180005c0c  mov     rdi, [rbp+hService]
0x180005c10  test    eax, eax
0x180005c12  jnz     loc_180005E5E
0x180005c18  lea     r13d, [rax+1]
0x180005c1c  cmp     [rbp+ServiceStatus.dwCurrentState], r13d
0x180005c20  jnz     short loc_180005C5C
0x180005c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c29  lea     rdx, WPP_GLOBAL_Control
0x180005c30  cmp     rcx, rdx
0x180005c33  jz      short loc_180005C54
0x180005c35  test    byte ptr [rcx+1Ch], 2
0x180005c39  jz      short loc_180005C54
0x180005c3b  cmp     byte ptr [rcx+19h], 5
0x180005c3f  jb      short loc_180005C54
0x180005c41  mov     rcx, [rcx+10h]
0x180005c45  lea     edx, [rax+21h]
0x180005c48  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180005c4f  call    WPP_SF_
0x180005c54  mov     esi, r13d
0x180005c57  jmp     loc_180005E66
0x180005c5c  test    ebx, ebx
0x180005c5e  jz      loc_180005DEE
0x180005c64  lea     rax, [rbp+hService]
0x180005c68  mov     dword ptr [rbp+hService], esi
0x180005c6b  mov     [rsp+80h+lpServicesReturned], rax; lpServicesReturned
0x180005c70  xor     r9d, r9d; cbBufSize
0x180005c73  lea     rax, [rbp+cbBufSize]
0x180005c77  mov     [rbp+cbBufSize], esi
0x180005c7a  xor     r8d, r8d; lpServices
0x180005c7d  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180005c82  mov     edx, r13d; dwServiceState
0x180005c85  mov     rcx, rdi; hService
0x180005c88  call    cs:__imp_EnumDependentServicesW
0x180005c8e  test    eax, eax
0x180005c90  jnz     loc_180005D53
0x180005c96  call    cs:__imp_GetLastError
0x180005c9c  cmp     eax, 0EAh
0x180005ca1  jz      short loc_180005CEB
0x180005ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005caa  lea     rdx, WPP_GLOBAL_Control
0x180005cb1  cmp     rcx, rdx
0x180005cb4  jz      loc_180005E66
0x180005cba  test    byte ptr [rcx+1Ch], 2
0x180005cbe  jz      loc_180005E66
0x180005cc4  cmp     byte ptr [rcx+19h], 5
0x180005cc8  jb      loc_180005E66
0x180005cce  mov     edx, 22h ; '"'
0x180005cd3  mov     rcx, [rcx+10h]
0x180005cd7  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180005cde  mov     r9d, eax
0x180005ce1  call    WPP_SF_d
0x180005ce6  jmp     loc_180005E66
0x180005ceb  mov     eax, [rbp+cbBufSize]
0x180005cee  test    eax, eax
0x180005cf0  jz      loc_180005DEE
0x180005cf6  mov     ecx, eax; dwBytes
0x180005cf8  call    pMemAlloc
0x180005cfd  mov     r14, rax
0x180005d00  test    rax, rax
0x180005d03  jnz     short loc_180005D53
0x180005d05  mov     rax, cs:WPP_GLOBAL_Control
0x180005d0c  lea     rdx, WPP_GLOBAL_Control
0x180005d13  cmp     rax, rdx
0x180005d16  jz      loc_180005E66
0x180005d1c  test    byte ptr [rax+1Ch], 2
0x180005d20  jz      loc_180005E66
0x180005d26  cmp     byte ptr [rax+19h], 5
0x180005d2a  jb      loc_180005E66
0x180005d30  call    cs:__imp_GetLastError
0x180005d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d3d  mov     r9d, [rbp+cbBufSize]
0x180005d41  mov     dword ptr [rsp+80h+pcbBytesNeeded], eax
0x180005d45  mov     rcx, [rcx+10h]
0x180005d49  call    WPP_SF_ll
0x180005d4e  jmp     loc_180005E66
0x180005d53  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x180005d57  lea     rax, [rbp+hService]
0x180005d5b  mov     [rsp+80h+lpServicesReturned], rax; lpServicesReturned
0x180005d60  mov     r8, r14; lpServices
0x180005d63  lea     rax, [rbp+cbBufSize]
0x180005d67  mov     edx, r13d; dwServiceState
0x180005d6a  mov     rcx, rdi; hService
0x180005d6d  mov     [rsp+80h+pcbBytesNeeded], rax; unsigned int
0x180005d72  call    cs:__imp_EnumDependentServicesW
0x180005d78  test    eax, eax
0x180005d7a  jnz     short loc_180005DBE
0x180005d7c  mov     rax, cs:WPP_GLOBAL_Control
0x180005d83  lea     rdx, WPP_GLOBAL_Control
0x180005d8a  cmp     rax, rdx
0x180005d8d  jz      loc_180005E66
0x180005d93  test    byte ptr [rax+1Ch], 2
0x180005d97  jz      loc_180005E66
0x180005d9d  cmp     byte ptr [rax+19h], 5
0x180005da1  jb      loc_180005E66
0x180005da7  call    cs:__imp_GetLastError
0x180005dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180005db4  mov     edx, 24h ; '$'
0x180005db9  jmp     loc_180005CD3
0x180005dbe  xor     ebx, ebx
0x180005dc0  cmp     dword ptr [rbp+hService], ebx
0x180005dc3  jbe     short loc_180005DEE
0x180005dc5  lea     rdx, [rbx+rbx*2]
0x180005dc9  or      r9d, 0FFFFFFFFh
0x180005dcd  add     rdx, rdx
0x180005dd0  xor     r8d, r8d
0x180005dd3  xor     ecx, ecx
0x180005dd5  mov     rdx, [r14+rdx*8]
0x180005dd9  call    StopService
0x180005dde  test    eax, eax
0x180005de0  jz      loc_180005E66
0x180005de6  add     ebx, r13d
0x180005de9  cmp     ebx, dword ptr [rbp+hService]
0x180005dec  jb      short loc_180005DC5
0x180005dee  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x180005df2  mov     edx, r13d; dwControl
0x180005df5  mov     rcx, rdi; hService
0x180005df8  call    cs:__imp_ControlService
0x180005dfe  test    eax, eax
0x180005e00  jnz     short loc_180005E48
0x180005e02  mov     rax, cs:WPP_GLOBAL_Control
0x180005e09  lea     rdx, WPP_GLOBAL_Control
0x180005e10  cmp     rax, rdx
0x180005e13  jz      short loc_180005E66
0x180005e15  test    byte ptr [rax+1Ch], 2
0x180005e19  jz      short loc_180005E66
0x180005e1b  cmp     byte ptr [rax+19h], 2
0x180005e1f  jb      short loc_180005E66
0x180005e21  call    cs:__imp_GetLastError
0x180005e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e2e  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180005e35  mov     edx, 25h ; '%'
0x180005e3a  mov     r9d, eax
0x180005e3d  mov     rcx, [rcx+10h]
0x180005e41  call    WPP_SF_d
0x180005e46  jmp     short loc_180005E66
0x180005e48  mov     r8d, r15d; unsigned int
0x180005e4b  mov     edx, r13d; int
0x180005e4e  mov     rcx, rdi; hService
0x180005e51  call    ?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z; WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)
0x180005e56  test    eax, eax
0x180005e58  jz      loc_180005C54
0x180005e5e  mov     ecx, eax; dwErrCode
0x180005e60  call    cs:__imp_SetLastError
0x180005e66  mov     rcx, r14; lpMem
0x180005e69  call    pMemFree
0x180005e6e  mov     rcx, [rbp+hSCObject]; hSCObject
0x180005e72  mov     rdx, rdi; SC_HANDLE
0x180005e75  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x180005e7a  mov     eax, esi
0x180005e7c  mov     rcx, [rbp+var_8]
0x180005e80  xor     rcx, rsp; StackCookie
0x180005e83  call    __security_check_cookie
0x180005e88  lea     r11, [rsp+80h+var_s0]
0x180005e90  mov     rbx, [r11+30h]
0x180005e94  mov     rsi, [r11+40h]
0x180005e98  mov     rsp, r11
0x180005e9b  pop     r15
0x180005e9d  pop     r14
0x180005e9f  pop     r13
0x180005ea1  pop     rdi
0x180005ea2  pop     rbp
0x180005ea3  retn
```
