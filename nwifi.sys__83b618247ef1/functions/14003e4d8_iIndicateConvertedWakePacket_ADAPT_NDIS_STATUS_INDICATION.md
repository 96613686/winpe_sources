# iIndicateConvertedWakePacket(_ADAPT *,_NDIS_STATUS_INDICATION *)

- ea: `0x14003e4d8`
- end: `0x14003e7f4`
- name: `?iIndicateConvertedWakePacket@@YAEPEAU_ADAPT@@PEAU_NDIS_STATUS_INDICATION@@@Z`
- size: `796`
- prototype: `unsigned __int8 __fastcall(struct _ADAPT *, struct _NDIS_STATUS_INDICATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14003dc90`

## callees

- `0x14000d22c`
- `0x1400168d8`
- `0x14003e230`
- `0x14003e324`
- `0x14003e4d8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003e5ef`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003e5ef`
- `ntoskrnl!ExAllocatePool2` at `0x14003e607`
- `ntoskrnl!ExAllocatePool2` at `0x14003e607`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003e77e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003e77e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e792`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e792`

## pseudocode

```c
char __fastcall iIndicateConvertedWakePacket(struct _ADAPT *a1, struct _NDIS_STATUS_INDICATION *a2)
{
  _DWORD *StatusBuffer; // r15
  char v3; // di
  char *v5; // rsi
  unsigned int v6; // edx
  struct DOT11_MGMT_HEADER *v7; // r12
  struct DOT11_MGMT_HEADER *v8; // rcx
  unsigned int PacketHeaderSize; // eax
  __int64 v10; // r9
  unsigned int v11; // r13d
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // r14d
  unsigned int v15; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v18; // rbx
  char *v19; // rdi
  unsigned __int16 v20; // r9
  unsigned int v21; // r8d
  int v22; // eax
  unsigned int v23; // edx
  unsigned __int16 v26; // [rsp+90h] [rbp+18h] BYREF
  int v27; // [rsp+98h] [rbp+20h]

  StatusBuffer = a2->StatusBuffer;
  v3 = 0;
  v5 = (char *)StatusBuffer + (unsigned int)StatusBuffer[3];
  v6 = *((_DWORD *)v5 + 37);
  if ( v6 <= 0x18 )
    return v3;
  v7 = (struct DOT11_MGMT_HEADER *)&v5[*((unsigned int *)v5 + 38)];
  if ( (*(_BYTE *)v7 & 0xC) != 8 )
    return v3;
  v8 = (struct DOT11_MGMT_HEADER *)&v5[*((unsigned int *)v5 + 38)];
  v26 = 0;
  PacketHeaderSize = iGetPacketHeaderSize(v8, v6, &v26);
  v11 = PacketHeaderSize;
  if ( !PacketHeaderSize )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      v13 = 39;
LABEL_32:
      WPP_SF_(v12->AttachedDevice, v13, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids);
      return v3;
    }
    return v3;
  }
  v14 = PacketHeaderSize - 14;
  if ( (int)(PacketHeaderSize - 14) < 0 )
    return v3;
  v15 = a2->StatusBufferSize - v14 + 128;
  if ( v15 >= 0x10 )
  {
    v27 = *((_DWORD *)v5 + 37);
    if ( v15 > 0x40 )
    {
      if ( v15 > 0x100 )
      {
        if ( v15 > 0x400 )
        {
          if ( v15 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v15, 1785295735, v10);
            goto LABEL_20;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_20:
    v18 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = p_WaitListHead;
      Pool2[2] = 1785295735;
      v19 = (char *)(Pool2 + 32);
      v20 = v26;
      v21 = v27 - v11;
      *((_OWORD *)Pool2 + 1) = *(_OWORD *)&a2->Header.Type;
      *((_OWORD *)Pool2 + 2) = *(_OWORD *)&a2->PortNumber;
      *((_OWORD *)Pool2 + 3) = *(_OWORD *)&a2->DestinationHandle;
      *((_OWORD *)Pool2 + 4) = *(_OWORD *)&a2->StatusBuffer;
      *((_OWORD *)Pool2 + 5) = *(_OWORD *)&a2->Guid.Data2;
      *((_OWORD *)Pool2 + 6) = *(_OWORD *)a2->NdisReserved;
      *((_OWORD *)Pool2 + 7) = *(_OWORD *)&a2->NdisReserved[2];
      Pool2[18] = a2->StatusBufferSize - v14;
      *((_QWORD *)Pool2 + 8) = Pool2 + 32;
      *((_OWORD *)Pool2 + 8) = *(_OWORD *)StatusBuffer;
      Pool2[36] = StatusBuffer[4];
      v22 = StatusBuffer[4];
      *((_DWORD *)v19 + 3) = 20;
      *((_DWORD *)v19 + 4) = v22 - v14;
      *(_OWORD *)(v19 + 20) = *(_OWORD *)v5;
      *(_OWORD *)(v19 + 36) = *((_OWORD *)v5 + 1);
      *(_OWORD *)(v19 + 52) = *((_OWORD *)v5 + 2);
      *(_OWORD *)(v19 + 68) = *((_OWORD *)v5 + 3);
      *(_OWORD *)(v19 + 84) = *((_OWORD *)v5 + 4);
      *(_OWORD *)(v19 + 100) = *((_OWORD *)v5 + 5);
      *(_OWORD *)(v19 + 116) = *((_OWORD *)v5 + 6);
      *(_OWORD *)(v19 + 132) = *((_OWORD *)v5 + 7);
      *(_OWORD *)(v19 + 148) = *((_OWORD *)v5 + 8);
      *((_OWORD *)v19 + 10) = *(_OWORD *)(v5 + 140);
      v23 = *((_DWORD *)v5 + 37) - v14;
      *((_DWORD *)v19 + 43) = 156;
      *((_DWORD *)v19 + 42) = v23;
      *((_DWORD *)v19 + 41) = *((_DWORD *)v5 + 36) - v14;
      if ( iConvertToEthPacket(v7, v11, v21, v20, (unsigned __int8 *)v19 + 176, v23) < 0 )
      {
        v3 = 0;
      }
      else
      {
        Dot11ForwardStatusIndication(a1, 1073938517, v19, *((_DWORD *)v18 + 18));
        v3 = 1;
      }
      if ( *v18 )
        ExFreeToNPagedLookasideList(*v18, v18);
      else
        ExFreePoolWithTag(v18, *((_DWORD *)v18 + 2));
      return v3;
    }
    v3 = 0;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    v13 = 40;
    goto LABEL_32;
  }
  return v3;
}

```

## disassembly

```asm
0x14003e4d8  mov     r11, rsp
0x14003e4db  mov     [r11+8], rcx
0x14003e4df  push    rbx
0x14003e4e0  push    rbp
0x14003e4e1  push    rsi
0x14003e4e2  push    rdi
0x14003e4e3  push    r12
0x14003e4e5  push    r13
0x14003e4e7  push    r14
0x14003e4e9  push    r15
0x14003e4eb  sub     rsp, 38h
0x14003e4ef  mov     r15, [rdx+30h]
0x14003e4f3  xor     dil, dil
0x14003e4f6  mov     rbp, rdx
0x14003e4f9  mov     [rsp+78h+arg_8], dil
0x14003e501  mov     esi, [r15+0Ch]
0x14003e505  add     rsi, r15
0x14003e508  mov     edx, [rsi+94h]; unsigned int
0x14003e50e  cmp     edx, 18h
0x14003e511  jbe     loc_14003E7DF
0x14003e517  mov     r12d, [rsi+98h]
0x14003e51e  add     r12, rsi
0x14003e521  mov     al, [r12]
0x14003e525  and     al, 0Ch
0x14003e527  cmp     al, 8
0x14003e529  jnz     loc_14003E7DF
0x14003e52f  xor     eax, eax
0x14003e531  lea     r8, [r11+18h]; unsigned __int16 *
0x14003e535  mov     rcx, r12; struct DOT11_MGMT_HEADER *
0x14003e538  mov     [r11+18h], ax
0x14003e53d  call    ?iGetPacketHeaderSize@@YAKPEAUDOT11_MGMT_HEADER@@KPEAG@Z; iGetPacketHeaderSize(DOT11_MGMT_HEADER *,ulong,ushort *)
0x14003e542  mov     r13d, eax
0x14003e545  test    eax, eax
0x14003e547  jnz     short loc_14003E580
0x14003e549  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e550  lea     rax, WPP_GLOBAL_Control
0x14003e557  cmp     rcx, rax
0x14003e55a  jz      loc_14003E7DF
0x14003e560  cmp     byte ptr [rcx+29h], 2
0x14003e564  jb      loc_14003E7DF
0x14003e56a  test    dword ptr [rcx+2Ch], 200h
0x14003e571  jz      loc_14003E7DF
0x14003e577  lea     edx, [r13+27h]
0x14003e57b  jmp     loc_14003E7CF
0x14003e580  lea     r14d, [rax-0Eh]
0x14003e584  test    r14d, r14d
0x14003e587  js      loc_14003E7DF
0x14003e58d  mov     eax, [rbp+38h]
0x14003e590  sub     eax, r14d
0x14003e593  sub     eax, 0FFFFFF80h
0x14003e596  cmp     eax, 10h
0x14003e599  jb      loc_14003E7A8
0x14003e59f  mov     ecx, [rsi+94h]
0x14003e5a5  mov     [rsp+78h+arg_18], ecx
0x14003e5ac  mov     ecx, 40h ; '@'
0x14003e5b1  cmp     eax, ecx
0x14003e5b3  ja      short loc_14003E5BE
0x14003e5b5  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14003e5bc  jmp     short loc_14003E5EC
0x14003e5be  cmp     eax, 100h
0x14003e5c3  ja      short loc_14003E5CE
0x14003e5c5  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003e5cc  jmp     short loc_14003E5EC
0x14003e5ce  cmp     eax, 400h
0x14003e5d3  ja      short loc_14003E5DE
0x14003e5d5  lea     rdi, Lookaside
0x14003e5dc  jmp     short loc_14003E5EC
0x14003e5de  cmp     eax, 800h
0x14003e5e3  ja      short loc_14003E5FD
0x14003e5e5  lea     rdi, stru_1400B0180
0x14003e5ec  mov     rcx, rdi; Lookaside
0x14003e5ef  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003e5f6  nop     dword ptr [rax+rax+00h]
0x14003e5fb  jmp     short loc_14003E613
0x14003e5fd  xor     edi, edi
0x14003e5ff  mov     edx, eax
0x14003e601  mov     r8d, 6A697377h
0x14003e607  call    cs:__imp_ExAllocatePool2
0x14003e60e  nop     dword ptr [rax+rax+00h]
0x14003e613  mov     rbx, rax
0x14003e616  test    rax, rax
0x14003e619  jz      loc_14003E7A0
0x14003e61f  mov     [rax], rdi
0x14003e622  mov     rcx, r12; struct DOT11_MGMT_HEADER *
0x14003e625  mov     dword ptr [rax+8], 6A697377h
0x14003e62c  lea     rdi, [rax+80h]
0x14003e633  movups  xmm0, xmmword ptr [rbp+0]
0x14003e637  mov     r8d, [rsp+78h+arg_18]
0x14003e63f  movzx   r9d, [rsp+78h+arg_10]; unsigned __int16
0x14003e648  sub     r8d, r13d; unsigned int
0x14003e64b  movups  xmmword ptr [rax+10h], xmm0
0x14003e64f  movups  xmm1, xmmword ptr [rbp+10h]
0x14003e653  movups  xmmword ptr [rax+20h], xmm1
0x14003e657  movups  xmm0, xmmword ptr [rbp+20h]
0x14003e65b  movups  xmmword ptr [rax+30h], xmm0
0x14003e65f  movups  xmm1, xmmword ptr [rbp+30h]
0x14003e663  movups  xmmword ptr [rax+40h], xmm1
0x14003e667  movups  xmm0, xmmword ptr [rbp+40h]
0x14003e66b  movups  xmmword ptr [rax+50h], xmm0
0x14003e66f  movups  xmm1, xmmword ptr [rbp+50h]
0x14003e673  movups  xmmword ptr [rax+60h], xmm1
0x14003e677  movups  xmm0, xmmword ptr [rbp+60h]
0x14003e67b  movups  xmmword ptr [rax+70h], xmm0
0x14003e67f  mov     eax, [rbp+38h]
0x14003e682  sub     eax, r14d
0x14003e685  mov     [rbx+48h], eax
0x14003e688  mov     [rbx+40h], rdi
0x14003e68c  movups  xmm0, xmmword ptr [r15]
0x14003e690  movups  xmmword ptr [rdi], xmm0
0x14003e693  mov     eax, [r15+10h]
0x14003e697  mov     [rdi+10h], eax
0x14003e69a  mov     eax, [r15+10h]
0x14003e69e  mov     dword ptr [rdi+0Ch], 14h
0x14003e6a5  sub     eax, r14d
0x14003e6a8  mov     [rdi+10h], eax
0x14003e6ab  movups  xmm0, xmmword ptr [rsi]
0x14003e6ae  movups  xmmword ptr [rdi+14h], xmm0
0x14003e6b2  movups  xmm1, xmmword ptr [rsi+10h]
0x14003e6b6  movups  xmmword ptr [rdi+24h], xmm1
0x14003e6ba  movups  xmm0, xmmword ptr [rsi+20h]
0x14003e6be  movups  xmmword ptr [rdi+34h], xmm0
0x14003e6c2  movups  xmm1, xmmword ptr [rsi+30h]
0x14003e6c6  movups  xmmword ptr [rdi+44h], xmm1
0x14003e6ca  movups  xmm0, xmmword ptr [rsi+40h]
0x14003e6ce  movups  xmmword ptr [rdi+54h], xmm0
0x14003e6d2  movups  xmm1, xmmword ptr [rsi+50h]
0x14003e6d6  movups  xmmword ptr [rdi+64h], xmm1
0x14003e6da  movups  xmm0, xmmword ptr [rsi+60h]
0x14003e6de  movups  xmmword ptr [rdi+74h], xmm0
0x14003e6e2  movups  xmm1, xmmword ptr [rsi+70h]
0x14003e6e6  movups  xmmword ptr [rdi+84h], xmm1
0x14003e6ed  movups  xmm0, xmmword ptr [rsi+80h]
0x14003e6f4  movups  xmmword ptr [rdi+94h], xmm0
0x14003e6fb  movups  xmm1, xmmword ptr [rsi+8Ch]
0x14003e702  movups  xmmword ptr [rdi+0A0h], xmm1
0x14003e709  mov     edx, [rsi+94h]
0x14003e70f  sub     edx, r14d
0x14003e712  mov     dword ptr [rdi+0ACh], 9Ch
0x14003e71c  mov     [rdi+0A8h], edx
0x14003e722  mov     eax, [rsi+90h]
0x14003e728  sub     eax, r14d
0x14003e72b  mov     [rsp+78h+var_50], edx; unsigned int
0x14003e72f  mov     [rdi+0A4h], eax
0x14003e735  mov     edx, r13d; unsigned int
0x14003e738  lea     rax, [rdi+0B0h]
0x14003e73f  mov     [rsp+78h+var_58], rax; unsigned __int8 *
0x14003e744  call    ?iConvertToEthPacket@@YAHPEAUDOT11_MGMT_HEADER@@KKGPEAEK@Z; iConvertToEthPacket(DOT11_MGMT_HEADER *,ulong,ulong,ushort,uchar *,ulong)
0x14003e749  test    eax, eax
0x14003e74b  js      short loc_14003E76B
0x14003e74d  mov     r9d, [rbx+48h]; unsigned int
0x14003e751  mov     r8, rdi; void *
0x14003e754  mov     rcx, [rsp+78h+arg_0]; struct _ADAPT *
0x14003e75c  mov     edx, 40030055h; int
0x14003e761  call    ?Dot11ForwardStatusIndication@@YAXPEAU_ADAPT@@HPEAXI@Z; Dot11ForwardStatusIndication(_ADAPT *,int,void *,uint)
0x14003e766  mov     dil, 1
0x14003e769  jmp     short loc_14003E773
0x14003e76b  mov     dil, [rsp+78h+arg_8]
0x14003e773  mov     rcx, [rbx]; Lookaside
0x14003e776  test    rcx, rcx
0x14003e779  jz      short loc_14003E78C
0x14003e77b  mov     rdx, rbx; Entry
0x14003e77e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003e785  nop     dword ptr [rax+rax+00h]
0x14003e78a  jmp     short loc_14003E7DF
0x14003e78c  mov     edx, [rbx+8]; Tag
0x14003e78f  mov     rcx, rbx; P
0x14003e792  call    cs:__imp_ExFreePoolWithTag
0x14003e799  nop     dword ptr [rax+rax+00h]
0x14003e79e  jmp     short loc_14003E7DF
0x14003e7a0  mov     dil, [rsp+78h+arg_8]
0x14003e7a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e7af  lea     rax, WPP_GLOBAL_Control
0x14003e7b6  cmp     rcx, rax
0x14003e7b9  jz      short loc_14003E7DF
0x14003e7bb  cmp     byte ptr [rcx+29h], 2
0x14003e7bf  jb      short loc_14003E7DF
0x14003e7c1  test    dword ptr [rcx+2Ch], 200h
0x14003e7c8  jz      short loc_14003E7DF
0x14003e7ca  mov     edx, 28h ; '('
0x14003e7cf  mov     rcx, [rcx+18h]
0x14003e7d3  lea     r8, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids
0x14003e7da  call    WPP_SF_
0x14003e7df  mov     al, dil
0x14003e7e2  add     rsp, 38h
0x14003e7e6  pop     r15
0x14003e7e8  pop     r14
0x14003e7ea  pop     r13
0x14003e7ec  pop     r12
0x14003e7ee  pop     rdi
0x14003e7ef  pop     rsi
0x14003e7f0  pop     rbp
0x14003e7f1  pop     rbx
0x14003e7f2  retn
```
