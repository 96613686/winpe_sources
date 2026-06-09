# StartZtHelperServiceOnDemand

- ea: `0x18008a138`
- end: `0x18008a33f`
- name: `StartZtHelperServiceOnDemand`
- size: `519`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180089f04`
- `0x18008a348`

## callees

- `0x1800861c8`
- `0x18008a138`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800e05ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a2f6`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18008a240`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18008a240`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008a2ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008a2dd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008a2ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18008a2dd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008a177`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008a177`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008a1cb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18008a1cb`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18008a285`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18008a285`

## pseudocode

```c
__int64 StartZtHelperServiceOnDemand()
{
  int v0; // esi
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbp
  DWORD v3; // ebx
  SC_HANDLE v4; // rdi
  DWORD LastError; // eax
  __int64 v6; // rcx
  DWORD v7; // eax

  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 17, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids);
  v0 = 1;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v4 = OpenServiceW(v1, L"ZTHELPER", 0x15u);
    if ( !v4 )
    {
      GetLastError();
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_(1035, 19, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids);
    }
    if ( (unsigned int)isServiceDisabled(v4) )
    {
      v3 = 1062;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_d(1035, 20, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids, 1062);
    }
    else
    {
      if ( !StartServiceW(v4, 0, 0) && (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(1035, 21, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids, LastError);
      }
      v0 = WaitServiceState(v4, 9, 2000);
      if ( v0 == 4 )
      {
        v3 = 0;
      }
      else
      {
        v3 = 1053;
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_lll(v6, 22, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids);
      }
    }
    if ( v4 )
      CloseServiceHandle(v4);
    CloseServiceHandle(v2);
    if ( !v0 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        return v3;
      v7 = GetLastError();
      WPP_SF_d(1035, 23, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids, v7);
    }
  }
  else
  {
    v3 = GetLastError();
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      return v3;
    WPP_SF_(1035, 18, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids);
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 24, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18008a138  push    rbx
0x18008a13a  push    rbp
0x18008a13b  push    rsi
0x18008a13c  push    rdi
0x18008a13d  push    r12
0x18008a13f  push    r15
0x18008a141  sub     rsp, 38h
0x18008a145  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008a14c  lea     r15, WPP_3b635760ae653fb307183583a3ac8b3b_Traceguids
0x18008a153  mov     r12d, 40Bh
0x18008a159  jz      short loc_18008A16B
0x18008a15b  mov     edx, 11h
0x18008a160  mov     ecx, r12d
0x18008a163  mov     r8, r15
0x18008a166  call    WPP_SF_
0x18008a16b  mov     esi, 1
0x18008a170  xor     edx, edx; lpDatabaseName
0x18008a172  mov     r8d, esi; dwDesiredAccess
0x18008a175  xor     ecx, ecx; lpMachineName
0x18008a177  call    cs:__imp_OpenSCManagerW
0x18008a17e  nop     dword ptr [rax+rax+00h]
0x18008a183  mov     rbp, rax
0x18008a186  test    rax, rax
0x18008a189  jnz     short loc_18008A1B9
0x18008a18b  call    cs:__imp_GetLastError
0x18008a192  nop     dword ptr [rax+rax+00h]
0x18008a197  mov     ebx, eax
0x18008a199  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008a1a0  jz      loc_18008A32F
0x18008a1a6  lea     edx, [rsi+11h]
0x18008a1a9  mov     ecx, r12d
0x18008a1ac  mov     r8, r15
0x18008a1af  call    WPP_SF_
0x18008a1b4  jmp     loc_18008A313
0x18008a1b9  mov     ebx, 15h
0x18008a1be  lea     rdx, aZthelper_0; "ZTHELPER"
0x18008a1c5  mov     r8d, ebx; dwDesiredAccess
0x18008a1c8  mov     rcx, rbp; hSCManager
0x18008a1cb  call    cs:__imp_OpenServiceW
0x18008a1d2  nop     dword ptr [rax+rax+00h]
0x18008a1d7  mov     rdi, rax
0x18008a1da  test    rax, rax
0x18008a1dd  jnz     short loc_18008A202
0x18008a1df  call    cs:__imp_GetLastError
0x18008a1e6  nop     dword ptr [rax+rax+00h]
0x18008a1eb  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008a1f2  jz      short loc_18008A202
0x18008a1f4  lea     edx, [rbx-2]
0x18008a1f7  mov     ecx, r12d
0x18008a1fa  mov     r8, r15
0x18008a1fd  call    WPP_SF_
0x18008a202  mov     rcx, rdi; hService
0x18008a205  call    isServiceDisabled
0x18008a20a  test    eax, eax
0x18008a20c  jz      short loc_18008A238
0x18008a20e  mov     ebx, 426h
0x18008a213  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008a21a  jz      loc_18008A2C6
0x18008a220  mov     edx, 14h
0x18008a225  mov     ecx, r12d
0x18008a228  mov     r9d, ebx
0x18008a22b  mov     r8, r15
0x18008a22e  call    WPP_SF_d
0x18008a233  jmp     loc_18008A2C6
0x18008a238  xor     r8d, r8d; lpServiceArgVectors
0x18008a23b  xor     edx, edx; dwNumServiceArgs
0x18008a23d  mov     rcx, rdi; hService
0x18008a240  call    cs:__imp_StartServiceW
0x18008a247  nop     dword ptr [rax+rax+00h]
0x18008a24c  test    eax, eax
0x18008a24e  jnz     short loc_18008A275
0x18008a250  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008a257  jz      short loc_18008A275
0x18008a259  call    cs:__imp_GetLastError
0x18008a260  nop     dword ptr [rax+rax+00h]
0x18008a265  mov     edx, ebx
0x18008a267  mov     ecx, r12d
0x18008a26a  mov     r9d, eax
0x18008a26d  mov     r8, r15
0x18008a270  call    WPP_SF_d
0x18008a275  xor     r9d, r9d
0x18008a278  mov     r8d, 7D0h
0x18008a27e  mov     rcx, rdi
0x18008a281  lea     edx, [r9+9]
0x18008a285  call    cs:__imp_WaitServiceState
0x18008a28c  nop     dword ptr [rax+rax+00h]
0x18008a291  mov     esi, eax
0x18008a293  cmp     eax, 4
0x18008a296  jnz     short loc_18008A29C
0x18008a298  xor     ebx, ebx
0x18008a29a  jmp     short loc_18008A2C6
0x18008a29c  mov     ebx, 41Dh
0x18008a2a1  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008a2a8  jz      short loc_18008A2C6
0x18008a2aa  mov     edx, 16h
0x18008a2af  mov     [rsp+68h+var_40], 4
0x18008a2b7  mov     r9d, ebx
0x18008a2ba  mov     [rsp+68h+var_48], eax
0x18008a2be  mov     r8, r15
0x18008a2c1  call    WPP_SF_lll
0x18008a2c6  test    rdi, rdi
0x18008a2c9  jz      short loc_18008A2DA
0x18008a2cb  mov     rcx, rdi; hSCObject
0x18008a2ce  call    cs:__imp_CloseServiceHandle
0x18008a2d5  nop     dword ptr [rax+rax+00h]
0x18008a2da  mov     rcx, rbp; hSCObject
0x18008a2dd  call    cs:__imp_CloseServiceHandle
0x18008a2e4  nop     dword ptr [rax+rax+00h]
0x18008a2e9  test    esi, esi
0x18008a2eb  jnz     short loc_18008A313
0x18008a2ed  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008a2f4  jz      short loc_18008A32F
0x18008a2f6  call    cs:__imp_GetLastError
0x18008a2fd  nop     dword ptr [rax+rax+00h]
0x18008a302  lea     edx, [rsi+17h]
0x18008a305  mov     ecx, r12d
0x18008a308  mov     r9d, eax
0x18008a30b  mov     r8, r15
0x18008a30e  call    WPP_SF_d
0x18008a313  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008a31a  jz      short loc_18008A32F
0x18008a31c  mov     edx, 18h
0x18008a321  mov     ecx, r12d
0x18008a324  mov     r9d, ebx
0x18008a327  mov     r8, r15
0x18008a32a  call    WPP_SF_d
0x18008a32f  mov     eax, ebx
0x18008a331  add     rsp, 38h
0x18008a335  pop     r15
0x18008a337  pop     r12
0x18008a339  pop     rdi
0x18008a33a  pop     rsi
0x18008a33b  pop     rbp
0x18008a33c  pop     rbx
0x18008a33d  retn
```
