# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x180014f08`
- end: `0x180015293`
- name: `?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ`
- size: `907`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180014644`
- `0x180015d78`
- `0x18001accc`

## callees

- `0x1800017e0`
- `0x180001ef0`
- `0x180007350`
- `0x180007cc4`
- `0x18000f7d4`
- `0x18000fa0c`
- `0x180013844`
- `0x180013974`
- `0x180013c70`
- `0x180014f08`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014f54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014f54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014ff0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014ff0`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180015197`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180015197`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800151d8`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800151d8`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800151e9`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800151e9`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800150a5`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800150a5`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800150fc`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800150fc`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(
        Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *this)
{
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *v2; // rdx
  __int64 v3; // rax
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rcx
  const unsigned __int16 *v6; // rdi
  __int64 v7; // rax
  HANDLE FirstVolumeW; // rsi
  int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  WCHAR *v13; // rcx
  DWORD cchReturnLength; // [rsp+20h] [rbp-C98h] BYREF
  HANDLE v15; // [rsp+28h] [rbp-C90h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-C88h] BYREF
  WCHAR szVolumeName[4]; // [rsp+240h] [rbp-A78h] BYREF
  char v18; // [rsp+248h] [rbp-A70h] BYREF
  __int16 v19; // [rsp+446h] [rbp-872h]
  WCHAR szVolumePathNames[1040]; // [rsp+450h] [rbp-868h] BYREF

  v2 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)*((_QWORD *)this + 1);
  if ( *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this != v2 )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
      *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this,
      v2);
    *((_QWORD *)this + 1) = *(_QWORD *)this;
  }
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    ATL::AtlThrowLastWin32();
  v3 = std::_WChar_traits<unsigned short>::length(Buffer);
  std::wstring::_Assign<unsigned short>((char *)this + 48, Buffer, v3);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\\\", &qword_180029A30, 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\", &qword_180029A30, 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\DriverStores\\BSPDRIVERS",
    L"\\\\?\\GLOBALROOT\\DriverStores\\BSPDRIVERS",
    1);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\DriverStore\\Nodes",
    L"\\\\?\\GLOBALROOT\\DriverStore\\Nodes",
    1);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
    ATL::AtlThrowLastWin32();
  v4 = -1;
  do
    ++v4;
  while ( Buffer[v4] );
  if ( v4 < 2 || Buffer[1] != 58 )
    ATL::AtlThrowImpl(-2147418113);
  if ( Buffer[v4 - 1] != 92 )
  {
    if ( v4 >= 0x104 )
      ATL::AtlThrowImpl(-2147024774);
    Buffer[v4] = 92;
    v5 = 2 * v4 + 2;
    if ( v5 >= 0x20A )
      ((void (__noreturn *)(void))_report_rangecheckfailure)();
    *(WCHAR *)((char *)Buffer + v5) = 0;
  }
  v6 = (const unsigned __int16 *)((char *)this + 80);
  v7 = std::_WChar_traits<unsigned short>::length(Buffer);
  std::wstring::_Assign<unsigned short>((char *)this + 80, Buffer, v7);
  if ( *((_QWORD *)this + 13) > 7u )
    v6 = *(const unsigned __int16 **)v6;
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\SystemRoot\\", v6, 1);
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  v15 = FirstVolumeW;
  if ( FirstVolumeW == (HANDLE)-1LL )
    ATL::AtlThrowLastWin32();
  try
  {
    cchReturnLength = 0;
    do
    {
      v19 = 0;
      v9 = 0;
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x410u, &cchReturnLength) )
        LOBYTE(v9) = szVolumePathNames[0] != 0;
      v11 = -1;
      do
        ++v11;
      while ( szVolumeName[v11] );
      if ( v11 && Buffer[v11 + 263] == 92 )
      {
        v12 = 2 * v11 - 2;
        if ( v12 >= 0x208 )
          _report_rangecheckfailure(v12, v10);
        *(WCHAR *)((char *)szVolumeName + v12) = 0;
      }
      if ( szVolumeName[0] != 92
        || szVolumeName[1] != 92
        || szVolumeName[2] != 63
        || (v13 = (WCHAR *)&v18, szVolumeName[3] != 92) )
      {
        v13 = szVolumeName;
      }
      if ( QueryDosDeviceW(v13, Buffer, 0x104u) )
      {
        if ( v9 )
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, Buffer, szVolumePathNames, 1);
        else
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(this, Buffer);
      }
    }
    while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
  }
  catch ( ... )
  {
    FindVolumeClose(v15);
    throw;
  }
  FindVolumeClose(FirstVolumeW);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\Device\\LanmanRedirector\\",
    L"\\\\",
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\Mup\\", L"\\\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\vmsmb\\", L"\\\\?\\VMSMB\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\GLOBAL??\\", L"\\\\?\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\\\", L"\\\\", 0);
  *((_BYTE *)this + 112) = 1;
}

