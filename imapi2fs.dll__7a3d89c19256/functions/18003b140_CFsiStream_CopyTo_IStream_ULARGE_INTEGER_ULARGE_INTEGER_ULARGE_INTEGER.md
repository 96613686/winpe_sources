# CFsiStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x18003b140`
- end: `0x18003b2de`
- name: `?CopyTo@CFsiStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `414`
- prototype: `int(CFsiStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `13`
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
- `0x18003b140`
- `0x18005b564`

## string_xrefs

- `0x18003b162`: `CFsiStream::CopyTo`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiStream::CopyTo(
        CStreamROBase ***this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  CIMAPIException *v9; // rax
  unsigned __int64 v10; // rbx
  _QWORD pExceptionObject[2]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v13[8]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v14[88]; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int64 v15; // [rsp+C0h] [rbp+8h] BYREF
  unsigned __int64 v16; // [rsp+C8h] [rbp+10h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)v13, "CFsiStream::CopyTo");
  ImapiClearErrorInfo();
  pExceptionObject[1] = this - 10;
  ImapiComObject::LockCS((ImapiComObject *)(this - 10));
  try
  {
    v16 = 0;
    v15 = 0;
    if ( !a2 )
    {
      v9 = (CIMAPIException *)operator new(0x58u);
      v15 = (unsigned __int64)v9;
      if ( v9 )
        v9 = CIMAPIException::CIMAPIException(v9, -2147467261, L"pstreamDest");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v15, v9);
      v10 = v15;
      if ( v15 && *(_QWORD *)v15 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v15,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsistream.cpp",
          100);
        pExceptionObject[0] = v10;
        if ( v10 )
          ++*(_DWORD *)(v10 + 8);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v14,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v14;
    }
    CStreamROBase::CopyTo(*this[9], a2, a3.QuadPart, &v15, &v16);
    if ( a4 )
      a4->QuadPart = v15;
    if ( a5 )
      a5->QuadPart = v16;
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiStream);
  }
  ImapiComObject::UnlockCS((ImapiComObject *)(this - 10));
  MethodTrace::~MethodTrace((MethodTrace *)v13);
  return 0;
}

```

## disassembly

```asm
0x18003b140  mov     [rsp+arg_10], rbx
0x18003b145  mov     [rsp+arg_18], rsi
0x18003b14a  push    rdi
0x18003b14b  push    r14
0x18003b14d  push    r15
0x18003b14f  sub     rsp, 0A0h
0x18003b156  mov     rsi, r9
0x18003b159  mov     rbx, r8
0x18003b15c  mov     r14, rdx
0x18003b15f  mov     r15, rcx
0x18003b162  lea     rdx, aCfsistreamCopy; "CFsiStream::CopyTo"
0x18003b169  lea     rcx, [rsp+0B8h+var_78]; this
0x18003b16e  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18003b173  nop
0x18003b174  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18003b179  nop
0x18003b17a  lea     rdi, [r15-50h]
0x18003b17e  mov     [rsp+0B8h+var_80], rdi
0x18003b183  mov     rcx, rdi; this
0x18003b186  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18003b18b  mov     [rsp+0B8h+arg_8], 0
0x18003b197  mov     [rsp+0B8h+arg_0], 0
0x18003b1a3  test    r14, r14
0x18003b1a6  jz      short loc_18003B1FE
0x18003b1a8  mov     rcx, [r15+48h]
0x18003b1ac  lea     rax, [rsp+0B8h+arg_8]
0x18003b1b4  mov     [rsp+0B8h+var_98], rax; unsigned __int64 *
0x18003b1b9  lea     r9, [rsp+0B8h+arg_0]; unsigned __int64 *
0x18003b1c1  mov     r8, rbx; unsigned __int64
0x18003b1c4  mov     rdx, r14; struct IStream *
0x18003b1c7  mov     rcx, [rcx]; this
0x18003b1ca  call    ?CopyTo@CStreamROBase@@QEAAXPEAUIStream@@_KPEA_K2@Z; CStreamROBase::CopyTo(IStream *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x18003b1cf  test    rsi, rsi
0x18003b1d2  jz      short loc_18003B1DF
0x18003b1d4  mov     rax, [rsp+0B8h+arg_0]
0x18003b1dc  mov     [rsi], rax
0x18003b1df  xor     ebx, ebx
0x18003b1e1  mov     rcx, [rsp+0B8h+arg_20]
0x18003b1e9  test    rcx, rcx
0x18003b1ec  jz      short loc_18003B1F9
0x18003b1ee  mov     rax, [rsp+0B8h+arg_8]
0x18003b1f6  mov     [rcx], rax
0x18003b1f9  jmp     loc_18003B2B0
0x18003b1fe  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003b203  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b208  mov     [rsp+0B8h+arg_0], rax
0x18003b210  test    rax, rax
0x18003b213  jz      short loc_18003B22A
0x18003b215  lea     r8, aPstreamdest; "pstreamDest"
0x18003b21c  mov     edx, 80004003h; int
0x18003b221  mov     rcx, rax; this
0x18003b224  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18003b229  nop
0x18003b22a  mov     rdx, rax
0x18003b22d  lea     rcx, [rsp+0B8h+arg_0]
0x18003b235  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003b23a  nop
0x18003b23b  mov     rbx, [rsp+0B8h+arg_0]
0x18003b243  test    rbx, rbx
0x18003b246  jz      short loc_18003B281
0x18003b248  cmp     qword ptr [rbx], 0
0x18003b24c  jz      short loc_18003B281
0x18003b24e  mov     r8d, 64h ; 'd'; int
0x18003b254  lea     rdx, aDriversStorage_4; "drivers\\storage\\imapi2\\filesystemima"...
0x18003b25b  mov     rcx, [rbx]; this
0x18003b25e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003b263  mov     [rsp+0B8h+pExceptionObject], rbx
0x18003b268  test    rbx, rbx
0x18003b26b  jz      short loc_18003B270
0x18003b26d  inc     dword ptr [rbx+8]
0x18003b270  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003b277  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18003b27c  call    _CxxThrowException_0
0x18003b281  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003b288  lea     rcx, [rsp+0B8h+var_70]; this
0x18003b28d  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003b292  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003b299  lea     rcx, [rsp+0B8h+var_70]; pExceptionObject
0x18003b29e  call    _CxxThrowException_0
0x18003b2a4  mov     ebx, dword ptr [rsp+0B8h+arg_0]
0x18003b2ab  mov     rdi, [rsp+0B8h+var_80]
0x18003b2b0  mov     rcx, rdi; this
0x18003b2b3  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18003b2b8  nop
0x18003b2b9  lea     rcx, [rsp+0B8h+var_78]; this
0x18003b2be  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18003b2c3  mov     eax, ebx
0x18003b2c5  lea     r11, [rsp+0B8h+var_18]
0x18003b2cd  mov     rbx, [r11+30h]
0x18003b2d1  mov     rsi, [r11+38h]
0x18003b2d5  mov     rsp, r11
0x18003b2d8  pop     r15
0x18003b2da  pop     r14
0x18003b2dc  pop     rdi
0x18003b2dd  retn
```
