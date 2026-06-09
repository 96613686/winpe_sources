# QuicPacketLogHeader

- ea: `0x140041de0`
- end: `0x1400424ce`
- name: `QuicPacketLogHeader`
- size: `1774`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x140012630`
- `0x140017580`
- `0x140042e10`

## callees

- `0x14000ed10`
- `0x140029fb0`
- `0x140029ffc`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003ead8`
- `0x140040b80`
- `0x140041de0`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140041f51`
- `ntoskrnl!_snprintf_s` at `0x14004219f`
- `ntoskrnl!_snprintf_s` at `0x1400422d9`
- `ntoskrnl!_snprintf_s` at `0x14004235b`
- `ntoskrnl!_snprintf_s` at `0x14004248d`
- `ntoskrnl!_snprintf_s` at `0x140041f51`
- `ntoskrnl!_snprintf_s` at `0x14004219f`
- `ntoskrnl!_snprintf_s` at `0x1400422d9`
- `ntoskrnl!_snprintf_s` at `0x14004235b`
- `ntoskrnl!_snprintf_s` at `0x14004248d`

## string_xrefs

- `0x1400420ae`: `[%c][%cX][-] LH Ver:0x%x DestCid:%s SrcCid:%s Type:R (Token %hu bytes)`
- `0x140042152`: `[%c][%cX][%llu] LH Ver:0x%x DestCid:%s SrcCid:%s Type:I (Token %hu bytes) (Payload %hu bytes)`

## pseudocode

```c
char __fastcall QuicPacketLogHeader(
        _DWORD *a1,
        unsigned __int8 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5,
        __int64 a6,
        int a7)
{
  __int64 v7; // r10
  __int64 v8; // rsi
  _DWORD *v9; // rbx
  char v10; // r12
  __int64 v11; // rcx
  int v12; // r13d
  __int64 v13; // r8
  unsigned __int16 i; // di
  __int64 v15; // rdx
  char result; // al
  int v17; // r12d
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 v21; // r9
  __int64 v22; // rax
  const char *v23; // r9
  __int64 v24; // rcx
  char v25; // r14
  unsigned __int16 v26; // di
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rbx
  __int64 v36; // r9
  __int64 v37; // rax
  int v38; // r12d
  int v39; // edi
  int v40; // esi
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // rbx
  __int64 v44; // r9
  __int64 v45; // rax
  const char *v46; // r9
  int v47; // edx
  int v48; // edi
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rax
  __int64 v53; // r8
  const char *v54; // rbx
  __int64 v55; // r9
  const char *v56; // rax
  __int64 v57; // rcx
  int v58; // r8d
  __int64 v59; // rcx
  int v60; // r12d
  int v61; // ebx
  const char *v62; // rax
  __int64 v63; // [rsp+20h] [rbp-E0h]
  __int64 v64; // [rsp+28h] [rbp-D8h]
  int v65; // [rsp+28h] [rbp-D8h]
  __int64 v66; // [rsp+30h] [rbp-D0h]
  __int64 v67; // [rsp+38h] [rbp-C8h]
  __int64 v68; // [rsp+40h] [rbp-C0h]
  __int64 v69; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v70; // [rsp+50h] [rbp-B0h]
  int v71; // [rsp+58h] [rbp-A8h]
  char v73; // [rsp+61h] [rbp-9Fh]
  unsigned __int8 v74; // [rsp+62h] [rbp-9Eh]
  char v75; // [rsp+62h] [rbp-9Eh]
  int v76; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int64 v77; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v78; // [rsp+70h] [rbp-90h]
  __int64 v79; // [rsp+78h] [rbp-88h]
  __int64 v80; // [rsp+80h] [rbp-80h]
  __int64 v81; // [rsp+88h] [rbp-78h]
  unsigned __int64 v82; // [rsp+90h] [rbp-70h] BYREF
  __int64 v83; // [rsp+98h] [rbp-68h]
  _BYTE v84[512]; // [rsp+A0h] [rbp-60h] BYREF
  char v85[512]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char DstBuf[128]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v7 = a6;
  v8 = 0;
  v81 = a4;
  v9 = a1;
  LOBYTE(a4) = a2;
  v77 = (unsigned __int64)a1;
  v10 = *(_BYTE *)a6;
  v79 = a6;
  v74 = v10;
  if ( v10 >= 0 )
  {
    if ( a7 != 52651 && a7 != 0x1000000 && a7 != 486539519 && a7 != -817679509 )
    {
      result = CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\packet.c", 799, "0");
      __int2c();
      return result;
    }
    result = byte_14005C48E;
    if ( byte_14005C48E < 0 )
    {
      if ( a1 )
      {
        LOBYTE(v8) = *a1 == 4;
        v60 = PacketLogPrefix[v8];
      }
      else
      {
        v60 = 45;
      }
      v61 = (unsigned __int16)(a5 - ((unsigned __int8)a3 + 1));
      v62 = (const char *)QuicCidBufToStr(v84, a6 + 1, a3, 1);
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "[%c][%cX][%llu] SH DestCid:%s KP:%hu SB:%hu (Payload %hu bytes)",
        v60,
        PacketLogPrefix[a2 + 2],
        v81,
        v62,
        (v74 >> 2) & 1,
        (v74 >> 5) & 1,
        v61);
      return McTemplateU0s_EtwWriteTransfer(v24, QuicLogVerbose, DstBuf);
    }
  }
  else
  {
    v11 = *(unsigned __int8 *)(a6 + 5);
    v12 = *(_DWORD *)(a6 + 1);
    v80 = a6 + 6;
    v73 = v11;
    v13 = *(unsigned __int8 *)(v11 + a6 + 6);
    i = v13 + v11 + 7;
    v75 = *(_BYTE *)(v11 + a6 + 6);
    v78 = i;
    v15 = v11 + a6 + 7;
    LOWORD(v76) = i;
    v83 = v15;
    if ( v12 )
    {
      if ( v12 != 52651 && v12 != 0x1000000 && v12 != 486539519 && v12 != -817679509 )
      {
        result = byte_14005C48E;
        if ( byte_14005C48E >= 0 )
          return result;
        if ( v9 )
        {
          LOBYTE(v8) = *v9 == 4;
          v17 = PacketLogPrefix[v8];
        }
        else
        {
          v17 = 45;
        }
        v18 = QuicCidBufToStr(v85, v15, v13, a4);
        LOBYTE(v19) = v73;
        v20 = v18;
        v22 = QuicCidBufToStr(v84, v80, v19, v21);
        v23 = "[%c][%cX][%llu] LH Ver:[UNSUPPORTED,0x%x] DestCid:%s SrcCid:%s";
        v69 = v20;
        v68 = v22;
        LODWORD(v67) = *(_DWORD *)(v79 + 1);
        v66 = v81;
        v65 = PacketLogPrefix[a2 + 2];
LABEL_12:
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v23, v17, v65, v66, v67, v68, v69);
        return McTemplateU0s_EtwWriteTransfer(v24, QuicLogVerbose, DstBuf);
      }
      v77 = 0;
      v25 = v10 & 0x30;
      v82 = 0;
      if ( v12 == -817679509 )
      {
        if ( v25 != 16 )
        {
          if ( v25 )
            goto LABEL_16;
          goto LABEL_27;
        }
      }
      else if ( v25 )
      {
        if ( v25 != 48 )
        {
LABEL_16:
          v77 = -1;
          v26 = a5;
          goto LABEL_17;
        }
LABEL_27:
        result = byte_14005C48E;
        if ( byte_14005C48E >= 0 )
          return result;
        if ( v9 )
        {
          LOBYTE(v8) = *v9 == 4;
          v17 = PacketLogPrefix[v8];
        }
        else
        {
          v17 = 45;
        }
        v33 = QuicCidBufToStr(v84, v15, v13, a4);
        LOBYTE(v34) = v73;
        v35 = v33;
        v37 = QuicCidBufToStr(v85, v80, v34, v36);
        v23 = "[%c][%cX][-] LH Ver:0x%x DestCid:%s SrcCid:%s Type:R (Token %hu bytes)";
        LODWORD(v69) = (unsigned __int16)(a5 - i - 16);
        v68 = v35;
        v67 = v37;
        LODWORD(v66) = *(_DWORD *)(v79 + 1);
        v65 = PacketLogPrefix[a2 + 2];
        goto LABEL_12;
      }
      v26 = a5;
      result = QuicVarIntDecode(a5, a6, &v76, &v77);
      if ( !result )
        return result;
      LOWORD(v76) = v77 + v76;
      v7 = v79;
LABEL_17:
      result = QuicVarIntDecode(v26, v7, &v76, &v82);
      if ( !result )
        return result;
      if ( v12 == -817679509 )
      {
        if ( v25 != 16 )
          goto LABEL_20;
      }
      else if ( v25 )
      {
LABEL_20:
        result = byte_14005C48E;
        if ( byte_14005C48E >= 0 )
          return result;
        LOBYTE(v27) = ((unsigned __int8)v10 >> 4) & 3;
        if ( v12 == -817679509 )
          v30 = QuicLongHeaderTypeToStringV2(v27);
        else
          v30 = QuicLongHeaderTypeToStringV1(v27);
        v77 = v30;
        if ( v9 )
        {
          LOBYTE(v8) = *v9 == 4;
          v38 = PacketLogPrefix[v8];
        }
        else
        {
          v38 = 45;
        }
        LOBYTE(v31) = v75;
        v48 = (unsigned __int16)v82;
        v49 = QuicCidBufToStr(v84, v83, v31, v32);
        LOBYTE(v50) = v73;
        v43 = v49;
        v45 = QuicCidBufToStr(v85, v80, v50, v51);
        v46 = "[%c][%cX][%llu] LH Ver:0x%x DestCid:%s SrcCid:%s Type:%s (Payload %hu bytes)";
        v71 = v48;
        v47 = PacketLogPrefix[a2 + 2];
        v70 = v77;
LABEL_38:
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, v46, v38, v47, v81, *(_DWORD *)(v79 + 1), v45, v43, v70, v71);
        return McTemplateU0s_EtwWriteTransfer(v24, QuicLogVerbose, DstBuf);
      }
      result = byte_14005C48E;
      if ( byte_14005C48E >= 0 )
        return result;
      if ( v9 )
      {
        LOBYTE(v8) = *v9 == 4;
        v38 = PacketLogPrefix[v8];
      }
      else
      {
        v38 = 45;
      }
      LOBYTE(v28) = v75;
      v39 = (unsigned __int16)v82;
      v40 = (unsigned __int16)v77;
      v41 = QuicCidBufToStr(v84, v83, v28, v29);
      LOBYTE(v42) = v73;
      v43 = v41;
      v45 = QuicCidBufToStr(v85, v80, v42, v44);
      v46 = "[%c][%cX][%llu] LH Ver:0x%x DestCid:%s SrcCid:%s Type:I (Token %hu bytes) (Payload %hu bytes)";
      v71 = v39;
      LODWORD(v70) = v40;
      v47 = PacketLogPrefix[a2 + 2];
      goto LABEL_38;
    }
    result = byte_14005C48E;
    if ( byte_14005C48E >= 0 )
      goto LABEL_56;
    if ( v9 )
      v76 = PacketLogPrefix[*v9 == 4];
    else
      v76 = 45;
    v52 = QuicCidBufToStr(v84, v15, v13, a4);
    LOBYTE(v53) = v73;
    v54 = (const char *)v52;
    v56 = (const char *)QuicCidBufToStr(v85, v80, v53, v55);
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[%c][%cX][-] VerNeg DestCid:%s SrcCid:%s (Payload %hu bytes)",
      v76,
      (unsigned __int8)PacketLogPrefix[a2 + 2],
      v56,
      v54,
      (unsigned __int16)(a5 - i));
    result = McTemplateU0s_EtwWriteTransfer(v57, QuicLogVerbose, DstBuf);
    v9 = (_DWORD *)v77;
    for ( i = v78; ; i += 4 )
    {
      LOBYTE(a4) = a2;
      v7 = v79;
LABEL_56:
      if ( i >= a5 )
        break;
      result = byte_14005C48E;
      if ( byte_14005C48E < 0 )
      {
        if ( v9 )
          v58 = PacketLogPrefix[*v9 == 4];
        else
          v58 = 45;
        LODWORD(v64) = (unsigned __int8)PacketLogPrefix[(unsigned __int8)a4 + 2];
        LODWORD(v63) = v58;
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[%c][%cX][-]   Ver:0x%x", v63, v64, *(_DWORD *)(i + v7));
        result = McTemplateU0s_EtwWriteTransfer(v59, QuicLogVerbose, DstBuf);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140041de0  push    rbp
0x140041de2  push    rbx
0x140041de3  push    rsi
0x140041de4  push    rdi
0x140041de5  push    r12
0x140041de7  push    r13
0x140041de9  push    r14
0x140041deb  lea     rbp, [rsp-430h]
0x140041df3  sub     rsp, 530h
0x140041dfa  mov     rax, cs:__security_cookie
0x140041e01  xor     rax, rsp
0x140041e04  mov     [rbp+460h+var_40], rax
0x140041e0b  mov     r10, [rbp+460h+arg_28]
0x140041e12  xor     esi, esi
0x140041e14  mov     [rbp+460h+var_4D8], r9
0x140041e18  mov     rbx, rcx
0x140041e1b  mov     r9b, dl
0x140041e1e  mov     [rsp+560h+var_500], dl
0x140041e22  mov     [rsp+560h+var_4F8], rcx
0x140041e27  mov     r12b, [r10]
0x140041e2a  mov     [rsp+560h+var_4E8], r10
0x140041e2f  mov     [rsp+560h+var_4FE], r12b
0x140041e34  test    r12b, r12b
0x140041e37  jns     loc_14004239A
0x140041e3d  movzx   ecx, byte ptr [r10+5]
0x140041e42  lea     rdx, [r10+6]
0x140041e46  mov     r13d, [r10+1]
0x140041e4a  mov     [rbp+460h+var_4E0], rdx
0x140041e4e  mov     [rsp+560h+var_4FF], cl
0x140041e52  movzx   r8d, byte ptr [rcx+rdx]
0x140041e57  lea     edi, [rcx+7]
0x140041e5a  add     edi, r8d
0x140041e5d  mov     [rsp+560h+var_4FE], r8b
0x140041e62  inc     rdx
0x140041e65  mov     [rsp+560h+var_4F0], di
0x140041e6a  add     rdx, rcx
0x140041e6d  mov     word ptr [rsp+560h+var_4FC], di
0x140041e72  mov     [rbp+460h+var_4C8], rdx
0x140041e76  test    r13d, r13d
0x140041e79  jz      loc_140042231
0x140041e7f  cmp     r13d, 0CDABh
0x140041e86  jz      loc_140041F62
0x140041e8c  cmp     r13d, 1000000h
0x140041e93  jz      loc_140041F62
0x140041e99  cmp     r13d, 1D0000FFh
0x140041ea0  jz      loc_140041F62
0x140041ea6  cmp     r13d, 0CF43336Bh
0x140041ead  jz      loc_140041F62
0x140041eb3  mov     al, cs:byte_14005C48E
0x140041eb9  test    al, al
0x140041ebb  jns     loc_1400424AC
0x140041ec1  lea     r14, PacketLogPrefix; "CSTR"
0x140041ec8  test    rbx, rbx
0x140041ecb  jnz     short loc_140041ED3
0x140041ecd  lea     r12d, [rbx+2Dh]
0x140041ed1  jmp     short loc_140041EE5
0x140041ed3  mov     r13d, 4
0x140041ed9  cmp     [rbx], r13d
0x140041edc  setz    sil
0x140041ee0  movsx   r12d, byte ptr [rsi+r14]
0x140041ee5  lea     rcx, [rbp+460h+var_2C0]
0x140041eec  call    QuicCidBufToStr
0x140041ef1  mov     r8b, [rsp+560h+var_4FF]
0x140041ef6  lea     rcx, [rbp+460h+var_4C0]
0x140041efa  mov     rdx, [rbp+460h+var_4E0]
0x140041efe  mov     rbx, rax
0x140041f01  call    QuicCidBufToStr
0x140041f06  movzx   ecx, [rsp+560h+var_500]
0x140041f0b  lea     r9, aCCxLluLhVerUns; "[%c][%cX][%llu] LH Ver:[UNSUPPORTED,0x%"...
0x140041f12  mov     [rsp+560h+var_518], rbx
0x140041f17  mov     [rsp+560h+var_520], rax
0x140041f1c  mov     rax, [rsp+560h+var_4E8]
0x140041f21  movsx   r8d, byte ptr [rcx+r14+2]
0x140041f27  mov     eax, [rax+1]
0x140041f2a  mov     dword ptr [rsp+560h+var_528], eax
0x140041f2e  mov     rax, [rbp+460h+var_4D8]
0x140041f32  mov     [rsp+560h+var_530], rax
0x140041f37  mov     dword ptr [rsp+560h+var_538], r8d
0x140041f3c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140041f40  mov     dword ptr [rsp+560h+var_540], r12d
0x140041f45  mov     edx, 80h; SizeInBytes
0x140041f4a  lea     rcx, [rbp+460h+DstBuf]; DstBuf
0x140041f51  call    cs:__imp__snprintf_s
0x140041f58  nop     dword ptr [rax+rax+00h]
0x140041f5d  jmp     loc_140042499
0x140041f62  mov     r14b, r12b
0x140041f65  mov     [rsp+560h+var_4F8], rsi
0x140041f6a  and     r14b, 30h
0x140041f6e  mov     [rbp+460h+var_4D0], rsi
0x140041f72  cmp     r13d, 0CF43336Bh
0x140041f79  jz      short loc_140041FF9
0x140041f7b  test    r14b, r14b
0x140041f7e  jz      short loc_140041FFF
0x140041f80  cmp     r14b, 30h ; '0'
0x140041f84  jz      loc_140042045
0x140041f8a  or      [rsp+560h+var_4F8], 0FFFFFFFFFFFFFFFFh
0x140041f90  movzx   edi, [rbp+460h+arg_20]
0x140041f97  lea     r9, [rbp+460h+var_4D0]
0x140041f9b  mov     rdx, r10
0x140041f9e  lea     r8, [rsp+560h+var_4FC]
0x140041fa3  movzx   ecx, di
0x140041fa6  call    QuicVarIntDecode
0x140041fab  test    al, al
0x140041fad  jz      loc_1400424AC
0x140041fb3  cmp     r13d, 0CF43336Bh
0x140041fba  jz      loc_1400420DE
0x140041fc0  test    r14b, r14b
0x140041fc3  jz      loc_1400420E8
0x140041fc9  mov     al, cs:byte_14005C48E
0x140041fcf  test    al, al
0x140041fd1  jns     loc_1400424AC
0x140041fd7  shr     r12b, 4
0x140041fdb  and     r12b, 3
0x140041fdf  mov     cl, r12b
0x140041fe2  cmp     r13d, 0CF43336Bh
0x140041fe9  jnz     loc_1400421B0
0x140041fef  call    QuicLongHeaderTypeToStringV2
0x140041ff4  jmp     loc_1400421B5
0x140041ff9  cmp     r14b, 10h
0x140041ffd  jnz     short loc_14004203C
0x140041fff  movzx   edi, [rbp+460h+arg_20]
0x140042006  lea     r9, [rsp+560h+var_4F8]
0x14004200b  movzx   ecx, di
0x14004200e  lea     r8, [rsp+560h+var_4FC]
0x140042013  mov     rdx, r10
0x140042016  call    QuicVarIntDecode
0x14004201b  test    al, al
0x14004201d  jz      loc_1400424AC
0x140042023  mov     rax, [rsp+560h+var_4F8]
0x140042028  add     word ptr [rsp+560h+var_4FC], ax
0x14004202d  mov     r10, [rsp+560h+var_4E8]
0x140042032  mov     [rsp+560h+var_4F8], rax
0x140042037  jmp     loc_140041F97
0x14004203c  test    r14b, r14b
0x14004203f  jnz     loc_140041F8A
0x140042045  mov     al, cs:byte_14005C48E
0x14004204b  test    al, al
0x14004204d  jns     loc_1400424AC
0x140042053  lea     r14, PacketLogPrefix; "CSTR"
0x14004205a  test    rbx, rbx
0x14004205d  jnz     short loc_140042065
0x14004205f  lea     r12d, [rbx+2Dh]
0x140042063  jmp     short loc_140042077
0x140042065  mov     r13d, 4
0x14004206b  cmp     [rbx], r13d
0x14004206e  setz    sil
0x140042072  movsx   r12d, byte ptr [rsi+r14]
0x140042077  movzx   eax, [rbp+460h+arg_20]
0x14004207e  lea     rcx, [rbp+460h+var_4C0]
0x140042082  sub     ax, di
0x140042085  sub     ax, 10h
0x140042089  movzx   edi, ax
0x14004208c  call    QuicCidBufToStr
0x140042091  mov     r8b, [rsp+560h+var_4FF]
0x140042096  lea     rcx, [rbp+460h+var_2C0]
0x14004209d  mov     rdx, [rbp+460h+var_4E0]
0x1400420a1  mov     rbx, rax
0x1400420a4  call    QuicCidBufToStr
0x1400420a9  movzx   ecx, [rsp+560h+var_500]
0x1400420ae  lea     r9, aCCxLhVer0xXDes; "[%c][%cX][-] LH Ver:0x%x DestCid:%s Src"...
0x1400420b5  mov     dword ptr [rsp+560h+var_518], edi
0x1400420b9  mov     [rsp+560h+var_520], rbx
0x1400420be  mov     [rsp+560h+var_528], rax
0x1400420c3  mov     rax, [rsp+560h+var_4E8]
0x1400420c8  movsx   edx, byte ptr [rcx+r14+2]
0x1400420ce  mov     eax, [rax+1]
0x1400420d1  mov     dword ptr [rsp+560h+var_530], eax
0x1400420d5  mov     dword ptr [rsp+560h+var_538], edx
0x1400420d9  jmp     loc_140041F3C
0x1400420de  cmp     r14b, 10h
0x1400420e2  jnz     loc_140041FC9
0x1400420e8  mov     al, cs:byte_14005C48E
0x1400420ee  test    al, al
0x1400420f0  jns     loc_1400424AC
0x1400420f6  lea     r14, PacketLogPrefix; "CSTR"
0x1400420fd  test    rbx, rbx
0x140042100  jnz     short loc_140042108
0x140042102  lea     r12d, [rbx+2Dh]
0x140042106  jmp     short loc_14004211A
0x140042108  mov     r13d, 4
0x14004210e  cmp     [rbx], r13d
0x140042111  setz    sil
0x140042115  movsx   r12d, byte ptr [rsi+r14]
0x14004211a  mov     r8b, [rsp+560h+var_4FE]
0x14004211f  lea     rcx, [rbp+460h+var_4C0]
0x140042123  mov     rdx, [rbp+460h+var_4C8]
0x140042127  movzx   edi, word ptr [rbp+460h+var_4D0]
0x14004212b  movzx   esi, word ptr [rsp+560h+var_4F8]
0x140042130  call    QuicCidBufToStr
0x140042135  mov     r8b, [rsp+560h+var_4FF]
0x14004213a  lea     rcx, [rbp+460h+var_2C0]
0x140042141  mov     rdx, [rbp+460h+var_4E0]
0x140042145  mov     rbx, rax
0x140042148  call    QuicCidBufToStr
0x14004214d  movzx   ecx, [rsp+560h+var_500]
0x140042152  lea     r9, aCCxLluLhVer0xX; "[%c][%cX][%llu] LH Ver:0x%x DestCid:%s "...
0x140042159  mov     [rsp+560h+var_508], edi
0x14004215d  mov     dword ptr [rsp+560h+var_510], esi
0x140042161  movsx   edx, byte ptr [rcx+r14+2]
0x140042167  mov     [rsp+560h+var_518], rbx
0x14004216c  lea     rcx, [rbp+460h+DstBuf]; DstBuf
0x140042173  mov     [rsp+560h+var_520], rax
0x140042178  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14004217c  mov     rax, [rsp+560h+var_4E8]
0x140042181  mov     eax, [rax+1]
0x140042184  mov     dword ptr [rsp+560h+var_528], eax
0x140042188  mov     rax, [rbp+460h+var_4D8]
0x14004218c  mov     [rsp+560h+var_530], rax
0x140042191  mov     dword ptr [rsp+560h+var_538], edx
0x140042195  mov     edx, 80h; SizeInBytes
0x14004219a  mov     dword ptr [rsp+560h+var_540], r12d
0x14004219f  call    cs:__imp__snprintf_s
0x1400421a6  nop     dword ptr [rax+rax+00h]
0x1400421ab  jmp     loc_140042499
0x1400421b0  call    QuicLongHeaderTypeToStringV1
0x1400421b5  mov     [rsp+560h+var_4F8], rax
0x1400421ba  lea     r14, PacketLogPrefix; "CSTR"
0x1400421c1  test    rbx, rbx
0x1400421c4  jnz     short loc_1400421CC
0x1400421c6  lea     r12d, [rbx+2Dh]
0x1400421ca  jmp     short loc_1400421DE
0x1400421cc  mov     r13d, 4
0x1400421d2  cmp     [rbx], r13d
0x1400421d5  setz    sil
0x1400421d9  movsx   r12d, byte ptr [rsi+r14]
0x1400421de  mov     r8b, [rsp+560h+var_4FE]
0x1400421e3  lea     rcx, [rbp+460h+var_4C0]
0x1400421e7  mov     rdx, [rbp+460h+var_4C8]
0x1400421eb  movzx   edi, word ptr [rbp+460h+var_4D0]
0x1400421ef  call    QuicCidBufToStr
0x1400421f4  mov     r8b, [rsp+560h+var_4FF]
0x1400421f9  lea     rcx, [rbp+460h+var_2C0]
0x140042200  mov     rdx, [rbp+460h+var_4E0]
0x140042204  mov     rbx, rax
0x140042207  call    QuicCidBufToStr
0x14004220c  movzx   ecx, [rsp+560h+var_500]
0x140042211  lea     r9, aCCxLluLhVer0xX_0; "[%c][%cX][%llu] LH Ver:0x%x DestCid:%s "...
0x140042218  mov     [rsp+560h+var_508], edi
0x14004221c  movsx   edx, byte ptr [rcx+r14+2]
0x140042222  mov     rcx, [rsp+560h+var_4F8]
0x140042227  mov     [rsp+560h+var_510], rcx
0x14004222c  jmp     loc_140042167
0x140042231  mov     al, cs:byte_14005C48E
0x140042237  lea     r14, PacketLogPrefix; "CSTR"
0x14004223e  mov     r12d, 2Dh ; '-'
0x140042244  lea     r13d, [r12-29h]
0x140042249  test    al, al
0x14004224b  jns     loc_140042388
0x140042251  test    rbx, rbx
0x140042254  jnz     short loc_14004225D
0x140042256  mov     [rsp+560h+var_4FC], r12d
0x14004225b  jmp     short loc_14004226F
0x14004225d  cmp     [rbx], r13d
0x140042260  mov     rax, rsi
0x140042263  setz    al
0x140042266  movsx   eax, byte ptr [rax+r14]
0x14004226b  mov     [rsp+560h+var_4FC], eax
0x14004226f  movzx   eax, [rbp+460h+arg_20]
0x140042276  lea     rcx, [rbp+460h+var_4C0]
0x14004227a  sub     ax, di
0x14004227d  movzx   edi, ax
0x140042280  call    QuicCidBufToStr
0x140042285  mov     r8b, [rsp+560h+var_4FF]
0x14004228a  lea     rcx, [rbp+460h+var_2C0]
0x140042291  mov     rdx, [rbp+460h+var_4E0]
0x140042295  mov     rbx, rax
0x140042298  call    QuicCidBufToStr
0x14004229d  movzx   ecx, [rsp+560h+var_500]
0x1400422a2  lea     r9, aCCxVernegDestc; "[%c][%cX][-] VerNeg DestCid:%s SrcCid:%"...
0x1400422a9  mov     dword ptr [rsp+560h+var_520], edi
0x1400422ad  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400422b1  mov     [rsp+560h+var_528], rbx
0x1400422b6  mov     [rsp+560h+var_530], rax
0x1400422bb  movzx   edx, byte ptr [rcx+r14+2]
0x1400422c1  lea     rcx, [rbp+460h+DstBuf]; DstBuf
0x1400422c8  mov     eax, [rsp+560h+var_4FC]
0x1400422cc  mov     dword ptr [rsp+560h+var_538], edx
0x1400422d0  mov     edx, 80h; SizeInBytes
0x1400422d5  mov     dword ptr [rsp+560h+var_540], eax
0x1400422d9  call    cs:__imp__snprintf_s
0x1400422e0  nop     dword ptr [rax+rax+00h]
0x1400422e5  lea     r8, [rbp+460h+DstBuf]
0x1400422ec  lea     rdx, QuicLogVerbose
0x1400422f3  call    McTemplateU0s_EtwWriteTransfer
0x1400422f8  mov     rbx, [rsp+560h+var_4F8]
0x1400422fd  movzx   edi, [rsp+560h+var_4F0]
0x140042302  jmp     short loc_14004237E
0x140042304  mov     al, cs:byte_14005C48E
0x14004230a  test    al, al
0x14004230c  jns     short loc_14004237A
0x14004230e  test    rbx, rbx
0x140042311  jnz     short loc_140042318
0x140042313  mov     r8d, r12d
0x140042316  jmp     short loc_140042326
0x140042318  cmp     [rbx], r13d
0x14004231b  mov     rax, rsi
0x14004231e  setz    al
0x140042321  movsx   r8d, byte ptr [rax+r14]
0x140042326  movzx   eax, r9b
0x14004232a  lea     r9, aCCxVer0xX; "[%c][%cX][-]   Ver:0x%x"
  ... truncated ...
```
