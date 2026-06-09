# CResourceManager::ProcessAttach(int)

- ea: `0x180004060`
- end: `0x18000444d`
- name: `?ProcessAttach@CResourceManager@@SAXH@Z`
- size: `1005`
- prototype: `void __fastcall(int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180003868`
- `0x1800049c0`
- `0x18002e884`

## callees

- `0x180004060`
- `0x180004924`
- `0x1800225c4`
- `0x1800388a0`
- `0x180039250`
- `0x18007321c`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x1800042c5`
- `KERNEL32!MapViewOfFile` at `0x1800042c5`
- `KERNEL32!CreateFileMappingW` at `0x18000415b`
- `KERNEL32!CreateFileMappingW` at `0x180004284`
- `KERNEL32!CreateFileMappingW` at `0x18000415b`
- `KERNEL32!CreateFileMappingW` at `0x180004284`
- `KERNEL32!LocalFree` at `0x180004209`
- `KERNEL32!LocalFree` at `0x180004218`
- `KERNEL32!LocalFree` at `0x180004209`
- `KERNEL32!LocalFree` at `0x180004218`
- `KERNEL32!UnmapViewOfFile` at `0x1800043ae`
- `KERNEL32!UnmapViewOfFile` at `0x1800043e6`
- `KERNEL32!UnmapViewOfFile` at `0x1800043ae`
- `KERNEL32!UnmapViewOfFile` at `0x1800043e6`
- `KERNEL32!VirtualAlloc` at `0x180004313`
- `KERNEL32!VirtualAlloc` at `0x180004337`
- `KERNEL32!VirtualAlloc` at `0x180004313`
- `KERNEL32!VirtualAlloc` at `0x180004337`
- `KERNEL32!GetSystemInfo` at `0x1800040dc`
- `KERNEL32!GetSystemInfo` at `0x1800040dc`
- `KERNEL32!WaitForSingleObject` at `0x18000409a`
- `KERNEL32!WaitForSingleObject` at `0x18000409a`
- `KERNEL32!ReleaseMutex` at `0x18000441f`
- `KERNEL32!ReleaseMutex` at `0x18000441f`
- `KERNEL32!CloseHandle` at `0x180004405`
- `KERNEL32!CloseHandle` at `0x180004405`
- `KERNEL32!GetLastError` at `0x18000416e`
- `KERNEL32!GetLastError` at `0x180004297`
- `KERNEL32!GetLastError` at `0x1800043c1`
- `KERNEL32!GetLastError` at `0x18000416e`
- `KERNEL32!GetLastError` at `0x180004297`
- `KERNEL32!GetLastError` at `0x1800043c1`
- `ADVAPI32!EqualSid` at `0x1800041f7`
- `ADVAPI32!EqualSid` at `0x1800041f7`
- `ADVAPI32!IsValidSid` at `0x1800041aa`
- `ADVAPI32!IsValidSid` at `0x1800041e1`
- `ADVAPI32!IsValidSid` at `0x1800041aa`
- `ADVAPI32!IsValidSid` at `0x1800041e1`

## pseudocode

```c
void __fastcall CResourceManager::ProcessAttach(int a1)
{
  DWORD LastError; // eax
  HANDLE v3; // rcx
  DWORD v4; // edi
  HLOCAL CurrentOwnerSID; // rax
  void *v6; // rsi
  void *v7; // rcx
  BOOL v8; // r14d
  HLOCAL KernelObjectOwnerSID; // rax
  void *v10; // rbp
  DWORD v11; // eax
  unsigned __int64 *v12; // rax
  void *v13; // rdi
  LPVOID v14; // rax
  char *v15; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+38h] [rbp-B0h] BYREF
  WCHAR Name[48]; // [rsp+70h] [rbp-78h] BYREF

  if ( CResourceManager::m_Mutex )
  {
    WaitForSingleObject(CResourceManager::m_Mutex, 0xFFFFFFFF);
    if ( a1 )
    {
      if ( ++CResourceManager::m_dwLoadCount == 1 )
      {
        memset(&SystemInfo, 0, sizeof(SystemInfo));
        GetSystemInfo(&SystemInfo);
        LODWORD(g_aMaxAllocations) = 306;
        dword_18019E87C = 267;
        StringCchPrintfW(Name, 0x30u, L"%s-%#04x-%#08x", L"AMResourceMapping3", SystemInfo.wProcessorArchitecture, 1950);
        if ( byte_18019DC80 )
        {
          CResourceManager::m_hData = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x4000004u, 0, 0xE000u, Name);
          LastError = GetLastError();
          v3 = CResourceManager::m_hData;
          v4 = LastError;
          if ( CResourceManager::m_hData )
          {
            CurrentOwnerSID = GetCurrentOwnerSID();
            v6 = CurrentOwnerSID;
            if ( !CurrentOwnerSID || !IsValidSid(CurrentOwnerSID) )
              goto LABEL_13;
            v8 = 0;
            KernelObjectOwnerSID = GetKernelObjectOwnerSID(v7);
            v10 = KernelObjectOwnerSID;
            if ( KernelObjectOwnerSID && IsValidSid(KernelObjectOwnerSID) )
            {
              v8 = EqualSid(v6, v10);
              LocalFree(v10);
            }
            LocalFree(v6);
            if ( v8 )
            {
              v3 = CResourceManager::m_hData;
            }
            else
            {
LABEL_13:
              v3 = 0;
              CResourceManager::m_hData = 0;
            }
          }
          if ( byte_18019DC80 && v3 )
            goto LABEL_17;
        }
        CResourceManager::m_hData = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x4000004u, 0, 0xE000u, 0);
        v11 = GetLastError();
        v3 = CResourceManager::m_hData;
        v4 = v11;
        if ( CResourceManager::m_hData )
        {
LABEL_17:
          v12 = (unsigned __int64 *)MapViewOfFile(v3, 0xF001Fu, 0, 0, 0);
          CResourceManager::m_pData = v12;
          if ( v12 )
          {
            CResourceManager::m_aoffsetAllocBase = v12 + 10;
            lpAddress = v12 + 1536;
            if ( !v4 )
            {
              v13 = VirtualAlloc(v12, 0x1000u, 0x1000u, 4u);
              v14 = VirtualAlloc(lpAddress, 0x1000u, 0x1000u, 4u);
              if ( v13 && v14 )
              {
                memset_0(v13, 0, 0x50u);
                v15 = (char *)CResourceManager::m_pData;
                *((_DWORD *)CResourceManager::m_pData + 2) = 0;
                *(_DWORD *)v15 = 0;
                *((_DWORD *)v15 + 5) = 0;
                *((_QWORD *)v15 + 3) = 1;
                *(_QWORD *)(v15 + 12) = 1;
                *((_DWORD *)v15 + 10) = 1;
                *((_DWORD *)v15 + 13) = 0;
                *((_QWORD *)v15 + 7) = 0;
                *((_QWORD *)v15 + 8) = 0;
                *((_DWORD *)v15 + 18) = 1;
                *((_DWORD *)v15 + 19) = 1;
              }
              else
              {
                if ( CResourceManager::m_pData )
                {
                  UnmapViewOfFile(CResourceManager::m_pData);
                  CResourceManager::m_pData = 0;
                }
                GetLastError();
              }
            }
          }
        }
      }
    }
    else if ( !--CResourceManager::m_dwLoadCount )
    {
      if ( CResourceManager::m_pData )
      {
        UnmapViewOfFile(CResourceManager::m_pData);
        CResourceManager::m_pData = 0;
      }
      if ( CResourceManager::m_hData )
      {
        CloseHandle(CResourceManager::m_hData);
        CResourceManager::m_hData = 0;
      }
    }
    ReleaseMutex(CResourceManager::m_Mutex);
  }
}

