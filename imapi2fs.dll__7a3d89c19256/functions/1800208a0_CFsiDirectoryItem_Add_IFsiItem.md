# CFsiDirectoryItem::Add(IFsiItem *)

- ea: `0x1800208a0`
- end: `0x180020fc8`
- name: `?Add@CFsiDirectoryItem@@UEAAJPEAUIFsiItem@@@Z`
- size: `1832`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, struct IFsiItem *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f824`
- `0x180011c48`
- `0x180014040`
- `0x180018fdc`
- `0x1800199b8`
- `0x18001f27c`
- `0x1800208a0`
- `0x1800218f0`
- `0x180023c08`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180047c94`
- `0x180077430`
- `0x180088010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180020912`
- `KERNEL32!GetTickCount` at `0x180020dbd`
- `KERNEL32!GetTickCount` at `0x180020912`
- `KERNEL32!GetTickCount` at `0x180020dbd`

## string_xrefs

- `0x1800208ef`: `CFsiDirectoryItem::Add`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CFsiDirectoryItem::Add(CFsiDirectoryItem *this, struct IFsiItem *a2)
{
  ImapiComObject *v4; // r13
  unsigned int v5; // r12d
  DWORD TickCount; // eax
  ImapiFsObjectBase ***v7; // r14
  ImapiFsObjectBase *v8; // rax
  CIMAPIException *v9; // rbx
  const struct ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException *v11; // rax
  CIMAPIException **v12; // rbx
  CIMAPIException *v13; // rax
  CIMAPIException *v14; // rax
  CIMAPIException **v15; // rbx
  int v16; // ebx
  __int64 v17; // rdi
  __int64 v18; // rdi
  int v19; // r15d
  ImapiFsObjectBase *v20; // rcx
  __int64 *v21; // rcx
  int v22; // ebx
  CIMAPISystemException *v23; // rax
  CIMAPISystemException *v24; // rax
  CIMAPIException **v25; // rbx
  int v26; // ebx
  __int64 v27; // rdi
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, __int64 *); // rdi
  __int64 v30; // r9
  ImapiFsObjectBase *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rbx
  CIMAPIException *v34; // rax
  CIMAPIException *v35; // rax
  CIMAPIException **v36; // rbx
  CIMAPIException *v37; // rax
  CIMAPIException *v38; // rax
  CIMAPIException **v39; // rbx
  __int64 v41; // [rsp+30h] [rbp-258h] BYREF
  __int64 v42; // [rsp+38h] [rbp-250h] BYREF
  __int64 v43; // [rsp+40h] [rbp-248h] BYREF
  __int64 v44; // [rsp+48h] [rbp-240h] BYREF
  char v45[8]; // [rsp+50h] [rbp-238h] BYREF
  __int64 v46; // [rsp+58h] [rbp-230h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+60h] [rbp-228h] BYREF
  CIMAPIException **v48; // [rsp+68h] [rbp-220h] BYREF
  CIMAPIException **v49; // [rsp+70h] [rbp-218h] BYREF
  CIMAPIException **v50; // [rsp+78h] [rbp-210h] BYREF
  _QWORD v51[2]; // [rsp+80h] [rbp-208h] BYREF
  char v52[8]; // [rsp+90h] [rbp-1F8h] BYREF
  _BYTE v53[88]; // [rsp+98h] [rbp-1F0h] BYREF
  _BYTE v54[88]; // [rsp+F0h] [rbp-198h] BYREF
  _BYTE v55[88]; // [rsp+148h] [rbp-140h] BYREF
  _BYTE v56[88]; // [rsp+1A0h] [rbp-E8h] BYREF
  _BYTE v57[144]; // [rsp+1F8h] [rbp-90h] BYREF
  CIMAPIException **v58; // [rsp+298h] [rbp+10h] BYREF
  unsigned int v59; // [rsp+2A0h] [rbp+18h]
  __int64 v60; // [rsp+2A8h] [rbp+20h] BYREF

  v46 = 0;
  v43 = 0;
  v4 = (CFsiDirectoryItem *)((char *)this - 80);
  v51[1] = (char *)this - 80;
  v5 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  v59 = v5;
  MethodTrace::MethodTrace((MethodTrace *)v52, "CFsiDirectoryItem::Add");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS(v4);
  TickCount = GetTickCount();
  try
  {
    LODWORD(v58) = TickCount;
    if ( !a2 )
    {
      v37 = (CIMAPIException *)operator new(0x58u);
      v58 = (CIMAPIException **)v37;
      if ( v37 )
        v38 = CIMAPIException::CIMAPIException(v37, -2147467261, L"newItem");
      else
        v38 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v58, v38);
      v39 = v58;
      if ( v58 && *v58 )
      {
        CIMAPIException::SetCodeRefInfo(*v58, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 411);
        v51[0] = v39;
        if ( v39 )
          ++*((_DWORD *)v39 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v51;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v57,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v57;
    }
    v7 = (ImapiFsObjectBase ***)((char *)this + 64);
    v8 = **v7;
    if ( !*((_QWORD *)v8 + 9) )
    {
      v9 = (CIMAPIException *)operator new(0x58u);
      v58 = (CIMAPIException **)v9;
      if ( v9 )
      {
        FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(**v7);
        v11 = CIMAPIException::CIMAPIException(v9, -1062555381, *(_QWORD *)FullPathOriginal);
      }
      else
      {
        v11 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v58, v11);
      v12 = v58;
      if ( v58 && *v58 )
      {
        CIMAPIException::SetCodeRefInfo(*v58, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 415);
        pExceptionObject = v12;
        if ( v12 )
          ++*((_DWORD *)v12 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v53,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v53;
    }
    if ( *(int *)(*((_QWORD *)v8 + 8) + 8LL) > 0 )
    {
      v13 = (CIMAPIException *)operator new(0x58u);
      v58 = (CIMAPIException **)v13;
      if ( v13 )
        v14 = CIMAPIException::CIMAPIException(v13, -1062555390);
      else
        v14 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v58, v14);
      v15 = v58;
      if ( v58 && *v58 )
      {
        CIMAPIException::SetCodeRefInfo(*v58, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 419);
        v48 = v15;
        if ( v15 )
          ++*((_DWORD *)v15 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v48;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v54,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v54;
    }
    if ( ((__int64 (__fastcall *)(struct IFsiItem *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_2c941fdc_975b_59be_a960_9a2a262853a5,
           &v46) )
    {
      v22 = ((__int64 (__fastcall *)(struct IFsiItem *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_2c941fdb_975b_59be_a960_9a2a262853a5,
              &v43);
      if ( v22 < 0 )
      {
        v23 = (CIMAPISystemException *)operator new(0x58u);
        v58 = (CIMAPIException **)v23;
        if ( v23 )
          v24 = CIMAPISystemException::CIMAPISystemException(v23, v22);
        else
          v24 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v58, v24);
        v25 = v58;
        if ( v58 && *v58 )
        {
          CIMAPIException::SetCodeRefInfo(*v58, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 433);
          v49 = v25;
          if ( v25 )
            ++*((_DWORD *)v25 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v49;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v55,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v55;
      }
      v41 = 0;
      if ( v43 )
      {
        v42 = 0;
        v26 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v43)(
                v43,
                &GUID_00000000_0000_0000_c000_000000000046,
                &v42);
        if ( v26 >= 0 )
        {
          v27 = v42;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
        }
        else
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
          v27 = 0;
        }
        v41 = v27;
        if ( (int)(v26 + 0x80000000) >= 0 && v26 != -2147467262 )
          _com_issue_error(v26);
      }
      v28 = *(_QWORD *)GetImplementationPtr(v45, &v41);
      v44 = v28;
      if ( v28 )
        ++*(_DWORD *)(v28 + 8);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v45);
      if ( !v28 || !*(_QWORD *)v28 )
      {
        v34 = (CIMAPIException *)operator new(0x58u);
        v58 = (CIMAPIException **)v34;
        if ( v34 )
          v35 = CIMAPIException::CIMAPIException(v34, -1062555392);
        else
          v35 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v58, v35);
        v36 = v58;
        if ( v58 && *v58 )
        {
          CIMAPIException::SetCodeRefInfo(*v58, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 438);
          v50 = v36;
          if ( v36 )
            ++*((_DWORD *)v36 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v50;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v56,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v56;
      }
      v60 = 0;
      v29 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 176LL);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
      v60 = 0;
      v19 = v29(v43, &v60);
      if ( v19 < 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
        SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v44);
        goto LABEL_89;
      }
      v31 = **v7;
      LOBYTE(v30) = *(_BYTE *)(*((_QWORD *)v31 + 8) + 672LL);
      v32 = v60;
      v42 = v28;
      ++*(_DWORD *)(v28 + 8);
      ImapiDirectoryInfo::AddFile(v31, &v42, v32, v30, 0);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
      v21 = &v44;
    }
    else
    {
      v60 = 0;
      if ( v46 )
      {
        v41 = 0;
        v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v46)(
                v46,
                &GUID_00000000_0000_0000_c000_000000000046,
                &v41);
        if ( v16 >= 0 )
        {
          v17 = v41;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
        }
        else
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v60);
          v17 = 0;
        }
        v60 = v17;
        if ( (int)(v16 + 0x80000000) >= 0 && v16 != -2147467262 )
          _com_issue_error(v16);
      }
      v18 = *(_QWORD *)GetImplementationPtr(&v44, &v60);
      v42 = v18;
      if ( v18 )
        ++*(_DWORD *)(v18 + 8);
      v19 = 0;
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v44);
      v20 = **v7;
      v41 = v18;
      if ( v18 )
        ++*(_DWORD *)(v18 + 8);
      ImapiDirectoryInfo::AddDirectory(v20, &v41);
      v21 = &v42;
    }
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v21);
    v33 = *((_QWORD *)**v7 + 8);
    *(_DWORD *)(v33 + 808) += GetTickCount() - (_DWORD)v58;
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
LABEL_89:
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v19 < 0 )
    FileSystemImage::RollbackRecover(*((FileSystemImage **)**v7 + 8), v5, 1);
  ImapiComObject::UnlockCS(v4);
  MethodTrace::~MethodTrace((MethodTrace *)v52);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800208a0  mov     [rsp+arg_0], rcx
