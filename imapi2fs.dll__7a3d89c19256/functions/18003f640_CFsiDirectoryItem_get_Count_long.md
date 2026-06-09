# CFsiDirectoryItem::get_Count(long *)

- ea: `0x18003f640`
- end: `0x18003f787`
- name: `?get_Count@CFsiDirectoryItem@@UEAAJPEAJ@Z`
- size: `327`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, int *)`
- caller_count: `0`
- callee_count: `12`
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
- `0x18003f640`

## string_xrefs

- `0x18003f658`: `CFsiDirectoryItem::get_Count`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiDirectoryItem::get_Count(CFsiDirectoryItem *this, int *a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CFsiDirectoryItem::get_Count");
  ImapiClearErrorInfo();
  v10 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
  if ( !a2 )
  {
    try
    {
      v4 = (CIMAPIException *)operator new(0x58u);
      v9 = (CIMAPIException **)v4;
      if ( v4 )
        v4 = CIMAPIException::CIMAPIException(v4, -2147467261, L"Count");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v9, v4);
      v5 = v9;
      if ( v9 && *v9 )
      {
        CIMAPIException::SetCodeRefInfo(*v9, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 43);
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
    catch ( ... )
    {
      ExceptionDispatcher(&CLSID_FsiDirectoryItem);
    }
  }
  *a2 = 0;
  *a2 = *(_DWORD *)(**((_QWORD **)this + 8) + 296LL) + *(_DWORD *)(**((_QWORD **)this + 8) + 248LL);
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x18003f640  mov     rax, rsp
0x18003f643  mov     [rax+20h], rbx
0x18003f647  push    rsi
0x18003f648  push    rdi
0x18003f649  push    r14
0x18003f64b  sub     rsp, 80h
0x18003f652  mov     rsi, rdx
0x18003f655  mov     r14, rcx
0x18003f658  lea     rdx, aCfsidirectoryi_15; "CFsiDirectoryItem::get_Count"
0x18003f65f  lea     rcx, [rax+18h]; this
0x18003f663  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003f668  nop
0x18003f669  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003f66e  nop
0x18003f66f  lea     rbx, [r14-50h]
0x18003f673  mov     [rsp+98h+arg_8], rbx
0x18003f67b  mov     rcx, rbx; this
0x18003f67e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003f683  test    rsi, rsi
0x18003f686  jz      short loc_18003F6A6
0x18003f688  xor     edi, edi
0x18003f68a  mov     [rsi], edi
0x18003f68c  mov     rax, [r14+40h]
0x18003f690  mov     rcx, [rax]
0x18003f693  mov     eax, [rcx+0F8h]
0x18003f699  add     eax, [rcx+128h]
0x18003f69f  mov     [rsi], eax
0x18003f6a1  jmp     loc_18003F75B
0x18003f6a6  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003f6ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f6b0  mov     [rsp+98h+arg_0], rax
0x18003f6b8  test    rax, rax
0x18003f6bb  jz      short loc_18003F6D2
0x18003f6bd  lea     r8, aCount; "Count"
0x18003f6c4  mov     edx, 80004003h; int
0x18003f6c9  mov     rcx, rax; this
0x18003f6cc  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003f6d1  nop
0x18003f6d2  mov     rdx, rax
0x18003f6d5  lea     rcx, [rsp+98h+arg_0]
0x18003f6dd  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003f6e2  nop
0x18003f6e3  mov     rbx, [rsp+98h+arg_0]
0x18003f6eb  test    rbx, rbx
0x18003f6ee  jz      short loc_18003F729
0x18003f6f0  cmp     qword ptr [rbx], 0
0x18003f6f4  jz      short loc_18003F729
0x18003f6f6  mov     r8d, 2Bh ; '+'; int
0x18003f6fc  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003f703  mov     rcx, [rbx]; this
0x18003f706  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003f70b  mov     [rsp+98h+pExceptionObject], rbx
0x18003f710  test    rbx, rbx
0x18003f713  jz      short loc_18003F718
0x18003f715  inc     dword ptr [rbx+8]
0x18003f718  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003f71f  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18003f724  call    _CxxThrowException_0
0x18003f729  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003f730  lea     rcx, [rsp+98h+var_70]; this
0x18003f735  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003f73a  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003f741  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x18003f746  call    _CxxThrowException_0
0x18003f74c  mov     edi, dword ptr [rsp+98h+arg_0]
0x18003f753  mov     rbx, [rsp+98h+arg_8]
0x18003f75b  mov     rcx, rbx; this
0x18003f75e  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003f763  nop
0x18003f764  lea     rcx, [rsp+98h+arg_10]; this
0x18003f76c  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003f771  mov     eax, edi
0x18003f773  mov     rbx, [rsp+98h+arg_18]
0x18003f77b  add     rsp, 80h
0x18003f782  pop     r14
0x18003f784  pop     rdi
0x18003f785  pop     rsi
0x18003f786  retn
```
