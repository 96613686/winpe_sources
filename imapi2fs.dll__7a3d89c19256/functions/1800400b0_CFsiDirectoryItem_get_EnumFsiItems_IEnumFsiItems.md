# CFsiDirectoryItem::get_EnumFsiItems(IEnumFsiItems * *)

- ea: `0x1800400b0`
- end: `0x18004021c`
- name: `?get_EnumFsiItems@CFsiDirectoryItem@@UEAAJPEAPEAUIEnumFsiItems@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, struct IEnumFsiItems **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x18000f90c`
- `0x18000fd20`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x1800400b0`

## string_xrefs

- `0x1800400c5`: `CFsiDirectoryItem::get_EnumFsiItems`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiDirectoryItem::get_EnumFsiItems(CFsiDirectoryItem *this, struct IEnumFsiItems **a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  CIMAPIException *v6; // rax
  CIMAPIException **v7; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v10[128]; // [rsp+28h] [rbp-80h] BYREF
  CIMAPIException **v11; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v12; // [rsp+B8h] [rbp+10h] BYREF
  char *v13; // [rsp+C0h] [rbp+18h]
  char v14; // [rsp+C8h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v14, "CFsiDirectoryItem::get_EnumFsiItems");
  ImapiClearErrorInfo();
  v13 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
  try
  {
    if ( !a2 )
    {
      v6 = (CIMAPIException *)operator new(0x58u);
      v11 = (CIMAPIException **)v6;
      if ( v6 )
        v6 = CIMAPIException::CIMAPIException(v6, -2147467261, L"NewEnum");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v11, v6);
      v7 = v11;
      if ( v11 && *v11 )
      {
        CIMAPIException::SetCodeRefInfo(*v11, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 330);
        pExceptionObject = v7;
        if ( v7 )
          ++*((_DWORD *)v7 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v10,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v10;
    }
    v4 = *((_QWORD *)this + 8);
    v12 = v4;
    if ( v4 )
      ++*(_DWORD *)(v4 + 8);
    v11 = (CIMAPIException **)*((_QWORD *)this - 2);
    _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(&v11);
    ImapiFsObjectBase::get_EnumFsiItems(v5, a2, &v11, &v12);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)&v14);
  return 0;
}

```

## disassembly

```asm
0x1800400b0  mov     rax, rsp
0x1800400b3  push    rbx
0x1800400b4  push    rsi
0x1800400b5  push    rdi
0x1800400b6  push    r14
0x1800400b8  sub     rsp, 88h
0x1800400bf  mov     r14, rdx
0x1800400c2  mov     rdi, rcx
0x1800400c5  lea     rdx, aCfsidirectoryi_4; "CFsiDirectoryItem::get_EnumFsiItems"
0x1800400cc  lea     rcx, [rax+20h]; this
0x1800400d0  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x1800400d5  nop
0x1800400d6  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x1800400db  nop
0x1800400dc  lea     rbx, [rdi-50h]
0x1800400e0  mov     [rsp+0A8h+arg_10], rbx
0x1800400e8  mov     rcx, rbx; this
0x1800400eb  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x1800400f0  test    r14, r14
0x1800400f3  jz      short loc_180040142
0x1800400f5  xor     esi, esi
0x1800400f7  mov     rax, [rdi+40h]
0x1800400fb  mov     [rsp+0A8h+arg_8], rax
0x180040103  test    rax, rax
0x180040106  jz      short loc_18004010B
0x180040108  inc     dword ptr [rax+8]
0x18004010b  mov     rax, [rdi-10h]
0x18004010f  mov     [rsp+0A8h+arg_0], rax
0x180040117  lea     rcx, [rsp+0A8h+arg_0]
0x18004011f  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x180040124  lea     r9, [rsp+0A8h+arg_8]
0x18004012c  lea     r8, [rsp+0A8h+arg_0]
0x180040134  mov     rdx, r14
0x180040137  call    ?get_EnumFsiItems@ImapiFsObjectBase@@QEAAXPEAPEAUIEnumFsiItems@@V?$_com_ptr_t@V?$_com_IIID@UIUnknown@@$1?_GUID_00000000_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@Z; ImapiFsObjectBase::get_EnumFsiItems(IEnumFsiItems * *,_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>)
0x18004013c  nop
0x18004013d  jmp     loc_1800401F7
0x180040142  mov     ecx, 58h ; 'X'; unsigned __int64
0x180040147  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004014c  mov     [rsp+0A8h+arg_0], rax
0x180040154  test    rax, rax
0x180040157  jz      short loc_18004016E
0x180040159  lea     r8, aNewenum; "NewEnum"
0x180040160  mov     edx, 80004003h; int
0x180040165  mov     rcx, rax; this
0x180040168  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18004016d  nop
0x18004016e  mov     rdx, rax
0x180040171  lea     rcx, [rsp+0A8h+arg_0]
0x180040179  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18004017e  nop
0x18004017f  mov     rbx, [rsp+0A8h+arg_0]
0x180040187  test    rbx, rbx
0x18004018a  jz      short loc_1800401C5
0x18004018c  cmp     qword ptr [rbx], 0
0x180040190  jz      short loc_1800401C5
0x180040192  mov     r8d, 14Ah; int
0x180040198  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18004019f  mov     rcx, [rbx]; this
0x1800401a2  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800401a7  mov     [rsp+0A8h+pExceptionObject], rbx
0x1800401ac  test    rbx, rbx
0x1800401af  jz      short loc_1800401B4
0x1800401b1  inc     dword ptr [rbx+8]
0x1800401b4  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800401bb  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800401c0  call    _CxxThrowException_0
0x1800401c5  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800401cc  lea     rcx, [rsp+0A8h+var_80]; this
0x1800401d1  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800401d6  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800401dd  lea     rcx, [rsp+0A8h+var_80]; pExceptionObject
0x1800401e2  call    _CxxThrowException_0
0x1800401e8  mov     esi, dword ptr [rsp+0A8h+arg_0]
0x1800401ef  mov     rbx, [rsp+0A8h+arg_10]
0x1800401f7  mov     rcx, rbx; this
0x1800401fa  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x1800401ff  nop
0x180040200  lea     rcx, [rsp+0A8h+arg_18]; this
0x180040208  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18004020d  mov     eax, esi
0x18004020f  add     rsp, 88h
0x180040216  pop     r14
0x180040218  pop     rdi
0x180040219  pop     rsi
0x18004021a  pop     rbx
0x18004021b  retn
```
