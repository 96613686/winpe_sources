# DrSession::SendCompletion(tagWriteContext *,_IO_STATUS_BLOCK *)

- ea: `0x14002a100`
- end: `0x14002a1b6`
- name: `?SendCompletion@DrSession@@AEAAXPEAUtagWriteContext@@PEAU_IO_STATUS_BLOCK@@@Z`
- size: `182`
- prototype: `void __fastcall(DrSession *__hidden this, struct tagWriteContext *, struct _IO_STATUS_BLOCK *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140027d50`

## callees

- `0x14000324c`
- `0x140006560`
- `0x1400111d0`
- `0x14002a100`

## pseudocode

```c
void __fastcall DrSession::SendCompletion(DrSession *this, struct tagWriteContext *a2, struct _IO_STATUS_BLOCK *a3)
{
  __int64 (__fastcall ***v4)(_QWORD, _QWORD, struct _IO_STATUS_BLOCK *, struct tagWriteContext *); // rcx
  int v5; // eax
  __int64 (__fastcall *v6)(_QWORD, struct _IO_STATUS_BLOCK *); // rax

  v4 = (__int64 (__fastcall ***)(_QWORD, _QWORD, struct _IO_STATUS_BLOCK *, struct tagWriteContext *))*((_QWORD *)a2 + 5);
  if ( v4 )
  {
    v5 = (**v4)(v4, *((_QWORD *)a2 + 4), a3, a2);
  }
  else
  {
    v6 = (__int64 (__fastcall *)(_QWORD, struct _IO_STATUS_BLOCK *))*((_QWORD *)a2 + 6);
    if ( !v6 )
    {
LABEL_4:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
      return;
    }
    v5 = v6(*((_QWORD *)a2 + 4), a3);
  }
  if ( (v5 & 0xC0000000) != 0xC0000000 )
    goto LABEL_4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
  DrSession::ChannelIoFailed(this);
}

```

## disassembly

```asm
0x14002a100  push    rbx
0x14002a102  sub     rsp, 20h
0x14002a106  mov     rbx, rcx
0x14002a109  mov     r9, rdx
0x14002a10c  mov     rcx, [rdx+28h]
0x14002a110  test    rcx, rcx
0x14002a113  jz      short loc_14002A14A
0x14002a115  mov     rax, [rcx]
0x14002a118  mov     rdx, [rdx+20h]
0x14002a11c  mov     rax, [rax]
0x14002a11f  call    _guard_dispatch_icall
0x14002a124  and     eax, 0C0000000h
0x14002a129  cmp     eax, 0C0000000h
0x14002a12e  jz      short loc_14002A161
0x14002a130  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a137  lea     rax, WPP_GLOBAL_Control
0x14002a13e  cmp     rcx, rax
0x14002a141  jnz     short loc_14002A199
0x14002a143  add     rsp, 20h
0x14002a147  pop     rbx
0x14002a148  retn
0x14002a14a  mov     rax, [rdx+30h]
0x14002a14e  test    rax, rax
0x14002a151  jz      short loc_14002A130
0x14002a153  mov     rcx, [r9+20h]
0x14002a157  mov     rdx, r8
0x14002a15a  call    _guard_dispatch_icall
0x14002a15f  jmp     short loc_14002A124
0x14002a161  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a168  lea     rax, WPP_GLOBAL_Control
0x14002a16f  cmp     rcx, rax
0x14002a172  jz      short loc_14002A18F
0x14002a174  cmp     byte ptr [rcx+29h], 4
0x14002a178  jb      short loc_14002A18F
0x14002a17a  mov     rcx, [rcx+18h]
0x14002a17e  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14002a185  mov     edx, 3Bh ; ';'
0x14002a18a  call    WPP_SF_
0x14002a18f  mov     rcx, rbx; this
0x14002a192  call    ?ChannelIoFailed@DrSession@@AEAAXXZ; DrSession::ChannelIoFailed(void)
0x14002a197  jmp     short loc_14002A143
0x14002a199  cmp     byte ptr [rcx+29h], 4
0x14002a19d  jb      short loc_14002A143
0x14002a19f  mov     rcx, [rcx+18h]
0x14002a1a3  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14002a1aa  mov     edx, 3Ah ; ':'
0x14002a1af  call    WPP_SF_
0x14002a1b4  jmp     short loc_14002A143
```
