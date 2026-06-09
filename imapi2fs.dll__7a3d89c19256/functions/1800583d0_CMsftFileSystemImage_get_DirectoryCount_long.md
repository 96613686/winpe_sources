# CMsftFileSystemImage::get_DirectoryCount(long *)

- ea: `0x1800583d0`
- end: `0x180058514`
- name: `?get_DirectoryCount@CMsftFileSystemImage@@UEAAJPEAJ@Z`
- size: `324`
- prototype: `__int64 __fastcall(CMsftFileSystemImage *__hidden this, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

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
- `0x1800583d0`

## string_xrefs

- `0x1800583e8`: `CMsftFileSystemImage::get_DirectoryCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMsftFileSystemImage::get_DirectoryCount(CMsftFileSystemImage *this, int *a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CMsftFileSystemImage::get_DirectoryCount");
  ImapiClearErrorInfo();
  v10 = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
  if ( !a2 )
  {
    try
    {
      v4 = (CIMAPIException *)operator new(0x58u);
      v9 = (CIMAPIException **)v4;
      if ( v4 )
        v4 = CIMAPIException::CIMAPIException(v4, -2147467261, L"pVal");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v9, v4);
      v5 = v9;
      if ( v9 && *v9 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v9,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          255);
        pExceptionObject = v5;
        if ( v5 )
          ++*((_DWORD *)v5 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v8,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v8;
    }
    catch ( ... )
    {
      ExceptionDispatcher(&CLSID_MsftFileSystemImage);
    }
  }
  *a2 = 0;
  *a2 = *(_DWORD *)(**((_QWORD **)this + 26) + 368LL);
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x1800583d0  mov     rax, rsp
0x1800583d3  mov     [rax+20h], rbx
0x1800583d7  push    rsi
0x1800583d8  push    rdi
0x1800583d9  push    r14
0x1800583db  sub     rsp, 80h
0x1800583e2  mov     rsi, rdx
0x1800583e5  mov     r14, rcx
0x1800583e8  lea     rdx, aCmsftfilesyste_12; "CMsftFileSystemImage::get_DirectoryCoun"...
0x1800583ef  lea     rcx, [rax+18h]; this
0x1800583f3  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x1800583f8  nop
0x1800583f9  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x1800583fe  nop
0x1800583ff  lea     rbx, [r14+50h]
0x180058403  mov     [rsp+98h+arg_8], rbx
0x18005840b  mov     rcx, rbx; this
0x18005840e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180058413  test    rsi, rsi
0x180058416  jz      short loc_180058433
0x180058418  xor     edi, edi
0x18005841a  mov     [rsi], edi
0x18005841c  mov     rax, [r14+0D0h]
0x180058423  mov     rcx, [rax]
0x180058426  mov     eax, [rcx+170h]
0x18005842c  mov     [rsi], eax
0x18005842e  jmp     loc_1800584E8
0x180058433  mov     ecx, 58h ; 'X'; unsigned __int64
0x180058438  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005843d  mov     [rsp+98h+arg_0], rax
0x180058445  test    rax, rax
0x180058448  jz      short loc_18005845F
0x18005844a  lea     r8, aPval; "pVal"
0x180058451  mov     edx, 80004003h; int
0x180058456  mov     rcx, rax; this
0x180058459  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18005845e  nop
0x18005845f  mov     rdx, rax
0x180058462  lea     rcx, [rsp+98h+arg_0]
0x18005846a  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18005846f  nop
0x180058470  mov     rbx, [rsp+98h+arg_0]
0x180058478  test    rbx, rbx
0x18005847b  jz      short loc_1800584B6
0x18005847d  cmp     qword ptr [rbx], 0
0x180058481  jz      short loc_1800584B6
0x180058483  mov     r8d, 0FFh; int
0x180058489  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180058490  mov     rcx, [rbx]; this
0x180058493  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180058498  mov     [rsp+98h+pExceptionObject], rbx
0x18005849d  test    rbx, rbx
0x1800584a0  jz      short loc_1800584A5
0x1800584a2  inc     dword ptr [rbx+8]
0x1800584a5  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800584ac  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800584b1  call    _CxxThrowException_0
0x1800584b6  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800584bd  lea     rcx, [rsp+98h+var_70]; this
0x1800584c2  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800584c7  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800584ce  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x1800584d3  call    _CxxThrowException_0
0x1800584d9  mov     edi, dword ptr [rsp+98h+arg_0]
0x1800584e0  mov     rbx, [rsp+98h+arg_8]
0x1800584e8  mov     rcx, rbx; this
0x1800584eb  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x1800584f0  nop
0x1800584f1  lea     rcx, [rsp+98h+arg_10]; this
0x1800584f9  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x1800584fe  mov     eax, edi
0x180058500  mov     rbx, [rsp+98h+arg_18]
0x180058508  add     rsp, 80h
0x18005850f  pop     r14
0x180058511  pop     rdi
0x180058512  pop     rsi
0x180058513  retn
```
