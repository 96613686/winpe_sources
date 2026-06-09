# FileSystemImage::ChooseImageDefaults(IDiscRecorder2 *)

- ea: `0x1800443c4`
- end: `0x180044729`
- name: `?ChooseImageDefaults@FileSystemImage@@QEAAXPEAUIDiscRecorder2@@@Z`
- size: `869`
- prototype: `void __fastcall(FileSystemImage *__hidden this, struct IDiscRecorder2 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180056b90`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18001f27c`
- `0x1800251dc`
- `0x180028568`
- `0x180028798`
- `0x180028ca8`
- `0x18002b268`
- `0x18002d4e4`
- `0x1800443c4`
- `0x180044730`
- `0x180048534`
- `0x180088010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180044457`
- `ole32!CoCreateInstance` at `0x180044457`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FileSystemImage::ChooseImageDefaults(FileSystemImage *this, struct IDiscRecorder2 *a2)
{
  FileSystemImage *v3; // rdi
  _DWORD *v4; // rsi
  HRESULT v5; // r15d
  CIMAPISystemException *v6; // rax
  int v7; // r15d
  CIMAPIPassThruException *v8; // rax
  _QWORD *v9; // rcx
  unsigned int v10; // edx
  CIMAPIException *v11; // rcx
  CIMAPIException *v12; // rax
  LPVOID ppv; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[8]; // [rsp+38h] [rbp-F0h] BYREF
  _BYTE v15[8]; // [rsp+40h] [rbp-E8h] BYREF
  _DWORD *v16; // [rsp+48h] [rbp-E0h]
  _BYTE v17[88]; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v18[128]; // [rsp+A8h] [rbp-80h] BYREF
  FileSystemImage *v19; // [rsp+130h] [rbp+8h] BYREF
  unsigned int v20; // [rsp+140h] [rbp+18h] BYREF
  _IMAPI_MEDIA_PHYSICAL_TYPE v21; // [rsp+148h] [rbp+20h] BYREF

  v19 = this;
  v3 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 101, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  ppv = 0;
  v20 = 0;
  v4 = (_DWORD *)((char *)v3 + 24);
  v16 = (_DWORD *)((char *)v3 + 24);
  *((_DWORD *)v3 + 6) = 0;
  *((_BYTE *)v3 + 28) = 0;
  v5 = CoCreateInstance(&CLSID_MsftDiscFormat2Data, 0, 0x17u, &GUID_27354153_9f64_5b0f_8f00_5d77afbe261e, &ppv);
  if ( v5 < 0 )
  {
    v6 = (CIMAPISystemException *)operator new(0x58u);
    v19 = v6;
    if ( v6 )
      v6 = CIMAPISystemException::CIMAPISystemException(v6, v5);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v19, v6);
    if ( v19 )
    {
      if ( *(_QWORD *)v19 )
      {
        v11 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v19);
        CIMAPIException::SetCodeRefInfo(v11, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 2796);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(pExceptionObject, &v19);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)pExceptionObject;
      }
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v17, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v17;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, struct IDiscRecorder2 *))(*(_QWORD *)ppv + 96LL))(ppv, a2);
  if ( v7 < 0 )
  {
    v8 = (CIMAPIPassThruException *)operator new(0x58u);
    v19 = v8;
    if ( v8 )
      v8 = CIMAPIPassThruException::CIMAPIPassThruException(v8, v7);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v19, v8);
    if ( v19 && *(_QWORD *)v19 )
    {
      v12 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&v19);
      CIMAPIException::SetCodeRefInfo(v12, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 2804);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v15, &v19);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v15;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v18, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v18;
  }
  v9 = (_QWORD *)*((_QWORD *)v3 + 98);
  if ( v9 && *v9 )
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 80LL))(*v9);
  }
  else if ( (*(int (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 168LL))(ppv, &v20) < 0 )
  {
    v20 = 0;
  }
  v21 = IMAPI_MEDIA_TYPE_UNKNOWN;
  if ( (*(int (__fastcall **)(LPVOID, _IMAPI_MEDIA_PHYSICAL_TYPE *))(*(_QWORD *)ppv + 232LL))(ppv, &v21) < 0 )
  {
LABEL_25:
    *v4 = 4;
    *((_DWORD *)v3 + 8) = 258;
    v10 = v20;
    if ( (int)v20 < 0x100000 && v20 )
      *v4 = 7;
  }
  else
  {
    try
    {
      FileSystemImage::ChooseImageDefaults(v3, v21);
    }
    catch ( ... )
    {
      v3 = v19;
      v4 = v16;
      goto LABEL_25;
    }
    v10 = v20;
  }
  *((_DWORD *)v3 + 9) = 1;
  FileSystemImage::SetFreeMediaBlocks(v3, v10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 102, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
}

```

## disassembly

