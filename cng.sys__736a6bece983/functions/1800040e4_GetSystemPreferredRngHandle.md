# GetSystemPreferredRngHandle

- ea: `0x1800040e4`
- end: `0x1800041e6`
- name: `GetSystemPreferredRngHandle`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003fe4`

## callees

- `0x1800016b0`
- `0x180001770`
- `0x1800023e0`
- `0x1800040e4`
- `0x18000743c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18000413c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000413c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180004151`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180004151`
- `ntoskrnl!KeResetEvent` at `0x18000411a`
- `ntoskrnl!KeResetEvent` at `0x18000411a`

## string_xrefs

- `0x1800041a1`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x1800041c3`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 __fastcall GetSystemPreferredRngHandle(BCRYPT_ALG_HANDLE *a1)
{
  BCRYPT_ALG_HANDLE v1; // rdi
  BCRYPT_ALG_HANDLE v3; // rax
  BCRYPT_ALG_HANDLE *v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  BCRYPT_ALG_HANDLE v9; // rcx
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  hAlgorithm = 0;
  if ( g_fLoadCNGDone )
  {
    v3 = ::hAlgorithm;
    v4 = &::hAlgorithm;
  }
  else
  {
    v3 = qword_1800CD7D8;
    v4 = &qword_1800CD7D8;
  }
  if ( v3 )
  {
    if ( KeResetEvent((PRKEVENT)&phEvent) )
    {
      v5 = ReopenSystemPreferredRngHandle(v4);
      v6 = v5;
      if ( v5 < 0 )
      {
        DebugTraceError((unsigned int)v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c", 484);
        return v6;
      }
    }
    goto LABEL_6;
  }
  v8 = OpenSystemPreferredAlgorithmProvider(&hAlgorithm);
  v6 = v8;
  if ( v8 >= 0 )
  {
    v9 = hAlgorithm;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)v4, (signed __int64)hAlgorithm, 0) )
    {
      BCryptCloseAlgorithmProvider(v9, 0);
    }
    else if ( g_fLoadCNGDone )
    {
      dword_1800CD7D0 = 1;
    }
LABEL_6:
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(g_pCachedRngRWLock, 1u);
    v6 = 0;
    *a1 = *v4;
    goto LABEL_7;
  }
  DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c", 442);
  v1 = hAlgorithm;
LABEL_7:
  if ( v1 )
    BCryptCloseAlgorithmProvider(v1, 0);
  return v6;
}

```

## disassembly

```asm
0x1800040e4  push    rbx
0x1800040e6  push    rsi
0x1800040e7  push    rdi
0x1800040e8  push    r14
0x1800040ea  sub     rsp, 28h
0x1800040ee  xor     edi, edi
0x1800040f0  mov     r14, rcx
0x1800040f3  cmp     cs:g_fLoadCNGDone, edi
0x1800040f9  mov     [rsp+48h+hAlgorithm], rdi
0x1800040fe  jz      short loc_180004177
0x180004100  mov     rax, cs:hAlgorithm
0x180004107  lea     rsi, hAlgorithm
0x18000410e  test    rax, rax
0x180004111  jz      short loc_180004187
0x180004113  lea     rcx, phEvent; Event
0x18000411a  call    cs:__imp_KeResetEvent
0x180004121  nop     dword ptr [rax+rax+00h]
0x180004126  test    eax, eax
0x180004128  jz      short loc_18000413C
0x18000412a  mov     rcx, rsi
0x18000412d  call    ReopenSystemPreferredRngHandle
0x180004132  mov     ebx, eax
0x180004134  test    eax, eax
0x180004136  js      loc_1800041BD
0x18000413c  call    cs:__imp_KeEnterCriticalRegion
0x180004143  nop     dword ptr [rax+rax+00h]
0x180004148  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x18000414f  mov     dl, 1; Wait
0x180004151  call    cs:__imp_ExAcquireResourceSharedLite
0x180004158  nop     dword ptr [rax+rax+00h]
0x18000415d  mov     rax, [rsi]
0x180004160  xor     ebx, ebx
0x180004162  mov     [r14], rax
0x180004165  test    rdi, rdi
0x180004168  jnz     short loc_1800041DA
0x18000416a  mov     eax, ebx
0x18000416c  add     rsp, 28h
0x180004170  pop     r14
0x180004172  pop     rdi
0x180004173  pop     rsi
0x180004174  pop     rbx
0x180004175  retn
0x180004177  mov     rax, cs:qword_1800CD7D8
0x18000417e  lea     rsi, qword_1800CD7D8
0x180004185  jmp     short loc_18000410E
0x180004187  lea     rcx, [rsp+48h+hAlgorithm]
0x18000418c  call    OpenSystemPreferredAlgorithmProvider
0x180004191  mov     ebx, eax
0x180004193  test    eax, eax
0x180004195  jns     loc_1800A07E2
0x18000419b  mov     r9d, 1BAh
0x1800041a1  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800041a8  lea     rdx, aStatus; "Status"
0x1800041af  mov     ecx, eax
0x1800041b1  call    DebugTraceError
0x1800041b6  mov     rdi, [rsp+48h+hAlgorithm]
0x1800041bb  jmp     short loc_180004165
0x1800041bd  mov     r9d, 1E4h
0x1800041c3  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800041ca  lea     rdx, aStatus; "Status"
0x1800041d1  mov     ecx, eax
0x1800041d3  call    DebugTraceError
0x1800041d8  jmp     short loc_18000416A
0x1800041da  xor     edx, edx; dwFlags
0x1800041dc  mov     rcx, rdi; hAlgorithm
0x1800041df  call    BCryptCloseAlgorithmProvider
0x1800041e4  jmp     short loc_18000416A
0x1800a07e2  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x1800a07e7  xor     eax, eax
0x1800a07e9  lock cmpxchg [rsi], rcx
0x1800a07ee  jz      short loc_1800A07FD
0x1800a07f0  xor     edx, edx; dwFlags
0x1800a07f2  call    BCryptCloseAlgorithmProvider
0x1800a07f7  nop
0x1800a07f8  jmp     loc_18000413C
0x1800a07fd  cmp     cs:g_fLoadCNGDone, edi
0x1800a0803  jz      loc_18000413C
0x1800a0809  mov     cs:dword_1800CD7D0, 1
0x1800a0813  jmp     loc_18000413C
```
