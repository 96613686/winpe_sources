# CFsiDirectoryItem::put_LastAccessedTime(double)

- ea: `0x180041720`
- end: `0x180041906`
- name: `?put_LastAccessedTime@CFsiDirectoryItem@@UEAAJN@Z`
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
- `0x180012cbc`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180041720`
- `0x180047c94`

## string_xrefs

- `0x18004175c`: `CFsiDirectoryItem::put_LastAccessedTime`

## pseudocode

```c
__int64 __fastcall CFsiDirectoryItem::put_LastAccessedTime(CFsiDirectoryItem *this, double a2)
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
  MethodTrace::MethodTrace((MethodTrace *)v15, "CFsiDirectoryItem::put_LastAccessedTime");
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
        CIMAPIException::SetCodeRefInfo(*v17, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 204);
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
  ImapiComObject::UnlockCS(v3);
  MethodTrace::~MethodTrace((MethodTrace *)v15);
  return 0;
}

```

## disassembly

```asm
0x180041720  mov     rax, rsp
0x180041723  push    rbx
0x180041724  push    rsi
0x180041725  push    rdi
0x180041726  push    r14
0x180041728  push    r15
0x18004172a  sub     rsp, 0B0h
0x180041731  movaps  xmmword ptr [rax-38h], xmm6
0x180041735  movaps  xmm6, xmm1
0x180041738  mov     r14, rcx
0x18004173b  lea     rbx, [rcx-50h]
0x18004173f  mov     [rsp+0D8h+var_B8], rbx
0x180041744  mov     rax, [rbx+90h]
0x18004174b  mov     rdx, [rax]
0x18004174e  mov     rax, [rdx+40h]
0x180041752  mov     edx, [rax+14h]
0x180041755  mov     [rsp+0D8h+arg_10], edx
0x18004175c  lea     rdx, aCfsidirectoryi_13; "CFsiDirectoryItem::put_LastAccessedTime"
0x180041763  lea     rcx, [rsp+0D8h+var_A0]; this
0x180041768  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18004176d  nop
0x18004176e  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180041773  xor     edi, edi
0x180041775  mov     esi, edi
0x180041777  mov     rcx, rbx; this
0x18004177a  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18004177f  add     r14, 40h ; '@'
0x180041783  mov     [rsp+0D8h+var_A8], r14
0x180041788  mov     rax, [r14]
0x18004178b  mov     rcx, [rax]
0x18004178e  cmp     [rcx+48h], rdi
0x180041792  jz      loc_18004189B
0x180041798  mov     r15, [rcx+40h]
0x18004179c  cmp     [r15+8], edi
0x1800417a0  jle     loc_180041846
0x1800417a6  lea     ecx, [rdi+58h]; unsigned __int64
0x1800417a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800417ae  mov     [rsp+0D8h+arg_0], rax
0x1800417b6  test    rax, rax
0x1800417b9  jz      short loc_1800417CA
0x1800417bb  mov     edx, 0C0AAB102h; int
0x1800417c0  mov     rcx, rax; this
0x1800417c3  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800417c8  jmp     short loc_1800417CD
0x1800417ca  mov     rax, rdi
0x1800417cd  mov     rdx, rax
0x1800417d0  lea     rcx, [rsp+0D8h+arg_0]
0x1800417d8  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800417dd  nop
0x1800417de  mov     rbx, [rsp+0D8h+arg_0]
0x1800417e6  test    rbx, rbx
0x1800417e9  jz      short loc_180041823
0x1800417eb  cmp     [rbx], rdi
0x1800417ee  jz      short loc_180041823
0x1800417f0  mov     r8d, 0CCh; int
0x1800417f6  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x1800417fd  mov     rcx, [rbx]; this
0x180041800  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180041805  mov     [rsp+0D8h+pExceptionObject], rbx
0x18004180a  test    rbx, rbx
0x18004180d  jz      short loc_180041812
0x18004180f  inc     dword ptr [rbx+8]
0x180041812  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180041819  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18004181e  call    _CxxThrowException_0
0x180041823  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18004182a  lea     rcx, [rsp+0D8h+var_98]; this
0x18004182f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180041834  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18004183b  lea     rcx, [rsp+0D8h+var_98]; pExceptionObject
0x180041840  call    _CxxThrowException_0
0x180041846  mov     ecx, 50h ; 'P'; unsigned __int64
0x18004184b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041850  test    rax, rax
0x180041853  jz      short loc_18004187B
0x180041855  mov     rcx, [r14]
0x180041858  mov     [rsp+0D8h+arg_0], rcx
0x180041860  test    rcx, rcx
0x180041863  jz      short loc_180041868
0x180041865  inc     dword ptr [rcx+8]
0x180041868  lea     rdx, [rsp+0D8h+arg_0]
0x180041870  mov     rcx, rax
0x180041873  call    ??0RollbackTime@@QEAA@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@Z; RollbackTime::RollbackTime(SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>)
0x180041878  mov     rdi, rax
0x18004187b  mov     rdx, rdi
0x18004187e  lea     rcx, [rsp+0D8h+arg_18]
0x180041886  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x18004188b  lea     rdx, [rsp+0D8h+arg_18]
0x180041893  mov     rcx, r15
0x180041896  call    ?AddToRollback@FileSystemImage@@QEAAXV?$SmartClassPtr@VRollbackBase@@V1@@@@Z; FileSystemImage::AddToRollback(SmartClassPtr<RollbackBase,RollbackBase>)
0x18004189b  mov     rcx, [r14]
0x18004189e  movaps  xmm1, xmm6; double
0x1800418a1  mov     rcx, [rcx]; this
0x1800418a4  call    ?SetLastAccessedTime@ImapiFsObjectBase@@QEAAXN@Z; ImapiFsObjectBase::SetLastAccessedTime(double)
0x1800418a9  nop
0x1800418aa  jmp     short loc_1800418DA
0x1800418ac  mov     esi, dword ptr [rsp+0D8h+arg_0]
0x1800418b3  test    esi, esi
0x1800418b5  jns     short loc_1800418D5
0x1800418b7  mov     rax, [rsp+0D8h+var_A8]
0x1800418bc  mov     rcx, [rax]
0x1800418bf  mov     rcx, [rcx]
0x1800418c2  mov     r8b, 1; bool
0x1800418c5  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x1800418cc  mov     rcx, [rcx+40h]; this
0x1800418d0  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x1800418d5  mov     rbx, [rsp+0D8h+var_B8]
0x1800418da  mov     rcx, rbx; this
0x1800418dd  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x1800418e2  nop
0x1800418e3  lea     rcx, [rsp+0D8h+var_A0]; this
0x1800418e8  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x1800418ed  mov     eax, esi
0x1800418ef  movaps  xmm6, [rsp+0D8h+var_38]
0x1800418f7  add     rsp, 0B0h
0x1800418fe  pop     r15
0x180041900  pop     r14
0x180041902  pop     rdi
0x180041903  pop     rsi
0x180041904  pop     rbx
0x180041905  retn
```
