# PingCleanup

- ea: `0x180033e3c`
- end: `0x180034068`
- name: `PingCleanup`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180053c80`

## callees

- `0x18000282c`
- `0x180033e3c`

## import_xrefs

- `IPHLPAPI!IcmpCloseHandle` at `0x18003401d`
- `IPHLPAPI!IcmpCloseHandle` at `0x18003401d`
- `KERNEL32!WaitForSingleObject` at `0x180033e8c`
- `KERNEL32!WaitForSingleObject` at `0x180033e8c`
- `KERNEL32!SetEvent` at `0x180033e71`
- `KERNEL32!SetEvent` at `0x180033e71`
- `KERNEL32!DeleteCriticalSection` at `0x180034030`
- `KERNEL32!DeleteCriticalSection` at `0x180034043`
- `KERNEL32!DeleteCriticalSection` at `0x180034056`
- `KERNEL32!DeleteCriticalSection` at `0x180034030`
- `KERNEL32!DeleteCriticalSection` at `0x180034043`
- `KERNEL32!DeleteCriticalSection` at `0x180034056`
- `KERNEL32!CloseHandle` at `0x180033ed4`
- `KERNEL32!CloseHandle` at `0x180033eec`
- `KERNEL32!CloseHandle` at `0x180033f04`
- `KERNEL32!CloseHandle` at `0x180033f17`
- `KERNEL32!CloseHandle` at `0x180033ed4`
- `KERNEL32!CloseHandle` at `0x180033eec`
- `KERNEL32!CloseHandle` at `0x180033f04`
- `KERNEL32!CloseHandle` at `0x180033f17`
- `KERNEL32!EnterCriticalSection` at `0x180033f2a`
- `KERNEL32!EnterCriticalSection` at `0x180033f9b`
- `KERNEL32!EnterCriticalSection` at `0x180033f2a`
- `KERNEL32!EnterCriticalSection` at `0x180033f9b`
- `KERNEL32!LeaveCriticalSection` at `0x180033f88`
- `KERNEL32!LeaveCriticalSection` at `0x180034000`
- `KERNEL32!LeaveCriticalSection` at `0x180033f88`
- `KERNEL32!LeaveCriticalSection` at `0x180034000`
- `KERNEL32!HeapFree` at `0x180033f73`
- `KERNEL32!HeapFree` at `0x180033fe4`
- `KERNEL32!HeapFree` at `0x180033f73`
- `KERNEL32!HeapFree` at `0x180033fe4`

## pseudocode

```c
void PingCleanup()
{
  DWORD v0; // eax
  void *v1; // r8
  _QWORD *v2; // rcx
  LPVOID *v3; // rax
  _QWORD *v4; // r8
  __int64 v5; // rdx
  _QWORD *v6; // rax
  HANDLE v7; // rcx

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
      v4 = (_QWORD *)(IcmpRequestsList - 16);
      v5 = *(_QWORD *)IcmpRequestsList;
      if ( *(_QWORD *)(*(_QWORD *)IcmpRequestsList + 8LL) != IcmpRequestsList )
        goto LABEL_24;
      v6 = (_QWORD *)v4[3];
      if ( *v6 != IcmpRequestsList )
        goto LABEL_24;
      v7 = gDhcpHeap;
      *v6 = v5;
      *(_QWORD *)(v5 + 8) = v6;
      HeapFree(v7, 0, v4);
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
0x180033e3c  sub     rsp, 28h
0x180033e40  mov     eax, cs:PingInitLevel
0x180033e46  test    eax, eax
0x180033e48  jz      loc_180034062
0x180033e4e  dec     eax
0x180033e50  cmp     cs:RepliesThreadHandle, 0
0x180033e58  mov     cs:PingInitLevel, eax
0x180033e5e  jnz     short loc_180033E6A
0x180033e60  cmp     cs:RequestsThreadHandle, 0
0x180033e68  jz      short loc_180033EE0
0x180033e6a  mov     rcx, cs:TerminateEvent; hEvent
0x180033e71  call    cs:__imp_SetEvent
0x180033e78  nop     dword ptr [rax+rax+00h]
0x180033e7d  mov     rcx, cs:RequestsThreadHandle; hHandle
0x180033e84  test    rcx, rcx
0x180033e87  jz      short loc_180033EE0
0x180033e89  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180033e8c  call    cs:__imp_WaitForSingleObject
0x180033e93  nop     dword ptr [rax+rax+00h]
0x180033e98  test    eax, eax
0x180033e9a  jz      short loc_180033ECD
0x180033e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033ea3  lea     rdx, WPP_GLOBAL_Control
0x180033eaa  cmp     rcx, rdx
0x180033ead  jz      short loc_180033ECD
0x180033eaf  test    byte ptr [rcx+1Ch], 10h
0x180033eb3  jz      short loc_180033ECD
0x180033eb5  mov     rcx, [rcx+10h]
0x180033eb9  lea     r8, WPP_62219ab234c230d680702fde24520652_Traceguids
0x180033ec0  mov     edx, 15h
0x180033ec5  mov     r9d, eax
0x180033ec8  call    WPP_SF_D
0x180033ecd  mov     rcx, cs:RequestsThreadHandle; hObject
0x180033ed4  call    cs:__imp_CloseHandle
0x180033edb  nop     dword ptr [rax+rax+00h]
0x180033ee0  mov     rcx, cs:IcmpRepliesEvent; hObject
0x180033ee7  test    rcx, rcx
0x180033eea  jz      short loc_180033EF8
0x180033eec  call    cs:__imp_CloseHandle
0x180033ef3  nop     dword ptr [rax+rax+00h]
0x180033ef8  mov     rcx, cs:IcmpRequestsEvent; hObject
0x180033eff  test    rcx, rcx
0x180033f02  jz      short loc_180033F10
0x180033f04  call    cs:__imp_CloseHandle
0x180033f0b  nop     dword ptr [rax+rax+00h]
0x180033f10  mov     rcx, cs:TerminateEvent; hObject
0x180033f17  call    cs:__imp_CloseHandle
0x180033f1e  nop     dword ptr [rax+rax+00h]
0x180033f23  lea     rcx, IcmpRepliesCritSect; lpCriticalSection
0x180033f2a  call    cs:__imp_EnterCriticalSection
0x180033f31  nop     dword ptr [rax+rax+00h]
0x180033f36  mov     r8, cs:IcmpRepliesList; lpMem
0x180033f3d  lea     rax, IcmpRepliesList
0x180033f44  cmp     r8, rax
0x180033f47  jz      short loc_180033F81
0x180033f49  mov     rcx, [r8]
0x180033f4c  cmp     [rcx+8], r8
0x180033f50  jnz     loc_180033FF2
0x180033f56  mov     rax, [r8+8]
0x180033f5a  cmp     [rax], r8
0x180033f5d  jnz     loc_180033FF2
0x180033f63  mov     [rax], rcx
0x180033f66  xor     edx, edx; dwFlags
0x180033f68  mov     [rcx+8], rax
0x180033f6c  mov     rcx, cs:gDhcpHeap; hHeap
0x180033f73  call    cs:__imp_HeapFree
0x180033f7a  nop     dword ptr [rax+rax+00h]
0x180033f7f  jmp     short loc_180033F36
0x180033f81  lea     rcx, IcmpRepliesCritSect; lpCriticalSection
0x180033f88  call    cs:__imp_LeaveCriticalSection
0x180033f8f  nop     dword ptr [rax+rax+00h]
0x180033f94  lea     rcx, IcmpRequestsCritSect; lpCriticalSection
0x180033f9b  call    cs:__imp_EnterCriticalSection
0x180033fa2  nop     dword ptr [rax+rax+00h]
0x180033fa7  mov     rax, cs:IcmpRequestsList
0x180033fae  lea     rcx, IcmpRequestsList
0x180033fb5  cmp     rax, rcx
0x180033fb8  jz      short loc_180033FF9
0x180033fba  lea     r8, [rax-10h]; lpMem
0x180033fbe  lea     rcx, [r8+10h]
0x180033fc2  mov     rdx, [rcx]
0x180033fc5  cmp     [rdx+8], rcx
0x180033fc9  jnz     short loc_180033FF2
0x180033fcb  mov     rax, [r8+18h]
0x180033fcf  cmp     [rax], rcx
0x180033fd2  jnz     short loc_180033FF2
0x180033fd4  mov     rcx, cs:gDhcpHeap; hHeap
0x180033fdb  mov     [rax], rdx
0x180033fde  mov     [rdx+8], rax
0x180033fe2  xor     edx, edx; dwFlags
0x180033fe4  call    cs:__imp_HeapFree
0x180033feb  nop     dword ptr [rax+rax+00h]
0x180033ff0  jmp     short loc_180033FA7
0x180033ff2  mov     ecx, 3
0x180033ff7  int     29h; Win8: RtlFailFast(ecx)
0x180033ff9  lea     rcx, IcmpRequestsCritSect; lpCriticalSection
0x180034000  call    cs:__imp_LeaveCriticalSection
0x180034007  nop     dword ptr [rax+rax+00h]
0x18003400c  mov     rcx, cs:IcmpHandle; IcmpHandle
0x180034013  lea     rax, [rcx-1]
0x180034017  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003401b  ja      short loc_180034029
0x18003401d  call    cs:__imp_IcmpCloseHandle
0x180034024  nop     dword ptr [rax+rax+00h]
0x180034029  lea     rcx, IcmpRepliesCritSect; lpCriticalSection
0x180034030  call    cs:__imp_DeleteCriticalSection
0x180034037  nop     dword ptr [rax+rax+00h]
0x18003403c  lea     rcx, IcmpRequestsCritSect; lpCriticalSection
0x180034043  call    cs:__imp_DeleteCriticalSection
0x18003404a  nop     dword ptr [rax+rax+00h]
0x18003404f  lea     rcx, OutputCritSect; lpCriticalSection
0x180034056  call    cs:__imp_DeleteCriticalSection
0x18003405d  nop     dword ptr [rax+rax+00h]
0x180034062  add     rsp, 28h
0x180034066  retn
```
