# SetServiceIsDownFlagThread(void *)

- ea: `0x1400255a0`
- end: `0x1400257a9`
- name: `?SetServiceIsDownFlagThread@@YAKPEAX@Z`
- size: `521`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x1400255a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140025693`
- `KERNEL32!GetLastError` at `0x1400256f7`
- `KERNEL32!GetLastError` at `0x140025776`
- `KERNEL32!GetLastError` at `0x140025693`
- `KERNEL32!GetLastError` at `0x1400256f7`
- `KERNEL32!GetLastError` at `0x140025776`
- `KERNEL32!SetEvent` at `0x140025671`
- `KERNEL32!SetEvent` at `0x140025671`
- `KERNEL32!WaitForSingleObject` at `0x140025754`
- `KERNEL32!WaitForSingleObject` at `0x140025754`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1400256d5`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1400256d5`

## pseudocode

```c
__int64 __fastcall SetServiceIsDownFlagThread(PVOID Parameter)
{
  unsigned int v1; // edi
  CMapDeviceId *v2; // rcx
  DWORD LastError; // eax
  DWORD v4; // eax
  unsigned int i; // ebx
  DWORD v6; // eax

  v1 = 2;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  g_bServiceIsDown = 1;
  if ( !g_hTapiWorkerThread )
  {
    if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)v2 + 2), 69, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v1 = 1;
  }
  if ( !g_hJobQueueThread )
  {
    if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)v2 + 2), 70, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    --v1;
  }
  if ( g_hJobQueueEvent )
  {
    if ( SetEvent(g_hJobQueueEvent) )
    {
LABEL_23:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_24;
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
      goto LABEL_23;
    }
  }
LABEL_24:
  if ( g_TapiCompletionPort )
  {
    if ( PostQueuedCompletionStatus(g_TapiCompletionPort, 0, 0x80000002, 0) )
    {
LABEL_30:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      goto LABEL_35;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v4);
      goto LABEL_30;
    }
  }
LABEL_31:
  if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_d(*((_QWORD *)v2 + 2), 73, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v1);
