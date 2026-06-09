# CRefresherCache::GetProviderInfo(IWbemServices *,ushort const *,_GUID &,_GUID &)

- ea: `0x1800555d0`
- end: `0x18005589b`
- name: `?GetProviderInfo@CRefresherCache@@QEAAJPEAUIWbemServices@@PEBGAEAU_GUID@@2@Z`
- size: `715`
- prototype: `int(CRefresherCache *__hidden this, struct IWbemServices *, const unsigned __int16 *, struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180055210`

## callees

- `0x180037120`
- `0x1800555d0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800556ea`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180055745`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800556ea`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180055745`
- `wbemcomn!GetMemLogObject` at `0x1800557f1`
- `wbemcomn!GetMemLogObject` at `0x18005585e`
- `wbemcomn!GetMemLogObject` at `0x1800557f1`
- `wbemcomn!GetMemLogObject` at `0x18005585e`
- `wbemcomn!??YWString@@QEAAAEAV0@PEBG@Z` at `0x180055611`
- `wbemcomn!??YWString@@QEAAAEAV0@PEBG@Z` at `0x180055626`
- `wbemcomn!??YWString@@QEAAAEAV0@PEBG@Z` at `0x180055611`
- `wbemcomn!??YWString@@QEAAAEAV0@PEBG@Z` at `0x180055626`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x1800555ff`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x1800555ff`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800556de`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180055734`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800556de`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180055734`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800556aa`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x1800556aa`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180055634`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180055634`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055801`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055869`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055801`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180055869`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180055756`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180055756`
- `wbemcomn!?Empty@CVar@@QEAAXXZ` at `0x1800556ff`
- `wbemcomn!?Empty@CVar@@QEAAXXZ` at `0x1800556ff`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18005578c`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180055822`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18005578c`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x180055822`
- `OLEAUT32!__imp_SysAllocString` at `0x18005563d`
- `OLEAUT32!__imp_SysAllocString` at `0x18005563d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005577d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005577d`

## string_xrefs

- `0x18005570d`: `ClientLoadableCLSID`
- `0x1800556b9`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CRefresherCache::GetProviderInfo(
        CRefresherCache *this,
        struct IWbemServices *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4,
        struct _GUID *pclsid)
{
  const OLECHAR *v8; // rax
  BSTR v9; // rax
  OLECHAR *v10; // r14
  HRESULT v11; // ebx
  __int64 v12; // rdi
  __int64 v13; // rsi
  const OLECHAR *LPWSTR; // rax
  const OLECHAR *v15; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v19; // [rsp+48h] [rbp-50h] BYREF
  __int64 v20; // [rsp+50h] [rbp-48h]
  BSTR v21; // [rsp+58h] [rbp-40h]
  _BYTE v22[32]; // [rsp+60h] [rbp-38h] BYREF
  CRefresherCache *v23; // [rsp+A0h] [rbp+8h] BYREF

  v23 = this;
  WString::WString((WString *)&v23, L"__Win32Provider.Name=\"");
  WString::operator+=(&v23, a3);
  WString::operator+=(&v23, L"\"");
  v8 = (const OLECHAR *)WString::operator unsigned short *(&v23);
  v9 = SysAllocString(v8);
  v10 = v9;
  if ( v9 )
  {
    v21 = v9;
    v19 = 0;
    v11 = ((__int64 (__fastcall *)(struct IWbemServices *, BSTR, _QWORD, _QWORD, __int64 *, _QWORD))a2->lpVtbl->GetObjectA)(
            a2,
            v9,
            0,
            0,
            &v19,
            0);
    v12 = v19;
    v20 = v19;
    if ( v11 >= 0 )
    {
      v13 = v19;
      CVar::CVar((CVar *)v22);
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _BYTE *))(*(_QWORD *)v13 + 776LL))(v13, L"CLSID", v22);
      if ( v11 >= 0 )
      {
        LPWSTR = CVar::GetLPWSTR((CVar *)v22);
        v11 = CLSIDFromString(LPWSTR, a4);
        if ( v11 >= 0 )
        {
          CVar::Empty((CVar *)v22);
          if ( (*(int (__fastcall **)(__int64, const wchar_t *, _BYTE *))(*(_QWORD *)v13 + 776LL))(
                 v13,
                 L"ClientLoadableCLSID",
                 v22) < 0 )
          {
            *pclsid = GUID_NULL;
            v11 = 0;
          }
          else
          {
            v15 = CVar::GetLPWSTR((CVar *)v22);
            v11 = CLSIDFromString(v15, pclsid);
          }
        }
      }
      CVar::~CVar((CVar *)v22);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v20 = 0;
    SysFreeString(v10);
    WString::~WString((WString *)&v23);
    if ( v11 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v11);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_583a410948f0357245c15279aca1a26e_Traceguids,
        (unsigned int)v11);
    }
    return (unsigned int)v11;
  }
  else
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_583a410948f0357245c15279aca1a26e_Traceguids, 2147749894LL);
    }
    WString::~WString((WString *)&v23);
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x1800555d0  mov     rax, rsp
0x1800555d3  mov     [rax+10h], rbx
0x1800555d7  mov     [rax+18h], rsi
0x1800555db  mov     [rax+8], rcx
0x1800555df  push    rdi
0x1800555e0  push    r14
0x1800555e2  push    r15
0x1800555e4  sub     rsp, 80h
0x1800555eb  mov     r15, r9
0x1800555ee  mov     rdi, r8
0x1800555f1  mov     rbx, rdx
0x1800555f4  lea     rdx, aWin32providerN; "__Win32Provider.Name=\""
0x1800555fb  lea     rcx, [rax+8]
0x1800555ff  call    cs:__imp_??0WString@@QEAA@PEBG@Z; WString::WString(ushort const *)
0x180055605  nop
0x180055606  mov     rdx, rdi
0x180055609  lea     rcx, [rsp+98h+arg_0]
0x180055611  call    cs:__imp_??YWString@@QEAAAEAV0@PEBG@Z; WString::operator+=(ushort const *)
0x180055617  lea     rdx, asc_1800A7298; "\""
0x18005561e  lea     rcx, [rsp+98h+arg_0]
0x180055626  call    cs:__imp_??YWString@@QEAAAEAV0@PEBG@Z; WString::operator+=(ushort const *)
0x18005562c  lea     rcx, [rsp+98h+arg_0]
0x180055634  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18005563a  mov     rcx, rax; psz
0x18005563d  call    cs:__imp_SysAllocString
0x180055643  mov     r14, rax
0x180055646  test    rax, rax
0x180055649  jz      loc_1800557F1
0x18005564f  mov     [rsp+98h+var_40], rax
0x180055654  mov     [rsp+98h+var_50], 0
0x18005565d  mov     rax, [rbx]
0x180055660  mov     [rsp+98h+var_70], 0
0x180055669  lea     rcx, [rsp+98h+var_50]
0x18005566e  mov     [rsp+98h+var_78], rcx
0x180055673  xor     r9d, r9d
0x180055676  xor     r8d, r8d
0x180055679  mov     rdx, r14
0x18005567c  mov     rcx, rbx
0x18005567f  mov     rax, [rax+30h]
0x180055683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055688  mov     ebx, eax
0x18005568a  mov     [rsp+98h+var_58], eax
0x18005568e  mov     rdi, [rsp+98h+var_50]
0x180055693  mov     [rsp+98h+var_48], rdi
0x180055698  test    eax, eax
0x18005569a  js      loc_18005575D
0x1800556a0  mov     rsi, [rsp+98h+var_50]
0x1800556a5  lea     rcx, [rsp+98h+var_38]
0x1800556aa  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800556b0  nop
0x1800556b1  mov     rax, [rsi]
0x1800556b4  lea     r8, [rsp+98h+var_38]
0x1800556b9  lea     rdx, aClsid; "CLSID"
0x1800556c0  mov     rcx, rsi
0x1800556c3  mov     rax, [rax+308h]
0x1800556ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556cf  mov     ebx, eax
0x1800556d1  mov     [rsp+98h+var_58], eax
0x1800556d5  test    eax, eax
0x1800556d7  js      short loc_180055751
0x1800556d9  lea     rcx, [rsp+98h+var_38]
0x1800556de  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x1800556e4  mov     rcx, rax; lpsz
0x1800556e7  mov     rdx, r15; pclsid
0x1800556ea  call    cs:__imp_CLSIDFromString
0x1800556f0  mov     ebx, eax
0x1800556f2  mov     [rsp+98h+var_58], eax
0x1800556f6  test    eax, eax
0x1800556f8  js      short loc_180055751
0x1800556fa  lea     rcx, [rsp+98h+var_38]
0x1800556ff  call    cs:__imp_?Empty@CVar@@QEAAXXZ; CVar::Empty(void)
0x180055705  mov     rax, [rsi]
0x180055708  lea     r8, [rsp+98h+var_38]
0x18005570d  lea     rdx, aClientloadable; "ClientLoadableCLSID"
0x180055714  mov     rcx, rsi
0x180055717  mov     rax, [rax+308h]
0x18005571e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055723  mov     [rsp+98h+var_58], eax
0x180055727  test    eax, eax
0x180055729  js      loc_1800557D3
0x18005572f  lea     rcx, [rsp+98h+var_38]
0x180055734  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x18005573a  mov     rcx, rax; lpsz
0x18005573d  mov     rdx, [rsp+98h+pclsid]; pclsid
0x180055745  call    cs:__imp_CLSIDFromString
0x18005574b  mov     ebx, eax
0x18005574d  mov     [rsp+98h+var_58], eax
0x180055751  lea     rcx, [rsp+98h+var_38]
0x180055756  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18005575c  nop
0x18005575d  test    rdi, rdi
0x180055760  jz      short loc_180055771
0x180055762  mov     rax, [rdi]
0x180055765  mov     rcx, rdi
0x180055768  mov     rax, [rax+10h]
0x18005576c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055771  mov     [rsp+98h+var_48], 0
0x18005577a  mov     rcx, r14; bstrString
0x18005577d  call    cs:__imp_SysFreeString
0x180055783  nop
0x180055784  lea     rcx, [rsp+98h+arg_0]
0x18005578c  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x180055792  nop
0x180055793  test    ebx, ebx
0x180055795  js      loc_18005585E
0x18005579b  lea     rax, WPP_GLOBAL_Control
0x1800557a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800557a9  cmp     rcx, rax
0x1800557ac  jz      short loc_1800557B8
0x1800557ae  test    byte ptr [rcx+1Ch], 1
0x1800557b2  jnz     loc_180055874
0x1800557b8  mov     eax, ebx
0x1800557ba  lea     r11, [rsp+98h+var_18]
0x1800557c2  mov     rbx, [r11+28h]
0x1800557c6  mov     rsi, [r11+30h]
0x1800557ca  mov     rsp, r11
0x1800557cd  pop     r15
0x1800557cf  pop     r14
0x1800557d1  pop     rdi
0x1800557d2  retn
0x1800557d3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800557da  mov     rax, [rsp+98h+pclsid]
0x1800557e2  movdqu  xmmword ptr [rax], xmm0
0x1800557e6  xor     ebx, ebx
0x1800557e8  mov     [rsp+98h+var_58], ebx
0x1800557ec  jmp     loc_180055751
0x1800557f1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800557f7  mov     ebx, 80041006h
0x1800557fc  mov     edx, ebx
0x1800557fe  mov     rcx, rax
0x180055801  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180055807  lea     rax, WPP_GLOBAL_Control
0x18005580e  mov     rcx, cs:WPP_GLOBAL_Control
0x180055815  cmp     rcx, rax
0x180055818  jnz     short loc_18005582C
0x18005581a  lea     rcx, [rsp+98h+arg_0]
0x180055822  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x180055828  mov     eax, ebx
0x18005582a  jmp     short loc_1800557BA
0x18005582c  test    byte ptr [rcx+1Ch], 1
0x180055830  jz      short loc_18005581A
0x180055832  cmp     byte ptr [rcx+19h], 2
0x180055836  jb      short loc_18005581A
0x180055838  mov     edx, 21h ; '!'
0x18005583d  mov     r9d, 80041006h
0x180055843  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x18005584a  mov     rcx, [rcx+10h]
0x18005584e  call    WPP_SF_d
0x180055853  jmp     short loc_18005581A
0x180055855  mov     ebx, [rsp+98h+var_58]
0x180055859  jmp     loc_180055793
0x18005585e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180055864  mov     edx, ebx
0x180055866  mov     rcx, rax
0x180055869  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005586f  jmp     loc_18005579B
0x180055874  cmp     byte ptr [rcx+19h], 2
0x180055878  jb      loc_1800557B8
0x18005587e  mov     edx, 22h ; '"'
0x180055883  mov     r9d, ebx
0x180055886  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x18005588d  mov     rcx, [rcx+10h]
0x180055891  call    WPP_SF_d
0x180055896  jmp     loc_1800557B8
```
