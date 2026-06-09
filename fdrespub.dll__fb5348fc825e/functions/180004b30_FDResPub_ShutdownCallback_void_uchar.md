# FDResPub_ShutdownCallback(void *,uchar)

- ea: `0x180004b30`
- end: `0x180004ccb`
- name: `?FDResPub_ShutdownCallback@@YAXPEAXE@Z`
- size: `411`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180004f30`

## callees

- `0x180001008`
- `0x180001bf0`
- `0x180004770`
- `0x1800047ac`
- `0x180004b30`
- `0x180006010`

## import_xrefs

- `ntdll!EtwUnregisterTraceGuids` at `0x180004ca3`
- `ntdll!EtwUnregisterTraceGuids` at `0x180004ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bec`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004c86`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004c86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c51`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180004be2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180004be2`

## pseudocode

```c
void __fastcall FDResPub_ShutdownCallback(void *a1)
{
  _QWORD *v1; // rbx
  CResourcePublisher *v2; // rbx
  CResourcePublisher *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  if ( g_pPublisher )
  {
    (*(void (__fastcall **)(CResourcePublisher *))(*(_QWORD *)g_pPublisher + 16LL))(g_pPublisher);
    v2 = g_pPublisher;
    if ( g_pPublisher )
    {
      v3 = g_pPublisher;
      *(_QWORD *)g_pPublisher = &CResourcePublisher::`vftable';
      CResourcePublisher::EndPublishing(v3);
      v4 = *((_QWORD *)v2 + 1);
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      operator delete(v2);
    }
    v1 = WPP_GLOBAL_Control;
    g_pPublisher = 0;
  }
  if ( g_hShutdownWait )
  {
    if ( !UnregisterWaitEx(g_hShutdownWait, 0) )
    {
      GetLastError();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_16;
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids);
    }
    v1 = WPP_GLOBAL_Control;
