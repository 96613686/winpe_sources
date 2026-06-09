# MsQuicListenerStart

- ea: `0x140002840`
- end: `0x140002c9c`
- name: `MsQuicListenerStart`
- size: `1116`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x140001860`
- `0x140002840`
- `0x140002ca4`
- `0x140004460`
- `0x1400206e8`
- `0x14002bdf0`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003eca4`
- `0x14003ed00`
- `0x14003fcc4`
- `0x14003fdf8`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002bd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002bd0`
- `ntoskrnl!KeResetEvent` at `0x140002b51`
- `ntoskrnl!KeResetEvent` at `0x140002b51`
- `ntoskrnl!ExAllocatePool2` at `0x140002940`
- `ntoskrnl!ExAllocatePool2` at `0x140002940`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140002a79`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140002a79`

## pseudocode

```c
__int64 __fastcall MsQuicListenerStart(__int64 a1, const void **a2, unsigned int a3, unsigned __int16 *a4)
{
  __int64 v4; // r15
  const void **v6; // r14
  __int64 v7; // rdi
  unsigned int v8; // ebx
  unsigned int v9; // edx
  unsigned int v10; // eax
  int Binding; // ebx
  __int64 Pool2; // rax
  __int64 v13; // rdx
  char *v14; // rsi
  __int64 v15; // rbx
  char *v16; // rsi
  __int64 v17; // rax
  _OWORD *v18; // r14
  bool v19; // r15
  __int16 v20; // ax
  int ThreadObjectCompartmentId; // eax
  unsigned int v22; // ecx
  int v23; // eax
  __int64 v24; // rsi
  int v25; // ecx
  __int64 v26; // rcx
  void *v27; // rcx
  __int128 *v28; // rax
  _QWORD v30[10]; // [rsp+40h] [rbp-59h] BYREF
  __int128 v31; // [rsp+90h] [rbp-9h] BYREF
  __int64 v32; // [rsp+A0h] [rbp+7h]
  int v33; // [rsp+A8h] [rbp+Fh]

  v4 = a3;
  v32 = 0;
  v6 = a2;
  v33 = 0;
  v7 = a1;
  v31 = 0;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 10, a1);
  if ( v7 && *(_DWORD *)v7 == 2 && v6 && (_DWORD)v4 )
  {
    v8 = 0;
    v9 = 0;
    a1 = (__int64)v6;
    do
    {
      if ( (unsigned int)(*(_DWORD *)a1 - 1) > 0xFE )
        goto LABEL_57;
      ++v9;
      v8 += *(_DWORD *)a1 + 1;
      a1 += 16;
    }
    while ( v9 < (unsigned int)v4 );
    if ( v8 > 0xFFFF )
      goto LABEL_57;
    a1 = 23;
    if ( a4 )
    {
      v10 = *a4;
      if ( (unsigned __int16)v10 > 0x17u )
        goto LABEL_57;
      a1 = 8388613;
      if ( !_bittest((const int *)&a1, v10) )
        goto LABEL_57;
    }
    if ( !*(_BYTE *)(v7 + 18) )
    {
      Binding = -1073741436;
      goto LABEL_58;
    }
    Pool2 = ExAllocatePool2(66, v8, 808543057);
    v14 = (char *)Pool2;
    if ( !Pool2 )
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(a1, v13, "AlpnList", v8);
      Binding = -1073741801;
      goto LABEL_58;
    }
    *(_QWORD *)(v7 + 184) = Pool2;
    *(_WORD *)(v7 + 176) = v8;
    v15 = v4;
    do
    {
      *v14 = *(_BYTE *)v6;
      v16 = v14 + 1;
      memmove(v16, v6[1], *(unsigned int *)v6);
      v17 = *(unsigned int *)v6;
      v6 += 2;
      v14 = &v16[v17];
      --v15;
    }
    while ( v15 );
    v18 = (_OWORD *)(v7 + 112);
    if ( a4 )
    {
      *v18 = *(_OWORD *)a4;
      *(_QWORD *)(v7 + 128) = *((_QWORD *)a4 + 2);
      *(_DWORD *)(v7 + 136) = *((_DWORD *)a4 + 6);
      *(_BYTE *)(v7 + 16) = QuicAddrIsWildCard(a4);
      v19 = __ROR2__(a4[1], 8) == 0;
    }
    else
    {
      *v18 = 0;
      *(_QWORD *)(v7 + 128) = 0;
      v19 = 1;
      *(_DWORD *)(v7 + 136) = 0;
      *(_BYTE *)(v7 + 16) = 1;
    }
    LOWORD(v31) = 23;
    if ( v19 )
      v20 = 0;
    else
      v20 = __ROR2__(a4[1], 8);
    WORD1(v31) = __ROR2__(v20, 8);
    if ( !(unsigned __int8)QuicLibraryOnListenerRegistered() )
    {
      Binding = -1073741801;
LABEL_48:
      v27 = *(void **)(v7 + 144);
      if ( v27 )
      {
        QuicLibraryReleaseBinding(v27);
        *(_QWORD *)(v7 + 144) = 0;
      }
      a1 = *(_QWORD *)(v7 + 184);
      if ( a1 )
      {
        ExFreePoolWithTag((PVOID)a1, 0x30316351u);
        *(_QWORD *)(v7 + 184) = 0;
      }
      *(_WORD *)(v7 + 176) = 0;
      goto LABEL_58;
    }
    memset(v30, 0, 0x48u);
    v30[1] = 0;
    v30[0] = &v31;
    v30[2] = 6;
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
    v22 = *(unsigned __int8 *)(v7 + 192);
    LODWORD(v30[5]) = ThreadObjectCompartmentId;
    v30[6] = 0;
    LOBYTE(v30[7]) = v22;
    BYTE1(v30[7]) = byte_14005C561 + 2;
    BYTE2(v30[7]) = byte_14005C561 + 2;
    if ( (_BYTE)v22 )
      memmove((char *)&v30[7] + 3, (const void *)(v7 + 194), v22);
    v23 = v30[2];
    if ( byte_14005C53C < 0 )
    {
      v23 = LODWORD(v30[2]) | 8;
      LODWORD(v30[2]) |= 8u;
    }
    if ( (byte_14005C53D & 1) != 0 )
    {
      v23 |= 0x10u;
      LODWORD(v30[2]) = v23;
    }
    if ( (byte_14005C53D & 2) != 0 )
      LODWORD(v30[2]) = v23 | 0x20;
    v24 = v7 + 144;
    if ( *(_QWORD *)(v7 + 144) )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\listener.c", 343, "Listener->Binding == ((void *)0)");
    Binding = QuicLibraryGetBinding(v30, v7 + 144);
    if ( Binding < 0 )
    {
      if ( (byte_14005C489 & 0x20) != 0 )
        McTemplateU0pqs_EtwWriteTransfer(
          v25,
          (unsigned int)QuicListenerErrorStatus,
          v7,
          Binding,
          (__int64)"Get binding");
      goto LABEL_48;
    }
    *(_BYTE *)(v7 + 18) = 0;
    KeResetEvent((PRKEVENT)(v7 + 88));
    v26 = *(_QWORD *)v24;
    *(_QWORD *)(v7 + 80) = 1;
    Binding = QuicBindingRegisterListener(v26, v7);
    if ( Binding < 0 )
    {
      if ( (byte_14005C489 & 0x20) != 0 )
        McTemplateU0pqs_EtwWriteTransfer(
          a1,
          (unsigned int)QuicListenerErrorStatus,
          v7,
          Binding,
          (__int64)"Register with binding");
      QuicListenerRelease(v7, 0);
      goto LABEL_48;
    }
    if ( v19 )
    {
      v28 = *(__int128 **)(*(_QWORD *)v24 + 32LL);
      v31 = *v28;
      v32 = *((_QWORD *)v28 + 2);
      v33 = *((_DWORD *)v28 + 6);
      *(_WORD *)(v7 + 114) = WORD1(v31);
    }
    if ( (byte_14005C489 & 0x10) != 0 )
      McTemplateU0ppubr2ubr4_EtwWriteTransfer(a1, (unsigned int)QuicListenerStarted, v7, *(_QWORD *)v24);
  }
  else
  {
LABEL_57:
    Binding = -1073741811;
  }
