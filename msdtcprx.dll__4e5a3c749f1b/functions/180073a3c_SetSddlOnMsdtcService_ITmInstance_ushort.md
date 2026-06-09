# SetSddlOnMsdtcService(ITmInstance *,ushort *)

- ea: `0x180073a3c`
- end: `0x180073c4c`
- name: `?SetSddlOnMsdtcService@@YAJPEAUITmInstance@@PEAG@Z`
- size: `528`
- prototype: `__int64 __fastcall(struct ITmInstance *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180047cac`
- `0x180074200`

## callees

- `0x180003cf0`
- `0x18001ce20`
- `0x18001d178`
- `0x180072cd4`
- `0x180072edc`
- `0x180073a3c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073bf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073bf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073c0a`

## string_xrefs

- `0x180073a61`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x180073a6f`: `SetSddlOnMsdtcService`
- `0x180073abb`: `Failed to get the service name for the specified TM instance`
- `0x180073b14`: `pTmInstance->GetServiceAccount failed`
- `0x180073b3d`: `GetAccountSid failed`
- `0x180073b84`: `GrantServiceLogOnAccess failed`

## pseudocode

```c
__int64 __fastcall SetSddlOnMsdtcService(struct ITmInstance *a1, unsigned __int16 *a2)
{
  void *v2; // rsi
  int AccountSid; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  __int64 v8; // [rsp+28h] [rbp-18h]
  void *Block; // [rsp+80h] [rbp+40h] BYREF
  LPCWSTR lpSystemName; // [rsp+88h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int16 *v12; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  Block = 0;
  pv = 0;
  lpSystemName = 0;
  v12 = 0;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    813,
    L"SetSddlOnMsdtcService",
    0,
    L"In");
  AccountSid = (*(__int64 (__fastcall **)(struct ITmInstance *, LPVOID *))(*(_QWORD *)a1 + 56LL))(a1, &pv);
  if ( AccountSid < 0 )
  {
    v5 = L"Failed to get the service name for the specified TM instance";
    v6 = 817;
LABEL_14:
    LODWORD(v8) = AccountSid;
    TraceStringInline(7, 1, L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp", v6, L"SetSddlOnMsdtcService", v8, v5);
    goto LABEL_15;
  }
  AccountSid = (*(__int64 (__fastcall **)(struct ITmInstance *, LPCWSTR *))(*(_QWORD *)a1 + 40LL))(a1, &lpSystemName);
  if ( AccountSid < 0 )
  {
    v5 = L"Failed to get the host name from the specified TM instance";
    v6 = 823;
    goto LABEL_14;
  }
  AccountSid = (*(__int64 (__fastcall **)(struct ITmInstance *, unsigned __int16 **))(*(_QWORD *)a1 + 312LL))(a1, &v12);
  if ( AccountSid < 0 )
  {
    v5 = L"pTmInstance->GetServiceAccount failed";
    v6 = 831;
    goto LABEL_14;
  }
  AccountSid = GetAccountSid(lpSystemName, v12, &Block);
  if ( AccountSid >= 0 )
  {
    v2 = Block;
    AccountSid = GrantServiceLogOnAccess((unsigned __int16 *)lpSystemName, Block);
    if ( AccountSid < 0 )
    {
      v5 = L"GrantServiceLogOnAccess failed";
      v6 = 845;
      goto LABEL_14;
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITmInstance *))(*(_QWORD *)a1 + 24LL))(a1) )
    {
      AccountSid = SetObjectSddl(
                     (LPWSTR)pv,
                     SE_SERVICE,
                     L"D:(A;;CCLCSWRPLORC;;;S-1-2-0)(A;;CCDCLCSWRPWPDTLORC;;;SY)(A;;CCDCLCSWRPWPDTLOSDRCWDWO;;;BA)(A;;CCLC"
                      "SWRPLORC;;;IU)(A;;CCLCSWLORC;;;AU)(A;;CCLCSWRPLORC;;;SU)(A;;CCLCSWLORC;;;S-1-5-80-3960419045-24601"
                      "39048-4046793004-1809597027-2250574426)S:(AU;FA;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;WD)");
      if ( AccountSid < 0 )
      {
        v5 = L"SetObjectSddl(MSDTC) failed";
        v6 = 856;
        goto LABEL_14;
      }
    }
  }
  else
  {
    LODWORD(v8) = AccountSid;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
      839,
      L"SetSddlOnMsdtcService",
      v8,
      L"GetAccountSid failed");
    v2 = Block;
  }
