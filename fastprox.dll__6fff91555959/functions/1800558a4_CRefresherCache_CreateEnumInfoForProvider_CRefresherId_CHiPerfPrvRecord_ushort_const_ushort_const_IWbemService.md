# CRefresherCache::CreateEnumInfoForProvider(CRefresherId *,CHiPerfPrvRecord *,ushort const *,ushort const *,IWbemServices *,CWbemObject *,ushort const *,long,IWbemContext *,CRefreshInfo *,IUnknown *)

- ea: `0x1800558a4`
- end: `0x180055c1f`
- name: `?CreateEnumInfoForProvider@CRefresherCache@@QEAAJPEAVCRefresherId@@PEAVCHiPerfPrvRecord@@PEBG2PEAUIWbemServices@@PEAVCWbemObject@@2JPEAUIWbemContext@@PEAVCRefreshInfo@@PEAUIUnknown@@@Z`
- size: `891`
- prototype: `__int64 __usercall@<rax>(CRefresherCache *__hidden this@<rcx>, struct CRefresherId *@<rdx>, struct CHiPerfPrvRecord *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct IWbemServices *, struct IWbemObjectAccess *, const unsigned __int16 *, int, struct IWbemContext *, struct CRefreshInfo *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054e80`

## callees

- `0x180037120`
- `0x1800558a4`
- `0x180055c28`
- `0x180055d48`
- `0x180056048`
- `0x18005609c`
- `0x180084fdc`
- `0x180085820`
- `0x18008b824`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800559fb`
- `wbemcomn!GetMemLogObject` at `0x180055a4e`
- `wbemcomn!GetMemLogObject` at `0x180055baa`
- `wbemcomn!GetMemLogObject` at `0x1800559fb`
- `wbemcomn!GetMemLogObject` at `0x180055a4e`
- `wbemcomn!GetMemLogObject` at `0x180055baa`
- `wbemcomn!??BWString@@QEBAPEBGXZ` at `0x180055b05`
- `wbemcomn!??BWString@@QEBAPEBGXZ` at `0x180055bc5`
- `wbemcomn!??BWString@@QEBAPEBGXZ` at `0x180055b05`
- `wbemcomn!??BWString@@QEBAPEBGXZ` at `0x180055bc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055a06`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055a5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055bb6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055a06`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055a5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055bb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall CRefresherCache::CreateEnumInfoForProvider(
        CRefresherCache *this,
        struct CRefresherId *a2,
        struct CHiPerfPrvRecord *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IWbemServices *a6,
        struct IWbemObjectAccess *a7,
        const unsigned __int16 *a8,
        int a9,
        struct IWbemContext *a10,
        struct CRefreshInfo *a11,
        struct IUnknown *a12)
{
  int DestinationContext; // ebx
  int RefresherRecord; // r14d
  struct _IWmiProviderStack *v18; // rbx
  int result; // eax
  CWbemRefreshingSvc *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v23; // rdx
  CRefresherRecord *v24; // rsi
  CRefresherRecord *v25; // rdi
  const unsigned __int16 *v26; // rax
  CMemoryLog *v27; // rax
  const unsigned __int16 *v28; // rax
  enum tagMSHCTX v29[2]; // [rsp+68h] [rbp-29h] BYREF
  struct _IWmiProviderStack *v30; // [rsp+70h] [rbp-21h] BYREF
  struct _GUID v31; // [rsp+78h] [rbp-19h] BYREF
  CRefresherRecord *v32; // [rsp+88h] [rbp-9h]