```asm
0x1800443c4  mov     [rsp+arg_0], rcx
0x1800443c9  push    rsi
0x1800443ca  push    rdi
0x1800443cb  push    r12
0x1800443cd  push    r14
0x1800443cf  push    r15
0x1800443d1  sub     rsp, 100h
0x1800443d8  mov     r12, rdx
0x1800443db  mov     rdi, rcx
0x1800443de  lea     r14, WPP_GLOBAL_Control
0x1800443e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800443ec  cmp     rcx, r14
0x1800443ef  jz      short loc_180044412
0x1800443f1  test    byte ptr [rcx+44h], 8
0x1800443f5  jz      short loc_180044412
0x1800443f7  cmp     byte ptr [rcx+41h], 5
0x1800443fb  jb      short loc_180044412
0x1800443fd  mov     edx, 65h ; 'e'
0x180044402  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x180044409  mov     rcx, [rcx+38h]
0x18004440d  call    WPP_SF_
0x180044412  mov     [rsp+128h+var_F8], 0
0x18004441b  mov     [rsp+128h+arg_10], 0
0x180044426  lea     rsi, [rdi+18h]
0x18004442a  mov     [rsp+128h+var_E0], rsi
0x18004442f  mov     dword ptr [rsi], 0
0x180044435  mov     byte ptr [rdi+1Ch], 0
0x180044439  lea     rax, [rsp+128h+var_F8]
0x18004443e  mov     [rsp+128h+ppv], rax; ppv
0x180044443  lea     r9, _GUID_27354153_9f64_5b0f_8f00_5d77afbe261e; riid
0x18004444a  xor     edx, edx; pUnkOuter
0x18004444c  lea     r8d, [rdx+17h]; dwClsContext
0x180044450  lea     rcx, CLSID_MsftDiscFormat2Data; rclsid
0x180044457  call    cs:__imp_CoCreateInstance
0x18004445d  mov     r15d, eax
0x180044460  test    eax, eax
0x180044462  jns     short loc_1800444B8
0x180044464  mov     ecx, 58h ; 'X'; unsigned __int64
0x180044469  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004446e  mov     [rsp+128h+arg_0], rax
0x180044476  test    rax, rax
0x180044479  jz      short loc_180044487
0x18004447b  mov     edx, r15d; int
0x18004447e  mov     rcx, rax; this
0x180044481  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180044486  nop
0x180044487  mov     rdx, rax
0x18004448a  lea     rcx, [rsp+128h+arg_0]
0x180044492  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180044497  nop
0x180044498  mov     rax, [rsp+128h+arg_0]
0x1800444a0  test    rax, rax
0x1800444a3  jz      loc_180044697
0x1800444a9  cmp     qword ptr [rax], 0
0x1800444ad  jz      loc_180044697
0x1800444b3  jmp     loc_180044651
0x1800444b8  mov     rcx, [rsp+128h+var_F8]
0x1800444bd  mov     rax, [rcx]
0x1800444c0  mov     rdx, r12
0x1800444c3  mov     rax, [rax+60h]
0x1800444c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444cc  mov     r15d, eax
0x1800444cf  test    eax, eax
0x1800444d1  jns     short loc_180044527
0x1800444d3  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800444d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800444dd  mov     [rsp+128h+arg_0], rax
0x1800444e5  test    rax, rax
0x1800444e8  jz      short loc_1800444F6
0x1800444ea  mov     edx, r15d; int
0x1800444ed  mov     rcx, rax; this
0x1800444f0  call    ??0CIMAPIPassThruException@@QEAA@J@Z; CIMAPIPassThruException::CIMAPIPassThruException(long)
0x1800444f5  nop
0x1800444f6  mov     rdx, rax
0x1800444f9  lea     rcx, [rsp+128h+arg_0]
0x180044501  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180044506  nop
0x180044507  mov     rax, [rsp+128h+arg_0]
0x18004450f  test    rax, rax
0x180044512  jz      loc_180044700
0x180044518  cmp     qword ptr [rax], 0
0x18004451c  jz      loc_180044700
0x180044522  jmp     loc_1800446BA
0x180044527  mov     rcx, [rdi+310h]
0x18004452e  test    rcx, rcx
0x180044531  jz      short loc_180044551
0x180044533  cmp     qword ptr [rcx], 0
0x180044537  jz      short loc_180044551
0x180044539  mov     rcx, [rcx]
0x18004453c  mov     rax, [rcx]
0x18004453f  mov     rax, [rax+50h]
0x180044543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044548  mov     [rsp+128h+arg_10], eax
0x18004454f  jmp     short loc_18004457C
0x180044551  mov     rcx, [rsp+128h+var_F8]
0x180044556  mov     rax, [rcx]
0x180044559  lea     rdx, [rsp+128h+arg_10]
0x180044561  mov     rax, [rax+0A8h]
0x180044568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004456d  test    eax, eax
0x18004456f  jns     short loc_18004457C
0x180044571  mov     [rsp+128h+arg_10], 0
0x18004457c  mov     [rsp+128h+arg_18], 0
0x180044587  mov     rcx, [rsp+128h+var_F8]
0x18004458c  mov     rax, [rcx]
0x18004458f  lea     rdx, [rsp+128h+arg_18]
0x180044597  mov     rax, [rax+0E8h]
0x18004459e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445a3  test    eax, eax
0x1800445a5  js      short loc_1800445D4
0x1800445a7  mov     edx, [rsp+128h+arg_18]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x1800445ae  mov     rcx, rdi; this
0x1800445b1  call    ?ChooseImageDefaults@FileSystemImage@@QEAAXW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z; FileSystemImage::ChooseImageDefaults(_IMAPI_MEDIA_PHYSICAL_TYPE)
0x1800445b6  nop
0x1800445b7  mov     edx, [rsp+128h+arg_10]
0x1800445be  jmp     short loc_1800445FA
0x1800445c0  lea     r14, WPP_GLOBAL_Control
0x1800445c7  mov     rdi, [rsp+128h+arg_0]
0x1800445cf  mov     rsi, [rsp+128h+var_E0]
0x1800445d4  mov     dword ptr [rsi], 4
0x1800445da  mov     dword ptr [rdi+20h], 102h
0x1800445e1  mov     edx, [rsp+128h+arg_10]; unsigned int
0x1800445e8  cmp     edx, 100000h
0x1800445ee  jge     short loc_1800445FA
0x1800445f0  test    edx, edx
0x1800445f2  jz      short loc_1800445FA
0x1800445f4  mov     dword ptr [rsi], 7
0x1800445fa  mov     dword ptr [rdi+24h], 1
0x180044601  mov     rcx, rdi; this
0x180044604  call    ?SetFreeMediaBlocks@FileSystemImage@@QEAAXK@Z; FileSystemImage::SetFreeMediaBlocks(ulong)
0x180044609  mov     rcx, cs:WPP_GLOBAL_Control
0x180044610  cmp     rcx, r14
0x180044613  jz      short loc_180044637
0x180044615  test    byte ptr [rcx+44h], 8
0x180044619  jz      short loc_180044637
0x18004461b  cmp     byte ptr [rcx+41h], 5
0x18004461f  jb      short loc_180044637
0x180044621  mov     edx, 66h ; 'f'
0x180044626  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x18004462d  mov     rcx, [rcx+38h]
0x180044631  call    WPP_SF_
0x180044636  nop
0x180044637  lea     rcx, [rsp+128h+var_F8]
0x18004463c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044641  add     rsp, 100h
0x180044648  pop     r15
0x18004464a  pop     r14
0x18004464c  pop     r12
0x18004464e  pop     rdi
0x18004464f  pop     rsi
0x180044650  retn
0x180044651  lea     rcx, [rsp+128h+arg_0]
0x180044659  call    ??C?$SmartClassPtr@VCIMAPIException@@V1@@@QEBAPEAVCIMAPIException@@XZ; SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(void)
0x18004465e  mov     rcx, rax; this
0x180044661  mov     r8d, 0AECh; int
0x180044667  lea     rdx, aDriversStorage_12; "drivers\\storage\\imapi2\\filesystemima"...
0x18004466e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180044673  lea     rdx, [rsp+128h+arg_0]
0x18004467b  lea     rcx, [rsp+128h+pExceptionObject]
0x180044680  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@AEBV0@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(SmartPtr<CIMAPIException> const &)
0x180044685  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18004468c  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180044691  call    _CxxThrowException_0
0x180044697  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18004469e  lea     rcx, [rsp+128h+var_D8]; this
0x1800446a3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800446a8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800446af  lea     rcx, [rsp+128h+var_D8]; pExceptionObject
0x1800446b4  call    _CxxThrowException_0
0x1800446ba  lea     rcx, [rsp+128h+arg_0]
0x1800446c2  call    ??C?$SmartClassPtr@VCIMAPIException@@V1@@@QEBAPEAVCIMAPIException@@XZ; SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(void)
0x1800446c7  mov     rcx, rax; this
0x1800446ca  mov     r8d, 0AF4h; int
0x1800446d0  lea     rdx, aDriversStorage_12; "drivers\\storage\\imapi2\\filesystemima"...
0x1800446d7  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800446dc  lea     rdx, [rsp+128h+arg_0]
0x1800446e4  lea     rcx, [rsp+128h+var_E8]
0x1800446e9  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@AEBV0@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(SmartPtr<CIMAPIException> const &)
0x1800446ee  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800446f5  lea     rcx, [rsp+128h+var_E8]; pExceptionObject
0x1800446fa  call    _CxxThrowException_0
0x180044700  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180044707  lea     rcx, [rsp+128h+var_80]; this
0x18004470f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180044714  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18004471b  lea     rcx, [rsp+128h+var_80]; pExceptionObject
0x180044723  call    _CxxThrowException_0
```
