# QuicBindingCreateConnection

- ea: `0x1400038cc`
- end: `0x140003b03`
- name: `QuicBindingCreateConnection`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002924c`

## callees

- `0x1400038cc`
- `0x140003bb0`
- `0x140003c14`
- `0x140007b30`
- `0x14000c4b8`
- `0x14000c5b0`
- `0x1400200d8`
- `0x140026a88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400039aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039aa`

## pseudocode

```c
__int64 __fastcall QuicBindingCreateConnection(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rdx
  const char *v5; // r8
  int v7; // r8d
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  _DWORD *v15; // rax
  __int64 v16; // [rsp+68h] [rbp+38h] BYREF
  __int64 v17; // [rsp+70h] [rbp+40h] BYREF

  v3 = a1;
  v4 = *((_QWORD *)qword_14005C5B8 + 6)
     + ((__int64)(*(unsigned __int16 *)(a2 + 26) % (unsigned int)**((unsigned __int16 **)qword_14005C5B8 + 6)) << 8);
  if ( *(_DWORD *)(v4 + 148) > (unsigned int)dword_14005C500 )
  {
    v5 = "Stateless worker overloaded";
LABEL_3:
    QuicPacketLogDrop(a1, a2, v5);
    return 0;
  }
  v16 = 0;
  v7 = v4 + 64;
  v8 = *(_QWORD *)(v4 + 112);
  v17 = 0;
  v9 = QuicConnAlloc((_DWORD)qword_14005C5B8, v8, v7, a2, (__int64)&v16);
  a1 = v3;
  if ( v9 < 0 )
  {
    v5 = "Failed to initialize new connection";
    goto LABEL_3;
  }
  v10 = *(_QWORD *)(v16 + 1280);
  _InterlockedAdd((volatile signed __int32 *)(v16 + 240), 1u);
  if ( !(unsigned __int8)QuicLibraryTryAddRefBinding(v3) )
  {
    QuicPacketLogDrop(v3, a2, "Clean up in progress");
    *(_QWORD *)(v16 + 1280) = 0;
    ExFreePoolWithTag((PVOID)(v10 - 24), 0x44306351u);
    v11 = v16;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 240), 0xFFFFFFFF) == 1 )
      QuicWorkerQueueConnection(*(_QWORD *)(v11 + 64), v11);
    v12 = v16;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 240), 0xFFFFFFFF) == 1 )
      QuicConnFree(v12);
    return v17;
  }
  *(_QWORD *)(v16 + 360) = v3;
  if ( !(unsigned __int8)QuicLookupAddRemoteHash(
                           (int)v3 + 64,
                           v16,
                           (unsigned int)*(_QWORD *)(a2 + 8) + 8,
                           *(_BYTE *)(a2 + 87),
                           *(void **)(a2 + 72),
                           (__int64)&v17) )
  {
    if ( !v17 )
      QuicPacketLogDrop(v3, a2, "Failed to insert remote hash");
    v13 = v16;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 240), 0xFFFFFFFF) == 1 )
      QuicWorkerQueueConnection(*(_QWORD *)(v13 + 64), v13);
    if ( !_InterlockedCompareExchange16((volatile signed __int16 *)(v16 + 1584), 1, 0) )
    {
      v14 = v16 + 1472;
      *(_BYTE *)(v16 + 1492) = 0;
      *(_DWORD *)(v14 + 16) = 0;
      v15 = (_DWORD *)(v16 + 1528);
      *(_QWORD *)(v14 + 24) = v16 + 1528;
      *v15 = 1;
      *(_DWORD *)(*(_QWORD *)(v14 + 24) + 24LL) = 32769;
      *(_QWORD *)(*(_QWORD *)(v14 + 24) + 32LL) = -1071382525;
      *(_BYTE *)(*(_QWORD *)(v14 + 24) + 28LL) &= ~1u;
      *(_BYTE *)(*(_QWORD *)(v14 + 24) + 28LL) |= 2u;
      QuicConnQueueOper(v16, v14);
    }
    return v17;
  }
  QuicWorkerQueueConnection(*(_QWORD *)(v16 + 64), v16);
  return v16;
}

