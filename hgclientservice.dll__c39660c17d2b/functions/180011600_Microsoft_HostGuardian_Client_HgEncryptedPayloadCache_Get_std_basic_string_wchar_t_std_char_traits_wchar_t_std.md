# Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<uchar,std::allocator<uchar>> &,std::vector<uchar,std::allocator<uchar>> &,std::vector<uchar,std::allocator<uchar>> &,std::vector<uchar,std::allocator<uchar>> &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180011600`
- end: `0x180011842`
- name: `?Get@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@6@1111@Z`
- size: `578`
- prototype: `char __fastcall(RTL_SRWLOCK *, _QWORD *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e100`

## callees

- `0x180008760`
- `0x18000b8b0`
- `0x18000c45c`
- `0x18000c7f0`
- `0x180010f68`
- `0x180011008`
- `0x180011600`
- `0x180011a28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800116d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800116d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800117a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800117b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800117a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800117b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001163b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001163b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800116be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001180e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800116be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001180e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800116c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800116c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116b3`

## string_xrefs

- `0x180011830`: `servercommon\base\securehostingservice\common\service\lib\hgencryptedpayloadcache.cpp`

## pseudocode

```c
char __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get(
        RTL_SRWLOCK *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v11; // rdx
  unsigned __int64 v12; // rcx
  __int64 v13; // r9
  unsigned __int64 v14; // r8
  char *Ptr; // rdi
  DWORD LastError; // edi
  int v18; // [rsp+20h] [rbp-C1h]
  RTL_SRWLOCK *v19; // [rsp+40h] [rbp-A1h] BYREF
  _BYTE v20[24]; // [rsp+50h] [rbp-91h] BYREF
  _BYTE v21[24]; // [rsp+68h] [rbp-79h] BYREF
  _BYTE v22[24]; // [rsp+80h] [rbp-61h] BYREF
  _BYTE v23[24]; // [rsp+98h] [rbp-49h] BYREF
  _BYTE v24[24]; // [rsp+B0h] [rbp-31h] BYREF
  char v25[88]; // [rsp+C8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  if ( !a2[2] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgencryptedpayloadcache.cpp",
      (const char *)0x80070057LL,
      v18);
  AcquireSRWLockShared(a1 + 13);
  if ( a2[3] <= 7u )
    v11 = a2;
  else
    v11 = (_QWORD *)*a2;
  v12 = 0;
  v13 = 0xCBF29CE484222325uLL;
  v14 = 2LL * a2[2];
  if ( v14 )
  {
    do
      v13 = 0x100000001B3LL * (*((unsigned __int8 *)v11 + v12++) ^ (unsigned __int64)v13);
    while ( v12 < v14 );
  }
  Ptr = *(char **)(std::_Hash<std::_Umap_traits<std::wstring,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>,0>>::_Find_last<std::wstring>(
                     &a1[5],
                     &v19,
                     a2,
                     v13)
                 + 8);
  if ( !Ptr )
    Ptr = (char *)a1[6].Ptr;
  if ( Ptr != a1[6].Ptr )
  {
    std::vector<unsigned char>::operator=(a3, Ptr + 144);
    std::vector<unsigned char>::operator=(a4, Ptr + 120);
    std::vector<unsigned char>::operator=(a5, Ptr + 96);
    std::vector<unsigned char>::operator=(a6, Ptr + 72);
    std::vector<unsigned char>::operator=(a7, Ptr + 48);
    if ( a1 != (RTL_SRWLOCK *)-104LL )
      ReleaseSRWLockShared(a1 + 13);
    return 1;
  }
  if ( a1 != (RTL_SRWLOCK *)-104LL )
  {
    LastError = GetLastError();
    ReleaseSRWLockShared(a1 + 13);
    SetLastError(LastError);
  }
  AcquireSRWLockExclusive(a1 + 13);
  v19 = a1 + 13;
  if ( (unsigned __int8)Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::LoadFromStorage(
                          (int)a1,
                          (int)a2,
                          a5,
                          a6,
                          a7) )
  {
    std::vector<unsigned char>::vector<unsigned char>(v20, a7);
    std::vector<unsigned char>::vector<unsigned char>(v21, a6);
    std::vector<unsigned char>::vector<unsigned char>(v22, a5);
    std::vector<unsigned char>::vector<unsigned char>(v23, a4);
    std::vector<unsigned char>::vector<unsigned char>(v24, a3);
    std::unordered_map<std::wstring,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>::_Insert_or_assign<std::wstring const &,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>(
      &a1[5],
      v25,
      a2,
      v20);
    std::vector<unsigned char>::~vector<unsigned char>(v24);
    std::vector<unsigned char>::~vector<unsigned char>(v23);
    std::vector<unsigned char>::~vector<unsigned char>(v22);
    std::vector<unsigned char>::~vector<unsigned char>(v21);
    std::vector<unsigned char>::~vector<unsigned char>(v20);
    if ( a1 != (RTL_SRWLOCK *)-104LL )
      ReleaseSRWLockExclusive(a1 + 13);
    return 1;
  }
  if ( a1 != (RTL_SRWLOCK *)-104LL )
    ReleaseSRWLockExclusive(a1 + 13);
  return 0;
}

```

