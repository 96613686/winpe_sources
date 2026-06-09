# NlResetWriterClientSession(_CLIENT_SESSION *)

- ea: `0x18006c2e8`
- end: `0x18006c3db`
- name: `?NlResetWriterClientSession@@YAXPEAU_CLIENT_SESSION@@@Z`
- size: `243`
- prototype: `void __fastcall(struct _CLIENT_SESSION *)`
- caller_count: `25`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002346c`
- `0x180029218`
- `0x18002ada0`
- `0x180030078`
- `0x180031a3c`
- `0x180033b90`
- `0x180033f80`
- `0x180035924`
- `0x18004370c`
- `0x180047dfc`
- `0x18005239c`
- `0x18005c514`
- `0x18005dfe0`
- `0x18005eb90`
- `0x18005fa30`
- `0x180061580`
- `0x180061800`
- `0x180068008`
- `0x180069f80`
- `0x18006ad64`
- `0x18006b5b4`
- `0x18006e1bc`
- `0x180070380`
- `0x180073c20`
- `0x180075b60`

## callees

- `0x18000dd00`
- `0x180040f18`
- `0x18006c2e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18006c3a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18006c3a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c3b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c3b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c362`
- `ntdll!RtlLeaveCriticalSection` at `0x18006c387`
- `ntdll!RtlLeaveCriticalSection` at `0x18006c387`
- `ntdll!RtlEnterCriticalSection` at `0x18006c343`
- `ntdll!RtlEnterCriticalSection` at `0x18006c343`

## string_xrefs

- `0x18006c329`: `ClientSession->CsFlags & CS_WRITER`
- `0x18006c300`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006c322`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006c3bd`: `ReleaseSemaphore CsWriterSemaphore returned %ld\n`

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
      0x6C8u,
      a4);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x6C9u,
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
0x18006c2e8  push    rbx
0x18006c2ea  sub     rsp, 20h
0x18006c2ee  cmp     dword ptr [rcx+148h], 0
0x18006c2f5  mov     rbx, rcx
0x18006c2f8  ja      short loc_18006C313
0x18006c2fa  mov     r8d, 6C8h; unsigned int
0x18006c300  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006c307  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18006c30e  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006c313  test    byte ptr [rbx+124h], 8
0x18006c31a  jnz     short loc_18006C335
0x18006c31c  mov     r8d, 6C9h; unsigned int
0x18006c322  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006c329  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x18006c330  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006c335  mov     rcx, [rbx+110h]
0x18006c33c  add     rcx, 190h; CriticalSection
0x18006c343  call    cs:__imp_RtlEnterCriticalSection
0x18006c34a  nop     dword ptr [rax+rax+00h]
0x18006c34f  and     dword ptr [rbx+124h], 0FFFFFFF7h
0x18006c356  mov     rcx, [rbx+2B8h]; hObject
0x18006c35d  test    rcx, rcx
0x18006c360  jz      short loc_18006C379
0x18006c362  call    cs:__imp_CloseHandle
0x18006c369  nop     dword ptr [rax+rax+00h]
0x18006c36e  mov     qword ptr [rbx+2B8h], 0
0x18006c379  mov     rcx, [rbx+110h]
0x18006c380  add     rcx, 190h; CriticalSection
0x18006c387  call    cs:__imp_RtlLeaveCriticalSection
0x18006c38e  nop     dword ptr [rax+rax+00h]
0x18006c393  mov     rcx, [rbx+150h]; hSemaphore
0x18006c39a  xor     r8d, r8d; lpPreviousCount
0x18006c39d  lea     edx, [r8+1]; lReleaseCount
0x18006c3a1  call    cs:__imp_ReleaseSemaphore
0x18006c3a8  nop     dword ptr [rax+rax+00h]
0x18006c3ad  test    eax, eax
0x18006c3af  jnz     short loc_18006C3D4
0x18006c3b1  call    cs:__imp_GetLastError
0x18006c3b8  nop     dword ptr [rax+rax+00h]
0x18006c3bd  lea     r8, aReleasesemapho; "ReleaseSemaphore CsWriterSemaphore retu"...
0x18006c3c4  mov     rdx, rbx; struct _CLIENT_SESSION *
0x18006c3c7  mov     r9d, eax
0x18006c3ca  mov     ecx, 100h; unsigned int
0x18006c3cf  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006c3d4  add     rsp, 20h
0x18006c3d8  pop     rbx
0x18006c3d9  retn
```
