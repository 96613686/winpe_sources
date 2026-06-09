# CFsiDirectoryItem::put_LastModifiedTime(double)

- ea: `0x180041910`
- end: `0x180041af6`
- name: `?put_LastModifiedTime@CFsiDirectoryItem@@UEAAJN@Z`
- size: `486`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, double)`
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
- `0x180012eec`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180041910`
- `0x180047c94`

## string_xrefs

- `0x18004194c`: `CFsiDirectoryItem::put_LastModifiedTime`

## pseudocode

```c
__int64 __fastcall CFsiDirectoryItem::put_LastModifiedTime(CFsiDirectoryItem *this, double a2)
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

  v3 = (CFsiDirectoryItem *)((char *)this - 80);
  v18 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  MethodTrace::MethodTrace((MethodTrace *)v15, "CFsiDirectoryItem::put_LastModifiedTime");
  ImapiClearErrorInfo();
  v4 = 0;
  ImapiComObject::LockCS(v3);
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
        CIMAPIException::SetCodeRefInfo(*v17, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 241);
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
  ImapiFsObjectBase::SetLastModifiedTime(**v5, a2);
  ImapiComObject::UnlockCS(v3);
  MethodTrace::~MethodTrace((MethodTrace *)v15);
  return 0;
}

```

## disassembly

```asm
0x180041910  mov     rax, rsp
0x180041913  push    rbx
0x180041914  push    rsi
0x180041915  push    rdi
0x180041916  push    r14
0x180041918  push    r15
0x18004191a  sub     rsp, 0B0h
0x180041921  movaps  xmmword ptr [rax-38h], xmm6
0x180041925  movaps  xmm6, xmm1
0x180041928  mov     r14, rcx
0x18004192b  lea     rbx, [rcx-50h]
0x18004192f  mov     [rsp+0D8h+var_B8], rbx
0x180041934  mov     rax, [rbx+90h]
0x18004193b  mov     rdx, [rax]
0x18004193e  mov     rax, [rdx+40h]
0x180041942  mov     edx, [rax+14h]
0x180041945  mov     [rsp+0D8h+arg_10], edx
0x18004194c  lea     rdx, aCfsidirectoryi_14; "CFsiDirectoryItem::put_LastModifiedTime"
0x180041953  lea     rcx, [rsp+0D8h+var_A0]; this
0x180041958  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18004195d  nop
0x18004195e  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180041963  xor     edi, edi
0x180041965  mov     esi, edi
0x180041967  mov     rcx, rbx; this
0x18004196a  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18004196f  add     r14, 40h ; '@'
0x180041973  mov     [rsp+0D8h+var_A8], r14
0x180041978  mov     rax, [r14]
0x18004197b  mov     rcx, [rax]
0x18004197e  cmp     [rcx+48h], rdi
0x180041982  jz      loc_180041A8B
0x180041988  mov     r15, [rcx+40h]
0x18004198c  cmp     [r15+8], edi
0x180041990  jle     loc_180041A36
0x180041996  lea     ecx, [rdi+58h]; unsigned __int64
0x180041999  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004199e  mov     [rsp+0D8h+arg_0], rax
0x1800419a6  test    rax, rax
0x1800419a9  jz      short loc_1800419BA
0x1800419ab  mov     edx, 0C0AAB102h; int
0x1800419b0  mov     rcx, rax; this
0x1800419b3  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800419b8  jmp     short loc_1800419BD
0x1800419ba  mov     rax, rdi
0x1800419bd  mov     rdx, rax
0x1800419c0  lea     rcx, [rsp+0D8h+arg_0]
0x1800419c8  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800419cd  nop
0x1800419ce  mov     rbx, [rsp+0D8h+arg_0]
0x1800419d6  test    rbx, rbx
0x1800419d9  jz      short loc_180041A13
0x1800419db  cmp     [rbx], rdi
0x1800419de  jz      short loc_180041A13
0x1800419e0  mov     r8d, 0F1h; int
0x1800419e6  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x1800419ed  mov     rcx, [rbx]; this
0x1800419f0  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800419f5  mov     [rsp+0D8h+pExceptionObject], rbx
0x1800419fa  test    rbx, rbx
0x1800419fd  jz      short loc_180041A02
0x1800419ff  inc     dword ptr [rbx+8]
0x180041a02  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180041a09  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180041a0e  call    _CxxThrowException_0
0x180041a13  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180041a1a  lea     rcx, [rsp+0D8h+var_98]; this
0x180041a1f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180041a24  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180041a2b  lea     rcx, [rsp+0D8h+var_98]; pExceptionObject
0x180041a30  call    _CxxThrowException_0
0x180041a36  mov     ecx, 50h ; 'P'; unsigned __int64
0x180041a3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041a40  test    rax, rax
0x180041a43  jz      short loc_180041A6B
0x180041a45  mov     rcx, [r14]
0x180041a48  mov     [rsp+0D8h+arg_0], rcx
0x180041a50  test    rcx, rcx
0x180041a53  jz      short loc_180041A58
0x180041a55  inc     dword ptr [rcx+8]
0x180041a58  lea     rdx, [rsp+0D8h+arg_0]
0x180041a60  mov     rcx, rax
0x180041a63  call    ??0RollbackTime@@QEAA@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@Z; RollbackTime::RollbackTime(SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>)
0x180041a68  mov     rdi, rax
0x180041a6b  mov     rdx, rdi
0x180041a6e  lea     rcx, [rsp+0D8h+arg_18]
0x180041a76  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x180041a7b  lea     rdx, [rsp+0D8h+arg_18]
0x180041a83  mov     rcx, r15
0x180041a86  call    ?AddToRollback@FileSystemImage@@QEAAXV?$SmartClassPtr@VRollbackBase@@V1@@@@Z; FileSystemImage::AddToRollback(SmartClassPtr<RollbackBase,RollbackBase>)
0x180041a8b  mov     rcx, [r14]
0x180041a8e  movaps  xmm1, xmm6; double
0x180041a91  mov     rcx, [rcx]; this
0x180041a94  call    ?SetLastModifiedTime@ImapiFsObjectBase@@QEAAXN@Z; ImapiFsObjectBase::SetLastModifiedTime(double)
0x180041a99  nop
0x180041a9a  jmp     short loc_180041ACA
0x180041a9c  mov     esi, dword ptr [rsp+0D8h+arg_0]
0x180041aa3  test    esi, esi
0x180041aa5  jns     short loc_180041AC5
0x180041aa7  mov     rax, [rsp+0D8h+var_A8]
0x180041aac  mov     rcx, [rax]
0x180041aaf  mov     rcx, [rcx]
0x180041ab2  mov     r8b, 1; bool
0x180041ab5  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x180041abc  mov     rcx, [rcx+40h]; this
0x180041ac0  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x180041ac5  mov     rbx, [rsp+0D8h+var_B8]
0x180041aca  mov     rcx, rbx; this
0x180041acd  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180041ad2  nop
0x180041ad3  lea     rcx, [rsp+0D8h+var_A0]; this
0x180041ad8  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180041add  mov     eax, esi
0x180041adf  movaps  xmm6, [rsp+0D8h+var_38]
0x180041ae7  add     rsp, 0B0h
0x180041aee  pop     r15
0x180041af0  pop     r14
0x180041af2  pop     rdi
0x180041af3  pop     rsi
0x180041af4  pop     rbx
0x180041af5  retn
```
