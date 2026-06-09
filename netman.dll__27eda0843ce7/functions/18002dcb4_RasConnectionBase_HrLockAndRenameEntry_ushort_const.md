# RasConnectionBase::HrLockAndRenameEntry(ushort const *)

- ea: `0x18002dcb4`
- end: `0x18002de28`
- name: `?HrLockAndRenameEntry@RasConnectionBase@@IEAAJPEBG@Z`
- size: `372`
- prototype: `__int64 __fastcall(RasConnectionBase *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002cfb0`

## callees

- `0x18000538c`
- `0x1800084fc`
- `0x18002cf50`
- `0x18002cf80`
- `0x18002d220`
- `0x18002d69c`
- `0x18002dcb4`
- `0x180030a00`
- `0x180030a50`
- `0x18003286c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002dd02`
- `KERNEL32!EnterCriticalSection` at `0x18002dd02`
- `RASAPI32!RasRenameEntryW` at `0x18002dd90`
- `RASAPI32!RasRenameEntryW` at `0x18002dd90`
- `RASAPI32!RasValidateEntryNameW` at `0x18002dd1b`
- `RASAPI32!RasValidateEntryNameW` at `0x18002dd1b`

## pseudocode

```c
__int64 __fastcall RasConnectionBase::HrLockAndRenameEntry(RasConnectionBase *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  const WCHAR *v5; // rax
  DWORD v6; // eax
  unsigned int v7; // eax
  const WCHAR *v8; // rbx
  const WCHAR *v9; // rax
  DWORD v10; // eax
  unsigned int v11; // eax
  _DWORD v13[4]; // [rsp+20h] [rbp-38h] BYREF
  char *v14; // [rsp+30h] [rbp-28h] BYREF

  v13[1] = 1;
  v13[0] = 0;
  v13[3] = 0;
  v4 = CAutoImpersonate::Impersonate((CAutoImpersonate *)v13);
  if ( v4 >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    v14 = (char *)this + 216;
    v5 = RasConnectionBase::PszwPbkFile(this);
    v6 = RasValidateEntryNameW(v5, a2);
    v7 = HrFromRasError(v6);
    v4 = v7;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids, v7);
    if ( v4 >= 0 || (unsigned int)HrFromRasError(0xB7u) == v4 )
    {
      v4 = RasConnectionBase::HrEnsureEntryPropertiesCached(this);
      if ( v4 >= 0 )
      {
        v8 = RasConnectionBase::PszwEntryName(this);
        v9 = RasConnectionBase::PszwPbkFile(this);
        v10 = RasRenameEntryW(v9, v8, a2);
        v11 = HrFromRasError(v10);
        v4 = v11;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids, v11);
        if ( v4 >= 0 )
          RasConnectionBase::SetEntryName(this, a2);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v14);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids, (unsigned int)v4);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002dcb4  mov     rax, rsp
0x18002dcb7  mov     [rax+18h], rbx
0x18002dcbb  push    rsi
0x18002dcbc  push    rdi
0x18002dcbd  push    r15
0x18002dcbf  sub     rsp, 40h
0x18002dcc3  mov     rsi, rdx
0x18002dcc6  mov     rdi, rcx
0x18002dcc9  mov     dword ptr [rax-34h], 1
0x18002dcd0  mov     dword ptr [rax-38h], 0
0x18002dcd7  mov     dword ptr [rax-2Ch], 0
0x18002dcde  lea     rcx, [rax-38h]; this
0x18002dce2  call    ?Impersonate@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::Impersonate(void)
0x18002dce7  mov     ebx, eax
0x18002dce9  lea     r15, WPP_GLOBAL_Control
0x18002dcf0  test    eax, eax
0x18002dcf2  js      loc_18002DDE3
0x18002dcf8  lea     rbx, [rdi+0D8h]
0x18002dcff  mov     rcx, rbx; lpCriticalSection
0x18002dd02  call    cs:__imp_EnterCriticalSection
0x18002dd08  mov     [rsp+58h+var_28], rbx
0x18002dd0d  mov     rcx, rdi; this
0x18002dd10  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002dd15  mov     rcx, rax; LPCWSTR
0x18002dd18  mov     rdx, rsi; LPCWSTR
0x18002dd1b  call    cs:__imp_RasValidateEntryNameW
0x18002dd21  mov     ecx, eax; unsigned int
0x18002dd23  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002dd28  mov     ebx, eax
0x18002dd2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd31  cmp     rcx, r15
0x18002dd34  jz      short loc_18002DD54
0x18002dd36  test    byte ptr [rcx+1Ch], 8
0x18002dd3a  jz      short loc_18002DD54
0x18002dd3c  mov     edx, 11h
0x18002dd41  mov     r9d, eax
0x18002dd44  lea     r8, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids
0x18002dd4b  mov     rcx, [rcx+10h]
0x18002dd4f  call    WPP_SF_d
0x18002dd54  test    ebx, ebx
0x18002dd56  jns     short loc_18002DD66
0x18002dd58  mov     ecx, 0B7h; unsigned int
0x18002dd5d  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002dd62  cmp     eax, ebx
0x18002dd64  jnz     short loc_18002DDD9
0x18002dd66  mov     rcx, rdi; this
0x18002dd69  call    ?HrEnsureEntryPropertiesCached@RasConnectionBase@@IEAAJXZ; RasConnectionBase::HrEnsureEntryPropertiesCached(void)
0x18002dd6e  mov     ebx, eax
0x18002dd70  test    eax, eax
0x18002dd72  js      short loc_18002DDD9
0x18002dd74  mov     rcx, rdi; this
0x18002dd77  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002dd7c  mov     rbx, rax
0x18002dd7f  mov     rcx, rdi; this
0x18002dd82  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002dd87  mov     r8, rsi; LPCWSTR
0x18002dd8a  mov     rdx, rbx; LPCWSTR
0x18002dd8d  mov     rcx, rax; LPCWSTR
0x18002dd90  call    cs:__imp_RasRenameEntryW
0x18002dd96  mov     ecx, eax; unsigned int
0x18002dd98  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002dd9d  mov     ebx, eax
0x18002dd9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dda6  cmp     rcx, r15
0x18002dda9  jz      short loc_18002DDC9
0x18002ddab  test    byte ptr [rcx+1Ch], 8
0x18002ddaf  jz      short loc_18002DDC9
0x18002ddb1  mov     edx, 12h
0x18002ddb6  mov     r9d, eax
0x18002ddb9  lea     r8, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids
0x18002ddc0  mov     rcx, [rcx+10h]
0x18002ddc4  call    WPP_SF_d
0x18002ddc9  test    ebx, ebx
0x18002ddcb  js      short loc_18002DDD9
0x18002ddcd  mov     rdx, rsi; unsigned __int16 *
0x18002ddd0  mov     rcx, rdi; this
0x18002ddd3  call    ?SetEntryName@RasConnectionBase@@IEAAXPEBG@Z; RasConnectionBase::SetEntryName(ushort const *)
0x18002ddd8  nop
0x18002ddd9  lea     rcx, [rsp+58h+var_28]
0x18002ddde  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002dde3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ddea  cmp     rcx, r15
0x18002dded  jz      short loc_18002DE0E
0x18002ddef  test    byte ptr [rcx+1Ch], 8
0x18002ddf3  jz      short loc_18002DE0E
0x18002ddf5  mov     edx, 13h
0x18002ddfa  mov     r9d, ebx
0x18002ddfd  lea     r8, WPP_62ccb5046d2c321286aba42ae98ece6a_Traceguids
0x18002de04  mov     rcx, [rcx+10h]
0x18002de08  call    WPP_SF_d
0x18002de0d  nop
0x18002de0e  lea     rcx, [rsp+58h+var_38]; this
0x18002de13  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18002de18  mov     eax, ebx
0x18002de1a  mov     rbx, [rsp+58h+arg_10]
0x18002de1f  add     rsp, 40h
0x18002de23  pop     r15
0x18002de25  pop     rdi
0x18002de26  pop     rsi
0x18002de27  retn
```