LABEL_15:
  operator delete(v2);
  CoTaskMemFree(pv);
  CoTaskMemFree((LPVOID)lpSystemName);
  CoTaskMemFree(v12);
  LODWORD(v8) = AccountSid;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    865,
    L"SetSddlOnMsdtcService",
    v8,
    L"Out");
  return (unsigned int)AccountSid;
}

```

## disassembly

```asm
0x180073a3c  mov     r11, rsp
0x180073a3f  mov     [r11+10h], rdx
0x180073a43  push    rbp
0x180073a44  push    rbx
0x180073a45  push    rsi
0x180073a46  push    rdi
0x180073a47  push    r12
0x180073a49  push    r13
0x180073a4b  push    r15
0x180073a4d  mov     rbp, rsp
0x180073a50  sub     rsp, 40h
0x180073a54  xor     esi, esi
0x180073a56  lea     rax, aIn_0; "In"
0x180073a5d  mov     [r11-48h], rax
0x180073a61  lea     r15, aComComplusDtcS_12; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x180073a68  mov     rdi, rcx
0x180073a6b  mov     [r11-50h], rsi
0x180073a6f  lea     r13, aSetsddlonmsdtc_0; "SetSddlOnMsdtcService"
0x180073a76  mov     [rbp+Block], rsi
0x180073a7a  lea     r12d, [rsi+7]
0x180073a7e  mov     [rbp+pv], rsi
0x180073a82  mov     ecx, r12d
0x180073a85  mov     [rbp+lpSystemName], rsi
0x180073a89  mov     r9d, 32Dh
0x180073a8f  mov     [rbp+arg_18], rsi
0x180073a93  mov     r8, r15
0x180073a96  mov     [r11-58h], r13
0x180073a9a  lea     edx, [rsi+6]
0x180073a9d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073aa2  mov     rax, [rdi]
0x180073aa5  lea     rdx, [rbp+pv]
0x180073aa9  mov     rcx, rdi
0x180073aac  mov     rax, [rax+38h]
0x180073ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ab5  mov     ebx, eax
0x180073ab7  test    eax, eax
0x180073ab9  jns     short loc_180073ACD
0x180073abb  lea     rax, aFailedToGetThe_1; "Failed to get the service name for the "...
0x180073ac2  mov     r9d, 331h
0x180073ac8  jmp     loc_180073BCC
0x180073acd  mov     rax, [rdi]
0x180073ad0  lea     rdx, [rbp+lpSystemName]
0x180073ad4  mov     rcx, rdi
0x180073ad7  mov     rax, [rax+28h]
0x180073adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ae0  mov     ebx, eax
0x180073ae2  test    eax, eax
0x180073ae4  jns     short loc_180073AF8
0x180073ae6  lea     rax, aFailedToGetThe_4; "Failed to get the host name from the sp"...
0x180073aed  mov     r9d, 337h
0x180073af3  jmp     loc_180073BCC
0x180073af8  mov     rax, [rdi]
0x180073afb  lea     rdx, [rbp+arg_18]
0x180073aff  mov     rcx, rdi
0x180073b02  mov     rax, [rax+138h]
0x180073b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073b0e  mov     ebx, eax
0x180073b10  test    eax, eax
0x180073b12  jns     short loc_180073B26
0x180073b14  lea     rax, aPtminstanceGet; "pTmInstance->GetServiceAccount failed"
0x180073b1b  mov     r9d, 33Fh
0x180073b21  jmp     loc_180073BCC
0x180073b26  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x180073b2a  lea     r8, [rbp+Block]; void **
0x180073b2e  mov     rcx, [rbp+lpSystemName]; lpSystemName
0x180073b32  call    ?GetAccountSid@@YAJPEAG0PEAPEAX@Z; GetAccountSid(ushort *,ushort *,void * *)
0x180073b37  mov     ebx, eax
0x180073b39  test    eax, eax
0x180073b3b  jns     short loc_180073B6E
0x180073b3d  lea     rax, aGetaccountsidF; "GetAccountSid failed"
0x180073b44  mov     r9d, 347h
0x180073b4a  mov     [rsp+40h+var_10], rax
0x180073b4f  mov     r8, r15
0x180073b52  mov     dword ptr [rsp+40h+var_18], ebx
0x180073b56  mov     edx, 1
0x180073b5b  mov     ecx, r12d
0x180073b5e  mov     [rsp+40h+var_20], r13
0x180073b63  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073b68  mov     rsi, [rbp+Block]
0x180073b6c  jmp     short loc_180073BEA
0x180073b6e  mov     rsi, [rbp+Block]
0x180073b72  mov     rcx, [rbp+lpSystemName]; unsigned __int16 *
0x180073b76  mov     rdx, rsi; void *
0x180073b79  call    ?GrantServiceLogOnAccess@@YAJPEAGPEAX@Z; GrantServiceLogOnAccess(ushort *,void *)
0x180073b7e  mov     ebx, eax
0x180073b80  test    eax, eax
0x180073b82  jns     short loc_180073B93
0x180073b84  lea     rax, aGrantservicelo; "GrantServiceLogOnAccess failed"
0x180073b8b  mov     r9d, 34Dh
0x180073b91  jmp     short loc_180073BCC
0x180073b93  mov     rax, [rdi]
0x180073b96  mov     rcx, rdi
0x180073b99  mov     rax, [rax+18h]
0x180073b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ba2  test    eax, eax
0x180073ba4  jnz     short loc_180073BEA
0x180073ba6  mov     rcx, [rbp+pv]; pObjectName
0x180073baa  lea     r8, aDACclcswrplorc; "D:(A;;CCLCSWRPLORC;;;S-1-2-0)(A;;CCDCLC"...
0x180073bb1  lea     edx, [rax+2]; ObjectType
0x180073bb4  call    ?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z; SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)
0x180073bb9  mov     ebx, eax
0x180073bbb  test    eax, eax
0x180073bbd  jns     short loc_180073BEA
0x180073bbf  lea     rax, aSetobjectsddlM; "SetObjectSddl(MSDTC) failed"
0x180073bc6  mov     r9d, 358h
0x180073bcc  mov     [rsp+40h+var_10], rax
0x180073bd1  mov     r8, r15
0x180073bd4  mov     dword ptr [rsp+40h+var_18], ebx
0x180073bd8  mov     edx, 1
0x180073bdd  mov     ecx, r12d
0x180073be0  mov     [rsp+40h+var_20], r13
0x180073be5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073bea  mov     rcx, rsi; Block
0x180073bed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180073bf2  mov     rcx, [rbp+pv]; pv
0x180073bf6  call    cs:__imp_CoTaskMemFree
0x180073bfc  mov     rcx, [rbp+lpSystemName]; pv
0x180073c00  call    cs:__imp_CoTaskMemFree
0x180073c06  mov     rcx, [rbp+arg_18]; pv
0x180073c0a  call    cs:__imp_CoTaskMemFree
0x180073c10  lea     rax, aOut; "Out"
0x180073c17  mov     r9d, 361h
0x180073c1d  mov     [rsp+40h+var_10], rax
0x180073c22  mov     r8, r15
0x180073c25  mov     dword ptr [rsp+40h+var_18], ebx
0x180073c29  mov     edx, 6
0x180073c2e  mov     ecx, r12d
0x180073c31  mov     [rsp+40h+var_20], r13
0x180073c36  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073c3b  mov     eax, ebx
0x180073c3d  add     rsp, 40h
0x180073c41  pop     r15
0x180073c43  pop     r13
0x180073c45  pop     r12
0x180073c47  pop     rdi
0x180073c48  pop     rsi
0x180073c49  pop     rbx
0x180073c4a  pop     rbp
0x180073c4b  retn
```
