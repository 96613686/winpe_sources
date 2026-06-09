# MsQuicConnectionOpenInPartition

- ea: `0x140029970`
- end: `0x140029a4d`
- name: `MsQuicConnectionOpenInPartition`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003390`

## callees

- `0x140007b30`
- `0x140029970`
- `0x14003eca4`
- `0x140040c2c`

## pseudocode

```c
__int64 __fastcall MsQuicConnectionOpenInPartition(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  int v7; // ebp
  _QWORD *v9; // rdi
  int v10; // ebx
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = 0;
  v7 = (unsigned __int16)a2;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer((__int64)a1, a2, 12, a1);
  if ( a1 && !*a1 && (unsigned __int16)v7 < (unsigned __int16)word_14005C55C && (v9 = a5) != 0 && a3 )
  {
    v10 = QuicConnAlloc((_DWORD)a1, (int)Val + 2496 * v7, 0, 0, (__int64)&v12);
    if ( v10 >= 0 )
    {
      v10 = 0;
      *(_QWORD *)(v12 + 3608) = a3;
      *(_QWORD *)(v12 + 8) = a4;
      *v9 = v12;
    }
  }
  else
  {
    v10 = -1073741811;
  }
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)QuicApiExitStatus, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140029970  mov     [rsp+arg_8], rbx
0x140029975  mov     [rsp+arg_10], rbp
0x14002997a  push    rsi
0x14002997b  push    rdi
0x14002997c  push    r14
0x14002997e  sub     rsp, 30h
0x140029982  and     [rsp+48h+arg_0], 0
0x140029988  mov     r14, r9
0x14002998b  test    cs:Microsoft_QuicEnableBits, 8
0x140029992  mov     rsi, r8
0x140029995  movzx   ebp, dx
0x140029998  mov     rbx, rcx
0x14002999b  jz      short loc_1400299AB
0x14002999d  mov     r9, rcx
0x1400299a0  mov     r8d, 0Ch
0x1400299a6  call    McTemplateU0qp_EtwWriteTransfer
0x1400299ab  test    rbx, rbx
0x1400299ae  jz      short loc_140029A1A
0x1400299b0  cmp     dword ptr [rbx], 0
0x1400299b3  jnz     short loc_140029A1A
0x1400299b5  cmp     bp, cs:word_14005C55C
0x1400299bc  jnb     short loc_140029A1A
0x1400299be  mov     rdi, [rsp+48h+arg_20]
0x1400299c3  test    rdi, rdi
0x1400299c6  jz      short loc_140029A1A
0x1400299c8  test    rsi, rsi
0x1400299cb  jz      short loc_140029A1A
0x1400299cd  lea     rax, [rsp+48h+arg_0]
0x1400299d2  xor     r9d, r9d
0x1400299d5  imul    rdx, rbp, 9C0h
0x1400299dc  xor     r8d, r8d
0x1400299df  mov     [rsp+48h+var_28], rax
0x1400299e4  add     rdx, cs:Val
0x1400299eb  mov     rcx, rbx
0x1400299ee  call    QuicConnAlloc
0x1400299f3  mov     ebx, eax
0x1400299f5  test    eax, eax
0x1400299f7  js      short loc_140029A1F
0x1400299f9  mov     rax, [rsp+48h+arg_0]
0x1400299fe  xor     ebx, ebx
0x140029a00  mov     [rax+0E18h], rsi
0x140029a07  mov     rax, [rsp+48h+arg_0]
0x140029a0c  mov     [rax+8], r14
0x140029a10  mov     rax, [rsp+48h+arg_0]
0x140029a15  mov     [rdi], rax
0x140029a18  jmp     short loc_140029A1F
0x140029a1a  mov     ebx, 0C000000Dh
0x140029a1f  test    cs:Microsoft_QuicEnableBits, 8
0x140029a26  jz      short loc_140029A37
0x140029a28  mov     r8d, ebx
0x140029a2b  lea     rdx, QuicApiExitStatus
0x140029a32  call    McTemplateU0q_EtwWriteTransfer
0x140029a37  mov     rbp, [rsp+48h+arg_10]
0x140029a3c  mov     eax, ebx
0x140029a3e  mov     rbx, [rsp+48h+arg_8]
0x140029a43  add     rsp, 30h
0x140029a47  pop     r14
0x140029a49  pop     rdi
0x140029a4a  pop     rsi
0x140029a4b  retn
```
