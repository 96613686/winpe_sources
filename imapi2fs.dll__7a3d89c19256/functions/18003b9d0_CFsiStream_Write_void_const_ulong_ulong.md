# CFsiStream::Write(void const *,ulong,ulong *)

- ea: `0x18003b9d0`
- end: `0x18003baf9`
- name: `?Write@CFsiStream@@UEAAJPEBXKPEAK@Z`
- size: `297`
- prototype: `void __noreturn(CFsiStream *__hidden this, const void *, unsigned int, unsigned int *)`
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
- `0x18003b9d0`
- `0x18005c164`

## string_xrefs

- `0x18003b9e6`: `CFsiStream::Write`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn CFsiStream::Write(CFsiStream *this, const void *a2, __int64 a3, unsigned int *a4)
{
  const void *v7; // rdx
  CStreamROBase *v8; // rcx
  unsigned int v9; // r8d
  CIMAPIException *v10; // rax
  CIMAPIException **v11; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v13[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v14; // [rsp+A0h] [rbp+8h] BYREF
  ImapiComObject *v15; // [rsp+A8h] [rbp+10h]
  char v16; // [rsp+B8h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v16, "CFsiStream::Write");
  ImapiClearErrorInfo();
  v15 = (CFsiStream *)((char *)this - 80);
  ImapiComObject::LockCS((CFsiStream *)((char *)this - 80));
  if ( a4 )
    *a4 = 0;
  try
  {
    if ( a2 )
      CStreamROBase::Write(v8, v7, v9, a4);
    v10 = (CIMAPIException *)operator new(0x58u);
    v14 = (CIMAPIException **)v10;
    if ( v10 )
      v10 = CIMAPIException::CIMAPIException(v10, -2147467261, L"pBuffer");
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v14, v10);
    v11 = v14;
    if ( v14 && *v14 )
    {
      CIMAPIException::SetCodeRefInfo(*v14, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsistream.cpp", 50);
      pExceptionObject = v11;
      if ( v11 )
        ++*((_DWORD *)v11 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v13, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v13;
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiStream);
  }
}

```

## disassembly

```asm
0x18003b9d0  mov     rax, rsp
0x18003b9d3  push    rbx
0x18003b9d4  push    rsi
0x18003b9d5  push    rdi
0x18003b9d6  sub     rsp, 80h
0x18003b9dd  mov     rbx, r9
0x18003b9e0  mov     rdi, rdx
0x18003b9e3  mov     rsi, rcx
0x18003b9e6  lea     rdx, aCfsistreamWrit; "CFsiStream::Write"
0x18003b9ed  lea     rcx, [rax+20h]; this
0x18003b9f1  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003b9f6  nop
0x18003b9f7  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003b9fc  nop
0x18003b9fd  lea     rcx, [rsi-50h]; this
0x18003ba01  mov     [rsp+98h+arg_8], rcx
0x18003ba09  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003ba0e  test    rbx, rbx
0x18003ba11  jz      short loc_18003BA19
0x18003ba13  mov     dword ptr [rbx], 0
0x18003ba19  test    rdi, rdi
0x18003ba1c  jz      short loc_18003BA26
0x18003ba1e  mov     r9, rbx; unsigned int *
0x18003ba21  call    ?Write@CStreamROBase@@QEAAXPEBXKPEAK@Z; CStreamROBase::Write(void const *,ulong,ulong *)
0x18003ba26  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003ba2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ba30  mov     [rsp+98h+arg_0], rax
0x18003ba38  test    rax, rax
0x18003ba3b  jz      short loc_18003BA52
0x18003ba3d  lea     r8, aPbuffer; "pBuffer"
0x18003ba44  mov     edx, 80004003h; int
0x18003ba49  mov     rcx, rax; this
0x18003ba4c  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003ba51  nop
0x18003ba52  mov     rdx, rax
0x18003ba55  lea     rcx, [rsp+98h+arg_0]
0x18003ba5d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003ba62  nop
0x18003ba63  mov     rbx, [rsp+98h+arg_0]
0x18003ba6b  test    rbx, rbx
0x18003ba6e  jz      short loc_18003BAA9
0x18003ba70  cmp     qword ptr [rbx], 0
0x18003ba74  jz      short loc_18003BAA9
0x18003ba76  mov     r8d, 32h ; '2'; int
0x18003ba7c  lea     rdx, aDriversStorage_4; "drivers\\storage\\imapi2\\filesystemima"...
0x18003ba83  mov     rcx, [rbx]; this
0x18003ba86  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003ba8b  mov     [rsp+98h+pExceptionObject], rbx
0x18003ba90  test    rbx, rbx
0x18003ba93  jz      short loc_18003BA98
0x18003ba95  inc     dword ptr [rbx+8]
0x18003ba98  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003ba9f  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18003baa4  call    _CxxThrowException_0
0x18003baa9  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003bab0  lea     rcx, [rsp+98h+var_70]; this
0x18003bab5  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003baba  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003bac1  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x18003bac6  call    _CxxThrowException_0
0x18003bacc  mov     rcx, [rsp+98h+arg_8]; this
0x18003bad4  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003bad9  nop
0x18003bada  lea     rcx, [rsp+98h+arg_18]; this
0x18003bae2  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003bae7  mov     eax, dword ptr [rsp+98h+arg_0]
0x18003baee  add     rsp, 80h
0x18003baf5  pop     rdi
0x18003baf6  pop     rsi
0x18003baf7  pop     rbx
0x18003baf8  retn
```
