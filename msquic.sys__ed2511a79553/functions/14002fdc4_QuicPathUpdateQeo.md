# QuicPathUpdateQeo

- ea: `0x14002fdc4`
- end: `0x14003003b`
- name: `QuicPathUpdateQeo`
- size: `631`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400099b4`
- `0x14001d88c`

## callees

- `0x14002fdc4`
- `0x1400385c0`
- `0x140039090`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14002ff95`
- `ntoskrnl!_snprintf_s` at `0x14002fff1`
- `ntoskrnl!_snprintf_s` at `0x14002ff95`
- `ntoskrnl!_snprintf_s` at `0x14002fff1`

## string_xrefs

- `0x14002ff7d`: `Path[%hhu] QEO enabled`
- `0x14002ffd9`: `Path[%hhu] QEO disabled`

## pseudocode

```c
char __fastcall QuicPathUpdateQeo(__int64 a1, unsigned __int8 *a2, int a3)
{
  __int64 v3; // rsi
  __int64 v4; // xmm1_8
  __int64 v6; // r14
  unsigned int v9; // ebx
  int v10; // edi
  __int128 v11; // xmm0
  int v12; // eax
  __int64 v13; // xmm1_8
  unsigned int v14; // edi
  __int64 v15; // r8
  _DWORD *v16; // rdx
  __int64 v17; // rdi
  unsigned __int8 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rcx
  char result; // al
  __int64 v24; // rcx
  _OWORD v25[18]; // [rsp+30h] [rbp-D0h] BYREF
  char DstBuf[128]; // [rsp+150h] [rbp+50h] BYREF

  v3 = *((_QWORD *)a2 + 18);
  v4 = *((_QWORD *)a2 + 9);
  v6 = *(_QWORD *)(a1 + 1280);
  v25[1] = *(_OWORD *)(a2 + 56);
  v9 = *(unsigned __int8 *)(v3 + 33);
  v10 = a3 & 1;
  *(_QWORD *)&v25[2] = v4;
  BYTE12(v25[2]) = v9;
  LODWORD(v25[0]) = v10 | 0x10000;
  *((_QWORD *)&v25[0] + 1) = *(_QWORD *)(a1 + 3424);
  DWORD2(v25[2]) = *((_DWORD *)a2 + 20);
  memset((char *)&v25[2] + 13, 0, 0x63u);
  v11 = *(_OWORD *)(a2 + 84);
  v12 = *((_DWORD *)a2 + 27);
  v13 = *(_QWORD *)(a2 + 100);
  *((_QWORD *)&v25[9] + 1) = 0;
  LODWORD(v25[9]) = v10 | 0x10002;
  v14 = *(unsigned __int8 *)(v6 + 17);
  v25[10] = v11;
  *(_QWORD *)&v25[11] = v13;
  DWORD2(v25[11]) = v12;
  BYTE12(v25[11]) = v14;
  memset((char *)&v25[11] + 13, 0, 0x63u);
  memmove((char *)&v25[2] + 13, (const void *)(v3 + 48), v9);
  memmove((char *)&v25[11] + 13, (const void *)(v6 + 32), v14);
  if ( a3 )
  {
    a2[2] &= ~0x20u;
    result = byte_14005C48B;
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Path[%hhu] QEO disabled", *a2);
      return McTemplateU0ps_EtwWriteTransfer(v24, QuicConnLogInfo, a1, DstBuf);
    }
  }
  else
  {
    v15 = *(_QWORD *)(a1 + 2776);
    v16 = v25;
    v17 = 2;
    v18 = 8 * *(_BYTE *)(v15 + 424);
    do
    {
      *v16 ^= (v18 ^ (unsigned __int8)*v16) & 8;
      v16 += 36;
      --v17;
    }
    while ( v17 );
    v19 = *(_QWORD *)(a1 + 2944);
    v20 = *(_QWORD *)(a1 + 2792);
    *((_QWORD *)&v25[9] + 1) = *(_QWORD *)(v15 + 376);
    if ( (unsigned __int8)QuicTlsPopulateOffloadKeys(v20, v19, v15, v25)
      && (unsigned __int8)QuicTlsPopulateOffloadKeys(*(_QWORD *)(a1 + 2792), *(_QWORD *)(a1 + 2896), v21, &v25[9])
      && (int)CxPlatSocketUpdateQeo(*(_QWORD *)(*((_QWORD *)a2 + 5) + 32LL), v25) >= 0 )
    {
      *(_DWORD *)(a1 + 3632) |= 0x20u;
      a2[2] |= 0x20u;
      if ( byte_14005C48B < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Path[%hhu] QEO enabled", *a2);
        McTemplateU0ps_EtwWriteTransfer(v22, QuicConnLogInfo, a1, DstBuf);
      }
    }
    result = 0;
    memset(v25, 0, sizeof(v25));
  }
  return result;
}

```

