# PerformRestore

- ea: `0x1800277f8`
- end: `0x180027af5`
- name: `PerformRestore`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180025bf4`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000c180`
- `0x18000f4b8`
- `0x18001d098`
- `0x18001ea10`
- `0x18001ef78`
- `0x1800277f8`
- `0x180062964`
- `0x18008f418`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180027a74`
- `ADVAPI32!RegDeleteValueW` at `0x180027a74`
- `KERNEL32!HeapAlloc` at `0x180027850`
- `KERNEL32!HeapAlloc` at `0x1800278b2`
- `KERNEL32!HeapAlloc` at `0x180027850`
- `KERNEL32!HeapAlloc` at `0x1800278b2`
- `KERNEL32!EnterCriticalSection` at `0x18002794c`
- `KERNEL32!EnterCriticalSection` at `0x18002794c`
- `KERNEL32!LeaveCriticalSection` at `0x180027a87`
- `KERNEL32!LeaveCriticalSection` at `0x180027a87`
- `KERNEL32!HeapFree` at `0x180027a9f`
- `KERNEL32!HeapFree` at `0x180027ac6`
- `KERNEL32!HeapFree` at `0x180027a9f`
- `KERNEL32!HeapFree` at `0x180027ac6`
- `KERNEL32!DeleteFileW` at `0x180027aae`
- `KERNEL32!DeleteFileW` at `0x180027aae`

## string_xrefs

- `0x180027a6d`: `RestoreDatabasePath`

## pseudocode

```c
__int64 PerformRestore()
{
  __int64 v0; // rax
  __int64 v1; // rcx
  SIZE_T v2; // rdi
  size_t v3; // rbx
  wchar_t *v4; // rax
  wchar_t *v5; // rsi
  wchar_t *v6; // rax
  wchar_t *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax

  v0 = -1;
  v1 = -1;
  do
    ++v1;
  while ( DhcpGlobalOemJetRestorePath[v1] );
  v2 = 2 * v1 + 18;
  do
    ++v0;
  while ( DhcpGlobalOemJetRestorePath[v0] );
  v3 = 2 * v0 + 26;
  if ( !HeapAlloc(gDhcpHeap, 8u, 2 * v3) )
    return 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids,
      DhcpGlobalOemJetRestorePath);
  HeapAlloc(gDhcpHeap, 8u, v2);
  if ( !DhcpGlobalOemJetRestorePath )
    return 8;
  v4 = (wchar_t *)DhcpOemToUnicode(DhcpGlobalOemJetRestorePath);
  v5 = v4;
  if ( !v4 )
    return 8;
  StringCbCatW(v4, v2, L"\\");
  StringCbCatW(v5, v2, L"DhcpCfg");
  v6 = (wchar_t *)DhcpOemToUnicode(DhcpGlobalOemJetRestorePath);
  v7 = v6;
  if ( !v6 )
    return 8;
  StringCbCatW(v6, v3, L"\\");
  StringCbCatW(v7, v3, L"DhcpCfg.tmp");
  EnterCriticalSection(&DhcpGlobalRegCritSect);
  v8 = DhcpBackupConfiguration(v7);
  if ( v8 )
    goto LABEL_13;
  v10 = DhcpRestoreConfiguration(v5);
  v8 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v10);
LABEL_13:
    v9 = 1019;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids,
      DhcpGlobalOemJetRestorePath);
  v11 = DhcpRestoreDatabase(DhcpGlobalOemJetRestorePath);
  v8 = v11;
  if ( !v11 )
  {
    DhcpServerEventLog(1040, 4, 0);
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v11);
  v9 = 1018;
LABEL_26:
  DhcpServerEventLog(v9, 1, v8);
  DhcpGlobalRestoreStatus = v8;
  v8 = DhcpRestoreConfiguration(v7);
LABEL_28:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
  RegDeleteValueW(DhcpGlobalRegParam, L"RestoreDatabasePath");
  LeaveCriticalSection(&DhcpGlobalRegCritSect);
  HeapFree(gDhcpHeap, 0, v5);
  DeleteFileW(v7);
  HeapFree(gDhcpHeap, 0, v7);
  return v8;
}

