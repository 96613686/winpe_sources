# FDResPub_MainHosted(void)

- ea: `0x180004a30`
- end: `0x180004b1f`
- name: `?FDResPub_MainHosted@@YAJXZ`
- size: `239`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180001bf0`
- `0x180004770`
- `0x1800047f8`
- `0x180004a30`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004a74`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004a74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004ab9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004ab9`

## pseudocode

```c
__int64 FDResPub_MainHosted(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  CResourcePublisher *v2; // rdi
  CResourcePublisher *v3; // rcx
  __int64 v4; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids);
  g_hShutdownEvent = CreateEventW(0, 1, 0, 0);
  if ( g_hShutdownEvent )
    goto LABEL_8;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( !v1 )
  {
LABEL_8:
    v1 = FDResPub_InitializeHost();
    if ( !v1 && g_hShutdownEvent )
      WaitForSingleObject(g_hShutdownEvent, 0xFFFFFFFF);
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
  }
  return v1;
}

```

## disassembly

```asm
0x180004a30  mov     [rsp+arg_0], rbx
0x180004a35  push    rdi
0x180004a36  sub     rsp, 20h
0x180004a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a41  lea     rax, WPP_GLOBAL_Control
0x180004a48  cmp     rcx, rax
0x180004a4b  jz      short loc_180004A68
0x180004a4d  cmp     byte ptr [rcx+19h], 4
0x180004a51  jb      short loc_180004A68
0x180004a53  mov     rcx, [rcx+10h]
0x180004a57  lea     r8, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids
0x180004a5e  mov     edx, 10h
0x180004a63  call    WPP_SF_s
0x180004a68  xor     r9d, r9d; lpName
0x180004a6b  xor     r8d, r8d; bInitialState
0x180004a6e  xor     ecx, ecx; lpEventAttributes
0x180004a70  lea     edx, [r9+1]; bManualReset
0x180004a74  call    cs:__imp_CreateEventW
0x180004a7a  mov     cs:?g_hShutdownEvent@@3PEAXEA, rax; void * g_hShutdownEvent
0x180004a81  test    rax, rax
0x180004a84  jnz     short loc_180004A9F
0x180004a86  call    cs:__imp_GetLastError
0x180004a8c  mov     ebx, eax
0x180004a8e  test    eax, eax
0x180004a90  jle     short loc_180004A9B
0x180004a92  movzx   ebx, ax
0x180004a95  or      ebx, 80070000h
0x180004a9b  test    ebx, ebx
0x180004a9d  jnz     short loc_180004ABF
0x180004a9f  call    ?FDResPub_InitializeHost@@YAJXZ; FDResPub_InitializeHost(void)
0x180004aa4  mov     ebx, eax
0x180004aa6  test    eax, eax
0x180004aa8  jnz     short loc_180004ABF
0x180004aaa  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hHandle
0x180004ab1  test    rcx, rcx
0x180004ab4  jz      short loc_180004ABF
0x180004ab6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004ab9  call    cs:__imp_WaitForSingleObject
0x180004abf  mov     rcx, cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA; CResourcePublisher * g_pPublisher
0x180004ac6  test    rcx, rcx
0x180004ac9  jz      short loc_180004B12
0x180004acb  mov     rax, [rcx]
0x180004ace  mov     rax, [rax+10h]
0x180004ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad7  mov     rdi, cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA; CResourcePublisher * g_pPublisher
0x180004ade  test    rdi, rdi
0x180004ae1  jz      short loc_180004B12
0x180004ae3  lea     rax, ??_7CResourcePublisher@@6B@; const CResourcePublisher::`vftable'
0x180004aea  mov     rcx, rdi; this
0x180004aed  mov     [rdi], rax
0x180004af0  call    ?EndPublishing@CResourcePublisher@@UEAAJXZ; CResourcePublisher::EndPublishing(void)
0x180004af5  mov     rcx, [rdi+8]
0x180004af9  test    rcx, rcx
0x180004afc  jz      short loc_180004B0A
0x180004afe  mov     rax, [rcx]
0x180004b01  mov     rax, [rax+10h]
0x180004b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b0a  mov     rcx, rdi; Block
0x180004b0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004b12  mov     eax, ebx
0x180004b14  mov     rbx, [rsp+28h+arg_0]
0x180004b19  add     rsp, 20h
0x180004b1d  pop     rdi
0x180004b1e  retn
```
