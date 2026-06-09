# TOKEN_CACHE::Initialize(void)

- ea: `0x180001fd8`
- end: `0x1800021f3`
- name: `?Initialize@TOKEN_CACHE@@QEAAJXZ`
- size: `539`
- prototype: `__int64 __fastcall(TOKEN_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002320`

## callees

- `0x180001530`
- `0x180001fd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800020ce`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800020ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002026`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002026`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000205a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000205a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002078`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000212d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000218e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000212d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000218e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002184`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002184`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000211e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000211e`
- `iisutil!PuDbgPrint` at `0x1800021d7`
- `iisutil!PuDbgPrint` at `0x1800021d7`

## string_xrefs

- `0x180001fed`: `System\CurrentControlSet\Services\inetinfo\Parameters`
- `0x18000204e`: `UserTokenTTL`
- `0x1800020a9`: `CreateEvent() failed. hr = 0x%x\n`
- `0x1800021c0`: `TOKEN_CACHE::Initialize`
- `0x1800021cb`: `servercommon\inetsrv\iis\iisrearc\iis70\token_cache\token_cache.cxx`
- `0x1800021ac`: `CreateTimerQueueTimer() failed. hr = 0x%x\n`

## pseudocode

```c
__int64 __fastcall TOKEN_CACHE::Initialize(TOKEN_CACHE *this)
{
  PVOID v1; // rdi
  HKEY *v2; // rbx
  int v3; // esi
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  LSTATUS v9; // eax
  __int64 v10; // rax
  signed int v11; // eax
  signed int v12; // eax
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF
  int v15; // [rsp+64h] [rbp+Ch]
  int Data; // [rsp+68h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF

  v15 = HIDWORD(this);
  v1 = g_pTokenCache;
  Data = 0;
  Type = 0;
  cbData = 4;
  v2 = (HKEY *)((char *)g_pTokenCache + 80);
  v3 = 900;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          (PHKEY)g_pTokenCache + 10) )
  {
    if ( !RegQueryValueExW(*v2, L"UserTokenTTL", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v3 = Data;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v1 + 11) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_26;
      v7 = "CreateEvent() failed. hr = 0x%x\n";
      v8 = 259;
LABEL_25:
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\token_cache\\token_cache.cxx",
        v8,
        "TOKEN_CACHE::Initialize",
        v7,
        v6);
LABEL_26:
      TOKEN_CACHE::Terminate((TOKEN_CACHE *)v1);
      return v6;
    }
    v9 = RegNotifyChangeKeyValue(*v2, 1, 4u, EventW, 1);
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_26;
      v7 = "RegNotifyChangeKeyValue failed. hr = 0x%x\n";
      v8 = 281;
      goto LABEL_25;
    }
    v10 = RegisterWaitForSingleObjectEx(
            *((_QWORD *)v1 + 11),
            TOKEN_CACHE::FlushTokenCacheWaitCallback,
            v1,
            0xFFFFFFFFLL,
            128);
    *((_QWORD *)v1 + 12) = v10;
    if ( !v10 )
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_26;
      v7 = "RegisterWaitForSingleObject failed. hr = 0x%x\n";
      v8 = 311;
      goto LABEL_25;
    }
  }
  if ( !CreateTimerQueueTimer((PHANDLE)v1 + 9, 0, TOKEN_CACHE::ScavengerCallback, v1, 1000 * v3, 1000 * v3, 0x10u) )
  {
    v12 = GetLastError();
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_26;
    v7 = "CreateTimerQueueTimer() failed. hr = 0x%x\n";
    v8 = 329;
    goto LABEL_25;
  }
  return 0;
}

```

## disassembly

