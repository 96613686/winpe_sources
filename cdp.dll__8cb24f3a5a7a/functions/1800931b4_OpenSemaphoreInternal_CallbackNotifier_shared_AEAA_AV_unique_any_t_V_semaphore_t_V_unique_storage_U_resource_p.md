# ?OpenSemaphoreInternal@CallbackNotifier@shared@@AEAA?AV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEBD@Z

- ea: `0x1800931b4`
- end: `0x1800935c4`
- name: `?OpenSemaphoreInternal@CallbackNotifier@shared@@AEAA?AV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEBD@Z`
- size: `1040`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180091c90`

## callees

- `0x180009770`
- `0x180009b94`
- `0x18000acdc`
- `0x18000d02c`
- `0x1800117f8`
- `0x180030190`
- `0x1800931b4`
- `0x1800935cc`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1801fcb4e`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800933bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009350c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800933bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009350c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18009322a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18009322a`
- `ntdll!RtlNtStatusToDosError` at `0x18009338e`
- `ntdll!RtlNtStatusToDosError` at `0x1800934d5`
- `ntdll!RtlNtStatusToDosError` at `0x18009338e`
- `ntdll!RtlNtStatusToDosError` at `0x1800934d5`
- `ntdll!NtOpenSemaphore` at `0x180093495`
- `ntdll!NtOpenSemaphore` at `0x1800934cd`
- `ntdll!NtOpenSemaphore` at `0x180093495`
- `ntdll!NtOpenSemaphore` at `0x1800934cd`

## string_xrefs

- `0x1800933e6`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180093537`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
const char *__fastcall shared::CallbackNotifier::OpenSemaphoreInternal(__int64 a1, const char *a2, _BYTE *a3)
{
  __int128 v5; // rdi
  void *v6; // rbx
  __int128 *v7; // r8
  _QWORD *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  _WORD *i; // rax
  _QWORD *v12; // r8
  NTSTATUS v13; // ecx
  _WORD *v14; // rax
  __int16 v15; // dx
  signed int v16; // eax
  unsigned int v17; // ebx
  int v18; // ecx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  __int16 v23; // cx
  NTSTATUS v24; // ebx
  NTSTATUS v25; // eax
  signed int v26; // eax
  unsigned int v27; // ebx
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  unsigned int v34; // [rsp+30h] [rbp-D0h] BYREF
  const char *v35; // [rsp+38h] [rbp-C8h] BYREF
  void *SemaphoreHandle; // [rsp+40h] [rbp-C0h] BYREF
  char v37; // [rsp+48h] [rbp-B8h]
  int v38; // [rsp+50h] [rbp-B0h]
  __int128 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 CurrentThreadId; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h]
  _BYTE v43[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v45; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v46; // [rsp+108h] [rbp+8h]
  _QWORD v47[3]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v48; // [rsp+130h] [rbp+30h]
  _BYTE v49[128]; // [rsp+140h] [rbp+40h] BYREF

  v42 = a2;
  v38 = 0;
  v45 = 0;
  v46 = 0;
  *(_QWORD *)&v5 = -1;
  do
    *(_QWORD *)&v5 = v5 + 1;
  while ( a3[v5] );
  *((_QWORD *)&v5 + 1) = 0x7FFFFFFFFFFFFFFFLL;
  if ( (unsigned __int64)v5 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("string too long");
  if ( (unsigned __int64)v5 > 0xF )
  {
    if ( ((unsigned __int64)v5 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      *((_QWORD *)&v5 + 1) = v5 | 0xF;
      if ( ((unsigned __int64)v5 | 0xF) < 0x16 )
        *((_QWORD *)&v5 + 1) = 22;
    }
    v6 = (void *)std::allocator<char>::allocate(&v45, *((_QWORD *)&v5 + 1) + 1LL);
    *(_QWORD *)&v45 = v6;
    v46 = v5;
    memcpy_0(v6, a3, v5);
    *((_BYTE *)v6 + v5) = 0;
  }
  else
  {
    *(_QWORD *)&v46 = v5;
    *((_QWORD *)&v46 + 1) = 15;
    memcpy_0(&v45, a3, v5);
    *((_BYTE *)&v45 + v5) = 0;
  }
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v49);
  v7 = &v45;
  if ( *((_QWORD *)&v46 + 1) > 0xFu )
    v7 = (__int128 *)v45;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v49,
    v47,
    v7,
    (char *)v7 + v46);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v49);
  v38 = 14;
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v45);
  v8 = v47;
  if ( v48 > 7 )
    v8 = (_QWORD *)v47[0];
  v39 = 0;
  if ( v8 )
  {
    v9 = 0x7FFF;
    v10 = 0x7FFF;
    for ( i = v8; *i; ++i )
    {
      if ( !--v10 )
      {
        v12 = v47;
        if ( v48 > 7 )
          v12 = (_QWORD *)v47[0];
        v13 = 0;
        v39 = 0;
        if ( v12 )
        {
          v14 = v12;
          do
          {
            if ( !*v14 )
              break;
            ++v14;
            --v9;
          }
          while ( v9 );
          v13 = v9 == 0 ? 0xC000000D : 0;
          if ( v9 )
          {
            v15 = 2 * v9;
            LOWORD(v39) = -2 - v15;
            WORD1(v39) = -v15;
            *((_QWORD *)&v39 + 1) = v12;
          }
        }
        v16 = RtlNtStatusToDosError(v13);
        v17 = v16;
        if ( v16 > 0 )
          v17 = (unsigned __int16)v16 | 0x80070000;
        v35 = ".\\callbacknotifier.cpp";
        LODWORD(SemaphoreHandle) = 92;
        v34 = v17;
        CurrentThreadId = GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v18,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v34,
          (unsigned int)&v35,
          (__int64)&SemaphoreHandle,
          (__int64)&CurrentThreadId);
        v19 = cdp::ExceptionStackFromSourceLocationInfo(v43, &v35);
        v22 = cdp::ErrorCodeToString(v17, v20, v21, v19);
        ConnectedDevices::Exception::Exception(pExceptionObject, v17, v22);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
    }
    v23 = 2 * v10;
    LOWORD(v39) = -2 - v23;
    WORD1(v39) = -v23;
    *((_QWORD *)&v39 + 1) = v8;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v39;
  *(_QWORD *)a2 = 0;
  v38 = 15;
  v35 = a2;
  SemaphoreHandle = 0;
  v37 = 1;
  v24 = NtOpenSemaphore(&SemaphoreHandle, 0x100002u, &ObjectAttributes);
  __1__out_param_t_V__unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAA_XZ(&v35);
  if ( v24 < 0 )
  {
    v35 = a2;
    SemaphoreHandle = 0;
    v37 = 1;
    v25 = NtOpenSemaphore(&SemaphoreHandle, 0x100002u, &ObjectAttributes);
    v26 = RtlNtStatusToDosError(v25);
    v27 = v26;
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    __1__out_param_t_V__unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAA_XZ(&v35);
    v35 = ".\\callbacknotifier.cpp";
    LODWORD(SemaphoreHandle) = 100;
    v34 = v27;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v28,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v34,
      (unsigned int)&v35,
      (__int64)&SemaphoreHandle,
      (__int64)&CurrentThreadId);
    v29 = cdp::ExceptionStackFromSourceLocationInfo(v43, &v35);
    v32 = cdp::ErrorCodeToString(v27, v30, v31, v29);
    ConnectedDevices::Exception::Exception(pExceptionObject, v27, v32);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( v48 > 7 )
    std::_Deallocate<16>(v47[0], 2 * v48 + 2);
  return a2;
}

