# GetServiceState(ushort const *)

- ea: `0x18001e6a8`
- end: `0x18001e7bd`
- name: `?GetServiceState@@YAKPEBG@Z`
- size: `277`
- prototype: `unsigned int __fastcall(LPCWSTR lpServiceName)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b384`
- `0x18001ecd0`

## callees

- `0x180002270`
- `0x180010e9c`
- `0x180014274`
- `0x18001e6a8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e765`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e76e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e765`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e76e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e6d2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e6d2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e6f8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e6f8`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001e74b`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001e74b`

## string_xrefs

- `0x18001e6c3`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall GetServiceState(LPCWSTR lpServiceName)
{
  unsigned int v2; // ebp
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  int Error; // ebx
  SC_HANDLE v6; // rdi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-68h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v10; // [rsp+48h] [rbp-50h]
  int v11; // [rsp+58h] [rbp-40h]

  v2 = 0;
  v3 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v4 = v3;
  if ( v3 )
  {
    v6 = OpenServiceW(v3, lpServiceName, 4u);
    if ( v6 )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_11:
        CloseServiceHandle(v4);
        goto LABEL_12;
      }
    }
    if ( v6 )
    {
      v11 = 0;
      pcbBytesNeeded = 0;
      *(_OWORD *)Buffer = 0;
      v10 = 0;
      if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
        v2 = *(_DWORD *)&Buffer[4];
      else
        Error = ResultFromKnownLastError();
      CloseServiceHandle(v6);
    }
    goto LABEL_11;
  }
  Error = ResultFromKnownLastError();
LABEL_12:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_ced5302f4559327de535a40a29eb9b0f_Traceguids,
      (unsigned int)Error);
  return v2;
}

```

## disassembly

```asm
0x18001e6a8  push    rbx
0x18001e6aa  push    rbp
0x18001e6ab  push    rsi
0x18001e6ac  push    rdi
0x18001e6ad  sub     rsp, 78h
0x18001e6b1  mov     rax, cs:__security_cookie
0x18001e6b8  xor     rax, rsp
0x18001e6bb  mov     [rsp+98h+var_38], rax
0x18001e6c0  mov     rbx, rcx
0x18001e6c3  lea     rdx, DatabaseName; "ServicesActive"
0x18001e6ca  xor     ebp, ebp
0x18001e6cc  xor     ecx, ecx; lpMachineName
0x18001e6ce  lea     r8d, [rbp+1]; dwDesiredAccess
0x18001e6d2  call    cs:__imp_OpenSCManagerW
0x18001e6d8  mov     rsi, rax
0x18001e6db  test    rax, rax
0x18001e6de  jnz     short loc_18001E6EC
0x18001e6e0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e6e5  mov     ebx, eax
0x18001e6e7  jmp     loc_18001E774
0x18001e6ec  mov     r8d, 4; dwDesiredAccess
0x18001e6f2  mov     rdx, rbx; lpServiceName
0x18001e6f5  mov     rcx, rsi; hSCManager
0x18001e6f8  call    cs:__imp_OpenServiceW
0x18001e6fe  mov     rdi, rax
0x18001e701  test    rax, rax
0x18001e704  jz      short loc_18001E70A
0x18001e706  xor     ebx, ebx
0x18001e708  jmp     short loc_18001E715
0x18001e70a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e70f  mov     ebx, eax
0x18001e711  test    eax, eax
0x18001e713  js      short loc_18001E76B
0x18001e715  test    rdi, rdi
0x18001e718  jz      short loc_18001E76B
0x18001e71a  xor     eax, eax
0x18001e71c  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x18001e721  xorps   xmm0, xmm0
0x18001e724  mov     [rsp+98h+var_40], eax
0x18001e728  mov     [rsp+98h+var_68], eax
0x18001e72c  mov     r9d, 24h ; '$'; cbBufSize
0x18001e732  lea     rax, [rsp+98h+var_68]
0x18001e737  xor     edx, edx; InfoLevel
0x18001e739  mov     rcx, rdi; hService
0x18001e73c  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18001e741  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x18001e746  movups  [rsp+98h+var_50], xmm0
0x18001e74b  call    cs:__imp_QueryServiceStatusEx
0x18001e751  test    eax, eax
0x18001e753  jnz     short loc_18001E75E
0x18001e755  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e75a  mov     ebx, eax
0x18001e75c  jmp     short loc_18001E762
0x18001e75e  mov     ebp, dword ptr [rsp+98h+Buffer+4]
0x18001e762  mov     rcx, rdi; hSCObject
0x18001e765  call    cs:__imp_CloseServiceHandle
0x18001e76b  mov     rcx, rsi; hSCObject
0x18001e76e  call    cs:__imp_CloseServiceHandle
0x18001e774  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e77b  lea     rax, WPP_GLOBAL_Control
0x18001e782  cmp     rcx, rax
0x18001e785  jz      short loc_18001E7A5
0x18001e787  test    byte ptr [rcx+1Ch], 8
0x18001e78b  jz      short loc_18001E7A5
0x18001e78d  mov     rcx, [rcx+10h]
0x18001e791  lea     r8, WPP_ced5302f4559327de535a40a29eb9b0f_Traceguids
0x18001e798  mov     edx, 0Ah
0x18001e79d  mov     r9d, ebx
0x18001e7a0  call    WPP_SF_d
0x18001e7a5  mov     eax, ebp
0x18001e7a7  mov     rcx, [rsp+98h+var_38]
0x18001e7ac  xor     rcx, rsp; StackCookie
0x18001e7af  call    __security_check_cookie
0x18001e7b4  add     rsp, 78h
0x18001e7b8  pop     rdi
0x18001e7b9  pop     rsi
0x18001e7ba  pop     rbp
0x18001e7bb  pop     rbx
0x18001e7bc  retn
```
