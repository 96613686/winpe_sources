# MupAcquireNextUncProvider

- ea: `0x14001e16c`
- end: `0x14001e3af`
- name: `MupAcquireNextUncProvider`
- size: `579`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001cf8`

## callees

- `0x140002754`
- `0x140013380`
- `0x140013e30`
- `0x140013e60`
- `0x14001e16c`
- `0x14001e3b8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001e21b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e2cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e338`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e21b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e2cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e338`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e187`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e29a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e187`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e29a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001e19c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001e2af`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001e19c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001e2af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e227`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e2d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e344`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e227`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e2d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e344`
- `ntoskrnl!KeReadStateEvent` at `0x14001e376`
- `ntoskrnl!KeReadStateEvent` at `0x14001e376`

## pseudocode

```c
__int64 __fastcall MupAcquireNextUncProvider(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  char v8; // bp
  __int64 *v9; // rcx
  char v10; // r8
  char v11; // si
  __int64 *v12; // rdi
  int v13; // edx
  char v14; // si

  do
  {
LABEL_1:
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&Resource, 1u);
    v8 = 0;
    if ( !a1 )
    {
      v10 = 0;
LABEL_26:
      v9 = (__int64 *)qword_14000A768;
      *a2 = dword_14000A778;
      goto LABEL_4;
    }
    if ( *a2 != dword_14000A778 )
    {
      v10 = 1;
      goto LABEL_26;
    }
    v9 = *(__int64 **)(a1 + 8);
    v10 = 0;
LABEL_4:
    v11 = 0;
    v12 = 0;
    while ( v9 != &qword_14000A768 )
    {
      v12 = v9 - 1;
      v13 = *((_DWORD *)v9 + 15);
      if ( ((unsigned int)(v13 - 2) <= 1 || v13 == 1 && v12[10]) && (!v10 || v12 != (__int64 *)a1) )
      {
        if ( v13 == 1 )
          v8 = 1;
        else
          _InterlockedIncrement((volatile signed __int32 *)v12 + 1);
        v11 = 1;
        break;
      }
      v9 = (__int64 *)*v9;
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    v14 = -v11;
    a1 = (unsigned __int64)v12 & -(__int64)(v14 != 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids,
        (unsigned __int64)v12 & -(__int64)(v14 != 0));
    }
    if ( !v8 )
    {
      if ( a1
        && *(_QWORD *)(((unsigned __int64)v12 & -(__int64)(v14 != 0)) + 0x50)
        && *(_QWORD *)(((unsigned __int64)v12 & -(__int64)(v14 != 0)) + 0x70) )
      {
        MupiLockProviderTriggerStartExclusive((unsigned __int64)v12 & -(__int64)(v14 != 0));
        if ( !*(_QWORD *)(((unsigned __int64)v12 & -(__int64)(v14 != 0)) + 0x70)
          || KeReadStateEvent(*(PRKEVENT *)(((unsigned __int64)v12 & -(__int64)(v14 != 0)) + 0x88)) )
        {
          MupiUnlockProviderTriggerStartExclusive((unsigned __int64)v12 & -(__int64)(v14 != 0));
        }
        else
        {
          ++*(_QWORD *)(((unsigned __int64)v12 & -(__int64)(v14 != 0)) + 0x70);
          MupiUnlockProviderTriggerStartExclusive((unsigned __int64)v12 & -(__int64)(v14 != 0));
          MupiWaitForProviderTriggerStart((unsigned __int64)v12 & -(__int64)(v14 != 0), a4);
        }
      }
      return (unsigned __int64)v12 & -(__int64)(v14 != 0);
    }
  }
  while ( !(unsigned __int8)MupiTriggerStartProvider((unsigned __int64)v12 & -(__int64)(v14 != 0), a3, a4) );
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(&Resource, 1u);
  if ( (unsigned int)(*(_DWORD *)(((unsigned __int64)v12 & -(__int64)(v14 != 0)) + 0x44) - 2) > 1 )
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    goto LABEL_1;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  return (unsigned __int64)v12 & -(__int64)(v14 != 0);
}

