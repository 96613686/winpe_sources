# CFileAccessor::GetDocFormat(wchar_t *,ulong,ulong *)

- ea: `0x1800052a0`
- end: `0x1800055a7`
- name: `?GetDocFormat@CFileAccessor@@UEAAJPEA_WKPEAK@Z`
- size: `775`
- prototype: `__int64 __fastcall(CFileAccessor *this, wchar_t *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004ec4`
- `0x1800052a0`
- `0x180005720`
- `0x180005c00`
- `0x180005ee0`
- `0x1800061d0`
- `0x180006430`
- `0x1800090b0`
- `0x18000a890`
- `0x18000e878`
- `0x18000fcd0`
- `0x18001e194`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000547a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000547a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005539`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000549f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000549f`

## string_xrefs

- `0x1800053fa`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CFileAccessor::GetDocFormat(CFileAccessor *this, wchar_t *a2, unsigned int a3, unsigned int *a4)
{
  const wchar_t *v8; // r9
  unsigned int v9; // edi
  __int64 v10; // r9
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  const WCHAR *v13; // rbx
  LSTATUS v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  void **v17; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-C8h]
  int v19; // [rsp+40h] [rbp-C0h]
  unsigned int v20; // [rsp+44h] [rbp-BCh]
  wchar_t v21[36]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[3]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v23[36]; // [rsp+A8h] [rbp-58h] BYREF
  void **v24; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v25[3]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v26[68]; // [rsp+110h] [rbp+10h] BYREF
  int v27; // [rsp+198h] [rbp+98h]
  HKEY hKey; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  *a4 = 0;
  v8 = (const wchar_t *)*((unsigned int *)this + 37);
  if ( (_DWORD)v8 )
    goto LABEL_8;
  if ( !*((_DWORD *)this + 36) || *((_DWORD *)this + 28) == 259 )
  {
    v8 = 0;
LABEL_8:
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
      (const wchar_t *)0x5CE,
      (__int64)L"[SrchPHFile] Check oplock %d\n",
      v8);
    goto LABEL_9;
  }
  if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(
      Microsoft_Windows_Search_ProtocolHandlers_Context,
      MSSearchTraceId_FilterOplockBreak,
      *((_QWORD *)this + 88));
  SearchIndexerTrace::Warning(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
    (const wchar_t *)0x5CA,
    (unsigned int)L"[SrchPHFile] Oplock broken for %ls\n",
    *((const wchar_t **)this + 88));
  *((_DWORD *)this + 37) = 1;
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
    (const wchar_t *)0x5CE,
    (__int64)L"[SrchPHFile] Check oplock %d\n",
    (const wchar_t *)1);
