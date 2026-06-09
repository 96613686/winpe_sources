# lldpTxTtr

- ea: `0x1400022c0`
- end: `0x1400024f9`
- name: `lldpTxTtr`
- size: `569`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400022c0`
- `0x140002500`
- `0x140005a6c`
- `0x140005dd0`
- `0x1400060e0`
- `0x140006840`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x1400023d6`
- `NDIS!NdisReleaseRWLock` at `0x1400023d6`
- `NDIS!NdisAcquireRWLockRead` at `0x14000234c`
- `NDIS!NdisAcquireRWLockRead` at `0x14000234c`
- `NDIS!NdisSendNetBufferLists` at `0x14000241f`
- `NDIS!NdisSendNetBufferLists` at `0x14000241f`

## pseudocode

```c
void __fastcall lldpTxTtr(struct _KDPC *Dpc, char *DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)
{
  int v4; // ecx
  char *v5; // rbx
  int v6; // ecx
  int v7; // eax
  struct _NET_BUFFER_LIST **v8; // r14
  unsigned int v9; // ecx
  __int64 v10; // r9
  PNET_BUFFER FirstNetBuffer; // rdi
  int v12; // esi
  ULONG v13; // esi
  struct _NET_BUFFER_LIST *v14; // rdi
  PNET_BUFFER v15; // r8
  struct _LOCK_STATE_EX LockState; // [rsp+48h] [rbp+10h] BYREF

  v4 = *((_DWORD *)DeferredContext + 62);
  *(_WORD *)&LockState.OldIrql = 0;
  v5 = DeferredContext;
  LockState.Flags = 0;
  if ( v4 && ((v6 = v4 - 1) == 0 || v6 == 2) )
  {
    v7 = _InterlockedDecrement((volatile signed __int32 *)DeferredContext + 219);
    if ( v7 )
    {
      if ( v7 < -10000000 )
        _InterlockedExchange((volatile __int32 *)DeferredContext + 219, 0);
    }
    else
    {
      lldpRecalculateTxTimer(DeferredContext, 0, SystemArgument1, SystemArgument2);
    }
    if ( _InterlockedExchange((volatile __int32 *)v5 + 38, 1) == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, DeferredContext, SystemArgument1, *((_QWORD *)v5 + 20));
    }
    else
    {
      NdisAcquireRWLockRead(*((PNDIS_RW_LOCK_EX *)v5 + 122), &LockState, 1u);
      v8 = (struct _NET_BUFFER_LIST **)(v5 + 160);
      if ( v5[151] )
      {
        v9 = *((_DWORD *)v5 + 34) - *((_DWORD *)v5 + 35);
        v10 = *((_QWORD *)v5 + 22);
        FirstNetBuffer = (*v8)->FirstNetBuffer;
        v12 = *((_DWORD *)v5 + 247);
        *(_DWORD *)(v10 + 6) = *((_DWORD *)v5 + 36);
        v13 = v9 + v12;
        *(_WORD *)(v10 + 10) = *((_WORD *)v5 + 74);
        memmove((void *)(v10 + v9), v5 + 996, *((unsigned int *)v5 + 247));
        FirstNetBuffer->DataLength = v13;
        v5[151] = 0;
      }
      NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v5 + 122), &LockState);
      v14 = *v8;
      if ( ((__int64)WPP_MAIN_CB.SecurityDescriptor & 0x20) != 0 )
      {
        v15 = v14->FirstNetBuffer;
        McTemplateK0qqbr1_EtwWriteTransfer(
          v15->Link.Region,
          (unsigned int)LldpduTransmitted,
          (_DWORD)v15,
          *((_DWORD *)v5 + 32),
          v15->DataLength,
          *(_QWORD *)(v15->Link.Region + 32)
        + v15->CurrentMdlOffset
        + (unsigned __int64)*(unsigned int *)(v15->Link.Region + 44));
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids,
          HIWORD(*((_QWORD *)v5 + 15)),
          (*((_QWORD *)v5 + 15) >> 24) & 0xFFFFFF);
      NdisSendNetBufferLists(*(NDIS_HANDLE *)(*((_QWORD *)v5 + 3) + 8LL), v14, *((_DWORD *)v5 + 1), 1u);
    }
  }
  else
  {
    LOBYTE(DeferredContext) = 1;
    lldpRecalculateTxTimer(v5, DeferredContext, SystemArgument1, SystemArgument2);
  }
}

```

## disassembly

