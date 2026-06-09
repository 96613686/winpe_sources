# CRefresherCache::AddEnumToRefresher(IWbemServices *,ushort const *,ushort const *,IWbemClassObject *,_WBEM_REFRESHER_ID *,IWbemClassObject *,ushort const *,long,IWbemContext *,IUnknown *,_WBEM_REFRESH_INFO *)

- ea: `0x180054e80`
- end: `0x180055088`
- name: `?AddEnumToRefresher@CRefresherCache@@MEAAJPEAUIWbemServices@@PEBG1PEAUIWbemClassObject@@PEAU_WBEM_REFRESHER_ID@@21JPEAUIWbemContext@@PEAUIUnknown@@PEAU_WBEM_REFRESH_INFO@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(CRefresherCache *this, struct IWbemServices *, const unsigned __int16 *, const unsigned __int16 *, struct IWbemClassObject *, struct _WBEM_REFRESHER_ID *, struct IWbemObjectAccess *, unsigned __int16 *, int, struct IWbemContext *, struct IUnknown *, struct _WBEM_REFRESH_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180054e00`

## callees

- `0x180037120`
- `0x180054e80`
- `0x180055090`
- `0x180055210`
- `0x1800558a4`
- `0x180055eb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180054fa7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180054fa7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180054f32`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180054f32`
- `wbemcomn!GetMemLogObject` at `0x180054ffa`
- `wbemcomn!GetMemLogObject` at `0x18005500e`
- `wbemcomn!GetMemLogObject` at `0x180054ffa`
- `wbemcomn!GetMemLogObject` at `0x18005500e`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180054f05`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180054f05`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180054ec5`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180054ec5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055006`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005501e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055006`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005501e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180054fe0`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180054fe0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRefresherCache::AddEnumToRefresher(
        CRefresherCache *this,
        struct IWbemServices *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IWbemClassObject *a5,
        struct _WBEM_REFRESHER_ID *a6,
        struct IWbemObjectAccess *a7,
        unsigned __int16 *a8,
        int a9,
        struct IWbemContext *a10,
        struct IUnknown *a11,
        struct _WBEM_REFRESH_INFO *a12)
{
  struct CRefresherId *v16; // rsi
  struct CHiPerfPrvRecord *v17; // rdi
  CRefresherCache *v18; // rcx
  HRESULT ProviderName; // ebx
  const unsigned __int16 *LPWSTR; // rax
  const unsigned __int16 *v21; // r8
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v24; // rax
  struct CHiPerfPrvRecord *v25; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v26[96]; // [rsp+68h] [rbp-60h] BYREF

  v16 = a6;
  if ( a6 && *(_QWORD *)a6 )
  {
    v17 = 0;
    v25 = 0;
    CVar::CVar((CVar *)v26);
    LODWORD(a6) = 0;
    ProviderName = CRefresherCache::GetProviderName(v18, a5, (struct CVar *)v26, (int *)&a6);
    if ( ProviderName < 0 )
    {
LABEL_14:
      CVar::~CVar((CVar *)v26);
      return (unsigned int)ProviderName;
    }
    if ( !(_DWORD)a6 )
    {
      LPWSTR = CVar::GetLPWSTR((CVar *)v26);
      ProviderName = CRefresherCache::FindProviderRecord(this, LPWSTR, v21, a2, &v25);
      if ( ProviderName < 0 )
      {
LABEL_16:
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, ProviderName);
LABEL_12:
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_583a410948f0357245c15279aca1a26e_Traceguids,
            (unsigned int)ProviderName);
        }
        goto LABEL_14;
      }
      v17 = v25;
    }
    ProviderName = CoImpersonateClient();
    if ( ProviderName >= 0 )
    {
      ProviderName = CRefresherCache::CreateEnumInfoForProvider(this, v16, v17, a3, a4, a2, a7, a8, a9, a10, a12, a11);
      CoRevertToSelf();
    }
    if ( v17 )
      CHiPerfPrvRecord::Release(v17);
    if ( ProviderName >= 0 )
      goto LABEL_12;
    goto LABEL_16;
  }
  v24 = GetMemLogObject();
  ProviderName = -2147217400;
  CMemoryLog::Write(v24, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_583a410948f0357245c15279aca1a26e_Traceguids, 2147749896LL);
  }
  return (unsigned int)ProviderName;
}

```

