# CdpCompleteServerConnection

- ea: `0x14000b3a0`
- end: `0x14000b4c3`
- name: `CdpCompleteServerConnection`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000b020`
- `0x14000b3a0`
- `0x14000bd90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b46a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b46a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b3fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b3fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b459`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b459`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b3eb`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b3eb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b410`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b410`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b448`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b448`

## pseudocode

```c
__int64 __fastcall CdpCompleteServerConnection(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rbp
  __int64 v6; // rdi
  char v7; // r14
  _QWORD *v8; // rdx

  v3 = (_QWORD *)*a3;
  v6 = *(_QWORD *)(*a3 + 24LL);
  _InterlockedIncrement64((volatile signed __int64 *)(v6 + 24));
  if ( *(int *)(a2 + 48) < 0 )
  {
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL) + 24LL) = 0;
    CdpFreeConnection(v3);
  }
  else
  {
    v7 = 0;
    if ( *(_QWORD *)(a2 + 56) == 24 )
    {
      v3[5] = a3[1];
      v3[6] = a3[2];
      v3[7] = a3[3];
    }
    if ( KeGetCurrentIrql() <= 1u )
    {
      KeEnterCriticalRegion();
      v7 = 1;
    }
    ExAcquirePushLockExclusiveEx(v6 + 40, 0);
    v8 = *(_QWORD **)(v6 + 208);
    if ( *v8 != v6 + 200 )
      __fastfail(3u);
    v3[1] = v6 + 200;
    v3[2] = v8;
    *v8 = v3 + 1;
    *(_QWORD *)(v6 + 208) = v3 + 1;
    ExReleasePushLockExclusiveEx(v6 + 40, 0);
    if ( v7 )
      KeLeaveCriticalRegion();
  }
  ExFreePoolWithTag(a3, 0);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  CdDereferenceServer((char *)v6);
  return 0;
}

```

## disassembly

```asm
0x14000b3a0  push    rbx
0x14000b3a2  push    rbp
0x14000b3a3  push    rsi
0x14000b3a4  push    rdi
0x14000b3a5  push    r14
0x14000b3a7  push    r15
0x14000b3a9  sub     rsp, 28h
0x14000b3ad  mov     rbp, [r8]
0x14000b3b0  mov     rsi, r8
0x14000b3b3  mov     rbx, rdx
0x14000b3b6  mov     rdi, [rbp+18h]
0x14000b3ba  lock inc qword ptr [rdi+18h]
0x14000b3bf  cmp     dword ptr [rdx+30h], 0
0x14000b3c3  jl      loc_14000B49F
0x14000b3c9  xor     r14b, r14b
0x14000b3cc  cmp     qword ptr [rdx+38h], 18h
0x14000b3d1  jnz     short loc_14000B3EB
0x14000b3d3  mov     rax, [r8+8]
0x14000b3d7  mov     [rbp+28h], rax
0x14000b3db  mov     rax, [r8+10h]
0x14000b3df  mov     [rbp+30h], rax
0x14000b3e3  mov     rax, [r8+18h]
0x14000b3e7  mov     [rbp+38h], rax
0x14000b3eb  call    cs:__imp_KeGetCurrentIrql
0x14000b3f2  nop     dword ptr [rax+rax+00h]
0x14000b3f7  cmp     al, 1
0x14000b3f9  ja      short loc_14000B40A
0x14000b3fb  call    cs:__imp_KeEnterCriticalRegion
0x14000b402  nop     dword ptr [rax+rax+00h]
0x14000b407  mov     r14b, 1
0x14000b40a  xor     edx, edx
0x14000b40c  lea     rcx, [rdi+28h]
0x14000b410  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b417  nop     dword ptr [rax+rax+00h]
0x14000b41c  lea     rcx, [rdi+0C8h]
0x14000b423  mov     rdx, [rcx+8]
0x14000b427  cmp     [rdx], rcx
0x14000b42a  jnz     loc_14000B4BC
0x14000b430  lea     rax, [rbp+8]
0x14000b434  mov     [rax], rcx
0x14000b437  mov     [rax+8], rdx
0x14000b43b  mov     [rdx], rax
0x14000b43e  xor     edx, edx
0x14000b440  mov     [rcx+8], rax
0x14000b444  lea     rcx, [rdi+28h]
0x14000b448  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b44f  nop     dword ptr [rax+rax+00h]
0x14000b454  test    r14b, r14b
0x14000b457  jz      short loc_14000B465
0x14000b459  call    cs:__imp_KeLeaveCriticalRegion
0x14000b460  nop     dword ptr [rax+rax+00h]
0x14000b465  xor     edx, edx; Tag
0x14000b467  mov     rcx, rsi; P
0x14000b46a  call    cs:__imp_ExFreePoolWithTag
0x14000b471  nop     dword ptr [rax+rax+00h]
0x14000b476  cmp     byte ptr [rbx+41h], 0
0x14000b47a  jz      short loc_14000B487
0x14000b47c  mov     rax, [rbx+0B8h]
0x14000b483  or      byte ptr [rax+3], 1
0x14000b487  mov     rcx, rdi; P
0x14000b48a  call    CdDereferenceServer
0x14000b48f  xor     eax, eax
0x14000b491  add     rsp, 28h
0x14000b495  pop     r15
0x14000b497  pop     r14
0x14000b499  pop     rdi
0x14000b49a  pop     rsi
0x14000b49b  pop     rbp
0x14000b49c  pop     rbx
0x14000b49d  retn
0x14000b49f  mov     rax, [rdx+0B8h]
0x14000b4a6  mov     rcx, rbp; P
0x14000b4a9  mov     rdx, [rax+30h]
0x14000b4ad  mov     qword ptr [rdx+18h], 0
0x14000b4b5  call    CdpFreeConnection
0x14000b4ba  jmp     short loc_14000B465
0x14000b4bc  mov     ecx, 3
0x14000b4c1  int     29h; Win8: RtlFailFast(ecx)
```
