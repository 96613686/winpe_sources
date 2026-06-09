# QuicCryptoDecodeClientTicket

- ea: `0x140045e34`
- end: `0x1400460ab`
- name: `QuicCryptoDecodeClientTicket`
- size: `631`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, char *, _QWORD *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140001d6c`

## callees

- `0x14000db70`
- `0x14000ed10`
- `0x140022dcc`
- `0x14003cb00`
- `0x14003ec10`
- `0x14003ed00`
- `0x140045e34`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004603d`
- `ntoskrnl!ExAllocatePool2` at `0x14004603d`

## string_xrefs

- `0x140046061`: `Resumption ticket copy`

## pseudocode

```c
__int64 __fastcall QuicCryptoDecodeClientTicket(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        char *a4,
        _QWORD *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  unsigned __int64 v8; // rdi
  unsigned int v10; // esi
  __int64 v11; // rcx
  const char *v12; // r9
  unsigned __int64 v13; // r12
  __int16 v14; // dx
  __int16 v15; // di
  __int64 v16; // r15
  unsigned __int64 v17; // rdi
  void *Pool2; // rax
  __int64 v19; // rdx
  unsigned __int16 v21; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v24; // [rsp+48h] [rbp-8h] BYREF

  v8 = a2;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v10 = -1073741811;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( QuicVarIntDecode(a2, a3, &v21, &v22) )
  {
    if ( v22 != 1 )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return v10;
      v12 = "Client Ticket version unsupported";
      goto LABEL_4;
    }
    v13 = v8;
    if ( v8 < (unsigned __int64)v21 + 4 )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return v10;
      v12 = "Client Ticket not long enough for QUIC version";
      goto LABEL_4;
    }
    *a7 = *(_DWORD *)(v21 + a3);
    if ( !(unsigned __int8)QuicIsVersionSupported() )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return v10;
      v12 = "Resumption Ticket for unsupported QUIC version";
      goto LABEL_4;
    }
    v21 = v14 + 4;
    if ( !QuicVarIntDecode(v8, a3, &v21, &v23) )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return v10;
      v12 = "Client Ticket TP length failed to decode";
      goto LABEL_4;
    }
    if ( !QuicVarIntDecode(v8, a3, &v21, &v24) )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return v10;
      v12 = "Resumption Ticket data length failed to decode";
      goto LABEL_4;
    }
    v11 = v21;
    v15 = v23;
    if ( v13 < v21 + v23 )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return v10;
      v12 = "Client Ticket not long enough for Client Transport Parameters";
      goto LABEL_4;
    }
    if ( !QuicCryptoTlsDecodeTransportParameters(a1, 1u, v21 + a3, v23, a4) )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return v10;
      v12 = "Resumption Ticket TParams failed to decode";
      goto LABEL_4;
    }
    v16 = (unsigned __int16)(v21 + v15);
    v17 = v24;
    if ( v24 + v16 != v13 )
    {
      if ( (byte_14005C48B & 4) == 0 )
        return v10;
      v12 = "Client resumption ticket length is corrupt";
      goto LABEL_4;
    }
    if ( v24 )
    {
      Pool2 = (void *)ExAllocatePool2(66, (unsigned int)v24, 942891857);
      *a5 = Pool2;
      if ( !Pool2 )
      {
        if ( (Microsoft_QuicEnableBits & 2) != 0 )
          McTemplateU0sx_EtwWriteTransfer(a5, v19, "Resumption ticket copy", v17);
        return (unsigned int)-1073741801;
      }
      memmove(Pool2, (const void *)(v16 + a3), (unsigned __int16)v17);
    }
    *a6 = v17;
    return 0;
  }
  if ( (byte_14005C48B & 4) != 0 )
  {
    v12 = "Client Ticket version failed to decode";
LABEL_4:
    McTemplateU0ps_EtwWriteTransfer(v11, QuicConnError, a1, v12);
  }
  return v10;
}

```

## disassembly

