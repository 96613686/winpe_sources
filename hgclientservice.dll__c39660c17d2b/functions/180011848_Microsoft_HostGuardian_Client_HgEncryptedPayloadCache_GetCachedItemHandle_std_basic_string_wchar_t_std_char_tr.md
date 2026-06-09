# Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::GetCachedItemHandle(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,wchar_t const * const,uint,uint,uint,uint,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180011848`
- end: `0x180011a21`
- name: `?GetCachedItemHandle@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_WIIIIAEAV78@@Z`
- size: `473`
- prototype: `HANDLE *__fastcall(_QWORD *, HANDLE *, _QWORD *, __int64, DWORD dwDesiredAccess, DWORD dwShareMode, DWORD, DWORD dwFlagsAndAttributes, WCHAR *lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180011a28`
- `0x180011cc0`

## callees

- `0x180008760`
- `0x180011274`
- `0x180011848`
- `0x180012018`
- `0x180014c74`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800119ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800119ca`

## string_xrefs

- `0x1800119ef`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`
- `0x180011a0c`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`

## pseudocode

```c
HANDLE *__fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::GetCachedItemHandle(
        _QWORD *a1,
        HANDLE *a2,
        _QWORD *a3,
        __int64 a4,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        DWORD a7,
        DWORD dwFlagsAndAttributes,
        WCHAR *lpFileName)
{
  __int64 v9; // rdi
  _QWORD *v10; // r14
  LPCWSTR v13; // rbx
  WCHAR *v14; // rsi
  WCHAR *v15; // rcx
  bool v16; // cc
  LPCWSTR v17; // r8
  const WCHAR *v18; // rdi
  char *i; // rcx
  _QWORD *v20; // rax
  wchar_t *v21; // rcx
  int v22; // eax
  int v23; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-78h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  wchar_t *v28; // [rsp+A0h] [rbp+8h] BYREF

  v9 = -1;
  v10 = a3;
  do
    ++v9;
  while ( *(_WORD *)(a4 + 2 * v9) );
  v13 = lpFileName;
  v14 = (WCHAR *)(v9 + a1[3] + a3[2] + 3LL);
  v15 = (WCHAR *)*((_QWORD *)lpFileName + 2);
  if ( v15 < v14 )
  {
    if ( (unsigned __int64)((char *)v14 - (char *)v15) > *((_QWORD *)lpFileName + 3) - (_QWORD)v15 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(lpFileName);
    }
    else
    {
      v16 = *((_QWORD *)lpFileName + 3) <= 7u;
      *((_QWORD *)lpFileName + 2) = v14;
      if ( v16 )
        v17 = v13;
      else
        v17 = *(LPCWSTR *)v13;
      v18 = &v17[(_QWORD)v15];
      if ( v14 != v15 )
      {
        for ( i = (char *)((char *)v14 - (char *)v15); i; --i )
          *v18++ = 0;
      }
      v17[(_QWORD)v14] = 0;
    }
  }
  v16 = v10[3] <= 7u;
  v28 = 0;
  lpFileName = v14;
  if ( !v16 )
    v10 = (_QWORD *)*v10;
  v20 = a1 + 1;
  if ( a1[4] > 7u )
    v20 = (_QWORD *)*v20;
  if ( *((_QWORD *)v13 + 3) <= 7u )
    v21 = (wchar_t *)v13;
  else
    v21 = *(wchar_t **)v13;
  v22 = StringCchPrintfExW(v21, *((_QWORD *)v13 + 2), &v28, (unsigned __int64 *)&lpFileName, 0, L"%s\\%s", v20, v10);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
      (const char *)(unsigned int)v22,
      dwCreationDisposition);
  Microsoft::HostGuardian::Client::Utilities::CreatePath(v13);
  v23 = StringCchPrintfExW(v28, (unsigned __int64)lpFileName, 0, 0, 0, L"\\%s");
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
      (const char *)(unsigned int)v23,
      dwCreationDispositiona);
  if ( *((_QWORD *)v13 + 3) > 7u )
    v13 = *(LPCWSTR *)v13;
  *a2 = CreateFileW(v13, dwDesiredAccess, dwShareMode, 0, a7, dwFlagsAndAttributes, 0);
  return a2;
}