LABEL_16:
    g_hShutdownWait = 0;
  }
  if ( g_hShutdownEvent )
  {
    CloseHandle(g_hShutdownEvent);
    v1 = WPP_GLOBAL_Control;
    g_hShutdownEvent = 0;
  }
  if ( hServiceStatus )
  {
    ServiceStatus.dwCurrentState = 1;
    SetServiceStatus(hServiceStatus, &ServiceStatus);
    v1 = WPP_GLOBAL_Control;
  }
  if ( v1 != &WPP_GLOBAL_Control )
  {
    while ( v1 )
    {
      v5 = v1[1];
      if ( v5 )
      {
        EtwUnregisterTraceGuids(v5);
        v1[1] = 0;
      }
      v1 = (_QWORD *)*v1;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x180004b30  mov     [rsp+arg_0], rbx
0x180004b35  push    rsi
0x180004b36  sub     rsp, 30h
0x180004b3a  mov     rbx, cs:WPP_GLOBAL_Control
0x180004b41  lea     rsi, WPP_GLOBAL_Control
0x180004b48  cmp     rbx, rsi
0x180004b4b  jz      short loc_180004B6F
0x180004b4d  cmp     byte ptr [rbx+19h], 4
0x180004b51  jb      short loc_180004B6F
0x180004b53  mov     rcx, [rbx+10h]
0x180004b57  lea     r8, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids
0x180004b5e  mov     edx, 14h
0x180004b63  call    WPP_SF_s
0x180004b68  mov     rbx, cs:WPP_GLOBAL_Control
0x180004b6f  mov     rcx, cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA; CResourcePublisher * g_pPublisher
0x180004b76  test    rcx, rcx
0x180004b79  jz      short loc_180004BD4
0x180004b7b  mov     rax, [rcx]
0x180004b7e  mov     rax, [rax+10h]
0x180004b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b87  mov     rbx, cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA; CResourcePublisher * g_pPublisher
0x180004b8e  test    rbx, rbx
0x180004b91  jz      short loc_180004BC2
0x180004b93  lea     rax, ??_7CResourcePublisher@@6B@; const CResourcePublisher::`vftable'
0x180004b9a  mov     rcx, rbx; this
0x180004b9d  mov     [rbx], rax
0x180004ba0  call    ?EndPublishing@CResourcePublisher@@UEAAJXZ; CResourcePublisher::EndPublishing(void)
0x180004ba5  mov     rcx, [rbx+8]
0x180004ba9  test    rcx, rcx
0x180004bac  jz      short loc_180004BBA
0x180004bae  mov     rax, [rcx]
0x180004bb1  mov     rax, [rax+10h]
0x180004bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bba  mov     rcx, rbx; Block
0x180004bbd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004bc2  mov     rbx, cs:WPP_GLOBAL_Control
0x180004bc9  mov     cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA, 0; CResourcePublisher * g_pPublisher
0x180004bd4  mov     rcx, cs:?g_hShutdownWait@@3PEAXEA; WaitHandle
0x180004bdb  test    rcx, rcx
0x180004bde  jz      short loc_180004C45
0x180004be0  xor     edx, edx; CompletionEvent
0x180004be2  call    cs:__imp_UnregisterWaitEx
0x180004be8  test    eax, eax
0x180004bea  jnz     short loc_180004C33
0x180004bec  call    cs:__imp_GetLastError
0x180004bf2  test    eax, eax
0x180004bf4  jle     short loc_180004BFE
0x180004bf6  movzx   eax, ax
0x180004bf9  or      eax, 80070000h
0x180004bfe  mov     rbx, cs:WPP_GLOBAL_Control
0x180004c05  xor     ecx, ecx
0x180004c07  cmp     eax, 800703E5h
0x180004c0c  cmovnz  ecx, eax
0x180004c0f  cmp     rbx, rsi
0x180004c12  jz      short loc_180004C3A
0x180004c14  cmp     byte ptr [rbx+19h], 4
0x180004c18  jb      short loc_180004C3A
0x180004c1a  mov     [rsp+38h+var_18], ecx
0x180004c1e  lea     r8, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids
0x180004c25  mov     rcx, [rbx+10h]
0x180004c29  mov     edx, 15h
0x180004c2e  call    WPP_SF_sD
0x180004c33  mov     rbx, cs:WPP_GLOBAL_Control
0x180004c3a  mov     cs:?g_hShutdownWait@@3PEAXEA, 0; void * g_hShutdownWait
0x180004c45  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hObject
0x180004c4c  test    rcx, rcx
0x180004c4f  jz      short loc_180004C69
0x180004c51  call    cs:__imp_CloseHandle
0x180004c57  mov     rbx, cs:WPP_GLOBAL_Control
0x180004c5e  mov     cs:?g_hShutdownEvent@@3PEAXEA, 0; void * g_hShutdownEvent
0x180004c69  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180004c70  test    rcx, rcx
0x180004c73  jz      short loc_180004C93
0x180004c75  lea     rdx, ServiceStatus; lpServiceStatus
0x180004c7c  mov     cs:ServiceStatus.dwCurrentState, 1
0x180004c86  call    cs:__imp_SetServiceStatus
0x180004c8c  mov     rbx, cs:WPP_GLOBAL_Control
0x180004c93  cmp     rbx, rsi
0x180004c96  jz      short loc_180004CC0
0x180004c98  jmp     short loc_180004CB4
0x180004c9a  mov     rcx, [rbx+8]
0x180004c9e  test    rcx, rcx
0x180004ca1  jz      short loc_180004CB1
0x180004ca3  call    cs:__imp_EtwUnregisterTraceGuids
0x180004ca9  mov     qword ptr [rbx+8], 0
0x180004cb1  mov     rbx, [rbx]
0x180004cb4  test    rbx, rbx
0x180004cb7  jnz     short loc_180004C9A
0x180004cb9  mov     cs:WPP_GLOBAL_Control, rsi
0x180004cc0  mov     rbx, [rsp+38h+arg_0]
0x180004cc5  add     rsp, 30h
0x180004cc9  pop     rsi
0x180004cca  retn
```
