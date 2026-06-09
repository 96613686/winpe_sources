# SendControl

- ea: `0x14000fd0c`
- end: `0x1400100c8`
- name: `SendControl`
- size: `956`
- prototype: ``
- caller_count: `11`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14000faa0`
- `0x1400102a0`
- `0x1400122e0`
- `0x140012400`
- `0x1400124b4`
- `0x1400128bc`
- `0x140012b20`
- `0x1400133ac`
- `0x1400135f0`
- `0x140013820`
- `0x140015050`

## callees

- `0x140001990`
- `0x140003050`
- `0x140003080`
- `0x140004830`
- `0x140004c00`
- `0x14000fd0c`
- `0x14001c050`
- `0x14001c400`
- `0x14001c620`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000fe2c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000fe6f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000fe2c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000fe6f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000fed8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000fed8`
- `NDIS!NdisAllocateNetBufferList` at `0x14000fd91`
- `NDIS!NdisAllocateNetBufferList` at `0x14000fd91`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14000fde4`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14000fde4`
- `NDIS!NdisGetDataBuffer` at `0x14000fe04`
- `NDIS!NdisGetDataBuffer` at `0x14000fe04`
- `NDIS!NdisFreeNetBufferList` at `0x14000feb9`
- `NDIS!NdisFreeNetBufferList` at `0x14000feb9`

## pseudocode