LABEL_35:
  for ( i = 0; i < v1; ++i )
  {
    if ( WaitForSingleObject(g_hServiceIsDownSemaphore, 0xFFFFFFFF)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400255a0  push    rbx
0x1400255a2  push    rbp
0x1400255a3  push    rdi
0x1400255a4  push    r14
0x1400255a6  sub     rsp, 28h
0x1400255aa  mov     edi, 2
0x1400255af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400255b6  lea     rbp, WPP_GLOBAL_Control
0x1400255bd  lea     r14, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400255c4  cmp     rcx, rbp
0x1400255c7  jz      short loc_1400255EB
0x1400255c9  test    byte ptr [rcx+1Ch], 4
0x1400255cd  jz      short loc_1400255EB
0x1400255cf  cmp     byte ptr [rcx+19h], 5
0x1400255d3  jb      short loc_1400255EB
0x1400255d5  mov     rcx, [rcx+10h]
0x1400255d9  lea     edx, [rdi+42h]
0x1400255dc  mov     r8, r14
0x1400255df  call    WPP_SF_
0x1400255e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400255eb  cmp     cs:?g_hTapiWorkerThread@@3PEAXEA, 0; void * g_hTapiWorkerThread
0x1400255f3  mov     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x1400255fd  jnz     short loc_14002562D
0x1400255ff  cmp     rcx, rbp
0x140025602  jz      short loc_140025628
0x140025604  test    byte ptr [rcx+1Ch], 4
0x140025608  jz      short loc_140025628
0x14002560a  cmp     byte ptr [rcx+19h], 3
0x14002560e  jb      short loc_140025628
0x140025610  mov     rcx, [rcx+10h]
0x140025614  mov     edx, 45h ; 'E'
0x140025619  mov     r8, r14
0x14002561c  call    WPP_SF_
0x140025621  mov     rcx, cs:WPP_GLOBAL_Control
0x140025628  mov     edi, 1
0x14002562d  cmp     cs:?g_hJobQueueThread@@3PEAXEA, 0; void * g_hJobQueueThread
0x140025635  jnz     short loc_140025662
0x140025637  cmp     rcx, rbp
0x14002563a  jz      short loc_140025660
0x14002563c  test    byte ptr [rcx+1Ch], 4
0x140025640  jz      short loc_140025660
0x140025642  cmp     byte ptr [rcx+19h], 3
0x140025646  jb      short loc_140025660
0x140025648  mov     rcx, [rcx+10h]
0x14002564c  mov     edx, 46h ; 'F'
0x140025651  mov     r8, r14
0x140025654  call    WPP_SF_
0x140025659  mov     rcx, cs:WPP_GLOBAL_Control
0x140025660  dec     edi
0x140025662  mov     rax, cs:?g_hJobQueueEvent@@3PEAXEA; void * g_hJobQueueEvent
0x140025669  test    rax, rax
0x14002566c  jz      short loc_1400256BB
0x14002566e  mov     rcx, rax; hEvent
0x140025671  call    cs:__imp_SetEvent
0x140025677  test    eax, eax
0x140025679  jnz     short loc_1400256B4
0x14002567b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025682  cmp     rcx, rbp
0x140025685  jz      short loc_1400256BB
0x140025687  test    byte ptr [rcx+1Ch], 4
0x14002568b  jz      short loc_1400256BB
0x14002568d  cmp     byte ptr [rcx+19h], 2
0x140025691  jb      short loc_1400256BB
0x140025693  call    cs:__imp_GetLastError
0x140025699  mov     rcx, cs:WPP_GLOBAL_Control
0x1400256a0  mov     edx, 47h ; 'G'
0x1400256a5  mov     r9d, eax
0x1400256a8  mov     r8, r14
0x1400256ab  mov     rcx, [rcx+10h]
0x1400256af  call    WPP_SF_d
0x1400256b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400256bb  mov     rax, cs:?g_TapiCompletionPort@@3PEAXEA; void * g_TapiCompletionPort
0x1400256c2  test    rax, rax
0x1400256c5  jz      short loc_14002571F
0x1400256c7  xor     r9d, r9d; lpOverlapped
0x1400256ca  xor     edx, edx; dwNumberOfBytesTransferred
0x1400256cc  mov     r8d, 80000002h; dwCompletionKey
0x1400256d2  mov     rcx, rax; CompletionPort
0x1400256d5  call    cs:__imp_PostQueuedCompletionStatus
0x1400256db  test    eax, eax
0x1400256dd  jnz     short loc_140025718
0x1400256df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400256e6  cmp     rcx, rbp
0x1400256e9  jz      short loc_140025744
0x1400256eb  test    byte ptr [rcx+1Ch], 4
0x1400256ef  jz      short loc_14002571F
0x1400256f1  cmp     byte ptr [rcx+19h], 2
0x1400256f5  jb      short loc_14002571F
0x1400256f7  call    cs:__imp_GetLastError
0x1400256fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140025704  mov     edx, 48h ; 'H'
0x140025709  mov     r9d, eax
0x14002570c  mov     r8, r14
0x14002570f  mov     rcx, [rcx+10h]
0x140025713  call    WPP_SF_d
0x140025718  mov     rcx, cs:WPP_GLOBAL_Control
0x14002571f  cmp     rcx, rbp
0x140025722  jz      short loc_140025744
0x140025724  test    byte ptr [rcx+1Ch], 4
0x140025728  jz      short loc_140025744
0x14002572a  cmp     byte ptr [rcx+19h], 5
0x14002572e  jb      short loc_140025744
0x140025730  mov     rcx, [rcx+10h]
0x140025734  mov     edx, 49h ; 'I'
0x140025739  mov     r9d, edi
0x14002573c  mov     r8, r14
0x14002573f  call    WPP_SF_d
0x140025744  xor     ebx, ebx
0x140025746  test    edi, edi
0x140025748  jz      short loc_14002579D
0x14002574a  mov     rcx, cs:?g_hServiceIsDownSemaphore@@3PEAXEA; hHandle
0x140025751  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140025754  call    cs:__imp_WaitForSingleObject
0x14002575a  test    eax, eax
0x14002575c  jz      short loc_140025797
0x14002575e  mov     rax, cs:WPP_GLOBAL_Control
0x140025765  cmp     rax, rbp
0x140025768  jz      short loc_140025797
0x14002576a  test    byte ptr [rax+1Ch], 4
0x14002576e  jz      short loc_140025797
0x140025770  cmp     byte ptr [rax+19h], 2
0x140025774  jb      short loc_140025797
0x140025776  call    cs:__imp_GetLastError
0x14002577c  mov     rcx, cs:WPP_GLOBAL_Control
0x140025783  mov     edx, 4Ah ; 'J'
0x140025788  mov     r9d, eax
0x14002578b  mov     r8, r14
0x14002578e  mov     rcx, [rcx+10h]
0x140025792  call    WPP_SF_d
0x140025797  inc     ebx
0x140025799  cmp     ebx, edi
0x14002579b  jb      short loc_14002574A
0x14002579d  xor     eax, eax
0x14002579f  add     rsp, 28h
0x1400257a3  pop     r14
0x1400257a5  pop     rdi
0x1400257a6  pop     rbp
0x1400257a7  pop     rbx
0x1400257a8  retn
```
