# XpsObjectModelState::InsertPartIntoLut(wchar_t const *,IUnknown *)

- ea: `0x140038508`
- end: `0x1400386f5`
- name: `?InsertPartIntoLut@XpsObjectModelState@@QEAAPEAUIUnknown@@PEB_WPEAU2@@Z`
- size: `493`
- prototype: `struct IUnknown *__fastcall(XpsObjectModelState *__hidden this, const wchar_t *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14003e5b0`
- `0x14003e950`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000f9d8`
- `0x14000fa68`
- `0x140010148`
- `0x1400172e8`
- `0x14001c7f4`
- `0x140025478`
- `0x140027b1c`
- `0x140027ea4`
- `0x140027f20`
- `0x140029c10`
- `0x140038508`
- `0x140038a74`
- `0x1400411d8`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x1400520ec`
- `0x140055c44`
- `0x140055f54`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14003869d`
- `KERNEL32!LeaveCriticalSection` at `0x14003869d`

## string_xrefs

- `0x1400385d1`: `Uri %ws is not in LUT. Cannot add it because pPart is NULL`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct IUnknown *__fastcall XpsObjectModelState::InsertPartIntoLut(
        XpsObjectModelState *this,
        const wchar_t *a2,
        struct IUnknown *a3)
{
  LPVOID *v6; // rax
  int v7; // r8d
  char *v8; // rbx
  const struct SplException::TSystemException *v9; // r8
  const struct _GUID *v10; // r9
  win_dox::OpcPartUri *v11; // rax
  __int64 v13; // rbx
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v16; // [rsp+28h] [rbp-D8h]
  HINSTANCE v17; // [rsp+30h] [rbp-D0h]
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[24]; // [rsp+58h] [rbp-A8h] BYREF
  char *v22; // [rsp+70h] [rbp-90h]
  _BYTE v23[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v24[160]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+140h] [rbp+40h] BYREF

  v19 = 0;
  v6 = win_musl::CreateComObject<IOpcFactory>(&ppv);
  win_dox::OpcFactory::OpcFactory((__int64)&v20, v6);
  win_dox::OpcUriFactory::CreatePartUri(&v20, (__int64)v21, (__int64)a2);
  v22 = (char *)this + 24;
  NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::find(
    (char *)this + 80,
    &ppv,
    v21);
  v8 = (char *)ppv;
  if ( ppv == *((LPVOID *)this + 10) )
  {
    if ( !a3 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v24, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v24,
        0x80004005,
        v9,
        v10,
        v15,
        v16,
        v17);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v24,
        "Uri %ws is not in LUT. Cannot add it because pPart is NULL",
        a2);
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v24);
      throw (SplException::THResultException *)pExceptionObject;
    }
    ppv = a3;
    PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)a3);
    v11 = PartMapItem::PartMapItem((win_dox::OpcPartUri *)v23, (const struct win_dox::OpcPartUri *)v21, (__int64 *)&ppv);
    PartMapInsert((char *)this + 80, v11);
    std::pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>::~pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>((win_dox::OpcPartUri *)v23);
    PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(&v19, a3);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, v7, (_DWORD)a2, (char)this);
    }
    PrnExcept::TRefSmartPtr<IUnknown>::operator=(&v19, v8 + 80);
  }
  if ( (*((_DWORD *)this + 17))-- == 1 )
    *((_DWORD *)this + 16) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v13 = v19;
  v19 = 0;
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v21);
  win_dox::Uri::~Uri((win_dox::Uri *)&v20);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v19);
  return (struct IUnknown *)v13;
}

```

## disassembly