LABEL_9:
  if ( *((_DWORD *)this + 37) )
  {
    return (unsigned int)-2147024864;
  }
  else
  {
    lpSubKey = v21;
    v19 = 33;
    wcscpy(v21, L".");
    v20 = 1;
    v17 = &TLMString<32,32,1024>::`vftable';
    CURL::ParseExtension((CFileAccessor *)((char *)this + 224));
    v10 = *((unsigned __int16 *)this + 342);
    v11 = *((unsigned __int16 *)this + 341);
    v12 = v10 + v11;
    if ( v10 + v11 < v11 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v12, v11);
    if ( v12 > *((unsigned int *)this + 67) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
        (const char *)0xCE,
        phkResult);
    v9 = 0;
    ((void (__fastcall *)(void ***, unsigned __int64, _QWORD))v17[4])(&v17, *((_QWORD *)this + 32) + 2 * v11, v20);
    v13 = lpSubKey;
    v25[1] = v26;
    v25[2] = 65;
    v26[0] = 0;
    v25[0] = &TLMString<64,64,32767>::`vftable';
    v24 = &CRegistry::`vftable';
    v27 = 1;
    CLMString::operator=((__int64)v25, (__int64)lpSubKey);
    SetLastError(0);
    v14 = RegOpenKeyExW(HKEY_CLASSES_ROOT, v13, 0, 0x20019u, &hKey);
    if ( v14 )
    {
      hKey = 0;
      SetLastError(v14);
    }
    v22[1] = v23;
    v22[2] = 33;
    v23[0] = 0;
    v22[0] = &TLMString<32,32,1024>::`vftable';
    if ( CRegistry::GetValue((CRegistry *)&v24, L"Content Type", (struct CLMString *)v22) )
      v9 = CLMString::Export((CLMString *)v22, a2, a3, a4);
    v22[0] = &TLMString<32,32,1024>::`vftable';
    CLMString::DeleteBuf((CLMString *)v22, v23);
    v22[0] = &CLMString::`vftable';
    v24 = &CRegistry::`vftable';
    if ( hKey && v27 )
      RegCloseKey(hKey);
    v24 = &PConfigNode::`vftable';
    v25[0] = &TLMString<64,64,32767>::`vftable';
    CLMString::DeleteBuf((CLMString *)v25, v26);
    v25[0] = &CLMString::`vftable';
    v17 = &TLMString<32,32,1024>::`vftable';
    CLMString::DeleteBuf((CLMString *)&v17, v21);
  }
  return v9;
}

```

## disassembly

```asm
0x1800052a0  mov     [rsp-8+arg_10], rbx
0x1800052a5  push    rbp
0x1800052a6  push    rsi
0x1800052a7  push    rdi
0x1800052a8  push    r12
0x1800052aa  push    r13
0x1800052ac  push    r14
0x1800052ae  push    r15
0x1800052b0  lea     rbp, [rsp-0C0h]
0x1800052b8  sub     rsp, 1C0h
0x1800052bf  mov     rax, cs:__security_cookie
0x1800052c6  xor     rax, rsp
0x1800052c9  mov     [rbp+0F0h+var_40], rax
0x1800052d0  mov     rsi, r9
0x1800052d3  mov     r14d, r8d
0x1800052d6  mov     r15, rdx
0x1800052d9  mov     rbx, rcx
0x1800052dc  xor     r12d, r12d
0x1800052df  mov     [r9], r12d
0x1800052e2  mov     r9d, [rcx+94h]
0x1800052e9  test    r9d, r9d
0x1800052ec  jnz     short loc_180005357
0x1800052ee  cmp     [rcx+90h], r12d
0x1800052f5  jz      short loc_180005354
0x1800052f7  cmp     dword ptr [rcx+70h], 103h
0x1800052fe  jz      short loc_180005354
0x180005300  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 8
0x180005307  jz      short loc_180005323
0x180005309  mov     r8, [rcx+2C0h]
0x180005310  lea     rdx, MSSearchTraceId_FilterOplockBreak
0x180005317  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x18000531e  call    McTemplateU0z_EventWriteTransfer
0x180005323  mov     r9, [rbx+2C0h]; wchar_t *
0x18000532a  lea     r8, aSrchphfileOplo; "[SrchPHFile] Oplock broken for %ls\n"
0x180005331  mov     edx, 5CAh; wchar_t *
0x180005336  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000533d  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180005342  mov     dword ptr [rbx+94h], 1
0x18000534c  mov     r9d, 1
0x180005352  jmp     short loc_180005357
0x180005354  mov     r9d, r12d; wchar_t *
0x180005357  lea     r8, aSrchphfileChec; "[SrchPHFile] Check oplock %d\n"
0x18000535e  mov     edx, 5CEh; wchar_t *
0x180005363  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000536a  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000536f  cmp     [rbx+94h], r12d
0x180005376  jz      short loc_180005382
0x180005378  mov     edi, 80070020h
0x18000537d  jmp     loc_18000557B
0x180005382  lea     rcx, [rsp+1F0h+var_1A8]
0x180005387  mov     [rsp+1F0h+lpSubKey], rcx
0x18000538c  mov     [rsp+1F0h+var_1B0], 21h ; '!'
0x180005394  mov     eax, dword ptr cs:asc_18002A97C; "."
0x18000539a  mov     [rsp+1F0h+var_1A8], ax
0x18000539f  mov     [rsp+1F0h+var_1AC], 1
0x1800053a7  mov     [rcx+2], r12w
0x1800053ac  lea     r13, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x1800053b3  mov     [rsp+1F0h+var_1C0], r13
0x1800053b8  lea     rcx, [rbx+0E0h]; this
0x1800053bf  call    ?ParseExtension@CURL@@IEAAXXZ; CURL::ParseExtension(void)
0x1800053c4  movzx   r9d, word ptr [rbx+2ACh]
0x1800053cc  movzx   edx, word ptr [rbx+2AAh]
0x1800053d3  lea     rcx, [r9+rdx]
0x1800053d7  cmp     rcx, rdx
0x1800053da  jnb     short loc_1800053E2
0x1800053dc  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800053e2  mov     eax, [rbx+10Ch]
0x1800053e8  cmp     rcx, rax
0x1800053eb  jbe     short loc_18000540C
0x1800053ed  mov     rcx, [rbp+0F8h]; this
0x1800053f4  mov     r9d, 0CEh; char *
0x1800053fa  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180005401  mov     edx, 40Ch; void *
0x180005406  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000540c  mov     edi, r12d
0x18000540f  mov     rax, [rbx+100h]
0x180005416  lea     rdx, [rax+rdx*2]
0x18000541a  mov     rax, [rsp+1F0h+var_1C0]
0x18000541f  mov     r8d, [rsp+1F0h+var_1AC]
0x180005424  lea     rcx, [rsp+1F0h+var_1C0]
0x180005429  mov     rax, [rax+20h]
0x18000542d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005432  mov     rbx, [rsp+1F0h+lpSubKey]
0x180005437  lea     rax, [rbp+0F0h+var_E0]
0x18000543b  mov     [rbp+0F0h+var_F0], rax
0x18000543f  mov     [rbp+0F0h+var_E8], 41h ; 'A'
0x180005447  mov     [rbp+0F0h+var_E0], r12w
0x18000544c  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180005453  mov     [rbp+0F0h+var_F8], rax
0x180005457  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18000545e  mov     [rbp+0F0h+var_100], rax
0x180005462  mov     [rbp+0F0h+var_58], 1
0x18000546c  mov     rdx, rbx
0x18000546f  lea     rcx, [rbp+0F0h+var_F8]
0x180005473  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180005478  xor     ecx, ecx; dwErrCode
0x18000547a  call    cs:__imp_SetLastError
0x180005480  lea     rax, [rbp+0F0h+hKey]
0x180005487  mov     qword ptr [rsp+1F0h+phkResult], rax; phkResult
0x18000548c  mov     r9d, 20019h; samDesired
0x180005492  xor     r8d, r8d; ulOptions
0x180005495  mov     rdx, rbx; lpSubKey
0x180005498  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000549f  call    cs:__imp_RegOpenKeyExW
0x1800054a5  test    eax, eax
0x1800054a7  jz      short loc_1800054B8
0x1800054a9  mov     [rbp+0F0h+hKey], r12
0x1800054b0  mov     ecx, eax; dwErrCode
0x1800054b2  call    cs:__imp_SetLastError
0x1800054b8  lea     rax, [rbp+0F0h+var_148]
0x1800054bc  mov     [rbp+0F0h+var_158], rax
0x1800054c0  mov     [rbp+0F0h+var_150], 21h ; '!'
0x1800054c8  mov     [rbp+0F0h+var_148], r12w
0x1800054cd  mov     [rbp+0F0h+var_160], r13
0x1800054d1  lea     r8, [rbp+0F0h+var_160]; struct CLMString *
0x1800054d5  lea     rdx, aContentType; "Content Type"
0x1800054dc  lea     rcx, [rbp+0F0h+var_100]; this
0x1800054e0  call    ?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z; CRegistry::GetValue(wchar_t const *,CLMString &)
0x1800054e5  test    eax, eax
0x1800054e7  jz      short loc_1800054FD
0x1800054e9  mov     r9, rsi; unsigned int *
0x1800054ec  mov     r8d, r14d; unsigned int
0x1800054ef  mov     rdx, r15; wchar_t *
0x1800054f2  lea     rcx, [rbp+0F0h+var_160]; this
0x1800054f6  call    ?Export@CLMString@@QEBAJQEA_WKPEAK@Z; CLMString::Export(wchar_t * const,ulong,ulong *)
0x1800054fb  mov     edi, eax
0x1800054fd  mov     [rbp+0F0h+var_160], r13
0x180005501  lea     rdx, [rbp+0F0h+var_148]; wchar_t *
0x180005505  lea     rcx, [rbp+0F0h+var_160]; this
0x180005509  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18000550e  lea     rbx, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180005515  mov     [rbp+0F0h+var_160], rbx
0x180005519  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180005520  mov     [rbp+0F0h+var_100], rax
0x180005524  mov     rcx, [rbp+0F0h+hKey]; hKey
0x18000552b  test    rcx, rcx
0x18000552e  jz      short loc_18000553F
0x180005530  cmp     [rbp+0F0h+var_58], 0
0x180005537  jz      short loc_18000553F
0x180005539  call    cs:__imp_RegCloseKey
0x18000553f  lea     rax, ??_7PConfigNode@@6B@; const PConfigNode::`vftable'
0x180005546  mov     [rbp+0F0h+var_100], rax
0x18000554a  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180005551  mov     [rbp+0F0h+var_F8], rax
0x180005555  lea     rdx, [rbp+0F0h+var_E0]; wchar_t *
0x180005559  lea     rcx, [rbp+0F0h+var_F8]; this
0x18000555d  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180005562  mov     [rbp+0F0h+var_F8], rbx
0x180005566  mov     [rsp+1F0h+var_1C0], r13
0x18000556b  lea     rdx, [rsp+1F0h+var_1A8]; wchar_t *
0x180005570  lea     rcx, [rsp+1F0h+var_1C0]; this
0x180005575  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18000557a  nop
0x18000557b  mov     eax, edi
0x18000557d  mov     rcx, [rbp+0F0h+var_40]
0x180005584  xor     rcx, rsp; StackCookie
0x180005587  call    __security_check_cookie
0x18000558c  mov     rbx, [rsp+1F0h+arg_10]
0x180005594  add     rsp, 1C0h
0x18000559b  pop     r15
0x18000559d  pop     r14
0x18000559f  pop     r13
0x1800055a1  pop     r12
0x1800055a3  pop     rdi
0x1800055a4  pop     rsi
0x1800055a5  pop     rbp
0x1800055a6  retn
```
