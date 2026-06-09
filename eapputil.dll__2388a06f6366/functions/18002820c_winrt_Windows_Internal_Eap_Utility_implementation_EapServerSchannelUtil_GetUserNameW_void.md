# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::GetUserNameW(void)

- ea: `0x18002820c`
- end: `0x1800283b4`
- name: `?GetUserNameW@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `424`
- prototype: `__int64 __fastcall(struct _SecHandle *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002a2a8`

## callees

- `0x180002b78`
- `0x1800037dc`
- `0x1800101c4`
- `0x180013cd0`
- `0x180023760`
- `0x180025808`
- `0x180025db0`
- `0x180025f54`
- `0x18002820c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028364`
- `SspiCli!GetUserNameExW` at `0x1800282b5`
- `SspiCli!GetUserNameExW` at `0x1800282b5`
- `SspiCli!QuerySecurityContextToken` at `0x18002822c`
- `SspiCli!QuerySecurityContextToken` at `0x18002822c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028242`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028242`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002834f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002834f`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::GetUserNameW(
        struct _SecHandle *a1,
        __int64 a2)
{
  SECURITY_STATUS v3; // eax
  const char *v4; // r9
  const char *v5; // r9
  LPWSTR v6; // rsi
  unsigned __int64 v7; // rcx
  WCHAR *v8; // rax
  size_t v9; // rbx
  LPWSTR v10; // rdx
  __int64 v11; // r8
  int v13; // [rsp+20h] [rbp-30h]
  __int64 v14; // [rsp+28h] [rbp-28h] BYREF
  LPWSTR lpNameBuffer[2]; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR v16; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  ULONG nSize; // [rsp+90h] [rbp+40h] BYREF
  void *Token; // [rsp+98h] [rbp+48h] BYREF

  Token = 0;
  v3 = QuerySecurityContextToken(a1 + 2, &Token);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x397,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)(unsigned int)v3,
      v13);
  if ( !ImpersonateLoggedOnUser(Token) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x349,
      (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      v4);
  nSize = 514;
  lpNameBuffer[0] = (LPWSTR)operator new(0x404u);
  v16 = lpNameBuffer[0] + 514;
  memset_0(lpNameBuffer[0], 0, 0x404u);
  lpNameBuffer[1] = lpNameBuffer[0] + 514;
  v14 = 0;
  std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(&v14);
  if ( !GetUserNameExW(NameSamCompatible, lpNameBuffer[0], &nSize) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x39E,
      (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      v5);
  v6 = lpNameBuffer[1];
  v7 = lpNameBuffer[1] - lpNameBuffer[0];
  if ( nSize < v7 )
  {
    v8 = &lpNameBuffer[0][nSize];
LABEL_10:
    lpNameBuffer[1] = v8;
    goto LABEL_11;
  }
  if ( nSize > v7 )
  {
    if ( nSize <= (unsigned __int64)(v16 - lpNameBuffer[0]) )
    {
      v9 = nSize - v7;
      memset_0(lpNameBuffer[1], 0, v9 * 2);
      v8 = &v6[v9];
      goto LABEL_10;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(lpNameBuffer, nSize);
  }
LABEL_11:
  v10 = lpNameBuffer[0];
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  std::wstring::_Construct<1,unsigned short const *>(a2);
  std::vector<unsigned short>::~vector<unsigned short>(lpNameBuffer);
  RevertToSelf();
  if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(Token);
  return a2;
}

```

## disassembly

```asm
0x18002820c  push    rbp
0x18002820e  push    rbx
0x18002820f  push    rsi
0x180028210  push    rdi
0x180028211  push    r14
0x180028213  mov     rbp, rsp
0x180028216  sub     rsp, 50h
0x18002821a  mov     rdi, rdx
0x18002821d  xor     r14d, r14d
0x180028220  mov     [rbp+Token], r14
0x180028224  add     rcx, 20h ; ' '; phContext
0x180028228  lea     rdx, [rbp+Token]; Token
0x18002822c  call    cs:__imp_QuerySecurityContextToken
0x180028232  mov     rcx, [rbp+28h]; this
0x180028236  test    eax, eax
0x180028238  js      loc_18002838D
0x18002823e  mov     rcx, [rbp+Token]; hToken
0x180028242  call    cs:__imp_ImpersonateLoggedOnUser
0x180028248  mov     rcx, [rbp+28h]; this
0x18002824c  test    eax, eax
0x18002824e  jz      loc_1800283A2
0x180028254  mov     [rbp+arg_0], 1
0x180028258  mov     [rbp+nSize], 202h
0x18002825f  xorps   xmm0, xmm0
0x180028262  movdqu  xmmword ptr [rbp+lpNameBuffer], xmm0
0x180028267  mov     [rbp+var_10], r14
0x18002826b  mov     esi, 404h
0x180028270  mov     ecx, esi; Size
0x180028272  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028277  mov     [rbp+lpNameBuffer], rax
0x18002827b  lea     rbx, [rax+404h]
0x180028282  mov     [rbp+var_10], rbx
0x180028286  mov     r8d, esi; Size
0x180028289  xor     edx, edx; Val
0x18002828b  mov     rcx, rax; void *
0x18002828e  call    memset_0
0x180028293  mov     [rbp+lpNameBuffer+8], rbx
0x180028297  mov     [rbp+var_28], r14
0x18002829b  lea     rcx, [rbp+var_28]
0x18002829f  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x1800282a4  nop
0x1800282a5  mov     rbx, [rbp+28h]
0x1800282a9  lea     r8, [rbp+nSize]; nSize
0x1800282ad  mov     rdx, [rbp+lpNameBuffer]; lpNameBuffer
0x1800282b1  lea     ecx, [r14+2]; NameFormat
0x1800282b5  call    cs:__imp_GetUserNameExW
0x1800282bb  test    al, al
0x1800282bd  jz      loc_180028378
0x1800282c3  mov     ebx, [rbp+nSize]
0x1800282c6  mov     rsi, [rbp+lpNameBuffer+8]
0x1800282ca  mov     rdx, [rbp+lpNameBuffer]
0x1800282ce  mov     rcx, rsi
0x1800282d1  sub     rcx, rdx
0x1800282d4  sar     rcx, 1
0x1800282d7  cmp     rbx, rcx
0x1800282da  jnb     short loc_1800282E2
0x1800282dc  lea     rax, [rdx+rbx*2]
0x1800282e0  jmp     short loc_180028318
0x1800282e2  jbe     short loc_18002831C
0x1800282e4  mov     rax, [rbp+var_10]
0x1800282e8  sub     rax, rdx
0x1800282eb  sar     rax, 1
0x1800282ee  cmp     rbx, rax
0x1800282f1  jbe     short loc_180028301
0x1800282f3  mov     rdx, rbx
0x1800282f6  lea     rcx, [rbp+lpNameBuffer]
0x1800282fa  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800282ff  jmp     short loc_18002831C
0x180028301  sub     rbx, rcx
0x180028304  add     rbx, rbx
0x180028307  mov     r8, rbx; Size
0x18002830a  xor     edx, edx; Val
0x18002830c  mov     rcx, rsi; void *
0x18002830f  call    memset_0
0x180028314  lea     rax, [rbx+rsi]
0x180028318  mov     [rbp+lpNameBuffer+8], rax
0x18002831c  mov     rdx, [rbp+lpNameBuffer]
0x180028320  xorps   xmm0, xmm0
0x180028323  movups  xmmword ptr [rdi], xmm0
0x180028326  mov     [rdi+10h], r14
0x18002832a  mov     [rdi+18h], r14
0x18002832e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028332  inc     r8
0x180028335  cmp     [rdx+r8*2], r14w
0x18002833a  jnz     short loc_180028332
0x18002833c  mov     rcx, rdi
0x18002833f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028344  nop
0x180028345  lea     rcx, [rbp+lpNameBuffer]
0x180028349  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002834e  nop
0x18002834f  call    cs:__imp_RevertToSelf
0x180028355  nop
0x180028356  mov     rcx, [rbp+Token]; hObject
0x18002835a  lea     rax, [rcx-1]
0x18002835e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028362  ja      short loc_18002836A
0x180028364  call    cs:__imp_CloseHandle
0x18002836a  mov     rax, rdi
0x18002836d  add     rsp, 50h
0x180028371  pop     r14
0x180028373  pop     rdi
0x180028374  pop     rsi
0x180028375  pop     rbx
0x180028376  pop     rbp
0x180028377  retn
0x180028378  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002837f  mov     edx, 39Eh; void *
0x180028384  mov     rcx, rbx; this
0x180028387  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002838d  mov     r9d, eax; char *
0x180028390  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180028397  mov     edx, 397h; void *
0x18002839c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800283a2  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x1800283a9  mov     edx, 349h; void *
0x1800283ae  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
