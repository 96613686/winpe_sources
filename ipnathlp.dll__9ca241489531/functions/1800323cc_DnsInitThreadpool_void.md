# DnsInitThreadpool(void)

- ea: `0x1800323cc`
- end: `0x18003251a`
- name: `?DnsInitThreadpool@@YAKXZ`
- size: `334`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024c90`

## callees

- `0x18000c750`
- `0x1800323cc`
- `0x180032520`
- `0x18003bd90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003244c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003248f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003244c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003248f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180032505`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180032505`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18003247a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18003247a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18003243a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18003243a`

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
0x1800323cc  push    rbx
0x1800323ce  sub     rsp, 20h
0x1800323d2  xorps   xmm0, xmm0
0x1800323d5  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x1800323df  xor     ecx, ecx; reserved
0x1800323e1  movdqa  xmmword ptr cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x1800323e9  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x1800323f4  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x1800323ff  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x18003240a  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180032415  mov     dword ptr cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x18003241f  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180032429  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x180032433  mov     cs:?gDnsThreadpoolEnvironInit@@3EA, 1; uchar gDnsThreadpoolEnvironInit
0x18003243a  call    cs:__imp_CreateThreadpool
0x180032440  mov     cs:?gDnsPool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * gDnsPool
0x180032447  test    rax, rax
0x18003244a  jnz     short loc_18003247A
0x18003244c  call    cs:__imp_GetLastError
0x180032452  mov     ebx, eax
0x180032454  mov     rcx, cs:WPP_GLOBAL_Control
0x18003245b  lea     rax, WPP_GLOBAL_Control
0x180032462  cmp     rcx, rax
0x180032465  jz      short loc_1800324CE
0x180032467  test    byte ptr [rcx+1Ch], 10h
0x18003246b  jz      short loc_1800324CE
0x18003246d  cmp     byte ptr [rcx+19h], 2
0x180032471  jb      short loc_1800324CE
0x180032473  mov     edx, 28h ; '('
0x180032478  jmp     short loc_1800324BB
0x18003247a  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180032480  mov     cs:?gDnsCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * gDnsCleanupGroup
0x180032487  mov     rcx, rax
0x18003248a  test    rax, rax
0x18003248d  jnz     short loc_1800324D9
0x18003248f  call    cs:__imp_GetLastError
0x180032495  mov     ebx, eax
0x180032497  mov     rcx, cs:WPP_GLOBAL_Control
0x18003249e  lea     rax, WPP_GLOBAL_Control
0x1800324a5  cmp     rcx, rax
0x1800324a8  jz      short loc_1800324CE
0x1800324aa  test    byte ptr [rcx+1Ch], 10h
0x1800324ae  jz      short loc_1800324CE
0x1800324b0  cmp     byte ptr [rcx+19h], 2
0x1800324b4  jb      short loc_1800324CE
0x1800324b6  mov     edx, 29h ; ')'
0x1800324bb  mov     rcx, [rcx+10h]
0x1800324bf  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x1800324c6  mov     r9d, ebx
0x1800324c9  call    WPP_SF_d
0x1800324ce  test    ebx, ebx
0x1800324d0  jz      short loc_180032512
0x1800324d2  call    ?DnsShutdownThreadpool@@YAXXZ; DnsShutdownThreadpool(void)
0x1800324d7  jmp     short loc_180032512
0x1800324d9  mov     rax, cs:?gDnsPool@@3PEAU_TP_POOL@@EA; _TP_POOL * gDnsPool
0x1800324e0  xor     ebx, ebx
0x1800324e2  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x1800324e9  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rbx; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x1800324f0  mov     cs:?gDnsCallbackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rcx; _TP_CALLBACK_ENVIRON_V3 gDnsCallbackEnviron ...
0x1800324f7  call    ?GetDnsThreadpoolThreadCount@@YAKXZ; GetDnsThreadpoolThreadCount(void)
0x1800324fc  mov     rcx, cs:?gDnsPool@@3PEAU_TP_POOL@@EA; ptpp
0x180032503  mov     edx, eax; cthrdMost
0x180032505  call    cs:__imp_SetThreadpoolThreadMaximum
0x18003250b  mov     cs:?gDnsThreadpoolReady@@3EA, 1; uchar gDnsThreadpoolReady
0x180032512  mov     eax, ebx
0x180032514  add     rsp, 20h
0x180032518  pop     rbx
0x180032519  retn
```
