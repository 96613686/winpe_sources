# StartDnsServiceOnDemand

- ea: `0x18006cf08`
- end: `0x18006d13c`
- name: `StartDnsServiceOnDemand`
- size: `564`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180013658`
- `0x180014b5c`
- `0x1800893bc`
- `0x1800937b0`

## callees

- `0x18006cf08`
- `0x1800861c8`
- `0x18008b5f0`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800e05ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cf69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cf69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d089`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18006cfe2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18006cfe2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006d01c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006d02b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006d01c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006d02b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18006cf55`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18006cf55`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18006cfb0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18006cfb0`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18006d002`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18006d002`

## string_xrefs

- `0x18006cfa6`: `dnsCache`

## pseudocode

```c
__int64 StartDnsServiceOnDemand()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  DWORD v2; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  __int64 v6; // rcx
  DWORD LastError; // eax
  LPCWSTR ServiceArgVectors; // [rsp+30h] [rbp-38h] BYREF

  ServiceArgVectors = L"DemandStart";
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 10, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids);
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"dnsCache", 0x15u);
    v5 = v4;
    if ( v4 )
    {
      if ( (unsigned int)isServiceDisabled(v4) )
      {
        v2 = 1062;
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 13, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids, 1062);
      }
      else
      {
        if ( !StartServiceW(v5, 1u, &ServiceArgVectors) && (BYTE1(xmmword_1801119E0) & 8) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(1035, 14, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids, LastError);
        }
        if ( (unsigned int)WaitServiceState(v5, 9, 2000) == 4 )
        {
          v2 = 0;
        }
        else
        {
          v2 = 1053;
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_lll(v6, 15, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids);
        }
      }
      CloseServiceHandle(v5);
    }
    else
    {
      v2 = GetLastError();
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_(1035, 12, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids);
    }
    CloseServiceHandle(v1);
  }
  else
  {
    v2 = GetLastError();
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      return v2;
    WPP_SF_(1035, 11, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids);
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 16, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18006cf08  push    rbx
0x18006cf0a  push    rsi
0x18006cf0b  push    rdi
0x18006cf0c  push    r14
0x18006cf0e  push    r15
0x18006cf10  sub     rsp, 40h
0x18006cf14  mov     rax, cs:__security_cookie
0x18006cf1b  xor     rax, rsp
0x18006cf1e  mov     [rsp+68h+var_30], rax
0x18006cf23  lea     rax, aDemandstart; "DemandStart"
0x18006cf2a  mov     [rsp+68h+ServiceArgVectors], rax
0x18006cf2f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006cf36  lea     r14, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids
0x18006cf3d  mov     r15d, 40Bh
0x18006cf43  jnz     loc_18006D0B5
0x18006cf49  mov     ebx, 1
0x18006cf4e  xor     edx, edx; lpDatabaseName
0x18006cf50  mov     r8d, ebx; dwDesiredAccess
0x18006cf53  xor     ecx, ecx; lpMachineName
0x18006cf55  call    cs:__imp_OpenSCManagerW
0x18006cf5c  nop     dword ptr [rax+rax+00h]
0x18006cf61  mov     rsi, rax
0x18006cf64  test    rax, rax
0x18006cf67  jnz     short loc_18006CFA0
0x18006cf69  call    cs:__imp_GetLastError
0x18006cf70  nop     dword ptr [rax+rax+00h]
0x18006cf75  mov     ebx, eax
0x18006cf77  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006cf7e  jnz     loc_18006D0CA
0x18006cf84  mov     eax, ebx
0x18006cf86  mov     rcx, [rsp+68h+var_30]
0x18006cf8b  xor     rcx, rsp; StackCookie
0x18006cf8e  call    __security_check_cookie
0x18006cf93  add     rsp, 40h
0x18006cf97  pop     r15
0x18006cf99  pop     r14
0x18006cf9b  pop     rdi
0x18006cf9c  pop     rsi
0x18006cf9d  pop     rbx
0x18006cf9e  retn
0x18006cfa0  mov     r8d, 15h; dwDesiredAccess
0x18006cfa6  lea     rdx, ServiceName; "dnsCache"
0x18006cfad  mov     rcx, rsi; hSCManager
0x18006cfb0  call    cs:__imp_OpenServiceW
0x18006cfb7  nop     dword ptr [rax+rax+00h]
0x18006cfbc  mov     rdi, rax
0x18006cfbf  test    rax, rax
0x18006cfc2  jz      loc_18006D089
0x18006cfc8  mov     rcx, rax; hService
0x18006cfcb  call    isServiceDisabled
0x18006cfd0  test    eax, eax
0x18006cfd2  jnz     loc_18006D0DF
0x18006cfd8  lea     r8, [rsp+68h+ServiceArgVectors]; lpServiceArgVectors
0x18006cfdd  mov     edx, ebx; dwNumServiceArgs
0x18006cfdf  mov     rcx, rdi; hService
0x18006cfe2  call    cs:__imp_StartServiceW
0x18006cfe9  nop     dword ptr [rax+rax+00h]
0x18006cfee  test    eax, eax
0x18006cff0  jz      short loc_18006D05C
0x18006cff2  xor     r9d, r9d
0x18006cff5  mov     r8d, 7D0h
0x18006cffb  mov     rcx, rdi
0x18006cffe  lea     edx, [r9+9]
0x18006d002  call    cs:__imp_WaitServiceState
0x18006d009  nop     dword ptr [rax+rax+00h]
0x18006d00e  cmp     eax, 4
0x18006d011  jnz     loc_18006D109
0x18006d017  xor     ebx, ebx
0x18006d019  mov     rcx, rdi; hSCObject
0x18006d01c  call    cs:__imp_CloseServiceHandle
0x18006d023  nop     dword ptr [rax+rax+00h]
0x18006d028  mov     rcx, rsi; hSCObject
0x18006d02b  call    cs:__imp_CloseServiceHandle
0x18006d032  nop     dword ptr [rax+rax+00h]
0x18006d037  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d03e  jz      loc_18006CF84
0x18006d044  mov     edx, 10h
0x18006d049  mov     ecx, r15d
0x18006d04c  mov     r9d, ebx
0x18006d04f  mov     r8, r14
0x18006d052  call    WPP_SF_d
0x18006d057  jmp     loc_18006CF84
0x18006d05c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d063  jz      short loc_18006CFF2
0x18006d065  call    cs:__imp_GetLastError
0x18006d06c  nop     dword ptr [rax+rax+00h]
0x18006d071  mov     edx, 0Eh
0x18006d076  mov     ecx, r15d
0x18006d079  mov     r9d, eax
0x18006d07c  mov     r8, r14
0x18006d07f  call    WPP_SF_d
0x18006d084  jmp     loc_18006CFF2
0x18006d089  call    cs:__imp_GetLastError
0x18006d090  nop     dword ptr [rax+rax+00h]
0x18006d095  mov     ebx, eax
0x18006d097  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d09e  jz      short loc_18006D028
0x18006d0a0  mov     edx, 0Ch
0x18006d0a5  mov     ecx, r15d
0x18006d0a8  mov     r8, r14
0x18006d0ab  call    WPP_SF_
0x18006d0b0  jmp     loc_18006D028
0x18006d0b5  mov     edx, 0Ah
0x18006d0ba  mov     ecx, r15d
0x18006d0bd  mov     r8, r14
0x18006d0c0  call    WPP_SF_
0x18006d0c5  jmp     loc_18006CF49
0x18006d0ca  mov     edx, 0Bh
0x18006d0cf  mov     ecx, r15d
0x18006d0d2  mov     r8, r14
0x18006d0d5  call    WPP_SF_
0x18006d0da  jmp     loc_18006D037
0x18006d0df  mov     ebx, 426h
0x18006d0e4  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d0eb  jz      loc_18006D019
0x18006d0f1  mov     edx, 0Dh
0x18006d0f6  mov     ecx, r15d
0x18006d0f9  mov     r9d, ebx
0x18006d0fc  mov     r8, r14
0x18006d0ff  call    WPP_SF_d
0x18006d104  jmp     loc_18006D019
0x18006d109  mov     ebx, 41Dh
0x18006d10e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006d115  jz      loc_18006D019
0x18006d11b  mov     edx, 0Fh
0x18006d120  mov     [rsp+68h+var_40], 4
0x18006d128  mov     r9d, ebx
0x18006d12b  mov     [rsp+68h+var_48], eax
0x18006d12f  mov     r8, r14
0x18006d132  call    WPP_SF_lll
0x18006d137  jmp     loc_18006D019
```
