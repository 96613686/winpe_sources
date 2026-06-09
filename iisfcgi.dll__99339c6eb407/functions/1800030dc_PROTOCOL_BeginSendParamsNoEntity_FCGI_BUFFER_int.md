# PROTOCOL::BeginSendParamsNoEntity(FCGI_BUFFER *,int *)

- ea: `0x1800030dc`
- end: `0x1800031b7`
- name: `?BeginSendParamsNoEntity@PROTOCOL@@AEAAJPEAVFCGI_BUFFER@@PEAH@Z`
- size: `219`
- prototype: `__int64 __fastcall(PROTOCOL *__hidden this, struct FCGI_BUFFER *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800039a0`

## callees

- `0x180002f60`

## pseudocode

```c
__int64 __fastcall PROTOCOL::BeginSendParamsNoEntity(PROTOCOL *this, struct FCGI_BUFFER *a2, int *a3)
{
  __int16 v3; // r9
  int v5; // r11d
  __int64 v7; // r10
  __int64 v9; // r8
  __int16 v10; // cx
  __int64 v11; // rdx
  __int16 v12; // cx
  __int64 v13; // rax

  v3 = *((_WORD *)this + 20);
  *((_DWORD *)this + 11) = 5;
  v5 = *((_DWORD *)a2 + 6);
  v7 = *(_QWORD *)a2;
  *(_QWORD *)(v7 - 8) = 0;
  *(_BYTE *)(v7 - 5) = v3;
  *(_WORD *)(v7 - 8) = 1025;
  *(_BYTE *)(v7 - 3) = v5;
  *(_BYTE *)(v7 - 6) = HIBYTE(v3);
  *(_BYTE *)(v7 - 4) = BYTE1(v5);
  v9 = *((unsigned int *)a2 + 6);
  v10 = *((_WORD *)this + 20);
  v11 = *((_QWORD *)a2 + 2);
  *(_QWORD *)(v9 + v11) = 0;
  *(_BYTE *)(v9 + v11 + 3) = v10;
  *(_WORD *)(v9 + v11) = 1025;
  *(_WORD *)(v9 + v11 + 4) = 0;
  *(_BYTE *)(v9 + v11 + 2) = HIBYTE(v10);
  v12 = *((_WORD *)this + 20);
  *(_QWORD *)(v9 + v11 + 8) = 0;
  *(_BYTE *)(v9 + v11 + 11) = v12;
  *(_WORD *)(v9 + v11 + 8) = 1281;
  *(_WORD *)(v9 + v11 + 12) = 0;
  *(_BYTE *)(v9 + v11 + 10) = HIBYTE(v12);
  v13 = *(_QWORD *)a2;
  *((_DWORD *)a2 + 6) += 16;
  *((_QWORD *)a2 + 2) = v13;
  *((_DWORD *)this + 15) = 0;
  *((_QWORD *)this + 18) = a2;
  return PROTOCOL::BeginSendCommon(this, a3);
}

```

## disassembly

```asm
0x1800030dc  mov     [rsp+arg_0], rbx
0x1800030e1  mov     [rsp+arg_8], rsi
0x1800030e6  push    rdi
0x1800030e7  movzx   r9d, word ptr [rcx+28h]
0x1800030ec  xor     eax, eax
0x1800030ee  mov     dword ptr [rcx+2Ch], 5
0x1800030f5  mov     rbx, rdx
0x1800030f8  mov     r11d, [rdx+18h]
0x1800030fc  mov     rdi, rcx
0x1800030ff  mov     r10, [rdx]
0x180003102  mov     rsi, r8
0x180003105  mov     [r10-8], rax
0x180003109  movzx   eax, r9w
0x18000310d  mov     [r10-5], r9b
0x180003111  xor     r9d, r9d
0x180003114  mov     word ptr [r10-8], 401h
0x18000311b  mov     [r10-3], r11b
0x18000311f  sar     ax, 8
0x180003123  mov     [r10-6], al
0x180003127  mov     eax, r11d
0x18000312a  shr     eax, 8
0x18000312d  mov     [r10-4], al
0x180003131  xor     eax, eax
0x180003133  mov     r8d, [rdx+18h]
0x180003137  movzx   ecx, word ptr [rcx+28h]
0x18000313b  mov     rdx, [rdx+10h]
0x18000313f  mov     [r8+rdx], rax
0x180003143  movzx   eax, cx
0x180003146  mov     [r8+rdx+3], cl
0x18000314b  mov     word ptr [r8+rdx], 401h
0x180003152  mov     [r8+rdx+4], r9w
0x180003158  sar     ax, 8
0x18000315c  mov     [r8+rdx+2], al
0x180003161  xor     eax, eax
0x180003163  movzx   ecx, word ptr [rdi+28h]
0x180003167  mov     [r8+rdx+8], rax
0x18000316c  movzx   eax, cx
0x18000316f  mov     [r8+rdx+0Bh], cl
0x180003174  mov     rcx, rdi; this
0x180003177  mov     word ptr [r8+rdx+8], 501h
0x18000317f  mov     [r8+rdx+0Ch], r9w
0x180003185  sar     ax, 8
0x180003189  mov     [r8+rdx+0Ah], al
0x18000318e  mov     rdx, rsi; int *
0x180003191  mov     rax, [rbx]
0x180003194  add     dword ptr [rbx+18h], 10h
0x180003198  mov     [rbx+10h], rax
0x18000319c  mov     [rdi+3Ch], r9d
0x1800031a0  mov     [rdi+90h], rbx
0x1800031a7  mov     rbx, [rsp+8+arg_0]
0x1800031ac  mov     rsi, [rsp+8+arg_8]
0x1800031b1  pop     rdi
0x1800031b2  jmp     ?BeginSendCommon@PROTOCOL@@AEAAJPEAH@Z; PROTOCOL::BeginSendCommon(int *)
```
