# CFsiDirectoryItem::FileSystemPath(FsiFileSystems,ushort * *)

- ea: `0x18003dfe0`
- end: `0x18003e203`
- name: `?FileSystemPath@CFsiDirectoryItem@@UEAAJW4FsiFileSystems@@PEAPEAG@Z`
- size: `547`
- prototype: `int(CFsiDirectoryItem *__hidden this, enum FsiFileSystems, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x18000d024`
- `0x18000d1c0`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003d73c`
- `0x18003dfe0`
- `0x18004938c`

## string_xrefs

- `0x18003dffa`: `CFsiDirectoryItem::FileSystemPath`

## pseudocode

```c
__int64 __fastcall CFsiDirectoryItem::FileSystemPath(
        CFsiDirectoryItem *this,
        enum FsiFileSystems a2,
        unsigned __int16 **a3)
{
  CIMAPIException *v6; // rax
  CIMAPIException **v7; // rbx
  __int64 v8; // rax
  CIMAPIException *v9; // rax
  CIMAPIException **v10; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-E8h] BYREF
  CIMAPIException **v13; // [rsp+28h] [rbp-E0h] BYREF
  _BYTE v14[88]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v15[128]; // [rsp+88h] [rbp-80h] BYREF
  CIMAPIException **v16; // [rsp+110h] [rbp+8h] BYREF
  char *v17; // [rsp+120h] [rbp+18h]
  char v18; // [rsp+128h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v18, "CFsiDirectoryItem::FileSystemPath");
  ImapiClearErrorInfo();
  v17 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
  if ( !a3 )
  {
    v9 = (CIMAPIException *)operator new(0x58u);
    v16 = (CIMAPIException **)v9;
    if ( v9 )
      v9 = CIMAPIException::CIMAPIException(v9, -2147467261, L"pVal");
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v16, v9);
    v10 = v16;
    if ( v16 && *v16 )
    {
      CIMAPIException::SetCodeRefInfo(*v16, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 313);
      v13 = v10;
      if ( v10 )
        ++*((_DWORD *)v10 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v13;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v15, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v15;
  }
  if ( !ValidateFileSystemIdParam(a2, 1) )
  {
    v6 = (CIMAPIException *)operator new(0x58u);
    v16 = (CIMAPIException **)v6;
    if ( v6 )
      v6 = CIMAPIException::CIMAPIException(v6, -1062555391, L"fileSystem");
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v16, v6);
    v7 = v16;
    if ( v16 && *v16 )
    {
      CIMAPIException::SetCodeRefInfo(*v16, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 316);
      pExceptionObject = v7;
      if ( v7 )
        ++*((_DWORD *)v7 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v14, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v14;
  }
  *a3 = 0;
  v8 = ImapiFsObjectBase::FullPathFsSpecific(**((_QWORD **)this + 8), &v16, (unsigned int)a2);
  *a3 = (unsigned __int16 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(v8);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v16);
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v18);
  return 0;
}

