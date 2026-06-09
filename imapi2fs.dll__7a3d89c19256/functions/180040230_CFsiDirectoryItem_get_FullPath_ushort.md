# CFsiDirectoryItem::get_FullPath(ushort * *)

- ea: `0x180040230`
- end: `0x18004037a`
- name: `?get_FullPath@CFsiDirectoryItem@@UEAAJPEAPEAG@Z`
- size: `330`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, unsigned __int16 **)`
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
- `0x180040230`

## string_xrefs

- `0x180040248`: `CFsiDirectoryItem::get_FullPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiDirectoryItem::get_FullPath(ImapiFsObjectBase ***this, unsigned __int16 **a2)
{
  ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException *v5; // rax
  CIMAPIException **v6; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v9[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v10; // [rsp+A0h] [rbp+8h] BYREF
  ImapiFsObjectBase ***v11; // [rsp+A8h] [rbp+10h]
  char v12; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v12, "CFsiDirectoryItem::get_FullPath");
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
        CIMAPIException::SetCodeRefInfo(*v10, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 136);
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
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  ImapiComObject::UnlockCS((ImapiComObject *)(this - 10));
  MethodTrace::~MethodTrace((MethodTrace *)&v12);
  return 0;
}

```

## disassembly

```asm
0x180040230  mov     rax, rsp
0x180040233  mov     [rax+20h], rbx
0x180040237  push    rsi
0x180040238  push    rdi
0x180040239  push    r14
0x18004023b  sub     rsp, 80h
0x180040242  mov     rdi, rdx
0x180040245  mov     r14, rcx
0x180040248  lea     rdx, aCfsidirectoryi_21; "CFsiDirectoryItem::get_FullPath"
0x18004024f  lea     rcx, [rax+18h]; this
0x180040253  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180040258  nop
0x180040259  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18004025e  nop
0x18004025f  lea     rbx, [r14-50h]
0x180040263  mov     [rsp+98h+arg_8], rbx
0x18004026b  mov     rcx, rbx; this
0x18004026e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180040273  test    rdi, rdi
0x180040276  jz      short loc_180040299
0x180040278  xor     esi, esi
0x18004027a  mov     [rdi], rsi
0x18004027d  mov     rcx, [r14+40h]
0x180040281  mov     rcx, [rcx]; this
0x180040284  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x180040289  mov     rcx, rax; this
0x18004028c  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180040291  mov     [rdi], rax
0x180040294  jmp     loc_18004034E
0x180040299  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004029e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800402a3  mov     [rsp+98h+arg_0], rax
0x1800402ab  test    rax, rax
0x1800402ae  jz      short loc_1800402C5
0x1800402b0  lea     r8, aPval; "pVal"
0x1800402b7  mov     edx, 80004003h; int
0x1800402bc  mov     rcx, rax; this
0x1800402bf  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800402c4  nop
0x1800402c5  mov     rdx, rax
0x1800402c8  lea     rcx, [rsp+98h+arg_0]
0x1800402d0  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800402d5  nop
0x1800402d6  mov     rbx, [rsp+98h+arg_0]
0x1800402de  test    rbx, rbx
0x1800402e1  jz      short loc_18004031C
0x1800402e3  cmp     qword ptr [rbx], 0
0x1800402e7  jz      short loc_18004031C
0x1800402e9  mov     r8d, 88h; int
0x1800402ef  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x1800402f6  mov     rcx, [rbx]; this
0x1800402f9  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800402fe  mov     [rsp+98h+pExceptionObject], rbx
0x180040303  test    rbx, rbx
0x180040306  jz      short loc_18004030B
0x180040308  inc     dword ptr [rbx+8]
0x18004030b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180040312  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180040317  call    _CxxThrowException_0
0x18004031c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180040323  lea     rcx, [rsp+98h+var_70]; this
0x180040328  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18004032d  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180040334  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180040339  call    _CxxThrowException_0
0x18004033f  mov     esi, dword ptr [rsp+98h+arg_0]
0x180040346  mov     rbx, [rsp+98h+arg_8]
0x18004034e  mov     rcx, rbx; this
0x180040351  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180040356  nop
0x180040357  lea     rcx, [rsp+98h+arg_10]; this
0x18004035f  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180040364  mov     eax, esi
0x180040366  mov     rbx, [rsp+98h+arg_18]
0x18004036e  add     rsp, 80h
0x180040375  pop     r14
0x180040377  pop     rdi
0x180040378  pop     rsi
0x180040379  retn
```
