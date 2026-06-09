# PerfDiagShared::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x18002c830`
- end: `0x18002cde2`
- name: `?Initialize@CLocalNtImagePathDecoder@PerfDiagShared@@AEAAXXZ`
- size: `1458`
- prototype: `void __fastcall(PerfDiagShared::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180042990`

## callees

- `0x180018044`
- `0x180018218`
- `0x180018350`
- `0x18002c830`
- `0x18002d530`
- `0x1800397f0`
- `0x180039bbc`
- `0x18003aaf0`
- `0x180041c4c`
- `0x180056c14`
- `0x180057c28`
- `0x1800cf080`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002c9c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002c9c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c8ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c8ef`
- `KERNEL32!FindFirstVolumeW` at `0x18002caca`
- `KERNEL32!FindFirstVolumeW` at `0x18002caca`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18002cbea`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18002cbea`
- `KERNEL32!QueryDosDeviceW` at `0x18002cca7`
- `KERNEL32!QueryDosDeviceW` at `0x18002cca7`
- `KERNEL32!FindNextVolumeW` at `0x18002cd0c`
- `KERNEL32!FindNextVolumeW` at `0x18002cd0c`
- `KERNEL32!FindVolumeClose` at `0x18002cd5d`
- `KERNEL32!FindVolumeClose` at `0x18002cd5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PerfDiagShared::CLocalNtImagePathDecoder::Initialize(PerfDiagShared::CLocalNtImagePathDecoder *this)
{
  LPWSTR *v2; // rdi
  __int64 i; // rcx
  LPWSTR *v4; // rdx
  WCHAR *v5; // rcx
  LPWSTR *v6; // rdi
  __int64 v7; // rax
  LPWSTR *v8; // rdi
  __int64 j; // rcx
  LPWSTR *v10; // rdx
  WCHAR *v11; // rcx
  LPWSTR *v12; // rax
  LPWSTR v13; // r8
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rdx
  LPWSTR *v16; // rax
  LPWSTR *v17; // rax
  LPWSTR *v18; // rax
  LPWSTR *v19; // rcx
  LPWSTR *v20; // rcx
  const unsigned __int16 *v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rcx
  HANDLE FirstVolumeW; // rax
  void *v25; // rsi
  LPWSTR *v26; // rdi
  __int64 k; // rcx
  LPWSTR *v28; // rdx
  LPWSTR *v29; // rdi
  __int64 m; // rcx
  LPWSTR *v31; // rdx
  int v32; // edi
  WCHAR *v33; // rdx
  __int64 v34; // rdx
  LPWSTR *v35; // rax
  __int64 v36; // rax
  unsigned __int64 v37; // rcx
  WCHAR *v38; // rcx
  WCHAR *v39; // rdx
  bool v40; // r8
  const unsigned __int16 *v41; // rdx
  const unsigned __int16 *v42; // r8
  DWORD cchReturnLength; // [rsp+20h] [rbp-2B8h] BYREF
  HANDLE v44; // [rsp+28h] [rbp-2B0h]
  LPWSTR lpBuffer[2]; // [rsp+30h] [rbp-2A8h] BYREF
  __int64 v46; // [rsp+40h] [rbp-298h]
  UINT uSize[2]; // [rsp+48h] [rbp-290h]
  LPWSTR v48[2]; // [rsp+50h] [rbp-288h] BYREF
  __int64 v49; // [rsp+60h] [rbp-278h]
  UINT v50[2]; // [rsp+68h] [rbp-270h]
  LPWSTR lpTargetPath[2]; // [rsp+70h] [rbp-268h] BYREF
  __int64 v52; // [rsp+80h] [rbp-258h]
  DWORD ucchMax[2]; // [rsp+88h] [rbp-250h]
  WCHAR szVolumeName[4]; // [rsp+90h] [rbp-248h] BYREF
  char v55; // [rsp+98h] [rbp-240h] BYREF

  std::vector<PerfDiagShared::CNtImagePathDecoderBase::CMapping>::_Destroy(this, *(_QWORD *)this, *((_QWORD *)this + 1));
  try
  {
    *((_QWORD *)this + 1) = *(_QWORD *)this;
    *(_QWORD *)uSize = 7;
    v46 = 0;
    LOWORD(lpBuffer[0]) = 0;
    std::wstring::_Copy(lpBuffer, 260, 0);
    v2 = lpBuffer;
    if ( *(_QWORD *)uSize >= 8u )
      v2 = (LPWSTR *)lpBuffer[0];
    for ( i = 260; i; --i )
    {
      *(_WORD *)v2 = 0;
      v2 = (LPWSTR *)((char *)v2 + 2);
    }
    v4 = lpBuffer;
    if ( *(_QWORD *)uSize >= 8u )
      v4 = (LPWSTR *)lpBuffer[0];
    v46 = 260;
    *((_WORD *)v4 + 260) = 0;
    v5 = (WCHAR *)lpBuffer;
    if ( *(_QWORD *)uSize >= 8u )
      v5 = lpBuffer[0];
    if ( !GetSystemDirectoryW(v5, uSize[0]) )
      ATL::AtlThrowLastWin32();
    v6 = lpBuffer;
    if ( *(_QWORD *)uSize >= 8u )
      v6 = (LPWSTR *)lpBuffer[0];
    v7 = std::char_traits<unsigned short>::length(v6);
    std::wstring::assign((char *)this + 48, v6, v7);
    if ( *(_QWORD *)uSize >= 8u )
      operator delete(lpBuffer[0]);
  }
  catch ( std::bad_alloc )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  PerfDiagShared::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\", &qword_1800E1280, 0);
  try
  {
    *(_QWORD *)v50 = 7;
    v49 = 0;
    LOWORD(v48[0]) = 0;
    std::wstring::_Copy(v48, 261, 0);
    v8 = v48;
    if ( *(_QWORD *)v50 >= 8u )
      v8 = (LPWSTR *)v48[0];
    for ( j = 261; j; --j )
    {
      *(_WORD *)v8 = 0;
      v8 = (LPWSTR *)((char *)v8 + 2);
    }
    v10 = v48;
    if ( *(_QWORD *)v50 >= 8u )
      v10 = (LPWSTR *)v48[0];
    v49 = 261;
    *((_WORD *)v10 + 261) = 0;
    v11 = (WCHAR *)v48;
    if ( *(_QWORD *)v50 >= 8u )
      v11 = v48[0];
    if ( !GetSystemWindowsDirectoryW(v11, v50[0]) )
      ATL::AtlThrowLastWin32();
    v12 = v48;
    v13 = v48[0];
    v14 = *(_QWORD *)v50;
    if ( *(_QWORD *)v50 >= 8u )
      v12 = (LPWSTR *)v48[0];
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v12 + v15) );
    if ( v15 < 2 )
      goto LABEL_108;
    v16 = v48;
    if ( *(_QWORD *)v50 >= 8u )
      v16 = (LPWSTR *)v48[0];
    if ( *((_WORD *)v16 + 1) != 58 )
