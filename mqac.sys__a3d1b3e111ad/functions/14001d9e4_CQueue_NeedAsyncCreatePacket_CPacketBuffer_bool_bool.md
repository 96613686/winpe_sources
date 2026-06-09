# CQueue::NeedAsyncCreatePacket(CPacketBuffer *,bool,bool)

- ea: `0x14001d9e4`
- end: `0x14001da58`
- name: `?NeedAsyncCreatePacket@CQueue@@QEBA_NPEAVCPacketBuffer@@_N1@Z`
- size: `116`
- prototype: `bool __fastcall(CQueue *__hidden this, struct CPacketBuffer *, bool, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000dc20`
- `0x14001cd90`

## callees

- `0x14001d9e4`
- `0x14001e6e8`
- `0x140024bf0`

## pseudocode

```c
bool __fastcall CQueue::NeedAsyncCreatePacket(CQueue *this, struct CPacketBuffer *a2, char a3, char a4)
{
  struct CSecurityHeader *v8; // rax
  struct CSecurityHeader *v9; // rdx
  __int16 v10; // ax

  if ( !(*(unsigned int (__fastcall **)(CQueue *))(*(_QWORD *)this + 32LL))(this) )
    return 0;
  if ( a3 )
    return a4 ^ 1;
  v8 = CPacketBuffer::SecurityHeaderSafe((struct CBaseHeader *)(((unsigned __int64)a2 + 36) & -(__int64)(a2 != 0)));
  v9 = v8;
  if ( !v8 )
    return 0;
  v10 = *(_WORD *)v8;
  return (v10 & 0xF) != 2 && *((_WORD *)v9 + 3) || (v10 & 0x20) != 0;
}

```

## disassembly

```asm
0x14001d9e4  push    rbx
0x14001d9e6  push    rbp
0x14001d9e7  push    rsi
0x14001d9e8  push    rdi
0x14001d9e9  sub     rsp, 28h
0x14001d9ed  mov     rax, [rcx]
0x14001d9f0  mov     bl, r9b
0x14001d9f3  mov     sil, r8b
0x14001d9f6  mov     rdi, rdx
0x14001d9f9  mov     rax, [rax+20h]
0x14001d9fd  call    _guard_dispatch_icall
0x14001da02  xor     ebp, ebp
0x14001da04  test    eax, eax
0x14001da06  jz      short loc_14001DA4C
0x14001da08  lea     rax, [rdi+24h]
0x14001da0c  neg     rdi
0x14001da0f  sbb     rcx, rcx
0x14001da12  and     rcx, rax; struct CBaseHeader *
0x14001da15  test    sil, sil
0x14001da18  jz      short loc_14001DA21
0x14001da1a  xor     bl, 1
0x14001da1d  mov     al, bl
0x14001da1f  jmp     short loc_14001DA4E
0x14001da21  call    ?SecurityHeaderSafe@CPacketBuffer@@SAPEAUCSecurityHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::SecurityHeaderSafe(CBaseHeader *)
0x14001da26  mov     rdx, rax
0x14001da29  test    rax, rax
0x14001da2c  jz      short loc_14001DA4C
0x14001da2e  movzx   eax, word ptr [rax]
0x14001da31  mov     cl, al
0x14001da33  and     cl, 0Fh
0x14001da36  cmp     cl, 2
0x14001da39  jz      short loc_14001DA45
0x14001da3b  cmp     [rdx+6], bp
0x14001da3f  jz      short loc_14001DA45
0x14001da41  mov     al, 1
0x14001da43  jmp     short loc_14001DA4E
0x14001da45  shr     al, 5
0x14001da48  and     al, 1
0x14001da4a  jmp     short loc_14001DA4E
0x14001da4c  xor     al, al
0x14001da4e  add     rsp, 28h
0x14001da52  pop     rdi
0x14001da53  pop     rsi
0x14001da54  pop     rbp
0x14001da55  pop     rbx
0x14001da56  retn
```
