# ExtSTASendPacketsEx(EXTSTA_VELAN *,_NET_BUFFER_LIST * *,uint,DOT11_INTERMEDIATE_LOCAL_QUEUE *,SEND_QUEUE_TYPE)

- ea: `0x140011ea0`
- end: `0x14001243b`
- name: `?ExtSTASendPacketsEx@@YAXPEAUEXTSTA_VELAN@@PEAPEAU_NET_BUFFER_LIST@@IPEAUDOT11_INTERMEDIATE_LOCAL_QUEUE@@W4SEND_QUEUE_TYPE@@@Z`
- size: `1435`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140011d00`
- `0x140011e80`

## callees

- `0x14000d21c`
- `0x14000df98`
- `0x140011908`
- `0x140011ea0`
- `0x140012450`
- `0x140013b80`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400121c0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012201`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400122cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400123f9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400121c0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012201`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400122cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400123f9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011f51`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011f51`
- `NDIS!NdisReleaseRWLock` at `0x1400123b2`
- `NDIS!NdisReleaseRWLock` at `0x1400123b2`
- `NDIS!NdisAcquireRWLockRead` at `0x140011efa`
- `NDIS!NdisAcquireRWLockRead` at `0x140011efa`

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
0x140011ea0  mov     [rsp-38h+arg_18], r9
0x140011ea5  mov     [rsp-38h+arg_10], r8d
0x140011eaa  mov     [rsp-38h+arg_8], rdx
0x140011eaf  push    rbp
0x140011eb0  push    rbx
0x140011eb1  push    rsi
0x140011eb2  push    rdi
0x140011eb3  push    r13
0x140011eb5  push    r14
0x140011eb7  push    r15
0x140011eb9  mov     rbp, rsp
0x140011ebc  sub     rsp, 40h
0x140011ec0  xor     eax, eax
0x140011ec2  mov     [rbp+LockState.OldIrql], 0
0x140011ec6  mov     word ptr [rbp+LockState.LockState], ax
0x140011eca  mov     rsi, r9
0x140011ecd  mov     eax, [rcx]
0x140011ecf  mov     ebx, r8d
0x140011ed2  mov     r13, rdx
0x140011ed5  mov     r14, rcx
0x140011ed8  mov     edi, 1
0x140011edd  test    al, 4
0x140011edf  jnz     loc_1400123C0
0x140011ee5  mov     rcx, [rcx+0A38h]
0x140011eec  lea     rdx, [rbp+LockState]; LockState
0x140011ef0  xor     r8d, r8d; Flags
0x140011ef3  mov     rcx, [rcx+90h]; Lock
0x140011efa  call    cs:__imp_NdisAcquireRWLockRead
0x140011f01  nop     dword ptr [rax+rax+00h]
0x140011f06  xor     r15d, r15d
0x140011f09  test    ebx, ebx
0x140011f0b  jz      loc_1400123A0
0x140011f11  lea     rdi, WPP_GLOBAL_Control
0x140011f18  lea     r9d, [r15+20h]
0x140011f1c  mov     r13, [r13+r15*8+0]
0x140011f21  mov     rax, [r13+8]
0x140011f25  mov     rcx, [rax+8]; MemoryDescriptorList
0x140011f29  mov     ebx, [rax+10h]
0x140011f2c  test    byte ptr [rcx+0Ah], 5
0x140011f30  jz      short loc_140011F38
0x140011f32  mov     rax, [rcx+18h]
0x140011f36  jmp     short loc_140011F63
0x140011f38  xor     r9d, r9d; RequestedAddress
0x140011f3b  mov     [rsp+40h+Priority], 40000020h; Priority
0x140011f43  xor     edx, edx; AccessMode
0x140011f45  mov     [rsp+40h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140011f4d  lea     r8d, [r9+1]; CacheType
0x140011f51  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140011f58  nop     dword ptr [rax+rax+00h]
0x140011f5d  mov     r9d, 20h ; ' '
0x140011f63  lea     r11, [rax+rbx]
0x140011f67  test    byte ptr [r11+4], 1
0x140011f6c  jnz     loc_140012091
0x140011f72  movzx   ecx, byte ptr [r11+8]
0x140011f77  movzx   eax, byte ptr [r11+9]
0x140011f7c  xor     eax, ecx
0x140011f7e  mov     ecx, 100h
0x140011f83  cdq
0x140011f84  idiv    ecx
0x140011f86  mov     r8d, edx
0x140011f89  add     r8, 0Ah
0x140011f8d  shl     r8, 4
0x140011f91  add     r8, [r14+0A38h]
0x140011f98  mov     rdx, [r8]
0x140011f9b  cmp     r8, rdx
0x140011f9e  jz      short loc_140011FBD
0x140011fa0  mov     ecx, [rdx+10h]
0x140011fa3  sub     ecx, [r11+4]
0x140011fa7  jnz     short loc_140011FB4
0x140011fa9  movzx   ecx, word ptr [rdx+14h]
0x140011fad  movzx   eax, word ptr [r11+8]
0x140011fb2  sub     ecx, eax
0x140011fb4  test    ecx, ecx
0x140011fb6  jz      short loc_140011FBF
0x140011fb8  mov     rdx, [rdx]
0x140011fbb  jmp     short loc_140011F9B
0x140011fbd  xor     edx, edx
0x140011fbf  mov     [rbp+var_10], rdx
0x140011fc3  test    rdx, rdx
0x140011fc6  jz      loc_1400121D3
0x140011fcc  lock inc dword ptr [rdx+24h]
0x140011fd0  mov     ecx, [rdx+28h]
0x140011fd3  mov     bl, 2
0x140011fd5  mov     eax, ecx
0x140011fd7  and     al, 12h
0x140011fd9  cmp     al, bl
0x140011fdb  jnz     loc_140012189
0x140011fe1  mov     r8b, 4
0x140011fe4  test    r8b, cl
0x140011fe7  jz      short loc_140012036
0x140011fe9  mov     rax, [r14+0A38h]
0x140011ff0  cmp     qword ptr [rax+1700h], 0
0x140011ff8  jnz     short loc_140012036
0x140011ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x140012001  cmp     rcx, rdi
0x140012004  jz      short loc_140012028
0x140012006  cmp     [rcx+29h], r8b
0x14001200a  jb      short loc_140012028
0x14001200c  mov     eax, [rcx+2Ch]
0x14001200f  test    al, 40h
0x140012011  jz      short loc_140012028
0x140012013  mov     edx, 0Dh
0x140012018  mov     rcx, [rcx+18h]
0x14001201c  lea     r8, WPP_28c57b3400c433998a951834ede6818b_Traceguids
0x140012023  call    WPP_SF_
0x140012028  lea     rcx, [rbp+var_10]; struct DOT11_MAC_STATE_ENTRY **
0x14001202c  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x140012031  jmp     loc_1400121C0
0x140012036  mov     eax, ecx
0x140012038  and     al, 0Ch
0x14001203a  cmp     al, r8b
0x14001203d  jnz     short loc_14001205F
0x14001203f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012046  cmp     rcx, rdi
0x140012049  jz      short loc_140012028
0x14001204b  cmp     [rcx+29h], r8b
0x14001204f  jb      short loc_140012028
0x140012051  mov     eax, [rcx+2Ch]
0x140012054  test    al, 40h
0x140012056  jz      short loc_140012028
0x140012058  mov     edx, 0Eh
0x14001205d  jmp     short loc_140012018
0x14001205f  test    r9b, cl
0x140012062  jz      short loc_140012084
0x140012064  mov     rcx, cs:WPP_GLOBAL_Control
0x14001206b  cmp     rcx, rdi
0x14001206e  jz      short loc_140012028
0x140012070  cmp     [rcx+29h], r8b
0x140012074  jb      short loc_140012028
0x140012076  mov     eax, [rcx+2Ch]
0x140012079  test    al, 40h
0x14001207b  jz      short loc_140012028
0x14001207d  mov     edx, 0Fh
0x140012082  jmp     short loc_140012018
0x140012084  mov     rcx, [r13+10h]
0x140012088  movzx   eax, word ptr [rcx+0Ah]
0x14001208c  mov     [rax+rcx+18h], rdx
0x140012091  mov     r10, [r13+0C0h]
0x140012098  xor     eax, eax
0x14001209a  mov     dword ptr [r10], 200180h
0x1400120a1  mov     [r10+4], ax
0x1400120a6  mov     dword ptr [r10+8], 0FFFFFFFFh
0x1400120ae  mov     [r10+0Ch], eax
0x1400120b2  mov     rcx, [r13+10h]
0x1400120b6  movzx   eax, word ptr [rcx+0Ah]
0x1400120ba  mov     rcx, [rax+rcx+28h]
0x1400120bf  mov     [r10+10h], rcx
0x1400120c3  mov     rax, [r14+0A38h]
0x1400120ca  mov     rdx, [rax+1700h]
0x1400120d1  test    rdx, rdx
0x1400120d4  jz      loc_14001224B
0x1400120da  movzx   ecx, word ptr [r11]
0x1400120de  bt      cx, 0Eh
0x1400120e3  jb      loc_14001224B
0x1400120e9  mov     rbx, [rdx+18h]
0x1400120ed  mov     esi, [rbx+0B8h]
0x1400120f3  test    esi, esi
0x1400120f5  jz      loc_140012247
0x1400120fb  cmp     dword ptr [rbx+0A8h], 0
0x140012102  jnz     loc_140012247
0x140012108  mov     r8d, 300h
0x14001210e  mov     eax, 24h ; '$'
0x140012113  and     cx, r8w
0x140012117  cmp     cx, r8w
0x14001211b  lea     edx, [rax-6]
0x14001211e  cmovnz  eax, edx
0x140012121  movzx   edi, word ptr [rax+r11]
0x140012126  lea     eax, [rdx+63h]
0x140012129  cmp     ax, di
0x14001212c  jnz     short loc_140012140
0x14001212e  lea     eax, [rdx+0Ah]
0x140012131  cmp     cx, r8w
0x140012135  lea     edx, [rax-6]
0x140012138  cmovnz  eax, edx
0x14001213b  movzx   edi, word ptr [rax+r11]
0x140012140  xor     r9d, r9d
0x140012143  movzx   eax, r9w
0x140012147  cmp     eax, esi
0x140012149  jnb     loc_140012240
0x14001214f  mov     r8, [rbx+0C0h]
0x140012156  movzx   eax, r9w
0x14001215a  lea     rdx, [rax+rax*2]
0x14001215e  cmp     di, [r8+rdx*2]
0x140012163  jnz     loc_14001226C
0x140012169  movzx   ecx, word ptr [r8+rdx*2+4]
0x14001216f  sub     ecx, 1
0x140012172  jz      loc_140012265
0x140012178  sub     ecx, 1
0x14001217b  jz      loc_14001222E
0x140012181  cmp     ecx, 1
0x140012184  jmp     loc_14001226A
0x140012189  lea     rcx, [rbp+var_10]; struct DOT11_MAC_STATE_ENTRY **
0x14001218d  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x140012192  mov     rcx, cs:WPP_GLOBAL_Control
0x140012199  cmp     rcx, rdi
0x14001219c  jz      short loc_1400121C0
0x14001219e  cmp     byte ptr [rcx+29h], 4
0x1400121a2  jb      short loc_1400121C0
0x1400121a4  mov     eax, [rcx+2Ch]
0x1400121a7  test    al, 40h
0x1400121a9  jz      short loc_1400121C0
0x1400121ab  mov     rcx, [rcx+18h]
0x1400121af  lea     r8, WPP_28c57b3400c433998a951834ede6818b_Traceguids
0x1400121b6  mov     edx, 0Ch
0x1400121bb  call    WPP_SF_
0x1400121c0  call    cs:__imp_KeGetCurrentIrql
0x1400121c7  nop     dword ptr [rax+rax+00h]
0x1400121cc  xor     r8d, r8d
0x1400121cf  cmp     al, bl
0x1400121d1  jmp     short loc_140012212
0x1400121d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121da  cmp     rcx, rdi
0x1400121dd  jz      short loc_140012201
0x1400121df  cmp     byte ptr [rcx+29h], 4
0x1400121e3  jb      short loc_140012201
0x1400121e5  mov     eax, [rcx+2Ch]
0x1400121e8  test    al, 40h
0x1400121ea  jz      short loc_140012201
0x1400121ec  mov     rcx, [rcx+18h]
0x1400121f0  lea     r8, WPP_28c57b3400c433998a951834ede6818b_Traceguids
0x1400121f7  mov     edx, 0Bh
0x1400121fc  call    WPP_SF_
0x140012201  call    cs:__imp_KeGetCurrentIrql
0x140012208  nop     dword ptr [rax+rax+00h]
0x14001220d  xor     r8d, r8d
0x140012210  cmp     al, 2
0x140012212  mov     rcx, [r14+0A38h]
0x140012219  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14001221d  mov     rdx, r13; struct _NET_BUFFER_LIST *
0x140012220  setz    r8b; unsigned int
0x140012224  call    ?Pt6SendComplete@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@K@Z; Pt6SendComplete(_ADAPT *,_NET_BUFFER_LIST *,ulong)
0x140012229  jmp     loc_140012383
0x14001222e  test    byte ptr [r11+4], 1
0x140012233  jz      short loc_14001226C
0x140012235  movzx   eax, word ptr [r8+rdx*2+2]
0x14001223b  mov     [r10+4], ax
0x140012240  lea     rdi, WPP_GLOBAL_Control
0x140012247  mov     rsi, [rbp+arg_18]
0x14001224b  cmp     [rbp+arg_20], 1
0x14001224f  jnz     short loc_140012275
0x140012251  mov     rcx, [r14+0A38h]; struct _VELAN *
0x140012258  mov     rdx, r13; struct _NET_BUFFER_LIST *
0x14001225b  call    ?Dot11QueueSendPacket@@YAXPEAU_VELAN@@PEAU_NET_BUFFER_LIST@@@Z; Dot11QueueSendPacket(_VELAN *,_NET_BUFFER_LIST *)
0x140012260  jmp     loc_140012383
0x140012265  test    byte ptr [r11+4], 1
0x14001226a  jz      short loc_140012235
0x14001226c  inc     r9w
0x140012270  jmp     loc_140012143
0x140012275  cmp     [rbp+arg_20], 0
0x140012279  jnz     loc_140012383
0x14001227f  mov     rbx, [r14+0A38h]
0x140012286  mov     [rbp+var_8], 0
0x14001228e  mov     dword ptr [rbp+var_10], 0
0x140012295  cmp     dword ptr [rbx+1308h], 0
0x14001229c  jz      short loc_1400122E6
0x14001229e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122a5  cmp     rcx, rdi
0x1400122a8  jz      short loc_1400122CC
0x1400122aa  cmp     byte ptr [rcx+29h], 4
0x1400122ae  jb      short loc_1400122CC
0x1400122b0  mov     eax, [rcx+2Ch]
0x1400122b3  test    al, 40h
0x1400122b5  jz      short loc_1400122CC
0x1400122b7  mov     edx, 0Bh
0x1400122bc  mov     rcx, [rcx+18h]
0x1400122c0  lea     r8, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids
0x1400122c7  call    WPP_SF_
0x1400122cc  call    cs:__imp_KeGetCurrentIrql
0x1400122d3  nop     dword ptr [rax+rax+00h]
0x1400122d8  mov     rcx, [rbx+10h]
0x1400122dc  xor     r8d, r8d
0x1400122df  cmp     al, 2
0x1400122e1  jmp     loc_14001221D
0x1400122e6  test    rsi, rsi
0x1400122e9  jnz     short loc_140012309
0x1400122eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122f2  cmp     rcx, rdi
0x1400122f5  jz      short loc_1400122CC
0x1400122f7  cmp     byte ptr [rcx+29h], 1
0x1400122fb  jb      short loc_1400122CC
0x1400122fd  mov     eax, [rcx+2Ch]
0x140012300  test    al, 40h
0x140012302  jz      short loc_1400122CC
0x140012304  lea     edx, [rsi+0Ch]
0x140012307  jmp     short loc_1400122BC
0x140012309  mov     ecx, [rsi]
0x14001230b  lea     eax, [rcx+1]
0x14001230e  cmp     eax, ecx
0x140012310  jnb     short loc_14001234E
0x140012312  mov     rcx, cs:WPP_GLOBAL_Control
0x140012319  cmp     rcx, rdi
0x14001231c  jz      short loc_140012340
0x14001231e  cmp     byte ptr [rcx+29h], 2
0x140012322  jb      short loc_140012340
0x140012324  mov     eax, [rcx+2Ch]
0x140012327  test    al, 40h
0x140012329  jz      short loc_140012340
0x14001232b  mov     rcx, [rcx+18h]
0x14001232f  lea     r8, WPP_591672ea4a6b33fdc9f57e1d50f33c40_Traceguids
0x140012336  mov     edx, 0Dh
  ... truncated ...
```
