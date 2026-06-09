# RealtimeProtection::DlpQuarantineEngine::DoCopyBack(RealtimeProtection::_DlpQuarantineItem &)

- ea: `0x1801fd528`
- end: `0x1801fd812`
- name: `?DoCopyBack@DlpQuarantineEngine@RealtimeProtection@@AEAAJAEAU_DlpQuarantineItem@2@@Z`
- size: `746`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpQuarantineEngine *__hidden this, struct RealtimeProtection::_DlpQuarantineItem *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1801fd814`

## callees

- `0x180080030`
- `0x1800809d0`
- `0x18009351c`
- `0x1800943fc`
- `0x1800b7f88`
- `0x180104f64`
- `0x180105f50`
- `0x18010cb40`
- `0x1801459c8`
- `0x1801fd528`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1801fd6c0`
- `KERNEL32!DeleteFileW` at `0x1801fd795`
- `KERNEL32!DeleteFileW` at `0x1801fd6c0`
- `KERNEL32!DeleteFileW` at `0x1801fd795`
- `KERNEL32!CloseHandle` at `0x1801fd76b`
- `KERNEL32!CloseHandle` at `0x1801fd76b`
- `KERNEL32!CopyFileW` at `0x1801fd65e`
- `KERNEL32!CopyFileW` at `0x1801fd65e`
- `KERNEL32!SetFileInformationByHandle` at `0x1801fd728`
- `KERNEL32!SetFileInformationByHandle` at `0x1801fd728`
- `ADVAPI32!RevertToSelf` at `0x1801fd7e3`
- `ADVAPI32!RevertToSelf` at `0x1801fd7e3`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpQuarantineEngine::DoCopyBack(
        RealtimeProtection::DlpQuarantineEngine *this,
        struct RealtimeProtection::_DlpQuarantineItem *a2)
{
  void *v2; // rbx
  _QWORD *v4; // rax
  _QWORD *v5; // r9
  const wchar_t *v6; // rdx
  CommonUtil *v7; // rbx
  char *v8; // rdi
  CommonUtil *v9; // rcx
  _QWORD *v10; // rbp
  const WCHAR *v11; // rdx
  const WCHAR *v12; // rcx
  char LastFailure; // al
  const WCHAR *v14; // rcx
  char v15; // al
  void *v16; // rcx
  unsigned int v17; // eax
  void *v18; // rcx
  const WCHAR **v19; // rbx
  const WCHAR *v20; // rcx
  char v21; // al
  __int128 v23; // [rsp+30h] [rbp-38h] BYREF
  char FileInformation[8]; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  if ( *((_DWORD *)a2 + 1) == 3 )
    v2 = (void *)*((_QWORD *)a2 + 90);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v4 = (_QWORD *)((char *)a2 + 272);
    if ( *((_QWORD *)a2 + 37) > 7u )
      v4 = (_QWORD *)*v4;
    v5 = (_QWORD *)((char *)a2 + 224);
    if ( *((_QWORD *)a2 + 31) > 7u )
      v5 = (_QWORD *)*v5;
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      92,
      (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
      (_DWORD)v5,
      (__int64)v4);
  }
  v23 = 0;
  CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken((CommonUtil::CAutoImpersonateToken *)&v23, v2);
  v7 = (struct RealtimeProtection::_DlpQuarantineItem *)((char *)a2 + 224);
  v8 = (char *)a2 + (-(__int64)(*((_BYTE *)a2 + 50) != 0) & 0xFFFFFFFFFFFFFFC0uLL) + 336;
  v9 = (struct RealtimeProtection::_DlpQuarantineItem *)((char *)a2 + 224);
  if ( *((_QWORD *)a2 + 31) > 7u )
    v9 = *(CommonUtil **)v7;
  if ( (int)CommonUtil::UtilIsFileExists(v9, v6) < 0 )
  {
    v11 = (const WCHAR *)((char *)a2 + 224);
    if ( *((_QWORD *)a2 + 31) > 7u )
      v11 = *(const WCHAR **)v7;
    v12 = (const WCHAR *)v8;
    if ( *((_QWORD *)v8 + 3) > 7u )
      v12 = *(const WCHAR **)v8;
    v10 = v8 + 24;
    if ( !CopyFileW(v12, v11, 1) )
    {
      LastFailure = HrGetLastFailure();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( *((_QWORD *)a2 + 31) > 7u )
          v7 = *(CommonUtil **)v7;
        WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v7, LastFailure);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( *((_QWORD *)a2 + 31) > 7u )
        v7 = *(CommonUtil **)v7;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v7);
    }
    v10 = v8 + 24;
  }
  v14 = (const WCHAR *)v8;
  if ( *v10 > 7u )
    v14 = *(const WCHAR **)v8;
  if ( !DeleteFileW(v14) )
  {
    v15 = HrGetLastFailure();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *v10 > 7u )
        v8 = *(char **)v8;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
        (_DWORD)v8,
        v15);
    }
  }
  v16 = (void *)*((_QWORD *)a2 + 225);
  if ( v16 != (void *)-1LL )
  {
    FileInformation[0] = 1;
    if ( !SetFileInformationByHandle(v16, FileDispositionInfo, FileInformation, 1u) )
    {
      v17 = HrGetLastFailure();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v17);
      v18 = (void *)*((_QWORD *)a2 + 225);
      if ( v18 != (void *)-1LL )
      {
        CloseHandle(v18);
        *((_QWORD *)a2 + 225) = -1;
      }
    }
  }
  if ( *((_QWORD *)a2 + 225) == -1 )
  {
    v19 = (const WCHAR **)((char *)a2 + 400);
    v20 = (const WCHAR *)((char *)a2 + 400);
    if ( *((_QWORD *)a2 + 53) > 7u )
      v20 = *v19;
    if ( !DeleteFileW(v20) )
    {
      v21 = HrGetLastFailure();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( *((_QWORD *)a2 + 53) > 7u )
          v19 = (const WCHAR **)*v19;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          97,
          (unsigned int)&WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
          (_DWORD)v19,
          v21);
      }
    }
  }
  if ( BYTE8(v23) )
    RevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x1801fd528  mov     [rsp+arg_0], rbx
