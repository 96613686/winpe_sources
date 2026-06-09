# win_musl::consumption::ZipConsumptionPart::CloseZipPackage(void)

- ea: `0x180028aa4`
- end: `0x180028c07`
- name: `?CloseZipPackage@ZipConsumptionPart@consumption@win_musl@@QEAAXXZ`
- size: `355`
- prototype: `void __fastcall(win_musl::consumption::ZipConsumptionPart *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800289c0`

## callees

- `0x180011b14`
- `0x180017320`
- `0x180028aa4`
- `0x180028c10`
- `0x180028cf0`
- `0x18002db70`
- `0x18004ea94`
- `0x180060c90`
- `0x180084010`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028af7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028af7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028b3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028b3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028ae4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028ae4`

## string_xrefs

- `0x180028b70`: `The interleaved part is incomplete. %{part}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall win_musl::consumption::ZipConsumptionPart::CloseZipPackage(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  bool v3; // dl
  win_dox *DebugInfo_high; // rcx
  __int64 v6; // rbx
  win_musl::Formatter *v7; // rax
  struct win_musl::TStringEllipseBase *v8; // rax
  _BYTE v9[40]; // [rsp+50h] [rbp-168h] BYREF
  _BYTE v10[40]; // [rsp+78h] [rbp-140h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+A0h] [rbp-118h] BYREF
  _BYTE v12[96]; // [rsp+140h] [rbp-78h] BYREF

  v2 = this + 4;
  EnterCriticalSection(this + 4);
  DebugInfo_high = (win_dox *)HIDWORD(v2[1].DebugInfo);
  HIDWORD(v2[1].DebugInfo) = (_DWORD)DebugInfo_high + 1;
  if ( !(_DWORD)DebugInfo_high )
    LODWORD(v2[1].DebugInfo) = GetCurrentThreadId();
  LOBYTE(DebugInfo_high) = this[5].OwningThread;
  win_dox::ThrowIfFailed(DebugInfo_high, v3);
  if ( win_musl::consumption::ZipConsumptionPart::HasCompleteSequence((win_musl::consumption::ZipConsumptionPart *)this) )
  {
    if ( !BYTE1(this[3].SpinCount) )
      win_musl::consumption::ZipConsumptionPart::AddPartToReceiver((win_musl::consumption::ZipConsumptionPart *)this, 0);
  }
  else if ( !*(_BYTE *)(this[2].SpinCount + 57) )
  {
    std::wstring::wstring(v9, L"The interleaved part is incomplete. %{part}");
    v6 = win_musl::Formatter::Formatter(v12, v9);
    std::wstring::wstring(v10, L"part");
    v7 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v6, v10, &this->OwningThread);
    v8 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v7);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x10Eu,
      0x80510017,
      v8);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( HIDWORD(v2[1].DebugInfo)-- == 1 )
    LODWORD(v2[1].DebugInfo) = 0;
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180028aa4  mov     rax, rsp
0x180028aa7  push    rdi
0x180028aa8  sub     rsp, 1B0h
0x180028aaf  mov     [rsp+1B8h+var_170], 0FFFFFFFFFFFFFFFEh
0x180028ab8  mov     [rax+10h], rbx
0x180028abc  mov     [rax+18h], rsi
0x180028ac0  mov     rax, cs:__security_cookie
0x180028ac7  xor     rax, rsp
0x180028aca  mov     [rsp+1B8h+var_18], rax
0x180028ad2  mov     rdi, rcx
0x180028ad5  lea     rbx, [rcx+0A0h]
0x180028adc  mov     [rsp+1B8h+var_178], rbx
0x180028ae1  mov     rcx, rbx; lpCriticalSection
0x180028ae4  call    cs:__imp_EnterCriticalSection
0x180028aea  mov     ecx, [rbx+2Ch]
0x180028aed  lea     eax, [rcx+1]
0x180028af0  mov     [rbx+2Ch], eax
0x180028af3  test    ecx, ecx
0x180028af5  jnz     short loc_180028B00
0x180028af7  call    cs:__imp_GetCurrentThreadId
0x180028afd  mov     [rbx+28h], eax
0x180028b00  mov     cl, [rdi+0D8h]; this
0x180028b06  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180028b0b  mov     rcx, rdi; this
0x180028b0e  call    ?HasCompleteSequence@ZipConsumptionPart@consumption@win_musl@@AEBA_NXZ; win_musl::consumption::ZipConsumptionPart::HasCompleteSequence(void)
0x180028b13  test    al, al
0x180028b15  jz      short loc_180028B66
0x180028b17  cmp     byte ptr [rdi+99h], 0
0x180028b1e  jnz     short loc_180028B2B
0x180028b20  xor     edx, edx; struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *
0x180028b22  mov     rcx, rdi; this
0x180028b25  call    ?AddPartToReceiver@ZipConsumptionPart@consumption@win_musl@@AEAAXPEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z; win_musl::consumption::ZipConsumptionPart::AddPartToReceiver(__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)
0x180028b2a  nop
0x180028b2b  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180028b2f  jnz     short loc_180028B38
0x180028b31  mov     dword ptr [rbx+28h], 0
0x180028b38  mov     rcx, rbx; lpCriticalSection
0x180028b3b  call    cs:__imp_LeaveCriticalSection
0x180028b41  mov     rcx, [rsp+1B8h+var_18]
0x180028b49  xor     rcx, rsp; StackCookie
0x180028b4c  call    __security_check_cookie
0x180028b51  lea     r11, [rsp+1B8h+var_8]
0x180028b59  mov     rbx, [r11+18h]
0x180028b5d  mov     rsi, [r11+20h]
0x180028b61  mov     rsp, r11
0x180028b64  pop     rdi
0x180028b65  retn
0x180028b66  mov     rax, [rdi+70h]
0x180028b6a  cmp     byte ptr [rax+39h], 0
0x180028b6e  jnz     short loc_180028B2B
0x180028b70  lea     rdx, aTheInterleaved; "The interleaved part is incomplete. %{p"...
0x180028b77  lea     rcx, [rsp+1B8h+var_168]
0x180028b7c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180028b81  nop
0x180028b82  lea     rdx, [rsp+1B8h+var_168]
0x180028b87  lea     rcx, [rsp+1B8h+var_78]
0x180028b8f  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180028b94  mov     rbx, rax
0x180028b97  lea     rdx, aPart_0; "part"
0x180028b9e  lea     rcx, [rsp+1B8h+var_140]
0x180028ba3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180028ba8  nop
0x180028ba9  lea     r8, [rdi+10h]
0x180028bad  lea     rdx, [rsp+1B8h+var_140]
0x180028bb2  mov     rcx, rbx
0x180028bb5  call    ??$insert@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@0@Z; win_musl::Formatter::insert<std::wstring>(std::wstring const &,std::wstring const &)
0x180028bba  mov     rcx, rax; this
0x180028bbd  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180028bc2  mov     [rsp+1B8h+var_188], rax; struct win_musl::TStringEllipseBase *
0x180028bc7  mov     [rsp+1B8h+var_190], 80510017h; unsigned int
0x180028bcf  mov     [rsp+1B8h+var_198], 10Eh; unsigned int
0x180028bd7  lea     r9, word_180139126
0x180028bde  lea     r8, aNoFilename; "(no filename)"
0x180028be5  lea     rcx, [rsp+1B8h+pExceptionObject]; this
0x180028bed  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180028bf2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180028bf9  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x180028c01  call    _CxxThrowException_0
```
