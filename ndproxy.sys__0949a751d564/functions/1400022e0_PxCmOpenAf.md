# PxCmOpenAf

- ea: `0x1400022e0`
- end: `0x1400024a3`
- name: `PxCmOpenAf`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001b54`
- `0x140001b84`
- `0x140001d54`
- `0x1400022e0`
- `0x1400079c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002375`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002415`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002375`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002415`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002392`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002455`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002392`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002455`
- `NDIS!NdisInitializeEvent` at `0x140002406`
- `NDIS!NdisInitializeEvent` at `0x140002406`

## pseudocode

```c
__int64 __fastcall PxCmOpenAf(__int64 a1, unsigned int *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // r9
  __int64 v10; // rdi
  KIRQL v11; // al
  bool v12; // zf
  KSPIN_LOCK *v13; // rcx
  __int64 CmAf; // rax
  _QWORD *v15; // rbx
  _QWORD *v16; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids, *a2);
  v8 = *a2;
  if ( (_DWORD)v8 == 2048 )
  {
    v10 = a1 - 16;
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 624));
    v12 = *(_DWORD *)(v10 + 20) == 3;
    v13 = (KSPIN_LOCK *)(v10 + 624);
    *(_BYTE *)(v10 + 632) = v11;
    if ( v12 )
    {
      KeReleaseSpinLock(v13, v11);
      CmAf = PxAllocateCmAf(a2);
      v15 = (_QWORD *)CmAf;
      if ( CmAf )
      {
        *(_QWORD *)(CmAf + 24) = a3;
        *(_DWORD *)(CmAf + 16) = 3;
        *(_QWORD *)(CmAf + 32) = v10;
        NdisInitializeEvent((PNDIS_EVENT)(CmAf + 104));
        *(_BYTE *)(v10 + 632) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 624));
        v16 = *(_QWORD **)(v10 + 88);
        if ( *v16 != v10 + 80 )
          __fastfail(3u);
        *v15 = v10 + 80;
        v15[1] = v16;
        *v16 = v15;
        *(_QWORD *)(v10 + 88) = v15;
        ++*(_DWORD *)(v10 + 24);
        KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 624), *(_BYTE *)(v10 + 632));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids, v15, a3);
        *a4 = v15;
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids);
        return 3221225626LL;
      }
    }
    else
    {
      KeReleaseSpinLock(v13, v11);
      return 3221291010LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids, v8);
    return 3221291012LL;
  }
}

```

## disassembly

