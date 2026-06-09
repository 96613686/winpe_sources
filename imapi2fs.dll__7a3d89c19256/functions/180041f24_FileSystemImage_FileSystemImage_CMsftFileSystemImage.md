# FileSystemImage::FileSystemImage(CMsftFileSystemImage *)

- ea: `0x180041f24`
- end: `0x180042310`
- name: `??0FileSystemImage@@QEAA@PEAVCMsftFileSystemImage@@@Z`
- size: `1004`
- prototype: `FileSystemImage *__fastcall(FileSystemImage *__hidden this, struct CMsftFileSystemImage *)`
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1800072d0`
- `0x180010b9c`

## callees

- `0x1800022c0`
- `0x180005040`
- `0x180005438`
- `0x18000550c`
- `0x18000726c`
- `0x18000c888`
- `0x18000c8d0`
- `0x180017090`
- `0x1800199d8`
- `0x18002502c`
- `0x180028568`
- `0x1800320d4`
- `0x18003239c`
- `0x180041f24`
- `0x180042770`
- `0x180047b30`
- `0x180049eec`
- `0x18004a0a8`
- `0x18004a8c8`
- `0x18004aab0`
- `0x1800517e8`
- `0x18008170e`
- `0x180081750`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x18004221e`
- `KERNEL32!GetTempPath2W` at `0x18004221e`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
FileSystemImage *__fastcall FileSystemImage::FileSystemImage(FileSystemImage *this, struct CMsftFileSystemImage *a2)
{
  char *v3; // rdi
  int i; // ecx
  Iso9660FileSystemSupport *v5; // rax
  Iso9660FileSystemSupport *v6; // rax
  JolietFileSystemSupport *v7; // rax
  JolietFileSystemSupport *v8; // rax
  UdfFileSystemSupport *v9; // rax
  UdfFileSystemSupport *v10; // rax
  ImapiDirectoryInfo *v11; // rax
  ImapiDirectoryInfo *v12; // rax
  __int64 v13; // rax
  FileSystemImage *v15; // rdi
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  int v17; // ebx
  __int64 v18; // rcx
  FileSystemImage *v19; // rdi
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  int v21; // ebx
  __int64 v22; // rcx
  Iso9660FileSystemSupport *v23; // [rsp+30h] [rbp-278h] BYREF
  FileSystemImage *v24; // [rsp+38h] [rbp-270h]
  struct CMsftFileSystemImage *v25; // [rsp+40h] [rbp-268h]
  _BYTE v26[528]; // [rsp+50h] [rbp-258h] BYREF
  CIMAPIException *v27; // [rsp+260h] [rbp-48h] BYREF
  __int64 v28; // [rsp+268h] [rbp-40h] BYREF

  v25 = a2;
  v24 = this;
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &FileSystemImage::`vftable';
  v3 = (char *)this + 40;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 5) = std::_List_alloc<0,std::_List_base_types<SmartClassPtr<ImapiBlockRange,ImapiImplementation>>>::_Buynode0(
                            this,
                            0,
                            0);
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>((char *)this + 56, 0);
  `eh vector constructor iterator'(
    (char *)this + 72,
    8u,
    0x20u,
    (void (*)(void *))FSI_UDF::extent_ad::extent_ad,
    ATL::CComPtr<IDiscFormat2Data>::~CComPtr<IDiscFormat2Data>);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 336);
  *((_QWORD *)this + 44) = 0;
  *((_DWORD *)this + 90) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 584);
  SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>((char *)this + 680);
  SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>((char *)this + 704);
  SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>((char *)this + 712);
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 10;
  *((_QWORD *)this + 96) = 0;
  SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>((char *)this + 784, 0);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 800);
  *((_WORD *)this + 8) = 0;
  *((_BYTE *)this + 18) = 0;
  *((_DWORD *)this + 5) = 0;
  *((_DWORD *)this + 6) = 7;
  *((_BYTE *)this + 28) = 0;
  *((_DWORD *)this + 8) = 258;
  *((_DWORD *)this + 9) = 1;
  std::list<SmartClassPtr<ImapiBlockRange,ImapiImplementation>>::clear(v3);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 328);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 336);
  *((_BYTE *)this + 344) = 0;
  *((_QWORD *)this + 46) = 1;
  *((_DWORD *)this + 94) = 0;
  *(_QWORD *)((char *)this + 604) = 332800;
  *((_QWORD *)this + 97) = 0;
  try
  {
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v23, 0);
    SmartPtr<ImportMetadata>::operator=((char *)this + 784, &v23);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v23);
    *((_BYTE *)this + 792) = 0;
    *(_QWORD *)((char *)this + 380) = 0;
    *((_DWORD *)this + 97) = 0;
    *((_WORD *)this + 196) = 257;
    *((_DWORD *)this + 99) = 32;
    *((_DWORD *)this + 203) = -1;
    *((_DWORD *)this + 202) = 0;
    *((_DWORD *)this + 164) = 3;
    for ( i = 0; i < 3; ++i )
    {
      *((_DWORD *)this + i + 148) = 0;
      *((_QWORD *)this + i + 79) = 0;
    }
    *((_DWORD *)this + 16) = 0;
    v5 = (Iso9660FileSystemSupport *)operator new(0x90u);
    v23 = v5;
    if ( v5 )
      v6 = Iso9660FileSystemSupport::Iso9660FileSystemSupport(v5, this);
    else
      v6 = 0;
    *((_QWORD *)this + 79) = v6;
    v7 = (JolietFileSystemSupport *)operator new(0x60u);
    v23 = v7;
    if ( v7 )
      v8 = JolietFileSystemSupport::JolietFileSystemSupport(v7, this);
    else
      v8 = 0;
    *((_QWORD *)this + 80) = v8;
    v9 = (UdfFileSystemSupport *)operator new(0x98u);
    v23 = v9;
    if ( v9 )
      v10 = UdfFileSystemSupport::UdfFileSystemSupport(v9, this);
    else
      v10 = 0;
    *((_QWORD *)this + 81) = v10;
    v11 = (ImapiDirectoryInfo *)operator new(0x318u);
    v23 = v11;
    if ( v11 )
      v12 = ImapiDirectoryInfo::ImapiDirectoryInfo(v11, this);
    else
      v12 = 0;
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v23, v12);
    SmartPtr<ImportMetadata>::operator=((char *)this + 56, &v23);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v23);
    GetTempPath2W(260, v26);
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 584, v26);
    v13 = FileSystemImage::CreateStashFile(this, &v23, L"DAT", L"data");
    SmartPtr<CFsiStashFile>::operator=((char *)this + 680, v13);
    SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(&v23);
    *((_BYTE *)this + 672) = 0;
    *((_QWORD *)this + 86) = 0;
    *((_DWORD *)this + 174) = 0;
    *((_DWORD *)this + 180) = 0;
    ATL::CRBTree<unsigned __int64,SmartClassPtr<ImapiFileInfo,ImapiImplementation>,ATL::CElementTraits<unsigned __int64>,ATL::CElementTraits<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::RemoveAll((char *)this + 728);
    memset_0((char *)this + 400, 0, 0xB8u);
    *((_QWORD *)this + 83) = v25;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
    }
  }
  catch ( CIMAPIException *v27 )
  {
    v17 = 0;
    v15 = v24;
    while ( 1 )
    {
      v16 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v15 + v17 + 79);
      if ( v16 )
        (**v16)(v16, 1);
      if ( ++v17 >= 3 )
      {
        if ( *((_QWORD *)v15 + 85) )
          v18 = **((_QWORD **)v15 + 85);
        else
          v18 = 0;
        if ( v18 )
        {
          SmartPtr<CFsiStashFile>::operator=((char *)v15 + 680, 0);
          *((_QWORD *)v15 + 86) = 0;
        }
        throw;
      }
    }
  }
  catch ( SmartClassPtr<CIMAPIException,CIMAPIException>v28 )
  {
    v21 = 0;
    v19 = v24;
    while ( 1 )
    {
      v20 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v19 + v21 + 79);
      if ( v20 )
        (**v20)(v20, 1);
      if ( ++v21 >= 3 )
      {
        if ( *((_QWORD *)v19 + 85) )
          v22 = **((_QWORD **)v19 + 85);
        else
          v22 = 0;
        if ( v22 )
        {
          SmartPtr<CFsiStashFile>::operator=((char *)v19 + 680, 0);
          *((_QWORD *)v19 + 86) = 0;
        }
        throw;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180041f24  mov     [rsp+arg_8], rbx
0x180041f29  mov     [rsp+arg_10], rsi
0x180041f2e  push    rdi
0x180041f2f  push    r12
0x180041f31  push    r13
0x180041f33  push    r14
0x180041f35  push    r15
0x180041f37  sub     rsp, 280h
0x180041f3e  mov     rax, cs:__security_cookie
0x180041f45  xor     rax, rsp
0x180041f48  mov     [rsp+2A8h+var_38], rax
0x180041f50  mov     [rsp+2A8h+var_268], rdx
0x180041f55  mov     rbx, rcx
0x180041f58  mov     [rsp+2A8h+var_270], rcx
0x180041f5d  xor     r15d, r15d
0x180041f60  mov     [rcx+8], r15d
0x180041f64  lea     rax, ??_7FileSystemImage@@6B@; const FileSystemImage::`vftable'
0x180041f6b  mov     [rcx], rax
0x180041f6e  lea     rdi, [rcx+28h]
0x180041f72  mov     [rdi], r15
0x180041f75  mov     [rdi+8], r15
0x180041f79  xor     r8d, r8d
0x180041f7c  xor     edx, edx
0x180041f7e  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@V?$SmartClassPtr@VImapiBlockRange@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiBlockRange@@VImapiImplementation@@@@@std@@@std@@@std@@QEAAPEAU?$_List_node@V?$SmartClassPtr@VImapiBlockRange@@VImapiImplementation@@@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<SmartClassPtr<ImapiBlockRange,ImapiImplementation>>>::_Buynode0(std::_List_node<SmartClassPtr<ImapiBlockRange,ImapiImplementation>,void *> *,std::_List_node<SmartClassPtr<ImapiBlockRange,ImapiImplementation>,void *> *)
0x180041f83  mov     [rdi], rax
0x180041f86  xor     edx, edx
0x180041f88  lea     rcx, [rbx+38h]
0x180041f8c  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x180041f91  nop
0x180041f92  lea     rcx, [rbx+48h]; void *
0x180041f96  lea     rax, ??1?$CComPtr@UIDiscFormat2Data@@@ATL@@QEAA@XZ; ATL::CComPtr<IDiscFormat2Data>::~CComPtr<IDiscFormat2Data>(void)
0x180041f9d  mov     [rsp+2A8h+var_288], rax; void (*)(void *)
0x180041fa2  lea     r9, ??0extent_ad@FSI_UDF@@QEAA@XZ; void (*)(void *)
0x180041fa9  lea     edx, [r15+8]; unsigned __int64
0x180041fad  lea     r8d, [r15+20h]; unsigned __int64
0x180041fb1  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180041fb6  nop
0x180041fb7  lea     rsi, [rbx+148h]
0x180041fbe  mov     rcx, rsi; void *
0x180041fc1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180041fc6  nop
0x180041fc7  lea     r14, [rbx+150h]
0x180041fce  mov     rcx, r14; void *
0x180041fd1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180041fd6  nop
0x180041fd7  mov     [rbx+160h], r15
0x180041fde  mov     [rbx+168h], r15d
0x180041fe5  lea     rcx, [rbx+248h]; void *
0x180041fec  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180041ff1  nop
0x180041ff2  lea     rcx, [rbx+2A8h]
0x180041ff9  call    ??0?$SmartPtr@V?$vector@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@std@@@std@@@@QEAA@PEAV?$vector@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@std@@@std@@@Z; SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>(std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>> *)
0x180041ffe  nop
0x180041fff  lea     rcx, [rbx+2C0h]
0x180042006  call    ??0?$SmartPtr@V?$vector@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@std@@@std@@@@QEAA@PEAV?$vector@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@std@@@std@@@Z; SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>(std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>> *)
0x18004200b  nop
0x18004200c  lea     rcx, [rbx+2C8h]
0x180042013  call    ??0?$SmartPtr@V?$vector@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@std@@@std@@@@QEAA@PEAV?$vector@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@std@@@std@@@Z; SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::SmartPtr<std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>(std::vector<SmartClassPtr<ImapiFileInfo,ImapiImplementation>> *)
0x180042018  nop
0x180042019  lea     r12, [rbx+2D8h]
0x180042020  mov     [r12], r15
0x180042024  mov     [r12+8], r15
0x180042029  mov     [r12+10h], r15
0x18004202e  mov     [r12+18h], r15
0x180042033  mov     qword ptr [r12+20h], 0Ah
0x18004203c  mov     [r12+28h], r15
0x180042041  lea     r15, [rbx+310h]
0x180042048  xor     edx, edx
0x18004204a  mov     rcx, r15
0x18004204d  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x180042052  nop
0x180042053  lea     rcx, [rbx+320h]; void *
0x18004205a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004205f  nop
0x180042060  xor     eax, eax
0x180042062  mov     [rbx+10h], ax
0x180042066  mov     [rbx+12h], al
0x180042069  mov     [rbx+14h], eax
0x18004206c  mov     dword ptr [rbx+18h], 7
0x180042073  mov     [rbx+1Ch], al
0x180042076  mov     dword ptr [rbx+20h], 102h
0x18004207d  mov     dword ptr [rbx+24h], 1
0x180042084  mov     rcx, rdi
0x180042087  call    ?clear@?$list@V?$SmartClassPtr@VImapiBlockRange@@VImapiImplementation@@@@V?$allocator@V?$SmartClassPtr@VImapiBlockRange@@VImapiImplementation@@@@@std@@@std@@QEAAXXZ; std::list<SmartClassPtr<ImapiBlockRange,ImapiImplementation>>::clear(void)
0x18004208c  mov     rcx, rsi
0x18004208f  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180042094  mov     rcx, r14
0x180042097  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18004209c  xor     edi, edi
0x18004209e  mov     [rbx+158h], dil
0x1800420a5  mov     qword ptr [rbx+170h], 1
0x1800420b0  mov     [rbx+178h], edi
0x1800420b6  mov     qword ptr [rbx+25Ch], 51400h
0x1800420c1  mov     [rbx+308h], rdi
0x1800420c8  xor     edx, edx
0x1800420ca  lea     rcx, [rsp+2A8h+var_278]
0x1800420cf  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x1800420d4  lea     rdx, [rsp+2A8h+var_278]
0x1800420d9  mov     rcx, r15
0x1800420dc  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x1800420e1  lea     rcx, [rsp+2A8h+var_278]; void *
0x1800420e6  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x1800420eb  mov     [rbx+318h], dil
0x1800420f2  mov     [rbx+17Ch], rdi
0x1800420f9  mov     [rbx+184h], edi
0x1800420ff  mov     word ptr [rbx+188h], 101h
0x180042108  mov     dword ptr [rbx+18Ch], 20h ; ' '
0x180042112  mov     dword ptr [rbx+32Ch], 0FFFFFFFFh
0x18004211c  mov     [rbx+328h], edi
0x180042122  mov     dword ptr [rbx+290h], 3
0x18004212c  mov     ecx, edi
0x18004212e  movsxd  rax, ecx
0x180042131  mov     [rbx+rax*4+250h], edi
0x180042138  mov     [rbx+rax*8+278h], rdi
0x180042140  inc     ecx
0x180042142  cmp     ecx, 3
0x180042145  jl      short loc_18004212E
0x180042147  mov     [rbx+40h], edi
0x18004214a  mov     ecx, 90h; unsigned __int64
0x18004214f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042154  mov     [rsp+2A8h+var_278], rax
0x180042159  test    rax, rax
0x18004215c  jz      short loc_18004216B
0x18004215e  mov     rdx, rbx; struct FileSystemImage *
0x180042161  mov     rcx, rax; this
0x180042164  call    ??0Iso9660FileSystemSupport@@QEAA@AEAVFileSystemImage@@@Z; Iso9660FileSystemSupport::Iso9660FileSystemSupport(FileSystemImage &)
0x180042169  jmp     short loc_18004216E
0x18004216b  mov     rax, rdi
0x18004216e  mov     [rbx+278h], rax
0x180042175  mov     ecx, 60h ; '`'; unsigned __int64
0x18004217a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004217f  mov     [rsp+2A8h+var_278], rax
0x180042184  test    rax, rax
0x180042187  jz      short loc_180042196
0x180042189  mov     rdx, rbx; struct FileSystemImage *
0x18004218c  mov     rcx, rax; this
0x18004218f  call    ??0JolietFileSystemSupport@@QEAA@AEAVFileSystemImage@@@Z; JolietFileSystemSupport::JolietFileSystemSupport(FileSystemImage &)
0x180042194  jmp     short loc_180042199
0x180042196  mov     rax, rdi
0x180042199  mov     [rbx+280h], rax
0x1800421a0  mov     ecx, 98h; unsigned __int64
0x1800421a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800421aa  mov     [rsp+2A8h+var_278], rax
0x1800421af  test    rax, rax
0x1800421b2  jz      short loc_1800421C1
0x1800421b4  mov     rdx, rbx; struct FileSystemImage *
0x1800421b7  mov     rcx, rax; this
0x1800421ba  call    ??0UdfFileSystemSupport@@QEAA@AEAVFileSystemImage@@@Z; UdfFileSystemSupport::UdfFileSystemSupport(FileSystemImage &)
0x1800421bf  jmp     short loc_1800421C4
0x1800421c1  mov     rax, rdi
0x1800421c4  mov     [rbx+288h], rax
0x1800421cb  mov     ecx, 318h; unsigned __int64
0x1800421d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800421d5  mov     [rsp+2A8h+var_278], rax
0x1800421da  test    rax, rax
0x1800421dd  jz      short loc_1800421EC
0x1800421df  mov     rdx, rbx; struct FileSystemImage *
0x1800421e2  mov     rcx, rax; this
0x1800421e5  call    ??0ImapiDirectoryInfo@@QEAA@AEAVFileSystemImage@@@Z; ImapiDirectoryInfo::ImapiDirectoryInfo(FileSystemImage &)
0x1800421ea  jmp     short loc_1800421EF
0x1800421ec  mov     rax, rdi
0x1800421ef  mov     rdx, rax
0x1800421f2  lea     rcx, [rsp+2A8h+var_278]
0x1800421f7  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x1800421fc  lea     rdx, [rsp+2A8h+var_278]
0x180042201  lea     rcx, [rbx+38h]
0x180042205  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x18004220a  lea     rcx, [rsp+2A8h+var_278]; void *
0x18004220f  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180042214  lea     rdx, [rsp+2A8h+var_258]
0x180042219  mov     ecx, 104h
0x18004221e  call    cs:__imp_GetTempPath2W
0x180042224  lea     rdx, [rsp+2A8h+var_258]
0x180042229  lea     rcx, [rbx+248h]
0x180042230  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180042235  lea     r9, aData; "data"
0x18004223c  lea     r8, aDat; "DAT"
0x180042243  lea     rdx, [rsp+2A8h+var_278]
0x180042248  mov     rcx, rbx
0x18004224b  call    ?CreateStashFile@FileSystemImage@@AEAA?AV?$SmartPtr@VCFsiStashFile@@@@PEBG0@Z; FileSystemImage::CreateStashFile(ushort const *,ushort const *)
0x180042250  mov     rdx, rax
0x180042253  lea     rcx, [rbx+2A8h]
0x18004225a  call    ??4?$SmartPtr@VCFsiStashFile@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CFsiStashFile>::operator=(SmartPtr<CFsiStashFile> const &)
0x18004225f  lea     rcx, [rsp+2A8h+var_278]
0x180042264  call    ??1?$SmartPtr@VCFsiStashFile@@@@QEAA@XZ; SmartPtr<CFsiStashFile>::~SmartPtr<CFsiStashFile>(void)
0x180042269  mov     [rbx+2A0h], dil
0x180042270  mov     [rbx+2B0h], rdi
0x180042277  mov     [rbx+2B8h], edi
0x18004227d  mov     [rbx+2D0h], edi
0x180042283  mov     rcx, r12
0x180042286  call    ?RemoveAll@?$CRBTree@_KV?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$CElementTraits@_K@ATL@@V?$CElementTraits@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@3@@ATL@@QEAAXXZ; ATL::CRBTree<unsigned __int64,SmartClassPtr<ImapiFileInfo,ImapiImplementation>,ATL::CElementTraits<unsigned __int64>,ATL::CElementTraits<SmartClassPtr<ImapiFileInfo,ImapiImplementation>>>::RemoveAll(void)
0x18004228b  lea     rcx, [rbx+190h]; void *
0x180042292  xor     edx, edx; Val
0x180042294  mov     r8d, 0B8h; Size
0x18004229a  call    memset_0
0x18004229f  mov     rax, [rsp+2A8h+var_268]
0x1800422a4  mov     [rbx+298h], rax
0x1800422ab  lea     rax, WPP_GLOBAL_Control
0x1800422b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800422b9  cmp     rcx, rax
0x1800422bc  jz      short loc_1800422E0
0x1800422be  test    byte ptr [rcx+44h], 4
0x1800422c2  jz      short loc_1800422E0
0x1800422c4  cmp     byte ptr [rcx+41h], 4
0x1800422c8  jb      short loc_1800422E0
0x1800422ca  mov     edx, 0Ah
0x1800422cf  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x1800422d6  mov     rcx, [rcx+38h]
0x1800422da  call    WPP_SF_
0x1800422df  nop
0x1800422e0  mov     rax, rbx
0x1800422e3  mov     rcx, [rsp+2A8h+var_38]
0x1800422eb  xor     rcx, rsp; StackCookie
0x1800422ee  call    __security_check_cookie
0x1800422f3  lea     r11, [rsp+2A8h+var_28]
0x1800422fb  mov     rbx, [r11+38h]
0x1800422ff  mov     rsi, [r11+40h]
0x180042303  mov     rsp, r11
0x180042306  pop     r15
0x180042308  pop     r14
0x18004230a  pop     r13
0x18004230c  pop     r12
0x18004230e  pop     rdi
0x18004230f  retn
```
