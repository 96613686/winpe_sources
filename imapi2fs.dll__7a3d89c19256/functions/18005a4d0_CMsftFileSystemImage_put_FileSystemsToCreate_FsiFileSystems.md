# CMsftFileSystemImage::put_FileSystemsToCreate(FsiFileSystems)

- ea: `0x18005a4d0`
- end: `0x18005a6ef`
- name: `?put_FileSystemsToCreate@CMsftFileSystemImage@@UEAAJW4FsiFileSystems@@@Z`
- size: `543`
- prototype: `int(CMsftFileSystemImage *__hidden this, enum FsiFileSystems)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

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
- `0x18002d4e4`
- `0x180048248`
- `0x18004938c`
- `0x18005a4d0`

## string_xrefs

- `0x18005a4e7`: `CMsftFileSystemImage::put_FileSystemsToCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMsftFileSystemImage::put_FileSystemsToCreate(CMsftFileSystemImage *this, enum FsiFileSystems a2)
{
  unsigned int v4; // ebx
  bool v5; // al
  CIMAPIException *v6; // rax
  CIMAPIException **v7; // rbx
  FileSystemImage **v8; // rax
  FileSystemImage *v9; // rcx
  CIMAPIException *v10; // rax
  CIMAPIException **v11; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-D8h] BYREF
  CIMAPIException **v14; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v15[88]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v16[112]; // [rsp+88h] [rbp-70h] BYREF
  CIMAPIException **v17; // [rsp+100h] [rbp+8h] BYREF
  char *v18; // [rsp+110h] [rbp+18h]
  char v19; // [rsp+118h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v19, "CMsftFileSystemImage::put_FileSystemsToCreate");
  ImapiClearErrorInfo();
  v4 = 0;
  v18 = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
  v5 = ValidateFileSystemIdParam(a2, 0);
  try
  {
    if ( !v5 )
    {
      v6 = (CIMAPIException *)operator new(0x58u);
      v17 = (CIMAPIException **)v6;
      if ( v6 )
        v6 = CIMAPIException::CIMAPIException(v6, -1062555391, L"newVal");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v17, v6);
      v7 = v17;
      if ( v17 && *v17 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v17,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          362);
        pExceptionObject = v7;
        if ( v7 )
          ++*((_DWORD *)v7 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v15,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v15;
    }
    v8 = (FileSystemImage **)*((_QWORD *)this + 26);
    v9 = *v8;
    if ( *((_BYTE *)*v8 + 792) == 1 && a2 != *((_DWORD *)v9 + 6) )
    {
      v10 = (CIMAPIException *)operator new(0x58u);
      v17 = (CIMAPIException **)v10;
      if ( v10 )
        v10 = CIMAPIException::CIMAPIException(v10, -1062555293);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v17, v10);
      v11 = v17;
      if ( v17 && *v17 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v17,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          368);
        v14 = v11;
        if ( v11 )
          ++*((_DWORD *)v11 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v14;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v16,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v16;
    }
    if ( (a2 & 4) == 0 && (*((_DWORD *)v9 + 95) || *((_DWORD *)v9 + 97)) )
      v4 = 11186527;
    FileSystemImage::SetFileSystemsToCreate(v9, a2);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_MsftFileSystemImage);
  }
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v19);
  return v4;
}

