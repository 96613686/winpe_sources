# NlResetWriterClientSession(_CLIENT_SESSION *)

- ea: `0x1800675c0`
- end: `0x180067694`
- name: `?NlResetWriterClientSession@@YAXPEAU_CLIENT_SESSION@@@Z`
- size: `212`
- prototype: `void __fastcall(struct _CLIENT_SESSION *)`
- caller_count: `25`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180022374`
- `0x180027d78`
- `0x180029680`
- `0x18002e478`
- `0x18002fdb4`
- `0x180031d90`
- `0x180032160`
- `0x180033a34`
- `0x180040bf8`
- `0x180044eb8`
- `0x18004ecb8`
- `0x1800585a0`
- `0x180059e9c`
- `0x18005a990`
- `0x18005b7e0`
- `0x18005d1c0`
- `0x18005d440`
- `0x1800636d4`
- `0x180065440`
- `0x180066108`
- `0x180066904`
- `0x18006925c`
- `0x18006b2e0`
- `0x18006e960`
- `0x18007070c`

## callees

- `0x18000d710`
- `0x18003e71c`
- `0x1800675c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180067667`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180067667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067634`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067634`
- `ntdll!RtlLeaveCriticalSection` at `0x180067653`
- `ntdll!RtlLeaveCriticalSection` at `0x180067653`
- `ntdll!RtlEnterCriticalSection` at `0x18006761b`
- `ntdll!RtlEnterCriticalSection` at `0x18006761b`

## string_xrefs

- `0x180067601`: `ClientSession->CsFlags & CS_WRITER`
- `0x1800675d8`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x1800675fa`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180067677`: `ReleaseSemaphore CsWriterSemaphore returned %ld\n`

## pseudocode

```c
void __fastcall NlResetWriterClientSession(struct _CLIENT_SESSION *a1, __int64 a2, __int64 a3, char *a4)
{
  void *v5; // rcx
  DWORD LastError; // eax

  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      1736,
      a4);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      1737,
      a4);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  *((_DWORD *)a1 + 73) &= ~8u;
  v5 = (void *)*((_QWORD *)a1 + 87);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)a1 + 87) = 0;
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  if ( !ReleaseSemaphore(*((HANDLE *)a1 + 42), 1, 0) )
  {
    LastError = GetLastError();
    NlPrintCsRoutine(0x100u, a1, L"ReleaseSemaphore CsWriterSemaphore returned %ld\n", LastError);
  }
}

```

## disassembly

```asm
0x1800675c0  push    rbx
0x1800675c2  sub     rsp, 20h
0x1800675c6  cmp     dword ptr [rcx+148h], 0
0x1800675cd  mov     rbx, rcx
0x1800675d0  ja      short loc_1800675EB
0x1800675d2  mov     r8d, 6C8h; unsigned int
0x1800675d8  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800675df  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x1800675e6  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800675eb  test    byte ptr [rbx+124h], 8
0x1800675f2  jnz     short loc_18006760D
0x1800675f4  mov     r8d, 6C9h; unsigned int
0x1800675fa  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180067601  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x180067608  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006760d  mov     rcx, [rbx+110h]
0x180067614  add     rcx, 190h; CriticalSection
0x18006761b  call    cs:__imp_RtlEnterCriticalSection
0x180067621  and     dword ptr [rbx+124h], 0FFFFFFF7h
0x180067628  mov     rcx, [rbx+2B8h]; hObject
0x18006762f  test    rcx, rcx
0x180067632  jz      short loc_180067645
0x180067634  call    cs:__imp_CloseHandle
0x18006763a  mov     qword ptr [rbx+2B8h], 0
0x180067645  mov     rcx, [rbx+110h]
0x18006764c  add     rcx, 190h; CriticalSection
0x180067653  call    cs:__imp_RtlLeaveCriticalSection
0x180067659  mov     rcx, [rbx+150h]; hSemaphore
0x180067660  xor     r8d, r8d; lpPreviousCount
0x180067663  lea     edx, [r8+1]; lReleaseCount
0x180067667  call    cs:__imp_ReleaseSemaphore
0x18006766d  test    eax, eax
0x18006766f  jnz     short loc_18006768E
0x180067671  call    cs:__imp_GetLastError
0x180067677  lea     r8, aReleasesemapho; "ReleaseSemaphore CsWriterSemaphore retu"...
0x18006767e  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180067681  mov     r9d, eax
0x180067684  mov     ecx, 100h; unsigned int
0x180067689  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006768e  add     rsp, 20h
0x180067692  pop     rbx
0x180067693  retn
```