```

## disassembly

```asm
0x180014f08  push    rbx
0x180014f0a  push    rsi
0x180014f0b  push    rdi
0x180014f0c  push    r12
0x180014f0e  push    r14
0x180014f10  push    r15
0x180014f12  sub     rsp, 0C88h
0x180014f19  mov     rax, cs:__security_cookie
0x180014f20  xor     rax, rsp
0x180014f23  mov     [rsp+0CB8h+var_48], rax
0x180014f2b  mov     rbx, rcx
0x180014f2e  mov     rdx, [rcx+8]
0x180014f32  cmp     [rcx], rdx
0x180014f35  jz      short loc_180014F46
0x180014f37  mov     rcx, [rcx]; this
0x180014f3a  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x180014f3f  mov     rax, [rbx]
0x180014f42  mov     [rbx+8], rax
0x180014f46  mov     r12d, 104h
0x180014f4c  mov     edx, r12d; uSize
0x180014f4f  lea     rcx, [rsp+0CB8h+Buffer]; lpBuffer
0x180014f54  call    cs:__imp_GetSystemDirectoryW
0x180014f5a  xor     r14d, r14d
0x180014f5d  test    eax, eax
0x180014f5f  jnz     short loc_180014F67
0x180014f61  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180014f67  lea     rcx, [rsp+0CB8h+Buffer]
0x180014f6c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180014f71  mov     r8, rax
0x180014f74  lea     rcx, [rbx+30h]
0x180014f78  lea     rdx, [rsp+0CB8h+Buffer]
0x180014f7d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180014f82  xor     r9d, r9d; bool
0x180014f85  lea     r8, qword_180029A30; unsigned __int16 *
0x180014f8c  lea     rdx, asc_18002AC20; "\\??\\\\"
0x180014f93  mov     rcx, rbx; this
0x180014f96  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180014f9b  xor     r9d, r9d; bool
0x180014f9e  lea     r8, qword_180029A30; unsigned __int16 *
0x180014fa5  lea     rdx, asc_18002AC30; "\\??\\"
0x180014fac  mov     rcx, rbx; this
0x180014faf  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180014fb4  mov     r9b, 1; bool
0x180014fb7  lea     r8, aGlobalrootDriv_1; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x180014fbe  lea     rdx, aDriverstoresBs; "\\DriverStores\\BSPDRIVERS"
0x180014fc5  mov     rcx, rbx; this
0x180014fc8  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180014fcd  mov     r9b, 1; bool
0x180014fd0  lea     r8, aGlobalrootDriv_0; "\\\\?\\GLOBALROOT\\DriverStore\\Nodes"
0x180014fd7  lea     rdx, aDriverstoreNod; "\\DriverStore\\Nodes"
0x180014fde  mov     rcx, rbx; this
0x180014fe1  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180014fe6  mov     edx, 105h; uSize
0x180014feb  lea     rcx, [rsp+0CB8h+Buffer]; lpBuffer
0x180014ff0  call    cs:__imp_GetSystemWindowsDirectoryW
0x180014ff6  test    eax, eax
0x180014ff8  jnz     short loc_180015000
0x180014ffa  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180015000  lea     rcx, [rsp+0CB8h+Buffer]
0x180015005  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015009  inc     rax
0x18001500c  cmp     [rcx+rax*2], r14w
0x180015011  jnz     short loc_180015009
0x180015013  cmp     rax, 2
0x180015017  jb      loc_180015288
0x18001501d  cmp     [rsp+0CB8h+var_C86], 3Ah ; ':'
0x180015023  jnz     loc_180015288
0x180015029  mov     r15d, 5Ch ; '\'
0x18001502f  cmp     [rsp+rax*2+0CB8h+var_C8A], r15w
0x180015035  jz      short loc_18001505D
0x180015037  cmp     rax, r12
0x18001503a  jnb     loc_1800150C5
0x180015040  mov     [rsp+rax*2+0CB8h+Buffer], r15w
0x180015046  lea     rcx, ds:2[rax*2]
0x18001504e  cmp     rcx, 20Ah
0x180015055  jnb     short loc_1800150BF
0x180015057  mov     [rsp+rcx+0CB8h+Buffer], r14w
0x18001505d  lea     rdi, [rbx+50h]
0x180015061  lea     rcx, [rsp+0CB8h+Buffer]
0x180015066  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001506b  mov     r8, rax
0x18001506e  lea     rdx, [rsp+0CB8h+Buffer]
0x180015073  mov     rcx, rdi
0x180015076  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001507b  cmp     qword ptr [rdi+18h], 7
0x180015080  jbe     short loc_180015085
0x180015082  mov     rdi, [rdi]
0x180015085  mov     r9b, 1; bool
0x180015088  mov     r8, rdi; unsigned __int16 *
0x18001508b  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x180015092  mov     rcx, rbx; this
0x180015095  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18001509a  mov     edx, r12d; cchBufferLength
0x18001509d  lea     rcx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x1800150a5  call    cs:__imp_FindFirstVolumeW
0x1800150ab  mov     rsi, rax
0x1800150ae  mov     [rsp+28h], rax
0x1800150b3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800150b7  jnz     short loc_1800150D0
0x1800150b9  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800150bf  call    __report_rangecheckfailure
0x1800150c5  mov     ecx, 8007007Ah; int
0x1800150ca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800150d0  mov     [rsp+0CB8h+cchReturnLength], r14d
0x1800150d5  mov     [rsp+0CB8h+var_872], r14w
0x1800150de  mov     edi, r14d
0x1800150e1  lea     r9, [rsp+0CB8h+cchReturnLength]; lpcchReturnLength
0x1800150e6  mov     r8d, 410h; cchBufferLength
0x1800150ec  lea     rdx, [rsp+0CB8h+szVolumePathNames]; lpszVolumePathNames
0x1800150f4  lea     rcx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x1800150fc  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180015102  test    eax, eax
0x180015104  jz      short loc_180015113
0x180015106  cmp     [rsp+0CB8h+szVolumePathNames], r14w
0x18001510f  setnz   dil
0x180015113  lea     rcx, [rsp+0CB8h+szVolumeName]
0x18001511b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001511f  inc     rax
0x180015122  cmp     [rcx+rax*2], r14w
0x180015127  jnz     short loc_18001511F
0x180015129  test    rax, rax
0x18001512c  jz      short loc_180015153
0x18001512e  cmp     [rsp+rax*2+0CB8h+var_A7A], r15w
0x180015137  jnz     short loc_180015153
0x180015139  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180015141  cmp     rcx, 208h
0x180015148  jnb     short loc_1800151BF
0x18001514a  mov     [rsp+rcx+0CB8h+szVolumeName], r14w
0x180015153  cmp     [rsp+0CB8h+szVolumeName], r15w
0x18001515c  jnz     short loc_180015187
0x18001515e  cmp     [rsp+0CB8h+var_A76], r15w
0x180015167  jnz     short loc_180015187
0x180015169  cmp     [rsp+0CB8h+var_A74], 3Fh ; '?'
0x180015172  jnz     short loc_180015187
0x180015174  cmp     [rsp+0CB8h+var_A72], r15w
0x18001517d  lea     rcx, [rsp+0CB8h+var_A70]
0x180015185  jz      short loc_18001518F
0x180015187  lea     rcx, [rsp+0CB8h+szVolumeName]; lpDeviceName
0x18001518f  mov     r8d, r12d; ucchMax
0x180015192  lea     rdx, [rsp+0CB8h+Buffer]; lpTargetPath
0x180015197  call    cs:__imp_QueryDosDeviceW
0x18001519d  test    eax, eax
0x18001519f  jz      short loc_1800151CA
0x1800151a1  lea     rdx, [rsp+0CB8h+Buffer]; unsigned __int16 *
0x1800151a6  mov     rcx, rbx; this
0x1800151a9  test    edi, edi
0x1800151ab  jz      short loc_1800151C5
0x1800151ad  mov     r9b, 1; bool
0x1800151b0  lea     r8, [rsp+0CB8h+szVolumePathNames]; unsigned __int16 *
0x1800151b8  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800151bd  jmp     short loc_1800151CA
0x1800151bf  call    __report_rangecheckfailure
0x1800151c5  call    ?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x1800151ca  mov     r8d, r12d; cchBufferLength
0x1800151cd  lea     rdx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x1800151d5  mov     rcx, rsi; hFindVolume
0x1800151d8  call    cs:__imp_FindNextVolumeW
0x1800151de  test    eax, eax
0x1800151e0  jnz     loc_1800150D5
0x1800151e6  mov     rcx, rsi; hFindVolume
0x1800151e9  call    cs:__imp_FindVolumeClose
0x1800151ef  xor     r9d, r9d; bool
0x1800151f2  lea     rdi, asc_18002AE18; "\\\\"
0x1800151f9  mov     r8, rdi; unsigned __int16 *
0x1800151fc  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x180015203  mov     rcx, rbx; this
0x180015206  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18001520b  xor     r9d, r9d; bool
0x18001520e  mov     r8, rdi; unsigned __int16 *
0x180015211  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x180015218  mov     rcx, rbx; this
0x18001521b  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015220  xor     r9d, r9d; bool
0x180015223  lea     r8, aVmsmb; "\\\\?\\VMSMB\\"
0x18001522a  lea     rdx, aDeviceVmsmb; "\\Device\\vmsmb\\"
0x180015231  mov     rcx, rbx; this
0x180015234  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015239  xor     r9d, r9d; bool
0x18001523c  lea     r8, asc_18002ADF0; "\\\\?\\"
0x180015243  lea     rdx, aGlobal; "\\GLOBAL??\\"
0x18001524a  mov     rcx, rbx; this
0x18001524d  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015252  xor     r9d, r9d; bool
0x180015255  mov     r8, rdi; unsigned __int16 *
0x180015258  mov     rdx, rdi; unsigned __int16 *
0x18001525b  mov     rcx, rbx; this
0x18001525e  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015263  mov     byte ptr [rbx+70h], 1
0x180015267  mov     rcx, [rsp+0CB8h+var_48]
0x18001526f  xor     rcx, rsp; StackCookie
0x180015272  call    __security_check_cookie
0x180015277  add     rsp, 0C88h
0x18001527e  pop     r15
0x180015280  pop     r14
0x180015282  pop     r12
0x180015284  pop     rdi
0x180015285  pop     rsi
0x180015286  pop     rbx
0x180015287  retn
0x180015288  mov     ecx, 8000FFFFh; int
0x18001528d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
