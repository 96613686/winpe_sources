# CFsiDirectoryItem::RemoveTree(ushort *)

- ea: `0x18000d200`
- end: `0x18000d7c9`
- name: `?RemoveTree@CFsiDirectoryItem@@UEAAJPEAG@Z`
- size: `1481`
- prototype: `int(CFsiDirectoryItem *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003a80`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x18000c888`
- `0x18000c8d0`
- `0x18000d1c0`
- `0x18000d200`
- `0x18000f28c`
- `0x180011c48`
- `0x1800133c0`
- `0x180017090`
- `0x180018fdc`
- `0x1800199b8`
- `0x18001ce58`
- `0x1800216cc`
- `0x180023c08`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x1800392dc`
- `0x180047c94`

## string_xrefs

- `0x18000d248`: `CFsiDirectoryItem::RemoveTree`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CFsiDirectoryItem::RemoveTree(CFsiDirectoryItem *this, unsigned __int16 *a2)
{
  ImapiComObject *v4; // r13
  unsigned int v5; // r14d
  int v6; // eax
  int v7; // r12d
  __int64 v8; // rax
  CIMAPIException *v9; // rax
  CIMAPIException *v10; // rax
  CIMAPIException **v11; // rbx
  _DWORD *v12; // rbx
  _DWORD *v13; // r14
  __int64 v14; // r8
  CIMAPIException *v15; // rax
  CIMAPIException *v16; // rax
  CIMAPIException **v17; // rbx
  __int64 v18; // rax
  _DWORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  _DWORD *v22; // rax
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rcx
  CIMAPIException *v26; // rbx
  const struct ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException *v28; // rax
  CIMAPIException **v29; // rbx
  CIMAPIException *v30; // rax
  CIMAPIException *v31; // rax
  CIMAPIException **v32; // rbx
  _DWORD *v34; // [rsp+20h] [rbp-208h] BYREF
  _DWORD *v35; // [rsp+28h] [rbp-200h] BYREF
  _DWORD *v36; // [rsp+30h] [rbp-1F8h] BYREF
  __int64 v37; // [rsp+38h] [rbp-1F0h] BYREF
  char v38[8]; // [rsp+40h] [rbp-1E8h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+48h] [rbp-1E0h] BYREF
  CIMAPIException **v40; // [rsp+50h] [rbp-1D8h] BYREF
  _DWORD *v41; // [rsp+58h] [rbp-1D0h] BYREF
  _DWORD *v42; // [rsp+60h] [rbp-1C8h] BYREF
  CIMAPIException **v43; // [rsp+68h] [rbp-1C0h] BYREF
  _QWORD v44[2]; // [rsp+70h] [rbp-1B8h] BYREF
  char v45[8]; // [rsp+80h] [rbp-1A8h] BYREF
  _BYTE v46[88]; // [rsp+88h] [rbp-1A0h] BYREF
  _BYTE v47[88]; // [rsp+E0h] [rbp-148h] BYREF
  _BYTE v48[88]; // [rsp+138h] [rbp-F0h] BYREF
  _BYTE v49[152]; // [rsp+190h] [rbp-98h] BYREF
  CIMAPIException **v50; // [rsp+240h] [rbp+18h] BYREF
  unsigned int v51; // [rsp+248h] [rbp+20h]

  v4 = (CFsiDirectoryItem *)((char *)this - 80);
  v44[1] = (char *)this - 80;
  v5 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  LODWORD(v50) = v5;
  v51 = v5;
  MethodTrace::MethodTrace((MethodTrace *)v45, "CFsiDirectoryItem::RemoveTree");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS(v4);
  v6 = ValidateStringPointer(a2, 1u, 0x10000u);
  try
  {
    v7 = v6;
    if ( v6 == -1062555391 || (v7 = ValidateStringPointer(a2, 1u, 0x10000u), v7 == -2147467261) )
    {
      v30 = (CIMAPIException *)operator new(0x58u);
      v50 = (CIMAPIException **)v30;
      if ( v30 )
        v31 = CIMAPIException::CIMAPIException(v30, v7, L"path");
      else
        v31 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v50, v31);
      v32 = v50;
      if ( v50 && *v50 )
      {
        CIMAPIException::SetCodeRefInfo(*v50, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 786);
        v44[0] = v32;
        if ( v32 )
          ++*((_DWORD *)v32 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v44;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v49,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v49;
    }
    if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
    {
      v8 = **((_QWORD **)this + 8);
      if ( !*(_QWORD *)(v8 + 72) )
      {
        v26 = (CIMAPIException *)operator new(0x58u);
        v50 = (CIMAPIException **)v26;
        if ( v26 )
        {
          FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(**((ImapiFsObjectBase ***)this + 8));
          v28 = CIMAPIException::CIMAPIException(v26, -1062555381, *(_QWORD *)FullPathOriginal);
        }
        else
        {
          v28 = 0;
        }
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v50, v28);
        v29 = v50;
        if ( v50 && *v50 )
        {
          CIMAPIException::SetCodeRefInfo(*v50, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 790);
          v43 = v29;
          if ( v29 )
            ++*((_DWORD *)v29 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v43;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v48,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v48;
      }
      if ( *(int *)(*(_QWORD *)(v8 + 64) + 8LL) > 0 )
      {
        v9 = (CIMAPIException *)operator new(0x58u);
        v50 = (CIMAPIException **)v9;
        if ( v9 )
          v10 = CIMAPIException::CIMAPIException(v9, -1062555390);
        else
          v10 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v50, v10);
        v11 = v50;
        if ( v50 && *v50 )
        {
          CIMAPIException::SetCodeRefInfo(*v50, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 794);
          pExceptionObject = v11;
          if ( v11 )
            ++*((_DWORD *)v11 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v46,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v46;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v37,
        a2);
      v12 = *(_DWORD **)ImapiDirectoryInfo::GetDirectoryRecord(**((_QWORD **)this + 8), &v34, &v37);
      v42 = v12;
      v13 = v12 + 2;
      if ( v12 )
        ++*v13;
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v34);
      if ( *(_DWORD *)(*(_QWORD *)v12 + 56LL) && *(_DWORD *)(*(_QWORD *)v12 + 56LL) != 3 )
      {
        v15 = (CIMAPIException *)operator new(0x58u);
        v50 = (CIMAPIException **)v15;
        if ( v15 )
          v16 = CIMAPIException::CIMAPIException(v15, -1062555383, v37);
        else
          v16 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v50, v16);
        v17 = v50;
        if ( v50 && *v50 )
        {
          CIMAPIException::SetCodeRefInfo(*v50, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 828);
          v40 = v17;
          if ( v17 )
            ++*((_DWORD *)v17 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v40;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v47,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v47;
      }
      v41 = v12;
      if ( v12 )
        ++*v13;
      if ( *(_BYTE *)(*(_QWORD *)v12 + 176LL) )
      {
        SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>::SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>(&v35);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v38);
        while ( 1 )
        {
          v18 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>>>::Minimum(
                  *(_QWORD *)v12 + 288LL,
                  *(_QWORD *)(*(_QWORD *)v12 + 288LL));
          if ( !v18 )
            break;
          v19 = *(_DWORD **)(v18 + 8);
          v36 = v19;
          if ( v19 )
            ++v19[2];
          SmartPtr<ImportMetadata>::operator=(&v35, &v36);
          SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v36);
          v20 = **((_QWORD **)this + 8);
          v34 = v35;
          if ( v35 )
            ++v35[2];
          ImapiDirectoryInfo::RemoveFileItem(v20, &v34);
        }
        while ( 1 )
        {
          v21 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>>>::Minimum(
                  *(_QWORD *)v12 + 240LL,
                  *(_QWORD *)(*(_QWORD *)v12 + 240LL));
          if ( !v21 )
            break;
          v22 = *(_DWORD **)(v21 + 8);
          v34 = v22;
          if ( v22 )
            ++v22[2];
          SmartPtr<ImportMetadata>::operator=(&v35, &v34);
          SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v34);
          v24 = **((_QWORD **)this + 8);
          v36 = v35;
          if ( v35 )
            ++v35[2];
          LOBYTE(v23) = 1;
          ImapiDirectoryInfo::RemoveDirectoryItem(v24, &v36, v23);
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v38);
        SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v35);
      }
      else
      {
        v25 = **((_QWORD **)this + 8);
        v34 = v12;
        if ( v12 )
          ++*v13;
        LOBYTE(v14) = 1;
        ImapiDirectoryInfo::RemoveDirectoryItem(v25, &v34, v14);
      }
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v41);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v42);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v37);
      v5 = (unsigned int)v50;
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  if ( v7 < 0 )
    FileSystemImage::RollbackRecover(*(FileSystemImage **)(**((_QWORD **)this + 8) + 64LL), v5, 1);
  ImapiComObject::UnlockCS(v4);
  MethodTrace::~MethodTrace((MethodTrace *)v45);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d200  mov     [rsp+arg_0], rcx
