# CRefresherCache::CreateObjectInfoForProvider(CRefresherId *,CHiPerfPrvRecord *,ushort const *,ushort const *,IWbemServices *,CWbemObject *,long,IWbemContext *,CRefreshInfo *,IUnknown *)

- ea: `0x1800548a0`
- end: `0x180054bf2`
- name: `?CreateObjectInfoForProvider@CRefresherCache@@QEAAJPEAVCRefresherId@@PEAVCHiPerfPrvRecord@@PEBG2PEAUIWbemServices@@PEAVCWbemObject@@JPEAUIWbemContext@@PEAVCRefreshInfo@@PEAUIUnknown@@@Z`
- size: `850`
- prototype: `__int64 __usercall@<rax>(CRefresherCache *__hidden this@<rcx>, struct CRefresherId *@<rdx>, struct CHiPerfPrvRecord *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct IWbemServices *, struct IWbemObjectAccess *, int, struct IWbemContext *, struct CRefreshInfo *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054c00`

## callees

- `0x180037120`
- `0x1800548a0`
- `0x180055c28`
- `0x180055d48`
- `0x180056048`
- `0x18005609c`
- `0x180084fdc`
- `0x180085820`
- `0x18008b824`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800548e7`
- `wbemcomn!GetMemLogObject` at `0x18005495f`
- `wbemcomn!GetMemLogObject` at `0x180054b8b`
- `wbemcomn!GetMemLogObject` at `0x1800548e7`
- `wbemcomn!GetMemLogObject` at `0x18005495f`
- `wbemcomn!GetMemLogObject` at `0x180054b8b`
- `wbemcomn!??BWString@@QEBAPEBGXZ` at `0x180054a39`
- `wbemcomn!??BWString@@QEBAPEBGXZ` at `0x180054b3e`
- `wbemcomn!??BWString@@QEBAPEBGXZ` at `0x180054a39`
- `wbemcomn!??BWString@@QEBAPEBGXZ` at `0x180054b3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800548f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005496a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180054b97`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800548f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005496a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180054b97`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRefresherCache::CreateObjectInfoForProvider(
        CRefresherCache *this,
        struct CRefresherId *a2,
        struct CHiPerfPrvRecord *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IWbemServices *a6,
        struct IWbemObjectAccess *a7,
        int a8,
        struct IWbemContext *a9,
        struct CRefreshInfo *a10,
        struct IUnknown *a11)
{
  int DestinationContext; // ebx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v17; // r10
  __int64 v18; // rdx
  CMemoryLog *v20; // rax
  int v21; // eax
  int RefresherRecord; // r14d
  CRefresherRecord *v23; // rdi
  struct _IWmiProviderStack *v24; // rbx
  CRefresherRecord *v25; // rsi
  const unsigned __int16 *v26; // rax
  const unsigned __int16 *v27; // rax
  CMemoryLog *v28; // rax
  tagMSHCTX v29[2]; // [rsp+68h] [rbp-29h] BYREF
  struct _IWmiProviderStack *v30; // [rsp+70h] [rbp-21h] BYREF
  struct _GUID v31; // [rsp+78h] [rbp-19h] BYREF
  CRefresherRecord *v32; // [rsp+88h] [rbp-9h]

  v29[0] = MSHCTX_LOCAL;
  DestinationContext = CRefresherCache::GetDestinationContext(v29, a2);
  if ( DestinationContext < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, DestinationContext);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)DestinationContext;
    }
    v18 = 19;
