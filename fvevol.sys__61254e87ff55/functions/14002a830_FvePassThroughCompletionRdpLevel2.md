# FvePassThroughCompletionRdpLevel2

- ea: `0x14002a830`
- end: `0x14002aa32`
- name: `FvePassThroughCompletionRdpLevel2`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140022bf0`
- `0x14002a830`
- `0x14002aa38`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002aa0d`
- `ntoskrnl!EtwWrite` at `0x14002aa0d`
- `ntoskrnl!EtwEventEnabled` at `0x14002a894`
- `ntoskrnl!EtwEventEnabled` at `0x14002a894`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002a8dd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002a8f0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002a8dd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002a8f0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002a99e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002a99e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a97b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a97b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a945`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a945`

## pseudocode

```c
__int64 __fastcall FvePassThroughCompletionRdpLevel2(__int64 a1, __int64 a2, __int64 a3)
{
  ULONGLONG v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rbp
  const EVENT_DESCRIPTOR *v7; // rsi
  REGHANDLE v8; // rcx
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v11; // rcx
  void *v13; // rsi
  KIRQL v14; // r8
  _QWORD *v15; // rdx
  _QWORD *i; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  REGHANDLE v19; // rcx
  __int64 v20; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v22; // [rsp+48h] [rbp-30h]
  int v23; // [rsp+50h] [rbp-28h]

  v4 = a3 & 0xFFFFFFFFFFFFFFFCuLL;
  v5 = a3 & 3;
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  v6 = *(_QWORD *)(v4 + 8);
  v20 = a2;
  v7 = (const EVENT_DESCRIPTOR *)FVE_PERF_WRITE_REQUEST_STOP;
  if ( !v5 )
    v7 = &FVE_PERF_READ_REQUEST_STOP;
  v8 = *(_QWORD *)(v6 + 96);
  if ( v8 && EtwEventEnabled(v8, v7) )
  {
    v19 = *(_QWORD *)(v6 + 96);
    v22 = &v20;
    UserData.Ptr = v4;
    UserData.Size = 8;
    v23 = 8;
    EtwWrite(v19, v7, 0, 2u, &UserData);
  }
  v9 = *(_QWORD *)(v4 + 2352);
  if ( *(_QWORD *)(v9 + 8) )
  {
    v13 = 0;
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 16));
    v15 = (_QWORD *)(*(_QWORD *)(v4 + 2352) + 24LL);
    for ( i = (_QWORD *)*v15; i != v15; i = (_QWORD *)*i )
    {
      if ( i[2] == a2 && *((_DWORD *)i + 6) == 2 )
      {
        v17 = (_QWORD *)*i;
        if ( *(_QWORD **)(*i + 8LL) != i || (v18 = (_QWORD *)i[1], (_QWORD *)*v18 != i) )
          __fastfail(3u);
        *v18 = v17;
        v13 = i;
        v17[1] = v18;
        break;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v4 + 2352) + 16LL), v14);
    if ( v13 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(v4 + 2352) + 8LL), v13);
  }
  if ( *(_DWORD *)(v4 + 2344) == 1 )
    v10 = *(volatile signed __int32 **)(v4 + 2352);
  else
    v10 = (volatile signed __int32 *)(*(_QWORD *)(v4 + 2352) + 296LL * HIDWORD(KeGetPcr()[1].LockArray));
  _InterlockedDecrement(v10);
  v11 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v4 + 1464);
  if ( !*(_BYTE *)(v4 + 1476) )
  {
    ExReleaseRundownProtectionCacheAware(v11);
    v11 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v4 + 1456);
  }
  ExReleaseRundownProtectionCacheAware(v11);
  FvepReleaseRemoveLock(v4 + 56);
  return 0;
}

```

## disassembly