```

## disassembly

```asm
0x14001e16c  push    rbx
0x14001e16e  push    rbp
0x14001e16f  push    rsi
0x14001e170  push    rdi
0x14001e171  push    r12
0x14001e173  push    r14
0x14001e175  push    r15
0x14001e177  sub     rsp, 20h
0x14001e17b  mov     r15, r9
0x14001e17e  mov     r12, r8
0x14001e181  mov     r14, rdx
0x14001e184  mov     rbx, rcx
0x14001e187  call    cs:__imp_KeEnterCriticalRegion
0x14001e18e  nop     dword ptr [rax+rax+00h]
0x14001e193  mov     dl, 1; Wait
0x14001e195  lea     rcx, Resource; Resource
0x14001e19c  call    cs:__imp_ExAcquireResourceSharedLite
0x14001e1a3  nop     dword ptr [rax+rax+00h]
0x14001e1a8  mov     eax, cs:dword_14000A778
0x14001e1ae  xor     bpl, bpl
0x14001e1b1  test    rbx, rbx
0x14001e1b4  jz      loc_14001E2F2
0x14001e1ba  cmp     [r14], eax
0x14001e1bd  jnz     loc_14001E304
0x14001e1c3  mov     rcx, [rbx+8]
0x14001e1c7  xor     r8b, r8b
0x14001e1ca  xor     sil, sil
0x14001e1cd  xor     edi, edi
0x14001e1cf  lea     rax, qword_14000A768
0x14001e1d6  cmp     rcx, rax
0x14001e1d9  jz      short loc_14001E214
0x14001e1db  lea     rdi, [rcx-8]
0x14001e1df  mov     edx, [rdi+44h]
0x14001e1e2  lea     eax, [rdx-2]
0x14001e1e5  cmp     eax, 1
0x14001e1e8  jbe     short loc_14001E1FB
0x14001e1ea  cmp     edx, 1
0x14001e1ed  jnz     short loc_14001E1F6
0x14001e1ef  cmp     qword ptr [rdi+50h], 0
0x14001e1f4  jnz     short loc_14001E1FB
0x14001e1f6  mov     rcx, [rcx]
0x14001e1f9  jmp     short loc_14001E1CF
0x14001e1fb  test    r8b, r8b
0x14001e1fe  jnz     loc_14001E309
0x14001e204  cmp     edx, 1
0x14001e207  jz      loc_14001E2EA
0x14001e20d  lock inc dword ptr [rdi+4]
0x14001e211  mov     sil, 1
0x14001e214  lea     rcx, Resource; Resource
0x14001e21b  call    cs:__imp_ExReleaseResourceLite
0x14001e222  nop     dword ptr [rax+rax+00h]
0x14001e227  call    cs:__imp_KeLeaveCriticalRegion
0x14001e22e  nop     dword ptr [rax+rax+00h]
0x14001e233  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e23a  lea     rax, WPP_GLOBAL_Control
0x14001e241  neg     sil
0x14001e244  sbb     rbx, rbx
0x14001e247  and     rbx, rdi
0x14001e24a  cmp     rcx, rax
0x14001e24d  jz      short loc_14001E25C
0x14001e24f  test    dword ptr [rcx+2Ch], 4000000h
0x14001e256  jnz     loc_14001E317
0x14001e25c  test    bpl, bpl
0x14001e25f  jnz     short loc_14001E284
0x14001e261  test    rbx, rbx
0x14001e264  jz      short loc_14001E271
0x14001e266  cmp     qword ptr [rbx+50h], 0
0x14001e26b  jnz     loc_14001E355
0x14001e271  mov     rax, rbx
0x14001e274  add     rsp, 20h
0x14001e278  pop     r15
0x14001e27a  pop     r14
0x14001e27c  pop     r12
0x14001e27e  pop     rdi
0x14001e27f  pop     rsi
0x14001e280  pop     rbp
0x14001e281  pop     rbx
0x14001e282  retn
0x14001e284  mov     r8, r15
0x14001e287  mov     rdx, r12
0x14001e28a  mov     rcx, rbx
0x14001e28d  call    MupiTriggerStartProvider
0x14001e292  test    al, al
0x14001e294  jz      loc_14001E187
0x14001e29a  call    cs:__imp_KeEnterCriticalRegion
0x14001e2a1  nop     dword ptr [rax+rax+00h]
0x14001e2a6  mov     dl, 1; Wait
0x14001e2a8  lea     rcx, Resource; Resource
0x14001e2af  call    cs:__imp_ExAcquireResourceSharedLite
0x14001e2b6  nop     dword ptr [rax+rax+00h]
0x14001e2bb  mov     eax, [rbx+44h]
0x14001e2be  lea     rcx, Resource; Resource
0x14001e2c5  sub     eax, 2
0x14001e2c8  cmp     eax, 1
0x14001e2cb  jbe     short loc_14001E334
0x14001e2cd  call    cs:__imp_ExReleaseResourceLite
0x14001e2d4  nop     dword ptr [rax+rax+00h]
0x14001e2d9  call    cs:__imp_KeLeaveCriticalRegion
0x14001e2e0  nop     dword ptr [rax+rax+00h]
0x14001e2e5  jmp     loc_14001E187
0x14001e2ea  mov     bpl, 1
0x14001e2ed  jmp     loc_14001E211
0x14001e2f2  xor     r8b, r8b
0x14001e2f5  mov     rcx, cs:qword_14000A768
0x14001e2fc  mov     [r14], eax
0x14001e2ff  jmp     loc_14001E1CA
0x14001e304  mov     r8b, 1
0x14001e307  jmp     short loc_14001E2F5
0x14001e309  cmp     rdi, rbx
0x14001e30c  jnz     loc_14001E204
0x14001e312  jmp     loc_14001E1F6
0x14001e317  mov     rcx, [rcx+18h]
0x14001e31b  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x14001e322  mov     edx, 0Eh
0x14001e327  mov     r9, rbx
0x14001e32a  call    WPP_SF_q
0x14001e32f  jmp     loc_14001E25C
0x14001e334  lock inc dword ptr [rbx+4]
0x14001e338  call    cs:__imp_ExReleaseResourceLite
0x14001e33f  nop     dword ptr [rax+rax+00h]
0x14001e344  call    cs:__imp_KeLeaveCriticalRegion
0x14001e34b  nop     dword ptr [rax+rax+00h]
0x14001e350  jmp     loc_14001E271
0x14001e355  cmp     qword ptr [rbx+70h], 0
0x14001e35a  jz      loc_14001E271
0x14001e360  mov     rcx, rbx
0x14001e363  call    MupiLockProviderTriggerStartExclusive
0x14001e368  cmp     qword ptr [rbx+70h], 0
0x14001e36d  jz      short loc_14001E3A2
0x14001e36f  mov     rcx, [rbx+88h]; Event
0x14001e376  call    cs:__imp_KeReadStateEvent
0x14001e37d  nop     dword ptr [rax+rax+00h]
0x14001e382  test    eax, eax
0x14001e384  jnz     short loc_14001E3A2
0x14001e386  inc     qword ptr [rbx+70h]
0x14001e38a  mov     rcx, rbx
0x14001e38d  call    MupiUnlockProviderTriggerStartExclusive
0x14001e392  mov     rdx, r15
0x14001e395  mov     rcx, rbx
0x14001e398  call    MupiWaitForProviderTriggerStart
0x14001e39d  jmp     loc_14001E271
0x14001e3a2  mov     rcx, rbx
0x14001e3a5  call    MupiUnlockProviderTriggerStartExclusive
0x14001e3aa  jmp     loc_14001E271
```