```asm
0x140045e34  mov     rax, rsp
0x140045e37  mov     [rax+8], rbx
0x140045e3b  mov     [rax+10h], rsi
0x140045e3f  mov     [rax+18h], rdi
0x140045e43  mov     [rax+20h], r9
0x140045e47  push    rbp
0x140045e48  push    r12
0x140045e4a  push    r13
0x140045e4c  push    r14
0x140045e4e  push    r15
0x140045e50  mov     rbp, rsp
0x140045e53  sub     rsp, 50h
0x140045e57  mov     rax, [rbp+arg_20]
0x140045e5b  lea     r9, [rbp+var_18]
0x140045e5f  mov     r13, [rbp+arg_28]
0x140045e63  xor     r12d, r12d
0x140045e66  mov     r15, [rbp+arg_30]
0x140045e6a  mov     r14, r8
0x140045e6d  movzx   edi, dx
0x140045e70  lea     r8, [rbp+var_20]
0x140045e74  mov     [rax], r12
0x140045e77  mov     rbx, rcx
0x140045e7a  mov     [r13+0], r12d
0x140045e7e  mov     rdx, r14
0x140045e81  movzx   ecx, di
0x140045e84  mov     [r15], r12d
0x140045e87  mov     esi, 0C000000Dh
0x140045e8c  mov     [rbp+var_20], r12w
0x140045e91  mov     [rbp+var_18], r12
0x140045e95  mov     [rbp+var_10], r12
0x140045e99  mov     [rbp+var_8], r12
0x140045e9d  call    QuicVarIntDecode
0x140045ea2  test    al, al
0x140045ea4  jnz     short loc_140045ECE
0x140045ea6  test    cs:byte_14005C48B, 4
0x140045ead  jz      loc_14004608A
0x140045eb3  lea     r9, aClientTicketVe_0; "Client Ticket version failed to decode"
0x140045eba  mov     r8, rbx
0x140045ebd  lea     rdx, QuicConnError
0x140045ec4  call    McTemplateU0ps_EtwWriteTransfer
0x140045ec9  jmp     loc_14004608A
0x140045ece  cmp     [rbp+var_18], 1
0x140045ed3  jz      short loc_140045EEB
0x140045ed5  test    cs:byte_14005C48B, 4
0x140045edc  jz      loc_14004608A
0x140045ee2  lea     r9, aClientTicketVe; "Client Ticket version unsupported"
0x140045ee9  jmp     short loc_140045EBA
0x140045eeb  movzx   edx, [rbp+var_20]
0x140045eef  mov     r12, rdi
0x140045ef2  lea     rax, [rdx+4]
0x140045ef6  cmp     rdi, rax
0x140045ef9  jnb     short loc_140045F11
0x140045efb  test    cs:byte_14005C48B, 4
0x140045f02  jz      loc_14004608A
0x140045f08  lea     r9, aClientTicketNo_0; "Client Ticket not long enough for QUIC "...
0x140045f0f  jmp     short loc_140045EBA
0x140045f11  mov     ecx, [rdx+r14]
0x140045f15  mov     [r15], ecx
0x140045f18  call    QuicIsVersionSupported
0x140045f1d  test    al, al
0x140045f1f  jnz     short loc_140045F37
0x140045f21  test    cs:byte_14005C48B, 4
0x140045f28  jz      loc_14004608A
0x140045f2e  lea     r9, aResumptionTick_5; "Resumption Ticket for unsupported QUIC "...
0x140045f35  jmp     short loc_140045EBA
0x140045f37  add     dx, 4
0x140045f3b  lea     r9, [rbp+var_10]
0x140045f3f  mov     [rbp+var_20], dx
0x140045f43  lea     r8, [rbp+var_20]
0x140045f47  mov     rdx, r14
0x140045f4a  movzx   ecx, di
0x140045f4d  call    QuicVarIntDecode
0x140045f52  test    al, al
0x140045f54  jnz     short loc_140045F6F
0x140045f56  test    cs:byte_14005C48B, 4
0x140045f5d  jz      loc_14004608A
0x140045f63  lea     r9, aClientTicketTp; "Client Ticket TP length failed to decod"...
0x140045f6a  jmp     loc_140045EBA
0x140045f6f  lea     r9, [rbp+var_8]
0x140045f73  mov     rdx, r14
0x140045f76  lea     r8, [rbp+var_20]
0x140045f7a  movzx   ecx, di
0x140045f7d  call    QuicVarIntDecode
0x140045f82  test    al, al
0x140045f84  jnz     short loc_140045F9F
0x140045f86  test    cs:byte_14005C48B, 4
0x140045f8d  jz      loc_14004608A
0x140045f93  lea     r9, aResumptionTick_9; "Resumption Ticket data length failed to"...
0x140045f9a  jmp     loc_140045EBA
0x140045f9f  movzx   ecx, [rbp+var_20]
0x140045fa3  mov     rdi, [rbp+var_10]
0x140045fa7  lea     rax, [rcx+rdi]
0x140045fab  cmp     r12, rax
0x140045fae  jnb     short loc_140045FC9
0x140045fb0  test    cs:byte_14005C48B, 4
0x140045fb7  jz      loc_14004608A
0x140045fbd  lea     r9, aClientTicketNo; "Client Ticket not long enough for Clien"...
0x140045fc4  jmp     loc_140045EBA
0x140045fc9  mov     rax, [rbp+arg_18]
0x140045fcd  lea     r8, [rcx+r14]; int
0x140045fd1  mov     rcx, rbx; int
0x140045fd4  mov     [rsp+50h+var_30], rax; void *
0x140045fd9  movzx   r9d, di; int
0x140045fdd  mov     dl, 1; int
0x140045fdf  call    QuicCryptoTlsDecodeTransportParameters
0x140045fe4  test    al, al
0x140045fe6  jnz     short loc_140046001
0x140045fe8  test    cs:byte_14005C48B, 4
0x140045fef  jz      loc_14004608A
0x140045ff5  lea     r9, aResumptionTick; "Resumption Ticket TParams failed to dec"...
0x140045ffc  jmp     loc_140045EBA
0x140046001  add     di, [rbp+var_20]
0x140046005  movzx   r15d, di
0x140046009  mov     rdi, [rbp+var_8]
0x14004600d  lea     rax, [rdi+r15]
0x140046011  cmp     rax, r12
0x140046014  jz      short loc_14004602B
0x140046016  test    cs:byte_14005C48B, 4
0x14004601d  jz      short loc_14004608A
0x14004601f  lea     r9, aClientResumpti; "Client resumption ticket length is corr"...
0x140046026  jmp     loc_140045EBA
0x14004602b  test    rdi, rdi
0x14004602e  jz      short loc_140046084
0x140046030  mov     edx, edi
0x140046032  mov     ecx, 42h ; 'B'
0x140046037  mov     r8d, 38336351h
0x14004603d  call    cs:__imp_ExAllocatePool2
0x140046044  nop     dword ptr [rax+rax+00h]
0x140046049  mov     rcx, [rbp+arg_20]
0x14004604d  mov     [rcx], rax
0x140046050  test    rax, rax
0x140046053  jnz     short loc_140046074
0x140046055  test    cs:Microsoft_QuicEnableBits, 2
0x14004605c  jz      short loc_14004606D
0x14004605e  mov     r9, rdi
0x140046061  lea     r8, aResumptionTick_8; "Resumption ticket copy"
0x140046068  call    McTemplateU0sx_EtwWriteTransfer
0x14004606d  mov     esi, 0C0000017h
0x140046072  jmp     short loc_14004608A
0x140046074  movzx   r8d, di; Size
0x140046078  lea     rdx, [r15+r14]; Src
0x14004607c  mov     rcx, rax; void *
0x14004607f  call    memmove
0x140046084  mov     [r13+0], edi
0x140046088  xor     esi, esi
0x14004608a  lea     r11, [rsp+50h+var_s0]
0x14004608f  mov     eax, esi
0x140046091  mov     rbx, [r11+30h]
0x140046095  mov     rsi, [r11+38h]
0x140046099  mov     rdi, [r11+40h]
0x14004609d  mov     rsp, r11
0x1400460a0  pop     r15
0x1400460a2  pop     r14
0x1400460a4  pop     r13
0x1400460a6  pop     r12
0x1400460a8  pop     rbp
0x1400460a9  retn
```
