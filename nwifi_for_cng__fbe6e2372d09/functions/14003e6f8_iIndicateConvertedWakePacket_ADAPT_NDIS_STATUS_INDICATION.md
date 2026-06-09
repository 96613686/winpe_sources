# iIndicateConvertedWakePacket(_ADAPT *,_NDIS_STATUS_INDICATION *)

- ea: `0x14003e6f8`
- end: `0x14003ea14`
- name: `?iIndicateConvertedWakePacket@@YAEPEAU_ADAPT@@PEAU_NDIS_STATUS_INDICATION@@@Z`
- size: `796`
- prototype: `unsigned __int8 __fastcall(struct _ADAPT *, struct _NDIS_STATUS_INDICATION *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14003deb0`

## callees

- `0x14000d21c`
- `0x1400168c8`
- `0x14003e450`
- `0x14003e544`
- `0x14003e6f8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003e80f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003e80f`
- `ntoskrnl!ExAllocatePool2` at `0x14003e827`
- `ntoskrnl!ExAllocatePool2` at `0x14003e827`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003e99e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003e99e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e9b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e9b2`

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
  unsigned int v10; // r13d
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // r14d
  unsigned int v14; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v17; // rbx
  char *v18; // rdi
  unsigned __int16 v19; // r9
  unsigned int v20; // r8d
  int v21; // eax
  unsigned int v22; // edx
  unsigned __int16 v25; // [rsp+90h] [rbp+18h] BYREF
  int v26; // [rsp+98h] [rbp+20h]

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
  v25 = 0;
  PacketHeaderSize = iGetPacketHeaderSize(v8, v6, &v25);
  v10 = PacketHeaderSize;
  if ( !PacketHeaderSize )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      v12 = 39;
LABEL_32:
      WPP_SF_(v11->AttachedDevice, v12, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids);
      return v3;
    }
    return v3;
  }
  v13 = PacketHeaderSize - 14;
  if ( (int)(PacketHeaderSize - 14) < 0 )
    return v3;
  v14 = a2->StatusBufferSize - v13 + 128;
  if ( v14 >= 0x10 )
  {
    v26 = *((_DWORD *)v5 + 37);
    if ( v14 > 0x40 )
    {
      if ( v14 > 0x100 )
      {
        if ( v14 > 0x400 )
        {
          if ( v14 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v14, 1785295735);
            goto LABEL_20;
          }
          p_WaitListHead = &stru_1400B31C0;
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
    v17 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = p_WaitListHead;
      Pool2[2] = 1785295735;
      v18 = (char *)(Pool2 + 32);
      v19 = v25;
      v20 = v26 - v10;
      *((_OWORD *)Pool2 + 1) = *(_OWORD *)&a2->Header.Type;
      *((_OWORD *)Pool2 + 2) = *(_OWORD *)&a2->PortNumber;
      *((_OWORD *)Pool2 + 3) = *(_OWORD *)&a2->DestinationHandle;
      *((_OWORD *)Pool2 + 4) = *(_OWORD *)&a2->StatusBuffer;
      *((_OWORD *)Pool2 + 5) = *(_OWORD *)&a2->Guid.Data2;
      *((_OWORD *)Pool2 + 6) = *(_OWORD *)a2->NdisReserved;
      *((_OWORD *)Pool2 + 7) = *(_OWORD *)&a2->NdisReserved[2];
      Pool2[18] = a2->StatusBufferSize - v13;
      *((_QWORD *)Pool2 + 8) = Pool2 + 32;
      *((_OWORD *)Pool2 + 8) = *(_OWORD *)StatusBuffer;
      Pool2[36] = StatusBuffer[4];
      v21 = StatusBuffer[4];
      *((_DWORD *)v18 + 3) = 20;
      *((_DWORD *)v18 + 4) = v21 - v13;
      *(_OWORD *)(v18 + 20) = *(_OWORD *)v5;
      *(_OWORD *)(v18 + 36) = *((_OWORD *)v5 + 1);
      *(_OWORD *)(v18 + 52) = *((_OWORD *)v5 + 2);
      *(_OWORD *)(v18 + 68) = *((_OWORD *)v5 + 3);
      *(_OWORD *)(v18 + 84) = *((_OWORD *)v5 + 4);
      *(_OWORD *)(v18 + 100) = *((_OWORD *)v5 + 5);
      *(_OWORD *)(v18 + 116) = *((_OWORD *)v5 + 6);
      *(_OWORD *)(v18 + 132) = *((_OWORD *)v5 + 7);
      *(_OWORD *)(v18 + 148) = *((_OWORD *)v5 + 8);
      *((_OWORD *)v18 + 10) = *(_OWORD *)(v5 + 140);
      v22 = *((_DWORD *)v5 + 37) - v13;
      *((_DWORD *)v18 + 43) = 156;
      *((_DWORD *)v18 + 42) = v22;
      *((_DWORD *)v18 + 41) = *((_DWORD *)v5 + 36) - v13;
      if ( iConvertToEthPacket(v7, v10, v20, v19, (unsigned __int8 *)v18 + 176, v22) < 0 )
      {
        v3 = 0;
      }
      else
      {
        Dot11ForwardStatusIndication(a1, 1073938517, v18, *((_DWORD *)v17 + 18));
        v3 = 1;
      }
      if ( *v17 )
        ExFreeToNPagedLookasideList(*v17, v17);
      else
        ExFreePoolWithTag(v17, *((_DWORD *)v17 + 2));
      return v3;
    }
    v3 = 0;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    v12 = 40;
    goto LABEL_32;
  }
  return v3;
}

```

