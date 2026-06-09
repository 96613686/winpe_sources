# shared::GetCallingPackageFamilyName(void)

- ea: `0x1800ec360`
- end: `0x1800ec516`
- name: `?GetCallingPackageFamilyName@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `438`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800ec200`
- `0x18017c588`

## callees

- `0x18000aec4`
- `0x18000d02c`
- `0x18000d098`
- `0x180042298`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800ec360`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801f7974`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec424`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec424`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec4ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec4ec`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800ec3bf`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800ec3bf`

## string_xrefs

- `0x1800ec44f`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall shared::GetCallingPackageFamilyName(__int64 a1)
{
  LONG PackageFamilyNameFromToken; // eax
  unsigned int v3; // ebx
  HANDLE v4; // rcx
  bool v5; // cc
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  UINT32 packageFamilyNameLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE token; // [rsp+38h] [rbp-C8h] BYREF
  __int64 CurrentThreadId; // [rsp+40h] [rbp-C0h] BYREF
  const char *v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[2]; // [rsp+98h] [rbp-68h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-58h]
  WCHAR packageFamilyName[64]; // [rsp+C0h] [rbp-40h] BYREF

  CurrentThreadId = a1;
  shared::GetCallingTokenViaImpersonation(&token);
  memset_0(packageFamilyName, 0, sizeof(packageFamilyName));
  packageFamilyNameLength = 64;
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(token, &packageFamilyNameLength, packageFamilyName);
  v3 = PackageFamilyNameFromToken;
  if ( PackageFamilyNameFromToken == 15700 )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 15;
    *(_BYTE *)a1 = 0;
    v4 = token;
    v5 = (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
  }
  else
  {
    if ( PackageFamilyNameFromToken )
    {
      if ( PackageFamilyNameFromToken > 0 )
        v3 = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
      v16 = ".\\platformshared.cpp";
      v17[0] = 424;
      v13 = v3;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v6,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v13,
        (unsigned int)&v16,
        (__int64)v17,
        (__int64)&CurrentThreadId);
      v7 = cdp::ExceptionStackFromSourceLocationInfo(v19, &v16);
      v10 = cdp::ErrorCodeToString(v3, v8, v9, v7);
      ConnectedDevices::Exception::Exception(pExceptionObject, v3, v10);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    std::wstring::wstring(v19, packageFamilyName);
    cdp::ToUtf8(a1, v19);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v19[0], 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v19[0]) = 0;
    v4 = token;
    v5 = (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
  }
  if ( v5 )
    CloseHandle(v4);
  return a1;
}

```

## disassembly

