# QuicStreamOnLoss

- ea: `0x14001ec64`
- end: `0x14001eeda`
- name: `QuicStreamOnLoss`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001e3b0`

## callees

- `0x14000b27c`
- `0x14000b60c`
- `0x14000d230`
- `0x14000d428`
- `0x14001ec64`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001eced`
- `ntoskrnl!_snprintf_s` at `0x14001ed39`
- `ntoskrnl!_snprintf_s` at `0x14001ee16`
- `ntoskrnl!_snprintf_s` at `0x14001eced`
- `ntoskrnl!_snprintf_s` at `0x14001ed39`
- `ntoskrnl!_snprintf_s` at `0x14001ee16`

## string_xrefs

- `0x14001ecdb`: `Recovering open STREAM frame`

## pseudocode

```c
char __fastcall QuicStreamOnLoss(__int64 a1, __int64 a2)
{
  char v4; // cl
  unsigned __int64 v5; // r14
  unsigned int v6; // ebx
  unsigned __int64 v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned int v11; // r8d
  __int64 v12; // rax
  unsigned __int64 *v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  char v16; // al
  __int64 v17; // rcx
  char v19; // al
  char v20; // bl
  _QWORD v21[2]; // [rsp+30h] [rbp-89h] BYREF
  __int128 v22; // [rsp+40h] [rbp-79h]
  int v23; // [rsp+50h] [rbp-69h]
  char DstBuf[128]; // [rsp+60h] [rbp-59h] BYREF

  v4 = *(_BYTE *)(a1 + 89);
  if ( (v4 & 0x10) != 0 || (v4 & 0x40) != 0 && *(_QWORD *)(a1 + 216) >= *(_QWORD *)(a1 + 248) )
    return 0;
  v5 = *(_QWORD *)(a2 + 8);
  v6 = 0;
  v7 = v5 + *(unsigned __int16 *)(a2 + 16);
  if ( (*(_BYTE *)(a2 + 20) & 1) != 0 && (v4 & 2) == 0 )
  {
    v6 = 32;
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Recovering open STREAM frame");
      McTemplateU0ps_EtwWriteTransfer(v8, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
    }
  }
  if ( (*(_BYTE *)(a2 + 20) & 2) != 0 && (*(_BYTE *)(a1 + 90) & 4) == 0 )
  {
    v6 |= 0x40u;
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Recovering fin STREAM frame");
      McTemplateU0ps_EtwWriteTransfer(v9, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
    }
  }
  v10 = *(_QWORD *)(a1 + 216);
  if ( v7 > v10 )
  {
    if ( v5 < v10 )
      v5 = *(_QWORD *)(a1 + 216);
    v11 = 0;
    while ( v11 < *(_DWORD *)(a1 + 272) )
    {
      v12 = v11++;
      v13 = (unsigned __int64 *)(*(_QWORD *)(a1 + 264) + 16 * v12);
      if ( !v13 )
        break;
      v14 = *v13;
      if ( *v13 >= v7 )
        break;
      v15 = v14 + v13[1];
      if ( v5 < v15 )
      {
        if ( v5 < v14 )
        {
          if ( v7 <= v15 )
            v7 = *v13;
        }
        else
        {
          if ( v7 <= v15 )
            goto LABEL_33;
          v5 = v14 + v13[1];
        }
      }
    }
    v16 = 0;
    if ( v5 < *(_QWORD *)(a1 + 232) )
    {
      *(_QWORD *)(a1 + 232) = v5;
      v16 = 1;
    }
    if ( *(_QWORD *)(a1 + 240) >= v7 )
    {
      if ( !v16 )
        goto LABEL_33;
    }
    else
    {
      *(_QWORD *)(a1 + 240) = v7;
    }
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Recovering offset %llu up to %llu", v5, v7);
      McTemplateU0ps_EtwWriteTransfer(v17, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
    }
    v6 |= 0x10u;
  }
LABEL_33:
  if ( !v6 )
    return 0;
  if ( (*(_BYTE *)(a1 + 92) & 1) != 0 )
  {
    v23 = 0;
    v21[1] = 0;
    v21[0] = 10;
    v22 = 0;
    QuicStreamIndicateEvent(a1, v21);
    QuicStreamShutdown(a1, 6);
    return 0;
  }
  v19 = *(_BYTE *)(a1 + 90);
  if ( (v19 & 8) == 0 )
    *(_BYTE *)(a1 + 90) = v19 | 8;
  v20 = QuicSendSetStreamSendFlag(*(_QWORD *)(a1 + 72) + 3416LL, a1, v6);
  QuicStreamSendDumpState(a1);
  return v20;
}

```

