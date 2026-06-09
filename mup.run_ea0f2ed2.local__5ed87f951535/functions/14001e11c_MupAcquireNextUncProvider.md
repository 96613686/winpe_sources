# MupAcquireNextUncProvider

- ea: `0x14001e11c`
- end: `0x14001e35f`
- name: `MupAcquireNextUncProvider`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001cf8`

## callees

- `0x140002754`
- `0x140013330`
- `0x140013de0`
- `0x140013e10`
- `0x14001e11c`
- `0x14001e368`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001e1cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e27d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e2e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e1cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e27d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e2e8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e137`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e24a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e137`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e24a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001e14c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001e25f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001e14c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001e25f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e1d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e289`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e2f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e1d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e289`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e2f4`
- `ntoskrnl!KeReadStateEvent` at `0x14001e326`
- `ntoskrnl!KeReadStateEvent` at `0x14001e326`

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
0x14001e11c  push    rbx
0x14001e11e  push    rbp
0x14001e11f  push    rsi
0x14001e120  push    rdi
0x14001e121  push    r12
0x14001e123  push    r14
0x14001e125  push    r15
0x14001e127  sub     rsp, 20h
0x14001e12b  mov     r15, r9
0x14001e12e  mov     r12, r8
0x14001e131  mov     r14, rdx
0x14001e134  mov     rbx, rcx
0x14001e137  call    cs:__imp_KeEnterCriticalRegion
0x14001e13e  nop     dword ptr [rax+rax+00h]
0x14001e143  mov     dl, 1; Wait
0x14001e145  lea     rcx, Resource; Resource
0x14001e14c  call    cs:__imp_ExAcquireResourceSharedLite
0x14001e153  nop     dword ptr [rax+rax+00h]
0x14001e158  mov     eax, cs:dword_14000A778
0x14001e15e  xor     bpl, bpl
0x14001e161  test    rbx, rbx
0x14001e164  jz      loc_14001E2A2
0x14001e16a  cmp     [r14], eax
0x14001e16d  jnz     loc_14001E2B4
0x14001e173  mov     rcx, [rbx+8]
0x14001e177  xor     r8b, r8b
0x14001e17a  xor     sil, sil
0x14001e17d  xor     edi, edi
0x14001e17f  lea     rax, qword_14000A768
0x14001e186  cmp     rcx, rax
0x14001e189  jz      short loc_14001E1C4
0x14001e18b  lea     rdi, [rcx-8]
0x14001e18f  mov     edx, [rdi+44h]
0x14001e192  lea     eax, [rdx-2]
0x14001e195  cmp     eax, 1
0x14001e198  jbe     short loc_14001E1AB
0x14001e19a  cmp     edx, 1
0x14001e19d  jnz     short loc_14001E1A6
0x14001e19f  cmp     qword ptr [rdi+50h], 0
0x14001e1a4  jnz     short loc_14001E1AB
0x14001e1a6  mov     rcx, [rcx]
0x14001e1a9  jmp     short loc_14001E17F
0x14001e1ab  test    r8b, r8b
0x14001e1ae  jnz     loc_14001E2B9
0x14001e1b4  cmp     edx, 1
0x14001e1b7  jz      loc_14001E29A
0x14001e1bd  lock inc dword ptr [rdi+4]
0x14001e1c1  mov     sil, 1
0x14001e1c4  lea     rcx, Resource; Resource
0x14001e1cb  call    cs:__imp_ExReleaseResourceLite
0x14001e1d2  nop     dword ptr [rax+rax+00h]
0x14001e1d7  call    cs:__imp_KeLeaveCriticalRegion
0x14001e1de  nop     dword ptr [rax+rax+00h]
0x14001e1e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1ea  lea     rax, WPP_GLOBAL_Control
0x14001e1f1  neg     sil
0x14001e1f4  sbb     rbx, rbx
0x14001e1f7  and     rbx, rdi
0x14001e1fa  cmp     rcx, rax
0x14001e1fd  jz      short loc_14001E20C
0x14001e1ff  test    dword ptr [rcx+2Ch], 4000000h
0x14001e206  jnz     loc_14001E2C7
0x14001e20c  test    bpl, bpl
0x14001e20f  jnz     short loc_14001E234
0x14001e211  test    rbx, rbx
0x14001e214  jz      short loc_14001E221
0x14001e216  cmp     qword ptr [rbx+50h], 0
0x14001e21b  jnz     loc_14001E305
0x14001e221  mov     rax, rbx
0x14001e224  add     rsp, 20h
0x14001e228  pop     r15
0x14001e22a  pop     r14
0x14001e22c  pop     r12
0x14001e22e  pop     rdi
0x14001e22f  pop     rsi
0x14001e230  pop     rbp
0x14001e231  pop     rbx
0x14001e232  retn
0x14001e234  mov     r8, r15
0x14001e237  mov     rdx, r12
0x14001e23a  mov     rcx, rbx
0x14001e23d  call    MupiTriggerStartProvider
0x14001e242  test    al, al
0x14001e244  jz      loc_14001E137
0x14001e24a  call    cs:__imp_KeEnterCriticalRegion
0x14001e251  nop     dword ptr [rax+rax+00h]
0x14001e256  mov     dl, 1; Wait
0x14001e258  lea     rcx, Resource; Resource
0x14001e25f  call    cs:__imp_ExAcquireResourceSharedLite
0x14001e266  nop     dword ptr [rax+rax+00h]
0x14001e26b  mov     eax, [rbx+44h]
0x14001e26e  lea     rcx, Resource; Resource
0x14001e275  sub     eax, 2
0x14001e278  cmp     eax, 1
0x14001e27b  jbe     short loc_14001E2E4
0x14001e27d  call    cs:__imp_ExReleaseResourceLite
0x14001e284  nop     dword ptr [rax+rax+00h]
0x14001e289  call    cs:__imp_KeLeaveCriticalRegion
0x14001e290  nop     dword ptr [rax+rax+00h]
0x14001e295  jmp     loc_14001E137
0x14001e29a  mov     bpl, 1
0x14001e29d  jmp     loc_14001E1C1
0x14001e2a2  xor     r8b, r8b
0x14001e2a5  mov     rcx, cs:qword_14000A768
0x14001e2ac  mov     [r14], eax
0x14001e2af  jmp     loc_14001E17A
0x14001e2b4  mov     r8b, 1
0x14001e2b7  jmp     short loc_14001E2A5
0x14001e2b9  cmp     rdi, rbx
0x14001e2bc  jnz     loc_14001E1B4
0x14001e2c2  jmp     loc_14001E1A6
0x14001e2c7  mov     rcx, [rcx+18h]
0x14001e2cb  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x14001e2d2  mov     edx, 0Eh
0x14001e2d7  mov     r9, rbx
0x14001e2da  call    WPP_SF_q
0x14001e2df  jmp     loc_14001E20C
0x14001e2e4  lock inc dword ptr [rbx+4]
0x14001e2e8  call    cs:__imp_ExReleaseResourceLite
0x14001e2ef  nop     dword ptr [rax+rax+00h]
0x14001e2f4  call    cs:__imp_KeLeaveCriticalRegion
0x14001e2fb  nop     dword ptr [rax+rax+00h]
0x14001e300  jmp     loc_14001E221
0x14001e305  cmp     qword ptr [rbx+70h], 0
0x14001e30a  jz      loc_14001E221
0x14001e310  mov     rcx, rbx
0x14001e313  call    MupiLockProviderTriggerStartExclusive
0x14001e318  cmp     qword ptr [rbx+70h], 0
0x14001e31d  jz      short loc_14001E352
0x14001e31f  mov     rcx, [rbx+88h]; Event
0x14001e326  call    cs:__imp_KeReadStateEvent
0x14001e32d  nop     dword ptr [rax+rax+00h]
0x14001e332  test    eax, eax
0x14001e334  jnz     short loc_14001E352
0x14001e336  inc     qword ptr [rbx+70h]
0x14001e33a  mov     rcx, rbx
0x14001e33d  call    MupiUnlockProviderTriggerStartExclusive
0x14001e342  mov     rdx, r15
0x14001e345  mov     rcx, rbx
0x14001e348  call    MupiWaitForProviderTriggerStart
0x14001e34d  jmp     loc_14001E221
0x14001e352  mov     rcx, rbx
0x14001e355  call    MupiUnlockProviderTriggerStartExclusive
0x14001e35a  jmp     loc_14001E221
```
