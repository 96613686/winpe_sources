# CMsftFileSystemImage::get_StrictFileSystemCompliance(short *)

- ea: `0x1800592e0`
- end: `0x180059425`
- name: `?get_StrictFileSystemCompliance@CMsftFileSystemImage@@UEAAJPEAF@Z`
- size: `325`
- prototype: `__int64 __fastcall(CMsftFileSystemImage *__hidden this, __int16 *)`
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
- `0x1800592e0`

## string_xrefs

- `0x1800592f8`: `CMsftFileSystemImage::get_StrictFileSystemCompliance`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMsftFileSystemImage::get_StrictFileSystemCompliance(CMsftFileSystemImage *this, __int16 *a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CMsftFileSystemImage::get_StrictFileSystemCompliance");
  ImapiClearErrorInfo();
  v10 = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
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
        CIMAPIException::SetCodeRefInfo(
          *v9,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          308);
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
      ExceptionDispatcher(&CLSID_MsftFileSystemImage);
    }
  }
  *a2 = -(*(_BYTE *)(**((_QWORD **)this + 26) + 16LL) != 0);
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x1800592e0  mov     rax, rsp
0x1800592e3  mov     [rax+20h], rbx
0x1800592e7  push    rsi
0x1800592e8  push    rdi
0x1800592e9  push    r14
0x1800592eb  sub     rsp, 80h
0x1800592f2  mov     rsi, rdx
0x1800592f5  mov     r14, rcx
0x1800592f8  lea     rdx, aCmsftfilesyste_20; "CMsftFileSystemImage::get_StrictFileSys"...
0x1800592ff  lea     rcx, [rax+18h]; this
0x180059303  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180059308  nop
0x180059309  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18005930e  nop
0x18005930f  lea     rbx, [r14+50h]
0x180059313  mov     [rsp+98h+arg_8], rbx
0x18005931b  mov     rcx, rbx; this
0x18005931e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180059323  test    rsi, rsi
0x180059326  jz      short loc_180059344
0x180059328  xor     edi, edi
0x18005932a  mov     rax, [r14+0D0h]
0x180059331  mov     rcx, [rax]
0x180059334  mov     al, [rcx+10h]
0x180059337  neg     al
0x180059339  sbb     cx, cx
0x18005933c  mov     [rsi], cx
0x18005933f  jmp     loc_1800593F9
0x180059344  mov     ecx, 58h ; 'X'; unsigned __int64
0x180059349  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005934e  mov     [rsp+98h+arg_0], rax
0x180059356  test    rax, rax
0x180059359  jz      short loc_180059370
0x18005935b  lea     r8, aPval; "pVal"
0x180059362  mov     edx, 80004003h; int
0x180059367  mov     rcx, rax; this
0x18005936a  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18005936f  nop
0x180059370  mov     rdx, rax
0x180059373  lea     rcx, [rsp+98h+arg_0]
0x18005937b  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180059380  nop
0x180059381  mov     rbx, [rsp+98h+arg_0]
0x180059389  test    rbx, rbx
0x18005938c  jz      short loc_1800593C7
0x18005938e  cmp     qword ptr [rbx], 0
0x180059392  jz      short loc_1800593C7
0x180059394  mov     r8d, 134h; int
0x18005939a  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x1800593a1  mov     rcx, [rbx]; this
0x1800593a4  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800593a9  mov     [rsp+98h+pExceptionObject], rbx
0x1800593ae  test    rbx, rbx
0x1800593b1  jz      short loc_1800593B6
0x1800593b3  inc     dword ptr [rbx+8]
0x1800593b6  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800593bd  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800593c2  call    _CxxThrowException_0
0x1800593c7  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800593ce  lea     rcx, [rsp+98h+var_70]; this
0x1800593d3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800593d8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800593df  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x1800593e4  call    _CxxThrowException_0
0x1800593ea  mov     edi, dword ptr [rsp+98h+arg_0]
0x1800593f1  mov     rbx, [rsp+98h+arg_8]
0x1800593f9  mov     rcx, rbx; this
0x1800593fc  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180059401  nop
0x180059402  lea     rcx, [rsp+98h+arg_10]; this
0x18005940a  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18005940f  mov     eax, edi
0x180059411  mov     rbx, [rsp+98h+arg_18]
0x180059419  add     rsp, 80h
0x180059420  pop     r14
0x180059422  pop     rdi
0x180059423  pop     rsi
0x180059424  retn
```
