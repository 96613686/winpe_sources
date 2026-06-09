# QuicListenerHandleDosModeStateChange

- ea: `0x14002bd08`
- end: `0x14002bd8d`
- name: `QuicListenerHandleDosModeStateChange`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140001b00`
- `0x14002854c`

## callees

- `0x14002bd08`
- `0x14002bd94`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14002bd75`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14002bd75`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14002bd50`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14002bd50`

## pseudocode

```c
void __fastcall QuicListenerHandleDosModeStateChange(__int64 a1, char a2)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  _DWORD v5[10]; // [rsp+20h] [rbp-28h] BYREF

  if ( *(_BYTE *)(a1 + 20) )
  {
    v3 = *(_QWORD *)(a1 + 72);
    v5[0] = 2;
    *(_OWORD *)&v5[1] = 0;
    LOBYTE(v5[2]) = a2 & 1 | _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4)) & 0xFE;
    if ( v3 )
      v4 = PsAttachSiloToCurrentThread(v3);
    else
      v4 = -1;
    QuicListenerIndicateDispatchEvent(a1, v5);
    if ( v4 != -1 )
      PsDetachSiloFromCurrentThread(v4);
  }
}

```

## disassembly

```asm
0x14002bd08  mov     [rsp+arg_0], rbx
0x14002bd0d  push    rdi
0x14002bd0e  sub     rsp, 40h
0x14002bd12  cmp     byte ptr [rcx+14h], 0
0x14002bd16  mov     rdi, rcx
0x14002bd19  jz      short loc_14002BD81
0x14002bd1b  mov     rcx, [rcx+48h]
0x14002bd1f  xorps   xmm0, xmm0
0x14002bd22  and     dl, 1
0x14002bd25  mov     qword ptr [rsp+48h+var_28], 2
0x14002bd2e  movdqu  xmmword ptr [rsp+48h+var_28+4], xmm0
0x14002bd34  psrldq  xmm0, 4
0x14002bd39  movd    eax, xmm0
0x14002bd3d  and     al, 0FEh
0x14002bd3f  or      al, dl
0x14002bd41  mov     [rsp+48h+var_28+8], al
0x14002bd45  test    rcx, rcx
0x14002bd48  jnz     short loc_14002BD50
0x14002bd4a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002bd4e  jmp     short loc_14002BD5F
0x14002bd50  call    cs:__imp_PsAttachSiloToCurrentThread
0x14002bd57  nop     dword ptr [rax+rax+00h]
0x14002bd5c  mov     rbx, rax
0x14002bd5f  lea     rdx, [rsp+48h+var_28]
0x14002bd64  mov     rcx, rdi
0x14002bd67  call    QuicListenerIndicateDispatchEvent
0x14002bd6c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14002bd70  jz      short loc_14002BD81
0x14002bd72  mov     rcx, rbx
0x14002bd75  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14002bd7c  nop     dword ptr [rax+rax+00h]
0x14002bd81  mov     rbx, [rsp+48h+arg_0]
0x14002bd86  add     rsp, 40h
0x14002bd8a  pop     rdi
0x14002bd8b  retn
```
