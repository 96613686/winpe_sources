# Dlp::Utils::GetVolumeGuidName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180084878`
- end: `0x180084c41`
- name: `?GetVolumeGuidName@Utils@Dlp@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@@Z`
- size: `969`
- prototype: `__int64 __fastcall(wchar_t *, void *)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path`

## callers

- `0x180084c44`

## callees

- `0x180029590`
- `0x18002c150`
- `0x180034420`
- `0x180038450`
- `0x18004b3bc`
- `0x1800542d0`
- `0x180080030`
- `0x1800809d0`
- `0x180083360`
- `0x180084878`
- `0x18009ce28`
- `0x18009fb1c`
- `0x1800b88dc`
- `0x18010cb40`
- `0x18010cc74`
- `0x18014d888`
- `0x18014f420`
- `0x18023a310`

## import_xrefs

- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180084a55`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180084a55`
- `KERNEL32!GetVolumePathNameW` at `0x180084951`
- `KERNEL32!GetVolumePathNameW` at `0x180084951`
- `KERNEL32!GetLastError` at `0x180084961`
- `KERNEL32!GetLastError` at `0x180084a5f`
- `KERNEL32!GetLastError` at `0x180084961`
- `KERNEL32!GetLastError` at `0x180084a5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Dlp::Utils::GetVolumeGuidName(wchar_t *a1, void *a2)
{
  wchar_t *v3; // rdi
  wchar_t *v4; // r9
  wchar_t *v5; // r9
  const WCHAR *v6; // rcx
  signed int LastError; // eax
  unsigned int v8; // r14d
  int v10; // eax
  unsigned int v11; // edi
  signed int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  int StringHashAsGuid; // edi
  void *v19; // rax
  _BYTE v20[32]; // [rsp+30h] [rbp-4B8h] BYREF
  __int128 v21; // [rsp+50h] [rbp-498h] BYREF
  _BYTE v22[48]; // [rsp+60h] [rbp-488h] BYREF
  wchar_t szVolumePathName[264]; // [rsp+90h] [rbp-458h] BYREF
  WCHAR szVolumeName[264]; // [rsp+2A0h] [rbp-248h] BYREF

  v3 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v4 = a1;
    if ( *((_QWORD *)a1 + 3) > 7u )
      v4 = *(wchar_t **)a1;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids, v4);
  }
  std::wstring::_Eos(a2, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v5 = v3;
    if ( *((_QWORD *)v3 + 3) > 7u )
      v5 = *(wchar_t **)v3;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids, v5);
  }
  memset(szVolumePathName, 0, 0x208u);
  v6 = v3;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v6 = *(const WCHAR **)v3;
  if ( !GetVolumePathNameW(v6, szVolumePathName, 0x104u) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids, v8);
    if ( v8 != -2147024895 )
      return v8;
    if ( *((_QWORD *)v3 + 3) > 7u )
      v3 = *(wchar_t **)v3;
    v10 = StringCchCopyW(szVolumePathName, 0x104u, v3);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids,
          (unsigned int)v10);
      return v11;
    }
    goto LABEL_41;
  }
  std::wstring::operator std::wstring_view(v3, &v21);
  if ( (unsigned __int8)Dlp::Utils::IsNetworkPath(&v21) )
  {
LABEL_41:
    v16 = -1;
    do
      ++v16;
    while ( szVolumePathName[v16] );
    v17 = 2 * v16 - 2;
    if ( v17 >= 0x208 )
      _report_rangecheckfailure(szVolumePathName);
    *(wchar_t *)((char *)szVolumePathName + v17) = 0;
    v21 = 0;
    std::wstring::wstring(v20, szVolumePathName);
    StringHashAsGuid = Dlp::Utils::GetStringHashAsGuid(v20, &v21);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v20);
    if ( StringHashAsGuid >= 0 )
    {
      RealtimeProtection::FileUniqueId::GuidToVolumeGuidString(v22, &v21);
      if ( v22[32] )
      {
        v19 = (void *)std::optional<std::wstring>::value(v22);
        std::wstring::operator=(a2, v19);
        std::optional<std::wstring>::~optional<std::wstring>(v22);
        return 0;
      }
      else
      {
        std::optional<std::wstring>::~optional<std::wstring>(v22);
        return 2147500037LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids,
          (unsigned int)StringHashAsGuid);
      return (unsigned int)StringHashAsGuid;
    }
  }
  memset(szVolumeName, 0, 0x208u);
  if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v14 = -1;
    do
      ++v14;
    while ( szVolumeName[v14] );
    v15 = 2 * v14 - 2;
    if ( v15 >= 0x208 )
      _report_rangecheckfailure(szVolumeName);
    *(WCHAR *)((char *)szVolumeName + v15) = 0;
    std::wstring::assign(a2, szVolumeName);
    return 0;
  }
  else
  {
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids, v13);
    return v13;
  }
}

```

