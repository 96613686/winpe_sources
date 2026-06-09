# SmbCeReferenceServer

- ea: `0x14000a000`
- end: `0x14000a21b`
- name: `SmbCeReferenceServer`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14004dd50`

## callees

- `0x1400098d0`
- `0x14000a000`
- `0x14000a440`
- `0x14001185c`
- `0x14003e6b4`
- `0x140040d88`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000a110`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a110`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a0c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a0c9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a1c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a1c8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a1bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a1bc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a09d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a09d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a086`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a086`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14000a06f`
- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x14000a202`

## pseudocode

```c
__int64 __fastcall SmbCeReferenceServer(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v3; // edi
  int v4; // ecx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rsi
  KIRQL v9; // r8
  _QWORD *v10; // rdx
  __int64 v11; // rax
  int v12; // ecx
  __int64 Object; // rax
  __int64 v14; // rdi
  __int64 v15; // rax

  v1 = *(_QWORD *)(a1 + 80);
  v3 = 0;
  v4 = *(_DWORD *)(v1 + 12);
  if ( !v4 )
    goto LABEL_2;
  if ( (*(_DWORD *)(a1 + 72) & 0x10) == 0 )
  {
    if ( !*(_BYTE *)(v1 + 640) )
      return (unsigned int)-1073741300;
    v11 = *(_QWORD *)(a1 + 24);
    if ( v11 )
    {
      if ( ((*(_BYTE *)(v11 + 32) - 2) & 0xEF) == 0 )
        return (unsigned int)-1073741300;
    }
  }
  v12 = v4 - 1;
  if ( v12 )
  {
    if ( v12 != 2 )
      return (unsigned int)-1073741300;
    Object = SmbMmAllocateObject(3);
    v14 = Object;
    if ( !Object )
      return (unsigned int)-1073741670;
    *(_DWORD *)(Object + 48) = 2;
    *(_QWORD *)(Object + 56) = a1;
    if ( !(unsigned int)SmbCeIncrementPendingOperations(a1, 1) )
    {
      v8 = v1 + 368;
      s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
      v9 = s_SmbCeDbSpinLockSavedIrql;
      v10 = *(_QWORD **)(v8 + 8);
      if ( *v10 != v8 )
        __fastfail(3u);
      *(_QWORD *)(v14 + 40) = v10;
      *(_QWORD *)(v14 + 32) = v8;
      *v10 = v14 + 32;
      *(_QWORD *)(v8 + 8) = v14 + 32;
      KeReleaseSpinLock(&s_SmbCeDbSpinLock, v9);
      v3 = 259;
      goto LABEL_2;
    }
    v3 = *(_DWORD *)(a1 + 48);
  }
  else
  {
    *(_BYTE *)(v1 + 672) |= 4u;
    _InterlockedExchange((volatile __int32 *)(v1 + 12), 3);
    ExReleaseResourceLite(&s_SmbCeDbResource);
    KeLeaveCriticalRegion();
    v3 = SmbCepInitializeServerTransport(v1);
    if ( !v3 )
    {
      v6 = *(_QWORD *)(a1 + 88);
      if ( v6 && (v15 = *(_QWORD *)(v6 + 96)) != 0 && ((*(_DWORD *)(v15 + 136) & 8) != 0 || MRxSmbUseKernelModeSecurity) )
        v7 = 1;
      else
        LOBYTE(v7) = 0;
      v3 = SmbCeNegotiate(v1, *(_QWORD *)(v1 + 48), v7);
    }
    SmbCeCompleteServerEntryInitialization(v1, v3);
    if ( v3 )
      _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)
                                                      + MRxSmbLegacyPerfCtrs
                                                      + 156));
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
  }
  if ( !v3 || v3 == 259 )
LABEL_2:
    *(_WORD *)(a1 + 60) = 1;
  return v3;
}