LABEL_6:
    WPP_SF_d(
      *((_QWORD *)v17 + 2),
      v18,
      WPP_583a410948f0357245c15279aca1a26e_Traceguids,
      (unsigned int)DestinationContext);
    return (unsigned int)DestinationContext;
  }
  DestinationContext = ((__int64 (__fastcall *)(struct IWbemObjectAccess *, const unsigned __int16 *, unsigned __int16 *))a7->lpVtbl[2].Release)(
                         a7,
                         a4,
                         a5);
  if ( DestinationContext < 0 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, DestinationContext);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)DestinationContext;
    }
    v18 = 20;
    goto LABEL_6;
  }
  if ( a3 )
  {
    if ( v29[0] )
    {
      if ( v29[0] != MSHCTX_INPROC )
      {
        *(_QWORD *)v29 = 0;
        RefresherRecord = CRefresherCache::FindRefresherRecord(this, a2, 1, a11, (struct CRefresherRecord **)v29);
        v23 = *(CRefresherRecord **)v29;
        v32 = *(CRefresherRecord **)v29;
        if ( RefresherRecord >= 0 )
        {
          *(_QWORD *)v29 = 0;
          v31 = *(struct _GUID *)((char *)a3 + 24);
          CRefresherRecord::FindProviderRecord(v23, &v31, (struct IWbemHiPerfProvider **)v29);
          v24 = 0;
          v30 = 0;
          v25 = *(CRefresherRecord **)v29;
          if ( !*(_QWORD *)v29 )
          {
            v26 = (const unsigned __int16 *)WString::operator unsigned short const *((char *)a3 + 16);
            RefresherRecord = CRefresherCache::LoadProviderInner(
                                this,
                                v26,
                                a5,
                                a6,
                                a9,
                                (struct IWbemHiPerfProvider **)v29,
                                &v30);
            v25 = *(CRefresherRecord **)v29;
            v24 = v30;
          }
          *(_QWORD *)&v31.Data1 = v25;
          v30 = v24;
          if ( RefresherRecord >= 0 )
            RefresherRecord = (*(__int64 (__fastcall **)(CRefresherRecord *, struct CHiPerfPrvRecord *, _QWORD, struct _IWmiProviderStack *, struct IWbemServices *, const unsigned __int16 *, unsigned __int16 *, struct IWbemObjectAccess *, int, struct IWbemContext *, struct CRefreshInfo *))(*(_QWORD *)v23 + 56LL))(
                                v23,
                                a3,
                                *(_QWORD *)v29,
                                v24,
                                a6,
                                a4,
                                a5,
                                a7,
                                a8,
                                a9,
                                a10);
          if ( v24 )
            (*(void (__fastcall **)(struct _IWmiProviderStack *))(*(_QWORD *)v24 + 16LL))(v24);
          v30 = 0;
          if ( v25 )
            (*(void (__fastcall **)(CRefresherRecord *))(*(_QWORD *)v25 + 16LL))(v25);
          *(_QWORD *)&v31.Data1 = 0;
        }
        if ( v23 )
          (*(void (__fastcall **)(CRefresherRecord *))(*(_QWORD *)v23 + 16LL))(v23);
        v32 = 0;
        goto LABEL_33;
      }
      v27 = (const unsigned __int16 *)WString::operator unsigned short const *((char *)a3 + 16);
      v21 = CRefreshInfo::SetDirect(
              a10,
              (const struct _GUID *)((char *)a3 + 40),
              a5,
              v27,
              a7,
              (CRefresherCache *)((char *)this + 272));
    }
    else
    {
      v21 = CRefreshInfo::SetClientLoadable(a10, (const struct _GUID *)((char *)a3 + 40), a5, a7);
    }
  }
  else
  {
    v21 = CRefreshInfo::SetNonHiPerf(a10, a5, a7);
  }
  RefresherRecord = v21;
LABEL_33:
  if ( RefresherRecord < 0 )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, RefresherRecord);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_583a410948f0357245c15279aca1a26e_Traceguids,
      (unsigned int)RefresherRecord);
  }
  return (unsigned int)RefresherRecord;
}

