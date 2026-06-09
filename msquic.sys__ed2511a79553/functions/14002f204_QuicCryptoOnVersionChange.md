# QuicCryptoOnVersionChange

- ea: `0x14002f204`
- end: `0x14002f3bb`
- name: `QuicCryptoOnVersionChange`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x14000524c`
- `0x140005aa4`
- `0x140015b70`
- `0x14002b054`
- `0x1400430f0`

## callees

- `0x1400087bc`
- `0x140008ef0`
- `0x14001c664`
- `0x14002f204`
- `0x1400337e4`
- `0x14003fdf8`

## string_xrefs

- `0x14002f2c9`: `Crypto->TlsState.WriteKeys[QUIC_PACKET_KEY_INITIAL] != ((void *)0)`

## pseudocode

```c
__int64 __fastcall QuicCryptoOnVersionChange(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rbx
  char *v4; // rcx
  char **v5; // r12
  char *v6; // rcx
  int *v7; // r13
  __int64 v8; // rax
  __int64 v9; // rax
  char v10; // bp
  __int64 v11; // r15
  __int64 v12; // rax
  PVOID *v13; // r14
  PVOID *v14; // rsi
  int Initial; // eax
  int v16; // ecx
  __int64 v17; // rsi
  void **v18; // rbx
  __int64 v19; // rdi
  void *v20; // rcx

  result = 0;
  v2 = a1 - 2784;
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    v4 = QuicSupportedVersionList;
    while ( *(_DWORD *)v4 != *(_DWORD *)(v2 + 3636) )
    {
      result = (unsigned int)(result + 1);
      v4 += 88;
      if ( (unsigned int)result >= 4 )
      {
        v5 = off_14004C048;
        v6 = (char *)off_14004C048;
        v7 = dword_14004C014;
        goto LABEL_7;
      }
    }
    v7 = &dword_14004C014[22 * result];
    v5 = &off_14004C048[11 * result];
    v6 = &QuicSupportedVersionList[88 * result + 56];
LABEL_7:
    v8 = *(_QWORD *)(a1 + 8);
    if ( v8 )
      *(_QWORD *)(v8 + 40) = v6;
    if ( *(_DWORD *)v2 == 4 )
    {
      v9 = *(_QWORD *)(v2 + 1280);
      v10 = *(_BYTE *)(v9 + 17);
      v11 = v9 + 32;
    }
    else
    {
      v12 = *(_QWORD *)(v2 + 1288);
      v10 = *(_BYTE *)(v12 + 33);
      v11 = v12 + 48;
    }
    v13 = (PVOID *)(a1 + 88);
    v14 = (PVOID *)(a1 + 136);
    if ( *(_QWORD *)(a1 + 88) )
    {
      if ( !*v14 )
      {
        CxPlatLogAssert(
          "C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c",
          441,
          "Crypto->TlsState.WriteKeys[QUIC_PACKET_KEY_INITIAL] != ((void *)0)");
        __int2c();
      }
      QuicPacketKeyFree(*v13);
      QuicPacketKeyFree(*v14);
      *v13 = 0;
      *v14 = 0;
    }
    LOBYTE(v6) = *(_DWORD *)v2 == 4;
    Initial = QuicPacketKeyCreateInitial((_DWORD)v6, (_DWORD)v5, (_DWORD)v7, v10, v11, a1 + 88, a1 + 136);
    v17 = Initial;
    if ( Initial < 0 )
    {
      if ( (byte_14005C48B & 4) != 0 )
        McTemplateU0pqs_EtwWriteTransfer(
          v16,
          (unsigned int)QuicConnErrorStatus,
          v2,
          Initial,
          (__int64)"Creating initial keys");
      QuicConnTryClose(v2, 18, v17, "New version key OOM", 0x13u);
      v18 = (void **)(a1 + 136);
      v19 = 6;
      do
      {
        QuicPacketKeyFree(*(v18 - 6));
        v20 = *v18;
        *(v18 - 6) = 0;
        QuicPacketKeyFree(v20);
        *v18++ = 0;
        --v19;
      }
      while ( v19 );
    }
    return (unsigned int)v17;
  }
  return result;
}