```asm
0x1800ec360  mov     [rsp-8+arg_8], rbx
0x1800ec365  mov     [rsp-8+arg_10], rdi
0x1800ec36a  push    rbp
0x1800ec36b  lea     rbp, [rsp-50h]
0x1800ec370  sub     rsp, 150h
0x1800ec377  mov     rax, cs:__security_cookie
0x1800ec37e  xor     rax, rsp
0x1800ec381  mov     [rbp+50h+var_10], rax
0x1800ec385  mov     rdi, rcx
0x1800ec388  mov     [rsp+150h+var_110], rcx
0x1800ec38d  lea     rcx, [rsp+150h+token]; TokenHandle
0x1800ec392  call    ?GetCallingTokenViaImpersonation@shared@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; shared::GetCallingTokenViaImpersonation(void)
0x1800ec397  nop
0x1800ec398  xor     edx, edx; Val
0x1800ec39a  mov     r8d, 80h; Size
0x1800ec3a0  lea     rcx, [rbp+50h+packageFamilyName]; void *
0x1800ec3a4  call    memset_0
0x1800ec3a9  mov     [rsp+150h+packageFamilyNameLength], 40h ; '@'
0x1800ec3b1  lea     r8, [rbp+50h+packageFamilyName]; packageFamilyName
0x1800ec3b5  lea     rdx, [rsp+150h+packageFamilyNameLength]; packageFamilyNameLength
0x1800ec3ba  mov     rcx, [rsp+150h+token]; token
0x1800ec3bf  call    cs:__imp_GetPackageFamilyNameFromToken
0x1800ec3c5  mov     ebx, eax
0x1800ec3c7  cmp     eax, 3D54h
0x1800ec3cc  jnz     short loc_1800EC3F9
0x1800ec3ce  xorps   xmm0, xmm0
0x1800ec3d1  movups  xmmword ptr [rdi], xmm0
0x1800ec3d4  mov     qword ptr [rdi+10h], 0
0x1800ec3dc  mov     qword ptr [rdi+18h], 0Fh
0x1800ec3e4  mov     byte ptr [rdi], 0
0x1800ec3e7  mov     rcx, [rsp+150h+token]
0x1800ec3ec  lea     rax, [rcx-1]
0x1800ec3f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ec3f4  jmp     loc_1800EC4EA
0x1800ec3f9  test    eax, eax
0x1800ec3fb  jz      loc_1800EC494
0x1800ec401  jle     short loc_1800EC40C
0x1800ec403  movzx   ebx, ax
0x1800ec406  or      ebx, 80070000h
0x1800ec40c  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x1800ec413  mov     [rsp+150h+var_108], rax
0x1800ec418  mov     [rsp+150h+var_100], 1A8h
0x1800ec420  mov     [rsp+150h+var_11C], ebx
0x1800ec424  call    cs:__imp_GetCurrentThreadId
0x1800ec42a  mov     eax, eax
0x1800ec42c  mov     [rsp+150h+var_110], rax
0x1800ec431  lea     rax, [rsp+150h+var_110]
0x1800ec436  mov     [rsp+150h+var_128], rax
0x1800ec43b  lea     rax, [rsp+150h+var_100]
0x1800ec440  mov     [rsp+150h+var_130], rax
0x1800ec445  lea     r9, [rsp+150h+var_108]
0x1800ec44a  lea     r8, [rsp+150h+var_11C]
0x1800ec44f  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800ec456  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800ec45b  lea     rdx, [rsp+150h+var_108]
0x1800ec460  lea     rcx, [rbp+50h+var_B8]
0x1800ec464  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800ec469  mov     r9, rax
0x1800ec46c  mov     ecx, ebx
0x1800ec46e  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800ec473  mov     r8, rax
0x1800ec476  mov     edx, ebx
0x1800ec478  lea     rcx, [rsp+150h+pExceptionObject]
0x1800ec47d  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800ec482  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800ec489  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x1800ec48e  call    _CxxThrowException_0
0x1800ec494  lea     rdx, [rbp+50h+packageFamilyName]
0x1800ec498  lea     rcx, [rbp+50h+var_B8]
0x1800ec49c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec4a1  nop
0x1800ec4a2  lea     rdx, [rbp+50h+var_B8]
0x1800ec4a6  mov     rcx, rdi
0x1800ec4a9  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1800ec4ae  nop
0x1800ec4af  mov     rdx, [rbp+50h+var_A0]
0x1800ec4b3  cmp     rdx, 7
0x1800ec4b7  jbe     short loc_1800EC4CA
0x1800ec4b9  lea     rdx, ds:2[rdx*2]
0x1800ec4c1  mov     rcx, [rbp+50h+var_B8]
0x1800ec4c5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800ec4ca  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800ec4d2  movdqu  xmmword ptr [rbp-58h], xmm0
0x1800ec4d7  xor     ecx, ecx
0x1800ec4d9  mov     word ptr [rbp+50h+var_B8], cx
0x1800ec4dd  mov     rcx, [rsp+150h+token]; hObject
0x1800ec4e2  lea     rdx, [rcx-1]
0x1800ec4e6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800ec4ea  ja      short loc_1800EC4F2
0x1800ec4ec  call    cs:__imp_CloseHandle
0x1800ec4f2  mov     rax, rdi
0x1800ec4f5  mov     rcx, [rbp+50h+var_10]
0x1800ec4f9  xor     rcx, rsp; StackCookie
0x1800ec4fc  call    __security_check_cookie
0x1800ec501  lea     r11, [rsp+150h+var_s0]
0x1800ec509  mov     rbx, [r11+18h]
0x1800ec50d  mov     rdi, [r11+20h]
0x1800ec511  mov     rsp, r11
0x1800ec514  pop     rbp
0x1800ec515  retn
```
