# CFsiDirectoryItem::AddFile(ushort *,IStream *)

- ea: `0x18003c9f0`
- end: `0x18003cdae`
- name: `?AddFile@CFsiDirectoryItem@@UEAAJPEAGPEAUIStream@@@Z`
- size: `958`
- prototype: `int(CFsiDirectoryItem *__hidden this, unsigned __int16 *, struct IStream *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003a80`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x18000d1c0`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x180021374`
- `0x180023c08`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x18003c9f0`
- `0x180047c94`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18003ca54`
- `KERNEL32!GetTickCount` at `0x18003cc7d`
- `KERNEL32!GetTickCount` at `0x18003ca54`
- `KERNEL32!GetTickCount` at `0x18003cc7d`

## string_xrefs

- `0x18003ca34`: `CFsiDirectoryItem::AddFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CFsiDirectoryItem::AddFile(CFsiDirectoryItem *this, unsigned __int16 *a2, struct IStream *a3)
{
  ImapiComObject *v5; // r13
  unsigned int v6; // r12d
  int v7; // eax
  int v8; // esi
  __int64 v9; // rax
  CIMAPIException *v10; // rbx
  const struct ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException *v12; // rax
  CIMAPIException **v13; // rbx
  CIMAPIException *v14; // rax
  CIMAPIException *v15; // rax
  CIMAPIException **v16; // rbx
  _QWORD *v17; // rax
  __int64 v18; // r9
  __int64 v19; // rbx
  CIMAPIException *v20; // rax
  CIMAPIException *v21; // rax
  CIMAPIException **v22; // rbx
  char v24[8]; // [rsp+38h] [rbp-160h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+40h] [rbp-158h] BYREF
  CIMAPIException **v26; // [rsp+48h] [rbp-150h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-148h] BYREF
  char v28[8]; // [rsp+60h] [rbp-138h] BYREF
  _BYTE v29[88]; // [rsp+68h] [rbp-130h] BYREF
  _BYTE v30[88]; // [rsp+C0h] [rbp-D8h] BYREF
  _BYTE v31[128]; // [rsp+118h] [rbp-80h] BYREF
  CIMAPIException **v33; // [rsp+1B8h] [rbp+20h] BYREF

  v5 = (CFsiDirectoryItem *)((char *)this - 80);
  v27[1] = (char *)this - 80;
  v6 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  MethodTrace::MethodTrace((MethodTrace *)v28, "CFsiDirectoryItem::AddFile");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS(v5);
  LODWORD(v33) = GetTickCount();
  v7 = ValidateStringPointer(a2, 1u, 0x10000u);
  try
  {
    v8 = v7;
    if ( v7 == -1062555391 || (v8 = ValidateStringPointer(a2, 1u, 0x10000u), v8 == -2147467261) )
    {
      v20 = (CIMAPIException *)operator new(0x58u);
      v33 = (CIMAPIException **)v20;
      if ( v20 )
        v21 = CIMAPIException::CIMAPIException(v20, v8, L"path");
      else
        v21 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v33, v21);
      v22 = v33;
      if ( v33 && *v33 )
      {
        CIMAPIException::SetCodeRefInfo(*v33, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 374);
        v27[0] = v22;
        if ( v22 )
          ++*((_DWORD *)v22 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v27;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v31,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v31;
    }
    if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
    {
      if ( a3 )
        v8 = 0;
      v9 = **((_QWORD **)this + 8);
      if ( !*(_QWORD *)(v9 + 72) )
      {
        v10 = (CIMAPIException *)operator new(0x58u);
        v33 = (CIMAPIException **)v10;
        if ( v10 )
        {
          FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(**((ImapiFsObjectBase ***)this + 8));
          v12 = CIMAPIException::CIMAPIException(v10, -1062555381, *(_QWORD *)FullPathOriginal);
        }
        else
        {
          v12 = 0;
        }
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v33, v12);
        v13 = v33;
        if ( v33 && *v33 )
        {
          CIMAPIException::SetCodeRefInfo(*v33, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 383);
          pExceptionObject = v13;
          if ( v13 )
            ++*((_DWORD *)v13 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v29,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v29;
      }
      if ( *(int *)(*(_QWORD *)(v9 + 64) + 8LL) > 0 )
      {
        v14 = (CIMAPIException *)operator new(0x58u);
        v33 = (CIMAPIException **)v14;
        if ( v14 )
          v15 = CIMAPIException::CIMAPIException(v14, -1062555390);
        else
          v15 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v33, v15);
        v16 = v33;
        if ( v33 && *v33 )
        {
          CIMAPIException::SetCodeRefInfo(*v33, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 387);
          v26 = v16;
          if ( v16 )
            ++*((_DWORD *)v16 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v26;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v30,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v30;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        v24,
        a2);
      v17 = (_QWORD *)*((_QWORD *)this + 8);
      v18 = *(_QWORD *)(*v17 + 64LL);
      LOBYTE(v18) = *(_BYTE *)(v18 + 672);
      ImapiDirectoryInfo::AddFile(*v17, v24, a3, v18);
      v19 = *(_QWORD *)(**((_QWORD **)this + 8) + 64LL);
      *(_DWORD *)(v19 + 808) += GetTickCount() - (_DWORD)v33;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v24);
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  if ( v8 < 0 )
    FileSystemImage::RollbackRecover(*(FileSystemImage **)(**((_QWORD **)this + 8) + 64LL), v6, 1);
  ImapiComObject::UnlockCS(v5);
  MethodTrace::~MethodTrace((MethodTrace *)v28);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003c9f0  mov     [rsp+arg_8], rbx
0x18003c9f5  mov     [rsp+arg_10], r8
0x18003c9fa  mov     [rsp+arg_0], rcx
0x18003c9ff  push    rsi
0x18003ca00  push    rdi
0x18003ca01  push    r12
0x18003ca03  push    r13
0x18003ca05  push    r15
0x18003ca07  sub     rsp, 170h
0x18003ca0e  mov     rbx, rdx
0x18003ca11  mov     r15, rcx
0x18003ca14  lea     r13, [rcx-50h]
0x18003ca18  mov     [rsp+198h+var_140], r13
0x18003ca1d  mov     rax, [r13+90h]
0x18003ca24  mov     r9, [rax]
0x18003ca27  mov     rax, [r9+40h]
0x18003ca2b  mov     r12d, [rax+14h]
0x18003ca2f  mov     [rsp+198h+var_168], r12d
0x18003ca34  lea     rdx, aCfsidirectoryi_7; "CFsiDirectoryItem::AddFile"
0x18003ca3b  lea     rcx, [rsp+198h+var_138]; this
0x18003ca40  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003ca45  nop
0x18003ca46  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003ca4b  nop
0x18003ca4c  mov     rcx, r13; this
0x18003ca4f  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003ca54  call    cs:__imp_GetTickCount
0x18003ca5a  mov     dword ptr [rsp+198h+arg_18], eax
0x18003ca61  mov     edi, 10000h
0x18003ca66  mov     r8d, edi; unsigned __int64
0x18003ca69  mov     edx, 1; unsigned __int64
0x18003ca6e  mov     rcx, rbx; pbstr
0x18003ca71  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003ca76  mov     esi, eax
0x18003ca78  cmp     eax, 0C0AAB101h
0x18003ca7d  jz      loc_18003CCA0
0x18003ca83  mov     r8d, edi; unsigned __int64
0x18003ca86  mov     edx, 1; unsigned __int64
0x18003ca8b  mov     rcx, rbx; pbstr
0x18003ca8e  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003ca93  mov     esi, eax
0x18003ca95  cmp     eax, 80004003h
0x18003ca9a  jz      loc_18003CCA0
0x18003caa0  mov     r8d, edi; unsigned __int64
0x18003caa3  mov     edx, 1; unsigned __int64
0x18003caa8  mov     rcx, rbx; pbstr
0x18003caab  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003cab0  xor     edi, edi
0x18003cab2  test    eax, eax
0x18003cab4  jns     short loc_18003CABB
0x18003cab6  jmp     loc_18003CD67
0x18003cabb  cmp     [rsp+198h+arg_10], rdi
0x18003cac3  cmovnz  esi, edi
0x18003cac6  mov     rax, [r15+40h]
0x18003caca  mov     rax, [rax]
0x18003cacd  cmp     [rax+48h], rdi
0x18003cad1  jnz     loc_18003CB8B
0x18003cad7  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003cadc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cae1  mov     rbx, rax
0x18003cae4  mov     [rsp+198h+arg_18], rax
0x18003caec  test    rax, rax
0x18003caef  jz      short loc_18003CB0F
0x18003caf1  mov     rcx, [r15+40h]
0x18003caf5  mov     rcx, [rcx]; this
0x18003caf8  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x18003cafd  mov     r8, [rax]
0x18003cb00  mov     edx, 0C0AAB10Bh; int
0x18003cb05  mov     rcx, rbx; this
0x18003cb08  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003cb0d  jmp     short loc_18003CB12
0x18003cb0f  mov     rax, rdi
0x18003cb12  mov     rdx, rax
0x18003cb15  lea     rcx, [rsp+198h+arg_18]
0x18003cb1d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003cb22  nop
0x18003cb23  mov     rbx, [rsp+198h+arg_18]
0x18003cb2b  test    rbx, rbx
0x18003cb2e  jz      short loc_18003CB68
0x18003cb30  cmp     [rbx], rdi
0x18003cb33  jz      short loc_18003CB68
0x18003cb35  mov     r8d, 17Fh; int
0x18003cb3b  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003cb42  mov     rcx, [rbx]; this
0x18003cb45  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003cb4a  mov     [rsp+198h+pExceptionObject], rbx
0x18003cb4f  test    rbx, rbx
0x18003cb52  jz      short loc_18003CB57
0x18003cb54  inc     dword ptr [rbx+8]
0x18003cb57  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003cb5e  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x18003cb63  call    _CxxThrowException_0
0x18003cb68  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003cb6f  lea     rcx, [rsp+198h+var_130]; this
0x18003cb74  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003cb79  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003cb80  lea     rcx, [rsp+198h+var_130]; pExceptionObject
0x18003cb85  call    _CxxThrowException_0
0x18003cb8b  mov     rax, [rax+40h]
0x18003cb8f  cmp     [rax+8], edi
0x18003cb92  jle     loc_18003CC40
0x18003cb98  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003cb9d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cba2  mov     [rsp+198h+arg_18], rax
0x18003cbaa  test    rax, rax
0x18003cbad  jz      short loc_18003CBBE
0x18003cbaf  mov     edx, 0C0AAB102h; int
0x18003cbb4  mov     rcx, rax; this
0x18003cbb7  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003cbbc  jmp     short loc_18003CBC1
0x18003cbbe  mov     rax, rdi
0x18003cbc1  mov     rdx, rax
0x18003cbc4  lea     rcx, [rsp+198h+arg_18]
0x18003cbcc  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003cbd1  nop
0x18003cbd2  mov     rbx, [rsp+198h+arg_18]
0x18003cbda  test    rbx, rbx
0x18003cbdd  jz      short loc_18003CC17
0x18003cbdf  cmp     [rbx], rdi
0x18003cbe2  jz      short loc_18003CC17
0x18003cbe4  mov     r8d, 183h; int
0x18003cbea  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003cbf1  mov     rcx, [rbx]; this
0x18003cbf4  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003cbf9  mov     [rsp+198h+var_150], rbx
0x18003cbfe  test    rbx, rbx
0x18003cc01  jz      short loc_18003CC06
0x18003cc03  inc     dword ptr [rbx+8]
0x18003cc06  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003cc0d  lea     rcx, [rsp+198h+var_150]; pExceptionObject
0x18003cc12  call    _CxxThrowException_0
0x18003cc17  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003cc1e  lea     rcx, [rsp+198h+var_D8]; this
0x18003cc26  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003cc2b  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003cc32  lea     rcx, [rsp+198h+var_D8]; pExceptionObject
0x18003cc3a  call    _CxxThrowException_0
0x18003cc40  mov     rdx, rbx
0x18003cc43  lea     rcx, [rsp+198h+var_160]
0x18003cc48  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003cc4d  nop
0x18003cc4e  mov     rax, [r15+40h]
0x18003cc52  mov     rcx, [rax]
0x18003cc55  mov     r9, [rcx+40h]
0x18003cc59  mov     r9b, [r9+2A0h]
0x18003cc60  mov     r8, [rsp+198h+arg_10]
0x18003cc68  lea     rdx, [rsp+198h+var_160]
0x18003cc6d  call    ?AddFile@ImapiDirectoryInfo@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUIStream@@_N2@Z; ImapiDirectoryInfo::AddFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,IStream *,bool,bool)
0x18003cc72  mov     rax, [r15+40h]
0x18003cc76  mov     rcx, [rax]
0x18003cc79  mov     rbx, [rcx+40h]
0x18003cc7d  call    cs:__imp_GetTickCount
0x18003cc83  sub     eax, dword ptr [rsp+198h+arg_18]
0x18003cc8a  add     [rbx+328h], eax
0x18003cc90  lea     rcx, [rsp+198h+var_160]; void *
0x18003cc95  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003cc9a  nop
0x18003cc9b  jmp     loc_18003CD67
0x18003cca0  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003cca5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ccaa  mov     [rsp+198h+arg_18], rax
0x18003ccb2  xor     edi, edi
0x18003ccb4  test    rax, rax
0x18003ccb7  jz      short loc_18003CCCC
0x18003ccb9  lea     r8, aPath; "path"
0x18003ccc0  mov     edx, esi; int
0x18003ccc2  mov     rcx, rax; this
0x18003ccc5  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003ccca  jmp     short loc_18003CCCF
0x18003cccc  mov     rax, rdi
0x18003cccf  mov     rdx, rax
0x18003ccd2  lea     rcx, [rsp+198h+arg_18]
0x18003ccda  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003ccdf  nop
0x18003cce0  mov     rbx, [rsp+198h+arg_18]
0x18003cce8  test    rbx, rbx
0x18003cceb  jz      short loc_18003CD25
0x18003cced  cmp     [rbx], rdi
0x18003ccf0  jz      short loc_18003CD25
0x18003ccf2  mov     r8d, 176h; int
0x18003ccf8  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003ccff  mov     rcx, [rbx]; this
0x18003cd02  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003cd07  mov     [rsp+198h+var_148], rbx
0x18003cd0c  test    rbx, rbx
0x18003cd0f  jz      short loc_18003CD14
0x18003cd11  inc     dword ptr [rbx+8]
0x18003cd14  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003cd1b  lea     rcx, [rsp+198h+var_148]; pExceptionObject
0x18003cd20  call    _CxxThrowException_0
0x18003cd25  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003cd2c  lea     rcx, [rsp+198h+var_80]; this
0x18003cd34  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003cd39  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003cd40  lea     rcx, [rsp+198h+var_80]; pExceptionObject
0x18003cd48  call    _CxxThrowException_0
0x18003cd4e  mov     r15, [rsp+198h+arg_0]
0x18003cd56  mov     esi, dword ptr [rsp+198h+arg_18]
0x18003cd5d  mov     r13, [rsp+198h+var_140]
0x18003cd62  mov     r12d, [rsp+198h+var_168]
0x18003cd67  test    esi, esi
0x18003cd69  jns     short loc_18003CD81
0x18003cd6b  mov     rax, [r15+40h]
0x18003cd6f  mov     rcx, [rax]
0x18003cd72  mov     r8b, 1; bool
0x18003cd75  mov     edx, r12d; unsigned int
0x18003cd78  mov     rcx, [rcx+40h]; this
0x18003cd7c  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x18003cd81  mov     rcx, r13; this
0x18003cd84  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003cd89  nop
0x18003cd8a  lea     rcx, [rsp+198h+var_138]; this
0x18003cd8f  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003cd94  mov     eax, esi
0x18003cd96  mov     rbx, [rsp+198h+arg_8]
0x18003cd9e  add     rsp, 170h
0x18003cda5  pop     r15
0x18003cda7  pop     r13
0x18003cda9  pop     r12
0x18003cdab  pop     rdi
0x18003cdac  pop     rsi
0x18003cdad  retn
```