```

## disassembly

```asm
0x1800277f8  mov     [rsp+arg_0], rbx
0x1800277fd  mov     [rsp+arg_8], rbp
0x180027802  mov     [rsp+arg_10], rsi
0x180027807  push    rdi
0x180027808  push    r14
0x18002780a  push    r15
0x18002780c  sub     rsp, 20h
0x180027810  mov     rdx, cs:DhcpGlobalOemJetRestorePath
0x180027817  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002781b  mov     rcx, rax
0x18002781e  inc     rcx
0x180027821  cmp     byte ptr [rdx+rcx], 0
0x180027825  jnz     short loc_18002781E
0x180027827  lea     rdi, ds:12h[rcx*2]
0x18002782f  inc     rax
0x180027832  cmp     byte ptr [rdx+rax], 0
0x180027836  jnz     short loc_18002782F
0x180027838  mov     rcx, cs:gDhcpHeap; hHeap
0x18002783f  lea     rbx, ds:1Ah[rax*2]
0x180027847  lea     r8, [rbx+rbx]; dwBytes
0x18002784b  mov     edx, 8; dwFlags
0x180027850  call    cs:__imp_HeapAlloc
0x180027857  nop     dword ptr [rax+rax+00h]
0x18002785c  mov     rbp, rax
0x18002785f  test    rax, rax
0x180027862  jz      loc_180027AD6
0x180027868  mov     rcx, cs:WPP_GLOBAL_Control
0x18002786f  lea     r14, WPP_GLOBAL_Control
0x180027876  lea     r15, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x18002787d  cmp     rcx, r14
0x180027880  jz      short loc_1800278A3
0x180027882  test    dword ptr [rcx+1Ch], 8000h
0x180027889  jz      short loc_1800278A3
0x18002788b  mov     r9, cs:DhcpGlobalOemJetRestorePath
0x180027892  mov     edx, 1Dh
0x180027897  mov     rcx, [rcx+10h]
0x18002789b  mov     r8, r15
0x18002789e  call    WPP_SF_s
0x1800278a3  mov     rcx, cs:gDhcpHeap; hHeap
0x1800278aa  mov     r8, rdi; dwBytes
0x1800278ad  mov     edx, 8; dwFlags
0x1800278b2  call    cs:__imp_HeapAlloc
0x1800278b9  nop     dword ptr [rax+rax+00h]
0x1800278be  mov     rcx, cs:DhcpGlobalOemJetRestorePath; SourceString
0x1800278c5  test    rcx, rcx
0x1800278c8  jz      loc_180027AD6
0x1800278ce  mov     rdx, rax
0x1800278d1  call    DhcpOemToUnicode
0x1800278d6  mov     rsi, rax
0x1800278d9  test    rax, rax
0x1800278dc  jz      loc_180027AD6
0x1800278e2  lea     r8, pszSrc; "\\"
0x1800278e9  mov     rdx, rdi; cbDest
0x1800278ec  mov     rcx, rax; pszDest
0x1800278ef  call    StringCbCatW
0x1800278f4  lea     r8, aDhcpcfg; "DhcpCfg"
0x1800278fb  mov     rdx, rdi; cbDest
0x1800278fe  mov     rcx, rsi; pszDest
0x180027901  call    StringCbCatW
0x180027906  mov     rcx, cs:DhcpGlobalOemJetRestorePath; SourceString
0x18002790d  mov     rdx, rbp
0x180027910  call    DhcpOemToUnicode
0x180027915  mov     rdi, rax
0x180027918  test    rax, rax
0x18002791b  jz      loc_180027AD6
0x180027921  lea     r8, pszSrc; "\\"
0x180027928  mov     rdx, rbx; cbDest
0x18002792b  mov     rcx, rax; pszDest
0x18002792e  call    StringCbCatW
0x180027933  lea     r8, aDhcpcfgTmp; "DhcpCfg.tmp"
0x18002793a  mov     rdx, rbx; cbDest
0x18002793d  mov     rcx, rdi; pszDest
0x180027940  call    StringCbCatW
0x180027945  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x18002794c  call    cs:__imp_EnterCriticalSection
0x180027953  nop     dword ptr [rax+rax+00h]
0x180027958  mov     rcx, rdi; lpFileName
0x18002795b  call    DhcpBackupConfiguration
0x180027960  mov     ebx, eax
0x180027962  test    eax, eax
0x180027964  jz      short loc_180027970
0x180027966  mov     ecx, 3FBh
0x18002796b  jmp     loc_180027A10
0x180027970  mov     rcx, rsi; lpFileName
0x180027973  call    DhcpRestoreConfiguration
0x180027978  mov     ebx, eax
0x18002797a  test    eax, eax
0x18002797c  jz      short loc_1800279A6
0x18002797e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027985  cmp     rcx, r14
0x180027988  jz      short loc_180027966
0x18002798a  test    byte ptr [rcx+1Ch], 10h
0x18002798e  jz      short loc_180027966
0x180027990  mov     rcx, [rcx+10h]
0x180027994  mov     edx, 1Eh
0x180027999  mov     r9d, eax
0x18002799c  mov     r8, r15
0x18002799f  call    WPP_SF_D
0x1800279a4  jmp     short loc_180027966
0x1800279a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279ad  cmp     rcx, r14
0x1800279b0  jz      short loc_1800279D3
0x1800279b2  test    dword ptr [rcx+1Ch], 8000h
0x1800279b9  jz      short loc_1800279D3
0x1800279bb  mov     r9, cs:DhcpGlobalOemJetRestorePath
0x1800279c2  mov     edx, 1Fh
0x1800279c7  mov     rcx, [rcx+10h]
0x1800279cb  mov     r8, r15
0x1800279ce  call    WPP_SF_s
0x1800279d3  mov     rcx, cs:DhcpGlobalOemJetRestorePath
0x1800279da  call    DhcpRestoreDatabase
0x1800279df  mov     ebx, eax
0x1800279e1  test    eax, eax
0x1800279e3  jz      short loc_180027A2F
0x1800279e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279ec  cmp     rcx, r14
0x1800279ef  jz      short loc_180027A0B
0x1800279f1  test    byte ptr [rcx+1Ch], 10h
0x1800279f5  jz      short loc_180027A0B
0x1800279f7  mov     rcx, [rcx+10h]
0x1800279fb  mov     edx, 20h ; ' '
0x180027a00  mov     r9d, eax
0x180027a03  mov     r8, r15
0x180027a06  call    WPP_SF_D
0x180027a0b  mov     ecx, 3FAh
0x180027a10  mov     edx, 1
0x180027a15  mov     r8d, ebx
0x180027a18  call    DhcpServerEventLog
0x180027a1d  mov     rcx, rdi; lpFileName
0x180027a20  mov     cs:DhcpGlobalRestoreStatus, ebx
0x180027a26  call    DhcpRestoreConfiguration
0x180027a2b  mov     ebx, eax
0x180027a2d  jmp     short loc_180027A40
0x180027a2f  xor     r8d, r8d
0x180027a32  mov     ecx, 410h
0x180027a37  lea     edx, [r8+4]
0x180027a3b  call    DhcpServerEventLog
0x180027a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a47  cmp     rcx, r14
0x180027a4a  jz      short loc_180027A66
0x180027a4c  test    dword ptr [rcx+1Ch], 400h
0x180027a53  jz      short loc_180027A66
0x180027a55  mov     rcx, [rcx+10h]
0x180027a59  mov     edx, 21h ; '!'
0x180027a5e  mov     r8, r15
0x180027a61  call    WPP_SF_
0x180027a66  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180027a6d  lea     rdx, aRestoredatabas; "RestoreDatabasePath"
0x180027a74  call    cs:__imp_RegDeleteValueW
0x180027a7b  nop     dword ptr [rax+rax+00h]
0x180027a80  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x180027a87  call    cs:__imp_LeaveCriticalSection
0x180027a8e  nop     dword ptr [rax+rax+00h]
0x180027a93  mov     rcx, cs:gDhcpHeap; hHeap
0x180027a9a  mov     r8, rsi; lpMem
0x180027a9d  xor     edx, edx; dwFlags
0x180027a9f  call    cs:__imp_HeapFree
0x180027aa6  nop     dword ptr [rax+rax+00h]
0x180027aab  mov     rcx, rdi; lpFileName
0x180027aae  call    cs:__imp_DeleteFileW
0x180027ab5  nop     dword ptr [rax+rax+00h]
0x180027aba  mov     rcx, cs:gDhcpHeap; hHeap
0x180027ac1  mov     r8, rdi; lpMem
0x180027ac4  xor     edx, edx; dwFlags
0x180027ac6  call    cs:__imp_HeapFree
0x180027acd  nop     dword ptr [rax+rax+00h]
0x180027ad2  mov     eax, ebx
0x180027ad4  jmp     short loc_180027ADB
0x180027ad6  mov     eax, 8
0x180027adb  mov     rbx, [rsp+38h+arg_0]
0x180027ae0  mov     rbp, [rsp+38h+arg_8]
0x180027ae5  mov     rsi, [rsp+38h+arg_10]
0x180027aea  add     rsp, 20h
0x180027aee  pop     r15
0x180027af0  pop     r14
0x180027af2  pop     rdi
0x180027af3  retn
```
