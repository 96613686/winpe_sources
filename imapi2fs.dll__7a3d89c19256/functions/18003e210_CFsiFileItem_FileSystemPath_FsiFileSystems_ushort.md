# CFsiFileItem::FileSystemPath(FsiFileSystems,ushort * *)

- ea: `0x18003e210`
- end: `0x18003e433`
- name: `?FileSystemPath@CFsiFileItem@@UEAAJW4FsiFileSystems@@PEAPEAG@Z`
- size: `547`
- prototype: `int(CFsiFileItem *__hidden this, enum FsiFileSystems, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

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
- `0x18003e210`
- `0x18004938c`

## string_xrefs

- `0x18003e22a`: `CFsiFileItem::FileSystemPath`

## pseudocode

```c
__int64 __fastcall CFsiFileItem::FileSystemPath(CFsiFileItem *this, enum FsiFileSystems a2, unsigned __int16 **a3)
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

  MethodTrace::MethodTrace((MethodTrace *)&v18, "CFsiFileItem::FileSystemPath");
  ImapiClearErrorInfo();
  v17 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiFileItem *)((char *)this - 80));
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
      CIMAPIException::SetCodeRefInfo(*v16, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 1157);
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
      CIMAPIException::SetCodeRefInfo(*v16, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 1160);
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
  ImapiComObject::UnlockCS((CFsiFileItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v18);
  return 0;
}

```

## disassembly

```asm
0x18003e210  mov     rax, rsp
0x18003e213  push    rbx
0x18003e214  push    rsi
0x18003e215  push    rdi
0x18003e216  push    r14
0x18003e218  push    r15
0x18003e21a  sub     rsp, 0E0h
0x18003e221  mov     rdi, r8
0x18003e224  mov     r15d, edx
0x18003e227  mov     r14, rcx
0x18003e22a  lea     rdx, aCfsifileitemFi; "CFsiFileItem::FileSystemPath"
0x18003e231  lea     rcx, [rax+20h]; this
0x18003e235  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003e23a  nop
0x18003e23b  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003e240  nop
0x18003e241  lea     rbx, [r14-50h]
0x18003e245  mov     [rsp+108h+arg_10], rbx
0x18003e24d  mov     rcx, rbx; this
0x18003e250  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003e255  test    rdi, rdi
0x18003e258  jz      loc_18003E351
0x18003e25e  mov     dl, 1; bool
0x18003e260  mov     ecx, r15d; enum FsiFileSystems
0x18003e263  call    ?ValidateFileSystemIdParam@@YA_NW4FsiFileSystems@@_N@Z; ValidateFileSystemIdParam(FsiFileSystems,bool)
0x18003e268  test    al, al
0x18003e26a  jnz     loc_18003E316
0x18003e270  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003e275  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e27a  mov     [rsp+108h+arg_0], rax
0x18003e282  test    rax, rax
0x18003e285  jz      short loc_18003E29C
0x18003e287  lea     r8, aFilesystem; "fileSystem"
0x18003e28e  mov     edx, 0C0AAB101h; int
0x18003e293  mov     rcx, rax; this
0x18003e296  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003e29b  nop
0x18003e29c  mov     rdx, rax
0x18003e29f  lea     rcx, [rsp+108h+arg_0]
0x18003e2a7  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003e2ac  nop
0x18003e2ad  mov     rbx, [rsp+108h+arg_0]
0x18003e2b5  test    rbx, rbx
0x18003e2b8  jz      short loc_18003E2F3
0x18003e2ba  cmp     qword ptr [rbx], 0
0x18003e2be  jz      short loc_18003E2F3
0x18003e2c0  mov     r8d, 488h; int
0x18003e2c6  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003e2cd  mov     rcx, [rbx]; this
0x18003e2d0  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003e2d5  mov     [rsp+108h+pExceptionObject], rbx
0x18003e2da  test    rbx, rbx
0x18003e2dd  jz      short loc_18003E2E2
0x18003e2df  inc     dword ptr [rbx+8]
0x18003e2e2  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003e2e9  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18003e2ee  call    _CxxThrowException_0
0x18003e2f3  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003e2fa  lea     rcx, [rsp+108h+var_D8]; this
0x18003e2ff  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003e304  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003e30b  lea     rcx, [rsp+108h+var_D8]; pExceptionObject
0x18003e310  call    _CxxThrowException_0
0x18003e316  xor     esi, esi
0x18003e318  mov     [rdi], rsi
0x18003e31b  mov     rcx, [r14+40h]
0x18003e31f  mov     r8d, r15d
0x18003e322  lea     rdx, [rsp+108h+arg_0]
0x18003e32a  mov     rcx, [rcx]
0x18003e32d  call    ?FullPathFsSpecific@ImapiFsObjectBase@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4FsiFileSystems@@@Z; ImapiFsObjectBase::FullPathFsSpecific(FsiFileSystems)
0x18003e332  nop
0x18003e333  mov     rcx, rax
0x18003e336  call    ?AllocSysString@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAGXZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AllocSysString(void)
0x18003e33b  mov     [rdi], rax
0x18003e33e  lea     rcx, [rsp+108h+arg_0]; void *
0x18003e346  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003e34b  nop
0x18003e34c  jmp     loc_18003E40C
0x18003e351  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003e356  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e35b  mov     [rsp+108h+arg_0], rax
0x18003e363  test    rax, rax
0x18003e366  jz      short loc_18003E37D
0x18003e368  lea     r8, aPval; "pVal"
0x18003e36f  mov     edx, 80004003h; int
0x18003e374  mov     rcx, rax; this
0x18003e377  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003e37c  nop
0x18003e37d  mov     rdx, rax
0x18003e380  lea     rcx, [rsp+108h+arg_0]
0x18003e388  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003e38d  nop
0x18003e38e  mov     rbx, [rsp+108h+arg_0]
0x18003e396  test    rbx, rbx
0x18003e399  jz      short loc_18003E3D4
0x18003e39b  cmp     qword ptr [rbx], 0
0x18003e39f  jz      short loc_18003E3D4
0x18003e3a1  mov     r8d, 485h; int
0x18003e3a7  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003e3ae  mov     rcx, [rbx]; this
0x18003e3b1  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003e3b6  mov     [rsp+108h+var_E0], rbx
0x18003e3bb  test    rbx, rbx
0x18003e3be  jz      short loc_18003E3C3
0x18003e3c0  inc     dword ptr [rbx+8]
0x18003e3c3  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003e3ca  lea     rcx, [rsp+108h+var_E0]; pExceptionObject
0x18003e3cf  call    _CxxThrowException_0
0x18003e3d4  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003e3db  lea     rcx, [rsp+108h+var_80]; this
0x18003e3e3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003e3e8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003e3ef  lea     rcx, [rsp+108h+var_80]; pExceptionObject
0x18003e3f7  call    _CxxThrowException_0
0x18003e3fd  mov     esi, dword ptr [rsp+108h+arg_0]
0x18003e404  mov     rbx, [rsp+108h+arg_10]
0x18003e40c  mov     rcx, rbx; this
0x18003e40f  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003e414  nop
0x18003e415  lea     rcx, [rsp+108h+arg_18]; this
0x18003e41d  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003e422  mov     eax, esi
0x18003e424  add     rsp, 0E0h
0x18003e42b  pop     r15
0x18003e42d  pop     r14
0x18003e42f  pop     rdi
0x18003e430  pop     rsi
0x18003e431  pop     rbx
0x18003e432  retn
```
