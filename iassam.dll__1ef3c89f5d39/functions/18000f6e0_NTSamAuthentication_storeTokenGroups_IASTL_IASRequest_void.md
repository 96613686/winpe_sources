# NTSamAuthentication::storeTokenGroups(IASTL::IASRequest &,void *)

- ea: `0x18000f6e0`
- end: `0x18000f889`
- name: `?storeTokenGroups@NTSamAuthentication@@CAXAEAVIASRequest@IASTL@@PEAX@Z`
- size: `425`
- prototype: `static void(struct IASTL::IASRequest *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f544`

## callees

- `0x180001c88`
- `0x18000a760`
- `0x18000acf4`
- `0x18000c28c`
- `0x18000c808`
- `0x18000d49c`
- `0x18000d55c`
- `0x18000f6e0`
- `0x1800254a0`
- `0x18002b4a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f72e`
- `KERNEL32!GetLastError` at `0x18000f72e`
- `ADVAPI32!GetTokenInformation` at `0x18000f726`
- `ADVAPI32!GetTokenInformation` at `0x18000f78e`
- `ADVAPI32!GetTokenInformation` at `0x18000f726`
- `ADVAPI32!GetTokenInformation` at `0x18000f78e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f756`

## string_xrefs

- `0x18000f837`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18000f826`: `GetTokenInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NTSamAuthentication::storeTokenGroups(struct IAttributesRaw **a1, void *a2)
{
  BOOL TokenInformation; // ebx
  DWORD LastError; // eax
  bool v6; // dl
  signed int v7; // edi
  void *v8; // rax
  _DWORD *v9; // rbx
  DWORD *ReturnLength; // rcx
  unsigned int v11; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-138h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-130h] BYREF
  char Buffer[256]; // [rsp+40h] [rbp-128h] BYREF

  TokenInformationLength = 0;
  TokenInformation = GetTokenInformation(a2, TokenGroups, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  v7 = LastError;
  if ( TokenInformation || LastError != 122 )
  {
    v11 = IASFormatSysErr(LastError, Buffer);
    if ( v11 < 0x100uLL )
    {
      Buffer[v11] = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
        WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"GetTokenInformation", (__int64)Buffer);
      }
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      _com_issue_error(v7);
    }
    _report_rangecheckfailure();
  }
  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&pv, v6);
  v8 = CoTaskMemAlloc(TokenInformationLength);
  v9 = pv;
  ReturnLength = (DWORD *)((char *)pv + 24);
  *((_QWORD *)pv + 4) = v8;
  if ( !v8 )
    _com_issue_error(-2147024882);
  GetTokenInformation(a2, TokenGroups, v8, TokenInformationLength, ReturnLength);
  v9[2] = 8119;
  v9[4] = 6;
  v9[1] |= 0x30000u;
  IASTL::IASAttribute::store((IASTL::IASAttribute *)&pv, a1[1]);
  IASAttributeRelease(v9);
}

