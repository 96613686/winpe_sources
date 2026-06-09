# CFsiDirectoryItem::AddTree(ushort *,short)

- ea: `0x18003d360`
- end: `0x18003d538`
- name: `?AddTree@CFsiDirectoryItem@@UEAAJPEAGF@Z`
- size: `472`
- prototype: `int(CFsiDirectoryItem *__hidden this, unsigned __int16 *, __int16)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003a80`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x180005d7c`
- `0x18000960c`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x18003d360`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18003d400`
- `KERNEL32!GetTickCount` at `0x18003d444`
- `KERNEL32!GetTickCount` at `0x18003d400`
- `KERNEL32!GetTickCount` at `0x18003d444`

## string_xrefs

- `0x18003d37e`: `CFsiDirectoryItem::AddTree`
- `0x18003d471`: `sourceDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CFsiDirectoryItem::AddTree(CFsiDirectoryItem *this, unsigned __int16 *a2, __int16 a3)
{
  unsigned int v5; // esi
  DWORD TickCount; // r13d
  unsigned int v7; // r12d
  __int64 v8; // rax
  __int64 v9; // rbx
  CIMAPIException *v10; // rax
  CIMAPIException *v11; // rax
  CIMAPIException **v12; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-A8h] BYREF
  char v15[8]; // [rsp+28h] [rbp-A0h] BYREF
  _BYTE v16[152]; // [rsp+30h] [rbp-98h] BYREF
  CIMAPIException **v17; // [rsp+D0h] [rbp+8h] BYREF
  __int16 v18; // [rsp+E0h] [rbp+18h]
  char *v19; // [rsp+E8h] [rbp+20h]

  v18 = a3;
  MethodTrace::MethodTrace((MethodTrace *)v15, "CFsiDirectoryItem::AddTree");
  ImapiClearErrorInfo();
  v19 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
  v5 = ValidateStringPointer(a2, 1u, 0x10000u);
  if ( v5 == -1062555391 || (v5 = ValidateStringPointer(a2, 1u, 0x10000u), v5 == -2147467261) )
  {
    v10 = (CIMAPIException *)operator new(0x58u);
    v17 = (CIMAPIException **)v10;
    if ( v10 )
      v11 = CIMAPIException::CIMAPIException(v10, v5, L"sourceDirectory");
    else
      v11 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v17, v11);
    v12 = v17;
    if ( v17 && *v17 )
    {
      CIMAPIException::SetCodeRefInfo(*v17, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 723);
      pExceptionObject = v12;
      if ( v12 )
        ++*((_DWORD *)v12 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v16, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v16;
  }
  if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
  {
    TickCount = GetTickCount();
    v7 = 2;
    if ( v18 )
      v7 = 0;
    v8 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v17,
           a2);
    CFsiDirectoryItem::AddTreeEx((char *)this - 80, v8, v7);
    v9 = *(_QWORD *)(**((_QWORD **)this + 8) + 64LL);
    *(_DWORD *)(v9 + 808) += GetTickCount() - TickCount;
  }
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)v15);
  return v5;
}

