# CubicCongestionControlOnSpuriousCongestionEvent

- ea: `0x140031b70`
- end: `0x140031c40`
- name: `CubicCongestionControlOnSpuriousCongestionEvent`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007a9c`
- `0x1400291f0`
- `0x140031b70`
- `0x140031d60`
- `0x14003c980`

## pseudocode

```c
char __fastcall CubicCongestionControlOnSpuriousCongestionEvent(__int64 a1)
{
  __int64 v3; // rdi
  __int64 v4; // rcx
  char v5; // si
  int v6; // ecx
  int v7; // eax
  int v8; // edx
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  char updated; // bl

  if ( (*(_BYTE *)(a1 + 136) & 2) == 0 )
    return 0;
  v3 = a1 - 2168;
  v5 = (*(__int64 (**)(void))(a1 + 8))();
  if ( (byte_14005C48A & 0x20) != 0 )
    McTemplateU0p_EtwWriteTransfer(v4, (const EVENT_DESCRIPTOR *)QuicConnSpuriousCongestion, v3);
  v6 = *(_DWORD *)(a1 + 220);
  v7 = *(_DWORD *)(a1 + 212);
  v8 = *(_DWORD *)(a1 + 236);
  *(_BYTE *)(a1 + 136) &= 0xFCu;
  *(_DWORD *)(a1 + 208) = v7;
  *(_DWORD *)(a1 + 156) = *(_DWORD *)(a1 + 160);
  v9 = *(_DWORD *)(a1 + 152);
  *(_DWORD *)(a1 + 216) = v6;
  v10 = *(_DWORD *)(a1 + 228);
  *(_DWORD *)(a1 + 148) = v9;
  v11 = *(_DWORD *)(a1 + 168);
  *(_DWORD *)(a1 + 224) = v10;
  *(_DWORD *)(a1 + 232) = v8;
  *(_DWORD *)(a1 + 164) = v11;
  updated = CubicCongestionControlUpdateBlockedState(a1, v5);
  QuicConnLogCubic(v3);
  return updated;
}

```

## disassembly

```asm
0x140031b70  mov     [rsp+arg_0], rbx
0x140031b75  mov     [rsp+arg_8], rsi
0x140031b7a  push    rdi
0x140031b7b  sub     rsp, 20h
0x140031b7f  test    byte ptr [rcx+88h], 2
0x140031b86  mov     rbx, rcx
0x140031b89  jnz     short loc_140031B92
0x140031b8b  xor     al, al
0x140031b8d  jmp     loc_140031C2F
0x140031b92  mov     rax, [rcx+8]
0x140031b96  lea     rdi, [rcx-878h]
0x140031b9d  call    _guard_dispatch_icall
0x140031ba2  test    cs:byte_14005C48A, 20h
0x140031ba9  mov     sil, al
0x140031bac  jz      short loc_140031BBD
0x140031bae  mov     r8, rdi
0x140031bb1  lea     rdx, QuicConnSpuriousCongestion
0x140031bb8  call    McTemplateU0p_EtwWriteTransfer
0x140031bbd  mov     ecx, [rbx+0DCh]
0x140031bc3  mov     eax, [rbx+0D4h]
0x140031bc9  mov     edx, [rbx+0ECh]
0x140031bcf  and     byte ptr [rbx+88h], 0FCh
0x140031bd6  mov     [rbx+0D0h], eax
0x140031bdc  mov     eax, [rbx+0A0h]
0x140031be2  mov     [rbx+9Ch], eax
0x140031be8  mov     eax, [rbx+98h]
0x140031bee  mov     [rbx+0D8h], ecx
0x140031bf4  mov     ecx, [rbx+0E4h]
0x140031bfa  mov     [rbx+94h], eax
0x140031c00  mov     eax, [rbx+0A8h]
0x140031c06  mov     [rbx+0E0h], ecx
0x140031c0c  mov     rcx, rbx
0x140031c0f  mov     [rbx+0E8h], edx
0x140031c15  mov     dl, sil
0x140031c18  mov     [rbx+0A4h], eax
0x140031c1e  call    CubicCongestionControlUpdateBlockedState
0x140031c23  mov     rcx, rdi
0x140031c26  mov     bl, al
0x140031c28  call    QuicConnLogCubic
0x140031c2d  mov     al, bl
0x140031c2f  mov     rbx, [rsp+28h+arg_0]
0x140031c34  mov     rsi, [rsp+28h+arg_8]
0x140031c39  add     rsp, 20h
0x140031c3d  pop     rdi
0x140031c3e  retn
```
