# CMsftIsoImageManager::SetPath(ushort *)

- ea: `0x18002a6c0`
- end: `0x18002a7ea`
- name: `?SetPath@CMsftIsoImageManager@@UEAAJPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(CMsftIsoImageManager *__hidden this, OLECHAR *psz)`
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
- `0x18002a6c0`
- `0x18002d4e4`
- `0x1800784c8`

## string_xrefs

- `0x18002a6d3`: `CMsftIsoImageManager::SetPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMsftIsoImageManager::SetPath(CMsftIsoImageManager *this, OLECHAR *psz)
{
  ImapiComObject *v4; // rdi
  unsigned __int16 **v5; // r8
  int v6; // ebx
  CIMAPIException *v7; // rax
  CIMAPIException **v8; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v11[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v12; // [rsp+A0h] [rbp+8h] BYREF
  char *v13; // [rsp+B0h] [rbp+18h]
  char v14; // [rsp+B8h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v14, "CMsftIsoImageManager::SetPath");
  ImapiClearErrorInfo();
  v4 = (CMsftIsoImageManager *)((char *)this + 8);
  v13 = (char *)this + 8;
  ImapiComObject::LockCS((CMsftIsoImageManager *)((char *)this + 8));
  try
  {
    v6 = Imapi2Utility::SetGenericStringProperty(
           psz,
           (unsigned __int16 *)this + 72,
           v5,
           (int (*)(void *, unsigned __int16 *))this,
           pExceptionObject);
    if ( v6 < 0 )
    {
      v7 = (CIMAPIException *)operator new(0x58u);
      v12 = (CIMAPIException **)v7;
      if ( v7 )
        v7 = CIMAPIException::CIMAPIException(v7, v6);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v12, v7);
      v8 = v12;
      if ( v12 && *v12 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v12,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp",
          104);
        pExceptionObject = v8;
        if ( v8 )
          ++*((_DWORD *)v8 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v11,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v11;
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_MsftIsoImageManager);
  }
  ImapiComObject::UnlockCS(v4);
  MethodTrace::~MethodTrace((MethodTrace *)&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002a6c0  mov     rax, rsp
0x18002a6c3  push    rbx
0x18002a6c4  push    rsi
0x18002a6c5  push    rdi
0x18002a6c6  sub     rsp, 80h
0x18002a6cd  mov     rsi, rdx
0x18002a6d0  mov     rbx, rcx
0x18002a6d3  lea     rdx, aCmsftisoimagem_0; "CMsftIsoImageManager::SetPath"
0x18002a6da  lea     rcx, [rax+20h]; this
0x18002a6de  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18002a6e3  nop
0x18002a6e4  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18002a6e9  nop
0x18002a6ea  lea     rdi, [rbx+8]
0x18002a6ee  mov     [rsp+98h+arg_10], rdi
0x18002a6f6  mov     rcx, rdi; this
0x18002a6f9  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18002a6fe  lea     rdx, [rbx+90h]; unsigned __int16 *
0x18002a705  mov     r9, rbx; int (*)(void *, unsigned __int16 *)
0x18002a708  mov     rcx, rsi; psz
0x18002a70b  call    ?SetGenericStringProperty@Imapi2Utility@@YAJPEAGPEAPEAGP6AJPEAX0@Z2@Z; Imapi2Utility::SetGenericStringProperty(ushort *,ushort * *,long (*)(void *,ushort *),void *)
0x18002a710  mov     ebx, eax
0x18002a712  test    eax, eax
0x18002a714  jns     loc_18002A7B6
0x18002a71a  mov     ecx, 58h ; 'X'; unsigned __int64
0x18002a71f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a724  mov     [rsp+98h+arg_0], rax
0x18002a72c  test    rax, rax
0x18002a72f  jz      short loc_18002A73C
0x18002a731  mov     edx, ebx; int
0x18002a733  mov     rcx, rax; this
0x18002a736  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18002a73b  nop
0x18002a73c  mov     rdx, rax
0x18002a73f  lea     rcx, [rsp+98h+arg_0]
0x18002a747  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18002a74c  nop
0x18002a74d  mov     rbx, [rsp+98h+arg_0]
0x18002a755  test    rbx, rbx
0x18002a758  jz      short loc_18002A793
0x18002a75a  cmp     qword ptr [rbx], 0
0x18002a75e  jz      short loc_18002A793
0x18002a760  mov     r8d, 68h ; 'h'; int
0x18002a766  lea     rdx, aDriversStorage_8; "drivers\\storage\\imapi2\\filesystemima"...
0x18002a76d  mov     rcx, [rbx]; this
0x18002a770  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18002a775  mov     [rsp+98h+pExceptionObject], rbx
0x18002a77a  test    rbx, rbx
0x18002a77d  jz      short loc_18002A782
0x18002a77f  inc     dword ptr [rbx+8]
0x18002a782  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18002a789  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18002a78e  call    _CxxThrowException_0
0x18002a793  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18002a79a  lea     rcx, [rsp+98h+var_70]; this
0x18002a79f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18002a7a4  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18002a7ab  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x18002a7b0  call    _CxxThrowException_0
0x18002a7b6  jmp     short loc_18002A7C7
0x18002a7b8  mov     ebx, dword ptr [rsp+98h+arg_0]
0x18002a7bf  mov     rdi, [rsp+98h+arg_10]
0x18002a7c7  mov     rcx, rdi; this
0x18002a7ca  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18002a7cf  nop
0x18002a7d0  lea     rcx, [rsp+98h+arg_18]; this
0x18002a7d8  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18002a7dd  mov     eax, ebx
0x18002a7df  add     rsp, 80h
0x18002a7e6  pop     rdi
0x18002a7e7  pop     rsi
0x18002a7e8  pop     rbx
0x18002a7e9  retn
```
