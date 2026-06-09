# FvePassThroughCompletion

- ea: `0x140029af0`
- end: `0x140029df6`
- name: `FvePassThroughCompletion`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140025fb0`

## callees

- `0x1400218c0`
- `0x140029af0`
- `0x140029dfc`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140029cf6`
- `ntoskrnl!EtwWrite` at `0x140029cf6`
- `ntoskrnl!EtwEventEnabled` at `0x140029b5d`
- `ntoskrnl!EtwEventEnabled` at `0x140029b5d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029bfd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029d47`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029bfd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029d47`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140029c87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140029c87`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140029d2f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140029d2f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140029dc0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140029dc0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029c64`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029c64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029c2e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029c2e`
- `ntoskrnl!KeBugCheckEx` at `0x140029de9`
- `ntoskrnl!KeBugCheckEx` at `0x140029de9`

## pseudocode

```c
__int64 __fastcall FvePassThroughCompletion(__int64 a1, signed __int64 a2, __int64 a3, unsigned __int8 a4)
{
  ULONGLONG v5; // rbx
  __int64 v6; // r8
  __int64 v8; // r14
  const EVENT_DESCRIPTOR *v9; // rsi
  REGHANDLE v10; // rcx
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v14; // rcx
  void *v15; // rsi
  KIRQL v16; // r9
  _QWORD *v17; // r8
  _QWORD *i; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  REGHANDLE v21; // rcx
  signed __int64 v22; // rdx
  char v23; // r9
  signed __int64 v24; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-40h] BYREF
  signed __int64 *v26; // [rsp+48h] [rbp-30h]
  int v27; // [rsp+50h] [rbp-28h]

  v5 = a3 & 0xFFFFFFFFFFFFFFFCuLL;
  v6 = a3 & 3;
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  v8 = *(_QWORD *)(v5 + 8);
  v24 = a2;
  v9 = (const EVENT_DESCRIPTOR *)FVE_PERF_WRITE_REQUEST_STOP;
  if ( !v6 )
    v9 = &FVE_PERF_READ_REQUEST_STOP;
  v10 = *(_QWORD *)(v8 + 96);
  if ( v10 && EtwEventEnabled(v10, v9) )
  {
    v21 = *(_QWORD *)(v8 + 96);
    v26 = &v24;
    UserData.Ptr = v5;
    UserData.Size = 8;
    v27 = 8;
    EtwWrite(v21, v9, 0, 2u, &UserData);
  }
  v11 = *(_QWORD *)(v5 + 2336);
  if ( *(_QWORD *)(v11 + 8) )
  {
    v15 = 0;
    v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 16));
    v17 = (_QWORD *)(*(_QWORD *)(v5 + 2336) + 24LL);
    for ( i = (_QWORD *)*v17; i != v17; i = (_QWORD *)*i )
    {
      if ( i[2] == a2 && *((_DWORD *)i + 6) == a4 )
      {
        v19 = (_QWORD *)*i;
        if ( *(_QWORD **)(*i + 8LL) != i || (v20 = (_QWORD *)i[1], (_QWORD *)*v20 != i) )
          __fastfail(3u);
        *v20 = v19;
        v15 = i;
        v19[1] = v20;
        break;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v5 + 2336) + 16LL), v16);
    if ( v15 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(v5 + 2336) + 8LL), v15);
  }
  if ( *(_DWORD *)(v5 + 2328) == 1 )
    v12 = *(volatile signed __int32 **)(v5 + 2336);
  else
    v12 = (volatile signed __int32 *)(*(_QWORD *)(v5 + 2336) + 296LL * HIDWORD(KeGetPcr()[1].LockArray));
  _InterlockedDecrement(v12);
  if ( !*(_BYTE *)(v5 + 1476) )
  {
    if ( a4 >= 2u )
    {
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v5 + 1464));
    }
    else if ( !a4 )
    {
      goto LABEL_14;
    }
    v14 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v5 + 1456);
    goto LABEL_19;
  }
  if ( a4 >= 2u )
  {
    v14 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v5 + 1464);
LABEL_19:
    ExReleaseRundownProtectionCacheAware(v14);
    goto LABEL_14;
  }
  if ( a4 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v5 + 1448));
LABEL_14:
  if ( *(_QWORD *)(v5 + 104) )
  {
    FvepReleaseScalableRemoveLock(v5 + 56);
  }
  else
  {
    do
    {
      v22 = *(_QWORD *)(v5 + 64);
      v24 = v22;
      if ( !(_DWORD)v22 )
        KeBugCheckEx(0x120u, 0xEu, v5 + 56, 0, 0);
      if ( WORD2(v22) )
      {
        v23 = 0;
        HIDWORD(v24) = HIDWORD(v22) ^ (unsigned __int16)(WORD2(v22) ^ (WORD2(v22) - 1));
      }
      else
      {
        v23 = 1;
        LODWORD(v24) = v22 - 1;
      }
    }
    while ( v22 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + 64), v24, v22) );
    if ( v23 )
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 72), *(PVOID *)(v5 + 56), 0x20u);
  }
  return 0;
}

```

