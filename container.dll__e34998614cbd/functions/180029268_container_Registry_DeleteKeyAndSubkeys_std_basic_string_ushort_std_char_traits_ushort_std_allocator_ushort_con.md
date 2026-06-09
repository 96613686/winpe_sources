# container::Registry::DeleteKeyAndSubkeys(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180029268`
- end: `0x1800295de`
- name: `?DeleteKeyAndSubkeys@Registry@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180029268`
- `0x180029bc0`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x180002f1c`
- `0x1800051b0`
- `0x18000b4bc`
- `0x18000ca10`
- `0x180012b30`
- `0x180026830`
- `0x18002759c`
- `0x180027610`
- `0x1800286cc`
- `0x180028878`
- `0x180028a70`
- `0x180029268`
- `0x18002b464`

## import_xrefs

- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800294d3`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800294d3`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800294e3`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800294e3`
- `ntdll!NtQueryKey` at `0x18002936b`
- `ntdll!NtQueryKey` at `0x18002936b`
- `ntdll!NtDeleteKey` at `0x180029501`
- `ntdll!NtDeleteKey` at `0x180029501`
- `ntdll!NtEnumerateKey` at `0x1800293d1`
- `ntdll!NtEnumerateKey` at `0x1800293d1`
- `ntdll!NtOpenKey` at `0x18002932b`
- `ntdll!NtOpenKey` at `0x18002932b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029305`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800292f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029541`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800292f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029541`

## string_xrefs

- `0x180029570`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x1800295a2`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x1800295b7`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x1800295cc`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x180029596`: `OpenKey(%ws) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall container::Registry::DeleteKeyAndSubkeys(_QWORD *a1)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // eax
  ULONG v4; // r14d
  void *v5; // rsi
  ULONG i; // r15d
  NTSTATUS v7; // eax
  _QWORD *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int128 *v11; // rdx
  __int64 v12; // rax
  NTSTATUS v13; // eax
  unsigned __int64 v14; // rdx
  int result; // eax
  const char *v16; // rax
  const char *v17; // r9
  int ResultLength; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v20; // [rsp+38h] [rbp-C8h] BYREF
  void *v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+4Ch] [rbp-B4h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[120]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[104]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v27; // [rsp+140h] [rbp+40h] BYREF
  __int64 v28; // [rsp+150h] [rbp+50h]
  unsigned __int64 v29; // [rsp+158h] [rbp+58h]
  int KeyInformation; // [rsp+160h] [rbp+60h] BYREF
  __int128 v31; // [rsp+164h] [rbp+64h]
  __int128 v32; // [rsp+174h] [rbp+74h]
  int v33; // [rsp+184h] [rbp+84h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v35[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  KeyInformation = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v20 = 0;
  windows_wrappers::ObjectAttributes::ObjectAttributes((unsigned int)&ObjectAttributes, (_DWORD)a1, 64, 0, 0);
  hObject = 0;
  v2 = NtOpenKey(&hObject, 0xF003Fu, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    v3 = NtQueryKey(hObject, KeyCachedInformation, &KeyInformation, 0x28u, &v20);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x42C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        (const char *)(unsigned int)v3,
        ResultLength);
    v4 = HIDWORD(v31) + 24;
    v21 = 0;
    v5 = operator new[]((unsigned int)(HIDWORD(v31) + 24));
    v21 = v5;
    for ( i = 0; i < DWORD2(v31); ++i )
    {
      v7 = NtEnumerateKey(hObject, i, KeyBasicInformation, v5, v4, &v20);
      if ( v7 == -2147483622 )
        break;
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x448,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
          (const char *)(unsigned int)v7,
          ResultLength);
      std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v23);
      if ( a1[3] <= 7u )
        v8 = a1;
      else
        v8 = (_QWORD *)*a1;
      v9 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(&v23, v8, a1[2]);
      v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9);
      v27 = 0;
      v28 = 0;
      v29 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v27);
      v11 = &v27;
      if ( v29 > 7 )
        v11 = (__int128 *)v27;
      std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v10, v11, v28);
      std::wstring::~wstring(&v27);
      v12 = std::basic_ostringstream<unsigned short>::str(&v23, &v27);
      container::Registry::DeleteKeyAndSubkeys(v12);
      std::wstring::~wstring(&v27);
      *(_QWORD *)&v24[*(int *)(v23 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
      *(int *)((char *)&v22 + *(int *)(v23 + 4)) = *(_DWORD *)(v23 + 4) - 136;
      std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v24);
      std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v25);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v26);
    }
    v13 = NtDeleteKey(hObject);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x457,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        (const char *)(unsigned int)v13,
        ResultLength);
    operator delete(v5, v14);
  }
  else if ( v2 != -1073741772 )
  {
    v16 = (const char *)std::wstring::c_str(a1);
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v17,
      (int)"OpenKey(%ws) failed",
      v16);
  }
  std::wstring::~wstring(v35);
  result = (_DWORD)hObject - 1;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(hObject);
  return result;
}