```

## disassembly

```asm
0x1800548a0  mov     rax, rsp
0x1800548a3  mov     [rax+10h], rbx
0x1800548a7  mov     [rax+20h], r9
0x1800548ab  mov     [rax+8], rcx
0x1800548af  push    rbp
0x1800548b0  push    rsi
0x1800548b1  push    rdi
0x1800548b2  push    r12
0x1800548b4  push    r13
0x1800548b6  push    r14
0x1800548b8  push    r15
0x1800548ba  lea     rbp, [rax-3Fh]
0x1800548be  sub     rsp, 90h
0x1800548c5  mov     r14, r9
0x1800548c8  mov     r15, r8
0x1800548cb  mov     rdi, rdx
0x1800548ce  mov     rsi, rcx
0x1800548d1  mov     [rbp+37h+var_60], 0
0x1800548d8  lea     rcx, [rbp+37h+var_60]; enum tagMSHCTX *
0x1800548dc  call    ?GetDestinationContext@CRefresherCache@@SAJAEAW4tagMSHCTX@@PEAVCRefresherId@@@Z; CRefresherCache::GetDestinationContext(tagMSHCTX &,CRefresherId *)
0x1800548e1  mov     ebx, eax
0x1800548e3  test    eax, eax
0x1800548e5  jns     short loc_180054938
0x1800548e7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800548ed  mov     edx, ebx
0x1800548ef  mov     rcx, rax
0x1800548f2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800548f8  lea     rcx, WPP_GLOBAL_Control
0x1800548ff  mov     r10, cs:WPP_GLOBAL_Control
0x180054906  cmp     r10, rcx
0x180054909  jz      short loc_180054931
0x18005490b  test    byte ptr [r10+1Ch], 1
0x180054910  jz      short loc_180054931
0x180054912  cmp     byte ptr [r10+19h], 2
0x180054917  jb      short loc_180054931
0x180054919  mov     edx, 13h
0x18005491e  mov     r9d, ebx
0x180054921  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180054928  mov     rcx, [r10+10h]
0x18005492c  call    WPP_SF_d
0x180054931  mov     eax, ebx
0x180054933  jmp     loc_180054BD7
0x180054938  mov     r12, [rbp+37h+arg_30]
0x18005493c  mov     rax, [r12]
0x180054940  mov     r13, [rbp+37h+arg_20]
0x180054944  mov     r8, r13
0x180054947  mov     rdx, r14
0x18005494a  mov     rcx, r12
0x18005494d  mov     rax, [rax+260h]
0x180054954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054959  mov     ebx, eax
0x18005495b  test    eax, eax
0x18005495d  jns     short loc_180054998
0x18005495f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180054965  mov     edx, ebx
0x180054967  mov     rcx, rax
0x18005496a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180054970  lea     rcx, WPP_GLOBAL_Control
0x180054977  mov     r10, cs:WPP_GLOBAL_Control
0x18005497e  cmp     r10, rcx
0x180054981  jz      short loc_180054931
0x180054983  test    byte ptr [r10+1Ch], 1
0x180054988  jz      short loc_180054931
0x18005498a  cmp     byte ptr [r10+19h], 2
0x18005498f  jb      short loc_180054931
0x180054991  mov     edx, 14h
0x180054996  jmp     short loc_18005491E
0x180054998  test    r15, r15
0x18005499b  jnz     short loc_1800549B4
0x18005499d  mov     r8, r12; struct IWbemObjectAccess *
0x1800549a0  mov     rdx, r13; unsigned __int16 *
0x1800549a3  mov     rcx, [rbp+37h+arg_48]; this
0x1800549aa  call    ?SetNonHiPerf@CRefreshInfo@@QEAAJPEBGPEAUIWbemObjectAccess@@@Z; CRefreshInfo::SetNonHiPerf(ushort const *,IWbemObjectAccess *)
0x1800549af  jmp     loc_180054B83
0x1800549b4  mov     eax, [rbp+37h+var_60]
0x1800549b7  test    eax, eax
0x1800549b9  jz      loc_180054B35
0x1800549bf  cmp     eax, 3
0x1800549c2  jz      loc_180054B3A
0x1800549c8  mov     qword ptr [rbp+37h+var_60], 0
0x1800549d0  lea     rax, [rbp+37h+var_60]
0x1800549d4  mov     [rsp+0C0h+var_A0], rax; struct CRefresherRecord **
0x1800549d9  mov     r9, [rbp+37h+arg_50]; struct IUnknown *
0x1800549e0  mov     r8d, 1; int
0x1800549e6  mov     rdx, rdi; struct CRefresherId *
0x1800549e9  mov     rcx, rsi; this
0x1800549ec  call    ?FindRefresherRecord@CRefresherCache@@QEAAJPEAVCRefresherId@@HPEAUIUnknown@@PEAPEAVCRefresherRecord@@@Z; CRefresherCache::FindRefresherRecord(CRefresherId *,int,IUnknown *,CRefresherRecord * *)
0x1800549f1  mov     r14d, eax
0x1800549f4  mov     rdi, qword ptr [rbp+37h+var_60]
0x1800549f8  mov     [rbp+37h+var_40], rdi
0x1800549fc  test    eax, eax
0x1800549fe  js      loc_180054B17
0x180054a04  mov     qword ptr [rbp+37h+var_60], 0
0x180054a0c  movups  xmm0, xmmword ptr [r15+18h]
0x180054a11  movdqu  xmmword ptr [rbp+37h+var_50.Data1], xmm0
0x180054a16  lea     r8, [rbp+37h+var_60]; struct IWbemHiPerfProvider **
0x180054a1a  lea     rdx, [rbp+37h+var_50]; struct _GUID
0x180054a1e  mov     rcx, rdi; this
0x180054a21  call    ?FindProviderRecord@CRefresherRecord@@QEAAPEAVCProviderRecord@@U_GUID@@PEAPEAUIWbemHiPerfProvider@@@Z; CRefresherRecord::FindProviderRecord(_GUID,IWbemHiPerfProvider * *)
0x180054a26  xor     ebx, ebx
0x180054a28  mov     [rbp+37h+var_58], rbx
0x180054a2c  mov     rsi, qword ptr [rbp+37h+var_60]
0x180054a30  test    rsi, rsi
0x180054a33  jnz     short loc_180054A7B
0x180054a35  lea     rcx, [r15+10h]
0x180054a39  call    cs:__imp_??BWString@@QEBAPEBGXZ; WString::operator ushort const *(void)
0x180054a3f  lea     rcx, [rbp+37h+var_58]
0x180054a43  mov     [rsp+0C0h+var_90], rcx; struct _IWmiProviderStack **
0x180054a48  lea     rcx, [rbp+37h+var_60]
0x180054a4c  mov     [rsp+0C0h+var_98], rcx; struct IWbemHiPerfProvider **
0x180054a51  mov     rcx, [rbp+37h+arg_40]
0x180054a58  mov     [rsp+0C0h+var_A0], rcx; struct IWbemContext *
0x180054a5d  mov     r9, [rbp+37h+arg_28]; struct IWbemServices *
0x180054a61  mov     r8, r13; unsigned __int16 *
0x180054a64  mov     rdx, rax; unsigned __int16 *
0x180054a67  mov     rcx, [rbp+37h+arg_0]; this
0x180054a6b  call    ?LoadProviderInner@CRefresherCache@@QEAAJPEBG0PEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemHiPerfProvider@@PEAPEAU_IWmiProviderStack@@@Z; CRefresherCache::LoadProviderInner(ushort const *,ushort const *,IWbemServices *,IWbemContext *,IWbemHiPerfProvider * *,_IWmiProviderStack * *)
0x180054a70  mov     r14d, eax
0x180054a73  mov     rsi, qword ptr [rbp+37h+var_60]
0x180054a77  mov     rbx, [rbp+37h+var_58]
0x180054a7b  mov     qword ptr [rbp+37h+var_50.Data1], rsi
0x180054a7f  mov     [rbp+37h+var_58], rbx
0x180054a83  test    r14d, r14d
0x180054a86  js      short loc_180054ADF
0x180054a88  mov     rax, [rdi]
0x180054a8b  mov     rcx, [rbp+37h+arg_48]
0x180054a92  mov     [rsp+50h], rcx
0x180054a97  mov     rcx, [rbp+37h+arg_40]
0x180054a9e  mov     [rsp+0C0h+var_78], rcx
0x180054aa3  mov     ecx, [rbp+37h+arg_38]
0x180054aa6  mov     dword ptr [rsp+0C0h+var_80], ecx
0x180054aaa  mov     qword ptr [rsp+0C0h+var_88], r12
0x180054aaf  mov     [rsp+0C0h+var_90], r13
0x180054ab4  mov     rcx, [rbp+37h+arg_18]
0x180054ab8  mov     [rsp+0C0h+var_98], rcx
0x180054abd  mov     rcx, [rbp+37h+arg_28]
0x180054ac1  mov     [rsp+0C0h+var_A0], rcx
0x180054ac6  mov     r9, rbx
0x180054ac9  mov     r8, qword ptr [rbp+37h+var_60]
0x180054acd  mov     rdx, r15
0x180054ad0  mov     rcx, rdi
0x180054ad3  mov     rax, [rax+38h]
0x180054ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054adc  mov     r14d, eax
0x180054adf  test    rbx, rbx
0x180054ae2  jz      short loc_180054AF3
0x180054ae4  mov     rax, [rbx]
0x180054ae7  mov     rcx, rbx
0x180054aea  mov     rax, [rax+10h]
0x180054aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054af3  mov     [rbp+37h+var_58], 0
0x180054afb  test    rsi, rsi
0x180054afe  jz      short loc_180054B0F
0x180054b00  mov     rax, [rsi]
0x180054b03  mov     rcx, rsi
0x180054b06  mov     rax, [rax+10h]
0x180054b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b0f  mov     qword ptr [rbp+37h+var_50.Data1], 0
0x180054b17  test    rdi, rdi
0x180054b1a  jz      short loc_180054B2B
0x180054b1c  mov     rax, [rdi]
0x180054b1f  mov     rcx, rdi
0x180054b22  mov     rax, [rax+10h]
0x180054b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b2b  mov     [rbp+37h+var_40], 0
0x180054b33  jmp     short loc_180054B86
0x180054b35  cmp     eax, 3
0x180054b38  jnz     short loc_180054B6D
0x180054b3a  lea     rcx, [r15+10h]
0x180054b3e  call    cs:__imp_??BWString@@QEBAPEBGXZ; WString::operator ushort const *(void)
0x180054b44  lea     rcx, [rsi+110h]
0x180054b4b  mov     [rsp+0C0h+var_98], rcx; struct _IWbemRefresherMgr *
0x180054b50  mov     [rsp+0C0h+var_A0], r12; struct IWbemObjectAccess *
0x180054b55  mov     r9, rax; unsigned __int16 *
0x180054b58  mov     r8, r13; unsigned __int16 *
0x180054b5b  lea     rdx, [r15+28h]; struct _GUID *
0x180054b5f  mov     rcx, [rbp+37h+arg_48]; this
0x180054b66  call    ?SetDirect@CRefreshInfo@@QEAAJAEBU_GUID@@PEBG1PEAUIWbemObjectAccess@@PEAU_IWbemRefresherMgr@@@Z; CRefreshInfo::SetDirect(_GUID const &,ushort const *,ushort const *,IWbemObjectAccess *,_IWbemRefresherMgr *)
0x180054b6b  jmp     short loc_180054B83
0x180054b6d  mov     r9, r12; struct IWbemObjectAccess *
0x180054b70  mov     r8, r13; unsigned __int16 *
0x180054b73  lea     rdx, [r15+28h]; struct _GUID *
0x180054b77  mov     rcx, [rbp+37h+arg_48]; this
0x180054b7e  call    ?SetClientLoadable@CRefreshInfo@@QEAAJAEBU_GUID@@PEBGPEAUIWbemObjectAccess@@@Z; CRefreshInfo::SetClientLoadable(_GUID const &,ushort const *,IWbemObjectAccess *)
0x180054b83  mov     r14d, eax
0x180054b86  test    r14d, r14d
0x180054b89  jns     short loc_180054B9D
0x180054b8b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180054b91  mov     edx, r14d
0x180054b94  mov     rcx, rax
0x180054b97  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180054b9d  lea     rcx, WPP_GLOBAL_Control
0x180054ba4  mov     rax, cs:WPP_GLOBAL_Control
0x180054bab  cmp     rax, rcx
0x180054bae  jz      short loc_180054BD4
0x180054bb0  test    byte ptr [rax+1Ch], 1
0x180054bb4  jz      short loc_180054BD4
0x180054bb6  cmp     byte ptr [rax+19h], 2
0x180054bba  jb      short loc_180054BD4
0x180054bbc  mov     edx, 15h
0x180054bc1  mov     r9d, r14d
0x180054bc4  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180054bcb  mov     rcx, [rax+10h]
0x180054bcf  call    WPP_SF_d
0x180054bd4  mov     eax, r14d
0x180054bd7  mov     rbx, [rsp+0C0h+arg_8]
0x180054bdf  add     rsp, 90h
0x180054be6  pop     r15
0x180054be8  pop     r14
0x180054bea  pop     r13
0x180054bec  pop     r12
0x180054bee  pop     rdi
0x180054bef  pop     rsi
0x180054bf0  pop     rbp
0x180054bf1  retn
```
