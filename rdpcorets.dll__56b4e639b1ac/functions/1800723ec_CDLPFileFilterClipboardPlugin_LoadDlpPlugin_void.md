# CDLPFileFilterClipboardPlugin::LoadDlpPlugin(void)

- ea: `0x1800723ec`
- end: `0x180072687`
- name: `?LoadDlpPlugin@CDLPFileFilterClipboardPlugin@@IEAAJXZ`
- size: `667`
- prototype: `__int64 __fastcall(CDLPFileFilterClipboardPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800722f4`

## callees

- `0x1800091a8`
- `0x18002f890`
- `0x180059838`
- `0x180072094`
- `0x1800723ec`
- `0x180072834`
- `0x180072abc`
- `0x180072bb0`
- `0x1800994f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072452`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800724ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072452`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800724ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800724c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007252c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800724c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007252c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180072432`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180072432`

## string_xrefs

- `0x180072445`: `MpCheckAccessForRdpOperation`

## pseudocode

```c
__int64 __fastcall CDLPFileFilterClipboardPlugin::LoadDlpPlugin(HMODULE *this)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  int v4; // edx
  const unsigned __int16 *v5; // r8
  signed int LastError; // ebp
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  char v9; // bp
  unsigned int v10; // eax
  int v11; // r8d
  FARPROC v12; // rax
  char v13; // bp
  unsigned int v14; // eax
  int v15; // r8d
  LPCWSTR v16; // rbx
  unsigned int v17; // eax
  int v18; // edx
  LPCWSTR v19; // rbx
  unsigned int v20; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LPCWSTR lpLibFileName[9]; // [rsp+30h] [rbp-48h] BYREF

  CDLPFileFilterClipboardPlugin::ReleaseDlpPlugin((CDLPFileFilterClipboardPlugin *)this);
  v2 = 1;
  CDLPFileFilterClipboardPlugin::GetDlpPluginPath(v3, (__int64)lpLibFileName);
  if ( lpLibFileName[0] == lpLibFileName[1] )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        &WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    goto LABEL_36;
  }
  LastError = ValidateExeFileDigitalSignature(lpLibFileName[0], v4, v5);
  if ( LastError )
  {
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = lpLibFileName[0];
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)&WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids,
          v20,
          (__int64)v19,
          LastError);
      }
      v2 = -2147019873;
      goto LABEL_36;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_36:
      CDLPFileFilterClipboardPlugin::ReleaseDlpPlugin((CDLPFileFilterClipboardPlugin *)this);
      goto LABEL_37;
    }
    v16 = lpLibFileName[0];
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 19;
LABEL_21:
    WPP_SF_DSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      (unsigned int)&WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids,
      v17,
      (__int64)v16,
      LastError);
    goto LABEL_36;
  }
  LibraryW = LoadLibraryW(lpLibFileName[0]);
  this[1] = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_36;
    }
    v16 = lpLibFileName[0];
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 17;
    goto LABEL_21;
  }
  ProcAddress = GetProcAddress(LibraryW, "MpCheckAccessForRdpOperation");
  this[2] = (HMODULE)ProcAddress;
  if ( !ProcAddress )
  {
    v9 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v11, v10, (__int64)"MpCheckAccessForRdpOperation", v9);
    }
  }
  v12 = GetProcAddress(this[1], "MpIsRdpEnlightmentEnabled");
  this[3] = (HMODULE)v12;
  if ( !v12 )
  {
    v13 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v15, v14, (__int64)"MpIsRdpEnlightmentEnabled", v13);
    }
  }
  if ( !this[2] || !this[3] )
    goto LABEL_36;
  v2 = 0;
LABEL_37:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpLibFileName);
  return v2;
}