## disassembly

```asm
0x180011600  push    rbp
0x180011602  push    rbx
0x180011603  push    rsi
0x180011604  push    rdi
0x180011605  push    r12
0x180011607  push    r13
0x180011609  push    r14
0x18001160b  push    r15
0x18001160d  lea     rbp, [rsp-7]
0x180011612  sub     rsp, 0E8h
0x180011619  mov     r12, r9
0x18001161c  mov     r13, r8
0x18001161f  mov     rsi, rdx
0x180011622  mov     r14, rcx
0x180011625  mov     rcx, [rbp+47h]; this
0x180011629  cmp     qword ptr [rdx+10h], 0
0x18001162e  jz      loc_18001182A
0x180011634  lea     rbx, [r14+68h]
0x180011638  mov     rcx, rbx; SRWLock
0x18001163b  call    cs:__imp_AcquireSRWLockShared
0x180011641  mov     [rbp+3Fh+arg_8], rbx
0x180011645  mov     r8, [rsi+10h]
0x180011649  cmp     qword ptr [rsi+18h], 7
0x18001164e  jbe     short loc_180011655
0x180011650  mov     rdx, [rsi]
0x180011653  jmp     short loc_180011658
0x180011655  mov     rdx, rsi
0x180011658  xor     ecx, ecx
0x18001165a  mov     r9, 0CBF29CE484222325h
0x180011664  add     r8, r8
0x180011667  jz      short loc_180011686
0x180011669  movzx   eax, byte ptr [rdx+rcx]
0x18001166d  xor     r9, rax
0x180011670  mov     r10, 100000001B3h
0x18001167a  imul    r9, r10
0x18001167e  inc     rcx
0x180011681  cmp     rcx, r8
0x180011684  jb      short loc_180011669
0x180011686  mov     r8, rsi
0x180011689  lea     rdx, [rsp+120h+var_E0]
0x18001168e  lea     rcx, [r14+28h]
0x180011692  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180011697  mov     rdi, [rax+8]
0x18001169b  test    rdi, rdi
0x18001169e  jnz     short loc_1800116A4
0x1800116a0  mov     rdi, [r14+30h]
0x1800116a4  cmp     rdi, [r14+30h]
0x1800116a8  jnz     loc_1800117C3
0x1800116ae  test    rbx, rbx
0x1800116b1  jz      short loc_1800116CC
0x1800116b3  call    cs:__imp_GetLastError
0x1800116b9  mov     edi, eax
0x1800116bb  mov     rcx, rbx; SRWLock
0x1800116be  call    cs:__imp_ReleaseSRWLockShared
0x1800116c4  mov     ecx, edi; dwErrCode
0x1800116c6  call    cs:__imp_SetLastError
0x1800116cc  mov     [rbp+3Fh+arg_8], 0
0x1800116d4  mov     rcx, rbx; SRWLock
0x1800116d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800116dd  mov     [rsp+120h+var_E0], rbx
0x1800116e2  mov     rdi, [rbp+3Fh+arg_30]
0x1800116e6  mov     [rsp+120h+var_F0], rdi; __int64
0x1800116eb  mov     rax, [rbp+3Fh+arg_28]
0x1800116ef  mov     [rsp+120h+var_F8], rax; __int64
0x1800116f4  mov     rax, [rbp+3Fh+arg_20]
0x1800116f8  mov     [rsp+120h+var_100], rax; __int64
0x1800116fd  mov     r9, r12
0x180011700  mov     r8, r13
0x180011703  mov     rdx, rsi; int
0x180011706  mov     rcx, r14; int
0x180011709  call    ?LoadFromStorage@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@6@1111@Z; Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::LoadFromStorage(std::wstring const &,std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &)
0x18001170e  test    al, al
0x180011710  jz      loc_1800117B0
0x180011716  mov     rdx, rdi
0x180011719  lea     rcx, [rsp+120h+var_D0]
0x18001171e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180011723  nop
0x180011724  mov     rdx, [rbp+3Fh+arg_28]
0x180011728  lea     rcx, [rbp+3Fh+var_B8]
0x18001172c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180011731  nop
0x180011732  mov     rdx, [rbp+3Fh+arg_20]
0x180011736  lea     rcx, [rbp+3Fh+var_A0]
0x18001173a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18001173f  nop
0x180011740  mov     rdx, r12
0x180011743  lea     rcx, [rbp+3Fh+var_88]
0x180011747  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18001174c  nop
0x18001174d  mov     rdx, r13
0x180011750  lea     rcx, [rbp+3Fh+var_70]
0x180011754  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180011759  nop
0x18001175a  lea     r9, [rsp+120h+var_D0]
0x18001175f  mov     r8, rsi
0x180011762  lea     rdx, [rbp+3Fh+var_58]
0x180011766  lea     rcx, [r14+28h]
0x18001176a  call    ??$_Insert_or_assign@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@2@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@1@@Z; std::unordered_map<std::wstring,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>::_Insert_or_assign<std::wstring const &,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>(std::wstring const &,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>> &&)
0x18001176f  nop
0x180011770  lea     rcx, [rbp+3Fh+var_70]
0x180011774  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011779  lea     rcx, [rbp+3Fh+var_88]
0x18001177d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011782  lea     rcx, [rbp+3Fh+var_A0]
0x180011786  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001178b  lea     rcx, [rbp+3Fh+var_B8]
0x18001178f  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180011794  lea     rcx, [rsp+120h+var_D0]
0x180011799  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001179e  nop
0x18001179f  test    rbx, rbx
0x1800117a2  jz      short loc_1800117AE
0x1800117a4  mov     rcx, rbx; SRWLock
0x1800117a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800117ad  nop
0x1800117ae  jmp     short loc_180011814
0x1800117b0  test    rbx, rbx
0x1800117b3  jz      short loc_1800117BF
0x1800117b5  mov     rcx, rbx; SRWLock
0x1800117b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800117be  nop
0x1800117bf  xor     al, al
0x1800117c1  jmp     short loc_180011816
0x1800117c3  lea     rdx, [rdi+90h]
0x1800117ca  mov     rcx, r13
0x1800117cd  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x1800117d2  lea     rdx, [rdi+78h]
0x1800117d6  mov     rcx, r12
0x1800117d9  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x1800117de  lea     rdx, [rdi+60h]
0x1800117e2  mov     rcx, [rbp+3Fh+arg_20]
0x1800117e6  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x1800117eb  lea     rdx, [rdi+48h]
0x1800117ef  mov     rcx, [rbp+3Fh+arg_28]
0x1800117f3  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x1800117f8  lea     rdx, [rdi+30h]
0x1800117fc  mov     rcx, [rbp+3Fh+arg_30]
0x180011800  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x180011805  nop
0x180011806  test    rbx, rbx
0x180011809  jz      short loc_180011814
0x18001180b  mov     rcx, rbx; SRWLock
0x18001180e  call    cs:__imp_ReleaseSRWLockShared
0x180011814  mov     al, 1
0x180011816  add     rsp, 0E8h
0x18001181d  pop     r15
0x18001181f  pop     r14
0x180011821  pop     r13
0x180011823  pop     r12
0x180011825  pop     rdi
0x180011826  pop     rsi
0x180011827  pop     rbx
0x180011828  pop     rbp
0x180011829  retn
0x18001182a  mov     r9d, 80070057h; char *
0x180011830  lea     r8, aServercommonBa_7; "servercommon\\base\\securehostingservic"...
0x180011837  mov     edx, 33h ; '3'; void *
0x18001183c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
