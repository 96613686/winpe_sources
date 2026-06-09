# CRefresherCache::AddObjectToRefresher(IWbemServices *,ushort const *,ushort const *,IWbemClassObject *,_WBEM_REFRESHER_ID *,IWbemClassObject *,long,IWbemContext *,IUnknown *,_WBEM_REFRESH_INFO *)

- ea: `0x180054c00`
- end: `0x180054deb`
- name: `?AddObjectToRefresher@CRefresherCache@@MEAAJPEAUIWbemServices@@PEBG1PEAUIWbemClassObject@@PEAU_WBEM_REFRESHER_ID@@2JPEAUIWbemContext@@PEAUIUnknown@@PEAU_WBEM_REFRESH_INFO@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(CRefresherCache *this, struct IWbemServices *, const unsigned __int16 *, const unsigned __int16 *, struct IWbemClassObject *, struct _WBEM_REFRESHER_ID *, struct IWbemObjectAccess *, int, struct IWbemContext *, struct IUnknown *, struct _WBEM_REFRESH_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180054830`

## callees

- `0x180037120`
- `0x1800548a0`
- `0x180054c00`
- `0x180055090`
- `0x180055210`
- `0x180055eb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180054d1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180054d1a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180054cb2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180054cb2`
- `wbemcomn!GetMemLogObject` at `0x180054d31`
- `wbemcomn!GetMemLogObject` at `0x180054d87`
- `wbemcomn!GetMemLogObject` at `0x180054d31`
- `wbemcomn!GetMemLogObject` at `0x180054d87`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180054c85`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180054c85`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180054c45`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180054c45`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180054d3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180054d97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180054d3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180054d97`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180054d7f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180054d7f`

## pseudocode

```c
__int64 __fastcall CRefresherCache::AddObjectToRefresher(
        CRefresherCache *this,
        struct IWbemServices *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IWbemClassObject *a5,
        struct _WBEM_REFRESHER_ID *a6,
        struct IWbemObjectAccess *a7,
        int a8,
        struct IWbemContext *a9,
        struct IUnknown *a10,
        struct _WBEM_REFRESH_INFO *a11)
{
  struct CRefresherId *v15; // rsi
  struct CHiPerfPrvRecord *v16; // rdi
  CRefresherCache *v17; // rcx
  HRESULT ProviderName; // ebx
  const unsigned __int16 *LPWSTR; // rax
  const unsigned __int16 *v20; // r8
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v22; // rax
  struct CHiPerfPrvRecord *v24; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v25[96]; // [rsp+68h] [rbp-60h] BYREF

  v15 = a6;
  if ( a6 && *(_QWORD *)a6 )
  {
    v16 = 0;
    v24 = 0;
    CVar::CVar((CVar *)v25);
    LODWORD(a6) = 0;
    ProviderName = CRefresherCache::GetProviderName(v17, a5, (struct CVar *)v25, (int *)&a6);
    if ( ProviderName < 0 )
    {
LABEL_17:
      CVar::~CVar((CVar *)v25);
      return (unsigned int)ProviderName;
    }
    if ( !(_DWORD)a6 )
    {
      LPWSTR = CVar::GetLPWSTR((CVar *)v25);
      ProviderName = CRefresherCache::FindProviderRecord(this, LPWSTR, v20, a2, &v24);
      if ( ProviderName < 0 )
      {
LABEL_12:
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, ProviderName);
LABEL_13:
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_583a410948f0357245c15279aca1a26e_Traceguids,
            (unsigned int)ProviderName);
        }
        goto LABEL_17;
      }
      v16 = v24;
    }
    ProviderName = CoImpersonateClient();
    if ( ProviderName >= 0 )
    {
      ProviderName = CRefresherCache::CreateObjectInfoForProvider(this, v15, v16, a3, a4, a2, a7, a8, a9, a11, a10);
      CoRevertToSelf();
    }
    if ( v16 )
      CHiPerfPrvRecord::Release(v16);
    if ( ProviderName >= 0 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v22 = GetMemLogObject();
  ProviderName = -2147217400;
  CMemoryLog::Write(v22, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_583a410948f0357245c15279aca1a26e_Traceguids, 2147749896LL);
  }
  return (unsigned int)ProviderName;
}

```

