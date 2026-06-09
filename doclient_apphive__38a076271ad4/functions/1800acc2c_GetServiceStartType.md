# _GetServiceStartType

- ea: `0x1800acc2c`
- end: `0x1800acd45`
- name: `_GetServiceStartType`
- size: `281`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800acd4c`

## callees

- `0x18000c40c`
- `0x18000c4b0`
- `0x1800a1f08`
- `0x1800acc2c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acc72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800accb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acc72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800accb8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x1800acc68`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x1800accaa`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x1800acc68`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x1800accaa`

## string_xrefs

- `0x1800accfb`: `_GetServiceStartType`

## pseudocode

```c
__int64 __fastcall GetServiceStartType(SC_HANDLE hService, DWORD *a2)
{
  LPQUERY_SERVICE_CONFIGA v5; // rsi
  unsigned int v6; // ebx
  signed int LastError; // eax
  const char *v8; // r9
  __int64 result; // rax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-38h] BYREF
  LPQUERY_SERVICE_CONFIGA lpServiceConfig[2]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v12; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a2 = 4;
  pcbBytesNeeded = 0;
  if ( !QueryServiceConfigA(hService, 0, 0, &pcbBytesNeeded) )
    GetLastError();
  try
  {
    *(_OWORD *)lpServiceConfig = 0;
    v12 = 0;
    std::vector<unsigned char>::vector<unsigned char>(lpServiceConfig, pcbBytesNeeded);
    v5 = lpServiceConfig[0];
    if ( QueryServiceConfigA(hService, lpServiceConfig[0], pcbBytesNeeded, &pcbBytesNeeded) )
    {
      v6 = 0;
      *a2 = v5->dwStartType;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v6 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v6 = LastError;
      }
      else
      {
        v6 = -2147467259;
      }
    }
    LogResult(5u, "_GetServiceStartType", 0x342u, v6, "pdwStartType = %u", *a2);
    std::vector<unsigned char>::_Tidy(lpServiceConfig);
    result = v6;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x345,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800acc2c  mov     [rsp+arg_10], rbx
0x1800acc31  mov     [rsp+arg_18], rsi
0x1800acc36  push    rdi
0x1800acc37  sub     rsp, 60h
0x1800acc3b  mov     rax, cs:__security_cookie
0x1800acc42  xor     rax, rsp
0x1800acc45  mov     [rsp+68h+var_18], rax
0x1800acc4a  mov     rdi, rdx
0x1800acc4d  mov     rbx, rcx
0x1800acc50  mov     dword ptr [rdx], 4
0x1800acc56  mov     [rsp+68h+pcbBytesNeeded], 0
0x1800acc5e  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x1800acc63  xor     r8d, r8d; cbBufSize
0x1800acc66  xor     edx, edx; lpServiceConfig
0x1800acc68  call    cs:__imp_QueryServiceConfigA
0x1800acc6e  test    eax, eax
0x1800acc70  jnz     short loc_1800ACC78
0x1800acc72  call    cs:__imp_GetLastError
0x1800acc78  xorps   xmm0, xmm0
0x1800acc7b  xor     eax, eax
0x1800acc7d  movups  xmmword ptr [rsp+68h+lpServiceConfig], xmm0
0x1800acc82  mov     [rsp+68h+var_20], rax
0x1800acc87  mov     edx, [rsp+68h+pcbBytesNeeded]
0x1800acc8b  lea     rcx, [rsp+68h+lpServiceConfig]
0x1800acc90  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800acc95  mov     rsi, [rsp+68h+lpServiceConfig]
0x1800acc9a  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x1800acc9f  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x1800acca4  mov     rdx, rsi; lpServiceConfig
0x1800acca7  mov     rcx, rbx; hService
0x1800accaa  call    cs:__imp_QueryServiceConfigA
0x1800accb0  test    eax, eax
0x1800accb2  jz      short loc_1800ACCB8
0x1800accb4  xor     ebx, ebx
0x1800accb6  jmp     short loc_1800ACCD4
0x1800accb8  call    cs:__imp_GetLastError
0x1800accbe  test    eax, eax
0x1800accc0  jz      short loc_1800ACCDB
0x1800accc2  movzx   ebx, ax
0x1800accc5  or      ebx, 80070000h
0x1800acccb  test    eax, eax
0x1800acccd  cmovle  ebx, eax
0x1800accd0  test    ebx, ebx
0x1800accd2  js      short loc_1800ACCE0
0x1800accd4  mov     eax, [rsi+4]
0x1800accd7  mov     [rdi], eax
0x1800accd9  jmp     short loc_1800ACCE0
0x1800accdb  mov     ebx, 80004005h
0x1800acce0  mov     ecx, [rdi]
0x1800acce2  mov     [rsp+68h+var_40], ecx
0x1800acce6  lea     rax, aPdwstarttypeU; "pdwStartType = %u"
0x1800acced  mov     [rsp+68h+var_48], rax; char *
0x1800accf2  mov     r9d, ebx; int
0x1800accf5  mov     r8d, 342h; unsigned int
0x1800accfb  lea     rdx, aGetservicestar; "_GetServiceStartType"
0x1800acd02  mov     ecx, 5; unsigned __int8
0x1800acd07  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800acd0c  lea     rcx, [rsp+68h+lpServiceConfig]
0x1800acd11  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800acd16  mov     eax, ebx
0x1800acd18  jmp     short loc_1800ACD25
0x1800acd1a  mov     eax, 8007000Eh
0x1800acd1f  jmp     short loc_1800ACD25
0x1800acd21  mov     eax, [rsp+68h+pcbBytesNeeded]
0x1800acd25  mov     rcx, [rsp+68h+var_18]
0x1800acd2a  xor     rcx, rsp; StackCookie
0x1800acd2d  call    __security_check_cookie
0x1800acd32  lea     r11, [rsp+68h+var_8]
0x1800acd37  mov     rbx, [r11+20h]
0x1800acd3b  mov     rsi, [r11+28h]
0x1800acd3f  mov     rsp, r11
0x1800acd42  pop     rdi
0x1800acd43  retn
```