LABEL_58:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, QuicApiExitStatus, (unsigned int)Binding);
  return (unsigned int)Binding;
}

```

## disassembly

```asm
0x140002840  mov     [rsp-8+arg_10], rbx
0x140002845  push    rbp
0x140002846  push    rsi
0x140002847  push    rdi
0x140002848  push    r12
0x14000284a  push    r13
0x14000284c  push    r14
0x14000284e  push    r15
0x140002850  lea     rbp, [rsp-27h]
0x140002855  sub     rsp, 0C0h
0x14000285c  mov     rax, cs:__security_cookie
0x140002863  xor     rax, rsp
0x140002866  mov     [rbp+57h+var_40], rax
0x14000286a  xor     eax, eax
0x14000286c  mov     r15d, r8d
0x14000286f  test    cs:Microsoft_QuicEnableBits, 8
0x140002876  xorps   xmm0, xmm0
0x140002879  mov     r12, r9
0x14000287c  mov     [rbp+57h+var_50], rax
0x140002880  mov     r14, rdx
0x140002883  mov     [rbp+57h+var_48], eax
0x140002886  mov     rdi, rcx
0x140002889  movups  [rbp+57h+var_60], xmm0
0x14000288d  jz      short loc_14000289B
0x14000288f  mov     r9, rcx
0x140002892  lea     r8d, [rax+0Ah]
0x140002896  call    McTemplateU0qp_EtwWriteTransfer
0x14000289b  test    rdi, rdi
0x14000289e  jz      loc_140002C55
0x1400028a4  cmp     dword ptr [rdi], 2
0x1400028a7  jnz     loc_140002C55
0x1400028ad  test    r14, r14
0x1400028b0  jz      loc_140002C55
0x1400028b6  test    r15d, r15d
0x1400028b9  jz      loc_140002C55
0x1400028bf  xor     ebx, ebx
0x1400028c1  xor     edx, edx
0x1400028c3  test    r15d, r15d
0x1400028c6  jz      short loc_1400028FA
0x1400028c8  mov     rcx, r14
0x1400028cb  mov     r8d, [rcx]
0x1400028ce  lea     eax, [r8-1]
0x1400028d2  cmp     eax, 0FEh
0x1400028d7  ja      loc_140002C55
0x1400028dd  inc     ebx
0x1400028df  inc     edx
0x1400028e1  add     ebx, r8d
0x1400028e4  add     rcx, 10h
0x1400028e8  mov     eax, ebx
0x1400028ea  cmp     edx, r15d
0x1400028ed  jb      short loc_1400028CB
0x1400028ef  cmp     eax, 0FFFFh
0x1400028f4  ja      loc_140002C55
0x1400028fa  mov     ecx, 17h
0x1400028ff  test    r12, r12
0x140002902  jz      short loc_140002920
0x140002904  movzx   eax, word ptr [r12]
0x140002909  cmp     ax, cx
0x14000290c  ja      loc_140002C55
0x140002912  mov     ecx, 800005h
0x140002917  bt      ecx, eax
0x14000291a  jnb     loc_140002C55
0x140002920  cmp     byte ptr [rdi+12h], 0
0x140002924  jnz     short loc_140002930
0x140002926  mov     ebx, 0C0000184h
0x14000292b  jmp     loc_140002C5A
0x140002930  mov     r8d, 30316351h
0x140002936  mov     edx, ebx
0x140002938  mov     ecx, 42h ; 'B'
0x14000293d  mov     r13d, ebx
0x140002940  call    cs:__imp_ExAllocatePool2
0x140002947  nop     dword ptr [rax+rax+00h]
0x14000294c  mov     rsi, rax
0x14000294f  test    rax, rax
0x140002952  jnz     short loc_140002976
0x140002954  test    cs:Microsoft_QuicEnableBits, 2
0x14000295b  jz      short loc_14000296C
0x14000295d  mov     r9d, r13d
0x140002960  lea     r8, aAlpnlist; "AlpnList"
0x140002967  call    McTemplateU0sx_EtwWriteTransfer
0x14000296c  mov     ebx, 0C0000017h
0x140002971  jmp     loc_140002C5A
0x140002976  xor     r13d, r13d
0x140002979  mov     [rdi+0B8h], rax
0x140002980  mov     [rdi+0B0h], bx
0x140002987  test    r15d, r15d
0x14000298a  jz      short loc_1400029B6
0x14000298c  mov     rbx, r15
0x14000298f  mov     al, [r14]
0x140002992  mov     [rsi], al
0x140002994  inc     rsi
0x140002997  mov     r8d, [r14]; Size
0x14000299a  mov     rcx, rsi; void *
0x14000299d  mov     rdx, [r14+8]; Src
0x1400029a1  call    memmove
0x1400029a6  mov     eax, [r14]
0x1400029a9  lea     r14, [r14+10h]
0x1400029ad  add     rsi, rax
0x1400029b0  sub     rbx, 1
0x1400029b4  jnz     short loc_14000298F
0x1400029b6  lea     r14, [rdi+70h]
0x1400029ba  test    r12, r12
0x1400029bd  jz      short loc_1400029FC
0x1400029bf  movups  xmm0, xmmword ptr [r12]
0x1400029c4  mov     rcx, r12
0x1400029c7  movups  xmmword ptr [r14], xmm0
0x1400029cb  movsd   xmm1, qword ptr [r12+10h]
0x1400029d2  movsd   qword ptr [r14+10h], xmm1
0x1400029d8  mov     eax, [r12+18h]
0x1400029dd  mov     [r14+18h], eax
0x1400029e1  call    QuicAddrIsWildCard
0x1400029e6  mov     [rdi+10h], al
0x1400029e9  movzx   eax, word ptr [r12+2]
0x1400029ef  ror     ax, 8
0x1400029f3  test    ax, ax
0x1400029f6  setz    r15b
0x1400029fa  jmp     short loc_140002A14
0x1400029fc  xor     eax, eax
0x1400029fe  xorps   xmm0, xmm0
0x140002a01  movups  xmmword ptr [r14], xmm0
0x140002a05  mov     [r14+10h], rax
0x140002a09  mov     r15b, 1
0x140002a0c  mov     [r14+18h], eax
0x140002a10  mov     byte ptr [rdi+10h], 1
0x140002a14  mov     eax, 17h
0x140002a19  mov     word ptr [rbp+57h+var_60], ax
0x140002a1d  test    r15b, r15b
0x140002a20  jz      short loc_140002A28
0x140002a22  movzx   eax, r13w
0x140002a26  jmp     short loc_140002A32
0x140002a28  movzx   eax, word ptr [r12+2]
0x140002a2e  ror     ax, 8
0x140002a32  ror     ax, 8
0x140002a36  mov     word ptr [rbp+57h+var_60+2], ax
0x140002a3a  call    QuicLibraryOnListenerRegistered
0x140002a3f  test    al, al
0x140002a41  jnz     short loc_140002A4D
0x140002a43  mov     ebx, 0C0000017h
0x140002a48  jmp     loc_140002BA7
0x140002a4d  xor     edx, edx; Val
0x140002a4f  lea     rcx, [rbp+57h+var_B0]; void *
0x140002a53  lea     r8d, [rdx+48h]; Size
0x140002a57  call    memset
0x140002a5c  lea     rax, [rbp+57h+var_60]
0x140002a60  mov     [rbp+57h+var_A8], r13
0x140002a64  mov     [rbp+57h+var_B0], rax
0x140002a68  mov     [rbp+57h+var_A0], 6
0x140002a70  mov     rcx, gs:188h
0x140002a79  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140002a80  nop     dword ptr [rax+rax+00h]
0x140002a85  movzx   ecx, byte ptr [rdi+0C0h]
0x140002a8c  mov     [rbp+57h+var_88], eax
0x140002a8f  mov     al, cs:byte_14005C561
0x140002a95  add     al, 2
0x140002a97  mov     [rbp+57h+var_80], r13
0x140002a9b  mov     [rbp+57h+var_78], cl
0x140002a9e  mov     [rbp+57h+var_77], al
0x140002aa1  mov     [rbp+57h+var_76], al
0x140002aa4  test    cl, cl
0x140002aa6  jz      short loc_140002ABB
0x140002aa8  mov     r8d, ecx; Size
0x140002aab  lea     rdx, [rdi+0C2h]; Src
0x140002ab2  lea     rcx, [rbp+57h+var_75]; void *
0x140002ab6  call    memmove
0x140002abb  mov     al, cs:byte_14005C53C
0x140002ac1  test    al, al
0x140002ac3  mov     eax, dword ptr [rbp+57h+var_A0]
0x140002ac6  jns     short loc_140002ACE
0x140002ac8  or      eax, 8
0x140002acb  mov     dword ptr [rbp+57h+var_A0], eax
0x140002ace  mov     cl, cs:byte_14005C53D
0x140002ad4  test    cl, 1
0x140002ad7  jz      short loc_140002ADF
0x140002ad9  or      eax, 10h
0x140002adc  mov     dword ptr [rbp+57h+var_A0], eax
0x140002adf  test    cl, 2
0x140002ae2  jz      short loc_140002AEA
0x140002ae4  or      eax, 20h
0x140002ae7  mov     dword ptr [rbp+57h+var_A0], eax
0x140002aea  lea     rsi, [rdi+90h]
0x140002af1  cmp     [rsi], r13
0x140002af4  jz      short loc_140002B0E
0x140002af6  lea     r8, aListenerBindin; "Listener->Binding == ((void *)0)"
0x140002afd  mov     edx, 157h
0x140002b02  lea     rcx, aCW1SMsquicSrcC; "C:\\__w\\1\\s\\msquic\\src\\core\\liste"...
0x140002b09  call    CxPlatLogAssert
0x140002b0e  mov     rdx, rsi
0x140002b11  lea     rcx, [rbp+57h+var_B0]
0x140002b15  call    QuicLibraryGetBinding
0x140002b1a  mov     ebx, eax
0x140002b1c  test    eax, eax
0x140002b1e  jns     short loc_140002B49
0x140002b20  test    cs:byte_14005C489, 20h
0x140002b27  jz      short loc_140002BA7
0x140002b29  lea     rax, aGetBinding; "Get binding"
0x140002b30  mov     r9d, ebx
0x140002b33  mov     r8, rdi
0x140002b36  mov     [rsp+0F0h+var_D0], rax
0x140002b3b  lea     rdx, QuicListenerErrorStatus
0x140002b42  call    McTemplateU0pqs_EtwWriteTransfer
0x140002b47  jmp     short loc_140002BA7
0x140002b49  lea     rcx, [rdi+58h]; Event
0x140002b4d  mov     [rdi+12h], r13b
0x140002b51  call    cs:__imp_KeResetEvent
0x140002b58  nop     dword ptr [rax+rax+00h]
0x140002b5d  mov     rcx, [rsi]
0x140002b60  mov     rdx, rdi
0x140002b63  mov     qword ptr [rdi+50h], 1
0x140002b6b  call    QuicBindingRegisterListener
0x140002b70  mov     ebx, eax
0x140002b72  test    eax, eax
0x140002b74  jns     short loc_140002BED
0x140002b76  test    cs:byte_14005C489, 20h
0x140002b7d  jz      short loc_140002B9D
0x140002b7f  lea     rax, aRegisterWithBi; "Register with binding"
0x140002b86  mov     r9d, ebx
0x140002b89  mov     r8, rdi
0x140002b8c  mov     [rsp+0F0h+var_D0], rax
0x140002b91  lea     rdx, QuicListenerErrorStatus
0x140002b98  call    McTemplateU0pqs_EtwWriteTransfer
0x140002b9d  xor     edx, edx
0x140002b9f  mov     rcx, rdi
0x140002ba2  call    QuicListenerRelease
0x140002ba7  mov     rcx, [rdi+90h]; P
0x140002bae  test    rcx, rcx
0x140002bb1  jz      short loc_140002BBF
0x140002bb3  call    QuicLibraryReleaseBinding
0x140002bb8  mov     [rdi+90h], r13
0x140002bbf  mov     rcx, [rdi+0B8h]; P
0x140002bc6  test    rcx, rcx
0x140002bc9  jz      short loc_140002BE3
0x140002bcb  mov     edx, 30316351h; Tag
0x140002bd0  call    cs:__imp_ExFreePoolWithTag
0x140002bd7  nop     dword ptr [rax+rax+00h]
0x140002bdc  mov     [rdi+0B8h], r13
0x140002be3  mov     [rdi+0B0h], r13w
0x140002beb  jmp     short loc_140002C5A
0x140002bed  test    r15b, r15b
0x140002bf0  jz      short loc_140002C1D
0x140002bf2  mov     rax, [rsi]
0x140002bf5  mov     rax, [rax+20h]
0x140002bf9  movups  xmm1, xmmword ptr [rax]
0x140002bfc  movups  [rbp+57h+var_60], xmm1
0x140002c00  movsd   xmm0, qword ptr [rax+10h]
0x140002c05  movsd   [rbp+57h+var_50], xmm0
0x140002c0a  mov     eax, [rax+18h]
0x140002c0d  mov     [rbp+57h+var_48], eax
0x140002c10  movq    rax, xmm1
0x140002c15  shr     rax, 10h
0x140002c19  mov     [rdi+72h], ax
0x140002c1d  test    cs:byte_14005C489, 10h
0x140002c24  jz      short loc_140002C5A
0x140002c26  mov     rax, [rdi+0B8h]
0x140002c2d  lea     rdx, QuicListenerStarted
0x140002c34  mov     r9, [rsi]
0x140002c37  mov     r8, rdi
0x140002c3a  mov     [rsp+0F0h+var_B8], rax
0x140002c3f  mov     al, [rdi+0B0h]
0x140002c45  mov     [rsp+0F0h+var_C0], al
0x140002c49  mov     [rsp+0F0h+var_C8], r14
0x140002c4e  call    McTemplateU0ppubr2ubr4_EtwWriteTransfer
0x140002c53  jmp     short loc_140002C5A
0x140002c55  mov     ebx, 0C000000Dh
0x140002c5a  test    cs:Microsoft_QuicEnableBits, 8
0x140002c61  jz      short loc_140002C72
0x140002c63  mov     r8d, ebx
0x140002c66  lea     rdx, QuicApiExitStatus
0x140002c6d  call    McTemplateU0q_EtwWriteTransfer
0x140002c72  mov     eax, ebx
0x140002c74  mov     rcx, [rbp+57h+var_40]
0x140002c78  xor     rcx, rsp; StackCookie
0x140002c7b  call    __security_check_cookie
0x140002c80  mov     rbx, [rsp+0F0h+arg_10]
0x140002c88  add     rsp, 0C0h
0x140002c8f  pop     r15
0x140002c91  pop     r14
0x140002c93  pop     r13
0x140002c95  pop     r12
0x140002c97  pop     rdi
0x140002c98  pop     rsi
0x140002c99  pop     rbp
0x140002c9a  retn
```