## disassembly

```asm
0x180054c00  push    rbx
0x180054c02  push    rbp
0x180054c03  push    rsi
0x180054c04  push    rdi
0x180054c05  push    r12
0x180054c07  push    r14
0x180054c09  push    r15
0x180054c0b  sub     rsp, 90h
0x180054c12  mov     r15, r9
0x180054c15  mov     r12, r8
0x180054c18  mov     rbp, rdx
0x180054c1b  mov     r14, rcx
0x180054c1e  mov     rsi, [rsp+0C8h+arg_28]
0x180054c26  test    rsi, rsi
0x180054c29  jz      loc_180054D87
0x180054c2f  cmp     qword ptr [rsi], 0
0x180054c33  jz      loc_180054D87
0x180054c39  xor     edi, edi
0x180054c3b  mov     [rsp+0C8h+var_68], rdi
0x180054c40  lea     rcx, [rsp+0C8h+var_60]
0x180054c45  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180054c4b  nop
0x180054c4c  mov     dword ptr [rsp+0C8h+arg_28], edi
0x180054c53  lea     r9, [rsp+0C8h+arg_28]; int *
0x180054c5b  lea     r8, [rsp+0C8h+var_60]; struct CVar *
0x180054c60  mov     rdx, [rsp+0C8h+arg_20]; struct IWbemClassObject *
0x180054c68  call    ?GetProviderName@CRefresherCache@@QEAAJPEAUIWbemClassObject@@AEAVCVar@@AEAH@Z; CRefresherCache::GetProviderName(IWbemClassObject *,CVar &,int &)
0x180054c6d  mov     ebx, eax
0x180054c6f  test    eax, eax
0x180054c71  js      loc_180054D7A
0x180054c77  cmp     dword ptr [rsp+0C8h+arg_28], edi
0x180054c7e  jnz     short loc_180054CB2
0x180054c80  lea     rcx, [rsp+0C8h+var_60]
0x180054c85  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180054c8b  mov     rdx, rax; unsigned __int16 *
0x180054c8e  lea     rax, [rsp+0C8h+var_68]
0x180054c93  mov     [rsp+0C8h+var_A8], rax; struct CHiPerfPrvRecord **
0x180054c98  mov     r9, rbp; struct IWbemServices *
0x180054c9b  mov     rcx, r14; this
0x180054c9e  call    ?FindProviderRecord@CRefresherCache@@QEAAJPEBG0PEAUIWbemServices@@PEAPEAVCHiPerfPrvRecord@@@Z; CRefresherCache::FindProviderRecord(ushort const *,ushort const *,IWbemServices *,CHiPerfPrvRecord * *)
0x180054ca3  mov     ebx, eax
0x180054ca5  test    eax, eax
0x180054ca7  js      loc_180054D31
0x180054cad  mov     rdi, [rsp+0C8h+var_68]
0x180054cb2  call    cs:__imp_CoImpersonateClient
0x180054cb8  mov     ebx, eax
0x180054cba  test    eax, eax
0x180054cbc  js      short loc_180054D20
0x180054cbe  mov     rax, [rsp+0C8h+arg_48]
0x180054cc6  mov     [rsp+0C8h+var_78], rax; struct IUnknown *
0x180054ccb  mov     rax, [rsp+0C8h+arg_50]
0x180054cd3  mov     [rsp+0C8h+var_80], rax; struct CRefreshInfo *
0x180054cd8  mov     rax, [rsp+0C8h+arg_40]
0x180054ce0  mov     [rsp+0C8h+var_88], rax; struct IWbemContext *
0x180054ce5  mov     eax, [rsp+0C8h+arg_38]
0x180054cec  mov     [rsp+0C8h+var_90], eax; int
0x180054cf0  mov     rax, [rsp+0C8h+arg_30]
0x180054cf8  mov     [rsp+0C8h+var_98], rax; struct IWbemObjectAccess *
0x180054cfd  mov     [rsp+0C8h+var_A0], rbp; struct IWbemServices *
0x180054d02  mov     [rsp+0C8h+var_A8], r15; unsigned __int16 *
0x180054d07  mov     r9, r12; unsigned __int16 *
0x180054d0a  mov     r8, rdi; struct CHiPerfPrvRecord *
0x180054d0d  mov     rdx, rsi; struct CRefresherId *
0x180054d10  mov     rcx, r14; this
0x180054d13  call    ?CreateObjectInfoForProvider@CRefresherCache@@QEAAJPEAVCRefresherId@@PEAVCHiPerfPrvRecord@@PEBG2PEAUIWbemServices@@PEAVCWbemObject@@JPEAUIWbemContext@@PEAVCRefreshInfo@@PEAUIUnknown@@@Z; CRefresherCache::CreateObjectInfoForProvider(CRefresherId *,CHiPerfPrvRecord *,ushort const *,ushort const *,IWbemServices *,CWbemObject *,long,IWbemContext *,CRefreshInfo *,IUnknown *)
0x180054d18  mov     ebx, eax
0x180054d1a  call    cs:__imp_CoRevertToSelf
0x180054d20  test    rdi, rdi
0x180054d23  jz      short loc_180054D2D
0x180054d25  mov     rcx, rdi; this
0x180054d28  call    ?Release@CHiPerfPrvRecord@@QEAAJXZ; CHiPerfPrvRecord::Release(void)
0x180054d2d  test    ebx, ebx
0x180054d2f  jns     short loc_180054D42
0x180054d31  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180054d37  mov     edx, ebx
0x180054d39  mov     rcx, rax
0x180054d3c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180054d42  lea     rax, WPP_GLOBAL_Control
0x180054d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d50  cmp     rcx, rax
0x180054d53  jz      short loc_180054D7A
0x180054d55  test    byte ptr [rcx+1Ch], 1
0x180054d59  jz      short loc_180054D7A
0x180054d5b  cmp     byte ptr [rcx+19h], 2
0x180054d5f  jb      short loc_180054D7A
0x180054d61  mov     edx, 0Bh
0x180054d66  mov     r9d, ebx
0x180054d69  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180054d70  mov     rcx, [rcx+10h]
0x180054d74  call    WPP_SF_d
0x180054d79  nop
0x180054d7a  lea     rcx, [rsp+0C8h+var_60]
0x180054d7f  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180054d85  jmp     short loc_180054DD7
0x180054d87  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180054d8d  mov     ebx, 80041008h
0x180054d92  mov     edx, ebx
0x180054d94  mov     rcx, rax
0x180054d97  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180054d9d  lea     rax, WPP_GLOBAL_Control
0x180054da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180054dab  cmp     rcx, rax
0x180054dae  jz      short loc_180054DD7
0x180054db0  test    byte ptr [rcx+1Ch], 1
0x180054db4  jz      short loc_180054DD7
0x180054db6  cmp     byte ptr [rcx+19h], 2
0x180054dba  jb      short loc_180054DD7
0x180054dbc  mov     edx, 0Ah
0x180054dc1  mov     r9d, 80041008h
0x180054dc7  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180054dce  mov     rcx, [rcx+10h]
0x180054dd2  call    WPP_SF_d
0x180054dd7  mov     eax, ebx
0x180054dd9  add     rsp, 90h
0x180054de0  pop     r15
0x180054de2  pop     r14
0x180054de4  pop     r12
0x180054de6  pop     rdi
0x180054de7  pop     rsi
0x180054de8  pop     rbp
0x180054de9  pop     rbx
0x180054dea  retn
```
