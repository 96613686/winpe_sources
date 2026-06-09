# RealtimeProtection::DlpQuarantineEngine::QuarantineFile(RealtimeProtection::_DlpQuarantineItem &,bool)

- ea: `0x180094038`
- end: `0x1800943dc`
- name: `?QuarantineFile@DlpQuarantineEngine@RealtimeProtection@@AEAA_NAEAU_DlpQuarantineItem@2@_N@Z`
- size: `932`
- prototype: `bool(RealtimeProtection::DlpQuarantineEngine *__hidden this, struct RealtimeProtection::_DlpQuarantineItem *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009358c`

## callees

- `0x180034420`
- `0x180080030`
- `0x18009351c`
- `0x180094038`
- `0x1800943dc`
- `0x1800943fc`
- `0x180104f64`
- `0x180105f50`
- `0x18010cb40`
- `0x1801a4090`
- `0x1801a5598`
- `0x180200ca8`

## import_xrefs

- `KERNEL32!Sleep` at `0x18009430a`
- `KERNEL32!Sleep` at `0x18009430a`
- `KERNEL32!DeleteFileW` at `0x18009424d`
- `KERNEL32!DeleteFileW` at `0x18009429f`
- `KERNEL32!DeleteFileW` at `0x18009431e`
- `KERNEL32!DeleteFileW` at `0x180094345`
- `KERNEL32!DeleteFileW` at `0x18009424d`
- `KERNEL32!DeleteFileW` at `0x18009429f`
- `KERNEL32!DeleteFileW` at `0x18009431e`
- `KERNEL32!DeleteFileW` at `0x180094345`
- `KERNEL32!CopyFileW` at `0x1800940e7`
- `KERNEL32!CopyFileW` at `0x1800940e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall RealtimeProtection::DlpQuarantineEngine::QuarantineFile(
        RealtimeProtection::DlpQuarantineEngine *this,
        struct RealtimeProtection::_DlpQuarantineItem *a2,
        unsigned __int8 a3)
{
  unsigned int v3; // r14d
  char v5; // bl
  const wchar_t *v6; // rdx
  char v7; // r12
  LPCWSTR *v8; // rcx
  const WCHAR *v9; // rdx
  const WCHAR *v10; // rcx
  char LastFailure; // al
  const wchar_t *v12; // rsi
  LPCWSTR *v13; // rcx
  const wchar_t *v14; // rsi
  RealtimeProtection::DlpQuarantineEngine *v15; // rcx
  const wchar_t *v16; // rax
  LPCWSTR *v17; // r9
  PVOID *v18; // rcx
  __int64 v19; // rdx
  LPCWSTR *v20; // r9
  const WCHAR *v21; // rcx
  bool v22; // al
  _QWORD *v23; // rcx
  int v24; // edx
  const WCHAR *v25; // rcx
  BOOL v26; // r12d
  int v27; // r15d
  char v28; // al
  LPCWSTR *v29; // r8
  const WCHAR *v30; // rcx
  const WCHAR *v31; // rcx
  LPCWSTR *v32; // r9
  LPCWSTR lpExistingFileName[3]; // [rsp+50h] [rbp-11h] BYREF
  unsigned __int64 v36; // [rsp+68h] [rbp+7h]
  LPCWSTR lpNewFileName[3]; // [rsp+70h] [rbp+Fh] BYREF
  unsigned __int64 v38; // [rsp+88h] [rbp+27h]

  v3 = a3;
  v5 = 0;
  std::filesystem::path::operator std::wstring((char *)a2 + 224, lpExistingFileName);
  std::filesystem::path::operator std::wstring((char *)a2 + 64 * (v3 ^ 1LL) + 272, lpNewFileName);
  v7 = *((_BYTE *)a2 + 53);
  v8 = lpNewFileName;
  if ( v38 > 7 )
    v8 = (LPCWSTR *)lpNewFileName[0];
  if ( (unsigned int)CommonUtil::UtilIsFileExists((CommonUtil *)v8, v6) != -2147024894 )
    goto LABEL_68;
  v9 = (const WCHAR *)lpNewFileName;
  if ( v38 > 7 )
    v9 = lpNewFileName[0];
  v10 = (const WCHAR *)lpExistingFileName;
  if ( v36 > 7 )
    v10 = lpExistingFileName[0];
  if ( !CopyFileW(v10, v9, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastFailure = HrGetLastFailure();
      v12 = L"primary";
      if ( !(_BYTE)v3 )
        v12 = (const wchar_t *)L"default";
      v13 = lpNewFileName;
      if ( v38 > 7 )
        v13 = (LPCWSTR *)lpNewFileName[0];
      WPP_SF_SSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v13, (__int64)v12, LastFailure);
    }
    goto LABEL_68;
  }
  v14 = L"primary";
  v15 = (RealtimeProtection::DlpQuarantineEngine *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v16 = L"primary";
    if ( !a3 )
      v16 = (const wchar_t *)L"default";
    v17 = lpExistingFileName;
    if ( v36 > 7 )
      LODWORD(v17) = lpExistingFileName[0];
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
      (_DWORD)v17,
      (__int64)v16);
  }
  if ( v7 )
  {
    if ( RealtimeProtection::DlpQuarantineEngine::TryCopyOverride(v15, a2) )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v19 = 65;
LABEL_64:
        v32 = lpExistingFileName;
        if ( v36 > 7 )
          v32 = (LPCWSTR *)lpExistingFileName[0];
        WPP_SF_S(v18[2], v19, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v32);
        goto LABEL_67;
      }
      goto LABEL_67;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = lpExistingFileName;
      if ( v36 > 7 )
        v20 = (LPCWSTR *)lpExistingFileName[0];
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v20);
    }
    v21 = (const WCHAR *)lpNewFileName;
    if ( v38 > 7 )
      v21 = lpNewFileName[0];
    v22 = DeleteFileW(v21);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v24 = 67;
LABEL_38:
      if ( !a3 )
        v14 = (const wchar_t *)L"default";
      WPP_SF_Sd(v23[2], v24, (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, (_DWORD)v14, v22);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  v25 = (const WCHAR *)lpExistingFileName;
  if ( v36 > 7 )
    v25 = lpExistingFileName[0];
  v26 = DeleteFileW(v25);
  v27 = 0;
  if ( v26 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  while ( 1 )
  {
    v28 = HrGetLastFailure();
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v29 = lpExistingFileName;
      if ( v36 > 7 )
        v29 = (LPCWSTR *)lpExistingFileName[0];
      WPP_SF_dSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v29, v28);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( ++v27 == 5 )
      break;
    Sleep(0xAu);
    v30 = (const WCHAR *)lpExistingFileName;
    if ( v36 > 7 )
      v30 = lpExistingFileName[0];
    v26 = DeleteFileW(v30);
    if ( v26 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      break;
    }
  }
  if ( v26 )
  {
LABEL_61:
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
    {
      v19 = 69;
      goto LABEL_64;
    }
LABEL_67:
    v5 = 1;
    goto LABEL_68;
  }
  v31 = (const WCHAR *)lpNewFileName;
  if ( v38 > 7 )
    v31 = lpNewFileName[0];
  v22 = DeleteFileW(v31);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v24 = 70;
    goto LABEL_38;
  }
LABEL_68:
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpNewFileName);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpExistingFileName);
  return v5;
}

```

