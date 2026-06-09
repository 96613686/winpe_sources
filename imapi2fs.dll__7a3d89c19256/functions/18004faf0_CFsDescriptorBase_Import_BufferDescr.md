# CFsDescriptorBase::Import(BufferDescr &)

- ea: `0x18004faf0`
- end: `0x18004fdb9`
- name: `?Import@CFsDescriptorBase@@UEAAKAEAUBufferDescr@@@Z`
- size: `713`
- prototype: `unsigned int __fastcall(CFsDescriptorBase *__hidden this, struct BufferDescr *)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x180007104`
- `0x18000960c`
- `0x18000d1c0`
- `0x1800251dc`
- `0x180028568`
- `0x18002a020`
- `0x18002d4e4`
- `0x18002db48`
- `0x18004faf0`
- `0x180051638`
- `0x180051734`
- `0x180088010`

## import_xrefs

- `msvcrt!__RTtypeid` at `0x18004fb60`
- `msvcrt!__RTtypeid` at `0x18004fc17`
- `msvcrt!__RTtypeid` at `0x18004fd43`
- `msvcrt!__RTtypeid` at `0x18004fb60`
- `msvcrt!__RTtypeid` at `0x18004fc17`
- `msvcrt!__RTtypeid` at `0x18004fd43`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x18004fb69`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x18004fc20`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x18004fd4c`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x18004fb69`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x18004fc20`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x18004fd4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFsDescriptorBase::Import(CFsDescriptorBase *this, struct BufferDescr *a2)
{
  char v4; // di
  PVOID *v5; // rax
  type_info *v6; // rax
  const char *v7; // rax
  unsigned int v8; // r14d
  char v9; // bl
  type_info *v10; // rax
  const char *v11; // rax
  int v12; // edx
  int v13; // r8d
  CIMAPIException *v14; // rax
  CIMAPIException *v15; // rbx
  CIMAPIException **v16; // rbx
  PVOID *v17; // rcx
  char v18; // di
  char v19; // bl
  type_info *v20; // rax
  unsigned int v21; // eax
  int v22; // r8d
  _BYTE v24[128]; // [rsp+30h] [rbp-29h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v26; // [rsp+D0h] [rbp+77h] BYREF
  CIMAPIException **v27; // [rsp+D8h] [rbp+7Fh] BYREF

  v4 = 0;
  LODWORD(pExceptionObject) = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 79, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 4) != 0 && *((_BYTE *)v5 + 65) >= 4u )
    {
      v6 = (type_info *)__RTtypeid(this);
      v7 = type_info::name(v6);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 80, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids, v7);
    }
  }
  v8 = 0;
  if ( (*(unsigned int (__fastcall **)(CFsDescriptorBase *))(*(_QWORD *)this + 48LL))(this) )
    v8 = (*(__int64 (__fastcall **)(CFsDescriptorBase *, struct BufferDescr *))(*(_QWORD *)this + 64LL))(this, a2);
  if ( (*(unsigned int (__fastcall **)(CFsDescriptorBase *))(*(_QWORD *)this + 56LL))(this) )
    v8 += (*(__int64 (__fastcall **)(CFsDescriptorBase *, struct BufferDescr *))(*(_QWORD *)this + 72LL))(this, a2);
  if ( CFsDescriptorBase::Length(this) != v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v9 = CFsDescriptorBase::Length(this);
      v10 = (type_info *)__RTtypeid(this);
      v11 = type_info::name(v10);
      WPP_SF_DsD(*((_QWORD *)WPP_GLOBAL_Control + 7), v12, v13, v8, (__int64)v11, v9);
    }
    v14 = (CIMAPIException *)operator new(0x58u);
    v15 = v14;
    v27 = (CIMAPIException **)v14;
    if ( v14 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v26,
        *((_QWORD *)this + 1) + 8LL);
      v4 = 3;
      LODWORD(pExceptionObject) = 3;
      v14 = CIMAPIException::CIMAPIException(v15, -1062555309, v26);
    }
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v27, v14);
    if ( (v4 & 1) != 0 )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
    v16 = v27;
    if ( v27 && *v27 )
    {
      CIMAPIException::SetCodeRefInfo(*v27, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp", 1332);
      pExceptionObject = v16;
      if ( v16 )
        ++*((_DWORD *)v16 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v24, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v24;
  }
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      v18 = (*(__int64 (__fastcall **)(CFsDescriptorBase *))(*(_QWORD *)this + 56LL))(this);
      v19 = (*(__int64 (__fastcall **)(CFsDescriptorBase *))(*(_QWORD *)this + 48LL))(this);
      v20 = (type_info *)__RTtypeid(this);
      v21 = (unsigned int)type_info::name(v20);
      WPP_SF_sLL(*((_QWORD *)WPP_GLOBAL_Control + 7), 82, v22, v21, v19, v18);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 68) & 8) != 0 && *((_BYTE *)v17 + 65) >= 5u )
      WPP_SF_(v17[7], 83, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
  }
  return v8;
}

```

