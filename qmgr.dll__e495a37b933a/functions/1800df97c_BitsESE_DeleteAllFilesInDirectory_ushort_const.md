# BitsESE::DeleteAllFilesInDirectory(ushort const *)

- ea: `0x1800df97c`
- end: `0x1800dfcdc`
- name: `?DeleteAllFilesInDirectory@BitsESE@@YAJPEBG@Z`
- size: `864`
- prototype: `__int64 __fastcall(BitsESE *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800e0330`

## callees

- `0x18003ca78`
- `0x18008ddc8`
- `0x18008e360`
- `0x1800a1114`
- `0x1800a3420`
- `0x1800a3de8`
- `0x1800b4c10`
- `0x1800df574`
- `0x1800df97c`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfb5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfb5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc2f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800dfb51`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800dfb51`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800dfa3b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800dfa3b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800dfbd2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800dfbd2`

## pseudocode

```c
__int64 __fastcall BitsESE::DeleteAllFilesInDirectory(BitsESE *this, const unsigned __int16 *a2)
{
  const WCHAR *v3; // rcx
  HANDLE FirstFileW; // rbx
  unsigned int LastError; // eax
  signed int v6; // esi
  __int64 v7; // r8
  LPCWSTR *v8; // r9
  const WCHAR *v9; // rcx
  signed int v10; // eax
  LPCWSTR *v11; // rax
  signed int v12; // eax
  HANDLE v14[2]; // [rsp+30h] [rbp-3E8h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-3D8h] BYREF
  __int128 v16; // [rsp+48h] [rbp-3D0h]
  unsigned int v17; // [rsp+58h] [rbp-3C0h]
  int v18; // [rsp+5Ch] [rbp-3BCh]
  int v19; // [rsp+60h] [rbp-3B8h]
  void **v20; // [rsp+A0h] [rbp-378h] BYREF
  __int128 v21; // [rsp+A8h] [rbp-370h]
  signed int v22; // [rsp+B8h] [rbp-360h]
  int v23; // [rsp+BCh] [rbp-35Ch]
  int v24; // [rsp+C0h] [rbp-358h]
  void **v25; // [rsp+100h] [rbp-318h] BYREF
  __int128 v26; // [rsp+108h] [rbp-310h]
  signed int v27; // [rsp+118h] [rbp-300h]
  int v28; // [rsp+11Ch] [rbp-2FCh]
  int v29; // [rsp+120h] [rbp-2F8h]
  LPCWSTR Src[3]; // [rsp+160h] [rbp-2B8h] BYREF
  unsigned __int64 v31; // [rsp+178h] [rbp-2A0h]
  LPCWSTR lpFileName[4]; // [rsp+180h] [rbp-298h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+1A0h] [rbp-278h] BYREF

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids, this);
  std::wstring::wstring(lpFileName, this);
  std::wstring::_Append<unsigned short>(lpFileName);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v3 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v3 = lpFileName[0];
  FirstFileW = FindFirstFileW(v3, &FindFileData);
  v14[0] = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v16 = 0;
    pExceptionObject = &ComError::`vftable';
    v17 = LastError;
    v18 = 1222;
    v19 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v6 = 0;
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      std::wstring::wstring(Src, this);
      v7 = -1;
      do
        ++v7;
      while ( FindFileData.cFileName[v7] );
      std::wstring::_Append<unsigned short>(Src);
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = Src;
        if ( v31 > 7 )
          v8 = (LPCWSTR *)Src[0];
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids, v8);
      }
      v9 = (const WCHAR *)Src;
      if ( v31 > 7 )
        v9 = Src[0];
      if ( !DeleteFileW(v9) )
      {
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v11 = Src;
          if ( v31 > 7 )
            v11 = (LPCWSTR *)Src[0];
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids,
            v6,
            (__int64)v11);
        }
      }
      std::wstring::~wstring(Src);
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  if ( v6 < 0 )
  {
    v21 = 0;
    v20 = &ComError::`vftable';
    v22 = v6;
    v23 = 1244;
    v24 = 1;
    throw (ComError *)&v20;
  }
  v12 = GetLastError();
  if ( v12 != 18 )
  {
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v26 = 0;
    v25 = &ComError::`vftable';
    v27 = v12;
    v28 = 1249;
    v29 = 1;
    throw (ComError *)&v25;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(v14);
  std::wstring::~wstring(lpFileName);
  return 0;
}

```

## disassembly

```asm
0x1800df97c  mov     [rsp+arg_8], rbx
0x1800df981  mov     [rsp+arg_10], rsi
0x1800df986  push    rdi
0x1800df987  push    r12
0x1800df989  push    r15
0x1800df98b  sub     rsp, 400h
0x1800df992  mov     rax, cs:__security_cookie
0x1800df999  xor     rax, rsp
0x1800df99c  mov     [rsp+418h+var_28], rax
0x1800df9a4  mov     r15, rcx
0x1800df9a7  lea     r12, WPP_GLOBAL_Control
0x1800df9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800df9b5  cmp     rcx, r12
0x1800df9b8  jz      short loc_1800DF9D9
0x1800df9ba  test    byte ptr [rcx+1Ch], 1
0x1800df9be  jz      short loc_1800DF9D9
0x1800df9c0  mov     edx, 31h ; '1'
0x1800df9c5  mov     r9, r15
0x1800df9c8  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x1800df9cf  mov     rcx, [rcx+10h]
0x1800df9d3  call    WPP_SF_S
0x1800df9d8  nop
0x1800df9d9  mov     rdx, r15
0x1800df9dc  lea     rcx, [rsp+418h+lpFileName]
0x1800df9e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df9e9  nop
0x1800df9ea  mov     r8d, 1
0x1800df9f0  lea     rdx, asc_18011D930; "*"
0x1800df9f7  lea     rcx, [rsp+418h+lpFileName]; Src
0x1800df9ff  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800dfa04  xor     edx, edx; Val
0x1800dfa06  mov     r8d, 250h; Size
0x1800dfa0c  lea     rcx, [rsp+418h+FindFileData]; void *
0x1800dfa14  call    memset_0
0x1800dfa19  lea     rcx, [rsp+418h+lpFileName]
0x1800dfa21  cmp     [rsp+418h+var_280], 7
0x1800dfa2a  cmova   rcx, [rsp+418h+lpFileName]; lpFileName
0x1800dfa33  lea     rdx, [rsp+418h+FindFileData]; lpFindFileData
0x1800dfa3b  call    cs:__imp_FindFirstFileW
0x1800dfa41  mov     rbx, rax
0x1800dfa44  mov     [rsp+418h+var_3E8], rax
0x1800dfa49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800dfa4d  jnz     short loc_1800DFAA8
0x1800dfa4f  call    cs:__imp_GetLastError
0x1800dfa55  test    eax, eax
0x1800dfa57  jg      short loc_1800DFA61
0x1800dfa59  call    cs:__imp_GetLastError
0x1800dfa5f  jmp     short loc_1800DFA6F
0x1800dfa61  call    cs:__imp_GetLastError
0x1800dfa67  movzx   eax, ax
0x1800dfa6a  or      eax, 80070000h
0x1800dfa6f  xorps   xmm0, xmm0
0x1800dfa72  movups  [rsp+418h+var_3D0], xmm0
0x1800dfa77  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800dfa7e  mov     [rsp+418h+pExceptionObject], rcx
0x1800dfa83  mov     [rsp+418h+var_3C0], eax
0x1800dfa87  mov     [rsp+418h+var_3BC], 4C6h
0x1800dfa8f  mov     [rsp+418h+var_3B8], 1
0x1800dfa97  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800dfa9e  lea     rcx, [rsp+418h+pExceptionObject]; pExceptionObject
0x1800dfaa3  call    _CxxThrowException_0
0x1800dfaa8  xor     edi, edi
0x1800dfaaa  mov     esi, edi
0x1800dfaac  test    byte ptr [rsp+418h+FindFileData.dwFileAttributes], 10h
0x1800dfab4  jnz     loc_1800DFBC7
0x1800dfaba  mov     rdx, r15
0x1800dfabd  lea     rcx, [rsp+418h+Src]
0x1800dfac5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dfaca  nop
0x1800dfacb  lea     rax, [rsp+418h+FindFileData.cFileName]
0x1800dfad3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800dfad7  inc     r8
0x1800dfada  cmp     [rax+r8*2], di
0x1800dfadf  jnz     short loc_1800DFAD7
0x1800dfae1  lea     rdx, [rsp+418h+FindFileData.cFileName]
0x1800dfae9  lea     rcx, [rsp+418h+Src]; Src
0x1800dfaf1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800dfaf6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfafd  cmp     rcx, r12
0x1800dfb00  jz      short loc_1800DFB37
0x1800dfb02  test    byte ptr [rcx+1Ch], 1
0x1800dfb06  jz      short loc_1800DFB37
0x1800dfb08  lea     r9, [rsp+418h+Src]
0x1800dfb10  cmp     [rsp+418h+var_2A0], 7
0x1800dfb19  cmova   r9, [rsp+418h+Src]
0x1800dfb22  mov     edx, 32h ; '2'
0x1800dfb27  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x1800dfb2e  mov     rcx, [rcx+10h]
0x1800dfb32  call    WPP_SF_S
0x1800dfb37  lea     rcx, [rsp+418h+Src]
0x1800dfb3f  cmp     [rsp+418h+var_2A0], 7
0x1800dfb48  cmova   rcx, [rsp+418h+Src]; lpFileName
0x1800dfb51  call    cs:__imp_DeleteFileW
0x1800dfb57  test    eax, eax
0x1800dfb59  jnz     short loc_1800DFBBA
0x1800dfb5b  call    cs:__imp_GetLastError
0x1800dfb61  mov     esi, eax
0x1800dfb63  test    eax, eax
0x1800dfb65  jle     short loc_1800DFB70
0x1800dfb67  movzx   esi, ax
0x1800dfb6a  or      esi, 80070000h
0x1800dfb70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfb77  cmp     rcx, r12
0x1800dfb7a  jz      short loc_1800DFBBA
0x1800dfb7c  test    byte ptr [rcx+1Ch], 4
0x1800dfb80  jz      short loc_1800DFBBA
0x1800dfb82  lea     rax, [rsp+418h+Src]
0x1800dfb8a  cmp     [rsp+418h+var_2A0], 7
0x1800dfb93  cmova   rax, [rsp+418h+Src]
0x1800dfb9c  mov     edx, 33h ; '3'
0x1800dfba1  mov     [rsp+418h+var_3F8], rax
0x1800dfba6  mov     r9d, esi
0x1800dfba9  lea     r8, WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids
0x1800dfbb0  mov     rcx, [rcx+10h]
0x1800dfbb4  call    WPP_SF_DS
0x1800dfbb9  nop
0x1800dfbba  lea     rcx, [rsp+418h+Src]
0x1800dfbc2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800dfbc7  lea     rdx, [rsp+418h+FindFileData]; lpFindFileData
0x1800dfbcf  mov     rcx, rbx; hFindFile
0x1800dfbd2  call    cs:__imp_FindNextFileW
0x1800dfbd8  test    eax, eax
0x1800dfbda  jnz     loc_1800DFAAC
0x1800dfbe0  test    esi, esi
0x1800dfbe2  jns     short loc_1800DFC2F
0x1800dfbe4  xorps   xmm0, xmm0
0x1800dfbe7  movups  [rsp+418h+var_370], xmm0
0x1800dfbef  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800dfbf6  mov     [rsp+418h+var_378], rcx
0x1800dfbfe  mov     [rsp+418h+var_360], esi
0x1800dfc05  mov     [rsp+418h+var_35C], 4DCh
0x1800dfc10  mov     [rsp+418h+var_358], 1
0x1800dfc1b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800dfc22  lea     rcx, [rsp+418h+var_378]; pExceptionObject
0x1800dfc2a  call    _CxxThrowException_0
0x1800dfc2f  call    cs:__imp_GetLastError
0x1800dfc35  cmp     eax, 12h
0x1800dfc38  jz      short loc_1800DFC92
0x1800dfc3a  test    eax, eax
0x1800dfc3c  jle     short loc_1800DFC46
0x1800dfc3e  movzx   eax, ax
0x1800dfc41  or      eax, 80070000h
0x1800dfc46  xorps   xmm0, xmm0
0x1800dfc49  movups  [rsp+418h+var_310], xmm0
0x1800dfc51  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800dfc58  mov     [rsp+418h+var_318], rcx
0x1800dfc60  mov     [rsp+418h+var_300], eax
0x1800dfc67  mov     [rsp+418h+var_2FC], 4E1h
0x1800dfc72  mov     [rsp+418h+var_2F8], 1
0x1800dfc7d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800dfc84  lea     rcx, [rsp+418h+var_318]; pExceptionObject
0x1800dfc8c  call    _CxxThrowException_0
0x1800dfc92  lea     rcx, [rsp+418h+var_3E8]
0x1800dfc97  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800dfc9c  nop
0x1800dfc9d  lea     rcx, [rsp+418h+lpFileName]
0x1800dfca5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800dfcaa  xor     eax, eax
0x1800dfcac  jmp     short loc_1800DFCB2
0x1800dfcae  mov     eax, dword ptr [rsp+418h+var_3E8]
0x1800dfcb2  mov     rcx, [rsp+418h+var_28]
0x1800dfcba  xor     rcx, rsp; StackCookie
0x1800dfcbd  call    __security_check_cookie
0x1800dfcc2  lea     r11, [rsp+418h+var_18]
0x1800dfcca  mov     rbx, [r11+28h]
0x1800dfcce  mov     rsi, [r11+30h]
0x1800dfcd2  mov     rsp, r11
0x1800dfcd5  pop     r15
0x1800dfcd7  pop     r12
0x1800dfcd9  pop     rdi
0x1800dfcda  retn
```
