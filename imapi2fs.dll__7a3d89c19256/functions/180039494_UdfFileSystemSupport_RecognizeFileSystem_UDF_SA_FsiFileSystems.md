# UdfFileSystemSupport::RecognizeFileSystem(UDF_SA *,FsiFileSystems &)

- ea: `0x180039494`
- end: `0x180039715`
- name: `?RecognizeFileSystem@UdfFileSystemSupport@@IEAAXPEAVUDF_SA@@AEAW4FsiFileSystems@@@Z`
- size: `641`
- prototype: `void __fastcall(UdfFileSystemSupport *__hidden this, struct UDF_SA *, enum FsiFileSystems *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180038d30`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x180005160`
- `0x180005c04`
- `0x18000960c`
- `0x18000d1c0`
- `0x1800251dc`
- `0x180028568`
- `0x18002b114`
- `0x18002d4e4`
- `0x180039494`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800396ac`
- `msvcrt!_wcsicmp` at `0x1800396ac`

## string_xrefs

- `0x180039694`: `*OSTA UDF Compliant`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall UdfFileSystemSupport::RecognizeFileSystem(wchar_t *this, struct UDF_SA *a2, enum FsiFileSystems *a3)
{
  PVOID *v5; // rcx
  __int64 v6; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // rbx
  __int64 v9; // rbx
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  _BYTE v12[96]; // [rsp+20h] [rbp-60h] BYREF
  wchar_t *String1; // [rsp+A0h] [rbp+20h] BYREF
  wchar_t *String2; // [rsp+A8h] [rbp+28h] BYREF
  wchar_t *pExceptionObject; // [rsp+B8h] [rbp+38h] BYREF

  String1 = this;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 73, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = *((_QWORD *)a2 + 75);
  if ( !v6 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 4) != 0 && *((_BYTE *)v5 + 65) >= 2u )
      WPP_SF_(v5[7], 74, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    v7 = (wchar_t *)operator new(0x58u);
    String1 = v7;
    if ( v7 )
      v7 = (wchar_t *)CIMAPIException::CIMAPIException((CIMAPIException *)v7, -1062555392);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&String1, v7);
    v8 = String1;
    if ( String1 && *(_QWORD *)String1 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)String1,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
        1872);
      pExceptionObject = v8;
      if ( v8 )
        ++*((_DWORD *)v8 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v12, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v12;
  }
  v9 = *(_QWORD *)(v6 + 48);
  if ( !v9 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 4) != 0 && *((_BYTE *)v5 + 65) >= 2u )
      WPP_SF_(v5[7], 75, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    v10 = (wchar_t *)operator new(0x58u);
    String1 = v10;
    if ( v10 )
      v10 = (wchar_t *)CIMAPIException::CIMAPIException((CIMAPIException *)v10, -1062555392);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&String1, v10);
    v11 = String1;
    if ( String1 && *(_QWORD *)String1 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)String1,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp",
        1883);
      pExceptionObject = v11;
      if ( v11 )
        ++*((_DWORD *)v11 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v12, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v12;
  }
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&String1, &ATL::g_strmgr);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    &String1,
    v9 + 217);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &String2,
    "*OSTA UDF Compliant");
  *a3 = _wcsicmp(String1, String2) != 0 ? FsiFileSystemUnknown : FsiFileSystemUDF;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 76, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&String2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&String1);
}

