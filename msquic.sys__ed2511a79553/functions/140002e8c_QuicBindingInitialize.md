# QuicBindingInitialize

- ea: `0x140002e8c`
- end: `0x14000318f`
- name: `QuicBindingInitialize`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140004460`

## callees

- `0x140002e8c`
- `0x140020984`
- `0x140029094`
- `0x140033810`
- `0x14003501c`
- `0x140038bf4`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003ed00`
- `0x14003fcc4`
- `0x14003fdf8`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140002f55`
- `ntoskrnl!KeInitializeSpinLock` at `0x140002f55`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400030c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400030c9`
- `ntoskrnl!ExAllocatePool2` at `0x140002ed2`
- `ntoskrnl!ExAllocatePool2` at `0x140002ed2`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x140002ffe`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x14000306d`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x140002ffe`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x14000306d`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140002fde`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140002fde`

## string_xrefs

- `0x14000301d`: `Set current compartment Id`
- `0x140003086`: `Create datapath binding`

## pseudocode

```c
__int64 __fastcall QuicBindingInitialize(__int64 a1, __int64 *a2)
{
  char v3; // r12
  __int64 Pool2; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdi
  int Udp; // ebx
  char v9; // cl
  char v10; // dl
  bool v11; // cf
  void *v12; // rsi
  char v13; // r15
  int v14; // ecx
  int v15; // ecx

  v3 = 0;
  Pool2 = ExAllocatePool2(66, 320, 925983569);
  v7 = Pool2;
  if ( !Pool2 )
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v6, v5, "QUIC_BINDING", 320);
    return (unsigned int)-1073741801;
  }
  *(_DWORD *)(Pool2 + 20) = 0;
  v9 = *(_BYTE *)(Pool2 + 16) & 0xFE | ((*(_DWORD *)(a1 + 16) & 2) == 0);
  *(_BYTE *)(Pool2 + 16) = v9;
  v10 = v9 & 0xFD | (*(_DWORD *)(a1 + 16) >> 1) & 2;
  *(_BYTE *)(Pool2 + 16) = v10;
  v11 = *(_QWORD *)(a1 + 8) != 0;
  *(_DWORD *)(Pool2 + 304) = 0;
  *(_BYTE *)(Pool2 + 16) = v10 & 0xFB | (v11 ? 4 : 0);
  *(_DWORD *)(Pool2 + 40) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 128));
  *(_QWORD *)(v7 + 56) = v7 + 48;
  *(_QWORD *)(v7 + 48) = v7 + 48;
  memset((void *)(v7 + 64), 0, 0x40u);
  v12 = (void *)(v7 + 144);
  *(_DWORD *)(v7 + 72) = 0;
  if ( !(unsigned __int8)CxPlatHashtableInitializeEx(v7 + 144) )
  {
    Udp = -1073741801;
LABEL_18:
    QuicLookupUninitialize(v7 + 64);
    if ( v3 )
      CxPlatHashtableUninitialize(v12);
    ExFreePoolWithTag((PVOID)v7, 0x37316351u);
    return (unsigned int)Udp;
  }
  *(_QWORD *)(v7 + 192) = v7 + 184;
  *(_QWORD *)(v7 + 184) = v7 + 184;
  v3 = 1;
  CxPlatRandom(4u);
  v13 = 0;
  *(_DWORD *)(v7 + 24) = *(_DWORD *)(v7 + 24) & 0xF0F0F0F0 | 0xA0A0A0A;
  *(_DWORD *)(v7 + 28) = *(_DWORD *)(a1 + 40);
  if ( (unsigned int)NdisGetThreadObjectCompartmentId(KeGetCurrentThread()) != *(_DWORD *)(a1 + 40) )
  {
    Udp = NdisSetThreadObjectCompartmentId(KeGetCurrentThread());
    if ( Udp < 0 )
    {
      if ( (byte_14005C48D & 0x20) != 0 )
        McTemplateU0pqs_EtwWriteTransfer(
          v14,
          (unsigned int)QuicBindingErrorStatus,
          v7,
          Udp,
          (__int64)"Set current compartment Id");
      goto LABEL_18;
    }
    v13 = 1;
  }
  *(_QWORD *)(a1 + 32) = v7;
  Udp = CxPlatSocketCreateUdp(qword_14005C590, a1, v7 + 32);
  if ( v13 )
    NdisSetThreadObjectCompartmentId(KeGetCurrentThread());
  if ( Udp < 0 )
  {
    if ( (byte_14005C48D & 0x20) != 0 )
      McTemplateU0pqs_EtwWriteTransfer(
        v15,
        (unsigned int)QuicBindingErrorStatus,
        v7,
        Udp,
        (__int64)"Create datapath binding");
    v12 = (void *)(v7 + 144);
    goto LABEL_18;
  }
  if ( (byte_14005C48D & 4) != 0 )
    McTemplateU0ppubr2ubr4_EtwWriteTransfer(v15, (unsigned int)QuicBindingCreated, v7, *(_QWORD *)(v7 + 32));
  Udp = 0;
  *a2 = v7;
  return (unsigned int)Udp;
}

```

