# URL_INFO::Connect(IHttpInterface *,HttpSecurityData const &,EidAsyncHelper &,bool)

- ea: `0x1800548e4`
- end: `0x180054dc8`
- name: `?Connect@URL_INFO@@QEAAXPEAVIHttpInterface@@AEBUHttpSecurityData@@AEAVEidAsyncHelper@@_N@Z`
- size: `1252`
- prototype: `void __fastcall(const WCHAR **this, struct IHttpInterface *, const struct HttpSecurityData *, struct _RTL_CRITICAL_SECTION *, bool)`
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bc5e0`
- `0x1800bc9d8`
- `0x1800bf280`

## callees

- `0x180006640`
- `0x1800066f0`
- `0x180006a78`
- `0x1800073f0`
- `0x180008b70`
- `0x18000db20`
- `0x18000e370`
- `0x180014310`
- `0x1800377b8`
- `0x1800548e4`
- `0x180054ea0`
- `0x1800554b0`
- `0x18009d024`
- `0x1800a1114`
- `0x1800a3444`
- `0x1800f6ee8`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180054b37`
- `ntdll!RtlAdjustPrivilege` at `0x180054bd9`
- `ntdll!RtlAdjustPrivilege` at `0x180054b37`
- `ntdll!RtlAdjustPrivilege` at `0x180054bd9`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800549c7`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800549c7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180054c25`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180054c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054d71`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005496f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005496f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180054abd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180054abd`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall URL_INFO::Connect(
        const WCHAR **this,
        struct IHttpInterface *a2,
        const struct HttpSecurityData *a3,
        struct _RTL_CRITICAL_SECTION *a4,
        bool a5)
{
  const WCHAR *v9; // rbx
  _DWORD *v10; // rax
  signed int LastError; // eax
  unsigned int v12; // ecx
  const WCHAR *v13; // r14
  EVENT_LOG *v14; // rcx
  const unsigned __int16 **v15; // rsi
  unsigned __int16 *v16; // rcx
  const unsigned __int16 *v17; // r14
  unsigned int v18; // ecx
  NTSTATUS v19; // eax
  int v20; // ecx
  HANDLE *v21; // rbx
  NTSTATUS v22; // eax
  int v23; // ecx
  NTSTATUS v24; // eax
  int v25; // ecx
  unsigned int v26; // ecx
  WCHAR *Session; // rax
  int v28; // ecx
  const WCHAR *v29; // r8
  unsigned int v30; // ecx
  void **pExceptionObject; // [rsp+30h] [rbp-91h] BYREF
  __int128 v32; // [rsp+38h] [rbp-89h]
  unsigned int v33; // [rsp+48h] [rbp-79h]
  int v34; // [rsp+4Ch] [rbp-75h]
  int v35; // [rsp+50h] [rbp-71h]
  HANDLE *v36; // [rsp+90h] [rbp-31h] BYREF
  char v37[8]; // [rsp+98h] [rbp-29h] BYREF
  char v38; // [rsp+A0h] [rbp-21h]
  __int64 v39; // [rsp+A8h] [rbp-19h]
  __int64 v40; // [rsp+B0h] [rbp-11h]
  _DWORD *v41; // [rsp+B8h] [rbp-9h]
  __int64 v42; // [rsp+C0h] [rbp-1h]
  void *v43; // [rsp+C8h] [rbp+7h]
  unsigned __int8 OldValue; // [rsp+120h] [rbp+5Fh] BYREF

  URL_INFO::CheckAndCreateProxySettingsContainerIfNeeded((URL_INFO *)this);
  v9 = this[6];
  CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)v37);
  v38 = 0;
  v39 = *(_QWORD *)v9;
  _InterlockedAdd((volatile signed __int32 *)(v39 + 8), 1u);
  v40 = 0;
  v10 = operator new(4u);
  if ( v10 )
    *v10 = 1;
  else
    v10 = 0;
  v41 = v10;
  v42 = 0;
  _InterlockedAdd(&dword_180145058, 1u);
  v43 = &GenericStringHandle<unsigned short>::s_EmptyString;
  if ( !v38 )
  {
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)v39) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v12;
      v34 = 0;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v38 = 1;
  }
  v13 = this[140];
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_16528e1573683c34a7ff296cba86f7f8_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
    v15 = this + 4;
  }
  else
  {
    v15 = this + 4;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_16528e1573683c34a7ff296cba86f7f8_Traceguids, v13);
    v16 = (unsigned __int16 *)*v15;
    *v15 = 0;
    if ( v16 )
      operator delete(v16, 2u);
    EidAsyncHelper::StartGetEidAsync(a4, v13);
    EidAsyncHelper::WaitForEnterpriseId(a4);
    v14 = WPP_GLOBAL_Control;
  }
  v17 = *v15;
  if ( v14 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)v14 + 2), 26, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, *v15);
  if ( v17 && *v17 )
  {
    CopyThreadToken(&v36);
    if ( !RevertToSelf() )
    {
      if ( (int)GetLastError() > 0 )
        v18 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v18 = GetLastError();
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v18;
      v34 = 584;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    OldValue = 0;
    v19 = RtlAdjustPrivilege(7u, 1u, 0, &OldValue);
    v20 = NtStatusToHResult(v19);
    if ( v20 < 0 )
    {
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v20;
      v34 = 588;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v21 = v36;
    v22 = SrpSetTokenEnterpriseExempt(*v36);
    v23 = NtStatusToHResult(v22);
    if ( v23 < 0 )
    {
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v23;
      v34 = 590;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v24 = RtlAdjustPrivilege(7u, OldValue, 0, &OldValue);
    v25 = NtStatusToHResult(v24);
    if ( v25 < 0 )
    {
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v25;
      v34 = 593;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( !SetThreadToken(0, *v21) )
    {
      if ( (int)GetLastError() > 0 )
        v26 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v26 = GetLastError();
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v26;
      v34 = 597;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    TokenHandle::Decrement((TokenHandle *)&v36);
  }
  Session = (WCHAR *)HttpSessionCache::GetSession(v14, a3, a2, *v15, a5);
  *this = Session;
  EnablePassport((struct IHttpSession *)Session);
  this[1] = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD, const WCHAR *, _QWORD))(*(_QWORD *)*this + 8LL))(
                             *this,
                             this[140],
                             *((unsigned __int16 *)this + 30));
  CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)v37);
  if ( *((_BYTE *)this + 18) )
  {
    if ( *(_DWORD *)this[8] )
    {
      v28 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*this + 24LL))(*this);
      if ( v28 < 0 )
      {
        v32 = 0;
        pExceptionObject = &ComError::`vftable';
        v33 = v28;
        v34 = 5057;
        v35 = 1;
        throw (ComError *)&pExceptionObject;
      }
    }
  }
  v29 = this[10];
  if ( v29
    && !(*(unsigned int (__fastcall **)(const WCHAR *, __int64, const WCHAR *, __int64))(*(_QWORD *)this[1] + 16LL))(
          this[1],
          131,
          v29,
          232) )
  {
    if ( (int)GetLastError() > 0 )
      v30 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v30 = GetLastError();
    v32 = 0;
    pExceptionObject = &ComError::`vftable';
    v33 = v30;
    v34 = 5064;
    v35 = 1;
    throw (ComError *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800548e4  push    rbp
0x1800548e6  push    rbx
0x1800548e7  push    rsi
0x1800548e8  push    rdi
0x1800548e9  push    r12
0x1800548eb  push    r13
0x1800548ed  push    r14
0x1800548ef  push    r15
0x1800548f1  lea     rbp, [rsp-17h]
0x1800548f6  sub     rsp, 0D8h
0x1800548fd  mov     r15, r9
0x180054900  mov     r12, r8
0x180054903  mov     r13, rdx
0x180054906  mov     rdi, rcx
0x180054909  call    ?CheckAndCreateProxySettingsContainerIfNeeded@URL_INFO@@AEAAXXZ; URL_INFO::CheckAndCreateProxySettingsContainerIfNeeded(void)
0x18005490e  mov     rbx, [rdi+30h]
0x180054912  lea     rcx, [rbp+4Fh+var_78]; this
0x180054916  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x18005491b  nop
0x18005491c  xor     esi, esi
0x18005491e  mov     [rbp+4Fh+var_70], sil
0x180054922  mov     rax, [rbx]
0x180054925  mov     [rbp+4Fh+var_68], rax
0x180054929  lea     ebx, [rsi+1]
0x18005492c  lock add [rax+8], ebx
0x180054930  mov     [rbp+4Fh+var_60], rsi
0x180054934  lea     ecx, [rsi+4]; dwBytes
0x180054937  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005493c  test    rax, rax
0x18005493f  jz      short loc_180054945
0x180054941  mov     [rax], ebx
0x180054943  jmp     short loc_180054948
0x180054945  mov     rax, rsi
0x180054948  mov     [rbp+4Fh+var_58], rax
0x18005494c  mov     [rbp+4Fh+var_50], rsi
0x180054950  lock add cs:dword_180145058, ebx
0x180054957  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18005495e  mov     [rbp+4Fh+var_48], rax
0x180054962  cmp     [rbp+4Fh+var_70], sil
0x180054966  jnz     short loc_1800549C0
0x180054968  mov     rcx, [rbp+4Fh+var_68]
0x18005496c  mov     rcx, [rcx]; hToken
0x18005496f  call    cs:__imp_ImpersonateLoggedOnUser
0x180054975  test    eax, eax
0x180054977  jnz     short loc_1800549BD
0x180054979  call    cs:__imp_GetLastError
0x18005497f  mov     ecx, eax
0x180054981  test    eax, eax
0x180054983  jle     short loc_18005498E
0x180054985  movzx   ecx, ax
0x180054988  or      ecx, 80070000h
0x18005498e  xorps   xmm0, xmm0
0x180054991  movups  [rsp+110h+var_D8], xmm0
0x180054996  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005499d  mov     [rsp+110h+pExceptionObject], rax
0x1800549a2  mov     [rbp+4Fh+var_C8], ecx
0x1800549a5  mov     [rbp+4Fh+var_C4], esi
0x1800549a8  mov     [rbp+4Fh+var_C0], ebx
0x1800549ab  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800549b2  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x1800549b7  call    _CxxThrowException_0
0x1800549bd  mov     [rbp+4Fh+var_70], bl
0x1800549c0  mov     r14, [rdi+460h]
0x1800549c7  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800549cd  test    eax, eax
0x1800549cf  jz      short loc_180054A0C
0x1800549d1  lea     rbx, WPP_GLOBAL_Control
0x1800549d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800549df  cmp     rcx, rbx
0x1800549e2  jz      short loc_180054A06
0x1800549e4  test    byte ptr [rcx+1Ch], 2
0x1800549e8  jz      short loc_180054A06
0x1800549ea  mov     edx, 0Ah
0x1800549ef  lea     r8, WPP_16528e1573683c34a7ff296cba86f7f8_Traceguids
0x1800549f6  mov     rcx, [rcx+10h]
0x1800549fa  call    WPP_SF_
0x1800549ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a06  lea     rsi, [rdi+20h]
0x180054a0a  jmp     short loc_180054A77
0x180054a0c  lea     rsi, [rdi+20h]
0x180054a10  lea     rbx, WPP_GLOBAL_Control
0x180054a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a1e  cmp     rcx, rbx
0x180054a21  jz      short loc_180054A41
0x180054a23  test    byte ptr [rcx+1Ch], 1
0x180054a27  jz      short loc_180054A41
0x180054a29  mov     edx, 0Bh
0x180054a2e  mov     r9, r14
0x180054a31  lea     r8, WPP_16528e1573683c34a7ff296cba86f7f8_Traceguids
0x180054a38  mov     rcx, [rcx+10h]
0x180054a3c  call    WPP_SF_S
0x180054a41  mov     rcx, [rsi]; void *
0x180054a44  mov     qword ptr [rsi], 0
0x180054a4b  test    rcx, rcx
0x180054a4e  jz      short loc_180054A5A
0x180054a50  mov     edx, 2; unsigned __int64
0x180054a55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180054a5a  mov     rdx, r14; wszServerName
0x180054a5d  mov     rcx, r15; lpCriticalSection
0x180054a60  call    ?StartGetEidAsync@EidAsyncHelper@@QEAA_NPEBG@Z; EidAsyncHelper::StartGetEidAsync(ushort const *)
0x180054a65  mov     rdx, rsi
0x180054a68  mov     rcx, r15; lpCriticalSection
0x180054a6b  call    ?WaitForEnterpriseId@EidAsyncHelper@@QEAA_NAEAV?$unique_ptr@GU?$default_delete@G@std@@@std@@@Z; EidAsyncHelper::WaitForEnterpriseId(std::unique_ptr<ushort> &)
0x180054a70  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a77  mov     r14, [rsi]
0x180054a7a  cmp     rcx, rbx
0x180054a7d  jz      short loc_180054A9D
0x180054a7f  test    byte ptr [rcx+1Ch], 1
0x180054a83  jz      short loc_180054A9D
0x180054a85  mov     edx, 1Ah
0x180054a8a  mov     r9, r14
0x180054a8d  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180054a94  mov     rcx, [rcx+10h]
0x180054a98  call    WPP_SF_S
0x180054a9d  xor     r15d, r15d
0x180054aa0  test    r14, r14
0x180054aa3  jz      loc_180054C91
0x180054aa9  cmp     [r14], r15w
0x180054aad  jz      loc_180054C91
0x180054ab3  lea     rcx, [rbp+4Fh+var_80]
0x180054ab7  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x180054abc  nop
0x180054abd  call    cs:__imp_RevertToSelf
0x180054ac3  test    eax, eax
0x180054ac5  jnz     short loc_180054B21
0x180054ac7  call    cs:__imp_GetLastError
0x180054acd  test    eax, eax
0x180054acf  jg      short loc_180054ADB
0x180054ad1  call    cs:__imp_GetLastError
0x180054ad7  mov     ecx, eax
0x180054ad9  jmp     short loc_180054AEA
0x180054adb  call    cs:__imp_GetLastError
0x180054ae1  movzx   ecx, ax
0x180054ae4  or      ecx, 80070000h
0x180054aea  xorps   xmm0, xmm0
0x180054aed  movups  [rsp+110h+var_D8], xmm0
0x180054af2  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180054af9  mov     [rsp+110h+pExceptionObject], rax
0x180054afe  mov     [rbp+4Fh+var_C8], ecx
0x180054b01  mov     [rbp+4Fh+var_C4], 248h
0x180054b08  mov     [rbp+4Fh+var_C0], 1
0x180054b0f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180054b16  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180054b1b  call    _CxxThrowException_0
0x180054b21  mov     [rbp+4Fh+OldValue], r15b
0x180054b25  lea     r9, [rbp+4Fh+OldValue]; OldValue
0x180054b29  xor     r8d, r8d; ForThread
0x180054b2c  lea     r14d, [r8+1]
0x180054b30  mov     dl, r14b; NewValue
0x180054b33  lea     ecx, [r8+7]; Privilege
0x180054b37  call    cs:__imp_RtlAdjustPrivilege
0x180054b3d  mov     ecx, eax; Status
0x180054b3f  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x180054b44  mov     ecx, eax
0x180054b46  test    eax, eax
0x180054b48  jns     short loc_180054B7E
0x180054b4a  xorps   xmm0, xmm0
0x180054b4d  movups  [rsp+110h+var_D8], xmm0
0x180054b52  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180054b59  mov     [rsp+110h+pExceptionObject], rax
0x180054b5e  mov     [rbp+4Fh+var_C8], ecx
0x180054b61  mov     [rbp+4Fh+var_C4], 24Ch
0x180054b68  mov     [rbp+4Fh+var_C0], r14d
0x180054b6c  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180054b73  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180054b78  call    _CxxThrowException_0
0x180054b7e  mov     rbx, [rbp+4Fh+var_80]
0x180054b82  mov     rcx, [rbx]; TokenHandle
0x180054b85  call    SrpSetTokenEnterpriseExempt
0x180054b8a  mov     ecx, eax; Status
0x180054b8c  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x180054b91  mov     ecx, eax
0x180054b93  test    eax, eax
0x180054b95  jns     short loc_180054BCB
0x180054b97  xorps   xmm0, xmm0
0x180054b9a  movups  [rsp+110h+var_D8], xmm0
0x180054b9f  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180054ba6  mov     [rsp+110h+pExceptionObject], rax
0x180054bab  mov     [rbp+4Fh+var_C8], ecx
0x180054bae  mov     [rbp+4Fh+var_C4], 24Eh
0x180054bb5  mov     [rbp+4Fh+var_C0], r14d
0x180054bb9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180054bc0  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180054bc5  call    _CxxThrowException_0
0x180054bcb  lea     r9, [rbp+4Fh+OldValue]; OldValue
0x180054bcf  xor     r8d, r8d; ForThread
0x180054bd2  mov     dl, [rbp+4Fh+OldValue]; NewValue
0x180054bd5  lea     ecx, [r8+7]; Privilege
0x180054bd9  call    cs:__imp_RtlAdjustPrivilege
0x180054bdf  mov     ecx, eax; Status
0x180054be1  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x180054be6  mov     ecx, eax
0x180054be8  test    eax, eax
0x180054bea  jns     short loc_180054C20
0x180054bec  xorps   xmm0, xmm0
0x180054bef  movups  [rsp+110h+var_D8], xmm0
0x180054bf4  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180054bfb  mov     [rsp+110h+pExceptionObject], rax
0x180054c00  mov     [rbp+4Fh+var_C8], ecx
0x180054c03  mov     [rbp+4Fh+var_C4], 251h
0x180054c0a  mov     [rbp+4Fh+var_C0], r14d
0x180054c0e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180054c15  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180054c1a  call    _CxxThrowException_0
0x180054c20  mov     rdx, [rbx]; Token
0x180054c23  xor     ecx, ecx; Thread
0x180054c25  call    cs:__imp_SetThreadToken
0x180054c2b  test    eax, eax
0x180054c2d  jnz     short loc_180054C86
0x180054c2f  call    cs:__imp_GetLastError
0x180054c35  test    eax, eax
0x180054c37  jg      short loc_180054C43
0x180054c39  call    cs:__imp_GetLastError
0x180054c3f  mov     ecx, eax
0x180054c41  jmp     short loc_180054C52
0x180054c43  call    cs:__imp_GetLastError
0x180054c49  movzx   ecx, ax
0x180054c4c  or      ecx, 80070000h
0x180054c52  xorps   xmm0, xmm0
0x180054c55  movups  [rsp+110h+var_D8], xmm0
0x180054c5a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180054c61  mov     [rsp+110h+pExceptionObject], rax
0x180054c66  mov     [rbp+4Fh+var_C8], ecx
0x180054c69  mov     [rbp+4Fh+var_C4], 255h
0x180054c70  mov     [rbp+4Fh+var_C0], r14d
0x180054c74  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180054c7b  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180054c80  call    _CxxThrowException_0
0x180054c86  lea     rcx, [rbp+4Fh+var_80]; this
0x180054c8a  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x180054c8f  jmp     short loc_180054C97
0x180054c91  mov     r14d, 1
0x180054c97  mov     al, [rbp+4Fh+arg_20]
0x180054c9a  mov     [rsp+110h+var_F0], al; bool
0x180054c9e  mov     r9, [rsi]; unsigned __int16 *
0x180054ca1  mov     r8, r13; struct IHttpInterface *
0x180054ca4  mov     rdx, r12; struct HttpSecurityData *
0x180054ca7  call    ?GetSession@HttpSessionCache@@QEAAPEAVIHttpSession@@AEBUHttpSecurityData@@PEAVIHttpInterface@@PEBG_N@Z; HttpSessionCache::GetSession(HttpSecurityData const &,IHttpInterface *,ushort const *,bool)
0x180054cac  mov     [rdi], rax
0x180054caf  mov     rcx, rax; struct IHttpSession *
0x180054cb2  call    ?EnablePassport@@YAXPEAVIHttpSession@@@Z; EnablePassport(IHttpSession *)
0x180054cb7  mov     rcx, [rdi]
0x180054cba  mov     rax, [rcx]
0x180054cbd  movzx   r8d, word ptr [rdi+3Ch]
0x180054cc2  mov     rdx, [rdi+460h]
0x180054cc9  mov     rax, [rax+8]
0x180054ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cd2  mov     [rdi+8], rax
0x180054cd6  lea     rcx, [rbp+4Fh+var_78]; this
0x180054cda  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x180054cdf  cmp     [rdi+12h], r15b
0x180054ce3  jz      short loc_180054D37
0x180054ce5  mov     rdx, [rdi+40h]
0x180054ce9  cmp     [rdx], r15d
0x180054cec  jz      short loc_180054D37
0x180054cee  mov     rcx, [rdi]
0x180054cf1  mov     rax, [rcx]
0x180054cf4  mov     rax, [rax+18h]
0x180054cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cfd  mov     ecx, eax
0x180054cff  test    eax, eax
0x180054d01  jns     short loc_180054D37
0x180054d03  xorps   xmm0, xmm0
0x180054d06  movups  [rsp+110h+var_D8], xmm0
0x180054d0b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180054d12  mov     [rsp+110h+pExceptionObject], rax
0x180054d17  mov     [rbp+4Fh+var_C8], ecx
0x180054d1a  mov     [rbp+4Fh+var_C4], 13C1h
0x180054d21  mov     [rbp+4Fh+var_C0], r14d
0x180054d25  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180054d2c  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180054d31  call    _CxxThrowException_0
0x180054d37  mov     r8, [rdi+50h]
0x180054d3b  test    r8, r8
0x180054d3e  jz      short loc_180054DB4
0x180054d40  mov     rcx, [rdi+8]
0x180054d44  mov     rax, [rcx]
0x180054d47  mov     edx, 83h
0x180054d4c  lea     r9d, [rdx+65h]
0x180054d50  mov     rax, [rax+10h]
0x180054d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d59  test    eax, eax
0x180054d5b  jnz     short loc_180054DB4
0x180054d5d  call    cs:__imp_GetLastError
0x180054d63  test    eax, eax
0x180054d65  jg      short loc_180054D71
0x180054d67  call    cs:__imp_GetLastError
0x180054d6d  mov     ecx, eax
0x180054d6f  jmp     short loc_180054D80
0x180054d71  call    cs:__imp_GetLastError
0x180054d77  movzx   ecx, ax
0x180054d7a  or      ecx, 80070000h
0x180054d80  xorps   xmm0, xmm0
0x180054d83  movups  [rsp+110h+var_D8], xmm0
0x180054d88  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180054d8f  mov     [rsp+110h+pExceptionObject], rax
0x180054d94  mov     [rbp+4Fh+var_C8], ecx
0x180054d97  mov     [rbp+4Fh+var_C4], 13C8h
0x180054d9e  mov     [rbp+4Fh+var_C0], r14d
0x180054da2  lea     rdx, _TI2?AVComError@@; pThrowInfo
  ... truncated ...
```
