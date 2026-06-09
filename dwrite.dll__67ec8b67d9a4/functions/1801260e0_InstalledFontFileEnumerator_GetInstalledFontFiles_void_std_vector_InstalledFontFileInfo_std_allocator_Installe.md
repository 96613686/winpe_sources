# InstalledFontFileEnumerator::GetInstalledFontFiles(void *,std::vector<InstalledFontFileInfo,std::allocator<InstalledFontFileInfo>> &,InstalledFontChangeInfo *)

- ea: `0x1801260e0`
- end: `0x180126498`
- name: `?GetInstalledFontFiles@InstalledFontFileEnumerator@@UEAAXPEAXAEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@PEAUInstalledFontChangeInfo@@@Z`
- size: `952`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18011ef30`
- `0x1801243d0`
- `0x1801260e0`
- `0x1801c8290`
- `0x1801e7ba8`
- `0x1801efaac`
- `0x18020a464`
- `0x1802496d4`
- `0x18024e90c`
- `0x18024e9e4`
- `0x18024ea1c`
- `0x18024ede4`
- `0x18024ef00`
- `0x18024ef8c`
- `0x18024f3b0`

## import_xrefs

- `kernel32!GetLastError` at `0x180126304`
- `kernel32!GetLastError` at `0x18012639b`
- `kernel32!GetLastError` at `0x180126304`
- `kernel32!GetLastError` at `0x18012639b`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x1801261d1`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x1801261d1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012616a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18012616a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18012613d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18012613d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012627b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18012627b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned __int64 __fastcall InstalledFontFileEnumerator::GetInstalledFontFiles(
        __int64 a1,
        void *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  __int128 i; // rdi
  HANDLE v10; // rax
  _QWORD *v11; // rdx
  _QWORD *v12; // r8
  unsigned __int64 v13; // rdx
  unsigned __int64 result; // rax
  InstalledFontFileEnumerator::LocalFileInfo *v15; // r15
  InstalledFontFileEnumerator::LocalFileInfo *v16; // r13
  DWORD LastError; // eax
  int v18; // r9d
  __int64 v19; // rdx
  __int64 v20; // rax
  DWORD v21; // eax
  int v22; // r9d
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // [rsp+20h] [rbp-60h]
  int v26; // [rsp+28h] [rbp-58h]
  __int128 v27; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+58h] [rbp-28h]
  InstalledFontFileEnumerator::LocalFileInfo *v29; // [rsp+60h] [rbp-20h] BYREF
  InstalledFontFileEnumerator::LocalFileInfo *v30; // [rsp+68h] [rbp-18h]
  __int64 v31; // [rsp+70h] [rbp-10h]
  unsigned __int64 v33; // [rsp+C8h] [rbp+48h] BYREF
  _QWORD *v34; // [rsp+D0h] [rbp+50h]

  v34 = a3;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v29);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v27);
  if ( v7 )
  {
    EventTag::EventTag((EventTag *)&v33, (const char (*)[9])"Imperson");
    if ( !ImpersonateLoggedOnUser(a2) )
      LogAndThrowLastError(v33);
  }
  InstalledFontFileEnumerator::EnumerateRegistry(a1, &v29, &v27, a4);
  if ( a2 )
    RevertToSelf();
  if ( a4 )
  {
    v8 = (__int64)(*((_QWORD *)&v27 + 1) - v27) >> 3;
    v33 = v8;
    if ( v8 > (__int64)(a4[4] - a4[2]) >> 3 )
    {
      if ( v8 > 0x1FFFFFFFFFFFFFFFLL )
        goto LABEL_20;
      std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Reallocate<0>(a4 + 2, &v33);
    }
    for ( i = v27; (_QWORD)i != *((_QWORD *)&i + 1); *(_QWORD *)&i = i + 8 )
    {
      v10 = FindFirstChangeNotificationW((LPCWSTR)(*(_QWORD *)i + 8LL), 0, 0x11u);
      if ( v10 != (HANDLE)-1LL )
      {
        v33 = (unsigned __int64)v10;
        v11 = (_QWORD *)a4[3];
        if ( v11 == (_QWORD *)a4[4] )
        {
          std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Emplace_reallocate<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>(
            a4 + 2,
            v11,
            &v33);
        }
        else
        {
          *v11 = v10;
          v33 = 0;
          a4[3] += 8LL;
        }
        ScopedHandle<FileChangeNotificationHandlePolicy,void *>::~ScopedHandle<FileChangeNotificationHandlePolicy,void *>(&v33);
      }
    }
  }
  v12 = v34;
  v13 = 0x6DB6DB6DB6DB6DB7LL * ((v30 - v29) >> 3) + 0x6DB6DB6DB6DB6DB7LL * ((__int64)(v34[1] - *v34) >> 3);
  v33 = v13;
  result = 0x6DB6DB6DB6DB6DB7LL * ((__int64)(v34[2] - *v34) >> 3);
  if ( v13 > result )
  {
    if ( v13 > 0x492492492492492LL )
LABEL_20:
      std::_Xlength_error("vector too long");
    result = std::vector<InstalledFontFileInfo>::_Reallocate<0>(v34, &v33);
    v12 = v34;
  }
  v15 = v29;
  v16 = v30;
  if ( v29 != v30 )
  {
    if ( a2 )
    {
      do
      {
        result = InstalledFontFileEnumerator::TryConvertFileInfo(a1, 0, v15, v12);
        if ( !(_BYTE)result )
        {
          result = InstalledFontFileEnumerator::TryConvertFileInfo(a1, a2, v15, v34);
          if ( !(_BYTE)result )
          {
            LastError = GetLastError();
            if ( *((_BYTE *)v15 + 48) )
            {
              if ( *((_QWORD *)v15 + 3) <= 7u )
                v19 = (__int64)v15;
              else
                v19 = *(_QWORD *)v15;
              result = EventLogger::LogEvent<long,EventTag,unsigned int,wchar_t const *,unsigned long>(
                         (int)a1 + 16,
                         1953394502,
                         1869771365,
                         v18,
                         0x6D756E65656C6966LL,
                         v26,
                         v19,
                         LastError);
            }
            else
            {
              if ( *((_QWORD *)v15 + 3) <= 7u )
                v20 = (__int64)v15;
              else
                v20 = *(_QWORD *)v15;
              result = EventLogger::LogEvent<EventTag,int,wchar_t const *>(
                         (int)a1 + 16,
                         1953394502,
                         1852989815,
                         1701603686,
                         v25,
                         v20);
            }
          }
        }
        v15 = (InstalledFontFileEnumerator::LocalFileInfo *)((char *)v15 + 56);
        v12 = v34;
      }
      while ( v15 != v16 );
    }
    else
    {
      do
      {
        result = InstalledFontFileEnumerator::TryConvertFileInfo(a1, 0, v15, v12);
        if ( !(_BYTE)result )
        {
          v21 = GetLastError();
          if ( *((_BYTE *)v15 + 48) )
          {
            if ( *((_QWORD *)v15 + 3) <= 7u )
              v23 = (__int64)v15;
            else
              v23 = *(_QWORD *)v15;
            result = EventLogger::LogEvent<long,EventTag,unsigned int,wchar_t const *,unsigned long>(
                       (int)a1 + 16,
                       1953394502,
                       1869771365,
                       v22,
                       0x6D756E65656C6966LL,
                       v26,
                       v23,
                       v21);
          }
          else
          {
            if ( *((_QWORD *)v15 + 3) <= 7u )
              v24 = (__int64)v15;
            else
              v24 = *(_QWORD *)v15;
            result = EventLogger::LogEvent<EventTag,int,wchar_t const *>(
                       (int)a1 + 16,
                       1953394502,
                       1852989815,
                       1701603686,
                       v25,
                       v24);
          }
        }
        v15 = (InstalledFontFileEnumerator::LocalFileInfo *)((char *)v15 + 56);
        v12 = v34;
      }
      while ( v15 != v16 );
    }
  }
  if ( (_QWORD)v27 )
  {
    std::_Destroy_range<std::allocator<DWrite::RefString>>(v27, *((_QWORD *)&v27 + 1));
    result = std::_Deallocate<16>(v27, (v28 - v27) & 0xFFFFFFFFFFFFFFF8uLL);
    v27 = 0;
    v28 = 0;
  }
  if ( v29 )
  {
    std::_Destroy_range<std::allocator<InstalledFontFileEnumerator::LocalFileInfo>>(v29);
    return std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
  }
  return result;
}

