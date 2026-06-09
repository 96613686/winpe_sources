# CFsiDirectoryItem::AddDirectory(ushort *)

- ea: `0x18003c660`
- end: `0x18003c9e8`
- name: `?AddDirectory@CFsiDirectoryItem@@UEAAJPEAG@Z`
- size: `904`
- prototype: `int(CFsiDirectoryItem *__hidden this, unsigned __int16 *)`
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
- `0x180020fd0`
- `0x180023c08`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x18003c660`
- `0x180047c94`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18003c6c3`
- `KERNEL32!GetTickCount` at `0x18003c8be`
- `KERNEL32!GetTickCount` at `0x18003c6c3`
- `KERNEL32!GetTickCount` at `0x18003c8be`

## string_xrefs

- `0x18003c6a3`: `CFsiDirectoryItem::AddDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFsiDirectoryItem::AddDirectory(CFsiDirectoryItem *this, unsigned __int16 *a2)
{
  ImapiComObject *v4; // r15
  unsigned int v5; // r12d
  DWORD TickCount; // r13d
  int v7; // eax
  int v8; // r14d
  __int64 v9; // rax
  CIMAPIException *v10; // rax
  CIMAPIException *v11; // rbx
  const struct ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException **v13; // rbx
  CIMAPIException *v14; // rax
  CIMAPIException **v15; // rbx
  __int64 v16; // rbx
  CIMAPIException *v17; // rax
  CIMAPIException **v18; // rbx
  CIMAPIException **v20; // [rsp+20h] [rbp-168h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+28h] [rbp-160h] BYREF
  CIMAPIException **v22; // [rsp+30h] [rbp-158h] BYREF
  _QWORD v23[2]; // [rsp+38h] [rbp-150h] BYREF
  char v24[8]; // [rsp+48h] [rbp-140h] BYREF
  _BYTE v25[88]; // [rsp+50h] [rbp-138h] BYREF
  _BYTE v26[88]; // [rsp+A8h] [rbp-E0h] BYREF
  _BYTE v27[136]; // [rsp+100h] [rbp-88h] BYREF
  int v28; // [rsp+1A0h] [rbp+18h] BYREF
  unsigned int v29; // [rsp+1A8h] [rbp+20h]

  v4 = (CFsiDirectoryItem *)((char *)this - 80);
  v23[1] = (char *)this - 80;
  v5 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  v29 = v5;
  MethodTrace::MethodTrace((MethodTrace *)v24, "CFsiDirectoryItem::AddDirectory");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS(v4);
  TickCount = GetTickCount();
  v7 = ValidateStringPointer(a2, 1u, 0x10000u);
  try
  {
    v8 = v7;
    if ( v7 == -1062555391 || (v8 = ValidateStringPointer(a2, 1u, 0x10000u), v8 == -2147467261) )
    {
      v17 = (CIMAPIException *)operator new(0x58u);
      v20 = (CIMAPIException **)v17;
      if ( v17 )
        v17 = CIMAPIException::CIMAPIException(v17, v8, L"path");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v20, v17);
      v18 = v20;
      if ( v20 && *v20 )
      {
        CIMAPIException::SetCodeRefInfo(*v20, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 345);
        v23[0] = v18;
        if ( v18 )
          ++*((_DWORD *)v18 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v23;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v27,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v27;
    }
    if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
    {
      v9 = **((_QWORD **)this + 8);
      if ( !*(_QWORD *)(v9 + 72) )
      {
        v10 = (CIMAPIException *)operator new(0x58u);
        v11 = v10;
        v20 = (CIMAPIException **)v10;
        if ( v10 )
        {
          FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(**((ImapiFsObjectBase ***)this + 8));
          v10 = CIMAPIException::CIMAPIException(v11, -1062555381, *(_QWORD *)FullPathOriginal);
        }
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v20, v10);
        v13 = v20;
        if ( v20 && *v20 )
        {
          CIMAPIException::SetCodeRefInfo(*v20, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 349);
          pExceptionObject = v13;
          if ( v13 )
            ++*((_DWORD *)v13 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v25,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v25;
      }
      if ( *(int *)(*(_QWORD *)(v9 + 64) + 8LL) > 0 )
      {
        v14 = (CIMAPIException *)operator new(0x58u);
        v20 = (CIMAPIException **)v14;
        if ( v14 )
          v14 = CIMAPIException::CIMAPIException(v14, -1062555390);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v20, v14);
        v15 = v20;
        if ( v20 && *v20 )
        {
          CIMAPIException::SetCodeRefInfo(*v20, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 353);
          v22 = v15;
          if ( v15 )
            ++*((_DWORD *)v15 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v22;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v26,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v26;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v28,
        a2);
      ImapiDirectoryInfo::AddDirectory(**((_QWORD **)this + 8), &v28);
      v16 = *(_QWORD *)(**((_QWORD **)this + 8) + 64LL);
      *(_DWORD *)(v16 + 808) += GetTickCount() - TickCount;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v28);
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  if ( v8 < 0 )
    FileSystemImage::RollbackRecover(*(FileSystemImage **)(**((_QWORD **)this + 8) + 64LL), v5, 1);
  ImapiComObject::UnlockCS(v4);
  MethodTrace::~MethodTrace((MethodTrace *)v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003c660  mov     [rsp+arg_8], rbx
0x18003c665  mov     [rsp+arg_0], rcx
0x18003c66a  push    rdi
0x18003c66b  push    r12
0x18003c66d  push    r13
0x18003c66f  push    r14
0x18003c671  push    r15
0x18003c673  sub     rsp, 160h
0x18003c67a  mov     rbx, rdx
0x18003c67d  mov     rdi, rcx
0x18003c680  lea     r15, [rcx-50h]
0x18003c684  mov     [rsp+188h+var_148], r15
0x18003c689  mov     rax, [r15+90h]
0x18003c690  mov     r8, [rax]
0x18003c693  mov     rax, [r8+40h]
0x18003c697  mov     r12d, [rax+14h]
0x18003c69b  mov     [rsp+188h+arg_18], r12d
0x18003c6a3  lea     rdx, aCfsidirectoryi_10; "CFsiDirectoryItem::AddDirectory"
0x18003c6aa  lea     rcx, [rsp+188h+var_140]; this
0x18003c6af  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003c6b4  nop
0x18003c6b5  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003c6ba  nop
0x18003c6bb  mov     rcx, r15; this
0x18003c6be  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003c6c3  call    cs:__imp_GetTickCount
0x18003c6c9  mov     r13d, eax
0x18003c6cc  mov     edx, 1; unsigned __int64
0x18003c6d1  mov     r8d, 10000h; unsigned __int64
0x18003c6d7  mov     rcx, rbx; pbstr
0x18003c6da  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003c6df  mov     r14d, eax
0x18003c6e2  cmp     eax, 0C0AAB101h
0x18003c6e7  jz      loc_18003C8E0
0x18003c6ed  mov     edx, 1; unsigned __int64
0x18003c6f2  mov     r8d, 10000h; unsigned __int64
0x18003c6f8  mov     rcx, rbx; pbstr
0x18003c6fb  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003c700  mov     r14d, eax
0x18003c703  cmp     eax, 80004003h
0x18003c708  jz      loc_18003C8E0
0x18003c70e  mov     edx, 1; unsigned __int64
0x18003c713  mov     r8d, 10000h; unsigned __int64
0x18003c719  mov     rcx, rbx; pbstr
0x18003c71c  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003c721  test    eax, eax
0x18003c723  jns     short loc_18003C72A
0x18003c725  jmp     loc_18003C99E
0x18003c72a  mov     rax, [rdi+40h]
0x18003c72e  mov     rax, [rax]
0x18003c731  cmp     qword ptr [rax+48h], 0
0x18003c736  jnz     loc_18003C7E4
0x18003c73c  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003c741  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c746  mov     rbx, rax
0x18003c749  mov     [rsp+188h+var_168], rax
0x18003c74e  test    rax, rax
0x18003c751  jz      short loc_18003C770
0x18003c753  mov     rcx, [rdi+40h]
0x18003c757  mov     rcx, [rcx]; this
0x18003c75a  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x18003c75f  mov     r8, [rax]
0x18003c762  mov     edx, 0C0AAB10Bh; int
0x18003c767  mov     rcx, rbx; this
0x18003c76a  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003c76f  nop
0x18003c770  mov     rdx, rax
0x18003c773  lea     rcx, [rsp+188h+var_168]
0x18003c778  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003c77d  nop
0x18003c77e  mov     rbx, [rsp+188h+var_168]
0x18003c783  test    rbx, rbx
0x18003c786  jz      short loc_18003C7C1
0x18003c788  cmp     qword ptr [rbx], 0
0x18003c78c  jz      short loc_18003C7C1
0x18003c78e  mov     r8d, 15Dh; int
0x18003c794  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003c79b  mov     rcx, [rbx]; this
0x18003c79e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003c7a3  mov     [rsp+188h+pExceptionObject], rbx
0x18003c7a8  test    rbx, rbx
0x18003c7ab  jz      short loc_18003C7B0
0x18003c7ad  inc     dword ptr [rbx+8]
0x18003c7b0  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003c7b7  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x18003c7bc  call    _CxxThrowException_0
0x18003c7c1  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003c7c8  lea     rcx, [rsp+188h+var_138]; this
0x18003c7cd  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003c7d2  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003c7d9  lea     rcx, [rsp+188h+var_138]; pExceptionObject
0x18003c7de  call    _CxxThrowException_0
0x18003c7e4  mov     rax, [rax+40h]
0x18003c7e8  cmp     dword ptr [rax+8], 0
0x18003c7ec  jle     loc_18003C88E
0x18003c7f2  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003c7f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c7fc  mov     [rsp+188h+var_168], rax
0x18003c801  test    rax, rax
0x18003c804  jz      short loc_18003C814
0x18003c806  mov     edx, 0C0AAB102h; int
0x18003c80b  mov     rcx, rax; this
0x18003c80e  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003c813  nop
0x18003c814  mov     rdx, rax
0x18003c817  lea     rcx, [rsp+188h+var_168]
0x18003c81c  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003c821  nop
0x18003c822  mov     rbx, [rsp+188h+var_168]
0x18003c827  test    rbx, rbx
0x18003c82a  jz      short loc_18003C865
0x18003c82c  cmp     qword ptr [rbx], 0
0x18003c830  jz      short loc_18003C865
0x18003c832  mov     r8d, 161h; int
0x18003c838  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003c83f  mov     rcx, [rbx]; this
0x18003c842  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003c847  mov     [rsp+188h+var_158], rbx
0x18003c84c  test    rbx, rbx
0x18003c84f  jz      short loc_18003C854
0x18003c851  inc     dword ptr [rbx+8]
0x18003c854  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003c85b  lea     rcx, [rsp+188h+var_158]; pExceptionObject
0x18003c860  call    _CxxThrowException_0
0x18003c865  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003c86c  lea     rcx, [rsp+188h+var_E0]; this
0x18003c874  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003c879  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003c880  lea     rcx, [rsp+188h+var_E0]; pExceptionObject
0x18003c888  call    _CxxThrowException_0
0x18003c88e  mov     rdx, rbx
0x18003c891  lea     rcx, [rsp+188h+arg_10]
0x18003c899  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003c89e  nop
0x18003c89f  mov     rcx, [rdi+40h]
0x18003c8a3  lea     rdx, [rsp+188h+arg_10]
0x18003c8ab  mov     rcx, [rcx]
0x18003c8ae  call    ?AddDirectory@ImapiDirectoryInfo@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; ImapiDirectoryInfo::AddDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003c8b3  mov     rax, [rdi+40h]
0x18003c8b7  mov     rcx, [rax]
0x18003c8ba  mov     rbx, [rcx+40h]
0x18003c8be  call    cs:__imp_GetTickCount
0x18003c8c4  sub     eax, r13d
0x18003c8c7  add     [rbx+328h], eax
0x18003c8cd  lea     rcx, [rsp+188h+arg_10]; void *
0x18003c8d5  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003c8da  nop
0x18003c8db  jmp     loc_18003C99E
0x18003c8e0  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003c8e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c8ea  mov     [rsp+188h+var_168], rax
0x18003c8ef  test    rax, rax
0x18003c8f2  jz      short loc_18003C907
0x18003c8f4  lea     r8, aPath; "path"
0x18003c8fb  mov     edx, r14d; int
0x18003c8fe  mov     rcx, rax; this
0x18003c901  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003c906  nop
0x18003c907  mov     rdx, rax
0x18003c90a  lea     rcx, [rsp+188h+var_168]
0x18003c90f  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003c914  nop
0x18003c915  mov     rbx, [rsp+188h+var_168]
0x18003c91a  test    rbx, rbx
0x18003c91d  jz      short loc_18003C958
0x18003c91f  cmp     qword ptr [rbx], 0
0x18003c923  jz      short loc_18003C958
0x18003c925  mov     r8d, 159h; int
0x18003c92b  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003c932  mov     rcx, [rbx]; this
0x18003c935  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003c93a  mov     [rsp+188h+var_150], rbx
0x18003c93f  test    rbx, rbx
0x18003c942  jz      short loc_18003C947
0x18003c944  inc     dword ptr [rbx+8]
0x18003c947  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003c94e  lea     rcx, [rsp+188h+var_150]; pExceptionObject
0x18003c953  call    _CxxThrowException_0
0x18003c958  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003c95f  lea     rcx, [rsp+188h+var_88]; this
0x18003c967  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003c96c  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003c973  lea     rcx, [rsp+188h+var_88]; pExceptionObject
0x18003c97b  call    _CxxThrowException_0
0x18003c981  mov     rdi, [rsp+188h+arg_0]
0x18003c989  mov     r14d, [rsp+188h+arg_10]
0x18003c991  mov     r15, [rsp+188h+var_148]
0x18003c996  mov     r12d, [rsp+188h+arg_18]
0x18003c99e  test    r14d, r14d
0x18003c9a1  jns     short loc_18003C9B9
0x18003c9a3  mov     rax, [rdi+40h]
0x18003c9a7  mov     rcx, [rax]
0x18003c9aa  mov     r8b, 1; bool
0x18003c9ad  mov     edx, r12d; unsigned int
0x18003c9b0  mov     rcx, [rcx+40h]; this
0x18003c9b4  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x18003c9b9  mov     rcx, r15; this
0x18003c9bc  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003c9c1  nop
0x18003c9c2  lea     rcx, [rsp+188h+var_140]; this
0x18003c9c7  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003c9cc  mov     eax, r14d
0x18003c9cf  mov     rbx, [rsp+188h+arg_8]
0x18003c9d7  add     rsp, 160h
0x18003c9de  pop     r15
0x18003c9e0  pop     r14
0x18003c9e2  pop     r13
0x18003c9e4  pop     r12
0x18003c9e6  pop     rdi
0x18003c9e7  retn
```
