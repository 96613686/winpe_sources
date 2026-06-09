# cdp::GetUserServiceMutexCheck(unsigned __int64)

- ea: `0x180097608`
- end: `0x18009781b`
- name: `?GetUserServiceMutexCheck@cdp@@YA?AVUserServiceMutexCheck@1@_K@Z`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x1802bc6d4`

## callees

- `0x180006800`
- `0x18000d02c`
- `0x18000d098`
- `0x1800624cc`
- `0x18009714c`
- `0x180097608`
- `0x180114ab4`
- `0x18011d8c4`
- `0x18018703c`
- `0x18018c1a4`
- `0x1801f6fb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800977f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800977f1`
- `ntdll!RtlFreeUnicodeString` at `0x1800977dc`
- `ntdll!RtlFreeUnicodeString` at `0x1800977dc`
- `ntdll!RtlGetTokenNamedObjectPath` at `0x1800976c0`
- `ntdll!RtlGetTokenNamedObjectPath` at `0x1800976c0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18009766b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18009766b`

## string_xrefs

- `0x180097675`: `.\userservicenotificationclient.cpp`
- `0x1800976d1`: `.\userservicenotificationclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void *__fastcall cdp::GetUserServiceMutexCheck(void *a1, __int64 a2)
{
  WCHAR *v3; // rax
  int v4; // eax
  __int64 v5; // rax
  unsigned int TokenNamedObjectPath; // eax
  int v7; // edx
  int v8; // eax
  __int64 v9; // rax
  WCHAR *RelativeUserServiceMutexName; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  __m128i si128; // xmm0
  HANDLE hObject; // [rsp+20h] [rbp-79h] BYREF
  const char *v17; // [rsp+28h] [rbp-71h] BYREF
  int v18; // [rsp+30h] [rbp-69h]
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-61h] BYREF
  WCHAR v20[28]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v21; // [rsp+88h] [rbp-11h] BYREF
  __m128i v22; // [rsp+98h] [rbp-1h]
  __int64 v23; // [rsp+A8h] [rbp+Fh] BYREF
  __m128i v24; // [rsp+B8h] [rbp+1Fh]
  WCHAR v25[8]; // [rsp+C8h] [rbp+2Fh] BYREF
  __m128i v26; // [rsp+D8h] [rbp+3Fh]

  hObject = a1;
  if ( a2 )
  {
    hObject = 0;
    v4 = UMgrQueryUserToken(a2, &hObject);
    if ( v4 < 0 )
    {
      v17 = ".\\userservicenotificationclient.cpp";
      v18 = 142;
      v5 = cdp::MakeException<cdp::hresult_exception>(v20, &v17, (unsigned int)v4);
      cdp::CdpThrow<cdp::hresult_exception>(&v17, v5);
    }
    *(_QWORD *)&UnicodeString.Length = 0;
    UnicodeString.Buffer = 0;
    TokenNamedObjectPath = RtlGetTokenNamedObjectPath(hObject, 0, &UnicodeString);
    v8 = wil::details::NtStatusToHr((wil::details *)TokenNamedObjectPath, v7);
    if ( v8 < 0 )
    {
      v17 = ".\\userservicenotificationclient.cpp";
      v18 = 151;
      v9 = cdp::MakeException<cdp::hresult_exception>(v20, &v17, (unsigned int)v8);
      cdp::CdpThrow<cdp::hresult_exception>(&v17, v9);
    }
    RelativeUserServiceMutexName = cdp::GetRelativeUserServiceMutexName(v25, hObject);
    v11 = std::wstring::wstring(&v23, UnicodeString.Buffer);
    v12 = std::operator+<unsigned short>(&v21, v11);
    std::wstring::wstring(v20, v13, v12, RelativeUserServiceMutexName);
    cdp::UserServiceMutexCheck::UserServiceMutexCheck(a1, v20, 1);
    if ( v22.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v21, 2 * v22.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v22 = si128;
    LOWORD(v21) = 0;
    if ( v24.m128i_i64[1] > 7uLL )
    {
      std::_Deallocate<16>(v23, 2 * v24.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v24 = si128;
    LOWORD(v23) = 0;
    if ( v26.m128i_i64[1] > 7uLL )
    {
      std::_Deallocate<16>(*(_QWORD *)v25, 2 * v26.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v26 = si128;
    v25[0] = 0;
    RtlFreeUnicodeString(&UnicodeString);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
  else
  {
    v3 = cdp::GetRelativeUserServiceMutexName(v20, (void *)0xFFFFFFFFFFFFFFFCLL);
    cdp::UserServiceMutexCheck::UserServiceMutexCheck(a1, v3, 0);
  }
  return a1;
}

```

## disassembly

```asm
0x180097608  mov     [rsp-8+arg_10], rbx
0x18009760d  mov     [rsp-8+arg_18], rdi
0x180097612  push    rbp
0x180097613  lea     rbp, [rsp-57h]
0x180097618  sub     rsp, 0F0h
0x18009761f  mov     rax, cs:__security_cookie
0x180097626  xor     rax, rsp
0x180097629  mov     [rbp+57h+var_8], rax
0x18009762d  mov     rax, rdx
0x180097630  mov     rdi, rcx
0x180097633  mov     [rbp+57h+hObject], rcx
0x180097637  test    rdx, rdx
0x18009763a  jnz     short loc_18009765C
0x18009763c  lea     rdx, [rax-4]
0x180097640  lea     rcx, [rbp+57h+var_A0]
0x180097644  call    ?GetRelativeUserServiceMutexName@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; cdp::GetRelativeUserServiceMutexName(void *)
0x180097649  xor     r8d, r8d
0x18009764c  mov     rdx, rax
0x18009764f  mov     rcx, rdi
0x180097652  call    ??0UserServiceMutexCheck@cdp@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UserServiceMutexCheckType@1@@Z; cdp::UserServiceMutexCheck::UserServiceMutexCheck(std::wstring,cdp::UserServiceMutexCheckType)
0x180097657  jmp     loc_1800977F7
0x18009765c  mov     [rbp+57h+hObject], 0
0x180097664  lea     rdx, [rbp+57h+hObject]
0x180097668  mov     rcx, rax
0x18009766b  call    cs:__imp_UMgrQueryUserToken
0x180097671  test    eax, eax
0x180097673  jns     short loc_1800976A5
0x180097675  lea     rcx, aUserservicenot; ".\\userservicenotificationclient.cpp"
0x18009767c  mov     [rbp+57h+var_C8], rcx
0x180097680  mov     [rbp+57h+var_C0], 8Eh
0x180097687  mov     r8d, eax
0x18009768a  lea     rdx, [rbp+57h+var_C8]
0x18009768e  lea     rcx, [rbp+57h+var_A0]
0x180097692  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x180097697  nop
0x180097698  mov     rdx, rax
0x18009769b  lea     rcx, [rbp+57h+var_C8]
0x18009769f  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800976a5  xorps   xmm0, xmm0
0x1800976a8  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1800976ac  xor     eax, eax
0x1800976ae  mov     [rbp+57h+UnicodeString.MaximumLength], ax
0x1800976b2  mov     [rbp+57h+UnicodeString.Buffer], rax
0x1800976b6  lea     r8, [rbp+57h+UnicodeString]
0x1800976ba  xor     edx, edx
0x1800976bc  mov     rcx, [rbp+57h+hObject]
0x1800976c0  call    cs:__imp_RtlGetTokenNamedObjectPath
0x1800976c6  mov     ecx, eax; this
0x1800976c8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800976cd  test    eax, eax
0x1800976cf  jns     short loc_180097701
0x1800976d1  lea     rcx, aUserservicenot; ".\\userservicenotificationclient.cpp"
0x1800976d8  mov     [rbp+57h+var_C8], rcx
0x1800976dc  mov     [rbp+57h+var_C0], 97h
0x1800976e3  mov     r8d, eax
0x1800976e6  lea     rdx, [rbp+57h+var_C8]
0x1800976ea  lea     rcx, [rbp+57h+var_A0]
0x1800976ee  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800976f3  nop
0x1800976f4  mov     rdx, rax
0x1800976f7  lea     rcx, [rbp+57h+var_C8]
0x1800976fb  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180097701  mov     rdx, [rbp+57h+hObject]
0x180097705  lea     rcx, [rbp+57h+var_28]
0x180097709  call    ?GetRelativeUserServiceMutexName@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; cdp::GetRelativeUserServiceMutexName(void *)
0x18009770e  mov     rbx, rax
0x180097711  mov     rdx, [rbp+57h+UnicodeString.Buffer]
0x180097715  lea     rcx, [rbp+57h+var_48]
0x180097719  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009771e  nop
0x18009771f  mov     rdx, rax
0x180097722  lea     rcx, [rbp+57h+var_68]
0x180097726  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@G@Z; std::operator+<ushort>(std::wstring &&,ushort)
0x18009772b  nop
0x18009772c  mov     r9, rbx
0x18009772f  mov     r8, rax
0x180097732  lea     rcx, [rbp+57h+var_A0]
0x180097736  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x18009773b  mov     r8d, 1
0x180097741  lea     rdx, [rbp+57h+var_A0]
0x180097745  mov     rcx, rdi
0x180097748  call    ??0UserServiceMutexCheck@cdp@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UserServiceMutexCheckType@1@@Z; cdp::UserServiceMutexCheck::UserServiceMutexCheck(std::wstring,cdp::UserServiceMutexCheckType)
0x18009774d  nop
0x18009774e  mov     rdx, [rbp+57h+var_50]
0x180097752  cmp     rdx, 7
0x180097756  jbe     short loc_180097769
0x180097758  lea     rdx, ds:2[rdx*2]
0x180097760  mov     rcx, [rbp+57h+var_68]
0x180097764  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180097769  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180097771  movdqu  xmmword ptr [rbp-1], xmm0
0x180097776  xor     eax, eax
0x180097778  mov     word ptr [rbp+57h+var_68], ax
0x18009777c  mov     rdx, [rbp+57h+var_30]
0x180097780  cmp     rdx, 7
0x180097784  jbe     short loc_18009779F
0x180097786  lea     rdx, ds:2[rdx*2]
0x18009778e  mov     rcx, [rbp+57h+var_48]
0x180097792  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180097797  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18009779f  movdqu  xmmword ptr [rbp+1Fh], xmm0
0x1800977a4  xor     eax, eax
0x1800977a6  mov     word ptr [rbp+57h+var_48], ax
0x1800977aa  mov     rdx, [rbp+57h+var_10]
0x1800977ae  cmp     rdx, 7
0x1800977b2  jbe     short loc_1800977CD
0x1800977b4  lea     rdx, ds:2[rdx*2]
0x1800977bc  mov     rcx, qword ptr [rbp+57h+var_28]
0x1800977c0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800977c5  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800977cd  movdqu  xmmword ptr [rbp+3Fh], xmm0
0x1800977d2  xor     eax, eax
0x1800977d4  mov     [rbp+57h+var_28], ax
0x1800977d8  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1800977dc  call    cs:__imp_RtlFreeUnicodeString
0x1800977e2  nop
0x1800977e3  mov     rcx, [rbp+57h+hObject]; hObject
0x1800977e7  lea     rax, [rcx-1]
0x1800977eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800977ef  ja      short loc_1800977F7
0x1800977f1  call    cs:__imp_CloseHandle
0x1800977f7  mov     rax, rdi
0x1800977fa  mov     rcx, [rbp+57h+var_8]
0x1800977fe  xor     rcx, rsp; StackCookie
0x180097801  call    __security_check_cookie
0x180097806  lea     r11, [rsp+0F0h+var_s0]
0x18009780e  mov     rbx, [r11+20h]
0x180097812  mov     rdi, [r11+28h]
0x180097816  mov     rsp, r11
0x180097819  pop     rbp
0x18009781a  retn
```