```asm
0x1400022e0  push    rbx
0x1400022e2  push    rbp
0x1400022e3  push    rsi
0x1400022e4  push    rdi
0x1400022e5  push    r12
0x1400022e7  push    r14
0x1400022e9  sub     rsp, 38h
0x1400022ed  mov     r14, r9
0x1400022f0  mov     rbp, r8
0x1400022f3  mov     rbx, rdx
0x1400022f6  mov     rdi, rcx
0x1400022f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140002300  lea     r12, WPP_GLOBAL_Control
0x140002307  cmp     rcx, r12
0x14000230a  jz      short loc_14000232A
0x14000230c  cmp     byte ptr [rcx+29h], 5
0x140002310  jb      short loc_14000232A
0x140002312  mov     r9d, [rbx]
0x140002315  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x14000231c  mov     rcx, [rcx+18h]
0x140002320  mov     edx, 0Ch
0x140002325  call    WPP_SF_d
0x14000232a  mov     r9d, [rbx]
0x14000232d  cmp     r9d, 800h
0x140002334  jz      short loc_140002367
0x140002336  mov     rcx, cs:WPP_GLOBAL_Control
0x14000233d  cmp     rcx, r12
0x140002340  jz      short loc_14000235D
0x140002342  cmp     byte ptr [rcx+29h], 2
0x140002346  jb      short loc_14000235D
0x140002348  mov     rcx, [rcx+18h]
0x14000234c  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x140002353  mov     edx, 0Dh
0x140002358  call    WPP_SF_d
0x14000235d  mov     eax, 0C0010004h
0x140002362  jmp     loc_140002495
0x140002367  add     rdi, 0FFFFFFFFFFFFFFF0h
0x14000236b  lea     rsi, [rdi+270h]
0x140002372  mov     rcx, rsi; SpinLock
0x140002375  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000237c  nop     dword ptr [rax+rax+00h]
0x140002381  cmp     dword ptr [rdi+14h], 3
0x140002385  mov     rcx, rsi; SpinLock
0x140002388  mov     [rdi+278h], al
0x14000238e  mov     dl, al; NewIrql
0x140002390  jz      short loc_1400023A8
0x140002392  call    cs:__imp_KeReleaseSpinLock
0x140002399  nop     dword ptr [rax+rax+00h]
0x14000239e  mov     eax, 0C0010002h
0x1400023a3  jmp     loc_140002495
0x1400023a8  call    cs:__imp_KeReleaseSpinLock
0x1400023af  nop     dword ptr [rax+rax+00h]
0x1400023b4  mov     rcx, rbx
0x1400023b7  call    PxAllocateCmAf
0x1400023bc  mov     rbx, rax
0x1400023bf  test    rax, rax
0x1400023c2  jnz     short loc_1400023F3
0x1400023c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023cb  cmp     rcx, r12
0x1400023ce  jz      short loc_1400023E9
0x1400023d0  cmp     byte ptr [rcx+29h], 2
0x1400023d4  jb      short loc_1400023E9
0x1400023d6  mov     rcx, [rcx+18h]
0x1400023da  lea     edx, [rax+0Eh]
0x1400023dd  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x1400023e4  call    WPP_SF_
0x1400023e9  mov     eax, 0C000009Ah
0x1400023ee  jmp     loc_140002495
0x1400023f3  lea     rcx, [rax+68h]; Event
0x1400023f7  mov     [rax+18h], rbp
0x1400023fb  mov     dword ptr [rax+10h], 3
0x140002402  mov     [rax+20h], rdi
0x140002406  call    cs:__imp_NdisInitializeEvent
0x14000240d  nop     dword ptr [rax+rax+00h]
0x140002412  mov     rcx, rsi; SpinLock
0x140002415  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000241c  nop     dword ptr [rax+rax+00h]
0x140002421  mov     [rdi+278h], al
0x140002427  lea     rax, [rdi+50h]
0x14000242b  mov     rdx, [rax+8]
0x14000242f  cmp     [rdx], rax
0x140002432  jz      short loc_14000243B
0x140002434  mov     ecx, 3
0x140002439  int     29h; Win8: RtlFailFast(ecx)
0x14000243b  mov     [rbx], rax
0x14000243e  mov     rcx, rsi; SpinLock
0x140002441  mov     [rbx+8], rdx
0x140002445  mov     [rdx], rbx
0x140002448  mov     [rax+8], rbx
0x14000244c  inc     dword ptr [rdi+18h]
0x14000244f  mov     dl, [rdi+278h]; NewIrql
0x140002455  call    cs:__imp_KeReleaseSpinLock
0x14000245c  nop     dword ptr [rax+rax+00h]
0x140002461  mov     rcx, cs:WPP_GLOBAL_Control
0x140002468  cmp     rcx, r12
0x14000246b  jz      short loc_140002490
0x14000246d  cmp     byte ptr [rcx+29h], 5
0x140002471  jb      short loc_140002490
0x140002473  mov     rcx, [rcx+18h]
0x140002477  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x14000247e  mov     edx, 0Fh
0x140002483  mov     [rsp+68h+var_48], rbp
0x140002488  mov     r9, rbx
0x14000248b  call    WPP_SF_qq
0x140002490  mov     [r14], rbx
0x140002493  xor     eax, eax
0x140002495  add     rsp, 38h
0x140002499  pop     r14
0x14000249b  pop     r12
0x14000249d  pop     rdi
0x14000249e  pop     rsi
0x14000249f  pop     rbp
0x1400024a0  pop     rbx
0x1400024a1  retn
```