```

## disassembly

```asm
0x14000a000  push    rbx
0x14000a002  push    rbp
0x14000a003  push    rsi
0x14000a004  push    rdi
0x14000a005  push    r14
0x14000a007  sub     rsp, 20h
0x14000a00b  mov     rsi, [rcx+50h]
0x14000a00f  mov     rbx, rcx
0x14000a012  xor     edi, edi
0x14000a014  mov     r14d, 1
0x14000a01a  mov     ecx, [rsi+0Ch]
0x14000a01d  test    ecx, ecx
0x14000a01f  jnz     loc_14000A126
0x14000a025  mov     [rbx+3Ch], r14w
0x14000a02a  mov     eax, edi
0x14000a02c  add     rsp, 20h
0x14000a030  pop     r14
0x14000a032  pop     rdi
0x14000a033  pop     rsi
0x14000a034  pop     rbp
0x14000a035  pop     rbx
0x14000a036  retn
0x14000a038  mov     rax, [rbx+58h]
0x14000a03c  test    rax, rax
0x14000a03f  jnz     loc_14000A1EB
0x14000a045  xor     r8b, r8b
0x14000a048  mov     rdx, [rsi+30h]
0x14000a04c  mov     rcx, rsi
0x14000a04f  call    SmbCeNegotiate
0x14000a054  mov     edi, eax
0x14000a056  mov     edx, edi
0x14000a058  mov     rcx, rsi
0x14000a05b  call    SmbCeCompleteServerEntryInitialization
0x14000a060  test    edi, edi
0x14000a062  jz      short loc_14000A086
0x14000a064  mov     eax, gs:1A4h
0x14000a06c  mov     r8d, eax
0x14000a06f  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14000a076  shl     r8, 8
0x14000a07a  mov     rdx, [rax]
0x14000a07d  lock inc dword ptr [r8+rdx+9Ch]
0x14000a086  call    cs:__imp_KeEnterCriticalRegion
0x14000a08d  nop     dword ptr [rax+rax+00h]
0x14000a092  movzx   edx, r14b; Wait
0x14000a096  lea     rcx, s_SmbCeDbResource; Resource
0x14000a09d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000a0a4  nop     dword ptr [rax+rax+00h]
0x14000a0a9  test    edi, edi
0x14000a0ab  jz      loc_14000A025
0x14000a0b1  cmp     edi, 103h
0x14000a0b7  jnz     loc_14000A02A
0x14000a0bd  jmp     loc_14000A025
0x14000a0c2  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000a0c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a0d0  nop     dword ptr [rax+rax+00h]
0x14000a0d5  add     rsi, 170h
0x14000a0dc  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000a0e2  movzx   r8d, al
0x14000a0e6  mov     rdx, [rsi+8]
0x14000a0ea  cmp     [rdx], rsi
0x14000a0ed  jnz     loc_14000A197
0x14000a0f3  lea     rax, [rdi+20h]
0x14000a0f7  mov     [rax+8], rdx
0x14000a0fb  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000a102  mov     [rax], rsi
0x14000a105  mov     [rdx], rax
0x14000a108  movzx   edx, r8b; NewIrql
0x14000a10c  mov     [rsi+8], rax
0x14000a110  call    cs:__imp_KeReleaseSpinLock
0x14000a117  nop     dword ptr [rax+rax+00h]
0x14000a11c  mov     edi, 103h
0x14000a121  jmp     loc_14000A025
0x14000a126  mov     eax, [rbx+48h]
0x14000a129  test    al, 10h
0x14000a12b  jnz     short loc_14000A153
0x14000a12d  cmp     [rsi+280h], dil
0x14000a134  jz      short loc_14000A149
0x14000a136  mov     rax, [rbx+18h]
0x14000a13a  test    rax, rax
0x14000a13d  jz      short loc_14000A153
0x14000a13f  movzx   eax, byte ptr [rax+20h]
0x14000a143  sub     al, 2
0x14000a145  test    al, 0EFh
0x14000a147  jnz     short loc_14000A153
0x14000a149  mov     edi, 0C000020Ch
0x14000a14e  jmp     loc_14000A02A
0x14000a153  sub     ecx, r14d
0x14000a156  jz      short loc_14000A1A6
0x14000a158  cmp     ecx, 2
0x14000a15b  jnz     short loc_14000A149
0x14000a15d  mov     ebp, 3
0x14000a162  mov     ecx, ebp
0x14000a164  call    SmbMmAllocateObject
0x14000a169  mov     rdi, rax
0x14000a16c  test    rax, rax
0x14000a16f  jz      short loc_14000A19C
0x14000a171  mov     edx, r14d
0x14000a174  mov     dword ptr [rax+30h], 2
0x14000a17b  mov     rcx, rbx
0x14000a17e  mov     [rax+38h], rbx
0x14000a182  call    SmbCeIncrementPendingOperations
0x14000a187  test    eax, eax
0x14000a189  jz      loc_14000A0C2
0x14000a18f  mov     edi, [rbx+30h]
0x14000a192  jmp     loc_14000A0A9
0x14000a197  mov     rcx, rbp
0x14000a19a  int     29h; Win8: RtlFailFast(ecx)
0x14000a19c  mov     edi, 0C000009Ah
0x14000a1a1  jmp     loc_14000A02A
0x14000a1a6  or      byte ptr [rsi+2A0h], 4
0x14000a1ad  lea     rcx, s_SmbCeDbResource; Resource
0x14000a1b4  mov     ebp, 3
0x14000a1b9  xchg    ebp, [rsi+0Ch]
0x14000a1bc  call    cs:__imp_ExReleaseResourceLite
0x14000a1c3  nop     dword ptr [rax+rax+00h]
0x14000a1c8  call    cs:__imp_KeLeaveCriticalRegion
0x14000a1cf  nop     dword ptr [rax+rax+00h]
0x14000a1d4  mov     rcx, rsi
0x14000a1d7  call    SmbCepInitializeServerTransport
0x14000a1dc  mov     edi, eax
0x14000a1de  test    eax, eax
0x14000a1e0  jnz     loc_14000A056
0x14000a1e6  jmp     loc_14000A038
0x14000a1eb  mov     rax, [rax+60h]
0x14000a1ef  test    rax, rax
0x14000a1f2  jz      loc_14000A045
0x14000a1f8  mov     eax, [rax+88h]
0x14000a1fe  test    al, 8
0x14000a200  jnz     short loc_14000A212
0x14000a202  mov     rax, cs:__imp_MRxSmbUseKernelModeSecurity
0x14000a209  cmp     byte ptr [rax], 0
0x14000a20c  jz      loc_14000A045
0x14000a212  movzx   r8d, r14b
0x14000a216  jmp     loc_14000A048
```