LABEL_108:
      ATL::AtlThrowImpl(-2147418113);
    v17 = v48;
    if ( *(_QWORD *)v50 >= 8u )
      v17 = (LPWSTR *)v48[0];
    if ( *((_WORD *)v17 + v15 - 1) != 92 )
    {
      if ( v15 >= v50[0] - 1 )
        ATL::AtlThrowImpl(-2147024774);
      v18 = v48;
      if ( *(_QWORD *)v50 >= 8u )
        v18 = (LPWSTR *)v48[0];
      *((_WORD *)v18 + v15) = 92;
      v19 = v48;
      if ( *(_QWORD *)v50 >= 8u )
        v19 = (LPWSTR *)v48[0];
      *((_WORD *)v19 + v15 + 1) = 0;
      v14 = *(_QWORD *)v50;
      v13 = v48[0];
    }
    v20 = v48;
    if ( v14 >= 8 )
      v20 = (LPWSTR *)v13;
    v21 = (const unsigned __int16 *)((char *)this + 80);
    v22 = std::char_traits<unsigned short>::length(v20);
    std::wstring::assign((char *)this + 80, v23, v22);
    if ( *((_QWORD *)this + 13) >= 8u )
      v21 = *(const unsigned __int16 **)v21;
    PerfDiagShared::CNtImagePathDecoderBase::AddMapping(this, L"\\SystemRoot\\", v21, 1);
    if ( *(_QWORD *)v50 >= 8u )
      operator delete(v48[0]);
    FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  }
  catch ( std::bad_alloc )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  v25 = FirstVolumeW;
  v44 = FirstVolumeW;
  if ( FirstVolumeW == (HANDLE)-1LL )
    ATL::AtlThrowLastWin32();
  try
  {
    cchReturnLength = 0;
    *(_QWORD *)uSize = 7;
    v46 = 0;
    LOWORD(lpBuffer[0]) = 0;
    std::wstring::_Copy(lpBuffer, 1040, 0);
    v26 = lpBuffer;
    if ( *(_QWORD *)uSize >= 8u )
      v26 = (LPWSTR *)lpBuffer[0];
    for ( k = 1040; k; --k )
    {
      *(_WORD *)v26 = 0;
      v26 = (LPWSTR *)((char *)v26 + 2);
    }
    v28 = lpBuffer;
    if ( *(_QWORD *)uSize >= 8u )
      v28 = (LPWSTR *)lpBuffer[0];
    v46 = 1040;
    *((_WORD *)v28 + 1040) = 0;
    *(_QWORD *)ucchMax = 7;
    v52 = 0;
    LOWORD(lpTargetPath[0]) = 0;
    std::wstring::_Copy(lpTargetPath, 260, 0);
    v29 = lpTargetPath;
    if ( *(_QWORD *)ucchMax >= 8u )
      v29 = (LPWSTR *)lpTargetPath[0];
    for ( m = 260; m; --m )
    {
      *(_WORD *)v29 = 0;
      v29 = (LPWSTR *)((char *)v29 + 2);
    }
    v31 = lpTargetPath;
    if ( *(_QWORD *)ucchMax >= 8u )
      v31 = (LPWSTR *)lpTargetPath[0];
    v52 = 260;
    *((_WORD *)v31 + 260) = 0;
    do
    {
      v32 = 0;
      v33 = (WCHAR *)lpBuffer;
      if ( *(_QWORD *)uSize >= 8u )
        v33 = lpBuffer[0];
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, v33, uSize[0], &cchReturnLength) )
      {
        v35 = lpBuffer;
        if ( *(_QWORD *)uSize >= 8u )
          v35 = (LPWSTR *)lpBuffer[0];
        LOBYTE(v32) = *(_WORD *)v35 != 0;
      }
      v36 = -1;
      do
        ++v36;
      while ( szVolumeName[v36] );
      if ( v36 && *((_WORD *)&ucchMax[1] + v36 + 1) == 92 )
      {
        v37 = 2 * v36 - 2;
        if ( v37 >= 0x208 )
          _report_rangecheckfailure(v37, v34);
        *(WCHAR *)((char *)szVolumeName + v37) = 0;
      }
      if ( szVolumeName[0] != 92
        || szVolumeName[1] != 92
        || szVolumeName[2] != 63
        || (v38 = (WCHAR *)&v55, szVolumeName[3] != 92) )
      {
        v38 = szVolumeName;
      }
      v39 = (WCHAR *)lpTargetPath;
      if ( *(_QWORD *)ucchMax >= 8u )
        v39 = lpTargetPath[0];
      if ( QueryDosDeviceW(v38, v39, ucchMax[0]) )
      {
        v41 = (const unsigned __int16 *)lpTargetPath;
        if ( v32 )
        {
          v42 = (const unsigned __int16 *)lpBuffer;
          if ( *(_QWORD *)uSize >= 8u )
            v42 = lpBuffer[0];
          if ( *(_QWORD *)ucchMax >= 8u )
            v41 = lpTargetPath[0];
          PerfDiagShared::CNtImagePathDecoderBase::AddMapping(this, v41, v42, 1);
        }
        else
        {
          if ( *(_QWORD *)ucchMax >= 8u )
            v41 = lpTargetPath[0];
          PerfDiagShared::CNtImagePathDecoderBase::AddSkip(this, v41, v40);
        }
      }
    }
    while ( FindNextVolumeW(v25, szVolumeName, 0x104u) );
    if ( *(_QWORD *)ucchMax >= 8u )
      operator delete(lpTargetPath[0]);
    *(_QWORD *)ucchMax = 7;
    v52 = 0;
    LOWORD(lpTargetPath[0]) = 0;
    if ( *(_QWORD *)uSize >= 8u )
      operator delete(lpBuffer[0]);
    FindVolumeClose(v25);
  }
  catch ( std::bad_alloc )
  {
    FindVolumeClose(v44);
    ATL::AtlThrowImpl(-2147024882);
  }
  catch ( ... )
  {
    FindVolumeClose(v44);
    throw;
  }
  PerfDiagShared::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\LanmanRedirector\\", L"\\\\", 0);
  PerfDiagShared::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\Mup\\", L"\\\\", 0);
  PerfDiagShared::CNtImagePathDecoderBase::AddMapping(this, L"\\\\", L"\\\\", 0);
  *((_BYTE *)this + 112) = 1;
}

