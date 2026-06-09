# CPDFComponent::LoadFromPDF(CString &,ulong,CList<CPDFRole *,CPDFRole * &> &,CList<CString,CString &> &,float)

- ea: `0x180047788`
- end: `0x180047dba`
- name: `?LoadFromPDF@CPDFComponent@@QEAAJAEAVCString@@KAEAV?$CList@PEAVCPDFRole@@AEAPEAV1@@@AEAV?$CList@VCString@@AEAV1@@@M@Z`
- size: `1586`
- prototype: `__int64 __usercall@<rax>(struct CString *@<rcx>, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180048b4c`

## callees

- `0x180009ee0`
- `0x1800447bc`
- `0x180044bc8`
- `0x18004522c`
- `0x18004744c`
- `0x180047788`
- `0x180047dc0`
- `0x18004895c`
- `0x1800489dc`
- `0x180048e10`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180047c3f`
- `msvcrt!_wcsicmp` at `0x180047c3f`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047827`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047865`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800478a3`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800478e1`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18004791f`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18004795d`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18004799b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800479d9`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047a17`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047a55`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047a93`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047ad1`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047b12`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047b53`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047ba9`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047bf6`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047c0a`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047827`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047865`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800478a3`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800478e1`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18004791f`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18004795d`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18004799b`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x1800479d9`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047a17`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047a55`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047a93`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047ad1`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047b12`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047b53`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047ba9`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047bf6`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x180047c0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047cff`

## string_xrefs

