# CStreamROBase::Stat(tagSTATSTG *,ulong)

- ea: `0x18005bda0`
- end: `0x18005c028`
- name: `?Stat@CStreamROBase@@QEAAXPEAUtagSTATSTG@@K@Z`
- size: `648`
- prototype: `void(CStreamROBase *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18003b820`
- `0x180043c04`
- `0x18004f8bc`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18005bda0`
- `0x18005c030`
- `0x18008170e`
- `0x180088010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18005bf31`
- `ole32!CoTaskMemAlloc` at `0x18005bf31`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CStreamROBase::Stat(CStreamROBase *this, struct tagSTATSTG *a2, int a3)
{
  CIMAPISystemException *v6; // rax
  CIMAPIException **v7; // rbx
  CIMAPISystemException *v8; // rax
  CIMAPIException **v9; // rbx
  unsigned __int16 *v10; // rcx
  CIMAPISystemException *v11; // rax
  CIMAPIException **v12; // rbx
  _BYTE v13[96]; // [rsp+20h] [rbp-60h] BYREF
  CIMAPIException **v14; // [rsp+A0h] [rbp+20h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+B8h] [rbp+38h] BYREF

  memset_0(a2, 0, 0x50u);
  if ( (*(__int64 (__fastcall **)(CStreamROBase *))(*(_QWORD *)this + 16LL))(this) != *((_QWORD *)this + 2) )
  {
    v6 = (CIMAPISystemException *)operator new(0x58u);
    v14 = (CIMAPIException **)v6;
    if ( v6 )
      v6 = CIMAPISystemException::CIMAPISystemException(v6, -2147023434);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v14, v6);
    v7 = v14;
    if ( v14 && *v14 )
    {
      CIMAPIException::SetCodeRefInfo(*v14, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filestream.cpp", 368);
      pExceptionObject = v7;
      if ( v7 )
        ++*((_DWORD *)v7 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v13, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v13;
  }
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      v8 = (CIMAPISystemException *)operator new(0x58u);
      v14 = (CIMAPIException **)v8;
      if ( v8 )
        v8 = CIMAPISystemException::CIMAPISystemException(v8, -2147287039);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v14, v8);
      v9 = v14;
      if ( v14 && *v14 )
      {
        CIMAPIException::SetCodeRefInfo(*v14, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filestream.cpp", 406);
        pExceptionObject = v9;
        if ( v9 )
          ++*((_DWORD *)v9 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v13,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v13;
    }
    *(_QWORD *)a2 = 0;
  }
  else
  {
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (*(_DWORD *)(*((_QWORD *)this + 3) - 16LL) + 1));
    *(_QWORD *)a2 = v10;
    if ( !v10 )
    {
      v11 = (CIMAPISystemException *)operator new(0x58u);
      v14 = (CIMAPIException **)v11;
      if ( v11 )
        v11 = CIMAPISystemException::CIMAPISystemException(v11, -2147024882);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v14, v11);
      v12 = v14;
      if ( v14 && *v14 )
      {
        CIMAPIException::SetCodeRefInfo(*v14, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filestream.cpp", 377);
        pExceptionObject = v12;
        if ( v12 )
          ++*((_DWORD *)v12 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v13,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v13;
    }
    StringCchCopyW(v10, *(_DWORD *)(*((_QWORD *)this + 3) - 16LL) + 1, *((const unsigned __int16 **)this + 3));
  }
  *((_QWORD *)a2 + 2) = *((_QWORD *)this + 2);
  *((_DWORD *)a2 + 2) = 3;
  *((_DWORD *)a2 + 13) = 0;
  *((_QWORD *)a2 + 5) = *((_QWORD *)this + 6);
  *((_QWORD *)a2 + 4) = *((_QWORD *)this + 4);
  *((_QWORD *)a2 + 3) = *((_QWORD *)this + 5);
}

```

## disassembly

