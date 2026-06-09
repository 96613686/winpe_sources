# GetPackageSidFromToken(void *,void * *)

- ea: `0x180051420`
- end: `0x18005155d`
- name: `?GetPackageSidFromToken@@YAJPEAXPEAPEAX@Z`
- size: `317`
- prototype: `HRESULT __fastcall(void *hToken, void **ppPackageSid)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005174c`
- `0x18013c024`
- `0x1801dcf2c`

## callees

- `0x180051420`
- `0x18008db2c`
- `0x1801457c0`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051508`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051508`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180051522`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180051522`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800514f4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800514f4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005147a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005147a`

## string_xrefs

- `0x1800514c2`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x1800514b4`: `GetPackageSidFromToken`

## pseudocode

```c
__int64 __fastcall GetPackageSidFromToken(void *hToken, void **ppPackageSid)
{
  DWORD LastError; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  DWORD LengthSid; // edi
  void *v8; // rax
  unsigned int dwPackageInfoSize[4]; // [rsp+30h] [rbp-78h] BYREF
  PSID packageInformation[10]; // [rsp+40h] [rbp-68h] BYREF

  dwPackageInfoSize[0] = 76;
  memset_0(packageInformation, 0, 0x4Cu);
  if ( GetTokenInformation(hToken, TokenAppContainerSid, packageInformation, 0x4Cu, dwPackageInfoSize) )
  {
    if ( packageInformation[0] )
    {
      LengthSid = GetLengthSid(packageInformation[0]);
      v8 = HeapAlloc(g_hHeap, 0, LengthSid);
      *ppPackageSid = v8;
      if ( v8 )
      {
        v6 = 0;
        CopySid(LengthSid, v8, packageInformation[0]);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147023728;
    }
  }
  else
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      LastError = GetLastError();
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\processtoken\\processtoken.cxx",
        "GetPackageSidFromToken",
        229,
        ERRORS,
        L"%!WINERROR!",
        LastError);
    }
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x180051420  mov     [rsp+arg_10], rbx
0x180051425  mov     [rsp+arg_18], rsi
0x18005142a  push    rdi
0x18005142b  sub     rsp, 0A0h
0x180051432  mov     rax, cs:__security_cookie
0x180051439  xor     rax, rsp
0x18005143c  mov     [rsp+0A8h+var_18], rax
0x180051444  mov     edi, 4Ch ; 'L'
0x180051449  mov     rsi, ppPackageSid
0x18005144c  mov     rbx, hToken
0x18005144f  mov     [rsp+0A8h+dwPackageInfoSize], edi
0x180051453  mov     r8d, edi; Size
0x180051456  lea     hToken, [rsp+0A8h+packageInformation]; void *
0x18005145b  xor     edx, edx; Val
0x18005145d  call    memset_0
0x180051462  lea     rax, [rsp+0A8h+dwPackageInfoSize]
0x180051467  mov     r9d, edi; TokenInformationLength
0x18005146a  lea     r8, [rsp+0A8h+packageInformation]; TokenInformation
0x18005146f  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x180051474  lea     edx, [rdi-2Dh]; TokenInformationClass
0x180051477  mov     hToken, rbx; TokenHandle
0x18005147a  call    cs:__imp_GetTokenInformation
0x180051480  test    eax, eax
0x180051482  jnz     short loc_1800514EA
0x180051484  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18005148a  test    eax, eax
0x18005148c  jnz     short loc_1800514A1
0x18005148e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180051494  jz      short loc_1800514D3
0x180051496  xor     ecx, ecx; level
0x180051498  call    IsWppLevelEnabled
0x18005149d  test    al, al
0x18005149f  jz      short loc_1800514D3
0x1800514a1  call    cs:__imp_GetLastError
0x1800514a7  mov     [rsp+0A8h+var_80], eax; <args_0>
0x1800514ab  xor     r9d, r9d; level
0x1800514ae  mov     r8d, 0E5h; line
0x1800514b4  lea     ppPackageSid, aGetpackagesidf; "GetPackageSidFromToken"
0x1800514bb  lea     rax, aWinerror; "%!WINERROR!"
0x1800514c2  lea     hToken, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x1800514c9  mov     [rsp+0A8h+ReturnLength], rax; format
0x1800514ce  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x1800514d3  call    cs:__imp_GetLastError
0x1800514d9  mov     ebx, eax
0x1800514db  test    eax, eax
0x1800514dd  jle     short loc_180051536
0x1800514df  movzx   ebx, ax
0x1800514e2  or      ebx, 80070000h
0x1800514e8  jmp     short loc_180051536
0x1800514ea  mov     hToken, [rsp+0A8h+packageInformation]; pSid
0x1800514ef  test    hToken, hToken
0x1800514f2  jz      short loc_180051531
0x1800514f4  call    cs:__imp_GetLengthSid
0x1800514fa  mov     hToken, cs:?g_hHeap@@3QEAXEA; hHeap
0x180051501  xor     edx, edx; dwFlags
0x180051503  mov     r8d, eax; dwBytes
0x180051506  mov     edi, eax
0x180051508  call    cs:__imp_HeapAlloc
0x18005150e  mov     [rsi], rax
0x180051511  test    rax, rax
0x180051514  jz      short loc_18005152A
0x180051516  mov     r8, [rsp+0A8h+packageInformation]; pSourceSid
0x18005151b  xor     ebx, ebx
0x18005151d  mov     ppPackageSid, rax; pDestinationSid
0x180051520  mov     ecx, edi; nDestinationSidLength
0x180051522  call    cs:__imp_CopySid
0x180051528  jmp     short loc_180051536
0x18005152a  mov     ebx, 8007000Eh
0x18005152f  jmp     short loc_180051536
0x180051531  mov     ebx, 80070490h
0x180051536  mov     eax, ebx
0x180051538  mov     hToken, [rsp+0A8h+var_18]
0x180051540  xor     hToken, rsp; StackCookie
0x180051543  call    __security_check_cookie
0x180051548  lea     r11, [rsp+0A8h+var_8]
0x180051550  mov     rbx, [r11+20h]
0x180051554  mov     rsi, [r11+28h]
0x180051558  mov     rsp, r11
0x18005155b  pop     rdi
0x18005155c  retn
```