```

## disassembly

```asm
0x1800723ec  push    rbx
0x1800723ee  push    rbp
0x1800723ef  push    rsi
0x1800723f0  push    rdi
0x1800723f1  push    r14
0x1800723f3  sub     rsp, 50h
0x1800723f7  mov     rsi, rcx
0x1800723fa  call    ?ReleaseDlpPlugin@CDLPFileFilterClipboardPlugin@@IEAAXXZ; CDLPFileFilterClipboardPlugin::ReleaseDlpPlugin(void)
0x1800723ff  lea     rdx, [rsp+78h+lpLibFileName]
0x180072404  mov     edi, 1
0x180072409  call    ?GetDlpPluginPath@CDLPFileFilterClipboardPlugin@@IEAA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ; CDLPFileFilterClipboardPlugin::GetDlpPluginPath(void)
0x18007240e  mov     rcx, [rsp+78h+lpLibFileName]; unsigned __int16 *
0x180072413  cmp     rcx, [rsp+78h+var_40]
0x180072418  jz      loc_180072625
0x18007241e  call    ?ValidateExeFileDigitalSignature@@YAHPEBGH0@Z; ValidateExeFileDigitalSignature(ushort const *,int,ushort const *)
0x180072423  mov     ebp, eax
0x180072425  test    eax, eax
0x180072427  jnz     loc_180072596
0x18007242d  mov     rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x180072432  call    cs:__imp_LoadLibraryW
0x180072438  mov     [rsi+8], rax
0x18007243c  test    rax, rax
0x18007243f  jz      loc_18007252C
0x180072445  lea     r14, aMpcheckaccessf; "MpCheckAccessForRdpOperation"
0x18007244c  mov     rcx, rax; hModule
0x18007244f  mov     rdx, r14; lpProcName
0x180072452  call    cs:__imp_GetProcAddress
0x180072458  mov     [rsi+10h], rax
0x18007245c  lea     rbx, WPP_GLOBAL_Control
0x180072463  test    rax, rax
0x180072466  jnz     short loc_1800724AC
0x180072468  call    cs:__imp_GetLastError
0x18007246e  mov     ebp, eax
0x180072470  mov     rcx, cs:WPP_GLOBAL_Control
0x180072477  cmp     rcx, rbx
0x18007247a  jz      short loc_1800724AC
0x18007247c  test    [rcx+1Ch], dil
0x180072480  jz      short loc_1800724AC
0x180072482  cmp     byte ptr [rcx+19h], 2
0x180072486  jb      short loc_1800724AC
0x180072488  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007248d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072494  lea     edx, [rdi+0Eh]
0x180072497  mov     [rsp+78h+var_50], ebp
0x18007249b  mov     r9d, eax
0x18007249e  mov     [rsp+78h+var_58], r14
0x1800724a3  mov     rcx, [rcx+10h]
0x1800724a7  call    WPP_SF_Dsd
0x1800724ac  mov     rcx, [rsi+8]; hModule
0x1800724b0  lea     r14, aMpisrdpenlight; "MpIsRdpEnlightmentEnabled"
0x1800724b7  mov     rdx, r14; lpProcName
0x1800724ba  call    cs:__imp_GetProcAddress
0x1800724c0  mov     [rsi+18h], rax
0x1800724c4  test    rax, rax
0x1800724c7  jnz     short loc_18007250F
0x1800724c9  call    cs:__imp_GetLastError
0x1800724cf  mov     ebp, eax
0x1800724d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800724d8  cmp     rcx, rbx
0x1800724db  jz      short loc_18007250F
0x1800724dd  test    [rcx+1Ch], dil
0x1800724e1  jz      short loc_18007250F
0x1800724e3  cmp     byte ptr [rcx+19h], 2
0x1800724e7  jb      short loc_18007250F
0x1800724e9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800724ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800724f5  mov     edx, 10h
0x1800724fa  mov     [rsp+78h+var_50], ebp
0x1800724fe  mov     r9d, eax
0x180072501  mov     [rsp+78h+var_58], r14
0x180072506  mov     rcx, [rcx+10h]
0x18007250a  call    WPP_SF_Dsd
0x18007250f  cmp     qword ptr [rsi+10h], 0
0x180072514  jz      loc_180072668
0x18007251a  cmp     qword ptr [rsi+18h], 0
0x18007251f  jz      loc_180072668
0x180072525  xor     edi, edi
0x180072527  jmp     loc_180072670
0x18007252c  call    cs:__imp_GetLastError
0x180072532  mov     ebp, eax
0x180072534  mov     rax, cs:WPP_GLOBAL_Control
0x18007253b  lea     rbx, WPP_GLOBAL_Control
0x180072542  cmp     rax, rbx
0x180072545  jz      loc_180072668
0x18007254b  test    [rax+1Ch], dil
0x18007254f  jz      loc_180072668
0x180072555  cmp     byte ptr [rax+19h], 2
0x180072559  jb      loc_180072668
0x18007255f  mov     rbx, [rsp+78h+lpLibFileName]
0x180072564  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180072569  mov     edx, 11h
0x18007256e  mov     rcx, cs:WPP_GLOBAL_Control
0x180072575  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x18007257c  mov     [rsp+78h+var_50], ebp
0x180072580  mov     r9d, eax
0x180072583  mov     [rsp+78h+var_58], rbx
0x180072588  mov     rcx, [rcx+10h]
0x18007258c  call    WPP_SF_DSd
0x180072591  jmp     loc_180072668
0x180072596  test    ebp, ebp
0x180072598  jns     short loc_1800725F2
0x18007259a  mov     rax, cs:WPP_GLOBAL_Control
0x1800725a1  lea     rbx, WPP_GLOBAL_Control
0x1800725a8  cmp     rax, rbx
0x1800725ab  jz      short loc_1800725EB
0x1800725ad  test    [rax+1Ch], dil
0x1800725b1  jz      short loc_1800725EB
0x1800725b3  cmp     byte ptr [rax+19h], 2
0x1800725b7  jb      short loc_1800725EB
0x1800725b9  mov     rbx, [rsp+78h+lpLibFileName]
0x1800725be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800725c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800725ca  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x1800725d1  mov     edx, 12h
0x1800725d6  mov     [rsp+78h+var_50], ebp
0x1800725da  mov     r9d, eax
0x1800725dd  mov     [rsp+78h+var_58], rbx
0x1800725e2  mov     rcx, [rcx+10h]
0x1800725e6  call    WPP_SF_DSd
0x1800725eb  mov     edi, 8007139Fh
0x1800725f0  jmp     short loc_180072668
0x1800725f2  mov     rax, cs:WPP_GLOBAL_Control
0x1800725f9  lea     rbx, WPP_GLOBAL_Control
0x180072600  cmp     rax, rbx
0x180072603  jz      short loc_180072668
0x180072605  test    [rax+1Ch], dil
0x180072609  jz      short loc_180072668
0x18007260b  cmp     byte ptr [rax+19h], 2
0x18007260f  jb      short loc_180072668
0x180072611  mov     rbx, [rsp+78h+lpLibFileName]
0x180072616  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007261b  mov     edx, 13h
0x180072620  jmp     loc_18007256E
0x180072625  mov     rax, cs:WPP_GLOBAL_Control
0x18007262c  lea     rbx, WPP_GLOBAL_Control
0x180072633  cmp     rax, rbx
0x180072636  jz      short loc_180072668
0x180072638  test    [rax+1Ch], dil
0x18007263c  jz      short loc_180072668
0x18007263e  cmp     byte ptr [rax+19h], 4
0x180072642  jb      short loc_180072668
0x180072644  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180072649  mov     rcx, cs:WPP_GLOBAL_Control
0x180072650  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x180072657  mov     edx, 14h
0x18007265c  mov     r9d, eax
0x18007265f  mov     rcx, [rcx+10h]
0x180072663  call    WPP_SF_d
0x180072668  mov     rcx, rsi; this
0x18007266b  call    ?ReleaseDlpPlugin@CDLPFileFilterClipboardPlugin@@IEAAXXZ; CDLPFileFilterClipboardPlugin::ReleaseDlpPlugin(void)
0x180072670  lea     rcx, [rsp+78h+lpLibFileName]
0x180072675  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007267a  mov     eax, edi
0x18007267c  add     rsp, 50h
0x180072680  pop     r14
0x180072682  pop     rdi
0x180072683  pop     rsi
0x180072684  pop     rbp
0x180072685  pop     rbx
0x180072686  retn
```
