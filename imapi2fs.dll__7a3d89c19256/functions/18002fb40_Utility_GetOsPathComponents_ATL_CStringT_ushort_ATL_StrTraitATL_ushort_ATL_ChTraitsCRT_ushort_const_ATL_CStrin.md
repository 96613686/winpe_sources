# Utility::GetOsPathComponents(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18002fb40`
- end: `0x18002fe2c`
- name: `?GetOsPathComponents@Utility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@1@Z`
- size: `748`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180005ff0`
- `0x18000b730`
- `0x18000e6a0`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180005438`
- `0x1800055c0`
- `0x180007104`
- `0x180007198`
- `0x18000960c`
- `0x18000d1c0`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x18002dba4`
- `0x18002dc70`
- `0x18002fb40`
- `0x180030bec`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18002fbbd`
- `KERNEL32!GetFullPathNameW` at `0x18002fcce`
- `KERNEL32!GetFullPathNameW` at `0x18002fbbd`
- `KERNEL32!GetFullPathNameW` at `0x18002fcce`
- `KERNEL32!GetLastError` at `0x18002fbcd`
- `KERNEL32!GetLastError` at `0x18002fcdc`
- `KERNEL32!GetLastError` at `0x18002fbcd`
- `KERNEL32!GetLastError` at `0x18002fcdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Utility::GetOsPathComponents(__int64 *a1, __int64 a2, __int64 a3)
{
  DWORD FullPathNameW; // eax
  DWORD v7; // esi
  DWORD LastError; // ebx
  int v9; // r8d
  CIMAPISystemException *v10; // rax
  CIMAPIException **v11; // rbx
  void *v12; // rax
  CIMAPIException *v13; // rbx
  DWORD v14; // ebx
  int v15; // r8d
  CIMAPISystemException *v16; // rax
  CIMAPIException **v17; // rbx
  CIMAPIException **v18; // [rsp+30h] [rbp-49h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-41h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+40h] [rbp-39h] BYREF
  CIMAPISystemException *v21; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v22[96]; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpFileName; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_4a1263e1fdae307c29234b23c923e679_Traceguids);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpFileName,
    a1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&lpFileName);
  FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
  v7 = FullPathNameW;
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 7), v7 + 15, v9, LastError, *a1);
    }
    v10 = (CIMAPISystemException *)operator new(0x58u);
    v21 = v10;
    if ( v10 )
      v10 = CIMAPISystemException::CIMAPISystemException(v10, LastError);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v18, v10);
    v11 = v18;
    if ( v18 && *v18 )
    {
      CIMAPIException::SetCodeRefInfo(*v18, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiutil.cpp", 174);
      pExceptionObject = v11;
      if ( v11 )
        ++*((_DWORD *)v11 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v22, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v22;
  }
  v12 = operator new(2LL * (FullPathNameW + 1));
  SmartArrayPtr<unsigned char>::SmartArrayPtr<unsigned char>(&v18, v12);
  if ( v18 )
    v13 = *v18;
  else
    v13 = 0;
  FilePart = 0;
  if ( !GetFullPathNameW(lpFileName, v7, (LPWSTR)v13, &FilePart) )
  {
    v14 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, v15, v14, *a1);
    }
    v16 = (CIMAPISystemException *)operator new(0x58u);
    v21 = v16;
    if ( v16 )
      v16 = CIMAPISystemException::CIMAPISystemException(v16, v14);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, v16);
    v17 = pExceptionObject;
    if ( pExceptionObject && *pExceptionObject )
    {
      CIMAPIException::SetCodeRefInfo(
        *pExceptionObject,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiutil.cpp",
        190);
      v21 = (CIMAPISystemException *)v17;
      if ( v17 )
        ++*((_DWORD *)v17 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v21;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v22, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v22;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a3, FilePart);
  if ( FilePart )
    *((_WORD *)v13 + (((char *)FilePart - (char *)v13) >> 1) - 1) = 0;
  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v13);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_4a1263e1fdae307c29234b23c923e679_Traceguids);
  }
  SmartArrayPtr<unsigned char>::~SmartArrayPtr<unsigned char>(&v18);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
}

```

## disassembly