```

## disassembly

```asm
0x1400038cc  mov     [rsp-28h+arg_0], rbx
0x1400038d1  push    rbp
0x1400038d2  push    rsi
0x1400038d3  push    rdi
0x1400038d4  push    r14
0x1400038d6  push    r15
0x1400038d8  mov     rbp, rsp
0x1400038db  sub     rsp, 30h
0x1400038df  movzx   eax, word ptr [rdx+1Ah]
0x1400038e3  mov     rbx, rdx
0x1400038e6  xor     edx, edx
0x1400038e8  mov     rdi, rcx
0x1400038eb  mov     rcx, cs:qword_14005C5B8
0x1400038f2  mov     r9, [rcx+30h]
0x1400038f6  movzx   r8d, word ptr [r9]
0x1400038fa  div     r8d
0x1400038fd  mov     eax, cs:dword_14005C500
0x140003903  movsxd  rdx, edx
0x140003906  shl     rdx, 8
0x14000390a  add     rdx, r9
0x14000390d  cmp     [rdx+94h], eax
0x140003913  jbe     short loc_14000392E
0x140003915  lea     r8, aStatelessWorke_0; "Stateless worker overloaded"
0x14000391c  mov     rcx, rdi
0x14000391f  mov     rdx, rbx
0x140003922  call    QuicPacketLogDrop
0x140003927  xor     eax, eax
0x140003929  jmp     loc_140003AF1
0x14000392e  xor     r14d, r14d
0x140003931  lea     rax, [rbp+arg_8]
0x140003935  mov     [rbp+arg_8], r14
0x140003939  lea     r8, [rdx+40h]
0x14000393d  mov     rdx, [rdx+70h]
0x140003941  mov     r9, rbx
0x140003944  mov     [rbp+arg_10], r14
0x140003948  mov     [rsp+30h+var_10], rax
0x14000394d  call    QuicConnAlloc
0x140003952  mov     rcx, rdi
0x140003955  test    eax, eax
0x140003957  jns     short loc_140003962
0x140003959  lea     r8, aFailedToInitia; "Failed to initialize new connection"
0x140003960  jmp     short loc_14000391F
0x140003962  mov     rax, [rbp+arg_8]
0x140003966  mov     r15d, 1
0x14000396c  mov     rsi, [rax+500h]
0x140003973  lock add [rax+0F0h], r15d
0x14000397b  call    QuicLibraryTryAddRefBinding
0x140003980  test    al, al
0x140003982  jnz     short loc_1400039F7
0x140003984  lea     r8, aCleanUpInProgr; "Clean up in progress"
0x14000398b  mov     rdx, rbx
0x14000398e  mov     rcx, rdi
0x140003991  call    QuicPacketLogDrop
0x140003996  mov     rax, [rbp+arg_8]
0x14000399a  lea     rcx, [rsi-18h]; P
0x14000399e  mov     edx, 44306351h; Tag
0x1400039a3  mov     [rax+500h], r14
0x1400039aa  call    cs:__imp_ExFreePoolWithTag
0x1400039b1  nop     dword ptr [rax+rax+00h]
0x1400039b6  mov     rcx, [rbp+arg_8]
0x1400039ba  or      ebx, 0FFFFFFFFh
0x1400039bd  mov     eax, ebx
0x1400039bf  lock xadd [rcx+0F0h], eax
0x1400039c7  add     eax, ebx
0x1400039c9  jnz     short loc_1400039D7
0x1400039cb  mov     rdx, rcx
0x1400039ce  mov     rcx, [rcx+40h]
0x1400039d2  call    QuicWorkerQueueConnection
0x1400039d7  mov     rcx, [rbp+arg_8]
0x1400039db  mov     eax, ebx
0x1400039dd  lock xadd [rcx+0F0h], eax
0x1400039e5  add     eax, ebx
0x1400039e7  jnz     loc_140003AD7
0x1400039ed  call    QuicConnFree
0x1400039f2  jmp     loc_140003AD7
0x1400039f7  mov     rax, [rbp+arg_8]
0x1400039fb  lea     rcx, [rdi+40h]; int
0x1400039ff  mov     [rax+168h], rdi
0x140003a06  lea     rax, [rbp+arg_10]
0x140003a0a  mov     r8, [rbx+8]
0x140003a0e  mov     r9b, [rbx+57h]; char
0x140003a12  add     r8, 8; int
0x140003a16  mov     rdx, [rbp+arg_8]; int
0x140003a1a  mov     [rsp+30h+var_8], rax; __int64
0x140003a1f  mov     rax, [rbx+48h]
0x140003a23  mov     [rsp+30h+var_10], rax; void *
0x140003a28  call    QuicLookupAddRemoteHash
0x140003a2d  test    al, al
0x140003a2f  jnz     loc_140003ADD
0x140003a35  cmp     [rbp+arg_10], r14
0x140003a39  jnz     short loc_140003A4D
0x140003a3b  lea     r8, aFailedToInsert; "Failed to insert remote hash"
0x140003a42  mov     rdx, rbx
0x140003a45  mov     rcx, rdi
0x140003a48  call    QuicPacketLogDrop
0x140003a4d  mov     rcx, [rbp+arg_8]
0x140003a51  or      ebx, 0FFFFFFFFh
0x140003a54  mov     eax, ebx
0x140003a56  lock xadd [rcx+0F0h], eax
0x140003a5e  add     eax, ebx
0x140003a60  jnz     short loc_140003A6E
0x140003a62  mov     rdx, rcx
0x140003a65  mov     rcx, [rcx+40h]
0x140003a69  call    QuicWorkerQueueConnection
0x140003a6e  mov     rcx, [rbp+arg_8]
0x140003a72  xor     eax, eax
0x140003a74  lock cmpxchg [rcx+630h], r15w
0x140003a7e  test    ax, ax
0x140003a81  jnz     short loc_140003AD7
0x140003a83  mov     rdx, [rbp+arg_8]
0x140003a87  add     rdx, 5C0h
0x140003a8e  mov     [rdx+14h], r14b
0x140003a92  mov     [rdx+10h], r14d
0x140003a96  mov     rax, [rbp+arg_8]
0x140003a9a  add     rax, 5F8h
0x140003aa0  mov     [rdx+18h], rax
0x140003aa4  mov     [rax], r15d
0x140003aa7  mov     rax, [rdx+18h]
0x140003aab  mov     dword ptr [rax+18h], 8001h
0x140003ab2  mov     rax, [rdx+18h]
0x140003ab6  mov     qword ptr [rax+20h], 0FFFFFFFFC0240003h
0x140003abe  mov     rax, [rdx+18h]
0x140003ac2  and     byte ptr [rax+1Ch], 0FEh
0x140003ac6  mov     rax, [rdx+18h]
0x140003aca  or      byte ptr [rax+1Ch], 2
0x140003ace  mov     rcx, [rbp+arg_8]
0x140003ad2  call    QuicConnQueueOper
0x140003ad7  mov     rax, [rbp+arg_10]
0x140003adb  jmp     short loc_140003AF1
0x140003add  mov     rcx, [rbp+arg_8]
0x140003ae1  mov     rdx, rcx
0x140003ae4  mov     rcx, [rcx+40h]
0x140003ae8  call    QuicWorkerQueueConnection
0x140003aed  mov     rax, [rbp+arg_8]
0x140003af1  mov     rbx, [rsp+30h+arg_0]
0x140003af6  add     rsp, 30h
0x140003afa  pop     r15
0x140003afc  pop     r14
0x140003afe  pop     rdi
0x140003aff  pop     rsi
0x140003b00  pop     rbp
0x140003b01  retn
```
