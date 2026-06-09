# I_ScPnPFreeState

- ea: `0x180019fa4`
- end: `0x18001a181`
- name: `I_ScPnPFreeState`
- size: `477`
- prototype: `__int64 __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ec48`
- `0x18001a44c`

## callees

- `0x180001274`
- `0x18000132c`
- `0x180004600`
- `0x18000e47c`
- `0x18000e7b8`
- `0x180018b58`
- `0x180019fa4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001a058`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001a058`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001a04b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001a04b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a133`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a133`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a034`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a0d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a034`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a0d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a0de`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a0f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a0de`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a0f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a019`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a0b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a019`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a0b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a082`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a082`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a02b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a02b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a08f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a08f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a106`

## pseudocode

```c
__int64 __fastcall I_ScPnPFreeState(char *lpMem)
{
  STRSAFE_LPSTR v2; // rcx
  void *v3; // rcx
  struct _TP_CLEANUP_GROUP *v4; // rcx
  void *v5; // rcx
  bool v6; // zf
  void *v7; // rcx
  __int64 result; // rax

  WppTraceIndent(lpMem, 0);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  if ( lpMem )
  {
    ReaderMonitorStopThread(lpMem);
    if ( *((_DWORD *)lpMem + 134) == 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(lpMem + 496));
      v3 = (void *)*((_QWORD *)lpMem + 61);
      if ( v3 )
        SetEvent(v3);
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 496));
    }
    v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)lpMem + 60);
    if ( v4 )
    {
      CloseThreadpoolCleanupGroupMembers(v4, 0, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)lpMem + 60));
      *((_QWORD *)lpMem + 60) = 0;
    }
    v5 = (void *)*((_QWORD *)lpMem + 28);
    *((_DWORD *)lpMem + 118) = 0;
    if ( v5 )
      WaitForSingleObject(v5, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)lpMem + 28));
    v6 = *((_DWORD *)lpMem + 146) == 1;
    *((_QWORD *)lpMem + 28) = 0;
    if ( v6 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(lpMem + 544));
      I_ScPnPFreeDeviceList(*((LPVOID *)lpMem + 74));
      *((_QWORD *)lpMem + 74) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 544));
      DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 544));
    }
    if ( *((_DWORD *)lpMem + 134) == 1 )
      DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 496));
    v7 = (void *)*((_QWORD *)lpMem + 61);
    if ( v7 )
    {
      CloseHandle(v7);
      *((_QWORD *)lpMem + 61) = 0;
    }
    ReaderMonitorReaderListFree(lpMem);
    I_ReaderMonitorCleanup((__int64)lpMem);
    HeapFree(g_hHeap, 0, lpMem);
  }
  result = WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    return WPP_SF_s(
             *((_QWORD *)WPP_GLOBAL_Control + 2),
             63,
             &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
             WPP_pszIndent);
  }
  return result;
}

```

## disassembly

