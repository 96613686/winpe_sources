# EndpointDlp::Common::MappedDriveToNetworkSharePath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1801f8054`
- end: `0x1801f82b8`
- name: `?MappedDriveToNetworkSharePath@Common@EndpointDlp@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18003cc38`

## callees

- `0x1800058a4`
- `0x1800225f4`
- `0x1800301a0`
- `0x180034420`
- `0x1800969d0`
- `0x18009d4ac`
- `0x1800c79a4`
- `0x1800ca044`
- `0x180103fec`
- `0x18010cb40`
- `0x1801645f4`
- `0x1801f8054`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801f8136`
- `KERNEL32!GetLastError` at `0x1801f8218`
- `KERNEL32!GetLastError` at `0x1801f8136`
- `KERNEL32!GetLastError` at `0x1801f8218`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1801f812a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1801f8190`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1801f812a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1801f8190`
- `KERNEL32!CloseHandle` at `0x1801f828b`
- `KERNEL32!CloseHandle` at `0x1801f828b`

## string_xrefs

- `0x1801f823a`: `Common::MappedDriveToNetworkSharePath: Failed to get final path name for file`
- `0x1801f80dc`: `Common::MappedDriveToNetworkSharePath: Failed to open file`
- `0x1801f8158`: `Common::MappedDriveToNetworkSharePath: Failed to get final path name for file with result as zero`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EndpointDlp::Common::MappedDriveToNetworkSharePath(__int64 a1, void **a2)
{
  signed int File; // edi
  struct EndpointDlp::TraceLoggingProvider *v4; // rax
  int v5; // r8d
  int v6; // r9d
  _DWORD *v7; // rcx
  const wchar_t *v8; // rax
  __int16 *v9; // rdx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v11; // edi
  signed int LastError; // eax
  struct EndpointDlp::TraceLoggingProvider *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  signed int v17; // eax
  unsigned int v18; // edi
  struct EndpointDlp::TraceLoggingProvider *v19; // rax
  int v20; // r8d
  int v21; // r9d
  _DWORD *v22; // rcx
  struct _SECURITY_ATTRIBUTES *v24; // [rsp+28h] [rbp-51h]
  BOOL v25; // [rsp+40h] [rbp-39h] BYREF
  const wchar_t *v26; // [rsp+48h] [rbp-31h] BYREF
  signed __int64 v27; // [rsp+50h] [rbp-29h]
  char v28[16]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v29[32]; // [rsp+70h] [rbp-9h] BYREF
  HANDLE hFile; // [rsp+90h] [rbp+17h] BYREF
  LPWSTR lpszFilePath[2]; // [rsp+98h] [rbp+1Fh] BYREF
  __int64 v32; // [rsp+A8h] [rbp+2Fh]

  v26 = (const wchar_t *)a1;
  hFile = (HANDLE)-1LL;
  if ( (unsigned __int64)a2[3] > 7 )
    a2 = (void **)*a2;
  LODWORD(v24) = 3;
  File = CommonUtil::MpCreateFile((CommonUtil *)&hFile, a2, (const wchar_t *)0x100080, 1u, 0, v24, 0x80u, 0, v25);
  if ( File < 0 )
  {
    v4 = EndpointDlp::TraceLoggingProvider::Instance();
    v7 = *(_DWORD **)v4;
    if ( **(_DWORD **)v4 <= 2u )
    {
LABEL_7:
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 7;
      *(_WORD *)a1 = 0;
      goto LABEL_23;
    }
    v8 = L"Common::MappedDriveToNetworkSharePath: Failed to open file";
    v9 = &word_1802C6716;
LABEL_6:
    v26 = v8;
    v25 = File;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      (_DWORD)v7,
      (_DWORD)v9,
      v5,
      v6,
      (__int64)&v25,
      (__int64)&v26);
    goto LABEL_7;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
  v11 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    File = LastError;
    if ( LastError > 0 )
      File = (unsigned __int16)LastError | 0x80070000;
    v13 = EndpointDlp::TraceLoggingProvider::Instance();
    v7 = *(_DWORD **)v13;
    if ( **(_DWORD **)v13 <= 2u )
      goto LABEL_7;
    v8 = L"Common::MappedDriveToNetworkSharePath: Failed to get final path name for file with result as zero";
    v9 = &word_1802C6776;
    goto LABEL_6;
  }
  *(_OWORD *)lpszFilePath = 0;
  v32 = 0;
  std::vector<wchar_t>::vector<wchar_t>(lpszFilePath, FinalPathNameByHandleW);
  if ( GetFinalPathNameByHandleW(hFile, lpszFilePath[0], v11, 0) )
  {
    v26 = lpszFilePath[0];
    v27 = lpszFilePath[1] - lpszFilePath[0];
    v14 = std::_Traits_find<std::char_traits<wchar_t>>(lpszFilePath[0], v27, 0, (unsigned int)L"\\\\?\\UNC\\", 8);
    if ( v14 == -1 )
    {
      std::wstring::wstring(a1, &v26);
    }
    else
    {
      v15 = std::wstring_view::substr(&v26, v28, v14 + 8);
      v16 = std::wstring::wstring(v29, v15);
      std::operator+<wchar_t>(a1, L"\\\\", v16);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v29);
    }
  }
  else
  {
    v17 = GetLastError();
    v18 = v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    v19 = EndpointDlp::TraceLoggingProvider::Instance();
    v22 = *(_DWORD **)v19;
    if ( **(_DWORD **)v19 > 2u )
    {
      v26 = L"Common::MappedDriveToNetworkSharePath: Failed to get final path name for file";
      v25 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (_DWORD)v22,
        (unsigned int)&word_1802C67A6,
        v20,
        v21,
        (__int64)&v25,
        (__int64)&v26);
    }
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 7;
    *(_WORD *)a1 = 0;
  }
  std::vector<wchar_t>::_Tidy(lpszFilePath);
LABEL_23:
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  return a1;
}

```