## disassembly

```asm
0x14002fdc4  mov     [rsp-8+arg_18], rbx
0x14002fdc9  push    rbp
0x14002fdca  push    rsi
0x14002fdcb  push    rdi
0x14002fdcc  push    r12
0x14002fdce  push    r13
0x14002fdd0  push    r14
0x14002fdd2  push    r15
0x14002fdd4  lea     rbp, [rsp-0E0h]
0x14002fddc  sub     rsp, 1E0h
0x14002fde3  mov     rax, cs:__security_cookie
0x14002fdea  xor     rax, rsp
0x14002fded  mov     [rbp+110h+var_40], rax
0x14002fdf4  movups  xmm0, xmmword ptr [rdx+38h]
0x14002fdf8  mov     edi, r8d
0x14002fdfb  mov     rsi, [rdx+90h]
0x14002fe02  movsd   xmm1, qword ptr [rdx+48h]
0x14002fe07  mov     r12, rdx
0x14002fe0a  mov     r14, [rcx+500h]
0x14002fe11  mov     r15d, r8d
0x14002fe14  mov     r13, rcx
0x14002fe17  movaps  [rsp+210h+var_1D0], xmm0
0x14002fe1c  movzx   ebx, byte ptr [rsi+21h]
0x14002fe20  and     edi, 1
0x14002fe23  mov     eax, edi
0x14002fe25  movsd   [rsp+210h+var_1C0], xmm1
0x14002fe2b  bts     eax, 10h
0x14002fe2f  mov     [rsp+210h+var_1B4], bl
0x14002fe33  mov     [rsp+210h+var_1E0], eax
0x14002fe37  mov     rax, [rcx+0D60h]
0x14002fe3e  lea     rcx, [rsp+210h+var_1B3]; void *
0x14002fe43  mov     [rsp+210h+var_1D8], rax
0x14002fe48  mov     eax, [rdx+50h]
0x14002fe4b  xor     edx, edx; Val
0x14002fe4d  mov     [rsp+210h+var_1B8], eax
0x14002fe51  lea     r8d, [rdx+63h]; Size
0x14002fe55  call    memset
0x14002fe5a  movups  xmm0, xmmword ptr [r12+54h]
0x14002fe60  lea     rcx, [rbp+110h+var_123]; void *
0x14002fe64  mov     eax, [r12+6Ch]
0x14002fe69  movsd   xmm1, qword ptr [r12+64h]
0x14002fe70  xor     edx, edx; Val
0x14002fe72  and     [rbp+110h+var_148], 0
0x14002fe77  or      edi, 10002h
0x14002fe7d  mov     [rbp+110h+var_150], edi
0x14002fe80  movzx   edi, byte ptr [r14+11h]
0x14002fe85  lea     r8d, [rdx+63h]; Size
0x14002fe89  movaps  [rbp+110h+var_140], xmm0
0x14002fe8d  movsd   [rbp+110h+var_130], xmm1
0x14002fe92  mov     [rbp+110h+var_128], eax
0x14002fe95  mov     [rbp+110h+var_124], dil
0x14002fe99  call    memset
0x14002fe9e  mov     r8d, ebx; Size
0x14002fea1  lea     rdx, [rsi+30h]; Src
0x14002fea5  lea     rcx, [rsp+210h+var_1B3]; void *
0x14002feaa  call    memmove
0x14002feaf  mov     r8d, edi; Size
0x14002feb2  lea     rdx, [r14+20h]; Src
0x14002feb6  lea     rcx, [rbp+110h+var_123]; void *
0x14002feba  call    memmove
0x14002febf  test    r15d, r15d
0x14002fec2  jnz     loc_14002FFC4
0x14002fec8  mov     r8, [r13+0AD8h]
0x14002fecf  lea     rdx, [rsp+210h+var_1E0]
0x14002fed4  lea     edi, [r15+2]
0x14002fed8  movzx   eax, byte ptr [r8+1A8h]
0x14002fee0  lea     r9d, ds:0[rax*8]
0x14002fee8  mov     eax, [rdx]
0x14002feea  mov     ecx, eax
0x14002feec  xor     ecx, r9d
0x14002feef  and     ecx, 8
0x14002fef2  xor     ecx, eax
0x14002fef4  mov     [rdx], ecx
0x14002fef6  lea     rdx, [rdx+90h]
0x14002fefd  sub     rdi, 1
0x14002ff01  jnz     short loc_14002FEE8
0x14002ff03  mov     rax, [r8+178h]
0x14002ff0a  lea     r9, [rsp+210h+var_1E0]
0x14002ff0f  mov     rdx, [r13+0B80h]
0x14002ff16  mov     rcx, [r13+0AE8h]
0x14002ff1d  mov     [rbp+110h+var_148], rax
0x14002ff21  call    QuicTlsPopulateOffloadKeys
0x14002ff26  test    al, al
0x14002ff28  jz      loc_14002FFB4
0x14002ff2e  mov     rdx, [r13+0B50h]
0x14002ff35  lea     r9, [rbp+110h+var_150]
0x14002ff39  mov     rcx, [r13+0AE8h]
0x14002ff40  call    QuicTlsPopulateOffloadKeys
0x14002ff45  test    al, al
0x14002ff47  jz      short loc_14002FFB4
0x14002ff49  mov     rcx, [r12+28h]
0x14002ff4e  lea     rdx, [rsp+210h+var_1E0]
0x14002ff53  mov     rcx, [rcx+20h]
0x14002ff57  call    CxPlatSocketUpdateQeo
0x14002ff5c  test    eax, eax
0x14002ff5e  js      short loc_14002FFB4
0x14002ff60  or      dword ptr [r13+0E30h], 20h
0x14002ff68  or      byte ptr [r12+2], 20h
0x14002ff6e  mov     al, cs:byte_14005C48B
0x14002ff74  test    al, al
0x14002ff76  jns     short loc_14002FFB4
0x14002ff78  movzx   eax, byte ptr [r12]
0x14002ff7d  lea     r9, aPathHhuQeoEnab; "Path[%hhu] QEO enabled"
0x14002ff84  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002ff88  mov     [rsp+210h+var_1F0], eax
0x14002ff8c  mov     edx, 80h; SizeInBytes
0x14002ff91  lea     rcx, [rbp+110h+DstBuf]; DstBuf
0x14002ff95  call    cs:__imp__snprintf_s
0x14002ff9c  nop     dword ptr [rax+rax+00h]
0x14002ffa1  lea     r9, [rbp+110h+DstBuf]
0x14002ffa5  mov     r8, r13
0x14002ffa8  lea     rdx, QuicConnLogInfo
0x14002ffaf  call    McTemplateU0ps_EtwWriteTransfer
0x14002ffb4  lea     rdi, [rsp+210h+var_1E0]
0x14002ffb9  xor     eax, eax
0x14002ffbb  mov     ecx, 120h
0x14002ffc0  rep stosb
0x14002ffc2  jmp     short loc_140030010
0x14002ffc4  and     byte ptr [r12+2], 0DFh
0x14002ffca  mov     al, cs:byte_14005C48B
0x14002ffd0  test    al, al
0x14002ffd2  jns     short loc_140030010
0x14002ffd4  movzx   eax, byte ptr [r12]
0x14002ffd9  lea     r9, aPathHhuQeoDisa; "Path[%hhu] QEO disabled"
0x14002ffe0  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002ffe4  mov     [rsp+210h+var_1F0], eax
0x14002ffe8  mov     edx, 80h; SizeInBytes
0x14002ffed  lea     rcx, [rbp+110h+DstBuf]; DstBuf
0x14002fff1  call    cs:__imp__snprintf_s
0x14002fff8  nop     dword ptr [rax+rax+00h]
0x14002fffd  lea     r9, [rbp+110h+DstBuf]
0x140030001  mov     r8, r13
0x140030004  lea     rdx, QuicConnLogInfo
0x14003000b  call    McTemplateU0ps_EtwWriteTransfer
0x140030010  mov     rcx, [rbp+110h+var_40]
0x140030017  xor     rcx, rsp; StackCookie
0x14003001a  call    __security_check_cookie
0x14003001f  mov     rbx, [rsp+210h+arg_18]
0x140030027  add     rsp, 1E0h
0x14003002e  pop     r15
0x140030030  pop     r14
0x140030032  pop     r13
0x140030034  pop     r12
0x140030036  pop     rdi
0x140030037  pop     rsi
0x140030038  pop     rbp
0x140030039  retn
```
