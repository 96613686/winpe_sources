# CFsiDirectoryItem::AddItemsFromSource(SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)

- ea: `0x180006900`
- end: `0x1800070fe`
- name: `?AddItemsFromSource@CFsiDirectoryItem@@AEAAXV?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z`
- size: `2046`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180005d7c`
- `0x180006900`

## callees

- `0x180002c80`
- `0x180003a20`
- `0x180004c70`
- `0x180005040`
- `0x1800051a0`
- `0x180005568`
- `0x180005ff0`
- `0x1800063b8`
- `0x180006900`
- `0x180007104`
- `0x180007198`
- `0x18000960c`
- `0x18000c888`
- `0x18000c8d0`
- `0x18000d1c0`
- `0x18000e6a0`
- `0x18000ea14`
- `0x18000fcb4`
- `0x180017090`
- `0x180018eec`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18008170e`
- `0x180081750`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x180006e7c`
- `KERNEL32!FindNextFileW` at `0x180006e7c`
- `KERNEL32!GetFileAttributesExW` at `0x180006a24`
- `KERNEL32!GetFileAttributesExW` at `0x180006a24`
- `KERNEL32!FindClose` at `0x180006e9b`
- `KERNEL32!FindClose` at `0x180006e9b`
- `KERNEL32!FindFirstFileW` at `0x180006c0a`
- `KERNEL32!FindFirstFileW` at `0x180006c0a`
- `KERNEL32!GetLastError` at `0x180006a47`
- `KERNEL32!GetLastError` at `0x180006c39`
- `KERNEL32!GetLastError` at `0x180006e90`
- `KERNEL32!GetLastError` at `0x180006ec8`
- `KERNEL32!GetLastError` at `0x180006a47`
- `KERNEL32!GetLastError` at `0x180006c39`
- `KERNEL32!GetLastError` at `0x180006e90`
- `KERNEL32!GetLastError` at `0x180006ec8`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall CFsiDirectoryItem::AddItemsFromSource(CIMAPIException **a1, __int64 *a2, char **a3, unsigned int a4)
{
  unsigned int v4; // r13d
  CIMAPIException **v7; // rsi
  bool v8; // r15
  unsigned __int16 **v9; // rax
  int v10; // ebx
  _BYTE *v11; // rdx
  __int64 v12; // r8
  _QWORD *v13; // rcx
  int *v14; // rsi
  __int64 v15; // rbx
  CIMAPISystemException *v16; // rbx
  DWORD LastError; // eax
  CIMAPISystemException *v18; // rax
  LPCWSTR v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  _DWORD *FirstFileW; // r15
  CIMAPISystemException *v26; // rsi
  signed int v27; // eax
  CIMAPISystemException *v28; // rax
  CIMAPIException *v29; // rax
  __int64 v30; // rax
  CIMAPIException **v31; // rbx
  int v32; // ecx
  int v33; // ecx
  __int64 v34; // rax
  _BYTE *v35; // rdx
  __int64 v36; // r8
  _QWORD *v37; // rcx
  int *v38; // rsi
  __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rcx
  signed int v42; // esi
  CIMAPISystemException *v43; // rax
  CIMAPISystemException *v44; // rax
  char **v45; // rbx
  CIMAPISystemException *v46; // rax
  CIMAPISystemException *v47; // rax
  CIMAPIException *v48; // rax
  __int64 v49; // rax
  CIMAPIException **v50; // rbx
  char *v51; // [rsp+30h] [rbp-4A8h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-4A0h] BYREF
  char **v53; // [rsp+40h] [rbp-498h] BYREF
  CIMAPIException **v54; // [rsp+48h] [rbp-490h] BYREF
  CIMAPIException **v55; // [rsp+50h] [rbp-488h] BYREF
  _DWORD *v56; // [rsp+58h] [rbp-480h] BYREF
  _DWORD *v57; // [rsp+60h] [rbp-478h] BYREF
  __int64 v58; // [rsp+68h] [rbp-470h] BYREF
  CIMAPISystemException *v59; // [rsp+70h] [rbp-468h]
  LPCWSTR pExceptionObject; // [rsp+78h] [rbp-460h] BYREF
  CIMAPIException **v61; // [rsp+80h] [rbp-458h] BYREF
  char v62[8]; // [rsp+88h] [rbp-450h] BYREF
  char **v63; // [rsp+90h] [rbp-448h] BYREF
  _QWORD v64[3]; // [rsp+98h] [rbp-440h] BYREF
  _BYTE v65[88]; // [rsp+B0h] [rbp-428h] BYREF
  _BYTE v66[88]; // [rsp+108h] [rbp-3D0h] BYREF
  _BYTE v67[88]; // [rsp+160h] [rbp-378h] BYREF
  _BYTE v68[88]; // [rsp+1B8h] [rbp-320h] BYREF
  _OWORD FileInformation[2]; // [rsp+210h] [rbp-2C8h] BYREF
  int v70; // [rsp+230h] [rbp-2A8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+240h] [rbp-298h] BYREF

  v4 = a4;
  v7 = a1;
  v54 = a1;
  v64[1] = a2;
  v64[2] = a3;
  memset(FileInformation, 0, sizeof(FileInformation));
  v70 = 0;
  v8 = (a4 & 4) == 0;
  v9 = (unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                              a3,
                              &lpFileName,
                              1);
  v10 = **v9 - 92;
  if ( **v9 == 92 )
    v10 = (*v9)[1];
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
  if ( !v10 )
  {
    v11 = *(_BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                       a3,
                       &lpFileName,
                       (unsigned int)(*((_DWORD *)*a3 - 4) - 1));
    v13 = v11 - 24;
    v14 = (int *)(*a3 - 24);
    if ( v11 - 24 != (_BYTE *)v14 )
    {
      if ( v14[4] >= 0 && *v13 == *(_QWORD *)v14 )
      {
        v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13, v11, v12);
        ATL::CStringData::Release((ATL::CStringData *)v14);
        *a3 = (char *)(v15 + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v11, *((_DWORD *)v11 - 4));
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
    v7 = v54;
  }
  if ( !GetFileAttributesExW((LPCWSTR)*a3, GetFileExInfoStandard, FileInformation) )
  {
    v16 = (CIMAPISystemException *)operator new(0x58u);
    v53 = (char **)v16;
    if ( v16 )
    {
      LastError = GetLastError();
      v18 = CIMAPISystemException::CIMAPISystemException(v16, LastError);
    }
    else
    {
      v18 = 0;
    }
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&lpFileName, v18);
    v19 = lpFileName;
    if ( lpFileName && *(_QWORD *)lpFileName )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)lpFileName,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp",
        622);
      pExceptionObject = v19;
      if ( v19 )
        ++*((_DWORD *)v19 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v65, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v65;
  }
  if ( (FileInformation[0] & 0x10) != 0 )
  {
    LODWORD(v57) = v4 & 1;
    if ( (v4 & 2) != 0 )
    {
      v4 &= ~2u;
    }
    else
    {
      --*(_DWORD *)(*(_QWORD *)(*(_QWORD *)*a2 + 64LL) + 20LL);
      v53 = &v51;
      v22 = *a2;
      v51 = (char *)v22;
      if ( v22 )
        ++*(_DWORD *)(v22 + 8);
      v23 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v56,
              a3);
      v24 = CFsiDirectoryItem::AddDirFromSource(v7, &v58, v23, FileInformation, &v51, v8);
      SmartPtr<ImportMetadata>::operator=(a2, v24);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v58);
    }
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    ATL::operator+(&lpFileName, a3, L"\\*");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v51);
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    v56 = FirstFileW;
    if ( FirstFileW == (_DWORD *)-1LL )
    {
      v26 = (CIMAPISystemException *)operator new(0x58u);
      v53 = (char **)v26;
      if ( v26 )
      {
        v27 = GetLastError();
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0x80070000;
        v28 = CIMAPISystemException::CIMAPISystemException(v26, v27);
      }
      else
      {
        v28 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v56, v28);
      v29 = (CIMAPIException *)operator new(0x58u);
      v53 = (char **)v29;
      if ( v29 )
      {
        v57 = v56;
        if ( v56 )
          ++v56[2];
        v30 = CIMAPIException::CIMAPIException(v29, &v57);
      }
      else
      {
        v30 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v54, v30);
      v31 = v54;
      if ( v54 && *v54 )
      {
        CIMAPIException::SetCodeRefInfo(*v54, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 658);
        v61 = v31;
        if ( v31 )
          ++*((_DWORD *)v31 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v61;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v66,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v66;
    }
    while ( FirstFileW )
    {
      v32 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v32 = FindFileData.cFileName[1];
      if ( v32 )
      {
        v33 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v33 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v33 = FindFileData.cFileName[2];
        }
        if ( v33 )
        {
          v34 = ATL::operator+(&v55, a3, L"\\");
          v35 = *(_BYTE **)ATL::operator+(v62, v34, FindFileData.cFileName);
          v37 = v35 - 24;
          v38 = (int *)(v51 - 24);
          if ( v35 - 24 != v51 - 24 )
          {
            if ( v38[4] >= 0 && *v37 == *(_QWORD *)v38 )
            {
              v39 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v37, v35, v36);
              ATL::CStringData::Release((ATL::CStringData *)v38);
              v51 = (char *)(v39 + 24);
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v51, v35, *((_DWORD *)v35 - 4));
            }
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v62);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v55);
          if ( (_BYTE)v57 || (FileInformation[0] & 0x10) == 0 )
          {
            try
            {
              v40 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                      &v53,
                      &v51);
              v41 = *a2;
              v58 = v41;
              if ( v41 )
                ++*(_DWORD *)(v41 + 8);
              CFsiDirectoryItem::AddItemsFromSource(v54, &v58, v40, v4);
            }
            catch ( ... )
            {
              FindClose(v56);
              throw;
            }
          }
        }
      }
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        v42 = GetLastError();
        if ( !FindClose(FirstFileW) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids);
          }
          v43 = (CIMAPISystemException *)operator new(0x58u);
          v59 = v43;
          if ( v43 )
            v44 = CIMAPISystemException::CIMAPISystemException(v43, -1062555392);
          else
            v44 = 0;
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v44);
          v45 = v53;
          if ( v53 && *v53 )
          {
            CIMAPIException::SetCodeRefInfo(
              (CIMAPIException *)*v53,
              "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp",
              691);
            v63 = v45;
            if ( v45 )
              ++*((_DWORD *)v45 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v63;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v67,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v67;
        }
        if ( v42 != 18 )
        {
          v46 = (CIMAPISystemException *)operator new(0x58u);
          v59 = v46;
          if ( v46 )
          {
            if ( v42 > 0 )
              v42 = (unsigned __int16)v42 | 0x80070000;
            v47 = CIMAPISystemException::CIMAPISystemException(v46, v42);
          }
          else
          {
            v47 = 0;
          }
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v53, v47);
          v48 = (CIMAPIException *)operator new(0x58u);
          v59 = v48;
          if ( v48 )
          {
            v54 = (CIMAPIException **)v53;
            if ( v53 )
              ++*((_DWORD *)v53 + 2);
            v49 = CIMAPIException::CIMAPIException(v48, &v54);
          }
          else
          {
            v49 = 0;
          }
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v55, v49);
          v50 = v55;
          if ( v55 && *v55 )
          {
            CIMAPIException::SetCodeRefInfo(*v55, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 698);
            v64[0] = v50;
            if ( v50 )
              ++*((_DWORD *)v50 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v64;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v68,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v68;
        }
        FirstFileW = 0;
        v56 = 0;
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v51);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
  }
  else
  {
    --*(_DWORD *)(*(_QWORD *)(*(_QWORD *)*a2 + 64LL) + 20LL);
    v53 = &v51;
    v20 = *a2;
    v51 = (char *)v20;
    if ( v20 )
      ++*(_DWORD *)(v20 + 8);
    v21 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &lpFileName,
            a3);
    CFsiDirectoryItem::AddFileFromSource(v7, v21, FileInformation, &v51, v8, v4, v51);
  }
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a3);
}

```

