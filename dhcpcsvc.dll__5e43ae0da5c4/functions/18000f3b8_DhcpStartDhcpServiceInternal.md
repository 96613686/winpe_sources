# DhcpStartDhcpServiceInternal

- ea: `0x18000f3b8`
- end: `0x18000f4e5`
- name: `DhcpStartDhcpServiceInternal`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180006790`
- `0x1800068b0`

## callees

- `0x18000c2c4`
- `0x18000f3b8`
- `0x180012628`
- `0x18001268c`
- `0x180012a00`
- `0x180012b80`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000f452`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000f452`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000f43a`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000f48a`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000f43a`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000f48a`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000f448`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000f448`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000f412`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000f412`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000f3e8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000f3e8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f4b6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f4bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f4b6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000f4bf`

## pseudocode

```c
__int64 DhcpStartDhcpServiceInternal()
{
  unsigned int v0; // edi
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbp
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int LastErrorOrUnknown; // ebx
  __int64 v6; // r8
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rsi
  DWORD LastError; // eax
  __int64 v10; // rcx

  v0 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 14, WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids);
  v1 = OpenSCManagerW(0, 0, 0x15u);
  v2 = v1;
  if ( v1 )
  {
    v7 = OpenServiceW(v1, L"DHCP", 0x14u);
    v8 = v7;
    if ( v7 )
    {
      WaitServiceState(v7, 3, 100);
      if ( !StartServiceW(v8, 0, 0) )
      {
        LastError = GetLastError();
        if ( (xmmword_18001E1E0 & 2) != 0 )
          WPP_SF_d(1025, 15, WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids, LastError);
      }
      if ( (unsigned int)WaitServiceState(v8, 9, 1000) == 4 )
      {
        LastErrorOrUnknown = 0;
        v0 = 1;
      }
      else
      {
        LastErrorOrUnknown = 1053;
        if ( (xmmword_18001E1E0 & 2) != 0 )
          WPP_SF_Ddd(v10);
      }
      CloseServiceHandle(v8);
    }
    else
    {
      LastErrorOrUnknown = GetLastErrorOrUnknown();
    }
    CloseServiceHandle(v2);
  }
  else
  {
    LastErrorOrUnknown = GetLastErrorOrUnknown();
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Dl(v4, v3, v6, LastErrorOrUnknown, v0);
  return v0;
}

```

## disassembly

```asm
0x18000f3b8  push    rbx
0x18000f3ba  push    rbp
0x18000f3bb  push    rsi
0x18000f3bc  push    rdi
0x18000f3bd  sub     rsp, 38h
0x18000f3c1  xor     edi, edi
0x18000f3c3  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f3ca  jz      short loc_18000F3E0
0x18000f3cc  lea     edx, [rdi+0Eh]
0x18000f3cf  mov     ecx, 404h
0x18000f3d4  lea     r8, WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids
0x18000f3db  call    WPP_SF_
0x18000f3e0  xor     edx, edx; lpDatabaseName
0x18000f3e2  xor     ecx, ecx; lpMachineName
0x18000f3e4  lea     r8d, [rdx+15h]; dwDesiredAccess
0x18000f3e8  call    cs:__imp_OpenSCManagerW
0x18000f3ee  mov     rbp, rax
0x18000f3f1  test    rax, rax
0x18000f3f4  jnz     short loc_18000F402
0x18000f3f6  call    GetLastErrorOrUnknown
0x18000f3fb  mov     ebx, eax
0x18000f3fd  jmp     loc_18000F4C5
0x18000f402  mov     r8d, 14h; dwDesiredAccess
0x18000f408  lea     rdx, ServiceName; "DHCP"
0x18000f40f  mov     rcx, rbp; hSCManager
0x18000f412  call    cs:__imp_OpenServiceW
0x18000f418  mov     rsi, rax
0x18000f41b  test    rax, rax
0x18000f41e  jnz     short loc_18000F42C
0x18000f420  call    GetLastErrorOrUnknown
0x18000f425  mov     ebx, eax
0x18000f427  jmp     loc_18000F4BC
0x18000f42c  xor     r9d, r9d
0x18000f42f  mov     rcx, rsi
0x18000f432  lea     edx, [r9+3]
0x18000f436  lea     r8d, [r9+64h]
0x18000f43a  call    cs:__imp_WaitServiceState
0x18000f440  xor     r8d, r8d; lpServiceArgVectors
0x18000f443  xor     edx, edx; dwNumServiceArgs
0x18000f445  mov     rcx, rsi; hService
0x18000f448  call    cs:__imp_StartServiceW
0x18000f44e  test    eax, eax
0x18000f450  jnz     short loc_18000F47A
0x18000f452  call    cs:__imp_GetLastError
0x18000f458  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000f45f  jz      short loc_18000F47A
0x18000f461  mov     edx, 0Fh
0x18000f466  lea     r8, WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids
0x18000f46d  mov     ecx, 401h
0x18000f472  mov     r9d, eax
0x18000f475  call    WPP_SF_d
0x18000f47a  xor     r9d, r9d
0x18000f47d  mov     r8d, 3E8h
0x18000f483  mov     rcx, rsi
0x18000f486  lea     edx, [r9+9]
0x18000f48a  call    cs:__imp_WaitServiceState
0x18000f490  cmp     eax, 4
0x18000f493  jnz     short loc_18000F49C
0x18000f495  xor     ebx, ebx
0x18000f497  lea     edi, [rax-3]
0x18000f49a  jmp     short loc_18000F4B3
0x18000f49c  mov     ebx, 41Dh
0x18000f4a1  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000f4a8  jz      short loc_18000F4B3
0x18000f4aa  mov     [rsp+58h+var_38], eax
0x18000f4ae  call    WPP_SF_Ddd
0x18000f4b3  mov     rcx, rsi; hSCObject
0x18000f4b6  call    cs:__imp_CloseServiceHandle
0x18000f4bc  mov     rcx, rbp; hSCObject
0x18000f4bf  call    cs:__imp_CloseServiceHandle
0x18000f4c5  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f4cc  jz      short loc_18000F4DA
0x18000f4ce  mov     r9d, ebx
0x18000f4d1  mov     [rsp+58h+var_38], edi
0x18000f4d5  call    WPP_SF_Dl
0x18000f4da  mov     eax, edi
0x18000f4dc  add     rsp, 38h
0x18000f4e0  pop     rdi
0x18000f4e1  pop     rsi
0x18000f4e2  pop     rbp
0x18000f4e3  pop     rbx
0x18000f4e4  retn
```
