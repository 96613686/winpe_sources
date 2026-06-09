# CMsftIsoImageManager::get_Path(ushort * *)

- ea: `0x18002aab0`
- end: `0x18002ac8f`
- name: `?get_Path@CMsftIsoImageManager@@UEAAJPEAPEAG@Z`
- size: `479`
- prototype: `int(CMsftIsoImageManager *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

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
- `0x18002aab0`
- `0x18002d4e4`
- `0x180077b94`

## string_xrefs

- `0x18002aac3`: `CMsftIsoImageManager::get_Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CMsftIsoImageManager::get_Path(unsigned __int16 ***this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // r8
  int GenericStringProperty; // edi
  CIMAPIException *v6; // rax
  CIMAPIException **v7; // rbx
  CIMAPIException *v8; // rax
  CIMAPIException **v9; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-D8h] BYREF
  CIMAPIException **v12; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v13[88]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v14[112]; // [rsp+88h] [rbp-70h] BYREF
  CIMAPIException **v15; // [rsp+100h] [rbp+8h] BYREF
  char *v16; // [rsp+108h] [rbp+10h]
  char v17; // [rsp+110h] [rbp+18h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)&v17, "CMsftIsoImageManager::get_Path");
  ImapiClearErrorInfo();
  v16 = (char *)(this + 1);
  ImapiComObject::LockCS((ImapiComObject *)(this + 1));
  if ( !a2 )
  {
    v8 = (CIMAPIException *)operator new(0x58u);
    v15 = (CIMAPIException **)v8;
    if ( v8 )
      v8 = CIMAPIException::CIMAPIException(v8, -2147467261, L"pVal");
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v15, v8);
    v9 = v15;
    if ( v15 && *v15 )
    {
      CIMAPIException::SetCodeRefInfo(*v15, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp", 43);
      v12 = v9;
      if ( v9 )
        ++*((_DWORD *)v9 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v12;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v14, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v14;
  }
  GenericStringProperty = Imapi2Utility::GetGenericStringProperty((Imapi2Utility *)a2, this[18], v4);
  if ( GenericStringProperty < 0 )
  {
    v6 = (CIMAPIException *)operator new(0x58u);
    v15 = (CIMAPIException **)v6;
    if ( v6 )
      v6 = CIMAPIException::CIMAPIException(v6, GenericStringProperty);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v15, v6);
    v7 = v15;
    if ( v15 && *v15 )
    {
      CIMAPIException::SetCodeRefInfo(*v15, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\isoimagemanager.cpp", 48);
      pExceptionObject = v7;
      if ( v7 )
        ++*((_DWORD *)v7 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v13, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v13;
  }
  ImapiComObject::UnlockCS((ImapiComObject *)(this + 1));
  MethodTrace::~MethodTrace((MethodTrace *)&v17);
  return (unsigned int)GenericStringProperty;
}

```

## disassembly

```asm
0x18002aab0  mov     rax, rsp
0x18002aab3  push    rbx
0x18002aab4  push    rsi
0x18002aab5  push    rdi
0x18002aab6  sub     rsp, 0E0h
0x18002aabd  mov     rdi, rdx
0x18002aac0  mov     rsi, rcx
0x18002aac3  lea     rdx, aCmsftisoimagem_3; "CMsftIsoImageManager::get_Path"
0x18002aaca  lea     rcx, [rax+18h]; this
0x18002aace  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18002aad3  nop
0x18002aad4  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18002aad9  nop
0x18002aada  lea     rbx, [rsi+8]
0x18002aade  mov     [rsp+0F8h+arg_8], rbx
0x18002aae6  mov     rcx, rbx; this
0x18002aae9  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18002aaee  test    rdi, rdi
0x18002aaf1  jz      loc_18002ABB1
0x18002aaf7  mov     rdx, [rsi+90h]; unsigned __int16 **
0x18002aafe  mov     rcx, rdi; this
0x18002ab01  call    ?GetGenericStringProperty@Imapi2Utility@@YAJPEAPEAGPEAG@Z; Imapi2Utility::GetGenericStringProperty(ushort * *,ushort *)
0x18002ab06  mov     edi, eax
0x18002ab08  test    eax, eax
0x18002ab0a  jns     loc_18002ABAC
0x18002ab10  mov     ecx, 58h ; 'X'; unsigned __int64
0x18002ab15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ab1a  mov     [rsp+0F8h+arg_0], rax
0x18002ab22  test    rax, rax
0x18002ab25  jz      short loc_18002AB32
0x18002ab27  mov     edx, edi; int
0x18002ab29  mov     rcx, rax; this
0x18002ab2c  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18002ab31  nop
0x18002ab32  mov     rdx, rax
0x18002ab35  lea     rcx, [rsp+0F8h+arg_0]
0x18002ab3d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18002ab42  nop
0x18002ab43  mov     rbx, [rsp+0F8h+arg_0]
0x18002ab4b  test    rbx, rbx
0x18002ab4e  jz      short loc_18002AB89
0x18002ab50  cmp     qword ptr [rbx], 0
0x18002ab54  jz      short loc_18002AB89
0x18002ab56  mov     r8d, 30h ; '0'; int
0x18002ab5c  lea     rdx, aDriversStorage_8; "drivers\\storage\\imapi2\\filesystemima"...
0x18002ab63  mov     rcx, [rbx]; this
0x18002ab66  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18002ab6b  mov     [rsp+0F8h+pExceptionObject], rbx
0x18002ab70  test    rbx, rbx
0x18002ab73  jz      short loc_18002AB78
0x18002ab75  inc     dword ptr [rbx+8]
0x18002ab78  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18002ab7f  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18002ab84  call    _CxxThrowException_0
0x18002ab89  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18002ab90  lea     rcx, [rsp+0F8h+var_C8]; this
0x18002ab95  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18002ab9a  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18002aba1  lea     rcx, [rsp+0F8h+var_C8]; pExceptionObject
0x18002aba6  call    _CxxThrowException_0
0x18002abac  jmp     loc_18002AC6C
0x18002abb1  mov     ecx, 58h ; 'X'; unsigned __int64
0x18002abb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002abbb  mov     [rsp+0F8h+arg_0], rax
0x18002abc3  test    rax, rax
0x18002abc6  jz      short loc_18002ABDD
0x18002abc8  lea     r8, aPval; "pVal"
0x18002abcf  mov     edx, 80004003h; int
0x18002abd4  mov     rcx, rax; this
0x18002abd7  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18002abdc  nop
0x18002abdd  mov     rdx, rax
0x18002abe0  lea     rcx, [rsp+0F8h+arg_0]
0x18002abe8  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18002abed  nop
0x18002abee  mov     rbx, [rsp+0F8h+arg_0]
0x18002abf6  test    rbx, rbx
0x18002abf9  jz      short loc_18002AC34
0x18002abfb  cmp     qword ptr [rbx], 0
0x18002abff  jz      short loc_18002AC34
0x18002ac01  mov     r8d, 2Bh ; '+'; int
0x18002ac07  lea     rdx, aDriversStorage_8; "drivers\\storage\\imapi2\\filesystemima"...
0x18002ac0e  mov     rcx, [rbx]; this
0x18002ac11  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18002ac16  mov     [rsp+0F8h+var_D0], rbx
0x18002ac1b  test    rbx, rbx
0x18002ac1e  jz      short loc_18002AC23
0x18002ac20  inc     dword ptr [rbx+8]
0x18002ac23  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18002ac2a  lea     rcx, [rsp+0F8h+var_D0]; pExceptionObject
0x18002ac2f  call    _CxxThrowException_0
0x18002ac34  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18002ac3b  lea     rcx, [rsp+0F8h+var_70]; this
0x18002ac43  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18002ac48  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18002ac4f  lea     rcx, [rsp+0F8h+var_70]; pExceptionObject
0x18002ac57  call    _CxxThrowException_0
0x18002ac5d  mov     edi, dword ptr [rsp+0F8h+arg_0]
0x18002ac64  mov     rbx, [rsp+0F8h+arg_8]
0x18002ac6c  mov     rcx, rbx; this
0x18002ac6f  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18002ac74  nop
0x18002ac75  lea     rcx, [rsp+0F8h+arg_10]; this
0x18002ac7d  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18002ac82  mov     eax, edi
0x18002ac84  add     rsp, 0E0h
0x18002ac8b  pop     rdi
0x18002ac8c  pop     rsi
0x18002ac8d  pop     rbx
0x18002ac8e  retn
```
