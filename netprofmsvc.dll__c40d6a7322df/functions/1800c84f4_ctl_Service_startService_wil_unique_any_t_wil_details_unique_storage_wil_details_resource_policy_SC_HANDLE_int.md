# ctl::Service::startService(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> const &,ulong)

- ea: `0x1800c84f4`
- end: `0x1800c8609`
- name: `?startService@Service@ctl@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18008cac0`

## callees

- `0x180013748`
- `0x1800a88a0`
- `0x1800baf04`
- `0x1800c84f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8527`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c8561`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c85a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c8561`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c85a4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c85ba`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800c85ba`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800c8591`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800c8591`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800c851d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800c851d`

## string_xrefs

- `0x1800c8539`: `onecoreuap\private\net\inc\winsock2\ctl\headers\ctServiceControl.hpp`
- `0x1800c85f4`: `onecoreuap\private\net\inc\winsock2\ctl\headers\ctServiceControl.hpp`

## pseudocode

```c
bool __fastcall ctl::Service::startService(SC_HANDLE *a1)
{
  DWORD LastError; // eax
  ULONGLONG TickCount64; // rbx
  SC_HANDLE v4; // rcx
  const char *v5; // r9
  int v6; // eax
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-58h]
  DWORD v9; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v11; // [rsp+48h] [rbp-30h]
  int v12; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !StartServiceW(*a1, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 1056 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xEE,
        (unsigned int)"onecoreuap\\private\\net\\inc\\winsock2\\ctl\\headers\\ctServiceControl.hpp",
        (const char *)LastError,
        pcbBytesNeeded);
  }
  *(_OWORD *)Buffer = 0;
  v12 = 0;
  v11 = 0;
  TickCount64 = GetTickCount64();
  do
  {
    v4 = *a1;
    v9 = 0;
    if ( !QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v9) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecoreuap\\private\\net\\inc\\winsock2\\ctl\\headers\\ctServiceControl.hpp",
        v5);
    v6 = *(_DWORD *)&Buffer[4];
    if ( *(_DWORD *)&Buffer[4] != 2 )
      break;
    if ( GetTickCount64() - TickCount64 >= 0x7530 )
    {
      v6 = *(_DWORD *)&Buffer[4];
      return v6 == 4;
    }
    Sleep(0x3E8u);
    v6 = *(_DWORD *)&Buffer[4];
  }
  while ( *(_DWORD *)&Buffer[4] == 2 );
  return v6 == 4;
}

```

## disassembly

```asm
0x1800c84f4  mov     [rsp+arg_8], rbx
0x1800c84f9  mov     [rsp+arg_10], rsi
0x1800c84fe  push    rdi
0x1800c84ff  sub     rsp, 70h
0x1800c8503  mov     rax, cs:__security_cookie
0x1800c850a  xor     rax, rsp
0x1800c850d  mov     [rsp+78h+var_18], rax
0x1800c8512  mov     rsi, rcx
0x1800c8515  xor     r8d, r8d; lpServiceArgVectors
0x1800c8518  mov     rcx, [rcx]; hService
0x1800c851b  xor     edx, edx; dwNumServiceArgs
0x1800c851d  call    cs:__imp_StartServiceW
0x1800c8523  test    eax, eax
0x1800c8525  jnz     short loc_1800C854E
0x1800c8527  call    cs:__imp_GetLastError
0x1800c852d  cmp     eax, 420h
0x1800c8532  jz      short loc_1800C854E
0x1800c8534  mov     rcx, [rsp+78h]; this
0x1800c8539  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\winsock2"...
0x1800c8540  mov     r9d, eax; char *
0x1800c8543  mov     edx, 0EEh; void *
0x1800c8548  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800c854e  xorps   xmm0, xmm0
0x1800c8551  xor     eax, eax
0x1800c8553  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x1800c8558  mov     [rsp+78h+var_20], eax
0x1800c855c  movups  [rsp+78h+var_30], xmm0
0x1800c8561  call    cs:__imp_GetTickCount64
0x1800c8567  mov     rbx, rax
0x1800c856a  mov     rcx, [rsi]; hService
0x1800c856d  lea     rax, [rsp+78h+var_48]
0x1800c8572  mov     rdi, [rsp+78h]
0x1800c8577  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x1800c857c  mov     r9d, 24h ; '$'; cbBufSize
0x1800c8582  mov     qword ptr [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800c8587  xor     edx, edx; InfoLevel
0x1800c8589  mov     [rsp+78h+var_48], 0
0x1800c8591  call    cs:__imp_QueryServiceStatusEx
0x1800c8597  test    eax, eax
0x1800c8599  jz      short loc_1800C85F4
0x1800c859b  mov     eax, dword ptr [rsp+78h+Buffer+4]
0x1800c859f  cmp     eax, 2
0x1800c85a2  jnz     short loc_1800C85CF
0x1800c85a4  call    cs:__imp_GetTickCount64
0x1800c85aa  sub     rax, rbx
0x1800c85ad  cmp     rax, 7530h
0x1800c85b3  jnb     short loc_1800C85CB
0x1800c85b5  mov     ecx, 3E8h; dwMilliseconds
0x1800c85ba  call    cs:__imp_Sleep
0x1800c85c0  mov     eax, dword ptr [rsp+78h+Buffer+4]
0x1800c85c4  cmp     eax, 2
0x1800c85c7  jz      short loc_1800C856A
0x1800c85c9  jmp     short loc_1800C85CF
0x1800c85cb  mov     eax, dword ptr [rsp+78h+Buffer+4]
0x1800c85cf  cmp     eax, 4
0x1800c85d2  setz    al
0x1800c85d5  mov     rcx, [rsp+78h+var_18]
0x1800c85da  xor     rcx, rsp; StackCookie
0x1800c85dd  call    __security_check_cookie
0x1800c85e2  lea     r11, [rsp+78h+var_8]
0x1800c85e7  mov     rbx, [r11+18h]
0x1800c85eb  mov     rsi, [r11+20h]
0x1800c85ef  mov     rsp, r11
0x1800c85f2  pop     rdi
0x1800c85f3  retn
0x1800c85f4  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\winsock2"...
0x1800c85fb  mov     edx, 0FDh; void *
0x1800c8600  mov     rcx, rdi; this
0x1800c8603  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
