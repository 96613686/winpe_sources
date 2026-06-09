# CFsiDirectoryItem::get_Name(ushort * *)

- ea: `0x180040f60`
- end: `0x1800410a6`
- name: `?get_Name@CFsiDirectoryItem@@UEAAJPEAPEAG@Z`
- size: `326`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, unsigned __int16 **)`
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
- `0x18003d73c`
- `0x180040f60`

## string_xrefs

- `0x180040f78`: `CFsiDirectoryItem::get_Name`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiDirectoryItem::get_Name(CFsiDirectoryItem *this, unsigned __int16 **a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CFsiDirectoryItem::get_Name");
  ImapiClearErrorInfo();
  v10 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
  try
  {
    if ( !a2 )
    {
      v4 = (CIMAPIException *)operator new(0x58u);
      v9 = (CIMAPIException **)v4;
      if ( v4 )
        v4 = CIMAPIException::CIMAPIException(v4, -2147467261, L"pVal");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v9, v4);
      v5 = v9;
      if ( v9 && *v9 )
      {
        CIMAPIException::SetCodeRefInfo(*v9, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 122);
        pExceptionObject = v5;
        if ( v5 )
          ++*((_DWORD *)v5 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v8,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v8;
    }
    *a2 = 0;
    *a2 = (unsigned __int16 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(**((_QWORD **)this + 8) + 88LL);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x180040f60  mov     rax, rsp
0x180040f63  mov     [rax+20h], rbx
0x180040f67  push    rsi
0x180040f68  push    rdi
0x180040f69  push    r14
0x180040f6b  sub     rsp, 80h
0x180040f72  mov     rdi, rdx
0x180040f75  mov     r14, rcx
0x180040f78  lea     rdx, aCfsidirectoryi_11; "CFsiDirectoryItem::get_Name"
0x180040f7f  lea     rcx, [rax+18h]; this
0x180040f83  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180040f88  nop
0x180040f89  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180040f8e  nop
0x180040f8f  lea     rbx, [r14-50h]
0x180040f93  mov     [rsp+98h+arg_8], rbx
0x180040f9b  mov     rcx, rbx; this
0x180040f9e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180040fa3  test    rdi, rdi
0x180040fa6  jz      short loc_180040FC5
0x180040fa8  xor     esi, esi
0x180040faa  mov     [rdi], rsi
0x180040fad  mov     rax, [r14+40h]
0x180040fb1  mov     rcx, [rax]
0x180040fb4  add     rcx, 58h ; 'X'
0x180040fb8  call    ?AllocSysString@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAGXZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AllocSysString(void)
0x180040fbd  mov     [rdi], rax
0x180040fc0  jmp     loc_18004107A
0x180040fc5  mov     ecx, 58h ; 'X'; unsigned __int64
0x180040fca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040fcf  mov     [rsp+98h+arg_0], rax
0x180040fd7  test    rax, rax
0x180040fda  jz      short loc_180040FF1
0x180040fdc  lea     r8, aPval; "pVal"
0x180040fe3  mov     edx, 80004003h; int
0x180040fe8  mov     rcx, rax; this
0x180040feb  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180040ff0  nop
0x180040ff1  mov     rdx, rax
0x180040ff4  lea     rcx, [rsp+98h+arg_0]
0x180040ffc  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180041001  nop
0x180041002  mov     rbx, [rsp+98h+arg_0]
0x18004100a  test    rbx, rbx
0x18004100d  jz      short loc_180041048
0x18004100f  cmp     qword ptr [rbx], 0
0x180041013  jz      short loc_180041048
0x180041015  mov     r8d, 7Ah ; 'z'; int
0x18004101b  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180041022  mov     rcx, [rbx]; this
0x180041025  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18004102a  mov     [rsp+98h+pExceptionObject], rbx
0x18004102f  test    rbx, rbx
0x180041032  jz      short loc_180041037
0x180041034  inc     dword ptr [rbx+8]
0x180041037  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18004103e  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180041043  call    _CxxThrowException_0
0x180041048  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18004104f  lea     rcx, [rsp+98h+var_70]; this
0x180041054  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180041059  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180041060  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180041065  call    _CxxThrowException_0
0x18004106b  mov     esi, dword ptr [rsp+98h+arg_0]
0x180041072  mov     rbx, [rsp+98h+arg_8]
0x18004107a  mov     rcx, rbx; this
0x18004107d  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180041082  nop
0x180041083  lea     rcx, [rsp+98h+arg_10]; this
0x18004108b  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180041090  mov     eax, esi
0x180041092  mov     rbx, [rsp+98h+arg_18]
0x18004109a  add     rsp, 80h
0x1800410a1  pop     r14
0x1800410a3  pop     rdi
0x1800410a4  pop     rsi
0x1800410a5  retn
```
