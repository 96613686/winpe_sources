# CBackgroundCopyFile::_PrecreateLocalFile(bool)

- ea: `0x1800851a8`
- end: `0x1800854d2`
- name: `?_PrecreateLocalFile@CBackgroundCopyFile@@AEAAJ_N@Z`
- size: `810`
- prototype: `__int64 __fastcall(CBackgroundCopyFile *__hidden this, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180086060`

## callees

- `0x1800095a0`
- `0x180009ab4`
- `0x18000d228`
- `0x1800199b4`
- `0x180019c5c`
- `0x1800851a8`
- `0x180086e68`
- `0x1800943c4`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800a59f8`
- `0x1800a688c`
- `0x1800a723c`
- `0x1800a9af0`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085458`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180085446`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180085446`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008546d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008546d`

## string_xrefs

- `0x18008523f`: `CBackgroundCopyFile::_PrecreateLocalFile`
- `0x180085286`: `CBackgroundCopyFile::_PrecreateLocalFile`
- `0x180085400`: `CBackgroundCopyFile::_PrecreateLocalFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CBackgroundCopyFile::_PrecreateLocalFile(CBackgroundCopyFile *this, char a2)
{
  char *v4; // rsi
  char *v6; // rbx
  _QWORD *v7; // rcx
  const char *v8; // r9
  int TemporaryFileName; // r14d
  __int64 v10; // r8
  __int64 v11; // rax
  HANDLE v12; // rbx
  wil::details::in1diag3 *v13; // rcx
  __int64 result; // rax
  HANDLE Token; // [rsp+30h] [rbp-98h] BYREF
  __int128 v17; // [rsp+38h] [rbp-90h] BYREF
  __int128 v18; // [rsp+48h] [rbp-80h]
  __int128 v19; // [rsp+58h] [rbp-70h]
  __int64 *v20; // [rsp+68h] [rbp-60h] BYREF
  int v21; // [rsp+70h] [rbp-58h]
  __int64 v22; // [rsp+78h] [rbp-50h]
  int v23; // [rsp+80h] [rbp-48h]
  __int64 v24; // [rsp+88h] [rbp-40h]
  int v25; // [rsp+90h] [rbp-38h]
  __int64 v26; // [rsp+98h] [rbp-30h]
  __int64 v27; // [rsp+A0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = (char *)this + 264;
  v19 = (unsigned __int64)this + 264;
  if ( (unsigned int)mtx_do_lock((char *)this + 264) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v19) = 1;
  if ( (*((_BYTE *)this + 495) & 4) != 0 )
  {
    LogMessage(
      2u,
      "CBackgroundCopyFile::_PrecreateLocalFile",
      0x641u,
      "TelemetryAssert (%s): %s",
      "!_fSavedFile",
      "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  if ( !*((_QWORD *)this + 8) )
  {
    LogMessage(
      2u,
      "CBackgroundCopyFile::_PrecreateLocalFile",
      0x642u,
      "TelemetryAssert (%s): %s",
      "!_localName.empty()",
      "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  try
  {
    Token = 0;
    CJobSharedData::ImpersonateOwner(*((CJobSharedData **)this + 4), (int)&Token);
    v6 = (char *)this + 80;
    if ( *((_QWORD *)this + 12) || !a2 )
      goto LABEL_44;
    v7 = (_QWORD *)((char *)this + 48);
    if ( *((_QWORD *)this + 9) > 0xFu )
      v7 = (_QWORD *)*v7;
    TemporaryFileName = CPath::GetTemporaryFileName(v7, (char *)this + 80);
    if ( TemporaryFileName >= 0 )
    {
LABEL_44:
      if ( !*((_QWORD *)this + 12) )
        v6 = (char *)this + 48;
      if ( *((_QWORD *)v6 + 3) > 0xFu )
        v6 = *(char **)v6;
      v27 = -1;
      *(_QWORD *)&v17 = this;
      *((_QWORD *)&v17 + 1) = v6;
      *(_QWORD *)&v18 = &v27;
      TemporaryFileName = ExecWithRetriesForSharingViolation__CBackgroundCopyFile::_PrecreateLocalFile_::_9_::_lambda_1___(&v17);
      if ( TemporaryFileName >= 0 )
      {
        v20 = &v27;
        v21 = 590020;
        v22 = 0;
        v23 = 0;
        v24 = 0;
        v25 = 0;
        v26 = 0;
        TemporaryFileName = CFile::_InvokeFileMethod__CFile::IoControl_::_2_::_lambda_1___(&v27, &v20);
        if ( TemporaryFileName < 0 )
        {
          v17 = 0;
          v18 = 0;
          v10 = -1;
          do
            ++v10;
          while ( v6[v10] );
          std::string::_Construct<1,char const *>(&v17, v6);
          v11 = RemovePIIFromFilePath(&v20);
          if ( *(_QWORD *)(v11 + 24) > 0xFu )
            v11 = *(_QWORD *)v11;
          LogMessage(
            3u,
            "CBackgroundCopyFile::_PrecreateLocalFile",
            0x669u,
            "Set file as sparse failed, ignoring hr = %x for %s",
            TemporaryFileName,
            (const char *)v11);
          std::string::~string(&v20);
          std::string::~string(&v17);
          TemporaryFileName = 0;
        }
      }
      CFile::~CFile((CFile *)&v27);
    }
    v12 = Token;
    if ( Token != (HANDLE)-1LL )
    {
      if ( !SetThreadToken(0, Token) )
        wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
      if ( v12 )
        CloseHandle(v12);
    }
    if ( (*((_DWORD *)v4 + 19))-- == 1 )
    {
      *((_DWORD *)v4 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v4 + 2);
    }
    result = (unsigned int)TemporaryFileName;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x670,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800851a8  mov     [rsp+arg_8], rbx
0x1800851ad  mov     [rsp+arg_10], rsi
0x1800851b2  push    rdi
0x1800851b3  push    r14
0x1800851b5  push    r15
0x1800851b7  sub     rsp, 0B0h
0x1800851be  mov     rax, cs:__security_cookie
0x1800851c5  xor     rax, rsp
0x1800851c8  mov     [rsp+0C8h+var_20], rax
0x1800851d0  mov     r15b, dl
0x1800851d3  mov     rdi, rcx
0x1800851d6  xorps   xmm0, xmm0
0x1800851d9  movups  [rsp+0C8h+var_70], xmm0
0x1800851de  lea     rsi, [rcx+108h]
0x1800851e5  mov     qword ptr [rsp+0C8h+var_70], rsi
0x1800851ea  mov     byte ptr [rsp+0C8h+var_70+8], 0
0x1800851ef  mov     rcx, rsi
0x1800851f2  call    mtx_do_lock
0x1800851f7  test    eax, eax
0x1800851f9  jnz     loc_1800854AF
0x1800851ff  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180085206  jz      loc_1800854B9
0x18008520c  mov     byte ptr [rsp+0C8h+var_70+8], 1
0x180085211  lea     r14, aFailed; "Failed"
0x180085218  test    byte ptr [rdi+1EFh], 4
0x18008521f  jz      short loc_18008525E
0x180085221  mov     [rsp+0C8h+var_A0], r14
0x180085226  lea     rax, aFsavedfile; "!_fSavedFile"
0x18008522d  mov     [rsp+0C8h+var_A8], rax
0x180085232  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180085239  mov     r8d, 641h; unsigned int
0x18008523f  lea     rdx, aCbackgroundcop_17; "CBackgroundCopyFile::_PrecreateLocalFil"...
0x180085246  mov     ecx, 2; unsigned __int8
0x18008524b  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180085250  or      ebx, 0FFFFFFFFh
0x180085253  mov     edx, ebx; unsigned int
0x180085255  mov     ecx, ebx; unsigned int
0x180085257  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x18008525c  jmp     short loc_180085261
0x18008525e  or      ebx, 0FFFFFFFFh
0x180085261  cmp     qword ptr [rdi+40h], 0
0x180085266  jnz     short loc_1800852A0
0x180085268  mov     [rsp+0C8h+var_A0], r14
0x18008526d  lea     rax, aLocalnameEmpty; "!_localName.empty()"
0x180085274  mov     [rsp+0C8h+var_A8], rax
0x180085279  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180085280  mov     r8d, 642h; unsigned int
0x180085286  lea     rdx, aCbackgroundcop_17; "CBackgroundCopyFile::_PrecreateLocalFil"...
0x18008528d  mov     ecx, 2; unsigned __int8
0x180085292  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180085297  mov     edx, ebx; unsigned int
0x180085299  mov     ecx, ebx; unsigned int
0x18008529b  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800852a0  mov     [rsp+0C8h+Token], 0
0x1800852a9  lea     rdx, [rsp+0C8h+Token]; int
0x1800852ae  mov     rcx, [rdi+20h]; this
0x1800852b2  call    ?ImpersonateOwner@CJobSharedData@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; CJobSharedData::ImpersonateOwner(void)
0x1800852b7  nop
0x1800852b8  lea     rbx, [rdi+50h]
0x1800852bc  cmp     qword ptr [rbx+10h], 0
0x1800852c1  jnz     short loc_1800852EE
0x1800852c3  test    r15b, r15b
0x1800852c6  jz      short loc_1800852EE
0x1800852c8  lea     rcx, [rdi+30h]
0x1800852cc  cmp     qword ptr [rcx+18h], 0Fh
0x1800852d1  jbe     short loc_1800852D6
0x1800852d3  mov     rcx, [rcx]
0x1800852d6  mov     rdx, rbx
0x1800852d9  call    ?GetTemporaryFileName@CPath@@SAJPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CPath::GetTemporaryFileName(char const *,std::string &)
0x1800852de  mov     r14d, eax
0x1800852e1  test    eax, eax
0x1800852e3  jns     short loc_1800852EE
0x1800852e5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800852e9  jmp     loc_180085437
0x1800852ee  cmp     qword ptr [rdi+60h], 0
0x1800852f3  jnz     short loc_1800852F9
0x1800852f5  lea     rbx, [rdi+30h]
0x1800852f9  cmp     qword ptr [rbx+18h], 0Fh
0x1800852fe  jbe     short loc_180085303
0x180085300  mov     rbx, [rbx]
0x180085303  or      r15, 0FFFFFFFFFFFFFFFFh
0x180085307  mov     [rsp+0C8h+var_28], r15
0x18008530f  mov     qword ptr [rsp+0C8h+var_90], rdi
0x180085314  mov     qword ptr [rsp+0C8h+var_90+8], rbx
0x180085319  lea     rax, [rsp+0C8h+var_28]
0x180085321  mov     qword ptr [rsp+0C8h+var_80], rax
0x180085326  lea     rcx, [rsp+0C8h+var_90]
0x18008532b  call    ExecWithRetriesForSharingViolation__CBackgroundCopyFile___PrecreateLocalFile____9____lambda_1___
0x180085330  mov     r14d, eax
0x180085333  test    eax, eax
0x180085335  js      loc_180085429
0x18008533b  lea     rax, [rsp+0C8h+var_28]
0x180085343  mov     [rsp+0C8h+var_60], rax
0x180085348  mov     [rsp+0C8h+var_58], 900C4h
0x180085350  mov     [rsp+0C8h+var_50], 0
0x180085359  mov     [rsp+0C8h+var_48], 0
0x180085364  mov     [rsp+0C8h+var_40], 0
0x180085370  mov     [rsp+0C8h+var_38], 0
0x18008537b  mov     [rsp+0C8h+var_30], 0
0x180085387  lea     rdx, [rsp+0C8h+var_60]
0x18008538c  lea     rcx, [rsp+0C8h+var_28]
0x180085394  call    CFile___InvokeFileMethod__CFile__IoControl____2____lambda_1___
0x180085399  mov     r14d, eax
0x18008539c  test    eax, eax
0x18008539e  jns     loc_180085429
0x1800853a4  xorps   xmm0, xmm0
0x1800853a7  movups  [rsp+0C8h+var_90], xmm0
0x1800853ac  xorps   xmm1, xmm1
0x1800853af  movdqu  [rsp+0C8h+var_80], xmm1
0x1800853b5  mov     r8, r15
0x1800853b8  inc     r8
0x1800853bb  cmp     byte ptr [rbx+r8], 0
0x1800853c0  jnz     short loc_1800853B8
0x1800853c2  mov     rdx, rbx
0x1800853c5  lea     rcx, [rsp+0C8h+var_90]
0x1800853ca  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800853cf  nop
0x1800853d0  lea     rdx, [rsp+0C8h+var_90]
0x1800853d5  lea     rcx, [rsp+0C8h+var_60]
0x1800853da  call    ?RemovePIIFromFilePath@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@@Z; RemovePIIFromFilePath(std::string const &)
0x1800853df  cmp     qword ptr [rax+18h], 0Fh
0x1800853e4  jbe     short loc_1800853E9
0x1800853e6  mov     rax, [rax]
0x1800853e9  mov     [rsp+0C8h+var_A0], rax
0x1800853ee  mov     dword ptr [rsp+0C8h+var_A8], r14d
0x1800853f3  lea     r9, aSetFileAsSpars; "Set file as sparse failed, ignoring hr "...
0x1800853fa  mov     r8d, 669h; unsigned int
0x180085400  lea     rdx, aCbackgroundcop_17; "CBackgroundCopyFile::_PrecreateLocalFil"...
0x180085407  mov     ecx, 3; unsigned __int8
0x18008540c  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180085411  lea     rcx, [rsp+0C8h+var_60]; void *
0x180085416  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18008541b  nop
0x18008541c  lea     rcx, [rsp+0C8h+var_90]; void *
0x180085421  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180085426  xor     r14d, r14d
0x180085429  lea     rcx, [rsp+0C8h+var_28]; this
0x180085431  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180085436  nop
0x180085437  mov     rbx, [rsp+0C8h+Token]
0x18008543c  cmp     rbx, r15
0x18008543f  jz      short loc_18008545F
0x180085441  mov     rdx, rbx; Token
0x180085444  xor     ecx, ecx; Thread
0x180085446  call    cs:__imp_SetThreadToken
0x18008544c  test    eax, eax
0x18008544e  jz      short loc_1800854CB
0x180085450  test    rbx, rbx
0x180085453  jz      short loc_18008545F
0x180085455  mov     rcx, rbx; hObject
0x180085458  call    cs:__imp_CloseHandle
0x18008545e  nop
0x18008545f  add     [rsi+4Ch], r15d
0x180085463  jnz     short loc_180085473
0x180085465  mov     [rsi+48h], r15d
0x180085469  lea     rcx, [rsi+10h]; SRWLock
0x18008546d  call    cs:__imp_ReleaseSRWLockExclusive
0x180085473  mov     eax, r14d
0x180085476  jmp     short loc_180085486
0x180085478  mov     eax, 8007000Eh
0x18008547d  jmp     short loc_180085486
0x18008547f  mov     eax, dword ptr [rsp+0C8h+var_28]
0x180085486  mov     rcx, [rsp+0C8h+var_20]
0x18008548e  xor     rcx, rsp; StackCookie
0x180085491  call    __security_check_cookie
0x180085496  lea     r11, [rsp+0C8h+var_18]
0x18008549e  mov     rbx, [r11+28h]
0x1800854a2  mov     rsi, [r11+30h]
0x1800854a6  mov     rsp, r11
0x1800854a9  pop     r15
0x1800854ab  pop     r14
0x1800854ad  pop     rdi
0x1800854ae  retn
0x1800854af  mov     ecx, 5; int
0x1800854b4  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800854b9  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x1800854c0  mov     ecx, 6; int
0x1800854c5  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800854cb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
