# LampArrayRawInputProvider::UpdateDeviceAmbientProcess(void)

- ea: `0x180124130`
- end: `0x1801243b0`
- name: `?UpdateDeviceAmbientProcess@LampArrayRawInputProvider@@AEAAXXZ`
- size: `640`
- prototype: `void __fastcall(LampArrayRawInputProvider *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180123b10`

## callees

- `0x18002fea0`
- `0x180055b40`
- `0x180064a30`
- `0x180068400`
- `0x180089a1c`
- `0x1800f0990`
- `0x180123480`
- `0x180124130`
- `0x180125ab0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180124164`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180124164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180124237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180124237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180124252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180124252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801241c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180124203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180124285`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801242ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012436a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801241c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180124203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180124285`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801242ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012436a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180124227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180124227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801242be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801242be`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall LampArrayRawInputProvider::UpdateDeviceAmbientProcess(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // r14
  RTL_SRWLOCK *Ptr; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  void (__fastcall *v7)(_QWORD *, HSTRING *); // rbx
  RTL_SRWLOCK *i; // rbx
  HSTRING v9; // rcx
  volatile signed __int32 *v10; // rdi
  const WCHAR *v11; // rcx
  __int64 v12; // rdx
  HSTRING StringRawBuffer; // rax
  int v14; // r8d
  int v15; // r9d
  HSTRING v16; // rbx
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rbx
  HSTRING string; // [rsp+30h] [rbp-59h] BYREF
  HSTRING string1; // [rsp+38h] [rbp-51h] BYREF
  INT32 result; // [rsp+40h] [rbp-49h] BYREF
  const char *v23; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-39h] BYREF
  char v25[16]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v26[32]; // [rsp+70h] [rbp-19h] BYREF

  v2 = this + 19;
  AcquireSRWLockExclusive(this + 19);
  v24[0] = v2;
  v3 = this + 15;
  Ptr = (RTL_SRWLOCK *)this[15].Ptr;
  v5 = Ptr->Ptr;
  if ( Ptr[1].Ptr != &this[15] )
LABEL_25:
    __fastfail(3u);
  while ( 1 )
  {
    if ( (RTL_SRWLOCK *)v5[1] != Ptr )
      goto LABEL_25;
    v3->Ptr = v5;
    v5[1] = v3;
    if ( Ptr == v3 )
      break;
    --LODWORD(this[17].Ptr);
    if ( !Ptr )
      break;
    string1 = 0;
    v24[1] = 0;
    v6 = Ptr[2].Ptr;
    v7 = *(void (__fastcall **)(_QWORD *, HSTRING *))(*v6 + 48LL);
    WindowsDeleteString(0);
    string1 = 0;
    v7(v6, &string1);
    for ( i = (RTL_SRWLOCK *)this[9].Ptr; i != &this[9]; i = (RTL_SRWLOCK *)i->Ptr )
    {
      v9 = 0;
      string = 0;
      v10 = (volatile signed __int32 *)i[2].Ptr;
      if ( v10 )
      {
        _InterlockedIncrement(v10 + 2);
        v9 = string;
      }
      WindowsDeleteString(v9);
      string = 0;
      v11 = (const WCHAR *)(*((_QWORD *)v10 + 3) + 24LL);
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      WindowsCreateString(v11, v12, &string);
      if ( string )
      {
        if ( WindowsGetStringLen(string1) >= 4 )
        {
          result = 0;
          if ( WindowsCompareStringOrdinal(string1, string, &result) >= 0 && !result )
          {
            LampArrayDevice::SetAmbientPids(
              (LampArrayDevice *)v10,
              (struct Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs *)Ptr[2].Ptr);
            InputContext::Release((InputContext *)v10);
            WindowsDeleteString(string);
            goto LABEL_24;
          }
        }
      }
      InputContext::Release((InputContext *)v10);
      WindowsDeleteString(string);
    }
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(string1, 0);
    v16 = StringRawBuffer;
    if ( (unsigned int)dword_180241248 > 5 )
    {
      string = StringRawBuffer;
      v23 = "Adding ambient PIDs to pending list";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_180241248,
        (unsigned int)&byte_18020725F,
        v14,
        v15,
        (__int64)&v23,
        (__int64)&string);
    }
    std::wstring::wstring(v26, v16);
    v17 = std::map<std::wstring,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>::_Try_emplace<std::wstring,>(
            &this[46],
            v25,
            v26);
    v18 = Ptr[2].Ptr;
    v19 = *(_QWORD *)(*(_QWORD *)v17 + 64LL);
    *(_QWORD *)(*(_QWORD *)v17 + 64LL) = v18;
    if ( v18 )
      (*(void (__fastcall **)(_QWORD *))(*v18 + 8LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    std::wstring::_Tidy_deallocate(v26);
LABEL_24:
    WindowsDeleteString(string1);
    Ptr = (RTL_SRWLOCK *)v3->Ptr;
    v5 = *(_QWORD **)v3->Ptr;
    if ( *((RTL_SRWLOCK **)v3->Ptr + 1) != v3 )
      goto LABEL_25;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v24);
}

```

