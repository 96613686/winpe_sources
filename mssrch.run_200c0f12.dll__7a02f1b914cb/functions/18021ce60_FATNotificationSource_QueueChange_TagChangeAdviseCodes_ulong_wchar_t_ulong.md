# FATNotificationSource::QueueChange(TagChangeAdviseCodes,ulong,wchar_t *,ulong)

- ea: `0x18021ce60`
- end: `0x18021d102`
- name: `?QueueChange@FATNotificationSource@@AEAAXW4TagChangeAdviseCodes@@KPEA_WK@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x18021d108`

## callees

- `0x18000d0d0`
- `0x18001d5b0`
- `0x180022710`
- `0x1800296b0`
- `0x18002bf00`
- `0x180052c14`
- `0x1800800f4`
- `0x1800e2374`
- `0x1801244c0`
- `0x18021c5e4`
- `0x18021c6f8`
- `0x18021c7a8`
- `0x18021ce60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18021d038`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18021d038`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18021cf2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18021cf2d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18021d0ba`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18021d0ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18021d084`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18021d084`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18021cff0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18021cff0`

## string_xrefs

- `0x18021cf6f`: `DELETE`
- `0x18021cfc8`: `DELETE`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FATNotificationSource::QueueChange(__int64 a1, int a2, int a3, const wchar_t *a4, unsigned int a5)
{
  __int64 v8; // rdi
  __int64 v9; // rcx
  const wchar_t *v10; // r9
  HANDLE EventW; // rax
  unsigned int Error; // eax
  struct _TP_WORK *ThreadpoolWork; // rax
  unsigned int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[16]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h]
  void **v19; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v20; // [rsp+58h] [rbp-A8h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  __int16 v22; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+1F0h] [rbp+F0h]
  ULONGLONG TickCount64; // [rsp+1F8h] [rbp+F8h]
  int v25; // [rsp+200h] [rbp+100h]
  _QWORD v26[3]; // [rsp+210h] [rbp+110h] BYREF
  __int16 v27; // [rsp+228h] [rbp+128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  v20 = (wchar_t *)&v22;
  v21 = 193;
  v22 = 0;
  v19 = &TLMString<192,64,32767>::`vftable';
  v26[1] = &v27;
  v26[2] = 193;
  v27 = 0;
  v26[0] = &TLMString<192,64,32767>::`vftable';
  CLMString::Assign((CLMString *)v26, a4, 0, a5 >> 1);
  TLMString<192,64,32767>::operator=(&v19, a1 + 65592);
  CLMString::operator+=(&v19, v26);
  v16 = a1 + 66064;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 66064));
  std::_Tree<std::_Tset_traits<FATNotificationSource::SNotification,std::less<FATNotificationSource::SNotification>,std::allocator<FATNotificationSource::SNotification>,0>>::_Find_lower_bound<FATNotificationSource::SNotification>(
    a1 + 66168,
    v17,
    &v19);
  v8 = v18;
  if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<FATNotificationSource::SNotification,std::less<FATNotificationSource::SNotification>,std::allocator<FATNotificationSource::SNotification>,0>>::_Lower_bound_duplicate<FATNotificationSource::SNotification>(
                           v9,
                           v18,
                           &v19)
    || v8 == *(_QWORD *)(a1 + 66168) )
  {
    v10 = L"DELETE";
    if ( a2 != 1 )
      v10 = L"INDEX";
    ETWLog::LogItem(0xFFFFFFFF, v20, L"CFatNotify - queued new notification (%s)", v10);
    v23 = a2;
    TickCount64 = GetTickCount64();
    v25 = a3;
    std::_Tree<std::_Tset_traits<FATNotificationSource::SNotification,std::less<FATNotificationSource::SNotification>,std::allocator<FATNotificationSource::SNotification>,0>>::_Emplace<FATNotificationSource::SNotification const &>(
      a1 + 66168,
      v17,
      &v19);
    if ( *(_QWORD *)(a1 + 66176) == 1 )
    {
      if ( !*(_QWORD *)(a1 + 66192) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *(_QWORD *)(a1 + 66192) = EventW;
        if ( !EventW )
        {
          Error = ResultFromLastError();
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x206,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\fatmonitor.cxx",
            (const char *)Error,
            v15);
        }
      }
      ThreadpoolWork = *(struct _TP_WORK **)(a1 + 66184);
      if ( !ThreadpoolWork )
      {
        ThreadpoolWork = CreateThreadpoolWork(TPProcessNotificationsCallback, (PVOID)a1, 0);
        *(_QWORD *)(a1 + 66184) = ThreadpoolWork;
        if ( !ThreadpoolWork )
        {
          v14 = ResultFromLastError();
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x20E,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\fatmonitor.cxx",
            (const char *)v14,
            v15);
        }
      }
      SubmitThreadpoolWork(ThreadpoolWork);
    }
  }
  else
  {
    ETWLog::LogItem(0xFFFFFFFF, v20, L"CFatNotify - coalesced duplicate notification (was:%s now:%s)");
    if ( a2 == 1 || *(_DWORD *)(v8 + 448) == 1 )
      *(_DWORD *)(v8 + 448) = a2;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v16);
  TLMString<192,64,32767>::~TLMString<192,64,32767>(v26);
  TLMString<192,64,32767>::~TLMString<192,64,32767>(&v19);
}

```

