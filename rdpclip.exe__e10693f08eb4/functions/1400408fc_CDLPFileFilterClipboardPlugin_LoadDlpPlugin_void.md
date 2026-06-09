# CDLPFileFilterClipboardPlugin::LoadDlpPlugin(void)

- ea: `0x1400408fc`
- end: `0x140040b97`
- name: `?LoadDlpPlugin@CDLPFileFilterClipboardPlugin@@IEAAJXZ`
- size: `667`
- prototype: `__int64 __fastcall(CDLPFileFilterClipboardPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x140040804`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x14000c7cc`
- `0x140014d64`
- `0x1400405a4`
- `0x1400408fc`
- `0x140040d38`
- `0x140040f48`
- `0x1400609c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140040962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400409ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140040962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400409ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400409d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400409d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040a3c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140040942`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140040942`

## string_xrefs

- `0x140040955`: `MpCheckAccessForRdpOperation`

## pseudocode

```c
__int64 __fastcall CDLPFileFilterClipboardPlugin::LoadDlpPlugin(HMODULE *this)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  int v4; // edx
  const unsigned __int16 *v5; // r8
  int v6; // ebp
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  char LastError; // bp
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
  v6 = ValidateExeFileDigitalSignature(lpLibFileName[0], v4, v5);
  if ( v6 )
  {
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = lpLibFileName[0];
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)&WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids,
          v20,
          (__int64)v19,
          v6);
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
    WPP_SF_DSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      (unsigned int)&WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids,
      v17,
      (__int64)v16,
      v6);
    goto LABEL_36;
  }
  LibraryW = LoadLibraryW(lpLibFileName[0]);
  this[1] = LibraryW;
  if ( !LibraryW )
  {
    LOBYTE(v6) = GetLastError();
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
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v11, v10, (__int64)"MpCheckAccessForRdpOperation", LastError);
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
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpLibFileName);
  return v2;
}

```

## disassembly

