# CscNotifyDereferenceContextAndComplete_Real

- ea: `0x14006f058`
- end: `0x14006f267`
- name: `CscNotifyDereferenceContextAndComplete_Real`
- size: `527`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400154f0`
- `0x14006e380`
- `0x14006e9e4`
- `0x14006eba0`

## callees

- `0x14000a4f0`
- `0x14000eef0`
- `0x140018930`
- `0x140018b50`
- `0x14001ac1c`
- `0x14001b568`
- `0x1400205dc`
- `0x1400208cc`
- `0x14002f0f0`
- `0x14006f058`
- `0x140076afc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006f1de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f1de`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14006f147`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14006f147`
- `rdbss!RxCompleteRequestEx` at `0x14006f205`
- `rdbss!RxCompleteRequestEx` at `0x14006f205`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14006f21f`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14006f21f`

## pseudocode

```c
__int64 __fastcall CscNotifyDereferenceContextAndComplete_Real(volatile signed __int32 *P)
{
  unsigned int v2; // ebp
  signed __int32 v3; // ebx
  __int64 (__fastcall *v4)(__int64); // r14
  __int64 v5; // rbx
  int v6; // eax
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  char v11; // cl
  IRP *v12; // rcx

  v2 = -1071906810;
  v3 = _InterlockedDecrement(P + 23);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_463ea68f65b43533505b8fb2e756adbc_Traceguids, P, v3);
  if ( !v3 )
  {
    v4 = (__int64 (__fastcall *)(__int64))*((_QWORD *)P + 2);
    v5 = *((_QWORD *)P + 1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_463ea68f65b43533505b8fb2e756adbc_Traceguids,
        P,
        *((_QWORD *)P + 1));
    v6 = v4(v5);
    v7 = v6;
    if ( v6 < 0 && (unsigned __int8)CscTransitnOKToGoOffline((unsigned int)v6) )
    {
      v8 = CscFcbContext(*(_QWORD *)(v5 + 56));
      if ( v8
        && (*(_DWORD *)(v8 + 4) & 0x1000000) == 0
        && !(unsigned __int8)CscLViewIsRootGhosted(*(_QWORD *)(v9 + 128)) )
      {
        if ( (unsigned __int8)ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(*(_QWORD *)(v5 + 56) + 8LL))
          || ((v11 = *(_BYTE *)(v5 + 32), (unsigned __int8)(v11 - 3) <= 1u) || (unsigned __int8)(v11 - 13) <= 1u)
          && ((v10 = *(_QWORD *)(v5 + 584), v10 == (*(_QWORD *)(v5 + 88) | 3LL)) || v10 == *(_QWORD *)(v5 + 88)) )
        {
          LOBYTE(v10) = 1;
          CscTransitionFcbOffline(*(_QWORD *)(v5 + 56), v10, 2, 2);
        }
        else
        {
          CscTransitionFcbOfflineNoLocksHeld((PMRX_FCB)v5);
        }
      }
      _InterlockedAnd8((volatile signed __int8 *)(*(_QWORD *)(v5 + 56) + 256LL), 0xFDu);
      v7 = 267;
    }
    v12 = (IRP *)*((_QWORD *)P + 3);
    if ( v12 )
    {
      CscNotifyFreeIrp(v12);
      *((_QWORD *)P + 3) = 0;
    }
    *(_QWORD *)(v5 + 264) = 0;
    ExFreePoolWithTag((PVOID)P, 0);
    if ( (*(_BYTE *)(v5 + 522) & 1) != 0 || v7 == -1069481983 )
      v2 = v7;
    else
      RxCompleteRequestEx(v5, *(_QWORD *)(v5 + 40), v7);
    *(_QWORD *)(v5 + 528) = v4;
    RxDereferenceAndDeleteRxContext_Real((PRX_CONTEXT)v5);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_463ea68f65b43533505b8fb2e756adbc_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x14006f058  push    rbx
