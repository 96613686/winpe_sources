# CMsftFileSystemImage::put_WorkingDirectory(ushort *)

- ea: `0x18005aea0`
- end: `0x18005b046`
- name: `?put_WorkingDirectory@CMsftFileSystemImage@@UEAAJPEAG@Z`
- size: `422`
- prototype: `int(CMsftFileSystemImage *__hidden this, unsigned __int16 *)`
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
- `0x18001d8a8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x18005aea0`

## string_xrefs

- `0x18005aebc`: `CMsftFileSystemImage::put_WorkingDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CMsftFileSystemImage::put_WorkingDirectory(CMsftFileSystemImage *this, unsigned __int16 *a2)
{
  ImapiComObject *v4; // rdi
  unsigned int v5; // ebx
  FileSystemImage *v6; // r14
  void *v7; // rax
  CIMAPIException *v8; // rax
  CIMAPIException **v9; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v12[128]; // [rsp+28h] [rbp-80h] BYREF
  CIMAPIException **v13; // [rsp+B0h] [rbp+8h] BYREF
  char *v14; // [rsp+C0h] [rbp+18h]
  char v15; // [rsp+C8h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v15, "CMsftFileSystemImage::put_WorkingDirectory");
  ImapiClearErrorInfo();
  v4 = (CMsftFileSystemImage *)((char *)this + 80);
  v14 = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
  v5 = ValidateStringPointer(a2, 1u, 0x10000u);
  if ( v5 == -1062555391 || (v5 = ValidateStringPointer(a2, 1u, 0x10000u), v5 == -2147467261) )
  {
    v8 = (CIMAPIException *)operator new(0x58u);
    v13 = (CIMAPIException **)v8;
    if ( v8 )
      v8 = CIMAPIException::CIMAPIException(v8, v5, L"newVal");
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v13, v8);
    v9 = v13;
    if ( v13 && *v13 )
    {
      CIMAPIException::SetCodeRefInfo(
        *v13,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
        283);
      pExceptionObject = v9;
      if ( v9 )
        ++*((_DWORD *)v9 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v12, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v12;
  }
  if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
  {
    v6 = (FileSystemImage *)**((_QWORD **)this + 26);
    v7 = (void *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                   &v13,
                   a2);
    FileSystemImage::SetWorkingDirectory(v6, v7);
  }
  ImapiComObject::UnlockCS(v4);
  MethodTrace::~MethodTrace((MethodTrace *)&v15);
  return v5;
}

```

## disassembly

```asm
0x18005aea0  mov     rax, rsp
0x18005aea3  mov     [rax+10h], rbx
0x18005aea7  push    rsi
0x18005aea8  push    rdi
0x18005aea9  push    r12
0x18005aeab  push    r14
0x18005aead  push    r15
0x18005aeaf  sub     rsp, 80h
0x18005aeb6  mov     rsi, rdx
0x18005aeb9  mov     r14, rcx
0x18005aebc  lea     rdx, aCmsftfilesyste; "CMsftFileSystemImage::put_WorkingDirect"...
0x18005aec3  lea     rcx, [rax+20h]; this
0x18005aec7  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18005aecc  nop
0x18005aecd  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18005aed2  nop
0x18005aed3  lea     rdi, [r14+50h]
0x18005aed7  mov     [rsp+0A8h+arg_10], rdi
0x18005aedf  mov     rcx, rdi; this
0x18005aee2  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18005aee7  mov     r12d, 10000h
0x18005aeed  mov     r8d, r12d; unsigned __int64
0x18005aef0  mov     r15d, 1
0x18005aef6  mov     edx, r15d; unsigned __int64
0x18005aef9  mov     rcx, rsi; pbstr
0x18005aefc  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18005af01  mov     ebx, eax
0x18005af03  cmp     eax, 0C0AAB101h
0x18005af08  jz      short loc_18005AF63
0x18005af0a  mov     r8d, r12d; unsigned __int64
0x18005af0d  mov     edx, r15d; unsigned __int64
0x18005af10  mov     rcx, rsi; pbstr
0x18005af13  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18005af18  mov     ebx, eax
0x18005af1a  cmp     eax, 80004003h
0x18005af1f  jz      short loc_18005AF63
0x18005af21  mov     r8d, r12d; unsigned __int64
0x18005af24  mov     edx, r15d; unsigned __int64
0x18005af27  mov     rcx, rsi; pbstr
0x18005af2a  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18005af2f  test    eax, eax
0x18005af31  jns     short loc_18005AF38
0x18005af33  jmp     loc_18005B016
0x18005af38  mov     rax, [r14+0D0h]
0x18005af3f  mov     r14, [rax]
0x18005af42  mov     rdx, rsi
0x18005af45  lea     rcx, [rsp+0A8h+arg_0]
0x18005af4d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005af52  mov     rdx, rax; void *
0x18005af55  mov     rcx, r14; this
0x18005af58  call    ?SetWorkingDirectory@FileSystemImage@@QEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; FileSystemImage::SetWorkingDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18005af5d  nop
0x18005af5e  jmp     loc_18005B016
0x18005af63  mov     ecx, 58h ; 'X'; unsigned __int64
0x18005af68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005af6d  mov     [rsp+0A8h+arg_0], rax
0x18005af75  test    rax, rax
0x18005af78  jz      short loc_18005AF8C
0x18005af7a  lea     r8, aNewval; "newVal"
0x18005af81  mov     edx, ebx; int
0x18005af83  mov     rcx, rax; this
0x18005af86  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18005af8b  nop
0x18005af8c  mov     rdx, rax
0x18005af8f  lea     rcx, [rsp+0A8h+arg_0]
0x18005af97  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18005af9c  nop
0x18005af9d  mov     rbx, [rsp+0A8h+arg_0]
0x18005afa5  test    rbx, rbx
0x18005afa8  jz      short loc_18005AFE4
0x18005afaa  cmp     qword ptr [rbx], 0
0x18005afae  jz      short loc_18005AFE4
0x18005afb0  mov     r8d, 11Bh; int
0x18005afb6  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x18005afbd  mov     rcx, [rbx]; this
0x18005afc0  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18005afc5  mov     [rsp+0A8h+pExceptionObject], rbx
0x18005afca  test    rbx, rbx
0x18005afcd  jz      short loc_18005AFD3
0x18005afcf  add     [rbx+8], r15d
0x18005afd3  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18005afda  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18005afdf  call    _CxxThrowException_0
0x18005afe4  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18005afeb  lea     rcx, [rsp+0A8h+var_80]; this
0x18005aff0  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18005aff5  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18005affc  lea     rcx, [rsp+0A8h+var_80]; pExceptionObject
0x18005b001  call    _CxxThrowException_0
0x18005b007  mov     ebx, dword ptr [rsp+0A8h+arg_0]
0x18005b00e  mov     rdi, [rsp+0A8h+arg_10]
0x18005b016  mov     rcx, rdi; this
0x18005b019  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18005b01e  nop
0x18005b01f  lea     rcx, [rsp+0A8h+arg_18]; this
0x18005b027  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18005b02c  mov     eax, ebx
0x18005b02e  mov     rbx, [rsp+0A8h+arg_8]
0x18005b036  add     rsp, 80h
0x18005b03d  pop     r15
0x18005b03f  pop     r14
0x18005b041  pop     r12
0x18005b043  pop     rdi
0x18005b044  pop     rsi
0x18005b045  retn
```
