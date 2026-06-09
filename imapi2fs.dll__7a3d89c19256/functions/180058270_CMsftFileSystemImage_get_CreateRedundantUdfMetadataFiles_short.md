# CMsftFileSystemImage::get_CreateRedundantUdfMetadataFiles(short *)

- ea: `0x180058270`
- end: `0x1800583bd`
- name: `?get_CreateRedundantUdfMetadataFiles@CMsftFileSystemImage@@UEAAJPEAF@Z`
- size: `333`
- prototype: `__int64 __fastcall(CMsftFileSystemImage *__hidden this, __int16 *)`
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
- `0x180058270`

## string_xrefs

- `0x180058288`: `CMsftFileSystemImage::get_CreateRedundantUDFMetadataFiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMsftFileSystemImage::get_CreateRedundantUdfMetadataFiles(CMsftFileSystemImage *this, __int16 *a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CMsftFileSystemImage::get_CreateRedundantUDFMetadataFiles");
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
          1092);
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
  *a2 = -1;
  *a2 = -(*(_BYTE *)(**((_QWORD **)this + 26) + 392LL) != 0);
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x180058270  mov     rax, rsp
0x180058273  mov     [rax+20h], rbx
0x180058277  push    rsi
0x180058278  push    rdi
0x180058279  push    r14
0x18005827b  sub     rsp, 80h
0x180058282  mov     rsi, rdx
0x180058285  mov     r14, rcx
0x180058288  lea     rdx, aCmsftfilesyste_23; "CMsftFileSystemImage::get_CreateRedunda"...
0x18005828f  lea     rcx, [rax+18h]; this
0x180058293  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180058298  nop
0x180058299  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18005829e  nop
0x18005829f  lea     rbx, [r14+50h]
0x1800582a3  mov     [rsp+98h+arg_8], rbx
0x1800582ab  mov     rcx, rbx; this
0x1800582ae  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x1800582b3  test    rsi, rsi
0x1800582b6  jz      short loc_1800582DC
0x1800582b8  xor     edi, edi
0x1800582ba  mov     word ptr [rsi], 0FFFFh
0x1800582bf  mov     rax, [r14+0D0h]
0x1800582c6  mov     rcx, [rax]
0x1800582c9  mov     al, [rcx+188h]
0x1800582cf  neg     al
0x1800582d1  sbb     cx, cx
0x1800582d4  mov     [rsi], cx
0x1800582d7  jmp     loc_180058391
0x1800582dc  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800582e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800582e6  mov     [rsp+98h+arg_0], rax
0x1800582ee  test    rax, rax
0x1800582f1  jz      short loc_180058308
0x1800582f3  lea     r8, aPval; "pVal"
0x1800582fa  mov     edx, 80004003h; int
0x1800582ff  mov     rcx, rax; this
0x180058302  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180058307  nop
0x180058308  mov     rdx, rax
0x18005830b  lea     rcx, [rsp+98h+arg_0]
0x180058313  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180058318  nop
0x180058319  mov     rbx, [rsp+98h+arg_0]
0x180058321  test    rbx, rbx
0x180058324  jz      short loc_18005835F
0x180058326  cmp     qword ptr [rbx], 0
0x18005832a  jz      short loc_18005835F
0x18005832c  mov     r8d, 444h; int
0x180058332  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180058339  mov     rcx, [rbx]; this
0x18005833c  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180058341  mov     [rsp+98h+pExceptionObject], rbx
0x180058346  test    rbx, rbx
0x180058349  jz      short loc_18005834E
0x18005834b  inc     dword ptr [rbx+8]
0x18005834e  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180058355  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18005835a  call    _CxxThrowException_0
0x18005835f  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180058366  lea     rcx, [rsp+98h+var_70]; this
0x18005836b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180058370  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180058377  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x18005837c  call    _CxxThrowException_0
0x180058382  mov     edi, dword ptr [rsp+98h+arg_0]
0x180058389  mov     rbx, [rsp+98h+arg_8]
0x180058391  mov     rcx, rbx; this
0x180058394  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180058399  nop
0x18005839a  lea     rcx, [rsp+98h+arg_10]; this
0x1800583a2  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x1800583a7  mov     eax, edi
0x1800583a9  mov     rbx, [rsp+98h+arg_18]
0x1800583b1  add     rsp, 80h
0x1800583b8  pop     r14
0x1800583ba  pop     rdi
0x1800583bb  pop     rsi
0x1800583bc  retn
```