## disassembly

```asm
0x140002e8c  mov     [rsp-8+arg_10], rbx
0x140002e91  push    rbp
0x140002e92  push    rsi
0x140002e93  push    rdi
0x140002e94  push    r12
0x140002e96  push    r13
0x140002e98  push    r14
0x140002e9a  push    r15
0x140002e9c  lea     rbp, [rsp-27h]
0x140002ea1  sub     rsp, 90h
0x140002ea8  mov     rax, cs:__security_cookie
0x140002eaf  xor     rax, rsp
0x140002eb2  mov     [rbp+57h+var_38], rax
0x140002eb6  xor     ebx, ebx
0x140002eb8  mov     [rbp+57h+var_80], rdx
0x140002ebc  mov     r14, rcx
0x140002ebf  mov     esi, 140h
0x140002ec4  mov     r8d, 37316351h
0x140002eca  mov     edx, esi
0x140002ecc  mov     r12b, bl
0x140002ecf  lea     ecx, [rbx+42h]
0x140002ed2  call    cs:__imp_ExAllocatePool2
0x140002ed9  nop     dword ptr [rax+rax+00h]
0x140002ede  mov     rdi, rax
0x140002ee1  test    rax, rax
0x140002ee4  jnz     short loc_140002F08
0x140002ee6  test    cs:Microsoft_QuicEnableBits, 2
0x140002eed  jz      short loc_140002EFE
0x140002eef  mov     r9d, esi
0x140002ef2  lea     r8, aQuicBinding; "QUIC_BINDING"
0x140002ef9  call    McTemplateU0sx_EtwWriteTransfer
0x140002efe  mov     ebx, 0C0000017h
0x140002f03  jmp     loc_140003165
0x140002f08  mov     [rax+14h], ebx
0x140002f0b  mov     ecx, [r14+10h]
0x140002f0f  mov     al, [rax+10h]
0x140002f12  shr     ecx, 1
0x140002f14  and     al, 0FEh
0x140002f16  not     cl
0x140002f18  and     cl, 1
0x140002f1b  or      cl, al
0x140002f1d  mov     [rdi+10h], cl
0x140002f20  and     cl, 0FDh
0x140002f23  mov     edx, [r14+10h]
0x140002f27  shr     edx, 1
0x140002f29  and     dl, 2
0x140002f2c  or      dl, cl
0x140002f2e  mov     [rdi+10h], dl
0x140002f31  mov     rax, [r14+8]
0x140002f35  neg     rax
0x140002f38  mov     [rdi+130h], ebx
0x140002f3e  sbb     cl, cl
0x140002f40  and     dl, 0FBh
0x140002f43  and     cl, 4
0x140002f46  or      cl, dl
0x140002f48  mov     [rdi+10h], cl
0x140002f4b  lea     rcx, [rdi+80h]; SpinLock
0x140002f52  mov     [rdi+28h], ebx
0x140002f55  call    cs:__imp_KeInitializeSpinLock
0x140002f5c  nop     dword ptr [rax+rax+00h]
0x140002f61  lea     rax, [rdi+30h]
0x140002f65  xor     edx, edx; Val
0x140002f67  lea     rcx, [rdi+40h]; void *
0x140002f6b  mov     [rax+8], rax
0x140002f6f  mov     [rax], rax
0x140002f72  lea     r8d, [rdx+40h]; Size
0x140002f76  call    memset
0x140002f7b  lea     rsi, [rdi+90h]
0x140002f82  mov     [rdi+48h], ebx
0x140002f85  mov     rcx, rsi
0x140002f88  call    CxPlatHashtableInitializeEx
0x140002f8d  test    al, al
0x140002f8f  jnz     short loc_140002F9B
0x140002f91  mov     ebx, 0C0000017h
0x140002f96  jmp     loc_1400030AB
0x140002f9b  lea     rax, [rdi+0B8h]
0x140002fa2  mov     ecx, 4; cbBuffer
0x140002fa7  lea     rbx, [rdi+18h]
0x140002fab  mov     [rax+8], rax
0x140002faf  mov     rdx, rbx
0x140002fb2  mov     [rax], rax
0x140002fb5  mov     r12b, 1
0x140002fb8  call    CxPlatRandom
0x140002fbd  mov     eax, [rbx]
0x140002fbf  xor     r15b, r15b
0x140002fc2  and     eax, 0FAFAFAFAh
0x140002fc7  or      eax, 0A0A0A0Ah
0x140002fcc  mov     [rbx], eax
0x140002fce  mov     eax, [r14+28h]
0x140002fd2  mov     [rdi+1Ch], eax
0x140002fd5  mov     rcx, gs:188h
0x140002fde  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140002fe5  nop     dword ptr [rax+rax+00h]
0x140002fea  mov     edx, [r14+28h]
0x140002fee  mov     r13d, eax
0x140002ff1  cmp     eax, edx
0x140002ff3  jz      short loc_140003040
0x140002ff5  mov     rcx, gs:188h
0x140002ffe  call    cs:__imp_NdisSetThreadObjectCompartmentId
0x140003005  nop     dword ptr [rax+rax+00h]
0x14000300a  mov     ebx, eax
0x14000300c  test    eax, eax
0x14000300e  jns     short loc_14000303D
0x140003010  test    cs:byte_14005C48D, 20h
0x140003017  jz      loc_1400030AB
0x14000301d  lea     rax, aSetCurrentComp; "Set current compartment Id"
0x140003024  mov     r9d, ebx
0x140003027  mov     r8, rdi
0x14000302a  mov     [rsp+0C0h+var_A0], rax
0x14000302f  lea     rdx, QuicBindingErrorStatus
0x140003036  call    McTemplateU0pqs_EtwWriteTransfer
0x14000303b  jmp     short loc_1400030AB
0x14000303d  mov     r15b, r12b
0x140003040  mov     [r14+20h], rdi
0x140003044  lea     rsi, [rdi+20h]
0x140003048  mov     rcx, cs:qword_14005C590
0x14000304f  mov     r8, rsi
0x140003052  mov     rdx, r14
0x140003055  call    CxPlatSocketCreateUdp
0x14000305a  mov     ebx, eax
0x14000305c  test    r15b, r15b
0x14000305f  jz      short loc_140003079
0x140003061  mov     rcx, gs:188h
0x14000306a  mov     edx, r13d
0x14000306d  call    cs:__imp_NdisSetThreadObjectCompartmentId
0x140003074  nop     dword ptr [rax+rax+00h]
0x140003079  test    ebx, ebx
0x14000307b  jns     short loc_1400030DA
0x14000307d  test    cs:byte_14005C48D, 20h
0x140003084  jz      short loc_1400030A4
0x140003086  lea     rax, aCreateDatapath; "Create datapath binding"
0x14000308d  mov     r9d, ebx
0x140003090  mov     r8, rdi
0x140003093  mov     [rsp+0C0h+var_A0], rax
0x140003098  lea     rdx, QuicBindingErrorStatus
0x14000309f  call    McTemplateU0pqs_EtwWriteTransfer
0x1400030a4  lea     rsi, [rdi+90h]
0x1400030ab  lea     rcx, [rdi+40h]
0x1400030af  call    QuicLookupUninitialize
0x1400030b4  test    r12b, r12b
0x1400030b7  jz      short loc_1400030C1
0x1400030b9  mov     rcx, rsi; P
0x1400030bc  call    CxPlatHashtableUninitialize
0x1400030c1  mov     edx, 37316351h; Tag
0x1400030c6  mov     rcx, rdi; P
0x1400030c9  call    cs:__imp_ExFreePoolWithTag
0x1400030d0  nop     dword ptr [rax+rax+00h]
0x1400030d5  jmp     loc_140003165
0x1400030da  xor     eax, eax
0x1400030dc  xorps   xmm0, xmm0
0x1400030df  test    cs:byte_14005C48D, 4
0x1400030e6  movups  [rbp+57h+var_58], xmm0
0x1400030ea  mov     [rbp+57h+var_48], rax
0x1400030ee  mov     [rbp+57h+var_40], eax
0x1400030f1  movups  [rbp+57h+var_78], xmm0
0x1400030f5  mov     [rbp+57h+var_68], rax
0x1400030f9  mov     [rbp+57h+var_60], eax
0x1400030fc  mov     rax, [rsi]
0x1400030ff  movups  xmm0, xmmword ptr [rax]
0x140003102  movups  [rbp+57h+var_58], xmm0
0x140003106  movsd   xmm1, qword ptr [rax+10h]
0x14000310b  movsd   [rbp+57h+var_48], xmm1
0x140003110  mov     eax, [rax+18h]
0x140003113  mov     [rbp+57h+var_40], eax
0x140003116  mov     rax, [rsi]
0x140003119  movups  xmm0, xmmword ptr [rax+1Ch]
0x14000311d  movups  [rbp+57h+var_78], xmm0
0x140003121  movsd   xmm1, qword ptr [rax+2Ch]
0x140003126  movsd   [rbp+57h+var_68], xmm1
0x14000312b  mov     eax, [rax+34h]
0x14000312e  mov     [rbp+57h+var_60], eax
0x140003131  jz      short loc_14000315C
0x140003133  mov     r9, [rsi]
0x140003136  lea     rax, [rbp+57h+var_78]
0x14000313a  mov     [rsp+0C0h+var_88], rax
0x14000313f  lea     rdx, QuicBindingCreated
0x140003146  lea     rax, [rbp+57h+var_58]
0x14000314a  mov     [rsp+0C0h+var_90], 1Ch
0x14000314f  mov     r8, rdi
0x140003152  mov     [rsp+0C0h+var_98], rax
0x140003157  call    McTemplateU0ppubr2ubr4_EtwWriteTransfer
0x14000315c  mov     rax, [rbp+57h+var_80]
0x140003160  xor     ebx, ebx
0x140003162  mov     [rax], rdi
0x140003165  mov     eax, ebx
0x140003167  mov     rcx, [rbp+57h+var_38]
0x14000316b  xor     rcx, rsp; StackCookie
0x14000316e  call    __security_check_cookie
0x140003173  mov     rbx, [rsp+0C0h+arg_10]
0x14000317b  add     rsp, 90h
0x140003182  pop     r15
0x140003184  pop     r14
0x140003186  pop     r13
0x140003188  pop     r12
0x14000318a  pop     rdi
0x14000318b  pop     rsi
0x14000318c  pop     rbp
0x14000318d  retn
```
