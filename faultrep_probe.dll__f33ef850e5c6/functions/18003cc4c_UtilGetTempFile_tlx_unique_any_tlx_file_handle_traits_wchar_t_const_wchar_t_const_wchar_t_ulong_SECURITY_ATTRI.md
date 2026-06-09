# UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x18003cc4c`
- end: `0x18003d18d`
- name: `?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `1345`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000fb44`
- `0x1800199f8`
- `0x180043ec4`
- `0x180047adc`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x180006b50`
- `0x18000760c`
- `0x180009e04`
- `0x180009f00`
- `0x18000aa54`
- `0x18000b90c`
- `0x18000e30c`
- `0x180016a6c`
- `0x180023ad8`
- `0x18003c344`
- `0x18003cc4c`
- `0x18003d528`
- `0x18003d5dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d02f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d02f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cfcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cfcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cf60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cf60`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003d020`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003d020`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003cddb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003cddb`

## string_xrefs

- `0x18003ccb6`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18003cd9d`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18003cf00`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18003cf81`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18003cfb4`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`
- `0x18003d139`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilGetTempFile(
        void **a1,
        WCHAR *a2,
        __int64 a3,
        wchar_t *a4,
        __int64 a5,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD a7,
        int a8)
{
  __int64 v12; // rdx
  int TempDirPath; // ebx
  unsigned int v14; // edx
  __int64 v15; // r8
  __int64 v16; // rdx
  const WCHAR *v17; // rcx
  __int64 v18; // r9
  LPCWSTR v19; // rdx
  const wchar_t *v20; // r8
  DWORD FileAttributesW; // eax
  __int64 v23; // rdx
  int v24; // eax
  HANDLE FileW; // rax
  int v26; // r8d
  const char *v27; // r9
  void *v28; // rbx
  void *v29; // rsi
  int v30; // edi
  __int64 v31; // rdx
  signed int LastError; // eax
  void *v33; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v37; // [rsp+48h] [rbp-B8h]
  _WORD v38[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszShortPath[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v40[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwShareMode[4]; // [rsp+80h] [rbp-80h]
  wchar_t v42[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  dwShareMode[0] = a7;
  if ( !a4 )
  {
    v12 = 75;
LABEL_3:
    TempDirPath = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)TempDirPath,
      dwCreationDisposition);
    return (unsigned int)TempDirPath;
  }
  memset_0(FileName, 0, 0x208u);
  if ( !a2 )
  {
    TempDirPath = UtilGetTempDirPath(FileName, v14);
    if ( TempDirPath < 0 )
    {
      v12 = 80;
      goto LABEL_4;
    }
    a2 = FileName;
  }
  if ( !*a2 )
  {
    v12 = 89;
    goto LABEL_3;
  }
  lpFileName = v38;
  v37 = v38;
  v38[0] = 0;
  v15 = -1;
  do
    ++v15;
  while ( a2[v15] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpFileName,
                           a2) )
  {
    v16 = 94;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    if ( lpFileName != v38 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v17 = lpFileName;
  if ( (unsigned __int64)(v37 - lpFileName) >= 4 )
  {
    v18 = 4;
    v19 = lpFileName;
    v20 = L"\\\\?\\";
    while ( *v20 == *v19 )
    {
      ++v20;
      ++v19;
      if ( !--v18 )
        goto LABEL_26;
    }
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(&lpFileName) )
  {
    v16 = 100;
    goto LABEL_22;
  }
  v17 = lpFileName;
LABEL_26:
  FileAttributesW = GetFileAttributesW(v17);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    TempDirPath = -2147024809;
    v23 = 106;
    goto LABEL_74;
  }
  if ( a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (_DWORD)lpFileName,
        a3);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, lpFileName);
  }
  TempDirPath = UtilUuidCreateAsString(v42);
  if ( TempDirPath < 0 )
  {
    v23 = 118;
LABEL_74:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)TempDirPath,
      dwCreationDisposition);
LABEL_75:
    if ( lpFileName != v38 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)TempDirPath;
  }
  lpszShortPath[0] = v40;
  lpszShortPath[1] = v40;
  v40[0] = 0;
  v24 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          lpszShortPath,
          L"%ls%lsWER.%ls.tmp%ls");
  TempDirPath = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)v24,
      (int)v42);
    goto LABEL_39;
  }
  FileW = CreateFileW(lpszShortPath[0], 0xC0000000, dwShareMode[0], lpSecurityAttributes, 1u, a8 | 0x80u, 0);
  v28 = FileW;
  v29 = FileW;
  *(_QWORD *)dwShareMode = FileW;
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    TempDirPath = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x8A,
                    (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
                    v27);
LABEL_39:
    if ( lpszShortPath[0] != v40 )
      operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_75;
  }
  v30 = UtilVerifyFilePath((wchar_t *)lpszShortPath[0], FileW, v26, (int)v27);
  if ( v30 < 0 )
  {
    v31 = 142;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)(unsigned int)v30,
      dwCreationDispositiona);
    CloseHandle(v28);
    if ( lpszShortPath[0] != v40 )
      operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpFileName != v38 )
      operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v30;
  }
  if ( GetLongPathNameW(lpszShortPath[0], a4, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (unsigned int)LastError);
    v30 = StringCchCopyW(a4, 0x104u, lpszShortPath[0]);
    if ( v30 < 0 )
    {
      v31 = 154;
      goto LABEL_45;
    }
  }
  if ( a1 )
  {
    v29 = 0;
    v33 = *a1;
    *a1 = v28;
    if ( (unsigned __int64)v33 + 1 > 1 )
      CloseHandle(v33);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, a4);
  if ( (unsigned __int64)v29 + 1 > 1 )
    CloseHandle(v29);
  if ( lpszShortPath[0] != v40 )
    operator delete((void *)lpszShortPath[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v38 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x18003cc4c  push    rbp
0x18003cc4e  push    rbx
0x18003cc4f  push    rsi
0x18003cc50  push    rdi
0x18003cc51  push    r12
0x18003cc53  push    r13
0x18003cc55  push    r14
0x18003cc57  push    r15
0x18003cc59  lea     rbp, [rsp-208h]
0x18003cc61  sub     rsp, 308h
0x18003cc68  mov     rax, cs:__security_cookie
0x18003cc6f  xor     rax, rsp
0x18003cc72  mov     [rbp+240h+var_50], rax
0x18003cc79  mov     r12, r9
0x18003cc7c  mov     rdi, r8
0x18003cc7f  mov     rbx, rdx
0x18003cc82  mov     r15, rcx
0x18003cc85  mov     r13, [rbp+240h+lpSecurityAttributes]
0x18003cc8c  mov     eax, [rbp+240h+arg_30]
0x18003cc92  mov     [rbp+240h+dwShareMode], eax
0x18003cc95  mov     esi, [rbp+240h+arg_38]
0x18003cc9b  xor     r14d, r14d
0x18003cc9e  test    r9, r9
0x18003cca1  jnz     short loc_18003CCC7
0x18003cca3  lea     edx, [r9+4Bh]; void *
0x18003cca7  mov     ebx, 80070057h
0x18003ccac  mov     rcx, [rbp+248h]; this
0x18003ccb3  mov     r9d, ebx; char *
0x18003ccb6  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x18003ccbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ccc2  jmp     loc_18003D168
0x18003ccc7  xor     edx, edx; Val
0x18003ccc9  mov     r8d, 208h; Size
0x18003cccf  lea     rcx, [rbp+240h+FileName]; void *
0x18003ccd3  call    memset_0
0x18003ccd8  test    rbx, rbx
0x18003ccdb  jnz     short loc_18003CCF7
0x18003ccdd  lea     rcx, [rbp+240h+FileName]; lpFileName
0x18003cce1  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x18003cce6  mov     ebx, eax
0x18003cce8  test    eax, eax
0x18003ccea  jns     short loc_18003CCF3
0x18003ccec  mov     edx, 50h ; 'P'
0x18003ccf1  jmp     short loc_18003CCAC
0x18003ccf3  lea     rbx, [rbp+240h+FileName]
0x18003ccf7  cmp     [rbx], r14w
0x18003ccfb  jnz     short loc_18003CD04
0x18003ccfd  mov     edx, 59h ; 'Y'
0x18003cd02  jmp     short loc_18003CCA7
0x18003cd04  lea     rax, [rsp+340h+var_2F0]
0x18003cd09  mov     [rsp+340h+lpFileName], rax
0x18003cd0e  lea     rax, [rsp+340h+var_2F0]
0x18003cd13  mov     [rsp+340h+var_2F8], rax
0x18003cd18  mov     [rsp+340h+var_2F0], r14w
0x18003cd1e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003cd22  inc     r8
0x18003cd25  cmp     [rbx+r8*2], r14w
0x18003cd2a  jnz     short loc_18003CD22
0x18003cd2c  mov     rdx, rbx
0x18003cd2f  lea     rcx, [rsp+340h+lpFileName]
0x18003cd34  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18003cd39  test    al, al
0x18003cd3b  jnz     short loc_18003CD44
0x18003cd3d  mov     edx, 5Eh ; '^'
0x18003cd42  jmp     short loc_18003CD97
0x18003cd44  mov     rax, [rsp+340h+var_2F8]
0x18003cd49  mov     rcx, [rsp+340h+lpFileName]
0x18003cd4e  sub     rax, rcx
0x18003cd51  sar     rax, 1
0x18003cd54  mov     ebx, 4
0x18003cd59  cmp     rax, rbx
0x18003cd5c  jb      short loc_18003CD84
0x18003cd5e  mov     r9d, ebx
0x18003cd61  mov     rdx, rcx
0x18003cd64  lea     r8, asc_180055660; "\\\\?\\"
0x18003cd6b  movzx   eax, word ptr [rdx]
0x18003cd6e  cmp     [r8], ax
0x18003cd72  jnz     short loc_18003CD84
0x18003cd74  add     r8, 2
0x18003cd78  add     rdx, 2
0x18003cd7c  sub     r9, 1
0x18003cd80  jnz     short loc_18003CD6B
0x18003cd82  jmp     short loc_18003CDDB
0x18003cd84  lea     rcx, [rsp+340h+lpFileName]
0x18003cd89  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *)
0x18003cd8e  test    al, al
0x18003cd90  jnz     short loc_18003CDD6
0x18003cd92  mov     edx, 64h ; 'd'; void *
0x18003cd97  mov     r9d, 8007000Eh; char *
0x18003cd9d  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x18003cda4  mov     rcx, [rbp+248h]; this
0x18003cdab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cdb0  nop
0x18003cdb1  lea     rax, [rsp+340h+var_2F0]
0x18003cdb6  mov     rcx, [rsp+340h+lpFileName]; void *
0x18003cdbb  cmp     rcx, rax
0x18003cdbe  jz      short loc_18003CDCC
0x18003cdc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cdc7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003cdcc  mov     eax, 8007000Eh
0x18003cdd1  jmp     loc_18003D16A
0x18003cdd6  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x18003cddb  call    cs:__imp_GetFileAttributesW
0x18003cde1  cmp     eax, 0FFFFFFFFh
0x18003cde4  jz      loc_18003D12C
0x18003cdea  test    al, 10h
0x18003cdec  jz      loc_18003D12C
0x18003cdf2  test    rdi, rdi
0x18003cdf5  jz      short loc_18003CE30
0x18003cdf7  lea     r14, WPP_GLOBAL_Control
0x18003cdfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce05  cmp     rcx, r14
0x18003ce08  jz      short loc_18003CE62
0x18003ce0a  test    [rcx+1Ch], bl
0x18003ce0d  jz      short loc_18003CE62
0x18003ce0f  mov     edx, 0Ah
0x18003ce14  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x18003ce19  mov     r9, [rsp+340h+lpFileName]
0x18003ce1e  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18003ce25  mov     rcx, [rcx+10h]
0x18003ce29  call    WPP_SF_SS
0x18003ce2e  jmp     short loc_18003CE62
0x18003ce30  lea     r14, WPP_GLOBAL_Control
0x18003ce37  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce3e  cmp     rcx, r14
0x18003ce41  jz      short loc_18003CE62
0x18003ce43  test    [rcx+1Ch], bl
0x18003ce46  jz      short loc_18003CE62
0x18003ce48  mov     edx, 0Bh
0x18003ce4d  mov     r9, [rsp+340h+lpFileName]
0x18003ce52  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18003ce59  mov     rcx, [rcx+10h]
0x18003ce5d  call    WPP_SF_S
0x18003ce62  lea     rcx, [rbp+240h+var_2B0]; wchar_t *
0x18003ce66  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x18003ce6b  mov     ebx, eax
0x18003ce6d  test    eax, eax
0x18003ce6f  jns     short loc_18003CE7B
0x18003ce71  mov     edx, 76h ; 'v'
0x18003ce76  jmp     loc_18003D136
0x18003ce7b  lea     rax, [rsp+340h+var_2D0]
0x18003ce80  mov     [rsp+340h+lpszShortPath], rax
0x18003ce85  lea     rax, [rsp+340h+var_2D0]
0x18003ce8a  mov     [rsp+340h+var_2D8], rax
0x18003ce8f  xor     eax, eax
0x18003ce91  mov     [rsp+340h+var_2D0], ax
0x18003ce96  lea     r9, unk_18004FE4C
0x18003ce9d  test    rdi, rdi
0x18003cea0  cmovz   rdi, r9
0x18003cea4  mov     r8, [rsp+340h+lpFileName]
0x18003cea9  mov     rax, [rsp+340h+var_2F8]
0x18003ceae  cmp     r8, rax
0x18003ceb1  jz      short loc_18003CEC2
0x18003ceb3  mov     ecx, 5Ch ; '\'
0x18003ceb8  cmp     cx, [rax-2]
0x18003cebc  jnz     short loc_18003CEC2
0x18003cebe  mov     al, 1
0x18003cec0  jmp     short loc_18003CEC4
0x18003cec2  xor     al, al
0x18003cec4  lea     rcx, SubBlock; "\\"
0x18003cecb  test    al, al
0x18003cecd  cmovz   r9, rcx
0x18003ced1  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], rdi
0x18003ced6  lea     rax, [rbp+240h+var_2B0]
0x18003ceda  mov     qword ptr [rsp+340h+dwCreationDisposition], rax; int
0x18003cedf  lea     rdx, aLsLswerLsTmpLs; "%ls%lsWER.%ls.tmp%ls"
0x18003cee6  lea     rcx, [rsp+340h+lpszShortPath]
0x18003ceeb  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003cef0  mov     ebx, eax
0x18003cef2  test    eax, eax
0x18003cef4  jns     short loc_18003CF36
0x18003cef6  mov     rcx, [rbp+248h]; this
0x18003cefd  mov     r9d, eax; char *
0x18003cf00  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x18003cf07  mov     edx, 7Fh; void *
0x18003cf0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cf11  nop
0x18003cf12  lea     rax, [rsp+340h+var_2D0]
0x18003cf17  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x18003cf1c  cmp     rcx, rax
0x18003cf1f  jz      loc_18003D14D
0x18003cf25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cf2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003cf31  jmp     loc_18003D14D
0x18003cf36  bts     esi, 7
0x18003cf3a  mov     [rsp+340h+hTemplateFile], 0; hTemplateFile
0x18003cf43  mov     [rsp+340h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18003cf47  mov     [rsp+340h+dwCreationDisposition], 1; int
0x18003cf4f  mov     r9, r13; lpSecurityAttributes
0x18003cf52  mov     r8d, [rbp+240h+dwShareMode]; dwShareMode
0x18003cf56  mov     edx, 0C0000000h; dwDesiredAccess
0x18003cf5b  mov     rcx, [rsp+340h+lpszShortPath]; lpFileName
0x18003cf60  call    cs:__imp_CreateFileW
0x18003cf66  mov     rbx, rax
0x18003cf69  mov     rsi, rax
0x18003cf6c  mov     qword ptr [rbp+240h+dwShareMode], rax
0x18003cf70  lea     rcx, [rax+1]
0x18003cf74  cmp     rcx, 1
0x18003cf78  ja      short loc_18003CF99
0x18003cf7a  mov     rcx, [rbp+248h]; this
0x18003cf81  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x18003cf88  mov     edx, 8Ah; void *
0x18003cf8d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003cf92  mov     ebx, eax
0x18003cf94  jmp     loc_18003CF12
0x18003cf99  mov     rdx, rbx; void *
0x18003cf9c  mov     rcx, [rsp+340h+lpszShortPath]; wchar_t *
0x18003cfa1  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18003cfa6  mov     edi, eax
0x18003cfa8  test    eax, eax
0x18003cfaa  jns     short loc_18003D010
0x18003cfac  mov     edx, 8Eh; void *
0x18003cfb1  mov     r9d, edi; char *
0x18003cfb4  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x18003cfbb  mov     rcx, [rbp+248h]; this
0x18003cfc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cfc7  nop
0x18003cfc8  mov     rcx, rbx; hObject
0x18003cfcb  call    cs:__imp_CloseHandle
0x18003cfd1  nop
0x18003cfd2  lea     rax, [rsp+340h+var_2D0]
0x18003cfd7  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x18003cfdc  cmp     rcx, rax
0x18003cfdf  jz      short loc_18003CFEE
0x18003cfe1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cfe8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003cfed  nop
0x18003cfee  lea     rax, [rsp+340h+var_2F0]
0x18003cff3  mov     rcx, [rsp+340h+lpFileName]; void *
0x18003cff8  cmp     rcx, rax
0x18003cffb  jz      short loc_18003D009
0x18003cffd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d004  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003d009  mov     eax, edi
0x18003d00b  jmp     loc_18003D16A
0x18003d010  mov     edi, 104h
0x18003d015  mov     r8d, edi; cchBuffer
0x18003d018  mov     rdx, r12; lpszLongPath
0x18003d01b  mov     rcx, [rsp+340h+lpszShortPath]; lpszShortPath
0x18003d020  call    cs:__imp_GetLongPathNameW
0x18003d026  dec     eax
0x18003d028  cmp     eax, 102h
0x18003d02d  jbe     short loc_18003D095
0x18003d02f  call    cs:__imp_GetLastError
0x18003d035  test    eax, eax
0x18003d037  jle     short loc_18003D041
0x18003d039  movzx   eax, ax
0x18003d03c  or      eax, 80070000h
0x18003d041  mov     ecx, 80004005h
0x18003d046  test    eax, eax
0x18003d048  cmovns  eax, ecx
0x18003d04b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d052  cmp     rcx, r14
0x18003d055  jz      short loc_18003D075
0x18003d057  test    byte ptr [rcx+1Ch], 2
0x18003d05b  jz      short loc_18003D075
0x18003d05d  mov     edx, 0Ch
0x18003d062  mov     r9d, eax
0x18003d065  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18003d06c  mov     rcx, [rcx+10h]
0x18003d070  call    WPP_SF_d
0x18003d075  mov     r8, [rsp+340h+lpszShortPath]; wchar_t *
0x18003d07a  mov     rdx, rdi; unsigned __int64
0x18003d07d  mov     rcx, r12; wchar_t *
0x18003d080  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003d085  mov     edi, eax
0x18003d087  test    eax, eax
0x18003d089  jns     short loc_18003D095
0x18003d08b  mov     edx, 9Ah
0x18003d090  jmp     loc_18003CFB1
0x18003d095  test    r15, r15
0x18003d098  jz      short loc_18003D0B2
0x18003d09a  xor     esi, esi
0x18003d09c  mov     rcx, [r15]; hObject
0x18003d09f  mov     [r15], rbx
0x18003d0a2  lea     rax, [rcx+1]
0x18003d0a6  cmp     rax, 1
0x18003d0aa  jbe     short loc_18003D0B2
0x18003d0ac  call    cs:__imp_CloseHandle
0x18003d0b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0b9  cmp     rcx, r14
0x18003d0bc  jz      short loc_18003D0DD
0x18003d0be  test    byte ptr [rcx+1Ch], 4
0x18003d0c2  jz      short loc_18003D0DD
0x18003d0c4  mov     edx, 0Dh
0x18003d0c9  mov     r9, r12
0x18003d0cc  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18003d0d3  mov     rcx, [rcx+10h]
0x18003d0d7  call    WPP_SF_S
0x18003d0dc  nop
0x18003d0dd  lea     rax, [rsi+1]
0x18003d0e1  cmp     rax, 1
0x18003d0e5  jbe     short loc_18003D0F1
0x18003d0e7  mov     rcx, rsi; hObject
0x18003d0ea  call    cs:__imp_CloseHandle
0x18003d0f0  nop
0x18003d0f1  lea     rax, [rsp+340h+var_2D0]
0x18003d0f6  mov     rcx, [rsp+340h+lpszShortPath]; void *
0x18003d0fb  cmp     rcx, rax
0x18003d0fe  jz      short loc_18003D10D
  ... truncated ...
```
