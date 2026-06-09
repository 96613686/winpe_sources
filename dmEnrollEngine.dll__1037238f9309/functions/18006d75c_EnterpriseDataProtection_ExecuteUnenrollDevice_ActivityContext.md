# EnterpriseDataProtection::ExecuteUnenrollDevice(ActivityContext *)

- ea: `0x18006d75c`
- end: `0x18006d92e`
- name: `?ExecuteUnenrollDevice@EnterpriseDataProtection@@AEAAJPEAVActivityContext@@@Z`
- size: `466`
- prototype: `int(EnterpriseDataProtection *__hidden this, struct ActivityContext *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d5c0`

## callees

- `0x180010f8c`
- `0x180011f94`
- `0x18001a86c`
- `0x18001acd8`
- `0x18001aec8`
- `0x18001dc4c`
- `0x18002e1a0`
- `0x18006d75c`
- `0x18006de08`
- `0x18007381c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18006d79f`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18006d7b6`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18006d79f`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18006d7b6`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18006d8e1`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18006d8e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall EnterpriseDataProtection::ExecuteUnenrollDevice(
        EnterpriseDataProtection *this,
        struct ActivityContext *a2)
{
  int result; // eax
  bool v4; // di
  __int64 v5; // rcx
  int v6; // ebx
  unsigned __int8 v7; // si
  __int64 v8; // rcx
  CEnrollmentLogger *Logger; // rax
  EnterpriseDataProtection *v10; // rcx
  int PolicyInt; // ebx
  CEnrollmentLogger *v12; // rax
  const unsigned __int16 *v13; // r8
  unsigned __int8 v14; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int8 v15[3]; // [rsp+31h] [rbp-68h] BYREF
  int v16; // [rsp+34h] [rbp-65h] BYREF
  unsigned __int16 *v17[2]; // [rsp+38h] [rbp-61h] BYREF
  __int64 v18; // [rsp+48h] [rbp-51h]
  unsigned __int64 v19; // [rsp+50h] [rbp-49h]
  WCHAR v20[20]; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 v21[40]; // [rsp+80h] [rbp-19h] BYREF

  RegDeleteKeyValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Policies\\Microsoft\\Internet Explorer\\Main\\EnterpriseMode",
    L"Enable");
  RegDeleteKeyValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Policies\\Microsoft\\Internet Explorer\\Main\\EnterpriseMode",
    L"SiteList");
  result = ActivityContext::get_KeyAsString(a2, v21);
  if ( result >= 0 )
  {
    *(_OWORD *)v17 = 0;
    v18 = 0;
    v19 = 7;
    LOWORD(v17[0]) = 0;
    v4 = 1;
    v14 = 1;
    v15[0] = 1;
    std::wstring::wstring(v20, v21);
    v6 = EnterpriseDataProtection::ReadPolicy(v5, v20, v17, &v14, v15);
    std::wstring::_Tidy_deallocate(v20);
    if ( v6 < 0 )
      goto LABEL_7;
    std::wstring::wstring(v20, v21);
    v7 = v15[0];
    v6 = EnterpriseDataProtection::PolicyStoragePersist(v8, v20, (__int64 *)v17, v14, v15[0]);
    std::wstring::_Tidy_deallocate(v20);
    if ( v6 < 0 )
      goto LABEL_7;
    if ( (*((_DWORD *)a2 + 18) & 0x100) != 0 )
    {
      if ( !v7 )
        goto LABEL_6;
    }
    else if ( !v14 )
    {
LABEL_6:
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogUnenrollEnterpriseDataProtection(
        Logger,
        0,
        L"Skipping revoke due to RevokeOnUnenroll policy");
      v6 = 0;
LABEL_7:
      std::wstring::_Tidy_deallocate(v17);
      return v6;
    }
    if ( v18 )
    {
      v16 = 0;
      PolicyInt = PolicyManager_GetPolicyInt(L"DataProtection", L"EDPEnforcementLevel", &v16);
      if ( PolicyInt >= 0 )
      {
        v4 = v16 != 0;
      }
      else
      {
        v12 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogUnenrollEnterpriseDataProtection(
          v12,
          PolicyInt,
          L"Failed get RevokeOnUnenroll policy value");
      }
      v13 = (const unsigned __int16 *)v17;
      if ( v19 > 7 )
        v13 = v17[0];
      v6 = EnterpriseDataProtection::RevokeAndDelete(v10, a2, v13, v4);
      goto LABEL_7;
    }
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x18006d75c  mov     [rsp-8+arg_0], rbx
0x18006d761  mov     [rsp-8+arg_10], rsi
0x18006d766  push    rbp
0x18006d767  push    rdi
0x18006d768  push    r15
0x18006d76a  lea     rbp, [rsp-47h]
0x18006d76f  sub     rsp, 0E0h
0x18006d776  mov     rax, cs:__security_cookie
0x18006d77d  xor     rax, rsp
0x18006d780  mov     [rbp+57h+var_20], rax
0x18006d784  mov     r15, rdx
0x18006d787  lea     r8, aEnable; "Enable"
0x18006d78e  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Internet"...
0x18006d795  mov     rbx, 0FFFFFFFF80000002h
0x18006d79c  mov     rcx, rbx; hKey
0x18006d79f  call    cs:__imp_RegDeleteKeyValueW
0x18006d7a5  lea     r8, aSitelist; "SiteList"
0x18006d7ac  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Internet"...
0x18006d7b3  mov     rcx, rbx; hKey
0x18006d7b6  call    cs:__imp_RegDeleteKeyValueW
0x18006d7bc  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18006d7c0  mov     rcx, r15; this
0x18006d7c3  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x18006d7c8  test    eax, eax
0x18006d7ca  js      loc_18006D898
0x18006d7d0  xorps   xmm0, xmm0
0x18006d7d3  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x18006d7d7  mov     [rbp+57h+var_A8], 0
0x18006d7df  mov     [rbp+57h+var_A0], 7
0x18006d7e7  xor     eax, eax
0x18006d7e9  mov     word ptr [rbp+57h+var_B8], ax
0x18006d7ed  mov     dil, 1
0x18006d7f0  mov     [rbp+57h+var_C0], dil
0x18006d7f4  mov     [rbp+57h+var_BF], dil
0x18006d7f8  lea     rdx, [rbp+57h+var_70]
0x18006d7fc  lea     rcx, [rbp+57h+var_98]
0x18006d800  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006d805  nop
0x18006d806  lea     rax, [rbp+57h+var_BF]
0x18006d80a  mov     [rsp+0F0h+var_D0], rax
0x18006d80f  lea     r9, [rbp+57h+var_C0]
0x18006d813  lea     r8, [rbp+57h+var_B8]
0x18006d817  lea     rdx, [rbp+57h+var_98]
0x18006d81b  call    ?ReadPolicy@EnterpriseDataProtection@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV23@PEA_N2@Z; EnterpriseDataProtection::ReadPolicy(std::wstring const &,std::wstring *,bool *,bool *)
0x18006d820  mov     ebx, eax
0x18006d822  lea     rcx, [rbp+57h+var_98]
0x18006d826  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d82b  test    ebx, ebx
0x18006d82d  js      short loc_18006D88D
0x18006d82f  lea     rdx, [rbp+57h+var_70]
0x18006d833  lea     rcx, [rbp+57h+var_98]
0x18006d837  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006d83c  mov     sil, [rbp+57h+var_BF]
0x18006d840  mov     byte ptr [rsp+0F0h+var_D0], sil
0x18006d845  mov     r9b, [rbp+57h+var_C0]
0x18006d849  lea     r8, [rbp+57h+var_B8]
0x18006d84d  lea     rdx, [rbp+57h+var_98]
0x18006d851  call    ?PolicyStoragePersist@EnterpriseDataProtection@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N1@Z; EnterpriseDataProtection::PolicyStoragePersist(std::wstring const &,std::wstring const &,bool,bool)
0x18006d856  mov     ebx, eax
0x18006d858  lea     rcx, [rbp+57h+var_98]
0x18006d85c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d861  test    ebx, ebx
0x18006d863  js      short loc_18006D88D
0x18006d865  test    dword ptr [r15+48h], 100h
0x18006d86d  jnz     short loc_18006D8BC
0x18006d86f  cmp     [rbp+57h+var_C0], 0
0x18006d873  jnz     short loc_18006D8C1
0x18006d875  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006d87a  lea     r8, aSkippingRevoke; "Skipping revoke due to RevokeOnUnenroll"...
0x18006d881  xor     edx, edx; int
0x18006d883  mov     rcx, rax; this
0x18006d886  call    ?LogUnenrollEnterpriseDataProtection@CEnrollmentLogger@@QEAAXJPEBG@Z; CEnrollmentLogger::LogUnenrollEnterpriseDataProtection(long,ushort const *)
0x18006d88b  xor     ebx, ebx
0x18006d88d  lea     rcx, [rbp+57h+var_B8]
0x18006d891  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d896  mov     eax, ebx
0x18006d898  mov     rcx, [rbp+57h+var_20]
0x18006d89c  xor     rcx, rsp; StackCookie
0x18006d89f  call    __security_check_cookie
0x18006d8a4  lea     r11, [rsp+0F0h+var_10]
0x18006d8ac  mov     rbx, [r11+20h]
0x18006d8b0  mov     rsi, [r11+30h]
0x18006d8b4  mov     rsp, r11
0x18006d8b7  pop     r15
0x18006d8b9  pop     rdi
0x18006d8ba  pop     rbp
0x18006d8bb  retn
0x18006d8bc  test    sil, sil
0x18006d8bf  jz      short loc_18006D875
0x18006d8c1  cmp     [rbp+57h+var_A8], 0
0x18006d8c6  jz      short loc_18006D875
0x18006d8c8  mov     [rbp+57h+var_BC], 0
0x18006d8cf  lea     r8, [rbp+57h+var_BC]
0x18006d8d3  lea     rdx, aEdpenforcement; "EDPEnforcementLevel"
0x18006d8da  lea     rcx, aDataprotection; "DataProtection"
0x18006d8e1  call    cs:__imp_PolicyManager_GetPolicyInt
0x18006d8e7  mov     ebx, eax
0x18006d8e9  test    eax, eax
0x18006d8eb  jns     short loc_18006D905
0x18006d8ed  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006d8f2  lea     r8, aFailedGetRevok_0; "Failed get RevokeOnUnenroll policy valu"...
0x18006d8f9  mov     edx, ebx; int
0x18006d8fb  mov     rcx, rax; this
0x18006d8fe  call    ?LogUnenrollEnterpriseDataProtection@CEnrollmentLogger@@QEAAXJPEBG@Z; CEnrollmentLogger::LogUnenrollEnterpriseDataProtection(long,ushort const *)
0x18006d903  jmp     short loc_18006D90D
0x18006d905  cmp     [rbp+57h+var_BC], 0
0x18006d909  setnz   dil
0x18006d90d  lea     r8, [rbp+57h+var_B8]
0x18006d911  cmp     [rbp+57h+var_A0], 7
0x18006d916  cmova   r8, [rbp+57h+var_B8]; unsigned __int16 *
0x18006d91b  mov     r9b, dil; bool
0x18006d91e  mov     rdx, r15; struct ActivityContext *
0x18006d921  call    ?RevokeAndDelete@EnterpriseDataProtection@@AEAAJPEAVActivityContext@@PEBG_N@Z; EnterpriseDataProtection::RevokeAndDelete(ActivityContext *,ushort const *,bool)
0x18006d926  mov     ebx, eax
0x18006d928  jmp     loc_18006D88D
```