```asm
0x18002fb40  mov     [rsp-8+arg_0], rbx
0x18002fb45  mov     [rsp-8+arg_8], rsi
0x18002fb4a  push    rbp
0x18002fb4b  push    rdi
0x18002fb4c  push    r13
0x18002fb4e  push    r14
0x18002fb50  push    r15
0x18002fb52  lea     rbp, [rsp-37h]
0x18002fb57  sub     rsp, 0B0h
0x18002fb5e  mov     r14, r8
0x18002fb61  mov     r15, rdx
0x18002fb64  mov     rdi, rcx
0x18002fb67  lea     r13, WPP_GLOBAL_Control
0x18002fb6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb75  cmp     rcx, r13
0x18002fb78  jz      short loc_18002FB9B
0x18002fb7a  test    byte ptr [rcx+44h], 8
0x18002fb7e  jz      short loc_18002FB9B
0x18002fb80  cmp     byte ptr [rcx+41h], 5
0x18002fb84  jb      short loc_18002FB9B
0x18002fb86  mov     edx, 0Eh
0x18002fb8b  lea     r8, WPP_4a1263e1fdae307c29234b23c923e679_Traceguids
0x18002fb92  mov     rcx, [rcx+38h]
0x18002fb96  call    WPP_SF_
0x18002fb9b  mov     rdx, rdi
0x18002fb9e  lea     rcx, [rbp+57h+lpFileName]
0x18002fba2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002fba7  nop
0x18002fba8  lea     rcx, [rbp+57h+lpFileName]
0x18002fbac  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@G@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(ushort)
0x18002fbb1  xor     r9d, r9d; lpFilePart
0x18002fbb4  xor     r8d, r8d; lpBuffer
0x18002fbb7  xor     edx, edx; nBufferLength
0x18002fbb9  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18002fbbd  call    cs:__imp_GetFullPathNameW
0x18002fbc3  mov     esi, eax
0x18002fbc5  test    eax, eax
0x18002fbc7  jnz     loc_18002FC91
0x18002fbcd  call    cs:__imp_GetLastError
0x18002fbd3  mov     ebx, eax
0x18002fbd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbdc  cmp     rcx, r13
0x18002fbdf  jz      short loc_18002FC04
0x18002fbe1  test    byte ptr [rcx+44h], 4
0x18002fbe5  jz      short loc_18002FC04
0x18002fbe7  cmp     byte ptr [rcx+41h], 2
0x18002fbeb  jb      short loc_18002FC04
0x18002fbed  lea     edx, [rsi+0Fh]
0x18002fbf0  mov     rax, [rdi]
0x18002fbf3  mov     [rsp+0D0h+var_B0], rax
0x18002fbf8  mov     r9d, ebx
0x18002fbfb  mov     rcx, [rcx+38h]
0x18002fbff  call    WPP_SF_DS
0x18002fc04  mov     ecx, 58h ; 'X'; unsigned __int64
0x18002fc09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fc0e  mov     [rbp+57h+var_88], rax
0x18002fc12  test    rax, rax
0x18002fc15  jz      short loc_18002FC22
0x18002fc17  mov     edx, ebx; int
0x18002fc19  mov     rcx, rax; this
0x18002fc1c  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18002fc21  nop
0x18002fc22  mov     rdx, rax
0x18002fc25  lea     rcx, [rbp+57h+var_A0]
0x18002fc29  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18002fc2e  nop
0x18002fc2f  mov     rbx, [rbp+57h+var_A0]
0x18002fc33  test    rbx, rbx
0x18002fc36  jz      short loc_18002FC70
0x18002fc38  cmp     qword ptr [rbx], 0
0x18002fc3c  jz      short loc_18002FC70
0x18002fc3e  mov     r8d, 0AEh; int
0x18002fc44  lea     rdx, aDriversStorage_2; "drivers\\storage\\imapi2\\filesystemima"...
0x18002fc4b  mov     rcx, [rbx]; this
0x18002fc4e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18002fc53  mov     [rbp+57h+pExceptionObject], rbx
0x18002fc57  test    rbx, rbx
0x18002fc5a  jz      short loc_18002FC5F
0x18002fc5c  inc     dword ptr [rbx+8]
0x18002fc5f  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18002fc66  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002fc6a  call    _CxxThrowException_0
0x18002fc70  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18002fc77  lea     rcx, [rbp+57h+var_80]; this
0x18002fc7b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18002fc80  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18002fc87  lea     rcx, [rbp+57h+var_80]; pExceptionObject
0x18002fc8b  call    _CxxThrowException_0
0x18002fc91  lea     ecx, [rax+1]
0x18002fc94  add     rcx, rcx; unsigned __int64
0x18002fc97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fc9c  mov     rdx, rax
0x18002fc9f  lea     rcx, [rbp+57h+var_A0]
0x18002fca3  call    ??0?$SmartArrayPtr@E@@QEAA@PEAE@Z; SmartArrayPtr<uchar>::SmartArrayPtr<uchar>(uchar *)
0x18002fca8  nop
0x18002fca9  mov     rax, [rbp+57h+var_A0]
0x18002fcad  test    rax, rax
0x18002fcb0  jz      short loc_18002FCB7
0x18002fcb2  mov     rbx, [rax]
0x18002fcb5  jmp     short loc_18002FCB9
0x18002fcb7  xor     ebx, ebx
0x18002fcb9  mov     [rbp+57h+FilePart], 0
0x18002fcc1  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x18002fcc5  mov     r8, rbx; lpBuffer
0x18002fcc8  mov     edx, esi; nBufferLength
0x18002fcca  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18002fcce  call    cs:__imp_GetFullPathNameW
0x18002fcd4  test    eax, eax
0x18002fcd6  jnz     loc_18002FDA2
0x18002fcdc  call    cs:__imp_GetLastError
0x18002fce2  mov     ebx, eax
0x18002fce4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fceb  cmp     rcx, r13
0x18002fcee  jz      short loc_18002FD15
0x18002fcf0  test    byte ptr [rcx+44h], 4
0x18002fcf4  jz      short loc_18002FD15
0x18002fcf6  cmp     byte ptr [rcx+41h], 2
0x18002fcfa  jb      short loc_18002FD15
0x18002fcfc  mov     edx, 10h
0x18002fd01  mov     rax, [rdi]
0x18002fd04  mov     [rsp+0D0h+var_B0], rax
0x18002fd09  mov     r9d, ebx
0x18002fd0c  mov     rcx, [rcx+38h]
0x18002fd10  call    WPP_SF_DS
0x18002fd15  mov     ecx, 58h ; 'X'; unsigned __int64
0x18002fd1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fd1f  mov     [rbp+57h+var_88], rax
0x18002fd23  test    rax, rax
0x18002fd26  jz      short loc_18002FD33
0x18002fd28  mov     edx, ebx; int
0x18002fd2a  mov     rcx, rax; this
0x18002fd2d  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18002fd32  nop
0x18002fd33  mov     rdx, rax
0x18002fd36  lea     rcx, [rbp+57h+pExceptionObject]
0x18002fd3a  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18002fd3f  nop
0x18002fd40  mov     rbx, [rbp+57h+pExceptionObject]
0x18002fd44  test    rbx, rbx
0x18002fd47  jz      short loc_18002FD81
0x18002fd49  cmp     qword ptr [rbx], 0
0x18002fd4d  jz      short loc_18002FD81
0x18002fd4f  mov     r8d, 0BEh; int
0x18002fd55  lea     rdx, aDriversStorage_2; "drivers\\storage\\imapi2\\filesystemima"...
0x18002fd5c  mov     rcx, [rbx]; this
0x18002fd5f  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18002fd64  mov     [rbp+57h+var_88], rbx
0x18002fd68  test    rbx, rbx
0x18002fd6b  jz      short loc_18002FD70
0x18002fd6d  inc     dword ptr [rbx+8]
0x18002fd70  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18002fd77  lea     rcx, [rbp+57h+var_88]; pExceptionObject
0x18002fd7b  call    _CxxThrowException_0
0x18002fd81  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18002fd88  lea     rcx, [rbp+57h+var_80]; this
0x18002fd8c  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18002fd91  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18002fd98  lea     rcx, [rbp+57h+var_80]; pExceptionObject
0x18002fd9c  call    _CxxThrowException_0
0x18002fda2  mov     rdx, [rbp+57h+FilePart]
0x18002fda6  mov     rcx, r14
0x18002fda9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002fdae  mov     rcx, [rbp+57h+FilePart]
0x18002fdb2  test    rcx, rcx
0x18002fdb5  jz      short loc_18002FDC4
0x18002fdb7  sub     rcx, rbx
0x18002fdba  sar     rcx, 1
0x18002fdbd  xor     eax, eax
0x18002fdbf  mov     [rbx+rcx*2-2], ax
0x18002fdc4  mov     rdx, rbx
0x18002fdc7  mov     rcx, r15
0x18002fdca  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002fdcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdd6  cmp     rcx, r13
0x18002fdd9  jz      short loc_18002FDFD
0x18002fddb  test    byte ptr [rcx+44h], 8
0x18002fddf  jz      short loc_18002FDFD
0x18002fde1  cmp     byte ptr [rcx+41h], 5
0x18002fde5  jb      short loc_18002FDFD
0x18002fde7  mov     edx, 11h
0x18002fdec  lea     r8, WPP_4a1263e1fdae307c29234b23c923e679_Traceguids
0x18002fdf3  mov     rcx, [rcx+38h]
0x18002fdf7  call    WPP_SF_
0x18002fdfc  nop
0x18002fdfd  lea     rcx, [rbp+57h+var_A0]
0x18002fe01  call    ??1?$SmartArrayPtr@E@@QEAA@XZ; SmartArrayPtr<uchar>::~SmartArrayPtr<uchar>(void)
0x18002fe06  nop
0x18002fe07  lea     rcx, [rbp+57h+lpFileName]; void *
0x18002fe0b  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002fe10  lea     r11, [rsp+0D0h+var_20]
0x18002fe18  mov     rbx, [r11+30h]
0x18002fe1c  mov     rsi, [r11+38h]
0x18002fe20  mov     rsp, r11
0x18002fe23  pop     r15
0x18002fe25  pop     r14
0x18002fe27  pop     r13
0x18002fe29  pop     rdi
0x18002fe2a  pop     rbp
0x18002fe2b  retn
```
