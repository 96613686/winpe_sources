# OOBEServiceHelper::_WaitForServiceState(ushort const *,SC_HANDLE__ *,ulong)

- ea: `0x180019ce8`
- end: `0x180019f35`
- name: `?_WaitForServiceState@OOBEServiceHelper@@CAJPEBGPEAUSC_HANDLE__@@K@Z`
- size: `589`
- prototype: `static int(const unsigned __int16 *, struct SC_HANDLE__ *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800196f0`

## callees

- `0x180003470`
- `0x18000ac48`
- `0x180019c7c`
- `0x180019ce8`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019de1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019de1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019d8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e32`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019d8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e32`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180019d45`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180019dff`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180019d45`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180019dff`

## string_xrefs

- `0x180019d7e`: `Beginning wait for service %ls (initial state %ls, desired state %ls)`
- `0x180019e61`: `QueryServiceStatusEx failed [0x%08X]`
- `0x180019efe`: `QueryServiceStatusEx failed [0x%08X]`
- `0x180019ee5`: `Service %ls successfully reports in state %ls`
- `0x180019ea9`: `Service %ls is not in state %ls after waiting %d milliseconds (final state is %ls)`
- `0x180019ecd`: `Service entered state other than %ls (dwCurrentState == [%ls])`

## pseudocode