## disassembly

```asm
0x180094038  mov     rax, rsp
0x18009403b  mov     [rax+8], rbx
0x18009403f  mov     [rax+18h], rsi
0x180094043  mov     [rax+20h], rdi
0x180094047  push    rbp
0x180094048  push    r12
0x18009404a  push    r13
0x18009404c  push    r14
0x18009404e  push    r15
0x180094050  lea     rbp, [rax-5Fh]
0x180094054  sub     rsp, 90h
0x18009405b  mov     rax, cs:__security_cookie
0x180094062  xor     rax, rsp
0x180094065  mov     [rbp+57h+var_28], rax
0x180094069  movzx   r14d, r8b
0x18009406d  mov     [rbp+57h+var_70], r14b
0x180094071  mov     r15, rdx
0x180094074  xor     ebx, ebx
0x180094076  lea     rcx, [rdx+0E0h]
0x18009407d  lea     rdx, [rbp+57h+lpExistingFileName]
0x180094081  call    ??Bpath@filesystem@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::filesystem::path::operator std::wstring(void)
0x180094086  nop
0x180094087  mov     eax, r14d
0x18009408a  xor     rax, 1
0x18009408e  shl     rax, 6
0x180094092  lea     rcx, [r15+110h]
0x180094099  add     rcx, rax
0x18009409c  lea     rdx, [rbp+57h+lpNewFileName]
0x1800940a0  call    ??Bpath@filesystem@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::filesystem::path::operator std::wstring(void)
0x1800940a5  nop
0x1800940a6  mov     r12b, [r15+35h]
0x1800940aa  lea     rcx, [rbp+57h+lpNewFileName]
0x1800940ae  cmp     [rbp+57h+var_30], 7
0x1800940b3  cmova   rcx, [rbp+57h+lpNewFileName]; this
0x1800940b8  call    ?UtilIsFileExists@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilIsFileExists(wchar_t const *)
0x1800940bd  cmp     eax, 80070002h
0x1800940c2  jnz     loc_18009439A
0x1800940c8  lea     rdx, [rbp+57h+lpNewFileName]
0x1800940cc  cmp     [rbp+57h+var_30], 7
0x1800940d1  cmova   rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x1800940d6  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800940da  cmp     [rbp+57h+var_50], 7
0x1800940df  cmova   rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800940e4  xor     r8d, r8d; bFailIfExists
0x1800940e7  call    cs:__imp_CopyFileW
0x1800940ed  test    eax, eax
0x1800940ef  jnz     loc_180094179
0x1800940f5  lea     rdi, WPP_GLOBAL_Control
0x1800940fc  mov     rax, cs:WPP_GLOBAL_Control
0x180094103  cmp     rax, rdi
0x180094106  jz      loc_18009439A
0x18009410c  test    byte ptr [rax+1Ch], 2
0x180094110  jz      loc_18009439A
0x180094116  call    HrGetLastFailure
0x18009411b  lea     r13, aDefault; "default"
0x180094122  lea     rsi, aPrimary; "primary"
0x180094129  test    r14b, r14b
0x18009412c  cmovz   rsi, r13
0x180094130  lea     rcx, [rbp+57h+lpNewFileName]
0x180094134  cmp     [rbp+57h+var_30], 7
0x180094139  cmova   rcx, [rbp+57h+lpNewFileName]
0x18009413e  lea     r9, [rbp+57h+lpExistingFileName]
0x180094142  cmp     [rbp+57h+var_50], 7
0x180094147  cmova   r9, [rbp+57h+lpExistingFileName]
0x18009414c  lea     edx, [rbx+3Fh]
0x18009414f  mov     dword ptr [rsp+0B0h+var_80], eax; char
0x180094153  mov     qword ptr [rsp+0B0h+var_88], rsi; __int64
0x180094158  mov     [rsp+0B0h+var_90], rcx; __int64
0x18009415d  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180094164  mov     rcx, cs:WPP_GLOBAL_Control
0x18009416b  mov     rcx, [rcx+10h]; LoggerHandle
0x18009416f  call    WPP_SF_SSSD
0x180094174  jmp     loc_18009439A
0x180094179  lea     rdi, WPP_GLOBAL_Control
0x180094180  lea     r13, aDefault; "default"
0x180094187  lea     rsi, aPrimary; "primary"
0x18009418e  lea     r14, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180094195  mov     rcx, cs:WPP_GLOBAL_Control
0x18009419c  cmp     rcx, rdi
0x18009419f  jz      short loc_1800941D5
0x1800941a1  test    byte ptr [rcx+1Ch], 4
0x1800941a5  jz      short loc_1800941D5
0x1800941a7  mov     rax, rsi
0x1800941aa  cmp     [rbp+57h+var_70], bl
0x1800941ad  cmovz   rax, r13
0x1800941b1  lea     r9, [rbp+57h+lpExistingFileName]
0x1800941b5  cmp     [rbp+57h+var_50], 7
0x1800941ba  cmova   r9, [rbp+57h+lpExistingFileName]
0x1800941bf  mov     edx, 40h ; '@'
0x1800941c4  mov     [rsp+0B0h+var_90], rax
0x1800941c9  mov     r8, r14
0x1800941cc  mov     rcx, [rcx+10h]
0x1800941d0  call    WPP_SF_SS
0x1800941d5  test    r12b, r12b
0x1800941d8  jz      loc_180094291
0x1800941de  mov     rdx, r15; struct RealtimeProtection::_DlpQuarantineItem *
0x1800941e1  call    ?TryCopyOverride@DlpQuarantineEngine@RealtimeProtection@@AEAA_NAEAU_DlpQuarantineItem@2@@Z; RealtimeProtection::DlpQuarantineEngine::TryCopyOverride(RealtimeProtection::_DlpQuarantineItem &)
0x1800941e6  test    al, al
0x1800941e8  jz      short loc_18009420E
0x1800941ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800941f1  cmp     rcx, rdi
0x1800941f4  jz      loc_180094398
0x1800941fa  test    byte ptr [rcx+1Ch], 4
0x1800941fe  jz      loc_180094398
0x180094204  mov     edx, 41h ; 'A'
0x180094209  jmp     loc_18009437E
0x18009420e  mov     rcx, cs:WPP_GLOBAL_Control
0x180094215  cmp     rcx, rdi
0x180094218  jz      short loc_18009423F
0x18009421a  test    byte ptr [rcx+1Ch], 1
0x18009421e  jz      short loc_18009423F
0x180094220  lea     r9, [rbp+57h+lpExistingFileName]
0x180094224  cmp     [rbp+57h+var_50], 7
0x180094229  cmova   r9, [rbp+57h+lpExistingFileName]
0x18009422e  mov     edx, 42h ; 'B'
0x180094233  mov     r8, r14
0x180094236  mov     rcx, [rcx+10h]
0x18009423a  call    WPP_SF_S
0x18009423f  lea     rcx, [rbp+57h+lpNewFileName]
0x180094243  cmp     [rbp+57h+var_30], 7
0x180094248  cmova   rcx, [rbp+57h+lpNewFileName]; lpFileName
0x18009424d  call    cs:__imp_DeleteFileW
0x180094253  mov     rcx, cs:WPP_GLOBAL_Control
0x18009425a  cmp     rcx, rdi
0x18009425d  jz      loc_18009439A
0x180094263  test    byte ptr [rcx+1Ch], 4
0x180094267  jz      loc_18009439A
0x18009426d  mov     edx, 43h ; 'C'
0x180094272  cmp     [rbp+57h+var_70], bl
0x180094275  cmovz   rsi, r13
0x180094279  mov     dword ptr [rsp+0B0h+var_90], eax
0x18009427d  mov     r9, rsi
0x180094280  mov     r8, r14
0x180094283  mov     rcx, [rcx+10h]
0x180094287  call    WPP_SF_Sd
0x18009428c  jmp     loc_18009439A
0x180094291  lea     rcx, [rbp+57h+lpExistingFileName]
0x180094295  cmp     [rbp+57h+var_50], 7
0x18009429a  cmova   rcx, [rbp+57h+lpExistingFileName]; lpFileName
0x18009429f  call    cs:__imp_DeleteFileW
0x1800942a5  mov     r12d, eax
0x1800942a8  mov     r15d, ebx
0x1800942ab  test    eax, eax
0x1800942ad  jnz     loc_180094367
0x1800942b3  call    HrGetLastFailure
0x1800942b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800942bf  cmp     rcx, rdi
0x1800942c2  jz      short loc_1800942FC
0x1800942c4  test    byte ptr [rcx+1Ch], 1
0x1800942c8  jz      short loc_1800942FC
0x1800942ca  lea     r8, [rbp+57h+lpExistingFileName]
0x1800942ce  cmp     [rbp+57h+var_50], 7
0x1800942d3  cmova   r8, [rbp+57h+lpExistingFileName]
0x1800942d8  mov     edx, 44h ; 'D'
0x1800942dd  mov     dword ptr [rsp+0B0h+var_88], eax; char
0x1800942e1  mov     [rsp+0B0h+var_90], r8; __int64
0x1800942e6  mov     r9d, r15d
0x1800942e9  mov     r8, r14
0x1800942ec  mov     rcx, [rcx+10h]; LoggerHandle
0x1800942f0  call    WPP_SF_dSd
0x1800942f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800942fc  inc     r15d
0x1800942ff  cmp     r15d, 5
0x180094303  jz      short loc_180094332
0x180094305  mov     ecx, 0Ah; dwMilliseconds
0x18009430a  call    cs:__imp_Sleep
0x180094310  lea     rcx, [rbp+57h+lpExistingFileName]
0x180094314  cmp     [rbp+57h+var_50], 7
0x180094319  cmova   rcx, [rbp+57h+lpExistingFileName]; lpFileName
0x18009431e  call    cs:__imp_DeleteFileW
0x180094324  mov     r12d, eax
0x180094327  test    eax, eax
0x180094329  jz      short loc_1800942B3
0x18009432b  mov     rcx, cs:WPP_GLOBAL_Control
0x180094332  test    r12d, r12d
0x180094335  jnz     short loc_18009436E
0x180094337  lea     rcx, [rbp+57h+lpNewFileName]
0x18009433b  cmp     [rbp+57h+var_30], 7
0x180094340  cmova   rcx, [rbp+57h+lpNewFileName]; lpFileName
0x180094345  call    cs:__imp_DeleteFileW
0x18009434b  mov     rcx, cs:WPP_GLOBAL_Control
0x180094352  cmp     rcx, rdi
0x180094355  jz      short loc_18009439A
0x180094357  test    byte ptr [rcx+1Ch], 4
0x18009435b  jz      short loc_18009439A
0x18009435d  lea     edx, [r12+46h]
0x180094362  jmp     loc_180094272
0x180094367  mov     rcx, cs:WPP_GLOBAL_Control
0x18009436e  cmp     rcx, rdi
0x180094371  jz      short loc_180094398
0x180094373  test    byte ptr [rcx+1Ch], 4
0x180094377  jz      short loc_180094398
0x180094379  mov     edx, 45h ; 'E'
0x18009437e  lea     r9, [rbp+57h+lpExistingFileName]
0x180094382  cmp     [rbp+57h+var_50], 7
0x180094387  cmova   r9, [rbp+57h+lpExistingFileName]
0x18009438c  mov     r8, r14
0x18009438f  mov     rcx, [rcx+10h]
0x180094393  call    WPP_SF_S
0x180094398  mov     bl, 1
0x18009439a  lea     rcx, [rbp+57h+lpNewFileName]; void *
0x18009439e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800943a3  nop
0x1800943a4  lea     rcx, [rbp+57h+lpExistingFileName]; void *
0x1800943a8  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800943ad  mov     al, bl
0x1800943af  mov     rcx, [rbp+57h+var_28]
0x1800943b3  xor     rcx, rsp; StackCookie
0x1800943b6  call    __security_check_cookie
0x1800943bb  lea     r11, [rsp+0B0h+var_20]
0x1800943c3  mov     rbx, [r11+30h]
0x1800943c7  mov     rsi, [r11+40h]
0x1800943cb  mov     rdi, [r11+48h]
0x1800943cf  mov     rsp, r11
0x1800943d2  pop     r15
0x1800943d4  pop     r14
0x1800943d6  pop     r13
0x1800943d8  pop     r12
0x1800943da  pop     rbp
0x1800943db  retn
```