```

## disassembly

```asm
0x1800931b4  mov     [rsp-8+arg_0], rbx
0x1800931b9  mov     [rsp-8+arg_18], rsi
0x1800931be  push    rbp
0x1800931bf  push    rdi
0x1800931c0  push    r12
0x1800931c2  push    r14
0x1800931c4  push    r15
0x1800931c6  lea     rbp, [rsp-0D0h]
0x1800931ce  sub     rsp, 1D0h
0x1800931d5  mov     rax, cs:__security_cookie
0x1800931dc  xor     rax, rsp
0x1800931df  mov     [rbp+0F0h+var_30], rax
0x1800931e6  mov     r15, r8
0x1800931e9  mov     r14, rdx
0x1800931ec  mov     [rbp+0F0h+var_150], rdx
0x1800931f0  xor     r12d, r12d
0x1800931f3  mov     [rsp+1F0h+var_1A0], r12d
0x1800931f8  xorps   xmm0, xmm0
0x1800931fb  movups  [rbp+0F0h+var_F8], xmm0
0x1800931ff  xorps   xmm1, xmm1
0x180093202  movdqu  [rbp+0F0h+var_E8], xmm1
0x180093207  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009320b  inc     rdi
0x18009320e  cmp     [r8+rdi], r12b
0x180093212  jnz     short loc_18009320B
0x180093214  mov     rsi, 7FFFFFFFFFFFFFFFh
0x18009321e  cmp     rdi, rsi
0x180093221  jbe     short loc_180093231
0x180093223  lea     rcx, aStringTooLong; "string too long"
0x18009322a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180093231  cmp     rdi, 0Fh
0x180093235  ja      short loc_180093259
0x180093237  mov     qword ptr [rbp+0F0h+var_E8], rdi
0x18009323b  mov     qword ptr [rbp+0F0h+var_E8+8], 0Fh
0x180093243  mov     r8, rdi; Size
0x180093246  mov     rdx, r15; Src
0x180093249  lea     rcx, [rbp+0F0h+var_F8]; void *
0x18009324d  call    memcpy_0
0x180093252  mov     byte ptr [rbp+rdi+0F0h+var_F8], r12b
0x180093257  jmp     short loc_1800932A2
0x180093259  mov     rax, rdi
0x18009325c  or      rax, 0Fh
0x180093260  cmp     rax, rsi
0x180093263  ja      short loc_180093274
0x180093265  mov     rsi, rax
0x180093268  mov     ecx, 16h
0x18009326d  cmp     rax, rcx
0x180093270  cmovb   rsi, rcx
0x180093274  lea     rdx, [rsi+1]
0x180093278  lea     rcx, [rbp+0F0h+var_F8]
0x18009327c  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x180093281  mov     rbx, rax
0x180093284  mov     qword ptr [rbp+0F0h+var_F8], rax
0x180093288  mov     qword ptr [rbp+0F0h+var_E8], rdi
0x18009328c  mov     qword ptr [rbp+0F0h+var_E8+8], rsi
0x180093290  mov     r8, rdi; Size
0x180093293  mov     rdx, r15; Src
0x180093296  mov     rcx, rax; void *
0x180093299  call    memcpy_0
0x18009329e  mov     [rdi+rbx], r12b
0x1800932a2  lea     rcx, [rbp+0F0h+var_B0]
0x1800932a6  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800932ab  nop
0x1800932ac  lea     r8, [rbp+0F0h+var_F8]
0x1800932b0  cmp     qword ptr [rbp+0F0h+var_E8+8], 0Fh
0x1800932b5  cmova   r8, qword ptr [rbp+0F0h+var_F8]
0x1800932ba  mov     r9, qword ptr [rbp+0F0h+var_E8]
0x1800932be  add     r9, r8
0x1800932c1  lea     rdx, [rbp+0F0h+var_D8]
0x1800932c5  lea     rcx, [rbp+0F0h+var_B0]
0x1800932c9  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x1800932ce  nop
0x1800932cf  lea     rcx, [rbp+0F0h+var_B0]
0x1800932d3  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800932d8  mov     [rsp+1F0h+var_1A0], 0Eh
0x1800932e0  lea     rcx, [rbp+0F0h+var_F8]; void *
0x1800932e4  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800932e9  lea     r8, [rbp+0F0h+var_D8]
0x1800932ed  cmp     [rbp+0F0h+var_C0], 7
0x1800932f2  cmova   r8, [rbp+0F0h+var_D8]
0x1800932f7  xorps   xmm0, xmm0
0x1800932fa  movups  [rsp+1F0h+var_198], xmm0
0x1800932ff  test    r8, r8
0x180093302  jz      loc_180093447
0x180093308  mov     edx, 7FFFh
0x18009330d  mov     ecx, edx
0x18009330f  mov     rax, r8
0x180093312  mov     r9d, 2
0x180093318  cmp     [rax], r12w
0x18009331c  jz      loc_180093429
0x180093322  add     rax, r9
0x180093325  sub     rcx, 1
0x180093329  jnz     short loc_180093318
0x18009332b  lea     r8, [rbp+0F0h+var_D8]
0x18009332f  cmp     [rbp+0F0h+var_C0], 7
0x180093334  cmova   r8, [rbp+0F0h+var_D8]
0x180093339  mov     ecx, r12d
0x18009333c  xorps   xmm0, xmm0
0x18009333f  movups  [rsp+1F0h+var_198], xmm0
0x180093344  test    r8, r8
0x180093347  jz      short loc_18009338E
0x180093349  mov     rax, r8
0x18009334c  cmp     [rax], r12w
0x180093350  jz      short loc_18009335B
0x180093352  add     rax, r9
0x180093355  sub     rdx, 1
0x180093359  jnz     short loc_18009334C
0x18009335b  mov     rax, rdx
0x18009335e  neg     rax
0x180093361  sbb     ecx, ecx
0x180093363  not     ecx
0x180093365  and     ecx, 0C000000Dh; Status
0x18009336b  test    rdx, rdx
0x18009336e  jz      short loc_18009338E
0x180093370  add     dx, dx
0x180093373  mov     eax, 0FFFEh
0x180093378  sub     ax, dx
0x18009337b  mov     word ptr [rsp+1F0h+var_198], ax
0x180093380  add     ax, r9w
0x180093384  mov     word ptr [rsp+1F0h+var_198+2], ax
0x180093389  mov     qword ptr [rsp+1F0h+var_198+8], r8
0x18009338e  call    cs:__imp_RtlNtStatusToDosError
0x180093394  mov     ebx, eax
0x180093396  test    eax, eax
0x180093398  jle     short loc_1800933A3
0x18009339a  movzx   ebx, ax
0x18009339d  or      ebx, 80070000h
0x1800933a3  lea     rax, aCallbacknotifi_0; ".\\callbacknotifier.cpp"
0x1800933aa  mov     [rsp+1F0h+var_1B8], rax
0x1800933af  mov     dword ptr [rsp+1F0h+SemaphoreHandle], 5Ch ; '\'
0x1800933b7  mov     [rsp+1F0h+var_1C0], ebx
0x1800933bb  call    cs:__imp_GetCurrentThreadId
0x1800933c1  mov     eax, eax
0x1800933c3  mov     [rsp+1F0h+var_188], rax
0x1800933c8  lea     rax, [rsp+1F0h+var_188]
0x1800933cd  mov     [rsp+1F0h+var_1C8], rax
0x1800933d2  lea     rax, [rsp+1F0h+SemaphoreHandle]
0x1800933d7  mov     [rsp+1F0h+var_1D0], rax
0x1800933dc  lea     r9, [rsp+1F0h+var_1B8]
0x1800933e1  lea     r8, [rsp+1F0h+var_1C0]
0x1800933e6  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800933ed  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800933f2  lea     rdx, [rsp+1F0h+var_1B8]
0x1800933f7  lea     rcx, [rbp+0F0h+var_148]
0x1800933fb  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180093400  mov     r9, rax
0x180093403  mov     ecx, ebx
0x180093405  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18009340a  mov     r8, rax
0x18009340d  mov     edx, ebx
0x18009340f  lea     rcx, [rbp+0F0h+pExceptionObject]
0x180093413  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180093418  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18009341f  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x180093423  call    _CxxThrowException_0
0x180093429  add     cx, cx
0x18009342c  mov     eax, 0FFFEh
0x180093431  sub     ax, cx
0x180093434  mov     word ptr [rsp+1F0h+var_198], ax
0x180093439  add     ax, r9w
0x18009343d  mov     word ptr [rsp+1F0h+var_198+2], ax
0x180093442  mov     qword ptr [rsp+1F0h+var_198+8], r8
0x180093447  mov     qword ptr [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x180093450  mov     qword ptr [rbp+0F0h+ObjectAttributes.Attributes], r12
0x180093454  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], r12
0x180093459  lea     rax, [rsp+1F0h+var_198]
0x18009345e  mov     [rbp+0F0h+ObjectAttributes.ObjectName], rax
0x180093462  xorps   xmm0, xmm0
0x180093465  movdqu  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009346a  mov     [r14], r12
0x18009346d  mov     [rsp+1F0h+var_1A0], 0Fh
0x180093475  mov     [rsp+1F0h+var_1B8], r14
0x18009347a  mov     [rsp+1F0h+SemaphoreHandle], r12
0x18009347f  mov     [rsp+1F0h+var_1A8], 1
0x180093484  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x180093489  mov     edi, 100002h
0x18009348e  mov     edx, edi; DesiredAcces
0x180093490  lea     rcx, [rsp+1F0h+SemaphoreHandle]; SemaphoreHandle
0x180093495  call    cs:__imp_NtOpenSemaphore
0x18009349b  mov     ebx, eax
0x18009349d  lea     rcx, [rsp+1F0h+var_1B8]
0x1800934a2  call    ??1?$out_param_t@V?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAA@XZ
0x1800934a7  shr     ebx, 1Fh
0x1800934aa  test    bl, bl
0x1800934ac  jz      loc_18009357A
0x1800934b2  mov     [rsp+1F0h+var_1B8], r14
0x1800934b7  mov     [rsp+1F0h+SemaphoreHandle], r12
0x1800934bc  mov     [rsp+1F0h+var_1A8], 1
0x1800934c1  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x1800934c6  mov     edx, edi; DesiredAcces
0x1800934c8  lea     rcx, [rsp+1F0h+SemaphoreHandle]; SemaphoreHandle
0x1800934cd  call    cs:__imp_NtOpenSemaphore
0x1800934d3  mov     ecx, eax; Status
0x1800934d5  call    cs:__imp_RtlNtStatusToDosError
0x1800934db  mov     ebx, eax
0x1800934dd  test    eax, eax
0x1800934df  jle     short loc_1800934EA
0x1800934e1  movzx   ebx, ax
0x1800934e4  or      ebx, 80070000h
0x1800934ea  lea     rcx, [rsp+1F0h+var_1B8]
0x1800934ef  call    ??1?$out_param_t@V?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAA@XZ
0x1800934f4  lea     rax, aCallbacknotifi_0; ".\\callbacknotifier.cpp"
0x1800934fb  mov     [rsp+1F0h+var_1B8], rax
0x180093500  mov     dword ptr [rsp+1F0h+SemaphoreHandle], 64h ; 'd'
0x180093508  mov     [rsp+1F0h+var_1C0], ebx
0x18009350c  call    cs:__imp_GetCurrentThreadId
0x180093512  mov     eax, eax
0x180093514  mov     [rsp+1F0h+var_188], rax
0x180093519  lea     rax, [rsp+1F0h+var_188]
0x18009351e  mov     [rsp+1F0h+var_1C8], rax
0x180093523  lea     rax, [rsp+1F0h+SemaphoreHandle]
0x180093528  mov     [rsp+1F0h+var_1D0], rax
0x18009352d  lea     r9, [rsp+1F0h+var_1B8]
0x180093532  lea     r8, [rsp+1F0h+var_1C0]
0x180093537  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18009353e  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180093543  lea     rdx, [rsp+1F0h+var_1B8]
0x180093548  lea     rcx, [rbp+0F0h+var_148]
0x18009354c  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180093551  mov     r9, rax
0x180093554  mov     ecx, ebx
0x180093556  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18009355b  mov     r8, rax
0x18009355e  mov     edx, ebx
0x180093560  lea     rcx, [rbp+0F0h+pExceptionObject]
0x180093564  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180093569  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180093570  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x180093574  call    _CxxThrowException_0
0x18009357a  mov     rdx, [rbp+0F0h+var_C0]
0x18009357e  cmp     rdx, 7
0x180093582  jbe     short loc_180093595
0x180093584  lea     rdx, ds:2[rdx*2]
0x18009358c  mov     rcx, [rbp+0F0h+var_D8]
0x180093590  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180093595  mov     rax, r14
0x180093598  mov     rcx, [rbp+0F0h+var_30]
0x18009359f  xor     rcx, rsp; StackCookie
0x1800935a2  call    __security_check_cookie
0x1800935a7  lea     r11, [rsp+1F0h+var_20]
0x1800935af  mov     rbx, [r11+30h]
0x1800935b3  mov     rsi, [r11+48h]
0x1800935b7  mov     rsp, r11
0x1800935ba  pop     r15
0x1800935bc  pop     r14
0x1800935be  pop     r12
0x1800935c0  pop     rdi
0x1800935c1  pop     rbp
0x1800935c2  retn
```
