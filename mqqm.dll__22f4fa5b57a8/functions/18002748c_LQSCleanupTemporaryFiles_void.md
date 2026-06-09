# LQSCleanupTemporaryFiles(void)

- ea: `0x18002748c`
- end: `0x180027660`
- name: `?LQSCleanupTemporaryFiles@@YAXXZ`
- size: `468`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x18002e010`

## callees

- `0x180009924`
- `0x18000bab8`
- `0x18000bb04`
- `0x18000cb80`
- `0x18000e558`
- `0x18002748c`
- `0x1800280a8`
- `0x18002c61c`
- `0x1800d08f8`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800275bb`
- `KERNEL32!GetLastError` at `0x1800275bb`
- `KERNEL32!LeaveCriticalSection` at `0x180027519`
- `KERNEL32!LeaveCriticalSection` at `0x180027555`
- `KERNEL32!LeaveCriticalSection` at `0x18002761d`
- `KERNEL32!LeaveCriticalSection` at `0x18002763e`
- `KERNEL32!LeaveCriticalSection` at `0x180027519`
- `KERNEL32!LeaveCriticalSection` at `0x180027555`
- `KERNEL32!LeaveCriticalSection` at `0x18002761d`
- `KERNEL32!LeaveCriticalSection` at `0x18002763e`
- `KERNEL32!FindClose` at `0x180027613`
- `KERNEL32!FindClose` at `0x180027613`
- `KERNEL32!FindFirstFileW` at `0x180027543`
- `KERNEL32!FindFirstFileW` at `0x180027543`
- `KERNEL32!FindNextFileW` at `0x180027602`
- `KERNEL32!FindNextFileW` at `0x180027602`
- `KERNEL32!DeleteFileW` at `0x1800275b1`
- `KERNEL32!DeleteFileW` at `0x1800275b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void LQSCleanupTemporaryFiles(void)
{
  unsigned int v0; // ebx
  wchar_t *v1; // rax
  int v2; // eax
  HANDLE FirstFileW; // rdi
  unsigned int v4; // ebx
  wchar_t *v5; // rax
  int v6; // eax
  char LastError; // al
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v9[312]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR FileName[312]; // [rsp+500h] [rbp+400h] BYREF

  CCriticalSection::Lock((CCriticalSection *)&stru_18013A368);
  v0 = 306 - mqwcslen(FileName);
  v1 = (wchar_t *)LQSGetDirectory(FileName);
  v2 = StringCchPrintfW(v1, v0, L"*%s", L".tmp");
  if ( v2 >= 0 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LeaveCriticalSection(&stru_18013A368);
    }
    else
    {
      while ( 1 )
      {
        LODWORD(qword_1801291DC) = qword_1801291DC + 1;
        HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
        SetStatus();
        v4 = 306 - mqwcslen(v9);
        v5 = (wchar_t *)LQSGetDirectory(v9);
        v6 = StringCchCopyW(v5, v4, FindFileData.cFileName);
        if ( v6 < 0 )
          break;
        if ( !DeleteFileW(v9) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          FindClose(FirstFileW);
          LeaveCriticalSection(&stru_18013A368);
          return;
        }
      }
      LogMsgHR(v6, (wchar_t *)L"lqs", 0x1446u);
      LeaveCriticalSection(&stru_18013A368);
    }
  }
  else
  {
    LogMsgHR(v2, (wchar_t *)L"lqs", 0x143Cu);
    LeaveCriticalSection(&stru_18013A368);
  }
}

```

## disassembly

