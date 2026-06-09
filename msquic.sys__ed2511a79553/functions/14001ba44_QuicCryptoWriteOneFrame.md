# QuicCryptoWriteOneFrame

- ea: `0x14001ba44`
- end: `0x14001bbc1`
- name: `QuicCryptoWriteOneFrame`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001b7ec`

## callees

- `0x140019ecc`
- `0x14001ba44`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003dc1e`
- `ntoskrnl!_snprintf_s` at `0x14003dc85`
- `ntoskrnl!_snprintf_s` at `0x14003dc1e`
- `ntoskrnl!_snprintf_s` at `0x14003dc85`

## pseudocode

```c
char __fastcall QuicCryptoWriteOneFrame(
        __int64 a1,
        int a2,
        unsigned int a3,
        _WORD *a4,
        unsigned __int16 *a5,
        unsigned __int16 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rbp
  unsigned __int64 v11; // rdx
  int v12; // ecx
  int v13; // r9d
  int v14; // r8d
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  char result; // al
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // [rsp+30h] [rbp-D8h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-D0h]
  __int64 v23; // [rsp+40h] [rbp-C8h]
  char DstBuf[128]; // [rsp+50h] [rbp-B8h] BYREF

  v8 = a1 - 2784;
  v21 = a3 - a2;
  v11 = 2;
  v23 = *(_QWORD *)(a1 + 56) + a3 + *(unsigned __int16 *)(a1 + 34) - *(_DWORD *)(a1 + 40);
  if ( a3 < 0x40 )
  {
    v12 = 2;
  }
  else if ( a3 >= 0x4000 )
  {
    v12 = a3 < 0x40000000 ? 5 : 9;
  }
  else
  {
    v12 = 3;
  }
  v13 = *a5;
  if ( a6 < (unsigned int)(v12 + v13 + 4) )
  {
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "No room for CRYPTO frame");
      McTemplateU0ps_EtwWriteTransfer(v19, (const EVENT_DESCRIPTOR *)QuicConnLogVerbose, v8, DstBuf);
    }
    return 0;
  }
  else
  {
    v14 = a6 - v13 - v12;
    if ( (unsigned __int64)v14 < 0x40 )
    {
      v11 = 1;
    }
    else if ( (unsigned __int64)v14 >= 0x4000 )
    {
      v11 = (-(__int64)((unsigned __int64)v14 < 0x40000000) & 0xFFFFFFFFFFFFFFFCuLL) + 8;
    }
    v15 = v14 - v11;
    if ( v15 > (unsigned __int16)*a4 )
      v15 = (unsigned __int16)*a4;
    *a4 = v15;
    v22 = v15;
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Sending %hu crypto bytes, offset=%u",
        (unsigned __int16)v15,
        a3);
      McTemplateU0ps_EtwWriteTransfer(v20, (const EVENT_DESCRIPTOR *)QuicConnLogVerbose, v8, DstBuf);
    }
    if ( !(unsigned __int8)QuicCryptoFrameEncode(&v21, a5, a6, a7) )
    {
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
        689,
        "QuicCryptoFrameEncode(&Frame, Offset, BufferLength, Buffer)");
      __int2c();
    }
    v16 = *(unsigned __int8 *)(a8 + 90);
    *(_BYTE *)(a8 + 88) |= 4u;
    v17 = 3 * v16;
    result = 1;
    *(_WORD *)(a8 + 8 * v17 + 114) = 6;
    *(_DWORD *)(a8 + 24 * (*(unsigned __int8 *)(a8 + 90) + 4LL)) = a3;
    *(_WORD *)(a8 + 24LL * *(unsigned __int8 *)(a8 + 90) + 100) = v22;
    *(_BYTE *)(a8 + 24LL * (unsigned __int8)(*(_BYTE *)(a8 + 90))++ + 116) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001ba44  push    rbx
0x14001ba46  push    rbp
0x14001ba47  push    rsi
0x14001ba48  push    rdi
0x14001ba49  push    r14
0x14001ba4b  sub     rsp, 0E0h
0x14001ba52  mov     rax, cs:__security_cookie
0x14001ba59  xor     rax, rsp
0x14001ba5c  mov     [rsp+108h+var_38], rax
0x14001ba64  mov     rsi, [rsp+108h+arg_20]
0x14001ba6c  lea     rbp, [rcx-0AE0h]
0x14001ba73  mov     r14, [rsp+108h+arg_30]
0x14001ba7b  mov     eax, r8d
0x14001ba7e  mov     rbx, [rsp+108h+arg_38]
0x14001ba86  sub     eax, edx
0x14001ba88  mov     [rsp+108h+var_D8], rax
0x14001ba8d  mov     r10, r9
0x14001ba90  movzx   eax, word ptr [rcx+22h]
0x14001ba94  mov     edi, r8d
0x14001ba97  sub     eax, [rcx+28h]
0x14001ba9a  mov     edx, 2
0x14001ba9f  add     eax, r8d
0x14001baa2  mov     r11d, 4000h
0x14001baa8  add     rax, [rcx+38h]
0x14001baac  mov     [rsp+108h+var_C8], rax
0x14001bab1  cmp     r8d, 40h ; '@'
0x14001bab5  jb      loc_14001BBA9
0x14001babb  cmp     r8d, r11d
0x14001babe  jnb     loc_14003DBF6
0x14001bac4  lea     ecx, [rdx+1]
0x14001bac7  movzx   r9d, word ptr [rsi]
0x14001bacb  movzx   r8d, [rsp+108h+arg_28]
0x14001bad4  lea     eax, [r9+4]
0x14001bad8  add     eax, ecx
0x14001bada  cmp     r8d, eax
0x14001badd  jb      loc_14001BBB0
0x14001bae3  sub     r8d, r9d
0x14001bae6  sub     r8d, ecx
0x14001bae9  movsxd  rcx, r8d
0x14001baec  cmp     rcx, 40h ; '@'
0x14001baf0  jb      loc_14003DC44
0x14001baf6  cmp     rcx, r11
0x14001baf9  jnb     loc_14003DC4E
0x14001baff  movzx   eax, word ptr [r10]
0x14001bb03  sub     rcx, rdx
0x14001bb06  cmp     rcx, rax
0x14001bb09  cmova   rcx, rax
0x14001bb0d  mov     [r10], cx
0x14001bb11  test    cs:byte_14005C48C, 1
0x14001bb18  mov     [rsp+108h+var_D0], rcx
0x14001bb1d  jnz     loc_14003DC65
0x14001bb23  movzx   r8d, [rsp+108h+arg_28]
0x14001bb2c  lea     rcx, [rsp+108h+var_D8]
0x14001bb31  mov     r9, r14
0x14001bb34  mov     rdx, rsi
0x14001bb37  call    QuicCryptoFrameEncode
0x14001bb3c  test    al, al
0x14001bb3e  jz      loc_14003DCAB
0x14001bb44  movzx   eax, byte ptr [rbx+5Ah]
0x14001bb48  or      byte ptr [rbx+58h], 4
0x14001bb4c  lea     rcx, [rax+rax*2]
0x14001bb50  mov     al, 1
0x14001bb52  mov     word ptr [rbx+rcx*8+72h], 6
0x14001bb59  movzx   ecx, byte ptr [rbx+5Ah]
0x14001bb5d  add     rcx, 4
0x14001bb61  lea     rcx, [rcx+rcx*2]
0x14001bb65  mov     [rbx+rcx*8], edi
0x14001bb68  movzx   ecx, byte ptr [rbx+5Ah]
0x14001bb6c  lea     rdx, [rcx+rcx*2]
0x14001bb70  movzx   ecx, word ptr [rsp+108h+var_D0]
0x14001bb75  mov     [rbx+rdx*8+64h], cx
0x14001bb7a  movzx   ecx, byte ptr [rbx+5Ah]
0x14001bb7e  lea     rdx, [rcx+rcx*2]
0x14001bb82  mov     byte ptr [rbx+rdx*8+74h], 0
0x14001bb87  inc     byte ptr [rbx+5Ah]
0x14001bb8a  mov     rcx, [rsp+108h+var_38]
0x14001bb92  xor     rcx, rsp; StackCookie
0x14001bb95  call    __security_check_cookie
0x14001bb9a  add     rsp, 0E0h
0x14001bba1  pop     r14
0x14001bba3  pop     rdi
0x14001bba4  pop     rsi
0x14001bba5  pop     rbp
0x14001bba6  pop     rbx
0x14001bba7  retn
0x14001bba9  mov     ecx, edx
0x14001bbab  jmp     loc_14001BAC7
0x14001bbb0  test    cs:byte_14005C48C, 1
0x14001bbb7  jnz     loc_14003DC09
0x14001bbbd  xor     al, al
0x14001bbbf  jmp     short loc_14001BB8A
0x14003dbf6  cmp     edi, 40000000h
0x14003dbfc  sbb     ecx, ecx
0x14003dbfe  and     ecx, 0FFFFFFFCh
0x14003dc01  add     ecx, 9
0x14003dc04  jmp     loc_14001BAC7
0x14003dc09  lea     r9, aNoRoomForCrypt; "No room for CRYPTO frame"
0x14003dc10  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003dc14  mov     edx, 80h; SizeInBytes
0x14003dc19  lea     rcx, [rsp+108h+DstBuf]; DstBuf
0x14003dc1e  call    cs:__imp__snprintf_s
0x14003dc25  nop     dword ptr [rax+rax+00h]
0x14003dc2a  lea     r9, [rsp+108h+DstBuf]
0x14003dc2f  mov     r8, rbp
0x14003dc32  lea     rdx, QuicConnLogVerbose
0x14003dc39  call    McTemplateU0ps_EtwWriteTransfer
0x14003dc3e  nop
0x14003dc3f  jmp     loc_14001BBBD
0x14003dc44  mov     edx, 1
0x14003dc49  jmp     loc_14001BAFF
0x14003dc4e  cmp     rcx, 40000000h
0x14003dc55  sbb     rdx, rdx
0x14003dc58  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14003dc5c  add     rdx, 8
0x14003dc60  jmp     loc_14001BAFF
0x14003dc65  movzx   eax, cx
0x14003dc68  lea     r9, aSendingHuCrypt; "Sending %hu crypto bytes, offset=%u"
0x14003dc6f  lea     rcx, [rsp+108h+DstBuf]; DstBuf
0x14003dc74  mov     [rsp+108h+var_E0], edi
0x14003dc78  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003dc7c  mov     [rsp+108h+var_E8], eax
0x14003dc80  mov     edx, 80h; SizeInBytes
0x14003dc85  call    cs:__imp__snprintf_s
0x14003dc8c  nop     dword ptr [rax+rax+00h]
0x14003dc91  lea     r9, [rsp+108h+DstBuf]
0x14003dc96  mov     r8, rbp
0x14003dc99  lea     rdx, QuicConnLogVerbose
0x14003dca0  call    McTemplateU0ps_EtwWriteTransfer
0x14003dca5  nop
0x14003dca6  jmp     loc_14001BB23
0x14003dcab  lea     r8, aQuiccryptofram; "QuicCryptoFrameEncode(&Frame, Offset, B"...
0x14003dcb2  mov     edx, 2B1h
0x14003dcb7  lea     rcx, aCW1SMsquicSrcC_15; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x14003dcbe  call    CxPlatLogAssert
0x14003dcc3  int     2Ch; Windows NT - assertion failure
0x14003dcc5  jmp     loc_14001BB44
```