- `0x180047bef`: `Install`
- `0x180047aea`: `CompDLL`
- `0x1800479f2`: `Security`
- `0x180047802`: `Clsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPDFComponent::LoadFromPDF(
        const struct _GUID *a1,
        const unsigned __int16 **a2,
        int a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  __int64 result; // rax
  const wchar_t **Data4; // rsi
  const wchar_t **v11; // r14
  unsigned __int16 *v12; // rdx
  unsigned int v13; // r14d
  unsigned int i; // r15d
  CPDFInterface *v15; // rax
  CPDFInterface *v16; // rsi
  unsigned int v17; // [rsp+30h] [rbp-8E8h] BYREF
  CPDFInterface *v18; // [rsp+38h] [rbp-8E0h]
  __int64 v19; // [rsp+40h] [rbp-8D8h]
  _QWORD v20[3]; // [rsp+48h] [rbp-8D0h] BYREF
  unsigned __int16 v21[56]; // [rsp+60h] [rbp-8B8h] BYREF
  unsigned __int16 v22[1024]; // [rsp+D0h] [rbp-848h] BYREF

  v19 = a4;
  result = StringCchPrintfW(v21, 0x32u, L"%s - C%lu", *(_QWORD *)&a1->Data1, a3);
  if ( (int)result < 0 )
    return result;
  if ( ReadStringFromPDF(v21, L"Clsid", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(a1->Data4, v22);
  if ( ReadStringFromPDF(v21, L"Description", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(a1[1].Data4, v22);
  if ( ReadStringFromPDF(v21, L"Transaction", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(&a1[2], v22);
  if ( ReadStringFromPDF(v21, L"RunInASP", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(a1[3].Data4, v22);
  if ( ReadStringFromPDF(v21, L"InProc", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(a1[4].Data4, v22);
  if ( ReadStringFromPDF(v21, L"Local", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(&a1[5], v22);
  if ( ReadStringFromPDF(v21, L"Remote", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(a1[5].Data4, v22);
  if ( ReadStringFromPDF(v21, L"Internet", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(&a1[6], v22);
  if ( ReadStringFromPDF(v21, L"Security", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(a1[6].Data4, v22);
  if ( ReadStringFromPDF(v21, L"AuthLevel", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(&a1[7], v22);
  if ( ReadStringFromPDF(v21, L"System", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(a1[7].Data4, v22);
  if ( ReadStringFromPDF(v21, L"ProgID", v22, 0x400u, *a2) )
    return 2148598792LL;
  CString::operator=(&a1[1], v22);
  if ( ReadStringFromPDF(v21, L"CompDLL", v22, 0x400u, *a2) )
    return 2148598792LL;
  Data4 = (const wchar_t **)a1[2].Data4;
  CString::operator=(a1[2].Data4, v22);
  if ( ReadStringFromPDF(v21, L"TypeLib", v22, 0x400u, *a2) )
    return 2148598792LL;
  v11 = (const wchar_t **)&a1[3];
  CString::operator=(&a1[3], v22);
  if ( *(float *)&a6 < 2.01 )
  {
    CString::operator=(&a1[8], L"Install");
    v12 = L"Y";
  }
  else
  {
    if ( ReadStringFromPDF(v21, L"Origin", v22, 0x400u, *a2) )
      return 2148598792LL;
    CString::operator=(&a1[8], v22);
    if ( ReadStringFromPDF(v21, L"Wrapped", v22, 0x400u, *a2) )
      return 2148598792LL;
    v12 = v22;
  }
  CString::operator=(a1[8].Data4, v12);
  if ( **Data4 )
  {
    result = InsertUniqueNameInList(a1[2].Data4, a5);
    if ( (int)result < 0 )
      return result;
  }
  if ( **v11 )
  {
    if ( _wcsicmp(*Data4, *v11) )
    {
      result = InsertUniqueNameInList(&a1[3], a5);
      if ( (int)result < 0 )
        return result;
    }
  }
  v17 = 0;
  if ( ReadIntFromPDF(v21, L"Roles", &v17, *a2) )
    return 2148598792LL;
  v13 = 0;
  if ( v17 )
  {
    result = ReadListFromPDF((unsigned __int16 *)*a2, a4, (__int64)&a1[9]);
    v13 = result;
    if ( (_DWORD)result )
      return result;
  }
  v17 = 0;
  if ( ReadIntFromPDF(v21, L"Interfaces", &v17, *a2) )
    return 2148598792LL;
  for ( i = 1; i <= v17; ++i )
  {
    v15 = (CPDFInterface *)CoTaskMemAlloc(0x70u);
    v20[1] = v15;
    if ( v15 )
      v16 = CPDFInterface::CPDFInterface(v15, (const struct CString *)a1, (const struct CString *)a1->Data4, a1 + 16);
    else
      v16 = 0;
    v18 = v16;
    v20[0] = v16;
    if ( !v16 )
      return 2147942414LL;
    v13 = CPDFInterface::LoadFromPDF(v16, a2, i, v19, a5);
    if ( v13 )
    {
LABEL_40:
      CPDFInterface::`scalar deleting destructor'(v16);
      return v13;
    }
    try
    {
      CList<CPDFComponent *,CPDFComponent * &>::AddTail((__int64)a1[12].Data4, v20);
    }
    catch ( ... )
    {
      v17 = -2147024882;
      v13 = -2147024882;
      v16 = v18;
      goto LABEL_40;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180047788  push    rbx
0x18004778a  push    rsi
0x18004778b  push    rdi
0x18004778c  push    r12
0x18004778e  push    r13
0x180047790  push    r14
0x180047792  push    r15
0x180047794  sub     rsp, 8E0h
0x18004779b  mov     rax, cs:__security_cookie
0x1800477a2  xor     rax, rsp
0x1800477a5  mov     [rsp+918h+var_48], rax
0x1800477ad  mov     r15, r9
0x1800477b0  mov     [rsp+918h+var_8D8], r9
0x1800477b5  mov     rdi, rdx
0x1800477b8  mov     rbx, rcx
0x1800477bb  mov     r12, [rsp+918h+arg_20]
0x1800477c3  mov     dword ptr [rsp+918h+var_8F8], r8d
0x1800477c8  mov     r9, [rcx]
0x1800477cb  lea     r8, aSCLu; "%s - C%lu"
0x1800477d2  mov     edx, 32h ; '2'; unsigned __int64
0x1800477d7  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x1800477dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800477e1  test    eax, eax
0x1800477e3  js      loc_180047D97
0x1800477e9  mov     rax, [rdi]
0x1800477ec  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x1800477f1  mov     r14d, 400h
0x1800477f7  mov     r9d, r14d; unsigned int
0x1800477fa  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047802  lea     rdx, aClsid_0; "Clsid"
0x180047809  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x18004780e  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047813  test    eax, eax
0x180047815  jnz     loc_180047D92
0x18004781b  lea     rdx, [rsp+918h+var_848]
0x180047823  lea     rcx, [rbx+8]
0x180047827  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18004782d  mov     rax, [rdi]
0x180047830  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047835  mov     r9d, r14d; unsigned int
0x180047838  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047840  lea     rdx, aDescription; "Description"
0x180047847  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x18004784c  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047851  test    eax, eax
0x180047853  jnz     loc_180047D92
0x180047859  lea     rcx, [rbx+18h]
0x18004785d  lea     rdx, [rsp+918h+var_848]
0x180047865  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18004786b  mov     rax, [rdi]
0x18004786e  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047873  mov     r9d, r14d; unsigned int
0x180047876  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x18004787e  lea     rdx, aTransaction; "Transaction"
0x180047885  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x18004788a  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x18004788f  test    eax, eax
0x180047891  jnz     loc_180047D92
0x180047897  lea     rcx, [rbx+20h]
0x18004789b  lea     rdx, [rsp+918h+var_848]
0x1800478a3  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800478a9  mov     rax, [rdi]
0x1800478ac  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x1800478b1  mov     r9d, r14d; unsigned int
0x1800478b4  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x1800478bc  lea     rdx, aRuninasp; "RunInASP"
0x1800478c3  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x1800478c8  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x1800478cd  test    eax, eax
0x1800478cf  jnz     loc_180047D92
0x1800478d5  lea     rcx, [rbx+38h]
0x1800478d9  lea     rdx, [rsp+918h+var_848]
0x1800478e1  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800478e7  mov     rax, [rdi]
0x1800478ea  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x1800478ef  mov     r9d, r14d; unsigned int
0x1800478f2  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x1800478fa  lea     rdx, aInproc_0; "InProc"
0x180047901  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047906  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x18004790b  test    eax, eax
0x18004790d  jnz     loc_180047D92
0x180047913  lea     rcx, [rbx+48h]
0x180047917  lea     rdx, [rsp+918h+var_848]
0x18004791f  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047925  mov     rax, [rdi]
0x180047928  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x18004792d  mov     r9d, r14d; unsigned int
0x180047930  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047938  lea     rdx, aLocal_0; "Local"
0x18004793f  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047944  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047949  test    eax, eax
0x18004794b  jnz     loc_180047D92
0x180047951  lea     rcx, [rbx+50h]
0x180047955  lea     rdx, [rsp+918h+var_848]
0x18004795d  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047963  mov     rax, [rdi]
0x180047966  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x18004796b  mov     r9d, r14d; unsigned int
0x18004796e  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047976  lea     rdx, aRemote; "Remote"
0x18004797d  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047982  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047987  test    eax, eax
0x180047989  jnz     loc_180047D92
0x18004798f  lea     rcx, [rbx+58h]
0x180047993  lea     rdx, [rsp+918h+var_848]
0x18004799b  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800479a1  mov     rax, [rdi]
0x1800479a4  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x1800479a9  mov     r9d, r14d; unsigned int
0x1800479ac  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x1800479b4  lea     rdx, aInternet; "Internet"
0x1800479bb  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x1800479c0  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x1800479c5  test    eax, eax
0x1800479c7  jnz     loc_180047D92
0x1800479cd  lea     rcx, [rbx+60h]
0x1800479d1  lea     rdx, [rsp+918h+var_848]
0x1800479d9  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800479df  mov     rax, [rdi]
0x1800479e2  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x1800479e7  mov     r9d, r14d; unsigned int
0x1800479ea  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x1800479f2  lea     rdx, aSecurity; "Security"
0x1800479f9  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x1800479fe  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047a03  test    eax, eax
0x180047a05  jnz     loc_180047D92
0x180047a0b  lea     rcx, [rbx+68h]
0x180047a0f  lea     rdx, [rsp+918h+var_848]
0x180047a17  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047a1d  mov     rax, [rdi]
0x180047a20  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047a25  mov     r9d, r14d; unsigned int
0x180047a28  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047a30  lea     rdx, aAuthlevel; "AuthLevel"
0x180047a37  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047a3c  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047a41  test    eax, eax
0x180047a43  jnz     loc_180047D92
0x180047a49  lea     rcx, [rbx+70h]
0x180047a4d  lea     rdx, [rsp+918h+var_848]
0x180047a55  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047a5b  mov     rax, [rdi]
0x180047a5e  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047a63  mov     r9d, r14d; unsigned int
0x180047a66  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047a6e  lea     rdx, aSystem; "System"
0x180047a75  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047a7a  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047a7f  test    eax, eax
0x180047a81  jnz     loc_180047D92
0x180047a87  lea     rcx, [rbx+78h]
0x180047a8b  lea     rdx, [rsp+918h+var_848]
0x180047a93  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047a99  mov     rax, [rdi]
0x180047a9c  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047aa1  mov     r9d, r14d; unsigned int
0x180047aa4  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047aac  lea     rdx, aProgid; "ProgID"
0x180047ab3  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047ab8  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047abd  test    eax, eax
0x180047abf  jnz     loc_180047D92
0x180047ac5  lea     rcx, [rbx+10h]
0x180047ac9  lea     rdx, [rsp+918h+var_848]
0x180047ad1  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047ad7  mov     rax, [rdi]
0x180047ada  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047adf  mov     r9d, r14d; unsigned int
0x180047ae2  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047aea  lea     rdx, aCompdll; "CompDLL"
0x180047af1  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047af6  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047afb  test    eax, eax
0x180047afd  jnz     loc_180047D92
0x180047b03  lea     rsi, [rbx+28h]
0x180047b07  lea     rdx, [rsp+918h+var_848]
0x180047b0f  mov     rcx, rsi
0x180047b12  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047b18  mov     rax, [rdi]
0x180047b1b  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047b20  mov     r9d, r14d; unsigned int
0x180047b23  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047b2b  lea     rdx, aTypelib_1; "TypeLib"
0x180047b32  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047b37  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047b3c  test    eax, eax
0x180047b3e  jnz     loc_180047D92
0x180047b44  lea     r14, [rbx+30h]
0x180047b48  lea     rdx, [rsp+918h+var_848]
0x180047b50  mov     rcx, r14
0x180047b53  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047b59  movss   xmm0, [rsp+918h+arg_28]
0x180047b62  comiss  xmm0, cs:__real@4000a3d7
0x180047b69  jb      short loc_180047BE8
0x180047b6b  mov     rax, [rdi]
0x180047b6e  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047b73  mov     r9d, 400h; unsigned int
0x180047b79  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047b81  lea     rdx, aOrigin; "Origin"
0x180047b88  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047b8d  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047b92  test    eax, eax
0x180047b94  jnz     loc_180047D92
0x180047b9a  lea     rcx, [rbx+80h]
0x180047ba1  lea     rdx, [rsp+918h+var_848]
0x180047ba9  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047baf  mov     rax, [rdi]
0x180047bb2  mov     [rsp+918h+var_8F8], rax; unsigned __int16 *
0x180047bb7  mov     r9d, 400h; unsigned int
0x180047bbd  lea     r8, [rsp+918h+var_848]; unsigned __int16 *
0x180047bc5  lea     rdx, aWrapped; "Wrapped"
0x180047bcc  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047bd1  call    ?ReadStringFromPDF@@YAJPEBG0PEAGK0@Z; ReadStringFromPDF(ushort const *,ushort const *,ushort *,ulong,ushort const *)
0x180047bd6  test    eax, eax
0x180047bd8  jnz     loc_180047D92
0x180047bde  lea     rdx, [rsp+918h+var_848]
0x180047be6  jmp     short loc_180047C03
0x180047be8  lea     rcx, [rbx+80h]
0x180047bef  lea     rdx, aInstall; "Install"
0x180047bf6  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047bfc  lea     rdx, aY; "Y"
0x180047c03  lea     rcx, [rbx+88h]
0x180047c0a  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x180047c10  mov     rax, [rsi]
0x180047c13  movzx   edx, word ptr [rax]
0x180047c16  xor     eax, eax
0x180047c18  movzx   ecx, ax
0x180047c1b  cmp     edx, ecx
0x180047c1d  jz      short loc_180047C32
0x180047c1f  mov     rdx, r12
0x180047c22  mov     rcx, rsi
0x180047c25  call    ?InsertUniqueNameInList@@YAJAEAVCString@@AEAV?$CList@VCString@@AEAV1@@@@Z; InsertUniqueNameInList(CString &,CList<CString,CString &> &)
0x180047c2a  test    eax, eax
0x180047c2c  js      loc_180047D97
0x180047c32  mov     rdx, [r14]; String2
0x180047c35  xor     eax, eax
0x180047c37  cmp     [rdx], ax
0x180047c3a  jz      short loc_180047C5C
0x180047c3c  mov     rcx, [rsi]; String1
0x180047c3f  call    cs:__imp__wcsicmp
0x180047c45  test    eax, eax
0x180047c47  jz      short loc_180047C5C
0x180047c49  mov     rdx, r12
0x180047c4c  mov     rcx, r14
0x180047c4f  call    ?InsertUniqueNameInList@@YAJAEAVCString@@AEAV?$CList@VCString@@AEAV1@@@@Z; InsertUniqueNameInList(CString &,CList<CString,CString &> &)
0x180047c54  test    eax, eax
0x180047c56  js      loc_180047D97
0x180047c5c  mov     [rsp+918h+var_8E8], 0
0x180047c64  mov     r9, [rdi]; unsigned __int16 *
0x180047c67  lea     r8, [rsp+918h+var_8E8]; unsigned int *
0x180047c6c  lea     rdx, aRoles; "Roles"
0x180047c73  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047c78  call    ?ReadIntFromPDF@@YAJPEBG0PEAK0@Z; ReadIntFromPDF(ushort const *,ushort const *,ulong *,ushort const *)
0x180047c7d  test    eax, eax
0x180047c7f  jnz     loc_180047D92
0x180047c85  xor     r14d, r14d
0x180047c88  mov     r9d, [rsp+918h+var_8E8]
0x180047c8d  test    r9d, r9d
0x180047c90  jz      short loc_180047CC2
0x180047c92  lea     rax, [rbx+90h]
0x180047c99  mov     [rsp+918h+var_8F0], rax; __int64
0x180047c9e  mov     [rsp+918h+var_8F8], r15; __int64
0x180047ca3  lea     r8, aRole; "Role"
0x180047caa  lea     rdx, [rsp+918h+var_8B8]
0x180047caf  mov     rcx, [rdi]; unsigned __int16 *
0x180047cb2  call    ?ReadListFromPDF@@YAJPEBG00KAEAV?$CList@PEAVCPDFRole@@AEAPEAV1@@@AEAV?$CList@VCString@@AEAV1@@@@Z; ReadListFromPDF(ushort const *,ushort const *,ushort const *,ulong,CList<CPDFRole *,CPDFRole * &> &,CList<CString,CString &> &)
0x180047cb7  mov     r14d, eax
0x180047cba  test    eax, eax
0x180047cbc  jnz     loc_180047D97
0x180047cc2  mov     [rsp+918h+var_8E8], 0
0x180047cca  mov     r9, [rdi]; unsigned __int16 *
0x180047ccd  lea     r8, [rsp+918h+var_8E8]; unsigned int *
0x180047cd2  lea     rdx, aInterfaces; "Interfaces"
0x180047cd9  lea     rcx, [rsp+918h+var_8B8]; unsigned __int16 *
0x180047cde  call    ?ReadIntFromPDF@@YAJPEBG0PEAK0@Z; ReadIntFromPDF(ushort const *,ushort const *,ulong *,ushort const *)
0x180047ce3  test    eax, eax
0x180047ce5  jnz     loc_180047D92
0x180047ceb  lea     r15d, [rax+1]
0x180047cef  cmp     r15d, [rsp+918h+var_8E8]
0x180047cf4  ja      loc_180047D8D
0x180047cfa  mov     ecx, 70h ; 'p'; cb
0x180047cff  call    cs:__imp_CoTaskMemAlloc
0x180047d05  mov     [rsp+918h+var_8C8], rax
0x180047d0a  test    rax, rax
0x180047d0d  jz      short loc_180047D2A
0x180047d0f  lea     r9, [rbx+100h]; struct _GUID *
0x180047d16  lea     r8, [rbx+8]; struct CString *
0x180047d1a  mov     rdx, rbx; struct CString *
0x180047d1d  mov     rcx, rax; this
0x180047d20  call    ??0CPDFInterface@@QEAA@AEBVCString@@0AEBU_GUID@@@Z; CPDFInterface::CPDFInterface(CString const &,CString const &,_GUID const &)
0x180047d25  mov     rsi, rax
0x180047d28  jmp     short loc_180047D2C
0x180047d2a  xor     esi, esi
0x180047d2c  mov     [rsp+918h+var_8E0], rsi
0x180047d31  mov     [rsp+918h+var_8D0], rsi
0x180047d36  test    rsi, rsi
  ... truncated ...
```
