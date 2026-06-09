# ExtSTASendPacketsEx(EXTSTA_VELAN *,_NET_BUFFER_LIST * *,uint,DOT11_INTERMEDIATE_LOCAL_QUEUE *,SEND_QUEUE_TYPE)

- ea: `0x140011eb0`
- end: `0x14001244b`
- name: `?ExtSTASendPacketsEx@@YAXPEAUEXTSTA_VELAN@@PEAPEAU_NET_BUFFER_LIST@@IPEAUDOT11_INTERMEDIATE_LOCAL_QUEUE@@W4SEND_QUEUE_TYPE@@@Z`
- size: `1435`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140011d10`
- `0x140011e90`

## callees

- `0x14000d22c`
- `0x14000dfa8`
- `0x140011918`
- `0x140011eb0`
- `0x140012460`
- `0x140013b90`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400121d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012211`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400122dc`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012409`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400121d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012211`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400122dc`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012409`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011f61`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011f61`
- `NDIS!NdisReleaseRWLock` at `0x1400123c2`
- `NDIS!NdisReleaseRWLock` at `0x1400123c2`
- `NDIS!NdisAcquireRWLockRead` at `0x140011f0a`
- `NDIS!NdisAcquireRWLockRead` at `0x140011f0a`

## pseudocode

```c
void __fastcall ExtSTASendPacketsEx(__int64 a1, __int64 a2, unsigned int a3, int *a4, int a5)
{
  int *v5; // rsi
  unsigned int v6; // ebx
  __int64 v7; // r13
  __int64 v9; // r15
  struct _NET_BUFFER_LIST *v10; // r13
  _NET_BUFFER *FirstNetBuffer; // rax
  _MDL *CurrentMdl; // rcx
  __int64 CurrentMdlOffset; // rbx
  _BYTE *MappedSystemVa; // rax
  char *v15; // r11
  __int64 **v16; // r8
  __int64 *i; // rdx
  int v18; // ecx
  int v19; // ecx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  _WORD *v22; // r10
  __int64 v23; // rdx
  __int64 v24; // rbx
  unsigned int v25; // esi
  __int64 v26; // rax
  __int16 v27; // cx
  __int16 v28; // di
  __int64 v29; // rax
  unsigned __int16 v30; // r9
  __int64 v31; // r8
  bool v32; // zf
  KIRQL v33; // al
  unsigned int v34; // r8d
  bool v35; // zf
  struct _ADAPT *pAdapt; // rcx
  struct _VELAN *v37; // rbx
  PDEVICE_OBJECT v38; // rcx
  __int64 v39; // rdx
  KIRQL CurrentIrql; // al
  int v41; // edx
  KIRQL v42; // al
  struct DOT11_MAC_STATE_ENTRY *v43; // [rsp+30h] [rbp-10h] BYREF
  __int64 v44; // [rsp+38h] [rbp-8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+40h] BYREF
  __int64 v46; // [rsp+88h] [rbp+48h]
  unsigned int v47; // [rsp+90h] [rbp+50h]
  int *v48; // [rsp+98h] [rbp+58h]

  v48 = a4;
  v47 = a3;
  v46 = a2;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  v5 = a4;
  v6 = a3;
  v7 = a2;
  if ( (*(_DWORD *)a1 & 4) != 0 )
  {
    v9 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_28c57b3400c433998a951834ede6818b_Traceguids);
    }
  }
  else
  {
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(a1 + 2616) + 144LL), &LockState, 0);
    v9 = 0;
    if ( v6 )
    {
      do
      {
        v10 = *(struct _NET_BUFFER_LIST **)(v7 + 8 * v9);
        FirstNetBuffer = v10->FirstNetBuffer;
        CurrentMdl = FirstNetBuffer->CurrentMdl;
        CurrentMdlOffset = FirstNetBuffer->CurrentMdlOffset;
        if ( (CurrentMdl->MdlFlags & 5) != 0 )
          MappedSystemVa = CurrentMdl->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000020u);
        v15 = &MappedSystemVa[CurrentMdlOffset];
        if ( (MappedSystemVa[CurrentMdlOffset + 4] & 1) != 0 )
          goto LABEL_35;
        v16 = (__int64 **)(*(_QWORD *)(a1 + 2616)
                         + 16
                         * ((__int64)((unsigned __int8)v15[8] ^ (unsigned __int64)(unsigned __int8)v15[9]) % 256 + 10));
        for ( i = *v16; v16 != (__int64 **)i; i = (__int64 *)*i )
        {
          v18 = *((_DWORD *)i + 4) - *((_DWORD *)v15 + 1);
          if ( !v18 )
            v18 = *((unsigned __int16 *)i + 10) - *((unsigned __int16 *)v15 + 4);
          if ( !v18 )
            goto LABEL_14;
        }
        i = 0;
LABEL_14:
        v43 = (struct DOT11_MAC_STATE_ENTRY *)i;
        if ( !i )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_28c57b3400c433998a951834ede6818b_Traceguids);
          }
          goto LABEL_60;
        }
        _InterlockedIncrement((volatile signed __int32 *)i + 9);
        v19 = *((_DWORD *)i + 10);
        if ( (v19 & 0x12) != 2 )
        {
          Dot11ReleaseMacState(&v43);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_28c57b3400c433998a951834ede6818b_Traceguids);
          }
          goto LABEL_60;
        }
        if ( (v19 & 4) == 0 || *(_QWORD *)(*(_QWORD *)(a1 + 2616) + 5888LL) )
        {
          if ( (v19 & 0xC) == 4 )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
            {
              goto LABEL_23;
            }
            v21 = 14;
          }
          else
          {
            if ( (v19 & 0x20) == 0 )
            {
              *(_QWORD *)&v10->Context->ContextData[v10->Context->Offset + 8] = i;
LABEL_35:
              v22 = v10->NetBufferListInfo[6];
              *(_DWORD *)v22 = 2097536;
              v22[2] = 0;
              *((_DWORD *)v22 + 2) = -1;
              *((_DWORD *)v22 + 3) = 0;
              *((_QWORD *)v22 + 2) = *(_QWORD *)&v10->Context->ContextData[v10->Context->Offset + 24];
              v23 = *(_QWORD *)(*(_QWORD *)(a1 + 2616) + 5888LL);
              if ( v23 && (*(_WORD *)v15 & 0x4000) == 0 )
              {
                v24 = *(_QWORD *)(v23 + 24);
                v25 = *(_DWORD *)(v24 + 184);
                if ( v25 && !*(_DWORD *)(v24 + 168) )
                {
                  v26 = 36;
                  v27 = *(_WORD *)v15 & 0x300;
                  if ( v27 != 768 )
                    v26 = 30;
                  v28 = *(_WORD *)&v15[v26];
                  if ( v28 == 129 )
                  {
                    v29 = 40;
                    if ( v27 != 768 )
                      v29 = 34;
                    v28 = *(_WORD *)&v15[v29];
                  }
                  v30 = 0;
                  while ( v30 < v25 )
                  {
                    v31 = *(_QWORD *)(v24 + 192);
                    if ( v28 == *(_WORD *)(v31 + 6LL * v30) )
                    {
                      if ( *(_WORD *)(v31 + 6LL * v30 + 4) == 1 )
                      {
                        v32 = (v15[4] & 1) == 0;
                        goto LABEL_68;
                      }
                      if ( *(_WORD *)(v31 + 6LL * v30 + 4) == 2 )
                      {
                        if ( (v15[4] & 1) != 0 )
                          goto LABEL_63;
                      }
                      else
                      {
                        v32 = *(unsigned __int16 *)(v31 + 6LL * v30 + 4) == 3;
LABEL_68:
                        if ( v32 )
                        {
LABEL_63:
                          v22[2] = *(_WORD *)(v31 + 6LL * v30 + 2);
                          break;
                        }
                      }
                    }
                    ++v30;
                    continue;
                  }
                }
                v5 = v48;
              }
              if ( a5 == 1 )
              {
                Dot11QueueSendPacket(*(struct _VELAN **)(a1 + 2616), v10);
                goto LABEL_94;
              }
              if ( a5 )
                goto LABEL_94;
              v37 = *(struct _VELAN **)(a1 + 2616);
              v44 = 0;
              LODWORD(v43) = 0;
              if ( v37->lSendBlockCount )
              {
                v38 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  v39 = 11;
                  goto LABEL_76;
                }
              }
              else
              {
                if ( v5 )
                {
                  if ( *v5 + 1 >= (unsigned int)*v5 )
                  {
                    v41 = 0;
                    if ( !*v5 )
                      goto LABEL_90;
                    **((_QWORD **)v5 + 2) = v10;
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids);
                    }
                    v41 = *v5;
                    *v5 = 0;
LABEL_90:
                    *((_QWORD *)v5 + 1) = v10;
                  }
                  *((_QWORD *)v5 + 2) = v10;
                  ++*v5;
                  if ( v41 )
                    Dot11FlushIntermediateSendQueueWithoutLock(v37, (__int64)&v44);
                  goto LABEL_94;
                }
                v38 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer)
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  v39 = 12;
LABEL_76:
                  WPP_SF_(v38->AttachedDevice, v39, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids);
                }
              }
              CurrentIrql = KeGetCurrentIrql();
              pAdapt = v37->pAdapt;
              v34 = 0;
              v35 = CurrentIrql == 2;
              goto LABEL_61;
            }
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
            {
              goto LABEL_23;
            }
            v21 = 15;
          }
        }
        else
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
          {
            goto LABEL_23;
          }
          v21 = 13;
        }
        WPP_SF_(v20->AttachedDevice, v21, WPP_28c57b3400c433998a951834ede6818b_Traceguids);