## disassembly

```asm
0x180084878  mov     [rsp+arg_10], rbx
0x18008487d  push    rsi
0x18008487e  push    rdi
0x18008487f  push    r12
0x180084881  push    r14
0x180084883  push    r15
0x180084885  sub     rsp, 4C0h
0x18008488c  mov     rax, cs:__security_cookie
0x180084893  xor     rax, rsp
0x180084896  mov     [rsp+4E8h+var_38], rax
0x18008489e  mov     r15, rdx
0x1800848a1  mov     rdi, rcx
0x1800848a4  lea     rsi, WPP_GLOBAL_Control
0x1800848ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800848b2  cmp     rcx, rsi
0x1800848b5  jz      short loc_1800848DF
0x1800848b7  test    byte ptr [rcx+1Ch], 4
0x1800848bb  jz      short loc_1800848DF
0x1800848bd  mov     r9, rdi
0x1800848c0  cmp     qword ptr [rdi+18h], 7
0x1800848c5  jbe     short loc_1800848CA
0x1800848c7  mov     r9, [rdi]
0x1800848ca  mov     edx, 15h
0x1800848cf  lea     r8, WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids
0x1800848d6  mov     rcx, [rcx+10h]
0x1800848da  call    WPP_SF_S
0x1800848df  xor     edx, edx
0x1800848e1  mov     rcx, r15
0x1800848e4  call    ?_Eos@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800848e9  nop
0x1800848ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800848f1  cmp     rcx, rsi
0x1800848f4  jz      short loc_18008491E
0x1800848f6  test    byte ptr [rcx+1Ch], 4
0x1800848fa  jz      short loc_18008491E
0x1800848fc  mov     r9, rdi
0x1800848ff  cmp     qword ptr [rdi+18h], 7
0x180084904  jbe     short loc_180084909
0x180084906  mov     r9, [rdi]
0x180084909  mov     edx, 16h
0x18008490e  lea     r8, WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids
0x180084915  mov     rcx, [rcx+10h]
0x180084919  call    WPP_SF_S
0x18008491e  mov     r12d, 208h
0x180084924  mov     r8d, r12d; Size
0x180084927  xor     edx, edx; Val
0x180084929  lea     rcx, [rsp+4E8h+szVolumePathName]; void *
0x180084931  call    memset
0x180084936  mov     rcx, rdi
0x180084939  cmp     qword ptr [rdi+18h], 7
0x18008493e  jbe     short loc_180084943
0x180084940  mov     rcx, [rdi]; lpszFileName
0x180084943  mov     r8d, 104h; cchBufferLength
0x180084949  lea     rdx, [rsp+4E8h+szVolumePathName]; lpszVolumePathName
0x180084951  call    cs:__imp_GetVolumePathNameW
0x180084957  xor     ebx, ebx
0x180084959  test    eax, eax
0x18008495b  jnz     loc_180084A0E
0x180084961  call    cs:__imp_GetLastError
0x180084967  mov     r14d, eax
0x18008496a  test    eax, eax
0x18008496c  jle     short loc_180084979
0x18008496e  movzx   r14d, ax
0x180084972  or      r14d, 80070000h
0x180084979  mov     rcx, cs:WPP_GLOBAL_Control
0x180084980  cmp     rcx, rsi
0x180084983  jz      short loc_1800849A3
0x180084985  test    byte ptr [rcx+1Ch], 1
0x180084989  jz      short loc_1800849A3
0x18008498b  mov     edx, 17h
0x180084990  mov     r9d, r14d
0x180084993  lea     r8, WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids
0x18008499a  mov     rcx, [rcx+10h]
0x18008499e  call    WPP_SF_d
0x1800849a3  cmp     r14d, 80070001h
0x1800849aa  jz      short loc_1800849B4
0x1800849ac  mov     eax, r14d
0x1800849af  jmp     loc_180084BD9
0x1800849b4  cmp     qword ptr [rdi+18h], 7
0x1800849b9  jbe     short loc_1800849BE
0x1800849bb  mov     rdi, [rdi]
0x1800849be  mov     r8, rdi; wchar_t *
0x1800849c1  mov     edx, 104h; unsigned __int64
0x1800849c6  lea     rcx, [rsp+4E8h+szVolumePathName]; wchar_t *
0x1800849ce  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800849d3  mov     edi, eax
0x1800849d5  test    eax, eax
0x1800849d7  jns     loc_180084AEB
0x1800849dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800849e4  cmp     rcx, rsi
0x1800849e7  jz      short loc_180084A07
0x1800849e9  test    byte ptr [rcx+1Ch], 1
0x1800849ed  jz      short loc_180084A07
0x1800849ef  mov     edx, 18h
0x1800849f4  mov     r9d, eax
0x1800849f7  lea     r8, WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids
0x1800849fe  mov     rcx, [rcx+10h]
0x180084a02  call    WPP_SF_d
0x180084a07  mov     eax, edi
0x180084a09  jmp     loc_180084BD9
0x180084a0e  lea     rdx, [rsp+4E8h+var_498]
0x180084a13  mov     rcx, rdi
0x180084a16  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180084a1b  lea     rcx, [rsp+4E8h+var_498]
0x180084a20  call    ?IsNetworkPath@Utils@Dlp@@YA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Dlp::Utils::IsNetworkPath(std::wstring_view const &)
0x180084a25  test    al, al
0x180084a27  jnz     loc_180084AEB
0x180084a2d  mov     r8, r12; Size
0x180084a30  xor     edx, edx; Val
0x180084a32  lea     rcx, [rsp+4E8h+szVolumeName]; void *
0x180084a3a  call    memset
0x180084a3f  mov     r8d, 104h; cchBufferLength
0x180084a45  lea     rdx, [rsp+4E8h+szVolumeName]; lpszVolumeName
0x180084a4d  lea     rcx, [rsp+4E8h+szVolumePathName]; lpszVolumeMountPoint
0x180084a55  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180084a5b  test    eax, eax
0x180084a5d  jnz     short loc_180084AA5
0x180084a5f  call    cs:__imp_GetLastError
0x180084a65  mov     edi, eax
0x180084a67  test    eax, eax
0x180084a69  jle     short loc_180084A74
0x180084a6b  movzx   edi, ax
0x180084a6e  or      edi, 80070000h
0x180084a74  mov     rcx, cs:WPP_GLOBAL_Control
0x180084a7b  cmp     rcx, rsi
0x180084a7e  jz      short loc_180084A9E
0x180084a80  test    byte ptr [rcx+1Ch], 1
0x180084a84  jz      short loc_180084A9E
0x180084a86  mov     edx, 1Ah
0x180084a8b  mov     r9d, edi
0x180084a8e  lea     r8, WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids
0x180084a95  mov     rcx, [rcx+10h]
0x180084a99  call    WPP_SF_d
0x180084a9e  mov     eax, edi
0x180084aa0  jmp     loc_180084BD9
0x180084aa5  lea     rcx, [rsp+4E8h+szVolumeName]
0x180084aad  or      rax, 0FFFFFFFFFFFFFFFFh
0x180084ab1  inc     rax
0x180084ab4  cmp     [rcx+rax*2], bx
0x180084ab8  jnz     short loc_180084AB1
0x180084aba  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180084ac2  cmp     rax, r12
0x180084ac5  jnb     short loc_180084AE5
0x180084ac7  mov     [rsp+rax+4E8h+szVolumeName], bx
0x180084acf  lea     rdx, [rsp+4E8h+szVolumeName]; Src
0x180084ad7  mov     rcx, r15; void *
0x180084ada  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180084adf  nop
0x180084ae0  jmp     loc_180084BD7
0x180084ae5  call    __report_rangecheckfailure
0x180084aeb  lea     rcx, [rsp+4E8h+szVolumePathName]
0x180084af3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180084af7  inc     rax
0x180084afa  cmp     [rcx+rax*2], bx
0x180084afe  jnz     short loc_180084AF7
0x180084b00  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180084b08  cmp     rax, r12
0x180084b0b  jnb     loc_180084C3A
0x180084b11  mov     [rsp+rax+4E8h+szVolumePathName], bx
0x180084b19  xorps   xmm0, xmm0
0x180084b1c  movups  [rsp+4E8h+var_498], xmm0
0x180084b21  lea     rdx, [rsp+4E8h+szVolumePathName]
0x180084b29  lea     rcx, [rsp+4E8h+var_4B8]
0x180084b2e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180084b33  nop
0x180084b34  lea     rdx, [rsp+4E8h+var_498]
0x180084b39  lea     rcx, [rsp+4E8h+var_4B8]
0x180084b3e  call    ?GetStringHashAsGuid@Utils@Dlp@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; Dlp::Utils::GetStringHashAsGuid(std::wstring const &,_GUID &)
0x180084b43  mov     edi, eax
0x180084b45  lea     rcx, [rsp+4E8h+var_4B8]; void *
0x180084b4a  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180084b4f  test    edi, edi
0x180084b51  jns     short loc_180084B81
0x180084b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180084b5a  cmp     rcx, rsi
0x180084b5d  jz      short loc_180084B7D
0x180084b5f  test    byte ptr [rcx+1Ch], 1
0x180084b63  jz      short loc_180084B7D
0x180084b65  mov     edx, 19h
0x180084b6a  mov     r9d, edi
0x180084b6d  lea     r8, WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids
0x180084b74  mov     rcx, [rcx+10h]
0x180084b78  call    WPP_SF_d
0x180084b7d  mov     eax, edi
0x180084b7f  jmp     short loc_180084BD9
0x180084b81  lea     rdx, [rsp+4E8h+var_498]
0x180084b86  lea     rcx, [rsp+4E8h+var_488]
0x180084b8b  call    ?GuidToVolumeGuidString@FileUniqueId@RealtimeProtection@@SA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBU_GUID@@@Z; RealtimeProtection::FileUniqueId::GuidToVolumeGuidString(_GUID const &)
0x180084b90  nop
0x180084b91  cmp     [rsp+4E8h+var_468], bl
0x180084b98  jnz     short loc_180084BAB
0x180084b9a  lea     rcx, [rsp+4E8h+var_488]
0x180084b9f  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x180084ba4  mov     eax, 80004005h
0x180084ba9  jmp     short loc_180084BD9
0x180084bab  lea     rcx, [rsp+4E8h+var_488]
0x180084bb0  call    ?value@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180084bb5  mov     rdx, rax; Src
0x180084bb8  mov     rcx, r15; void *
0x180084bbb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180084bc0  nop
0x180084bc1  lea     rcx, [rsp+4E8h+var_488]
0x180084bc6  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x180084bcb  xor     eax, eax
0x180084bcd  jmp     short loc_180084BD9
0x180084bcf  mov     edi, [rsp+4E8h+var_4C8]
0x180084bd3  test    edi, edi
0x180084bd5  js      short loc_180084C05
0x180084bd7  xor     eax, eax
0x180084bd9  mov     rcx, [rsp+4E8h+var_38]
0x180084be1  xor     rcx, rsp; StackCookie
0x180084be4  call    __security_check_cookie
0x180084be9  mov     rbx, [rsp+4E8h+arg_10]
0x180084bf1  add     rsp, 4C0h
0x180084bf8  pop     r15
0x180084bfa  pop     r14
0x180084bfc  pop     r12
0x180084bfe  pop     rdi
0x180084bff  pop     rsi
0x180084c00  retn
0x180084c01  mov     edi, [rsp+4E8h+var_4C8]
0x180084c05  lea     rsi, WPP_GLOBAL_Control
0x180084c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180084c13  cmp     rcx, rsi
0x180084c16  jz      short loc_180084C36
0x180084c18  test    byte ptr [rcx+1Ch], 1
0x180084c1c  jz      short loc_180084C36
0x180084c1e  mov     edx, 1Bh
0x180084c23  mov     r9d, edi
0x180084c26  lea     r8, WPP_dbe499f1c74b3fbd586c5b5708b5dda0_Traceguids
0x180084c2d  mov     rcx, [rcx+10h]
0x180084c31  call    WPP_SF_d
0x180084c36  mov     eax, edi
0x180084c38  jmp     short loc_180084BD9
0x180084c3a  call    __report_rangecheckfailure
```
