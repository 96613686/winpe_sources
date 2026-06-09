# shared::GetCallingAppUserModelId(void)

- ea: `0x1800420c4`
- end: `0x180042291`
- name: `?GetCallingAppUserModelId@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180041eac`

## callees

- `0x18000aec4`
- `0x18000d02c`
- `0x18000d098`
- `0x1800420c4`
- `0x180042298`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801f7974`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042208`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042286`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180042129`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180042129`

## string_xrefs

- `0x180042233`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall shared::GetCallingAppUserModelId(__int64 a1)
{
  LONG ApplicationUserModelIdFromToken; // eax
  unsigned int v3; // ebx
  HANDLE v4; // rcx
  bool v5; // cc
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  UINT32 applicationUserModelIdLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE token; // [rsp+38h] [rbp-C8h] BYREF
  __int64 CurrentThreadId; // [rsp+40h] [rbp-C0h] BYREF
  const char *v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[2]; // [rsp+98h] [rbp-68h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-58h]
  WCHAR applicationUserModelId[136]; // [rsp+C0h] [rbp-40h] BYREF

  CurrentThreadId = a1;
  shared::GetCallingTokenViaImpersonation(&token);
  memset_0(applicationUserModelId, 0, 0x104u);
  applicationUserModelIdLength = 130;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  v3 = ApplicationUserModelIdFromToken;
  if ( ApplicationUserModelIdFromToken == 15703 )
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
    if ( ApplicationUserModelIdFromToken )
    {
      if ( ApplicationUserModelIdFromToken > 0 )
        v3 = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
      v16 = ".\\platformshared.cpp";
      v17[0] = 401;
      v13 = v3;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v7,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v13,
        (unsigned int)&v16,
        (__int64)v17,
        (__int64)&CurrentThreadId);
      v8 = cdp::ExceptionStackFromSourceLocationInfo(v19, &v16);
      v11 = cdp::ErrorCodeToString(v3, v9, v10, v8);
      ConnectedDevices::Exception::Exception(pExceptionObject, v3, v11);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    std::wstring::wstring(v19, applicationUserModelId);
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
0x1800420c4  mov     [rsp-8+arg_8], rbx
0x1800420c9  mov     [rsp-8+arg_10], rdi
0x1800420ce  push    rbp
0x1800420cf  lea     rbp, [rsp-0E0h]
0x1800420d7  sub     rsp, 1E0h
0x1800420de  mov     rax, cs:__security_cookie
0x1800420e5  xor     rax, rsp
0x1800420e8  mov     [rbp+0E0h+var_10], rax
0x1800420ef  mov     rdi, rcx
0x1800420f2  mov     [rsp+1E0h+var_1A0], rcx
0x1800420f7  lea     rcx, [rsp+1E0h+token]; TokenHandle
0x1800420fc  call    ?GetCallingTokenViaImpersonation@shared@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; shared::GetCallingTokenViaImpersonation(void)
0x180042101  nop
0x180042102  xor     edx, edx; Val
0x180042104  mov     r8d, 104h; Size
0x18004210a  lea     rcx, [rbp+0E0h+applicationUserModelId]; void *
0x18004210e  call    memset_0
0x180042113  mov     [rsp+1E0h+applicationUserModelIdLength], 82h
0x18004211b  lea     r8, [rbp+0E0h+applicationUserModelId]; applicationUserModelId
0x18004211f  lea     rdx, [rsp+1E0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180042124  mov     rcx, [rsp+1E0h+token]; token
0x180042129  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18004212f  mov     ebx, eax
0x180042131  cmp     eax, 3D57h
0x180042136  jnz     short loc_18004218B
0x180042138  xorps   xmm0, xmm0
0x18004213b  movups  xmmword ptr [rdi], xmm0
0x18004213e  mov     qword ptr [rdi+10h], 0
0x180042146  mov     qword ptr [rdi+18h], 0Fh
0x18004214e  mov     byte ptr [rdi], 0
0x180042151  mov     rcx, [rsp+1E0h+token]; hObject
0x180042156  lea     rax, [rcx-1]
0x18004215a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004215e  jbe     loc_180042286
0x180042164  mov     rax, rdi
0x180042167  mov     rcx, [rbp+0E0h+var_10]
0x18004216e  xor     rcx, rsp; StackCookie
0x180042171  call    __security_check_cookie
0x180042176  lea     r11, [rsp+1E0h+var_s0]
0x18004217e  mov     rbx, [r11+18h]
0x180042182  mov     rdi, [r11+20h]
0x180042186  mov     rsp, r11
0x180042189  pop     rbp
0x18004218a  retn
0x18004218b  test    eax, eax
0x18004218d  jnz     short loc_1800421EA
0x18004218f  lea     rdx, [rbp+0E0h+applicationUserModelId]
0x180042193  lea     rcx, [rbp+0E0h+var_148]
0x180042197  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004219c  nop
0x18004219d  lea     rdx, [rbp+0E0h+var_148]
0x1800421a1  mov     rcx, rdi
0x1800421a4  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1800421a9  nop
0x1800421aa  mov     rdx, [rbp+0E0h+var_130]
0x1800421ae  cmp     rdx, 7
0x1800421b2  jbe     short loc_1800421C5
0x1800421b4  lea     rdx, ds:2[rdx*2]
0x1800421bc  mov     rcx, [rbp+0E0h+var_148]
0x1800421c0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800421c5  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800421cd  movdqu  xmmword ptr [rbp-58h], xmm0
0x1800421d2  xor     ecx, ecx
0x1800421d4  mov     word ptr [rbp+0E0h+var_148], cx
0x1800421d8  mov     rcx, [rsp+1E0h+token]
0x1800421dd  lea     rdx, [rcx-1]
0x1800421e1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800421e5  jmp     loc_18004215E
0x1800421ea  jg      loc_180042278
0x1800421f0  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x1800421f7  mov     [rsp+1E0h+var_198], rax
0x1800421fc  mov     [rsp+1E0h+var_190], 191h
0x180042204  mov     [rsp+1E0h+var_1AC], ebx
0x180042208  call    cs:__imp_GetCurrentThreadId
0x18004220e  mov     eax, eax
0x180042210  mov     [rsp+1E0h+var_1A0], rax
0x180042215  lea     rax, [rsp+1E0h+var_1A0]
0x18004221a  mov     [rsp+1E0h+var_1B8], rax
0x18004221f  lea     rax, [rsp+1E0h+var_190]
0x180042224  mov     [rsp+1E0h+var_1C0], rax
0x180042229  lea     r9, [rsp+1E0h+var_198]
0x18004222e  lea     r8, [rsp+1E0h+var_1AC]
0x180042233  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18004223a  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18004223f  lea     rdx, [rsp+1E0h+var_198]
0x180042244  lea     rcx, [rbp+0E0h+var_148]
0x180042248  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18004224d  mov     r9, rax
0x180042250  mov     ecx, ebx
0x180042252  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180042257  mov     r8, rax
0x18004225a  mov     edx, ebx
0x18004225c  lea     rcx, [rsp+1E0h+pExceptionObject]
0x180042261  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180042266  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18004226d  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x180042272  call    _CxxThrowException_0
0x180042278  movzx   ebx, ax
0x18004227b  or      ebx, 80070000h
0x180042281  jmp     loc_1800421F0
0x180042286  call    cs:__imp_CloseHandle
0x18004228c  jmp     loc_180042164
```
