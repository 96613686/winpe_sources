# CFsiFileItem::get_FullPath(ushort * *)

- ea: `0x180040380`
- end: `0x1800404ca`
- name: `?get_FullPath@CFsiFileItem@@UEAAJPEAPEAG@Z`
- size: `330`
- prototype: `__int64 __fastcall(CFsiFileItem *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

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
- `0x180023c08`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003d764`
- `0x180040380`

## string_xrefs

- `0x180040398`: `CFsiFileItem::get_FullPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiFileItem::get_FullPath(ImapiFsObjectBase ***this, unsigned __int16 **a2)
{
  ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException *v5; // rax
  CIMAPIException **v6; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v9[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v10; // [rsp+A0h] [rbp+8h] BYREF
  ImapiFsObjectBase ***v11; // [rsp+A8h] [rbp+10h]
  char v12; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v12, "CFsiFileItem::get_FullPath");
  ImapiClearErrorInfo();
  v11 = this - 10;
  ImapiComObject::LockCS((ImapiComObject *)(this - 10));
  try
  {
    if ( !a2 )
    {
      v5 = (CIMAPIException *)operator new(0x58u);
      v10 = (CIMAPIException **)v5;
      if ( v5 )
        v5 = CIMAPIException::CIMAPIException(v5, -2147467261, L"pVal");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v10, v5);
      v6 = v10;
      if ( v10 && *v10 )
      {
        CIMAPIException::SetCodeRefInfo(*v10, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 980);
        pExceptionObject = v6;
        if ( v6 )
          ++*((_DWORD *)v6 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v9,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v9;
    }
    *a2 = 0;
    FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(*this[8]);
    *a2 = ATL::CComBSTR::Copy(FullPathOriginal);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiFileItem);
  }
  ImapiComObject::UnlockCS((ImapiComObject *)(this - 10));
  MethodTrace::~MethodTrace((MethodTrace *)&v12);
  return 0;
}

```

## disassembly

```asm
0x180040380  mov     rax, rsp
0x180040383  mov     [rax+20h], rbx
0x180040387  push    rsi
0x180040388  push    rdi
0x180040389  push    r14
0x18004038b  sub     rsp, 80h
0x180040392  mov     rdi, rdx
0x180040395  mov     r14, rcx
0x180040398  lea     rdx, aCfsifileitemGe; "CFsiFileItem::get_FullPath"
0x18004039f  lea     rcx, [rax+18h]; this
0x1800403a3  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x1800403a8  nop
0x1800403a9  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x1800403ae  nop
0x1800403af  lea     rbx, [r14-50h]
0x1800403b3  mov     [rsp+98h+arg_8], rbx
0x1800403bb  mov     rcx, rbx; this
0x1800403be  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x1800403c3  test    rdi, rdi
0x1800403c6  jz      short loc_1800403E9
0x1800403c8  xor     esi, esi
0x1800403ca  mov     [rdi], rsi
0x1800403cd  mov     rcx, [r14+40h]
0x1800403d1  mov     rcx, [rcx]; this
0x1800403d4  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x1800403d9  mov     rcx, rax; this
0x1800403dc  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x1800403e1  mov     [rdi], rax
0x1800403e4  jmp     loc_18004049E
0x1800403e9  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800403ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800403f3  mov     [rsp+98h+arg_0], rax
0x1800403fb  test    rax, rax
0x1800403fe  jz      short loc_180040415
0x180040400  lea     r8, aPval; "pVal"
0x180040407  mov     edx, 80004003h; int
0x18004040c  mov     rcx, rax; this
0x18004040f  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180040414  nop
0x180040415  mov     rdx, rax
0x180040418  lea     rcx, [rsp+98h+arg_0]
0x180040420  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180040425  nop
0x180040426  mov     rbx, [rsp+98h+arg_0]
0x18004042e  test    rbx, rbx
0x180040431  jz      short loc_18004046C
0x180040433  cmp     qword ptr [rbx], 0
0x180040437  jz      short loc_18004046C
0x180040439  mov     r8d, 3D4h; int
0x18004043f  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180040446  mov     rcx, [rbx]; this
0x180040449  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18004044e  mov     [rsp+98h+pExceptionObject], rbx
0x180040453  test    rbx, rbx
0x180040456  jz      short loc_18004045B
0x180040458  inc     dword ptr [rbx+8]
0x18004045b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180040462  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180040467  call    _CxxThrowException_0
0x18004046c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180040473  lea     rcx, [rsp+98h+var_70]; this
0x180040478  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18004047d  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180040484  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180040489  call    _CxxThrowException_0
0x18004048f  mov     esi, dword ptr [rsp+98h+arg_0]
0x180040496  mov     rbx, [rsp+98h+arg_8]
0x18004049e  mov     rcx, rbx; this
0x1800404a1  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x1800404a6  nop
0x1800404a7  lea     rcx, [rsp+98h+arg_10]; this
0x1800404af  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x1800404b4  mov     eax, esi
0x1800404b6  mov     rbx, [rsp+98h+arg_18]
0x1800404be  add     rsp, 80h
0x1800404c5  pop     r14
0x1800404c7  pop     rdi
0x1800404c8  pop     rsi
0x1800404c9  retn
```
