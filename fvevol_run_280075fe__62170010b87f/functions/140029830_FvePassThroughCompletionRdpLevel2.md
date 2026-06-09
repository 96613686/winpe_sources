# FvePassThroughCompletionRdpLevel2

- ea: `0x140029830`
- end: `0x140029a32`
- name: `FvePassThroughCompletionRdpLevel2`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400218c0`
- `0x140029830`
- `0x140029a38`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140029a0d`
- `ntoskrnl!EtwWrite` at `0x140029a0d`
- `ntoskrnl!EtwEventEnabled` at `0x140029894`
- `ntoskrnl!EtwEventEnabled` at `0x140029894`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400298dd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400298f0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400298dd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400298f0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002999e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002999e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002997b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002997b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029945`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029945`

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
  v9 = *(_QWORD *)(v4 + 2336);
  if ( *(_QWORD *)(v9 + 8) )
  {
    v13 = 0;
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 16));
    v15 = (_QWORD *)(*(_QWORD *)(v4 + 2336) + 24LL);
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
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v4 + 2336) + 16LL), v14);
    if ( v13 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(v4 + 2336) + 8LL), v13);
  }
  if ( *(_DWORD *)(v4 + 2328) == 1 )
    v10 = *(volatile signed __int32 **)(v4 + 2336);
  else
    v10 = (volatile signed __int32 *)(*(_QWORD *)(v4 + 2336) + 296LL * HIDWORD(KeGetPcr()[1].LockArray));
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
0x140029830  mov     [rsp+arg_0], rbx
0x140029835  push    rbp
0x140029836  push    rsi
0x140029837  push    rdi
0x140029838  sub     rsp, 60h
0x14002983c  mov     rax, cs:__security_cookie
0x140029843  xor     rax, rsp
0x140029846  mov     [rsp+78h+var_20], rax
0x14002984b  mov     rbx, r8
0x14002984e  mov     rdi, rdx
0x140029851  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140029855  and     r8d, 3
0x140029859  cmp     byte ptr [rdx+41h], 0
0x14002985d  jz      short loc_14002986A
0x14002985f  mov     rax, [rdx+0B8h]
0x140029866  or      byte ptr [rax+3], 1
0x14002986a  mov     rbp, [rbx+8]
0x14002986e  lea     rax, FVE_PERF_READ_REQUEST_STOP
0x140029875  test    r8, r8
0x140029878  mov     [rsp+78h+var_48], rdi
0x14002987d  lea     rsi, FVE_PERF_WRITE_REQUEST_STOP
0x140029884  cmovz   rsi, rax
0x140029888  mov     rcx, [rbp+60h]; RegHandle
0x14002988c  test    rcx, rcx
0x14002988f  jz      short loc_1400298A8
0x140029891  mov     rdx, rsi; EventDescriptor
0x140029894  call    cs:__imp_EtwEventEnabled
0x14002989b  nop     dword ptr [rax+rax+00h]
0x1400298a0  test    al, al
0x1400298a2  jnz     loc_1400299D4
0x1400298a8  mov     rcx, [rbx+920h]
0x1400298af  cmp     qword ptr [rcx+8], 0
0x1400298b4  jnz     loc_14002993F
0x1400298ba  cmp     dword ptr [rbx+918h], 1
0x1400298c1  jnz     short loc_140029925
0x1400298c3  mov     rax, [rbx+920h]
0x1400298ca  lock dec dword ptr [rax]
0x1400298cd  cmp     byte ptr [rbx+5C4h], 0
0x1400298d4  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x1400298db  jnz     short loc_1400298F0
0x1400298dd  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400298e4  nop     dword ptr [rax+rax+00h]
0x1400298e9  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x1400298f0  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400298f7  nop     dword ptr [rax+rax+00h]
0x1400298fc  lea     rcx, [rbx+38h]; BugCheckParameter2
0x140029900  call    FvepReleaseRemoveLock
0x140029905  xor     eax, eax
0x140029907  mov     rcx, [rsp+78h+var_20]
0x14002990c  xor     rcx, rsp; StackCookie
0x14002990f  call    __security_check_cookie
0x140029914  mov     rbx, [rsp+78h+arg_0]
0x14002991c  add     rsp, 60h
0x140029920  pop     rdi
0x140029921  pop     rsi
0x140029922  pop     rbp
0x140029923  retn
0x140029925  mov     eax, gs:1A4h
0x14002992d  mov     ecx, eax
0x14002992f  imul    rax, rcx, 128h
0x140029936  add     rax, [rbx+920h]
0x14002993d  jmp     short loc_1400298CA
0x14002993f  add     rcx, 10h; SpinLock
0x140029943  xor     esi, esi
0x140029945  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002994c  nop     dword ptr [rax+rax+00h]
0x140029951  mov     rdx, [rbx+920h]
0x140029958  movzx   r8d, al
0x14002995c  add     rdx, 18h
0x140029960  mov     rcx, [rdx]
0x140029963  cmp     rcx, rdx
0x140029966  jnz     loc_140029A1E
0x14002996c  mov     rcx, [rbx+920h]
0x140029973  movzx   edx, r8b; NewIrql
0x140029977  add     rcx, 10h; SpinLock
0x14002997b  call    cs:__imp_KeReleaseSpinLock
0x140029982  nop     dword ptr [rax+rax+00h]
0x140029987  test    rsi, rsi
0x14002998a  jz      loc_1400298BA
0x140029990  mov     rcx, [rbx+920h]
0x140029997  mov     rdx, rsi; Entry
0x14002999a  mov     rcx, [rcx+8]; Lookaside
0x14002999e  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400299a5  nop     dword ptr [rax+rax+00h]
0x1400299aa  jmp     loc_1400298BA
0x1400299af  mov     rax, [rcx]
0x1400299b2  cmp     [rax+8], rcx
0x1400299b6  jnz     short loc_1400299CD
0x1400299b8  mov     rdx, [rcx+8]
0x1400299bc  cmp     [rdx], rcx
0x1400299bf  jnz     short loc_1400299CD
0x1400299c1  mov     [rdx], rax
0x1400299c4  mov     rsi, rcx
0x1400299c7  mov     [rax+8], rdx
0x1400299cb  jmp     short loc_14002996C
0x1400299cd  mov     ecx, 3
0x1400299d2  int     29h; Win8: RtlFailFast(ecx)
0x1400299d4  mov     rcx, [rbp+60h]; RegHandle
0x1400299d8  lea     rax, [rsp+78h+var_48]
0x1400299dd  mov     [rsp+78h+var_30], rax
0x1400299e2  mov     r9d, 2; UserDataCount
0x1400299e8  lea     rax, [rsp+78h+var_40]
0x1400299ed  mov     [rsp+78h+var_40.Ptr], rbx
0x1400299f2  xor     r8d, r8d; ActivityId
0x1400299f5  mov     [rsp+78h+UserData], rax; UserData
0x1400299fa  mov     rdx, rsi; EventDescriptor
0x1400299fd  mov     [rsp+78h+var_40.Size], 8
0x140029a05  mov     [rsp+78h+var_28], 8
0x140029a0d  call    cs:__imp_EtwWrite
0x140029a14  nop     dword ptr [rax+rax+00h]
0x140029a19  jmp     loc_1400298A8
0x140029a1e  cmp     [rcx+10h], rdi
0x140029a22  jnz     short loc_140029A2A
0x140029a24  cmp     dword ptr [rcx+18h], 2
0x140029a28  jz      short loc_1400299AF
0x140029a2a  mov     rcx, [rcx]
0x140029a2d  jmp     loc_140029963
```