```

## disassembly

```asm
0x14002f204  mov     [rsp+arg_0], rbx
0x14002f209  mov     [rsp+arg_8], rbp
0x14002f20e  mov     [rsp+arg_10], rsi
0x14002f213  push    rdi
0x14002f214  push    r12
0x14002f216  push    r13
0x14002f218  push    r14
0x14002f21a  push    r15
0x14002f21c  sub     rsp, 40h
0x14002f220  xor     eax, eax
0x14002f222  lea     rbx, [rcx-0AE0h]
0x14002f229  test    byte ptr [rcx], 1
0x14002f22c  mov     rdi, rcx
0x14002f22f  jz      loc_14002F39C
0x14002f235  mov     edx, [rbx+0E34h]
0x14002f23b  lea     r8, QuicSupportedVersionList
0x14002f242  mov     rcx, r8
0x14002f245  cmp     [rcx], edx
0x14002f247  jz      short loc_14002F267
0x14002f249  inc     eax
0x14002f24b  add     rcx, 58h ; 'X'
0x14002f24f  cmp     eax, 4
0x14002f252  jb      short loc_14002F245
0x14002f254  lea     r12, off_14004C048; "quicv2 key"
0x14002f25b  mov     rcx, r12
0x14002f25e  lea     r13, dword_14004C014
0x14002f265  jmp     short loc_14002F280
0x14002f267  imul    rcx, rax, 58h ; 'X'
0x14002f26b  lea     r13, [r8+4]
0x14002f26f  add     r13, rcx
0x14002f272  lea     r12, [r8+38h]
0x14002f276  add     r12, rcx
0x14002f279  add     rcx, 38h ; '8'
0x14002f27d  add     rcx, r8
0x14002f280  mov     rax, [rdi+8]
0x14002f284  test    rax, rax
0x14002f287  jz      short loc_14002F28D
0x14002f289  mov     [rax+28h], rcx
0x14002f28d  cmp     dword ptr [rbx], 4
0x14002f290  jnz     short loc_14002F2A3
0x14002f292  mov     rax, [rbx+500h]
0x14002f299  mov     bpl, [rax+11h]
0x14002f29d  lea     r15, [rax+20h]
0x14002f2a1  jmp     short loc_14002F2B2
0x14002f2a3  mov     rax, [rbx+508h]
0x14002f2aa  mov     bpl, [rax+21h]
0x14002f2ae  lea     r15, [rax+30h]
0x14002f2b2  lea     r14, [rdi+58h]
0x14002f2b6  cmp     qword ptr [r14], 0
0x14002f2ba  lea     rsi, [rdi+88h]
0x14002f2c1  jz      short loc_14002F2FB
0x14002f2c3  cmp     qword ptr [rsi], 0
0x14002f2c7  jnz     short loc_14002F2E3
0x14002f2c9  lea     r8, aCryptoTlsstate_3; "Crypto->TlsState.WriteKeys[QUIC_PACKET_"...
0x14002f2d0  mov     edx, 1B9h
0x14002f2d5  lea     rcx, aCW1SMsquicSrcC_15; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x14002f2dc  call    CxPlatLogAssert
0x14002f2e1  int     2Ch; Windows NT - assertion failure
0x14002f2e3  mov     rcx, [r14]; P
0x14002f2e6  call    QuicPacketKeyFree
0x14002f2eb  mov     rcx, [rsi]; P
0x14002f2ee  call    QuicPacketKeyFree
0x14002f2f3  and     qword ptr [r14], 0
0x14002f2f7  and     qword ptr [rsi], 0
0x14002f2fb  cmp     dword ptr [rbx], 4
0x14002f2fe  mov     r9b, bpl
0x14002f301  mov     [rsp+68h+var_38], rsi
0x14002f306  mov     r8, r13
0x14002f309  setz    cl
0x14002f30c  mov     [rsp+68h+var_40], r14
0x14002f311  mov     rdx, r12
0x14002f314  mov     [rsp+68h+var_48], r15
0x14002f319  call    QuicPacketKeyCreateInitial
0x14002f31e  movsxd  rsi, eax
0x14002f321  test    eax, eax
0x14002f323  jns     short loc_14002F39A
0x14002f325  test    cs:byte_14005C48B, 4
0x14002f32c  jz      short loc_14002F34C
0x14002f32e  lea     rax, aCreatingInitia; "Creating initial keys"
0x14002f335  mov     r9d, esi
0x14002f338  mov     r8, rbx
0x14002f33b  mov     [rsp+68h+var_48], rax
0x14002f340  lea     rdx, QuicConnErrorStatus
0x14002f347  call    McTemplateU0pqs_EtwWriteTransfer
0x14002f34c  mov     r8, rsi
0x14002f34f  mov     word ptr [rsp+68h+var_48], 13h
0x14002f356  lea     r9, aNewVersionKeyO; "New version key OOM"
0x14002f35d  mov     edx, 12h
0x14002f362  mov     rcx, rbx
0x14002f365  call    QuicConnTryClose
0x14002f36a  lea     rbx, [rdi+88h]
0x14002f371  mov     edi, 6
0x14002f376  mov     rcx, [rbx-30h]; P
0x14002f37a  call    QuicPacketKeyFree
0x14002f37f  mov     rcx, [rbx]; P
0x14002f382  and     qword ptr [rbx-30h], 0
0x14002f387  call    QuicPacketKeyFree
0x14002f38c  and     qword ptr [rbx], 0
0x14002f390  lea     rbx, [rbx+8]
0x14002f394  sub     rdi, 1
0x14002f398  jnz     short loc_14002F376
0x14002f39a  mov     eax, esi
0x14002f39c  lea     r11, [rsp+68h+var_28]
0x14002f3a1  mov     rbx, [r11+30h]
0x14002f3a5  mov     rbp, [r11+38h]
0x14002f3a9  mov     rsi, [r11+40h]
0x14002f3ad  mov     rsp, r11
0x14002f3b0  pop     r15
0x14002f3b2  pop     r14
0x14002f3b4  pop     r13
0x14002f3b6  pop     r12
0x14002f3b8  pop     rdi
0x14002f3b9  retn
```
