# QuicCryptoWriteFrames

- ea: `0x14001bbc8`
- end: `0x14001bcc1`
- name: `QuicCryptoWriteFrames`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140019040`

## callees

- `0x140008944`
- `0x14001b7ec`
- `0x14001bbc8`
- `0x14001bcc8`
- `0x14001dfa4`
- `0x140029ef0`
- `0x14002f560`
- `0x14002f57c`

## pseudocode

```c
bool __fastcall QuicCryptoWriteFrames(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  __int64 NextEncryptLevel; // rcx
  char v9; // al
  unsigned __int8 v10; // bp
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9

  v5 = a1 - 2784;
  if ( !(unsigned __int8)QuicCryptoHasPendingCryptoFrame(a1, a2, a3, a4) )
  {
    *(_DWORD *)(v5 + 3488) &= ~2u;
    return 1;
  }
  NextEncryptLevel = (unsigned int)QuicCryptoGetNextEncryptLevel();
  if ( *(_DWORD *)(v5 + 3636) == -817679509 )
    v9 = QuicEncryptLevelToPacketTypeV2(NextEncryptLevel);
  else
    v9 = QuicEncryptLevelToPacketTypeV1(NextEncryptLevel);
  if ( *(_BYTE *)(a2 + 376) != v9 )
    return 1;
  if ( (unsigned __int8)QuicConnIsClient(v5) && *(_QWORD *)(a2 + 40) == *(_QWORD *)(a1 + 152) )
    QuicCryptoDiscardKeys(a1, 0);
  v10 = *(_BYTE *)(*(_QWORD *)(a2 + 408) + 90LL);
  QuicCryptoWriteCryptoFrames(
    a1,
    a2,
    a2 + 378,
    (unsigned __int16)(**(_WORD **)(a2 + 32) - *(unsigned __int8 *)(a2 + 370)),
    *(_QWORD *)(*(_QWORD *)(a2 + 32) + 8LL));
  if ( !(unsigned __int8)QuicCryptoHasPendingCryptoFrame(a1, v11, v12, v13) )
    *(_DWORD *)(v5 + 3488) &= ~2u;
  return *(_BYTE *)(*(_QWORD *)(a2 + 408) + 90LL) > v10;
}

```

## disassembly

```asm
0x14001bbc8  mov     [rsp+arg_0], rbx
0x14001bbcd  mov     [rsp+arg_8], rbp
0x14001bbd2  mov     [rsp+arg_10], rsi
0x14001bbd7  push    rdi
0x14001bbd8  sub     rsp, 30h
0x14001bbdc  mov     rsi, rdx
0x14001bbdf  lea     rbx, [rcx-0AE0h]
0x14001bbe6  mov     rdi, rcx
0x14001bbe9  call    QuicCryptoHasPendingCryptoFrame
0x14001bbee  test    al, al
0x14001bbf0  jnz     short loc_14001BC00
0x14001bbf2  and     dword ptr [rbx+0DA0h], 0FFFFFFFDh
0x14001bbf9  mov     al, 1
0x14001bbfb  jmp     loc_14001BCA1
0x14001bc00  call    QuicCryptoGetNextEncryptLevel
0x14001bc05  cmp     dword ptr [rbx+0E34h], 0CF43336Bh
0x14001bc0f  mov     ecx, eax
0x14001bc11  jz      loc_14001BCB7
0x14001bc17  call    QuicEncryptLevelToPacketTypeV1
0x14001bc1c  cmp     [rsi+178h], al
0x14001bc22  jnz     short loc_14001BBF9
0x14001bc24  mov     rcx, rbx
0x14001bc27  call    QuicConnIsClient
0x14001bc2c  test    al, al
0x14001bc2e  jz      short loc_14001BC47
0x14001bc30  mov     rax, [rdi+98h]
0x14001bc37  cmp     [rsi+28h], rax
0x14001bc3b  jnz     short loc_14001BC47
0x14001bc3d  xor     edx, edx
0x14001bc3f  mov     rcx, rdi
0x14001bc42  call    QuicCryptoDiscardKeys
0x14001bc47  mov     rax, [rsi+198h]
0x14001bc4e  lea     r8, [rsi+17Ah]
0x14001bc55  mov     rcx, [rsi+20h]
0x14001bc59  mov     rdx, rsi
0x14001bc5c  mov     bpl, [rax+5Ah]
0x14001bc60  movzx   eax, byte ptr [rsi+172h]
0x14001bc67  movzx   r9d, word ptr [rcx]
0x14001bc6b  sub     r9w, ax
0x14001bc6f  mov     rax, [rcx+8]
0x14001bc73  mov     rcx, rdi
0x14001bc76  mov     [rsp+38h+var_18], rax
0x14001bc7b  call    QuicCryptoWriteCryptoFrames
0x14001bc80  mov     rcx, rdi
0x14001bc83  call    QuicCryptoHasPendingCryptoFrame
0x14001bc88  test    al, al
0x14001bc8a  jnz     short loc_14001BC93
0x14001bc8c  and     dword ptr [rbx+0DA0h], 0FFFFFFFDh
0x14001bc93  mov     rax, [rsi+198h]
0x14001bc9a  cmp     [rax+5Ah], bpl
0x14001bc9e  setnbe  al
0x14001bca1  mov     rbx, [rsp+38h+arg_0]
0x14001bca6  mov     rbp, [rsp+38h+arg_8]
0x14001bcab  mov     rsi, [rsp+38h+arg_10]
0x14001bcb0  add     rsp, 30h
0x14001bcb4  pop     rdi
0x14001bcb5  retn
0x14001bcb7  call    QuicEncryptLevelToPacketTypeV2
0x14001bcbc  jmp     loc_14001BC1C
```