LABEL_23:
        Dot11ReleaseMacState(&v43);
LABEL_60:
        v33 = KeGetCurrentIrql();
        v34 = 0;
        v35 = v33 == 2;
        pAdapt = *(struct _ADAPT **)(*(_QWORD *)(a1 + 2616) + 16LL);
LABEL_61:
        LOBYTE(v34) = v35;
        Pt6SendComplete(pAdapt, v10, v34);
LABEL_94:
        v6 = v47;
        v9 = (unsigned int)(v9 + 1);
        v7 = v46;
      }
      while ( (unsigned int)v9 < v47 );
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(a1 + 2616) + 144LL), &LockState);
  }
  while ( (unsigned int)v9 < v6 )
  {
    v42 = KeGetCurrentIrql();
    Pt6SendComplete(
      *(struct _ADAPT **)(*(_QWORD *)(a1 + 2616) + 16LL),
      *(struct _NET_BUFFER_LIST **)(v7 + 8 * v9),
      v42 == 2);
    v9 = (unsigned int)(v9 + 1);
  }
}

```

## disassembly

```asm
0x140011eb0  mov     [rsp-38h+arg_18], r9
0x140011eb5  mov     [rsp-38h+arg_10], r8d
0x140011eba  mov     [rsp-38h+arg_8], rdx
0x140011ebf  push    rbp
0x140011ec0  push    rbx
0x140011ec1  push    rsi
0x140011ec2  push    rdi
0x140011ec3  push    r13
0x140011ec5  push    r14
0x140011ec7  push    r15
0x140011ec9  mov     rbp, rsp
0x140011ecc  sub     rsp, 40h
0x140011ed0  xor     eax, eax
0x140011ed2  mov     [rbp+LockState.OldIrql], 0
0x140011ed6  mov     word ptr [rbp+LockState.LockState], ax
0x140011eda  mov     rsi, r9
0x140011edd  mov     eax, [rcx]
0x140011edf  mov     ebx, r8d
0x140011ee2  mov     r13, rdx
0x140011ee5  mov     r14, rcx
0x140011ee8  mov     edi, 1
0x140011eed  test    al, 4
0x140011eef  jnz     loc_1400123D0
0x140011ef5  mov     rcx, [rcx+0A38h]
0x140011efc  lea     rdx, [rbp+LockState]; LockState
0x140011f00  xor     r8d, r8d; Flags
0x140011f03  mov     rcx, [rcx+90h]; Lock
0x140011f0a  call    cs:__imp_NdisAcquireRWLockRead
0x140011f11  nop     dword ptr [rax+rax+00h]
0x140011f16  xor     r15d, r15d
0x140011f19  test    ebx, ebx
0x140011f1b  jz      loc_1400123B0
0x140011f21  lea     rdi, WPP_GLOBAL_Control
0x140011f28  lea     r9d, [r15+20h]
0x140011f2c  mov     r13, [r13+r15*8+0]
0x140011f31  mov     rax, [r13+8]
0x140011f35  mov     rcx, [rax+8]; MemoryDescriptorList
0x140011f39  mov     ebx, [rax+10h]
0x140011f3c  test    byte ptr [rcx+0Ah], 5
0x140011f40  jz      short loc_140011F48
0x140011f42  mov     rax, [rcx+18h]
0x140011f46  jmp     short loc_140011F73
0x140011f48  xor     r9d, r9d; RequestedAddress
0x140011f4b  mov     [rsp+40h+Priority], 40000020h; Priority
0x140011f53  xor     edx, edx; AccessMode
0x140011f55  mov     [rsp+40h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140011f5d  lea     r8d, [r9+1]; CacheType
0x140011f61  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140011f68  nop     dword ptr [rax+rax+00h]
0x140011f6d  mov     r9d, 20h ; ' '
0x140011f73  lea     r11, [rax+rbx]
0x140011f77  test    byte ptr [r11+4], 1
0x140011f7c  jnz     loc_1400120A1
0x140011f82  movzx   ecx, byte ptr [r11+8]
0x140011f87  movzx   eax, byte ptr [r11+9]
0x140011f8c  xor     eax, ecx
0x140011f8e  mov     ecx, 100h
0x140011f93  cdq
0x140011f94  idiv    ecx
0x140011f96  mov     r8d, edx
0x140011f99  add     r8, 0Ah
0x140011f9d  shl     r8, 4
0x140011fa1  add     r8, [r14+0A38h]
0x140011fa8  mov     rdx, [r8]
0x140011fab  cmp     r8, rdx
0x140011fae  jz      short loc_140011FCD
0x140011fb0  mov     ecx, [rdx+10h]
0x140011fb3  sub     ecx, [r11+4]
0x140011fb7  jnz     short loc_140011FC4
0x140011fb9  movzx   ecx, word ptr [rdx+14h]
0x140011fbd  movzx   eax, word ptr [r11+8]
0x140011fc2  sub     ecx, eax
0x140011fc4  test    ecx, ecx
0x140011fc6  jz      short loc_140011FCF
0x140011fc8  mov     rdx, [rdx]
0x140011fcb  jmp     short loc_140011FAB
0x140011fcd  xor     edx, edx
0x140011fcf  mov     [rbp+var_10], rdx
0x140011fd3  test    rdx, rdx
0x140011fd6  jz      loc_1400121E3
0x140011fdc  lock inc dword ptr [rdx+24h]
0x140011fe0  mov     ecx, [rdx+28h]
0x140011fe3  mov     bl, 2
0x140011fe5  mov     eax, ecx
0x140011fe7  and     al, 12h
0x140011fe9  cmp     al, bl
0x140011feb  jnz     loc_140012199
0x140011ff1  mov     r8b, 4
0x140011ff4  test    r8b, cl
0x140011ff7  jz      short loc_140012046
0x140011ff9  mov     rax, [r14+0A38h]
0x140012000  cmp     qword ptr [rax+1700h], 0
0x140012008  jnz     short loc_140012046
0x14001200a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012011  cmp     rcx, rdi
0x140012014  jz      short loc_140012038
0x140012016  cmp     [rcx+29h], r8b
0x14001201a  jb      short loc_140012038
0x14001201c  mov     eax, [rcx+2Ch]
0x14001201f  test    al, 40h
0x140012021  jz      short loc_140012038
0x140012023  mov     edx, 0Dh
0x140012028  mov     rcx, [rcx+18h]
0x14001202c  lea     r8, WPP_28c57b3400c433998a951834ede6818b_Traceguids
0x140012033  call    WPP_SF_
0x140012038  lea     rcx, [rbp+var_10]; struct DOT11_MAC_STATE_ENTRY **
0x14001203c  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x140012041  jmp     loc_1400121D0
0x140012046  mov     eax, ecx
0x140012048  and     al, 0Ch
0x14001204a  cmp     al, r8b
0x14001204d  jnz     short loc_14001206F
0x14001204f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012056  cmp     rcx, rdi
0x140012059  jz      short loc_140012038
0x14001205b  cmp     [rcx+29h], r8b
0x14001205f  jb      short loc_140012038
0x140012061  mov     eax, [rcx+2Ch]
0x140012064  test    al, 40h
0x140012066  jz      short loc_140012038
0x140012068  mov     edx, 0Eh
0x14001206d  jmp     short loc_140012028
0x14001206f  test    r9b, cl
0x140012072  jz      short loc_140012094
0x140012074  mov     rcx, cs:WPP_GLOBAL_Control
0x14001207b  cmp     rcx, rdi
0x14001207e  jz      short loc_140012038
0x140012080  cmp     [rcx+29h], r8b
0x140012084  jb      short loc_140012038
0x140012086  mov     eax, [rcx+2Ch]
0x140012089  test    al, 40h
0x14001208b  jz      short loc_140012038
0x14001208d  mov     edx, 0Fh
0x140012092  jmp     short loc_140012028
0x140012094  mov     rcx, [r13+10h]
0x140012098  movzx   eax, word ptr [rcx+0Ah]
0x14001209c  mov     [rax+rcx+18h], rdx
0x1400120a1  mov     r10, [r13+0C0h]
0x1400120a8  xor     eax, eax
0x1400120aa  mov     dword ptr [r10], 200180h
0x1400120b1  mov     [r10+4], ax
0x1400120b6  mov     dword ptr [r10+8], 0FFFFFFFFh
0x1400120be  mov     [r10+0Ch], eax
0x1400120c2  mov     rcx, [r13+10h]
0x1400120c6  movzx   eax, word ptr [rcx+0Ah]
0x1400120ca  mov     rcx, [rax+rcx+28h]
0x1400120cf  mov     [r10+10h], rcx
0x1400120d3  mov     rax, [r14+0A38h]
0x1400120da  mov     rdx, [rax+1700h]
0x1400120e1  test    rdx, rdx
0x1400120e4  jz      loc_14001225B
0x1400120ea  movzx   ecx, word ptr [r11]
0x1400120ee  bt      cx, 0Eh
0x1400120f3  jb      loc_14001225B
0x1400120f9  mov     rbx, [rdx+18h]
0x1400120fd  mov     esi, [rbx+0B8h]
0x140012103  test    esi, esi
0x140012105  jz      loc_140012257
0x14001210b  cmp     dword ptr [rbx+0A8h], 0
0x140012112  jnz     loc_140012257
0x140012118  mov     r8d, 300h
0x14001211e  mov     eax, 24h ; '$'
0x140012123  and     cx, r8w
0x140012127  cmp     cx, r8w
0x14001212b  lea     edx, [rax-6]
0x14001212e  cmovnz  eax, edx
0x140012131  movzx   edi, word ptr [rax+r11]
0x140012136  lea     eax, [rdx+63h]
0x140012139  cmp     ax, di
0x14001213c  jnz     short loc_140012150
0x14001213e  lea     eax, [rdx+0Ah]
0x140012141  cmp     cx, r8w
0x140012145  lea     edx, [rax-6]
0x140012148  cmovnz  eax, edx
0x14001214b  movzx   edi, word ptr [rax+r11]
0x140012150  xor     r9d, r9d
0x140012153  movzx   eax, r9w
0x140012157  cmp     eax, esi
0x140012159  jnb     loc_140012250
0x14001215f  mov     r8, [rbx+0C0h]
0x140012166  movzx   eax, r9w
0x14001216a  lea     rdx, [rax+rax*2]
0x14001216e  cmp     di, [r8+rdx*2]
0x140012173  jnz     loc_14001227C
0x140012179  movzx   ecx, word ptr [r8+rdx*2+4]
0x14001217f  sub     ecx, 1
0x140012182  jz      loc_140012275
0x140012188  sub     ecx, 1
0x14001218b  jz      loc_14001223E
0x140012191  cmp     ecx, 1
0x140012194  jmp     loc_14001227A
0x140012199  lea     rcx, [rbp+var_10]; struct DOT11_MAC_STATE_ENTRY **
0x14001219d  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x1400121a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121a9  cmp     rcx, rdi
0x1400121ac  jz      short loc_1400121D0
0x1400121ae  cmp     byte ptr [rcx+29h], 4
0x1400121b2  jb      short loc_1400121D0
0x1400121b4  mov     eax, [rcx+2Ch]
0x1400121b7  test    al, 40h
0x1400121b9  jz      short loc_1400121D0
0x1400121bb  mov     rcx, [rcx+18h]
0x1400121bf  lea     r8, WPP_28c57b3400c433998a951834ede6818b_Traceguids
0x1400121c6  mov     edx, 0Ch
0x1400121cb  call    WPP_SF_
0x1400121d0  call    cs:__imp_KeGetCurrentIrql
0x1400121d7  nop     dword ptr [rax+rax+00h]
0x1400121dc  xor     r8d, r8d
0x1400121df  cmp     al, bl
0x1400121e1  jmp     short loc_140012222
0x1400121e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121ea  cmp     rcx, rdi
0x1400121ed  jz      short loc_140012211
0x1400121ef  cmp     byte ptr [rcx+29h], 4
0x1400121f3  jb      short loc_140012211
0x1400121f5  mov     eax, [rcx+2Ch]
0x1400121f8  test    al, 40h
0x1400121fa  jz      short loc_140012211
0x1400121fc  mov     rcx, [rcx+18h]
0x140012200  lea     r8, WPP_28c57b3400c433998a951834ede6818b_Traceguids
0x140012207  mov     edx, 0Bh
0x14001220c  call    WPP_SF_
0x140012211  call    cs:__imp_KeGetCurrentIrql
0x140012218  nop     dword ptr [rax+rax+00h]
0x14001221d  xor     r8d, r8d
0x140012220  cmp     al, 2
0x140012222  mov     rcx, [r14+0A38h]
0x140012229  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14001222d  mov     rdx, r13; struct _NET_BUFFER_LIST *
0x140012230  setz    r8b; unsigned int
0x140012234  call    ?Pt6SendComplete@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@K@Z; Pt6SendComplete(_ADAPT *,_NET_BUFFER_LIST *,ulong)
0x140012239  jmp     loc_140012393
0x14001223e  test    byte ptr [r11+4], 1
0x140012243  jz      short loc_14001227C
0x140012245  movzx   eax, word ptr [r8+rdx*2+2]
0x14001224b  mov     [r10+4], ax
0x140012250  lea     rdi, WPP_GLOBAL_Control
0x140012257  mov     rsi, [rbp+arg_18]
0x14001225b  cmp     [rbp+arg_20], 1
0x14001225f  jnz     short loc_140012285
0x140012261  mov     rcx, [r14+0A38h]; struct _VELAN *
0x140012268  mov     rdx, r13; struct _NET_BUFFER_LIST *
0x14001226b  call    ?Dot11QueueSendPacket@@YAXPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@@Z; Dot11QueueSendPacket(_VELAN *,_NET_BUFFER_LIST *)
0x140012270  jmp     loc_140012393
0x140012275  test    byte ptr [r11+4], 1
0x14001227a  jz      short loc_140012245
0x14001227c  inc     r9w
0x140012280  jmp     loc_140012153
0x140012285  cmp     [rbp+arg_20], 0
0x140012289  jnz     loc_140012393
0x14001228f  mov     rbx, [r14+0A38h]
0x140012296  mov     [rbp+var_8], 0
0x14001229e  mov     dword ptr [rbp+var_10], 0
0x1400122a5  cmp     dword ptr [rbx+1308h], 0
0x1400122ac  jz      short loc_1400122F6
0x1400122ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122b5  cmp     rcx, rdi
0x1400122b8  jz      short loc_1400122DC
0x1400122ba  cmp     byte ptr [rcx+29h], 4
0x1400122be  jb      short loc_1400122DC
0x1400122c0  mov     eax, [rcx+2Ch]
0x1400122c3  test    al, 40h
0x1400122c5  jz      short loc_1400122DC
0x1400122c7  mov     edx, 0Bh
0x1400122cc  mov     rcx, [rcx+18h]
0x1400122d0  lea     r8, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids
0x1400122d7  call    WPP_SF_
0x1400122dc  call    cs:__imp_KeGetCurrentIrql
0x1400122e3  nop     dword ptr [rax+rax+00h]
0x1400122e8  mov     rcx, [rbx+10h]
0x1400122ec  xor     r8d, r8d
0x1400122ef  cmp     al, 2
0x1400122f1  jmp     loc_14001222D
0x1400122f6  test    rsi, rsi
0x1400122f9  jnz     short loc_140012319
0x1400122fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140012302  cmp     rcx, rdi
0x140012305  jz      short loc_1400122DC
0x140012307  cmp     byte ptr [rcx+29h], 1
0x14001230b  jb      short loc_1400122DC
0x14001230d  mov     eax, [rcx+2Ch]
0x140012310  test    al, 40h
0x140012312  jz      short loc_1400122DC
0x140012314  lea     edx, [rsi+0Ch]
0x140012317  jmp     short loc_1400122CC
0x140012319  mov     ecx, [rsi]
0x14001231b  lea     eax, [rcx+1]
0x14001231e  cmp     eax, ecx
0x140012320  jnb     short loc_14001235E
0x140012322  mov     rcx, cs:WPP_GLOBAL_Control
0x140012329  cmp     rcx, rdi
0x14001232c  jz      short loc_140012350
0x14001232e  cmp     byte ptr [rcx+29h], 2
0x140012332  jb      short loc_140012350
0x140012334  mov     eax, [rcx+2Ch]
0x140012337  test    al, 40h
0x140012339  jz      short loc_140012350
0x14001233b  mov     rcx, [rcx+18h]
0x14001233f  lea     r8, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids
0x140012346  mov     edx, 0Dh
  ... truncated ...
```
