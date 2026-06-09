# CFsiDirectoryItem::get_IsHidden(short *)

- ea: `0x1800404d0`
- end: `0x18004061a`
- name: `?get_IsHidden@CFsiDirectoryItem@@UEAAJPEAF@Z`
- size: `330`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, __int16 *)`
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
- `0x1800404d0`

## string_xrefs

- `0x1800404e8`: `CFsiDirectoryItem::get_IsHidden`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiDirectoryItem::get_IsHidden(CFsiDirectoryItem *this, __int16 *a2)
{
  CIMAPIException *v4; // rax
  CIMAPIException **v5; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v8[112]; // [rsp+28h] [rbp-70h] BYREF
  CIMAPIException **v9; // [rsp+A0h] [rbp+8h] BYREF
  char *v10; // [rsp+A8h] [rbp+10h]
  char v11; // [rsp+B0h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v11, "CFsiDirectoryItem::get_IsHidden");
  ImapiClearErrorInfo();
  v10 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
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
        CIMAPIException::SetCodeRefInfo(*v9, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 261);
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
      ExceptionDispatcher(&CLSID_FsiDirectoryItem);
    }
  }
  *a2 = 0;
  *a2 = -(*(_BYTE *)(**((_QWORD **)this + 8) + 177LL) != 0);
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v11);
  return 0;
}

```

## disassembly

```asm
0x1800404d0  mov     rax, rsp
0x1800404d3  mov     [rax+20h], rbx
0x1800404d7  push    rsi
0x1800404d8  push    rdi
0x1800404d9  push    r14
0x1800404db  sub     rsp, 80h
0x1800404e2  mov     rsi, rdx
0x1800404e5  mov     r14, rcx
0x1800404e8  lea     rdx, aCfsidirectoryi_12; "CFsiDirectoryItem::get_IsHidden"
0x1800404ef  lea     rcx, [rax+18h]; this
0x1800404f3  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x1800404f8  nop
0x1800404f9  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x1800404fe  nop
0x1800404ff  lea     rbx, [r14-50h]
0x180040503  mov     [rsp+98h+arg_8], rbx
0x18004050b  mov     rcx, rbx; this
0x18004050e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180040513  test    rsi, rsi
0x180040516  jz      short loc_180040539
0x180040518  xor     edi, edi
0x18004051a  xor     eax, eax
0x18004051c  mov     [rsi], ax
0x18004051f  mov     rax, [r14+40h]
0x180040523  mov     rcx, [rax]
0x180040526  mov     al, [rcx+0B1h]
0x18004052c  neg     al
0x18004052e  sbb     cx, cx
0x180040531  mov     [rsi], cx
0x180040534  jmp     loc_1800405EE
0x180040539  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004053e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040543  mov     [rsp+98h+arg_0], rax
0x18004054b  test    rax, rax
0x18004054e  jz      short loc_180040565
0x180040550  lea     r8, aPval; "pVal"
0x180040557  mov     edx, 80004003h; int
0x18004055c  mov     rcx, rax; this
0x18004055f  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180040564  nop
0x180040565  mov     rdx, rax
0x180040568  lea     rcx, [rsp+98h+arg_0]
0x180040570  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180040575  nop
0x180040576  mov     rbx, [rsp+98h+arg_0]
0x18004057e  test    rbx, rbx
0x180040581  jz      short loc_1800405BC
0x180040583  cmp     qword ptr [rbx], 0
0x180040587  jz      short loc_1800405BC
0x180040589  mov     r8d, 105h; int
0x18004058f  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180040596  mov     rcx, [rbx]; this
0x180040599  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18004059e  mov     [rsp+98h+pExceptionObject], rbx
0x1800405a3  test    rbx, rbx
0x1800405a6  jz      short loc_1800405AB
0x1800405a8  inc     dword ptr [rbx+8]
0x1800405ab  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800405b2  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800405b7  call    _CxxThrowException_0
0x1800405bc  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800405c3  lea     rcx, [rsp+98h+var_70]; this
0x1800405c8  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800405cd  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800405d4  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x1800405d9  call    _CxxThrowException_0
0x1800405df  mov     edi, dword ptr [rsp+98h+arg_0]
0x1800405e6  mov     rbx, [rsp+98h+arg_8]
0x1800405ee  mov     rcx, rbx; this
0x1800405f1  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x1800405f6  nop
0x1800405f7  lea     rcx, [rsp+98h+arg_10]; this
0x1800405ff  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180040604  mov     eax, edi
0x180040606  mov     rbx, [rsp+98h+arg_18]
0x18004060e  add     rsp, 80h
0x180040615  pop     r14
0x180040617  pop     rdi
0x180040618  pop     rsi
0x180040619  retn
```
