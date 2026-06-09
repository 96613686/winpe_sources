# CMsftFileSystemImage::Exists(ushort *,FsiItemType *)

- ea: `0x180056f30`
- end: `0x18005719a`
- name: `?Exists@CMsftFileSystemImage@@UEAAJPEAGPEAW4FsiItemType@@@Z`
- size: `618`
- prototype: `int(CMsftFileSystemImage *__hidden this, unsigned __int16 *, enum FsiItemType *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003a80`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x18004640c`
- `0x180056f30`

## string_xrefs

- `0x18005701e`: `fullPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CMsftFileSystemImage::Exists(CMsftFileSystemImage *this, unsigned __int16 *a2, enum FsiItemType *a3)
{
  unsigned int v6; // esi
  __int64 v7; // rdi
  __int64 v8; // rax
  CIMAPIException *v9; // rax
  CIMAPIException **v10; // rbx
  CIMAPIException *v11; // rax
  CIMAPIException **v12; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-E8h] BYREF
  CIMAPIException **v15; // [rsp+28h] [rbp-E0h] BYREF
  _BYTE v16[88]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v17[128]; // [rsp+88h] [rbp-80h] BYREF
  CIMAPIException **v18; // [rsp+110h] [rbp+8h] BYREF
  char *v19; // [rsp+120h] [rbp+18h]
  char v20; // [rsp+128h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v20, "CMsftFileSystemImage::Exists");
  ImapiClearErrorInfo();
  v19 = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
  if ( !a3 )
  {
    v11 = (CIMAPIException *)operator new(0x58u);
    v18 = (CIMAPIException **)v11;
    if ( v11 )
      v11 = CIMAPIException::CIMAPIException(v11, -2147467261, L"itemType");
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v18, v11);
    v12 = v18;
    if ( v18 && *v18 )
    {
      CIMAPIException::SetCodeRefInfo(
        *v18,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
        561);
      v15 = v12;
      if ( v12 )
        ++*((_DWORD *)v12 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v15;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v17, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v17;
  }
  *a3 = FsiItemNotFound;
  v6 = ValidateStringPointer(a2, 1u, 0x10000u);
  if ( v6 == -1062555391 || (v6 = ValidateStringPointer(a2, 1u, 0x10000u), v6 == -2147467261) )
  {
    v9 = (CIMAPIException *)operator new(0x58u);
    v18 = (CIMAPIException **)v9;
    if ( v9 )
      v9 = CIMAPIException::CIMAPIException(v9, v6, L"fullPath");
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v18, v9);
    v10 = v18;
    if ( v18 && *v18 )
    {
      CIMAPIException::SetCodeRefInfo(
        *v18,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
        566);
      pExceptionObject = v10;
      if ( v10 )
        ++*((_DWORD *)v10 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v16, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v16;
  }
  if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
  {
    v7 = **((_QWORD **)this + 26);
    v8 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v18,
           a2);
    *a3 = FileSystemImage::Exists(v7, v8);
  }
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v20);
  return v6;
}