```

## disassembly

```asm
0x18003dfe0  mov     rax, rsp
0x18003dfe3  push    rbx
0x18003dfe4  push    rsi
0x18003dfe5  push    rdi
0x18003dfe6  push    r14
0x18003dfe8  push    r15
0x18003dfea  sub     rsp, 0E0h
0x18003dff1  mov     rdi, r8
0x18003dff4  mov     r15d, edx
0x18003dff7  mov     r14, rcx
0x18003dffa  lea     rdx, aCfsidirectoryi_5; "CFsiDirectoryItem::FileSystemPath"
0x18003e001  lea     rcx, [rax+20h]; this
0x18003e005  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003e00a  nop
0x18003e00b  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003e010  nop
0x18003e011  lea     rbx, [r14-50h]
0x18003e015  mov     [rsp+108h+arg_10], rbx
0x18003e01d  mov     rcx, rbx; this
0x18003e020  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003e025  test    rdi, rdi
0x18003e028  jz      loc_18003E121
0x18003e02e  mov     dl, 1; bool
0x18003e030  mov     ecx, r15d; enum FsiFileSystems
0x18003e033  call    ?ValidateFileSystemIdParam@@YA_NW4FsiFileSystems@@_N@Z; ValidateFileSystemIdParam(FsiFileSystems,bool)
0x18003e038  test    al, al
0x18003e03a  jnz     loc_18003E0E6
0x18003e040  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003e045  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e04a  mov     [rsp+108h+arg_0], rax
0x18003e052  test    rax, rax
0x18003e055  jz      short loc_18003E06C
0x18003e057  lea     r8, aFilesystem; "fileSystem"
0x18003e05e  mov     edx, 0C0AAB101h; int
0x18003e063  mov     rcx, rax; this
0x18003e066  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003e06b  nop
0x18003e06c  mov     rdx, rax
0x18003e06f  lea     rcx, [rsp+108h+arg_0]
0x18003e077  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003e07c  nop
0x18003e07d  mov     rbx, [rsp+108h+arg_0]
0x18003e085  test    rbx, rbx
0x18003e088  jz      short loc_18003E0C3
0x18003e08a  cmp     qword ptr [rbx], 0
0x18003e08e  jz      short loc_18003E0C3
0x18003e090  mov     r8d, 13Ch; int
0x18003e096  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003e09d  mov     rcx, [rbx]; this
0x18003e0a0  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003e0a5  mov     [rsp+108h+pExceptionObject], rbx
0x18003e0aa  test    rbx, rbx
0x18003e0ad  jz      short loc_18003E0B2
0x18003e0af  inc     dword ptr [rbx+8]
0x18003e0b2  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003e0b9  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18003e0be  call    _CxxThrowException_0
0x18003e0c3  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003e0ca  lea     rcx, [rsp+108h+var_D8]; this
0x18003e0cf  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003e0d4  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003e0db  lea     rcx, [rsp+108h+var_D8]; pExceptionObject
0x18003e0e0  call    _CxxThrowException_0
0x18003e0e6  xor     esi, esi
0x18003e0e8  mov     [rdi], rsi
0x18003e0eb  mov     rcx, [r14+40h]
0x18003e0ef  mov     r8d, r15d
0x18003e0f2  lea     rdx, [rsp+108h+arg_0]
0x18003e0fa  mov     rcx, [rcx]
0x18003e0fd  call    ?FullPathFsSpecific@ImapiFsObjectBase@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4FsiFileSystems@@@Z; ImapiFsObjectBase::FullPathFsSpecific(FsiFileSystems)
0x18003e102  nop
0x18003e103  mov     rcx, rax
0x18003e106  call    ?AllocSysString@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAGXZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AllocSysString(void)
0x18003e10b  mov     [rdi], rax
0x18003e10e  lea     rcx, [rsp+108h+arg_0]; void *
0x18003e116  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003e11b  nop
0x18003e11c  jmp     loc_18003E1DC
0x18003e121  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003e126  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e12b  mov     [rsp+108h+arg_0], rax
0x18003e133  test    rax, rax
0x18003e136  jz      short loc_18003E14D
0x18003e138  lea     r8, aPval; "pVal"
0x18003e13f  mov     edx, 80004003h; int
0x18003e144  mov     rcx, rax; this
0x18003e147  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003e14c  nop
0x18003e14d  mov     rdx, rax
0x18003e150  lea     rcx, [rsp+108h+arg_0]
0x18003e158  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003e15d  nop
0x18003e15e  mov     rbx, [rsp+108h+arg_0]
0x18003e166  test    rbx, rbx
0x18003e169  jz      short loc_18003E1A4
0x18003e16b  cmp     qword ptr [rbx], 0
0x18003e16f  jz      short loc_18003E1A4
0x18003e171  mov     r8d, 139h; int
0x18003e177  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003e17e  mov     rcx, [rbx]; this
0x18003e181  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003e186  mov     [rsp+108h+var_E0], rbx
0x18003e18b  test    rbx, rbx
0x18003e18e  jz      short loc_18003E193
0x18003e190  inc     dword ptr [rbx+8]
0x18003e193  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003e19a  lea     rcx, [rsp+108h+var_E0]; pExceptionObject
0x18003e19f  call    _CxxThrowException_0
0x18003e1a4  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003e1ab  lea     rcx, [rsp+108h+var_80]; this
0x18003e1b3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003e1b8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003e1bf  lea     rcx, [rsp+108h+var_80]; pExceptionObject
0x18003e1c7  call    _CxxThrowException_0
0x18003e1cd  mov     esi, dword ptr [rsp+108h+arg_0]
0x18003e1d4  mov     rbx, [rsp+108h+arg_10]
0x18003e1dc  mov     rcx, rbx; this
0x18003e1df  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003e1e4  nop
0x18003e1e5  lea     rcx, [rsp+108h+arg_18]; this
0x18003e1ed  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003e1f2  mov     eax, esi
0x18003e1f4  add     rsp, 0E0h
0x18003e1fb  pop     r15
0x18003e1fd  pop     r14
0x18003e1ff  pop     rdi
0x18003e200  pop     rsi
0x18003e201  pop     rbx
0x18003e202  retn
```
