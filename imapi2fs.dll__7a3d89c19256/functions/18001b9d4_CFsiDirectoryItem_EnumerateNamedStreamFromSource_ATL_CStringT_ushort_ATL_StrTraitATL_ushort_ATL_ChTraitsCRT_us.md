# CFsiDirectoryItem::EnumerateNamedStreamFromSource(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18001b9d4`
- end: `0x18001bee1`
- name: `?EnumerateNamedStreamFromSource@CFsiDirectoryItem@@AEAA?AV?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1293`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180005ff0`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003a80`
- `0x180004c70`
- `0x180005040`
- `0x1800051a0`
- `0x180005568`
- `0x1800058f8`
- `0x1800063b8`
- `0x180007104`
- `0x18000960c`
- `0x18000d1c0`
- `0x18000ea14`
- `0x18001b974`
- `0x18001b9d4`
- `0x18001bee8`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x18002dc70`
- `0x180030d88`
- `0x180033204`
- `0x18003f544`
- `0x18003f610`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18001baaa`
- `ntdll!NtQueryInformationFile` at `0x18001baaa`
- `KERNEL32!CreateFileW` at `0x18001ba51`
- `KERNEL32!CreateFileW` at `0x18001ba51`
- `KERNEL32!CloseHandle` at `0x18001bac1`
- `KERNEL32!CloseHandle` at `0x18001bd25`
- `KERNEL32!CloseHandle` at `0x18001bac1`
- `KERNEL32!CloseHandle` at `0x18001bd25`
- `KERNEL32!GetLastError` at `0x18001baef`
- `KERNEL32!GetLastError` at `0x18001bb2a`
- `KERNEL32!GetLastError` at `0x18001bd75`
- `KERNEL32!GetLastError` at `0x18001be52`
- `KERNEL32!GetLastError` at `0x18001baef`
- `KERNEL32!GetLastError` at `0x18001bb2a`
- `KERNEL32!GetLastError` at `0x18001bd75`
- `KERNEL32!GetLastError` at `0x18001be52`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall CFsiDirectoryItem::EnumerateNamedStreamFromSource(CIMAPIException **a1, _QWORD *a2, LPCWSTR *a3)
{
  char *FileW; // r14
  unsigned int i; // esi
  PVOID *v7; // rbx
  NTSTATUS v8; // r15d
  CIMAPIException *v9; // rbx
  signed int v10; // eax
  CIMAPIException *v11; // rax
  CIMAPIException **v12; // rbx
  unsigned int *v13; // rsi
  unsigned int v14; // eax
  __int64 v15; // rdx
  int *v16; // r14
  __int64 v17; // rbx
  int v18; // edx
  unsigned __int64 v19; // rax
  __int64 v20; // rbx
  unsigned __int16 **v21; // rdx
  CIMAPIException *v23; // rbx
  signed int v24; // eax
  CIMAPIException *v25; // rax
  CIMAPIException **v26; // rbx
  CIMAPIException *v27; // rbx
  signed int LastError; // eax
  CIMAPIException *v29; // rax
  CIMAPIException **v30; // rbx
  unsigned __int16 *v31; // [rsp+48h] [rbp-79h] BYREF
  int v32; // [rsp+50h] [rbp-71h]
  _QWORD v33[3]; // [rsp+58h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-51h] BYREF
  _BYTE v35[152]; // [rsp+80h] [rbp-41h] BYREF
  CIMAPIException **v36; // [rsp+128h] [rbp+67h] BYREF
  _QWORD *v37; // [rsp+130h] [rbp+6Fh]
  LPCWSTR *v38; // [rsp+138h] [rbp+77h]
  CIMAPIException **pExceptionObject; // [rsp+140h] [rbp+7Fh] BYREF

  v38 = a3;
  v37 = a2;
  v36 = a1;
  BufferDescr::BufferDescr((BufferDescr *)v33);
  IoStatusBlock = 0;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v32 = 1;
  std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::clear(a2);
  FileW = (char *)CreateFileW(*a3, 0, 3u, 0, 3u, 0x2000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids, *a3);
    }
    v27 = (CIMAPIException *)operator new(0x58u);
    v36 = (CIMAPIException **)v27;
    if ( v27 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v29 = CIMAPIException::CIMAPIException(v27, LastError);
    }
    else
    {
      v29 = 0;
    }
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v36, v29);
    v30 = v36;
    if ( v36 && *v36 )
    {
      CIMAPIException::SetCodeRefInfo(*v36, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 1966);
      pExceptionObject = v30;
      if ( v30 )
        ++*((_DWORD *)v30 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v35, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v35;
  }
  for ( i = 4096; ; i *= 2 )
  {
    BufferDescr::Allocate((BufferDescr *)v33, i);
    v7 = (PVOID *)v33[0];
    if ( !v33[0] || !*(_QWORD *)v33[0] )
    {
      CloseHandle(FileW);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids);
      }
      v23 = (CIMAPIException *)operator new(0x58u);
      v36 = (CIMAPIException **)v23;
      if ( v23 )
      {
        v24 = GetLastError();
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        v25 = CIMAPIException::CIMAPIException(v23, v24);
      }
      else
      {
        v25 = 0;
      }
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v36, v25);
      v26 = v36;
      if ( v36 && *v36 )
      {
        CIMAPIException::SetCodeRefInfo(*v36, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 2005);
        pExceptionObject = v26;
        if ( v26 )
          ++*((_DWORD *)v26 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v35,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v35;
    }
    *(_DWORD *)(*(_QWORD *)v33[0] + 4LL) = 0;
    v8 = NtQueryInformationFile(FileW, &IoStatusBlock, *v7, i, FileStreamInformation);
    if ( v8 != -2147483643 )
      break;
  }
  CloseHandle(FileW);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids);
    }
    v9 = (CIMAPIException *)operator new(0x58u);
    v36 = (CIMAPIException **)v9;
    if ( v9 )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      v11 = CIMAPIException::CIMAPIException(v9, v10);
    }
    else
    {
      v11 = 0;
    }
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v36, v11);
    v12 = v36;
    if ( v36 && *v36 )
    {
      CIMAPIException::SetCodeRefInfo(*v36, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 2016);
      pExceptionObject = v12;
      if ( v12 )
        ++*((_DWORD *)v12 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v35, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v35;
  }
  if ( v7 )
  {
    v13 = (unsigned int *)*v7;
    if ( *v7 )
    {
      while ( v13[1] )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v31,
          v13 + 6);
        v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
                &v31,
                58);
        v15 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                           &v31,
                           &v36,
                           v14);
        v16 = (int *)(v31 - 12);
        if ( (unsigned __int16 *)(v15 - 24) != v31 - 12 )
        {
          if ( v16[4] >= 0 && *(_QWORD *)(v15 - 24) == *(_QWORD *)v16 )
          {
            v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
            ATL::CStringData::Release((ATL::CStringData *)v16);
            v31 = (unsigned __int16 *)(v17 + 24);
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, v15, *(unsigned int *)(v15 - 16));
          }
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v36);
        v18 = *v31 - 58;
        if ( *v31 == 58 )
          v18 = v31[1];
        if ( v18 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(&v31);
          v19 = a2[1];
          if ( (unsigned __int64)&v31 >= v19 || *a2 > (unsigned __int64)&v31 )
          {
            if ( v19 == a2[2] )
              std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::_Reserve(a2);
            v21 = &v31;
          }
          else
          {
            v20 = ((__int64)&v31 - *a2) >> 3;
            if ( v19 == a2[2] )
              std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::_Reserve(a2);
            v21 = (unsigned __int16 **)(*a2 + 8 * v20);
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            a2[1],
            v21);
          a2[1] += 8LL;
        }
        if ( !*v13 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v31);
          break;
        }
        v13 = (unsigned int *)((char *)v13 + *v13);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v31);
      }
    }
  }
  SmartArrayPtr<unsigned char>::~SmartArrayPtr<unsigned char>(v33);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a3);
  return a2;
}

