# CFsiDirectoryItem::get_CreationTime(double *)

- ea: `0x18003f8e0`
- end: `0x18003fa24`
- name: `?get_CreationTime@CFsiDirectoryItem@@UEAAJPEAN@Z`
- size: `324`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, double *)`
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
- `0x18003f8e0`

## string_xrefs

- `0x18003f8f8`: `CFsiDirectoryItem::get_CreationTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiDirectoryItem::get_CreationTime(CFsiDirectoryItem *this, double *a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CFsiDirectoryItem::get_CreationTime");
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
        v4 = CIMAPIException::CIMAPIException(v4, -2147467261, L"pVal");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v9, v4);
      v5 = v9;
      if ( v9 && *v9 )
      {
        CIMAPIException::SetCodeRefInfo(*v9, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 150);
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
  *a2 = 0.0;
  *a2 = *(double *)(**((_QWORD **)this + 8) + 184LL);
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x18003f8e0  mov     rax, rsp
0x18003f8e3  mov     [rax+20h], rbx
0x18003f8e7  push    rsi
0x18003f8e8  push    rdi
0x18003f8e9  push    r14
0x18003f8eb  sub     rsp, 80h
0x18003f8f2  mov     rsi, rdx
0x18003f8f5  mov     r14, rcx
0x18003f8f8  lea     rdx, aCfsidirectoryi_9; "CFsiDirectoryItem::get_CreationTime"
0x18003f8ff  lea     rcx, [rax+18h]; this
0x18003f903  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003f908  nop
0x18003f909  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003f90e  nop
0x18003f90f  lea     rbx, [r14-50h]
0x18003f913  mov     [rsp+98h+arg_8], rbx
0x18003f91b  mov     rcx, rbx; this
0x18003f91e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003f923  test    rsi, rsi
0x18003f926  jz      short loc_18003F943
0x18003f928  xor     edi, edi
0x18003f92a  mov     [rsi], rdi
0x18003f92d  mov     rax, [r14+40h]
0x18003f931  mov     rcx, [rax]
0x18003f934  mov     rax, [rcx+0B8h]
0x18003f93b  mov     [rsi], rax
0x18003f93e  jmp     loc_18003F9F8
0x18003f943  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003f948  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f94d  mov     [rsp+98h+arg_0], rax
0x18003f955  test    rax, rax
0x18003f958  jz      short loc_18003F96F
0x18003f95a  lea     r8, aPval; "pVal"
0x18003f961  mov     edx, 80004003h; int
0x18003f966  mov     rcx, rax; this
0x18003f969  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003f96e  nop
0x18003f96f  mov     rdx, rax
0x18003f972  lea     rcx, [rsp+98h+arg_0]
0x18003f97a  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003f97f  nop
0x18003f980  mov     rbx, [rsp+98h+arg_0]
0x18003f988  test    rbx, rbx
0x18003f98b  jz      short loc_18003F9C6
0x18003f98d  cmp     qword ptr [rbx], 0
0x18003f991  jz      short loc_18003F9C6
0x18003f993  mov     r8d, 96h; int
0x18003f999  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003f9a0  mov     rcx, [rbx]; this
0x18003f9a3  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003f9a8  mov     [rsp+98h+pExceptionObject], rbx
0x18003f9ad  test    rbx, rbx
0x18003f9b0  jz      short loc_18003F9B5
0x18003f9b2  inc     dword ptr [rbx+8]
0x18003f9b5  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003f9bc  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18003f9c1  call    _CxxThrowException_0
0x18003f9c6  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003f9cd  lea     rcx, [rsp+98h+var_70]; this
0x18003f9d2  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003f9d7  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003f9de  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x18003f9e3  call    _CxxThrowException_0
0x18003f9e9  mov     edi, dword ptr [rsp+98h+arg_0]
0x18003f9f0  mov     rbx, [rsp+98h+arg_8]
0x18003f9f8  mov     rcx, rbx; this
0x18003f9fb  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003fa00  nop
0x18003fa01  lea     rcx, [rsp+98h+arg_10]; this
0x18003fa09  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003fa0e  mov     eax, edi
0x18003fa10  mov     rbx, [rsp+98h+arg_18]
0x18003fa18  add     rsp, 80h
0x18003fa1f  pop     r14
0x18003fa21  pop     rdi
0x18003fa22  pop     rsi
0x18003fa23  retn
```