```

## disassembly

```asm
0x180011848  push    rbx
0x18001184a  push    rbp
0x18001184b  push    rsi
0x18001184c  push    rdi
0x18001184d  push    r12
0x18001184f  push    r13
0x180011851  push    r14
0x180011853  push    r15
0x180011855  sub     rsp, 58h
0x180011859  xor     r13d, r13d
0x18001185c  mov     r12, r9
0x18001185f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011863  mov     r14, r8
0x180011866  mov     r15, rdx
0x180011869  mov     rbp, rcx
0x18001186c  inc     rdi
0x18001186f  cmp     [r9+rdi*2], r13w
0x180011874  jnz     short loc_18001186C
0x180011876  mov     rsi, [r8+10h]
0x18001187a  mov     rbx, [rsp+98h+lpFileName]
0x180011882  add     rsi, 3
0x180011886  add     rsi, [rcx+18h]
0x18001188a  add     rsi, rdi
0x18001188d  mov     rcx, [rbx+10h]
0x180011891  cmp     rcx, rsi
0x180011894  jnb     short loc_1800118E0
0x180011896  mov     rax, [rbx+18h]
0x18001189a  mov     rdx, rsi
0x18001189d  sub     rdx, rcx
0x1800118a0  sub     rax, rcx
0x1800118a3  cmp     rdx, rax
0x1800118a6  ja      short loc_1800118D5
0x1800118a8  cmp     qword ptr [rbx+18h], 7
0x1800118ad  mov     [rbx+10h], rsi
0x1800118b1  jbe     short loc_1800118B8
0x1800118b3  mov     r8, [rbx]
0x1800118b6  jmp     short loc_1800118BB
0x1800118b8  mov     r8, rbx
0x1800118bb  lea     rdi, [r8+rcx*2]
0x1800118bf  test    rdx, rdx
0x1800118c2  jz      short loc_1800118CE
0x1800118c4  movzx   eax, r13w
0x1800118c8  mov     rcx, rdx
0x1800118cb  rep stosw
0x1800118ce  mov     [r8+rsi*2], r13w
0x1800118d3  jmp     short loc_1800118E0
0x1800118d5  mov     r9, rdx
0x1800118d8  mov     rcx, rbx; Src
0x1800118db  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x1800118e0  cmp     qword ptr [r14+18h], 7
0x1800118e5  mov     [rsp+98h+arg_0], r13
0x1800118ed  mov     [rsp+98h+lpFileName], rsi
0x1800118f5  jbe     short loc_1800118FA
0x1800118f7  mov     r14, [r14]
0x1800118fa  lea     rax, [rbp+8]
0x1800118fe  cmp     qword ptr [rax+18h], 7
0x180011903  jbe     short loc_180011908
0x180011905  mov     rax, [rax]
0x180011908  cmp     qword ptr [rbx+18h], 7
0x18001190d  jbe     short loc_180011914
0x18001190f  mov     rcx, [rbx]
0x180011912  jmp     short loc_180011917
0x180011914  mov     rcx, rbx; wchar_t *
0x180011917  mov     rdx, [rbx+10h]; unsigned __int64
0x18001191b  lea     r9, [rsp+98h+lpFileName]; unsigned __int64 *
0x180011923  mov     [rsp+98h+var_60], r14
0x180011928  lea     r8, [rsp+98h+arg_0]; wchar_t **
0x180011930  mov     [rsp+98h+hTemplateFile], rax
0x180011935  lea     rax, aSS; "%s\\%s"
0x18001193c  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rax; wchar_t *
0x180011941  mov     qword ptr [rsp+98h+dwCreationDisposition], r13; int
0x180011946  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x18001194b  test    eax, eax
0x18001194d  js      loc_180011A04
0x180011953  mov     rcx, rbx
0x180011956  call    ?CreatePath@Utilities@Client@HostGuardian@Microsoft@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::HostGuardian::Client::Utilities::CreatePath(std::wstring const &)
0x18001195b  mov     rdx, [rsp+98h+lpFileName]; unsigned __int64
0x180011963  lea     rax, aS; "\\%s"
0x18001196a  mov     rcx, [rsp+98h+arg_0]; wchar_t *
0x180011972  xor     r9d, r9d; unsigned __int64 *
0x180011975  mov     [rsp+98h+hTemplateFile], r12
0x18001197a  xor     r8d, r8d; wchar_t **
0x18001197d  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rax; wchar_t *
0x180011982  mov     qword ptr [rsp+98h+dwCreationDisposition], r13; int
0x180011987  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x18001198c  test    eax, eax
0x18001198e  js      short loc_1800119E7
0x180011990  cmp     qword ptr [rbx+18h], 7
0x180011995  jbe     short loc_18001199A
0x180011997  mov     rbx, [rbx]
0x18001199a  mov     eax, [rsp+98h+arg_38]
0x1800119a1  xor     r9d, r9d; lpSecurityAttributes
0x1800119a4  mov     r8d, [rsp+98h+dwShareMode]; dwShareMode
0x1800119ac  mov     rcx, rbx; lpFileName
0x1800119af  mov     edx, [rsp+98h+dwDesiredAccess]; dwDesiredAccess
0x1800119b6  mov     [rsp+98h+hTemplateFile], r13; hTemplateFile
0x1800119bb  mov     [rsp+98h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800119bf  mov     eax, [rsp+98h+arg_30]
0x1800119c6  mov     [rsp+98h+dwCreationDisposition], eax; dwCreationDisposition
0x1800119ca  call    cs:__imp_CreateFileW
0x1800119d0  mov     [r15], rax
0x1800119d3  mov     rax, r15
0x1800119d6  add     rsp, 58h
0x1800119da  pop     r15
0x1800119dc  pop     r14
0x1800119de  pop     r13
0x1800119e0  pop     r12
0x1800119e2  pop     rdi
0x1800119e3  pop     rsi
0x1800119e4  pop     rbp
0x1800119e5  pop     rbx
0x1800119e6  retn
0x1800119e7  mov     rcx, [rsp+98h]; this
0x1800119ef  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x1800119f6  mov     r9d, eax; char *
0x1800119f9  mov     edx, 117h; void *
0x1800119fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011a04  mov     rcx, [rsp+98h]; this
0x180011a0c  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011a13  mov     r9d, eax; char *
0x180011a16  mov     edx, 10Eh; void *
0x180011a1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
