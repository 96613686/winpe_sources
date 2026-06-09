# QuicSendSetSendFlag

- ea: `0x14000d490`
- end: `0x14000d630`
- name: `QuicSendSetSendFlag`
- size: `416`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `12`
- tags: ``

## callers

- `0x140001d6c`
- `0x1400049b0`
- `0x1400051c0`
- `0x1400099b4`
- `0x14000acfc`
- `0x14000b780`
- `0x14000ca70`
- `0x1400108c0`
- `0x140013200`
- `0x1400183d0`
- `0x14001c664`
- `0x14001d238`
- `0x14001e1b8`
- `0x14001e3b0`
- `0x14001ef7c`
- `0x140022b44`
- `0x14002ba00`
- `0x14002ef50`
- `0x1400309f8`
- `0x140030cd4`
- `0x140042bdc`
- `0x140043368`
- `0x1400457f0`
- `0x140045b1c`
- `0x140049624`

## callees

- `0x14000c500`
- `0x14000c5b0`
- `0x14000c718`
- `0x14000d490`
- `0x14000d7a0`
- `0x140010820`
- `0x1400290b4`
- `0x140030168`
- `0x14003c8e0`
- `0x14003e884`
- `0x14003ec10`
- `0x14003fd84`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000d54a`
- `ntoskrnl!_snprintf_s` at `0x14000d54a`

## pseudocode

```c
_BOOL8 __fastcall QuicSendSetSendFlag(__int64 a1, __int64 a2)
{
  char v2; // al
  _QWORD *v3; // rdi
  int v4; // esi
  int v5; // r14d
  __int64 v6; // rbx
  bool v7; // bp
  __int64 v8; // rcx
  PSLIST_ENTRY v9; // rax
  PSLIST_ENTRY v10; // rsi
  __int64 v11; // rax
  char DstBuf[128]; // [rsp+40h] [rbp-A8h] BYREF

  v2 = *(_BYTE *)(a1 - 3168);
  v3 = (_QWORD *)(a1 - 3416);
  v4 = a2;
  v5 = a2 & 0xC;
  v6 = a1;
  v7 = (v2 & 0x30) == 0 || (v2 & 0x40) == 0 && (a2 & 0xC) != 0;
  if ( (a2 & 1) != 0 && (*(_BYTE *)a1 & 2) != 0 )
  {
    QuicConnTimerCancel(v3, 1);
    *(_BYTE *)v6 &= ~2u;
  }
  if ( v7 )
  {
    a1 = *(unsigned int *)(v6 + 72);
    if ( (v4 & *(_DWORD *)(v6 + 72)) != v4 )
    {
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Adding send flags 0x%x (prev: 0x%x, new: 0x%x)",
          v4,
          a1,
          v4 | a1);
        McTemplateU0ps_EtwWriteTransfer(v8, (const EVENT_DESCRIPTOR *)QuicConnLogVerbose, (__int64)v3, DstBuf);
      }
      *(_DWORD *)(v6 + 72) |= v4;
      if ( (*(_BYTE *)v6 & 1) == 0 )
      {
        if ( (unsigned __int8)QuicSendCanSendFlagsNow(v6) )
        {
          v9 = CxPlatPoolAlloc(v3[9] + 2016LL);
          v10 = v9;
          if ( v9 )
          {
            LODWORD(v9[1].Next) = 4;
            BYTE4(v9[1].Next) = 1;
            *(_BYTE *)v6 |= 1u;
            if ( (byte_14005C48A & 1) != 0 )
              McTemplateU0pq_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)QuicConnQueueSendFlush, (__int64)v3, 0);
            if ( (unsigned __int8)QuicOperationEnqueue(v3 + 178, v3[9], v10) )
              QuicWorkerQueueConnection(v3[8], v3);
          }
        }
      }
    }
  }
  if ( v5 )
  {
    v11 = QuicTimePlat(a1, a2);
    v3[172] = QuicTimePlatToUs64(v11);
    QuicSendClear(v6);
  }
  return v7;
}