```asm
0x180019fa4  push    rbx
0x180019fa6  push    rsi
0x180019fa7  push    rdi
0x180019fa8  push    r15
0x180019faa  sub     rsp, 28h
0x180019fae  mov     esi, edx
0x180019fb0  mov     rdi, rcx
0x180019fb3  xor     edx, edx
0x180019fb5  call    WppTraceIndent
0x180019fba  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fc1  lea     r15, WPP_GLOBAL_Control
0x180019fc8  cmp     rcx, r15
0x180019fcb  jz      short loc_180019FF5
0x180019fcd  test    byte ptr [rcx+1Ch], 2
0x180019fd1  jz      short loc_180019FF5
0x180019fd3  cmp     byte ptr [rcx+19h], 5
0x180019fd7  jb      short loc_180019FF5
0x180019fd9  mov     r9, cs:WPP_pszIndent
0x180019fe0  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180019fe7  mov     rcx, [rcx+10h]
0x180019feb  mov     edx, 3Eh ; '>'
0x180019ff0  call    WPP_SF_s
0x180019ff5  test    rdi, rdi
0x180019ff8  jz      loc_18001A139
0x180019ffe  mov     rcx, rdi
0x18001a001  call    ReaderMonitorStopThread
0x18001a006  cmp     dword ptr [rdi+218h], 1
0x18001a00d  jnz     short loc_18001A03A
0x18001a00f  lea     rbx, [rdi+1F0h]
0x18001a016  mov     rcx, rbx; lpCriticalSection
0x18001a019  call    cs:__imp_EnterCriticalSection
0x18001a01f  mov     rcx, [rdi+1E8h]; hEvent
0x18001a026  test    rcx, rcx
0x18001a029  jz      short loc_18001A031
0x18001a02b  call    cs:__imp_SetEvent
0x18001a031  mov     rcx, rbx; lpCriticalSection
0x18001a034  call    cs:__imp_LeaveCriticalSection
0x18001a03a  mov     rcx, [rdi+1E0h]; ptpcg
0x18001a041  test    rcx, rcx
0x18001a044  jz      short loc_18001A069
0x18001a046  xor     r8d, r8d; pvCleanupContext
0x18001a049  xor     edx, edx; fCancelPendingCallbacks
0x18001a04b  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001a051  mov     rcx, [rdi+1E0h]; ptpcg
0x18001a058  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001a05e  mov     qword ptr [rdi+1E0h], 0
0x18001a069  mov     rcx, [rdi+0E0h]; hHandle
0x18001a070  mov     dword ptr [rdi+1D8h], 0
0x18001a07a  test    rcx, rcx
0x18001a07d  jz      short loc_18001A088
0x18001a07f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a082  call    cs:__imp_WaitForSingleObject
0x18001a088  mov     rcx, [rdi+0E0h]; hObject
0x18001a08f  call    cs:__imp_CloseHandle
0x18001a095  cmp     dword ptr [rdi+248h], 1
0x18001a09c  mov     qword ptr [rdi+0E0h], 0
0x18001a0a7  jnz     short loc_18001A0E4
0x18001a0a9  lea     rbx, [rdi+220h]
0x18001a0b0  mov     rcx, rbx; lpCriticalSection
0x18001a0b3  call    cs:__imp_EnterCriticalSection
0x18001a0b9  mov     rcx, [rdi+250h]; lpMem
0x18001a0c0  mov     edx, esi
0x18001a0c2  call    I_ScPnPFreeDeviceList
0x18001a0c7  mov     rcx, rbx; lpCriticalSection
0x18001a0ca  mov     qword ptr [rdi+250h], 0
0x18001a0d5  call    cs:__imp_LeaveCriticalSection
0x18001a0db  mov     rcx, rbx; lpCriticalSection
0x18001a0de  call    cs:__imp_DeleteCriticalSection
0x18001a0e4  cmp     dword ptr [rdi+218h], 1
0x18001a0eb  jnz     short loc_18001A0FA
0x18001a0ed  lea     rcx, [rdi+1F0h]; lpCriticalSection
0x18001a0f4  call    cs:__imp_DeleteCriticalSection
0x18001a0fa  mov     rcx, [rdi+1E8h]; hObject
0x18001a101  test    rcx, rcx
0x18001a104  jz      short loc_18001A117
0x18001a106  call    cs:__imp_CloseHandle
0x18001a10c  mov     qword ptr [rdi+1E8h], 0
0x18001a117  mov     rcx, rdi
0x18001a11a  call    ReaderMonitorReaderListFree
0x18001a11f  mov     rcx, rdi
0x18001a122  call    I_ReaderMonitorCleanup
0x18001a127  mov     rcx, cs:g_hHeap; hHeap
0x18001a12e  mov     r8, rdi; lpMem
0x18001a131  xor     edx, edx; dwFlags
0x18001a133  call    cs:__imp_HeapFree
0x18001a139  mov     edx, 1
0x18001a13e  call    WppTraceIndent
0x18001a143  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a14a  cmp     rcx, r15
0x18001a14d  jz      short loc_18001A177
0x18001a14f  test    byte ptr [rcx+1Ch], 2
0x18001a153  jz      short loc_18001A177
0x18001a155  cmp     byte ptr [rcx+19h], 5
0x18001a159  jb      short loc_18001A177
0x18001a15b  mov     r9, cs:WPP_pszIndent
0x18001a162  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a169  mov     rcx, [rcx+10h]
0x18001a16d  mov     edx, 3Fh ; '?'
0x18001a172  call    WPP_SF_s
0x18001a177  add     rsp, 28h
0x18001a17b  pop     r15
0x18001a17d  pop     rdi
0x18001a17e  pop     rsi
0x18001a17f  pop     rbx
0x18001a180  retn
```
