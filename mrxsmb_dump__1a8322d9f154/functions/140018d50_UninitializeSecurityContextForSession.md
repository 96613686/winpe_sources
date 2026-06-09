# UninitializeSecurityContextForSession

- ea: `0x140018d50`
- end: `0x140018eff`
- name: `UninitializeSecurityContextForSession`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140024010`
- `0x14002ed80`

## callees

- `0x140018d50`
- `0x140019908`
- `0x140046f1c`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140018dde`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140018dde`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140018d82`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140018d82`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018d92`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140018d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ee3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ee3`
- `ksecdd!BCryptDestroyKey` at `0x140018e78`
- `ksecdd!BCryptDestroyKey` at `0x140018ecf`
- `ksecdd!BCryptDestroyKey` at `0x140018e78`
- `ksecdd!BCryptDestroyKey` at `0x140018ecf`

## pseudocode

```c
_BYTE *__fastcall UninitializeSecurityContextForSession(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  KIRQL v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // rcx
  _BYTE *result; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx

  v3 = *(_QWORD *)(a1 + 24);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qiq(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, *(_QWORD *)(a1 + 440), *(_QWORD *)(a1 + 384));
  }
  v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920));
  *(_DWORD *)(v3 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v6 = *(_QWORD *)(a1 + 624);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v6 )
        BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)v6);
      ExFreePoolWithTag((PVOID)v6, 0x2332534Cu);
    }
    *(_QWORD *)(a1 + 624) = 0;
  }
  v7 = *(_QWORD *)(a1 + 632);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v7 )
        BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)v7);
      ExFreePoolWithTag((PVOID)v7, 0x2332534Cu);
    }
    v10 = *(_QWORD *)(a1 + 440);
    v11 = *(_QWORD *)(a1 + 384);
    *(_QWORD *)(a1 + 632) = 0;
    RxCeDeregisterDecryptionKey(v11, v10);
  }
  *(_DWORD *)(v3 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920), v5);
  v8 = 16;
  *(_QWORD *)(a1 + 440) = 0;
  result = (_BYTE *)(a1 + 448);
  do
  {
    *result++ = 0;
    --v8;
  }
  while ( v8 );
  *(_DWORD *)(a1 + 4) &= ~4u;
  *(_BYTE *)(a1 + 464) = 0;
  return result;
}

```

## disassembly

```asm
0x140018d50  push    rbx
0x140018d52  push    rbp
0x140018d53  push    rsi
0x140018d54  push    rdi
0x140018d55  push    r14
0x140018d57  push    r15
0x140018d59  sub     rsp, 38h
0x140018d5d  mov     rdi, [rcx+18h]
0x140018d61  mov     r15, rcx
0x140018d64  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018d6b  lea     rax, WPP_GLOBAL_Control
0x140018d72  cmp     rcx, rax
0x140018d75  jnz     loc_140018E28
0x140018d7b  lea     rcx, [rdi+780h]; SpinLock
0x140018d82  call    cs:__imp_ExAcquireSpinLockExclusive
0x140018d89  nop     dword ptr [rax+rax+00h]
0x140018d8e  movzx   r14d, al
0x140018d92  call    cs:__imp_PsGetCurrentThreadId
0x140018d99  nop     dword ptr [rax+rax+00h]
0x140018d9e  mov     [rdi+930h], eax
0x140018da4  mov     esi, 0FFFFFFFFh
0x140018da9  mov     rbx, [r15+270h]
0x140018db0  test    rbx, rbx
0x140018db3  jnz     loc_140018EBB
0x140018db9  mov     rbx, [r15+278h]
0x140018dc0  test    rbx, rbx
0x140018dc3  jnz     loc_140018E66
0x140018dc9  movzx   edx, r14b; OldIrql
0x140018dcd  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x140018dd7  lea     rcx, [rdi+780h]; SpinLock
0x140018dde  call    cs:__imp_ExReleaseSpinLockExclusive
0x140018de5  nop     dword ptr [rax+rax+00h]
0x140018dea  mov     ecx, 10h
0x140018def  mov     qword ptr [r15+1B8h], 0
0x140018dfa  lea     rax, [r15+1C0h]
0x140018e01  mov     byte ptr [rax], 0
0x140018e04  lea     rax, [rax+1]
0x140018e08  sub     rcx, 1
0x140018e0c  jnz     short loc_140018E01
0x140018e0e  and     dword ptr [r15+4], 0FFFFFFFBh
0x140018e13  mov     [r15+1D0h], cl
0x140018e1a  add     rsp, 38h
0x140018e1e  pop     r15
0x140018e20  pop     r14
0x140018e22  pop     rdi
0x140018e23  pop     rsi
0x140018e24  pop     rbp
0x140018e25  pop     rbx
0x140018e26  retn
0x140018e28  mov     eax, [rcx+2Ch]
0x140018e2b  test    al, 8
0x140018e2d  jz      loc_140018D7B
0x140018e33  cmp     byte ptr [rcx+29h], 2
0x140018e37  jb      loc_140018D7B
0x140018e3d  mov     rax, [r15+180h]
0x140018e44  mov     r9, r15
0x140018e47  mov     rcx, [rcx+18h]
0x140018e4b  mov     [rsp+68h+var_40], rax
0x140018e50  mov     rax, [r15+1B8h]
0x140018e57  mov     [rsp+68h+var_48], rax
0x140018e5c  call    WPP_SF_qiq
0x140018e61  jmp     loc_140018D7B
0x140018e66  lock xadd [rbx+10h], esi
0x140018e6b  cmp     esi, 1
0x140018e6e  jnz     short loc_140018E98
0x140018e70  mov     rcx, [rbx]; hKey
0x140018e73  test    rcx, rcx
0x140018e76  jz      short loc_140018E84
0x140018e78  call    cs:__imp_BCryptDestroyKey
0x140018e7f  nop     dword ptr [rax+rax+00h]
0x140018e84  mov     edx, 2332534Ch; Tag
0x140018e89  mov     rcx, rbx; P
0x140018e8c  call    cs:__imp_ExFreePoolWithTag
0x140018e93  nop     dword ptr [rax+rax+00h]
0x140018e98  mov     rdx, [r15+1B8h]
0x140018e9f  mov     rcx, [r15+180h]
0x140018ea6  mov     qword ptr [r15+278h], 0
0x140018eb1  call    RxCeDeregisterDecryptionKey
0x140018eb6  jmp     loc_140018DC9
0x140018ebb  mov     edx, esi
0x140018ebd  lock xadd [rbx+10h], edx
0x140018ec2  cmp     edx, 1
0x140018ec5  jnz     short loc_140018EEF
0x140018ec7  mov     rcx, [rbx]; hKey
0x140018eca  test    rcx, rcx
0x140018ecd  jz      short loc_140018EDB
0x140018ecf  call    cs:__imp_BCryptDestroyKey
0x140018ed6  nop     dword ptr [rax+rax+00h]
0x140018edb  mov     edx, 2332534Ch; Tag
0x140018ee0  mov     rcx, rbx; P
0x140018ee3  call    cs:__imp_ExFreePoolWithTag
0x140018eea  nop     dword ptr [rax+rax+00h]
0x140018eef  mov     qword ptr [r15+270h], 0
0x140018efa  jmp     loc_140018DB9
```
