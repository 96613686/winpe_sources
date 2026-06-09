# PerformRestore

- ea: `0x180026d78`
- end: `0x180027075`
- name: `PerformRestore`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180025144`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000c164`
- `0x18000eb90`
- `0x18001c63c`
- `0x18001dfc8`
- `0x18001e530`
- `0x180026d78`
- `0x1800626dc`
- `0x18008f5b4`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180026ff4`
- `ADVAPI32!RegDeleteValueW` at `0x180026ff4`
- `KERNEL32!HeapAlloc` at `0x180026dd0`
- `KERNEL32!HeapAlloc` at `0x180026e32`
- `KERNEL32!HeapAlloc` at `0x180026dd0`
- `KERNEL32!HeapAlloc` at `0x180026e32`
- `KERNEL32!EnterCriticalSection` at `0x180026ecc`
- `KERNEL32!EnterCriticalSection` at `0x180026ecc`
- `KERNEL32!LeaveCriticalSection` at `0x180027007`
- `KERNEL32!LeaveCriticalSection` at `0x180027007`
- `KERNEL32!HeapFree` at `0x18002701f`
- `KERNEL32!HeapFree` at `0x180027046`
- `KERNEL32!HeapFree` at `0x18002701f`
- `KERNEL32!HeapFree` at `0x180027046`
- `KERNEL32!DeleteFileW` at `0x18002702e`
- `KERNEL32!DeleteFileW` at `0x18002702e`

## string_xrefs

- `0x180026fed`: `RestoreDatabasePath`

## pseudocode

```c
__int64 PerformRestore()
{
  __int64 v0; // rax
  __int64 v1; // rcx
  SIZE_T v2; // rbx
  size_t v3; // r14
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
0x180026d78  mov     [rsp+arg_0], rbx
0x180026d7d  mov     [rsp+arg_8], rbp
0x180026d82  mov     [rsp+arg_10], rsi
0x180026d87  push    rdi
0x180026d88  push    r14
0x180026d8a  push    r15
0x180026d8c  sub     rsp, 20h
0x180026d90  mov     rdx, cs:DhcpGlobalOemJetRestorePath
0x180026d97  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026d9b  mov     rcx, rax
0x180026d9e  inc     rcx
0x180026da1  cmp     byte ptr [rdx+rcx], 0
0x180026da5  jnz     short loc_180026D9E
0x180026da7  lea     rbx, ds:12h[rcx*2]
0x180026daf  inc     rax
0x180026db2  cmp     byte ptr [rdx+rax], 0
0x180026db6  jnz     short loc_180026DAF
0x180026db8  mov     rcx, cs:gDhcpHeap; hHeap
0x180026dbf  lea     r14, ds:1Ah[rax*2]
0x180026dc7  lea     r8, [r14+r14]; dwBytes
0x180026dcb  mov     edx, 8; dwFlags
0x180026dd0  call    cs:__imp_HeapAlloc
0x180026dd7  nop     dword ptr [rax+rax+00h]
0x180026ddc  mov     rdi, rax
0x180026ddf  test    rax, rax
0x180026de2  jz      loc_180027056
0x180026de8  mov     rcx, cs:WPP_GLOBAL_Control
0x180026def  lea     rbp, WPP_GLOBAL_Control
0x180026df6  lea     r15, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180026dfd  cmp     rcx, rbp
0x180026e00  jz      short loc_180026E23
0x180026e02  test    dword ptr [rcx+1Ch], 8000h
0x180026e09  jz      short loc_180026E23
0x180026e0b  mov     r9, cs:DhcpGlobalOemJetRestorePath
0x180026e12  mov     edx, 1Dh
0x180026e17  mov     rcx, [rcx+10h]
0x180026e1b  mov     r8, r15
0x180026e1e  call    WPP_SF_s
0x180026e23  mov     rcx, cs:gDhcpHeap; hHeap
0x180026e2a  mov     r8, rbx; dwBytes
0x180026e2d  mov     edx, 8; dwFlags
0x180026e32  call    cs:__imp_HeapAlloc
0x180026e39  nop     dword ptr [rax+rax+00h]
0x180026e3e  mov     rcx, cs:DhcpGlobalOemJetRestorePath; SourceString
0x180026e45  test    rcx, rcx
0x180026e48  jz      loc_180027056
0x180026e4e  mov     rdx, rax
0x180026e51  call    DhcpOemToUnicode
0x180026e56  mov     rsi, rax
0x180026e59  test    rax, rax
0x180026e5c  jz      loc_180027056
0x180026e62  lea     r8, pszSrc; "\\"
0x180026e69  mov     rdx, rbx; cbDest
0x180026e6c  mov     rcx, rax; pszDest
0x180026e6f  call    StringCbCatW
0x180026e74  lea     r8, aDhcpcfg; "DhcpCfg"
0x180026e7b  mov     rdx, rbx; cbDest
0x180026e7e  mov     rcx, rsi; pszDest
0x180026e81  call    StringCbCatW
0x180026e86  mov     rcx, cs:DhcpGlobalOemJetRestorePath; SourceString
0x180026e8d  mov     rdx, rdi
0x180026e90  call    DhcpOemToUnicode
0x180026e95  mov     rdi, rax
0x180026e98  test    rax, rax
0x180026e9b  jz      loc_180027056
0x180026ea1  lea     r8, pszSrc; "\\"
0x180026ea8  mov     rdx, r14; cbDest
0x180026eab  mov     rcx, rax; pszDest
0x180026eae  call    StringCbCatW
0x180026eb3  lea     r8, aDhcpcfgTmp; "DhcpCfg.tmp"
0x180026eba  mov     rdx, r14; cbDest
0x180026ebd  mov     rcx, rdi; pszDest
0x180026ec0  call    StringCbCatW
0x180026ec5  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x180026ecc  call    cs:__imp_EnterCriticalSection
0x180026ed3  nop     dword ptr [rax+rax+00h]
0x180026ed8  mov     rcx, rdi; lpFileName
0x180026edb  call    DhcpBackupConfiguration
0x180026ee0  mov     ebx, eax
0x180026ee2  test    eax, eax
0x180026ee4  jz      short loc_180026EF0
0x180026ee6  mov     ecx, 3FBh
0x180026eeb  jmp     loc_180026F90
0x180026ef0  mov     rcx, rsi; lpFileName
0x180026ef3  call    DhcpRestoreConfiguration
0x180026ef8  mov     ebx, eax
0x180026efa  test    eax, eax
0x180026efc  jz      short loc_180026F26
0x180026efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f05  cmp     rcx, rbp
0x180026f08  jz      short loc_180026EE6
0x180026f0a  test    byte ptr [rcx+1Ch], 10h
0x180026f0e  jz      short loc_180026EE6
0x180026f10  mov     rcx, [rcx+10h]
0x180026f14  mov     edx, 1Eh
0x180026f19  mov     r9d, eax
0x180026f1c  mov     r8, r15
0x180026f1f  call    WPP_SF_D
0x180026f24  jmp     short loc_180026EE6
0x180026f26  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f2d  cmp     rcx, rbp
0x180026f30  jz      short loc_180026F53
0x180026f32  test    dword ptr [rcx+1Ch], 8000h
0x180026f39  jz      short loc_180026F53
0x180026f3b  mov     r9, cs:DhcpGlobalOemJetRestorePath
0x180026f42  mov     edx, 1Fh
0x180026f47  mov     rcx, [rcx+10h]
0x180026f4b  mov     r8, r15
0x180026f4e  call    WPP_SF_s
0x180026f53  mov     rcx, cs:DhcpGlobalOemJetRestorePath
0x180026f5a  call    DhcpRestoreDatabase
0x180026f5f  mov     ebx, eax
0x180026f61  test    eax, eax
0x180026f63  jz      short loc_180026FAF
0x180026f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f6c  cmp     rcx, rbp
0x180026f6f  jz      short loc_180026F8B
0x180026f71  test    byte ptr [rcx+1Ch], 10h
0x180026f75  jz      short loc_180026F8B
0x180026f77  mov     rcx, [rcx+10h]
0x180026f7b  mov     edx, 20h ; ' '
0x180026f80  mov     r9d, eax
0x180026f83  mov     r8, r15
0x180026f86  call    WPP_SF_D
0x180026f8b  mov     ecx, 3FAh
0x180026f90  mov     edx, 1
0x180026f95  mov     r8d, ebx
0x180026f98  call    DhcpServerEventLog
0x180026f9d  mov     rcx, rdi; lpFileName
0x180026fa0  mov     cs:DhcpGlobalRestoreStatus, ebx
0x180026fa6  call    DhcpRestoreConfiguration
0x180026fab  mov     ebx, eax
0x180026fad  jmp     short loc_180026FC0
0x180026faf  xor     r8d, r8d
0x180026fb2  mov     ecx, 410h
0x180026fb7  lea     edx, [r8+4]
0x180026fbb  call    DhcpServerEventLog
0x180026fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180026fc7  cmp     rcx, rbp
0x180026fca  jz      short loc_180026FE6
0x180026fcc  test    dword ptr [rcx+1Ch], 400h
0x180026fd3  jz      short loc_180026FE6
0x180026fd5  mov     rcx, [rcx+10h]
0x180026fd9  mov     edx, 21h ; '!'
0x180026fde  mov     r8, r15
0x180026fe1  call    WPP_SF_
0x180026fe6  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180026fed  lea     rdx, aRestoredatabas; "RestoreDatabasePath"
0x180026ff4  call    cs:__imp_RegDeleteValueW
0x180026ffb  nop     dword ptr [rax+rax+00h]
0x180027000  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x180027007  call    cs:__imp_LeaveCriticalSection
0x18002700e  nop     dword ptr [rax+rax+00h]
0x180027013  mov     rcx, cs:gDhcpHeap; hHeap
0x18002701a  mov     r8, rsi; lpMem
0x18002701d  xor     edx, edx; dwFlags
0x18002701f  call    cs:__imp_HeapFree
0x180027026  nop     dword ptr [rax+rax+00h]
0x18002702b  mov     rcx, rdi; lpFileName
0x18002702e  call    cs:__imp_DeleteFileW
0x180027035  nop     dword ptr [rax+rax+00h]
0x18002703a  mov     rcx, cs:gDhcpHeap; hHeap
0x180027041  mov     r8, rdi; lpMem
0x180027044  xor     edx, edx; dwFlags
0x180027046  call    cs:__imp_HeapFree
0x18002704d  nop     dword ptr [rax+rax+00h]
0x180027052  mov     eax, ebx
0x180027054  jmp     short loc_18002705B
0x180027056  mov     eax, 8
0x18002705b  mov     rbx, [rsp+38h+arg_0]
0x180027060  mov     rbp, [rsp+38h+arg_8]
0x180027065  mov     rsi, [rsp+38h+arg_10]
0x18002706a  add     rsp, 20h
0x18002706e  pop     r15
0x180027070  pop     r14
0x180027072  pop     rdi
0x180027073  retn
```
