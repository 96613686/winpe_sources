# DialupConnection::Delete(void)

- ea: `0x18002b060`
- end: `0x18002b1a9`
- name: `?Delete@DialupConnection@@UEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x18000538c`
- `0x1800084fc`
- `0x180019200`
- `0x18002b060`
- `0x18002cf50`
- `0x18002cf80`
- `0x18002d69c`
- `0x18002dbc8`
- `0x180030a00`
- `0x180030a50`
- `0x18003286c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002b07c`
- `KERNEL32!EnterCriticalSection` at `0x18002b07c`
- `RASAPI32!RasDeleteEntryW` at `0x18002b118`
- `RASAPI32!RasDeleteEntryW` at `0x18002b118`

## pseudocode

```c
__int64 __fastcall DialupConnection::Delete(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  RasConnectionBase *p_LockSemaphore; // rdi
  HRESULT v4; // ebx
  const WCHAR *v5; // rbx
  const WCHAR *v6; // rax
  DWORD v7; // eax
  enum tagNETCON_STATUS v9; // [rsp+20h] [rbp-28h] BYREF
  _DWORD v10[4]; // [rsp+28h] [rbp-20h] BYREF
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+38h] [rbp-10h] BYREF

  v1 = this + 8;
  EnterCriticalSection(this + 8);
  p_LockSemaphore = (RasConnectionBase *)&this[2].LockSemaphore;
  v11 = v1;
  if ( !*(_DWORD *)p_LockSemaphore )
  {
    v4 = -2147418113;
LABEL_13:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids,
        (unsigned int)v4);
    goto LABEL_16;
  }
  v10[1] = 1;
  v10[0] = 0;
  v10[3] = 0;
  v4 = CAutoImpersonate::Impersonate((CAutoImpersonate *)v10);
  if ( v4 >= 0 )
  {
    v4 = RasConnectionBase::HrEnsureEntryPropertiesCached(p_LockSemaphore);
    if ( v4 >= 0 )
    {
      v9 = NCS_DISCONNECTED;
      if ( (int)RasConnectionBase::HrGetStatus(p_LockSemaphore, &v9) < 0 || (unsigned int)(v9 - 1) <= 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids);
        v4 = -2147418113;
      }
      else
      {
        v5 = RasConnectionBase::PszwEntryName(p_LockSemaphore);
        v6 = RasConnectionBase::PszwPbkFile(p_LockSemaphore);
        v7 = RasDeleteEntryW(v6, v5);
        v4 = HrFromRasError(v7);
      }
    }
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)v10);
  if ( v4 < 0 )
    goto LABEL_13;
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002b060  mov     [rsp+arg_8], rbx
0x18002b065  mov     [rsp+arg_10], rbp
0x18002b06a  push    rdi
0x18002b06b  sub     rsp, 40h
0x18002b06f  lea     rbx, [rcx+140h]
0x18002b076  mov     rdi, rcx
0x18002b079  mov     rcx, rbx; lpCriticalSection
0x18002b07c  call    cs:__imp_EnterCriticalSection
0x18002b082  add     rdi, 68h ; 'h'
0x18002b086  mov     [rsp+48h+var_10], rbx
0x18002b08b  lea     rbp, WPP_GLOBAL_Control
0x18002b092  cmp     dword ptr [rdi], 0
0x18002b095  jnz     short loc_18002B0A1
0x18002b097  mov     ebx, 8000FFFFh
0x18002b09c  jmp     loc_18002B163
0x18002b0a1  lea     rcx, [rsp+48h+var_20]; this
0x18002b0a6  mov     [rsp+48h+var_1C], 1
0x18002b0ae  mov     [rsp+48h+var_20], 0
0x18002b0b6  mov     [rsp+48h+var_14], 0
0x18002b0be  call    ?Impersonate@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::Impersonate(void)
0x18002b0c3  mov     ebx, eax
0x18002b0c5  test    eax, eax
0x18002b0c7  js      loc_18002B155
0x18002b0cd  mov     rcx, rdi; this
0x18002b0d0  call    ?HrEnsureEntryPropertiesCached@RasConnectionBase@@IEAAJXZ; RasConnectionBase::HrEnsureEntryPropertiesCached(void)
0x18002b0d5  mov     ebx, eax
0x18002b0d7  test    eax, eax
0x18002b0d9  js      short loc_18002B155
0x18002b0db  lea     rdx, [rsp+48h+var_28]; enum tagNETCON_STATUS *
0x18002b0e0  mov     [rsp+48h+var_28], 0
0x18002b0e8  mov     rcx, rdi; this
0x18002b0eb  call    ?HrGetStatus@RasConnectionBase@@IEAAJPEAW4tagNETCON_STATUS@@@Z; RasConnectionBase::HrGetStatus(tagNETCON_STATUS *)
0x18002b0f0  test    eax, eax
0x18002b0f2  js      short loc_18002B129
0x18002b0f4  mov     eax, [rsp+48h+var_28]
0x18002b0f8  dec     eax
0x18002b0fa  cmp     eax, 2
0x18002b0fd  jbe     short loc_18002B129
0x18002b0ff  mov     rcx, rdi; this
0x18002b102  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002b107  mov     rcx, rdi; this
0x18002b10a  mov     rbx, rax
0x18002b10d  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002b112  mov     rdx, rbx; LPCWSTR
0x18002b115  mov     rcx, rax; LPCWSTR
0x18002b118  call    cs:__imp_RasDeleteEntryW
0x18002b11e  mov     ecx, eax; unsigned int
0x18002b120  call    ?HrFromRasError@@YAJK@Z; HrFromRasError(ulong)
0x18002b125  mov     ebx, eax
0x18002b127  jmp     short loc_18002B155
0x18002b129  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b130  cmp     rcx, rbp
0x18002b133  jz      short loc_18002B150
0x18002b135  test    byte ptr [rcx+1Ch], 8
0x18002b139  jz      short loc_18002B150
0x18002b13b  mov     rcx, [rcx+10h]
0x18002b13f  lea     r8, WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids
0x18002b146  mov     edx, 11h
0x18002b14b  call    WPP_SF_
0x18002b150  mov     ebx, 8000FFFFh
0x18002b155  lea     rcx, [rsp+48h+var_20]; this
0x18002b15a  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18002b15f  test    ebx, ebx
0x18002b161  jns     short loc_18002B18D
0x18002b163  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b16a  cmp     rcx, rbp
0x18002b16d  jz      short loc_18002B18D
0x18002b16f  test    byte ptr [rcx+1Ch], 1
0x18002b173  jz      short loc_18002B18D
0x18002b175  mov     rcx, [rcx+10h]
0x18002b179  lea     r8, WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids
0x18002b180  mov     edx, 12h
0x18002b185  mov     r9d, ebx
0x18002b188  call    WPP_SF_d
0x18002b18d  lea     rcx, [rsp+48h+var_10]
0x18002b192  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002b197  mov     rbp, [rsp+48h+arg_10]
0x18002b19c  mov     eax, ebx
0x18002b19e  mov     rbx, [rsp+48h+arg_8]
0x18002b1a3  add     rsp, 40h
0x18002b1a7  pop     rdi
0x18002b1a8  retn
```