0x1801fd52d  mov     [rsp+arg_10], rbp
0x1801fd532  mov     [rsp+arg_18], rsi
0x1801fd537  push    rdi
0x1801fd538  push    r13
0x1801fd53a  push    r14
0x1801fd53c  sub     rsp, 50h
0x1801fd540  mov     rax, cs:__security_cookie
0x1801fd547  xor     rax, rsp
0x1801fd54a  mov     [rsp+68h+var_20], rax
0x1801fd54f  xor     ebx, ebx
0x1801fd551  mov     rsi, rdx
0x1801fd554  cmp     dword ptr [rdx+4], 3
0x1801fd558  jnz     short loc_1801FD561
0x1801fd55a  mov     rbx, [rdx+2D0h]
0x1801fd561  mov     rcx, cs:WPP_GLOBAL_Control
0x1801fd568  lea     r13, WPP_GLOBAL_Control
0x1801fd56f  cmp     rcx, r13
0x1801fd572  jz      short loc_1801FD5B6
0x1801fd574  test    byte ptr [rcx+1Ch], 4
0x1801fd578  jz      short loc_1801FD5B6
0x1801fd57a  lea     rax, [rdx+110h]
0x1801fd581  cmp     qword ptr [rax+18h], 7
0x1801fd586  jbe     short loc_1801FD58B
0x1801fd588  mov     rax, [rax]
0x1801fd58b  lea     r9, [rdx+0E0h]
0x1801fd592  cmp     qword ptr [r9+18h], 7
0x1801fd597  jbe     short loc_1801FD59C
0x1801fd599  mov     r9, [r9]
0x1801fd59c  mov     rcx, [rcx+10h]
0x1801fd5a0  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801fd5a7  mov     edx, 5Ch ; '\'
0x1801fd5ac  mov     [rsp+68h+var_48], rax
0x1801fd5b1  call    WPP_SF_SS
0x1801fd5b6  xorps   xmm0, xmm0
0x1801fd5b9  lea     rcx, [rsp+68h+var_38]; this
0x1801fd5be  mov     rdx, rbx; void *
0x1801fd5c1  movups  [rsp+68h+var_38], xmm0
0x1801fd5c6  call    ??0CAutoImpersonateToken@CommonUtil@@QEAA@PEAX@Z; CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken(void *)
0x1801fd5cb  mov     al, [rsi+32h]
0x1801fd5ce  lea     rbx, [rsi+0E0h]
0x1801fd5d5  neg     al
0x1801fd5d7  lea     rdi, [rsi+150h]
0x1801fd5de  sbb     rcx, rcx
0x1801fd5e1  and     rcx, 0FFFFFFFFFFFFFFC0h
0x1801fd5e5  add     rdi, rcx
0x1801fd5e8  mov     rcx, rbx
0x1801fd5eb  cmp     qword ptr [rbx+18h], 7
0x1801fd5f0  jbe     short loc_1801FD5F5
0x1801fd5f2  mov     rcx, [rbx]; this
0x1801fd5f5  call    ?UtilIsFileExists@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilIsFileExists(wchar_t const *)
0x1801fd5fa  test    eax, eax
0x1801fd5fc  js      short loc_1801FD638
0x1801fd5fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1801fd605  cmp     rcx, r13
0x1801fd608  jz      short loc_1801FD632
0x1801fd60a  test    byte ptr [rcx+1Ch], 10h
0x1801fd60e  jz      short loc_1801FD632
0x1801fd610  cmp     qword ptr [rbx+18h], 7
0x1801fd615  jbe     short loc_1801FD61A
0x1801fd617  mov     rbx, [rbx]
0x1801fd61a  mov     rcx, [rcx+10h]
0x1801fd61e  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801fd625  mov     edx, 5Dh ; ']'
0x1801fd62a  mov     r9, rbx
0x1801fd62d  call    WPP_SF_S
0x1801fd632  lea     rbp, [rdi+18h]
0x1801fd636  jmp     short loc_1801FD6B3
0x1801fd638  cmp     qword ptr [rbx+18h], 7
0x1801fd63d  mov     rdx, rbx
0x1801fd640  jbe     short loc_1801FD645
0x1801fd642  mov     rdx, [rbx]; lpNewFileName
0x1801fd645  lea     r14, [rdi+18h]
0x1801fd649  mov     rcx, rdi
0x1801fd64c  cmp     qword ptr [r14], 7
0x1801fd650  jbe     short loc_1801FD655
0x1801fd652  mov     rcx, [rdi]; lpExistingFileName
0x1801fd655  mov     r8d, 1; bFailIfExists
0x1801fd65b  mov     rbp, r14
0x1801fd65e  call    cs:__imp_CopyFileW
0x1801fd664  test    eax, eax
0x1801fd666  jnz     short loc_1801FD6B3
0x1801fd668  call    HrGetLastFailure
0x1801fd66d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801fd674  cmp     rcx, r13
0x1801fd677  jz      short loc_1801FD6B3
0x1801fd679  test    byte ptr [rcx+1Ch], 1
0x1801fd67d  jz      short loc_1801FD6B3
0x1801fd67f  cmp     qword ptr [rbx+18h], 7
0x1801fd684  jbe     short loc_1801FD689
0x1801fd686  mov     rbx, [rbx]
0x1801fd689  cmp     qword ptr [r14], 7
0x1801fd68d  mov     r9, rdi
0x1801fd690  jbe     short loc_1801FD695
0x1801fd692  mov     r9, [rdi]
0x1801fd695  mov     rcx, [rcx+10h]; LoggerHandle
0x1801fd699  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801fd6a0  mov     dword ptr [rsp+68h+var_40], eax; char
0x1801fd6a4  mov     edx, 5Eh ; '^'
0x1801fd6a9  mov     [rsp+68h+var_48], rbx; __int64
0x1801fd6ae  call    WPP_SF_SSD
0x1801fd6b3  cmp     qword ptr [rbp+0], 7
0x1801fd6b8  mov     rcx, rdi
0x1801fd6bb  jbe     short loc_1801FD6C0
0x1801fd6bd  mov     rcx, [rdi]; lpFileName
0x1801fd6c0  call    cs:__imp_DeleteFileW
0x1801fd6c6  test    eax, eax
0x1801fd6c8  jnz     short loc_1801FD707
0x1801fd6ca  call    HrGetLastFailure
0x1801fd6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801fd6d6  cmp     rcx, r13
0x1801fd6d9  jz      short loc_1801FD707
0x1801fd6db  test    byte ptr [rcx+1Ch], 1
0x1801fd6df  jz      short loc_1801FD707
0x1801fd6e1  cmp     qword ptr [rbp+0], 7
0x1801fd6e6  jbe     short loc_1801FD6EB
0x1801fd6e8  mov     rdi, [rdi]
0x1801fd6eb  mov     rcx, [rcx+10h]
0x1801fd6ef  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801fd6f6  mov     edx, 5Fh ; '_'
0x1801fd6fb  mov     dword ptr [rsp+68h+var_48], eax
0x1801fd6ff  mov     r9, rdi
0x1801fd702  call    WPP_SF_Sd
0x1801fd707  mov     rcx, [rsi+708h]; hFile
0x1801fd70e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801fd712  cmp     rcx, rbx
0x1801fd715  jz      short loc_1801FD778
0x1801fd717  lea     r9d, [rbx+2]; dwBufferSize
0x1801fd71b  mov     [rsp+68h+FileInformation], 1
0x1801fd720  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x1801fd725  lea     edx, [rbx+5]; FileInformationClass
0x1801fd728  call    cs:__imp_SetFileInformationByHandle
0x1801fd72e  test    eax, eax
0x1801fd730  jnz     short loc_1801FD778
0x1801fd732  call    HrGetLastFailure
0x1801fd737  mov     rcx, cs:WPP_GLOBAL_Control
0x1801fd73e  cmp     rcx, r13
0x1801fd741  jz      short loc_1801FD75F
0x1801fd743  test    byte ptr [rcx+1Ch], 1
0x1801fd747  jz      short loc_1801FD75F
0x1801fd749  mov     rcx, [rcx+10h]
0x1801fd74d  lea     edx, [rbx+61h]
0x1801fd750  mov     r9d, eax
0x1801fd753  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801fd75a  call    WPP_SF_d
0x1801fd75f  mov     rcx, [rsi+708h]; hObject
0x1801fd766  cmp     rcx, rbx
0x1801fd769  jz      short loc_1801FD778
0x1801fd76b  call    cs:__imp_CloseHandle
0x1801fd771  mov     [rsi+708h], rbx
0x1801fd778  cmp     [rsi+708h], rbx
0x1801fd77f  jnz     short loc_1801FD7DC
0x1801fd781  lea     rbx, [rsi+190h]
0x1801fd788  cmp     qword ptr [rbx+18h], 7
0x1801fd78d  mov     rcx, rbx
0x1801fd790  jbe     short loc_1801FD795
0x1801fd792  mov     rcx, [rbx]; lpFileName
0x1801fd795  call    cs:__imp_DeleteFileW
0x1801fd79b  test    eax, eax
0x1801fd79d  jnz     short loc_1801FD7DC
0x1801fd79f  call    HrGetLastFailure
0x1801fd7a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801fd7ab  cmp     rcx, r13
0x1801fd7ae  jz      short loc_1801FD7DC
0x1801fd7b0  test    byte ptr [rcx+1Ch], 1
0x1801fd7b4  jz      short loc_1801FD7DC
0x1801fd7b6  cmp     qword ptr [rbx+18h], 7
0x1801fd7bb  jbe     short loc_1801FD7C0
0x1801fd7bd  mov     rbx, [rbx]
0x1801fd7c0  mov     rcx, [rcx+10h]
0x1801fd7c4  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1801fd7cb  mov     edx, 61h ; 'a'
0x1801fd7d0  mov     dword ptr [rsp+68h+var_48], eax
0x1801fd7d4  mov     r9, rbx
0x1801fd7d7  call    WPP_SF_Sd
0x1801fd7dc  cmp     byte ptr [rsp+68h+var_38+8], 0
0x1801fd7e1  jz      short loc_1801FD7E9
0x1801fd7e3  call    cs:__imp_RevertToSelf
0x1801fd7e9  xor     eax, eax
0x1801fd7eb  mov     rcx, [rsp+68h+var_20]
0x1801fd7f0  xor     rcx, rsp; StackCookie
0x1801fd7f3  call    __security_check_cookie
0x1801fd7f8  lea     r11, [rsp+68h+var_18]
0x1801fd7fd  mov     rbx, [r11+20h]
0x1801fd801  mov     rbp, [r11+30h]
0x1801fd805  mov     rsi, [r11+38h]
0x1801fd809  mov     rsp, r11
0x1801fd80c  pop     r14
0x1801fd80e  pop     r13
0x1801fd810  pop     rdi
0x1801fd811  retn
```