```asm
0x14002a830  mov     [rsp+arg_0], rbx
0x14002a835  push    rbp
0x14002a836  push    rsi
0x14002a837  push    rdi
0x14002a838  sub     rsp, 60h
0x14002a83c  mov     rax, cs:__security_cookie
0x14002a843  xor     rax, rsp
0x14002a846  mov     [rsp+78h+var_20], rax
0x14002a84b  mov     rbx, r8
0x14002a84e  mov     rdi, rdx
0x14002a851  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14002a855  and     r8d, 3
0x14002a859  cmp     byte ptr [rdx+41h], 0
0x14002a85d  jz      short loc_14002A86A
0x14002a85f  mov     rax, [rdx+0B8h]
0x14002a866  or      byte ptr [rax+3], 1
0x14002a86a  mov     rbp, [rbx+8]
0x14002a86e  lea     rax, FVE_PERF_READ_REQUEST_STOP
0x14002a875  test    r8, r8
0x14002a878  mov     [rsp+78h+var_48], rdi
0x14002a87d  lea     rsi, FVE_PERF_WRITE_REQUEST_STOP
0x14002a884  cmovz   rsi, rax
0x14002a888  mov     rcx, [rbp+60h]; RegHandle
0x14002a88c  test    rcx, rcx
0x14002a88f  jz      short loc_14002A8A8
0x14002a891  mov     rdx, rsi; EventDescriptor
0x14002a894  call    cs:__imp_EtwEventEnabled
0x14002a89b  nop     dword ptr [rax+rax+00h]
0x14002a8a0  test    al, al
0x14002a8a2  jnz     loc_14002A9D4
0x14002a8a8  mov     rcx, [rbx+930h]
0x14002a8af  cmp     qword ptr [rcx+8], 0
0x14002a8b4  jnz     loc_14002A93F
0x14002a8ba  cmp     dword ptr [rbx+928h], 1
0x14002a8c1  jnz     short loc_14002A925
0x14002a8c3  mov     rax, [rbx+930h]
0x14002a8ca  lock dec dword ptr [rax]
0x14002a8cd  cmp     byte ptr [rbx+5C4h], 0
0x14002a8d4  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002a8db  jnz     short loc_14002A8F0
0x14002a8dd  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002a8e4  nop     dword ptr [rax+rax+00h]
0x14002a8e9  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x14002a8f0  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002a8f7  nop     dword ptr [rax+rax+00h]
0x14002a8fc  lea     rcx, [rbx+38h]; BugCheckParameter2
0x14002a900  call    FvepReleaseRemoveLock
0x14002a905  xor     eax, eax
0x14002a907  mov     rcx, [rsp+78h+var_20]
0x14002a90c  xor     rcx, rsp; StackCookie
0x14002a90f  call    __security_check_cookie
0x14002a914  mov     rbx, [rsp+78h+arg_0]
0x14002a91c  add     rsp, 60h
0x14002a920  pop     rdi
0x14002a921  pop     rsi
0x14002a922  pop     rbp
0x14002a923  retn
0x14002a925  mov     eax, gs:1A4h
0x14002a92d  mov     ecx, eax
0x14002a92f  imul    rax, rcx, 128h
0x14002a936  add     rax, [rbx+930h]
0x14002a93d  jmp     short loc_14002A8CA
0x14002a93f  add     rcx, 10h; SpinLock
0x14002a943  xor     esi, esi
0x14002a945  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a94c  nop     dword ptr [rax+rax+00h]
0x14002a951  mov     rdx, [rbx+930h]
0x14002a958  movzx   r8d, al
0x14002a95c  add     rdx, 18h
0x14002a960  mov     rcx, [rdx]
0x14002a963  cmp     rcx, rdx
0x14002a966  jnz     loc_14002AA1E
0x14002a96c  mov     rcx, [rbx+930h]
0x14002a973  movzx   edx, r8b; NewIrql
0x14002a977  add     rcx, 10h; SpinLock
0x14002a97b  call    cs:__imp_KeReleaseSpinLock
0x14002a982  nop     dword ptr [rax+rax+00h]
0x14002a987  test    rsi, rsi
0x14002a98a  jz      loc_14002A8BA
0x14002a990  mov     rcx, [rbx+930h]
0x14002a997  mov     rdx, rsi; Entry
0x14002a99a  mov     rcx, [rcx+8]; Lookaside
0x14002a99e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002a9a5  nop     dword ptr [rax+rax+00h]
0x14002a9aa  jmp     loc_14002A8BA
0x14002a9af  mov     rax, [rcx]
0x14002a9b2  cmp     [rax+8], rcx
0x14002a9b6  jnz     short loc_14002A9CD
0x14002a9b8  mov     rdx, [rcx+8]
0x14002a9bc  cmp     [rdx], rcx
0x14002a9bf  jnz     short loc_14002A9CD
0x14002a9c1  mov     [rdx], rax
0x14002a9c4  mov     rsi, rcx
0x14002a9c7  mov     [rax+8], rdx
0x14002a9cb  jmp     short loc_14002A96C
0x14002a9cd  mov     ecx, 3
0x14002a9d2  int     29h; Win8: RtlFailFast(ecx)
0x14002a9d4  mov     rcx, [rbp+60h]; RegHandle
0x14002a9d8  lea     rax, [rsp+78h+var_48]
0x14002a9dd  mov     [rsp+78h+var_30], rax
0x14002a9e2  mov     r9d, 2; UserDataCount
0x14002a9e8  lea     rax, [rsp+78h+var_40]
0x14002a9ed  mov     [rsp+78h+var_40.Ptr], rbx
0x14002a9f2  xor     r8d, r8d; ActivityId
0x14002a9f5  mov     [rsp+78h+UserData], rax; UserData
0x14002a9fa  mov     rdx, rsi; EventDescriptor
0x14002a9fd  mov     [rsp+78h+var_40.Size], 8
0x14002aa05  mov     [rsp+78h+var_28], 8
0x14002aa0d  call    cs:__imp_EtwWrite
0x14002aa14  nop     dword ptr [rax+rax+00h]
0x14002aa19  jmp     loc_14002A8A8
0x14002aa1e  cmp     [rcx+10h], rdi
0x14002aa22  jnz     short loc_14002AA2A
0x14002aa24  cmp     dword ptr [rcx+18h], 2
0x14002aa28  jz      short loc_14002A9AF
0x14002aa2a  mov     rcx, [rcx]
0x14002aa2d  jmp     loc_14002A963
```