```c
__int64 __fastcall OOBEServiceHelper::_WaitForServiceState(const unsigned __int16 *a1, SC_HANDLE a2, unsigned int a3)
{
  int v6; // ebx
  int Error; // eax
  const unsigned __int16 *v8; // rsi
  const unsigned __int16 *v9; // rax
  DWORD TickCount; // eax
  unsigned int v11; // r15d
  DWORD v12; // r12d
  unsigned int v13; // ecx
  DWORD v14; // edx
  int v15; // eax
  DWORD v16; // eax
  const unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // rax
  LPDWORD pcbBytesNeeded; // [rsp+20h] [rbp-50h]
  DWORD v21; // [rsp+30h] [rbp-40h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v23; // [rsp+48h] [rbp-28h]
  int v24; // [rsp+58h] [rbp-18h]

  v21 = 0;
  v24 = 0;
  *(_OWORD *)Buffer = 0;
  v23 = 0;
  if ( QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v21) )
  {
    v6 = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    v6 = Error;
    if ( Error < 0 )
    {
      UnattendLogW(1, L"QueryServiceStatusEx failed [0x%08X]", (unsigned int)Error);
      return (unsigned int)v6;
    }
  }
  v8 = OOBEServiceHelper::_ServiceStateToString(a3);
  v9 = OOBEServiceHelper::_ServiceStateToString(*(unsigned int *)&Buffer[4]);
  UnattendLogW(0, L"Beginning wait for service %ls (initial state %ls, desired state %ls)", a1, v9, v8);
  TickCount = GetTickCount();
  v11 = DWORD1(v23);
  v12 = TickCount;
  while ( 1 )
  {
    v13 = *(_DWORD *)&Buffer[4];
    if ( *(_DWORD *)&Buffer[4] == a3 )
      goto LABEL_30;
    if ( *(_DWORD *)&Buffer[4] == 4 && a3 == 2 )
      goto LABEL_23;
    v14 = DWORD2(v23) / 0xA;
    if ( DWORD2(v23) / 0xA >= 0x1F4 )
    {
      if ( v14 > 0x2710 )
        v14 = 10000;
    }
    else
    {
      v14 = 500;
    }
    Sleep(v14);
    if ( !QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v21) )
      break;
    v6 = 0;
LABEL_15:
    if ( DWORD1(v23) <= v11 )
    {
      if ( GetTickCount() - v12 > DWORD2(v23) + 10000 )
        v6 = -2147023843;
    }
    else
    {
      v16 = GetTickCount();
      v11 = DWORD1(v23);
      v12 = v16;
    }
    if ( v6 < 0 )
      goto LABEL_22;
  }
  v15 = ResultFromKnownLastError();
  v6 = v15;
  if ( v15 >= 0 )
    goto LABEL_15;
  UnattendLogW(1, L"QueryServiceStatusEx failed [0x%08X]", (unsigned int)v15);
LABEL_22:
  v13 = *(_DWORD *)&Buffer[4];
LABEL_23:
  if ( v13 == a3 || v13 == 4 && a3 == 2 )
  {
LABEL_30:
    v6 = 0;
    UnattendLogW(0, L"Service %ls successfully reports in state %ls", a1, v8);
    return (unsigned int)v6;
  }
  if ( v6 == -2147023843 )
  {
    v17 = OOBEServiceHelper::_ServiceStateToString(v13);
    LODWORD(pcbBytesNeeded) = DWORD2(v23) + 10000;
    UnattendLogW(
      2,
      L"Service %ls is not in state %ls after waiting %d milliseconds (final state is %ls)",
      a1,
      v8,
      pcbBytesNeeded,
      v17);
  }
  else if ( v6 >= 0 )
  {
    v6 = -2147467259;
    v18 = OOBEServiceHelper::_ServiceStateToString(v13);
    UnattendLogW(2, L"Service entered state other than %ls (dwCurrentState == [%ls])", v8, v18);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019ce8  mov     [rsp-38h+arg_18], rbx
0x180019ced  push    rbp
0x180019cee  push    rsi
0x180019cef  push    rdi
0x180019cf0  push    r12
0x180019cf2  push    r13
0x180019cf4  push    r14
0x180019cf6  push    r15
0x180019cf8  mov     rbp, rsp
0x180019cfb  sub     rsp, 70h
0x180019cff  mov     rax, cs:__security_cookie
0x180019d06  xor     rax, rsp
0x180019d09  mov     [rbp+var_10], rax
0x180019d0d  xor     eax, eax
0x180019d0f  mov     [rbp+var_40], 0
0x180019d16  mov     r13, rdx
0x180019d19  mov     [rbp+var_18], eax
0x180019d1c  xorps   xmm0, xmm0
0x180019d1f  lea     rax, [rbp+var_40]
0x180019d23  mov     edi, r8d
0x180019d26  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180019d2b  mov     r14, rcx
0x180019d2e  lea     r8, [rbp+Buffer]; lpBuffer
0x180019d32  mov     r9d, 24h ; '$'; cbBufSize
0x180019d38  xor     edx, edx; InfoLevel
0x180019d3a  mov     rcx, r13; hService
0x180019d3d  movups  xmmword ptr [rbp+Buffer], xmm0
0x180019d41  movups  [rbp+var_28], xmm0
0x180019d45  call    cs:__imp_QueryServiceStatusEx
0x180019d4b  test    eax, eax
0x180019d4d  jz      short loc_180019D53
0x180019d4f  xor     ebx, ebx
0x180019d51  jmp     short loc_180019D62
0x180019d53  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180019d58  mov     ebx, eax
0x180019d5a  test    eax, eax
0x180019d5c  js      loc_180019EFB
0x180019d62  mov     ecx, edi; unsigned int
0x180019d64  call    ?_ServiceStateToString@OOBEServiceHelper@@CAPEBGK@Z; OOBEServiceHelper::_ServiceStateToString(ulong)
0x180019d69  mov     ecx, dword ptr [rbp+Buffer+4]; unsigned int
0x180019d6c  mov     rsi, rax
0x180019d6f  call    ?_ServiceStateToString@OOBEServiceHelper@@CAPEBGK@Z; OOBEServiceHelper::_ServiceStateToString(ulong)
0x180019d74  mov     r9, rax
0x180019d77  mov     [rsp+70h+pcbBytesNeeded], rsi
0x180019d7c  xor     ecx, ecx
0x180019d7e  lea     rdx, aBeginningWaitF; "Beginning wait for service %ls (initial"...
0x180019d85  mov     r8, r14
0x180019d88  call    UnattendLogW
0x180019d8d  call    cs:__imp_GetTickCount
0x180019d93  mov     r15d, dword ptr [rbp+var_28+4]
0x180019d97  mov     r8d, 2710h
0x180019d9d  mov     r12d, eax
0x180019da0  mov     eax, 8007041Dh
0x180019da5  mov     ecx, dword ptr [rbp+Buffer+4]
0x180019da8  cmp     ecx, edi
0x180019daa  jz      loc_180019EE3
0x180019db0  cmp     ecx, 4
0x180019db3  jnz     short loc_180019DBE
0x180019db5  cmp     edi, 2
0x180019db8  jz      loc_180019E7A
0x180019dbe  mov     eax, 0CCCCCCCDh
0x180019dc3  mul     dword ptr [rbp+var_28+8]
0x180019dc6  shr     edx, 3
0x180019dc9  cmp     edx, 1F4h
0x180019dcf  jnb     short loc_180019DD8
0x180019dd1  mov     edx, 1F4h
0x180019dd6  jmp     short loc_180019DDF
0x180019dd8  cmp     edx, r8d
0x180019ddb  cmova   edx, r8d
0x180019ddf  mov     ecx, edx; dwMilliseconds
0x180019de1  call    cs:__imp_Sleep
0x180019de7  lea     rax, [rbp+var_40]
0x180019deb  mov     r9d, 24h ; '$'; cbBufSize
0x180019df1  lea     r8, [rbp+Buffer]; lpBuffer
0x180019df5  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180019dfa  xor     edx, edx; InfoLevel
0x180019dfc  mov     rcx, r13; hService
0x180019dff  call    cs:__imp_QueryServiceStatusEx
0x180019e05  test    eax, eax
0x180019e07  jz      short loc_180019E0D
0x180019e09  xor     ebx, ebx
0x180019e0b  jmp     short loc_180019E18
0x180019e0d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180019e12  mov     ebx, eax
0x180019e14  test    eax, eax
0x180019e16  js      short loc_180019E5E
0x180019e18  cmp     dword ptr [rbp+var_28+4], r15d
0x180019e1c  jbe     short loc_180019E32
0x180019e1e  call    cs:__imp_GetTickCount
0x180019e24  mov     r15d, dword ptr [rbp+var_28+4]
0x180019e28  mov     r12d, eax
0x180019e2b  mov     eax, 8007041Dh
0x180019e30  jmp     short loc_180019E4E
0x180019e32  call    cs:__imp_GetTickCount
0x180019e38  mov     ecx, dword ptr [rbp+var_28+8]
0x180019e3b  sub     eax, r12d
0x180019e3e  add     ecx, 2710h
0x180019e44  cmp     eax, ecx
0x180019e46  mov     eax, 8007041Dh
0x180019e4b  cmova   ebx, eax
0x180019e4e  mov     r8d, 2710h
0x180019e54  test    ebx, ebx
0x180019e56  jns     loc_180019DA5
0x180019e5c  jmp     short loc_180019E77
0x180019e5e  mov     r8d, eax
0x180019e61  lea     rdx, aQueryservicest; "QueryServiceStatusEx failed [0x%08X]"
0x180019e68  mov     ecx, 1
0x180019e6d  call    UnattendLogW
0x180019e72  mov     eax, 8007041Dh
0x180019e77  mov     ecx, dword ptr [rbp+Buffer+4]; unsigned int
0x180019e7a  cmp     ecx, edi
0x180019e7c  jz      short loc_180019EE3
0x180019e7e  cmp     ecx, 4
0x180019e81  jnz     short loc_180019E88
0x180019e83  cmp     edi, 2
0x180019e86  jz      short loc_180019EE3
0x180019e88  cmp     ebx, eax
0x180019e8a  jnz     short loc_180019EBC
0x180019e8c  call    ?_ServiceStateToString@OOBEServiceHelper@@CAPEBGK@Z; OOBEServiceHelper::_ServiceStateToString(ulong)
0x180019e91  mov     edx, dword ptr [rbp+var_28+8]
0x180019e94  mov     r9, rsi
0x180019e97  add     edx, 2710h
0x180019e9d  mov     [rsp+70h+var_48], rax
0x180019ea2  mov     dword ptr [rsp+70h+pcbBytesNeeded], edx
0x180019ea6  mov     r8, r14
0x180019ea9  lea     rdx, aServiceLsIsNot; "Service %ls is not in state %ls after w"...
0x180019eb0  mov     ecx, 2
0x180019eb5  call    UnattendLogW
0x180019eba  jmp     short loc_180019F0F
0x180019ebc  test    ebx, ebx
0x180019ebe  js      short loc_180019F0F
0x180019ec0  mov     ebx, 80004005h
0x180019ec5  call    ?_ServiceStateToString@OOBEServiceHelper@@CAPEBGK@Z; OOBEServiceHelper::_ServiceStateToString(ulong)
0x180019eca  mov     r9, rax
0x180019ecd  lea     rdx, aServiceEntered; "Service entered state other than %ls (d"...
0x180019ed4  mov     ecx, 2
0x180019ed9  mov     r8, rsi
0x180019edc  call    UnattendLogW
0x180019ee1  jmp     short loc_180019F0F
0x180019ee3  xor     ebx, ebx
0x180019ee5  lea     rdx, aServiceLsSucce; "Service %ls successfully reports in sta"...
0x180019eec  mov     r9, rsi
0x180019eef  mov     r8, r14
0x180019ef2  xor     ecx, ecx
0x180019ef4  call    UnattendLogW
0x180019ef9  jmp     short loc_180019F0F
0x180019efb  mov     r8d, eax
0x180019efe  lea     rdx, aQueryservicest; "QueryServiceStatusEx failed [0x%08X]"
0x180019f05  mov     ecx, 1
0x180019f0a  call    UnattendLogW
0x180019f0f  mov     eax, ebx
0x180019f11  mov     rcx, [rbp+var_10]
0x180019f15  xor     rcx, rsp; StackCookie
0x180019f18  call    __security_check_cookie
0x180019f1d  mov     rbx, [rsp+70h+arg_18]
0x180019f25  add     rsp, 70h
0x180019f29  pop     r15
0x180019f2b  pop     r14
0x180019f2d  pop     r13
0x180019f2f  pop     r12
0x180019f31  pop     rdi
0x180019f32  pop     rsi
0x180019f33  pop     rbp
0x180019f34  retn
```
