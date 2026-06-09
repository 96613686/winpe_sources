# NcaServiceShutdown(void)

- ea: `0x180004984`
- end: `0x180004c19`
- name: `?NcaServiceShutdown@@YAXXZ`
- size: `661`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800026d0`
- `0x1800048e0`

## callees

- `0x180004380`
- `0x180004680`
- `0x180004984`
- `0x180004db4`
- `0x180004f04`
- `0x1800190a0`
- `0x180019a3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004afc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004afc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800049e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800049e6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800049c6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800049c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ae9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ae9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b61`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b19`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b19`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b2c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b2c`
- `KERNEL32!UnregisterWait` at `0x180004b49`
- `KERNEL32!UnregisterWait` at `0x180004b49`

## pseudocode

```c
void NcaServiceShutdown(void)
{
  PVOID *v0; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  SetEvent(gNcaMain);
  while ( dword_180028AE8 && !WaitForSingleObject(hHandle, 0xFFFFFFFF) )
    ;
  if ( ServiceStatus.dwCurrentState != 1 )
  {
    NcaServiceChangeState(3u);
    if ( byte_180028B6E )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      NcaComponentsShutdown(22, off_18001F010);
      byte_180028B6E = 0;
    }
    if ( byte_180028B6D )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      NcaComponentsShutdown(4, &off_18001F170);
      byte_180028B6D = 0;
    }
    if ( byte_180028B6C )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      NcaComponentsShutdown(2, off_18001F1B0);
      byte_180028B6C = 0;
    }
    if ( dword_180028B68 == 1 )
    {
      EnterCriticalSection(&stru_180028AF0);
      LeaveCriticalSection(&stru_180028AF0);
    }
  }
  if ( pti )
  {
    WaitForThreadpoolTimerCallbacks(pti, 1);
    CloseThreadpoolTimer(pti);
    NcaSQMSubmit();
  }
  if ( WaitHandle )
    UnregisterWait(WaitHandle);
  if ( hEvent )
    CloseHandle(hEvent);
  NcaCriticalSectionDestroy(&stru_180028AF0);
  NcaDestroyCancelableLock((struct _tag_NCA_CANCELABLE_LOCK *)&gNcaMain);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  ServiceStatus.dwControlsAccepted = 0;
  NcaServiceChangeState(1u);
  hServiceStatus = 0;
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 8) != 0 )
      WPP_SF_(v0[2], 35, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  }
}

```

## disassembly