```

## disassembly

```asm
0x18003d360  mov     [rsp+arg_10], r8w
0x18003d366  push    rbx
0x18003d367  push    rsi
0x18003d368  push    rdi
0x18003d369  push    r12
0x18003d36b  push    r13
0x18003d36d  push    r14
0x18003d36f  push    r15
0x18003d371  sub     rsp, 90h
0x18003d378  mov     rbx, rdx
0x18003d37b  mov     r15, rcx
0x18003d37e  lea     rdx, aCfsidirectoryi_3; "CFsiDirectoryItem::AddTree"
0x18003d385  lea     rcx, [rsp+0C8h+var_A0]; this
0x18003d38a  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003d38f  nop
0x18003d390  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003d395  nop
0x18003d396  lea     r14, [r15-50h]
0x18003d39a  mov     [rsp+0C8h+arg_18], r14
0x18003d3a2  mov     rcx, r14; this
0x18003d3a5  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003d3aa  mov     edi, 10000h
0x18003d3af  mov     r8d, edi; unsigned __int64
0x18003d3b2  mov     r12d, 1
0x18003d3b8  mov     edx, r12d; unsigned __int64
0x18003d3bb  mov     rcx, rbx; pbstr
0x18003d3be  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003d3c3  mov     esi, eax
0x18003d3c5  cmp     eax, 0C0AAB101h
0x18003d3ca  jz      loc_18003D458
0x18003d3d0  mov     r8d, edi; unsigned __int64
0x18003d3d3  mov     edx, r12d; unsigned __int64
0x18003d3d6  mov     rcx, rbx; pbstr
0x18003d3d9  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003d3de  mov     esi, eax
0x18003d3e0  cmp     eax, 80004003h
0x18003d3e5  jz      short loc_18003D458
0x18003d3e7  mov     r8d, edi; unsigned __int64
0x18003d3ea  mov     edx, r12d; unsigned __int64
0x18003d3ed  mov     rcx, rbx; pbstr
0x18003d3f0  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003d3f5  xor     edi, edi
0x18003d3f7  test    eax, eax
0x18003d3f9  jns     short loc_18003D400
0x18003d3fb  jmp     loc_18003D510
0x18003d400  call    cs:__imp_GetTickCount
0x18003d406  mov     r13d, eax
0x18003d409  mov     r12d, 2
0x18003d40f  cmp     di, [rsp+0C8h+arg_10]
0x18003d417  cmovnz  r12d, edi
0x18003d41b  mov     rdx, rbx
0x18003d41e  lea     rcx, [rsp+0C8h+arg_0]
0x18003d426  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003d42b  mov     r8d, r12d
0x18003d42e  mov     rdx, rax
0x18003d431  mov     rcx, r14
0x18003d434  call    ?AddTreeEx@CFsiDirectoryItem@@AEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; CFsiDirectoryItem::AddTreeEx(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x18003d439  mov     rax, [r15+40h]
0x18003d43d  mov     rcx, [rax]
0x18003d440  mov     rbx, [rcx+40h]
0x18003d444  call    cs:__imp_GetTickCount
0x18003d44a  sub     eax, r13d
0x18003d44d  add     [rbx+328h], eax
0x18003d453  jmp     loc_18003D510
0x18003d458  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003d45d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d462  mov     [rsp+0C8h+arg_0], rax
0x18003d46a  xor     edi, edi
0x18003d46c  test    rax, rax
0x18003d46f  jz      short loc_18003D484
0x18003d471  lea     r8, aSourcedirector; "sourceDirectory"
0x18003d478  mov     edx, esi; int
0x18003d47a  mov     rcx, rax; this
0x18003d47d  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003d482  jmp     short loc_18003D487
0x18003d484  mov     rax, rdi
0x18003d487  mov     rdx, rax
0x18003d48a  lea     rcx, [rsp+0C8h+arg_0]
0x18003d492  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003d497  nop
0x18003d498  mov     rbx, [rsp+0C8h+arg_0]
0x18003d4a0  test    rbx, rbx
0x18003d4a3  jz      short loc_18003D4DE
0x18003d4a5  cmp     [rbx], rdi
0x18003d4a8  jz      short loc_18003D4DE
0x18003d4aa  mov     r8d, 2D3h; int
0x18003d4b0  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003d4b7  mov     rcx, [rbx]; this
0x18003d4ba  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003d4bf  mov     [rsp+0C8h+pExceptionObject], rbx
0x18003d4c4  test    rbx, rbx
0x18003d4c7  jz      short loc_18003D4CD
0x18003d4c9  add     [rbx+8], r12d
0x18003d4cd  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003d4d4  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18003d4d9  call    _CxxThrowException_0
0x18003d4de  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003d4e5  lea     rcx, [rsp+0C8h+var_98]; this
0x18003d4ea  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003d4ef  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003d4f6  lea     rcx, [rsp+0C8h+var_98]; pExceptionObject
0x18003d4fb  call    _CxxThrowException_0
0x18003d501  mov     esi, dword ptr [rsp+0C8h+arg_0]
0x18003d508  mov     r14, [rsp+0C8h+arg_18]
0x18003d510  mov     rcx, r14; this
0x18003d513  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003d518  nop
0x18003d519  lea     rcx, [rsp+0C8h+var_A0]; this
0x18003d51e  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003d523  mov     eax, esi
0x18003d525  add     rsp, 90h
0x18003d52c  pop     r15
0x18003d52e  pop     r14
0x18003d530  pop     r13
0x18003d532  pop     r12
0x18003d534  pop     rdi
0x18003d535  pop     rsi
0x18003d536  pop     rbx
0x18003d537  retn
```