## disassembly

```asm
0x14003e6f8  mov     r11, rsp
0x14003e6fb  mov     [r11+8], rcx
0x14003e6ff  push    rbx
0x14003e700  push    rbp
0x14003e701  push    rsi
0x14003e702  push    rdi
0x14003e703  push    r12
0x14003e705  push    r13
0x14003e707  push    r14
0x14003e709  push    r15
0x14003e70b  sub     rsp, 38h
0x14003e70f  mov     r15, [rdx+30h]
0x14003e713  xor     dil, dil
0x14003e716  mov     rbp, rdx
0x14003e719  mov     [rsp+78h+arg_8], dil
0x14003e721  mov     esi, [r15+0Ch]
0x14003e725  add     rsi, r15
0x14003e728  mov     edx, [rsi+94h]; unsigned int
0x14003e72e  cmp     edx, 18h
0x14003e731  jbe     loc_14003E9FF
0x14003e737  mov     r12d, [rsi+98h]
0x14003e73e  add     r12, rsi
0x14003e741  mov     al, [r12]
0x14003e745  and     al, 0Ch
0x14003e747  cmp     al, 8
0x14003e749  jnz     loc_14003E9FF
0x14003e74f  xor     eax, eax
0x14003e751  lea     r8, [r11+18h]; unsigned __int16 *
0x14003e755  mov     rcx, r12; struct DOT11_MGMT_HEADER *
0x14003e758  mov     [r11+18h], ax
0x14003e75d  call    ?iGetPacketHeaderSize@@YAKPEAUDOT11_MGMT_HEADER@@KPEAG@Z; iGetPacketHeaderSize(DOT11_MGMT_HEADER *,ulong,ushort *)
0x14003e762  mov     r13d, eax
0x14003e765  test    eax, eax
0x14003e767  jnz     short loc_14003E7A0
0x14003e769  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e770  lea     rax, WPP_GLOBAL_Control
0x14003e777  cmp     rcx, rax
0x14003e77a  jz      loc_14003E9FF
0x14003e780  cmp     byte ptr [rcx+29h], 2
0x14003e784  jb      loc_14003E9FF
0x14003e78a  test    dword ptr [rcx+2Ch], 200h
0x14003e791  jz      loc_14003E9FF
0x14003e797  lea     edx, [r13+27h]
0x14003e79b  jmp     loc_14003E9EF
0x14003e7a0  lea     r14d, [rax-0Eh]
0x14003e7a4  test    r14d, r14d
0x14003e7a7  js      loc_14003E9FF
0x14003e7ad  mov     eax, [rbp+38h]
0x14003e7b0  sub     eax, r14d
0x14003e7b3  sub     eax, 0FFFFFF80h
0x14003e7b6  cmp     eax, 10h
0x14003e7b9  jb      loc_14003E9C8
0x14003e7bf  mov     ecx, [rsi+94h]
0x14003e7c5  mov     [rsp+78h+arg_18], ecx
0x14003e7cc  mov     ecx, 40h ; '@'
0x14003e7d1  cmp     eax, ecx
0x14003e7d3  ja      short loc_14003E7DE
0x14003e7d5  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14003e7dc  jmp     short loc_14003E80C
0x14003e7de  cmp     eax, 100h
0x14003e7e3  ja      short loc_14003E7EE
0x14003e7e5  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003e7ec  jmp     short loc_14003E80C
0x14003e7ee  cmp     eax, 400h
0x14003e7f3  ja      short loc_14003E7FE
0x14003e7f5  lea     rdi, Lookaside
0x14003e7fc  jmp     short loc_14003E80C
0x14003e7fe  cmp     eax, 800h
0x14003e803  ja      short loc_14003E81D
0x14003e805  lea     rdi, stru_1400B31C0
0x14003e80c  mov     rcx, rdi; Lookaside
0x14003e80f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003e816  nop     dword ptr [rax+rax+00h]
0x14003e81b  jmp     short loc_14003E833
0x14003e81d  xor     edi, edi
0x14003e81f  mov     edx, eax
0x14003e821  mov     r8d, 6A697377h
0x14003e827  call    cs:__imp_ExAllocatePool2
0x14003e82e  nop     dword ptr [rax+rax+00h]
0x14003e833  mov     rbx, rax
0x14003e836  test    rax, rax
0x14003e839  jz      loc_14003E9C0
0x14003e83f  mov     [rax], rdi
0x14003e842  mov     rcx, r12; struct DOT11_MGMT_HEADER *
0x14003e845  mov     dword ptr [rax+8], 6A697377h
0x14003e84c  lea     rdi, [rax+80h]
0x14003e853  movups  xmm0, xmmword ptr [rbp+0]
0x14003e857  mov     r8d, [rsp+78h+arg_18]
0x14003e85f  movzx   r9d, [rsp+78h+arg_10]; unsigned __int16
0x14003e868  sub     r8d, r13d; unsigned int
0x14003e86b  movups  xmmword ptr [rax+10h], xmm0
0x14003e86f  movups  xmm1, xmmword ptr [rbp+10h]
0x14003e873  movups  xmmword ptr [rax+20h], xmm1
0x14003e877  movups  xmm0, xmmword ptr [rbp+20h]
0x14003e87b  movups  xmmword ptr [rax+30h], xmm0
0x14003e87f  movups  xmm1, xmmword ptr [rbp+30h]
0x14003e883  movups  xmmword ptr [rax+40h], xmm1
0x14003e887  movups  xmm0, xmmword ptr [rbp+40h]
0x14003e88b  movups  xmmword ptr [rax+50h], xmm0
0x14003e88f  movups  xmm1, xmmword ptr [rbp+50h]
0x14003e893  movups  xmmword ptr [rax+60h], xmm1
0x14003e897  movups  xmm0, xmmword ptr [rbp+60h]
0x14003e89b  movups  xmmword ptr [rax+70h], xmm0
0x14003e89f  mov     eax, [rbp+38h]
0x14003e8a2  sub     eax, r14d
0x14003e8a5  mov     [rbx+48h], eax
0x14003e8a8  mov     [rbx+40h], rdi
0x14003e8ac  movups  xmm0, xmmword ptr [r15]
0x14003e8b0  movups  xmmword ptr [rdi], xmm0
0x14003e8b3  mov     eax, [r15+10h]
0x14003e8b7  mov     [rdi+10h], eax
0x14003e8ba  mov     eax, [r15+10h]
0x14003e8be  mov     dword ptr [rdi+0Ch], 14h
0x14003e8c5  sub     eax, r14d
0x14003e8c8  mov     [rdi+10h], eax
0x14003e8cb  movups  xmm0, xmmword ptr [rsi]
0x14003e8ce  movups  xmmword ptr [rdi+14h], xmm0
0x14003e8d2  movups  xmm1, xmmword ptr [rsi+10h]
0x14003e8d6  movups  xmmword ptr [rdi+24h], xmm1
0x14003e8da  movups  xmm0, xmmword ptr [rsi+20h]
0x14003e8de  movups  xmmword ptr [rdi+34h], xmm0
0x14003e8e2  movups  xmm1, xmmword ptr [rsi+30h]
0x14003e8e6  movups  xmmword ptr [rdi+44h], xmm1
0x14003e8ea  movups  xmm0, xmmword ptr [rsi+40h]
0x14003e8ee  movups  xmmword ptr [rdi+54h], xmm0
0x14003e8f2  movups  xmm1, xmmword ptr [rsi+50h]
0x14003e8f6  movups  xmmword ptr [rdi+64h], xmm1
0x14003e8fa  movups  xmm0, xmmword ptr [rsi+60h]
0x14003e8fe  movups  xmmword ptr [rdi+74h], xmm0
0x14003e902  movups  xmm1, xmmword ptr [rsi+70h]
0x14003e906  movups  xmmword ptr [rdi+84h], xmm1
0x14003e90d  movups  xmm0, xmmword ptr [rsi+80h]
0x14003e914  movups  xmmword ptr [rdi+94h], xmm0
0x14003e91b  movups  xmm1, xmmword ptr [rsi+8Ch]
0x14003e922  movups  xmmword ptr [rdi+0A0h], xmm1
0x14003e929  mov     edx, [rsi+94h]
0x14003e92f  sub     edx, r14d
0x14003e932  mov     dword ptr [rdi+0ACh], 9Ch
0x14003e93c  mov     [rdi+0A8h], edx
0x14003e942  mov     eax, [rsi+90h]
0x14003e948  sub     eax, r14d
0x14003e94b  mov     [rsp+78h+var_50], edx; unsigned int
0x14003e94f  mov     [rdi+0A4h], eax
0x14003e955  mov     edx, r13d; unsigned int
0x14003e958  lea     rax, [rdi+0B0h]
0x14003e95f  mov     [rsp+78h+var_58], rax; unsigned __int8 *
0x14003e964  call    ?iConvertToEthPacket@@YAHPEAUDOT11_MGMT_HEADER@@KKGPEAEK@Z; iConvertToEthPacket(DOT11_MGMT_HEADER *,ulong,ulong,ushort,uchar *,ulong)
0x14003e969  test    eax, eax
0x14003e96b  js      short loc_14003E98B
0x14003e96d  mov     r9d, [rbx+48h]; unsigned int
0x14003e971  mov     r8, rdi; void *
0x14003e974  mov     rcx, [rsp+78h+arg_0]; struct _ADAPT *
0x14003e97c  mov     edx, 40030055h; int
0x14003e981  call    ?Dot11ForwardStatusIndication@@YAXPEAU_ADAPT@@HPEAXI@Z; Dot11ForwardStatusIndication(_ADAPT *,int,void *,uint)
0x14003e986  mov     dil, 1
0x14003e989  jmp     short loc_14003E993
0x14003e98b  mov     dil, [rsp+78h+arg_8]
0x14003e993  mov     rcx, [rbx]; Lookaside
0x14003e996  test    rcx, rcx
0x14003e999  jz      short loc_14003E9AC
0x14003e99b  mov     rdx, rbx; Entry
0x14003e99e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003e9a5  nop     dword ptr [rax+rax+00h]
0x14003e9aa  jmp     short loc_14003E9FF
0x14003e9ac  mov     edx, [rbx+8]; Tag
0x14003e9af  mov     rcx, rbx; P
0x14003e9b2  call    cs:__imp_ExFreePoolWithTag
0x14003e9b9  nop     dword ptr [rax+rax+00h]
0x14003e9be  jmp     short loc_14003E9FF
0x14003e9c0  mov     dil, [rsp+78h+arg_8]
0x14003e9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e9cf  lea     rax, WPP_GLOBAL_Control
0x14003e9d6  cmp     rcx, rax
0x14003e9d9  jz      short loc_14003E9FF
0x14003e9db  cmp     byte ptr [rcx+29h], 2
0x14003e9df  jb      short loc_14003E9FF
0x14003e9e1  test    dword ptr [rcx+2Ch], 200h
0x14003e9e8  jz      short loc_14003E9FF
0x14003e9ea  mov     edx, 28h ; '('
0x14003e9ef  mov     rcx, [rcx+18h]
0x14003e9f3  lea     r8, WPP_f7be174c5c0c3ddfd0519d9dc4150861_Traceguids
0x14003e9fa  call    WPP_SF_
0x14003e9ff  mov     al, dil
0x14003ea02  add     rsp, 38h
0x14003ea06  pop     r15
0x14003ea08  pop     r14
0x14003ea0a  pop     r13
0x14003ea0c  pop     r12
0x14003ea0e  pop     rdi
0x14003ea0f  pop     rsi
0x14003ea10  pop     rbp
0x14003ea11  pop     rbx
0x14003ea12  retn
```