## disassembly

```asm
0x180054e80  push    rbx
0x180054e82  push    rbp
0x180054e83  push    rsi
0x180054e84  push    rdi
0x180054e85  push    r12
0x180054e87  push    r14
0x180054e89  push    r15
0x180054e8b  sub     rsp, 90h
0x180054e92  mov     r15, r9
0x180054e95  mov     r12, r8
0x180054e98  mov     rbp, rdx
0x180054e9b  mov     r14, rcx
0x180054e9e  mov     rsi, [rsp+0C8h+arg_28]
0x180054ea6  test    rsi, rsi
0x180054ea9  jz      loc_18005500E
0x180054eaf  cmp     qword ptr [rsi], 0
0x180054eb3  jz      loc_18005500E
0x180054eb9  xor     edi, edi
0x180054ebb  mov     [rsp+0C8h+var_68], rdi
0x180054ec0  lea     rcx, [rsp+0C8h+var_60]
0x180054ec5  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180054ecb  nop
0x180054ecc  mov     dword ptr [rsp+0C8h+arg_28], edi
0x180054ed3  lea     r9, [rsp+0C8h+arg_28]; int *
0x180054edb  lea     r8, [rsp+0C8h+var_60]; struct CVar *
0x180054ee0  mov     rdx, [rsp+0C8h+arg_20]; struct IWbemClassObject *
0x180054ee8  call    ?GetProviderName@CRefresherCache@@QEAAJPEAUIWbemClassObject@@AEAVCVar@@AEAH@Z; CRefresherCache::GetProviderName(IWbemClassObject *,CVar &,int &)
0x180054eed  mov     ebx, eax
0x180054eef  test    eax, eax
0x180054ef1  js      loc_180054FDB
0x180054ef7  cmp     dword ptr [rsp+0C8h+arg_28], edi
0x180054efe  jnz     short loc_180054F32
0x180054f00  lea     rcx, [rsp+0C8h+var_60]
0x180054f05  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180054f0b  mov     rdx, rax; unsigned __int16 *
0x180054f0e  lea     rax, [rsp+0C8h+var_68]
0x180054f13  mov     [rsp+0C8h+var_A8], rax; struct CHiPerfPrvRecord **
0x180054f18  mov     r9, rbp; struct IWbemServices *
0x180054f1b  mov     rcx, r14; this
0x180054f1e  call    ?FindProviderRecord@CRefresherCache@@QEAAJPEBG0PEAUIWbemServices@@PEAPEAVCHiPerfPrvRecord@@@Z; CRefresherCache::FindProviderRecord(ushort const *,ushort const *,IWbemServices *,CHiPerfPrvRecord * *)
0x180054f23  mov     ebx, eax
0x180054f25  test    eax, eax
0x180054f27  js      loc_180054FFA
0x180054f2d  mov     rdi, [rsp+0C8h+var_68]
0x180054f32  call    cs:__imp_CoImpersonateClient
0x180054f38  mov     ebx, eax
0x180054f3a  test    eax, eax
0x180054f3c  js      short loc_180054FAD
0x180054f3e  mov     rax, [rsp+0C8h+arg_50]
0x180054f46  mov     [rsp+0C8h+var_70], rax; struct IUnknown *
0x180054f4b  mov     rax, [rsp+0C8h+arg_58]
0x180054f53  mov     [rsp+0C8h+var_78], rax; struct CRefreshInfo *
0x180054f58  mov     rax, [rsp+0C8h+arg_48]
0x180054f60  mov     [rsp+0C8h+var_80], rax; struct IWbemContext *
0x180054f65  mov     eax, [rsp+0C8h+arg_40]
0x180054f6c  mov     [rsp+0C8h+var_88], eax; int
0x180054f70  mov     rax, [rsp+0C8h+arg_38]
0x180054f78  mov     [rsp+0C8h+var_90], rax; unsigned __int16 *
0x180054f7d  mov     rax, [rsp+0C8h+arg_30]
0x180054f85  mov     [rsp+0C8h+var_98], rax; struct IWbemObjectAccess *
0x180054f8a  mov     [rsp+0C8h+var_A0], rbp; struct IWbemServices *
0x180054f8f  mov     [rsp+0C8h+var_A8], r15; unsigned __int16 *
0x180054f94  mov     r9, r12; unsigned __int16 *
0x180054f97  mov     r8, rdi; struct CHiPerfPrvRecord *
0x180054f9a  mov     rdx, rsi; struct CRefresherId *
0x180054f9d  mov     rcx, r14; this
0x180054fa0  call    ?CreateEnumInfoForProvider@CRefresherCache@@QEAAJPEAVCRefresherId@@PEAVCHiPerfPrvRecord@@PEBG2PEAUIWbemServices@@PEAVCWbemObject@@2JPEAUIWbemContext@@PEAVCRefreshInfo@@PEAUIUnknown@@@Z; CRefresherCache::CreateEnumInfoForProvider(CRefresherId *,CHiPerfPrvRecord *,ushort const *,ushort const *,IWbemServices *,CWbemObject *,ushort const *,long,IWbemContext *,CRefreshInfo *,IUnknown *)
0x180054fa5  mov     ebx, eax
0x180054fa7  call    cs:__imp_CoRevertToSelf
0x180054fad  test    rdi, rdi
0x180054fb0  jz      short loc_180054FBA
0x180054fb2  mov     rcx, rdi; this
0x180054fb5  call    ?Release@CHiPerfPrvRecord@@QEAAJXZ; CHiPerfPrvRecord::Release(void)
0x180054fba  test    ebx, ebx
0x180054fbc  js      short loc_180054FFA
0x180054fbe  lea     rax, WPP_GLOBAL_Control
0x180054fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180054fcc  cmp     rcx, rax
0x180054fcf  jz      short loc_180054FDB
0x180054fd1  test    byte ptr [rcx+1Ch], 1
0x180054fd5  jnz     loc_180055060
0x180054fdb  lea     rcx, [rsp+0C8h+var_60]
0x180054fe0  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180054fe6  mov     eax, ebx
0x180054fe8  add     rsp, 90h
0x180054fef  pop     r15
0x180054ff1  pop     r14
0x180054ff3  pop     r12
0x180054ff5  pop     rdi
0x180054ff6  pop     rsi
0x180054ff7  pop     rbp
0x180054ff8  pop     rbx
0x180054ff9  retn
0x180054ffa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180055000  nop
0x180055001  mov     edx, ebx
0x180055003  mov     rcx, rax
0x180055006  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005500c  jmp     short loc_180054FBE
0x18005500e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180055014  mov     ebx, 80041008h
0x180055019  mov     edx, ebx
0x18005501b  mov     rcx, rax
0x18005501e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180055024  lea     rax, WPP_GLOBAL_Control
0x18005502b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055032  cmp     rcx, rax
0x180055035  jz      short loc_180054FE6
0x180055037  test    byte ptr [rcx+1Ch], 1
0x18005503b  jz      short loc_180054FE6
0x18005503d  cmp     byte ptr [rcx+19h], 2
0x180055041  jb      short loc_180054FE6
0x180055043  mov     edx, 0Ch
0x180055048  mov     r9d, 80041008h
0x18005504e  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180055055  mov     rcx, [rcx+10h]
0x180055059  call    WPP_SF_d
0x18005505e  jmp     short loc_180054FE6
0x180055060  cmp     byte ptr [rcx+19h], 2
0x180055064  jb      loc_180054FDB
0x18005506a  mov     edx, 0Dh
0x18005506f  mov     r9d, ebx
0x180055072  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180055079  mov     rcx, [rcx+10h]
0x18005507d  call    WPP_SF_d
0x180055082  jmp     loc_180054FDB
```