```c
__int64 __fastcall SendControl(__int64 a1, __int64 a2, unsigned __int16 a3, int a4, int a5, _WORD *DataBuffer, int a7)
{
  __int64 v7; // r12
  __int64 v10; // rbx
  PNET_BUFFER_LIST NetBufferList; // rax
  struct _NET_BUFFER_LIST *v12; // r14
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // r15
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  int v18; // edx
  PVOID v19; // rsi
  __int16 v20; // ax
  __int64 v21; // rbx
  __int64 v22; // r8
  int v23; // ecx
  int v24; // eax
  __int64 v25; // rcx
  _QWORD *v26; // rcx
  int v28; // [rsp+90h] [rbp+8h] BYREF
  __int16 v29; // [rsp+A0h] [rbp+18h] BYREF
  int v30; // [rsp+A8h] [rbp+20h]

  v30 = a4;
  v7 = a3;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids, a3);
  }
  if ( (unsigned __int16)(v7 - 1) > 0xFu )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return ScheduleTunnelWork(a1, 0, (unsigned int)FsmCloseTunnel, 2, 4, 0, 0, 0, 0);
    }
    v14 = 11;
    goto LABEL_36;
  }
  v10 = *(_QWORD *)(a1 + 24);
  NetBufferList = NdisAllocateNetBufferList(*(NDIS_HANDLE *)(v10 + 208), 0, 0);
  v12 = NetBufferList;
  if ( !NetBufferList )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return ScheduleTunnelWork(a1, 0, (unsigned int)FsmCloseTunnel, 2, 4, 0, 0, 0, 0);
    }
    v14 = 12;
LABEL_36:
    WPP_SF_(v13->AttachedDevice, v14, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
    return ScheduleTunnelWork(a1, 0, (unsigned int)FsmCloseTunnel, 2, 4, 0, 0, 0, 0);
  }
  NdisRetreatNetBufferDataStart(NetBufferList->FirstNetBuffer, 0x612u, 0, 0);
  DataBuffer = NdisGetDataBuffer(v12->FirstNetBuffer, 0x612u, 0, 1u, 0);
  memset(DataBuffer, 0, 0x612u);
  v15 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576));
  if ( !v15 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v17 = 13;
LABEL_21:
      WPP_SF_(v16->AttachedDevice, v17, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v19 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 704));
  if ( !v19 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v17 = 14;
      goto LABEL_21;
    }
LABEL_22:
    NdisFreeNetBufferList(v12);
    if ( v15 )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 576), v15);
    return ScheduleTunnelWork(a1, 0, (unsigned int)FsmCloseTunnel, 2, 4, 0, 0, 0, 0);
  }
  if ( a2 )
    v20 = *(_WORD *)(a2 + 58);
  else
    v20 = 0;
  v29 = v20;
  LOBYTE(v18) = 1;
  v21 = (unsigned int)BuildL2tpHeader(
                        (_DWORD)DataBuffer,
                        v18,
                        0,
                        (int)a1 + 116,
                        (__int64)&v29,
                        a1 + 200,
                        *(_WORD *)(a1 + 280));
  off_140007050[v7 - 1](a1, a2, v30, a5, v22, (__int64)DataBuffer + v21, (__int64)&v28);
  v23 = v21 + v28;
  DataBuffer[1] = __ROR2__(v21 + v28, 8);
  *(_DWORD *)(v12->Link.Region + 24) = v23;
  *((_DWORD *)v19 + 4) = 0;
  *((_WORD *)v19 + 10) = *(_WORD *)(a1 + 200);
  v24 = a7;
  *((_WORD *)v19 + 11) = v7;
  v15[1] = v15;
  *v15 = v15;
  *((_DWORD *)v19 + 9) = v24 | 1;
  *((_QWORD *)v19 + 3) = v15;
  *((_DWORD *)v19 + 8) = 0;
  *((_QWORD *)v19 + 5) = v12;
  *((_QWORD *)v19 + 6) = a1;
  *((_QWORD *)v19 + 7) = a2;
  *((_QWORD *)v19 + 9) = 0;
  ++*(_WORD *)(a1 + 200);
  _InterlockedAdd((volatile signed __int32 *)v19 + 4, 1u);
  ReferenceTunnel(a1, 0);
  v25 = *((_QWORD *)v19 + 7);
  if ( v25 )
    ReferenceVc(v25);
  v26 = *(_QWORD **)(a1 + 216);
  if ( *v26 != a1 + 208 )
    __fastfail(3u);
  *(_QWORD *)v19 = a1 + 208;
  *((_QWORD *)v19 + 1) = v26;
  *v26 = v19;
  *(_QWORD *)(a1 + 216) = v19;
  return ScheduleTunnelWork(a1, 0, (unsigned int)SendPending, 0, 0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x14000fd0c  mov     rax, rsp
0x14000fd0f  mov     [rax+10h], rbx
0x14000fd13  mov     [rax+20h], r9d
0x14000fd17  push    rbp
0x14000fd18  push    rsi
0x14000fd19  push    rdi
0x14000fd1a  push    r12
0x14000fd1c  push    r13
0x14000fd1e  push    r14
0x14000fd20  push    r15
0x14000fd22  sub     rsp, 50h
0x14000fd26  xor     edi, edi
0x14000fd28  movzx   r12d, r8w
0x14000fd2c  mov     [rax+8], edi
0x14000fd2f  mov     r13, rdx
0x14000fd32  mov     rbp, rcx
0x14000fd35  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd3c  lea     r15, WPP_GLOBAL_Control
0x14000fd43  cmp     rcx, r15
0x14000fd46  jz      short loc_14000FD6B
0x14000fd48  mov     eax, [rcx+2Ch]
0x14000fd4b  test    al, 10h
0x14000fd4d  jz      short loc_14000FD6B
0x14000fd4f  cmp     byte ptr [rcx+29h], 4
0x14000fd53  jb      short loc_14000FD6B
0x14000fd55  mov     rcx, [rcx+18h]
0x14000fd59  lea     edx, [rdi+0Ah]
0x14000fd5c  mov     r9d, r12d
0x14000fd5f  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14000fd66  call    WPP_SF_d
0x14000fd6b  movzx   eax, r12w
0x14000fd6f  mov     esi, 1
0x14000fd74  sub     ax, si
0x14000fd77  cmp     ax, 0Fh
0x14000fd7b  ja      loc_14001004C
0x14000fd81  mov     rbx, [rbp+18h]
0x14000fd85  xor     r8d, r8d; ContextBackFill
0x14000fd88  xor     edx, edx; ContextSize
0x14000fd8a  mov     rcx, [rbx+0D0h]; PoolHandle
0x14000fd91  call    cs:__imp_NdisAllocateNetBufferList
0x14000fd98  nop     dword ptr [rax+rax+00h]
0x14000fd9d  mov     r14, rax
0x14000fda0  test    rax, rax
0x14000fda3  jnz     short loc_14000FDD3
0x14000fda5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fdac  cmp     rcx, r15
0x14000fdaf  jz      loc_14001007B
0x14000fdb5  mov     eax, [rcx+2Ch]
0x14000fdb8  test    sil, al
0x14000fdbb  jz      loc_14001007B
0x14000fdc1  cmp     [rcx+29h], sil
0x14000fdc5  jb      loc_14001007B
0x14000fdcb  lea     edx, [rsi+0Bh]
0x14000fdce  jmp     loc_14001006B
0x14000fdd3  mov     rcx, [rax+8]; NetBuffer
0x14000fdd7  mov     edi, 612h
0x14000fddc  mov     edx, edi; DataOffsetDelta
0x14000fdde  xor     r9d, r9d; AllocateMdlHandler
0x14000fde1  xor     r8d, r8d; DataBackFill
0x14000fde4  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14000fdeb  nop     dword ptr [rax+rax+00h]
0x14000fdf0  mov     rcx, [r14+8]; NetBuffer
0x14000fdf4  mov     r9d, esi; AlignMultiple
0x14000fdf7  xor     r8d, r8d; Storage
0x14000fdfa  mov     [rsp+88h+AlignOffset], 0; AlignOffset
0x14000fe02  mov     edx, edi; BytesNeeded
0x14000fe04  call    cs:__imp_NdisGetDataBuffer
0x14000fe0b  nop     dword ptr [rax+rax+00h]
0x14000fe10  mov     r8d, edi; Size
0x14000fe13  xor     edx, edx; Val
0x14000fe15  mov     rcx, rax; void *
0x14000fe18  mov     [rsp+88h+arg_28], rax
0x14000fe20  call    memset
0x14000fe25  lea     rcx, [rbx+240h]; Lookaside
0x14000fe2c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000fe33  nop     dword ptr [rax+rax+00h]
0x14000fe38  xor     edi, edi
0x14000fe3a  mov     r15, rax
0x14000fe3d  test    rax, rax
0x14000fe40  jnz     short loc_14000FE68
0x14000fe42  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe49  lea     rax, WPP_GLOBAL_Control
0x14000fe50  cmp     rcx, rax
0x14000fe53  jz      short loc_14000FEB6
0x14000fe55  mov     edx, [rcx+2Ch]
0x14000fe58  test    dl, 2
0x14000fe5b  jz      short loc_14000FEB6
0x14000fe5d  cmp     [rcx+29h], sil
0x14000fe61  jb      short loc_14000FEB6
0x14000fe63  lea     edx, [rdi+0Dh]
0x14000fe66  jmp     short loc_14000FEA6
0x14000fe68  lea     rcx, [rbx+2C0h]; Lookaside
0x14000fe6f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000fe76  nop     dword ptr [rax+rax+00h]
0x14000fe7b  mov     rsi, rax
0x14000fe7e  test    rax, rax
0x14000fe81  jnz     short loc_14000FEE9
0x14000fe83  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe8a  lea     rax, WPP_GLOBAL_Control
0x14000fe91  cmp     rcx, rax
0x14000fe94  jz      short loc_14000FEB6
0x14000fe96  mov     eax, [rcx+2Ch]
0x14000fe99  test    al, 2
0x14000fe9b  jz      short loc_14000FEB6
0x14000fe9d  cmp     byte ptr [rcx+29h], 1
0x14000fea1  jb      short loc_14000FEB6
0x14000fea3  lea     edx, [rsi+0Eh]
0x14000fea6  mov     rcx, [rcx+18h]
0x14000feaa  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14000feb1  call    WPP_SF_
0x14000feb6  mov     rcx, r14; NetBufferList
0x14000feb9  call    cs:__imp_NdisFreeNetBufferList
0x14000fec0  nop     dword ptr [rax+rax+00h]
0x14000fec5  test    r15, r15
0x14000fec8  jz      loc_14001007B
0x14000fece  lea     rcx, [rbx+240h]; Lookaside
0x14000fed5  mov     rdx, r15; Entry
0x14000fed8  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000fedf  nop     dword ptr [rax+rax+00h]
0x14000fee4  jmp     loc_14001007B
0x14000fee9  test    r13, r13
0x14000feec  jz      short loc_14000FEF5
0x14000feee  movzx   eax, word ptr [r13+3Ah]
0x14000fef3  jmp     short loc_14000FEF7
0x14000fef5  mov     eax, edi
0x14000fef7  mov     rcx, [rsp+88h+arg_28]
0x14000feff  lea     rdi, [rbp+0C8h]
0x14000ff06  mov     [rsp+88h+arg_10], ax
0x14000ff0e  lea     r9, [rbp+74h]
0x14000ff12  movzx   eax, word ptr [rbp+118h]
0x14000ff19  xor     r8d, r8d
0x14000ff1c  mov     word ptr [rsp+88h+var_58], ax
0x14000ff21  mov     dl, 1
0x14000ff23  lea     rax, [rsp+88h+arg_10]
0x14000ff2b  mov     [rsp+88h+var_60], rdi
0x14000ff30  mov     qword ptr [rsp+88h+AlignOffset], rax
0x14000ff35  call    BuildL2tpHeader
0x14000ff3a  mov     r9d, [rsp+88h+arg_20]
0x14000ff42  lea     rcx, [rsp+88h+arg_0]
0x14000ff4a  mov     ebx, eax
0x14000ff4c  lea     rax, off_140007050
0x14000ff53  mov     rax, [rax+r12*8-8]
0x14000ff58  mov     edx, ebx
0x14000ff5a  add     rdx, [rsp+88h+arg_28]
0x14000ff62  mov     [rsp+88h+var_58], rcx
0x14000ff67  mov     rcx, rbp
0x14000ff6a  mov     [rsp+88h+var_60], rdx
0x14000ff6f  mov     rdx, r13
0x14000ff72  mov     qword ptr [rsp+88h+AlignOffset], r8
0x14000ff77  mov     r8d, [rsp+88h+arg_18]
0x14000ff7f  call    _guard_dispatch_icall
0x14000ff84  mov     ecx, [rsp+88h+arg_0]
0x14000ff8b  mov     rdx, [rsp+88h+arg_28]
0x14000ff93  add     ecx, ebx
0x14000ff95  xor     ebx, ebx
0x14000ff97  movzx   eax, cx
0x14000ff9a  ror     ax, 8
0x14000ff9e  mov     [rdx+2], ax
0x14000ffa2  mov     rax, [r14+8]
0x14000ffa6  mov     [rax+18h], ecx
0x14000ffa9  lea     ecx, [rbx+1]
0x14000ffac  mov     [rsi+10h], ebx
0x14000ffaf  movzx   eax, word ptr [rdi]
0x14000ffb2  mov     [rsi+14h], ax
0x14000ffb6  mov     eax, [rsp+88h+arg_30]
0x14000ffbd  mov     [rsi+16h], r12w
0x14000ffc2  or      eax, ecx
0x14000ffc4  mov     [r15+8], r15
0x14000ffc8  mov     [r15], r15
0x14000ffcb  mov     [rsi+24h], eax
0x14000ffce  mov     [rsi+18h], r15
0x14000ffd2  mov     [rsi+20h], ebx
0x14000ffd5  mov     [rsi+28h], r14
0x14000ffd9  mov     [rsi+30h], rbp
0x14000ffdd  mov     [rsi+38h], r13
0x14000ffe1  mov     [rsi+48h], rbx
0x14000ffe5  add     [rdi], cx
0x14000ffe8  lock add [rsi+10h], ecx
0x14000ffec  xor     edx, edx
0x14000ffee  mov     rcx, rbp
0x14000fff1  call    ReferenceTunnel
0x14000fff6  mov     rcx, [rsi+38h]
0x14000fffa  test    rcx, rcx
0x14000fffd  jz      short loc_140010004
0x14000ffff  call    ReferenceVc
0x140010004  lea     rax, [rbp+0D0h]
0x14001000b  mov     rcx, [rax+8]
0x14001000f  cmp     [rcx], rax
0x140010012  jz      short loc_14001001B
0x140010014  mov     ecx, 3
0x140010019  int     29h; Win8: RtlFailFast(ecx)
0x14001001b  mov     [rsp+88h+var_48], bl
0x14001001f  lea     r8, SendPending
0x140010026  mov     [rsp+88h+var_50], bl
0x14001002a  xor     r9d, r9d
0x14001002d  mov     [rsp+88h+var_58], rbx
0x140010032  mov     [rsi], rax
0x140010035  mov     [rsi+8], rcx
0x140010039  mov     [rsp+88h+var_60], rbx
0x14001003e  mov     [rcx], rsi
0x140010041  mov     qword ptr [rsp+88h+AlignOffset], rbx
0x140010046  mov     [rax+8], rsi
0x14001004a  jmp     short loc_1400100A5
0x14001004c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010053  cmp     rcx, r15
0x140010056  jz      short loc_14001007B
0x140010058  mov     eax, [rcx+2Ch]
0x14001005b  test    sil, al
0x14001005e  jz      short loc_14001007B
0x140010060  cmp     [rcx+29h], sil
0x140010064  jb      short loc_14001007B
0x140010066  mov     edx, 0Bh
0x14001006b  mov     rcx, [rcx+18h]
0x14001006f  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140010076  call    WPP_SF_
0x14001007b  mov     [rsp+88h+var_48], dil
0x140010080  lea     r8, FsmCloseTunnel
0x140010087  mov     [rsp+88h+var_50], dil
0x14001008c  mov     r9d, 2
0x140010092  mov     [rsp+88h+var_58], rdi
0x140010097  mov     [rsp+88h+var_60], rdi
0x14001009c  mov     qword ptr [rsp+88h+AlignOffset], 4
0x1400100a5  xor     edx, edx
0x1400100a7  mov     rcx, rbp
0x1400100aa  call    ScheduleTunnelWork
0x1400100af  mov     rbx, [rsp+88h+arg_8]
0x1400100b7  add     rsp, 50h
0x1400100bb  pop     r15
0x1400100bd  pop     r14
0x1400100bf  pop     r13
0x1400100c1  pop     r12
0x1400100c3  pop     rdi
0x1400100c4  pop     rsi
0x1400100c5  pop     rbp
0x1400100c6  retn
```
