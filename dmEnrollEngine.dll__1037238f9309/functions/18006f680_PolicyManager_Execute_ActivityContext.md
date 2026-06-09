# PolicyManager::Execute(ActivityContext *)

- ea: `0x18006f680`
- end: `0x18006f7eb`
- name: `?Execute@PolicyManager@@UEAAJPEAVActivityContext@@@Z`
- size: `363`
- prototype: `int(PolicyManager *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000de50`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18004e6c8`
- `0x18006f680`
- `0x180073e50`

## import_xrefs

- `policymanager!EnterprisePolicyManagerStore_DeleteVirtuallyDeletedHive` at `0x18006f70d`
- `policymanager!EnterprisePolicyManagerStore_DeleteVirtuallyDeletedHive` at `0x18006f70d`
- `policymanager!EnterprisePolicyManagerStore_DeleteEnrollmentAdmxMetadata` at `0x18006f7a4`
- `policymanager!EnterprisePolicyManagerStore_DeleteEnrollmentAdmxMetadata` at `0x18006f7a4`
- `policymanager!EnterprisePolicyManagerStore_PerformEvaluatorMerge` at `0x18006f7bb`
- `policymanager!EnterprisePolicyManagerStore_PerformEvaluatorMerge` at `0x18006f7bb`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18006f6f5`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18006f6f5`
- `DMCmnUtils!DmWnfQuery` at `0x18006f731`
- `DMCmnUtils!DmWnfQuery` at `0x18006f731`

## string_xrefs

- `0x18006f737`: `./User/Vendor/MSFT/Policy/Config`
- `0x18006f73e`: `./Vendor/MSFT/Policy/Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PolicyManager::Execute(PolicyManager *this, struct ActivityContext *a2)
{
  int EnrollmentString; // eax
  const unsigned __int16 *v5; // r9
  int v6; // edi
  CEnrollmentLogger *Logger; // rax
  int v9; // [rsp+30h] [rbp-59h] BYREF
  OLECHAR *v10; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v11[4]; // [rsp+40h] [rbp-49h] BYREF
  struct _GUID v12; // [rsp+50h] [rbp-39h] BYREF
  OLECHAR psz[40]; // [rsp+60h] [rbp-29h] BYREF

  v10 = 0;
  psz[0] = 0;
  if ( ActivityContext::get_KeyAsString(a2, psz) < 0 )
    goto LABEL_16;
  if ( *((_DWORD *)this + 6) )
  {
LABEL_7:
    EnterprisePolicyManagerStore_DeleteVirtuallyDeletedHive(psz);
    goto LABEL_8;
  }
  v12 = *(struct _GUID *)((char *)a2 + 8);
  EnrollmentString = EEDBManager::GetEnrollmentString(&v12, L"SID", &v10);
  if ( EnrollmentString == -2147024894 )
    EnrollmentString = DmGetActiveUserSid(&v10);
  if ( EnrollmentString < 0 )
  {
LABEL_16:
    v6 = -2147418113;
    goto LABEL_17;
  }
  if ( *((_DWORD *)this + 6) )
    goto LABEL_7;
LABEL_8:
  v9 = -1;
  v11[0] = 4;
  DmWnfQuery(
    (struct _WNF_STATE_NAME)WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED,
    4u,
    (unsigned __int8 *)&v9,
    v11);
  v5 = L"./Vendor/MSFT/Policy/Config";
  if ( !*((_DWORD *)this + 6) )
    v5 = L"./User/Vendor/MSFT/Policy/Config";
  v6 = CommonUnenrollCsp(psz, (OLECHAR *)&wszURI, v10, v5, 0, 0);
  if ( v6 < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    v12 = *(struct _GUID *)((char *)a2 + 8);
    CEnrollmentLogger::LogUnenrollPolicyManagerFail(Logger, v6, &v12);
  }
  if ( *((_DWORD *)this + 6) )
    EnterprisePolicyManagerStore_DeleteEnrollmentAdmxMetadata(psz, L"device");
  if ( v9 )
    EnterprisePolicyManagerStore_PerformEvaluatorMerge(psz, L"DataProtection");
LABEL_17:
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006f680  push    rbp
0x18006f682  push    rbx
0x18006f683  push    rsi
0x18006f684  push    rdi
0x18006f685  lea     rbp, [rsp-3Fh]
0x18006f68a  sub     rsp, 0C8h
0x18006f691  mov     rax, cs:__security_cookie
0x18006f698  xor     rax, rsp
0x18006f69b  mov     [rbp+57h+var_30], rax
0x18006f69f  mov     rsi, rdx
0x18006f6a2  mov     rbx, rcx
0x18006f6a5  mov     [rbp+57h+var_A8], 0
0x18006f6ad  xor     eax, eax
0x18006f6af  mov     [rbp+57h+psz], ax
0x18006f6b3  lea     rdx, [rbp+57h+psz]; unsigned __int16 *
0x18006f6b7  mov     rcx, rsi; this
0x18006f6ba  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x18006f6bf  test    eax, eax
0x18006f6c1  js      loc_18006F7C3
0x18006f6c7  cmp     dword ptr [rbx+18h], 0
0x18006f6cb  jnz     short loc_18006F709
0x18006f6cd  movups  xmm0, xmmword ptr [rsi+8]
0x18006f6d1  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x18006f6d6  lea     r8, [rbp+57h+var_A8]; unsigned __int16 **
0x18006f6da  lea     rdx, aSid; "SID"
0x18006f6e1  lea     rcx, [rbp+57h+var_90]; struct _GUID
0x18006f6e5  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18006f6ea  cmp     eax, 80070002h
0x18006f6ef  jnz     short loc_18006F6FB
0x18006f6f1  lea     rcx, [rbp+57h+var_A8]
0x18006f6f5  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18006f6fb  test    eax, eax
0x18006f6fd  js      loc_18006F7C3
0x18006f703  cmp     dword ptr [rbx+18h], 0
0x18006f707  jz      short loc_18006F713
0x18006f709  lea     rcx, [rbp+57h+psz]
0x18006f70d  call    cs:__imp_?EnterprisePolicyManagerStore_DeleteVirtuallyDeletedHive@@YAJPEBG@Z; EnterprisePolicyManagerStore_DeleteVirtuallyDeletedHive(ushort const *)
0x18006f713  mov     [rbp+57h+var_B0], 0FFFFFFFFh
0x18006f71a  mov     edx, 4
0x18006f71f  mov     [rbp+57h+var_A0], edx
0x18006f722  lea     r9, [rbp+57h+var_A0]
0x18006f726  lea     r8, [rbp+57h+var_B0]
0x18006f72a  mov     rcx, cs:WNF_ENTR_EDPENFORCEMENTLEVEL_CACHED_POLICY_VALUE_CHANGED
0x18006f731  call    cs:__imp_?DmWnfQuery@@YAJU_WNF_STATE_NAME@@KPEAEPEAK@Z; DmWnfQuery(_WNF_STATE_NAME,ulong,uchar *,ulong *)
0x18006f737  lea     rax, aUserVendorMsft; "./User/Vendor/MSFT/Policy/Config"
0x18006f73e  lea     r9, aVendorMsftPoli; "./Vendor/MSFT/Policy/Config"
0x18006f745  cmp     dword ptr [rbx+18h], 0
0x18006f749  cmovz   r9, rax; unsigned __int16 *
0x18006f74d  mov     [rsp+0E0h+var_B8], 0; int
0x18006f755  mov     [rsp+0E0h+var_C0], 0; int
0x18006f75d  mov     r8, [rbp+57h+var_A8]; OLECHAR *
0x18006f761  lea     rdx, wszURI; OLECHAR *
0x18006f768  lea     rcx, [rbp+57h+psz]; psz
0x18006f76c  call    ?CommonUnenrollCsp@@YAJPEBG000HH@Z; CommonUnenrollCsp(ushort const *,ushort const *,ushort const *,ushort const *,int,int)
0x18006f771  mov     edi, eax
0x18006f773  test    eax, eax
0x18006f775  jns     short loc_18006F793
0x18006f777  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006f77c  movups  xmm0, xmmword ptr [rsi+8]
0x18006f780  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x18006f785  lea     r8, [rbp+57h+var_90]; struct _GUID
0x18006f789  mov     edx, edi; int
0x18006f78b  mov     rcx, rax; this
0x18006f78e  call    ?LogUnenrollPolicyManagerFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollPolicyManagerFail(long,_GUID)
0x18006f793  cmp     dword ptr [rbx+18h], 0
0x18006f797  jz      short loc_18006F7AA
0x18006f799  lea     rdx, aDevice_0; "device"
0x18006f7a0  lea     rcx, [rbp+57h+psz]
0x18006f7a4  call    cs:__imp_?EnterprisePolicyManagerStore_DeleteEnrollmentAdmxMetadata@@YAJPEBG0@Z; EnterprisePolicyManagerStore_DeleteEnrollmentAdmxMetadata(ushort const *,ushort const *)
0x18006f7aa  cmp     [rbp+57h+var_B0], 0
0x18006f7ae  jz      short loc_18006F7C8
0x18006f7b0  lea     rdx, aDataprotection; "DataProtection"
0x18006f7b7  lea     rcx, [rbp+57h+psz]
0x18006f7bb  call    cs:__imp_?EnterprisePolicyManagerStore_PerformEvaluatorMerge@@YAJPEBG0@Z; EnterprisePolicyManagerStore_PerformEvaluatorMerge(ushort const *,ushort const *)
0x18006f7c1  jmp     short loc_18006F7C8
0x18006f7c3  mov     edi, 8000FFFFh
0x18006f7c8  lea     rcx, [rbp+57h+var_A8]
0x18006f7cc  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18006f7d1  mov     eax, edi
0x18006f7d3  mov     rcx, [rbp+57h+var_30]
0x18006f7d7  xor     rcx, rsp; StackCookie
0x18006f7da  call    __security_check_cookie
0x18006f7df  add     rsp, 0C8h
0x18006f7e6  pop     rdi
0x18006f7e7  pop     rsi
0x18006f7e8  pop     rbx
0x18006f7e9  pop     rbp
0x18006f7ea  retn
```
