# CMsftFileSystemImage::get_MultisessionInterfaces(tagSAFEARRAY * *)

- ea: `0x180058e30`
- end: `0x18005902f`
- name: `?get_MultisessionInterfaces@CMsftFileSystemImage@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `511`
- prototype: `int(CMsftFileSystemImage *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180058e30`
- `0x180077640`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x180058e90`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180058e90`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMsftFileSystemImage::get_MultisessionInterfaces(
        CMsftFileSystemImage *this,
        struct tagSAFEARRAY **a2)
{
  struct tagSAFEARRAY **v4; // r9
  SAFEARRAY *v5; // rcx
  int VariantSafeArrayFromIDispatch; // ebx
  CIMAPIException *v7; // rax
  CIMAPIException **v8; // rbx
  CIMAPIException *v9; // rax
  CIMAPIException **v10; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-D8h] BYREF
  CIMAPIException **v13; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v14[88]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v15[112]; // [rsp+88h] [rbp-70h] BYREF
  CIMAPIException **v16; // [rsp+100h] [rbp+8h] BYREF
  char *v17; // [rsp+108h] [rbp+10h]
  char v18; // [rsp+110h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v18, "CMsftFileSystemImage::get_MultisessionInterfaces");
  ImapiClearErrorInfo();
  v17 = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
  try
  {
    if ( !a2 )
    {
      v9 = (CIMAPIException *)operator new(0x58u);
      v16 = (CIMAPIException **)v9;
      if ( v9 )
        v9 = CIMAPIException::CIMAPIException(v9, -2147467261, L"pVal");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v16, v9);
      v10 = v16;
      if ( v16 && *v16 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v16,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          900);
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
    v5 = *(SAFEARRAY **)(**((_QWORD **)this + 26) + 776LL);
    if ( v5 )
      VariantSafeArrayFromIDispatch = SafeArrayCopy(v5, a2);
    else
      VariantSafeArrayFromIDispatch = Imapi2Utility::CreateVariantSafeArrayFromIDispatch(0, 0, a2, v4);
    if ( VariantSafeArrayFromIDispatch < 0 )
    {
      v7 = (CIMAPIException *)operator new(0x58u);
      v16 = (CIMAPIException **)v7;
      if ( v7 )
        v7 = CIMAPIException::CIMAPIException(v7, VariantSafeArrayFromIDispatch);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v16, v7);
      v8 = v16;
      if ( v16 && *v16 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v16,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          914);
        pExceptionObject = v8;
        if ( v8 )
          ++*((_DWORD *)v8 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v14,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v14;
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_MsftFileSystemImage);
  }
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v18);
  return (unsigned int)VariantSafeArrayFromIDispatch;
}

```

## disassembly

```asm
0x180058e30  mov     rax, rsp
0x180058e33  push    rbx
0x180058e34  push    rsi
0x180058e35  push    rdi
0x180058e36  sub     rsp, 0E0h
0x180058e3d  mov     rbx, rdx
0x180058e40  mov     rsi, rcx
0x180058e43  lea     rdx, aCmsftfilesyste_19; "CMsftFileSystemImage::get_MultisessionI"...
0x180058e4a  lea     rcx, [rax+18h]; this
0x180058e4e  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180058e53  nop
0x180058e54  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180058e59  nop
0x180058e5a  lea     rdi, [rsi+50h]
0x180058e5e  mov     [rsp+0F8h+arg_8], rdi
0x180058e66  mov     rcx, rdi; this
0x180058e69  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180058e6e  test    rbx, rbx
0x180058e71  jz      loc_180058F51
0x180058e77  mov     rax, [rsi+0D0h]
0x180058e7e  mov     rcx, [rax]
0x180058e81  mov     rcx, [rcx+308h]; psa
0x180058e88  test    rcx, rcx
0x180058e8b  jz      short loc_180058E9A
0x180058e8d  mov     rdx, rbx; ppsaOut
0x180058e90  call    cs:__imp_SafeArrayCopy
0x180058e96  mov     ebx, eax
0x180058e98  jmp     short loc_180058EA8
0x180058e9a  mov     r8, rbx; unsigned int
0x180058e9d  xor     edx, edx; struct IDispatch **
0x180058e9f  xor     ecx, ecx; this
0x180058ea1  call    ?CreateVariantSafeArrayFromIDispatch@Imapi2Utility@@YA?BJPEAPEAUIDispatch@@KPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromIDispatch(IDispatch * *,ulong,tagSAFEARRAY * *)
0x180058ea6  mov     ebx, eax
0x180058ea8  test    ebx, ebx
0x180058eaa  jns     loc_180058F4C
0x180058eb0  mov     ecx, 58h ; 'X'; unsigned __int64
0x180058eb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058eba  mov     [rsp+0F8h+arg_0], rax
0x180058ec2  test    rax, rax
0x180058ec5  jz      short loc_180058ED2
0x180058ec7  mov     edx, ebx; int
0x180058ec9  mov     rcx, rax; this
0x180058ecc  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180058ed1  nop
0x180058ed2  mov     rdx, rax
0x180058ed5  lea     rcx, [rsp+0F8h+arg_0]
0x180058edd  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180058ee2  nop
0x180058ee3  mov     rbx, [rsp+0F8h+arg_0]
0x180058eeb  test    rbx, rbx
0x180058eee  jz      short loc_180058F29
0x180058ef0  cmp     qword ptr [rbx], 0
0x180058ef4  jz      short loc_180058F29
0x180058ef6  mov     r8d, 392h; int
0x180058efc  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180058f03  mov     rcx, [rbx]; this
0x180058f06  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180058f0b  mov     [rsp+0F8h+pExceptionObject], rbx
0x180058f10  test    rbx, rbx
0x180058f13  jz      short loc_180058F18
0x180058f15  inc     dword ptr [rbx+8]
0x180058f18  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180058f1f  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180058f24  call    _CxxThrowException_0
0x180058f29  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180058f30  lea     rcx, [rsp+0F8h+var_C8]; this
0x180058f35  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180058f3a  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180058f41  lea     rcx, [rsp+0F8h+var_C8]; pExceptionObject
0x180058f46  call    _CxxThrowException_0
0x180058f4c  jmp     loc_18005900C
0x180058f51  mov     ecx, 58h ; 'X'; unsigned __int64
0x180058f56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058f5b  mov     [rsp+0F8h+arg_0], rax
0x180058f63  test    rax, rax
0x180058f66  jz      short loc_180058F7D
0x180058f68  lea     r8, aPval; "pVal"
0x180058f6f  mov     edx, 80004003h; int
0x180058f74  mov     rcx, rax; this
0x180058f77  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180058f7c  nop
0x180058f7d  mov     rdx, rax
0x180058f80  lea     rcx, [rsp+0F8h+arg_0]
0x180058f88  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180058f8d  nop
0x180058f8e  mov     rbx, [rsp+0F8h+arg_0]
0x180058f96  test    rbx, rbx
0x180058f99  jz      short loc_180058FD4
0x180058f9b  cmp     qword ptr [rbx], 0
0x180058f9f  jz      short loc_180058FD4
0x180058fa1  mov     r8d, 384h; int
0x180058fa7  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180058fae  mov     rcx, [rbx]; this
0x180058fb1  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180058fb6  mov     [rsp+0F8h+var_D0], rbx
0x180058fbb  test    rbx, rbx
0x180058fbe  jz      short loc_180058FC3
0x180058fc0  inc     dword ptr [rbx+8]
0x180058fc3  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180058fca  lea     rcx, [rsp+0F8h+var_D0]; pExceptionObject
0x180058fcf  call    _CxxThrowException_0
0x180058fd4  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180058fdb  lea     rcx, [rsp+0F8h+var_70]; this
0x180058fe3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180058fe8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180058fef  lea     rcx, [rsp+0F8h+var_70]; pExceptionObject
0x180058ff7  call    _CxxThrowException_0
0x180058ffd  mov     ebx, dword ptr [rsp+0F8h+arg_0]
0x180059004  mov     rdi, [rsp+0F8h+arg_8]
0x18005900c  mov     rcx, rdi; this
0x18005900f  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180059014  nop
0x180059015  lea     rcx, [rsp+0F8h+arg_10]; this
0x18005901d  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180059022  mov     eax, ebx
0x180059024  add     rsp, 0E0h
0x18005902b  pop     rdi
0x18005902c  pop     rsi
0x18005902d  pop     rbx
0x18005902e  retn
```
