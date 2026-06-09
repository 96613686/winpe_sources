# FsmSendProtocolRej

- ea: `0x18000dda4`
- end: `0x18000de53`
- name: `FsmSendProtocolRej`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x18000dda4`
- `0x1800111ac`
- `0x18001238c`
- `0x18001378c`
- `0x180032460`

## pseudocode

```c
_BOOL8 __fastcall FsmSendProtocolRej(__int64 a1, __int64 a2, int a3)
{
  _BYTE *v4; // r9
  unsigned int v5; // ebx
  __int16 v6; // ax
  char UId; // al
  _BYTE *v8; // r9
  const void *v9; // r10

  if ( !*(_DWORD *)(a1 + 48) )
    return 0;
  v4 = *(_BYTE **)(a1 + 40);
  v5 = a3 + 6;
  if ( (unsigned int)(a3 + 6) > 0x5DC )
    v5 = 1500;
  v6 = *(_WORD *)CpTable;
  v4[1] = *(_WORD *)CpTable;
  *v4 = HIBYTE(v6);
  v4[2] = 8;
  UId = GetUId(a1, 0);
  v8[3] = UId;
  v8[5] = v5 - 2;
  v8[4] = (unsigned __int16)(v5 - 2) >> 8;
  memcpy_0(v8 + 6, v9, v5 - 6LL);
  LogPPPPacket(0, a1, *(unsigned __int8 **)(a1 + 40), v5);
  return (unsigned int)PortSendOrDisconnect(a1, v5) == 0;
}

```

## disassembly

```asm
0x18000dda4  mov     [rsp+arg_0], rbx
0x18000dda9  push    rdi
0x18000ddaa  sub     rsp, 20h
0x18000ddae  cmp     dword ptr [rcx+30h], 0
0x18000ddb2  mov     r10, rdx
0x18000ddb5  mov     rdi, rcx
0x18000ddb8  jz      loc_18000DE46
0x18000ddbe  mov     r9, [rcx+28h]
0x18000ddc2  lea     ebx, [r8+6]
0x18000ddc6  mov     eax, 5DCh
0x18000ddcb  cmp     ebx, eax
0x18000ddcd  cmova   ebx, eax
0x18000ddd0  mov     rax, cs:CpTable
0x18000ddd7  xor     edx, edx
0x18000ddd9  movzx   ecx, word ptr [rax]
0x18000dddc  movzx   eax, cx
0x18000dddf  mov     [r9+1], cl
0x18000dde3  shr     ax, 8
0x18000dde7  mov     rcx, rdi
0x18000ddea  mov     [r9], al
0x18000dded  mov     byte ptr [r9+2], 8
0x18000ddf2  call    GetUId
0x18000ddf7  mov     [r9+3], al
0x18000ddfb  lea     ecx, [rbx-2]
0x18000ddfe  movzx   eax, cx
0x18000de01  mov     [r9+5], cl
0x18000de05  shr     ax, 8
0x18000de09  lea     rcx, [r9+6]; void *
0x18000de0d  mov     r8d, ebx
0x18000de10  mov     rdx, r10; Src
0x18000de13  sub     r8, 6; Size
0x18000de17  mov     [r9+4], al
0x18000de1b  call    memcpy_0
0x18000de20  mov     r8, [rdi+28h]
0x18000de24  mov     r9d, ebx
0x18000de27  mov     rdx, rdi
0x18000de2a  xor     ecx, ecx
0x18000de2c  call    LogPPPPacket
0x18000de31  mov     edx, ebx
0x18000de33  mov     rcx, rdi
0x18000de36  call    PortSendOrDisconnect
0x18000de3b  xor     ecx, ecx
0x18000de3d  test    eax, eax
0x18000de3f  setz    cl
0x18000de42  mov     eax, ecx
0x18000de44  jmp     short loc_18000DE48
0x18000de46  xor     eax, eax
0x18000de48  mov     rbx, [rsp+28h+arg_0]
0x18000de4d  add     rsp, 20h
0x18000de51  pop     rdi
0x18000de52  retn
```
