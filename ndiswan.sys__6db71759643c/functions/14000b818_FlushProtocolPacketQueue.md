# FlushProtocolPacketQueue

- ea: `0x14000b818`
- end: `0x14000b8f9`
- name: `FlushProtocolPacketQueue`
- size: `225`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007364`
- `0x14000d0c0`
- `0x1400254c8`
- `0x140027a50`

## callees

- `0x14000b818`
- `0x1400353d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000b887`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b887`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b8be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b8be`

## pseudocode

```c
void __fastcall FlushProtocolPacketQueue(__int64 a1)
{
  __int64 v1; // rbp
  __int64 i; // rdi
  __int64 v4; // rsi
  struct _NET_BUFFER_LIST *j; // r14
  ULONGLONG Alignment; // rax

  v1 = *(_QWORD *)(a1 + 64);
  for ( i = 0; i != 2; ++i )
  {
    v4 = 48 * i;
    for ( j = *(struct _NET_BUFFER_LIST **)(48 * i + a1 + 112); j; j = *(struct _NET_BUFFER_LIST **)(v4 + a1 + 112) )
    {
      Alignment = j->Link.Alignment;
      if ( !j->Link.Alignment )
        *(_QWORD *)(v4 + a1 + 120) = 0;
      j->Link.Alignment = 0;
      *(_QWORD *)(v4 + a1 + 112) = Alignment;
      *(_DWORD *)(v4 + a1 + 128) -= *(_DWORD *)&j->Context->ContextData[j->Context->Offset + 100];
      --*(_DWORD *)(v4 + a1 + 136);
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 1768), *(_BYTE *)(v1 + 1776));
      if ( _InterlockedExchangeAdd(
             (volatile signed __int32 *)&j->Context->ContextData[j->Context->Offset + 24],
             0xFFFFFFFF) == 1 )
        CompleteNetBufferList(*(_QWORD *)(a1 + 56), a1, j, 0);
      *(_BYTE *)(v1 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 1768));
    }
  }
}

```

## disassembly

```asm
0x14000b818  push    rbx
0x14000b81a  push    rbp
0x14000b81b  push    rsi
0x14000b81c  push    rdi
0x14000b81d  push    r14
0x14000b81f  push    r15
0x14000b821  sub     rsp, 28h
0x14000b825  mov     rbp, [rcx+40h]
0x14000b829  mov     rbx, rcx
0x14000b82c  xor     edi, edi
0x14000b82e  lea     rsi, [rdi+rdi*2]
0x14000b832  shl     rsi, 4
0x14000b836  mov     r14, [rsi+rbx+70h]
0x14000b83b  test    r14, r14
0x14000b83e  jz      loc_14000B8DE
0x14000b844  lea     r15, [rbp+6E8h]
0x14000b84b  mov     rax, [r14]
0x14000b84e  test    rax, rax
0x14000b851  jnz     short loc_14000B858
0x14000b853  mov     [rsi+rbx+78h], rax
0x14000b858  mov     qword ptr [r14], 0
0x14000b85f  mov     [rsi+rbx+70h], rax
0x14000b864  mov     rcx, [r14+10h]
0x14000b868  movzx   eax, word ptr [rcx+0Ah]
0x14000b86c  mov     edx, [rax+rcx+74h]
0x14000b870  mov     rcx, r15; SpinLock
0x14000b873  sub     [rsi+rbx+80h], edx
0x14000b87a  dec     dword ptr [rsi+rbx+88h]
0x14000b881  mov     dl, [rbp+6F0h]; NewIrql
0x14000b887  call    cs:__imp_KeReleaseSpinLock
0x14000b88e  nop     dword ptr [rax+rax+00h]
0x14000b893  mov     rdx, [r14+10h]
0x14000b897  or      eax, 0FFFFFFFFh
0x14000b89a  movzx   ecx, word ptr [rdx+0Ah]
0x14000b89e  lock xadd [rcx+rdx+28h], eax
0x14000b8a4  cmp     eax, 1
0x14000b8a7  jnz     short loc_14000B8BB
0x14000b8a9  mov     rcx, [rbx+38h]
0x14000b8ad  xor     r9d, r9d
0x14000b8b0  mov     r8, r14
0x14000b8b3  mov     rdx, rbx
0x14000b8b6  call    CompleteNetBufferList
0x14000b8bb  mov     rcx, r15; SpinLock
0x14000b8be  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b8c5  nop     dword ptr [rax+rax+00h]
0x14000b8ca  mov     [rbp+6F0h], al
0x14000b8d0  mov     r14, [rsi+rbx+70h]
0x14000b8d5  test    r14, r14
0x14000b8d8  jnz     loc_14000B84B
0x14000b8de  inc     rdi
0x14000b8e1  cmp     rdi, 2
0x14000b8e5  jnz     loc_14000B82E
0x14000b8eb  add     rsp, 28h
0x14000b8ef  pop     r15
0x14000b8f1  pop     r14
0x14000b8f3  pop     rdi
0x14000b8f4  pop     rsi
0x14000b8f5  pop     rbp
0x14000b8f6  pop     rbx
0x14000b8f7  retn
```