```

## disassembly

```asm
0x1801260e0  mov     [rsp-38h+arg_18], rbx
0x1801260e5  mov     [rsp-38h+arg_10], r8
0x1801260ea  mov     [rsp-38h+arg_0], rcx
0x1801260ef  push    rbp
0x1801260f0  push    rsi
0x1801260f1  push    rdi
0x1801260f2  push    r12
0x1801260f4  push    r13
0x1801260f6  push    r14
0x1801260f8  push    r15
0x1801260fa  mov     rbp, rsp
0x1801260fd  sub     rsp, 80h
0x180126104  mov     rbx, r9
0x180126107  mov     r12, rdx
0x18012610a  mov     rdi, rcx
0x18012610d  lea     rcx, [rbp+var_20]; void *
0x180126111  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180126116  nop
0x180126117  lea     rcx, [rbp+var_38]; void *
0x18012611b  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180126120  nop
0x180126121  mov     [rbp+var_40], rdx
0x180126125  test    rdx, rdx
0x180126128  jz      short loc_180126151
0x18012612a  lea     rdx, aImperson; "Imperson"
0x180126131  lea     rcx, [rbp+arg_8]; this
0x180126135  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x18012613a  mov     rcx, r12; hToken
0x18012613d  call    cs:__imp_ImpersonateLoggedOnUser
0x180126143  test    eax, eax
0x180126145  jnz     short loc_180126151
0x180126147  mov     rcx, [rbp+arg_8]
0x18012614b  call    ?LogAndThrowLastError@@YAXVEventTag@@I@Z; LogAndThrowLastError(EventTag,uint)
0x180126151  mov     r9, rbx
0x180126154  lea     r8, [rbp+var_38]
0x180126158  lea     rdx, [rbp+var_20]
0x18012615c  mov     rcx, rdi
0x18012615f  call    ?EnumerateRegistry@InstalledFontFileEnumerator@@AEAAXAEAV?$vector@ULocalFileInfo@InstalledFontFileEnumerator@@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@AEAV?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@3@PEAUInstalledFontChangeInfo@@@Z; InstalledFontFileEnumerator::EnumerateRegistry(std::vector<InstalledFontFileEnumerator::LocalFileInfo> &,std::vector<DWrite::RefString> &,InstalledFontChangeInfo *)
0x180126164  nop
0x180126165  test    r12, r12
0x180126168  jz      short loc_180126170
0x18012616a  call    cs:__imp_RevertToSelf
0x180126170  test    rbx, rbx
0x180126173  jz      loc_18012621D
0x180126179  mov     rcx, qword ptr [rbp+var_38+8]
0x18012617d  sub     rcx, qword ptr [rbp+var_38]
0x180126181  sar     rcx, 3
0x180126185  mov     [rbp+arg_8], rcx
0x180126189  mov     rax, [rbx+20h]
0x18012618d  sub     rax, [rbx+10h]
0x180126191  sar     rax, 3
0x180126195  cmp     rcx, rax
0x180126198  jbe     short loc_1801261BA
0x18012619a  mov     rax, 1FFFFFFFFFFFFFFFh
0x1801261a4  cmp     rcx, rax
0x1801261a7  ja      loc_180126274
0x1801261ad  lea     rdx, [rbp+arg_8]
0x1801261b1  lea     rcx, [rbx+10h]
0x1801261b5  call    ??$_Reallocate@$0A@@?$vector@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@V?$allocator@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@@std@@@std@@AEAAXAEA_K@Z; std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Reallocate<0>(unsigned __int64 &)
0x1801261ba  mov     rdi, qword ptr [rbp+var_38]
0x1801261be  mov     rsi, qword ptr [rbp+var_38+8]
0x1801261c2  jmp     short loc_180126218
0x1801261c4  mov     rcx, [rdi]
0x1801261c7  add     rcx, 8; lpPathName
0x1801261cb  xor     edx, edx; bWatchSubtree
0x1801261cd  lea     r8d, [rdx+11h]; dwNotifyFilter
0x1801261d1  call    cs:__imp_FindFirstChangeNotificationW
0x1801261d7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801261db  jz      short loc_180126214
0x1801261dd  mov     [rbp+arg_8], rax
0x1801261e1  mov     rdx, [rbx+18h]
0x1801261e5  cmp     rdx, [rbx+20h]
0x1801261e9  jz      short loc_1801261FD
0x1801261eb  mov     [rdx], rax
0x1801261ee  mov     [rbp+arg_8], 0
0x1801261f6  add     qword ptr [rbx+18h], 8
0x1801261fb  jmp     short loc_18012620B
0x1801261fd  lea     r8, [rbp+arg_8]
0x180126201  lea     rcx, [rbx+10h]
0x180126205  call    ??$_Emplace_reallocate@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@@?$vector@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@V?$allocator@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@@std@@@std@@AEAAPEAV?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@QEAV2@$$QEAV2@@Z; std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Emplace_reallocate<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>(ScopedHandle<FileChangeNotificationHandlePolicy,void *> * const,ScopedHandle<FileChangeNotificationHandlePolicy,void *> &&)
0x18012620a  nop
0x18012620b  lea     rcx, [rbp+arg_8]
0x18012620f  call    ??1?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@QEAA@XZ; ScopedHandle<FileChangeNotificationHandlePolicy,void *>::~ScopedHandle<FileChangeNotificationHandlePolicy,void *>(void)
0x180126214  add     rdi, 8
0x180126218  cmp     rdi, rsi
0x18012621b  jnz     short loc_1801261C4
0x18012621d  mov     r8, [rbp+arg_10]
0x180126221  mov     rdx, [r8+8]
0x180126225  sub     rdx, [r8]
0x180126228  sar     rdx, 3
0x18012622c  mov     rbx, 6DB6DB6DB6DB6DB7h
0x180126236  imul    rdx, rbx
0x18012623a  mov     rax, [rbp+var_18]
0x18012623e  sub     rax, [rbp+var_20]
0x180126242  sar     rax, 3
0x180126246  imul    rax, rbx
0x18012624a  add     rdx, rax
0x18012624d  mov     [rbp+arg_8], rdx
0x180126251  mov     rax, [r8+10h]
0x180126255  sub     rax, [r8]
0x180126258  sar     rax, 3
0x18012625c  imul    rax, rbx
0x180126260  cmp     rdx, rax
0x180126263  jbe     short loc_180126292
0x180126265  mov     rax, 492492492492492h
0x18012626f  cmp     rdx, rax
0x180126272  jbe     short loc_180126282
0x180126274  lea     rcx, aVectorTooLong; "vector too long"
0x18012627b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180126282  lea     rdx, [rbp+arg_8]
0x180126286  mov     rcx, r8
0x180126289  call    ??$_Reallocate@$0A@@?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@AEAAXAEA_K@Z; std::vector<InstalledFontFileInfo>::_Reallocate<0>(unsigned __int64 &)
0x18012628e  mov     r8, [rbp+arg_10]
0x180126292  mov     r15, [rbp+var_20]
0x180126296  mov     r13, [rbp+var_18]
0x18012629a  cmp     r15, r13
0x18012629d  jz      loc_180126419
0x1801262a3  mov     rdi, 6D756E65656C6966h
0x1801262ad  mov     rsi, 726F727265h
0x1801262b7  mov     rbx, 6D756E45746E6F46h
0x1801262c1  mov     r14, 676E696E726177h
0x1801262cb  test    r12, r12
0x1801262ce  jz      loc_180126383
0x1801262d4  mov     r9, r8
0x1801262d7  mov     r8, r15
0x1801262da  xor     edx, edx
0x1801262dc  mov     rcx, [rbp+arg_0]
0x1801262e0  call    ?TryConvertFileInfo@InstalledFontFileEnumerator@@AEAA_NPEAXAEBULocalFileInfo@1@AEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@@Z; InstalledFontFileEnumerator::TryConvertFileInfo(void *,InstalledFontFileEnumerator::LocalFileInfo const &,std::vector<InstalledFontFileInfo> &)
0x1801262e5  test    al, al
0x1801262e7  jnz     loc_18012636D
0x1801262ed  mov     r9, [rbp+arg_10]
0x1801262f1  mov     r8, r15
0x1801262f4  mov     rdx, r12
0x1801262f7  mov     rcx, [rbp+arg_0]
0x1801262fb  call    ?TryConvertFileInfo@InstalledFontFileEnumerator@@AEAA_NPEAXAEBULocalFileInfo@1@AEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@@Z; InstalledFontFileEnumerator::TryConvertFileInfo(void *,InstalledFontFileEnumerator::LocalFileInfo const &,std::vector<InstalledFontFileInfo> &)
0x180126300  test    al, al
0x180126302  jnz     short loc_18012636D
0x180126304  call    cs:__imp_GetLastError
0x18012630a  cmp     byte ptr [r15+30h], 0
0x18012630f  jz      short loc_180126343
0x180126311  cmp     qword ptr [r15+18h], 7
0x180126316  jbe     short loc_18012631D
0x180126318  mov     rdx, [r15]
0x18012631b  jmp     short loc_180126320
0x18012631d  mov     rdx, r15
0x180126320  mov     rcx, [rbp+arg_0]
0x180126324  add     rcx, 10h
0x180126328  mov     [rsp+80h+var_48], eax
0x18012632c  mov     [rsp+80h+var_50], rdx
0x180126331  mov     [rsp+80h+var_60], rdi
0x180126336  mov     r8, rsi
0x180126339  mov     rdx, rbx
0x18012633c  call    ??$LogEvent@JVEventTag@@IPEB_WK@EventLogger@@QEBAXVEventTag@@0J0IPEB_WK@Z; EventLogger::LogEvent<long,EventTag,uint,wchar_t const *,ulong>(EventTag,EventTag,long,EventTag,uint,wchar_t const *,ulong)
0x180126341  jmp     short loc_18012636D
0x180126343  cmp     qword ptr [r15+18h], 7
0x180126348  jbe     short loc_18012634F
0x18012634a  mov     rax, [r15]
0x18012634d  jmp     short loc_180126352
0x18012634f  mov     rax, r15
0x180126352  mov     rcx, [rbp+arg_0]
0x180126356  add     rcx, 10h
0x18012635a  mov     [rsp+80h+var_58], rax
0x18012635f  mov     r9, rdi
0x180126362  mov     r8, r14
0x180126365  mov     rdx, rbx
0x180126368  call    ??$LogEvent@VEventTag@@HPEB_W@EventLogger@@QEBAXVEventTag@@00HPEB_W@Z; EventLogger::LogEvent<EventTag,int,wchar_t const *>(EventTag,EventTag,EventTag,int,wchar_t const *)
0x18012636d  add     r15, 38h ; '8'
0x180126371  cmp     r15, r13
0x180126374  mov     r8, [rbp+arg_10]
0x180126378  jnz     loc_1801262D4
0x18012637e  jmp     loc_18012640F
0x180126383  mov     r12, [rbp+arg_0]
0x180126387  mov     r9, r8
0x18012638a  mov     r8, r15
0x18012638d  xor     edx, edx
0x18012638f  mov     rcx, r12
0x180126392  call    ?TryConvertFileInfo@InstalledFontFileEnumerator@@AEAA_NPEAXAEBULocalFileInfo@1@AEAV?$vector@UInstalledFontFileInfo@@V?$allocator@UInstalledFontFileInfo@@@std@@@std@@@Z; InstalledFontFileEnumerator::TryConvertFileInfo(void *,InstalledFontFileEnumerator::LocalFileInfo const &,std::vector<InstalledFontFileInfo> &)
0x180126397  test    al, al
0x180126399  jnz     short loc_1801263FE
0x18012639b  call    cs:__imp_GetLastError
0x1801263a1  cmp     byte ptr [r15+30h], 0
0x1801263a6  jz      short loc_1801263D7
0x1801263a8  cmp     qword ptr [r15+18h], 7
0x1801263ad  jbe     short loc_1801263B4
0x1801263af  mov     rdx, [r15]
0x1801263b2  jmp     short loc_1801263B7
0x1801263b4  mov     rdx, r15
0x1801263b7  lea     rcx, [r12+10h]
0x1801263bc  mov     [rsp+80h+var_48], eax
0x1801263c0  mov     [rsp+80h+var_50], rdx
0x1801263c5  mov     [rsp+80h+var_60], rdi
0x1801263ca  mov     r8, rsi
0x1801263cd  mov     rdx, rbx
0x1801263d0  call    ??$LogEvent@JVEventTag@@IPEB_WK@EventLogger@@QEBAXVEventTag@@0J0IPEB_WK@Z; EventLogger::LogEvent<long,EventTag,uint,wchar_t const *,ulong>(EventTag,EventTag,long,EventTag,uint,wchar_t const *,ulong)
0x1801263d5  jmp     short loc_1801263FE
0x1801263d7  cmp     qword ptr [r15+18h], 7
0x1801263dc  jbe     short loc_1801263E3
0x1801263de  mov     rax, [r15]
0x1801263e1  jmp     short loc_1801263E6
0x1801263e3  mov     rax, r15
0x1801263e6  lea     rcx, [r12+10h]
0x1801263eb  mov     [rsp+80h+var_58], rax
0x1801263f0  mov     r9, rdi
0x1801263f3  mov     r8, r14
0x1801263f6  mov     rdx, rbx
0x1801263f9  call    ??$LogEvent@VEventTag@@HPEB_W@EventLogger@@QEBAXVEventTag@@00HPEB_W@Z; EventLogger::LogEvent<EventTag,int,wchar_t const *>(EventTag,EventTag,EventTag,int,wchar_t const *)
0x1801263fe  add     r15, 38h ; '8'
0x180126402  cmp     r15, r13
0x180126405  mov     r8, [rbp+arg_10]
0x180126409  jnz     loc_180126387
0x18012640f  mov     rbx, 6DB6DB6DB6DB6DB7h
0x180126419  mov     rcx, qword ptr [rbp+var_38]
0x18012641d  test    rcx, rcx
0x180126420  jz      short loc_18012644F
0x180126422  mov     rdx, qword ptr [rbp+var_38+8]
0x180126426  call    ??$_Destroy_range@V?$allocator@VRefString@DWrite@@@std@@@std@@YAXPEAVRefString@DWrite@@QEAV12@AEAV?$allocator@VRefString@DWrite@@@0@@Z; std::_Destroy_range<std::allocator<DWrite::RefString>>(DWrite::RefString *,DWrite::RefString * const,std::allocator<DWrite::RefString> &)
0x18012642b  mov     rcx, qword ptr [rbp+var_38]
0x18012642f  mov     rdx, [rbp+var_28]
0x180126433  sub     rdx, rcx
0x180126436  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18012643a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012643f  xorps   xmm0, xmm0
0x180126442  movdqu  [rbp+var_38], xmm0
0x180126447  mov     [rbp+var_28], 0
0x18012644f  mov     rcx, [rbp+var_20]; this
0x180126453  test    rcx, rcx
0x180126456  jz      short loc_18012647D
0x180126458  mov     rdx, [rbp+var_18]
0x18012645c  call    ??$_Destroy_range@V?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@std@@@std@@YAXPEAULocalFileInfo@InstalledFontFileEnumerator@@QEAU12@AEAV?$allocator@ULocalFileInfo@InstalledFontFileEnumerator@@@0@@Z; std::_Destroy_range<std::allocator<InstalledFontFileEnumerator::LocalFileInfo>>(InstalledFontFileEnumerator::LocalFileInfo *,InstalledFontFileEnumerator::LocalFileInfo * const,std::allocator<InstalledFontFileEnumerator::LocalFileInfo> &)
0x180126461  mov     rcx, [rbp+var_20]
0x180126465  mov     rax, [rbp+var_10]
0x180126469  sub     rax, rcx
0x18012646c  sar     rax, 3
0x180126470  imul    rax, rbx
0x180126474  imul    rdx, rax, 38h ; '8'
0x180126478  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012647d  mov     rbx, [rsp+80h+arg_18]
0x180126485  add     rsp, 80h
0x18012648c  pop     r15
0x18012648e  pop     r14
0x180126490  pop     r13
0x180126492  pop     r12
0x180126494  pop     rdi
0x180126495  pop     rsi
0x180126496  pop     rbp
0x180126497  retn
```
