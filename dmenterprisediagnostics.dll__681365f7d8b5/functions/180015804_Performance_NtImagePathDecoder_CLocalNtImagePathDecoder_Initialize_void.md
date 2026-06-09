# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x180015804`
- end: `0x180015bba`
- name: `?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ`
- size: `950`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180014ecc`
- `0x180016758`
- `0x18001b77c`

## callees

- `0x180001800`
- `0x180001f10`
- `0x180007618`
- `0x180008044`
- `0x18000fec0`
- `0x1800100fc`
- `0x180014030`
- `0x180014168`
- `0x180014460`
- `0x180015804`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180015850`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180015850`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800158f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800158f2`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180015aab`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180015aab`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180015af2`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180015af2`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180015b09`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180015b09`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800159ad`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800159ad`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180015a0a`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180015a0a`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **this)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // rcx
  const unsigned __int16 *v5; // rdi
  __int64 v6; // rax
  HANDLE FirstVolumeW; // rsi
  int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  WCHAR *v12; // rcx
  bool v13; // r8
  DWORD cchReturnLength; // [rsp+20h] [rbp-C98h] BYREF
  HANDLE v15; // [rsp+28h] [rbp-C90h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-C88h] BYREF
  WCHAR szVolumeName[4]; // [rsp+240h] [rbp-A78h] BYREF
  char v18; // [rsp+248h] [rbp-A70h] BYREF
  __int16 v19; // [rsp+446h] [rbp-872h]
  WCHAR szVolumePathNames[1040]; // [rsp+450h] [rbp-868h] BYREF

  if ( *this != this[1] )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(*this);
    this[1] = *this;
  }
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    ATL::AtlThrowLastWin32();
  v2 = std::_WChar_traits<unsigned short>::length(Buffer);
  std::wstring::_Assign<unsigned short>(this + 6, Buffer, v2);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\??\\\\",
    &qword_18002AA30,
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\??\\",
    &qword_18002AA30,
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\DriverStores\\BSPDRIVERS",
    L"\\\\?\\GLOBALROOT\\DriverStores\\BSPDRIVERS",
    1);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\DriverStore\\Nodes",
    L"\\\\?\\GLOBALROOT\\DriverStore\\Nodes",
    1);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
    ATL::AtlThrowLastWin32();
  v3 = -1;
  do
    ++v3;
  while ( Buffer[v3] );
  if ( v3 < 2 || Buffer[1] != 58 )
    ATL::AtlThrowImpl(-2147418113);
  if ( Buffer[v3 - 1] != 92 )
  {
    if ( v3 >= 0x104 )
      ATL::AtlThrowImpl(-2147024774);
    Buffer[v3] = 92;
    v4 = 2 * v3 + 2;
    if ( v4 >= 0x20A )
      ((void (__noreturn *)(void))_report_rangecheckfailure)();
    *(WCHAR *)((char *)Buffer + v4) = 0;
  }
  v5 = (const unsigned __int16 *)(this + 10);
  v6 = std::_WChar_traits<unsigned short>::length(Buffer);
  std::wstring::_Assign<unsigned short>(this + 10, Buffer, v6);
  if ( (unsigned __int64)this[13] > 7 )
    v5 = *(const unsigned __int16 **)v5;
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\SystemRoot\\",
    v5,
    1);
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
      v8 = 0;
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x410u, &cchReturnLength) )
        LOBYTE(v8) = szVolumePathNames[0] != 0;
      v10 = -1;
      do
        ++v10;
      while ( szVolumeName[v10] );
      if ( v10 && Buffer[v10 + 263] == 92 )
      {
        v11 = 2 * v10 - 2;
        if ( v11 >= 0x208 )
          _report_rangecheckfailure(v11, v9);
        *(WCHAR *)((char *)szVolumeName + v11) = 0;
      }
      if ( szVolumeName[0] != 92
        || szVolumeName[1] != 92
        || szVolumeName[2] != 63
        || (v12 = (WCHAR *)&v18, szVolumeName[3] != 92) )
      {
        v12 = szVolumeName;
      }
      if ( QueryDosDeviceW(v12, Buffer, 0x104u) )
      {
        if ( v8 )
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
            (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
            Buffer,
            szVolumePathNames,
            1);
        else
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(
            (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
            Buffer,
            v13);
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
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\Device\\LanmanRedirector\\",
    L"\\\\",
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\Device\\Mup\\",
    L"\\\\",
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\Device\\vmsmb\\",
    L"\\\\?\\VMSMB\\",
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\GLOBAL??\\",
    L"\\\\?\\",
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    (Performance::NtImagePathDecoder::CNtImagePathDecoderBase *)this,
    L"\\\\",
    L"\\\\",
    0);
  *((_BYTE *)this + 112) = 1;
}