0x18000d205  push    rbx
0x18000d206  push    rsi
0x18000d207  push    rdi
0x18000d208  push    r12
0x18000d20a  push    r13
0x18000d20c  push    r14
0x18000d20e  push    r15
0x18000d210  sub     rsp, 1F0h
0x18000d217  mov     rbx, rdx
0x18000d21a  mov     r15, rcx
0x18000d21d  lea     r13, [rcx-50h]
0x18000d221  mov     [rsp+228h+var_1B0], r13
0x18000d226  mov     rax, [r13+90h]
0x18000d22d  mov     r8, [rax]
0x18000d230  mov     rax, [r8+40h]
0x18000d234  mov     r14d, [rax+14h]
0x18000d238  mov     dword ptr [rsp+228h+arg_10], r14d
0x18000d240  mov     [rsp+228h+arg_18], r14d
0x18000d248  lea     rdx, aCfsidirectoryi_16; "CFsiDirectoryItem::RemoveTree"
0x18000d24f  lea     rcx, [rsp+228h+var_1A8]; this
0x18000d257  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18000d25c  nop
0x18000d25d  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18000d262  nop
0x18000d263  mov     rcx, r13; this
0x18000d266  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18000d26b  mov     edi, 10000h
0x18000d270  mov     r8d, edi; unsigned __int64
0x18000d273  mov     esi, 1
0x18000d278  mov     edx, esi; unsigned __int64
0x18000d27a  mov     rcx, rbx; pbstr
0x18000d27d  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18000d282  mov     r12d, eax
0x18000d285  cmp     eax, 0C0AAB101h
0x18000d28a  jz      loc_18000D6B1
0x18000d290  mov     r8d, edi; unsigned __int64
0x18000d293  mov     edx, esi; unsigned __int64
0x18000d295  mov     rcx, rbx; pbstr
0x18000d298  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18000d29d  mov     r12d, eax
0x18000d2a0  cmp     eax, 80004003h
0x18000d2a5  jz      loc_18000D6B1
0x18000d2ab  mov     r8d, edi; unsigned __int64
0x18000d2ae  mov     edx, esi; unsigned __int64
0x18000d2b0  mov     rcx, rbx; pbstr
0x18000d2b3  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18000d2b8  xor     edi, edi
0x18000d2ba  test    eax, eax
0x18000d2bc  jns     short loc_18000D2C3
0x18000d2be  jmp     loc_18000D782
0x18000d2c3  mov     rax, [r15+40h]
0x18000d2c7  mov     rax, [rax]
0x18000d2ca  cmp     [rax+48h], rdi
0x18000d2ce  jz      loc_18000D5F7
0x18000d2d4  mov     rax, [rax+40h]
0x18000d2d8  cmp     [rax+8], edi
0x18000d2db  jle     loc_18000D389
0x18000d2e1  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000d2e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d2eb  mov     [rsp+228h+arg_10], rax
0x18000d2f3  test    rax, rax
0x18000d2f6  jz      short loc_18000D307
0x18000d2f8  mov     edx, 0C0AAB102h; int
0x18000d2fd  mov     rcx, rax; this
0x18000d300  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000d305  jmp     short loc_18000D30A
0x18000d307  mov     rax, rdi
0x18000d30a  mov     rdx, rax
0x18000d30d  lea     rcx, [rsp+228h+arg_10]
0x18000d315  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000d31a  nop
0x18000d31b  mov     rbx, [rsp+228h+arg_10]
0x18000d323  test    rbx, rbx
0x18000d326  jz      short loc_18000D360
0x18000d328  cmp     [rbx], rdi
0x18000d32b  jz      short loc_18000D360
0x18000d32d  mov     r8d, 31Ah; int
0x18000d333  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18000d33a  mov     rcx, [rbx]; this
0x18000d33d  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000d342  mov     [rsp+228h+pExceptionObject], rbx
0x18000d347  test    rbx, rbx
0x18000d34a  jz      short loc_18000D34F
0x18000d34c  add     [rbx+8], esi
0x18000d34f  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000d356  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x18000d35b  call    _CxxThrowException_0
0x18000d360  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000d367  lea     rcx, [rsp+228h+var_1A0]; this
0x18000d36f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000d374  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000d37b  lea     rcx, [rsp+228h+var_1A0]; pExceptionObject
0x18000d383  call    _CxxThrowException_0
0x18000d389  mov     rdx, rbx
0x18000d38c  lea     rcx, [rsp+228h+var_1F0]
0x18000d391  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000d396  nop
0x18000d397  mov     rcx, [r15+40h]
0x18000d39b  lea     r8, [rsp+228h+var_1F0]
0x18000d3a0  lea     rdx, [rsp+228h+var_208]
0x18000d3a5  mov     rcx, [rcx]
0x18000d3a8  call    ?GetDirectoryRecord@ImapiDirectoryInfo@@QEAA?AV?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; ImapiDirectoryInfo::GetDirectoryRecord(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000d3ad  mov     rbx, [rax]
0x18000d3b0  mov     [rsp+228h+var_1C8], rbx
0x18000d3b5  lea     r14, [rbx+8]
0x18000d3b9  test    rbx, rbx
0x18000d3bc  jz      short loc_18000D3C1
0x18000d3be  add     [r14], esi
0x18000d3c1  lea     rcx, [rsp+228h+var_208]; void *
0x18000d3c6  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000d3cb  mov     rax, [rbx]
0x18000d3ce  cmp     [rax+38h], edi
0x18000d3d1  jz      loc_18000D48E
0x18000d3d7  cmp     dword ptr [rax+38h], 3
0x18000d3db  jz      loc_18000D48E
0x18000d3e1  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000d3e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d3eb  mov     [rsp+228h+arg_10], rax
0x18000d3f3  test    rax, rax
0x18000d3f6  jz      short loc_18000D40C
0x18000d3f8  mov     r8, [rsp+228h+var_1F0]
0x18000d3fd  mov     edx, 0C0AAB109h; int
0x18000d402  mov     rcx, rax; this
0x18000d405  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000d40a  jmp     short loc_18000D40F
0x18000d40c  mov     rax, rdi
0x18000d40f  mov     rdx, rax
0x18000d412  lea     rcx, [rsp+228h+arg_10]
0x18000d41a  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000d41f  nop
0x18000d420  mov     rbx, [rsp+228h+arg_10]
0x18000d428  test    rbx, rbx
0x18000d42b  jz      short loc_18000D465
0x18000d42d  cmp     [rbx], rdi
0x18000d430  jz      short loc_18000D465
0x18000d432  mov     r8d, 33Ch; int
0x18000d438  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18000d43f  mov     rcx, [rbx]; this
0x18000d442  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000d447  mov     [rsp+228h+var_1D8], rbx
0x18000d44c  test    rbx, rbx
0x18000d44f  jz      short loc_18000D454
0x18000d451  add     [rbx+8], esi
0x18000d454  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000d45b  lea     rcx, [rsp+228h+var_1D8]; pExceptionObject
0x18000d460  call    _CxxThrowException_0
0x18000d465  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000d46c  lea     rcx, [rsp+228h+var_148]; this
0x18000d474  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000d479  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000d480  lea     rcx, [rsp+228h+var_148]; pExceptionObject
0x18000d488  call    _CxxThrowException_0
0x18000d48e  mov     [rsp+228h+var_1D0], rbx
0x18000d493  test    rbx, rbx
0x18000d496  jz      short loc_18000D49B
0x18000d498  add     [r14], esi
0x18000d49b  mov     rax, [rbx]
0x18000d49e  cmp     [rax+0B0h], dil
0x18000d4a5  jz      loc_18000D5A7
0x18000d4ab  lea     rcx, [rsp+228h+var_200]
0x18000d4b0  call    ??0?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@QEAA@PEAVImapiFsObjectBase@@@Z; SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>::SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>(ImapiFsObjectBase *)
0x18000d4b5  nop
0x18000d4b6  lea     rcx, [rsp+228h+var_1E8]; void *
0x18000d4bb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000d4c0  nop
0x18000d4c1  mov     rcx, [rbx]
0x18000d4c4  add     rcx, 120h
0x18000d4cb  mov     rdx, [rcx]
0x18000d4ce  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>>>::CNode *)
0x18000d4d3  test    rax, rax
0x18000d4d6  jz      short loc_18000D527
0x18000d4d8  mov     rax, [rax+8]
0x18000d4dc  mov     [rsp+228h+var_1F8], rax
0x18000d4e1  test    rax, rax
0x18000d4e4  jz      short loc_18000D4E9
0x18000d4e6  add     [rax+8], esi
0x18000d4e9  lea     rdx, [rsp+228h+var_1F8]
0x18000d4ee  lea     rcx, [rsp+228h+var_200]
0x18000d4f3  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x18000d4f8  lea     rcx, [rsp+228h+var_1F8]; void *
0x18000d4fd  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000d502  mov     rax, [r15+40h]
0x18000d506  mov     rcx, [rax]
0x18000d509  mov     rax, [rsp+228h+var_200]
0x18000d50e  mov     [rsp+228h+var_208], rax
0x18000d513  test    rax, rax
0x18000d516  jz      short loc_18000D51B
0x18000d518  add     [rax+8], esi
0x18000d51b  lea     rdx, [rsp+228h+var_208]
0x18000d520  call    ?RemoveFileItem@ImapiDirectoryInfo@@QEAAXV?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@Z; ImapiDirectoryInfo::RemoveFileItem(SmartClassPtr<ImapiFileInfo,ImapiImplementation>)
0x18000d525  jmp     short loc_18000D4C1
0x18000d527  mov     rcx, [rbx]
0x18000d52a  add     rcx, 0F0h
0x18000d531  mov     rdx, [rcx]
0x18000d534  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>>>::CNode *)
0x18000d539  test    rax, rax
0x18000d53c  jz      short loc_18000D590
0x18000d53e  mov     rax, [rax+8]
0x18000d542  mov     [rsp+228h+var_208], rax
0x18000d547  test    rax, rax
0x18000d54a  jz      short loc_18000D54F
0x18000d54c  add     [rax+8], esi
0x18000d54f  lea     rdx, [rsp+228h+var_208]
0x18000d554  lea     rcx, [rsp+228h+var_200]
0x18000d559  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x18000d55e  lea     rcx, [rsp+228h+var_208]; void *
0x18000d563  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000d568  mov     rax, [r15+40h]
0x18000d56c  mov     rcx, [rax]
0x18000d56f  mov     rax, [rsp+228h+var_200]
0x18000d574  mov     [rsp+228h+var_1F8], rax
0x18000d579  test    rax, rax
0x18000d57c  jz      short loc_18000D581
0x18000d57e  add     [rax+8], esi
0x18000d581  mov     r8b, sil
0x18000d584  lea     rdx, [rsp+228h+var_1F8]
0x18000d589  call    ?RemoveDirectoryItem@ImapiDirectoryInfo@@QEAAXV?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@_N@Z; ImapiDirectoryInfo::RemoveDirectoryItem(SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>,bool)
0x18000d58e  jmp     short loc_18000D527
0x18000d590  lea     rcx, [rsp+228h+var_1E8]; void *
0x18000d595  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000d59a  nop
0x18000d59b  lea     rcx, [rsp+228h+var_200]; void *
0x18000d5a0  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000d5a5  jmp     short loc_18000D5C9
0x18000d5a7  mov     rax, [r15+40h]
0x18000d5ab  mov     rcx, [rax]
0x18000d5ae  mov     [rsp+228h+var_208], rbx
0x18000d5b3  test    rbx, rbx
0x18000d5b6  jz      short loc_18000D5BB
0x18000d5b8  add     [r14], esi
0x18000d5bb  mov     r8b, sil
0x18000d5be  lea     rdx, [rsp+228h+var_208]
0x18000d5c3  call    ?RemoveDirectoryItem@ImapiDirectoryInfo@@QEAAXV?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@_N@Z; ImapiDirectoryInfo::RemoveDirectoryItem(SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>,bool)
0x18000d5c8  nop
0x18000d5c9  lea     rcx, [rsp+228h+var_1D0]; void *
0x18000d5ce  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000d5d3  nop
0x18000d5d4  lea     rcx, [rsp+228h+var_1C8]; void *
0x18000d5d9  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000d5de  nop
0x18000d5df  lea     rcx, [rsp+228h+var_1F0]; void *
0x18000d5e4  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000d5e9  nop
0x18000d5ea  mov     r14d, dword ptr [rsp+228h+arg_10]
0x18000d5f2  jmp     loc_18000D782
0x18000d5f7  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000d5fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d601  mov     rbx, rax
0x18000d604  mov     [rsp+228h+arg_10], rax
0x18000d60c  test    rax, rax
0x18000d60f  jz      short loc_18000D62F
0x18000d611  mov     rcx, [r15+40h]
0x18000d615  mov     rcx, [rcx]; this
0x18000d618  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x18000d61d  mov     r8, [rax]
0x18000d620  mov     edx, 0C0AAB10Bh; int
0x18000d625  mov     rcx, rbx; this
0x18000d628  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000d62d  jmp     short loc_18000D632
0x18000d62f  mov     rax, rdi
0x18000d632  mov     rdx, rax
0x18000d635  lea     rcx, [rsp+228h+arg_10]
0x18000d63d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000d642  nop
0x18000d643  mov     rbx, [rsp+228h+arg_10]
0x18000d64b  test    rbx, rbx
0x18000d64e  jz      short loc_18000D688
0x18000d650  cmp     [rbx], rdi
0x18000d653  jz      short loc_18000D688
0x18000d655  mov     r8d, 316h; int
0x18000d65b  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18000d662  mov     rcx, [rbx]; this
0x18000d665  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000d66a  mov     [rsp+228h+var_1C0], rbx
0x18000d66f  test    rbx, rbx
0x18000d672  jz      short loc_18000D677
0x18000d674  add     [rbx+8], esi
0x18000d677  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000d67e  lea     rcx, [rsp+228h+var_1C0]; pExceptionObject
0x18000d683  call    _CxxThrowException_0
0x18000d688  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000d68f  lea     rcx, [rsp+228h+var_F0]; this
0x18000d697  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000d69c  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000d6a3  lea     rcx, [rsp+228h+var_F0]; pExceptionObject
0x18000d6ab  call    _CxxThrowException_0
0x18000d6b1  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000d6b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d6bb  mov     [rsp+228h+arg_10], rax
0x18000d6c3  xor     edi, edi
0x18000d6c5  test    rax, rax
0x18000d6c8  jz      short loc_18000D6DE
0x18000d6ca  lea     r8, aPath; "path"
0x18000d6d1  mov     edx, r12d; int
0x18000d6d4  mov     rcx, rax; this
0x18000d6d7  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000d6dc  jmp     short loc_18000D6E1
0x18000d6de  mov     rax, rdi
0x18000d6e1  mov     rdx, rax
  ... truncated ...
```
