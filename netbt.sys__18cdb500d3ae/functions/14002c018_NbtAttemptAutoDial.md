# NbtAttemptAutoDial

- ea: `0x14002c018`
- end: `0x14002c211`
- name: `NbtAttemptAutoDial`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002410c`

## callees

- `0x140006900`
- `0x14000dc40`
- `0x14001db4c`
- `0x14002c018`
- `0x140030f40`
- `0x140030f80`
- `0x140043b4c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c11e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c1d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c11e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c1d4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c13f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c1ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c13f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c1ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c1fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c1fd`
- `ntoskrnl!ExAllocatePool2` at `0x14002c0fc`
- `ntoskrnl!ExAllocatePool2` at `0x14002c0fc`

## pseudocode

```c
char __fastcall NbtAttemptAutoDial(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v9; // rax
  __int128 v10; // xmm0
  char *Pool2; // rdi
  _OWORD *v12; // r15
  KIRQL v13; // al
  char v14; // si
  KIRQL v15; // al
  _OWORD v16[3]; // [rsp+40h] [rbp-49h] BYREF
  __int128 v17; // [rsp+70h] [rbp-19h] BYREF
  __int128 v18; // [rsp+80h] [rbp-9h]

  v17 = 0;
  v18 = 0;
  memset(v16, 0, 44);
  if ( *(_BYTE *)(a1 + 266) )
    return 0;
  if ( *(_UNKNOWN **)(*(_QWORD *)(a4 + 184) + 56LL) == &NbtpConnectCompletionRoutine )
  {
    v9 = *(_QWORD *)(a3 + 40);
    v10 = *(_OWORD *)(v9 + 36);
    v16[1] = *(_OWORD *)(v9 + 24);
    *(_OWORD *)((char *)&v16[1] + 12) = v10;
  }
  else if ( (unsigned int)GetNetBiosNameFromTransportAddress(*(_QWORD *)(a3 + 40), *(unsigned int *)(a3 + 32), v16) )
  {
    return 0;
  }
  if ( !(unsigned __int8)NBT_REFERENCE_DEVICE(*(_QWORD *)(a1 + 32), 13, 0) )
    return 0;
  Pool2 = (char *)ExAllocatePool2(64, 1028, 1098146382);
  if ( !Pool2 )
    return 0;
  v12 = *(_OWORD **)((char *)&v16[1] + 12);
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 248));
  *(_BYTE *)(a1 + 265) = 1;
  *(_OWORD *)(a1 + 52) = *v12;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 248), v13);
  *(_DWORD *)Pool2 = 2;
  *(_OWORD *)(Pool2 + 4) = *v12;
  if ( (xmmword_140038420 & 0x80u) != 0LL )
    WPP_SF_s(1031, 13, WPP_39f1e1c971f83cf429ccc88df75b8d05_Traceguids, v12);
  *(_QWORD *)&v17 = a1;
  *((_QWORD *)&v17 + 1) = a2;
  *(_QWORD *)&v18 = a3;
  *((_QWORD *)&v18 + 1) = a4;
  v14 = ((__int64 (__fastcall *)(__int64, char *, _QWORD, __int64 (__fastcall *)(unsigned __int8, __int64 *, int), __int16, __int128 *))qword_1400391E8)(
          1315075104,
          Pool2,
          0,
          NbtRetryPreConnect,
          4,
          &v17);
  if ( !v14 )
  {
    NBT_DEREFERENCE_DEVICE(*(_QWORD *)(a1 + 32), 13);
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 248));
    *(_BYTE *)(a1 + 265) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 248), v15);
  }
  ExFreePoolWithTag(Pool2, 0);
  return v14;
}