## disassembly

```asm
0x180124130  push    rbp
0x180124132  push    rbx
0x180124133  push    rsi
0x180124134  push    rdi
0x180124135  push    r12
0x180124137  push    r13
0x180124139  push    r14
0x18012413b  push    r15
0x18012413d  lea     rbp, [rsp-1Fh]
0x180124142  sub     rsp, 0A8h
0x180124149  mov     rax, cs:__security_cookie
0x180124150  xor     rax, rsp
0x180124153  mov     [rbp+57h+var_50], rax
0x180124157  mov     r15, rcx
0x18012415a  lea     rbx, [rcx+98h]
0x180124161  mov     rcx, rbx; SRWLock
0x180124164  call    cs:__imp_AcquireSRWLockExclusive
0x18012416a  mov     [rbp+57h+var_90], rbx
0x18012416e  lea     r14, [r15+78h]
0x180124172  mov     rsi, [r14]
0x180124175  mov     rax, [rsi]
0x180124178  cmp     [rsi+8], r14
0x18012417c  jnz     loc_180124380
0x180124182  xor     r13d, r13d
0x180124185  cmp     [rax+8], rsi
0x180124189  jnz     loc_180124380
0x18012418f  mov     [r14], rax
0x180124192  mov     [rax+8], r14
0x180124196  cmp     rsi, r14
0x180124199  jz      loc_180124387
0x18012419f  dec     dword ptr [r14+10h]
0x1801241a3  test    rsi, rsi
0x1801241a6  jz      loc_180124387
0x1801241ac  mov     [rbp+57h+string1], r13
0x1801241b0  mov     [rbp+57h+var_88], r13
0x1801241b4  mov     rdi, [rsi+10h]
0x1801241b8  mov     rax, [rdi]
0x1801241bb  mov     rbx, [rax+30h]
0x1801241bf  xor     ecx, ecx; string
0x1801241c1  call    cs:__imp_WindowsDeleteString
0x1801241c7  mov     [rbp+57h+string1], r13
0x1801241cb  lea     rdx, [rbp+57h+string1]
0x1801241cf  mov     rcx, rdi
0x1801241d2  mov     rax, rbx
0x1801241d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801241da  lea     r12, [r15+48h]
0x1801241de  mov     rbx, [r12]
0x1801241e2  cmp     rbx, r12
0x1801241e5  jz      loc_1801242B8
0x1801241eb  mov     rcx, r13
0x1801241ee  mov     [rbp+57h+string], rcx
0x1801241f2  mov     rdi, [rbx+10h]
0x1801241f6  test    rdi, rdi
0x1801241f9  jz      short loc_180124203
0x1801241fb  lock inc dword ptr [rdi+8]
0x1801241ff  mov     rcx, [rbp+57h+string]; string
0x180124203  call    cs:__imp_WindowsDeleteString
0x180124209  mov     [rbp+57h+string], r13
0x18012420d  mov     rcx, [rdi+18h]
0x180124211  add     rcx, 18h; sourceString
0x180124215  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180124219  inc     rdx; length
0x18012421c  cmp     [rcx+rdx*2], r13w
0x180124221  jnz     short loc_180124219
0x180124223  lea     r8, [rbp+57h+string]; string
0x180124227  call    cs:__imp_WindowsCreateString
0x18012422d  cmp     [rbp+57h+string], r13
0x180124231  jz      short loc_180124278
0x180124233  mov     rcx, [rbp+57h+string1]; string
0x180124237  call    cs:__imp_WindowsGetStringLen
0x18012423d  cmp     eax, 4
0x180124240  jb      short loc_180124278
0x180124242  mov     [rbp+57h+result], r13d
0x180124246  lea     r8, [rbp+57h+result]; result
0x18012424a  mov     rdx, [rbp+57h+string]; string2
0x18012424e  mov     rcx, [rbp+57h+string1]; string1
0x180124252  call    cs:__imp_WindowsCompareStringOrdinal
0x180124258  test    eax, eax
0x18012425a  jns     short loc_180124267
0x18012425c  mov     rcx, rdi; this
0x18012425f  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180124264  nop
0x180124265  jmp     short loc_180124281
0x180124267  cmp     [rbp+57h+result], r13d
0x18012426b  jz      short loc_180124293
0x18012426d  mov     rcx, rdi; this
0x180124270  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180124275  nop
0x180124276  jmp     short loc_180124281
0x180124278  mov     rcx, rdi; this
0x18012427b  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x180124280  nop
0x180124281  mov     rcx, [rbp+57h+string]; string
0x180124285  call    cs:__imp_WindowsDeleteString
0x18012428b  mov     rbx, [rbx]
0x18012428e  jmp     loc_1801241E2
0x180124293  mov     rdx, [rsi+10h]; struct Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs *
0x180124297  mov     rcx, rdi; this
0x18012429a  call    ?SetAmbientPids@LampArrayDevice@@QEAAXPEAUIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@@Z; LampArrayDevice::SetAmbientPids(Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs *)
0x18012429f  nop
0x1801242a0  mov     rcx, rdi; this
0x1801242a3  call    ?Release@InputContext@@UEAAKXZ; InputContext::Release(void)
0x1801242a8  nop
0x1801242a9  mov     rcx, [rbp+57h+string]; string
0x1801242ad  call    cs:__imp_WindowsDeleteString
0x1801242b3  jmp     loc_180124366
0x1801242b8  xor     edx, edx; length
0x1801242ba  mov     rcx, [rbp+57h+string1]; string
0x1801242be  call    cs:__imp_WindowsGetStringRawBuffer
0x1801242c4  mov     rbx, rax
0x1801242c7  mov     ecx, cs:dword_180241248
0x1801242cd  cmp     ecx, 5
0x1801242d0  jbe     short loc_180124306
0x1801242d2  mov     [rbp+57h+string], rax
0x1801242d6  lea     rax, aAddingAmbientP; "Adding ambient PIDs to pending list"
0x1801242dd  mov     [rbp+57h+var_98], rax
0x1801242e1  lea     rax, [rbp+57h+string]
0x1801242e5  mov     [rsp+0E0h+var_B8], rax
0x1801242ea  lea     rax, [rbp+57h+var_98]
0x1801242ee  mov     [rsp+0E0h+var_C0], rax
0x1801242f3  lea     rdx, byte_18020725F
0x1801242fa  lea     rcx, dword_180241248
0x180124301  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180124306  mov     rdx, rbx
0x180124309  lea     rcx, [rbp+57h+var_70]
0x18012430d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180124312  nop
0x180124313  lea     rcx, [r15+170h]
0x18012431a  lea     r8, [rbp+57h+var_70]
0x18012431e  lea     rdx, [rbp+57h+var_80]
0x180124322  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x180124327  mov     rdx, [rax]
0x18012432a  mov     rcx, [rsi+10h]
0x18012432e  mov     rbx, [rdx+40h]
0x180124332  mov     [rdx+40h], rcx
0x180124336  test    rcx, rcx
0x180124339  jz      short loc_180124347
0x18012433b  mov     rax, [rcx]
0x18012433e  mov     rax, [rax+8]
0x180124342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124347  test    rbx, rbx
0x18012434a  jz      short loc_18012435C
0x18012434c  mov     rax, [rbx]
0x18012434f  mov     rcx, rbx
0x180124352  mov     rax, [rax+10h]
0x180124356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012435b  nop
0x18012435c  lea     rcx, [rbp+57h+var_70]
0x180124360  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180124365  nop
0x180124366  mov     rcx, [rbp+57h+string1]; string
0x18012436a  call    cs:__imp_WindowsDeleteString
0x180124370  mov     rsi, [r14]
0x180124373  mov     rax, [rsi]
0x180124376  cmp     [rsi+8], r14
0x18012437a  jz      loc_180124185
0x180124380  mov     ecx, 3
0x180124385  int     29h; Win8: RtlFailFast(ecx)
0x180124387  lea     rcx, [rbp+57h+var_90]
0x18012438b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180124390  mov     rcx, [rbp+57h+var_50]
0x180124394  xor     rcx, rsp; StackCookie
0x180124397  call    __security_check_cookie
0x18012439c  add     rsp, 0A8h
0x1801243a3  pop     r15
0x1801243a5  pop     r14
0x1801243a7  pop     r13
0x1801243a9  pop     r12
0x1801243ab  pop     rdi
0x1801243ac  pop     rsi
0x1801243ad  pop     rbx
0x1801243ae  pop     rbp
0x1801243af  retn
```