```

## disassembly

```asm
0x18002c830  mov     [rsp+arg_8], rbx
0x18002c835  mov     [rsp+arg_10], rsi
0x18002c83a  push    rdi
0x18002c83b  push    r12
0x18002c83d  push    r13
0x18002c83f  push    r14
0x18002c841  push    r15
0x18002c843  sub     rsp, 2B0h
0x18002c84a  mov     rax, cs:__security_cookie
0x18002c851  xor     rax, rsp
0x18002c854  mov     [rsp+2D8h+var_38], rax
0x18002c85c  mov     rbx, rcx
0x18002c85f  mov     r8, [rcx+8]
0x18002c863  mov     rdx, [rcx]
0x18002c866  call    ?_Destroy@?$vector@UCMapping@CNtImagePathDecoderBase@PerfDiagShared@@V?$allocator@UCMapping@CNtImagePathDecoderBase@PerfDiagShared@@@std@@@std@@IEAAXPEAUCMapping@CNtImagePathDecoderBase@PerfDiagShared@@0@Z; std::vector<PerfDiagShared::CNtImagePathDecoderBase::CMapping>::_Destroy(PerfDiagShared::CNtImagePathDecoderBase::CMapping *,PerfDiagShared::CNtImagePathDecoderBase::CMapping *)
0x18002c86b  mov     rax, [rbx]
0x18002c86e  mov     [rbx+8], rax
0x18002c872  mov     esi, 7
0x18002c877  mov     qword ptr [rsp+2D8h+uSize], rsi
0x18002c87c  xor     r14d, r14d
0x18002c87f  mov     [rsp+2D8h+var_298], r14
0x18002c884  mov     word ptr [rsp+2D8h+lpBuffer], r14w
0x18002c88a  xor     r8d, r8d
0x18002c88d  mov     r13d, 104h
0x18002c893  mov     edx, r13d
0x18002c896  lea     rcx, [rsp+2D8h+lpBuffer]
0x18002c89b  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18002c8a0  lea     rdi, [rsp+2D8h+lpBuffer]
0x18002c8a5  lea     r15d, [rsi+1]
0x18002c8a9  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002c8ae  cmovnb  rdi, [rsp+2D8h+lpBuffer]
0x18002c8b4  movzx   eax, r14w
0x18002c8b8  mov     ecx, r13d
0x18002c8bb  rep stosw
0x18002c8be  lea     rdx, [rsp+2D8h+lpBuffer]
0x18002c8c3  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002c8c8  cmovnb  rdx, [rsp+2D8h+lpBuffer]
0x18002c8ce  mov     [rsp+2D8h+var_298], r13
0x18002c8d3  mov     [rdx+208h], r14w
0x18002c8db  lea     rcx, [rsp+2D8h+lpBuffer]
0x18002c8e0  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002c8e5  cmovnb  rcx, [rsp+2D8h+lpBuffer]; lpBuffer
0x18002c8eb  mov     edx, [rsp+2D8h+uSize]; uSize
0x18002c8ef  call    cs:__imp_GetSystemDirectoryW
0x18002c8f5  test    eax, eax
0x18002c8f7  jnz     short loc_18002C8FE
0x18002c8f9  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18002c8fe  lea     rdi, [rsp+2D8h+lpBuffer]
0x18002c903  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002c908  cmovnb  rdi, [rsp+2D8h+lpBuffer]
0x18002c90e  mov     rcx, rdi
0x18002c911  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002c916  mov     r8, rax
0x18002c919  lea     rcx, [rbx+30h]
0x18002c91d  mov     rdx, rdi
0x18002c920  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002c925  nop
0x18002c926  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002c92b  jb      short loc_18002C938
0x18002c92d  mov     rcx, [rsp+2D8h+lpBuffer]; Block
0x18002c932  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c937  nop
0x18002c938  xor     r9d, r9d; bool
0x18002c93b  lea     r8, qword_1800E1280; unsigned __int16 *
0x18002c942  lea     rdx, asc_1800E1288; "\\??\\"
0x18002c949  mov     rcx, rbx; this
0x18002c94c  call    ?AddMapping@CNtImagePathDecoderBase@PerfDiagShared@@IEAAXPEBG0_N@Z; PerfDiagShared::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002c951  nop
0x18002c952  mov     qword ptr [rsp+2D8h+var_270], rsi
0x18002c957  mov     [rsp+2D8h+var_278], r14
0x18002c95c  mov     word ptr [rsp+2D8h+var_288], r14w
0x18002c962  xor     r8d, r8d
0x18002c965  mov     esi, 105h
0x18002c96a  mov     edx, esi
0x18002c96c  lea     rcx, [rsp+2D8h+var_288]
0x18002c971  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18002c976  lea     rdi, [rsp+2D8h+var_288]
0x18002c97b  cmp     qword ptr [rsp+2D8h+var_270], r15
0x18002c980  cmovnb  rdi, [rsp+2D8h+var_288]
0x18002c986  movzx   eax, r14w
0x18002c98a  mov     ecx, esi
0x18002c98c  rep stosw
0x18002c98f  lea     rdx, [rsp+2D8h+var_288]
0x18002c994  cmp     qword ptr [rsp+2D8h+var_270], r15
0x18002c999  cmovnb  rdx, [rsp+2D8h+var_288]
0x18002c99f  mov     [rsp+2D8h+var_278], rsi
0x18002c9a4  mov     [rdx+20Ah], r14w
0x18002c9ac  lea     rcx, [rsp+2D8h+var_288]
0x18002c9b1  cmp     qword ptr [rsp+2D8h+var_270], r15
0x18002c9b6  cmovnb  rcx, [rsp+2D8h+var_288]; lpBuffer
0x18002c9bc  mov     edx, [rsp+2D8h+var_270]; uSize
0x18002c9c0  call    cs:__imp_GetSystemWindowsDirectoryW
0x18002c9c6  test    eax, eax
0x18002c9c8  jnz     short loc_18002C9CF
0x18002c9ca  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18002c9cf  lea     rax, [rsp+2D8h+var_288]
0x18002c9d4  mov     r8, [rsp+2D8h+var_288]
0x18002c9d9  mov     rdi, qword ptr [rsp+2D8h+var_270]
0x18002c9de  cmp     rdi, r15
0x18002c9e1  cmovnb  rax, r8
0x18002c9e5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002c9e9  inc     rdx
0x18002c9ec  cmp     [rax+rdx*2], r14w
0x18002c9f1  jnz     short loc_18002C9E9
0x18002c9f3  cmp     rdx, 2
0x18002c9f7  jb      loc_18002CDD6
0x18002c9fd  lea     rax, [rsp+2D8h+var_288]
0x18002ca02  cmp     rdi, r15
0x18002ca05  cmovnb  rax, r8
0x18002ca09  cmp     word ptr [rax+2], 3Ah ; ':'
0x18002ca0e  jnz     loc_18002CDD6
0x18002ca14  lea     rax, [rsp+2D8h+var_288]
0x18002ca19  cmp     rdi, r15
0x18002ca1c  cmovnb  rax, r8
0x18002ca20  mov     r12d, 5Ch ; '\'
0x18002ca26  cmp     [rax+rdx*2-2], r12w
0x18002ca2c  jz      short loc_18002CA6B
0x18002ca2e  lea     ecx, [rdi-1]
0x18002ca31  cmp     rdx, rcx
0x18002ca34  jnb     loc_18002CAE4
0x18002ca3a  lea     rax, [rsp+2D8h+var_288]
0x18002ca3f  cmp     rdi, r15
0x18002ca42  cmovnb  rax, r8
0x18002ca46  mov     [rax+rdx*2], r12w
0x18002ca4b  lea     rcx, [rsp+2D8h+var_288]
0x18002ca50  cmp     qword ptr [rsp+2D8h+var_270], r15
0x18002ca55  cmovnb  rcx, [rsp+2D8h+var_288]
0x18002ca5b  mov     [rcx+rdx*2+2], r14w
0x18002ca61  mov     rdi, qword ptr [rsp+2D8h+var_270]
0x18002ca66  mov     r8, [rsp+2D8h+var_288]
0x18002ca6b  lea     rcx, [rsp+2D8h+var_288]
0x18002ca70  cmp     rdi, r15
0x18002ca73  cmovnb  rcx, r8
0x18002ca77  lea     rdi, [rbx+50h]
0x18002ca7b  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002ca80  mov     r8, rax
0x18002ca83  mov     rdx, rcx
0x18002ca86  mov     rcx, rdi
0x18002ca89  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002ca8e  cmp     [rdi+18h], r15
0x18002ca92  jb      short loc_18002CA97
0x18002ca94  mov     rdi, [rdi]
0x18002ca97  mov     r9b, 1; bool
0x18002ca9a  mov     r8, rdi; unsigned __int16 *
0x18002ca9d  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x18002caa4  mov     rcx, rbx; this
0x18002caa7  call    ?AddMapping@CNtImagePathDecoderBase@PerfDiagShared@@IEAAXPEBG0_N@Z; PerfDiagShared::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002caac  nop
0x18002caad  cmp     qword ptr [rsp+2D8h+var_270], r15
0x18002cab2  jb      short loc_18002CABF
0x18002cab4  mov     rcx, [rsp+2D8h+var_288]; Block
0x18002cab9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cabe  nop
0x18002cabf  mov     edx, r13d; cchBufferLength
0x18002cac2  lea     rcx, [rsp+2D8h+szVolumeName]; lpszVolumeName
0x18002caca  call    cs:__imp_FindFirstVolumeW
0x18002cad0  mov     rsi, rax
0x18002cad3  mov     [rsp+2D8h+var_2B0], rax
0x18002cad8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002cadc  jnz     short loc_18002CAEF
0x18002cade  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18002cae4  mov     ecx, 8007007Ah; int
0x18002cae9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002caef  mov     [rsp+2D8h+cchReturnLength], r14d
0x18002caf4  mov     qword ptr [rsp+2D8h+uSize], 7
0x18002cafd  mov     [rsp+2D8h+var_298], r14
0x18002cb02  mov     word ptr [rsp+2D8h+lpBuffer], r14w
0x18002cb08  xor     r8d, r8d
0x18002cb0b  mov     r13d, 410h
0x18002cb11  mov     edx, r13d
0x18002cb14  lea     rcx, [rsp+2D8h+lpBuffer]
0x18002cb19  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18002cb1e  lea     rdi, [rsp+2D8h+lpBuffer]
0x18002cb23  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002cb28  cmovnb  rdi, [rsp+2D8h+lpBuffer]
0x18002cb2e  movzx   eax, r14w
0x18002cb32  mov     ecx, r13d
0x18002cb35  rep stosw
0x18002cb38  lea     rdx, [rsp+2D8h+lpBuffer]
0x18002cb3d  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002cb42  cmovnb  rdx, [rsp+2D8h+lpBuffer]
0x18002cb48  mov     [rsp+2D8h+var_298], r13
0x18002cb4d  mov     [rdx+820h], r14w
0x18002cb55  mov     qword ptr [rsp+2D8h+ucchMax], 7
0x18002cb61  mov     [rsp+2D8h+var_258], r14
0x18002cb69  mov     word ptr [rsp+2D8h+lpTargetPath], r14w
0x18002cb6f  xor     r8d, r8d
0x18002cb72  mov     r13d, 104h
0x18002cb78  mov     edx, r13d
0x18002cb7b  lea     rcx, [rsp+2D8h+lpTargetPath]
0x18002cb80  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18002cb85  lea     rdi, [rsp+2D8h+lpTargetPath]
0x18002cb8a  cmp     qword ptr [rsp+2D8h+ucchMax], r15
0x18002cb92  cmovnb  rdi, [rsp+2D8h+lpTargetPath]
0x18002cb98  movzx   eax, r14w
0x18002cb9c  mov     ecx, r13d
0x18002cb9f  rep stosw
0x18002cba2  lea     rdx, [rsp+2D8h+lpTargetPath]
0x18002cba7  cmp     qword ptr [rsp+2D8h+ucchMax], r15
0x18002cbaf  cmovnb  rdx, [rsp+2D8h+lpTargetPath]
0x18002cbb5  mov     [rsp+2D8h+var_258], r13
0x18002cbbd  mov     [rdx+208h], r14w
0x18002cbc5  mov     edi, r14d
0x18002cbc8  lea     rdx, [rsp+2D8h+lpBuffer]
0x18002cbcd  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002cbd2  cmovnb  rdx, [rsp+2D8h+lpBuffer]; lpszVolumePathNames
0x18002cbd8  lea     r9, [rsp+2D8h+cchReturnLength]; lpcchReturnLength
0x18002cbdd  mov     r8d, [rsp+2D8h+uSize]; cchBufferLength
0x18002cbe2  lea     rcx, [rsp+2D8h+szVolumeName]; lpszVolumeName
0x18002cbea  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18002cbf0  test    eax, eax
0x18002cbf2  jz      short loc_18002CC0C
0x18002cbf4  lea     rax, [rsp+2D8h+lpBuffer]
0x18002cbf9  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002cbfe  cmovnb  rax, [rsp+2D8h+lpBuffer]
0x18002cc04  cmp     [rax], r14w
0x18002cc08  setnz   dil
0x18002cc0c  lea     rcx, [rsp+2D8h+szVolumeName]
0x18002cc14  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002cc18  inc     rax
0x18002cc1b  cmp     [rcx+rax*2], r14w
0x18002cc20  jnz     short loc_18002CC18
0x18002cc22  test    rax, rax
0x18002cc25  jz      short loc_18002CC50
0x18002cc27  cmp     word ptr [rsp+rax*2+2D8h+ucchMax+6], r12w
0x18002cc30  jnz     short loc_18002CC50
0x18002cc32  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18002cc3a  cmp     rcx, 208h
0x18002cc41  jnb     loc_18002CCE5
0x18002cc47  mov     [rsp+rcx+2D8h+szVolumeName], r14w
0x18002cc50  cmp     [rsp+2D8h+szVolumeName], r12w
0x18002cc59  jnz     short loc_18002CC84
0x18002cc5b  cmp     [rsp+2D8h+var_246], r12w
0x18002cc64  jnz     short loc_18002CC84
0x18002cc66  cmp     [rsp+2D8h+var_244], 3Fh ; '?'
0x18002cc6f  jnz     short loc_18002CC84
0x18002cc71  cmp     [rsp+2D8h+var_242], r12w
0x18002cc7a  lea     rcx, [rsp+2D8h+var_240]
0x18002cc82  jz      short loc_18002CC8C
0x18002cc84  lea     rcx, [rsp+2D8h+szVolumeName]; lpDeviceName
0x18002cc8c  lea     rdx, [rsp+2D8h+lpTargetPath]
0x18002cc91  cmp     qword ptr [rsp+2D8h+ucchMax], r15
0x18002cc99  cmovnb  rdx, [rsp+2D8h+lpTargetPath]; lpTargetPath
0x18002cc9f  mov     r8d, [rsp+2D8h+ucchMax]; ucchMax
0x18002cca7  call    cs:__imp_QueryDosDeviceW
0x18002ccad  test    eax, eax
0x18002ccaf  jz      short loc_18002CCFE
0x18002ccb1  lea     rdx, [rsp+2D8h+lpTargetPath]
0x18002ccb6  mov     rcx, rbx; this
0x18002ccb9  test    edi, edi
0x18002ccbb  jz      short loc_18002CCEB
0x18002ccbd  lea     r8, [rsp+2D8h+lpBuffer]
0x18002ccc2  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002ccc7  cmovnb  r8, [rsp+2D8h+lpBuffer]; unsigned __int16 *
0x18002cccd  cmp     qword ptr [rsp+2D8h+ucchMax], r15
0x18002ccd5  cmovnb  rdx, [rsp+2D8h+lpTargetPath]; unsigned __int16 *
0x18002ccdb  mov     r9b, 1; bool
0x18002ccde  call    ?AddMapping@CNtImagePathDecoderBase@PerfDiagShared@@IEAAXPEBG0_N@Z; PerfDiagShared::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002cce3  jmp     short loc_18002CCFE
0x18002cce5  call    __report_rangecheckfailure
0x18002cceb  cmp     qword ptr [rsp+2D8h+ucchMax], r15
0x18002ccf3  cmovnb  rdx, [rsp+2D8h+lpTargetPath]; unsigned __int16 *
0x18002ccf9  call    ?AddSkip@CNtImagePathDecoderBase@PerfDiagShared@@IEAAXPEBG_N@Z; PerfDiagShared::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x18002ccfe  mov     r8d, r13d; cchBufferLength
0x18002cd01  lea     rdx, [rsp+2D8h+szVolumeName]; lpszVolumeName
0x18002cd09  mov     rcx, rsi; hFindVolume
0x18002cd0c  call    cs:__imp_FindNextVolumeW
0x18002cd12  test    eax, eax
0x18002cd14  jnz     loc_18002CBC5
0x18002cd1a  cmp     qword ptr [rsp+2D8h+ucchMax], r15
0x18002cd22  jb      short loc_18002CD2E
0x18002cd24  mov     rcx, [rsp+2D8h+lpTargetPath]; Block
0x18002cd29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cd2e  mov     qword ptr [rsp+2D8h+ucchMax], 7
0x18002cd3a  mov     [rsp+2D8h+var_258], r14
0x18002cd42  mov     word ptr [rsp+2D8h+lpTargetPath], r14w
0x18002cd48  cmp     qword ptr [rsp+2D8h+uSize], r15
0x18002cd4d  jb      short loc_18002CD5A
0x18002cd4f  mov     rcx, [rsp+2D8h+lpBuffer]; Block
0x18002cd54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cd59  nop
0x18002cd5a  mov     rcx, rsi; hFindVolume
0x18002cd5d  call    cs:__imp_FindVolumeClose
0x18002cd63  xor     r9d, r9d; bool
0x18002cd66  lea     rdi, asc_1800E1278; "\\\\"
0x18002cd6d  mov     r8, rdi; unsigned __int16 *
0x18002cd70  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x18002cd77  mov     rcx, rbx; this
0x18002cd7a  call    ?AddMapping@CNtImagePathDecoderBase@PerfDiagShared@@IEAAXPEBG0_N@Z; PerfDiagShared::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002cd7f  xor     r9d, r9d; bool
0x18002cd82  mov     r8, rdi; unsigned __int16 *
0x18002cd85  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x18002cd8c  mov     rcx, rbx; this
0x18002cd8f  call    ?AddMapping@CNtImagePathDecoderBase@PerfDiagShared@@IEAAXPEBG0_N@Z; PerfDiagShared::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002cd94  xor     r9d, r9d; bool
0x18002cd97  mov     r8, rdi; unsigned __int16 *
0x18002cd9a  mov     rdx, rdi; unsigned __int16 *
0x18002cd9d  mov     rcx, rbx; this
0x18002cda0  call    ?AddMapping@CNtImagePathDecoderBase@PerfDiagShared@@IEAAXPEBG0_N@Z; PerfDiagShared::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002cda5  mov     byte ptr [rbx+70h], 1
  ... truncated ...
```
