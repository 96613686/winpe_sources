# ReopenSystemPreferredRngHandle

- ea: `0x18000b7d8`
- end: `0x18000b890`
- name: `ReopenSystemPreferredRngHandle`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e204`

## callees

- `0x18000b7d8`
- `0x18000b898`
- `0x18000c500`
- `0x1800123d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b7e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b7e1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b7f6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b7f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b82a`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b82a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b836`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b836`

## string_xrefs

- `0x18000b86a`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 __fastcall ReopenSystemPreferredRngHandle(BCRYPT_ALG_HANDLE *a1)
{
  int v2; // ebx
  int v3; // r8d
  int v5; // edx

  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(g_pCachedRngRWLock, 1u);
  BCryptCloseAlgorithmProvider(*a1, 0);
  *a1 = 0;
  v2 = OpenSystemPreferredAlgorithmProvider(a1);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v5 = *((_DWORD *)WPP_GLOBAL_Control + 11);
      if ( (v5 & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v5,
          v3,
          (unsigned int)"Status",
          v2,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
          127);
    }
  }
  else
  {
    v2 = 0;
  }
  ExReleaseResourceLite(g_pCachedRngRWLock);
  KeLeaveCriticalRegion();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b7d8  push    rbx
0x18000b7da  sub     rsp, 40h
0x18000b7de  mov     rbx, rcx
0x18000b7e1  call    cs:__imp_KeEnterCriticalRegion
0x18000b7e8  nop     dword ptr [rax+rax+00h]
0x18000b7ed  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x18000b7f4  mov     dl, 1; Wait
0x18000b7f6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000b7fd  nop     dword ptr [rax+rax+00h]
0x18000b802  mov     rcx, [rbx]; hAlgorithm
0x18000b805  xor     edx, edx; dwFlags
0x18000b807  call    BCryptCloseAlgorithmProvider
0x18000b80c  mov     rcx, rbx
0x18000b80f  mov     qword ptr [rbx], 0
0x18000b816  call    OpenSystemPreferredAlgorithmProvider
0x18000b81b  mov     ebx, eax
0x18000b81d  test    eax, eax
0x18000b81f  js      short loc_18000B84B
0x18000b821  xor     ebx, ebx
0x18000b823  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x18000b82a  call    cs:__imp_ExReleaseResourceLite
0x18000b831  nop     dword ptr [rax+rax+00h]
0x18000b836  call    cs:__imp_KeLeaveCriticalRegion
0x18000b83d  nop     dword ptr [rax+rax+00h]
0x18000b842  mov     eax, ebx
0x18000b844  add     rsp, 40h
0x18000b848  pop     rbx
0x18000b849  retn
0x18000b84b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b852  lea     rax, WPP_GLOBAL_Control
0x18000b859  cmp     rcx, rax
0x18000b85c  jz      short loc_18000B823
0x18000b85e  mov     edx, [rcx+2Ch]
0x18000b861  test    dl, 1
0x18000b864  jz      short loc_18000B823
0x18000b866  mov     rcx, [rcx+18h]
0x18000b86a  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b871  mov     [rsp+48h+var_18], 7Fh
0x18000b879  lea     r9, aStatus; "Status"
0x18000b880  mov     [rsp+48h+var_20], rax
0x18000b885  mov     [rsp+48h+var_28], ebx
0x18000b889  call    WPP_SF_sDsd
0x18000b88e  jmp     short loc_18000B823
```