```asm
0x180004984  mov     [rsp+arg_0], rbp
0x180004989  push    rdi
0x18000498a  sub     rsp, 20h
0x18000498e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004995  lea     rdi, WPP_GLOBAL_Control
0x18000499c  lea     rbp, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800049a3  cmp     rcx, rdi
0x1800049a6  jz      short loc_1800049BF
0x1800049a8  test    byte ptr [rcx+1Ch], 8
0x1800049ac  jz      short loc_1800049BF
0x1800049ae  mov     rcx, [rcx+10h]
0x1800049b2  mov     edx, 1Dh
0x1800049b7  mov     r8, rbp
0x1800049ba  call    WPP_SF_
0x1800049bf  mov     rcx, cs:?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; hEvent
0x1800049c6  call    cs:__imp_SetEvent
0x1800049cd  nop     dword ptr [rax+rax+00h]
0x1800049d2  mov     eax, cs:dword_180028AE8
0x1800049d8  test    eax, eax
0x1800049da  jz      short loc_1800049F6
0x1800049dc  mov     rcx, cs:hHandle; hHandle
0x1800049e3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800049e6  call    cs:__imp_WaitForSingleObject
0x1800049ed  nop     dword ptr [rax+rax+00h]
0x1800049f2  test    eax, eax
0x1800049f4  jz      short loc_1800049D2
0x1800049f6  cmp     cs:ServiceStatus.dwCurrentState, 1
0x1800049fd  jz      loc_180004B08
0x180004a03  mov     ecx, 3; unsigned int
0x180004a08  call    ?NcaServiceChangeState@@YAJK@Z; NcaServiceChangeState(ulong)
0x180004a0d  cmp     cs:byte_180028B6E, 0
0x180004a14  jz      short loc_180004A51
0x180004a16  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a1d  cmp     rcx, rdi
0x180004a20  jz      short loc_180004A39
0x180004a22  test    byte ptr [rcx+1Ch], 4
0x180004a26  jz      short loc_180004A39
0x180004a28  mov     rcx, [rcx+10h]
0x180004a2c  mov     edx, 1Eh
0x180004a31  mov     r8, rbp
0x180004a34  call    WPP_SF_
0x180004a39  lea     rdx, off_18001F010
0x180004a40  mov     ecx, 16h
0x180004a45  call    NcaComponentsShutdown
0x180004a4a  mov     cs:byte_180028B6E, 0
0x180004a51  cmp     cs:byte_180028B6D, 0
0x180004a58  jz      short loc_180004A95
0x180004a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a61  cmp     rcx, rdi
0x180004a64  jz      short loc_180004A7D
0x180004a66  test    byte ptr [rcx+1Ch], 4
0x180004a6a  jz      short loc_180004A7D
0x180004a6c  mov     rcx, [rcx+10h]
0x180004a70  mov     edx, 1Fh
0x180004a75  mov     r8, rbp
0x180004a78  call    WPP_SF_
0x180004a7d  lea     rdx, off_18001F170
0x180004a84  mov     ecx, 4
0x180004a89  call    NcaComponentsShutdown
0x180004a8e  mov     cs:byte_180028B6D, 0
0x180004a95  cmp     cs:byte_180028B6C, 0
0x180004a9c  jz      short loc_180004AD9
0x180004a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004aa5  cmp     rcx, rdi
0x180004aa8  jz      short loc_180004AC1
0x180004aaa  test    byte ptr [rcx+1Ch], 4
0x180004aae  jz      short loc_180004AC1
0x180004ab0  mov     rcx, [rcx+10h]
0x180004ab4  mov     edx, 20h ; ' '
0x180004ab9  mov     r8, rbp
0x180004abc  call    WPP_SF_
0x180004ac1  lea     rdx, off_18001F1B0
0x180004ac8  mov     ecx, 2
0x180004acd  call    NcaComponentsShutdown
0x180004ad2  mov     cs:byte_180028B6C, 0
0x180004ad9  cmp     cs:dword_180028B68, 1
0x180004ae0  jnz     short loc_180004B08
0x180004ae2  lea     rcx, stru_180028AF0; lpCriticalSection
0x180004ae9  call    cs:__imp_EnterCriticalSection
0x180004af0  nop     dword ptr [rax+rax+00h]
0x180004af5  lea     rcx, stru_180028AF0; lpCriticalSection
0x180004afc  call    cs:__imp_LeaveCriticalSection
0x180004b03  nop     dword ptr [rax+rax+00h]
0x180004b08  mov     rcx, cs:pti; pti
0x180004b0f  test    rcx, rcx
0x180004b12  jz      short loc_180004B3D
0x180004b14  mov     edx, 1; fCancelPendingCallbacks
0x180004b19  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004b20  nop     dword ptr [rax+rax+00h]
0x180004b25  mov     rcx, cs:pti; pti
0x180004b2c  call    cs:__imp_CloseThreadpoolTimer
0x180004b33  nop     dword ptr [rax+rax+00h]
0x180004b38  call    NcaSQMSubmit
0x180004b3d  mov     rcx, cs:WaitHandle; WaitHandle
0x180004b44  test    rcx, rcx
0x180004b47  jz      short loc_180004B55
0x180004b49  call    cs:__imp_UnregisterWait
0x180004b50  nop     dword ptr [rax+rax+00h]
0x180004b55  mov     rcx, cs:hEvent; hObject
0x180004b5c  test    rcx, rcx
0x180004b5f  jz      short loc_180004B6D
0x180004b61  call    cs:__imp_CloseHandle
0x180004b68  nop     dword ptr [rax+rax+00h]
0x180004b6d  lea     rcx, stru_180028AF0; lpCriticalSection
0x180004b74  call    NcaCriticalSectionDestroy
0x180004b79  lea     rcx, ?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; struct _tag_NCA_CANCELABLE_LOCK *
0x180004b80  call    ?NcaDestroyCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaDestroyCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x180004b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b8c  cmp     rcx, rdi
0x180004b8f  jz      short loc_180004BA8
0x180004b91  test    byte ptr [rcx+1Ch], 4
0x180004b95  jz      short loc_180004BA8
0x180004b97  mov     rcx, [rcx+10h]
0x180004b9b  mov     edx, 21h ; '!'
0x180004ba0  mov     r8, rbp
0x180004ba3  call    WPP_SF_
0x180004ba8  mov     ecx, 1; unsigned int
0x180004bad  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x180004bb7  call    ?NcaServiceChangeState@@YAJK@Z; NcaServiceChangeState(ulong)
0x180004bbc  mov     cs:hServiceStatus, 0
0x180004bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bce  cmp     rcx, rdi
0x180004bd1  jz      short loc_180004C0D
0x180004bd3  test    byte ptr [rcx+1Ch], 4
0x180004bd7  jz      short loc_180004BF1
0x180004bd9  mov     rcx, [rcx+10h]
0x180004bdd  mov     edx, 22h ; '"'
0x180004be2  mov     r8, rbp
0x180004be5  call    WPP_SF_
0x180004bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bf1  cmp     rcx, rdi
0x180004bf4  jz      short loc_180004C0D
0x180004bf6  test    byte ptr [rcx+1Ch], 8
0x180004bfa  jz      short loc_180004C0D
0x180004bfc  mov     rcx, [rcx+10h]
0x180004c00  mov     edx, 23h ; '#'
0x180004c05  mov     r8, rbp
0x180004c08  call    WPP_SF_
0x180004c0d  mov     rbp, [rsp+28h+arg_0]
0x180004c12  add     rsp, 20h
0x180004c16  pop     rdi
0x180004c17  retn
```
