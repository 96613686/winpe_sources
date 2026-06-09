# CFsiDirectoryItem::AddTreeWithNamedStreams(ushort *,short)

- ea: `0x18003d540`
- end: `0x18003d733`
- name: `?AddTreeWithNamedStreams@CFsiDirectoryItem@@UEAAJPEAGF@Z`
- size: `499`
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
- `0x18003d540`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18003d5e4`
- `KERNEL32!GetTickCount` at `0x18003d63f`
- `KERNEL32!GetTickCount` at `0x18003d5e4`
- `KERNEL32!GetTickCount` at `0x18003d63f`

## string_xrefs

- `0x18003d66c`: `sourceDirectory`
- `0x18003d55e`: `CFsiDirectoryItem::AddTreeWithNamedStreams`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CFsiDirectoryItem::AddTreeWithNamedStreams(
        CFsiDirectoryItem *this,
        unsigned __int16 *a2,
        __int16 a3)
{
  unsigned int v5; // ebx
  DWORD TickCount; // r13d
  unsigned int v7; // r12d
  __int64 v8; // rax
  __int64 v9; // rdi
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
  MethodTrace::MethodTrace((MethodTrace *)v15, "CFsiDirectoryItem::AddTreeWithNamedStreams");
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
      CIMAPIException::SetCodeRefInfo(*v17, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 911);
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
    v7 = 10;
    if ( v18 )
      v7 = 8;
    v8 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v17,
           a2);
    CFsiDirectoryItem::AddTreeEx((char *)this - 80, v8, v7);
    v9 = *(_QWORD *)(**((_QWORD **)this + 8) + 64LL);
    if ( (*(_BYTE *)(v9 + 24) & 4) == 0 || *(_DWORD *)(v9 + 32) < 0x200u )
      v5 = 11186527;
    *(_DWORD *)(v9 + 808) += GetTickCount() - TickCount;
  }
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)v15);
  return v5;
}

```

## disassembly

