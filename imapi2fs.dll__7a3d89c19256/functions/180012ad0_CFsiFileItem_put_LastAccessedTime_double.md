# CFsiFileItem::put_LastAccessedTime(double)

- ea: `0x180012ad0`
- end: `0x180012cb6`
- name: `?put_LastAccessedTime@CFsiFileItem@@UEAAJN@Z`
- size: `486`
- prototype: `__int64 __fastcall(CFsiFileItem *__hidden this, double)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000726c`
- `0x18000960c`
- `0x180011c48`
- `0x1800125ec`
- `0x1800127bc`
- `0x180012ad0`
- `0x180012cbc`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180047c94`

## string_xrefs

- `0x180012b0c`: `CFsiFileItem::put_LastAccessedTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiFileItem::put_LastAccessedTime(CFsiFileItem *this, double a2)
{
  ImapiComObject *v3; // rbx
  __int64 v4; // rdi
  ImapiFsObjectBase ***v5; // r14
  ImapiFsObjectBase *v6; // rcx
  __int64 v7; // r15
  CIMAPIException *v8; // rax
  CIMAPIException *v9; // rax
  CIMAPIException **v10; // rbx
  void *v11; // rax
  CIMAPIException **v12; // rcx
  _QWORD pExceptionObject[2]; // [rsp+28h] [rbp-B0h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v16[96]; // [rsp+40h] [rbp-98h] BYREF
  CIMAPIException **v17; // [rsp+E0h] [rbp+8h] BYREF
  unsigned int v18; // [rsp+F0h] [rbp+18h]
  char v19; // [rsp+F8h] [rbp+20h] BYREF

  v3 = (CFsiFileItem *)((char *)this - 80);
  v18 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  MethodTrace::MethodTrace((MethodTrace *)v15, "CFsiFileItem::put_LastAccessedTime");
  ImapiClearErrorInfo();
  v4 = 0;
  ImapiComObject::LockCS(v3);
  try
  {
    v5 = (ImapiFsObjectBase ***)((char *)this + 64);
    pExceptionObject[1] = v5;
    v6 = **v5;
    if ( *((_QWORD *)v6 + 9) )
    {
      v7 = *((_QWORD *)v6 + 8);
      if ( *(int *)(v7 + 8) > 0 )
      {
        v8 = (CIMAPIException *)operator new(0x58u);
        v17 = (CIMAPIException **)v8;
        if ( v8 )
          v9 = CIMAPIException::CIMAPIException(v8, -1062555390);
        else
          v9 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v17, v9);
        v10 = v17;
        if ( v17 && *v17 )
        {
          CIMAPIException::SetCodeRefInfo(*v17, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 1048);
          pExceptionObject[0] = v10;
          if ( v10 )
            ++*((_DWORD *)v10 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v16,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v16;
      }
      v11 = operator new(0x50u);
      if ( v11 )
      {
        v12 = *v5;
        v17 = v12;
        if ( v12 )
          ++*((_DWORD *)v12 + 2);
        v4 = RollbackTime::RollbackTime(v11, &v17);
      }
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v19, v4);
      FileSystemImage::AddToRollback(v7, &v19);
    }
    ImapiFsObjectBase::SetLastAccessedTime(**v5, a2);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiFileItem);
  }
  ImapiComObject::UnlockCS(v3);
  MethodTrace::~MethodTrace((MethodTrace *)v15);
  return 0;
}