```

## disassembly

```asm
0x180029268  push    rbp
0x18002926a  push    rbx
0x18002926b  push    rsi
0x18002926c  push    rdi
0x18002926d  push    r14
0x18002926f  push    r15
0x180029271  lea     rbp, [rsp-108h]
0x180029279  sub     rsp, 208h
0x180029280  mov     rax, cs:__security_cookie
0x180029287  xor     rax, rsp
0x18002928a  mov     [rbp+130h+var_40], rax
0x180029291  mov     rdi, rcx
0x180029294  mov     [rsp+230h+hObject], 0
0x18002929d  mov     [rbp+130h+KeyInformation], 0
0x1800292a4  xorps   xmm0, xmm0
0x1800292a7  xor     eax, eax
0x1800292a9  movups  [rbp+130h+var_CC], xmm0
0x1800292ad  movups  [rbp+130h+var_BC], xmm0
0x1800292b1  mov     [rbp+130h+var_AC], eax
0x1800292b7  mov     [rsp+230h+var_1F8], eax
0x1800292bb  mov     [rsp+230h+ResultLength], rax
0x1800292c0  xor     r9d, r9d
0x1800292c3  lea     r8d, [rax+40h]
0x1800292c7  mov     rdx, rcx
0x1800292ca  lea     rcx, [rbp+130h+ObjectAttributes]
0x1800292d1  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x1800292d6  nop
0x1800292d7  mov     rsi, [rsp+230h+hObject]
0x1800292dc  lea     rax, [rsi-1]
0x1800292e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800292e4  ja      short loc_180029311
0x1800292e6  call    cs:__imp_GetLastError
0x1800292ed  nop     dword ptr [rax+rax+00h]
0x1800292f2  mov     ebx, eax
0x1800292f4  mov     rcx, rsi; hObject
0x1800292f7  call    cs:__imp_CloseHandle
0x1800292fe  nop     dword ptr [rax+rax+00h]
0x180029303  mov     ecx, ebx; dwErrCode
0x180029305  call    cs:__imp_SetLastError
0x18002930c  nop     dword ptr [rax+rax+00h]
0x180029311  mov     [rsp+230h+hObject], 0
0x18002931a  lea     r8, [rbp+130h+ObjectAttributes]; ObjectAttributes
0x180029321  mov     edx, 0F003Fh; DesiredAccess
0x180029326  lea     rcx, [rsp+230h+hObject]; KeyHandle
0x18002932b  call    cs:__imp_NtOpenKey
0x180029332  nop     dword ptr [rax+rax+00h]
0x180029337  mov     r9d, eax
0x18002933a  test    eax, eax
0x18002933c  jns     short loc_18002934E
0x18002933e  cmp     eax, 0C0000034h
0x180029343  jnz     loc_180029582
0x180029349  jmp     loc_180029525
0x18002934e  lea     rax, [rsp+230h+var_1F8]
0x180029353  mov     [rsp+230h+ResultLength], rax; int
0x180029358  mov     r9d, 28h ; '('; Length
0x18002935e  lea     r8, [rbp+130h+KeyInformation]; KeyInformation
0x180029362  lea     edx, [r9-24h]; KeyInformationClass
0x180029366  mov     rcx, [rsp+230h+hObject]; KeyHandle
0x18002936b  call    cs:__imp_NtQueryKey
0x180029372  nop     dword ptr [rax+rax+00h]
0x180029377  mov     rcx, [rbp+138h]; this
0x18002937e  test    eax, eax
0x180029380  js      loc_1800295B4
0x180029386  mov     r14d, dword ptr [rbp+130h+var_CC+0Ch]
0x18002938a  add     r14d, 18h
0x18002938e  mov     [rsp+230h+var_1F0], 0
0x180029397  mov     ecx, r14d; unsigned __int64
0x18002939a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002939f  mov     rsi, rax
0x1800293a2  mov     [rsp+230h+var_1F0], rax
0x1800293a7  xor     r15d, r15d
0x1800293aa  cmp     dword ptr [rbp+130h+var_CC+8], r15d
0x1800293ae  jbe     loc_1800294FC
0x1800293b4  lea     rax, [rsp+230h+var_1F8]
0x1800293b9  mov     [rsp+230h+var_208], rax; ResultLength
0x1800293be  mov     dword ptr [rsp+230h+ResultLength], r14d; int
0x1800293c3  mov     r9, rsi; KeyInformation
0x1800293c6  xor     r8d, r8d; KeyInformationClass
0x1800293c9  mov     edx, r15d; Index
0x1800293cc  mov     rcx, [rsp+230h+hObject]; KeyHandle
0x1800293d1  call    cs:__imp_NtEnumerateKey
0x1800293d8  nop     dword ptr [rax+rax+00h]
0x1800293dd  cmp     eax, 8000001Ah
0x1800293e2  jz      loc_1800294FC
0x1800293e8  mov     rcx, [rbp+138h]; this
0x1800293ef  test    eax, eax
0x1800293f1  js      loc_18002956D
0x1800293f7  lea     rcx, [rsp+230h+var_1E0]
0x1800293fc  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180029401  nop
0x180029402  cmp     qword ptr [rdi+18h], 7
0x180029407  jbe     short loc_18002940E
0x180029409  mov     rdx, [rdi]
0x18002940c  jmp     short loc_180029411
0x18002940e  mov     rdx, rdi
0x180029411  mov     r8, [rdi+10h]
0x180029415  lea     rcx, [rsp+230h+var_1E0]
0x18002941a  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x18002941f  mov     rcx, rax
0x180029422  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180029427  mov     rbx, rax
0x18002942a  xorps   xmm0, xmm0
0x18002942d  movups  [rbp+130h+var_F0], xmm0
0x180029431  mov     [rbp+130h+var_E0], 0
0x180029439  mov     [rbp+130h+var_D8], 0
0x180029441  mov     r8d, [rsi+0Ch]
0x180029445  shr     r8, 1
0x180029448  lea     rdx, [rsi+10h]
0x18002944c  lea     rcx, [rbp+130h+var_F0]
0x180029450  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180029455  nop
0x180029456  lea     rdx, [rbp+130h+var_F0]
0x18002945a  cmp     [rbp+130h+var_D8], 7
0x18002945f  cmova   rdx, qword ptr [rbp+130h+var_F0]
0x180029464  mov     r8, [rbp+130h+var_E0]
0x180029468  mov     rcx, rbx
0x18002946b  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180029470  nop
0x180029471  lea     rcx, [rbp+130h+var_F0]
0x180029475  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002947a  lea     rdx, [rbp+130h+var_F0]
0x18002947e  lea     rcx, [rsp+230h+var_1E0]
0x180029483  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x180029488  nop
0x180029489  mov     rcx, rax
0x18002948c  call    ?DeleteKeyAndSubkeys@Registry@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; container::Registry::DeleteKeyAndSubkeys(std::wstring const &)
0x180029491  nop
0x180029492  lea     rcx, [rbp+130h+var_F0]
0x180029496  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002949b  nop
0x18002949c  mov     rax, [rsp+230h+var_1E0]
0x1800294a1  movsxd  rcx, dword ptr [rax+4]
0x1800294a5  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x1800294ac  mov     [rsp+rcx+230h+var_1E0], rax
0x1800294b1  mov     rax, [rsp+230h+var_1E0]
0x1800294b6  movsxd  rcx, dword ptr [rax+4]
0x1800294ba  lea     edx, [rcx-88h]
0x1800294c0  mov     [rsp+rcx+230h+var_1E4], edx
0x1800294c4  lea     rcx, [rsp+230h+var_1D8]
0x1800294c9  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x1800294ce  lea     rcx, [rsp+230h+var_1D0]
0x1800294d3  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x1800294da  nop     dword ptr [rax+rax+00h]
0x1800294df  lea     rcx, [rbp+130h+var_158]
0x1800294e3  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x1800294ea  nop     dword ptr [rax+rax+00h]
0x1800294ef  inc     r15d
0x1800294f2  cmp     r15d, dword ptr [rbp+130h+var_CC+8]
0x1800294f6  jb      loc_1800293B4
0x1800294fc  mov     rcx, [rsp+230h+hObject]; KeyHandle
0x180029501  call    cs:__imp_NtDeleteKey
0x180029508  nop     dword ptr [rax+rax+00h]
0x18002950d  mov     rcx, [rbp+138h]; this
0x180029514  test    eax, eax
0x180029516  js      loc_1800295C9
0x18002951c  mov     rcx, rsi; void *
0x18002951f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029524  nop
0x180029525  lea     rcx, [rbp+130h+var_60]
0x18002952c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029531  nop
0x180029532  mov     rcx, [rsp+230h+hObject]; hObject
0x180029537  lea     rax, [rcx-1]
0x18002953b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002953f  ja      short loc_18002954D
0x180029541  call    cs:__imp_CloseHandle
0x180029548  nop     dword ptr [rax+rax+00h]
0x18002954d  mov     rcx, [rbp+130h+var_40]
0x180029554  xor     rcx, rsp; StackCookie
0x180029557  call    __security_check_cookie
0x18002955c  add     rsp, 208h
0x180029563  pop     r15
0x180029565  pop     r14
0x180029567  pop     rdi
0x180029568  pop     rsi
0x180029569  pop     rbx
0x18002956a  pop     rbp
0x18002956b  retn
0x18002956d  mov     r9d, eax; char *
0x180029570  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029577  mov     edx, 448h; void *
0x18002957c  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180029582  mov     rcx, rdi
0x180029585  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002958a  mov     rcx, [rbp+138h]; this
0x180029591  mov     [rsp+230h+var_208], rax; char *
0x180029596  lea     rax, aOpenkeyWsFaile; "OpenKey(%ws) failed"
0x18002959d  mov     [rsp+230h+ResultLength], rax; int
0x1800295a2  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x1800295a9  mov     edx, 41Fh; void *
0x1800295ae  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800295b4  mov     r9d, eax; char *
0x1800295b7  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x1800295be  mov     edx, 42Ch; void *
0x1800295c3  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1800295c9  mov     r9d, eax; char *
0x1800295cc  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x1800295d3  mov     edx, 457h; void *
0x1800295d8  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