```asm
0x180001fd8  mov     rax, rsp
0x180001fdb  mov     [rax+8], rcx
0x180001fdf  push    rbx
0x180001fe0  push    rsi
0x180001fe1  push    rdi
0x180001fe2  sub     rsp, 40h
0x180001fe6  mov     rdi, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; TOKEN_CACHE * g_pTokenCache
0x180001fed  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x180001ff4  mov     r9d, 20019h; samDesired
0x180001ffa  mov     dword ptr [rax+10h], 0
0x180002001  xor     r8d, r8d; ulOptions
0x180002004  mov     dword ptr [rax+8], 0
0x18000200b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002012  mov     dword ptr [rax+18h], 4
0x180002019  lea     rbx, [rdi+50h]
0x18000201d  mov     esi, 384h
0x180002022  mov     [rax-38h], rbx
0x180002026  call    cs:__imp_RegOpenKeyExW
0x18000202c  test    eax, eax
0x18000202e  jnz     loc_18000215E
0x180002034  mov     rcx, [rbx]; hKey
0x180002037  lea     rax, [rsp+58h+cbData]
0x18000203c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180002041  lea     r9, [rsp+58h+Type]; lpType
0x180002046  lea     rax, [rsp+58h+Data]
0x18000204b  xor     r8d, r8d; lpReserved
0x18000204e  lea     rdx, aUsertokenttl; "UserTokenTTL"
0x180002055  mov     [rsp+58h+lpData], rax; lpData
0x18000205a  call    cs:__imp_RegQueryValueExW
0x180002060  test    eax, eax
0x180002062  jnz     short loc_18000206E
0x180002064  cmp     [rsp+58h+Type], 4
0x180002069  cmovz   esi, [rsp+58h+Data]
0x18000206e  xor     r9d, r9d; lpName
0x180002071  xor     r8d, r8d; bInitialState
0x180002074  xor     edx, edx; bManualReset
0x180002076  xor     ecx, ecx; lpEventAttributes
0x180002078  call    cs:__imp_CreateEventW
0x18000207e  mov     [rdi+58h], rax
0x180002082  test    rax, rax
0x180002085  jnz     short loc_1800020BB
0x180002087  call    cs:__imp_GetLastError
0x18000208d  mov     ebx, eax
0x18000208f  test    eax, eax
0x180002091  jle     short loc_18000209C
0x180002093  movzx   ebx, ax
0x180002096  or      ebx, 80070000h
0x18000209c  test    cs:g_dwDebugFlags, 3
0x1800020a3  jz      loc_1800021DD
0x1800020a9  lea     rax, aCreateeventFai; "CreateEvent() failed. hr = 0x%x\n"
0x1800020b0  mov     r8d, 103h
0x1800020b6  jmp     loc_1800021B9
0x1800020bb  mov     rcx, [rbx]; hKey
0x1800020be  mov     edx, 1; bWatchSubtree
0x1800020c3  mov     r9, rax; hEvent
0x1800020c6  mov     dword ptr [rsp+58h+lpData], edx; fAsynchronous
0x1800020ca  lea     r8d, [rdx+3]; dwNotifyFilter
0x1800020ce  call    cs:__imp_RegNotifyChangeKeyValue
0x1800020d4  mov     ebx, eax
0x1800020d6  test    eax, eax
0x1800020d8  jz      short loc_180002104
0x1800020da  jle     short loc_1800020E5
0x1800020dc  movzx   ebx, ax
0x1800020df  or      ebx, 80070000h
0x1800020e5  test    cs:g_dwDebugFlags, 3
0x1800020ec  jz      loc_1800021DD
0x1800020f2  lea     rax, aRegnotifychang; "RegNotifyChangeKeyValue failed. hr = 0x"...
0x1800020f9  mov     r8d, 119h
0x1800020ff  jmp     loc_1800021B9
0x180002104  mov     rcx, [rdi+58h]
0x180002108  lea     rdx, ?FlushTokenCacheWaitCallback@TOKEN_CACHE@@SAXPEAXE@Z; TOKEN_CACHE::FlushTokenCacheWaitCallback(void *,uchar)
0x18000210f  or      r9d, 0FFFFFFFFh
0x180002113  mov     dword ptr [rsp+58h+lpData], 80h
0x18000211b  mov     r8, rdi
0x18000211e  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180002124  mov     [rdi+60h], rax
0x180002128  test    rax, rax
0x18000212b  jnz     short loc_18000215E
0x18000212d  call    cs:__imp_GetLastError
0x180002133  mov     ebx, eax
0x180002135  test    eax, eax
0x180002137  jle     short loc_180002142
0x180002139  movzx   ebx, ax
0x18000213c  or      ebx, 80070000h
0x180002142  test    cs:g_dwDebugFlags, 3
0x180002149  jz      loc_1800021DD
0x18000214f  lea     rax, aRegisterwaitfo; "RegisterWaitForSingleObject failed. hr "...
0x180002156  mov     r8d, 137h
0x18000215c  jmp     short loc_1800021B9
0x18000215e  imul    eax, esi, 3E8h
0x180002164  lea     rcx, [rdi+48h]; phNewTimer
0x180002168  mov     [rsp+58h+Flags], 10h; Flags
0x180002170  lea     r8, ?ScavengerCallback@TOKEN_CACHE@@CAXPEAXE@Z; Callback
0x180002177  mov     r9, rdi; Parameter
0x18000217a  xor     edx, edx; TimerQueue
0x18000217c  mov     dword ptr [rsp+58h+lpcbData], eax; Period
0x180002180  mov     dword ptr [rsp+58h+lpData], eax; DueTime
0x180002184  call    cs:__imp_CreateTimerQueueTimer
0x18000218a  test    eax, eax
0x18000218c  jnz     short loc_1800021E9
0x18000218e  call    cs:__imp_GetLastError
0x180002194  mov     ebx, eax
0x180002196  test    eax, eax
0x180002198  jle     short loc_1800021A3
0x18000219a  movzx   ebx, ax
0x18000219d  or      ebx, 80070000h
0x1800021a3  test    cs:g_dwDebugFlags, 3
0x1800021aa  jz      short loc_1800021DD
0x1800021ac  lea     rax, aCreatetimerque; "CreateTimerQueueTimer() failed. hr = 0x"...
0x1800021b3  mov     r8d, 149h
0x1800021b9  mov     rcx, cs:g_pDebug
0x1800021c0  lea     r9, aTokenCacheInit; "TOKEN_CACHE::Initialize"
0x1800021c7  mov     dword ptr [rsp+58h+lpcbData], ebx
0x1800021cb  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800021d2  mov     [rsp+58h+lpData], rax
0x1800021d7  call    cs:__imp_PuDbgPrint
0x1800021dd  mov     rcx, rdi; this
0x1800021e0  call    ?Terminate@TOKEN_CACHE@@QEAAXXZ; TOKEN_CACHE::Terminate(void)
0x1800021e5  mov     eax, ebx
0x1800021e7  jmp     short loc_1800021EB
0x1800021e9  xor     eax, eax
0x1800021eb  add     rsp, 40h
0x1800021ef  pop     rdi
0x1800021f0  pop     rsi
0x1800021f1  pop     rbx
0x1800021f2  retn
```