```

## disassembly

```asm
0x18005a4d0  mov     rax, rsp
0x18005a4d3  mov     [rax+10h], rbx
0x18005a4d7  push    rsi
0x18005a4d8  push    rdi
0x18005a4d9  push    r14
0x18005a4db  sub     rsp, 0E0h
0x18005a4e2  mov     edi, edx
0x18005a4e4  mov     r14, rcx
0x18005a4e7  lea     rdx, aCmsftfilesyste_3; "CMsftFileSystemImage::put_FileSystemsTo"...
0x18005a4ee  lea     rcx, [rax+20h]; this
0x18005a4f2  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18005a4f7  nop
0x18005a4f8  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18005a4fd  xor     ebx, ebx
0x18005a4ff  lea     rsi, [r14+50h]
0x18005a503  mov     [rsp+0F8h+arg_10], rsi
0x18005a50b  mov     rcx, rsi; this
0x18005a50e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18005a513  xor     edx, edx; bool
0x18005a515  mov     ecx, edi; enum FsiFileSystems
0x18005a517  call    ?ValidateFileSystemIdParam@@YA_NW4FsiFileSystems@@_N@Z; ValidateFileSystemIdParam(FsiFileSystems,bool)
0x18005a51c  test    al, al
0x18005a51e  jnz     loc_18005A5C8
0x18005a524  lea     ecx, [rbx+58h]; unsigned __int64
0x18005a527  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a52c  mov     [rsp+0F8h+arg_0], rax
0x18005a534  test    rax, rax
0x18005a537  jz      short loc_18005A54E
0x18005a539  lea     r8, aNewval; "newVal"
0x18005a540  mov     edx, 0C0AAB101h; int
0x18005a545  mov     rcx, rax; this
0x18005a548  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18005a54d  nop
0x18005a54e  mov     rdx, rax
0x18005a551  lea     rcx, [rsp+0F8h+arg_0]
0x18005a559  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18005a55e  nop
0x18005a55f  mov     rbx, [rsp+0F8h+arg_0]
0x18005a567  test    rbx, rbx
0x18005a56a  jz      short loc_18005A5A5
0x18005a56c  cmp     qword ptr [rbx], 0
0x18005a570  jz      short loc_18005A5A5
0x18005a572  mov     r8d, 16Ah; int
0x18005a578  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x18005a57f  mov     rcx, [rbx]; this
0x18005a582  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18005a587  mov     [rsp+0F8h+pExceptionObject], rbx
0x18005a58c  test    rbx, rbx
0x18005a58f  jz      short loc_18005A594
0x18005a591  inc     dword ptr [rbx+8]
0x18005a594  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18005a59b  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18005a5a0  call    _CxxThrowException_0
0x18005a5a5  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18005a5ac  lea     rcx, [rsp+0F8h+var_C8]; this
0x18005a5b1  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18005a5b6  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18005a5bd  lea     rcx, [rsp+0F8h+var_C8]; pExceptionObject
0x18005a5c2  call    _CxxThrowException_0
0x18005a5c8  mov     rax, [r14+0D0h]
0x18005a5cf  mov     rcx, [rax]; this
0x18005a5d2  cmp     byte ptr [rcx+318h], 1
0x18005a5d9  jnz     loc_18005A68D
0x18005a5df  cmp     edi, [rcx+18h]
0x18005a5e2  jz      loc_18005A68D
0x18005a5e8  mov     ecx, 58h ; 'X'; unsigned __int64
0x18005a5ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a5f2  mov     [rsp+0F8h+arg_0], rax
0x18005a5fa  test    rax, rax
0x18005a5fd  jz      short loc_18005A60D
0x18005a5ff  mov     edx, 0C0AAB163h; int
0x18005a604  mov     rcx, rax; this
0x18005a607  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18005a60c  nop
0x18005a60d  mov     rdx, rax
0x18005a610  lea     rcx, [rsp+0F8h+arg_0]
0x18005a618  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18005a61d  nop
0x18005a61e  mov     rbx, [rsp+0F8h+arg_0]
0x18005a626  test    rbx, rbx
0x18005a629  jz      short loc_18005A664
0x18005a62b  cmp     qword ptr [rbx], 0
0x18005a62f  jz      short loc_18005A664
0x18005a631  mov     r8d, 170h; int
0x18005a637  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x18005a63e  mov     rcx, [rbx]; this
0x18005a641  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18005a646  mov     [rsp+0F8h+var_D0], rbx
0x18005a64b  test    rbx, rbx
0x18005a64e  jz      short loc_18005A653
0x18005a650  inc     dword ptr [rbx+8]
0x18005a653  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18005a65a  lea     rcx, [rsp+0F8h+var_D0]; pExceptionObject
0x18005a65f  call    _CxxThrowException_0
0x18005a664  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18005a66b  lea     rcx, [rsp+0F8h+var_70]; this
0x18005a673  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18005a678  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18005a67f  lea     rcx, [rsp+0F8h+var_70]; pExceptionObject
0x18005a687  call    _CxxThrowException_0
0x18005a68d  test    dil, 4
0x18005a691  jnz     short loc_18005A6AA
0x18005a693  cmp     dword ptr [rcx+17Ch], 0
0x18005a69a  ja      short loc_18005A6A5
0x18005a69c  cmp     dword ptr [rcx+184h], 0
0x18005a6a3  jbe     short loc_18005A6AA
0x18005a6a5  mov     ebx, 0AAB15Fh
0x18005a6aa  mov     edx, edi; enum FsiFileSystems
0x18005a6ac  call    ?SetFileSystemsToCreate@FileSystemImage@@QEAAXW4FsiFileSystems@@@Z; FileSystemImage::SetFileSystemsToCreate(FsiFileSystems)
0x18005a6b1  nop
0x18005a6b2  jmp     short loc_18005A6C3
0x18005a6b4  mov     ebx, dword ptr [rsp+0F8h+arg_0]
0x18005a6bb  mov     rsi, [rsp+0F8h+arg_10]
0x18005a6c3  mov     rcx, rsi; this
0x18005a6c6  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18005a6cb  nop
0x18005a6cc  lea     rcx, [rsp+0F8h+arg_18]; this
0x18005a6d4  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18005a6d9  mov     eax, ebx
0x18005a6db  mov     rbx, [rsp+0F8h+arg_8]
0x18005a6e3  add     rsp, 0E0h
0x18005a6ea  pop     r14
0x18005a6ec  pop     rdi
0x18005a6ed  pop     rsi
0x18005a6ee  retn
```
