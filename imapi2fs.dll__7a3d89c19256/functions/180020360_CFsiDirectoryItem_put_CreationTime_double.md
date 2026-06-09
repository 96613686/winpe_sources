# CFsiDirectoryItem::put_CreationTime(double)

- ea: `0x180020360`
- end: `0x180020546`
- name: `?put_CreationTime@CFsiDirectoryItem@@UEAAJN@Z`
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
- `0x180018fdc`
- `0x1800199b8`
- `0x180020360`
- `0x18002073c`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180047c94`

## string_xrefs

- `0x18002039c`: `CFsiDirectoryItem::put_CreationTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiDirectoryItem::put_CreationTime(CFsiDirectoryItem *this, double a2)
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
  MethodTrace::MethodTrace((MethodTrace *)v15, "CFsiDirectoryItem::put_CreationTime");
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
          CIMAPIException::SetCodeRefInfo(*v17, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 167);
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
    ImapiFsObjectBase::SetCreationTime(**v5, a2);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  ImapiComObject::UnlockCS(v3);
  MethodTrace::~MethodTrace((MethodTrace *)v15);
  return 0;
}

```

## disassembly

```asm
0x180020360  mov     rax, rsp
0x180020363  push    rbx
0x180020364  push    rsi
0x180020365  push    rdi
0x180020366  push    r14
0x180020368  push    r15
0x18002036a  sub     rsp, 0B0h
0x180020371  movaps  xmmword ptr [rax-38h], xmm6
0x180020375  movaps  xmm6, xmm1
0x180020378  mov     r14, rcx
0x18002037b  lea     rbx, [rcx-50h]
0x18002037f  mov     [rsp+0D8h+var_B8], rbx
0x180020384  mov     rax, [rbx+90h]
0x18002038b  mov     rdx, [rax]
0x18002038e  mov     rax, [rdx+40h]
0x180020392  mov     edx, [rax+14h]
0x180020395  mov     [rsp+0D8h+arg_10], edx
0x18002039c  lea     rdx, aCfsidirectoryi_0; "CFsiDirectoryItem::put_CreationTime"
0x1800203a3  lea     rcx, [rsp+0D8h+var_A0]; this
0x1800203a8  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x1800203ad  nop
0x1800203ae  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x1800203b3  xor     edi, edi
0x1800203b5  mov     esi, edi
0x1800203b7  mov     rcx, rbx; this
0x1800203ba  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x1800203bf  add     r14, 40h ; '@'
0x1800203c3  mov     [rsp+0D8h+var_A8], r14
0x1800203c8  mov     rax, [r14]
0x1800203cb  mov     rcx, [rax]
0x1800203ce  cmp     [rcx+48h], rdi
0x1800203d2  jz      loc_1800204DB
0x1800203d8  mov     r15, [rcx+40h]
0x1800203dc  cmp     [r15+8], edi
0x1800203e0  jle     loc_180020486
0x1800203e6  lea     ecx, [rdi+58h]; unsigned __int64
0x1800203e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800203ee  mov     [rsp+0D8h+arg_0], rax
0x1800203f6  test    rax, rax
0x1800203f9  jz      short loc_18002040A
0x1800203fb  mov     edx, 0C0AAB102h; int
0x180020400  mov     rcx, rax; this
0x180020403  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180020408  jmp     short loc_18002040D
0x18002040a  mov     rax, rdi
0x18002040d  mov     rdx, rax
0x180020410  lea     rcx, [rsp+0D8h+arg_0]
0x180020418  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18002041d  nop
0x18002041e  mov     rbx, [rsp+0D8h+arg_0]
0x180020426  test    rbx, rbx
0x180020429  jz      short loc_180020463
0x18002042b  cmp     [rbx], rdi
0x18002042e  jz      short loc_180020463
0x180020430  mov     r8d, 0A7h; int
0x180020436  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18002043d  mov     rcx, [rbx]; this
0x180020440  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180020445  mov     [rsp+0D8h+pExceptionObject], rbx
0x18002044a  test    rbx, rbx
0x18002044d  jz      short loc_180020452
0x18002044f  inc     dword ptr [rbx+8]
0x180020452  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180020459  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18002045e  call    _CxxThrowException_0
0x180020463  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18002046a  lea     rcx, [rsp+0D8h+var_98]; this
0x18002046f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180020474  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18002047b  lea     rcx, [rsp+0D8h+var_98]; pExceptionObject
0x180020480  call    _CxxThrowException_0
0x180020486  mov     ecx, 50h ; 'P'; unsigned __int64
0x18002048b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020490  test    rax, rax
0x180020493  jz      short loc_1800204BB
0x180020495  mov     rcx, [r14]
0x180020498  mov     [rsp+0D8h+arg_0], rcx
0x1800204a0  test    rcx, rcx
0x1800204a3  jz      short loc_1800204A8
0x1800204a5  inc     dword ptr [rcx+8]
0x1800204a8  lea     rdx, [rsp+0D8h+arg_0]
0x1800204b0  mov     rcx, rax
0x1800204b3  call    ??0RollbackTime@@QEAA@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@Z; RollbackTime::RollbackTime(SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>)
0x1800204b8  mov     rdi, rax
0x1800204bb  mov     rdx, rdi
0x1800204be  lea     rcx, [rsp+0D8h+arg_18]
0x1800204c6  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x1800204cb  lea     rdx, [rsp+0D8h+arg_18]
0x1800204d3  mov     rcx, r15
0x1800204d6  call    ?AddToRollback@FileSystemImage@@QEAAXV?$SmartClassPtr@VRollbackBase@@V1@@@@Z; FileSystemImage::AddToRollback(SmartClassPtr<RollbackBase,RollbackBase>)
0x1800204db  mov     rcx, [r14]
0x1800204de  movaps  xmm1, xmm6; double
0x1800204e1  mov     rcx, [rcx]; this
0x1800204e4  call    ?SetCreationTime@ImapiFsObjectBase@@QEAAXN@Z; ImapiFsObjectBase::SetCreationTime(double)
0x1800204e9  nop
0x1800204ea  jmp     short loc_18002051A
0x1800204ec  mov     esi, dword ptr [rsp+0D8h+arg_0]
0x1800204f3  test    esi, esi
0x1800204f5  jns     short loc_180020515
0x1800204f7  mov     rax, [rsp+0D8h+var_A8]
0x1800204fc  mov     rcx, [rax]
0x1800204ff  mov     rcx, [rcx]
0x180020502  mov     r8b, 1; bool
0x180020505  mov     edx, [rsp+0D8h+arg_10]; unsigned int
0x18002050c  mov     rcx, [rcx+40h]; this
0x180020510  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x180020515  mov     rbx, [rsp+0D8h+var_B8]
0x18002051a  mov     rcx, rbx; this
0x18002051d  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180020522  nop
0x180020523  lea     rcx, [rsp+0D8h+var_A0]; this
0x180020528  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18002052d  mov     eax, esi
0x18002052f  movaps  xmm6, [rsp+0D8h+var_38]
0x180020537  add     rsp, 0B0h
0x18002053e  pop     r15
0x180020540  pop     r14
0x180020542  pop     rdi
0x180020543  pop     rsi
0x180020544  pop     rbx
0x180020545  retn
```