```

## disassembly

```asm
0x180015804  push    rbx
0x180015806  push    rsi
0x180015807  push    rdi
0x180015808  push    r12
0x18001580a  push    r14
0x18001580c  push    r15
0x18001580e  sub     rsp, 0C88h
0x180015815  mov     rax, cs:__security_cookie
0x18001581c  xor     rax, rsp
0x18001581f  mov     [rsp+0CB8h+var_48], rax
0x180015827  mov     rbx, rcx
0x18001582a  mov     rdx, [rcx+8]
0x18001582e  cmp     [rcx], rdx
0x180015831  jz      short loc_180015842
0x180015833  mov     rcx, [rcx]; this
0x180015836  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18001583b  mov     rax, [rbx]
0x18001583e  mov     [rbx+8], rax
0x180015842  mov     r12d, 104h
0x180015848  mov     edx, r12d; uSize
0x18001584b  lea     rcx, [rsp+0CB8h+Buffer]; lpBuffer
0x180015850  call    cs:__imp_GetSystemDirectoryW
0x180015857  nop     dword ptr [rax+rax+00h]
0x18001585c  xor     r14d, r14d
0x18001585f  test    eax, eax
0x180015861  jnz     short loc_180015869
0x180015863  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180015869  lea     rcx, [rsp+0CB8h+Buffer]
0x18001586e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180015873  mov     r8, rax
0x180015876  lea     rcx, [rbx+30h]
0x18001587a  lea     rdx, [rsp+0CB8h+Buffer]
0x18001587f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180015884  xor     r9d, r9d; bool
0x180015887  lea     r8, qword_18002AA30; unsigned __int16 *
0x18001588e  lea     rdx, asc_18002BC20; "\\??\\\\"
0x180015895  mov     rcx, rbx; this
0x180015898  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18001589d  xor     r9d, r9d; bool
0x1800158a0  lea     r8, qword_18002AA30; unsigned __int16 *
0x1800158a7  lea     rdx, asc_18002BC30; "\\??\\"
0x1800158ae  mov     rcx, rbx; this
0x1800158b1  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800158b6  mov     r9b, 1; bool
0x1800158b9  lea     r8, aGlobalrootDriv_1; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x1800158c0  lea     rdx, aDriverstoresBs; "\\DriverStores\\BSPDRIVERS"
0x1800158c7  mov     rcx, rbx; this
0x1800158ca  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800158cf  mov     r9b, 1; bool
0x1800158d2  lea     r8, aGlobalrootDriv_0; "\\\\?\\GLOBALROOT\\DriverStore\\Nodes"
0x1800158d9  lea     rdx, aDriverstoreNod; "\\DriverStore\\Nodes"
0x1800158e0  mov     rcx, rbx; this
0x1800158e3  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800158e8  mov     edx, 105h; uSize
0x1800158ed  lea     rcx, [rsp+0CB8h+Buffer]; lpBuffer
0x1800158f2  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800158f9  nop     dword ptr [rax+rax+00h]
0x1800158fe  test    eax, eax
0x180015900  jnz     short loc_180015908
0x180015902  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180015908  lea     rcx, [rsp+0CB8h+Buffer]
0x18001590d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015911  inc     rax
0x180015914  cmp     [rcx+rax*2], r14w
0x180015919  jnz     short loc_180015911
0x18001591b  cmp     rax, 2
0x18001591f  jb      loc_180015BAF
0x180015925  cmp     [rsp+0CB8h+var_C86], 3Ah ; ':'
0x18001592b  jnz     loc_180015BAF
0x180015931  mov     r15d, 5Ch ; '\'
0x180015937  cmp     [rsp+rax*2+0CB8h+var_C8A], r15w
0x18001593d  jz      short loc_180015965
0x18001593f  cmp     rax, r12
0x180015942  jnb     loc_1800159D3
0x180015948  mov     [rsp+rax*2+0CB8h+Buffer], r15w
0x18001594e  lea     rcx, ds:2[rax*2]
0x180015956  cmp     rcx, 20Ah
0x18001595d  jnb     short loc_1800159CD
0x18001595f  mov     [rsp+rcx+0CB8h+Buffer], r14w
0x180015965  lea     rdi, [rbx+50h]
0x180015969  lea     rcx, [rsp+0CB8h+Buffer]
0x18001596e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180015973  mov     r8, rax
0x180015976  lea     rdx, [rsp+0CB8h+Buffer]
0x18001597b  mov     rcx, rdi
0x18001597e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180015983  cmp     qword ptr [rdi+18h], 7
0x180015988  jbe     short loc_18001598D
0x18001598a  mov     rdi, [rdi]
0x18001598d  mov     r9b, 1; bool
0x180015990  mov     r8, rdi; unsigned __int16 *
0x180015993  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x18001599a  mov     rcx, rbx; this
0x18001599d  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800159a2  mov     edx, r12d; cchBufferLength
0x1800159a5  lea     rcx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x1800159ad  call    cs:__imp_FindFirstVolumeW
0x1800159b4  nop     dword ptr [rax+rax+00h]
0x1800159b9  mov     rsi, rax
0x1800159bc  mov     [rsp+28h], rax
0x1800159c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800159c5  jnz     short loc_1800159DE
0x1800159c7  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800159cd  call    __report_rangecheckfailure
0x1800159d3  mov     ecx, 8007007Ah; int
0x1800159d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800159de  mov     [rsp+0CB8h+cchReturnLength], r14d
0x1800159e3  mov     [rsp+0CB8h+var_872], r14w
0x1800159ec  mov     edi, r14d
0x1800159ef  lea     r9, [rsp+0CB8h+cchReturnLength]; lpcchReturnLength
0x1800159f4  mov     r8d, 410h; cchBufferLength
0x1800159fa  lea     rdx, [rsp+0CB8h+szVolumePathNames]; lpszVolumePathNames
0x180015a02  lea     rcx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x180015a0a  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180015a11  nop     dword ptr [rax+rax+00h]
0x180015a16  test    eax, eax
0x180015a18  jz      short loc_180015A27
0x180015a1a  cmp     [rsp+0CB8h+szVolumePathNames], r14w
0x180015a23  setnz   dil
0x180015a27  lea     rcx, [rsp+0CB8h+szVolumeName]
0x180015a2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015a33  inc     rax
0x180015a36  cmp     [rcx+rax*2], r14w
0x180015a3b  jnz     short loc_180015A33
0x180015a3d  test    rax, rax
0x180015a40  jz      short loc_180015A67
0x180015a42  cmp     [rsp+rax*2+0CB8h+var_A7A], r15w
0x180015a4b  jnz     short loc_180015A67
0x180015a4d  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180015a55  cmp     rcx, 208h
0x180015a5c  jnb     short loc_180015AD9
0x180015a5e  mov     [rsp+rcx+0CB8h+szVolumeName], r14w
0x180015a67  cmp     [rsp+0CB8h+szVolumeName], r15w
0x180015a70  jnz     short loc_180015A9B
0x180015a72  cmp     [rsp+0CB8h+var_A76], r15w
0x180015a7b  jnz     short loc_180015A9B
0x180015a7d  cmp     [rsp+0CB8h+var_A74], 3Fh ; '?'
0x180015a86  jnz     short loc_180015A9B
0x180015a88  cmp     [rsp+0CB8h+var_A72], r15w
0x180015a91  lea     rcx, [rsp+0CB8h+var_A70]
0x180015a99  jz      short loc_180015AA3
0x180015a9b  lea     rcx, [rsp+0CB8h+szVolumeName]; lpDeviceName
0x180015aa3  mov     r8d, r12d; ucchMax
0x180015aa6  lea     rdx, [rsp+0CB8h+Buffer]; lpTargetPath
0x180015aab  call    cs:__imp_QueryDosDeviceW
0x180015ab2  nop     dword ptr [rax+rax+00h]
0x180015ab7  test    eax, eax
0x180015ab9  jz      short loc_180015AE4
0x180015abb  lea     rdx, [rsp+0CB8h+Buffer]; unsigned __int16 *
0x180015ac0  mov     rcx, rbx; this
0x180015ac3  test    edi, edi
0x180015ac5  jz      short loc_180015ADF
0x180015ac7  mov     r9b, 1; bool
0x180015aca  lea     r8, [rsp+0CB8h+szVolumePathNames]; unsigned __int16 *
0x180015ad2  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015ad7  jmp     short loc_180015AE4
0x180015ad9  call    __report_rangecheckfailure
0x180015adf  call    ?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x180015ae4  mov     r8d, r12d; cchBufferLength
0x180015ae7  lea     rdx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x180015aef  mov     rcx, rsi; hFindVolume
0x180015af2  call    cs:__imp_FindNextVolumeW
0x180015af9  nop     dword ptr [rax+rax+00h]
0x180015afe  test    eax, eax
0x180015b00  jnz     loc_1800159E3
0x180015b06  mov     rcx, rsi; hFindVolume
0x180015b09  call    cs:__imp_FindVolumeClose
0x180015b10  nop     dword ptr [rax+rax+00h]
0x180015b15  xor     r9d, r9d; bool
0x180015b18  lea     rdi, asc_18002BE18; "\\\\"
0x180015b1f  mov     r8, rdi; unsigned __int16 *
0x180015b22  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x180015b29  mov     rcx, rbx; this
0x180015b2c  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015b31  xor     r9d, r9d; bool
0x180015b34  mov     r8, rdi; unsigned __int16 *
0x180015b37  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x180015b3e  mov     rcx, rbx; this
0x180015b41  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015b46  xor     r9d, r9d; bool
0x180015b49  lea     r8, aVmsmb; "\\\\?\\VMSMB\\"
0x180015b50  lea     rdx, aDeviceVmsmb; "\\Device\\vmsmb\\"
0x180015b57  mov     rcx, rbx; this
0x180015b5a  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015b5f  xor     r9d, r9d; bool
0x180015b62  lea     r8, asc_18002BDF0; "\\\\?\\"
0x180015b69  lea     rdx, aGlobal; "\\GLOBAL??\\"
0x180015b70  mov     rcx, rbx; this
0x180015b73  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015b78  xor     r9d, r9d; bool
0x180015b7b  mov     r8, rdi; unsigned __int16 *
0x180015b7e  mov     rdx, rdi; unsigned __int16 *
0x180015b81  mov     rcx, rbx; this
0x180015b84  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180015b89  mov     byte ptr [rbx+70h], 1
0x180015b8d  mov     rcx, [rsp+0CB8h+var_48]
0x180015b95  xor     rcx, rsp; StackCookie
0x180015b98  call    __security_check_cookie
0x180015b9d  add     rsp, 0C88h
0x180015ba4  pop     r15
0x180015ba6  pop     r14
0x180015ba8  pop     r12
0x180015baa  pop     rdi
0x180015bab  pop     rsi
0x180015bac  pop     rbx
0x180015bad  retn
0x180015baf  mov     ecx, 8000FFFFh; int
0x180015bb4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
