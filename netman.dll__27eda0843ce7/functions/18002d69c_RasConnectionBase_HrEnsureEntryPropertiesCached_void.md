# RasConnectionBase::HrEnsureEntryPropertiesCached(void)

- ea: `0x18002d69c`
- end: `0x18002d927`
- name: `?HrEnsureEntryPropertiesCached@RasConnectionBase@@IEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(RasConnectionBase *__hidden this)`
- caller_count: `13`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002b060`
- `0x18002b2d0`
- `0x18002b7d0`
- `0x18002bc80`
- `0x18002bd30`
- `0x18002c340`
- `0x18002c86c`
- `0x18002c960`
- `0x18002d0c0`
- `0x18002d930`
- `0x18002dabc`
- `0x18002dcb4`
- `0x18002e050`

## callees

- `0x1800052b4`
- `0x18000538c`
- `0x1800084fc`
- `0x180019c9c`
- `0x18002cf50`
- `0x18002cf80`
- `0x18002d42c`
- `0x18002d69c`
- `0x180030a00`
- `0x180030a50`
- `0x18003286c`
- `0x1800329b8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002d6c5`
- `KERNEL32!EnterCriticalSection` at `0x18002d6c5`
- `KERNEL32!lstrcmpW` at `0x18002d841`
- `KERNEL32!lstrcmpW` at `0x18002d841`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RasConnectionBase::HrEnsureEntryPropertiesCached(RasConnectionBase *this)
{
  RasConnectionBase *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // edi
  unsigned int v4; // r14d
  const unsigned __int16 *v5; // rax
  __int64 v6; // rax
  BOOL v7; // r13d
  unsigned int i; // r12d
  char *v9; // r15
  __int64 v10; // rax
  const unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  const WCHAR *v13; // rax
  unsigned int v15; // [rsp+20h] [rbp-58h] BYREF
  RasConnectionBase *v16; // [rsp+28h] [rbp-50h]
  void *lpMem; // [rsp+30h] [rbp-48h] BYREF
  _DWORD v18[4]; // [rsp+38h] [rbp-40h] BYREF
  struct _RTL_CRITICAL_SECTION *v19; // [rsp+48h] [rbp-30h] BYREF

  v1 = this;
  v16 = this;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v19 = v2;
  if ( *((_DWORD *)v1 + 14) )
  {
    v3 = 0;
    if ( *((_DWORD *)v1 + 15) == g_lRasEntryModifiedVersionEra )
      goto LABEL_34;
  }
  lpMem = 0;
  v4 = 0;
  v15 = 0;
  v18[1] = 1;
  v18[0] = 0;
  v18[3] = 0;
  v3 = CAutoImpersonate::Impersonate((CAutoImpersonate *)v18);
  if ( v3 >= 0 )
  {
    v5 = RasConnectionBase::PszwPbkFile(v1);
    v3 = HrRasEnumAllEntriesWithDetails(v5, (struct _RASENUMENTRYDETAILS **)&lpMem, &v15);
    v4 = v15;
    if ( !lpMem || !v15 )
      v3 = HrFromRasError(0x490u);
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)v18);
  if ( v3 >= 0 )
  {
    v6 = *((_QWORD *)v1 + 5) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v6 )
      v6 = *((_QWORD *)v1 + 6) - *(_QWORD *)GUID_NULL.Data4;
    v7 = v6 == 0;
    v3 = HrFromRasError(0x490u);
    for ( i = 0; ; ++i )
    {
      if ( i >= v4 )
        goto LABEL_27;
      v9 = (char *)lpMem + 3672 * i;
      v10 = *(_QWORD *)(v9 + 12) - *((_QWORD *)v1 + 5);
      if ( !v10 )
        v10 = *(_QWORD *)(v9 + 20) - *((_QWORD *)v1 + 6);
      if ( !v10 )
      {
        try
        {
          RasConnectionBase::CacheProperties(v1, (const struct _RASENUMENTRYDETAILS *)((char *)lpMem + 3672 * i));
          v3 = 0;
        }
        catch ( std::length_error )
        {
          v15 = HrFromRasError(0x18u);
          v1 = v16;
          v3 = v15;
        }
        catch ( std::bad_alloc )
        {
          v15 = -2147024882;
          v1 = v16;
          v3 = -2147024882;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v11 = RasConnectionBase::PszwEntryName(v1);
          v12 = 13;
LABEL_19:
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids, v11);
          goto LABEL_27;
        }
        goto LABEL_27;
      }
      if ( v7 )
      {
        v13 = RasConnectionBase::PszwEntryName(v1);
        if ( !lstrcmpW(v13, (LPCWSTR)v9 + 148) )
          break;
      }
    }
    try
    {
      RasConnectionBase::CacheProperties(v1, (const struct _RASENUMENTRYDETAILS *)v9);
      v3 = 0;
    }
    catch ( std::length_error )
    {
      v15 = HrFromRasError(0x18u);
      v1 = v16;
      v3 = v15;
    }
    catch ( std::bad_alloc )
    {
      v15 = -2147024882;
      v1 = v16;
      v3 = -2147024882;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v11 = RasConnectionBase::PszwEntryName(v1);
      v12 = 14;
      goto LABEL_19;
    }
LABEL_27:
    MemFree(lpMem);
LABEL_30:
    if ( v3 >= 0 )
      goto LABEL_34;
    goto LABEL_31;
  }
  if ( (unsigned int)HrFromRasError(0x26Du) == v3 )
  {
    v3 = HrFromRasError(0x490u);
    goto LABEL_30;
  }
LABEL_31:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids, (unsigned int)v3);
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v19);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002d69c  mov     [rsp+arg_8], rbx
0x18002d6a1  mov     [rsp+arg_10], rsi
0x18002d6a6  push    rdi
0x18002d6a7  push    r12
0x18002d6a9  push    r13
0x18002d6ab  push    r14
0x18002d6ad  push    r15
0x18002d6af  sub     rsp, 50h
0x18002d6b3  mov     rsi, rcx
0x18002d6b6  mov     [rsp+78h+var_50], rcx
0x18002d6bb  lea     rbx, [rcx+0D8h]
0x18002d6c2  mov     rcx, rbx; lpCriticalSection
0x18002d6c5  call    cs:__imp_EnterCriticalSection
0x18002d6cb  mov     [rsp+78h+var_30], rbx
0x18002d6d0  cmp     dword ptr [rsi+38h], 0
0x18002d6d4  jz      short loc_18002D6E7
0x18002d6d6  xor     edi, edi
0x18002d6d8  mov     eax, cs:?g_lRasEntryModifiedVersionEra@@3JA; long g_lRasEntryModifiedVersionEra
0x18002d6de  cmp     [rsi+3Ch], eax
0x18002d6e1  jz      loc_18002D901
0x18002d6e7  mov     [rsp+78h+lpMem], 0
0x18002d6f0  xor     r14d, r14d
0x18002d6f3  mov     [rsp+78h+var_58], r14d
0x18002d6f8  mov     [rsp+78h+var_3C], 1
0x18002d700  mov     [rsp+78h+var_40], r14d
0x18002d705  mov     [rsp+78h+var_34], r14d
0x18002d70a  lea     rcx, [rsp+78h+var_40]; this
0x18002d70f  call    ?Impersonate@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::Impersonate(void)
0x18002d714  mov     edi, eax
0x18002d716  test    eax, eax
0x18002d718  js      short loc_18002D754
0x18002d71a  mov     rcx, rsi; this
0x18002d71d  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002d722  mov     rcx, rax; unsigned __int16 *
0x18002d725  lea     r8, [rsp+78h+var_58]; unsigned int *
0x18002d72a  lea     rdx, [rsp+78h+lpMem]; struct _RASENUMENTRYDETAILS **
0x18002d72f  call    ?HrRasEnumAllEntriesWithDetails@@YAJPEBGPEAPEAU_RASENUMENTRYDETAILS@@PEAK@Z; HrRasEnumAllEntriesWithDetails(ushort const *,_RASENUMENTRYDETAILS * *,ulong *)
0x18002d734  mov     edi, eax
0x18002d736  mov     r14d, [rsp+78h+var_58]
0x18002d73b  cmp     [rsp+78h+lpMem], 0
0x18002d741  jz      short loc_18002D748
0x18002d743  test    r14d, r14d
0x18002d746  jnz     short loc_18002D754
0x18002d748  mov     ecx, 490h; unsigned int
0x18002d74d  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002d752  mov     edi, eax
0x18002d754  lea     rcx, [rsp+78h+var_40]; this
0x18002d759  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18002d75e  test    edi, edi
0x18002d760  js      loc_18002D8A8
0x18002d766  mov     rax, [rsi+28h]
0x18002d76a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18002d771  jnz     short loc_18002D77E
0x18002d773  mov     rax, [rsi+30h]
0x18002d777  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18002d77e  xor     r13d, r13d
0x18002d781  test    rax, rax
0x18002d784  setz    r13b
0x18002d788  mov     ecx, 490h; unsigned int
0x18002d78d  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002d792  mov     edi, eax
0x18002d794  xor     r12d, r12d
0x18002d797  cmp     r12d, r14d
0x18002d79a  jnb     loc_18002D895
0x18002d7a0  mov     eax, r12d
0x18002d7a3  imul    r15, rax, 0E58h
0x18002d7aa  add     r15, [rsp+78h+lpMem]
0x18002d7af  mov     rax, [r15+0Ch]
0x18002d7b3  sub     rax, [rsi+28h]
0x18002d7b7  jnz     short loc_18002D7C1
0x18002d7b9  mov     rax, [r15+14h]
0x18002d7bd  sub     rax, [rsi+30h]
0x18002d7c1  test    rax, rax
0x18002d7c4  jnz     short loc_18002D82A
0x18002d7c6  mov     rdx, r15; struct _RASENUMENTRYDETAILS *
0x18002d7c9  mov     rcx, rsi; this
0x18002d7cc  call    ?CacheProperties@RasConnectionBase@@IEAAXPEBU_RASENUMENTRYDETAILS@@@Z; RasConnectionBase::CacheProperties(_RASENUMENTRYDETAILS const *)
0x18002d7d1  xor     edi, edi
0x18002d7d3  jmp     short loc_18002D7E0
0x18002d7d5  jmp     short $+2
0x18002d7d7  mov     rsi, [rsp+78h+var_50]
0x18002d7dc  mov     edi, [rsp+78h+var_58]
0x18002d7e0  lea     rbx, WPP_GLOBAL_Control
0x18002d7e7  mov     rax, cs:WPP_GLOBAL_Control
0x18002d7ee  cmp     rax, rbx
0x18002d7f1  jz      loc_18002D89C
0x18002d7f7  test    byte ptr [rax+1Ch], 8
0x18002d7fb  jz      loc_18002D89C
0x18002d801  mov     rcx, rsi; this
0x18002d804  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002d809  mov     edx, 0Dh
0x18002d80e  mov     r9, rax
0x18002d811  lea     r8, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids
0x18002d818  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d81f  mov     rcx, [rcx+10h]
0x18002d823  call    WPP_SF_S
0x18002d828  jmp     short loc_18002D89C
0x18002d82a  test    r13d, r13d
0x18002d82d  jz      short loc_18002D88D
0x18002d82f  mov     rcx, rsi; this
0x18002d832  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002d837  mov     rcx, rax; lpString1
0x18002d83a  lea     rdx, [r15+128h]; lpString2
0x18002d841  call    cs:__imp_lstrcmpW
0x18002d847  test    eax, eax
0x18002d849  jnz     short loc_18002D88D
0x18002d84b  mov     rdx, r15; struct _RASENUMENTRYDETAILS *
0x18002d84e  mov     rcx, rsi; this
0x18002d851  call    ?CacheProperties@RasConnectionBase@@IEAAXPEBU_RASENUMENTRYDETAILS@@@Z; RasConnectionBase::CacheProperties(_RASENUMENTRYDETAILS const *)
0x18002d856  xor     edi, edi
0x18002d858  jmp     short loc_18002D865
0x18002d85a  jmp     short $+2
0x18002d85c  mov     rsi, [rsp+78h+var_50]
0x18002d861  mov     edi, [rsp+78h+var_58]
0x18002d865  lea     rbx, WPP_GLOBAL_Control
0x18002d86c  mov     rax, cs:WPP_GLOBAL_Control
0x18002d873  cmp     rax, rbx
0x18002d876  jz      short loc_18002D89C
0x18002d878  test    byte ptr [rax+1Ch], 8
0x18002d87c  jz      short loc_18002D89C
0x18002d87e  mov     rcx, rsi; this
0x18002d881  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002d886  mov     edx, 0Eh
0x18002d88b  jmp     short loc_18002D80E
0x18002d88d  inc     r12d
0x18002d890  jmp     loc_18002D797
0x18002d895  lea     rbx, WPP_GLOBAL_Control
0x18002d89c  mov     rcx, [rsp+78h+lpMem]; lpMem
0x18002d8a1  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18002d8a6  jmp     short loc_18002D8C9
0x18002d8a8  mov     ecx, 26Dh; unsigned int
0x18002d8ad  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002d8b2  cmp     eax, edi
0x18002d8b4  jnz     short loc_18002D8CF
0x18002d8b6  mov     ecx, 490h; unsigned int
0x18002d8bb  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002d8c0  mov     edi, eax
0x18002d8c2  lea     rbx, WPP_GLOBAL_Control
0x18002d8c9  test    edi, edi
0x18002d8cb  jns     short loc_18002D901
0x18002d8cd  jmp     short loc_18002D8D6
0x18002d8cf  lea     rbx, WPP_GLOBAL_Control
0x18002d8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8dd  cmp     rcx, rbx
0x18002d8e0  jz      short loc_18002D901
0x18002d8e2  test    byte ptr [rcx+1Ch], 1
0x18002d8e6  jz      short loc_18002D901
0x18002d8e8  mov     edx, 0Fh
0x18002d8ed  mov     r9d, edi
0x18002d8f0  lea     r8, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids
0x18002d8f7  mov     rcx, [rcx+10h]
0x18002d8fb  call    WPP_SF_d
0x18002d900  nop
0x18002d901  lea     rcx, [rsp+78h+var_30]
0x18002d906  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002d90b  mov     eax, edi
0x18002d90d  lea     r11, [rsp+78h+var_28]
0x18002d912  mov     rbx, [r11+38h]
0x18002d916  mov     rsi, [r11+40h]
0x18002d91a  mov     rsp, r11
0x18002d91d  pop     r15
0x18002d91f  pop     r14
0x18002d921  pop     r13
0x18002d923  pop     r12
0x18002d925  pop     rdi
0x18002d926  retn
```
