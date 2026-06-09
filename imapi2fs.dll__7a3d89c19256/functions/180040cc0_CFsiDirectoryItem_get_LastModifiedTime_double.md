# CFsiDirectoryItem::get_LastModifiedTime(double *)

- ea: `0x180040cc0`
- end: `0x180040e04`
- name: `?get_LastModifiedTime@CFsiDirectoryItem@@UEAAJPEAN@Z`
- size: `324`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, double *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

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
- `0x180040cc0`

## string_xrefs

- `0x180040cd8`: `CFsiDirectoryItem::get_LastModifiedTime`

## pseudocode

```c
__int64 __fastcall CFsiDirectoryItem::get_LastModifiedTime(CFsiDirectoryItem *this, double *a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CFsiDirectoryItem::get_LastModifiedTime");
  ImapiClearErrorInfo();
  v10 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
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
      CIMAPIException::SetCodeRefInfo(*v9, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 224);
      pExceptionObject = v5;
      if ( v5 )
        ++*((_DWORD *)v5 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v8, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v8;
  }
  *a2 = 0.0;
  *a2 = *(double *)(**((_QWORD **)this + 8) + 216LL);
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x180040cc0  mov     rax, rsp
0x180040cc3  mov     [rax+20h], rbx
0x180040cc7  push    rsi
0x180040cc8  push    rdi
0x180040cc9  push    r14
0x180040ccb  sub     rsp, 80h
0x180040cd2  mov     rsi, rdx
0x180040cd5  mov     r14, rcx
0x180040cd8  lea     rdx, aCfsidirectoryi_19; "CFsiDirectoryItem::get_LastModifiedTime"
0x180040cdf  lea     rcx, [rax+18h]; this
0x180040ce3  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180040ce8  nop
0x180040ce9  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180040cee  nop
0x180040cef  lea     rbx, [r14-50h]
0x180040cf3  mov     [rsp+98h+arg_8], rbx
0x180040cfb  mov     rcx, rbx; this
0x180040cfe  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180040d03  test    rsi, rsi
0x180040d06  jz      short loc_180040D23
0x180040d08  xor     edi, edi
0x180040d0a  mov     [rsi], rdi
0x180040d0d  mov     rax, [r14+40h]
0x180040d11  mov     rcx, [rax]
0x180040d14  mov     rax, [rcx+0D8h]
0x180040d1b  mov     [rsi], rax
0x180040d1e  jmp     loc_180040DD8
0x180040d23  mov     ecx, 58h ; 'X'; unsigned __int64
0x180040d28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040d2d  mov     [rsp+98h+arg_0], rax
0x180040d35  test    rax, rax
0x180040d38  jz      short loc_180040D4F
0x180040d3a  lea     r8, aPval; "pVal"
0x180040d41  mov     edx, 80004003h; int
0x180040d46  mov     rcx, rax; this
0x180040d49  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180040d4e  nop
0x180040d4f  mov     rdx, rax
0x180040d52  lea     rcx, [rsp+98h+arg_0]
0x180040d5a  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180040d5f  nop
0x180040d60  mov     rbx, [rsp+98h+arg_0]
0x180040d68  test    rbx, rbx
0x180040d6b  jz      short loc_180040DA6
0x180040d6d  cmp     qword ptr [rbx], 0
0x180040d71  jz      short loc_180040DA6
0x180040d73  mov     r8d, 0E0h; int
0x180040d79  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180040d80  mov     rcx, [rbx]; this
0x180040d83  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180040d88  mov     [rsp+98h+pExceptionObject], rbx
0x180040d8d  test    rbx, rbx
0x180040d90  jz      short loc_180040D95
0x180040d92  inc     dword ptr [rbx+8]
0x180040d95  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180040d9c  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180040da1  call    _CxxThrowException_0
0x180040da6  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180040dad  lea     rcx, [rsp+98h+var_70]; this
0x180040db2  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180040db7  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180040dbe  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180040dc3  call    _CxxThrowException_0
0x180040dc9  mov     edi, dword ptr [rsp+98h+arg_0]
0x180040dd0  mov     rbx, [rsp+98h+arg_8]
0x180040dd8  mov     rcx, rbx; this
0x180040ddb  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180040de0  nop
0x180040de1  lea     rcx, [rsp+98h+arg_10]; this
0x180040de9  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180040dee  mov     eax, edi
0x180040df0  mov     rbx, [rsp+98h+arg_18]
0x180040df8  add     rsp, 80h
0x180040dff  pop     r14
0x180040e01  pop     rdi
0x180040e02  pop     rsi
0x180040e03  retn
```