```asm
0x140038508  push    rbp
0x14003850a  push    rbx
0x14003850b  push    rsi
0x14003850c  push    rdi
0x14003850d  push    r12
0x14003850f  push    r14
0x140038511  push    r15
0x140038513  lea     rbp, [rsp-0F0h]
0x14003851b  sub     rsp, 1F0h
0x140038522  mov     rax, cs:__security_cookie
0x140038529  xor     rax, rsp
0x14003852c  mov     [rbp+120h+var_40], rax
0x140038533  mov     rsi, r8
0x140038536  mov     r14, rdx
0x140038539  mov     r15, rcx
0x14003853c  mov     [rsp+220h+var_1D8], 0
0x140038545  lea     rcx, [rsp+220h+ppv]; ppv
0x14003854a  call    ??$CreateComObject@UIOpcFactory@@@win_musl@@YA?AV?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBU_GUID@@K@Z; win_musl::CreateComObject<IOpcFactory>(_GUID const &,ulong)
0x14003854f  mov     rdx, rax
0x140038552  lea     rcx, [rsp+220h+var_1D0]
0x140038557  call    ??$?0V?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@OpcFactory@win_dox@@QEAA@V?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcFactory::OpcFactory(win_scope::scope<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>)
0x14003855c  nop
0x14003855d  mov     r8, r14
0x140038560  lea     rdx, [rsp+220h+var_1C8]
0x140038565  lea     rcx, [rsp+220h+var_1D0]
0x14003856a  call    ?CreatePartUri@OpcUriFactory@win_dox@@QEBA?AVOpcPartUri@2@PEB_W@Z; win_dox::OpcUriFactory::CreatePartUri(wchar_t const *)
0x14003856f  nop
0x140038570  lea     rdi, [r15+18h]
0x140038574  mov     [rsp+220h+var_1B0], rdi
0x140038579  mov     rcx, rdi; this
0x14003857c  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140038581  nop
0x140038582  lea     r12, [r15+50h]
0x140038586  lea     r8, [rsp+220h+var_1C8]
0x14003858b  lea     rdx, [rsp+220h+ppv]
0x140038590  mov     rcx, r12
0x140038593  call    ?find@?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VOpcPartUri@win_dox@@@std@@@std@@@2@AEBVOpcPartUri@win_dox@@@Z; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::find(win_dox::OpcPartUri const &)
0x140038598  mov     rbx, [rsp+220h+ppv]
0x14003859d  cmp     rbx, [r12]
0x1400385a1  jnz     loc_140038646
0x1400385a7  test    rsi, rsi
0x1400385aa  jnz     short loc_1400385FF
0x1400385ac  xor     r8d, r8d; unsigned int
0x1400385af  lea     rdx, asc_1400696D8; "-"
0x1400385b6  lea     rcx, [rbp+120h+var_180]; this
0x1400385ba  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400385bf  nop
0x1400385c0  mov     edx, 80004005h; unsigned int
0x1400385c5  lea     rcx, [rbp+120h+var_180]; this
0x1400385c9  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400385ce  mov     r8, r14
0x1400385d1  lea     rdx, aUriWsIsNotInLu; "Uri %ws is not in LUT. Cannot add it be"...
0x1400385d8  lea     rcx, [rbp+120h+var_180]; this
0x1400385dc  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400385e1  lea     rdx, [rbp+120h+var_180]; struct SplException::THResultException *
0x1400385e5  lea     rcx, [rbp+120h+pExceptionObject]; this
0x1400385e9  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400385ee  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400385f5  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x1400385f9  call    _CxxThrowException_0
0x1400385ff  mov     [rsp+220h+ppv], rsi
0x140038604  mov     rcx, rsi
0x140038607  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14003860c  lea     r8, [rsp+220h+ppv]
0x140038611  lea     rdx, [rsp+220h+var_1C8]
0x140038616  lea     rcx, [rsp+220h+var_1A8]
0x14003861b  call    ??0PartMapItem@@QEAA@AEBVOpcPartUri@win_dox@@V?$TRefSmartPtr@UIUnknown@@@PrnExcept@@@Z; PartMapItem::PartMapItem(win_dox::OpcPartUri const &,PrnExcept::TRefSmartPtr<IUnknown>)
0x140038620  nop
0x140038621  mov     rdx, rax
0x140038624  mov     rcx, r12
0x140038627  call    ?PartMapInsert@@YA_NPEAV?$map@VOpcPartUri@win_dox@@UPartMapItem@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@UPartMapItem@@@std@@@5@@std@@AEAUPartMapItem@@@Z; PartMapInsert(std::map<win_dox::OpcPartUri,PartMapItem> *,PartMapItem &)
0x14003862c  nop
0x14003862d  lea     rcx, [rsp+220h+var_1A8]; this
0x140038632  call    ??1?$pair@$$CBVOpcPartUri@win_dox@@V?$TRefSmartPtr@UIStream@@@PrnExcept@@@std@@QEAA@XZ; std::pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>::~pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>(void)
0x140038637  mov     rdx, rsi
0x14003863a  lea     rcx, [rsp+220h+var_1D8]
0x14003863f  call    ??4?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@QEAAAEAV01@PEAUIShutdownComponent@@@Z; PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(IShutdownComponent *)
0x140038644  jmp     short loc_14003868A
0x140038646  lea     rax, WPP_GLOBAL_Control
0x14003864d  mov     rcx, cs:WPP_GLOBAL_Control
0x140038654  cmp     rcx, rax
0x140038657  jz      short loc_14003867B
0x140038659  test    byte ptr [rcx+1Ch], 10h
0x14003865d  jz      short loc_14003867B
0x14003865f  cmp     byte ptr [rcx+19h], 4
0x140038663  jb      short loc_14003867B
0x140038665  mov     edx, 0AEh
0x14003866a  mov     [rsp+220h+var_200], r15
0x14003866f  mov     r9, r14
0x140038672  mov     rcx, [rcx+10h]
0x140038676  call    WPP_SF_Sq
0x14003867b  lea     rdx, [rbx+50h]
0x14003867f  lea     rcx, [rsp+220h+var_1D8]
0x140038684  call    ??4?$TRefSmartPtr@UIUnknown@@@PrnExcept@@QEAAAEAV01@AEBV01@@Z; PrnExcept::TRefSmartPtr<IUnknown>::operator=(PrnExcept::TRefSmartPtr<IUnknown> const &)
0x140038689  nop
0x14003868a  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x14003868e  mov     eax, [rdi+2Ch]
0x140038691  jnz     short loc_14003869A
0x140038693  mov     dword ptr [rdi+28h], 0
0x14003869a  mov     rcx, rdi; lpCriticalSection
0x14003869d  call    cs:__imp_LeaveCriticalSection
0x1400386a3  mov     rbx, [rsp+220h+var_1D8]
0x1400386a8  mov     [rsp+220h+var_1D8], 0
0x1400386b1  lea     rcx, [rsp+220h+var_1C8]; this
0x1400386b6  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x1400386bb  nop
0x1400386bc  lea     rcx, [rsp+220h+var_1D0]; this
0x1400386c1  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x1400386c6  nop
0x1400386c7  lea     rcx, [rsp+220h+var_1D8]
0x1400386cc  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400386d1  mov     rax, rbx
0x1400386d4  mov     rcx, [rbp+120h+var_40]
0x1400386db  xor     rcx, rsp; StackCookie
0x1400386de  call    __security_check_cookie
0x1400386e3  add     rsp, 1F0h
0x1400386ea  pop     r15
0x1400386ec  pop     r14
0x1400386ee  pop     r12
0x1400386f0  pop     rdi
0x1400386f1  pop     rsi
0x1400386f2  pop     rbx
0x1400386f3  pop     rbp
0x1400386f4  retn
```