## disassembly

```asm
0x180006900  push    rbx
0x180006902  push    rsi
0x180006903  push    rdi
0x180006904  push    r12
0x180006906  push    r13
0x180006908  push    r14
0x18000690a  push    r15
0x18000690c  sub     rsp, 4A0h
0x180006913  mov     rax, cs:__security_cookie
0x18000691a  xor     rax, rsp
0x18000691d  mov     [rsp+4D8h+var_48], rax
0x180006925  mov     r13d, r9d
0x180006928  mov     r14, r8
0x18000692b  mov     r12, rdx
0x18000692e  mov     rsi, rcx
0x180006931  mov     [rsp+4D8h+var_490], rcx
0x180006936  mov     [rsp+4D8h+var_438], rdx
0x18000693e  mov     [rsp+4D8h+var_430], r8
0x180006946  xorps   xmm0, xmm0
0x180006949  xor     eax, eax
0x18000694b  movups  [rsp+4D8h+FileInformation], xmm0
0x180006953  movups  [rsp+4D8h+var_2B8], xmm0
0x18000695b  mov     [rsp+4D8h+var_2A8], eax
0x180006962  mov     r15d, r9d
0x180006965  shr     r15d, 2
0x180006969  not     r15b
0x18000696c  and     r15b, 1
0x180006970  lea     r8d, [rax+1]
0x180006974  lea     rdx, [rsp+4D8h+lpFileName]
0x180006979  mov     rcx, r14
0x18000697c  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x180006981  nop
0x180006982  mov     rcx, [rax]
0x180006985  movzx   ebx, word ptr [rcx]
0x180006988  sub     ebx, 5Ch ; '\'
0x18000698b  jnz     short loc_18000699A
0x18000698d  movzx   ebx, word ptr [rcx+2]
0x180006991  xor     edi, edi
0x180006993  movzx   eax, di
0x180006996  sub     ebx, eax
0x180006998  jmp     short loc_18000699C
0x18000699a  xor     edi, edi
0x18000699c  lea     rcx, [rsp+4D8h+lpFileName]; void *
0x1800069a1  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800069a6  test    ebx, ebx
0x1800069a8  jnz     short loc_180006A17
0x1800069aa  mov     rax, [r14]
0x1800069ad  mov     r8d, [rax-10h]
0x1800069b1  dec     r8d
0x1800069b4  lea     rdx, [rsp+4D8h+lpFileName]
0x1800069b9  mov     rcx, r14
0x1800069bc  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x1800069c1  nop
0x1800069c2  mov     rdx, [rax]
0x1800069c5  lea     rcx, [rdx-18h]
0x1800069c9  mov     rsi, [r14]
0x1800069cc  add     rsi, 0FFFFFFFFFFFFFFE8h
0x1800069d0  cmp     rcx, rsi
0x1800069d3  jz      short loc_180006A08
0x1800069d5  cmp     [rsi+10h], edi
0x1800069d8  jl      short loc_1800069FB
0x1800069da  mov     rax, [rsi]
0x1800069dd  cmp     [rcx], rax
0x1800069e0  jnz     short loc_1800069FB
0x1800069e2  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800069e7  mov     rbx, rax
0x1800069ea  mov     rcx, rsi; this
0x1800069ed  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800069f2  lea     rax, [rbx+18h]
0x1800069f6  mov     [r14], rax
0x1800069f9  jmp     short loc_180006A08
0x1800069fb  mov     r8d, [rdx-10h]
0x1800069ff  mov     rcx, r14
0x180006a02  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006a07  nop
0x180006a08  lea     rcx, [rsp+4D8h+lpFileName]; void *
0x180006a0d  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006a12  mov     rsi, [rsp+4D8h+var_490]
0x180006a17  lea     r8, [rsp+4D8h+FileInformation]; lpFileInformation
0x180006a1f  xor     edx, edx; fInfoLevelId
0x180006a21  mov     rcx, [r14]; lpFileName
0x180006a24  call    cs:__imp_GetFileAttributesExW
0x180006a2a  test    eax, eax
0x180006a2c  jnz     loc_180006AD6
0x180006a32  lea     ecx, [rax+58h]; unsigned __int64
0x180006a35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a3a  mov     rbx, rax
0x180006a3d  mov     [rsp+4D8h+var_498], rax
0x180006a42  test    rax, rax
0x180006a45  jz      short loc_180006A59
0x180006a47  call    cs:__imp_GetLastError
0x180006a4d  mov     edx, eax; int
0x180006a4f  mov     rcx, rbx; this
0x180006a52  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180006a57  jmp     short loc_180006A5C
0x180006a59  mov     rax, rdi
0x180006a5c  mov     rdx, rax
0x180006a5f  lea     rcx, [rsp+4D8h+lpFileName]
0x180006a64  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180006a69  nop
0x180006a6a  mov     rbx, [rsp+4D8h+lpFileName]
0x180006a6f  test    rbx, rbx
0x180006a72  jz      short loc_180006AAD
0x180006a74  cmp     [rbx], rdi
0x180006a77  jz      short loc_180006AAD
0x180006a79  mov     r8d, 26Eh; int
0x180006a7f  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180006a86  mov     rcx, [rbx]; this
0x180006a89  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180006a8e  mov     [rsp+4D8h+pExceptionObject], rbx
0x180006a93  test    rbx, rbx
0x180006a96  jz      short loc_180006A9B
0x180006a98  inc     dword ptr [rbx+8]
0x180006a9b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180006aa2  lea     rcx, [rsp+4D8h+pExceptionObject]; pExceptionObject
0x180006aa7  call    _CxxThrowException_0
0x180006aad  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180006ab4  lea     rcx, [rsp+4D8h+var_428]; this
0x180006abc  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180006ac1  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180006ac8  lea     rcx, [rsp+4D8h+var_428]; pExceptionObject
0x180006ad0  call    _CxxThrowException_0
0x180006ad6  mov     eax, dword ptr [rsp+4D8h+FileInformation]
0x180006add  test    al, 10h
0x180006adf  jnz     short loc_180006B3F
0x180006ae1  mov     rax, [r12]
0x180006ae5  mov     rcx, [rax]
0x180006ae8  mov     rax, [rcx+40h]
0x180006aec  dec     dword ptr [rax+14h]
0x180006aef  lea     rax, [rsp+4D8h+var_4A8]
0x180006af4  mov     [rsp+4D8h+var_498], rax
0x180006af9  mov     rax, [r12]
0x180006afd  mov     [rsp+4D8h+var_4A8], rax
0x180006b02  test    rax, rax
0x180006b05  jz      short loc_180006B0A
0x180006b07  inc     dword ptr [rax+8]
0x180006b0a  mov     rdx, r14
0x180006b0d  lea     rcx, [rsp+4D8h+lpFileName]
0x180006b12  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180006b17  nop
0x180006b18  mov     [rsp+4D8h+var_4B0], r13d
0x180006b1d  mov     byte ptr [rsp+4D8h+var_4B8], r15b
0x180006b22  lea     r9, [rsp+4D8h+var_4A8]
0x180006b27  lea     r8, [rsp+4D8h+FileInformation]
0x180006b2f  mov     rdx, rax
0x180006b32  mov     rcx, rsi
0x180006b35  call    ?AddFileFromSource@CFsiDirectoryItem@@AEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAU_WIN32_FILE_ATTRIBUTE_DATA@@V?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@_NH@Z; CFsiDirectoryItem::AddFileFromSource(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_WIN32_FILE_ATTRIBUTE_DATA &,SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>,bool,int)
0x180006b3a  jmp     loc_1800070CA
0x180006b3f  mov     eax, r13d
0x180006b42  and     eax, 1
0x180006b45  mov     dword ptr [rsp+4D8h+var_478], eax
0x180006b49  test    r13b, 2
0x180006b4d  jz      short loc_180006B55
0x180006b4f  and     r13d, 0FFFFFFFDh
0x180006b53  jmp     short loc_180006BC8
0x180006b55  mov     rax, [r12]
0x180006b59  mov     rcx, [rax]
0x180006b5c  mov     rax, [rcx+40h]
0x180006b60  dec     dword ptr [rax+14h]
0x180006b63  lea     rax, [rsp+4D8h+var_4A8]
0x180006b68  mov     [rsp+4D8h+var_498], rax
0x180006b6d  mov     rax, [r12]
0x180006b71  mov     [rsp+4D8h+var_4A8], rax
0x180006b76  test    rax, rax
0x180006b79  jz      short loc_180006B7E
0x180006b7b  inc     dword ptr [rax+8]
0x180006b7e  mov     rdx, r14
0x180006b81  lea     rcx, [rsp+4D8h+var_480]
0x180006b86  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180006b8b  nop
0x180006b8c  mov     byte ptr [rsp+4D8h+var_4B0], r15b
0x180006b91  lea     rcx, [rsp+4D8h+var_4A8]
0x180006b96  mov     [rsp+4D8h+var_4B8], rcx
0x180006b9b  lea     r9, [rsp+4D8h+FileInformation]
0x180006ba3  mov     r8, rax
0x180006ba6  lea     rdx, [rsp+4D8h+var_470]
0x180006bab  mov     rcx, rsi
0x180006bae  call    ?AddDirFromSource@CFsiDirectoryItem@@AEAA?AV?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAU_WIN32_FILE_ATTRIBUTE_DATA@@V2@_N@Z; CFsiDirectoryItem::AddDirFromSource(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_WIN32_FILE_ATTRIBUTE_DATA &,SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>,bool)
0x180006bb3  mov     rdx, rax
0x180006bb6  mov     rcx, r12
0x180006bb9  call    ??4?$SmartPtr@VImportMetadata@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<ImportMetadata>::operator=(SmartPtr<ImportMetadata> const &)
0x180006bbe  lea     rcx, [rsp+4D8h+var_470]; void *
0x180006bc3  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180006bc8  xor     edx, edx; Val
0x180006bca  mov     r8d, 250h; Size
0x180006bd0  lea     rcx, [rsp+4D8h+FindFileData]; void *
0x180006bd8  call    memset_0
0x180006bdd  lea     r8, asc_180098120; "\\*"
0x180006be4  mov     rdx, r14
0x180006be7  lea     rcx, [rsp+4D8h+lpFileName]
0x180006bec  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180006bf1  nop
0x180006bf2  lea     rcx, [rsp+4D8h+var_4A8]; void *
0x180006bf7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006bfc  nop
0x180006bfd  lea     rdx, [rsp+4D8h+FindFileData]; lpFindFileData
0x180006c05  mov     rcx, [rsp+4D8h+lpFileName]; lpFileName
0x180006c0a  call    cs:__imp_FindFirstFileW
0x180006c10  mov     r15, rax
0x180006c13  mov     [rsp+4D8h+var_480], rax
0x180006c18  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006c1c  jnz     loc_180006D27
0x180006c22  lea     ebx, [rax+59h]
0x180006c25  mov     ecx, ebx; unsigned __int64
0x180006c27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c2c  mov     rsi, rax
0x180006c2f  mov     [rsp+4D8h+var_498], rax
0x180006c34  test    rax, rax
0x180006c37  jz      short loc_180006C57
0x180006c39  call    cs:__imp_GetLastError
0x180006c3f  test    eax, eax
0x180006c41  jle     short loc_180006C4B
0x180006c43  movzx   eax, ax
0x180006c46  or      eax, 80070000h
0x180006c4b  mov     edx, eax; int
0x180006c4d  mov     rcx, rsi; this
0x180006c50  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180006c55  jmp     short loc_180006C5A
0x180006c57  mov     rax, rdi
0x180006c5a  mov     rdx, rax
0x180006c5d  lea     rcx, [rsp+4D8h+var_480]
0x180006c62  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180006c67  nop
0x180006c68  mov     rcx, rbx; unsigned __int64
0x180006c6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c70  mov     [rsp+4D8h+var_498], rax
0x180006c75  test    rax, rax
0x180006c78  jz      short loc_180006CA4
0x180006c7a  mov     r9, [r14]
0x180006c7d  mov     rcx, [rsp+4D8h+var_480]
0x180006c82  mov     [rsp+4D8h+var_478], rcx
0x180006c87  test    rcx, rcx
0x180006c8a  jz      short loc_180006C8F
0x180006c8c  inc     dword ptr [rcx+8]
0x180006c8f  mov     r8d, 0C0AAB12Bh
0x180006c95  lea     rdx, [rsp+4D8h+var_478]; void *
0x180006c9a  mov     rcx, rax; this
0x180006c9d  call    ??0CIMAPIException@@QEAA@V?$SmartClassPtr@VCIMAPIException@@V1@@@JZZ; CIMAPIException::CIMAPIException(SmartClassPtr<CIMAPIException,CIMAPIException>,long,...)
0x180006ca2  jmp     short loc_180006CA7
0x180006ca4  mov     rax, rdi
0x180006ca7  mov     rdx, rax
0x180006caa  lea     rcx, [rsp+4D8h+var_490]
0x180006caf  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180006cb4  nop
0x180006cb5  mov     rbx, [rsp+4D8h+var_490]
0x180006cba  test    rbx, rbx
0x180006cbd  jz      short loc_180006CFE
0x180006cbf  cmp     [rbx], rdi
0x180006cc2  jz      short loc_180006CFE
0x180006cc4  mov     r8d, 292h; int
0x180006cca  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180006cd1  mov     rcx, [rbx]; this
0x180006cd4  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180006cd9  mov     [rsp+4D8h+var_458], rbx
0x180006ce1  test    rbx, rbx
0x180006ce4  jz      short loc_180006CE9
0x180006ce6  inc     dword ptr [rbx+8]
0x180006ce9  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180006cf0  lea     rcx, [rsp+4D8h+var_458]; pExceptionObject
0x180006cf8  call    _CxxThrowException_0
0x180006cfe  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180006d05  lea     rcx, [rsp+4D8h+var_3D0]; this
0x180006d0d  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180006d12  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180006d19  lea     rcx, [rsp+4D8h+var_3D0]; pExceptionObject
0x180006d21  call    _CxxThrowException_0
0x180006d27  mov     r8d, 2Eh ; '.'
0x180006d2d  test    r15, r15
0x180006d30  jz      loc_1800070B4
0x180006d36  movzx   ecx, [rsp+4D8h+FindFileData.cFileName]
0x180006d3e  movzx   eax, r8w
0x180006d42  sub     ecx, eax
0x180006d44  jnz     short loc_180006D57
0x180006d46  movzx   edx, [rsp+4D8h+FindFileData.cFileName+2]
0x180006d4e  mov     ecx, edx
0x180006d50  movzx   eax, di
0x180006d53  sub     ecx, eax
0x180006d55  jmp     short loc_180006D5F
0x180006d57  movzx   edx, [rsp+4D8h+FindFileData.cFileName+2]
0x180006d5f  test    ecx, ecx
0x180006d61  jz      loc_180006E71
0x180006d67  movzx   ecx, [rsp+4D8h+FindFileData.cFileName]
0x180006d6f  movzx   eax, r8w
0x180006d73  sub     ecx, eax
0x180006d75  jnz     short loc_180006D8F
0x180006d77  movzx   ecx, dx
0x180006d7a  movzx   eax, r8w
0x180006d7e  sub     ecx, eax
0x180006d80  jnz     short loc_180006D8F
0x180006d82  movzx   ecx, [rsp+4D8h+FindFileData.cFileName+4]
0x180006d8a  movzx   eax, di
0x180006d8d  sub     ecx, eax
0x180006d8f  test    ecx, ecx
0x180006d91  jz      loc_180006E71
0x180006d97  lea     r8, asc_180094194; "\\"
0x180006d9e  mov     rdx, r14
0x180006da1  lea     rcx, [rsp+4D8h+var_488]
0x180006da6  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180006dab  nop
0x180006dac  lea     r8, [rsp+4D8h+FindFileData.cFileName]
  ... truncated ...
```
