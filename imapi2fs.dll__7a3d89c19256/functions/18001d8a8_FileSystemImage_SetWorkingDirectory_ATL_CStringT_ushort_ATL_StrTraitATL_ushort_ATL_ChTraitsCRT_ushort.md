# FileSystemImage::SetWorkingDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18001d8a8`
- end: `0x18001dc8c`
- name: `?SetWorkingDirectory@FileSystemImage@@QEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(FileSystemImage *this, void *)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x18005aea0`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180004c70`
- `0x180005040`
- `0x1800051a0`
- `0x180005568`
- `0x18000960c`
- `0x18000d1c0`
- `0x18000ea14`
- `0x18001d8a8`
- `0x18001dc94`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x18002f534`
- `0x18003016c`
- `0x180043f0c`
- `0x180081750`

## import_xrefs

- `msvcrt!_wstat` at `0x18001d9d5`
- `msvcrt!_wstat` at `0x18001d9d5`
- `msvcrt!_wcsicmp` at `0x18001d9b1`
- `msvcrt!_wcsicmp` at `0x18001d9b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall FileSystemImage::SetWorkingDirectory(char **this, char **a2)
{
  _BYTE *v4; // rdx
  __int64 v5; // r8
  _QWORD *v6; // rcx
  int *v7; // rsi
  __int64 v8; // rbx
  _QWORD *v9; // r14
  CIMAPIException *v10; // rax
  __int64 v11; // rbx
  CIMAPIException *v12; // rax
  CIMAPIException **v13; // rbx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rsi
  CIMAPIException *v16; // rax
  CIMAPIException **v17; // rbx
  __int64 v18; // r8
  char *v19; // rdx
  int *v20; // rcx
  int *v21; // rsi
  __int64 v22; // rbx
  CIMAPIException **pExceptionObject; // [rsp+30h] [rbp-79h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v25[88]; // [rsp+48h] [rbp-61h] BYREF
  _OWORD v26[3]; // [rsp+A0h] [rbp-9h] BYREF

  v24[1] = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  while ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(a2, (unsigned int)(*((_DWORD *)*a2 - 4) - 1)) == 92
       || (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(a2, (unsigned int)(*((_DWORD *)*a2 - 4) - 1)) == 47 )
  {
    v4 = *(_BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                      a2,
                      v24,
                      (unsigned int)(*((_DWORD *)*a2 - 4) - 1));
    v6 = v4 - 24;
    v7 = (int *)(*a2 - 24);
    if ( v4 - 24 != (_BYTE *)v7 )
    {
      if ( v7[4] >= 0 && *v6 == *(_QWORD *)v7 )
      {
        v8 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v6, v4, v5);
        ATL::CStringData::Release((ATL::CStringData *)v7);
        *a2 = (char *)(v8 + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v4, *((_DWORD *)v4 - 4));
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v24);
  }
  v9 = this + 73;
  if ( _wcsicmp((const wchar_t *)this[73], (const wchar_t *)*a2) )
  {
    memset(v26, 0, sizeof(v26));
    if ( (unsigned int)_wstat(*a2, v26) )
    {
      v10 = (CIMAPIException *)operator new(0x58u);
      pExceptionObject = (CIMAPIException **)v10;
      if ( v10 )
        v10 = CIMAPIException::CIMAPIException(v10, -1062555328, *a2);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v24, v10);
      v11 = v24[0];
      if ( v24[0] && *(_QWORD *)v24[0] )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v24[0],
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp",
          402);
        pExceptionObject = (CIMAPIException **)v11;
        if ( v11 )
          ++*(_DWORD *)(v11 + 8);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v25,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v25;
    }
    if ( (WORD3(v26[0]) & 0x4000) == 0 )
    {
      v12 = (CIMAPIException *)operator new(0x58u);
      pExceptionObject = (CIMAPIException **)v12;
      if ( v12 )
        v12 = CIMAPIException::CIMAPIException(v12, -1062555328, *a2);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, v12);
      v13 = pExceptionObject;
      if ( pExceptionObject && *pExceptionObject )
      {
        CIMAPIException::SetCodeRefInfo(
          *pExceptionObject,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp",
          406);
        v24[0] = v13;
        if ( v13 )
          ++*((_DWORD *)v13 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v24;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v25,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v25;
    }
    v14 = Utility::OsPathAvailableSpace(a2);
    v15 = FileSystemImage::CalcImageSize((FileSystemImage *)this) << 11;
    if ( v14 < v15 )
    {
      v16 = (CIMAPIException *)operator new(0x58u);
      pExceptionObject = (CIMAPIException **)v16;
      if ( v16 )
        v16 = CIMAPIException::CIMAPIException(v16, -1062555327, *a2, v14, v15);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, v16);
      v17 = pExceptionObject;
      if ( pExceptionObject && *pExceptionObject )
      {
        CIMAPIException::SetCodeRefInfo(
          *pExceptionObject,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp",
          414);
        v24[0] = v17;
        if ( v17 )
          ++*((_DWORD *)v17 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v24;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v25,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v25;
    }
    CFsiStashFile::Move(*(_QWORD *)this[85], a2);
    v19 = *a2;
    v20 = (int *)(*a2 - 24);
    v21 = (int *)(*v9 - 24LL);
    if ( v20 != v21 )
    {
      if ( v21[4] >= 0 && *(_QWORD *)v20 == *(_QWORD *)v21 )
      {
        v22 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v20, v19, v18);
        ATL::CStringData::Release((ATL::CStringData *)v21);
        *v9 = v22 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(this + 73, v19, *((_DWORD *)v19 - 4));
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
}

```