```

## disassembly

```asm
0x18001b9d4  mov     rax, rsp
0x18001b9d7  mov     [rax+18h], r8
0x18001b9db  mov     [rax+10h], rdx
0x18001b9df  mov     [rax+8], rcx
0x18001b9e3  push    rbp
0x18001b9e4  push    rbx
0x18001b9e5  push    rsi
0x18001b9e6  push    rdi
0x18001b9e7  push    r12
0x18001b9e9  push    r13
0x18001b9eb  push    r14
0x18001b9ed  push    r15
0x18001b9ef  lea     rbp, [rax-5Fh]
0x18001b9f3  sub     rsp, 0D8h
0x18001b9fa  mov     r12, r8
0x18001b9fd  mov     rdi, rdx
0x18001ba00  xor     r13d, r13d
0x18001ba03  mov     [rbp+57h+var_C8], r13d
0x18001ba07  lea     rcx, [rbp+57h+var_C0]; this
0x18001ba0b  call    ??0BufferDescr@@QEAA@XZ; BufferDescr::BufferDescr(void)
0x18001ba10  nop
0x18001ba11  xorps   xmm0, xmm0
0x18001ba14  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001ba18  mov     [rdi], r13
0x18001ba1b  mov     [rdi+8], r13
0x18001ba1f  mov     [rdi+10h], r13
0x18001ba23  mov     [rbp+57h+var_C8], 1
0x18001ba2a  mov     rcx, rdi
0x18001ba2d  call    ?clear@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAAXXZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::clear(void)
0x18001ba32  mov     [rsp+30h], r13; hTemplateFile
0x18001ba37  mov     [rsp+110h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001ba3f  lea     r8d, [r13+3]; dwShareMode
0x18001ba43  mov     [rsp+110h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001ba48  xor     r9d, r9d; lpSecurityAttributes
0x18001ba4b  xor     edx, edx; dwDesiredAccess
0x18001ba4d  mov     rcx, [r12]; lpFileName
0x18001ba51  call    cs:__imp_CreateFileW
0x18001ba57  mov     r14, rax
0x18001ba5a  lea     rcx, [rax-1]
0x18001ba5e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001ba62  ja      loc_18001BE04
0x18001ba68  mov     esi, 1000h
0x18001ba6d  mov     edx, esi; unsigned int
0x18001ba6f  lea     rcx, [rbp+57h+var_C0]; this
0x18001ba73  call    ?Allocate@BufferDescr@@QEAAXK@Z; BufferDescr::Allocate(ulong)
0x18001ba78  mov     rbx, [rbp+57h+var_C0]
0x18001ba7c  test    rbx, rbx
0x18001ba7f  jz      loc_18001BD22
0x18001ba85  cmp     [rbx], r13
0x18001ba88  jz      loc_18001BD22
0x18001ba8e  mov     rax, [rbx]
0x18001ba91  mov     [rax+4], r13d
0x18001ba95  mov     [rsp+110h+dwCreationDisposition], 16h; FileInformationClass
0x18001ba9d  mov     r9d, esi; Length
0x18001baa0  mov     r8, [rbx]; FileInformation
0x18001baa3  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001baa7  mov     rcx, r14; FileHandle
0x18001baaa  call    cs:__imp_NtQueryInformationFile
0x18001bab0  mov     r15d, eax
0x18001bab3  cmp     eax, 80000005h
0x18001bab8  jnz     short loc_18001BABE
0x18001baba  add     esi, esi
0x18001babc  jmp     short loc_18001BA6D
0x18001babe  mov     rcx, r14; hObject
0x18001bac1  call    cs:__imp_CloseHandle
0x18001bac7  test    r15d, r15d
0x18001baca  jns     loc_18001BBB9
0x18001bad0  lea     rax, WPP_GLOBAL_Control
0x18001bad7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bade  cmp     rcx, rax
0x18001bae1  jz      short loc_18001BB14
0x18001bae3  test    byte ptr [rcx+44h], 4
0x18001bae7  jz      short loc_18001BB14
0x18001bae9  cmp     byte ptr [rcx+41h], 2
0x18001baed  jb      short loc_18001BB14
0x18001baef  call    cs:__imp_GetLastError
0x18001baf5  mov     edx, 17h
0x18001bafa  mov     r9d, eax
0x18001bafd  lea     r8, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids
0x18001bb04  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb0b  mov     rcx, [rcx+38h]
0x18001bb0f  call    WPP_SF_d
0x18001bb14  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001bb19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bb1e  mov     rbx, rax
0x18001bb21  mov     [rbp+57h+arg_0], rax
0x18001bb25  test    rax, rax
0x18001bb28  jz      short loc_18001BB48
0x18001bb2a  call    cs:__imp_GetLastError
0x18001bb30  test    eax, eax
0x18001bb32  jle     short loc_18001BB3C
0x18001bb34  movzx   eax, ax
0x18001bb37  or      eax, 80070000h
0x18001bb3c  mov     edx, eax; int
0x18001bb3e  mov     rcx, rbx; this
0x18001bb41  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18001bb46  jmp     short loc_18001BB4B
0x18001bb48  mov     rax, r13
0x18001bb4b  mov     rdx, rax
0x18001bb4e  lea     rcx, [rbp+57h+arg_0]
0x18001bb52  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001bb57  nop
0x18001bb58  mov     rbx, [rbp+57h+arg_0]
0x18001bb5c  test    rbx, rbx
0x18001bb5f  jz      short loc_18001BB98
0x18001bb61  cmp     [rbx], r13
0x18001bb64  jz      short loc_18001BB98
0x18001bb66  mov     r8d, 7E0h; int
0x18001bb6c  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18001bb73  mov     rcx, [rbx]; this
0x18001bb76  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001bb7b  mov     [rbp+57h+pExceptionObject], rbx
0x18001bb7f  test    rbx, rbx
0x18001bb82  jz      short loc_18001BB87
0x18001bb84  inc     dword ptr [rbx+8]
0x18001bb87  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001bb8e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001bb92  call    _CxxThrowException_0
0x18001bb98  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001bb9f  lea     rcx, [rbp+57h+var_98]; this
0x18001bba3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001bba8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001bbaf  lea     rcx, [rbp+57h+var_98]; pExceptionObject
0x18001bbb3  call    _CxxThrowException_0
0x18001bbb9  test    rbx, rbx
0x18001bbbc  jz      loc_18001BCF9
0x18001bbc2  mov     rsi, [rbx]
0x18001bbc5  test    rsi, rsi
0x18001bbc8  jz      loc_18001BCF9
0x18001bbce  mov     r15d, 3Ah ; ':'
0x18001bbd4  cmp     [rsi+4], r13d
0x18001bbd8  jz      loc_18001BCF9
0x18001bbde  lea     rdx, [rsi+18h]
0x18001bbe2  lea     rcx, [rbp+57h+var_D0]
0x18001bbe6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001bbeb  nop
0x18001bbec  mov     edx, r15d
0x18001bbef  lea     rcx, [rbp+57h+var_D0]
0x18001bbf3  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18001bbf8  mov     r8d, eax
0x18001bbfb  lea     rdx, [rbp+57h+arg_0]
0x18001bbff  lea     rcx, [rbp+57h+var_D0]
0x18001bc03  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18001bc08  nop
0x18001bc09  mov     rdx, [rax]
0x18001bc0c  lea     rcx, [rdx-18h]
0x18001bc10  mov     r14, [rbp+57h+var_D0]
0x18001bc14  add     r14, 0FFFFFFFFFFFFFFE8h
0x18001bc18  cmp     rcx, r14
0x18001bc1b  jz      short loc_18001BC53
0x18001bc1d  cmp     [r14+10h], r13d
0x18001bc21  jl      short loc_18001BC45
0x18001bc23  mov     rax, [r14]
0x18001bc26  cmp     [rcx], rax
0x18001bc29  jnz     short loc_18001BC45
0x18001bc2b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001bc30  mov     rbx, rax
0x18001bc33  mov     rcx, r14; this
0x18001bc36  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001bc3b  lea     rax, [rbx+18h]
0x18001bc3f  mov     [rbp+57h+var_D0], rax
0x18001bc43  jmp     short loc_18001BC53
0x18001bc45  mov     r8d, [rdx-10h]
0x18001bc49  lea     rcx, [rbp+57h+var_D0]
0x18001bc4d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001bc52  nop
0x18001bc53  lea     rcx, [rbp+57h+arg_0]; void *
0x18001bc57  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001bc5c  mov     rcx, [rbp+57h+var_D0]
0x18001bc60  movzx   edx, word ptr [rcx]
0x18001bc63  sub     edx, r15d
0x18001bc66  jnz     short loc_18001BC72
0x18001bc68  movzx   edx, word ptr [rcx+2]
0x18001bc6c  movzx   ecx, r13w
0x18001bc70  sub     edx, ecx
0x18001bc72  test    edx, edx
0x18001bc74  jz      short loc_18001BCD7
0x18001bc76  lea     rcx, [rbp+57h+var_D0]
0x18001bc7a  call    ?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(ushort const *)
0x18001bc7f  mov     rax, [rdi+8]
0x18001bc83  lea     rcx, [rbp+57h+var_D0]
0x18001bc87  cmp     rcx, rax
0x18001bc8a  jnb     short loc_18001BCB7
0x18001bc8c  lea     rcx, [rbp+57h+var_D0]
0x18001bc90  cmp     [rdi], rcx
0x18001bc93  ja      short loc_18001BCB7
0x18001bc95  lea     rbx, [rbp+57h+var_D0]
0x18001bc99  sub     rbx, [rdi]
0x18001bc9c  sar     rbx, 3
0x18001bca0  cmp     rax, [rdi+10h]
0x18001bca4  jnz     short loc_18001BCAE
0x18001bca6  mov     rcx, rdi
0x18001bca9  call    ?_Reserve@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::_Reserve(unsigned __int64)
0x18001bcae  mov     rax, [rdi]
0x18001bcb1  lea     rdx, [rax+rbx*8]
0x18001bcb5  jmp     short loc_18001BCC9
0x18001bcb7  cmp     rax, [rdi+10h]
0x18001bcbb  jnz     short loc_18001BCC5
0x18001bcbd  mov     rcx, rdi
0x18001bcc0  call    ?_Reserve@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::_Reserve(unsigned __int64)
0x18001bcc5  lea     rdx, [rbp+57h+var_D0]
0x18001bcc9  mov     rcx, [rdi+8]
0x18001bccd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001bcd2  add     qword ptr [rdi+8], 8
0x18001bcd7  cmp     [rsi], r13d
0x18001bcda  jz      short loc_18001BCEF
0x18001bcdc  mov     eax, [rsi]
0x18001bcde  add     rsi, rax
0x18001bce1  lea     rcx, [rbp+57h+var_D0]; void *
0x18001bce5  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001bcea  jmp     loc_18001BBD4
0x18001bcef  lea     rcx, [rbp+57h+var_D0]; void *
0x18001bcf3  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001bcf8  nop
0x18001bcf9  lea     rcx, [rbp+57h+var_C0]
0x18001bcfd  call    ??1?$SmartArrayPtr@E@@QEAA@XZ; SmartArrayPtr<uchar>::~SmartArrayPtr<uchar>(void)
0x18001bd02  nop
0x18001bd03  mov     rcx, r12; void *
0x18001bd06  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001bd0b  mov     rax, rdi
0x18001bd0e  add     rsp, 0D8h
0x18001bd15  pop     r15
0x18001bd17  pop     r14
0x18001bd19  pop     r13
0x18001bd1b  pop     r12
0x18001bd1d  pop     rdi
0x18001bd1e  pop     rsi
0x18001bd1f  pop     rbx
0x18001bd20  pop     rbp
0x18001bd21  retn
0x18001bd22  mov     rcx, r14; hObject
0x18001bd25  call    cs:__imp_CloseHandle
0x18001bd2b  lea     rax, WPP_GLOBAL_Control
0x18001bd32  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd39  cmp     rcx, rax
0x18001bd3c  jz      short loc_18001BD5F
0x18001bd3e  test    byte ptr [rcx+44h], 4
0x18001bd42  jz      short loc_18001BD5F
0x18001bd44  cmp     byte ptr [rcx+41h], 2
0x18001bd48  jb      short loc_18001BD5F
0x18001bd4a  mov     edx, 16h
0x18001bd4f  lea     r8, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids
0x18001bd56  mov     rcx, [rcx+38h]
0x18001bd5a  call    WPP_SF_
0x18001bd5f  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001bd64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bd69  mov     rbx, rax
0x18001bd6c  mov     [rbp+57h+arg_0], rax
0x18001bd70  test    rax, rax
0x18001bd73  jz      short loc_18001BD93
0x18001bd75  call    cs:__imp_GetLastError
0x18001bd7b  test    eax, eax
0x18001bd7d  jle     short loc_18001BD87
0x18001bd7f  movzx   eax, ax
0x18001bd82  or      eax, 80070000h
0x18001bd87  mov     edx, eax; int
0x18001bd89  mov     rcx, rbx; this
0x18001bd8c  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18001bd91  jmp     short loc_18001BD96
0x18001bd93  mov     rax, r13
0x18001bd96  mov     rdx, rax
0x18001bd99  lea     rcx, [rbp+57h+arg_0]
0x18001bd9d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001bda2  nop
0x18001bda3  mov     rbx, [rbp+57h+arg_0]
0x18001bda7  test    rbx, rbx
0x18001bdaa  jz      short loc_18001BDE3
0x18001bdac  cmp     [rbx], r13
0x18001bdaf  jz      short loc_18001BDE3
0x18001bdb1  mov     r8d, 7D5h; int
0x18001bdb7  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18001bdbe  mov     rcx, [rbx]; this
0x18001bdc1  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001bdc6  mov     [rbp+57h+pExceptionObject], rbx
0x18001bdca  test    rbx, rbx
0x18001bdcd  jz      short loc_18001BDD2
0x18001bdcf  inc     dword ptr [rbx+8]
0x18001bdd2  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001bdd9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001bddd  call    _CxxThrowException_0
0x18001bde3  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001bdea  lea     rcx, [rbp+57h+var_98]; this
0x18001bdee  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001bdf3  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001bdfa  lea     rcx, [rbp+57h+var_98]; pExceptionObject
0x18001bdfe  call    _CxxThrowException_0
0x18001be04  lea     rax, WPP_GLOBAL_Control
0x18001be0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be12  cmp     rcx, rax
0x18001be15  jz      short loc_18001BE3C
0x18001be17  test    byte ptr [rcx+44h], 4
0x18001be1b  jz      short loc_18001BE3C
0x18001be1d  cmp     byte ptr [rcx+41h], 2
0x18001be21  jb      short loc_18001BE3C
0x18001be23  mov     edx, 15h
0x18001be28  mov     r9, [r12]
0x18001be2c  lea     r8, WPP_6c54475ddd03376c268e374d931b1de1_Traceguids
0x18001be33  mov     rcx, [rcx+38h]
0x18001be37  call    WPP_SF_S
0x18001be3c  mov     ecx, 58h ; 'X'; unsigned __int64
  ... truncated ...
```
