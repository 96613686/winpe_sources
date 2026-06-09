# CDirectMusicVoice::StopVoiceServiceThread(IDirectMusicPort *)

- ea: `0x18001a5c4`
- end: `0x18001a6c6`
- name: `?StopVoiceServiceThread@CDirectMusicVoice@@SAJPEAUIDirectMusicPort@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(struct IDirectMusicPort *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180017390`

## callees

- `0x1800012c4`
- `0x18001a5c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a6a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a6a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a60a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a60a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a5d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a5d8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a691`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6bb`

## pseudocode

```c
__int64 __fastcall CDirectMusicVoice::StopVoiceServiceThread(struct IDirectMusicPort *a1)
{
  __int64 v2; // rax
  struct IDirectMusicPort *v3; // rbx
  unsigned int v4; // edi
  __int64 v6; // rcx
  struct IDirectMusicPort *v7; // r8
  struct IDirectMusicPort *v8; // rcx
  struct IDirectMusicPortVtbl *lpVtbl; // rdx

  EnterCriticalSection(&CDirectMusicVoice::m_csVST);
  v2 = CDirectMusicVoice::m_ClientList;
  v3 = (struct IDirectMusicPort *)CDirectMusicVoice::m_ClientList;
  if ( CDirectMusicVoice::m_ClientList )
  {
    while ( (struct IDirectMusicPort *)v3[1].lpVtbl != a1 )
    {
      v3 = (struct IDirectMusicPort *)v3->lpVtbl;
      if ( !v3 )
        goto LABEL_4;
    }
    v4 = 0;
    if ( v3 == (struct IDirectMusicPort *)CDirectMusicVoice::m_ClientList )
    {
      v6 = *CDirectMusicVoice::m_ClientList;
      *CDirectMusicVoice::m_ClientList = 0;
    }
    else
    {
      v7 = 0;
      v8 = (struct IDirectMusicPort *)CDirectMusicVoice::m_ClientList;
      while ( 1 )
      {
        lpVtbl = v8->lpVtbl;
        if ( v8 == v3 )
          break;
        v7 = v8;
        v8 = (struct IDirectMusicPort *)v8->lpVtbl;
        if ( !lpVtbl )
          goto LABEL_13;
      }
      v7->lpVtbl = lpVtbl;
      v8->lpVtbl = 0;
      v3->lpVtbl = 0;
LABEL_13:
      v6 = v2;
    }
    CDirectMusicVoice::m_ClientList = v6;
    operator delete(v3[3].lpVtbl);
    operator delete(v3[4].lpVtbl);
    operator delete(v3);
    if ( !--CDirectMusicVoice::m_cRefVST )
    {
      CDirectMusicVoice::m_fVSTStopping = 1;
      SetEvent(CDirectMusicVoice::m_hVSTWakeUp);
      WaitForSingleObject(CDirectMusicVoice::m_hVSTThread, 0xFFFFFFFF);
      CloseHandle(CDirectMusicVoice::m_hVSTWakeUp);
      CloseHandle(CDirectMusicVoice::m_hVSTThread);
    }
  }
  else
  {
LABEL_4:
    v4 = -2147024809;
  }
  LeaveCriticalSection(&CDirectMusicVoice::m_csVST);
  return v4;
}

```

## disassembly

```asm
0x18001a5c4  mov     [rsp+arg_0], rbx
0x18001a5c9  push    rdi
0x18001a5ca  sub     rsp, 20h
0x18001a5ce  mov     rdi, rcx
0x18001a5d1  lea     rcx, ?m_csVST@CDirectMusicVoice@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a5d8  call    cs:__imp_EnterCriticalSection
0x18001a5de  mov     rax, cs:?m_ClientList@CDirectMusicVoice@@0VCVSTClientList@@A; CVSTClientList CDirectMusicVoice::m_ClientList
0x18001a5e5  xor     r9d, r9d
0x18001a5e8  mov     rbx, rax
0x18001a5eb  test    rax, rax
0x18001a5ee  jz      short loc_18001A5FE
0x18001a5f0  cmp     [rbx+8], rdi
0x18001a5f4  jz      short loc_18001A61D
0x18001a5f6  mov     rbx, [rbx]
0x18001a5f9  test    rbx, rbx
0x18001a5fc  jnz     short loc_18001A5F0
0x18001a5fe  mov     edi, 80070057h
0x18001a603  lea     rcx, ?m_csVST@CDirectMusicVoice@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a60a  call    cs:__imp_LeaveCriticalSection
0x18001a610  mov     rbx, [rsp+28h+arg_0]
0x18001a615  mov     eax, edi
0x18001a617  add     rsp, 20h
0x18001a61b  pop     rdi
0x18001a61c  retn
0x18001a61d  mov     edi, r9d
0x18001a620  cmp     rbx, rax
0x18001a623  jnz     short loc_18001A62D
0x18001a625  mov     rcx, [rax]
0x18001a628  mov     [rax], r9
0x18001a62b  jmp     short loc_18001A654
0x18001a62d  mov     r8, r9
0x18001a630  mov     rcx, rax
0x18001a633  mov     rdx, [rcx]; unsigned __int64
0x18001a636  cmp     rcx, rbx
0x18001a639  jz      short loc_18001A648
0x18001a63b  mov     r8, rcx
0x18001a63e  mov     rcx, rdx
0x18001a641  test    rdx, rdx
0x18001a644  jnz     short loc_18001A633
0x18001a646  jmp     short loc_18001A651
0x18001a648  mov     [r8], rdx
0x18001a64b  mov     [rcx], r9
0x18001a64e  mov     [rbx], r9
0x18001a651  mov     rcx, rax
0x18001a654  mov     cs:?m_ClientList@CDirectMusicVoice@@0VCVSTClientList@@A, rcx; CVSTClientList CDirectMusicVoice::m_ClientList
0x18001a65b  mov     rcx, [rbx+18h]; void *
0x18001a65f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a664  mov     rcx, [rbx+20h]; void *
0x18001a668  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a66d  mov     edx, 30h ; '0'; unsigned __int64
0x18001a672  mov     rcx, rbx; void *
0x18001a675  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a67a  sub     cs:?m_cRefVST@CDirectMusicVoice@@0JA, 1; long CDirectMusicVoice::m_cRefVST
0x18001a681  jnz     short loc_18001A603
0x18001a683  mov     rcx, cs:?m_hVSTWakeUp@CDirectMusicVoice@@0PEAXEA; hEvent
0x18001a68a  mov     cs:?m_fVSTStopping@CDirectMusicVoice@@0_NA, 1; bool CDirectMusicVoice::m_fVSTStopping
0x18001a691  call    cs:__imp_SetEvent
0x18001a697  mov     rcx, cs:?m_hVSTThread@CDirectMusicVoice@@0PEAXEA; hHandle
0x18001a69e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a6a1  call    cs:__imp_WaitForSingleObject
0x18001a6a7  mov     rcx, cs:?m_hVSTWakeUp@CDirectMusicVoice@@0PEAXEA; hObject
0x18001a6ae  call    cs:__imp_CloseHandle
0x18001a6b4  mov     rcx, cs:?m_hVSTThread@CDirectMusicVoice@@0PEAXEA; hObject
0x18001a6bb  call    cs:__imp_CloseHandle
0x18001a6c1  jmp     loc_18001A603
```