```

## disassembly

```asm
0x180012ad0  mov     rax, rsp
0x180012ad3  push    rbx
0x180012ad4  push    rsi
0x180012ad5  push    rdi
0x180012ad6  push    r14
0x180012ad8  push    r15
0x180012ada  sub     rsp, 0B0h
0x180012ae1  movaps  xmmword ptr [rax-38h], xmm6
0x180012ae5  movaps  xmm6, xmm1
0x180012ae8  mov     r14, rcx
0x180012aeb  lea     rbx, [rcx-50h]
0x180012aef  mov     [rsp+0D8h+var_B8], rbx
0x180012af4  mov     rax, [rbx+90h]
0x180012afb  mov     rdx, [rax]
0x180012afe  mov     rax, [rdx+40h]
0x180012b02  mov     edx, [rax+14h]
0x180012b05  mov     [rsp+0D8h+arg_10], edx
0x180012b0c  lea     rdx, aCfsifileitemPu_0; "CFsiFileItem::put_LastAccessedTime"
0x180012b13  lea     rcx, [rsp+0D8h+var_A0]; this
0x180012b18  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180012b1d  nop
0x180012b1e  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180012b23  xor     edi, edi
0x180012b25  mov     esi, edi
0x180012b27  mov     rcx, rbx; this
0x180012b2a  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180012b2f  add     r14, 40h ; '@'
0x180012b33  mov     [rsp+0D8h+var_A8], r14
0x180012b38  mov     rax, [r14]
0x180012b3b  mov     rcx, [rax]
0x180012b3e  cmp     [rcx+48h], rdi
0x180012b42  jz      loc_180012C4B
0x180012b48  mov     r15, [rcx+40h]
0x180012b4c  cmp     [r15+8], edi
0x180012b50  jle     loc_180012BF6
0x180012b56  lea     ecx, [rdi+58h]; unsigned __int64
0x180012b59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012b5e  mov     [rsp+0D8h+arg_0], rax
0x180012b66  test    rax, rax
0x180012b69  jz      short loc_180012B7A
0x180012b6b  mov     edx, 0C0AAB102h; int
0x180012b70  mov     rcx, rax; this
0x180012b73  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180012b78  jmp     short loc_180012B7D
0x180012b7a  mov     rax, rdi
0x180012b7d  mov     rdx, rax
0x180012b80  lea     rcx, [rsp+0D8h+arg_0]
0x180012b88  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180012b8d  nop
0x180012b8e  mov     rbx, [rsp+0D8h+arg_0]
0x180012b96  test    rbx, rbx
0x180012b99  jz      short loc_180012BD3
0x180012b9b  cmp     [rbx], rdi
0x180012b9e  jz      short loc_180012BD3
0x180012ba0  mov     r8d, 418h; int
0x180012ba6  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180012bad  mov     rcx, [rbx]; this
0x180012bb0  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180012bb5  mov     [rsp+0D8h+pExceptionObject], rbx
0x180012bba  test    rbx, rbx
0x180012bbd  jz      short loc_180012BC2
0x180012bbf  inc     dword ptr [rbx+8]
0x180012bc2  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180012bc9  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180012bce  call    _CxxThrowException_0
0x180012bd3  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180012bda  lea     rcx, [rsp+0D8h+var_98]; this
0x180012bdf  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180012be4  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180012beb  lea     rcx, [rsp+0D8h+var_98]; pExceptionObject
0x180012bf0  call    _CxxThrowException_0
0x180012bf6  mov     ecx, 50h ; 'P'; unsigned __int64
0x180012bfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012c00  test    rax, rax
0x180012c03  jz      short loc_180012C2B
0x180012c05  mov     rcx, [r14]
0x180012c08  mov     [rsp+0D8h+arg_0], rcx
0x180012c10  test    rcx, rcx
0x180012c13  jz      short loc_180012C18
0x180012c15  inc     dword ptr [rcx+8]
0x180012c18  lea     rdx, [rsp+0D8h+arg_0]
0x180012c20  mov     rcx, rax
0x180012c23  call    ??0RollbackTime@@QEAA@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@Z; RollbackTime::RollbackTime(SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>)
0x180012c28  mov     rdi, rax
0x180012c2b  mov     rdx, rdi
0x180012c2e  lea     rcx, [rsp+0D8h+arg_18]
0x180012c36  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x180012c3b  lea     rdx, [rsp+0D8h+arg_18]
0x180012c43  mov     rcx, r15
0x180012c46  call    ?AddToRollback@FileSystemImage@@QEAAXV?$SmartClassPtr@VRollbackBase@@V1@@@@Z; FileSystemImage::AddToRollback(SmartClassPtr<RollbackBase,RollbackBase>)
0x180012c4b  mov     rcx, [r14]
0x180012c4e  movaps  xmm1, xmm6; double
0x180012c51  mov     rcx, [rcx]; this
0x180012c54  call    ?SetLastAccessedTime@ImapiFsObjectBase@@QEAAXN@Z; ImapiFsObjectBase::SetLastAccessedTime(double)
0x180012c59  nop
0x180012c5a  jmp     short loc_180012C8A
0x180012c5c  mov     esi, dword ptr [rsp+0D8h+arg_0]
0x180012c63  test    esi, esi
0x180012c65  jns     short loc_180012C85
0x180012c67  mov     rax, [rsp+0D8h+var_A8]
0x180012c6c  mov     rcx, [rax]
0x180012c6f  mov     rcx, [rcx]
0x180012c72  mov     r8b, 1; bool
0x180012c75  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x180012c7c  mov     rcx, [rcx+40h]; this
0x180012c80  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x180012c85  mov     rbx, [rsp+0D8h+var_B8]
0x180012c8a  mov     rcx, rbx; this
0x180012c8d  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180012c92  nop
0x180012c93  lea     rcx, [rsp+0D8h+var_A0]; this
0x180012c98  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180012c9d  mov     eax, esi
0x180012c9f  movaps  xmm6, [rsp+0D8h+var_38]
0x180012ca7  add     rsp, 0B0h
0x180012cae  pop     r15
0x180012cb0  pop     r14
0x180012cb2  pop     rdi
0x180012cb3  pop     rsi
0x180012cb4  pop     rbx
0x180012cb5  retn
```
