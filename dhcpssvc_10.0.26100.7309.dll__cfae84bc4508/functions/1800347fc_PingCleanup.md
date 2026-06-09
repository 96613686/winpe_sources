# PingCleanup

- ea: `0x1800347fc`
- end: `0x180034a28`
- name: `PingCleanup`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180053f60`

## callees

- `0x180002854`
- `0x1800347fc`

## import_xrefs

- `IPHLPAPI!IcmpCloseHandle` at `0x1800349dd`
- `IPHLPAPI!IcmpCloseHandle` at `0x1800349dd`
- `KERNEL32!WaitForSingleObject` at `0x18003484c`
- `KERNEL32!WaitForSingleObject` at `0x18003484c`
- `KERNEL32!SetEvent` at `0x180034831`
- `KERNEL32!SetEvent` at `0x180034831`
- `KERNEL32!DeleteCriticalSection` at `0x1800349f0`
- `KERNEL32!DeleteCriticalSection` at `0x180034a03`
- `KERNEL32!DeleteCriticalSection` at `0x180034a16`
- `KERNEL32!DeleteCriticalSection` at `0x1800349f0`
- `KERNEL32!DeleteCriticalSection` at `0x180034a03`
- `KERNEL32!DeleteCriticalSection` at `0x180034a16`
- `KERNEL32!CloseHandle` at `0x180034894`
- `KERNEL32!CloseHandle` at `0x1800348ac`
- `KERNEL32!CloseHandle` at `0x1800348c4`
- `KERNEL32!CloseHandle` at `0x1800348d7`
- `KERNEL32!CloseHandle` at `0x180034894`
- `KERNEL32!CloseHandle` at `0x1800348ac`
- `KERNEL32!CloseHandle` at `0x1800348c4`
- `KERNEL32!CloseHandle` at `0x1800348d7`
- `KERNEL32!EnterCriticalSection` at `0x1800348ea`
- `KERNEL32!EnterCriticalSection` at `0x18003495b`
- `KERNEL32!EnterCriticalSection` at `0x1800348ea`
- `KERNEL32!EnterCriticalSection` at `0x18003495b`
- `KERNEL32!LeaveCriticalSection` at `0x180034948`
- `KERNEL32!LeaveCriticalSection` at `0x1800349c0`
- `KERNEL32!LeaveCriticalSection` at `0x180034948`
- `KERNEL32!LeaveCriticalSection` at `0x1800349c0`
- `KERNEL32!HeapFree` at `0x180034933`
- `KERNEL32!HeapFree` at `0x1800349a4`
- `KERNEL32!HeapFree` at `0x180034933`
- `KERNEL32!HeapFree` at `0x1800349a4`

## pseudocode

```c
void PingCleanup()
{
  DWORD v0; // eax
  void *v1; // r8
  _QWORD *v2; // rcx
  LPVOID *v3; // rax
  void *v4; // r8
  __int64 v5; // rdx
  _QWORD *v6; // rcx

  if ( PingInitLevel )
  {
    --PingInitLevel;
    if ( RepliesThreadHandle || RequestsThreadHandle )
    {
      SetEvent(TerminateEvent);
      if ( RequestsThreadHandle )
      {
        v0 = WaitForSingleObject(RequestsThreadHandle, 0xFFFFFFFF);
        if ( v0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_62219ab234c230d680702fde24520652_Traceguids, v0);
        }
        CloseHandle(RequestsThreadHandle);
      }
    }
    if ( IcmpRepliesEvent )
      CloseHandle(IcmpRepliesEvent);
    if ( IcmpRequestsEvent )
      CloseHandle(IcmpRequestsEvent);
    CloseHandle(TerminateEvent);
    EnterCriticalSection(&IcmpRepliesCritSect);
    while ( 1 )
    {
      v1 = IcmpRepliesList;
      if ( IcmpRepliesList == &IcmpRepliesList )
        break;
      v2 = *(_QWORD **)IcmpRepliesList;
      if ( *(LPVOID *)(*(_QWORD *)IcmpRepliesList + 8LL) != IcmpRepliesList
        || (v3 = (LPVOID *)*((_QWORD *)IcmpRepliesList + 1), *v3 != IcmpRepliesList) )
      {
LABEL_24:
        __fastfail(3u);
      }
      *v3 = v2;
      v2[1] = v3;
      HeapFree(gDhcpHeap, 0, v1);
    }
    LeaveCriticalSection(&IcmpRepliesCritSect);
    EnterCriticalSection(&IcmpRequestsCritSect);
    while ( (__int64 *)IcmpRequestsList != &IcmpRequestsList )
    {
      v4 = (void *)(IcmpRequestsList - 16);
      v5 = *(_QWORD *)IcmpRequestsList;
      if ( *(_QWORD *)(*(_QWORD *)IcmpRequestsList + 8LL) != IcmpRequestsList )
        goto LABEL_24;
      v6 = *(_QWORD **)(IcmpRequestsList + 8);
      if ( *v6 != IcmpRequestsList )
        goto LABEL_24;
      *v6 = v5;
      *(_QWORD *)(v5 + 8) = v6;
      HeapFree(gDhcpHeap, 0, v4);
    }
    LeaveCriticalSection(&IcmpRequestsCritSect);
    if ( (char *)IcmpHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      IcmpCloseHandle(IcmpHandle);
    DeleteCriticalSection(&IcmpRepliesCritSect);
    DeleteCriticalSection(&IcmpRequestsCritSect);
    DeleteCriticalSection(&OutputCritSect);
  }
}

