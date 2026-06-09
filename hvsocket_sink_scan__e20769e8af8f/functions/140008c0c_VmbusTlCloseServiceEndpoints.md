# VmbusTlCloseServiceEndpoints

- ea: `0x140008c0c`
- end: `0x140008e76`
- name: `VmbusTlCloseServiceEndpoints`
- size: `618`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006de8`
- `0x1400222b0`
- `0x140022634`

## callees

- `0x140001e90`
- `0x140001fa0`
- `0x1400023b0`
- `0x140008c0c`
- `0x140009fa4`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140008c8e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140008c8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008dd0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008dd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008d4d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008dec`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008d4d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008dec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008d69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008e08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008e58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008d69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008e08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008e58`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008d5d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008dfc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008e4c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008d5d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008dfc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008e4c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008c23`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008d11`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008db0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008c23`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008d11`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008db0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008c36`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008d21`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008dc0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008c36`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008d21`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008dc0`

## string_xrefs

- `0x140008c7d`: `VmbusTlCloseServiceEndpoints: Unable to cancel listener.`

## pseudocode

```c
void __fastcall VmbusTlCloseServiceEndpoints(__int64 a1, char a2)
{
  struct _FAST_MUTEX *v4; // r13
  BOOLEAN i; // dl
  _QWORD *v6; // rax
  __int64 v7; // rax
  _QWORD *j; // rbx
  _QWORD *v9; // rcx
  void (*v10)(void); // rax
  _QWORD *v11; // r14
  __int64 v12; // r15
  KIRQL v13; // bl
  _QWORD *v14; // r14
  __int64 v15; // rbp
  KIRQL v16; // bl
  int v17; // [rsp+70h] [rbp+8h] BYREF

  KeEnterCriticalRegion();
  v4 = (struct _FAST_MUTEX *)(a1 + 16);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  for ( i = 1; ; i = 0 )
  {
    v6 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(a1 + 168), i);
    if ( !v6 )
      break;
    v7 = v6[2];
    if ( !v7 )
      break;
    if ( !a2 || !*(_BYTE *)(v7 + 185) )
    {
      if ( *(_QWORD *)(v7 + 336) )
      {
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceMessage("VmbusTlCloseServiceEndpoints: Unable to cancel listener.", a1 + 112);
      }
      else
      {
        *(_BYTE *)(v7 + 424) = 1;
      }
    }
  }
  for ( j = *(_QWORD **)(a1 + 312); j != (_QWORD *)(a1 + 312); j = (_QWORD *)*j )
  {
    v9 = j - 15;
    if ( a2 && *((_BYTE *)v9 + 185) )
    {
      v10 = *(void (**)(void))(v9[92] + 184LL);
      if ( v10 )
        v10();
    }
    else
    {
      VmbusTlCommonCancelConnection(v9);
    }
  }
  v11 = (_QWORD *)(a1 + 272);
  while ( (_QWORD *)*v11 != v11 )
  {
    v12 = *v11 - 120LL;
    if ( !a2 || !*(_BYTE *)(v12 + 185) )
    {
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v12 + 16));
      v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v12 + 72));
      HvSocketUnPendConnectionLocked(v12);
      KeReleaseSpinLock((PKSPIN_LOCK)(v12 + 72), v13);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v12 + 16));
      KeLeaveCriticalRegion();
      VmbusTlCommonCancelConnection((PVOID)v12);
    }
  }
  v14 = (_QWORD *)(a1 + 288);
  while ( (_QWORD *)*v14 != v14 )
  {
    v15 = *v14 - 120LL;
    if ( !a2 || !*(_BYTE *)(v15 + 185) )
    {
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v15 + 16));
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v15 + 72));
      HvSocketUnPendConnectionLocked(v15);
      KeReleaseSpinLock((PKSPIN_LOCK)(v15 + 72), v16);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v15 + 16));
      KeLeaveCriticalRegion();
      v17 = -1073741258;
      VmbusTlConnectComplete((char *)v15, &v17);
      if ( v17 >= 0 )
        VmbusTlCommonCancelConnection((PVOID)v15);
    }
  }
  ExReleaseFastMutexUnsafe(v4);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140008c0c  push    rbx
0x140008c0e  push    rbp
0x140008c0f  push    rsi
0x140008c10  push    rdi
0x140008c11  push    r12
0x140008c13  push    r13
0x140008c15  push    r14
0x140008c17  push    r15
0x140008c19  sub     rsp, 28h
0x140008c1d  mov     r12b, dl
0x140008c20  mov     rbp, rcx
0x140008c23  call    cs:__imp_KeEnterCriticalRegion
0x140008c2a  nop     dword ptr [rax+rax+00h]
0x140008c2f  lea     r13, [rbp+10h]
0x140008c33  mov     rcx, r13; FastMutex
0x140008c36  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140008c3d  nop     dword ptr [rax+rax+00h]
0x140008c42  mov     dl, 1
0x140008c44  lea     rbx, [rbp+0A8h]
0x140008c4b  jmp     short loc_140008C8B
0x140008c4d  test    r12b, r12b
0x140008c50  jz      short loc_140008C5B
0x140008c52  cmp     byte ptr [rax+0B9h], 0
0x140008c59  jnz     short loc_140008C89
0x140008c5b  cmp     qword ptr [rax+150h], 0
0x140008c63  jnz     short loc_140008C6E
0x140008c65  mov     byte ptr [rax+1A8h], 1
0x140008c6c  jmp     short loc_140008C89
0x140008c6e  mov     eax, cs:dword_140013058
0x140008c74  cmp     eax, 4
0x140008c77  jbe     short loc_140008C89
0x140008c79  lea     rdx, [rbp+70h]
0x140008c7d  lea     rcx, aVmbustlclosese; "VmbusTlCloseServiceEndpoints: Unable to"...
0x140008c84  call    HvsocketTraceMessage
0x140008c89  xor     edx, edx; Restart
0x140008c8b  mov     rcx, rbx; Table
0x140008c8e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140008c95  nop     dword ptr [rax+rax+00h]
0x140008c9a  test    rax, rax
0x140008c9d  jz      short loc_140008CA8
0x140008c9f  mov     rax, [rax+10h]
0x140008ca3  test    rax, rax
0x140008ca6  jnz     short loc_140008C4D
0x140008ca8  lea     rdi, [rbp+138h]
0x140008caf  mov     rbx, [rdi]
0x140008cb2  jmp     short loc_140008CED
0x140008cb4  lea     rcx, [rbx-78h]
0x140008cb8  test    r12b, r12b
0x140008cbb  jz      short loc_140008CE0
0x140008cbd  cmp     byte ptr [rcx+0B9h], 0
0x140008cc4  jz      short loc_140008CE0
0x140008cc6  mov     rax, [rcx+2E0h]
0x140008ccd  mov     rax, [rax+0B8h]
0x140008cd4  test    rax, rax
0x140008cd7  jz      short loc_140008CEA
0x140008cd9  call    _guard_dispatch_icall
0x140008cde  jmp     short loc_140008CEA
0x140008ce0  mov     r8b, 1
0x140008ce3  xor     edx, edx
0x140008ce5  call    VmbusTlCommonCancelConnection
0x140008cea  mov     rbx, [rbx]
0x140008ced  cmp     rbx, rdi
0x140008cf0  jnz     short loc_140008CB4
0x140008cf2  lea     r14, [rbp+110h]
0x140008cf9  jmp     loc_140008D82
0x140008cfe  lea     r15, [rax-78h]
0x140008d02  test    r12b, r12b
0x140008d05  jz      short loc_140008D11
0x140008d07  cmp     byte ptr [r15+0B9h], 0
0x140008d0f  jnz     short loc_140008D82
0x140008d11  call    cs:__imp_KeEnterCriticalRegion
0x140008d18  nop     dword ptr [rax+rax+00h]
0x140008d1d  lea     rcx, [r15+10h]; FastMutex
0x140008d21  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140008d28  nop     dword ptr [rax+rax+00h]
0x140008d2d  lea     rcx, [r15+48h]; SpinLock
0x140008d31  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008d38  nop     dword ptr [rax+rax+00h]
0x140008d3d  mov     rcx, r15
0x140008d40  mov     bl, al
0x140008d42  call    HvSocketUnPendConnectionLocked
0x140008d47  mov     dl, bl; NewIrql
0x140008d49  lea     rcx, [r15+48h]; SpinLock
0x140008d4d  call    cs:__imp_KeReleaseSpinLock
0x140008d54  nop     dword ptr [rax+rax+00h]
0x140008d59  lea     rcx, [r15+10h]; FastMutex
0x140008d5d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008d64  nop     dword ptr [rax+rax+00h]
0x140008d69  call    cs:__imp_KeLeaveCriticalRegion
0x140008d70  nop     dword ptr [rax+rax+00h]
0x140008d75  mov     r8b, 1
0x140008d78  xor     edx, edx
0x140008d7a  mov     rcx, r15
0x140008d7d  call    VmbusTlCommonCancelConnection
0x140008d82  mov     rax, [r14]
0x140008d85  cmp     rax, r14
0x140008d88  jnz     loc_140008CFE
0x140008d8e  lea     r14, [rbp+120h]
0x140008d95  jmp     loc_140008E3D
0x140008d9a  lea     rbp, [rax-78h]
0x140008d9e  test    r12b, r12b
0x140008da1  jz      short loc_140008DB0
0x140008da3  cmp     byte ptr [rbp+0B9h], 0
0x140008daa  jnz     loc_140008E3D
0x140008db0  call    cs:__imp_KeEnterCriticalRegion
0x140008db7  nop     dword ptr [rax+rax+00h]
0x140008dbc  lea     rcx, [rbp+10h]; FastMutex
0x140008dc0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140008dc7  nop     dword ptr [rax+rax+00h]
0x140008dcc  lea     rcx, [rbp+48h]; SpinLock
0x140008dd0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008dd7  nop     dword ptr [rax+rax+00h]
0x140008ddc  mov     rcx, rbp
0x140008ddf  mov     bl, al
0x140008de1  call    HvSocketUnPendConnectionLocked
0x140008de6  mov     dl, bl; NewIrql
0x140008de8  lea     rcx, [rbp+48h]; SpinLock
0x140008dec  call    cs:__imp_KeReleaseSpinLock
0x140008df3  nop     dword ptr [rax+rax+00h]
0x140008df8  lea     rcx, [rbp+10h]; FastMutex
0x140008dfc  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008e03  nop     dword ptr [rax+rax+00h]
0x140008e08  call    cs:__imp_KeLeaveCriticalRegion
0x140008e0f  nop     dword ptr [rax+rax+00h]
0x140008e14  lea     rdx, [rsp+68h+arg_0]
0x140008e19  mov     [rsp+68h+arg_0], 0C0000236h
0x140008e21  mov     rcx, rbp; P
0x140008e24  call    VmbusTlConnectComplete
0x140008e29  cmp     [rsp+68h+arg_0], 0
0x140008e2e  jl      short loc_140008E3D
0x140008e30  mov     r8b, 1
0x140008e33  xor     edx, edx
0x140008e35  mov     rcx, rbp
0x140008e38  call    VmbusTlCommonCancelConnection
0x140008e3d  mov     rax, [r14]
0x140008e40  cmp     rax, r14
0x140008e43  jnz     loc_140008D9A
0x140008e49  mov     rcx, r13; FastMutex
0x140008e4c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008e53  nop     dword ptr [rax+rax+00h]
0x140008e58  call    cs:__imp_KeLeaveCriticalRegion
0x140008e5f  nop     dword ptr [rax+rax+00h]
0x140008e64  add     rsp, 28h
0x140008e68  pop     r15
0x140008e6a  pop     r14
0x140008e6c  pop     r13
0x140008e6e  pop     r12
0x140008e70  pop     rdi
0x140008e71  pop     rsi
0x140008e72  pop     rbp
0x140008e73  pop     rbx
0x140008e74  retn
```
