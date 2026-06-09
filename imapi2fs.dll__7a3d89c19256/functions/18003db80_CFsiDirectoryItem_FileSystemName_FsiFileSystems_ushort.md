# CFsiDirectoryItem::FileSystemName(FsiFileSystems,ushort * *)

- ea: `0x18003db80`
- end: `0x18003dda3`
- name: `?FileSystemName@CFsiDirectoryItem@@UEAAJW4FsiFileSystems@@PEAPEAG@Z`
- size: `547`
- prototype: `int(CFsiDirectoryItem *__hidden this, enum FsiFileSystems, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x18000d1c0`
- `0x18000ea78`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003d73c`
- `0x18003db80`
- `0x18004938c`

## string_xrefs

- `0x18003db9a`: `CFsiDirectoryItem::FileSystemName`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFsiDirectoryItem::FileSystemName(
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

  MethodTrace::MethodTrace((MethodTrace *)&v18, "CFsiDirectoryItem::FileSystemName");
  ImapiClearErrorInfo();
  v17 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
  try
  {
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
        CIMAPIException::SetCodeRefInfo(*v16, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 296);
        v13 = v10;
        if ( v10 )
          ++*((_DWORD *)v10 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v13;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v15,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
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
        CIMAPIException::SetCodeRefInfo(*v16, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 299);
        pExceptionObject = v7;
        if ( v7 )
          ++*((_DWORD *)v7 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v14,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v14;
    }
    *a3 = 0;
    v8 = ImapiFsObjectBase::NameFsSpecific(**((_QWORD **)this + 8), &v16, (unsigned int)a2);
    *a3 = (unsigned __int16 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(v8);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v16);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v18);
  return 0;
}

```

## disassembly