```

## disassembly

```asm
0x1800347fc  sub     rsp, 28h
0x180034800  mov     eax, cs:PingInitLevel
0x180034806  test    eax, eax
0x180034808  jz      loc_180034A22
0x18003480e  dec     eax
0x180034810  cmp     cs:RepliesThreadHandle, 0
0x180034818  mov     cs:PingInitLevel, eax
0x18003481e  jnz     short loc_18003482A
0x180034820  cmp     cs:RequestsThreadHandle, 0
0x180034828  jz      short loc_1800348A0
0x18003482a  mov     rcx, cs:TerminateEvent; hEvent
0x180034831  call    cs:__imp_SetEvent
0x180034838  nop     dword ptr [rax+rax+00h]
0x18003483d  mov     rcx, cs:RequestsThreadHandle; hHandle
0x180034844  test    rcx, rcx
0x180034847  jz      short loc_1800348A0
0x180034849  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003484c  call    cs:__imp_WaitForSingleObject
0x180034853  nop     dword ptr [rax+rax+00h]
0x180034858  test    eax, eax
0x18003485a  jz      short loc_18003488D
0x18003485c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034863  lea     rdx, WPP_GLOBAL_Control
0x18003486a  cmp     rcx, rdx
0x18003486d  jz      short loc_18003488D
0x18003486f  test    byte ptr [rcx+1Ch], 10h
0x180034873  jz      short loc_18003488D
0x180034875  mov     rcx, [rcx+10h]
0x180034879  lea     r8, WPP_62219ab234c230d680702fde24520652_Traceguids
0x180034880  mov     edx, 15h
0x180034885  mov     r9d, eax
0x180034888  call    WPP_SF_D
0x18003488d  mov     rcx, cs:RequestsThreadHandle; hObject
0x180034894  call    cs:__imp_CloseHandle
0x18003489b  nop     dword ptr [rax+rax+00h]
0x1800348a0  mov     rcx, cs:IcmpRepliesEvent; hObject
0x1800348a7  test    rcx, rcx
0x1800348aa  jz      short loc_1800348B8
0x1800348ac  call    cs:__imp_CloseHandle
0x1800348b3  nop     dword ptr [rax+rax+00h]
0x1800348b8  mov     rcx, cs:IcmpRequestsEvent; hObject
0x1800348bf  test    rcx, rcx
0x1800348c2  jz      short loc_1800348D0
0x1800348c4  call    cs:__imp_CloseHandle
0x1800348cb  nop     dword ptr [rax+rax+00h]
0x1800348d0  mov     rcx, cs:TerminateEvent; hObject
0x1800348d7  call    cs:__imp_CloseHandle
0x1800348de  nop     dword ptr [rax+rax+00h]
0x1800348e3  lea     rcx, IcmpRepliesCritSect; lpCriticalSection
0x1800348ea  call    cs:__imp_EnterCriticalSection
0x1800348f1  nop     dword ptr [rax+rax+00h]
0x1800348f6  mov     r8, cs:IcmpRepliesList; lpMem
0x1800348fd  lea     rax, IcmpRepliesList
0x180034904  cmp     r8, rax
0x180034907  jz      short loc_180034941
0x180034909  mov     rcx, [r8]
0x18003490c  cmp     [rcx+8], r8
0x180034910  jnz     loc_1800349B2
0x180034916  mov     rax, [r8+8]
0x18003491a  cmp     [rax], r8
0x18003491d  jnz     loc_1800349B2
0x180034923  mov     [rax], rcx
0x180034926  xor     edx, edx; dwFlags
0x180034928  mov     [rcx+8], rax
0x18003492c  mov     rcx, cs:gDhcpHeap; hHeap
0x180034933  call    cs:__imp_HeapFree
0x18003493a  nop     dword ptr [rax+rax+00h]
0x18003493f  jmp     short loc_1800348F6
0x180034941  lea     rcx, IcmpRepliesCritSect; lpCriticalSection
0x180034948  call    cs:__imp_LeaveCriticalSection
0x18003494f  nop     dword ptr [rax+rax+00h]
0x180034954  lea     rcx, IcmpRequestsCritSect; lpCriticalSection
0x18003495b  call    cs:__imp_EnterCriticalSection
0x180034962  nop     dword ptr [rax+rax+00h]
0x180034967  mov     rax, cs:IcmpRequestsList
0x18003496e  lea     rcx, IcmpRequestsList
0x180034975  cmp     rax, rcx
0x180034978  jz      short loc_1800349B9
0x18003497a  lea     r8, [rax-10h]; lpMem
0x18003497e  lea     rax, [r8+10h]
0x180034982  mov     rdx, [rax]
0x180034985  cmp     [rdx+8], rax
0x180034989  jnz     short loc_1800349B2
0x18003498b  mov     rcx, [rax+8]
0x18003498f  cmp     [rcx], rax
0x180034992  jnz     short loc_1800349B2
0x180034994  mov     [rcx], rdx
0x180034997  mov     [rdx+8], rcx
0x18003499b  xor     edx, edx; dwFlags
0x18003499d  mov     rcx, cs:gDhcpHeap; hHeap
0x1800349a4  call    cs:__imp_HeapFree
0x1800349ab  nop     dword ptr [rax+rax+00h]
0x1800349b0  jmp     short loc_180034967
0x1800349b2  mov     ecx, 3
0x1800349b7  int     29h; Win8: RtlFailFast(ecx)
0x1800349b9  lea     rcx, IcmpRequestsCritSect; lpCriticalSection
0x1800349c0  call    cs:__imp_LeaveCriticalSection
0x1800349c7  nop     dword ptr [rax+rax+00h]
0x1800349cc  mov     rcx, cs:IcmpHandle; IcmpHandle
0x1800349d3  lea     rax, [rcx-1]
0x1800349d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800349db  ja      short loc_1800349E9
0x1800349dd  call    cs:__imp_IcmpCloseHandle
0x1800349e4  nop     dword ptr [rax+rax+00h]
0x1800349e9  lea     rcx, IcmpRepliesCritSect; lpCriticalSection
0x1800349f0  call    cs:__imp_DeleteCriticalSection
0x1800349f7  nop     dword ptr [rax+rax+00h]
0x1800349fc  lea     rcx, IcmpRequestsCritSect; lpCriticalSection
0x180034a03  call    cs:__imp_DeleteCriticalSection
0x180034a0a  nop     dword ptr [rax+rax+00h]
0x180034a0f  lea     rcx, OutputCritSect; lpCriticalSection
0x180034a16  call    cs:__imp_DeleteCriticalSection
0x180034a1d  nop     dword ptr [rax+rax+00h]
0x180034a22  add     rsp, 28h
0x180034a26  retn
```