## disassembly

```asm
0x18001d8a8  mov     [rsp-8+arg_10], rbx
0x18001d8ad  push    rbp
0x18001d8ae  push    rsi
0x18001d8af  push    rdi
0x18001d8b0  push    r14
0x18001d8b2  push    r15
0x18001d8b4  lea     rbp, [rsp-37h]
0x18001d8b9  sub     rsp, 0E0h
0x18001d8c0  mov     rax, cs:__security_cookie
0x18001d8c7  xor     rax, rsp
0x18001d8ca  mov     [rbp+57h+var_30], rax
0x18001d8ce  mov     rdi, rdx
0x18001d8d1  mov     r15, rcx
0x18001d8d4  mov     [rbp+57h+var_C0], rdx
0x18001d8d8  lea     rax, WPP_GLOBAL_Control
0x18001d8df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8e6  cmp     rcx, rax
0x18001d8e9  jz      short loc_18001D90C
0x18001d8eb  test    byte ptr [rcx+44h], 8
0x18001d8ef  jz      short loc_18001D90C
0x18001d8f1  cmp     byte ptr [rcx+41h], 5
0x18001d8f5  jb      short loc_18001D90C
0x18001d8f7  mov     edx, 12h
0x18001d8fc  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x18001d903  mov     rcx, [rcx+38h]
0x18001d907  call    WPP_SF_
0x18001d90c  mov     rax, [rdi]
0x18001d90f  mov     edx, [rax-10h]
0x18001d912  dec     edx
0x18001d914  mov     rcx, rdi
0x18001d917  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18001d91c  cmp     ax, 5Ch ; '\'
0x18001d920  jz      short loc_18001D938
0x18001d922  mov     rax, [rdi]
0x18001d925  mov     edx, [rax-10h]
0x18001d928  dec     edx
0x18001d92a  mov     rcx, rdi
0x18001d92d  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18001d932  cmp     ax, 2Fh ; '/'
0x18001d936  jnz     short loc_18001D9A4
0x18001d938  mov     rax, [rdi]
0x18001d93b  mov     r8d, [rax-10h]
0x18001d93f  dec     r8d
0x18001d942  lea     rdx, [rbp+57h+var_C8]
0x18001d946  mov     rcx, rdi
0x18001d949  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18001d94e  nop
0x18001d94f  mov     rdx, [rax]
0x18001d952  lea     rcx, [rdx-18h]
0x18001d956  mov     rsi, [rdi]
0x18001d959  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001d95d  cmp     rcx, rsi
0x18001d960  jz      short loc_18001D996
0x18001d962  cmp     dword ptr [rsi+10h], 0
0x18001d966  jl      short loc_18001D989
0x18001d968  mov     rax, [rsi]
0x18001d96b  cmp     [rcx], rax
0x18001d96e  jnz     short loc_18001D989
0x18001d970  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001d975  mov     rbx, rax
0x18001d978  mov     rcx, rsi; this
0x18001d97b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d980  lea     rax, [rbx+18h]
0x18001d984  mov     [rdi], rax
0x18001d987  jmp     short loc_18001D996
0x18001d989  mov     r8d, [rdx-10h]
0x18001d98d  mov     rcx, rdi
0x18001d990  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001d995  nop
0x18001d996  lea     rcx, [rbp+57h+var_C8]; void *
0x18001d99a  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001d99f  jmp     loc_18001D90C
0x18001d9a4  lea     r14, [r15+248h]
0x18001d9ab  mov     rdx, [rdi]; String2
0x18001d9ae  mov     rcx, [r14]; String1
0x18001d9b1  call    cs:__imp__wcsicmp
0x18001d9b7  test    eax, eax
0x18001d9b9  jz      loc_18001DC2C
0x18001d9bf  xorps   xmm0, xmm0
0x18001d9c2  movups  [rbp+57h+var_60], xmm0
0x18001d9c6  movups  [rbp+57h+var_50], xmm0
0x18001d9ca  movups  [rbp+57h+var_40], xmm0
0x18001d9ce  lea     rdx, [rbp+57h+var_60]
0x18001d9d2  mov     rcx, [rdi]
0x18001d9d5  call    cs:__imp__wstat
0x18001d9db  test    eax, eax
0x18001d9dd  jz      loc_18001DA76
0x18001d9e3  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001d9e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d9ed  mov     [rbp+57h+pExceptionObject], rax
0x18001d9f1  test    rax, rax
0x18001d9f4  jz      short loc_18001DA07
0x18001d9f6  mov     r8, [rdi]
0x18001d9f9  mov     edx, 0C0AAB140h; int
0x18001d9fe  mov     rcx, rax; this
0x18001da01  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18001da06  nop
0x18001da07  mov     rdx, rax
0x18001da0a  lea     rcx, [rbp+57h+var_C8]
0x18001da0e  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001da13  nop
0x18001da14  mov     rbx, [rbp+57h+var_C8]
0x18001da18  test    rbx, rbx
0x18001da1b  jz      short loc_18001DA55
0x18001da1d  cmp     qword ptr [rbx], 0
0x18001da21  jz      short loc_18001DA55
0x18001da23  mov     r8d, 192h; int
0x18001da29  lea     rdx, aDriversStorage_12; "drivers\\storage\\imapi2\\filesystemima"...
0x18001da30  mov     rcx, [rbx]; this
0x18001da33  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001da38  mov     [rbp+57h+pExceptionObject], rbx
0x18001da3c  test    rbx, rbx
0x18001da3f  jz      short loc_18001DA44
0x18001da41  inc     dword ptr [rbx+8]
0x18001da44  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001da4b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001da4f  call    _CxxThrowException_0
0x18001da55  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001da5c  lea     rcx, [rbp+57h+var_B8]; this
0x18001da60  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001da65  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001da6c  lea     rcx, [rbp+57h+var_B8]; pExceptionObject
0x18001da70  call    _CxxThrowException_0
0x18001da76  mov     eax, 4000h
0x18001da7b  test    word ptr [rbp+57h+var_60+6], ax
0x18001da7f  jnz     loc_18001DB18
0x18001da85  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001da8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001da8f  mov     [rbp+57h+pExceptionObject], rax
0x18001da93  test    rax, rax
0x18001da96  jz      short loc_18001DAA9
0x18001da98  mov     r8, [rdi]
0x18001da9b  mov     edx, 0C0AAB140h; int
0x18001daa0  mov     rcx, rax; this
0x18001daa3  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18001daa8  nop
0x18001daa9  mov     rdx, rax
0x18001daac  lea     rcx, [rbp+57h+pExceptionObject]
0x18001dab0  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001dab5  nop
0x18001dab6  mov     rbx, [rbp+57h+pExceptionObject]
0x18001daba  test    rbx, rbx
0x18001dabd  jz      short loc_18001DAF7
0x18001dabf  cmp     qword ptr [rbx], 0
0x18001dac3  jz      short loc_18001DAF7
0x18001dac5  mov     r8d, 196h; int
0x18001dacb  lea     rdx, aDriversStorage_12; "drivers\\storage\\imapi2\\filesystemima"...
0x18001dad2  mov     rcx, [rbx]; this
0x18001dad5  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001dada  mov     [rbp+57h+var_C8], rbx
0x18001dade  test    rbx, rbx
0x18001dae1  jz      short loc_18001DAE6
0x18001dae3  inc     dword ptr [rbx+8]
0x18001dae6  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001daed  lea     rcx, [rbp+57h+var_C8]; pExceptionObject
0x18001daf1  call    _CxxThrowException_0
0x18001daf7  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001dafe  lea     rcx, [rbp+57h+var_B8]; this
0x18001db02  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001db07  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001db0e  lea     rcx, [rbp+57h+var_B8]; pExceptionObject
0x18001db12  call    _CxxThrowException_0
0x18001db18  mov     rcx, rdi
0x18001db1b  call    ?OsPathAvailableSpace@Utility@@SA_KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Utility::OsPathAvailableSpace(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001db20  mov     rbx, rax
0x18001db23  mov     rcx, r15; this
0x18001db26  call    ?CalcImageSize@FileSystemImage@@QEAAKXZ; FileSystemImage::CalcImageSize(void)
0x18001db2b  shl     eax, 0Bh
0x18001db2e  mov     esi, eax
0x18001db30  cmp     rbx, rsi
0x18001db33  jnb     loc_18001DBD4
0x18001db39  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001db3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001db43  mov     [rbp+57h+pExceptionObject], rax
0x18001db47  test    rax, rax
0x18001db4a  jz      short loc_18001DB65
0x18001db4c  mov     [rsp+100h+var_E0], rsi
0x18001db51  mov     r9, rbx
0x18001db54  mov     r8, [rdi]
0x18001db57  mov     edx, 0C0AAB141h; int
0x18001db5c  mov     rcx, rax; this
0x18001db5f  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18001db64  nop
0x18001db65  mov     rdx, rax
0x18001db68  lea     rcx, [rbp+57h+pExceptionObject]
0x18001db6c  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001db71  nop
0x18001db72  mov     rbx, [rbp+57h+pExceptionObject]
0x18001db76  test    rbx, rbx
0x18001db79  jz      short loc_18001DBB3
0x18001db7b  cmp     qword ptr [rbx], 0
0x18001db7f  jz      short loc_18001DBB3
0x18001db81  mov     r8d, 19Eh; int
0x18001db87  lea     rdx, aDriversStorage_12; "drivers\\storage\\imapi2\\filesystemima"...
0x18001db8e  mov     rcx, [rbx]; this
0x18001db91  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001db96  mov     [rbp+57h+var_C8], rbx
0x18001db9a  test    rbx, rbx
0x18001db9d  jz      short loc_18001DBA2
0x18001db9f  inc     dword ptr [rbx+8]
0x18001dba2  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001dba9  lea     rcx, [rbp+57h+var_C8]; pExceptionObject
0x18001dbad  call    _CxxThrowException_0
0x18001dbb3  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001dbba  lea     rcx, [rbp+57h+var_B8]; this
0x18001dbbe  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001dbc3  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001dbca  lea     rcx, [rbp+57h+var_B8]; pExceptionObject
0x18001dbce  call    _CxxThrowException_0
0x18001dbd4  mov     rcx, [r15+2A8h]
0x18001dbdb  mov     rdx, rdi
0x18001dbde  mov     rcx, [rcx]
0x18001dbe1  call    ?Move@CFsiStashFile@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CFsiStashFile::Move(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001dbe6  mov     rdx, [rdi]
0x18001dbe9  lea     rcx, [rdx-18h]
0x18001dbed  mov     rsi, [r14]
0x18001dbf0  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001dbf4  cmp     rcx, rsi
0x18001dbf7  jz      short loc_18001DC2C
0x18001dbf9  cmp     dword ptr [rsi+10h], 0
0x18001dbfd  jl      short loc_18001DC20
0x18001dbff  mov     rax, [rsi]
0x18001dc02  cmp     [rcx], rax
0x18001dc05  jnz     short loc_18001DC20
0x18001dc07  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001dc0c  mov     rbx, rax
0x18001dc0f  mov     rcx, rsi; this
0x18001dc12  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001dc17  lea     rax, [rbx+18h]
0x18001dc1b  mov     [r14], rax
0x18001dc1e  jmp     short loc_18001DC2C
0x18001dc20  mov     r8d, [rdx-10h]
0x18001dc24  mov     rcx, r14
0x18001dc27  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001dc2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc33  lea     rax, WPP_GLOBAL_Control
0x18001dc3a  cmp     rcx, rax
0x18001dc3d  jz      short loc_18001DC61
0x18001dc3f  test    byte ptr [rcx+44h], 8
0x18001dc43  jz      short loc_18001DC61
0x18001dc45  cmp     byte ptr [rcx+41h], 5
0x18001dc49  jb      short loc_18001DC61
0x18001dc4b  mov     edx, 13h
0x18001dc50  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x18001dc57  mov     rcx, [rcx+38h]
0x18001dc5b  call    WPP_SF_
0x18001dc60  nop
0x18001dc61  mov     rcx, rdi; void *
0x18001dc64  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001dc69  mov     rcx, [rbp+57h+var_30]
0x18001dc6d  xor     rcx, rsp; StackCookie
0x18001dc70  call    __security_check_cookie
0x18001dc75  mov     rbx, [rsp+100h+arg_10]
0x18001dc7d  add     rsp, 0E0h
0x18001dc84  pop     r15
0x18001dc86  pop     r14
0x18001dc88  pop     rdi
0x18001dc89  pop     rsi
0x18001dc8a  pop     rbp
0x18001dc8b  retn
```