```

## disassembly

```asm
0x180039494  mov     [rsp-18h+arg_10], rbx
0x180039499  mov     [rsp-18h+String1], rcx
0x18003949e  push    rbp
0x18003949f  push    rdi
0x1800394a0  push    r14
0x1800394a2  mov     rbp, rsp
0x1800394a5  sub     rsp, 80h
0x1800394ac  mov     rdi, r8
0x1800394af  mov     rbx, rdx
0x1800394b2  lea     r14, WPP_GLOBAL_Control
0x1800394b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394c0  cmp     rcx, r14
0x1800394c3  jz      short loc_1800394ED
0x1800394c5  test    byte ptr [rcx+44h], 8
0x1800394c9  jz      short loc_1800394ED
0x1800394cb  cmp     byte ptr [rcx+41h], 5
0x1800394cf  jb      short loc_1800394ED
0x1800394d1  mov     edx, 49h ; 'I'
0x1800394d6  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x1800394dd  mov     rcx, [rcx+38h]
0x1800394e1  call    WPP_SF_
0x1800394e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394ed  mov     rax, [rbx+258h]
0x1800394f4  test    rax, rax
0x1800394f7  jnz     loc_1800395B1
0x1800394fd  cmp     rcx, r14
0x180039500  jz      short loc_180039521
0x180039502  test    byte ptr [rcx+44h], 4
0x180039506  jz      short loc_180039521
0x180039508  cmp     byte ptr [rcx+41h], 2
0x18003950c  jb      short loc_180039521
0x18003950e  lea     edx, [rax+4Ah]
0x180039511  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x180039518  mov     rcx, [rcx+38h]
0x18003951c  call    WPP_SF_
0x180039521  mov     ecx, 58h ; 'X'; unsigned __int64
0x180039526  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003952b  mov     [rbp+String1], rax
0x18003952f  test    rax, rax
0x180039532  jz      short loc_180039542
0x180039534  mov     edx, 0C0AAB100h; int
0x180039539  mov     rcx, rax; this
0x18003953c  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180039541  nop
0x180039542  mov     rdx, rax
0x180039545  lea     rcx, [rbp+String1]
0x180039549  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003954e  nop
0x18003954f  mov     rbx, [rbp+String1]
0x180039553  test    rbx, rbx
0x180039556  jz      short loc_180039590
0x180039558  cmp     qword ptr [rbx], 0
0x18003955c  jz      short loc_180039590
0x18003955e  mov     r8d, 750h; int
0x180039564  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x18003956b  mov     rcx, [rbx]; this
0x18003956e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180039573  mov     [rbp+pExceptionObject], rbx
0x180039577  test    rbx, rbx
0x18003957a  jz      short loc_18003957F
0x18003957c  inc     dword ptr [rbx+8]
0x18003957f  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180039586  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003958a  call    _CxxThrowException_0
0x180039590  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180039597  lea     rcx, [rbp+var_60]; this
0x18003959b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800395a0  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800395a7  lea     rcx, [rbp+var_60]; pExceptionObject
0x1800395ab  call    _CxxThrowException_0
0x1800395b1  mov     rbx, [rax+30h]
0x1800395b5  test    rbx, rbx
0x1800395b8  jnz     loc_180039672
0x1800395be  cmp     rcx, r14
0x1800395c1  jz      short loc_1800395E2
0x1800395c3  test    byte ptr [rcx+44h], 4
0x1800395c7  jz      short loc_1800395E2
0x1800395c9  cmp     byte ptr [rcx+41h], 2
0x1800395cd  jb      short loc_1800395E2
0x1800395cf  lea     edx, [rbx+4Bh]
0x1800395d2  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x1800395d9  mov     rcx, [rcx+38h]
0x1800395dd  call    WPP_SF_
0x1800395e2  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800395e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800395ec  mov     [rbp+String1], rax
0x1800395f0  test    rax, rax
0x1800395f3  jz      short loc_180039603
0x1800395f5  mov     edx, 0C0AAB100h; int
0x1800395fa  mov     rcx, rax; this
0x1800395fd  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180039602  nop
0x180039603  mov     rdx, rax
0x180039606  lea     rcx, [rbp+String1]
0x18003960a  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003960f  nop
0x180039610  mov     rbx, [rbp+String1]
0x180039614  test    rbx, rbx
0x180039617  jz      short loc_180039651
0x180039619  cmp     qword ptr [rbx], 0
0x18003961d  jz      short loc_180039651
0x18003961f  mov     r8d, 75Bh; int
0x180039625  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x18003962c  mov     rcx, [rbx]; this
0x18003962f  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180039634  mov     [rbp+pExceptionObject], rbx
0x180039638  test    rbx, rbx
0x18003963b  jz      short loc_180039640
0x18003963d  inc     dword ptr [rbx+8]
0x180039640  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180039647  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003964b  call    _CxxThrowException_0
0x180039651  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180039658  lea     rcx, [rbp+var_60]; this
0x18003965c  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180039661  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180039668  lea     rcx, [rbp+var_60]; pExceptionObject
0x18003966c  call    _CxxThrowException_0
0x180039672  lea     rdx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180039679  lea     rcx, [rbp+String1]
0x18003967d  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180039682  nop
0x180039683  lea     rdx, [rbx+0D9h]
0x18003968a  lea     rcx, [rbp+String1]
0x18003968e  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180039693  nop
0x180039694  lea     rdx, aOstaUdfComplia; "*OSTA UDF Compliant"
0x18003969b  lea     rcx, [rbp+String2]
0x18003969f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x1800396a4  mov     rdx, [rbp+String2]; String2
0x1800396a8  mov     rcx, [rbp+String1]; String1
0x1800396ac  call    cs:__imp__wcsicmp
0x1800396b2  neg     eax
0x1800396b4  sbb     ecx, ecx
0x1800396b6  and     ecx, 3FFFFFFCh
0x1800396bc  add     ecx, 4
0x1800396bf  mov     [rdi], ecx
0x1800396c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396c8  cmp     rcx, r14
0x1800396cb  jz      short loc_1800396EE
0x1800396cd  test    byte ptr [rcx+44h], 8
0x1800396d1  jz      short loc_1800396EE
0x1800396d3  cmp     byte ptr [rcx+41h], 5
0x1800396d7  jb      short loc_1800396EE
0x1800396d9  mov     edx, 4Ch ; 'L'
0x1800396de  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x1800396e5  mov     rcx, [rcx+38h]
0x1800396e9  call    WPP_SF_
0x1800396ee  lea     rcx, [rbp+String2]; void *
0x1800396f2  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800396f7  nop
0x1800396f8  lea     rcx, [rbp+String1]; void *
0x1800396fc  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180039701  mov     rbx, [rsp+80h+arg_10]
0x180039709  add     rsp, 80h
0x180039710  pop     r14
0x180039712  pop     rdi
0x180039713  pop     rbp
0x180039714  retn
```