```

## disassembly

```asm
0x180056f30  mov     rax, rsp
0x180056f33  mov     [rax+10h], rbx
0x180056f37  push    rsi
0x180056f38  push    rdi
0x180056f39  push    r13
0x180056f3b  push    r14
0x180056f3d  push    r15
0x180056f3f  sub     rsp, 0E0h
0x180056f46  mov     r14, r8
0x180056f49  mov     r15, rdx
0x180056f4c  mov     r13, rcx
0x180056f4f  lea     rdx, aCmsftfilesyste_31; "CMsftFileSystemImage::Exists"
0x180056f56  lea     rcx, [rax+20h]; this
0x180056f5a  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180056f5f  nop
0x180056f60  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180056f65  nop
0x180056f66  lea     rbx, [r13+50h]
0x180056f6a  mov     [rsp+108h+arg_10], rbx
0x180056f72  mov     rcx, rbx; this
0x180056f75  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180056f7a  test    r14, r14
0x180056f7d  jz      loc_1800570AA
0x180056f83  mov     dword ptr [r14], 0
0x180056f8a  mov     edi, 1
0x180056f8f  mov     r8d, 10000h; unsigned __int64
0x180056f95  mov     edx, edi; unsigned __int64
0x180056f97  mov     rcx, r15; pbstr
0x180056f9a  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180056f9f  mov     esi, eax
0x180056fa1  cmp     eax, 0C0AAB101h
0x180056fa6  jz      short loc_180057007
0x180056fa8  mov     r8d, 10000h; unsigned __int64
0x180056fae  mov     edx, edi; unsigned __int64
0x180056fb0  mov     rcx, r15; pbstr
0x180056fb3  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180056fb8  mov     esi, eax
0x180056fba  cmp     eax, 80004003h
0x180056fbf  jz      short loc_180057007
0x180056fc1  mov     r8d, 10000h; unsigned __int64
0x180056fc7  mov     edx, edi; unsigned __int64
0x180056fc9  mov     rcx, r15; pbstr
0x180056fcc  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180056fd1  test    eax, eax
0x180056fd3  jns     short loc_180056FDA
0x180056fd5  jmp     loc_18005716A
0x180056fda  mov     rax, [r13+0D0h]
0x180056fe1  mov     rdi, [rax]
0x180056fe4  mov     rdx, r15
0x180056fe7  lea     rcx, [rsp+108h+arg_0]
0x180056fef  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180056ff4  mov     rdx, rax
0x180056ff7  mov     rcx, rdi
0x180056ffa  call    ?Exists@FileSystemImage@@QEAA?AW4FsiItemType@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; FileSystemImage::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x180056fff  mov     [r14], eax
0x180057002  jmp     loc_18005716A
0x180057007  mov     ecx, 58h ; 'X'; unsigned __int64
0x18005700c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180057011  mov     [rsp+108h+arg_0], rax
0x180057019  test    rax, rax
0x18005701c  jz      short loc_180057030
0x18005701e  lea     r8, aFullpath; "fullPath"
0x180057025  mov     edx, esi; int
0x180057027  mov     rcx, rax; this
0x18005702a  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18005702f  nop
0x180057030  mov     rdx, rax
0x180057033  lea     rcx, [rsp+108h+arg_0]
0x18005703b  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180057040  nop
0x180057041  mov     rbx, [rsp+108h+arg_0]
0x180057049  test    rbx, rbx
0x18005704c  jz      short loc_180057087
0x18005704e  cmp     qword ptr [rbx], 0
0x180057052  jz      short loc_180057087
0x180057054  mov     r8d, 236h; int
0x18005705a  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180057061  mov     rcx, [rbx]; this
0x180057064  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180057069  mov     [rsp+108h+pExceptionObject], rbx
0x18005706e  test    rbx, rbx
0x180057071  jz      short loc_180057076
0x180057073  add     [rbx+8], edi
0x180057076  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18005707d  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180057082  call    _CxxThrowException_0
0x180057087  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18005708e  lea     rcx, [rsp+108h+var_D8]; this
0x180057093  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180057098  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18005709f  lea     rcx, [rsp+108h+var_D8]; pExceptionObject
0x1800570a4  call    _CxxThrowException_0
0x1800570aa  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800570af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800570b4  mov     [rsp+108h+arg_0], rax
0x1800570bc  test    rax, rax
0x1800570bf  jz      short loc_1800570D6
0x1800570c1  lea     r8, aItemtype; "itemType"
0x1800570c8  mov     edx, 80004003h; int
0x1800570cd  mov     rcx, rax; this
0x1800570d0  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800570d5  nop
0x1800570d6  mov     rdx, rax
0x1800570d9  lea     rcx, [rsp+108h+arg_0]
0x1800570e1  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800570e6  nop
0x1800570e7  mov     rbx, [rsp+108h+arg_0]
0x1800570ef  test    rbx, rbx
0x1800570f2  jz      short loc_180057132
0x1800570f4  cmp     qword ptr [rbx], 0
0x1800570f8  jz      short loc_180057132
0x1800570fa  mov     r8d, 231h; int
0x180057100  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180057107  mov     rcx, [rbx]; this
0x18005710a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18005710f  mov     [rsp+108h+var_E0], rbx
0x180057114  test    rbx, rbx
0x180057117  jz      short loc_180057121
0x180057119  mov     edi, 1
0x18005711e  add     [rbx+8], edi
0x180057121  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180057128  lea     rcx, [rsp+108h+var_E0]; pExceptionObject
0x18005712d  call    _CxxThrowException_0
0x180057132  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180057139  lea     rcx, [rsp+108h+var_80]; this
0x180057141  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180057146  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18005714d  lea     rcx, [rsp+108h+var_80]; pExceptionObject
0x180057155  call    _CxxThrowException_0
0x18005715b  mov     esi, dword ptr [rsp+108h+arg_0]
0x180057162  mov     rbx, [rsp+108h+arg_10]
0x18005716a  mov     rcx, rbx; this
0x18005716d  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180057172  nop
0x180057173  lea     rcx, [rsp+108h+arg_18]; this
0x18005717b  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180057180  mov     eax, esi
0x180057182  mov     rbx, [rsp+108h+arg_8]
0x18005718a  add     rsp, 0E0h
0x180057191  pop     r15
0x180057193  pop     r14
0x180057195  pop     r13
0x180057197  pop     rdi
0x180057198  pop     rsi
0x180057199  retn
```