```

## disassembly

```asm
0x180004060  push    rbx
0x180004062  sub     rsp, 0E0h
0x180004069  mov     rax, cs:__security_cookie
0x180004070  xor     rax, rsp
0x180004073  mov     [rsp+0E8h+var_18], rax
0x18000407b  mov     ebx, ecx
0x18000407d  mov     rcx, cs:?m_Mutex@CResourceManager@@0VCAMMutex@@A; hHandle
0x180004084  test    rcx, rcx
0x180004087  jz      loc_180004433
0x18000408d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180004092  mov     [rsp+0E8h+arg_10], rdi
0x18000409a  call    cs:__imp_WaitForSingleObject
0x1800040a1  nop     dword ptr [rax+rax+00h]
0x1800040a6  test    ebx, ebx
0x1800040a8  jz      loc_1800043CF
0x1800040ae  mov     eax, cs:?m_dwLoadCount@CResourceManager@@0KA; ulong CResourceManager::m_dwLoadCount
0x1800040b4  inc     eax
0x1800040b6  mov     cs:?m_dwLoadCount@CResourceManager@@0KA, eax; ulong CResourceManager::m_dwLoadCount
0x1800040bc  cmp     eax, 1
0x1800040bf  jnz     loc_180004418
0x1800040c5  xorps   xmm0, xmm0
0x1800040c8  lea     rcx, [rsp+0E8h+SystemInfo]; lpSystemInfo
0x1800040cd  movups  xmmword ptr [rsp+0E8h+SystemInfo], xmm0
0x1800040d2  movups  xmmword ptr [rsp+0E8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800040d7  movups  xmmword ptr [rsp+0E8h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800040dc  call    cs:__imp_GetSystemInfo
0x1800040e3  nop     dword ptr [rax+rax+00h]
0x1800040e8  movzx   eax, word ptr [rsp+0E8h+SystemInfo]
0x1800040ed  lea     r9, aAmresourcemapp; "AMResourceMapping3"
0x1800040f4  mov     dword ptr [rsp+0E8h+lpName], 79Eh
0x1800040fc  lea     r8, aS04x08x; "%s-%#04x-%#08x"
0x180004103  mov     edx, 30h ; '0'; unsigned __int64
0x180004108  mov     [rsp+0E8h+dwMaximumSizeLow], eax
0x18000410c  lea     rcx, [rsp+0E8h+Name]; Buffer
0x180004111  mov     cs:?g_aMaxAllocations@@3PAKA, 132h; ulong near * g_aMaxAllocations
0x18000411b  mov     cs:dword_18019E87C, 10Bh
0x180004125  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000412a  cmp     cs:byte_18019DC80, 0
0x180004131  jz      loc_180004263
0x180004137  lea     rax, [rsp+0E8h+Name]
0x18000413c  xor     r9d, r9d; dwMaximumSizeHigh
0x18000413f  mov     [rsp+0E8h+lpName], rax; lpName
0x180004144  xor     edx, edx; lpFileMappingAttributes
0x180004146  mov     rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000414d  mov     [rsp+0E8h+dwMaximumSizeLow], 0E000h; dwMaximumSizeLow
0x180004155  mov     r8d, 4000004h; flProtect
0x18000415b  call    cs:__imp_CreateFileMappingW
0x180004162  nop     dword ptr [rax+rax+00h]
0x180004167  mov     cs:?m_hData@CResourceManager@@0PEAXEA, rax; void * CResourceManager::m_hData
0x18000416e  call    cs:__imp_GetLastError
0x180004175  nop     dword ptr [rax+rax+00h]
0x18000417a  mov     rcx, cs:?m_hData@CResourceManager@@0PEAXEA; void * CResourceManager::m_hData
0x180004181  xor     ebx, ebx
0x180004183  mov     edi, eax
0x180004185  test    rcx, rcx
0x180004188  jz      loc_180004254
0x18000418e  mov     [rsp+0E8h+arg_8], rsi
0x180004196  call    ?GetCurrentOwnerSID@@YAPEAXXZ; GetCurrentOwnerSID(void)
0x18000419b  mov     rsi, rax
0x18000419e  test    rax, rax
0x1800041a1  jz      loc_180004242
0x1800041a7  mov     rcx, rax; pSid
0x1800041aa  call    cs:__imp_IsValidSid
0x1800041b1  nop     dword ptr [rax+rax+00h]
0x1800041b6  test    eax, eax
0x1800041b8  jz      loc_180004242
0x1800041be  mov     [rsp+0E8h+arg_0], rbp
0x1800041c6  mov     [rsp+0E8h+arg_18], r14
0x1800041ce  mov     r14d, ebx
0x1800041d1  call    ?GetKernelObjectOwnerSID@@YAPEAXPEAX@Z; GetKernelObjectOwnerSID(void *)
0x1800041d6  mov     rbp, rax
0x1800041d9  test    rax, rax
0x1800041dc  jz      short loc_180004215
0x1800041de  mov     rcx, rax; pSid
0x1800041e1  call    cs:__imp_IsValidSid
0x1800041e8  nop     dword ptr [rax+rax+00h]
0x1800041ed  test    eax, eax
0x1800041ef  jz      short loc_180004215
0x1800041f1  mov     rdx, rbp; pSid2
0x1800041f4  mov     rcx, rsi; pSid1
0x1800041f7  call    cs:__imp_EqualSid
0x1800041fe  nop     dword ptr [rax+rax+00h]
0x180004203  mov     rcx, rbp; hMem
0x180004206  mov     r14d, eax
0x180004209  call    cs:__imp_LocalFree
0x180004210  nop     dword ptr [rax+rax+00h]
0x180004215  mov     rcx, rsi; hMem
0x180004218  call    cs:__imp_LocalFree
0x18000421f  nop     dword ptr [rax+rax+00h]
0x180004224  mov     rbp, [rsp+0E8h+arg_0]
0x18000422c  test    r14d, r14d
0x18000422f  mov     r14, [rsp+0E8h+arg_18]
0x180004237  jz      short loc_180004242
0x180004239  mov     rcx, cs:?m_hData@CResourceManager@@0PEAXEA; void * CResourceManager::m_hData
0x180004240  jmp     short loc_18000424C
0x180004242  mov     rcx, rbx
0x180004245  mov     cs:?m_hData@CResourceManager@@0PEAXEA, rbx; void * CResourceManager::m_hData
0x18000424c  mov     rsi, [rsp+0E8h+arg_8]
0x180004254  cmp     cs:byte_18019DC80, bl
0x18000425a  jz      short loc_180004265
0x18000425c  test    rcx, rcx
0x18000425f  jz      short loc_180004265
0x180004261  jmp     short loc_1800042B5
0x180004263  xor     ebx, ebx
0x180004265  mov     [rsp+0E8h+lpName], rbx; lpName
0x18000426a  xor     r9d, r9d; dwMaximumSizeHigh
0x18000426d  xor     edx, edx; lpFileMappingAttributes
0x18000426f  mov     [rsp+0E8h+dwMaximumSizeLow], 0E000h; dwMaximumSizeLow
0x180004277  mov     rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000427e  mov     r8d, 4000004h; flProtect
0x180004284  call    cs:__imp_CreateFileMappingW
0x18000428b  nop     dword ptr [rax+rax+00h]
0x180004290  mov     cs:?m_hData@CResourceManager@@0PEAXEA, rax; void * CResourceManager::m_hData
0x180004297  call    cs:__imp_GetLastError
0x18000429e  nop     dword ptr [rax+rax+00h]
0x1800042a3  mov     rcx, cs:?m_hData@CResourceManager@@0PEAXEA; hFileMappingObject
0x1800042aa  mov     edi, eax
0x1800042ac  test    rcx, rcx
0x1800042af  jz      loc_180004418
0x1800042b5  xor     r9d, r9d; dwFileOffsetLow
0x1800042b8  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x1800042bd  xor     r8d, r8d; dwFileOffsetHigh
0x1800042c0  mov     edx, 0F001Fh; dwDesiredAccess
0x1800042c5  call    cs:__imp_MapViewOfFile
0x1800042cc  nop     dword ptr [rax+rax+00h]
0x1800042d1  mov     cs:?m_pData@CResourceManager@@2PEAVCResourceData@@EA, rax; CResourceData * CResourceManager::m_pData
0x1800042d8  mov     rcx, rax; lpAddress
0x1800042db  test    rax, rax
0x1800042de  jz      loc_180004418
0x1800042e4  add     rax, 50h ; 'P'
0x1800042e8  mov     cs:?m_aoffsetAllocBase@CResourceManager@@2PA_KA, rax; unsigned __int64 near * CResourceManager::m_aoffsetAllocBase
0x1800042ef  lea     rax, [rcx+3000h]
0x1800042f6  mov     cs:lpAddress, rax
0x1800042fd  test    edi, edi
0x1800042ff  jnz     loc_180004418
0x180004305  mov     edx, 1000h; dwSize
0x18000430a  mov     r9d, 4; flProtect
0x180004310  mov     r8d, edx; flAllocationType
0x180004313  call    cs:__imp_VirtualAlloc
0x18000431a  nop     dword ptr [rax+rax+00h]
0x18000431f  mov     rcx, cs:lpAddress; lpAddress
0x180004326  mov     edx, 1000h; dwSize
0x18000432b  mov     r8d, edx; flAllocationType
0x18000432e  mov     r9d, 4; flProtect
0x180004334  mov     rdi, rax
0x180004337  call    cs:__imp_VirtualAlloc
0x18000433e  nop     dword ptr [rax+rax+00h]
0x180004343  test    rdi, rdi
0x180004346  jz      short loc_1800043A2
0x180004348  test    rax, rax
0x18000434b  jz      short loc_1800043A2
0x18000434d  xor     edx, edx; Val
0x18000434f  mov     r8d, 50h ; 'P'; Size
0x180004355  mov     rcx, rdi; void *
0x180004358  call    memset_0
0x18000435d  mov     rax, cs:?m_pData@CResourceManager@@2PEAVCResourceData@@EA; CResourceData * CResourceManager::m_pData
0x180004364  mov     [rax+8], ebx
0x180004367  mov     [rax], ebx
0x180004369  mov     [rax+14h], ebx
0x18000436c  mov     qword ptr [rax+18h], 1
0x180004374  mov     qword ptr [rax+0Ch], 1
0x18000437c  mov     dword ptr [rax+28h], 1
0x180004383  mov     [rax+34h], ebx
0x180004386  mov     [rax+38h], rbx
0x18000438a  mov     qword ptr [rax+40h], 0
0x180004392  mov     dword ptr [rax+48h], 1
0x180004399  mov     dword ptr [rax+4Ch], 1
0x1800043a0  jmp     short loc_180004418
0x1800043a2  mov     rcx, cs:?m_pData@CResourceManager@@2PEAVCResourceData@@EA; lpBaseAddress
0x1800043a9  test    rcx, rcx
0x1800043ac  jz      short loc_1800043C1
0x1800043ae  call    cs:__imp_UnmapViewOfFile
0x1800043b5  nop     dword ptr [rax+rax+00h]
0x1800043ba  mov     cs:?m_pData@CResourceManager@@2PEAVCResourceData@@EA, rbx; CResourceData * CResourceManager::m_pData
0x1800043c1  call    cs:__imp_GetLastError
0x1800043c8  nop     dword ptr [rax+rax+00h]
0x1800043cd  jmp     short loc_180004418
0x1800043cf  add     cs:?m_dwLoadCount@CResourceManager@@0KA, 0FFFFFFFFh; ulong CResourceManager::m_dwLoadCount
0x1800043d6  jnz     short loc_180004418
0x1800043d8  mov     rcx, cs:?m_pData@CResourceManager@@2PEAVCResourceData@@EA; lpBaseAddress
0x1800043df  xor     ebx, ebx
0x1800043e1  test    rcx, rcx
0x1800043e4  jz      short loc_1800043F9
0x1800043e6  call    cs:__imp_UnmapViewOfFile
0x1800043ed  nop     dword ptr [rax+rax+00h]
0x1800043f2  mov     cs:?m_pData@CResourceManager@@2PEAVCResourceData@@EA, rbx; CResourceData * CResourceManager::m_pData
0x1800043f9  mov     rcx, cs:?m_hData@CResourceManager@@0PEAXEA; hObject
0x180004400  test    rcx, rcx
0x180004403  jz      short loc_180004418
0x180004405  call    cs:__imp_CloseHandle
0x18000440c  nop     dword ptr [rax+rax+00h]
0x180004411  mov     cs:?m_hData@CResourceManager@@0PEAXEA, rbx; void * CResourceManager::m_hData
0x180004418  mov     rcx, cs:?m_Mutex@CResourceManager@@0VCAMMutex@@A; hMutex
0x18000441f  call    cs:__imp_ReleaseMutex
0x180004426  nop     dword ptr [rax+rax+00h]
0x18000442b  mov     rdi, [rsp+0E8h+arg_10]
0x180004433  mov     rcx, [rsp+0E8h+var_18]
0x18000443b  xor     rcx, rsp; StackCookie
0x18000443e  call    __security_check_cookie
0x180004443  add     rsp, 0E0h
0x18000444a  pop     rbx
0x18000444b  retn
```
