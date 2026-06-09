# CFsiFileItem::RemoveStream(ushort *)

- ea: `0x18003ee20`
- end: `0x18003f2bf`
- name: `?RemoveStream@CFsiFileItem@@UEAAJPEAG@Z`
- size: `1183`
- prototype: `int(CFsiFileItem *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
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
- `0x180022180`
- `0x180023c08`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x180030b90`
- `0x18003ee20`
- `0x180047c94`

## string_xrefs

- `0x18003ee63`: `CFsiFileItem::RemoveStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFsiFileItem::RemoveStream(CFsiFileItem *this, unsigned __int16 *a2)
{
  ImapiComObject *v4; // r14
  unsigned int v5; // r12d
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rax
  CIMAPIException *v9; // rax
  CIMAPIException **v10; // rbx
  CIMAPIException *v11; // rax
  CIMAPIException **v12; // rbx
  CIMAPIException *v13; // rax
  CIMAPIException *v14; // rbx
  const struct ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException **v16; // rbx
  CIMAPIException *v17; // rax
  CIMAPIException **v18; // rbx
  CIMAPIException **v20; // [rsp+20h] [rbp-1C8h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+28h] [rbp-1C0h] BYREF
  CIMAPIException **v22; // [rsp+30h] [rbp-1B8h] BYREF
  CIMAPIException **v23; // [rsp+38h] [rbp-1B0h] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-1A8h] BYREF
  char v25[8]; // [rsp+50h] [rbp-198h] BYREF
  _BYTE v26[88]; // [rsp+58h] [rbp-190h] BYREF
  _BYTE v27[88]; // [rsp+B0h] [rbp-138h] BYREF
  _BYTE v28[88]; // [rsp+108h] [rbp-E0h] BYREF
  _BYTE v29[136]; // [rsp+160h] [rbp-88h] BYREF
  int v30; // [rsp+200h] [rbp+18h] BYREF
  unsigned int v31; // [rsp+208h] [rbp+20h]

  v4 = (CFsiFileItem *)((char *)this - 80);
  v24[1] = (char *)this - 80;
  v5 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  v31 = v5;
  MethodTrace::MethodTrace((MethodTrace *)v25, "CFsiFileItem::RemoveStream");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS(v4);
  v6 = ValidateStringPointer(a2, 1u, 0x10000u);
  try
  {
    v7 = v6;
    if ( v6 == -1062555391 || (v7 = ValidateStringPointer(a2, 1u, 0x10000u), v7 == -2147467261) )
    {
      v17 = (CIMAPIException *)operator new(0x58u);
      v20 = (CIMAPIException **)v17;
      if ( v17 )
        v17 = CIMAPIException::CIMAPIException(v17, v7, L"name");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v20, v17);
      v18 = v20;
      if ( v20 && *v20 )
      {
        CIMAPIException::SetCodeRefInfo(*v20, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 1459);
        v24[0] = v18;
        if ( v18 )
          ++*((_DWORD *)v18 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v24;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v29,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v29;
    }
    if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
    {
      v8 = **((_QWORD **)this + 8);
      if ( *(_DWORD *)(v8 + 56) == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids);
        }
        v9 = (CIMAPIException *)operator new(0x58u);
        v20 = (CIMAPIException **)v9;
        if ( v9 )
          v9 = CIMAPIException::CIMAPIException(v9, -1062555392);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v20, v9);
        v10 = v20;
        if ( v20 && *v20 )
        {
          CIMAPIException::SetCodeRefInfo(*v20, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 1466);
          pExceptionObject = v10;
          if ( v10 )
            ++*((_DWORD *)v10 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v26,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v26;
      }
      if ( !*(_QWORD *)(v8 + 72) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids);
        }
        v13 = (CIMAPIException *)operator new(0x58u);
        v14 = v13;
        v20 = (CIMAPIException **)v13;
        if ( v13 )
        {
          FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(**((ImapiFsObjectBase ***)this + 8));
          v13 = CIMAPIException::CIMAPIException(v14, -1062555381, *(_QWORD *)FullPathOriginal);
        }
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v20, v13);
        v16 = v20;
        if ( v20 && *v20 )
        {
          CIMAPIException::SetCodeRefInfo(*v20, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 1474);
          v23 = v16;
          if ( v16 )
            ++*((_DWORD *)v16 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v23;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v28,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v28;
      }
      if ( *(int *)(*(_QWORD *)(v8 + 64) + 8LL) > 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids);
        }
        v11 = (CIMAPIException *)operator new(0x58u);
        v20 = (CIMAPIException **)v11;
        if ( v11 )
          v11 = CIMAPIException::CIMAPIException(v11, -1062555390);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v20, v11);
        v12 = v20;
        if ( v20 && *v20 )
        {
          CIMAPIException::SetCodeRefInfo(*v20, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 1481);
          v22 = v12;
          if ( v12 )
            ++*((_DWORD *)v12 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v22;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v27,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v27;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v30,
        a2);
      ImapiFileInfo::RemoveStream(**((ImapiFsObjectBase ***)this + 8));
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v30);
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiFileItem);
  }
  if ( v7 < 0 )
    FileSystemImage::RollbackRecover(*(FileSystemImage **)(**((_QWORD **)this + 8) + 64LL), v5, 1);
  ImapiComObject::UnlockCS(v4);
  MethodTrace::~MethodTrace((MethodTrace *)v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003ee20  mov     [rsp+arg_8], rbx
0x18003ee25  mov     [rsp+arg_0], rcx
0x18003ee2a  push    rsi
0x18003ee2b  push    r12
0x18003ee2d  push    r13
0x18003ee2f  push    r14
0x18003ee31  push    r15
0x18003ee33  sub     rsp, 1C0h
0x18003ee3a  mov     r15, rdx
0x18003ee3d  mov     rsi, rcx
0x18003ee40  lea     r14, [rcx-50h]
0x18003ee44  mov     [rsp+1E8h+var_1A0], r14
0x18003ee49  mov     rax, [r14+90h]
0x18003ee50  mov     r8, [rax]
0x18003ee53  mov     rax, [r8+40h]
0x18003ee57  mov     r12d, [rax+14h]
0x18003ee5b  mov     [rsp+1E8h+arg_18], r12d
0x18003ee63  lea     rdx, aCfsifileitemRe; "CFsiFileItem::RemoveStream"
0x18003ee6a  lea     rcx, [rsp+1E8h+var_198]; this
0x18003ee6f  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003ee74  nop
0x18003ee75  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003ee7a  nop
0x18003ee7b  mov     rcx, r14; this
0x18003ee7e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003ee83  mov     r13d, 10000h
0x18003ee89  mov     r8d, r13d; unsigned __int64
0x18003ee8c  mov     edx, 1; unsigned __int64
0x18003ee91  mov     rcx, r15; pbstr
0x18003ee94  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003ee99  mov     ebx, eax
0x18003ee9b  cmp     eax, 0C0AAB101h
0x18003eea0  jz      loc_18003F1BB
0x18003eea6  mov     r8d, r13d; unsigned __int64
0x18003eea9  mov     edx, 1; unsigned __int64
0x18003eeae  mov     rcx, r15; pbstr
0x18003eeb1  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003eeb6  mov     ebx, eax
0x18003eeb8  cmp     eax, 80004003h
0x18003eebd  jz      loc_18003F1BB
0x18003eec3  mov     r8d, r13d; unsigned __int64
0x18003eec6  mov     edx, 1; unsigned __int64
0x18003eecb  mov     rcx, r15; pbstr
0x18003eece  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003eed3  test    eax, eax
0x18003eed5  jns     short loc_18003EEDC
0x18003eed7  jmp     loc_18003F277
0x18003eedc  mov     rax, [rsi+40h]
0x18003eee0  mov     rax, [rax]
0x18003eee3  cmp     dword ptr [rax+38h], 2
0x18003eee7  jnz     loc_18003EFB7
0x18003eeed  lea     rax, WPP_GLOBAL_Control
0x18003eef4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eefb  cmp     rcx, rax
0x18003eefe  jz      short loc_18003EF21
0x18003ef00  test    byte ptr [rcx+44h], 4
0x18003ef04  jz      short loc_18003EF21
0x18003ef06  cmp     byte ptr [rcx+41h], 2
0x18003ef0a  jb      short loc_18003EF21
0x18003ef0c  mov     edx, 12h
0x18003ef11  lea     r8, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids
0x18003ef18  mov     rcx, [rcx+38h]
0x18003ef1c  call    WPP_SF_
0x18003ef21  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003ef26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ef2b  mov     [rsp+1E8h+var_1C8], rax
0x18003ef30  test    rax, rax
0x18003ef33  jz      short loc_18003EF43
0x18003ef35  mov     edx, 0C0AAB100h; int
0x18003ef3a  mov     rcx, rax; this
0x18003ef3d  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003ef42  nop
0x18003ef43  mov     rdx, rax
0x18003ef46  lea     rcx, [rsp+1E8h+var_1C8]
0x18003ef4b  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003ef50  nop
0x18003ef51  mov     rbx, [rsp+1E8h+var_1C8]
0x18003ef56  test    rbx, rbx
0x18003ef59  jz      short loc_18003EF94
0x18003ef5b  cmp     qword ptr [rbx], 0
0x18003ef5f  jz      short loc_18003EF94
0x18003ef61  mov     r8d, 5BAh; int
0x18003ef67  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003ef6e  mov     rcx, [rbx]; this
0x18003ef71  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003ef76  mov     [rsp+1E8h+pExceptionObject], rbx
0x18003ef7b  test    rbx, rbx
0x18003ef7e  jz      short loc_18003EF83
0x18003ef80  inc     dword ptr [rbx+8]
0x18003ef83  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003ef8a  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x18003ef8f  call    _CxxThrowException_0
0x18003ef94  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003ef9b  lea     rcx, [rsp+1E8h+var_190]; this
0x18003efa0  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003efa5  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003efac  lea     rcx, [rsp+1E8h+var_190]; pExceptionObject
0x18003efb1  call    _CxxThrowException_0
0x18003efb7  cmp     qword ptr [rax+48h], 0
0x18003efbc  jz      loc_18003F0D9
0x18003efc2  mov     rax, [rax+40h]
0x18003efc6  cmp     dword ptr [rax+8], 0
0x18003efca  jle     loc_18003F0A0
0x18003efd0  lea     rax, WPP_GLOBAL_Control
0x18003efd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003efde  cmp     rcx, rax
0x18003efe1  jz      short loc_18003F004
0x18003efe3  test    byte ptr [rcx+44h], 4
0x18003efe7  jz      short loc_18003F004
0x18003efe9  cmp     byte ptr [rcx+41h], 2
0x18003efed  jb      short loc_18003F004
0x18003efef  mov     edx, 14h
0x18003eff4  lea     r8, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids
0x18003effb  mov     rcx, [rcx+38h]
0x18003efff  call    WPP_SF_
0x18003f004  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003f009  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f00e  mov     [rsp+1E8h+var_1C8], rax
0x18003f013  test    rax, rax
0x18003f016  jz      short loc_18003F026
0x18003f018  mov     edx, 0C0AAB102h; int
0x18003f01d  mov     rcx, rax; this
0x18003f020  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003f025  nop
0x18003f026  mov     rdx, rax
0x18003f029  lea     rcx, [rsp+1E8h+var_1C8]
0x18003f02e  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003f033  nop
0x18003f034  mov     rbx, [rsp+1E8h+var_1C8]
0x18003f039  test    rbx, rbx
0x18003f03c  jz      short loc_18003F077
0x18003f03e  cmp     qword ptr [rbx], 0
0x18003f042  jz      short loc_18003F077
0x18003f044  mov     r8d, 5C9h; int
0x18003f04a  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003f051  mov     rcx, [rbx]; this
0x18003f054  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003f059  mov     [rsp+1E8h+var_1B8], rbx
0x18003f05e  test    rbx, rbx
0x18003f061  jz      short loc_18003F066
0x18003f063  inc     dword ptr [rbx+8]
0x18003f066  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003f06d  lea     rcx, [rsp+1E8h+var_1B8]; pExceptionObject
0x18003f072  call    _CxxThrowException_0
0x18003f077  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003f07e  lea     rcx, [rsp+1E8h+var_138]; this
0x18003f086  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003f08b  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003f092  lea     rcx, [rsp+1E8h+var_138]; pExceptionObject
0x18003f09a  call    _CxxThrowException_0
0x18003f0a0  mov     rdx, r15
0x18003f0a3  lea     rcx, [rsp+1E8h+arg_10]
0x18003f0ab  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003f0b0  nop
0x18003f0b1  mov     rcx, [rsi+40h]
0x18003f0b5  lea     rdx, [rsp+1E8h+arg_10]
0x18003f0bd  mov     rcx, [rcx]; this
0x18003f0c0  call    ?RemoveStream@ImapiFileInfo@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; ImapiFileInfo::RemoveStream(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003f0c5  nop
0x18003f0c6  lea     rcx, [rsp+1E8h+arg_10]; void *
0x18003f0ce  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003f0d3  nop
0x18003f0d4  jmp     loc_18003F277
0x18003f0d9  lea     rax, WPP_GLOBAL_Control
0x18003f0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f0e7  cmp     rcx, rax
0x18003f0ea  jz      short loc_18003F10D
0x18003f0ec  test    byte ptr [rcx+44h], 4
0x18003f0f0  jz      short loc_18003F10D
0x18003f0f2  cmp     byte ptr [rcx+41h], 2
0x18003f0f6  jb      short loc_18003F10D
0x18003f0f8  mov     edx, 13h
0x18003f0fd  lea     r8, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids
0x18003f104  mov     rcx, [rcx+38h]
0x18003f108  call    WPP_SF_
0x18003f10d  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003f112  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f117  mov     rbx, rax
0x18003f11a  mov     [rsp+1E8h+var_1C8], rax
0x18003f11f  test    rax, rax
0x18003f122  jz      short loc_18003F141
0x18003f124  mov     rcx, [rsi+40h]
0x18003f128  mov     rcx, [rcx]; this
0x18003f12b  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x18003f130  mov     r8, [rax]
0x18003f133  mov     edx, 0C0AAB10Bh; int
0x18003f138  mov     rcx, rbx; this
0x18003f13b  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003f140  nop
0x18003f141  mov     rdx, rax
0x18003f144  lea     rcx, [rsp+1E8h+var_1C8]
0x18003f149  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003f14e  nop
0x18003f14f  mov     rbx, [rsp+1E8h+var_1C8]
0x18003f154  test    rbx, rbx
0x18003f157  jz      short loc_18003F192
0x18003f159  cmp     qword ptr [rbx], 0
0x18003f15d  jz      short loc_18003F192
0x18003f15f  mov     r8d, 5C2h; int
0x18003f165  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003f16c  mov     rcx, [rbx]; this
0x18003f16f  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003f174  mov     [rsp+1E8h+var_1B0], rbx
0x18003f179  test    rbx, rbx
0x18003f17c  jz      short loc_18003F181
0x18003f17e  inc     dword ptr [rbx+8]
0x18003f181  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003f188  lea     rcx, [rsp+1E8h+var_1B0]; pExceptionObject
0x18003f18d  call    _CxxThrowException_0
0x18003f192  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003f199  lea     rcx, [rsp+1E8h+var_E0]; this
0x18003f1a1  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003f1a6  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003f1ad  lea     rcx, [rsp+1E8h+var_E0]; pExceptionObject
0x18003f1b5  call    _CxxThrowException_0
0x18003f1bb  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003f1c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f1c5  mov     [rsp+1E8h+var_1C8], rax
0x18003f1ca  test    rax, rax
0x18003f1cd  jz      short loc_18003F1E1
0x18003f1cf  lea     r8, aName; "name"
0x18003f1d6  mov     edx, ebx; int
0x18003f1d8  mov     rcx, rax; this
0x18003f1db  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003f1e0  nop
0x18003f1e1  mov     rdx, rax
0x18003f1e4  lea     rcx, [rsp+1E8h+var_1C8]
0x18003f1e9  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003f1ee  nop
0x18003f1ef  mov     rbx, [rsp+1E8h+var_1C8]
0x18003f1f4  test    rbx, rbx
0x18003f1f7  jz      short loc_18003F232
0x18003f1f9  cmp     qword ptr [rbx], 0
0x18003f1fd  jz      short loc_18003F232
0x18003f1ff  mov     r8d, 5B3h; int
0x18003f205  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003f20c  mov     rcx, [rbx]; this
0x18003f20f  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003f214  mov     [rsp+1E8h+var_1A8], rbx
0x18003f219  test    rbx, rbx
0x18003f21c  jz      short loc_18003F221
0x18003f21e  inc     dword ptr [rbx+8]
0x18003f221  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003f228  lea     rcx, [rsp+1E8h+var_1A8]; pExceptionObject
0x18003f22d  call    _CxxThrowException_0
0x18003f232  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003f239  lea     rcx, [rsp+1E8h+var_88]; this
0x18003f241  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003f246  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003f24d  lea     rcx, [rsp+1E8h+var_88]; pExceptionObject
0x18003f255  call    _CxxThrowException_0
0x18003f25b  mov     rsi, [rsp+1E8h+arg_0]
0x18003f263  mov     ebx, [rsp+1E8h+arg_10]
0x18003f26a  mov     r14, [rsp+1E8h+var_1A0]
0x18003f26f  mov     r12d, [rsp+1E8h+arg_18]
0x18003f277  test    ebx, ebx
0x18003f279  jns     short loc_18003F291
0x18003f27b  mov     rax, [rsi+40h]
0x18003f27f  mov     rcx, [rax]
0x18003f282  mov     r8b, 1; bool
0x18003f285  mov     edx, r12d; unsigned int
0x18003f288  mov     rcx, [rcx+40h]; this
0x18003f28c  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x18003f291  mov     rcx, r14; this
0x18003f294  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003f299  nop
0x18003f29a  lea     rcx, [rsp+1E8h+var_198]; this
0x18003f29f  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003f2a4  mov     eax, ebx
0x18003f2a6  mov     rbx, [rsp+1E8h+arg_8]
0x18003f2ae  add     rsp, 1C0h
0x18003f2b5  pop     r15
0x18003f2b7  pop     r14
0x18003f2b9  pop     r13
0x18003f2bb  pop     r12
0x18003f2bd  pop     rsi
0x18003f2be  retn
```
