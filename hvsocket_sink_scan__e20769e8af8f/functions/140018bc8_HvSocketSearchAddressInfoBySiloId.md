# HvSocketSearchAddressInfoBySiloId

- ea: `0x140018bc8`
- end: `0x140018cea`
- name: `HvSocketSearchAddressInfoBySiloId`
- size: `290`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140004dec`
- `0x14001dfd8`
- `0x14001e5ac`
- `0x14001febc`

## callees

- `0x1400015dc`
- `0x140009df0`
- `0x140018bc8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018c8a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018ca8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018c8a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018ca8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018c7e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018c9c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018c7e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018c9c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018be3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018c37`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018be3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018c37`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018bf3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018c47`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018bf3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018c47`

## pseudocode

```c
__int64 __fastcall HvSocketSearchAddressInfoBySiloId(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v6; // esi
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rdi
  int v11; // eax
  __int128 v12; // xmm1
  __int128 v13; // xmm0

  v6 = -1073741275;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  LOBYTE(v8) = 1;
  while ( 1 )
  {
    v9 = VmbusTlEnumerateObjectTable(v7, a1 + 1312, v8);
    v10 = v9;
    if ( !v9 )
      break;
    if ( *(_QWORD *)(v9 + 136) == *a2 && *(_QWORD *)(v9 + 144) == a2[1] )
    {
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
      v11 = *(_DWORD *)(v10 + 152);
      v12 = *(_OWORD *)(v10 + 120);
      *(_OWORD *)a3 = *(_OWORD *)(v10 + 104);
      v13 = *(_OWORD *)(v10 + 136);
      *(_OWORD *)(a3 + 16) = v12;
      *(_OWORD *)(a3 + 32) = v13;
      *(_DWORD *)(a3 + 48) = v11;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
      KeLeaveCriticalRegion();
      v6 = 0;
      break;
    }
    v8 = 0;
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  if ( v6 < 0 && (unsigned int)dword_140013058 > 2 )
    HvsocketTraceGuidError((const int *)"HvSocketSearchAddressInfoBySiloId", 578, (unsigned int)v6, (__int64)a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140018bc8  push    rbx
0x140018bca  push    rbp
0x140018bcb  push    rsi
0x140018bcc  push    rdi
0x140018bcd  push    r14
0x140018bcf  push    r15
0x140018bd1  sub     rsp, 28h
0x140018bd5  mov     r14, r8
0x140018bd8  mov     rbp, rdx
0x140018bdb  mov     rbx, rcx
0x140018bde  mov     esi, 0C0000225h
0x140018be3  call    cs:__imp_KeEnterCriticalRegion
0x140018bea  nop     dword ptr [rax+rax+00h]
0x140018bef  lea     rcx, [rbx+10h]; FastMutex
0x140018bf3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140018bfa  nop     dword ptr [rax+rax+00h]
0x140018bff  mov     r8b, 1
0x140018c02  jmp     short loc_140018C21
0x140018c04  mov     rax, [rdi+88h]
0x140018c0b  cmp     rax, [rbp+0]
0x140018c0f  jnz     short loc_140018C1E
0x140018c11  mov     rax, [rdi+90h]
0x140018c18  cmp     rax, [rbp+8]
0x140018c1c  jz      short loc_140018C37
0x140018c1e  xor     r8d, r8d
0x140018c21  lea     rdx, [rbx+520h]
0x140018c28  call    VmbusTlEnumerateObjectTable
0x140018c2d  mov     rdi, rax
0x140018c30  test    rax, rax
0x140018c33  jnz     short loc_140018C04
0x140018c35  jmp     short loc_140018C98
0x140018c37  call    cs:__imp_KeEnterCriticalRegion
0x140018c3e  nop     dword ptr [rax+rax+00h]
0x140018c43  lea     rcx, [rdi+10h]; FastMutex
0x140018c47  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140018c4e  nop     dword ptr [rax+rax+00h]
0x140018c53  movups  xmm0, xmmword ptr [rdi+68h]
0x140018c57  mov     eax, [rdi+98h]
0x140018c5d  lea     rcx, [rdi+10h]; FastMutex
0x140018c61  movups  xmm1, xmmword ptr [rdi+78h]
0x140018c65  movups  xmmword ptr [r14], xmm0
0x140018c69  movups  xmm0, xmmword ptr [rdi+88h]
0x140018c70  movups  xmmword ptr [r14+10h], xmm1
0x140018c75  movups  xmmword ptr [r14+20h], xmm0
0x140018c7a  mov     [r14+30h], eax
0x140018c7e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018c85  nop     dword ptr [rax+rax+00h]
0x140018c8a  call    cs:__imp_KeLeaveCriticalRegion
0x140018c91  nop     dword ptr [rax+rax+00h]
0x140018c96  xor     esi, esi
0x140018c98  lea     rcx, [rbx+10h]; FastMutex
0x140018c9c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018ca3  nop     dword ptr [rax+rax+00h]
0x140018ca8  call    cs:__imp_KeLeaveCriticalRegion
0x140018caf  nop     dword ptr [rax+rax+00h]
0x140018cb4  test    esi, esi
0x140018cb6  jns     short loc_140018CDA
0x140018cb8  mov     ecx, cs:dword_140013058
0x140018cbe  cmp     ecx, 2
0x140018cc1  jbe     short loc_140018CDA
0x140018cc3  mov     r9, rbp
0x140018cc6  lea     rcx, aHvsocketsearch_0; "HvSocketSearchAddressInfoBySiloId"
0x140018ccd  mov     r8d, esi
0x140018cd0  mov     edx, 242h
0x140018cd5  call    HvsocketTraceGuidError
0x140018cda  mov     eax, esi
0x140018cdc  add     rsp, 28h
0x140018ce0  pop     r15
0x140018ce2  pop     r14
0x140018ce4  pop     rdi
0x140018ce5  pop     rsi
0x140018ce6  pop     rbp
0x140018ce7  pop     rbx
0x140018ce8  retn
```
