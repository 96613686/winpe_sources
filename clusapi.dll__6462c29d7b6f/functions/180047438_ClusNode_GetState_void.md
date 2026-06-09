# ClusNode::GetState(void)

- ea: `0x180047438`
- end: `0x1800474f6`
- name: `?GetState@ClusNode@@QEAAKXZ`
- size: `190`
- prototype: `unsigned int __fastcall(ClusNode *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18003f638`

## callees

- `0x180002f50`
- `0x180028f30`
- `0x180047438`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047488`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800474d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800474d4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18004747e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18004747e`

## string_xrefs

- `0x1800474a7`: `QueryServiceStatus failed for the clussvc on node %ws`

## pseudocode

```c
__int64 __fastcall ClusNode::GetState(ClusNode *this)
{
  SC_HANDLE v2; // rcx
  DWORD LastError; // ebx
  __int64 v4; // rax
  DWORD dwWin32ExitCode; // ecx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  ServiceStatus.dwServiceType = 0;
  v2 = (SC_HANDLE)*((_QWORD *)this + 16);
  ServiceStatus.dwCurrentState = 1;
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  if ( QueryServiceStatus(v2, &ServiceStatus) )
  {
    if ( ServiceStatus.dwCurrentState == 1 )
      dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
    else
      dwWin32ExitCode = 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 48);
    TraceMsg(3u, 0, (__int64)L"ClusNode::GetState", 515, L"QueryServiceStatus failed for the clussvc on node %ws", v4);
    dwWin32ExitCode = LastError;
  }
  SetLastError(dwWin32ExitCode);
  return ServiceStatus.dwCurrentState;
}

```

## disassembly

```asm
0x180047438  mov     [rsp+arg_8], rbx
0x18004743d  push    rdi
0x18004743e  sub     rsp, 60h
0x180047442  mov     rax, cs:__security_cookie
0x180047449  xor     rax, rsp
0x18004744c  mov     [rsp+68h+var_18], rax
0x180047451  mov     rdi, rcx
0x180047454  mov     [rsp+68h+ServiceStatus.dwServiceType], 0
0x18004745c  mov     rcx, [rcx+80h]; hService
0x180047463  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180047468  xorps   xmm0, xmm0
0x18004746b  mov     [rsp+68h+ServiceStatus.dwCurrentState], 1
0x180047473  xor     eax, eax
0x180047475  movups  xmmword ptr [rsp+68h+ServiceStatus.dwControlsAccepted], xmm0
0x18004747a  mov     [rsp+68h+ServiceStatus.dwWaitHint], eax
0x18004747e  call    cs:__imp_QueryServiceStatus
0x180047484  test    eax, eax
0x180047486  jnz     short loc_1800474C5
0x180047488  call    cs:__imp_GetLastError
0x18004748e  lea     rcx, [rdi+30h]
0x180047492  mov     ebx, eax
0x180047494  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180047499  mov     [rsp+68h+var_40], rax
0x18004749e  lea     r8, aClusnodeGetsta; "ClusNode::GetState"
0x1800474a5  xor     edx, edx
0x1800474a7  lea     rax, aQueryservicest_0; "QueryServiceStatus failed for the cluss"...
0x1800474ae  mov     r9d, 203h
0x1800474b4  mov     [rsp+68h+var_48], rax
0x1800474b9  lea     ecx, [rdx+3]
0x1800474bc  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800474c1  mov     ecx, ebx
0x1800474c3  jmp     short loc_1800474D4
0x1800474c5  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 1
0x1800474ca  jnz     short loc_1800474D2
0x1800474cc  mov     ecx, [rsp+68h+ServiceStatus.dwWin32ExitCode]
0x1800474d0  jmp     short loc_1800474D4
0x1800474d2  xor     ecx, ecx; dwErrCode
0x1800474d4  call    cs:__imp_SetLastError
0x1800474da  mov     eax, [rsp+68h+ServiceStatus.dwCurrentState]
0x1800474de  mov     rcx, [rsp+68h+var_18]
0x1800474e3  xor     rcx, rsp; StackCookie
0x1800474e6  call    __security_check_cookie
0x1800474eb  mov     rbx, [rsp+68h+arg_8]
0x1800474f0  add     rsp, 60h
0x1800474f4  pop     rdi
0x1800474f5  retn
```