## disassembly

```asm
0x1801f8054  mov     [rsp-8+arg_10], rbx
0x1801f8059  mov     [rsp-8+arg_18], rsi
0x1801f805e  push    rbp
0x1801f805f  push    rdi
0x1801f8060  push    r15
0x1801f8062  lea     rbp, [rsp-47h]
0x1801f8067  sub     rsp, 0C0h
0x1801f806e  mov     rax, cs:__security_cookie
0x1801f8075  xor     rax, rsp
0x1801f8078  mov     [rbp+57h+var_20], rax
0x1801f807c  mov     rbx, rcx
0x1801f807f  mov     [rbp+57h+var_88], rcx
0x1801f8083  xor     esi, esi
0x1801f8085  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x1801f808d  lea     r15d, [rsi+7]
0x1801f8091  cmp     [rdx+18h], r15
0x1801f8095  jbe     short loc_1801F809A
0x1801f8097  mov     rdx, [rdx]; void **
0x1801f809a  mov     [rsp+0D0h+var_98], sil; char
0x1801f809f  mov     [rsp+0D0h+var_A0], 80h; unsigned int
0x1801f80a7  mov     dword ptr [rsp+0D0h+var_A8], 3; struct _SECURITY_ATTRIBUTES *
0x1801f80af  mov     qword ptr [rsp+0D0h+var_B0], rsi; unsigned int
0x1801f80b4  mov     r9d, 1; unsigned int
0x1801f80ba  mov     r8d, 100080h; wchar_t *
0x1801f80c0  lea     rcx, [rbp+57h+hFile]; this
0x1801f80c4  call    ?MpCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KK_N@Z; CommonUtil::MpCreateFile(void * *,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,bool)
0x1801f80c9  mov     edi, eax
0x1801f80cb  test    eax, eax
0x1801f80cd  jns     short loc_1801F811E
0x1801f80cf  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1801f80d4  mov     rcx, [rax]
0x1801f80d7  cmp     dword ptr [rcx], 2
0x1801f80da  jbe     short loc_1801F8108
0x1801f80dc  lea     rax, aCommonMappeddr_1; "Common::MappedDriveToNetworkSharePath: "...
0x1801f80e3  lea     rdx, word_1802C6716
0x1801f80ea  mov     [rbp+57h+var_88], rax
0x1801f80ee  lea     rax, [rbp+57h+var_88]
0x1801f80f2  mov     [rsp+0D0h+var_A8], rax
0x1801f80f7  lea     rax, [rbp+57h+var_90]
0x1801f80fb  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1801f8100  mov     [rbp+57h+var_90], edi
0x1801f8103  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1801f8108  xorps   xmm0, xmm0
0x1801f810b  movups  xmmword ptr [rbx], xmm0
0x1801f810e  mov     [rbx+10h], rsi
0x1801f8112  mov     [rbx+18h], r15
0x1801f8116  mov     [rbx], si
0x1801f8119  jmp     loc_1801F8281
0x1801f811e  xor     r9d, r9d; dwFlags
0x1801f8121  xor     r8d, r8d; cchFilePath
0x1801f8124  xor     edx, edx; lpszFilePath
0x1801f8126  mov     rcx, [rbp+57h+hFile]; hFile
0x1801f812a  call    cs:__imp_GetFinalPathNameByHandleW
0x1801f8130  mov     edi, eax
0x1801f8132  test    eax, eax
0x1801f8134  jnz     short loc_1801F8168
0x1801f8136  call    cs:__imp_GetLastError
0x1801f813c  mov     edi, eax
0x1801f813e  test    eax, eax
0x1801f8140  jle     short loc_1801F814B
0x1801f8142  movzx   edi, ax
0x1801f8145  or      edi, 80070000h
0x1801f814b  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1801f8150  mov     rcx, [rax]
0x1801f8153  cmp     dword ptr [rcx], 2
0x1801f8156  jbe     short loc_1801F8108
0x1801f8158  lea     rax, aCommonMappeddr_0; "Common::MappedDriveToNetworkSharePath: "...
0x1801f815f  lea     rdx, word_1802C6776
0x1801f8166  jmp     short loc_1801F80EA
0x1801f8168  xorps   xmm0, xmm0
0x1801f816b  xor     eax, eax
0x1801f816d  movups  xmmword ptr [rbp+57h+lpszFilePath], xmm0
0x1801f8171  mov     [rbp+57h+var_28], rax
0x1801f8175  mov     rdx, rdi
0x1801f8178  lea     rcx, [rbp+57h+lpszFilePath]
0x1801f817c  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x1801f8181  nop
0x1801f8182  xor     r9d, r9d; dwFlags
0x1801f8185  mov     r8d, edi; cchFilePath
0x1801f8188  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x1801f818c  mov     rcx, [rbp+57h+hFile]; hFile
0x1801f8190  call    cs:__imp_GetFinalPathNameByHandleW
0x1801f8196  test    eax, eax
0x1801f8198  jz      short loc_1801F8218
0x1801f819a  mov     rcx, [rbp+57h+lpszFilePath]
0x1801f819e  mov     rdx, [rbp+57h+lpszFilePath+8]
0x1801f81a2  sub     rdx, rcx
0x1801f81a5  sar     rdx, 1
0x1801f81a8  mov     [rbp+57h+var_88], rcx
0x1801f81ac  mov     [rbp+57h+var_80], rdx
0x1801f81b0  mov     qword ptr [rsp+0D0h+var_B0], 8
0x1801f81b9  lea     r9, aUnc_1; "\\\\?\\UNC\\"
0x1801f81c0  xor     r8d, r8d
0x1801f81c3  call    ??$_Traits_find@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K101@Z; std::_Traits_find<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1801f81c8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801f81cc  jz      short loc_1801F820A
0x1801f81ce  lea     r8, [rax+8]
0x1801f81d2  lea     rdx, [rbp+57h+var_70]
0x1801f81d6  lea     rcx, [rbp+57h+var_88]
0x1801f81da  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1801f81df  mov     rdx, rax
0x1801f81e2  lea     rcx, [rbp+57h+var_60]
0x1801f81e6  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x1801f81eb  nop
0x1801f81ec  mov     r8, rax
0x1801f81ef  lea     rdx, asc_18025EF0C; "\\\\"
0x1801f81f6  mov     rcx, rbx
0x1801f81f9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x1801f81fe  nop
0x1801f81ff  lea     rcx, [rbp+57h+var_60]; void *
0x1801f8203  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801f8208  jmp     short loc_1801F8277
0x1801f820a  lea     rdx, [rbp+57h+var_88]
0x1801f820e  mov     rcx, rbx
0x1801f8211  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x1801f8216  jmp     short loc_1801F8277
0x1801f8218  call    cs:__imp_GetLastError
0x1801f821e  mov     edi, eax
0x1801f8220  test    eax, eax
0x1801f8222  jle     short loc_1801F822D
0x1801f8224  movzx   edi, ax
0x1801f8227  or      edi, 80070000h
0x1801f822d  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1801f8232  mov     rcx, [rax]
0x1801f8235  cmp     dword ptr [rcx], 2
0x1801f8238  jbe     short loc_1801F8266
0x1801f823a  lea     rax, aCommonMappeddr; "Common::MappedDriveToNetworkSharePath: "...
0x1801f8241  mov     [rbp+57h+var_88], rax
0x1801f8245  mov     [rbp+57h+var_90], edi
0x1801f8248  lea     rax, [rbp+57h+var_88]
0x1801f824c  mov     [rsp+0D0h+var_A8], rax
0x1801f8251  lea     rax, [rbp+57h+var_90]
0x1801f8255  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1801f825a  lea     rdx, word_1802C67A6
0x1801f8261  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1801f8266  xorps   xmm0, xmm0
0x1801f8269  movups  xmmword ptr [rbx], xmm0
0x1801f826c  mov     [rbx+10h], rsi
0x1801f8270  mov     [rbx+18h], r15
0x1801f8274  mov     [rbx], si
0x1801f8277  lea     rcx, [rbp+57h+lpszFilePath]
0x1801f827b  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x1801f8280  nop
0x1801f8281  mov     rcx, [rbp+57h+hFile]; hObject
0x1801f8285  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801f8289  jz      short loc_1801F8291
0x1801f828b  call    cs:__imp_CloseHandle
0x1801f8291  mov     rax, rbx
0x1801f8294  mov     rcx, [rbp+57h+var_20]
0x1801f8298  xor     rcx, rsp; StackCookie
0x1801f829b  call    __security_check_cookie
0x1801f82a0  lea     r11, [rsp+0D0h+var_10]
0x1801f82a8  mov     rbx, [r11+30h]
0x1801f82ac  mov     rsi, [r11+38h]
0x1801f82b0  mov     rsp, r11
0x1801f82b3  pop     r15
0x1801f82b5  pop     rdi
0x1801f82b6  pop     rbp
0x1801f82b7  retn
```