```asm
0x1400408fc  push    rbx
0x1400408fe  push    rbp
0x1400408ff  push    rsi
0x140040900  push    rdi
0x140040901  push    r14
0x140040903  sub     rsp, 50h
0x140040907  mov     rsi, rcx
0x14004090a  call    ?ReleaseDlpPlugin@CDLPFileFilterClipboardPlugin@@IEAAXXZ; CDLPFileFilterClipboardPlugin::ReleaseDlpPlugin(void)
0x14004090f  lea     rdx, [rsp+78h+lpLibFileName]
0x140040914  mov     edi, 1
0x140040919  call    ?GetDlpPluginPath@CDLPFileFilterClipboardPlugin@@IEAA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ; CDLPFileFilterClipboardPlugin::GetDlpPluginPath(void)
0x14004091e  mov     rcx, [rsp+78h+lpLibFileName]; unsigned __int16 *
0x140040923  cmp     rcx, [rsp+78h+var_40]
0x140040928  jz      loc_140040B35
0x14004092e  call    ?ValidateExeFileDigitalSignature@@YAHPEBGH0@Z; ValidateExeFileDigitalSignature(ushort const *,int,ushort const *)
0x140040933  mov     ebp, eax
0x140040935  test    eax, eax
0x140040937  jnz     loc_140040AA6
0x14004093d  mov     rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x140040942  call    cs:__imp_LoadLibraryW
0x140040948  mov     [rsi+8], rax
0x14004094c  test    rax, rax
0x14004094f  jz      loc_140040A3C
0x140040955  lea     r14, aMpcheckaccessf; "MpCheckAccessForRdpOperation"
0x14004095c  mov     rcx, rax; hModule
0x14004095f  mov     rdx, r14; lpProcName
0x140040962  call    cs:__imp_GetProcAddress
0x140040968  mov     [rsi+10h], rax
0x14004096c  lea     rbx, WPP_GLOBAL_Control
0x140040973  test    rax, rax
0x140040976  jnz     short loc_1400409BC
0x140040978  call    cs:__imp_GetLastError
0x14004097e  mov     ebp, eax
0x140040980  mov     rcx, cs:WPP_GLOBAL_Control
0x140040987  cmp     rcx, rbx
0x14004098a  jz      short loc_1400409BC
0x14004098c  test    [rcx+1Ch], dil
0x140040990  jz      short loc_1400409BC
0x140040992  cmp     byte ptr [rcx+19h], 2
0x140040996  jb      short loc_1400409BC
0x140040998  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004099d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400409a4  lea     edx, [rdi+0Eh]
0x1400409a7  mov     [rsp+78h+var_50], ebp
0x1400409ab  mov     r9d, eax
0x1400409ae  mov     [rsp+78h+var_58], r14
0x1400409b3  mov     rcx, [rcx+10h]
0x1400409b7  call    WPP_SF_Dsd
0x1400409bc  mov     rcx, [rsi+8]; hModule
0x1400409c0  lea     r14, aMpisrdpenlight; "MpIsRdpEnlightmentEnabled"
0x1400409c7  mov     rdx, r14; lpProcName
0x1400409ca  call    cs:__imp_GetProcAddress
0x1400409d0  mov     [rsi+18h], rax
0x1400409d4  test    rax, rax
0x1400409d7  jnz     short loc_140040A1F
0x1400409d9  call    cs:__imp_GetLastError
0x1400409df  mov     ebp, eax
0x1400409e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400409e8  cmp     rcx, rbx
0x1400409eb  jz      short loc_140040A1F
0x1400409ed  test    [rcx+1Ch], dil
0x1400409f1  jz      short loc_140040A1F
0x1400409f3  cmp     byte ptr [rcx+19h], 2
0x1400409f7  jb      short loc_140040A1F
0x1400409f9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400409fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140040a05  mov     edx, 10h
0x140040a0a  mov     [rsp+78h+var_50], ebp
0x140040a0e  mov     r9d, eax
0x140040a11  mov     [rsp+78h+var_58], r14
0x140040a16  mov     rcx, [rcx+10h]
0x140040a1a  call    WPP_SF_Dsd
0x140040a1f  cmp     qword ptr [rsi+10h], 0
0x140040a24  jz      loc_140040B78
0x140040a2a  cmp     qword ptr [rsi+18h], 0
0x140040a2f  jz      loc_140040B78
0x140040a35  xor     edi, edi
0x140040a37  jmp     loc_140040B80
0x140040a3c  call    cs:__imp_GetLastError
0x140040a42  mov     ebp, eax
0x140040a44  mov     rax, cs:WPP_GLOBAL_Control
0x140040a4b  lea     rbx, WPP_GLOBAL_Control
0x140040a52  cmp     rax, rbx
0x140040a55  jz      loc_140040B78
0x140040a5b  test    [rax+1Ch], dil
0x140040a5f  jz      loc_140040B78
0x140040a65  cmp     byte ptr [rax+19h], 2
0x140040a69  jb      loc_140040B78
0x140040a6f  mov     rbx, [rsp+78h+lpLibFileName]
0x140040a74  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140040a79  mov     edx, 11h
0x140040a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140040a85  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x140040a8c  mov     [rsp+78h+var_50], ebp
0x140040a90  mov     r9d, eax
0x140040a93  mov     [rsp+78h+var_58], rbx
0x140040a98  mov     rcx, [rcx+10h]
0x140040a9c  call    WPP_SF_DSD
0x140040aa1  jmp     loc_140040B78
0x140040aa6  test    ebp, ebp
0x140040aa8  jns     short loc_140040B02
0x140040aaa  mov     rax, cs:WPP_GLOBAL_Control
0x140040ab1  lea     rbx, WPP_GLOBAL_Control
0x140040ab8  cmp     rax, rbx
0x140040abb  jz      short loc_140040AFB
0x140040abd  test    [rax+1Ch], dil
0x140040ac1  jz      short loc_140040AFB
0x140040ac3  cmp     byte ptr [rax+19h], 2
0x140040ac7  jb      short loc_140040AFB
0x140040ac9  mov     rbx, [rsp+78h+lpLibFileName]
0x140040ace  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140040ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x140040ada  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x140040ae1  mov     edx, 12h
0x140040ae6  mov     [rsp+78h+var_50], ebp
0x140040aea  mov     r9d, eax
0x140040aed  mov     [rsp+78h+var_58], rbx
0x140040af2  mov     rcx, [rcx+10h]
0x140040af6  call    WPP_SF_DSD
0x140040afb  mov     edi, 8007139Fh
0x140040b00  jmp     short loc_140040B78
0x140040b02  mov     rax, cs:WPP_GLOBAL_Control
0x140040b09  lea     rbx, WPP_GLOBAL_Control
0x140040b10  cmp     rax, rbx
0x140040b13  jz      short loc_140040B78
0x140040b15  test    [rax+1Ch], dil
0x140040b19  jz      short loc_140040B78
0x140040b1b  cmp     byte ptr [rax+19h], 2
0x140040b1f  jb      short loc_140040B78
0x140040b21  mov     rbx, [rsp+78h+lpLibFileName]
0x140040b26  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140040b2b  mov     edx, 13h
0x140040b30  jmp     loc_140040A7E
0x140040b35  mov     rax, cs:WPP_GLOBAL_Control
0x140040b3c  lea     rbx, WPP_GLOBAL_Control
0x140040b43  cmp     rax, rbx
0x140040b46  jz      short loc_140040B78
0x140040b48  test    [rax+1Ch], dil
0x140040b4c  jz      short loc_140040B78
0x140040b4e  cmp     byte ptr [rax+19h], 4
0x140040b52  jb      short loc_140040B78
0x140040b54  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140040b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140040b60  lea     r8, WPP_a31a5bd54957311bf525e6b1b558f9d9_Traceguids
0x140040b67  mov     edx, 14h
0x140040b6c  mov     r9d, eax
0x140040b6f  mov     rcx, [rcx+10h]
0x140040b73  call    WPP_SF_d
0x140040b78  mov     rcx, rsi; this
0x140040b7b  call    ?ReleaseDlpPlugin@CDLPFileFilterClipboardPlugin@@IEAAXXZ; CDLPFileFilterClipboardPlugin::ReleaseDlpPlugin(void)
0x140040b80  lea     rcx, [rsp+78h+lpLibFileName]
0x140040b85  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x140040b8a  mov     eax, edi
0x140040b8c  add     rsp, 50h
0x140040b90  pop     r14
0x140040b92  pop     rdi
0x140040b93  pop     rsi
0x140040b94  pop     rbp
0x140040b95  pop     rbx
0x140040b96  retn
```