```asm
0x18005bda0  mov     [rsp-18h+arg_8], rbx
0x18005bda5  push    rbp
0x18005bda6  push    rsi
0x18005bda7  push    r14
0x18005bda9  mov     rbp, rsp
0x18005bdac  sub     rsp, 80h
0x18005bdb3  mov     r14d, r8d
0x18005bdb6  mov     rbx, rdx
0x18005bdb9  mov     rsi, rcx
0x18005bdbc  xor     edx, edx; Val
0x18005bdbe  lea     r8d, [rdx+50h]; Size
0x18005bdc2  mov     rcx, rbx; void *
0x18005bdc5  call    memset_0
0x18005bdca  mov     rax, [rsi]
0x18005bdcd  mov     rcx, rsi
0x18005bdd0  mov     rax, [rax+10h]
0x18005bdd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdd9  cmp     rax, [rsi+10h]
0x18005bddd  jz      loc_18005BE73
0x18005bde3  mov     ecx, 58h ; 'X'; unsigned __int64
0x18005bde8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bded  mov     [rbp+arg_0], rax
0x18005bdf1  test    rax, rax
0x18005bdf4  jz      short loc_18005BE04
0x18005bdf6  mov     edx, 800705B6h; int
0x18005bdfb  mov     rcx, rax; this
0x18005bdfe  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18005be03  nop
0x18005be04  mov     rdx, rax
0x18005be07  lea     rcx, [rbp+arg_0]
0x18005be0b  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18005be10  nop
0x18005be11  mov     rbx, [rbp+arg_0]
0x18005be15  test    rbx, rbx
0x18005be18  jz      short loc_18005BE52
0x18005be1a  cmp     qword ptr [rbx], 0
0x18005be1e  jz      short loc_18005BE52
0x18005be20  mov     r8d, 170h; int
0x18005be26  lea     rdx, aDriversStorage_13; "drivers\\storage\\imapi2\\filesystemima"...
0x18005be2d  mov     rcx, [rbx]; this
0x18005be30  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18005be35  mov     [rbp+pExceptionObject], rbx
0x18005be39  test    rbx, rbx
0x18005be3c  jz      short loc_18005BE41
0x18005be3e  inc     dword ptr [rbx+8]
0x18005be41  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18005be48  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005be4c  call    _CxxThrowException_0
0x18005be52  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18005be59  lea     rcx, [rbp+var_60]; this
0x18005be5d  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18005be62  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18005be69  lea     rcx, [rbp+var_60]; pExceptionObject
0x18005be6d  call    _CxxThrowException_0
0x18005be73  test    r14d, r14d
0x18005be76  jz      loc_18005BF22
0x18005be7c  cmp     r14d, 1
0x18005be80  jz      loc_18005BF16
0x18005be86  mov     ecx, 58h ; 'X'; unsigned __int64
0x18005be8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005be90  mov     [rbp+arg_0], rax
0x18005be94  test    rax, rax
0x18005be97  jz      short loc_18005BEA7
0x18005be99  mov     edx, 80030001h; int
0x18005be9e  mov     rcx, rax; this
0x18005bea1  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18005bea6  nop
0x18005bea7  mov     rdx, rax
0x18005beaa  lea     rcx, [rbp+arg_0]
0x18005beae  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18005beb3  nop
0x18005beb4  mov     rbx, [rbp+arg_0]
0x18005beb8  test    rbx, rbx
0x18005bebb  jz      short loc_18005BEF5
0x18005bebd  cmp     qword ptr [rbx], 0
0x18005bec1  jz      short loc_18005BEF5
0x18005bec3  mov     r8d, 196h; int
0x18005bec9  lea     rdx, aDriversStorage_13; "drivers\\storage\\imapi2\\filesystemima"...
0x18005bed0  mov     rcx, [rbx]; this
0x18005bed3  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18005bed8  mov     [rbp+pExceptionObject], rbx
0x18005bedc  test    rbx, rbx
0x18005bedf  jz      short loc_18005BEE4
0x18005bee1  inc     dword ptr [rbx+8]
0x18005bee4  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18005beeb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005beef  call    _CxxThrowException_0
0x18005bef5  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18005befc  lea     rcx, [rbp+var_60]; this
0x18005bf00  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18005bf05  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18005bf0c  lea     rcx, [rbp+var_60]; pExceptionObject
0x18005bf10  call    _CxxThrowException_0
0x18005bf16  mov     qword ptr [rbx], 0
0x18005bf1d  jmp     loc_18005BFE6
0x18005bf22  mov     rax, [rsi+18h]
0x18005bf26  mov     ecx, [rax-10h]
0x18005bf29  inc     ecx
0x18005bf2b  movsxd  rcx, ecx
0x18005bf2e  add     rcx, rcx; cb
0x18005bf31  call    cs:__imp_CoTaskMemAlloc
0x18005bf37  mov     rcx, rax; unsigned __int16 *
0x18005bf3a  mov     [rbx], rax
0x18005bf3d  test    rax, rax
0x18005bf40  jnz     loc_18005BFD4
0x18005bf46  lea     ecx, [rax+58h]; unsigned __int64
0x18005bf49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bf4e  mov     [rbp+arg_0], rax
0x18005bf52  test    rax, rax
0x18005bf55  jz      short loc_18005BF65
0x18005bf57  mov     edx, 8007000Eh; int
0x18005bf5c  mov     rcx, rax; this
0x18005bf5f  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18005bf64  nop
0x18005bf65  mov     rdx, rax
0x18005bf68  lea     rcx, [rbp+arg_0]
0x18005bf6c  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18005bf71  nop
0x18005bf72  mov     rbx, [rbp+arg_0]
0x18005bf76  test    rbx, rbx
0x18005bf79  jz      short loc_18005BFB3
0x18005bf7b  cmp     qword ptr [rbx], 0
0x18005bf7f  jz      short loc_18005BFB3
0x18005bf81  mov     r8d, 179h; int
0x18005bf87  lea     rdx, aDriversStorage_13; "drivers\\storage\\imapi2\\filesystemima"...
0x18005bf8e  mov     rcx, [rbx]; this
0x18005bf91  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18005bf96  mov     [rbp+pExceptionObject], rbx
0x18005bf9a  test    rbx, rbx
0x18005bf9d  jz      short loc_18005BFA2
0x18005bf9f  inc     dword ptr [rbx+8]
0x18005bfa2  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18005bfa9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005bfad  call    _CxxThrowException_0
0x18005bfb3  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18005bfba  lea     rcx, [rbp+var_60]; this
0x18005bfbe  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18005bfc3  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18005bfca  lea     rcx, [rbp+var_60]; pExceptionObject
0x18005bfce  call    _CxxThrowException_0
0x18005bfd4  mov     r8, [rsi+18h]; unsigned __int16 *
0x18005bfd8  mov     eax, [r8-10h]
0x18005bfdc  inc     eax
0x18005bfde  movsxd  rdx, eax; unsigned __int64
0x18005bfe1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005bfe6  mov     rax, [rsi+10h]
0x18005bfea  mov     [rbx+10h], rax
0x18005bfee  mov     dword ptr [rbx+8], 3
0x18005bff5  mov     dword ptr [rbx+34h], 0
0x18005bffc  mov     rax, [rsi+30h]
0x18005c000  mov     [rbx+28h], rax
0x18005c004  mov     rax, [rsi+20h]
0x18005c008  mov     [rbx+20h], rax
0x18005c00c  mov     rax, [rsi+28h]
0x18005c010  mov     [rbx+18h], rax
0x18005c014  mov     rbx, [rsp+80h+arg_8]
0x18005c01c  add     rsp, 80h
0x18005c023  pop     r14
0x18005c025  pop     rsi
0x18005c026  pop     rbp
0x18005c027  retn
```
