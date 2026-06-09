# DAS::Dispatcher::Watchdog::AddTimestamp(void)

- ea: `0x18002410c`
- end: `0x18002418c`
- name: `?AddTimestamp@Watchdog@Dispatcher@DAS@@QEAAXXZ`
- size: `128`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180026cf0`

## callees

- `0x18002410c`
- `0x180024194`
- `0x18003bc80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024173`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024173`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024124`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024142`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024142`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002413c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002413c`

## pseudocode

```c
void __fastcall DAS::Dispatcher::Watchdog::AddTimestamp(PSRWLOCK SRWLock)
{
  _BYTE v2[16]; // [rsp+28h] [rbp-50h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-40h] BYREF
  DWORD CurrentThreadId; // [rsp+48h] [rbp-30h] BYREF
  _SYSTEMTIME v5; // [rsp+4Ch] [rbp-2Ch]

  AcquireSRWLockExclusive(SRWLock);
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  CurrentThreadId = GetCurrentThreadId();
  v5 = SystemTime;
  std::_Tree<std::_Tmap_traits<unsigned long,_SYSTEMTIME,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,_SYSTEMTIME>>,0>>::_Emplace<std::pair<unsigned long const,_SYSTEMTIME>>(
    &SRWLock[1],
    v2,
    &CurrentThreadId);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x18002410c  push    rbx
0x18002410e  sub     rsp, 70h
0x180024112  mov     rax, cs:__security_cookie
0x180024119  xor     rax, rsp
0x18002411c  mov     [rsp+78h+var_18], rax
0x180024121  mov     rbx, rcx
0x180024124  call    cs:__imp_AcquireSRWLockExclusive
0x18002412a  mov     [rsp+78h+var_58], rbx
0x18002412f  xorps   xmm0, xmm0
0x180024132  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x180024137  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x18002413c  call    cs:__imp_GetSystemTime
0x180024142  call    cs:__imp_GetCurrentThreadId
0x180024148  mov     [rsp+78h+var_30], eax
0x18002414c  movups  xmm0, xmmword ptr [rsp+78h+SystemTime.wYear]
0x180024151  movdqu  [rsp+78h+var_2C], xmm0
0x180024157  lea     rcx, [rbx+8]
0x18002415b  lea     r8, [rsp+78h+var_30]
0x180024160  lea     rdx, [rsp+78h+var_50]
0x180024165  call    ??$_Emplace@U?$pair@$$CBKU_SYSTEMTIME@@@std@@@?$_Tree@V?$_Tmap_traits@KU_SYSTEMTIME@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_SYSTEMTIME@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKU_SYSTEMTIME@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CBKU_SYSTEMTIME@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,_SYSTEMTIME,std::less<ulong>,std::allocator<std::pair<ulong const,_SYSTEMTIME>>,0>>::_Emplace<std::pair<ulong const,_SYSTEMTIME>>(std::pair<ulong const,_SYSTEMTIME> &&)
0x18002416a  nop
0x18002416b  test    rbx, rbx
0x18002416e  jz      short loc_180024179
0x180024170  mov     rcx, rbx; SRWLock
0x180024173  call    cs:__imp_ReleaseSRWLockExclusive
0x180024179  mov     rcx, [rsp+78h+var_18]
0x18002417e  xor     rcx, rsp; StackCookie
0x180024181  call    __security_check_cookie
0x180024186  add     rsp, 70h
0x18002418a  pop     rbx
0x18002418b  retn
```
