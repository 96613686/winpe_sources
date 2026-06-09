# CFsiDirectoryItem::get_LastAccessedTime(double *)

- ea: `0x180040a20`
- end: `0x180040b64`
- name: `?get_LastAccessedTime@CFsiDirectoryItem@@UEAAJPEAN@Z`
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
- `0x180040a20`

## string_xrefs

- `0x180040a38`: `CFsiDirectoryItem::get_LastAccessedTime`

## pseudocode

```c
__int64 __fastcall CFsiDirectoryItem::get_LastAccessedTime(CFsiDirectoryItem *this, double *a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CFsiDirectoryItem::get_LastAccessedTime");
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
      CIMAPIException::SetCodeRefInfo(*v9, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 187);
      pExceptionObject = v5;
      if ( v5 )
        ++*((_DWORD *)v5 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v8, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v8;
  }
  *a2 = 0.0;
  *a2 = *(double *)(**((_QWORD **)this + 8) + 200LL);
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x180040a20  mov     rax, rsp
0x180040a23  mov     [rax+20h], rbx
0x180040a27  push    rsi
0x180040a28  push    rdi
0x180040a29  push    r14
0x180040a2b  sub     rsp, 80h
0x180040a32  mov     rsi, rdx
0x180040a35  mov     r14, rcx
0x180040a38  lea     rdx, aCfsidirectoryi_18; "CFsiDirectoryItem::get_LastAccessedTime"
0x180040a3f  lea     rcx, [rax+18h]; this
0x180040a43  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180040a48  nop
0x180040a49  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180040a4e  nop
0x180040a4f  lea     rbx, [r14-50h]
0x180040a53  mov     [rsp+98h+arg_8], rbx
0x180040a5b  mov     rcx, rbx; this
0x180040a5e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180040a63  test    rsi, rsi
0x180040a66  jz      short loc_180040A83
0x180040a68  xor     edi, edi
0x180040a6a  mov     [rsi], rdi
0x180040a6d  mov     rax, [r14+40h]
0x180040a71  mov     rcx, [rax]
0x180040a74  mov     rax, [rcx+0C8h]
0x180040a7b  mov     [rsi], rax
0x180040a7e  jmp     loc_180040B38
0x180040a83  mov     ecx, 58h ; 'X'; unsigned __int64
0x180040a88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040a8d  mov     [rsp+98h+arg_0], rax
0x180040a95  test    rax, rax
0x180040a98  jz      short loc_180040AAF
0x180040a9a  lea     r8, aPval; "pVal"
0x180040aa1  mov     edx, 80004003h; int
0x180040aa6  mov     rcx, rax; this
0x180040aa9  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180040aae  nop
0x180040aaf  mov     rdx, rax
0x180040ab2  lea     rcx, [rsp+98h+arg_0]
0x180040aba  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180040abf  nop
0x180040ac0  mov     rbx, [rsp+98h+arg_0]
0x180040ac8  test    rbx, rbx
0x180040acb  jz      short loc_180040B06
0x180040acd  cmp     qword ptr [rbx], 0
0x180040ad1  jz      short loc_180040B06
0x180040ad3  mov     r8d, 0BBh; int
0x180040ad9  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180040ae0  mov     rcx, [rbx]; this
0x180040ae3  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180040ae8  mov     [rsp+98h+pExceptionObject], rbx
0x180040aed  test    rbx, rbx
0x180040af0  jz      short loc_180040AF5
0x180040af2  inc     dword ptr [rbx+8]
0x180040af5  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180040afc  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180040b01  call    _CxxThrowException_0
0x180040b06  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180040b0d  lea     rcx, [rsp+98h+var_70]; this
0x180040b12  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180040b17  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180040b1e  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180040b23  call    _CxxThrowException_0
0x180040b29  mov     edi, dword ptr [rsp+98h+arg_0]
0x180040b30  mov     rbx, [rsp+98h+arg_8]
0x180040b38  mov     rcx, rbx; this
0x180040b3b  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180040b40  nop
0x180040b41  lea     rcx, [rsp+98h+arg_10]; this
0x180040b49  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180040b4e  mov     eax, edi
0x180040b50  mov     rbx, [rsp+98h+arg_18]
0x180040b58  add     rsp, 80h
0x180040b5f  pop     r14
0x180040b61  pop     rdi
0x180040b62  pop     rsi
0x180040b63  retn
```