  v29[0] = MSHCTX_LOCAL;
  DestinationContext = CRefresherCache::GetDestinationContext(v29, a2);
  if ( DestinationContext >= 0 )
  {
    RefresherRecord = ((__int64 (__fastcall *)(struct IWbemObjectAccess *, const unsigned __int16 *, unsigned __int16 *))a7->lpVtbl[2].Release)(
                        a7,
                        a4,
                        a5);
    v18 = 0;
    if ( RefresherRecord < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, RefresherRecord);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return RefresherRecord;
      }
      v23 = 23;
      goto LABEL_39;
    }
    if ( a3 )
    {
      if ( v29[0] )
      {
        if ( v29[0] != MSHCTX_INPROC )
        {
          *(_QWORD *)v29 = 0;
          RefresherRecord = CRefresherCache::FindRefresherRecord(this, a2, 1, a12, (struct CRefresherRecord **)v29);
          v24 = *(CRefresherRecord **)v29;
          v32 = *(CRefresherRecord **)v29;
          if ( RefresherRecord >= 0 )
          {
            *(_QWORD *)v29 = 0;
            v31 = *(struct _GUID *)((char *)a3 + 24);
            CRefresherRecord::FindProviderRecord(v24, &v31, (struct IWbemHiPerfProvider **)v29);
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
                                  a10,
                                  (struct IWbemHiPerfProvider **)v29,
                                  &v30);
              v25 = *(CRefresherRecord **)v29;
              v18 = v30;
            }
            *(_QWORD *)&v31.Data1 = v25;
            v30 = v18;
            if ( RefresherRecord >= 0 )
              RefresherRecord = (*(__int64 (__fastcall **)(CRefresherRecord *, struct CHiPerfPrvRecord *, _QWORD, struct _IWmiProviderStack *, struct IWbemServices *, struct IWbemObjectAccess *, const unsigned __int16 *, int, struct IWbemContext *, struct CRefreshInfo *))(*(_QWORD *)v24 + 64LL))(
                                  v24,
                                  a3,
                                  *(_QWORD *)v29,
                                  v18,
                                  a6,
                                  a7,
                                  a8,
                                  a9,
                                  a10,
                                  a11);
            if ( v18 )
              (*(void (__fastcall **)(struct _IWmiProviderStack *))(*(_QWORD *)v18 + 16LL))(v18);
            v30 = 0;
            if ( v25 )
              (*(void (__fastcall **)(CRefresherRecord *))(*(_QWORD *)v25 + 16LL))(v25);
            *(_QWORD *)&v31.Data1 = 0;
          }
          if ( v24 )
            (*(void (__fastcall **)(CRefresherRecord *))(*(_QWORD *)v24 + 16LL))(v24);
          v32 = 0;
          if ( RefresherRecord < 0 )
          {
            v27 = GetMemLogObject();
            CMemoryLog::Write(v27, RefresherRecord);
          }
LABEL_17:
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return RefresherRecord;
          }
          v23 = 24;
LABEL_39:
          WPP_SF_d(
            *((_QWORD *)v20 + 2),
            v23,
            WPP_583a410948f0357245c15279aca1a26e_Traceguids,
            (unsigned int)RefresherRecord);
          return RefresherRecord;
        }
        v28 = (const unsigned __int16 *)WString::operator unsigned short const *((char *)a3 + 16);
        result = CRefreshInfo::SetDirect(
                   a11,
                   (const struct _GUID *)((char *)a3 + 40),
                   a5,
                   v28,
                   a7,
                   (CRefresherCache *)((char *)this + 272));
      }
      else
      {
        result = CRefreshInfo::SetClientLoadable(a11, (const struct _GUID *)((char *)a3 + 40), a5, a7);
      }
    }
    else
    {
      result = CRefreshInfo::SetNonHiPerf(a11, a5, a7);
    }
    if ( result < 0 )
      return result;
    goto LABEL_17;
  }
  v21 = GetMemLogObject();
  CMemoryLog::Write(v21, DestinationContext);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_583a410948f0357245c15279aca1a26e_Traceguids,
      (unsigned int)DestinationContext);
  }
  return DestinationContext;
}