```

## disassembly

```asm
0x18000f6e0  mov     [rsp+arg_10], rbx
0x18000f6e5  push    rbp
0x18000f6e6  push    rsi
0x18000f6e7  push    rdi
0x18000f6e8  sub     rsp, 150h
0x18000f6ef  mov     rax, cs:__security_cookie
0x18000f6f6  xor     rax, rsp
0x18000f6f9  mov     [rsp+168h+var_28], rax
0x18000f701  mov     rsi, rdx
0x18000f704  mov     rbp, rcx
0x18000f707  mov     [rsp+168h+TokenInformationLength], 0
0x18000f70f  lea     rax, [rsp+168h+TokenInformationLength]
0x18000f714  mov     [rsp+168h+ReturnLength], rax; ReturnLength
0x18000f719  xor     r9d, r9d; TokenInformationLength
0x18000f71c  xor     r8d, r8d; TokenInformation
0x18000f71f  lea     edx, [r9+2]; TokenInformationClass
0x18000f723  mov     rcx, rsi; TokenHandle
0x18000f726  call    cs:__imp_GetTokenInformation
0x18000f72c  mov     ebx, eax
0x18000f72e  call    cs:__imp_GetLastError
0x18000f734  mov     edi, eax
0x18000f736  test    ebx, ebx
0x18000f738  jnz     loc_18000F7E3
0x18000f73e  cmp     eax, 7Ah ; 'z'
0x18000f741  jnz     loc_18000F7E3
0x18000f747  lea     rcx, [rsp+168h+pv]; this
0x18000f74c  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x18000f751  nop
0x18000f752  mov     ecx, [rsp+168h+TokenInformationLength]; cb
0x18000f756  call    cs:__imp_CoTaskMemAlloc
0x18000f75c  mov     rbx, [rsp+168h+pv]
0x18000f761  lea     rcx, [rbx+18h]
0x18000f765  mov     [rcx+8], rax
0x18000f769  test    rax, rax
0x18000f76c  jnz     short loc_18000F779
0x18000f76e  mov     ecx, 8007000Eh; int
0x18000f773  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f779  mov     [rsp+168h+ReturnLength], rcx; ReturnLength
0x18000f77e  mov     r9d, [rsp+168h+TokenInformationLength]; TokenInformationLength
0x18000f783  mov     r8, rax; TokenInformation
0x18000f786  mov     edx, 2; TokenInformationClass
0x18000f78b  mov     rcx, rsi; TokenHandle
0x18000f78e  call    cs:__imp_GetTokenInformation
0x18000f794  mov     dword ptr [rbx+8], 1FB7h
0x18000f79b  mov     dword ptr [rbx+10h], 6
0x18000f7a2  or      dword ptr [rbx+4], 30000h
0x18000f7a9  mov     rdx, [rbp+8]; struct IAttributesRaw *
0x18000f7ad  lea     rcx, [rsp+168h+pv]; this
0x18000f7b2  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x18000f7b7  nop
0x18000f7b8  mov     rcx, rbx; pv
0x18000f7bb  call    IASAttributeRelease
0x18000f7c0  mov     rcx, [rsp+168h+var_28]
0x18000f7c8  xor     rcx, rsp; StackCookie
0x18000f7cb  call    __security_check_cookie
0x18000f7d0  mov     rbx, [rsp+168h+arg_10]
0x18000f7d8  add     rsp, 150h
0x18000f7df  pop     rdi
0x18000f7e0  pop     rsi
0x18000f7e1  pop     rbp
0x18000f7e2  retn
0x18000f7e3  lea     rdx, [rsp+168h+Buffer]; Buffer
0x18000f7e8  mov     ecx, edi; dwMessageId
0x18000f7ea  call    IASFormatSysErr
0x18000f7ef  mov     eax, eax
0x18000f7f1  cmp     rax, 100h
0x18000f7f7  jnb     loc_18000F883
0x18000f7fd  mov     [rsp+rax+168h+Buffer], 0
0x18000f802  lea     rcx, WPP_GLOBAL_Control
0x18000f809  mov     rax, cs:WPP_GLOBAL_Control
0x18000f810  cmp     rax, rcx
0x18000f813  jz      short loc_18000F86E
0x18000f815  cmp     byte ptr [rax+19h], 2
0x18000f819  jb      short loc_18000F86E
0x18000f81b  test    byte ptr [rax+1Ch], 4
0x18000f81f  jz      short loc_18000F86E
0x18000f821  lea     r9, [rsp+168h+Buffer]
0x18000f826  lea     rbx, aGettokeninform; "GetTokenInformation"
0x18000f82d  mov     r8, rbx
0x18000f830  lea     rdx, aNpssvc; "NPSSVC"
0x18000f837  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18000f83e  call    WppDbgPrint
0x18000f843  mov     edx, 11h
0x18000f848  lea     rax, [rsp+168h+Buffer]
0x18000f84d  mov     [rsp+168h+var_140], rax; __int64
0x18000f852  mov     [rsp+168h+ReturnLength], rbx; __int64
0x18000f857  lea     r8, WPP_ef5de34208083dee9ce33f3a59973eaa_Traceguids
0x18000f85e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f865  mov     rcx, [rcx+10h]; LoggerHandle
0x18000f869  call    WPP_SF_sss
0x18000f86e  test    edi, edi
0x18000f870  jle     short loc_18000F87B
0x18000f872  movzx   edi, di
0x18000f875  or      edi, 80070000h
0x18000f87b  mov     ecx, edi; int
0x18000f87d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f883  call    __report_rangecheckfailure
```
