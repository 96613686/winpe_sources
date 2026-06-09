# FsmSendProtocolRej

- ea: `0x18000e1e0`
- end: `0x18000e290`
- name: `FsmSendProtocolRej`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c3e8`

## callees

- `0x18000e1e0`
- `0x180011748`
- `0x180012a20`
- `0x180013e50`
- `0x180033a80`

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
0x18000e1e0  mov     [rsp+arg_0], rbx
0x18000e1e5  push    rdi
0x18000e1e6  sub     rsp, 20h
0x18000e1ea  cmp     dword ptr [rcx+30h], 0
0x18000e1ee  mov     r10, rdx
0x18000e1f1  mov     rdi, rcx
0x18000e1f4  jz      loc_18000E282
0x18000e1fa  mov     r9, [rcx+28h]
0x18000e1fe  lea     ebx, [r8+6]
0x18000e202  mov     eax, 5DCh
0x18000e207  cmp     ebx, eax
0x18000e209  cmova   ebx, eax
0x18000e20c  mov     rax, cs:CpTable
0x18000e213  xor     edx, edx
0x18000e215  movzx   ecx, word ptr [rax]
0x18000e218  movzx   eax, cx
0x18000e21b  mov     [r9+1], cl
0x18000e21f  shr     ax, 8
0x18000e223  mov     rcx, rdi
0x18000e226  mov     [r9], al
0x18000e229  mov     byte ptr [r9+2], 8
0x18000e22e  call    GetUId
0x18000e233  mov     [r9+3], al
0x18000e237  lea     ecx, [rbx-2]
0x18000e23a  movzx   eax, cx
0x18000e23d  mov     [r9+5], cl
0x18000e241  shr     ax, 8
0x18000e245  lea     rcx, [r9+6]; void *
0x18000e249  mov     r8d, ebx
0x18000e24c  mov     rdx, r10; Src
0x18000e24f  sub     r8, 6; Size
0x18000e253  mov     [r9+4], al
0x18000e257  call    memcpy_0
0x18000e25c  mov     r8, [rdi+28h]
0x18000e260  mov     r9d, ebx
0x18000e263  mov     rdx, rdi
0x18000e266  xor     ecx, ecx
0x18000e268  call    LogPPPPacket
0x18000e26d  mov     edx, ebx
0x18000e26f  mov     rcx, rdi
0x18000e272  call    PortSendOrDisconnect
0x18000e277  xor     ecx, ecx
0x18000e279  test    eax, eax
0x18000e27b  setz    cl
0x18000e27e  mov     eax, ecx
0x18000e280  jmp     short loc_18000E284
0x18000e282  xor     eax, eax
0x18000e284  mov     rbx, [rsp+28h+arg_0]
0x18000e289  add     rsp, 20h
0x18000e28d  pop     rdi
0x18000e28e  retn
```