```asm
0x18003d540  mov     [rsp+arg_10], r8w
0x18003d546  push    rbx
0x18003d547  push    rsi
0x18003d548  push    rdi
0x18003d549  push    r12
0x18003d54b  push    r13
0x18003d54d  push    r14
0x18003d54f  push    r15
0x18003d551  sub     rsp, 90h
0x18003d558  mov     r14, rdx
0x18003d55b  mov     r15, rcx
0x18003d55e  lea     rdx, aCfsidirectoryi_2; "CFsiDirectoryItem::AddTreeWithNamedStre"...
0x18003d565  lea     rcx, [rsp+0C8h+var_A0]; this
0x18003d56a  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003d56f  nop
0x18003d570  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003d575  nop
0x18003d576  lea     rsi, [r15-50h]
0x18003d57a  mov     [rsp+0C8h+arg_18], rsi
0x18003d582  mov     rcx, rsi; this
0x18003d585  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003d58a  mov     edi, 10000h
0x18003d58f  mov     r8d, edi; unsigned __int64
0x18003d592  mov     r12d, 1
0x18003d598  mov     edx, r12d; unsigned __int64
0x18003d59b  mov     rcx, r14; pbstr
0x18003d59e  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003d5a3  mov     ebx, eax
0x18003d5a5  cmp     eax, 0C0AAB101h
0x18003d5aa  jz      loc_18003D653
0x18003d5b0  mov     r8d, edi; unsigned __int64
0x18003d5b3  mov     edx, r12d; unsigned __int64
0x18003d5b6  mov     rcx, r14; pbstr
0x18003d5b9  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003d5be  mov     ebx, eax
0x18003d5c0  cmp     eax, 80004003h
0x18003d5c5  jz      loc_18003D653
0x18003d5cb  mov     r8d, edi; unsigned __int64
0x18003d5ce  mov     edx, r12d; unsigned __int64
0x18003d5d1  mov     rcx, r14; pbstr
0x18003d5d4  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18003d5d9  xor     edi, edi
0x18003d5db  test    eax, eax
0x18003d5dd  jns     short loc_18003D5E4
0x18003d5df  jmp     loc_18003D70B
0x18003d5e4  call    cs:__imp_GetTickCount
0x18003d5ea  mov     r13d, eax
0x18003d5ed  mov     eax, 8
0x18003d5f2  lea     r12d, [rax+2]
0x18003d5f6  cmp     di, [rsp+0C8h+arg_10]
0x18003d5fe  cmovnz  r12d, eax
0x18003d602  mov     rdx, r14
0x18003d605  lea     rcx, [rsp+0C8h+arg_0]
0x18003d60d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003d612  mov     r8d, r12d
0x18003d615  mov     rdx, rax
0x18003d618  mov     rcx, rsi
0x18003d61b  call    ?AddTreeEx@CFsiDirectoryItem@@AEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; CFsiDirectoryItem::AddTreeEx(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x18003d620  mov     rax, [r15+40h]
0x18003d624  mov     rcx, [rax]
0x18003d627  mov     rdi, [rcx+40h]
0x18003d62b  test    byte ptr [rdi+18h], 4
0x18003d62f  jz      short loc_18003D63A
0x18003d631  cmp     dword ptr [rdi+20h], 200h
0x18003d638  jnb     short loc_18003D63F
0x18003d63a  mov     ebx, 0AAB15Fh
0x18003d63f  call    cs:__imp_GetTickCount
0x18003d645  sub     eax, r13d
0x18003d648  add     [rdi+328h], eax
0x18003d64e  jmp     loc_18003D70B
0x18003d653  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003d658  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d65d  mov     [rsp+0C8h+arg_0], rax
0x18003d665  xor     edi, edi
0x18003d667  test    rax, rax
0x18003d66a  jz      short loc_18003D67F
0x18003d66c  lea     r8, aSourcedirector; "sourceDirectory"
0x18003d673  mov     edx, ebx; int
0x18003d675  mov     rcx, rax; this
0x18003d678  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003d67d  jmp     short loc_18003D682
0x18003d67f  mov     rax, rdi
0x18003d682  mov     rdx, rax
0x18003d685  lea     rcx, [rsp+0C8h+arg_0]
0x18003d68d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003d692  nop
0x18003d693  mov     rbx, [rsp+0C8h+arg_0]
0x18003d69b  test    rbx, rbx
0x18003d69e  jz      short loc_18003D6D9
0x18003d6a0  cmp     [rbx], rdi
0x18003d6a3  jz      short loc_18003D6D9
0x18003d6a5  mov     r8d, 38Fh; int
0x18003d6ab  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18003d6b2  mov     rcx, [rbx]; this
0x18003d6b5  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003d6ba  mov     [rsp+0C8h+pExceptionObject], rbx
0x18003d6bf  test    rbx, rbx
0x18003d6c2  jz      short loc_18003D6C8
0x18003d6c4  add     [rbx+8], r12d
0x18003d6c8  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003d6cf  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18003d6d4  call    _CxxThrowException_0
0x18003d6d9  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003d6e0  lea     rcx, [rsp+0C8h+var_98]; this
0x18003d6e5  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003d6ea  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003d6f1  lea     rcx, [rsp+0C8h+var_98]; pExceptionObject
0x18003d6f6  call    _CxxThrowException_0
0x18003d6fc  mov     ebx, dword ptr [rsp+0C8h+arg_0]
0x18003d703  mov     rsi, [rsp+0C8h+arg_18]
0x18003d70b  mov     rcx, rsi; this
0x18003d70e  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003d713  nop
0x18003d714  lea     rcx, [rsp+0C8h+var_A0]; this
0x18003d719  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003d71e  mov     eax, ebx
0x18003d720  add     rsp, 90h
0x18003d727  pop     r15
0x18003d729  pop     r14
0x18003d72b  pop     r13
0x18003d72d  pop     r12
0x18003d72f  pop     rdi
0x18003d730  pop     rsi
0x18003d731  pop     rbx
0x18003d732  retn
```