```

## disassembly

```asm
0x14000d490  mov     [rsp+arg_10], rbx
0x14000d495  mov     [rsp+arg_18], rbp
0x14000d49a  push    rsi
0x14000d49b  push    rdi
0x14000d49c  push    r14
0x14000d49e  sub     rsp, 0D0h
0x14000d4a5  mov     rax, cs:__security_cookie
0x14000d4ac  xor     rax, rsp
0x14000d4af  mov     [rsp+0E8h+var_28], rax
0x14000d4b7  movzx   eax, byte ptr [rcx-0C60h]
0x14000d4be  lea     rdi, [rcx-0D58h]
0x14000d4c5  mov     r14d, edx
0x14000d4c8  mov     esi, edx
0x14000d4ca  and     r14d, 0Ch
0x14000d4ce  mov     rbx, rcx
0x14000d4d1  test    al, 30h
0x14000d4d3  jz      short loc_14000D4E3
0x14000d4d5  test    al, 40h
0x14000d4d7  jnz     short loc_14000D4DE
0x14000d4d9  test    r14d, r14d
0x14000d4dc  jnz     short loc_14000D4E3
0x14000d4de  xor     bpl, bpl
0x14000d4e1  jmp     short loc_14000D4E6
0x14000d4e3  mov     bpl, 1
0x14000d4e6  test    sil, 1
0x14000d4ea  jz      short loc_14000D501
0x14000d4ec  test    byte ptr [rcx], 2
0x14000d4ef  jz      short loc_14000D501
0x14000d4f1  mov     edx, 1
0x14000d4f6  mov     rcx, rdi
0x14000d4f9  call    QuicConnTimerCancel
0x14000d4fe  and     byte ptr [rbx], 0FDh
0x14000d501  test    bpl, bpl
0x14000d504  jz      loc_14000D5E2
0x14000d50a  mov     ecx, [rbx+48h]
0x14000d50d  mov     eax, ecx
0x14000d50f  and     eax, esi
0x14000d511  cmp     eax, esi
0x14000d513  jz      loc_14000D5E2
0x14000d519  test    cs:byte_14005C48C, 1
0x14000d520  jz      short loc_14000D56A
0x14000d522  mov     eax, ecx
0x14000d524  lea     r9, aAddingSendFlag; "Adding send flags 0x%x (prev: 0x%x, new"...
0x14000d52b  or      eax, esi
0x14000d52d  mov     edx, 80h; SizeInBytes
0x14000d532  mov     [rsp+0E8h+var_B8], eax
0x14000d536  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000d53d  mov     [rsp+0E8h+var_C0], ecx
0x14000d541  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x14000d546  mov     [rsp+0E8h+var_C8], esi
0x14000d54a  call    cs:__imp__snprintf_s
0x14000d551  nop     dword ptr [rax+rax+00h]
0x14000d556  lea     r9, [rsp+0E8h+DstBuf]
0x14000d55b  mov     r8, rdi
0x14000d55e  lea     rdx, QuicConnLogVerbose
0x14000d565  call    McTemplateU0ps_EtwWriteTransfer
0x14000d56a  or      [rbx+48h], esi
0x14000d56d  test    byte ptr [rbx], 1
0x14000d570  jnz     short loc_14000D5E2
0x14000d572  mov     rcx, rbx
0x14000d575  call    QuicSendCanSendFlagsNow
0x14000d57a  test    al, al
0x14000d57c  jz      short loc_14000D5E2
0x14000d57e  mov     rcx, [rdi+48h]
0x14000d582  add     rcx, 7E0h
0x14000d589  call    CxPlatPoolAlloc
0x14000d58e  mov     rsi, rax
0x14000d591  test    rax, rax
0x14000d594  jz      short loc_14000D5E2
0x14000d596  mov     dword ptr [rax+10h], 4
0x14000d59d  mov     byte ptr [rax+14h], 1
0x14000d5a1  or      byte ptr [rbx], 1
0x14000d5a4  test    cs:byte_14005C48A, 1
0x14000d5ab  jz      short loc_14000D5BF
0x14000d5ad  xor     r9d, r9d
0x14000d5b0  lea     rdx, QuicConnQueueSendFlush
0x14000d5b7  mov     r8, rdi
0x14000d5ba  call    McTemplateU0pq_EtwWriteTransfer
0x14000d5bf  mov     rdx, [rdi+48h]
0x14000d5c3  lea     rcx, [rdi+590h]
0x14000d5ca  mov     r8, rsi
0x14000d5cd  call    QuicOperationEnqueue
0x14000d5d2  test    al, al
0x14000d5d4  jz      short loc_14000D5E2
0x14000d5d6  mov     rcx, [rdi+40h]
0x14000d5da  mov     rdx, rdi
0x14000d5dd  call    QuicWorkerQueueConnection
0x14000d5e2  test    r14d, r14d
0x14000d5e5  jz      short loc_14000D603
0x14000d5e7  call    QuicTimePlat
0x14000d5ec  mov     rcx, rax
0x14000d5ef  call    QuicTimePlatToUs64
0x14000d5f4  mov     rcx, rbx
0x14000d5f7  mov     [rdi+560h], rax
0x14000d5fe  call    QuicSendClear
0x14000d603  movzx   eax, bpl
0x14000d607  mov     rcx, [rsp+0E8h+var_28]
0x14000d60f  xor     rcx, rsp; StackCookie
0x14000d612  call    __security_check_cookie
0x14000d617  lea     r11, [rsp+0E8h+var_18]
0x14000d61f  mov     rbx, [r11+30h]
0x14000d623  mov     rbp, [r11+38h]
0x14000d627  mov     rsp, r11
0x14000d62a  pop     r14
0x14000d62c  pop     rdi
0x14000d62d  pop     rsi
0x14000d62e  retn
```