0x1800208a5  push    rbx
0x1800208a6  push    rsi
0x1800208a7  push    rdi
0x1800208a8  push    r12
0x1800208aa  push    r13
0x1800208ac  push    r14
0x1800208ae  push    r15
0x1800208b0  sub     rsp, 250h
0x1800208b7  mov     rbx, rdx
0x1800208ba  mov     r14, rcx
0x1800208bd  xor     esi, esi
0x1800208bf  mov     [rsp+288h+var_230], rsi
0x1800208c4  mov     [rsp+288h+var_248], rsi
0x1800208c9  lea     r13, [rcx-50h]
0x1800208cd  mov     [rsp+288h+var_200], r13
0x1800208d5  mov     rax, [r13+90h]
0x1800208dc  mov     r8, [rax]
0x1800208df  mov     rax, [r8+40h]
0x1800208e3  mov     r12d, [rax+14h]
0x1800208e7  mov     [rsp+288h+arg_10], r12d
0x1800208ef  lea     rdx, aCfsidirectoryi_20; "CFsiDirectoryItem::Add"
0x1800208f6  lea     rcx, [rsp+288h+var_1F8]; this
0x1800208fe  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180020903  nop
0x180020904  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180020909  nop
0x18002090a  mov     rcx, r13; this
0x18002090d  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180020912  call    cs:__imp_GetTickCount
0x180020918  mov     dword ptr [rsp+288h+arg_8], eax
0x18002091f  test    rbx, rbx
0x180020922  jz      loc_180020E7D
0x180020928  add     r14, 40h ; '@'
0x18002092c  mov     rcx, [r14]
0x18002092f  mov     rax, [rcx]
0x180020932  cmp     [rax+48h], rsi
0x180020936  jnz     loc_1800209F3
0x18002093c  lea     ecx, [rsi+58h]; unsigned __int64
0x18002093f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020944  mov     rbx, rax
0x180020947  mov     [rsp+288h+arg_8], rax
0x18002094f  test    rax, rax
0x180020952  jz      short loc_180020971
0x180020954  mov     rcx, [r14]
0x180020957  mov     rcx, [rcx]; this
0x18002095a  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x18002095f  mov     r8, [rax]
0x180020962  mov     edx, 0C0AAB10Bh; int
0x180020967  mov     rcx, rbx; this
0x18002096a  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18002096f  jmp     short loc_180020974
0x180020971  mov     rax, rsi
0x180020974  mov     rdx, rax
0x180020977  lea     rcx, [rsp+288h+arg_8]
0x18002097f  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180020984  nop
0x180020985  mov     rbx, [rsp+288h+arg_8]
0x18002098d  test    rbx, rbx
0x180020990  jz      short loc_1800209CA
0x180020992  cmp     [rbx], rsi
0x180020995  jz      short loc_1800209CA
0x180020997  mov     r8d, 19Fh; int
0x18002099d  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x1800209a4  mov     rcx, [rbx]; this
0x1800209a7  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800209ac  mov     [rsp+288h+pExceptionObject], rbx
0x1800209b1  test    rbx, rbx
0x1800209b4  jz      short loc_1800209B9
0x1800209b6  inc     dword ptr [rbx+8]
0x1800209b9  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800209c0  lea     rcx, [rsp+288h+pExceptionObject]; pExceptionObject
0x1800209c5  call    _CxxThrowException_0
0x1800209ca  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800209d1  lea     rcx, [rsp+288h+var_1F0]; this
0x1800209d9  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800209de  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800209e5  lea     rcx, [rsp+288h+var_1F0]; pExceptionObject
0x1800209ed  call    _CxxThrowException_0
0x1800209f3  mov     rax, [rax+40h]
0x1800209f7  cmp     [rax+8], esi
0x1800209fa  jle     loc_180020AA8
0x180020a00  mov     ecx, 58h ; 'X'; unsigned __int64
0x180020a05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020a0a  mov     [rsp+288h+arg_8], rax
0x180020a12  test    rax, rax
0x180020a15  jz      short loc_180020A26
0x180020a17  mov     edx, 0C0AAB102h; int
0x180020a1c  mov     rcx, rax; this
0x180020a1f  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180020a24  jmp     short loc_180020A29
0x180020a26  mov     rax, rsi
0x180020a29  mov     rdx, rax
0x180020a2c  lea     rcx, [rsp+288h+arg_8]
0x180020a34  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180020a39  nop
0x180020a3a  mov     rbx, [rsp+288h+arg_8]
0x180020a42  test    rbx, rbx
0x180020a45  jz      short loc_180020A7F
0x180020a47  cmp     [rbx], rsi
0x180020a4a  jz      short loc_180020A7F
0x180020a4c  mov     r8d, 1A3h; int
0x180020a52  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180020a59  mov     rcx, [rbx]; this
0x180020a5c  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180020a61  mov     [rsp+288h+var_220], rbx
0x180020a66  test    rbx, rbx
0x180020a69  jz      short loc_180020A6E
0x180020a6b  inc     dword ptr [rbx+8]
0x180020a6e  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180020a75  lea     rcx, [rsp+288h+var_220]; pExceptionObject
0x180020a7a  call    _CxxThrowException_0
0x180020a7f  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180020a86  lea     rcx, [rsp+288h+var_198]; this
0x180020a8e  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180020a93  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180020a9a  lea     rcx, [rsp+288h+var_198]; pExceptionObject
0x180020aa2  call    _CxxThrowException_0
0x180020aa8  mov     rax, [rbx]
0x180020aab  lea     r8, [rsp+288h+var_230]
0x180020ab0  lea     rdx, _GUID_2c941fdc_975b_59be_a960_9a2a262853a5
0x180020ab7  mov     rcx, rbx
0x180020aba  mov     rax, [rax]
0x180020abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ac2  test    eax, eax
0x180020ac4  jnz     loc_180020B95
0x180020aca  mov     [rsp+288h+arg_18], rsi
0x180020ad2  mov     rcx, [rsp+288h+var_230]
0x180020ad7  test    rcx, rcx
0x180020ada  jz      short loc_180020B3E
0x180020adc  mov     [rsp+288h+var_258], rsi
0x180020ae1  mov     rax, [rcx]
0x180020ae4  lea     r8, [rsp+288h+var_258]
0x180020ae9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180020af0  mov     rax, [rax]
0x180020af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020af8  mov     ebx, eax
0x180020afa  lea     rcx, [rsp+288h+arg_18]
0x180020b02  test    eax, eax
0x180020b04  jns     short loc_180020B10
0x180020b06  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020b0b  mov     rdi, rsi
0x180020b0e  jmp     short loc_180020B1B
0x180020b10  mov     rdi, [rsp+288h+var_258]
0x180020b15  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020b1a  nop
0x180020b1b  mov     [rsp+288h+arg_18], rdi
0x180020b23  mov     ecx, 80000000h
0x180020b28  lea     eax, [rbx+rcx]
0x180020b2b  test    ecx, eax
0x180020b2d  jnz     short loc_180020B3E
0x180020b2f  cmp     ebx, 80004002h
0x180020b35  jz      short loc_180020B3E
0x180020b37  mov     ecx, ebx; int
0x180020b39  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180020b3e  lea     rdx, [rsp+288h+arg_18]
0x180020b46  lea     rcx, [rsp+288h+var_240]
0x180020b4b  call    ?GetImplementationPtr@@YA?AV?$SmartClassPtr@VImapiImplementation@@V1@@@V?$_com_ptr_t@V?$_com_IIID@UIUnknown@@$1?_GUID_00000000_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@@Z; GetImplementationPtr(_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>)
0x180020b50  mov     rdi, [rax]
0x180020b53  mov     [rsp+288h+var_250], rdi
0x180020b58  test    rdi, rdi
0x180020b5b  jz      short loc_180020B60
0x180020b5d  inc     dword ptr [rdi+8]
0x180020b60  mov     r15d, esi
0x180020b63  lea     rcx, [rsp+288h+var_240]; void *
0x180020b68  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180020b6d  mov     rax, [r14]
0x180020b70  mov     rcx, [rax]
0x180020b73  mov     [rsp+288h+var_258], rdi
0x180020b78  test    rdi, rdi
0x180020b7b  jz      short loc_180020B80
0x180020b7d  inc     dword ptr [rdi+8]
0x180020b80  lea     rdx, [rsp+288h+var_258]
0x180020b85  call    ?AddDirectory@ImapiDirectoryInfo@@QEAAXV?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@@Z; ImapiDirectoryInfo::AddDirectory(SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>)
0x180020b8a  nop
0x180020b8b  lea     rcx, [rsp+288h+var_250]
0x180020b90  jmp     loc_180020DAE
0x180020b95  mov     rax, [rbx]
0x180020b98  lea     r8, [rsp+288h+var_248]
0x180020b9d  lea     rdx, _GUID_2c941fdb_975b_59be_a960_9a2a262853a5
0x180020ba4  mov     rcx, rbx
0x180020ba7  mov     rax, [rax]
0x180020baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020baf  mov     ebx, eax
0x180020bb1  test    eax, eax
0x180020bb3  jns     loc_180020C5E
0x180020bb9  mov     ecx, 58h ; 'X'; unsigned __int64
0x180020bbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020bc3  mov     [rsp+288h+arg_8], rax
0x180020bcb  test    rax, rax
0x180020bce  jz      short loc_180020BDC
0x180020bd0  mov     edx, ebx; int
0x180020bd2  mov     rcx, rax; this
0x180020bd5  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180020bda  jmp     short loc_180020BDF
0x180020bdc  mov     rax, rsi
0x180020bdf  mov     rdx, rax
0x180020be2  lea     rcx, [rsp+288h+arg_8]
0x180020bea  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180020bef  nop
0x180020bf0  mov     rbx, [rsp+288h+arg_8]
0x180020bf8  test    rbx, rbx
0x180020bfb  jz      short loc_180020C35
0x180020bfd  cmp     [rbx], rsi
0x180020c00  jz      short loc_180020C35
0x180020c02  mov     r8d, 1B1h; int
0x180020c08  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180020c0f  mov     rcx, [rbx]; this
0x180020c12  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180020c17  mov     [rsp+288h+var_218], rbx
0x180020c1c  test    rbx, rbx
0x180020c1f  jz      short loc_180020C24
0x180020c21  inc     dword ptr [rbx+8]
0x180020c24  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180020c2b  lea     rcx, [rsp+288h+var_218]; pExceptionObject
0x180020c30  call    _CxxThrowException_0
0x180020c35  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180020c3c  lea     rcx, [rsp+288h+var_140]; this
0x180020c44  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180020c49  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180020c50  lea     rcx, [rsp+288h+var_140]; pExceptionObject
0x180020c58  call    _CxxThrowException_0
0x180020c5e  mov     [rsp+288h+var_258], rsi
0x180020c63  mov     rcx, [rsp+288h+var_248]
0x180020c68  test    rcx, rcx
0x180020c6b  jz      short loc_180020CC9
0x180020c6d  mov     [rsp+288h+var_250], rsi
0x180020c72  mov     rax, [rcx]
0x180020c75  lea     r8, [rsp+288h+var_250]
0x180020c7a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180020c81  mov     rax, [rax]
0x180020c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c89  mov     ebx, eax
0x180020c8b  lea     rcx, [rsp+288h+var_258]
0x180020c90  test    eax, eax
0x180020c92  jns     short loc_180020C9E
0x180020c94  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020c99  mov     rdi, rsi
0x180020c9c  jmp     short loc_180020CA9
0x180020c9e  mov     rdi, [rsp+288h+var_250]
0x180020ca3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020ca8  nop
0x180020ca9  mov     [rsp+288h+var_258], rdi
0x180020cae  mov     ecx, 80000000h
0x180020cb3  lea     eax, [rbx+rcx]
0x180020cb6  test    ecx, eax
0x180020cb8  jnz     short loc_180020CC9
0x180020cba  cmp     ebx, 80004002h
0x180020cc0  jz      short loc_180020CC9
0x180020cc2  mov     ecx, ebx; int
0x180020cc4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180020cc9  lea     rdx, [rsp+288h+var_258]
0x180020cce  lea     rcx, [rsp+288h+var_238]
0x180020cd3  call    ?GetImplementationPtr@@YA?AV?$SmartClassPtr@VImapiImplementation@@V1@@@V?$_com_ptr_t@V?$_com_IIID@UIUnknown@@$1?_GUID_00000000_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@@Z; GetImplementationPtr(_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>)
0x180020cd8  mov     rbx, [rax]
0x180020cdb  mov     [rsp+288h+var_240], rbx
0x180020ce0  test    rbx, rbx
0x180020ce3  jz      short loc_180020CE8
0x180020ce5  inc     dword ptr [rbx+8]
0x180020ce8  lea     rcx, [rsp+288h+var_238]; void *
0x180020ced  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180020cf2  test    rbx, rbx
0x180020cf5  jz      loc_180020DD5
0x180020cfb  cmp     [rbx], rsi
0x180020cfe  jz      loc_180020DD5
0x180020d04  mov     [rsp+288h+arg_18], rsi
0x180020d0c  mov     rax, [rsp+288h+var_248]
0x180020d11  mov     rcx, [rax]
0x180020d14  mov     rdi, [rcx+0B0h]
0x180020d1b  lea     rcx, [rsp+288h+arg_18]
0x180020d23  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020d28  mov     [rsp+288h+arg_18], rsi
0x180020d30  lea     rdx, [rsp+288h+arg_18]
0x180020d38  mov     rcx, [rsp+288h+var_248]
0x180020d3d  mov     rax, rdi
0x180020d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d45  mov     r15d, eax
0x180020d48  test    eax, eax
0x180020d4a  jns     short loc_180020D6A
0x180020d4c  lea     rcx, [rsp+288h+arg_18]
0x180020d54  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020d59  nop
0x180020d5a  lea     rcx, [rsp+288h+var_240]; void *
0x180020d5f  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180020d64  nop
0x180020d65  jmp     loc_180020F56
0x180020d6a  mov     rax, [r14]
0x180020d6d  mov     rcx, [rax]
0x180020d70  mov     rax, [rcx+40h]
0x180020d74  mov     r9b, [rax+2A0h]
0x180020d7b  mov     r8, [rsp+288h+arg_18]
0x180020d83  mov     [rsp+288h+var_250], rbx
0x180020d88  inc     dword ptr [rbx+8]
0x180020d8b  mov     [rsp+288h+var_268], sil
0x180020d90  lea     rdx, [rsp+288h+var_250]
0x180020d95  call    ?AddFile@ImapiDirectoryInfo@@QEAAXV?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@PEAUIStream@@_N2@Z; ImapiDirectoryInfo::AddFile(SmartClassPtr<ImapiFileInfo,ImapiImplementation>,IStream *,bool,bool)
0x180020d9a  nop
0x180020d9b  lea     rcx, [rsp+288h+arg_18]
0x180020da3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020da8  nop
  ... truncated ...
```
