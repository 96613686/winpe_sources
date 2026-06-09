# FvePassThroughCompletion

- ea: `0x14002aaf0`
- end: `0x14002adf6`
- name: `FvePassThroughCompletion`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140026fb0`

## callees

- `0x140022bf0`
- `0x14002aaf0`
- `0x14002adfc`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002acf6`
- `ntoskrnl!EtwWrite` at `0x14002acf6`
- `ntoskrnl!EtwEventEnabled` at `0x14002ab5d`
- `ntoskrnl!EtwEventEnabled` at `0x14002ab5d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002abfd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002ad47`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002abfd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002ad47`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002ac87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002ac87`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002ad2f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002ad2f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002adc0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002adc0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ac64`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ac64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ac2e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ac2e`
- `ntoskrnl!KeBugCheckEx` at `0x14002ade9`
- `ntoskrnl!KeBugCheckEx` at `0x14002ade9`

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
  v11 = *(_QWORD *)(v5 + 2352);
  if ( *(_QWORD *)(v11 + 8) )
  {
    v15 = 0;
    v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 16));
    v17 = (_QWORD *)(*(_QWORD *)(v5 + 2352) + 24LL);
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
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v5 + 2352) + 16LL), v16);
    if ( v15 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(v5 + 2352) + 8LL), v15);
  }
  if ( *(_DWORD *)(v5 + 2344) == 1 )
    v12 = *(volatile signed __int32 **)(v5 + 2352);
  else
    v12 = (volatile signed __int32 *)(*(_QWORD *)(v5 + 2352) + 296LL * HIDWORD(KeGetPcr()[1].LockArray));
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
0x14002aaf0  mov     [rsp+arg_0], rbx
0x14002aaf5  mov     [rsp+arg_18], rbp
0x14002aafa  push    rsi
0x14002aafb  push    rdi
0x14002aafc  push    r14
0x14002aafe  sub     rsp, 60h
0x14002ab02  mov     rax, cs:__security_cookie
0x14002ab09  xor     rax, rsp
0x14002ab0c  mov     [rsp+78h+var_20], rax
0x14002ab11  mov     rbx, r8
0x14002ab14  mov     edi, r9d
0x14002ab17  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14002ab1b  and     r8d, 3
0x14002ab1f  cmp     byte ptr [rdx+41h], 0
0x14002ab23  mov     rbp, rdx
0x14002ab26  jz      short loc_14002AB33
0x14002ab28  mov     rax, [rdx+0B8h]
0x14002ab2f  or      byte ptr [rax+3], 1
0x14002ab33  mov     r14, [rbx+8]
0x14002ab37  lea     rax, FVE_PERF_READ_REQUEST_STOP
0x14002ab3e  test    r8, r8
0x14002ab41  mov     [rsp+78h+var_48], rbp
0x14002ab46  lea     rsi, FVE_PERF_WRITE_REQUEST_STOP
0x14002ab4d  cmovz   rsi, rax
0x14002ab51  mov     rcx, [r14+60h]; RegHandle
0x14002ab55  test    rcx, rcx
0x14002ab58  jz      short loc_14002AB71
0x14002ab5a  mov     rdx, rsi; EventDescriptor
0x14002ab5d  call    cs:__imp_EtwEventEnabled
0x14002ab64  nop     dword ptr [rax+rax+00h]
0x14002ab69  test    al, al
0x14002ab6b  jnz     loc_14002ACBD
0x14002ab71  mov     rcx, [rbx+930h]
0x14002ab78  cmp     qword ptr [rcx+8], 0
0x14002ab7d  jnz     loc_14002AC28
0x14002ab83  cmp     dword ptr [rbx+928h], 1
0x14002ab8a  jnz     short loc_14002AC0B
0x14002ab8c  mov     rax, [rbx+930h]
0x14002ab93  lock dec dword ptr [rax]
0x14002ab96  cmp     byte ptr [rbx+5C4h], 0
0x14002ab9d  jnz     short loc_14002ABEC
0x14002ab9f  cmp     dil, 2
0x14002aba3  jnb     loc_14002AD40
0x14002aba9  cmp     dil, 1
0x14002abad  jnb     loc_14002AD53
0x14002abb3  cmp     qword ptr [rbx+68h], 0
0x14002abb8  jz      loc_14002AD5F
0x14002abbe  lea     rcx, [rbx+38h]; BugCheckParameter2
0x14002abc2  call    FvepReleaseScalableRemoveLock
0x14002abc7  xor     eax, eax
0x14002abc9  mov     rcx, [rsp+78h+var_20]
0x14002abce  xor     rcx, rsp; StackCookie
0x14002abd1  call    __security_check_cookie
0x14002abd6  lea     r11, [rsp+78h+var_18]
0x14002abdb  mov     rbx, [r11+20h]
0x14002abdf  mov     rbp, [r11+38h]
0x14002abe3  mov     rsp, r11
0x14002abe6  pop     r14
0x14002abe8  pop     rdi
0x14002abe9  pop     rsi
0x14002abea  retn
0x14002abec  cmp     dil, 2
0x14002abf0  jb      loc_14002AD1E
0x14002abf6  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002abfd  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002ac04  nop     dword ptr [rax+rax+00h]
0x14002ac09  jmp     short loc_14002ABB3
0x14002ac0b  mov     eax, gs:1A4h
0x14002ac13  mov     ecx, eax
0x14002ac15  imul    rax, rcx, 128h
0x14002ac1c  add     rax, [rbx+930h]
0x14002ac23  jmp     loc_14002AB93
0x14002ac28  add     rcx, 10h; SpinLock
0x14002ac2c  xor     esi, esi
0x14002ac2e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ac35  nop     dword ptr [rax+rax+00h]
0x14002ac3a  mov     r8, [rbx+930h]
0x14002ac41  movzx   r9d, al
0x14002ac45  add     r8, 18h
0x14002ac49  mov     rdx, [r8]
0x14002ac4c  cmp     rdx, r8
0x14002ac4f  jnz     loc_14002AD07
0x14002ac55  mov     rcx, [rbx+930h]
0x14002ac5c  movzx   edx, r9b; NewIrql
0x14002ac60  add     rcx, 10h; SpinLock
0x14002ac64  call    cs:__imp_KeReleaseSpinLock
0x14002ac6b  nop     dword ptr [rax+rax+00h]
0x14002ac70  test    rsi, rsi
0x14002ac73  jz      loc_14002AB83
0x14002ac79  mov     rcx, [rbx+930h]
0x14002ac80  mov     rdx, rsi; Entry
0x14002ac83  mov     rcx, [rcx+8]; Lookaside
0x14002ac87  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002ac8e  nop     dword ptr [rax+rax+00h]
0x14002ac93  jmp     loc_14002AB83
0x14002ac98  mov     rax, [rdx]
0x14002ac9b  cmp     [rax+8], rdx
0x14002ac9f  jnz     short loc_14002ACB6
0x14002aca1  mov     rcx, [rdx+8]
0x14002aca5  cmp     [rcx], rdx
0x14002aca8  jnz     short loc_14002ACB6
0x14002acaa  mov     [rcx], rax
0x14002acad  mov     rsi, rdx
0x14002acb0  mov     [rax+8], rcx
0x14002acb4  jmp     short loc_14002AC55
0x14002acb6  mov     ecx, 3
0x14002acbb  int     29h; Win8: RtlFailFast(ecx)
0x14002acbd  mov     rcx, [r14+60h]; RegHandle
0x14002acc1  lea     rax, [rsp+78h+var_48]
0x14002acc6  mov     [rsp+78h+var_30], rax
0x14002accb  mov     r9d, 2; UserDataCount
0x14002acd1  lea     rax, [rsp+78h+var_40]
0x14002acd6  mov     [rsp+78h+var_40.Ptr], rbx
0x14002acdb  xor     r8d, r8d; ActivityId
0x14002acde  mov     [rsp+78h+UserData], rax; UserData
0x14002ace3  mov     rdx, rsi; EventDescriptor
0x14002ace6  mov     [rsp+78h+var_40.Size], 8
0x14002acee  mov     [rsp+78h+var_28], 8
0x14002acf6  call    cs:__imp_EtwWrite
0x14002acfd  nop     dword ptr [rax+rax+00h]
0x14002ad02  jmp     loc_14002AB71
0x14002ad07  cmp     [rdx+10h], rbp
0x14002ad0b  jnz     short loc_14002AD16
0x14002ad0d  movzx   ecx, dil
0x14002ad11  cmp     [rdx+18h], ecx
0x14002ad14  jz      short loc_14002AC98
0x14002ad16  mov     rdx, [rdx]
0x14002ad19  jmp     loc_14002AC4C
0x14002ad1e  cmp     dil, 1
0x14002ad22  jb      loc_14002ABB3
0x14002ad28  lea     rcx, [rbx+5A8h]; RunRef
0x14002ad2f  call    cs:__imp_ExReleaseRundownProtection
0x14002ad36  nop     dword ptr [rax+rax+00h]
0x14002ad3b  jmp     loc_14002ABB3
0x14002ad40  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x14002ad47  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002ad4e  nop     dword ptr [rax+rax+00h]
0x14002ad53  mov     rcx, [rbx+5B0h]
0x14002ad5a  jmp     loc_14002ABFD
0x14002ad5f  mov     rdx, [rbx+40h]
0x14002ad63  mov     [rsp+78h+var_48], rdx
0x14002ad68  test    edx, edx
0x14002ad6a  jz      short loc_14002ADD1
0x14002ad6c  mov     r8, rdx
0x14002ad6f  shr     r8, 20h
0x14002ad73  test    r8w, r8w
0x14002ad77  jz      short loc_14002AD8F
0x14002ad79  lea     eax, [r8-1]
0x14002ad7d  xor     r9b, r9b
0x14002ad80  xor     eax, r8d
0x14002ad83  movzx   ecx, ax
0x14002ad86  xor     ecx, r8d
0x14002ad89  mov     dword ptr [rsp+78h+var_48+4], ecx
0x14002ad8d  jmp     short loc_14002AD99
0x14002ad8f  lea     ecx, [rdx-1]
0x14002ad92  mov     r9b, 1
0x14002ad95  mov     dword ptr [rsp+78h+var_48], ecx
0x14002ad99  mov     rcx, [rsp+78h+var_48]
0x14002ad9e  mov     rax, rdx
0x14002ada1  lock cmpxchg [rbx+40h], rcx
0x14002ada7  jnz     short loc_14002AD5F
0x14002ada9  test    r9b, r9b
0x14002adac  jz      loc_14002ABC7
0x14002adb2  mov     rdx, [rbx+38h]; Tag
0x14002adb6  lea     rcx, [rbx+48h]; RemoveLock
0x14002adba  mov     r8d, 20h ; ' '; RemlockSize
0x14002adc0  call    cs:__imp_IoReleaseRemoveLockEx
0x14002adc7  nop     dword ptr [rax+rax+00h]
0x14002adcc  jmp     loc_14002ABC7
0x14002add1  mov     eax, edx
0x14002add3  lea     r8, [rbx+38h]; BugCheckParameter2
0x14002add7  mov     edx, 0Eh; BugCheckParameter1
0x14002addc  mov     [rsp+78h+UserData], rax; BugCheckParameter4
0x14002ade1  xor     r9d, r9d; BugCheckParameter3
0x14002ade4  mov     ecx, 120h; BugCheckCode
0x14002ade9  call    cs:__imp_KeBugCheckEx
```
