# CFsiDirectoryItem::put_IsHidden(short)

- ea: `0x180011200`
- end: `0x1800113ef`
- name: `?put_IsHidden@CFsiDirectoryItem@@UEAAJF@Z`
- size: `495`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000726c`
- `0x18000960c`
- `0x180011200`
- `0x180011c48`
- `0x180012090`
- `0x1800125ec`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180047c94`

## string_xrefs

- `0x18001123e`: `CFsiDirectoryItem::put_IsHidden`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiDirectoryItem::put_IsHidden(CFsiDirectoryItem *this, __int16 a2)
{
  ImapiComObject *v4; // rbx
  CIMAPIException ***v5; // r14
  CIMAPIException *v6; // rcx
  __int64 v7; // r15
  CIMAPIException *v8; // rax
  CIMAPIException *v9; // rax
  CIMAPIException **v10; // rbx
  void *v11; // rax
  CIMAPIException **v12; // rcx
  __int64 v13; // rax
  _QWORD pExceptionObject[2]; // [rsp+28h] [rbp-A0h] BYREF
  char v16[8]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v17[136]; // [rsp+40h] [rbp-88h] BYREF
  CIMAPIException **v18; // [rsp+D0h] [rbp+8h] BYREF
  unsigned int v19; // [rsp+E0h] [rbp+18h]
  char v20; // [rsp+E8h] [rbp+20h] BYREF

  v4 = (CFsiDirectoryItem *)((char *)this - 80);
  v19 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  MethodTrace::MethodTrace((MethodTrace *)v16, "CFsiDirectoryItem::put_IsHidden");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS(v4);
  try
  {
    v5 = (CIMAPIException ***)((char *)this + 64);
    pExceptionObject[1] = v5;
    v6 = **v5;
    if ( *((_QWORD *)v6 + 9) )
    {
      v7 = *((_QWORD *)v6 + 8);
      if ( *(int *)(v7 + 8) > 0 )
      {
        v8 = (CIMAPIException *)operator new(0x58u);
        v18 = (CIMAPIException **)v8;
        if ( v8 )
          v9 = CIMAPIException::CIMAPIException(v8, -1062555390);
        else
          v9 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v18, v9);
        v10 = v18;
        if ( v18 && *v18 )
        {
          CIMAPIException::SetCodeRefInfo(*v18, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 278);
          pExceptionObject[0] = v10;
          if ( v10 )
            ++*((_DWORD *)v10 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v17,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v17;
      }
      v11 = operator new(0x28u);
      if ( v11 )
      {
        v12 = *v5;
        v18 = v12;
        if ( v12 )
          ++*((_DWORD *)v12 + 2);
        v13 = RollbackHidden::RollbackHidden(v11, &v18);
      }
      else
      {
        v13 = 0;
      }
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v20, v13);
      FileSystemImage::AddToRollback(v7, &v20);
    }
    *((_BYTE *)**v5 + 177) = a2 != 0;
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  ImapiComObject::UnlockCS(v4);
  MethodTrace::~MethodTrace((MethodTrace *)v16);
  return 0;
}

```

## disassembly

```asm
0x180011200  mov     [rsp+arg_8], rbx
0x180011205  push    rsi
0x180011206  push    rdi
0x180011207  push    r12
0x180011209  push    r14
0x18001120b  push    r15
0x18001120d  sub     rsp, 0A0h
0x180011214  movzx   r12d, dx
0x180011218  mov     r14, rcx
0x18001121b  lea     rbx, [rcx-50h]
0x18001121f  mov     [rsp+0C8h+var_A8], rbx
0x180011224  mov     rax, [rbx+90h]
0x18001122b  mov     r8, [rax]
0x18001122e  mov     rax, [r8+40h]
0x180011232  mov     r8d, [rax+14h]
0x180011236  mov     [rsp+0C8h+arg_10], r8d
0x18001123e  lea     rdx, aCfsidirectoryi_1; "CFsiDirectoryItem::put_IsHidden"
0x180011245  lea     rcx, [rsp+0C8h+var_90]; this
0x18001124a  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18001124f  nop
0x180011250  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180011255  xor     edi, edi
0x180011257  mov     esi, edi
0x180011259  mov     rcx, rbx; this
0x18001125c  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180011261  add     r14, 40h ; '@'
0x180011265  mov     [rsp+0C8h+var_98], r14
0x18001126a  mov     rax, [r14]
0x18001126d  mov     rcx, [rax]
0x180011270  cmp     [rcx+48h], rdi
0x180011274  jz      loc_18001137F
0x18001127a  mov     r15, [rcx+40h]
0x18001127e  cmp     [r15+8], edi
0x180011282  jle     loc_180011328
0x180011288  lea     ecx, [rdi+58h]; unsigned __int64
0x18001128b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011290  mov     [rsp+0C8h+arg_0], rax
0x180011298  test    rax, rax
0x18001129b  jz      short loc_1800112AC
0x18001129d  mov     edx, 0C0AAB102h; int
0x1800112a2  mov     rcx, rax; this
0x1800112a5  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800112aa  jmp     short loc_1800112AF
0x1800112ac  mov     rax, rdi
0x1800112af  mov     rdx, rax
0x1800112b2  lea     rcx, [rsp+0C8h+arg_0]
0x1800112ba  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800112bf  nop
0x1800112c0  mov     rbx, [rsp+0C8h+arg_0]
0x1800112c8  test    rbx, rbx
0x1800112cb  jz      short loc_180011305
0x1800112cd  cmp     [rbx], rdi
0x1800112d0  jz      short loc_180011305
0x1800112d2  mov     r8d, 116h; int
0x1800112d8  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x1800112df  mov     rcx, [rbx]; this
0x1800112e2  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800112e7  mov     [rsp+0C8h+pExceptionObject], rbx
0x1800112ec  test    rbx, rbx
0x1800112ef  jz      short loc_1800112F4
0x1800112f1  inc     dword ptr [rbx+8]
0x1800112f4  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800112fb  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180011300  call    _CxxThrowException_0
0x180011305  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001130c  lea     rcx, [rsp+0C8h+var_88]; this
0x180011311  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180011316  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001131d  lea     rcx, [rsp+0C8h+var_88]; pExceptionObject
0x180011322  call    _CxxThrowException_0
0x180011328  mov     ecx, 28h ; '('; unsigned __int64
0x18001132d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011332  test    rax, rax
0x180011335  jz      short loc_18001135C
0x180011337  mov     rcx, [r14]
0x18001133a  mov     [rsp+0C8h+arg_0], rcx
0x180011342  test    rcx, rcx
0x180011345  jz      short loc_18001134A
0x180011347  inc     dword ptr [rcx+8]
0x18001134a  lea     rdx, [rsp+0C8h+arg_0]
0x180011352  mov     rcx, rax
0x180011355  call    ??0RollbackHidden@@QEAA@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@Z; RollbackHidden::RollbackHidden(SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>)
0x18001135a  jmp     short loc_18001135F
0x18001135c  mov     rax, rdi
0x18001135f  mov     rdx, rax
0x180011362  lea     rcx, [rsp+0C8h+arg_18]
0x18001136a  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x18001136f  lea     rdx, [rsp+0C8h+arg_18]
0x180011377  mov     rcx, r15
0x18001137a  call    ?AddToRollback@FileSystemImage@@QEAAXV?$SmartClassPtr@VRollbackBase@@V1@@@@Z; FileSystemImage::AddToRollback(SmartClassPtr<RollbackBase,RollbackBase>)
0x18001137f  test    r12w, r12w
0x180011383  setnz   dl
0x180011386  mov     rax, [r14]
0x180011389  mov     rcx, [rax]
0x18001138c  mov     [rcx+0B1h], dl
0x180011392  jmp     short loc_1800113C2
0x180011394  mov     esi, dword ptr [rsp+0C8h+arg_0]
0x18001139b  test    esi, esi
0x18001139d  jns     short loc_1800113BD
0x18001139f  mov     rax, [rsp+0C8h+var_98]
0x1800113a4  mov     rcx, [rax]
0x1800113a7  mov     rcx, [rcx]
0x1800113aa  mov     r8b, 1; bool
0x1800113ad  mov     edx, [rsp+0C8h+arg_10]; unsigned int
0x1800113b4  mov     rcx, [rcx+40h]; this
0x1800113b8  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x1800113bd  mov     rbx, [rsp+0C8h+var_A8]
0x1800113c2  mov     rcx, rbx; this
0x1800113c5  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x1800113ca  nop
0x1800113cb  lea     rcx, [rsp+0C8h+var_90]; this
0x1800113d0  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x1800113d5  mov     eax, esi
0x1800113d7  mov     rbx, [rsp+0C8h+arg_8]
0x1800113df  add     rsp, 0A0h
0x1800113e6  pop     r15
0x1800113e8  pop     r14
0x1800113ea  pop     r12
0x1800113ec  pop     rdi
0x1800113ed  pop     rsi
0x1800113ee  retn
```
