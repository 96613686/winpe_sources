# QuicLibraryGenerateStatelessResetToken

- ea: `0x140028658`
- end: `0x14002870e`
- name: `QuicLibraryGenerateStatelessResetToken`
- size: `182`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000577c`
- `0x140019040`
- `0x1400401b4`

## callees

- `0x140028658`
- `0x1400346f8`
- `0x14003c8e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002867c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002867c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028691`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028691`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400286c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400286c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400286d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400286d4`

## pseudocode

```c
__int64 __fastcall QuicLibraryGenerateStatelessResetToken(__int64 a1, __int64 a2, _OWORD *a3)
{
  int v5; // eax
  __int64 v6; // rcx
  int v7; // edi
  UCHAR pbOutput[32]; // [rsp+30h] [rbp-48h] BYREF

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 40, 0);
  v5 = CxPlatHashCompute(*(BCRYPT_HASH_HANDLE *)(a1 + 32), pbOutput);
  v6 = a1 + 40;
  v7 = v5;
  ExReleasePushLockExclusiveEx(v6, 0);
  KeLeaveCriticalRegion();
  if ( v7 >= 0 )
    *a3 = *(_OWORD *)pbOutput;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140028658  mov     [rsp+arg_18], rbx
0x14002865d  push    rbp
0x14002865e  push    rsi
0x14002865f  push    rdi
0x140028660  sub     rsp, 60h
0x140028664  mov     rax, cs:__security_cookie
0x14002866b  xor     rax, rsp
0x14002866e  mov     [rsp+78h+var_28], rax
0x140028673  mov     rbp, r8
0x140028676  mov     rsi, rdx
0x140028679  mov     rdi, rcx
0x14002867c  call    cs:__imp_KeEnterCriticalRegion
0x140028683  nop     dword ptr [rax+rax+00h]
0x140028688  lea     rbx, [rdi+28h]
0x14002868c  xor     edx, edx
0x14002868e  mov     rcx, rbx
0x140028691  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140028698  nop     dword ptr [rax+rax+00h]
0x14002869d  movzx   r8d, cs:byte_14005C562
0x1400286a5  lea     rax, [rsp+78h+var_48]
0x1400286aa  mov     rcx, [rdi+20h]; hHash
0x1400286ae  mov     r9d, 20h ; ' '
0x1400286b4  mov     rdx, rsi
0x1400286b7  mov     [rsp+78h+pbOutput], rax; pbOutput
0x1400286bc  call    CxPlatHashCompute
0x1400286c1  xor     edx, edx
0x1400286c3  mov     rcx, rbx
0x1400286c6  mov     edi, eax
0x1400286c8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400286cf  nop     dword ptr [rax+rax+00h]
0x1400286d4  call    cs:__imp_KeLeaveCriticalRegion
0x1400286db  nop     dword ptr [rax+rax+00h]
0x1400286e0  test    edi, edi
0x1400286e2  js      short loc_1400286EE
0x1400286e4  movups  xmm0, xmmword ptr [rsp+78h+var_48]
0x1400286e9  movdqu  xmmword ptr [rbp+0], xmm0
0x1400286ee  mov     eax, edi
0x1400286f0  mov     rcx, [rsp+78h+var_28]
0x1400286f5  xor     rcx, rsp; StackCookie
0x1400286f8  call    __security_check_cookie
0x1400286fd  mov     rbx, [rsp+78h+arg_18]
0x140028705  add     rsp, 60h
0x140028709  pop     rdi
0x14002870a  pop     rsi
0x14002870b  pop     rbp
0x14002870c  retn
```
