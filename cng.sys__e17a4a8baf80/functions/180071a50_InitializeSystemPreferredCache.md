# InitializeSystemPreferredCache

- ea: `0x180071a50`
- end: `0x180071b28`
- name: `InitializeSystemPreferredCache`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060308`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x1800719a0`
- `0x180071a50`
- `0x1800756e0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x180071a62`
- `ntoskrnl!KeInitializeEvent` at `0x180071a62`
- `ntoskrnl!ExInitializeResourceLite` at `0x180071a99`
- `ntoskrnl!ExInitializeResourceLite` at `0x180071a99`

## string_xrefs

- `0x180071ab1`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x180071af9`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

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
      dword_1800D37D0 = 1;
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
0x180071a50  push    rbx
0x180071a52  sub     rsp, 20h
0x180071a56  xor     r8d, r8d; State
0x180071a59  lea     rcx, phEvent; Event
0x180071a60  xor     edx, edx; Type
0x180071a62  call    cs:__imp_KeInitializeEvent
0x180071a69  nop     dword ptr [rax+rax+00h]
0x180071a6e  mov     ecx, 68h ; 'h'
0x180071a73  call    MSCryptAlloc
0x180071a78  mov     cs:g_pCachedRngRWLock, rax
0x180071a7f  test    rax, rax
0x180071a82  jnz     short loc_180071A96
0x180071a84  mov     ebx, 0C0000017h
0x180071a89  mov     r9d, 0FAh
0x180071a8f  mov     ecx, 0C0000017h
0x180071a94  jmp     short loc_180071AF9
0x180071a96  mov     rcx, rax; Resource
0x180071a99  call    cs:__imp_ExInitializeResourceLite
0x180071aa0  nop     dword ptr [rax+rax+00h]
0x180071aa5  mov     ebx, eax
0x180071aa7  test    eax, eax
0x180071aa9  jns     short loc_180071ADF
0x180071aab  mov     r9d, 101h
0x180071ab1  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180071ab8  lea     rdx, aStatus; "Status"
0x180071abf  mov     ecx, eax
0x180071ac1  call    DebugTraceError
0x180071ac6  mov     rcx, cs:g_pCachedRngRWLock; P
0x180071acd  call    MSCryptFree
0x180071ad2  mov     cs:g_pCachedRngRWLock, 0
0x180071add  jmp     short loc_180071B0C
0x180071adf  lea     rcx, phEvent; phEvent
0x180071ae6  call    BCryptRegisterConfigChangeNotify
0x180071aeb  mov     ebx, eax
0x180071aed  test    eax, eax
0x180071aef  jns     short loc_180071B13
0x180071af1  mov     r9d, 134h
0x180071af7  mov     ecx, eax
0x180071af9  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180071b00  lea     rdx, aStatus; "Status"
0x180071b07  call    DebugTraceError
0x180071b0c  call    CleanupSystemPreferredCache
0x180071b11  jmp     short loc_180071B1F
0x180071b13  mov     cs:dword_1800D37D0, 1
0x180071b1d  xor     ebx, ebx
0x180071b1f  mov     eax, ebx
0x180071b21  add     rsp, 20h
0x180071b25  pop     rbx
0x180071b26  retn
```