## disassembly

```asm
0x140029af0  mov     [rsp+arg_0], rbx
0x140029af5  mov     [rsp+arg_18], rbp
0x140029afa  push    rsi
0x140029afb  push    rdi
0x140029afc  push    r14
0x140029afe  sub     rsp, 60h
0x140029b02  mov     rax, cs:__security_cookie
0x140029b09  xor     rax, rsp
0x140029b0c  mov     [rsp+78h+var_20], rax
0x140029b11  mov     rbx, r8
0x140029b14  mov     edi, r9d
0x140029b17  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140029b1b  and     r8d, 3
0x140029b1f  cmp     byte ptr [rdx+41h], 0
0x140029b23  mov     rbp, rdx
0x140029b26  jz      short loc_140029B33
0x140029b28  mov     rax, [rdx+0B8h]
0x140029b2f  or      byte ptr [rax+3], 1
0x140029b33  mov     r14, [rbx+8]
0x140029b37  lea     rax, FVE_PERF_READ_REQUEST_STOP
0x140029b3e  test    r8, r8
0x140029b41  mov     [rsp+78h+var_48], rbp
0x140029b46  lea     rsi, FVE_PERF_WRITE_REQUEST_STOP
0x140029b4d  cmovz   rsi, rax
0x140029b51  mov     rcx, [r14+60h]; RegHandle
0x140029b55  test    rcx, rcx
0x140029b58  jz      short loc_140029B71
0x140029b5a  mov     rdx, rsi; EventDescriptor
0x140029b5d  call    cs:__imp_EtwEventEnabled
0x140029b64  nop     dword ptr [rax+rax+00h]
0x140029b69  test    al, al
0x140029b6b  jnz     loc_140029CBD
0x140029b71  mov     rcx, [rbx+920h]
0x140029b78  cmp     qword ptr [rcx+8], 0
0x140029b7d  jnz     loc_140029C28
0x140029b83  cmp     dword ptr [rbx+918h], 1
0x140029b8a  jnz     short loc_140029C0B
0x140029b8c  mov     rax, [rbx+920h]
0x140029b93  lock dec dword ptr [rax]
0x140029b96  cmp     byte ptr [rbx+5C4h], 0
0x140029b9d  jnz     short loc_140029BEC
0x140029b9f  cmp     dil, 2
0x140029ba3  jnb     loc_140029D40
0x140029ba9  cmp     dil, 1
0x140029bad  jnb     loc_140029D53
0x140029bb3  cmp     qword ptr [rbx+68h], 0
0x140029bb8  jz      loc_140029D5F
0x140029bbe  lea     rcx, [rbx+38h]; BugCheckParameter2
0x140029bc2  call    FvepReleaseScalableRemoveLock
0x140029bc7  xor     eax, eax
0x140029bc9  mov     rcx, [rsp+78h+var_20]
0x140029bce  xor     rcx, rsp; StackCookie
0x140029bd1  call    __security_check_cookie
0x140029bd6  lea     r11, [rsp+78h+var_18]
0x140029bdb  mov     rbx, [r11+20h]
0x140029bdf  mov     rbp, [r11+38h]
0x140029be3  mov     rsp, r11
0x140029be6  pop     r14
0x140029be8  pop     rdi
0x140029be9  pop     rsi
0x140029bea  retn
0x140029bec  cmp     dil, 2
0x140029bf0  jb      loc_140029D1E
0x140029bf6  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140029bfd  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140029c04  nop     dword ptr [rax+rax+00h]
0x140029c09  jmp     short loc_140029BB3
0x140029c0b  mov     eax, gs:1A4h
0x140029c13  mov     ecx, eax
0x140029c15  imul    rax, rcx, 128h
0x140029c1c  add     rax, [rbx+920h]
0x140029c23  jmp     loc_140029B93
0x140029c28  add     rcx, 10h; SpinLock
0x140029c2c  xor     esi, esi
0x140029c2e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029c35  nop     dword ptr [rax+rax+00h]
0x140029c3a  mov     r8, [rbx+920h]
0x140029c41  movzx   r9d, al
0x140029c45  add     r8, 18h
0x140029c49  mov     rdx, [r8]
0x140029c4c  cmp     rdx, r8
0x140029c4f  jnz     loc_140029D07
0x140029c55  mov     rcx, [rbx+920h]
0x140029c5c  movzx   edx, r9b; NewIrql
0x140029c60  add     rcx, 10h; SpinLock
0x140029c64  call    cs:__imp_KeReleaseSpinLock
0x140029c6b  nop     dword ptr [rax+rax+00h]
0x140029c70  test    rsi, rsi
0x140029c73  jz      loc_140029B83
0x140029c79  mov     rcx, [rbx+920h]
0x140029c80  mov     rdx, rsi; Entry
0x140029c83  mov     rcx, [rcx+8]; Lookaside
0x140029c87  call    cs:__imp_ExFreeToNPagedLookasideList
0x140029c8e  nop     dword ptr [rax+rax+00h]
0x140029c93  jmp     loc_140029B83
0x140029c98  mov     rax, [rdx]
0x140029c9b  cmp     [rax+8], rdx
0x140029c9f  jnz     short loc_140029CB6
0x140029ca1  mov     rcx, [rdx+8]
0x140029ca5  cmp     [rcx], rdx
0x140029ca8  jnz     short loc_140029CB6
0x140029caa  mov     [rcx], rax
0x140029cad  mov     rsi, rdx
0x140029cb0  mov     [rax+8], rcx
0x140029cb4  jmp     short loc_140029C55
0x140029cb6  mov     ecx, 3
0x140029cbb  int     29h; Win8: RtlFailFast(ecx)
0x140029cbd  mov     rcx, [r14+60h]; RegHandle
0x140029cc1  lea     rax, [rsp+78h+var_48]
0x140029cc6  mov     [rsp+78h+var_30], rax
0x140029ccb  mov     r9d, 2; UserDataCount
0x140029cd1  lea     rax, [rsp+78h+var_40]
0x140029cd6  mov     [rsp+78h+var_40.Ptr], rbx
0x140029cdb  xor     r8d, r8d; ActivityId
0x140029cde  mov     [rsp+78h+UserData], rax; UserData
0x140029ce3  mov     rdx, rsi; EventDescriptor
0x140029ce6  mov     [rsp+78h+var_40.Size], 8
0x140029cee  mov     [rsp+78h+var_28], 8
0x140029cf6  call    cs:__imp_EtwWrite
0x140029cfd  nop     dword ptr [rax+rax+00h]
0x140029d02  jmp     loc_140029B71
0x140029d07  cmp     [rdx+10h], rbp
0x140029d0b  jnz     short loc_140029D16
0x140029d0d  movzx   ecx, dil
0x140029d11  cmp     [rdx+18h], ecx
0x140029d14  jz      short loc_140029C98
0x140029d16  mov     rdx, [rdx]
0x140029d19  jmp     loc_140029C4C
0x140029d1e  cmp     dil, 1
0x140029d22  jb      loc_140029BB3
0x140029d28  lea     rcx, [rbx+5A8h]; RunRef
0x140029d2f  call    cs:__imp_ExReleaseRundownProtection
0x140029d36  nop     dword ptr [rax+rax+00h]
0x140029d3b  jmp     loc_140029BB3
0x140029d40  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140029d47  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140029d4e  nop     dword ptr [rax+rax+00h]
0x140029d53  mov     rcx, [rbx+5B0h]
0x140029d5a  jmp     loc_140029BFD
0x140029d5f  mov     rdx, [rbx+40h]
0x140029d63  mov     [rsp+78h+var_48], rdx
0x140029d68  test    edx, edx
0x140029d6a  jz      short loc_140029DD1
0x140029d6c  mov     r8, rdx
0x140029d6f  shr     r8, 20h
0x140029d73  test    r8w, r8w
0x140029d77  jz      short loc_140029D8F
0x140029d79  lea     eax, [r8-1]
0x140029d7d  xor     r9b, r9b
0x140029d80  xor     eax, r8d
0x140029d83  movzx   ecx, ax
0x140029d86  xor     ecx, r8d
0x140029d89  mov     dword ptr [rsp+78h+var_48+4], ecx
0x140029d8d  jmp     short loc_140029D99
0x140029d8f  lea     ecx, [rdx-1]
0x140029d92  mov     r9b, 1
0x140029d95  mov     dword ptr [rsp+78h+var_48], ecx
0x140029d99  mov     rcx, [rsp+78h+var_48]
0x140029d9e  mov     rax, rdx
0x140029da1  lock cmpxchg [rbx+40h], rcx
0x140029da7  jnz     short loc_140029D5F
0x140029da9  test    r9b, r9b
0x140029dac  jz      loc_140029BC7
0x140029db2  mov     rdx, [rbx+38h]; Tag
0x140029db6  lea     rcx, [rbx+48h]; RemoveLock
0x140029dba  mov     r8d, 20h ; ' '; RemlockSize
0x140029dc0  call    cs:__imp_IoReleaseRemoveLockEx
0x140029dc7  nop     dword ptr [rax+rax+00h]
0x140029dcc  jmp     loc_140029BC7
0x140029dd1  mov     eax, edx
0x140029dd3  lea     r8, [rbx+38h]; BugCheckParameter2
0x140029dd7  mov     edx, 0Eh; BugCheckParameter1
0x140029ddc  mov     [rsp+78h+UserData], rax; BugCheckParameter4
0x140029de1  xor     r9d, r9d; BugCheckParameter3
0x140029de4  mov     ecx, 120h; BugCheckCode
0x140029de9  call    cs:__imp_KeBugCheckEx
```
