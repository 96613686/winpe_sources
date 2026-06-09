# CWinRtUrlAccessor::_ResolveMimeType(wchar_t const *)

- ea: `0x18000ec40`
- end: `0x18000ee57`
- name: `?_ResolveMimeType@CWinRtUrlAccessor@@AEAAXPEB_W@Z`
- size: `535`
- prototype: `void __fastcall(CWinRtUrlAccessor *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022cc8`

## callees

- `0x180002c20`
- `0x1800055b0`
- `0x180005ee0`
- `0x180007158`
- `0x1800098f0`
- `0x18000a210`
- `0x18000cc1c`
- `0x18000e9f4`
- `0x18000ec40`
- `0x18000fcd0`
- `0x18001de28`
- `0x180023068`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ed9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ed9d`

## string_xrefs

- `0x18000ed46`: `Extension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWinRtUrlAccessor::_ResolveMimeType(CWinRtUrlAccessor *this, const wchar_t *a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  wchar_t *v6; // [rsp+30h] [rbp-208h] BYREF
  void **v7; // [rsp+40h] [rbp-1F8h] BYREF
  wchar_t *v8; // [rsp+48h] [rbp-1F0h]
  unsigned __int64 v9; // [rsp+50h] [rbp-1E8h]
  __int16 v10; // [rsp+58h] [rbp-1E0h] BYREF
  _QWORD v11[4]; // [rsp+E0h] [rbp-158h] BYREF
  __int16 v12; // [rsp+100h] [rbp-138h] BYREF
  int v13; // [rsp+188h] [rbp-B0h]
  __int64 v14; // [rsp+190h] [rbp-A8h]
  _BYTE v15[8]; // [rsp+1A0h] [rbp-98h] BYREF
  wchar_t *v16; // [rsp+1A8h] [rbp-90h]
  wchar_t v17[20]; // [rsp+200h] [rbp-38h] BYREF

  try
  {
    TLMString<32,32,1024>::TLMString<32,32,1024>((TLMString<32,32,1024> *)v15, L"MIME\\Database\\Content Type\\");
    v11[2] = &v12;
    v11[3] = 65;
    v12 = 0;
    v11[1] = &TLMString<64,64,32767>::`vftable';
    v11[0] = &CRegistry::`vftable';
    v13 = 0;
    v14 = 0;
    CLMString::Append((CLMString *)v15, a2, 0xFFFFFFFF);
    if ( CRegistry::Init((CRegistry *)v11, HKEY_CLASSES_ROOT, v16, 1u, 0) >= 0 )
    {
      v8 = (wchar_t *)&v10;
      v9 = 65;
      v10 = 0;
      v7 = &TLMString<64,64,32767>::`vftable';
      if ( CRegistry::GetValue((CRegistry *)v11, L"Extension", (struct CLMString *)&v7) )
      {
        wcscpy(v17, L"winrt://dummy/dummy");
        v4 = (wchar_t *)CoTaskMemAlloc(2LL * HIDWORD(v9) + 40);
        v5 = v4;
        v6 = v4;
        if ( v4
          && StringCchCopyW(v4, HIDWORD(v9) + 20LL, v17) >= 0
          && (int)StringCchCatNW(v5, HIDWORD(v9) + 20LL, v8, HIDWORD(v9)) >= 0 )
        {
          wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::swap(
            (char *)this + 48,
            &v6);
          v5 = v6;
        }
        if ( v5 )
          CoTaskMemFree(v5);
      }
      TLMString<64,64,32767>::~TLMString<64,64,32767>((wchar_t *)&v7);
    }
    CRegistry::~CRegistry((CRegistry *)v11);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v15);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18000ec40  mov     [rsp+arg_10], rbx
0x18000ec45  mov     [rsp+arg_18], rdi
0x18000ec4a  push    r15
0x18000ec4c  sub     rsp, 230h
0x18000ec53  mov     rax, cs:__security_cookie
0x18000ec5a  xor     rax, rsp
0x18000ec5d  mov     [rsp+238h+var_10], rax
0x18000ec65  mov     rbx, rdx
0x18000ec68  mov     rdi, rcx
0x18000ec6b  lea     rdx, aMimeDatabaseCo; "MIME\\Database\\Content Type\\"
0x18000ec72  lea     rcx, [rsp+238h+var_98]
0x18000ec7a  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x18000ec7f  nop
0x18000ec80  lea     rax, [rsp+238h+var_138]
0x18000ec88  mov     [rsp+238h+var_148], rax
0x18000ec90  mov     [rsp+238h+var_140], 41h ; 'A'
0x18000ec9c  xor     eax, eax
0x18000ec9e  mov     [rsp+238h+var_138], ax
0x18000eca6  lea     r15, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x18000ecad  mov     [rsp+238h+var_150], r15
0x18000ecb5  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18000ecbc  mov     [rsp+238h+var_158], rax
0x18000ecc4  mov     [rsp+238h+var_B0], 0
0x18000eccf  mov     [rsp+238h+var_A8], 0
0x18000ecdb  or      r8d, 0FFFFFFFFh; unsigned int
0x18000ecdf  mov     rdx, rbx; wchar_t *
0x18000ece2  lea     rcx, [rsp+238h+var_98]; this
0x18000ecea  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18000ecef  mov     [rsp+238h+var_218], 0; wchar_t *
0x18000ecf8  mov     r9d, 1; unsigned int
0x18000ecfe  mov     r8, [rsp+238h+var_90]; wchar_t *
0x18000ed06  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x18000ed0d  lea     rcx, [rsp+238h+var_158]; this
0x18000ed15  call    ?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z; CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x18000ed1a  test    eax, eax
0x18000ed1c  js      loc_18000EE13
0x18000ed22  lea     rax, [rsp+238h+var_1E0]
0x18000ed27  mov     [rsp+238h+var_1F0], rax
0x18000ed2c  mov     [rsp+238h+var_1E8], 41h ; 'A'
0x18000ed35  xor     eax, eax
0x18000ed37  mov     [rsp+238h+var_1E0], ax
0x18000ed3c  mov     [rsp+238h+var_1F8], r15
0x18000ed41  lea     r8, [rsp+238h+var_1F8]; struct CLMString *
0x18000ed46  lea     rdx, aExtension; "Extension"
0x18000ed4d  lea     rcx, [rsp+238h+var_158]; this
0x18000ed55  call    ?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z; CRegistry::GetValue(wchar_t const *,CLMString &)
0x18000ed5a  test    eax, eax
0x18000ed5c  jz      loc_18000EE08
0x18000ed62  movups  xmm0, xmmword ptr cs:aWinrtDummyDumm; "winrt://dummy/dummy"
0x18000ed69  movups  xmmword ptr [rsp+238h+var_38], xmm0
0x18000ed71  movups  xmm1, xmmword ptr cs:aWinrtDummyDumm+10h; "dummy/dummy"
0x18000ed78  movups  [rsp+238h+var_28], xmm1
0x18000ed80  movsd   xmm0, qword ptr cs:aWinrtDummyDumm+20h; "mmy"
0x18000ed88  movsd   [rsp+238h+var_18], xmm0
0x18000ed91  mov     ecx, dword ptr [rsp+238h+var_1E8+4]
0x18000ed95  lea     rcx, ds:28h[rcx*2]; cb
0x18000ed9d  call    cs:__imp_CoTaskMemAlloc
0x18000eda3  mov     rbx, rax
0x18000eda6  mov     [rsp+238h+var_208], rax
0x18000edab  test    rax, rax
0x18000edae  jz      short loc_18000EDF9
0x18000edb0  mov     edx, dword ptr [rsp+238h+var_1E8+4]
0x18000edb4  add     rdx, 14h; unsigned __int64
0x18000edb8  lea     r8, [rsp+238h+var_38]; wchar_t *
0x18000edc0  mov     rcx, rax; wchar_t *
0x18000edc3  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000edc8  test    eax, eax
0x18000edca  js      short loc_18000EDF9
0x18000edcc  mov     r9d, dword ptr [rsp+238h+var_1E8+4]; unsigned __int64
0x18000edd1  lea     rdx, [r9+14h]; unsigned __int64
0x18000edd5  mov     r8, [rsp+238h+var_1F0]; wchar_t *
0x18000edda  mov     rcx, rbx; wchar_t *
0x18000eddd  call    ?StringCchCatNW@@YAJPEA_W_KPEB_W1@Z; StringCchCatNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18000ede2  test    eax, eax
0x18000ede4  js      short loc_18000EDF9
0x18000ede6  lea     rcx, [rdi+30h]
0x18000edea  lea     rdx, [rsp+238h+var_208]
0x18000edef  call    ?swap@?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::swap(wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x18000edf4  mov     rbx, [rsp+238h+var_208]
0x18000edf9  test    rbx, rbx
0x18000edfc  jz      short loc_18000EE08
0x18000edfe  mov     rcx, rbx; pv
0x18000ee01  call    cs:__imp_CoTaskMemFree
0x18000ee07  nop
0x18000ee08  lea     rcx, [rsp+238h+var_1F8]
0x18000ee0d  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x18000ee12  nop
0x18000ee13  lea     rcx, [rsp+238h+var_158]; this
0x18000ee1b  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18000ee20  nop
0x18000ee21  lea     rcx, [rsp+238h+var_98]
0x18000ee29  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18000ee2e  nop
0x18000ee2f  jmp     short $+2
0x18000ee31  mov     rcx, [rsp+238h+var_10]
0x18000ee39  xor     rcx, rsp; StackCookie
0x18000ee3c  call    __security_check_cookie
0x18000ee41  lea     r11, [rsp+238h+var_8]
0x18000ee49  mov     rbx, [r11+20h]
0x18000ee4d  mov     rdi, [r11+28h]
0x18000ee51  mov     rsp, r11
0x18000ee54  pop     r15
0x18000ee56  retn
```