```asm
0x1400022c0  push    rbx
0x1400022c2  sub     rsp, 30h
0x1400022c6  mov     ecx, [rdx+0F8h]
0x1400022cc  xor     eax, eax
0x1400022ce  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x1400022d3  mov     rbx, rdx
0x1400022d6  mov     [rsp+38h+LockState.Flags], al
0x1400022da  test    ecx, ecx
0x1400022dc  jz      short loc_1400022ED
0x1400022de  sub     ecx, 1
0x1400022e1  jz      short loc_1400022FE
0x1400022e3  sub     ecx, 1
0x1400022e6  jz      short loc_1400022ED
0x1400022e8  cmp     ecx, 1
0x1400022eb  jz      short loc_1400022FE
0x1400022ed  mov     dl, 1
0x1400022ef  mov     rcx, rbx
0x1400022f2  call    lldpRecalculateTxTimer
0x1400022f7  add     rsp, 30h
0x1400022fb  pop     rbx
0x1400022fc  retn
0x1400022fe  mov     eax, 0FFFFFFFFh
0x140002303  lock xadd [rdx+36Ch], eax
0x14000230b  sub     eax, 1
0x14000230e  jz      loc_14000246C
0x140002314  cmp     eax, 0FF676980h
0x140002319  jl      loc_14000247B
0x14000231f  mov     eax, 1
0x140002324  xchg    eax, [rbx+98h]
0x14000232a  cmp     eax, 1
0x14000232d  jz      loc_140002488
0x140002333  mov     rcx, [rbx+3D0h]; Lock
0x14000233a  lea     rdx, [rsp+38h+LockState]; LockState
0x14000233f  mov     [rsp+38h+arg_10], rdi
0x140002344  mov     r8b, 1; Flags
0x140002347  mov     [rsp+38h+arg_18], r14
0x14000234c  call    cs:__imp_NdisAcquireRWLockRead
0x140002353  nop     dword ptr [rax+rax+00h]
0x140002358  cmp     byte ptr [rbx+97h], 0
0x14000235f  lea     r14, [rbx+0A0h]
0x140002366  jz      short loc_1400023CA
0x140002368  mov     rax, [r14]
0x14000236b  lea     rdx, [rbx+3E4h]; Src
0x140002372  mov     ecx, [rbx+88h]
0x140002378  sub     ecx, [rbx+8Ch]
0x14000237e  mov     r9, [rbx+0B0h]
0x140002385  mov     rdi, [rax+8]
0x140002389  mov     eax, [rbx+90h]
0x14000238f  mov     [rsp+38h+arg_0], rsi
0x140002394  mov     esi, [rbx+3DCh]
0x14000239a  mov     [r9+6], eax
0x14000239e  add     esi, ecx
0x1400023a0  movzx   eax, word ptr [rbx+94h]
0x1400023a7  add     rcx, r9; void *
0x1400023aa  mov     [r9+0Ah], ax
0x1400023af  mov     r8d, [rbx+3DCh]; Size
0x1400023b6  call    memmove
0x1400023bb  mov     [rdi+18h], esi
0x1400023be  mov     rsi, [rsp+38h+arg_0]
0x1400023c3  mov     byte ptr [rbx+97h], 0
0x1400023ca  mov     rcx, [rbx+3D0h]; Lock
0x1400023d1  lea     rdx, [rsp+38h+LockState]; LockState
0x1400023d6  call    cs:__imp_NdisReleaseRWLock
0x1400023dd  nop     dword ptr [rax+rax+00h]
0x1400023e2  test    byte ptr cs:WPP_MAIN_CB.SecurityDescriptor, 20h
0x1400023e9  mov     rdi, [r14]
0x1400023ec  mov     r14, [rsp+38h+arg_18]
0x1400023f1  jnz     loc_1400024BE
0x1400023f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023fe  lea     rax, WPP_GLOBAL_Control
0x140002405  cmp     rcx, rax
0x140002408  jnz     short loc_140002437
0x14000240a  mov     rcx, [rbx+18h]
0x14000240e  mov     r9d, 1; SendFlags
0x140002414  mov     r8d, [rbx+4]; PortNumber
0x140002418  mov     rdx, rdi; NetBufferLists
0x14000241b  mov     rcx, [rcx+8]; NdisBindingHandle
0x14000241f  call    cs:__imp_NdisSendNetBufferLists
0x140002426  nop     dword ptr [rax+rax+00h]
0x14000242b  mov     rdi, [rsp+38h+arg_10]
0x140002430  add     rsp, 30h
0x140002434  pop     rbx
0x140002435  retn
0x140002437  cmp     byte ptr [rcx+29h], 4
0x14000243b  jb      short loc_14000240A
0x14000243d  mov     r9, [rbx+78h]
0x140002441  lea     r8, WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids
0x140002448  mov     rcx, [rcx+18h]
0x14000244c  mov     rax, r9
0x14000244f  shr     rax, 18h
0x140002453  mov     edx, 0Fh
0x140002458  and     eax, 0FFFFFFh
0x14000245d  shr     r9, 30h
0x140002461  mov     [rsp+38h+var_18], eax
0x140002465  call    WPP_SF_DD
0x14000246a  jmp     short loc_14000240A
0x14000246c  xor     edx, edx
0x14000246e  mov     rcx, rbx
0x140002471  call    lldpRecalculateTxTimer
0x140002476  jmp     loc_14000231F
0x14000247b  xor     eax, eax
0x14000247d  xchg    eax, [rdx+36Ch]
0x140002483  jmp     loc_14000231F
0x140002488  mov     rcx, cs:WPP_GLOBAL_Control
0x14000248f  lea     rax, WPP_GLOBAL_Control
0x140002496  cmp     rcx, rax
0x140002499  jz      loc_1400022F7
0x14000249f  cmp     byte ptr [rcx+29h], 3
0x1400024a3  jb      loc_1400022F7
0x1400024a9  mov     r9, [rbx+0A0h]
0x1400024b0  mov     rcx, [rcx+18h]
0x1400024b4  call    WPP_SF_q
0x1400024b9  jmp     loc_1400022F7
0x1400024be  mov     r8, [rdi+8]
0x1400024c2  mov     r9d, [rbx+80h]
0x1400024c9  mov     rcx, [r8+8]
0x1400024cd  mov     eax, [r8+10h]
0x1400024d1  mov     edx, [rcx+2Ch]
0x1400024d4  add     rdx, rax
0x1400024d7  mov     eax, [r8+18h]
0x1400024db  add     rdx, [rcx+20h]
0x1400024df  mov     [rsp+38h+var_10], rdx
0x1400024e4  lea     rdx, LldpduTransmitted
0x1400024eb  mov     [rsp+38h+var_18], eax
0x1400024ef  call    McTemplateK0qqbr1_EtwWriteTransfer
0x1400024f4  jmp     loc_1400023F7
```
