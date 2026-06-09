# PackageCopier::CopyFileW(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002b17c`
- end: `0x18002b409`
- name: `?CopyFileW@PackageCopier@@QEAAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `653`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18002b410`

## callees

- `0x1800015b4`
- `0x18000164c`
- `0x1800017ec`
- `0x180001878`
- `0x180002614`
- `0x180004d68`
- `0x18001b388`
- `0x180021200`
- `0x18002b17c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b26a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b26a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b380`
- `api-ms-win-core-file-l2-1-0!CopyFile2` at `0x18002b208`
- `api-ms-win-core-file-l2-1-0!CopyFile2` at `0x18002b208`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002b1a5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002b227`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002b1a5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002b227`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002b24e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002b24e`

## pseudocode

```c
__int64 __fastcall PackageCopier::CopyFileW(const WCHAR *a1, const WCHAR *a2, __int64 a3)
{
  const WCHAR *v4; // rbx
  const WCHAR *v5; // rcx
  int v6; // r9d
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  HRESULT v10; // esi
  const WCHAR *v11; // rcx
  DWORD FileAttributesW; // eax
  DWORD v13; // eax
  const WCHAR *v14; // rcx
  signed int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // r9d
  unsigned int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r8
  int v25; // r9d
  unsigned int v26; // eax
  signed int LastError; // eax
  unsigned int v28; // ebx
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // r9d
  unsigned int v32; // eax
  int v33; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  const WCHAR *v35; // [rsp+60h] [rbp+20h] BYREF
  char v36; // [rsp+68h] [rbp+28h] BYREF
  char v37; // [rsp+78h] [rbp+38h] BYREF

  v35 = a1;
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) < 8u )
    v5 = a2;
  else
    v5 = *(const WCHAR **)a2;
  if ( (GetFileAttributesW(v5) & 0x10) != 0 )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 3u )
    {
      if ( *((_QWORD *)v4 + 3) >= 8u )
        v4 = *(const WCHAR **)v4;
      v35 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        g_hProvTraceProvider,
        (unsigned int)&dword_18004164C,
        0,
        v6,
        (__int64)&v35);
    }
    return 0;
  }
  else
  {
    if ( *(_QWORD *)(a3 + 24) < 8u )
      v8 = (const WCHAR *)a3;
    else
      v8 = *(const WCHAR **)a3;
    if ( *((_QWORD *)v4 + 3) < 8u )
      v9 = v4;
    else
      v9 = *(const WCHAR **)v4;
    v10 = CopyFile2(v9, v8, 0);
    if ( v10 < 0 )
    {
      if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
      {
        LODWORD(v35) = v10;
        v21 = std::wstring::c_str(a3);
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v36, v21);
        v22 = std::wstring::c_str(v4);
        v23 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v37, v22);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)&byte_1800415FF,
          v24,
          v25,
          v23,
          v24,
          (__int64)&v35);
      }
      v26 = wil::verify_hresult<long>((unsigned int)v10);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
        (const char *)v26,
        v33);
    }
    if ( *(_QWORD *)(a3 + 24) < 8u )
      v11 = (const WCHAR *)a3;
    else
      v11 = *(const WCHAR **)a3;
    FileAttributesW = GetFileAttributesW(v11);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      v28 = LastError;
      if ( LastError > 0 )
        v28 = (unsigned __int16)LastError | 0x80070000;
      if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
      {
        LODWORD(v35) = v28;
        v29 = std::wstring::c_str(a3);
        v30 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v36, v29);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v31,
          (unsigned int)&word_1800415BE,
          0,
          v31,
          v30,
          (__int64)&v35);
      }
      v32 = wil::verify_hresult<long>(v28);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF5,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
        (const char *)v32,
        v33);
    }
    if ( (FileAttributesW & 1) != 0 )
    {
      v13 = FileAttributesW & 0xFFFFFFFE;
      v14 = *(_QWORD *)(a3 + 24) < 8u ? (const WCHAR *)a3 : *(const WCHAR **)a3;
      if ( !SetFileAttributesW(v14, v13) )
      {
        v15 = GetLastError();
        v16 = v15;
        if ( v15 > 0 )
          v16 = (unsigned __int16)v15 | 0x80070000;
        if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
        {
          LODWORD(v35) = v16;
          v17 = std::wstring::c_str(a3);
          v18 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v36, v17);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v19,
            (unsigned int)byte_18004157D,
            0,
            v19,
            v18,
            (__int64)&v35);
        }
        v20 = wil::verify_hresult<long>(v16);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
          (const char *)v20,
          v33);
      }
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18002b17c  mov     [rsp-18h+arg_10], rbx
0x18002b181  mov     [rsp-18h+arg_0], rcx
0x18002b186  push    rbp
0x18002b187  push    rsi
0x18002b188  push    rdi
0x18002b189  mov     rbp, rsp
0x18002b18c  sub     rsp, 40h
0x18002b190  cmp     qword ptr [rdx+18h], 8
0x18002b195  mov     rdi, r8
0x18002b198  mov     rbx, rdx
0x18002b19b  jb      short loc_18002B1A2
0x18002b19d  mov     rcx, [rdx]
0x18002b1a0  jmp     short loc_18002B1A5
0x18002b1a2  mov     rcx, rbx; lpFileName
0x18002b1a5  call    cs:__imp_GetFileAttributesW
0x18002b1ab  test    al, 10h
0x18002b1ad  jz      short loc_18002B1E7
0x18002b1af  mov     rcx, cs:g_hProvTraceProvider
0x18002b1b6  mov     eax, [rcx]
0x18002b1b8  cmp     eax, 3
0x18002b1bb  jbe     short loc_18002B1E3
0x18002b1bd  cmp     qword ptr [rbx+18h], 8
0x18002b1c2  jb      short loc_18002B1C7
0x18002b1c4  mov     rbx, [rbx]
0x18002b1c7  lea     rax, [rbp+arg_0]
0x18002b1cb  mov     [rbp+arg_0], rbx
0x18002b1cf  xor     r8d, r8d
0x18002b1d2  mov     qword ptr [rsp+40h+var_20], rax
0x18002b1d7  lea     rdx, dword_18004164C
0x18002b1de  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002b1e3  xor     eax, eax
0x18002b1e5  jmp     short loc_18002B25D
0x18002b1e7  cmp     qword ptr [rdi+18h], 8
0x18002b1ec  jb      short loc_18002B1F3
0x18002b1ee  mov     rdx, [rdi]
0x18002b1f1  jmp     short loc_18002B1F6
0x18002b1f3  mov     rdx, rdi; pwszNewFileName
0x18002b1f6  cmp     qword ptr [rbx+18h], 8
0x18002b1fb  jb      short loc_18002B202
0x18002b1fd  mov     rcx, [rbx]
0x18002b200  jmp     short loc_18002B205
0x18002b202  mov     rcx, rbx; pwszExistingFileName
0x18002b205  xor     r8d, r8d; pExtendedParameters
0x18002b208  call    cs:__imp_CopyFile2
0x18002b20e  mov     esi, eax
0x18002b210  test    eax, eax
0x18002b212  js      loc_18002B2F3
0x18002b218  cmp     qword ptr [rdi+18h], 8
0x18002b21d  jb      short loc_18002B224
0x18002b21f  mov     rcx, [rdi]
0x18002b222  jmp     short loc_18002B227
0x18002b224  mov     rcx, rdi; lpFileName
0x18002b227  call    cs:__imp_GetFileAttributesW
0x18002b22d  cmp     eax, 0FFFFFFFFh
0x18002b230  jz      loc_18002B380
0x18002b236  test    al, 1
0x18002b238  jz      short loc_18002B258
0x18002b23a  and     eax, 0FFFFFFFEh
0x18002b23d  cmp     qword ptr [rdi+18h], 8
0x18002b242  jb      short loc_18002B249
0x18002b244  mov     rcx, [rdi]
0x18002b247  jmp     short loc_18002B24C
0x18002b249  mov     rcx, rdi; lpFileName
0x18002b24c  mov     edx, eax; dwFileAttributes
0x18002b24e  call    cs:__imp_SetFileAttributesW
0x18002b254  test    eax, eax
0x18002b256  jz      short loc_18002B26A
0x18002b258  mov     eax, 1
0x18002b25d  mov     rbx, [rsp+40h+arg_10]
0x18002b262  add     rsp, 40h
0x18002b266  pop     rdi
0x18002b267  pop     rsi
0x18002b268  pop     rbp
0x18002b269  retn
0x18002b26a  call    cs:__imp_GetLastError
0x18002b270  mov     ebx, eax
0x18002b272  test    eax, eax
0x18002b274  jle     short loc_18002B27F
0x18002b276  movzx   ebx, ax
0x18002b279  or      ebx, 80070000h
0x18002b27f  mov     r9, cs:g_hProvTraceProvider
0x18002b286  mov     eax, [r9]
0x18002b289  cmp     eax, 2
0x18002b28c  jbe     short loc_18002B2D3
0x18002b28e  xor     edx, edx
0x18002b290  mov     rcx, r9
0x18002b293  call    _tlgKeywordOn
0x18002b298  test    al, al
0x18002b29a  jz      short loc_18002B2D3
0x18002b29c  mov     rcx, rdi
0x18002b29f  mov     dword ptr [rbp+arg_0], ebx
0x18002b2a2  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002b2a7  mov     rdx, rax
0x18002b2aa  lea     rcx, [rbp+arg_8]
0x18002b2ae  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18002b2b3  lea     rcx, [rbp+arg_0]
0x18002b2b7  xor     r8d, r8d
0x18002b2ba  mov     [rsp+40h+var_18], rcx
0x18002b2bf  lea     rdx, byte_18004157D
0x18002b2c6  mov     rcx, r9
0x18002b2c9  mov     qword ptr [rsp+40h+var_20], rax; int
0x18002b2ce  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002b2d3  mov     ecx, ebx
0x18002b2d5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002b2da  mov     rcx, [rbp+18h]; this
0x18002b2de  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002b2e5  mov     r9d, eax; char *
0x18002b2e8  mov     edx, 103h; void *
0x18002b2ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b2f3  mov     r9, cs:g_hProvTraceProvider
0x18002b2fa  mov     ecx, [r9]
0x18002b2fd  cmp     ecx, 2
0x18002b300  jbe     short loc_18002B360
0x18002b302  xor     edx, edx
0x18002b304  mov     rcx, r9
0x18002b307  call    _tlgKeywordOn
0x18002b30c  test    al, al
0x18002b30e  jz      short loc_18002B360
0x18002b310  mov     rcx, rdi
0x18002b313  mov     dword ptr [rbp+arg_0], esi
0x18002b316  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002b31b  mov     rdx, rax
0x18002b31e  lea     rcx, [rbp+arg_8]
0x18002b322  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18002b327  mov     rcx, rbx
0x18002b32a  mov     r8, rax
0x18002b32d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002b332  mov     rdx, rax
0x18002b335  lea     rcx, [rbp+arg_18]
0x18002b339  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18002b33e  lea     rcx, [rbp+arg_0]
0x18002b342  mov     [rsp+40h+var_10], rcx
0x18002b347  lea     rdx, byte_1800415FF
0x18002b34e  mov     [rsp+40h+var_18], r8
0x18002b353  mov     rcx, r9
0x18002b356  mov     qword ptr [rsp+40h+var_20], rax; int
0x18002b35b  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002b360  mov     ecx, esi
0x18002b362  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002b367  mov     rcx, [rbp+18h]; this
0x18002b36b  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002b372  mov     r9d, eax; char *
0x18002b375  mov     edx, 0E8h; void *
0x18002b37a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b380  call    cs:__imp_GetLastError
0x18002b386  mov     ebx, eax
0x18002b388  test    eax, eax
0x18002b38a  jle     short loc_18002B395
0x18002b38c  movzx   ebx, ax
0x18002b38f  or      ebx, 80070000h
0x18002b395  mov     r9, cs:g_hProvTraceProvider
0x18002b39c  mov     eax, [r9]
0x18002b39f  cmp     eax, 2
0x18002b3a2  jbe     short loc_18002B3E9
0x18002b3a4  xor     edx, edx
0x18002b3a6  mov     rcx, r9
0x18002b3a9  call    _tlgKeywordOn
0x18002b3ae  test    al, al
0x18002b3b0  jz      short loc_18002B3E9
0x18002b3b2  mov     rcx, rdi
0x18002b3b5  mov     dword ptr [rbp+arg_0], ebx
0x18002b3b8  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002b3bd  mov     rdx, rax
0x18002b3c0  lea     rcx, [rbp+arg_8]
0x18002b3c4  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18002b3c9  lea     rcx, [rbp+arg_0]
0x18002b3cd  xor     r8d, r8d
0x18002b3d0  mov     [rsp+40h+var_18], rcx
0x18002b3d5  lea     rdx, word_1800415BE
0x18002b3dc  mov     rcx, r9
0x18002b3df  mov     qword ptr [rsp+40h+var_20], rax; int
0x18002b3e4  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002b3e9  mov     ecx, ebx
0x18002b3eb  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002b3f0  mov     rcx, [rbp+18h]; this
0x18002b3f4  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002b3fb  mov     r9d, eax; char *
0x18002b3fe  mov     edx, 0F5h; void *
0x18002b403  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