## disassembly

```asm
0x14001ec64  mov     [rsp-8+arg_10], rbx
0x14001ec69  push    rbp
0x14001ec6a  push    rsi
0x14001ec6b  push    rdi
0x14001ec6c  push    r14
0x14001ec6e  push    r15
0x14001ec70  lea     rbp, [rsp-37h]
0x14001ec75  sub     rsp, 0F0h
0x14001ec7c  mov     rax, cs:__security_cookie
0x14001ec83  xor     rax, rsp
0x14001ec86  mov     [rbp+57h+var_30], rax
0x14001ec8a  mov     rdi, rcx
0x14001ec8d  mov     r15, rdx
0x14001ec90  mov     cl, [rcx+59h]
0x14001ec93  test    cl, 10h
0x14001ec96  jnz     loc_14001EE81
0x14001ec9c  test    cl, 40h
0x14001ec9f  jz      short loc_14001ECB5
0x14001eca1  mov     rax, [rdi+0F8h]
0x14001eca8  cmp     [rdi+0D8h], rax
0x14001ecaf  jnb     loc_14001EE81
0x14001ecb5  mov     r14, [rdx+8]
0x14001ecb9  xor     ebx, ebx
0x14001ecbb  movzx   esi, word ptr [rdx+10h]
0x14001ecbf  add     rsi, r14
0x14001ecc2  test    byte ptr [rdx+14h], 1
0x14001ecc6  jz      short loc_14001ED0C
0x14001ecc8  test    cl, 2
0x14001eccb  jnz     short loc_14001ED0C
0x14001eccd  test    cs:byte_14005C48D, 1
0x14001ecd4  mov     ebx, 20h ; ' '
0x14001ecd9  jz      short loc_14001ED0C
0x14001ecdb  lea     r9, aRecoveringOpen; "Recovering open STREAM frame"
0x14001ece2  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001ece6  lea     edx, [rbx+60h]; SizeInBytes
0x14001ece9  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14001eced  call    cs:__imp__snprintf_s
0x14001ecf4  nop     dword ptr [rax+rax+00h]
0x14001ecf9  lea     r9, [rbp+57h+DstBuf]
0x14001ecfd  mov     r8, rdi
0x14001ed00  lea     rdx, QuicStreamLogVerbose
0x14001ed07  call    McTemplateU0ps_EtwWriteTransfer
0x14001ed0c  test    byte ptr [r15+14h], 2
0x14001ed11  jz      short loc_14001ED58
0x14001ed13  test    byte ptr [rdi+5Ah], 4
0x14001ed17  jnz     short loc_14001ED58
0x14001ed19  or      ebx, 40h
0x14001ed1c  test    cs:byte_14005C48D, 1
0x14001ed23  jz      short loc_14001ED58
0x14001ed25  lea     r9, aRecoveringFinS; "Recovering fin STREAM frame"
0x14001ed2c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001ed30  mov     edx, 80h; SizeInBytes
0x14001ed35  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14001ed39  call    cs:__imp__snprintf_s
0x14001ed40  nop     dword ptr [rax+rax+00h]
0x14001ed45  lea     r9, [rbp+57h+DstBuf]
0x14001ed49  mov     r8, rdi
0x14001ed4c  lea     rdx, QuicStreamLogVerbose
0x14001ed53  call    McTemplateU0ps_EtwWriteTransfer
0x14001ed58  mov     rax, [rdi+0D8h]
0x14001ed5f  cmp     rsi, rax
0x14001ed62  jbe     loc_14001EE38
0x14001ed68  mov     r9d, [rdi+110h]
0x14001ed6f  cmp     r14, rax
0x14001ed72  cmovb   r14, rax
0x14001ed76  xor     r8d, r8d
0x14001ed79  cmp     r8d, r9d
0x14001ed7c  jnb     short loc_14001EDC5
0x14001ed7e  mov     eax, r8d
0x14001ed81  inc     r8d
0x14001ed84  shl     rax, 4
0x14001ed88  add     rax, [rdi+108h]
0x14001ed8f  test    rax, rax
0x14001ed92  jz      short loc_14001EDC5
0x14001ed94  mov     rcx, [rax]
0x14001ed97  cmp     rcx, rsi
0x14001ed9a  jnb     short loc_14001EDC5
0x14001ed9c  mov     rdx, [rax+8]
0x14001eda0  add     rdx, rcx
0x14001eda3  cmp     r14, rdx
0x14001eda6  jnb     short loc_14001ED79
0x14001eda8  cmp     r14, rcx
0x14001edab  jb      short loc_14001EDBB
0x14001edad  cmp     rsi, rdx
0x14001edb0  jbe     loc_14001EE38
0x14001edb6  mov     r14, rdx
0x14001edb9  jmp     short loc_14001ED79
0x14001edbb  cmp     rsi, rdx
0x14001edbe  ja      short loc_14001ED79
0x14001edc0  mov     rsi, rcx
0x14001edc3  jmp     short loc_14001ED79
0x14001edc5  xor     al, al
0x14001edc7  cmp     r14, [rdi+0E8h]
0x14001edce  jnb     short loc_14001EDD9
0x14001edd0  mov     [rdi+0E8h], r14
0x14001edd7  mov     al, 1
0x14001edd9  cmp     [rdi+0F0h], rsi
0x14001ede0  jnb     short loc_14001EDEB
0x14001ede2  mov     [rdi+0F0h], rsi
0x14001ede9  jmp     short loc_14001EDEF
0x14001edeb  test    al, al
0x14001eded  jz      short loc_14001EE38
0x14001edef  test    cs:byte_14005C48D, 1
0x14001edf6  jz      short loc_14001EE35
0x14001edf8  mov     [rsp+110h+var_E8], rsi
0x14001edfd  lea     r9, aRecoveringOffs; "Recovering offset %llu up to %llu"
0x14001ee04  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001ee08  mov     [rsp+110h+var_F0], r14
0x14001ee0d  mov     edx, 80h; SizeInBytes
0x14001ee12  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x14001ee16  call    cs:__imp__snprintf_s
0x14001ee1d  nop     dword ptr [rax+rax+00h]
0x14001ee22  lea     r9, [rbp+57h+DstBuf]
0x14001ee26  mov     r8, rdi
0x14001ee29  lea     rdx, QuicStreamLogVerbose
0x14001ee30  call    McTemplateU0ps_EtwWriteTransfer
0x14001ee35  or      ebx, 10h
0x14001ee38  test    ebx, ebx
0x14001ee3a  jz      short loc_14001EE81
0x14001ee3c  test    byte ptr [rdi+5Ch], 1
0x14001ee40  jz      short loc_14001EEA7
0x14001ee42  and     [rbp+57h+var_C0], 0
0x14001ee46  lea     rdx, [rsp+110h+var_E0]
0x14001ee4b  and     [rsp+110h+var_D8], 0
0x14001ee51  xorps   xmm0, xmm0
0x14001ee54  mov     [rsp+110h+var_E0], 0Ah
0x14001ee5d  mov     rcx, rdi
0x14001ee60  and     dword ptr [rsp+110h+var_E0+4], 0
0x14001ee65  movdqu  [rbp+57h+var_D0], xmm0
0x14001ee6a  call    QuicStreamIndicateEvent
0x14001ee6f  mov     r8, [rsp+110h+var_D8]
0x14001ee74  mov     edx, 6
0x14001ee79  mov     rcx, rdi
0x14001ee7c  call    QuicStreamShutdown
0x14001ee81  xor     al, al
0x14001ee83  mov     rcx, [rbp+57h+var_30]
0x14001ee87  xor     rcx, rsp; StackCookie
0x14001ee8a  call    __security_check_cookie
0x14001ee8f  mov     rbx, [rsp+110h+arg_10]
0x14001ee97  add     rsp, 0F0h
0x14001ee9e  pop     r15
0x14001eea0  pop     r14
0x14001eea2  pop     rdi
0x14001eea3  pop     rsi
0x14001eea4  pop     rbp
0x14001eea5  retn
0x14001eea7  mov     al, [rdi+5Ah]
0x14001eeaa  test    al, 8
0x14001eeac  jnz     short loc_14001EEB3
0x14001eeae  or      al, 8
0x14001eeb0  mov     [rdi+5Ah], al
0x14001eeb3  mov     rcx, [rdi+48h]
0x14001eeb7  xor     r9d, r9d
0x14001eeba  add     rcx, 0D58h
0x14001eec1  mov     r8d, ebx
0x14001eec4  mov     rdx, rdi
0x14001eec7  call    QuicSendSetStreamSendFlag
0x14001eecc  mov     rcx, rdi
0x14001eecf  mov     bl, al
0x14001eed1  call    QuicStreamSendDumpState
0x14001eed6  mov     al, bl
0x14001eed8  jmp     short loc_14001EE83
```
