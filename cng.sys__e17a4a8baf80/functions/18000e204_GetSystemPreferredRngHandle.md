# GetSystemPreferredRngHandle

- ea: `0x18000e204`
- end: `0x18000e306`
- name: `GetSystemPreferredRngHandle`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e104`

## callees

- `0x18000b7d8`
- `0x18000b898`
- `0x18000c500`
- `0x18000e204`
- `0x18001155c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18000e25c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000e25c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18000e271`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18000e271`
- `ntoskrnl!KeResetEvent` at `0x18000e23a`
- `ntoskrnl!KeResetEvent` at `0x18000e23a`

## string_xrefs

- `0x18000e2c1`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x18000e2e3`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

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
    v3 = qword_1800D37D8;
    v4 = &qword_1800D37D8;
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
      dword_1800D37D0 = 1;
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
0x18000e204  push    rbx
0x18000e206  push    rsi
0x18000e207  push    rdi
0x18000e208  push    r14
0x18000e20a  sub     rsp, 28h
0x18000e20e  xor     edi, edi
0x18000e210  mov     r14, rcx
0x18000e213  cmp     cs:g_fLoadCNGDone, edi
0x18000e219  mov     [rsp+48h+hAlgorithm], rdi
0x18000e21e  jz      short loc_18000E297
0x18000e220  mov     rax, cs:hAlgorithm
0x18000e227  lea     rsi, hAlgorithm
0x18000e22e  test    rax, rax
0x18000e231  jz      short loc_18000E2A7
0x18000e233  lea     rcx, phEvent; Event
0x18000e23a  call    cs:__imp_KeResetEvent
0x18000e241  nop     dword ptr [rax+rax+00h]
0x18000e246  test    eax, eax
0x18000e248  jz      short loc_18000E25C
0x18000e24a  mov     rcx, rsi
0x18000e24d  call    ReopenSystemPreferredRngHandle
0x18000e252  mov     ebx, eax
0x18000e254  test    eax, eax
0x18000e256  js      loc_18000E2DD
0x18000e25c  call    cs:__imp_KeEnterCriticalRegion
0x18000e263  nop     dword ptr [rax+rax+00h]
0x18000e268  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x18000e26f  mov     dl, 1; Wait
0x18000e271  call    cs:__imp_ExAcquireResourceSharedLite
0x18000e278  nop     dword ptr [rax+rax+00h]
0x18000e27d  mov     rax, [rsi]
0x18000e280  xor     ebx, ebx
0x18000e282  mov     [r14], rax
0x18000e285  test    rdi, rdi
0x18000e288  jnz     short loc_18000E2FA
0x18000e28a  mov     eax, ebx
0x18000e28c  add     rsp, 28h
0x18000e290  pop     r14
0x18000e292  pop     rdi
0x18000e293  pop     rsi
0x18000e294  pop     rbx
0x18000e295  retn
0x18000e297  mov     rax, cs:qword_1800D37D8
0x18000e29e  lea     rsi, qword_1800D37D8
0x18000e2a5  jmp     short loc_18000E22E
0x18000e2a7  lea     rcx, [rsp+48h+hAlgorithm]
0x18000e2ac  call    OpenSystemPreferredAlgorithmProvider
0x18000e2b1  mov     ebx, eax
0x18000e2b3  test    eax, eax
0x18000e2b5  jns     loc_1800A5750
0x18000e2bb  mov     r9d, 1BAh
0x18000e2c1  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e2c8  lea     rdx, aStatus; "Status"
0x18000e2cf  mov     ecx, eax
0x18000e2d1  call    DebugTraceError
0x18000e2d6  mov     rdi, [rsp+48h+hAlgorithm]
0x18000e2db  jmp     short loc_18000E285
0x18000e2dd  mov     r9d, 1E4h
0x18000e2e3  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e2ea  lea     rdx, aStatus; "Status"
0x18000e2f1  mov     ecx, eax
0x18000e2f3  call    DebugTraceError
0x18000e2f8  jmp     short loc_18000E28A
0x18000e2fa  xor     edx, edx; dwFlags
0x18000e2fc  mov     rcx, rdi; hAlgorithm
0x18000e2ff  call    BCryptCloseAlgorithmProvider
0x18000e304  jmp     short loc_18000E28A
0x1800a5750  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x1800a5755  xor     eax, eax
0x1800a5757  lock cmpxchg [rsi], rcx
0x1800a575c  jz      short loc_1800A576B
0x1800a575e  xor     edx, edx; dwFlags
0x1800a5760  call    BCryptCloseAlgorithmProvider
0x1800a5765  nop
0x1800a5766  jmp     loc_18000E25C
0x1800a576b  cmp     cs:g_fLoadCNGDone, edi
0x1800a5771  jz      loc_18000E25C
0x1800a5777  mov     cs:dword_1800D37D0, 1
0x1800a5781  jmp     loc_18000E25C
```