```asm
0x18003db80  mov     rax, rsp
0x18003db83  push    rbx
0x18003db84  push    rsi
0x18003db85  push    rdi
0x18003db86  push    r14
0x18003db88  push    r15
0x18003db8a  sub     rsp, 0E0h
0x18003db91  mov     rdi, r8
0x18003db94  mov     r15d, edx
0x18003db97  mov     r14, rcx
0x18003db9a  lea     rdx, aCfsidirectoryi_6; "CFsiDirectoryItem::FileSystemName"
0x18003dba1  lea     rcx, [rax+20h]; this
0x18003dba5  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003dbaa  nop
0x18003dbab  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003dbb0  nop
0x18003dbb1  lea     rbx, [r14-50h]
0x18003dbb5  mov     [rsp+108h+arg_10], rbx
0x18003dbbd  mov     rcx, rbx; this
0x18003dbc0  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003dbc5  test    rdi, rdi
0x18003dbc8  jz      loc_18003DCC1
0x18003dbce  mov     dl, 1; bool
0x18003dbd0  mov     ecx, r15d; enum FsiFileSystems
0x18003dbd3  call    ?ValidateFileSystemIdParam@@YA_NW4FsiFileSystems@@_N@Z; ValidateFileSystemIdParam(FsiFileSystems,bool)
0x18003dbd8  test    al, al
0x18003dbda  jnz     loc_18003DC86
0x18003dbe0  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003dbe5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dbea  mov     [rsp+108h+arg_0], rax
0x18003dbf2  test    rax, rax
0x18003dbf5  jz      short loc_18003DC0C
0x18003dbf7  lea     r8, aFilesystem; "fileSystem"
0x18003dbfe  mov     edx, 0C0AAB101h; int
0x18003dc03  mov     rcx, rax; this
0x18003dc06  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003dc0b  nop
0x18003dc0c  mov     rdx, rax
0x18003dc0f  lea     rcx, [rsp+108h+arg_0]
0x18003dc17  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003dc1c  nop
0x18003dc1d  mov     rbx, [rsp+108h+arg_0]
0x18003dc25  test    rbx, rbx
0x18003dc28  jz      short loc_18003DC63
0x18003dc2a  cmp     qword ptr [rbx], 0
0x18003dc2e  jz      short loc_18003DC63
0x18003dc30  mov     r8d, 12Bh; int
0x18003dc36  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003dc3d  mov     rcx, [rbx]; this
0x18003dc40  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003dc45  mov     [rsp+108h+pExceptionObject], rbx
0x18003dc4a  test    rbx, rbx
0x18003dc4d  jz      short loc_18003DC52
0x18003dc4f  inc     dword ptr [rbx+8]
0x18003dc52  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003dc59  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18003dc5e  call    _CxxThrowException_0
0x18003dc63  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003dc6a  lea     rcx, [rsp+108h+var_D8]; this
0x18003dc6f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003dc74  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003dc7b  lea     rcx, [rsp+108h+var_D8]; pExceptionObject
0x18003dc80  call    _CxxThrowException_0
0x18003dc86  xor     esi, esi
0x18003dc88  mov     [rdi], rsi
0x18003dc8b  mov     rcx, [r14+40h]
0x18003dc8f  mov     r8d, r15d
0x18003dc92  lea     rdx, [rsp+108h+arg_0]
0x18003dc9a  mov     rcx, [rcx]
0x18003dc9d  call    ?NameFsSpecific@ImapiFsObjectBase@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4FsiFileSystems@@@Z; ImapiFsObjectBase::NameFsSpecific(FsiFileSystems)
0x18003dca2  nop
0x18003dca3  mov     rcx, rax
0x18003dca6  call    ?AllocSysString@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAGXZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AllocSysString(void)
0x18003dcab  mov     [rdi], rax
0x18003dcae  lea     rcx, [rsp+108h+arg_0]; void *
0x18003dcb6  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003dcbb  nop
0x18003dcbc  jmp     loc_18003DD7C
0x18003dcc1  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003dcc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dccb  mov     [rsp+108h+arg_0], rax
0x18003dcd3  test    rax, rax
0x18003dcd6  jz      short loc_18003DCED
0x18003dcd8  lea     r8, aPval; "pVal"
0x18003dcdf  mov     edx, 80004003h; int
0x18003dce4  mov     rcx, rax; this
0x18003dce7  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003dcec  nop
0x18003dced  mov     rdx, rax
0x18003dcf0  lea     rcx, [rsp+108h+arg_0]
0x18003dcf8  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003dcfd  nop
0x18003dcfe  mov     rbx, [rsp+108h+arg_0]
0x18003dd06  test    rbx, rbx
0x18003dd09  jz      short loc_18003DD44
0x18003dd0b  cmp     qword ptr [rbx], 0
0x18003dd0f  jz      short loc_18003DD44
0x18003dd11  mov     r8d, 128h; int
0x18003dd17  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003dd1e  mov     rcx, [rbx]; this
0x18003dd21  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003dd26  mov     [rsp+108h+var_E0], rbx
0x18003dd2b  test    rbx, rbx
0x18003dd2e  jz      short loc_18003DD33
0x18003dd30  inc     dword ptr [rbx+8]
0x18003dd33  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003dd3a  lea     rcx, [rsp+108h+var_E0]; pExceptionObject
0x18003dd3f  call    _CxxThrowException_0
0x18003dd44  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003dd4b  lea     rcx, [rsp+108h+var_80]; this
0x18003dd53  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003dd58  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003dd5f  lea     rcx, [rsp+108h+var_80]; pExceptionObject
0x18003dd67  call    _CxxThrowException_0
0x18003dd6d  mov     esi, dword ptr [rsp+108h+arg_0]
0x18003dd74  mov     rbx, [rsp+108h+arg_10]
0x18003dd7c  mov     rcx, rbx; this
0x18003dd7f  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003dd84  nop
0x18003dd85  lea     rcx, [rsp+108h+arg_18]; this
0x18003dd8d  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003dd92  mov     eax, esi
0x18003dd94  add     rsp, 0E0h
0x18003dd9b  pop     r15
0x18003dd9d  pop     r14
0x18003dd9f  pop     rdi
0x18003dda0  pop     rsi
0x18003dda1  pop     rbx
0x18003dda2  retn
```
