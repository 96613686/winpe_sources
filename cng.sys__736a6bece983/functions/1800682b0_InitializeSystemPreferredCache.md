# InitializeSystemPreferredCache

- ea: `0x1800682b0`
- end: `0x180068388`
- name: `InitializeSystemPreferredCache`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056a28`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180068200`
- `0x1800682b0`
- `0x18006bf40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1800682c2`
- `ntoskrnl!KeInitializeEvent` at `0x1800682c2`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800682f9`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800682f9`

## string_xrefs

- `0x180068311`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x180068359`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 InitializeSystemPreferredCache()
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // r9
  struct _ERESOURCE *v3; // rax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rcx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax

  KeInitializeEvent((PRKEVENT)&phEvent, NotificationEvent, 0);
  v3 = (struct _ERESOURCE *)MSCryptAlloc(104, v0, v1, v2);
  g_pCachedRngRWLock = v3;
  if ( !v3 )
  {
    v4 = -1073741801;
    v5 = 250;
    v6 = 3221225495LL;
LABEL_7:
    DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c", v5);
    goto LABEL_8;
  }
  v7 = ExInitializeResourceLite(v3);
  v4 = v7;
  if ( v7 >= 0 )
  {
    v8 = BCryptRegisterConfigChangeNotify(&phEvent);
    v4 = v8;
    if ( v8 >= 0 )
    {
      dword_1800CD7D0 = 1;
      return 0;
    }
    v5 = 308;
    v6 = (unsigned int)v8;
    goto LABEL_7;
  }
  DebugTraceError((unsigned int)v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c", 257);
  MSCryptFree(g_pCachedRngRWLock);
  g_pCachedRngRWLock = 0;
LABEL_8:
  CleanupSystemPreferredCache();
  return v4;
}

```

## disassembly

```asm
0x1800682b0  push    rbx
0x1800682b2  sub     rsp, 20h
0x1800682b6  xor     r8d, r8d; State
0x1800682b9  lea     rcx, phEvent; Event
0x1800682c0  xor     edx, edx; Type
0x1800682c2  call    cs:__imp_KeInitializeEvent
0x1800682c9  nop     dword ptr [rax+rax+00h]
0x1800682ce  mov     ecx, 68h ; 'h'
0x1800682d3  call    MSCryptAlloc
0x1800682d8  mov     cs:g_pCachedRngRWLock, rax
0x1800682df  test    rax, rax
0x1800682e2  jnz     short loc_1800682F6
0x1800682e4  mov     ebx, 0C0000017h
0x1800682e9  mov     r9d, 0FAh
0x1800682ef  mov     ecx, 0C0000017h
0x1800682f4  jmp     short loc_180068359
0x1800682f6  mov     rcx, rax; Resource
0x1800682f9  call    cs:__imp_ExInitializeResourceLite
0x180068300  nop     dword ptr [rax+rax+00h]
0x180068305  mov     ebx, eax
0x180068307  test    eax, eax
0x180068309  jns     short loc_18006833F
0x18006830b  mov     r9d, 101h
0x180068311  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068318  lea     rdx, aStatus; "Status"
0x18006831f  mov     ecx, eax
0x180068321  call    DebugTraceError
0x180068326  mov     rcx, cs:g_pCachedRngRWLock; P
0x18006832d  call    MSCryptFree
0x180068332  mov     cs:g_pCachedRngRWLock, 0
0x18006833d  jmp     short loc_18006836C
0x18006833f  lea     rcx, phEvent; phEvent
0x180068346  call    BCryptRegisterConfigChangeNotify
0x18006834b  mov     ebx, eax
0x18006834d  test    eax, eax
0x18006834f  jns     short loc_180068373
0x180068351  mov     r9d, 134h
0x180068357  mov     ecx, eax
0x180068359  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068360  lea     rdx, aStatus; "Status"
0x180068367  call    DebugTraceError
0x18006836c  call    CleanupSystemPreferredCache
0x180068371  jmp     short loc_18006837F
0x180068373  mov     cs:dword_1800CD7D0, 1
0x18006837d  xor     ebx, ebx
0x18006837f  mov     eax, ebx
0x180068381  add     rsp, 20h
0x180068385  pop     rbx
0x180068386  retn
```
