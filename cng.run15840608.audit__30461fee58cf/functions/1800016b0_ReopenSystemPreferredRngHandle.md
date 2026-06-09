# ReopenSystemPreferredRngHandle

- ea: `0x1800016b0`
- end: `0x180001768`
- name: `ReopenSystemPreferredRngHandle`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800040e4`

## callees

- `0x1800016b0`
- `0x180001770`
- `0x1800023e0`
- `0x1800082b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800016b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800016b9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800016ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800016ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001702`
- `ntoskrnl!ExReleaseResourceLite` at `0x180001702`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000170e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000170e`

## string_xrefs

- `0x180001742`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

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
0x1800016b0  push    rbx
0x1800016b2  sub     rsp, 40h
0x1800016b6  mov     rbx, rcx
0x1800016b9  call    cs:__imp_KeEnterCriticalRegion
0x1800016c0  nop     dword ptr [rax+rax+00h]
0x1800016c5  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x1800016cc  mov     dl, 1; Wait
0x1800016ce  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800016d5  nop     dword ptr [rax+rax+00h]
0x1800016da  mov     rcx, [rbx]; hAlgorithm
0x1800016dd  xor     edx, edx; dwFlags
0x1800016df  call    BCryptCloseAlgorithmProvider
0x1800016e4  mov     rcx, rbx
0x1800016e7  mov     qword ptr [rbx], 0
0x1800016ee  call    OpenSystemPreferredAlgorithmProvider
0x1800016f3  mov     ebx, eax
0x1800016f5  test    eax, eax
0x1800016f7  js      short loc_180001723
0x1800016f9  xor     ebx, ebx
0x1800016fb  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x180001702  call    cs:__imp_ExReleaseResourceLite
0x180001709  nop     dword ptr [rax+rax+00h]
0x18000170e  call    cs:__imp_KeLeaveCriticalRegion
0x180001715  nop     dword ptr [rax+rax+00h]
0x18000171a  mov     eax, ebx
0x18000171c  add     rsp, 40h
0x180001720  pop     rbx
0x180001721  retn
0x180001723  mov     rcx, cs:WPP_GLOBAL_Control
0x18000172a  lea     rax, WPP_GLOBAL_Control
0x180001731  cmp     rcx, rax
0x180001734  jz      short loc_1800016FB
0x180001736  mov     edx, [rcx+2Ch]
0x180001739  test    dl, 1
0x18000173c  jz      short loc_1800016FB
0x18000173e  mov     rcx, [rcx+18h]
0x180001742  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001749  mov     [rsp+48h+var_18], 7Fh
0x180001751  lea     r9, aStatus; "Status"
0x180001758  mov     [rsp+48h+var_20], rax
0x18000175d  mov     [rsp+48h+var_28], ebx
0x180001761  call    WPP_SF_sDsd
0x180001766  jmp     short loc_1800016FB
```
