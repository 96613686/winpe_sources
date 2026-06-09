# CMDCOM::ComMDPublish(void)

- ea: `0x180018f60`
- end: `0x180019109`
- name: `?ComMDPublish@CMDCOM@@UEAAJXZ`
- size: `425`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000a528`
- `0x18000e9b8`
- `0x180018f60`
- `0x18001d6d4`
- `0x18001f638`
- `0x180020f18`
- `0x180023be0`
- `0x180028f34`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180019084`
- `ole32!CoTaskMemFree` at `0x180019084`
- `KERNEL32!ReleaseSemaphore` at `0x180019073`
- `KERNEL32!ReleaseSemaphore` at `0x180019073`
- `KERNEL32!DeleteFileW` at `0x180019059`
- `KERNEL32!DeleteFileW` at `0x180019059`
- `KERNEL32!LeaveCriticalSection` at `0x1800190df`
- `KERNEL32!LeaveCriticalSection` at `0x1800190df`
- `KERNEL32!EnterCriticalSection` at `0x18001908e`
- `KERNEL32!EnterCriticalSection` at `0x18001908e`
- `IisRTL!ScheduleWorkItem` at `0x1800190bf`
- `IisRTL!ScheduleWorkItem` at `0x1800190bf`
- `IisRTL!RemoveWorkItem` at `0x1800190ed`
- `IisRTL!RemoveWorkItem` at `0x1800190ed`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDPublish(CMDCOM *this)
{
  int v2; // ebx
  unsigned int v3; // r14d
  int inited; // eax
  const unsigned __int16 *v5; // rcx
  _BYTE *v6; // rsi
  unsigned __int16 *v7; // rcx
  _QWORD v9[2]; // [rsp+30h] [rbp-30h] BYREF
  int v10; // [rsp+40h] [rbp-20h]
  __int128 v11; // [rsp+48h] [rbp-18h]
  __int64 v12; // [rsp+58h] [rbp-8h]
  unsigned int v13; // [rsp+98h] [rbp+38h] BYREF
  int v14; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF

  v14 = 0;
  v9[0] = &IIS_CRYPTO_STORAGE::`vftable';
  v9[1] = 0;
  v10 = 0;
  v12 = 0;
  pv = 0;
  v13 = 0;
  v11 = 0;
  if ( g_dwInitialized )
  {
    if ( (unsigned int)ShouldDoPublish() )
    {
      v3 = 0;
      v2 = AttemptNetConnection();
      if ( v2 >= 0 )
      {
        inited = InitStorageAndSessionKey((struct IIS_CRYPTO_STORAGE *)v9, (struct _IIS_CRYPTO_BLOB **)&pv);
        v6 = pv;
        v2 = inited;
        if ( inited >= 0 )
        {
          v2 = SaveDataTo(v5, this, (struct IIS_CRYPTO_STORAGE *)v9, (struct _IIS_CRYPTO_BLOB *)pv, &v13, &v14);
          if ( v2 >= 0 )
          {
            v2 = DoRemoteTempFileDance(v7);
            if ( v2 < 0 || (v2 = MoveFileToHistoryAndCopySchema(g_wszTempFileName, g_wszSchemaFileName, v13), v2 < 0) )
              DeleteFileW(g_wszTempFileName);
            else
              v2 = 0;
          }
          if ( v14 )
            ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
        }
        if ( v6 )
        {
          *v6 = 88;
          CoTaskMemFree(v6);
        }
      }
      EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
      if ( v2 < 0 && *((_DWORD *)this + 13) )
      {
        if ( !*((_DWORD *)this + 30) )
          *((_DWORD *)this + 30) = ScheduleWorkItem(
                                     (void (*)(void *))CMDCOM::MetabasePublishCallback,
                                     this,
                                     1000 * g_dwUNCRetryInterval,
                                     1);
      }
      else if ( *((_DWORD *)this + 30) )
      {
        v3 = *((_DWORD *)this + 30);
        *((_DWORD *)this + 30) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
      if ( v3 )
        RemoveWorkItem(v3);
    }
    else
    {
      v2 = 1;
    }
  }
  else
  {
    v2 = -2146646016;
  }
  IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE((IIS_CRYPTO_STORAGE *)v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180018f60  push    rbp
0x180018f62  push    rbx
0x180018f63  push    rsi
0x180018f64  push    rdi
0x180018f65  push    r14
0x180018f67  mov     rbp, rsp
0x180018f6a  sub     rsp, 60h
0x180018f6e  lea     rax, ??_7IIS_CRYPTO_STORAGE@@6B@; const IIS_CRYPTO_STORAGE::`vftable'
0x180018f75  mov     [rbp+arg_10], 0
0x180018f7c  mov     [rbp+var_30], rax
0x180018f80  xorps   xmm0, xmm0
0x180018f83  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180018f89  mov     rdi, rcx
0x180018f8c  mov     [rbp+var_28], 0
0x180018f94  mov     [rbp+var_20], 0
0x180018f9b  mov     [rbp+var_8], 0
0x180018fa3  mov     [rbp+pv], 0
0x180018fab  mov     [rbp+arg_8], 0
0x180018fb2  movdqu  [rbp+var_18], xmm0
0x180018fb7  test    eax, eax
0x180018fb9  jnz     short loc_180018FC5
0x180018fbb  mov     ebx, 800CC800h
0x180018fc0  jmp     loc_1800190F3
0x180018fc5  call    ?ShouldDoPublish@@YAHXZ; ShouldDoPublish(void)
0x180018fca  test    eax, eax
0x180018fcc  jnz     short loc_180018FD6
0x180018fce  lea     ebx, [rax+1]
0x180018fd1  jmp     loc_1800190F3
0x180018fd6  xor     r14d, r14d
0x180018fd9  call    ?AttemptNetConnection@@YAJXZ; AttemptNetConnection(void)
0x180018fde  mov     ebx, eax
0x180018fe0  test    eax, eax
0x180018fe2  js      loc_18001908A
0x180018fe8  lea     rdx, [rbp+pv]; struct _IIS_CRYPTO_BLOB **
0x180018fec  lea     rcx, [rbp+var_30]; this
0x180018ff0  call    ?InitStorageAndSessionKey@@YAJPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@@Z; InitStorageAndSessionKey(IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB * *)
0x180018ff5  mov     rsi, [rbp+pv]
0x180018ff9  mov     ebx, eax
0x180018ffb  test    eax, eax
0x180018ffd  js      short loc_180019079
0x180018fff  lea     rax, [rbp+arg_10]
0x180019003  mov     r9, rsi; struct _IIS_CRYPTO_BLOB *
0x180019006  mov     [rsp+60h+var_38], rax; int *
0x18001900b  lea     r8, [rbp+var_30]; struct IIS_CRYPTO_STORAGE *
0x18001900f  lea     rax, [rbp+arg_8]
0x180019013  mov     rdx, rdi; struct IMDCOM *
0x180019016  mov     [rsp+60h+var_40], rax; unsigned int *
0x18001901b  call    ?SaveDataTo@@YAJPEBGPEAUIMDCOM@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEAKPEAH@Z; SaveDataTo(ushort const *,IMDCOM *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ulong *,int *)
0x180019020  mov     ebx, eax
0x180019022  test    eax, eax
0x180019024  js      short loc_18001905F
0x180019026  call    ?DoRemoteTempFileDance@@YAJPEAG@Z; DoRemoteTempFileDance(ushort *)
0x18001902b  mov     ebx, eax
0x18001902d  test    eax, eax
0x18001902f  js      short loc_180019052
0x180019031  mov     r8d, [rbp+arg_8]; unsigned int
0x180019035  mov     rdx, cs:?g_wszSchemaFileName@@3PEAGEA; unsigned __int16 *
0x18001903c  mov     rcx, cs:?g_wszTempFileName@@3PEAGEA; lpExistingFileName
0x180019043  call    ?MoveFileToHistoryAndCopySchema@@YAJPEAG0K@Z; MoveFileToHistoryAndCopySchema(ushort *,ushort *,ulong)
0x180019048  mov     ebx, eax
0x18001904a  test    eax, eax
0x18001904c  js      short loc_180019052
0x18001904e  xor     ebx, ebx
0x180019050  jmp     short loc_18001905F
0x180019052  mov     rcx, cs:?g_wszTempFileName@@3PEAGEA; lpFileName
0x180019059  call    cs:__imp_DeleteFileW
0x18001905f  cmp     [rbp+arg_10], r14d
0x180019063  jz      short loc_180019079
0x180019065  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x18001906c  xor     r8d, r8d; lpPreviousCount
0x18001906f  lea     edx, [r8+1]; lReleaseCount
0x180019073  call    cs:__imp_ReleaseSemaphore
0x180019079  test    rsi, rsi
0x18001907c  jz      short loc_18001908A
0x18001907e  mov     rcx, rsi; pv
0x180019081  mov     byte ptr [rsi], 58h ; 'X'
0x180019084  call    cs:__imp_CoTaskMemFree
0x18001908a  lea     rcx, [rdi+50h]; lpCriticalSection
0x18001908e  call    cs:__imp_EnterCriticalSection
0x180019094  test    ebx, ebx
0x180019096  jns     short loc_1800190CA
0x180019098  cmp     [rdi+34h], r14d
0x18001909c  jz      short loc_1800190CA
0x18001909e  cmp     [rdi+78h], r14d
0x1800190a2  jnz     short loc_1800190DB
0x1800190a4  imul    r8d, cs:?g_dwUNCRetryInterval@@3KA, 3E8h; ulong g_dwUNCRetryInterval
0x1800190af  lea     rcx, ?MetabasePublishCallback@CMDCOM@@CAXPEAX@Z; CMDCOM::MetabasePublishCallback(void *)
0x1800190b6  mov     r9d, 1
0x1800190bc  mov     rdx, rdi
0x1800190bf  call    cs:__imp_?ScheduleWorkItem@@YAKP6AXPEAX@Z0KH@Z; ScheduleWorkItem(void (*)(void *),void *,ulong,int)
0x1800190c5  mov     [rdi+78h], eax
0x1800190c8  jmp     short loc_1800190DB
0x1800190ca  cmp     [rdi+78h], r14d
0x1800190ce  jz      short loc_1800190DB
0x1800190d0  mov     r14d, [rdi+78h]
0x1800190d4  mov     dword ptr [rdi+78h], 0
0x1800190db  lea     rcx, [rdi+50h]; lpCriticalSection
0x1800190df  call    cs:__imp_LeaveCriticalSection
0x1800190e5  test    r14d, r14d
0x1800190e8  jz      short loc_1800190F3
0x1800190ea  mov     ecx, r14d
0x1800190ed  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x1800190f3  lea     rcx, [rbp+var_30]; this
0x1800190f7  call    ??1IIS_CRYPTO_STORAGE@@QEAA@XZ; IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(void)
0x1800190fc  mov     eax, ebx
0x1800190fe  add     rsp, 60h
0x180019102  pop     r14
0x180019104  pop     rdi
0x180019105  pop     rsi
0x180019106  pop     rbx
0x180019107  pop     rbp
0x180019108  retn
```