0x14006f05a  push    rbp
0x14006f05b  push    rsi
0x14006f05c  push    rdi
0x14006f05d  push    r12
0x14006f05f  push    r14
0x14006f061  sub     rsp, 38h
0x14006f065  mov     rdi, rcx
0x14006f068  mov     ebp, 0C01C0006h
0x14006f06d  or      ebx, 0FFFFFFFFh
0x14006f070  lock xadd [rcx+5Ch], ebx
0x14006f075  dec     ebx
0x14006f077  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f07e  lea     r12, WPP_GLOBAL_Control
0x14006f085  cmp     rcx, r12
0x14006f088  jz      short loc_14006F0AD
0x14006f08a  mov     eax, [rcx+2Ch]
0x14006f08d  test    al, 40h
0x14006f08f  jz      short loc_14006F0AD
0x14006f091  mov     rcx, [rcx+18h]
0x14006f095  lea     r8, WPP_463ea68f65b43533505b8fb2e756adbc_Traceguids
0x14006f09c  mov     edx, 0Dh
0x14006f0a1  mov     dword ptr [rsp+68h+var_48], ebx
0x14006f0a5  mov     r9, rdi
0x14006f0a8  call    WPP_SF_qD
0x14006f0ad  test    ebx, ebx
0x14006f0af  jnz     loc_14006F22B
0x14006f0b5  mov     r14, [rdi+10h]
0x14006f0b9  mov     rbx, [rdi+8]
0x14006f0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f0c4  cmp     rcx, r12
0x14006f0c7  jz      short loc_14006F0ED
0x14006f0c9  mov     eax, [rcx+2Ch]
0x14006f0cc  test    al, 20h
0x14006f0ce  jz      short loc_14006F0ED
0x14006f0d0  mov     rcx, [rcx+18h]
0x14006f0d4  lea     r8, WPP_463ea68f65b43533505b8fb2e756adbc_Traceguids
0x14006f0db  mov     edx, 0Eh
0x14006f0e0  mov     [rsp+68h+var_48], rbx
0x14006f0e5  mov     r9, rdi
0x14006f0e8  call    WPP_SF_qq
0x14006f0ed  mov     rcx, rbx
0x14006f0f0  mov     rax, r14
0x14006f0f3  call    _guard_dispatch_icall
0x14006f0f8  mov     esi, eax
0x14006f0fa  test    eax, eax
0x14006f0fc  jns     loc_14006F1B8
0x14006f102  mov     ecx, eax
0x14006f104  call    CscTransitnOKToGoOffline
0x14006f109  test    al, al
0x14006f10b  jz      loc_14006F1B8
0x14006f111  mov     r8, [rbx+38h]
0x14006f115  mov     rcx, r8
0x14006f118  call    CscFcbContext
0x14006f11d  test    rax, rax
0x14006f120  jz      loc_14006F1A7
0x14006f126  test    dword ptr [rax+4], 1000000h
0x14006f12d  jnz     short loc_14006F1A7
0x14006f12f  mov     rcx, [r8+80h]
0x14006f136  call    CscLViewIsRootGhosted
0x14006f13b  test    al, al
0x14006f13d  jnz     short loc_14006F1A7
0x14006f13f  mov     rcx, [rbx+38h]
0x14006f143  mov     rcx, [rcx+8]; Resource
0x14006f147  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14006f14e  nop     dword ptr [rax+rax+00h]
0x14006f153  test    al, al
0x14006f155  jnz     short loc_14006F193
0x14006f157  mov     cl, [rbx+20h]
0x14006f15a  lea     eax, [rcx-3]
0x14006f15d  cmp     al, 1
0x14006f15f  jbe     short loc_14006F169
0x14006f161  sub     cl, 0Dh
0x14006f164  cmp     cl, 1
0x14006f167  ja      short loc_14006F185
0x14006f169  mov     rcx, [rbx+58h]
0x14006f16d  mov     rdx, [rbx+248h]
0x14006f174  mov     rax, rcx
0x14006f177  or      rax, 3
0x14006f17b  cmp     rdx, rax
0x14006f17e  jz      short loc_14006F193
0x14006f180  cmp     rdx, rcx
0x14006f183  jz      short loc_14006F193
0x14006f185  mov     rdx, [rbx+38h]
0x14006f189  mov     rcx, rbx; Fcb
0x14006f18c  call    CscTransitionFcbOfflineNoLocksHeld
0x14006f191  jmp     short loc_14006F1A7
0x14006f193  mov     rcx, [rbx+38h]
0x14006f197  mov     r8d, 2
0x14006f19d  mov     r9d, r8d
0x14006f1a0  mov     dl, 1
0x14006f1a2  call    CscTransitionFcbOffline
0x14006f1a7  mov     rax, [rbx+38h]
0x14006f1ab  lock and byte ptr [rax+100h], 0FDh
0x14006f1b3  mov     esi, 10Bh
0x14006f1b8  mov     rcx, [rdi+18h]; Irp
0x14006f1bc  test    rcx, rcx
0x14006f1bf  jz      short loc_14006F1CE
0x14006f1c1  call    CscNotifyFreeIrp
0x14006f1c6  mov     qword ptr [rdi+18h], 0
0x14006f1ce  xor     edx, edx; Tag
0x14006f1d0  mov     qword ptr [rbx+108h], 0
0x14006f1db  mov     rcx, rdi; P
0x14006f1de  call    cs:__imp_ExFreePoolWithTag
0x14006f1e5  nop     dword ptr [rax+rax+00h]
0x14006f1ea  test    byte ptr [rbx+20Ah], 1
0x14006f1f1  jnz     short loc_14006F213
0x14006f1f3  cmp     esi, 0C0410001h
0x14006f1f9  jz      short loc_14006F213
0x14006f1fb  mov     rdx, [rbx+28h]
0x14006f1ff  mov     r8d, esi
0x14006f202  mov     rcx, rbx
0x14006f205  call    cs:__imp_RxCompleteRequestEx
0x14006f20c  nop     dword ptr [rax+rax+00h]
0x14006f211  jmp     short loc_14006F215
0x14006f213  mov     ebp, esi
0x14006f215  mov     rcx, rbx; RxContext
0x14006f218  mov     [rbx+210h], r14
0x14006f21f  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x14006f226  nop     dword ptr [rax+rax+00h]
0x14006f22b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f232  cmp     rcx, r12
0x14006f235  jz      short loc_14006F257
0x14006f237  mov     edx, [rcx+2Ch]
0x14006f23a  test    dl, 20h
0x14006f23d  jz      short loc_14006F257
0x14006f23f  mov     rcx, [rcx+18h]
0x14006f243  lea     r8, WPP_463ea68f65b43533505b8fb2e756adbc_Traceguids
0x14006f24a  mov     edx, 0Fh
0x14006f24f  mov     r9d, ebp
0x14006f252  call    WPP_SF_d
0x14006f257  mov     eax, ebp
0x14006f259  add     rsp, 38h
0x14006f25d  pop     r14
0x14006f25f  pop     r12
0x14006f261  pop     rdi
0x14006f262  pop     rsi
0x14006f263  pop     rbp
0x14006f264  pop     rbx
0x14006f265  retn
```
