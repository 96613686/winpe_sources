# DnsInitThreadpool(void)

- ea: `0x180034b54`
- end: `0x180034cc1`
- name: `?DnsInitThreadpool@@YAKXZ`
- size: `365`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800271d0`

## callees

- `0x18000d090`
- `0x180034b54`
- `0x180034cc8`
- `0x18003edc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180034ca5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180034ca5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180034c0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180034c0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180034bc2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180034bc2`

## pseudocode

```c
__int64 DnsInitThreadpool(void)
{
  DWORD LastError; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  DWORD DnsThreadpoolThreadCount; // eax

  gDnsCallbackEnviron.Version = 3;
  *(_OWORD *)&gDnsCallbackEnviron.RaceDll = 0;
  gDnsCallbackEnviron.Pool = 0;
  gDnsCallbackEnviron.CleanupGroup = 0;
  gDnsCallbackEnviron.CleanupGroupCancelCallback = 0;
  gDnsCallbackEnviron.FinalizationCallback = 0;
  gDnsCallbackEnviron.u.Flags = 0;
  gDnsCallbackEnviron.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  gDnsCallbackEnviron.Size = 72;
  gDnsThreadpoolEnvironInit = 1;
  gDnsPool = CreateThreadpool(0);
  if ( gDnsPool )
  {
    gDnsCleanupGroup = CreateThreadpoolCleanupGroup();
    if ( gDnsCleanupGroup )
    {
      LastError = 0;
      gDnsCallbackEnviron.Pool = gDnsPool;
      gDnsCallbackEnviron.CleanupGroupCancelCallback = 0;
      gDnsCallbackEnviron.CleanupGroup = gDnsCleanupGroup;
      DnsThreadpoolThreadCount = GetDnsThreadpoolThreadCount();
      SetThreadpoolThreadMaximum(gDnsPool, DnsThreadpoolThreadCount);
      gDnsThreadpoolReady = 1;
      return LastError;
    }
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = 41;
      goto LABEL_11;
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = 40;
LABEL_11:
      WPP_SF_d(v1[2], v2, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, LastError);
    }
  }
  if ( LastError )
    DnsShutdownThreadpool();
  return LastError;
}

```

## disassembly

```asm
0x180034b54  push    rbx
0x180034b56  sub     rsp, 20h
0x180034b5a  xorps   xmm0, xmm0
0x180034b5d  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034b67  xor     ecx, ecx; reserved
0x180034b69  movdqa  xmmword ptr cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034b71  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034b7c  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034b87  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034b92  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034b9d  mov     dword ptr cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034ba7  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034bb1  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034bbb  mov     cs:?gDnsThreadpoolEnvironInit@@3EA, 1; uchar gDnsThreadpoolEnvironInit
0x180034bc2  call    cs:__imp_CreateThreadpool
0x180034bc9  nop     dword ptr [rax+rax+00h]
0x180034bce  mov     cs:?gDnsPool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * gDnsPool
0x180034bd5  test    rax, rax
0x180034bd8  jnz     short loc_180034C0E
0x180034bda  call    cs:__imp_GetLastError
0x180034be1  nop     dword ptr [rax+rax+00h]
0x180034be6  mov     ebx, eax
0x180034be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180034bef  lea     rax, WPP_GLOBAL_Control
0x180034bf6  cmp     rcx, rax
0x180034bf9  jz      short loc_180034C6E
0x180034bfb  test    byte ptr [rcx+1Ch], 10h
0x180034bff  jz      short loc_180034C6E
0x180034c01  cmp     byte ptr [rcx+19h], 2
0x180034c05  jb      short loc_180034C6E
0x180034c07  mov     edx, 28h ; '('
0x180034c0c  jmp     short loc_180034C5B
0x180034c0e  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180034c15  nop     dword ptr [rax+rax+00h]
0x180034c1a  mov     cs:?gDnsCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * gDnsCleanupGroup
0x180034c21  mov     rcx, rax
0x180034c24  test    rax, rax
0x180034c27  jnz     short loc_180034C79
0x180034c29  call    cs:__imp_GetLastError
0x180034c30  nop     dword ptr [rax+rax+00h]
0x180034c35  mov     ebx, eax
0x180034c37  mov     rcx, cs:WPP_GLOBAL_Control
0x180034c3e  lea     rax, WPP_GLOBAL_Control
0x180034c45  cmp     rcx, rax
0x180034c48  jz      short loc_180034C6E
0x180034c4a  test    byte ptr [rcx+1Ch], 10h
0x180034c4e  jz      short loc_180034C6E
0x180034c50  cmp     byte ptr [rcx+19h], 2
0x180034c54  jb      short loc_180034C6E
0x180034c56  mov     edx, 29h ; ')'
0x180034c5b  mov     rcx, [rcx+10h]
0x180034c5f  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180034c66  mov     r9d, ebx
0x180034c69  call    WPP_SF_d
0x180034c6e  test    ebx, ebx
0x180034c70  jz      short loc_180034CB8
0x180034c72  call    ?DnsShutdownThreadpool@@YAXXZ; DnsShutdownThreadpool(void)
0x180034c77  jmp     short loc_180034CB8
0x180034c79  mov     rax, cs:?gDnsPool@@3PEAU_TP_POOL@@EA; _TP_POOL * gDnsPool
0x180034c80  xor     ebx, ebx
0x180034c82  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034c89  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rbx; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034c90  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rcx; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180034c97  call    ?GetDnsThreadpoolThreadCount@@YAKXZ; GetDnsThreadpoolThreadCount(void)
0x180034c9c  mov     rcx, cs:?gDnsPool@@3PEAU_TP_POOL@@EA; ptpp
0x180034ca3  mov     edx, eax; cthrdMost
0x180034ca5  call    cs:__imp_SetThreadpoolThreadMaximum
0x180034cac  nop     dword ptr [rax+rax+00h]
0x180034cb1  mov     cs:?gDnsThreadpoolReady@@3EA, 1; uchar gDnsThreadpoolReady
0x180034cb8  mov     eax, ebx
0x180034cba  add     rsp, 20h
0x180034cbe  pop     rbx
0x180034cbf  retn
```