```asm
0x18002748c  push    rbp
0x18002748e  push    rbx
0x18002748f  push    rsi
0x180027490  push    rdi
0x180027491  lea     rbp, [rsp-688h]
0x180027499  sub     rsp, 788h
0x1800274a0  mov     rax, cs:__security_cookie
0x1800274a7  xor     rax, rsp
0x1800274aa  mov     [rbp+6A0h+var_30], rax
0x1800274b1  lea     rsi, stru_18013A368
0x1800274b8  mov     [rsp+7A0h+var_770], rsi
0x1800274bd  mov     rcx, rsi; this
0x1800274c0  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800274c5  nop
0x1800274c6  lea     rcx, [rbp+6A0h+FileName]; wchar_t *
0x1800274cd  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800274d2  mov     ebx, 132h
0x1800274d7  sub     ebx, eax
0x1800274d9  lea     rcx, [rbp+6A0h+FileName]; wchar_t *
0x1800274e0  call    LQSGetDirectory
0x1800274e5  lea     r9, aTmp; ".tmp"
0x1800274ec  lea     r8, aS_3; "*%s"
0x1800274f3  mov     edx, ebx; unsigned __int64
0x1800274f5  mov     rcx, rax; wchar_t *
0x1800274f8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800274fd  test    eax, eax
0x1800274ff  jns     short loc_180027525
0x180027501  mov     r8d, 143Ch; unsigned __int16
0x180027507  lea     rdx, aLqs_0; "lqs"
0x18002750e  mov     ecx, eax; int
0x180027510  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180027515  nop
0x180027516  mov     rcx, rsi; lpCriticalSection
0x180027519  call    cs:__imp_LeaveCriticalSection
0x18002751f  nop
0x180027520  jmp     loc_180027645
0x180027525  xor     edx, edx; Val
0x180027527  mov     r8d, 250h; Size
0x18002752d  lea     rcx, [rsp+7A0h+FindFileData]; void *
0x180027532  call    memset_0
0x180027537  lea     rdx, [rsp+7A0h+FindFileData]; lpFindFileData
0x18002753c  lea     rcx, [rbp+6A0h+FileName]; lpFileName
0x180027543  call    cs:__imp_FindFirstFileW
0x180027549  mov     rdi, rax
0x18002754c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027550  jnz     short loc_180027561
0x180027552  mov     rcx, rsi; lpCriticalSection
0x180027555  call    cs:__imp_LeaveCriticalSection
0x18002755b  nop
0x18002755c  jmp     loc_180027645
0x180027561  inc     dword ptr cs:qword_1801291DC
0x180027567  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x18002756d  mov     dword ptr cs:qword_1801291DC+4, eax
0x180027573  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x180027578  lea     rcx, [rbp+6A0h+var_510]; wchar_t *
0x18002757f  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027584  mov     ebx, 132h
0x180027589  sub     ebx, eax
0x18002758b  lea     rcx, [rbp+6A0h+var_510]; wchar_t *
0x180027592  call    LQSGetDirectory
0x180027597  lea     r8, [rsp+7A0h+FindFileData.cFileName]; wchar_t *
0x18002759c  mov     edx, ebx; unsigned __int64
0x18002759e  mov     rcx, rax; wchar_t *
0x1800275a1  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800275a6  test    eax, eax
0x1800275a8  js      short loc_180027626
0x1800275aa  lea     rcx, [rbp+6A0h+var_510]; lpFileName
0x1800275b1  call    cs:__imp_DeleteFileW
0x1800275b7  test    eax, eax
0x1800275b9  jnz     short loc_1800275FA
0x1800275bb  call    cs:__imp_GetLastError
0x1800275c1  lea     rdx, WPP_GLOBAL_Control
0x1800275c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275cf  cmp     rcx, rdx
0x1800275d2  jz      short loc_1800275FA
0x1800275d4  test    byte ptr [rcx+1Ch], 1
0x1800275d8  jz      short loc_1800275FA
0x1800275da  mov     edx, 2Ah ; '*'
0x1800275df  mov     dword ptr [rsp+7A0h+var_780], eax; char
0x1800275e3  lea     r9, [rbp+6A0h+var_510]
0x1800275ea  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x1800275f1  mov     rcx, [rcx+10h]; LoggerHandle
0x1800275f5  call    WPP_SF_Sd
0x1800275fa  lea     rdx, [rsp+7A0h+FindFileData]; lpFindFileData
0x1800275ff  mov     rcx, rdi; hFindFile
0x180027602  call    cs:__imp_FindNextFileW
0x180027608  test    eax, eax
0x18002760a  jnz     loc_180027561
0x180027610  mov     rcx, rdi; hFindFile
0x180027613  call    cs:__imp_FindClose
0x180027619  nop
0x18002761a  mov     rcx, rsi; lpCriticalSection
0x18002761d  call    cs:__imp_LeaveCriticalSection
0x180027623  nop
0x180027624  jmp     short loc_180027645
0x180027626  mov     r8d, 1446h; unsigned __int16
0x18002762c  lea     rdx, aLqs_0; "lqs"
0x180027633  mov     ecx, eax; int
0x180027635  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002763a  nop
0x18002763b  mov     rcx, rsi; lpCriticalSection
0x18002763e  call    cs:__imp_LeaveCriticalSection
0x180027644  nop
0x180027645  mov     rcx, [rbp+6A0h+var_30]
0x18002764c  xor     rcx, rsp; StackCookie
0x18002764f  call    __security_check_cookie
0x180027654  add     rsp, 788h
0x18002765b  pop     rdi
0x18002765c  pop     rsi
0x18002765d  pop     rbx
0x18002765e  pop     rbp
0x18002765f  retn
```