## disassembly

```asm
0x18021ce60  push    rbp
0x18021ce62  push    rbx
0x18021ce63  push    rsi
0x18021ce64  push    rdi
0x18021ce65  push    r14
0x18021ce67  push    r15
0x18021ce69  lea     rbp, [rsp-2C8h]
0x18021ce71  sub     rsp, 3C8h
0x18021ce78  mov     rax, cs:__security_cookie
0x18021ce7f  xor     rax, rsp
0x18021ce82  mov     [rbp+2F0h+var_40], rax
0x18021ce89  mov     r10, r9
0x18021ce8c  mov     r15d, r8d
0x18021ce8f  mov     esi, edx
0x18021ce91  mov     rbx, rcx
0x18021ce94  lea     rax, [rsp+3F0h+var_388]
0x18021ce99  mov     [rsp+3F0h+var_398], rax
0x18021ce9e  mov     [rsp+3F0h+var_390], 0C1h
0x18021cea7  xor     eax, eax
0x18021cea9  mov     [rsp+3F0h+var_388], ax
0x18021ceae  lea     rcx, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x18021ceb5  mov     [rsp+3F0h+var_3A0], rcx
0x18021ceba  lea     rax, [rbp+2F0h+var_1C8]
0x18021cec1  mov     [rbp+2F0h+var_1D8], rax
0x18021cec8  mov     [rbp+2F0h+var_1D0], 0C1h
0x18021ced3  xor     eax, eax
0x18021ced5  mov     [rbp+2F0h+var_1C8], ax
0x18021cedc  mov     [rbp+2F0h+var_1E0], rcx
0x18021cee3  mov     r9d, [rbp+2F0h+arg_20]
0x18021ceea  shr     r9d, 1; unsigned int
0x18021ceed  xor     r8d, r8d; unsigned int
0x18021cef0  mov     rdx, r10; wchar_t *
0x18021cef3  lea     rcx, [rbp+2F0h+var_1E0]; this
0x18021cefa  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x18021ceff  lea     rdx, [rbx+10038h]
0x18021cf06  lea     rcx, [rsp+3F0h+var_3A0]
0x18021cf0b  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x18021cf10  lea     rdx, [rbp+2F0h+var_1E0]
0x18021cf17  lea     rcx, [rsp+3F0h+var_3A0]
0x18021cf1c  call    ??YCLMString@@QEAAXAEBV0@@Z; CLMString::operator+=(CLMString const &)
0x18021cf21  lea     rcx, [rbx+10210h]; lpCriticalSection
0x18021cf28  mov     [rsp+3F0h+var_3C0], rcx
0x18021cf2d  call    cs:__imp_EnterCriticalSection
0x18021cf33  nop
0x18021cf34  lea     r14, [rbx+10278h]
0x18021cf3b  lea     r8, [rsp+3F0h+var_3A0]
0x18021cf40  lea     rdx, [rsp+3F0h+var_3B8]
0x18021cf45  mov     rcx, r14
0x18021cf48  call    ??$_Find_lower_bound@USNotification@FATNotificationSource@@@?$_Tree@V?$_Tset_traits@USNotification@FATNotificationSource@@U?$less@USNotification@FATNotificationSource@@@std@@V?$allocator@USNotification@FATNotificationSource@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@USNotification@FATNotificationSource@@PEAX@std@@@1@AEBUSNotification@FATNotificationSource@@@Z; std::_Tree<std::_Tset_traits<FATNotificationSource::SNotification,std::less<FATNotificationSource::SNotification>,std::allocator<FATNotificationSource::SNotification>,0>>::_Find_lower_bound<FATNotificationSource::SNotification>(FATNotificationSource::SNotification const &)
0x18021cf4d  lea     r8, [rsp+3F0h+var_3A0]
0x18021cf52  mov     rdi, [rsp+3F0h+var_3A8]
0x18021cf57  mov     rdx, rdi
0x18021cf5a  call    ??$_Lower_bound_duplicate@USNotification@FATNotificationSource@@@?$_Tree@V?$_Tset_traits@USNotification@FATNotificationSource@@U?$less@USNotification@FATNotificationSource@@@std@@V?$allocator@USNotification@FATNotificationSource@@@4@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@USNotification@FATNotificationSource@@PEAX@1@AEBUSNotification@FATNotificationSource@@@Z; std::_Tree<std::_Tset_traits<FATNotificationSource::SNotification,std::less<FATNotificationSource::SNotification>,std::allocator<FATNotificationSource::SNotification>,0>>::_Lower_bound_duplicate<FATNotificationSource::SNotification>(std::_Tree_node<FATNotificationSource::SNotification,void *> * const,FATNotificationSource::SNotification const &)
0x18021cf5f  test    al, al
0x18021cf61  jz      short loc_18021CFC1
0x18021cf63  cmp     rdi, [r14]
0x18021cf66  jz      short loc_18021CFC1
0x18021cf68  lea     rcx, aIndex; "INDEX"
0x18021cf6f  lea     r9, aDelete_2; "DELETE"
0x18021cf76  mov     rax, r9
0x18021cf79  cmp     esi, 1
0x18021cf7c  cmovnz  rax, rcx
0x18021cf80  cmp     dword ptr [rdi+1C0h], 1
0x18021cf87  cmovnz  r9, rcx
0x18021cf8b  mov     qword ptr [rsp+3F0h+var_3D0], rax
0x18021cf90  lea     r8, aCfatnotifyCoal; "CFatNotify - coalesced duplicate notifi"...
0x18021cf97  mov     rdx, [rsp+3F0h+var_398]; wchar_t *
0x18021cf9c  or      ecx, 0FFFFFFFFh; unsigned int
0x18021cf9f  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18021cfa4  cmp     esi, 1
0x18021cfa7  jz      short loc_18021CFB6
0x18021cfa9  cmp     dword ptr [rdi+1C0h], 1
0x18021cfb0  jnz     loc_18021D0C1
0x18021cfb6  mov     [rdi+1C0h], esi
0x18021cfbc  jmp     loc_18021D0C1
0x18021cfc1  lea     rcx, aIndex; "INDEX"
0x18021cfc8  lea     r9, aDelete_2; "DELETE"
0x18021cfcf  cmp     esi, 1
0x18021cfd2  cmovnz  r9, rcx
0x18021cfd6  lea     r8, aCfatnotifyQueu; "CFatNotify - queued new notification (%"...
0x18021cfdd  mov     rdx, [rsp+3F0h+var_398]; wchar_t *
0x18021cfe2  or      ecx, 0FFFFFFFFh; unsigned int
0x18021cfe5  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18021cfea  mov     [rbp+2F0h+var_200], esi
0x18021cff0  call    cs:__imp_GetTickCount64
0x18021cff6  mov     [rbp+2F0h+var_1F8], rax
0x18021cffd  mov     [rbp+2F0h+var_1F0], r15d
0x18021d004  lea     r8, [rsp+3F0h+var_3A0]
0x18021d009  lea     rdx, [rsp+3F0h+var_3B8]
0x18021d00e  mov     rcx, r14
0x18021d011  call    ??$_Emplace@AEBUSNotification@FATNotificationSource@@@?$_Tree@V?$_Tset_traits@USNotification@FATNotificationSource@@U?$less@USNotification@FATNotificationSource@@@std@@V?$allocator@USNotification@FATNotificationSource@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@USNotification@FATNotificationSource@@PEAX@std@@_N@1@AEBUSNotification@FATNotificationSource@@@Z; std::_Tree<std::_Tset_traits<FATNotificationSource::SNotification,std::less<FATNotificationSource::SNotification>,std::allocator<FATNotificationSource::SNotification>,0>>::_Emplace<FATNotificationSource::SNotification const &>(FATNotificationSource::SNotification const &)
0x18021d016  cmp     qword ptr [rbx+10280h], 1
0x18021d01e  jnz     loc_18021D0C1
0x18021d024  cmp     qword ptr [rbx+10290h], 0
0x18021d02c  jnz     short loc_18021D06B
0x18021d02e  xor     r9d, r9d; lpName
0x18021d031  xor     r8d, r8d; bInitialState
0x18021d034  xor     edx, edx; bManualReset
0x18021d036  xor     ecx, ecx; lpEventAttributes
0x18021d038  call    cs:__imp_CreateEventW
0x18021d03e  mov     [rbx+10290h], rax
0x18021d045  test    rax, rax
0x18021d048  jnz     short loc_18021D06B
0x18021d04a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18021d04f  mov     rcx, [rbp+2F8h]; this
0x18021d056  mov     r9d, eax; char *
0x18021d059  lea     r8, aOnecoreuapBase_256; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18021d060  mov     edx, 206h; void *
0x18021d065  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18021d06b  mov     rax, [rbx+10288h]
0x18021d072  test    rax, rax
0x18021d075  jnz     short loc_18021D0B7
0x18021d077  xor     r8d, r8d; pcbe
0x18021d07a  mov     rdx, rbx; pv
0x18021d07d  lea     rcx, ?TPProcessNotificationsCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18021d084  call    cs:__imp_CreateThreadpoolWork
0x18021d08a  mov     [rbx+10288h], rax
0x18021d091  test    rax, rax
0x18021d094  jnz     short loc_18021D0B7
0x18021d096  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18021d09b  mov     rcx, [rbp+2F8h]; this
0x18021d0a2  mov     r9d, eax; char *
0x18021d0a5  lea     r8, aOnecoreuapBase_256; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18021d0ac  mov     edx, 20Eh; void *
0x18021d0b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18021d0b7  mov     rcx, rax; pwk
0x18021d0ba  call    cs:__imp_SubmitThreadpoolWork
0x18021d0c0  nop
0x18021d0c1  lea     rcx, [rsp+3F0h+var_3C0]
0x18021d0c6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18021d0cb  nop
0x18021d0cc  lea     rcx, [rbp+2F0h+var_1E0]; void *
0x18021d0d3  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x18021d0d8  nop
0x18021d0d9  lea     rcx, [rsp+3F0h+var_3A0]; void *
0x18021d0de  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x18021d0e3  mov     rcx, [rbp+2F0h+var_40]
0x18021d0ea  xor     rcx, rsp; StackCookie
0x18021d0ed  call    __security_check_cookie
0x18021d0f2  add     rsp, 3C8h
0x18021d0f9  pop     r15
0x18021d0fb  pop     r14
0x18021d0fd  pop     rdi
0x18021d0fe  pop     rsi
0x18021d0ff  pop     rbx
0x18021d100  pop     rbp
0x18021d101  retn
```