```

## disassembly

```asm
0x14002c018  mov     [rsp-8+arg_8], rbx
0x14002c01d  push    rbp
0x14002c01e  push    rsi
0x14002c01f  push    rdi
0x14002c020  push    r12
0x14002c022  push    r13
0x14002c024  push    r14
0x14002c026  push    r15
0x14002c028  lea     rbp, [rsp-17h]
0x14002c02d  sub     rsp, 0A0h
0x14002c034  mov     rax, cs:__security_cookie
0x14002c03b  xor     rax, rsp
0x14002c03e  mov     [rbp+47h+var_40], rax
0x14002c042  xorps   xmm1, xmm1
0x14002c045  xorps   xmm0, xmm0
0x14002c048  xor     eax, eax
0x14002c04a  mov     r13, r9
0x14002c04d  mov     rsi, r8
0x14002c050  mov     r12, rdx
0x14002c053  mov     rbx, rcx
0x14002c056  movups  xmmword ptr [rbp+47h+var_80], xmm1
0x14002c05a  movups  xmmword ptr [rbp+47h+var_80+0Ch], xmm1
0x14002c05e  movups  [rbp+47h+var_60], xmm0
0x14002c062  movups  [rbp+47h+var_50], xmm0
0x14002c066  movups  [rbp+47h+var_90], xmm1
0x14002c06a  cmp     [rcx+10Ah], al
0x14002c070  jnz     short loc_14002C09A
0x14002c072  mov     rax, [r9+0B8h]
0x14002c079  lea     rcx, NbtpConnectCompletionRoutine
0x14002c080  cmp     [rax+38h], rcx
0x14002c084  jz      short loc_14002C0C4
0x14002c086  mov     rcx, [rsi+28h]
0x14002c08a  lea     r8, [rbp+47h+var_90]
0x14002c08e  mov     edx, [rsi+20h]
0x14002c091  call    GetNetBiosNameFromTransportAddress
0x14002c096  test    eax, eax
0x14002c098  jz      short loc_14002C0D8
0x14002c09a  xor     al, al
0x14002c09c  mov     rcx, [rbp+47h+var_40]
0x14002c0a0  xor     rcx, rsp; StackCookie
0x14002c0a3  call    __security_check_cookie
0x14002c0a8  mov     rbx, [rsp+0D0h+arg_8]
0x14002c0b0  add     rsp, 0A0h
0x14002c0b7  pop     r15
0x14002c0b9  pop     r14
0x14002c0bb  pop     r13
0x14002c0bd  pop     r12
0x14002c0bf  pop     rdi
0x14002c0c0  pop     rsi
0x14002c0c1  pop     rbp
0x14002c0c2  retn
0x14002c0c4  mov     rax, [r8+28h]
0x14002c0c8  movups  xmm1, xmmword ptr [rax+18h]
0x14002c0cc  movups  xmm0, xmmword ptr [rax+24h]
0x14002c0d0  movups  xmmword ptr [rbp+47h+var_80], xmm1
0x14002c0d4  movups  xmmword ptr [rbp+47h+var_80+0Ch], xmm0
0x14002c0d8  mov     rcx, [rbx+20h]
0x14002c0dc  xor     r8d, r8d
0x14002c0df  lea     edx, [r8+0Dh]
0x14002c0e3  call    NBT_REFERENCE_DEVICE
0x14002c0e8  test    al, al
0x14002c0ea  jz      short loc_14002C09A
0x14002c0ec  mov     edx, 404h
0x14002c0f1  mov     ecx, 40h ; '@'
0x14002c0f6  mov     r8d, 4174624Eh
0x14002c0fc  call    cs:__imp_ExAllocatePool2
0x14002c103  nop     dword ptr [rax+rax+00h]
0x14002c108  mov     rdi, rax
0x14002c10b  test    rax, rax
0x14002c10e  jz      short loc_14002C09A
0x14002c110  mov     r15, qword ptr [rbp+47h+var_80+0Ch]
0x14002c114  lea     r14, [rbx+0F8h]
0x14002c11b  mov     rcx, r14; SpinLock
0x14002c11e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c125  nop     dword ptr [rax+rax+00h]
0x14002c12a  mov     byte ptr [rbx+109h], 1
0x14002c131  mov     rcx, r14; SpinLock
0x14002c134  movups  xmm0, xmmword ptr [r15]
0x14002c138  mov     dl, al; NewIrql
0x14002c13a  movdqu  xmmword ptr [rbx+34h], xmm0
0x14002c13f  call    cs:__imp_KeReleaseSpinLock
0x14002c146  nop     dword ptr [rax+rax+00h]
0x14002c14b  mov     dword ptr [rdi], 2
0x14002c151  movups  xmm0, xmmword ptr [r15]
0x14002c155  movdqu  xmmword ptr [rdi+4], xmm0
0x14002c15a  cmp     byte ptr cs:xmmword_140038420, 0
0x14002c161  jge     short loc_14002C17C
0x14002c163  mov     edx, 0Dh
0x14002c168  lea     r8, WPP_39f1e1c971f83cf429ccc88df75b8d05_Traceguids
0x14002c16f  mov     ecx, 407h
0x14002c174  mov     r9, r15
0x14002c177  call    WPP_SF_s
0x14002c17c  mov     rax, cs:qword_1400391E8
0x14002c183  lea     rcx, [rbp+47h+var_60]
0x14002c187  mov     [rsp+0D0h+var_A8], rcx
0x14002c18c  lea     r9, NbtRetryPreConnect
0x14002c193  mov     ecx, 4E627420h
0x14002c198  mov     qword ptr [rbp+47h+var_60], rbx
0x14002c19c  xor     r8d, r8d
0x14002c19f  mov     qword ptr [rbp+47h+var_60+8], r12
0x14002c1a3  mov     rdx, rdi
0x14002c1a6  mov     qword ptr [rbp+47h+var_50], rsi
0x14002c1aa  mov     qword ptr [rbp+47h+var_50+8], r13
0x14002c1ae  mov     [rsp+0D0h+var_B0], 4
0x14002c1b5  call    _guard_dispatch_icall
0x14002c1ba  mov     sil, al
0x14002c1bd  test    al, al
0x14002c1bf  jnz     short loc_14002C1F8
0x14002c1c1  mov     rcx, [rbx+20h]
0x14002c1c5  xor     r8d, r8d
0x14002c1c8  lea     edx, [r8+0Dh]
0x14002c1cc  call    NBT_DEREFERENCE_DEVICE
0x14002c1d1  mov     rcx, r14; SpinLock
0x14002c1d4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c1db  nop     dword ptr [rax+rax+00h]
0x14002c1e0  mov     rcx, r14; SpinLock
0x14002c1e3  mov     [rbx+109h], sil
0x14002c1ea  mov     dl, al; NewIrql
0x14002c1ec  call    cs:__imp_KeReleaseSpinLock
0x14002c1f3  nop     dword ptr [rax+rax+00h]
0x14002c1f8  xor     edx, edx; Tag
0x14002c1fa  mov     rcx, rdi; P
0x14002c1fd  call    cs:__imp_ExFreePoolWithTag
0x14002c204  nop     dword ptr [rax+rax+00h]
0x14002c209  mov     al, sil
0x14002c20c  jmp     loc_14002C09C
```