```

## disassembly

```asm
0x1800558a4  mov     rax, rsp
0x1800558a7  mov     [rax+10h], rbx
0x1800558ab  mov     [rax+18h], rsi
0x1800558af  mov     [rax+8], rcx
0x1800558b3  push    rbp
0x1800558b4  push    rdi
0x1800558b5  push    r12
0x1800558b7  push    r14
0x1800558b9  push    r15
0x1800558bb  lea     rbp, [rax-2Fh]
0x1800558bf  sub     rsp, 90h
0x1800558c6  mov     r14, r9
0x1800558c9  mov     r15, r8
0x1800558cc  mov     rdi, rdx
0x1800558cf  mov     rsi, rcx
0x1800558d2  mov     [rbp+27h+var_50], 0
0x1800558d9  lea     rcx, [rbp+27h+var_50]; enum tagMSHCTX *
0x1800558dd  call    ?GetDestinationContext@CRefresherCache@@SAJAEAW4tagMSHCTX@@PEAVCRefresherId@@@Z; CRefresherCache::GetDestinationContext(tagMSHCTX &,CRefresherId *)
0x1800558e2  mov     ebx, eax
0x1800558e4  test    eax, eax
0x1800558e6  js      loc_1800559FB
0x1800558ec  mov     r12, [rbp+27h+arg_30]
0x1800558f0  mov     rax, [r12]
0x1800558f4  mov     r8, [rbp+27h+arg_20]
0x1800558f8  mov     rdx, r14
0x1800558fb  mov     rcx, r12
0x1800558fe  mov     rax, [rax+260h]
0x180055905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005590a  mov     r14d, eax
0x18005590d  xor     ebx, ebx
0x18005590f  test    eax, eax
0x180055911  js      loc_180055A4E
0x180055917  test    r15, r15
0x18005591a  jz      loc_1800559E3
0x180055920  mov     eax, [rbp+27h+var_50]
0x180055923  test    eax, eax
0x180055925  jnz     loc_180055A95
0x18005592b  cmp     eax, 3
0x18005592e  jz      loc_180055BC1
0x180055934  mov     r9, r12; struct IWbemObjectAccess *
0x180055937  mov     r8, [rbp+27h+arg_20]; unsigned __int16 *
0x18005593b  lea     rdx, [r15+28h]; struct _GUID *
0x18005593f  mov     rcx, [rbp+27h+arg_50]; this
0x180055946  call    ?SetClientLoadable@CRefreshInfo@@QEAAJAEBU_GUID@@PEBGPEAUIWbemObjectAccess@@@Z; CRefreshInfo::SetClientLoadable(_GUID const &,ushort const *,IWbemObjectAccess *)
0x18005594b  test    eax, eax
0x18005594d  jns     short loc_1800559BE
0x18005594f  lea     r11, [rsp+0B0h+var_20]
0x180055957  mov     rbx, [r11+38h]
0x18005595b  mov     rsi, [r11+40h]
0x18005595f  mov     rsp, r11
0x180055962  pop     r15
0x180055964  pop     r14
0x180055966  pop     r12
0x180055968  pop     rdi
0x180055969  pop     rbp
0x18005596a  retn
0x18005596b  test    rbx, rbx
0x18005596e  jz      short loc_18005597F
0x180055970  mov     rax, [rbx]
0x180055973  mov     rcx, rbx
0x180055976  mov     rax, [rax+10h]
0x18005597a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005597f  xor     ebx, ebx
0x180055981  mov     [rbp+27h+var_48], rbx
0x180055985  test    rdi, rdi
0x180055988  jz      short loc_180055999
0x18005598a  mov     rax, [rdi]
0x18005598d  mov     rcx, rdi
0x180055990  mov     rax, [rax+10h]
0x180055994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055999  mov     qword ptr [rbp+27h+var_40.Data1], rbx
0x18005599d  test    rsi, rsi
0x1800559a0  jz      short loc_1800559B1
0x1800559a2  mov     rax, [rsi]
0x1800559a5  mov     rcx, rsi
0x1800559a8  mov     rax, [rax+10h]
0x1800559ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559b1  mov     [rbp+27h+var_30], rbx
0x1800559b5  test    r14d, r14d
0x1800559b8  js      loc_180055BAA
0x1800559be  lea     rcx, WPP_GLOBAL_Control
0x1800559c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800559cc  cmp     rax, rcx
0x1800559cf  jz      short loc_1800559DB
0x1800559d1  test    byte ptr [rax+1Ch], 1
0x1800559d5  jnz     loc_180055BF8
0x1800559db  mov     eax, r14d
0x1800559de  jmp     loc_18005594F
0x1800559e3  mov     r8, r12; struct IWbemObjectAccess *
0x1800559e6  mov     rdx, [rbp+27h+arg_20]; unsigned __int16 *
0x1800559ea  mov     rcx, [rbp+27h+arg_50]; this
0x1800559f1  call    ?SetNonHiPerf@CRefreshInfo@@QEAAJPEBGPEAUIWbemObjectAccess@@@Z; CRefreshInfo::SetNonHiPerf(ushort const *,IWbemObjectAccess *)
0x1800559f6  jmp     loc_18005594B
0x1800559fb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180055a01  mov     edx, ebx
0x180055a03  mov     rcx, rax
0x180055a06  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180055a0c  lea     rcx, WPP_GLOBAL_Control
0x180055a13  mov     r10, cs:WPP_GLOBAL_Control
0x180055a1a  cmp     r10, rcx
0x180055a1d  jnz     short loc_180055A26
0x180055a1f  mov     eax, ebx
0x180055a21  jmp     loc_18005594F
0x180055a26  test    byte ptr [r10+1Ch], 1
0x180055a2b  jz      short loc_180055A1F
0x180055a2d  cmp     byte ptr [r10+19h], 2
0x180055a32  jb      short loc_180055A1F
0x180055a34  mov     edx, 16h
0x180055a39  mov     r9d, ebx
0x180055a3c  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180055a43  mov     rcx, [r10+10h]
0x180055a47  call    WPP_SF_d
0x180055a4c  jmp     short loc_180055A1F
0x180055a4e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180055a54  mov     edx, r14d
0x180055a57  mov     rcx, rax
0x180055a5a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180055a60  lea     rcx, WPP_GLOBAL_Control
0x180055a67  mov     rax, cs:WPP_GLOBAL_Control
0x180055a6e  cmp     rax, rcx
0x180055a71  jz      loc_1800559DB
0x180055a77  test    byte ptr [rax+1Ch], 1
0x180055a7b  jz      loc_1800559DB
0x180055a81  cmp     byte ptr [rax+19h], 2
0x180055a85  jb      loc_1800559DB
0x180055a8b  mov     edx, 17h
0x180055a90  jmp     loc_180055C07
0x180055a95  cmp     eax, 3
0x180055a98  jz      loc_180055BC1
0x180055a9e  mov     qword ptr [rbp+27h+var_50], rbx
0x180055aa2  lea     rax, [rbp+27h+var_50]
0x180055aa6  mov     [rsp+0B0h+var_90], rax; struct CRefresherRecord **
0x180055aab  mov     r9, [rbp+27h+arg_58]; struct IUnknown *
0x180055ab2  mov     r8d, 1; int
0x180055ab8  mov     rdx, rdi; struct CRefresherId *
0x180055abb  mov     rcx, rsi; this
0x180055abe  call    ?FindRefresherRecord@CRefresherCache@@QEAAJPEAVCRefresherId@@HPEAUIUnknown@@PEAPEAVCRefresherRecord@@@Z; CRefresherCache::FindRefresherRecord(CRefresherId *,int,IUnknown *,CRefresherRecord * *)
0x180055ac3  mov     r14d, eax
0x180055ac6  mov     rsi, qword ptr [rbp+27h+var_50]
0x180055aca  mov     [rbp+27h+var_30], rsi
0x180055ace  test    eax, eax
0x180055ad0  js      loc_18005599D
0x180055ad6  mov     qword ptr [rbp+27h+var_50], rbx
0x180055ada  movups  xmm0, xmmword ptr [r15+18h]
0x180055adf  movdqu  xmmword ptr [rbp+27h+var_40.Data1], xmm0
0x180055ae4  lea     r8, [rbp+27h+var_50]; struct IWbemHiPerfProvider **
0x180055ae8  lea     rdx, [rbp+27h+var_40]; struct _GUID
0x180055aec  mov     rcx, rsi; this
0x180055aef  call    ?FindProviderRecord@CRefresherRecord@@QEAAPEAVCProviderRecord@@U_GUID@@PEAPEAUIWbemHiPerfProvider@@@Z; CRefresherRecord::FindProviderRecord(_GUID,IWbemHiPerfProvider * *)
0x180055af4  mov     [rbp+27h+var_48], rbx
0x180055af8  mov     rdi, qword ptr [rbp+27h+var_50]
0x180055afc  test    rdi, rdi
0x180055aff  jnz     short loc_180055B45
0x180055b01  lea     rcx, [r15+10h]
0x180055b05  call    cs:__imp_??BWString@@QEBAPEBGXZ; WString::operator ushort const *(void)
0x180055b0b  lea     rcx, [rbp+27h+var_48]
0x180055b0f  mov     [rsp+0B0h+var_80], rcx; struct _IWmiProviderStack **
0x180055b14  lea     rcx, [rbp+27h+var_50]
0x180055b18  mov     [rsp+0B0h+var_88], rcx; struct IWbemHiPerfProvider **
0x180055b1d  mov     rcx, [rbp+27h+arg_48]
0x180055b21  mov     [rsp+0B0h+var_90], rcx; struct IWbemContext *
0x180055b26  mov     r9, [rbp+27h+arg_28]; struct IWbemServices *
0x180055b2a  mov     r8, [rbp+27h+arg_20]; unsigned __int16 *
0x180055b2e  mov     rdx, rax; unsigned __int16 *
0x180055b31  mov     rcx, [rbp+27h+arg_0]; this
0x180055b35  call    ?LoadProviderInner@CRefresherCache@@QEAAJPEBG0PEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemHiPerfProvider@@PEAPEAU_IWmiProviderStack@@@Z; CRefresherCache::LoadProviderInner(ushort const *,ushort const *,IWbemServices *,IWbemContext *,IWbemHiPerfProvider * *,_IWmiProviderStack * *)
0x180055b3a  mov     r14d, eax
0x180055b3d  mov     rdi, qword ptr [rbp+27h+var_50]
0x180055b41  mov     rbx, [rbp+27h+var_48]
0x180055b45  mov     qword ptr [rbp+27h+var_40.Data1], rdi
0x180055b49  mov     [rbp+27h+var_48], rbx
0x180055b4d  test    r14d, r14d
0x180055b50  js      loc_18005596B
0x180055b56  mov     rax, [rsi]
0x180055b59  mov     rcx, [rbp+27h+arg_50]
0x180055b60  mov     [rsp+0B0h+var_68], rcx
0x180055b65  mov     rcx, [rbp+27h+arg_48]
0x180055b69  mov     [rsp+0B0h+var_70], rcx
0x180055b6e  mov     ecx, [rbp+27h+arg_40]
0x180055b71  mov     dword ptr [rsp+0B0h+var_78], ecx
0x180055b75  mov     rcx, [rbp+27h+arg_38]
0x180055b79  mov     [rsp+0B0h+var_80], rcx
0x180055b7e  mov     [rsp+0B0h+var_88], r12
0x180055b83  mov     rcx, [rbp+27h+arg_28]
0x180055b87  mov     [rsp+0B0h+var_90], rcx
0x180055b8c  mov     r9, rbx
0x180055b8f  mov     r8, qword ptr [rbp+27h+var_50]
0x180055b93  mov     rdx, r15
0x180055b96  mov     rcx, rsi
0x180055b99  mov     rax, [rax+40h]
0x180055b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ba2  mov     r14d, eax
0x180055ba5  jmp     loc_18005596B
0x180055baa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180055bb0  mov     edx, r14d
0x180055bb3  mov     rcx, rax
0x180055bb6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180055bbc  jmp     loc_1800559BE
0x180055bc1  lea     rcx, [r15+10h]
0x180055bc5  call    cs:__imp_??BWString@@QEBAPEBGXZ; WString::operator ushort const *(void)
0x180055bcb  lea     rcx, [rsi+110h]
0x180055bd2  mov     [rsp+0B0h+var_88], rcx; struct _IWbemRefresherMgr *
0x180055bd7  mov     [rsp+0B0h+var_90], r12; struct IWbemObjectAccess *
0x180055bdc  mov     r9, rax; unsigned __int16 *
0x180055bdf  mov     r8, [rbp+27h+arg_20]; unsigned __int16 *
0x180055be3  lea     rdx, [r15+28h]; struct _GUID *
0x180055be7  mov     rcx, [rbp+27h+arg_50]; this
0x180055bee  call    ?SetDirect@CRefreshInfo@@QEAAJAEBU_GUID@@PEBG1PEAUIWbemObjectAccess@@PEAU_IWbemRefresherMgr@@@Z; CRefreshInfo::SetDirect(_GUID const &,ushort const *,ushort const *,IWbemObjectAccess *,_IWbemRefresherMgr *)
0x180055bf3  jmp     loc_18005594B
0x180055bf8  cmp     byte ptr [rax+19h], 2
0x180055bfc  jb      loc_1800559DB
0x180055c02  mov     edx, 18h
0x180055c07  mov     r9d, r14d
0x180055c0a  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180055c11  mov     rcx, [rax+10h]
0x180055c15  call    WPP_SF_d
0x180055c1a  jmp     loc_1800559DB
```
