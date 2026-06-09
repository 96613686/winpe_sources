# InitializeSystemPreferredCache

- ea: `0x1800678b0`
- end: `0x180067988`
- name: `InitializeSystemPreferredCache`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056138`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180067800`
- `0x1800678b0`
- `0x18006b540`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1800678c2`
- `ntoskrnl!KeInitializeEvent` at `0x1800678c2`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800678f9`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800678f9`

## string_xrefs

- `0x180067911`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x180067959`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 InitializeSystemPreferredCache()
{
  __int64 v0; // rdx
  struct _ERESOURCE *v1; // rax
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // rcx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax

  KeInitializeEvent((PRKEVENT)&phEvent, NotificationEvent, 0);
  v1 = (struct _ERESOURCE *)MSCryptAlloc(104, v0);
  g_pCachedRngRWLock = v1;
  if ( !v1 )
  {
    v2 = -1073741801;
    v3 = 250;
    v4 = 3221225495LL;
LABEL_7:
    DebugTraceError(v4, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c", v3);
    goto LABEL_8;
  }
  v5 = ExInitializeResourceLite(v1);
  v2 = v5;
  if ( v5 >= 0 )
  {
    v6 = BCryptRegisterConfigChangeNotify(&phEvent);
    v2 = v6;
    if ( v6 >= 0 )
    {
      dword_1800CB790 = 1;
      return 0;
    }
    v3 = 308;
    v4 = (unsigned int)v6;
    goto LABEL_7;
  }
  DebugTraceError((unsigned int)v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c", 257);
  MSCryptFree(g_pCachedRngRWLock);
  g_pCachedRngRWLock = 0;
LABEL_8:
  CleanupSystemPreferredCache();
  return v2;
}

```

## disassembly

```asm
0x1800678b0  push    rbx
0x1800678b2  sub     rsp, 20h
0x1800678b6  xor     r8d, r8d; State
0x1800678b9  lea     rcx, phEvent; Event
0x1800678c0  xor     edx, edx; Type
0x1800678c2  call    cs:__imp_KeInitializeEvent
0x1800678c9  nop     dword ptr [rax+rax+00h]
0x1800678ce  mov     ecx, 68h ; 'h'
0x1800678d3  call    MSCryptAlloc
0x1800678d8  mov     cs:g_pCachedRngRWLock, rax
0x1800678df  test    rax, rax
0x1800678e2  jnz     short loc_1800678F6
0x1800678e4  mov     ebx, 0C0000017h
0x1800678e9  mov     r9d, 0FAh
0x1800678ef  mov     ecx, 0C0000017h
0x1800678f4  jmp     short loc_180067959
0x1800678f6  mov     rcx, rax; Resource
0x1800678f9  call    cs:__imp_ExInitializeResourceLite
0x180067900  nop     dword ptr [rax+rax+00h]
0x180067905  mov     ebx, eax
0x180067907  test    eax, eax
0x180067909  jns     short loc_18006793F
0x18006790b  mov     r9d, 101h
0x180067911  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067918  lea     rdx, aStatus; "Status"
0x18006791f  mov     ecx, eax
0x180067921  call    DebugTraceError
0x180067926  mov     rcx, cs:g_pCachedRngRWLock; P
0x18006792d  call    MSCryptFree
0x180067932  mov     cs:g_pCachedRngRWLock, 0
0x18006793d  jmp     short loc_18006796C
0x18006793f  lea     rcx, phEvent; phEvent
0x180067946  call    BCryptRegisterConfigChangeNotify
0x18006794b  mov     ebx, eax
0x18006794d  test    eax, eax
0x18006794f  jns     short loc_180067973
0x180067951  mov     r9d, 134h
0x180067957  mov     ecx, eax
0x180067959  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067960  lea     rdx, aStatus; "Status"
0x180067967  call    DebugTraceError
0x18006796c  call    CleanupSystemPreferredCache
0x180067971  jmp     short loc_18006797F
0x180067973  mov     cs:dword_1800CB790, 1
0x18006797d  xor     ebx, ebx
0x18006797f  mov     eax, ebx
0x180067981  add     rsp, 20h
0x180067985  pop     rbx
0x180067986  retn
```
