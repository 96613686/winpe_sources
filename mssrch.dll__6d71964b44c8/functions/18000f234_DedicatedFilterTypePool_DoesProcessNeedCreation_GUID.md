# DedicatedFilterTypePool::DoesProcessNeedCreation(_GUID)

- ea: `0x18000f234`
- end: `0x18000f424`
- name: `?DoesProcessNeedCreation@DedicatedFilterTypePool@@QEAA_NU_GUID@@@Z`
- size: `496`
- prototype: `bool(DedicatedFilterTypePool *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000f050`

## callees

- `0x18000f234`
- `0x180012120`
- `0x180012190`
- `0x18002bf00`
- `0x18006b500`
- `0x1800a5d3c`
- `0x1800af7c4`
- `0x1800fc1f8`
- `0x1801244c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f267`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f267`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f2a7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000f2a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f2bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f32c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f2bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f32c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
char __fastcall DedicatedFilterTypePool::DoesProcessNeedCreation(struct _RTL_CRITICAL_SECTION *this, struct _GUID *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  LPOLESTR *v5; // rax
  __int64 v7; // r8
  LPVOID v8; // rcx
  const unsigned __int8 *v9; // rdx
  unsigned __int8 *v10; // r15
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // rax
  __int64 v13; // r11
  _QWORD *LockSemaphore; // rcx
  _QWORD *v15; // rbx
  _QWORD *v16; // r14
  _QWORD *v17; // r8
  unsigned __int8 **v18; // rcx
  LPVOID pv; // [rsp+20h] [rbp-68h] BYREF
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int8 *v21[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v22; // [rsp+40h] [rbp-48h]
  unsigned __int64 v23; // [rsp+48h] [rbp-40h]

  v4 = this + 1;
  EnterCriticalSection(this + 1);
  v20 = v4;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct_empty(v21);
  pv = 0;
  v5 = (LPOLESTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&pv);
  if ( StringFromCLSID(a2, v5) >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)pv + v7) );
    std::wstring::_Assign<wchar_t>(v21);
    v8 = pv;
    if ( pv )
      CoTaskMemFree(pv);
    v9 = (const unsigned __int8 *)v21;
    v10 = v21[0];
    v11 = v23;
    if ( v23 > 7 )
      v9 = v21[0];
    v12 = 2 * (*(_QWORD *)&this[3].LockCount & std::_Fnv1a_append_bytes((unsigned __int64)v8, v9, 2 * v22));
    LockSemaphore = this[2].LockSemaphore;
    v15 = (_QWORD *)LockSemaphore[v12 + 1];
    if ( v15 == *(_QWORD **)&this[2].LockCount )
    {
LABEL_28:
      v15 = 0;
    }
    else
    {
      v16 = (_QWORD *)LockSemaphore[v12];
      while ( 1 )
      {
        v17 = v15 + 2;
        if ( v15[5] > 7u )
          v17 = (_QWORD *)*v17;
        v18 = v21;
        if ( v11 > 7 )
          v18 = (unsigned __int8 **)v10;
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v18, v13, v17, v15[4]) )
          break;
        if ( v15 == v16 )
          goto LABEL_28;
        v15 = (_QWORD *)v15[1];
        v11 = v23;
        v13 = v22;
        v10 = v21[0];
      }
    }
    if ( !v15 || v15 == *(_QWORD **)&this[2].LockCount )
    {
      ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v21);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v20);
      return 1;
    }
    else
    {
      ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v21);
      if ( v4 )
        LeaveCriticalSection(v4);
      return 0;
    }
  }
  else
  {
    if ( pv )
      CoTaskMemFree(pv);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v21);
    if ( v4 )
      LeaveCriticalSection(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x18000f234  mov     [rsp+arg_10], rbx
0x18000f239  mov     [rsp+arg_18], rsi
0x18000f23e  push    rdi
0x18000f23f  push    r12
0x18000f241  push    r13
0x18000f243  push    r14
0x18000f245  push    r15
0x18000f247  sub     rsp, 60h
0x18000f24b  mov     rax, cs:__security_cookie
0x18000f252  xor     rax, rsp
0x18000f255  mov     [rsp+88h+var_38], rax
0x18000f25a  mov     rbx, rdx
0x18000f25d  mov     rsi, rcx
0x18000f260  lea     rdi, [rcx+28h]
0x18000f264  mov     rcx, rdi; lpCriticalSection
0x18000f267  call    cs:__imp_EnterCriticalSection
0x18000f26d  mov     [rsp+88h+var_60], rdi
0x18000f272  xorps   xmm0, xmm0
0x18000f275  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x18000f27a  xor     r13d, r13d
0x18000f27d  mov     [rsp+88h+var_48], r13
0x18000f282  mov     [rsp+88h+var_40], r13
0x18000f287  lea     rcx, [rsp+88h+var_58]
0x18000f28c  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000f291  nop
0x18000f292  mov     [rsp+88h+pv], r13
0x18000f297  lea     rcx, [rsp+88h+pv]
0x18000f29c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(void)
0x18000f2a1  mov     rdx, rax; lplpsz
0x18000f2a4  mov     rcx, rbx; rclsid
0x18000f2a7  call    cs:__imp_StringFromCLSID
0x18000f2ad  test    eax, eax
0x18000f2af  jns     short loc_18000F304
0x18000f2b1  mov     rcx, [rsp+88h+pv]; pv
0x18000f2b6  test    rcx, rcx
0x18000f2b9  jz      short loc_18000F2C2
0x18000f2bb  call    cs:__imp_CoTaskMemFree
0x18000f2c1  nop
0x18000f2c2  lea     rcx, [rsp+88h+var_58]; this
0x18000f2c7  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18000f2cc  nop
0x18000f2cd  test    rdi, rdi
0x18000f2d0  jz      short loc_18000F2DB
0x18000f2d2  mov     rcx, rdi; lpCriticalSection
0x18000f2d5  call    cs:__imp_LeaveCriticalSection
0x18000f2db  xor     al, al
0x18000f2dd  mov     rcx, [rsp+88h+var_38]
0x18000f2e2  xor     rcx, rsp; StackCookie
0x18000f2e5  call    __security_check_cookie
0x18000f2ea  lea     r11, [rsp+88h+var_28]
0x18000f2ef  mov     rbx, [r11+40h]
0x18000f2f3  mov     rsi, [r11+48h]
0x18000f2f7  mov     rsp, r11
0x18000f2fa  pop     r15
0x18000f2fc  pop     r14
0x18000f2fe  pop     r13
0x18000f300  pop     r12
0x18000f302  pop     rdi
0x18000f303  retn
0x18000f304  mov     rdx, [rsp+88h+pv]
0x18000f309  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f30d  inc     r8
0x18000f310  cmp     [rdx+r8*2], r13w
0x18000f315  jnz     short loc_18000F30D
0x18000f317  lea     rcx, [rsp+88h+var_58]
0x18000f31c  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000f321  nop
0x18000f322  mov     rcx, [rsp+88h+pv]; pv
0x18000f327  test    rcx, rcx
0x18000f32a  jz      short loc_18000F333
0x18000f32c  call    cs:__imp_CoTaskMemFree
0x18000f332  nop
0x18000f333  mov     r11, [rsp+88h+var_48]
0x18000f338  lea     rdx, [rsp+88h+var_58]
0x18000f33d  mov     r15, [rsp+88h+var_58]
0x18000f342  mov     r12, [rsp+88h+var_40]
0x18000f347  cmp     r12, 7
0x18000f34b  cmova   rdx, r15; unsigned __int8 *
0x18000f34f  lea     r8, [r11+r11]; unsigned __int64
0x18000f353  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18000f358  and     rax, [rsi+80h]
0x18000f35f  add     rax, rax
0x18000f362  mov     rcx, [rsi+68h]
0x18000f366  mov     rbx, [rcx+rax*8+8]
0x18000f36b  cmp     rbx, [rsi+58h]
0x18000f36f  jz      loc_18000F408
0x18000f375  mov     r14, [rcx+rax*8]
0x18000f379  lea     r8, [rbx+10h]
0x18000f37d  cmp     qword ptr [rbx+28h], 7
0x18000f382  jbe     short loc_18000F387
0x18000f384  mov     r8, [r8]
0x18000f387  lea     rcx, [rsp+88h+var_58]
0x18000f38c  cmp     r12, 7
0x18000f390  cmova   rcx, r15
0x18000f394  mov     r9, [rbx+20h]
0x18000f398  mov     rdx, r11
0x18000f39b  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18000f3a0  test    al, al
0x18000f3a2  jz      short loc_18000F3EB
0x18000f3a4  test    rbx, rbx
0x18000f3a7  jz      short loc_18000F3CF
0x18000f3a9  cmp     rbx, [rsi+58h]
0x18000f3ad  jz      short loc_18000F3CF
0x18000f3af  lea     rcx, [rsp+88h+var_58]; this
0x18000f3b4  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18000f3b9  nop
0x18000f3ba  test    rdi, rdi
0x18000f3bd  jz      short loc_18000F3C8
0x18000f3bf  mov     rcx, rdi; lpCriticalSection
0x18000f3c2  call    cs:__imp_LeaveCriticalSection
0x18000f3c8  xor     al, al
0x18000f3ca  jmp     loc_18000F2DD
0x18000f3cf  lea     rcx, [rsp+88h+var_58]; this
0x18000f3d4  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18000f3d9  nop
0x18000f3da  lea     rcx, [rsp+88h+var_60]
0x18000f3df  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18000f3e4  mov     al, 1
0x18000f3e6  jmp     loc_18000F2DD
0x18000f3eb  cmp     rbx, r14
0x18000f3ee  jz      short loc_18000F408
0x18000f3f0  mov     rbx, [rbx+8]
0x18000f3f4  mov     r12, [rsp+88h+var_40]
0x18000f3f9  mov     r11, [rsp+88h+var_48]
0x18000f3fe  mov     r15, [rsp+88h+var_58]
0x18000f403  jmp     loc_18000F379
0x18000f408  mov     rbx, r13
0x18000f40b  jmp     short loc_18000F3A4
0x18000f40d  lea     rcx, [rsp+88h+var_58]; this
0x18000f412  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18000f417  nop
0x18000f418  lea     rcx, [rsp+88h+var_60]
0x18000f41d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18000f422  jmp     short loc_18000F3C8
```