## disassembly

```asm
0x18004faf0  mov     [rsp-8+arg_8], rbx
0x18004faf5  push    rbp
0x18004faf6  push    rsi
0x18004faf7  push    rdi
0x18004faf8  push    r12
0x18004fafa  push    r14
0x18004fafc  lea     rbp, [rsp-37h]
0x18004fb01  sub     rsp, 90h
0x18004fb08  mov     rbx, rdx
0x18004fb0b  mov     rsi, rcx
0x18004fb0e  xor     edi, edi
0x18004fb10  mov     dword ptr [rbp+57h+pExceptionObject], edi
0x18004fb13  lea     r12, WPP_GLOBAL_Control
0x18004fb1a  mov     rax, cs:WPP_GLOBAL_Control
0x18004fb21  cmp     rax, r12
0x18004fb24  jz      short loc_18004FB8E
0x18004fb26  test    byte ptr [rax+44h], 8
0x18004fb2a  jz      short loc_18004FB4C
0x18004fb2c  cmp     byte ptr [rax+41h], 5
0x18004fb30  jb      short loc_18004FB4C
0x18004fb32  lea     edx, [rdi+4Fh]
0x18004fb35  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004fb3c  mov     rcx, [rax+38h]
0x18004fb40  call    WPP_SF_
0x18004fb45  mov     rax, cs:WPP_GLOBAL_Control
0x18004fb4c  cmp     rax, r12
0x18004fb4f  jz      short loc_18004FB8E
0x18004fb51  test    byte ptr [rax+44h], 4
0x18004fb55  jz      short loc_18004FB8E
0x18004fb57  cmp     byte ptr [rax+41h], 4
0x18004fb5b  jb      short loc_18004FB8E
0x18004fb5d  mov     rcx, rsi
0x18004fb60  call    cs:__imp___RTtypeid
0x18004fb66  mov     rcx, rax
0x18004fb69  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x18004fb6f  mov     edx, 50h ; 'P'
0x18004fb74  mov     r9, rax
0x18004fb77  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004fb7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fb85  mov     rcx, [rcx+38h]
0x18004fb89  call    WPP_SF_s
0x18004fb8e  xor     r14d, r14d
0x18004fb91  mov     rax, [rsi]
0x18004fb94  mov     rcx, rsi
0x18004fb97  mov     rax, [rax+30h]
0x18004fb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fba0  test    eax, eax
0x18004fba2  jz      short loc_18004FBB9
0x18004fba4  mov     rax, [rsi]
0x18004fba7  mov     rdx, rbx
0x18004fbaa  mov     rcx, rsi
0x18004fbad  mov     rax, [rax+40h]
0x18004fbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbb6  mov     r14d, eax
0x18004fbb9  mov     rcx, [rsi]
0x18004fbbc  mov     rax, [rcx+38h]
0x18004fbc0  mov     rcx, rsi
0x18004fbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbc8  test    eax, eax
0x18004fbca  jz      short loc_18004FBE1
0x18004fbcc  mov     rcx, [rsi]
0x18004fbcf  mov     rax, [rcx+48h]
0x18004fbd3  mov     rdx, rbx
0x18004fbd6  mov     rcx, rsi
0x18004fbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbde  add     r14d, eax
0x18004fbe1  mov     rcx, rsi; this
0x18004fbe4  call    ?Length@CFsDescriptorBase@@QEAAKXZ; CFsDescriptorBase::Length(void)
0x18004fbe9  cmp     eax, r14d
0x18004fbec  jz      loc_18004FD02
0x18004fbf2  mov     rax, cs:WPP_GLOBAL_Control
0x18004fbf9  cmp     rax, r12
0x18004fbfc  jz      short loc_18004FC42
0x18004fbfe  test    byte ptr [rax+44h], 4
0x18004fc02  jz      short loc_18004FC42
0x18004fc04  cmp     byte ptr [rax+41h], 2
0x18004fc08  jb      short loc_18004FC42
0x18004fc0a  mov     rcx, rsi; this
0x18004fc0d  call    ?Length@CFsDescriptorBase@@QEAAKXZ; CFsDescriptorBase::Length(void)
0x18004fc12  mov     ebx, eax
0x18004fc14  mov     rcx, rsi
0x18004fc17  call    cs:__imp___RTtypeid
0x18004fc1d  mov     rcx, rax
0x18004fc20  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x18004fc26  mov     [rsp+0B0h+var_88], ebx
0x18004fc2a  mov     [rsp+0B0h+var_90], rax
0x18004fc2f  mov     r9d, r14d
0x18004fc32  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fc39  mov     rcx, [rcx+38h]
0x18004fc3d  call    WPP_SF_DsD
0x18004fc42  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004fc47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fc4c  mov     rbx, rax
0x18004fc4f  mov     [rbp+57h+arg_18], rax
0x18004fc53  test    rax, rax
0x18004fc56  jz      short loc_18004FC84
0x18004fc58  mov     rdx, [rsi+8]
0x18004fc5c  add     rdx, 8
0x18004fc60  lea     rcx, [rbp+57h+arg_10]
0x18004fc64  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004fc69  nop
0x18004fc6a  mov     edi, 3
0x18004fc6f  mov     dword ptr [rbp+57h+pExceptionObject], edi
0x18004fc72  mov     r8, [rbp+57h+arg_10]
0x18004fc76  mov     edx, 0C0AAB153h; int
0x18004fc7b  mov     rcx, rbx; this
0x18004fc7e  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18004fc83  nop
0x18004fc84  mov     rdx, rax
0x18004fc87  lea     rcx, [rbp+57h+arg_18]
0x18004fc8b  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18004fc90  nop
0x18004fc91  test    dil, 1
0x18004fc95  jz      short loc_18004FCA0
0x18004fc97  lea     rcx, [rbp+57h+arg_10]; void *
0x18004fc9b  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004fca0  mov     rbx, [rbp+57h+arg_18]
0x18004fca4  test    rbx, rbx
0x18004fca7  jz      short loc_18004FCE1
0x18004fca9  cmp     qword ptr [rbx], 0
0x18004fcad  jz      short loc_18004FCE1
0x18004fcaf  mov     r8d, 534h; int
0x18004fcb5  lea     rdx, aDriversStorage_9; "drivers\\storage\\imapi2\\filesystemima"...
0x18004fcbc  mov     rcx, [rbx]; this
0x18004fcbf  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18004fcc4  mov     [rbp+57h+pExceptionObject], rbx
0x18004fcc8  test    rbx, rbx
0x18004fccb  jz      short loc_18004FCD0
0x18004fccd  inc     dword ptr [rbx+8]
0x18004fcd0  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18004fcd7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004fcdb  call    _CxxThrowException_0
0x18004fce1  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18004fce8  lea     rcx, [rbp+57h+var_80]; this
0x18004fcec  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18004fcf1  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18004fcf8  lea     rcx, [rbp+57h+var_80]; pExceptionObject
0x18004fcfc  call    _CxxThrowException_0
0x18004fd02  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fd09  cmp     rcx, r12
0x18004fd0c  jz      loc_18004FD9F
0x18004fd12  test    byte ptr [rcx+44h], 4
0x18004fd16  jz      short loc_18004FD79
0x18004fd18  cmp     byte ptr [rcx+41h], 4
0x18004fd1c  jb      short loc_18004FD79
0x18004fd1e  mov     rax, [rsi]
0x18004fd21  mov     rcx, rsi
0x18004fd24  mov     rax, [rax+38h]
0x18004fd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd2d  mov     edi, eax
0x18004fd2f  mov     rcx, [rsi]
0x18004fd32  mov     rax, [rcx+30h]
0x18004fd36  mov     rcx, rsi
0x18004fd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd3e  mov     ebx, eax
0x18004fd40  mov     rcx, rsi
0x18004fd43  call    cs:__imp___RTtypeid
0x18004fd49  mov     rcx, rax
0x18004fd4c  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x18004fd52  mov     edx, 52h ; 'R'
0x18004fd57  mov     [rsp+0B0h+var_88], edi
0x18004fd5b  mov     dword ptr [rsp+0B0h+var_90], ebx
0x18004fd5f  mov     r9, rax
0x18004fd62  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fd69  mov     rcx, [rcx+38h]
0x18004fd6d  call    WPP_SF_sLL
0x18004fd72  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fd79  cmp     rcx, r12
0x18004fd7c  jz      short loc_18004FD9F
0x18004fd7e  test    byte ptr [rcx+44h], 8
0x18004fd82  jz      short loc_18004FD9F
0x18004fd84  cmp     byte ptr [rcx+41h], 5
0x18004fd88  jb      short loc_18004FD9F
0x18004fd8a  mov     edx, 53h ; 'S'
0x18004fd8f  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004fd96  mov     rcx, [rcx+38h]
0x18004fd9a  call    WPP_SF_
0x18004fd9f  mov     eax, r14d
0x18004fda2  mov     rbx, [rsp+0B0h+arg_8]
0x18004fdaa  add     rsp, 90h
0x18004fdb1  pop     r14
0x18004fdb3  pop     r12
0x18004fdb5  pop     rdi
0x18004fdb6  pop     rsi
0x18004fdb7  pop     rbp
0x18004fdb8  retn
```
