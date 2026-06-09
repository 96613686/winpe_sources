# SendPayloadUnseq

- ea: `0x14001b1e0`
- end: `0x14001b822`
- name: `SendPayloadUnseq`
- size: `1602`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001e1c`
- `0x140003050`
- `0x1400031ec`
- `0x140003ac8`
- `0x140003cf8`
- `0x140003df0`
- `0x140003ec8`
- `0x1400047f0`
- `0x14001b1e0`
- `0x14001b830`
- `0x1400208f0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001b2d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b3fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b4c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b65f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b7ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b2d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b3fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b4c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b65f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b7ac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b260`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b260`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b2ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b2f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b443`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b2ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b2f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b443`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001b377`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001b377`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x14001b7ed`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x14001b7ed`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14001b3d9`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14001b3d9`

## pseudocode

```c
__int64 __fastcall SendPayloadUnseq(PVOID Entry, __int64 a2, __int64 a3, __int64 **a4)
{
  PNET_BUFFER_LIST *p_NetBufferLists; // r13
  __int64 *v9; // r14
  KSPIN_LOCK *v10; // rsi
  __int64 *v11; // rdi
  KIRQL v12; // al
  bool v13; // zf
  __int64 i; // r12
  __int16 v15; // dx
  __int16 *v16; // rcx
  __int16 v17; // sp
  ULONG v18; // esi
  int v19; // edi
  __int64 v20; // r8
  __int64 v21; // rdx
  KIRQL v22; // dl
  int v23; // edi
  KIRQL v24; // al
  __int64 v25; // rcx
  __int16 v26; // dx
  __int64 v27; // rax
  __int64 v28; // rsi
  unsigned int v29; // eax
  __int64 result; // rax
  int v31; // edi
  struct _DEVICE_OBJECT *AttachedDevice; // rsi
  int StringFromSockAddr; // eax
  int v34; // edx
  int v35; // r8d
  __int64 v36; // rdi
  struct _DEVICE_OBJECT *v37; // rbp
  __int64 v38; // rax
  int v39; // edx
  int v40; // r8d
  char v41; // [rsp+40h] [rbp-E8h]
  __int64 v42; // [rsp+48h] [rbp-E0h]
  __int64 v43; // [rsp+50h] [rbp-D8h] BYREF
  __int64 *v44; // [rsp+58h] [rbp-D0h]
  PNET_BUFFER_LIST NetBufferLists; // [rsp+60h] [rbp-C8h] BYREF
  __int16 v46; // [rsp+68h] [rbp-C0h] BYREF
  __int16 v47; // [rsp+6Ah] [rbp-BEh]
  __int16 v48; // [rsp+6Ch] [rbp-BCh] BYREF
  char v49; // [rsp+6Eh] [rbp-BAh] BYREF
  _OWORD v50[4]; // [rsp+80h] [rbp-A8h] BYREF
  char v51; // [rsp+C0h] [rbp-68h]

  p_NetBufferLists = &NetBufferLists;
  NetBufferLists = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  v9 = *a4;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  if ( v9 )
  {
    v10 = (KSPIN_LOCK *)(a3 + 72);
    do
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids, v9);
      }
      v11 = (__int64 *)*v9;
      v44 = (__int64 *)*v9;
      *((_DWORD *)v9 + 35) = 0;
      *v9 = 0;
      v12 = KeAcquireSpinLockRaiseToDpc(v10);
      v13 = (*(_DWORD *)(a3 + 60) & 0x200) == 0;
      *(_BYTE *)(a3 + 80) = v12;
      if ( v13 )
      {
        KeReleaseSpinLock(v10, v12);
        *((_DWORD *)v9 + 35) = -1073741823;
        *p_NetBufferLists = (PNET_BUFFER_LIST)v9;
        p_NetBufferLists = (PNET_BUFFER_LIST *)v9;
      }
      else
      {
        ++*(_DWORD *)(a3 + 64);
        KeReleaseSpinLock(v10, v12);
        *((_DWORD *)v9 + 28) = 1;
        for ( i = v9[1]; i; i = *(_QWORD *)i )
        {
          *(_BYTE *)(a3 + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 40));
          v15 = 16386;
          v46 = 16386;
          v16 = &v48;
          if ( a2 != -116 )
          {
            v16 = (__int16 *)&v49;
            v48 = __ROR2__(*(_WORD *)(a2 + 116), 8);
          }
          if ( a3 != -58 )
          {
            *v16 = __ROR2__(*(_WORD *)(a3 + 58), 8);
            LOWORD(v16) = (_WORD)v16 + 2;
            v15 = v46;
          }
          v46 = __ROR2__(v15, 8);
          v18 = (unsigned __int16)((_WORD)v16 - (v17 + 104));
          v47 = __ROR2__(v18, 8);
          if ( NdisRetreatNetBufferDataStart((PNET_BUFFER)i, v18, 0, 0) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_dq(
                WPP_GLOBAL_Control->AttachedDevice,
                25,
                WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids,
                v18,
                v9);
            }
            KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 40), *(_BYTE *)(a3 + 48));
            *((_DWORD *)v9 + 35) = -1073741823;
            break;
          }
          v19 = *(_DWORD *)(i + 24);
          *(_DWORD *)(i + 136) = v18;
          *(_QWORD *)(i + 128) = v9;
          *(_QWORD *)(i + 144) = a3;
          v47 = __ROR2__(v19, 8);
          v20 = *(unsigned int *)(i + 16);
          v21 = *(_QWORD *)(i + 8);
          v43 = 0;
          RtlCopyKernelBufferToMdl(&v46, v21, v20, v18, &v43);
          ++*(_DWORD *)(a3 + 388);
          v22 = *(_BYTE *)(a3 + 48);
          *(_DWORD *)(a3 + 360) += v19 - v18;
          KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 40), v22);
          _InterlockedIncrement((volatile signed __int32 *)v9 + 28);
          v23 = 0;
          v43 = 0;
          memset(v50, 0, sizeof(v50));
          v51 = 0;
          v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
          v13 = *(_BYTE *)(a2 + 112) == 0;
          v25 = *(_QWORD *)(a2 + 24);
          v26 = *(_WORD *)(a2 + 50);
          *(_BYTE *)(a2 + 40) = v24;
          v27 = 312;
          if ( v13 )
            v27 = 272;
          v41 = __ROR2__(v26, 8);
          v28 = *(_QWORD *)(v25 + v27);
          v42 = v28;
          if ( (*(_DWORD *)(a2 + 120) & 0x4000) != 0 )
          {
            v23 = a2 + 80;
            v43 = a2 + 80;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              v31 = *(_DWORD *)(a2 + 108);
              AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
              StringFromSockAddr = GetStringFromSockAddr(v43, v50);
              WPP_SF_sd((_DWORD)AttachedDevice, v34, v35, StringFromSockAddr, v31);
              v23 = v43;
            }
            v28 = v42;
          }
          KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v36 = *(_QWORD *)(v28 + 384);
            v37 = WPP_GLOBAL_Control->AttachedDevice;
            v38 = GetStringFromSockAddr(a2 + 48, v50);
            WPP_SF_qsdqq((_DWORD)v37, v39, v40, a2, v38, v41, v42, v36);
            v23 = v43;
            LODWORD(v28) = v42;
          }
          v29 = WskSendDatagram(v28, (int)a2 + 48, v23, i, 0, 3, i);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_GLOBAL_Control, v29, i);
          }
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 28, 0xFFFFFFFF) == 1 )
        {
          *p_NetBufferLists = (PNET_BUFFER_LIST)v9;
          p_NetBufferLists = (PNET_BUFFER_LIST *)v9;
          DereferenceCall(a3);
        }
        v11 = v44;
        v10 = (KSPIN_LOCK *)(a3 + 72);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids,
          *((unsigned int *)v9 + 28),
          v9);
      }
      v9 = v11;
    }
    while ( v11 );
    if ( NetBufferLists )
      NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a3 + 304), NetBufferLists, 0);
  }
  result = DereferenceCall(a3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14001b1e0  mov     r11, rsp
0x14001b1e3  sub     rsp, 128h
0x14001b1ea  mov     rax, cs:__security_cookie
0x14001b1f1  xor     rax, rsp
0x14001b1f4  mov     [rsp+128h+var_58], rax
0x14001b1fc  mov     [r11-8], rbx
0x14001b200  mov     rbx, r8
0x14001b203  mov     [r11-10h], rbp
0x14001b207  mov     [r11-20h], rdi
0x14001b20b  mov     rdi, rcx
0x14001b20e  mov     [r11-28h], r12
0x14001b212  xor     r12d, r12d
0x14001b215  mov     [r11-30h], r13
0x14001b219  lea     r13, [rsp+128h+NetBufferLists]
0x14001b21e  mov     [r11-38h], r14
0x14001b222  mov     r14, r9
0x14001b225  mov     [r11-40h], r15
0x14001b229  mov     r15, rdx
0x14001b22c  mov     [rsp+128h+NetBufferLists], r12
0x14001b231  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b238  lea     rbp, WPP_GLOBAL_Control
0x14001b23f  cmp     rcx, rbp
0x14001b242  jz      short loc_14001B24F
0x14001b244  mov     eax, [rcx+2Ch]
0x14001b247  test    al, 10h
0x14001b249  jnz     loc_14001B682
0x14001b24f  mov     rcx, [r15+18h]
0x14001b253  mov     rdx, rdi; Entry
0x14001b256  mov     r14, [r14]
0x14001b259  add     rcx, 3C0h; Lookaside
0x14001b260  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001b267  nop     dword ptr [rax+rax+00h]
0x14001b26c  test    r14, r14
0x14001b26f  jz      loc_14001B584
0x14001b275  mov     [rsp+128h+var_18], rsi
0x14001b27d  lea     rsi, [rbx+48h]
0x14001b281  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b288  cmp     rcx, rbp
0x14001b28b  jz      short loc_14001B298
0x14001b28d  mov     eax, [rcx+2Ch]
0x14001b290  test    al, 10h
0x14001b292  jnz     loc_14001B6A6
0x14001b298  mov     rdi, [r14]
0x14001b29b  mov     rcx, rsi; SpinLock
0x14001b29e  mov     [rsp+128h+var_D0], rdi
0x14001b2a3  mov     [r14+8Ch], r12d
0x14001b2aa  mov     [r14], r12
0x14001b2ad  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b2b4  nop     dword ptr [rax+rax+00h]
0x14001b2b9  test    dword ptr [rbx+3Ch], 200h
0x14001b2c0  mov     rcx, rsi; SpinLock
0x14001b2c3  mov     [rbx+50h], al
0x14001b2c6  movzx   edx, al; NewIrql
0x14001b2c9  jz      loc_14001B65F
0x14001b2cf  inc     dword ptr [rbx+40h]
0x14001b2d2  call    cs:__imp_KeReleaseSpinLock
0x14001b2d9  nop     dword ptr [rax+rax+00h]
0x14001b2de  mov     dword ptr [r14+70h], 1
0x14001b2e6  mov     r12, [r14+8]
0x14001b2ea  test    r12, r12
0x14001b2ed  jz      loc_14001B532
0x14001b2f3  lea     rcx, [rbx+28h]; SpinLock
0x14001b2f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b2fe  nop     dword ptr [rax+rax+00h]
0x14001b303  mov     [rbx+30h], al
0x14001b306  mov     edx, 4002h
0x14001b30b  lea     r8, [rbx+3Ah]
0x14001b30f  mov     [rsp+128h+var_C0], dx
0x14001b314  lea     rax, [r15+74h]
0x14001b318  lea     rcx, [rsp+128h+var_BC]
0x14001b31d  test    rax, rax
0x14001b320  jz      short loc_14001B333
0x14001b322  movzx   eax, word ptr [rax]
0x14001b325  lea     rcx, [rsp+128h+var_BA]
0x14001b32a  ror     ax, 8
0x14001b32e  mov     [rsp+128h+var_BC], ax
0x14001b333  test    r8, r8
0x14001b336  jz      short loc_14001B34C
0x14001b338  movzx   eax, word ptr [r8]
0x14001b33c  ror     ax, 8
0x14001b340  mov     [rcx], ax
0x14001b343  add     rcx, 2
0x14001b347  movzx   edx, [rsp+128h+var_C0]
0x14001b34c  lea     rax, [rsp+128h+var_C0]
0x14001b351  ror     dx, 8
0x14001b355  sub     cx, ax
0x14001b358  mov     [rsp+128h+var_C0], dx
0x14001b35d  movzx   esi, cx
0x14001b360  xor     r9d, r9d; AllocateMdlHandler
0x14001b363  movzx   eax, si
0x14001b366  xor     r8d, r8d; DataBackFill
0x14001b369  ror     ax, 8
0x14001b36d  mov     edx, esi; DataOffsetDelta
0x14001b36f  mov     rcx, r12; NetBuffer
0x14001b372  mov     [rsp+128h+var_BE], ax
0x14001b377  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001b37e  nop     dword ptr [rax+rax+00h]
0x14001b383  test    eax, eax
0x14001b385  jnz     loc_14001B767
0x14001b38b  mov     edi, [r12+18h]
0x14001b390  lea     rcx, [rsp+128h+var_C0]
0x14001b395  movzx   eax, di
0x14001b398  mov     [r12+88h], esi
0x14001b3a0  ror     ax, 8
0x14001b3a4  mov     r9d, esi
0x14001b3a7  mov     [r12+80h], r14
0x14001b3af  mov     [r12+90h], rbx
0x14001b3b7  mov     [rsp+128h+var_BE], ax
0x14001b3bc  lea     rax, [rsp+128h+var_D8]
0x14001b3c1  mov     r8d, [r12+10h]
0x14001b3c6  mov     rdx, [r12+8]
0x14001b3cb  mov     [rsp+128h+var_108], rax
0x14001b3d0  mov     [rsp+128h+var_D8], 0
0x14001b3d9  call    cs:__imp_RtlCopyKernelBufferToMdl
0x14001b3e0  nop     dword ptr [rax+rax+00h]
0x14001b3e5  inc     dword ptr [rbx+184h]
0x14001b3eb  lea     rcx, [rbx+28h]; SpinLock
0x14001b3ef  movzx   edx, byte ptr [rbx+30h]; NewIrql
0x14001b3f3  sub     edi, esi
0x14001b3f5  add     [rbx+168h], edi
0x14001b3fb  call    cs:__imp_KeReleaseSpinLock
0x14001b402  nop     dword ptr [rax+rax+00h]
0x14001b407  lock inc dword ptr [r14+70h]
0x14001b40c  xorps   xmm0, xmm0
0x14001b40f  lea     rcx, [r15+20h]; SpinLock
0x14001b413  xor     eax, eax
0x14001b415  xor     edi, edi
0x14001b417  mov     [rsp+128h+var_D8], rdi
0x14001b41c  movups  [rsp+128h+var_A8], xmm0
0x14001b424  mov     [rsp+128h+var_68], al
0x14001b42b  movups  [rsp+128h+var_98], xmm0
0x14001b433  movups  [rsp+128h+var_88], xmm0
0x14001b43b  movups  [rsp+128h+var_78], xmm0
0x14001b443  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b44a  nop     dword ptr [rax+rax+00h]
0x14001b44f  cmp     [r15+70h], dil
0x14001b453  mov     r8d, 110h
0x14001b459  mov     rcx, [r15+18h]
0x14001b45d  movzx   edx, word ptr [r15+32h]
0x14001b462  mov     [r15+28h], al
0x14001b466  mov     eax, 138h
0x14001b46b  cmovz   eax, r8d
0x14001b46f  ror     dx, 8
0x14001b473  test    dword ptr [r15+78h], 4000h
0x14001b47b  mov     word ptr [rsp+128h+var_E8], dx
0x14001b480  mov     rsi, [rcx+rax]
0x14001b484  mov     [rsp+128h+var_E0], rsi
0x14001b489  jz      short loc_14001B4B7
0x14001b48b  lea     rdi, [r15+50h]
0x14001b48f  mov     [rsp+128h+var_D8], rdi
0x14001b494  mov     rsi, cs:WPP_GLOBAL_Control
0x14001b49b  lea     rax, WPP_GLOBAL_Control
0x14001b4a2  cmp     rsi, rax
0x14001b4a5  jz      short loc_14001B4B2
0x14001b4a7  mov     eax, [rsi+2Ch]
0x14001b4aa  test    al, 10h
0x14001b4ac  jnz     loc_14001B6CD
0x14001b4b2  mov     rsi, [rsp+128h+var_E0]
0x14001b4b7  movzx   edx, byte ptr [r15+28h]; NewIrql
0x14001b4bc  lea     rcx, [r15+20h]; SpinLock
0x14001b4c0  call    cs:__imp_KeReleaseSpinLock
0x14001b4c7  nop     dword ptr [rax+rax+00h]
0x14001b4cc  mov     rbp, cs:WPP_GLOBAL_Control
0x14001b4d3  lea     rax, WPP_GLOBAL_Control
0x14001b4da  cmp     rbp, rax
0x14001b4dd  jz      short loc_14001B4EA
0x14001b4df  mov     eax, [rbp+2Ch]
0x14001b4e2  test    al, 10h
0x14001b4e4  jnz     loc_14001B70A
0x14001b4ea  mov     [rsp+128h+var_F8], r12
0x14001b4ef  lea     rdx, [r15+30h]
0x14001b4f3  mov     [rsp+128h+var_100], 3
0x14001b4fb  mov     r9, r12
0x14001b4fe  mov     r8, rdi
0x14001b501  mov     [rsp+128h+var_108], 0
0x14001b50a  mov     rcx, rsi
0x14001b50d  call    WskSendDatagram
0x14001b512  mov     r8, cs:WPP_GLOBAL_Control
0x14001b519  lea     rbp, WPP_GLOBAL_Control
0x14001b520  cmp     r8, rbp
0x14001b523  jnz     loc_14001B5F4
0x14001b529  mov     r12, [r12]
0x14001b52d  jmp     loc_14001B2EA
0x14001b532  mov     eax, 0FFFFFFFFh
0x14001b537  lock xadd [r14+70h], eax
0x14001b53d  cmp     eax, 1
0x14001b540  jz      loc_14001B7CF
0x14001b546  mov     rdi, [rsp+128h+var_D0]
0x14001b54b  lea     rsi, [rbx+48h]
0x14001b54f  xor     r12d, r12d
0x14001b552  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b559  cmp     rcx, rbp
0x14001b55c  jnz     loc_14001B627
0x14001b562  mov     r14, rdi
0x14001b565  test    rdi, rdi
0x14001b568  jnz     loc_14001B281
0x14001b56e  mov     rdx, [rsp+128h+NetBufferLists]; NetBufferLists
0x14001b573  mov     rsi, [rsp+128h+var_18]
0x14001b57b  test    rdx, rdx
0x14001b57e  jnz     loc_14001B7E3
0x14001b584  mov     rcx, rbx
0x14001b587  call    DereferenceCall
0x14001b58c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b593  mov     r15, [rsp+128h+var_40]
0x14001b59b  cmp     rcx, rbp
0x14001b59e  mov     rbp, [rsp+128h+var_10]
0x14001b5a6  mov     r14, [rsp+128h+var_38]
0x14001b5ae  mov     r13, [rsp+128h+var_30]
0x14001b5b6  mov     r12, [rsp+128h+var_28]
0x14001b5be  mov     rdi, [rsp+128h+var_20]
0x14001b5c6  mov     rbx, [rsp+128h+var_8]
0x14001b5ce  jz      short loc_14001B5DB
0x14001b5d0  mov     eax, [rcx+2Ch]
0x14001b5d3  test    al, 10h
0x14001b5d5  jnz     loc_14001B7FE
0x14001b5db  mov     rcx, [rsp+128h+var_58]
0x14001b5e3  xor     rcx, rsp; StackCookie
0x14001b5e6  call    __security_check_cookie
0x14001b5eb  add     rsp, 128h
0x14001b5f2  retn
0x14001b5f4  mov     ecx, [r8+2Ch]
0x14001b5f8  test    cl, 10h
0x14001b5fb  jz      loc_14001B529
0x14001b601  cmp     byte ptr [r8+29h], 4
0x14001b606  jb      loc_14001B529
0x14001b60c  mov     rcx, [r8+18h]
0x14001b610  mov     edx, 1Ah
0x14001b615  mov     r9d, eax
0x14001b618  mov     [rsp+128h+var_108], r12
0x14001b61d  call    WPP_SF_Dq
0x14001b622  jmp     loc_14001B529
0x14001b627  mov     eax, [rcx+2Ch]
0x14001b62a  test    al, 10h
0x14001b62c  jz      loc_14001B562
0x14001b632  cmp     byte ptr [rcx+29h], 4
0x14001b636  jb      loc_14001B562
0x14001b63c  mov     r9d, [r14+70h]
0x14001b640  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14001b647  mov     rcx, [rcx+18h]
0x14001b64b  mov     edx, 1Bh
0x14001b650  mov     [rsp+128h+var_108], r14
0x14001b655  call    WPP_SF_dq
0x14001b65a  jmp     loc_14001B562
0x14001b65f  call    cs:__imp_KeReleaseSpinLock
0x14001b666  nop     dword ptr [rax+rax+00h]
0x14001b66b  mov     dword ptr [r14+8Ch], 0C0000001h
0x14001b676  mov     [r13+0], r14
0x14001b67a  mov     r13, r14
0x14001b67d  jmp     loc_14001B552
0x14001b682  cmp     byte ptr [rcx+29h], 4
0x14001b686  jb      loc_14001B24F
0x14001b68c  mov     rcx, [rcx+18h]
0x14001b690  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14001b697  mov     edx, 17h
0x14001b69c  call    WPP_SF_
0x14001b6a1  jmp     loc_14001B24F
0x14001b6a6  cmp     byte ptr [rcx+29h], 4
0x14001b6aa  jb      loc_14001B298
0x14001b6b0  mov     rcx, [rcx+18h]
0x14001b6b4  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14001b6bb  mov     edx, 18h
0x14001b6c0  mov     r9, r14
0x14001b6c3  call    WPP_SF_q
0x14001b6c8  jmp     loc_14001B298
0x14001b6cd  cmp     byte ptr [rsi+29h], 1
0x14001b6d1  jb      loc_14001B4B2
0x14001b6d7  mov     rcx, [rsp+128h+var_D8]
0x14001b6dc  lea     rdx, [rsp+128h+var_A8]
0x14001b6e4  mov     edi, [r15+6Ch]
0x14001b6e8  mov     rsi, [rsi+18h]
0x14001b6ec  call    GetStringFromSockAddr
0x14001b6f1  mov     r9, rax
0x14001b6f4  mov     dword ptr [rsp+128h+var_108], edi
0x14001b6f8  mov     rcx, rsi
0x14001b6fb  call    WPP_SF_sd
0x14001b700  mov     rdi, [rsp+128h+var_D8]
0x14001b705  jmp     loc_14001B4B2
0x14001b70a  cmp     byte ptr [rbp+29h], 1
0x14001b70e  jb      loc_14001B4EA
0x14001b714  mov     rdi, [rsi+180h]
0x14001b71b  lea     rcx, [r15+30h]
0x14001b71f  movzx   esi, word ptr [rsp+128h+var_E8]
0x14001b724  lea     rdx, [rsp+128h+var_A8]
0x14001b72c  mov     rbp, [rbp+18h]
0x14001b730  call    GetStringFromSockAddr
0x14001b735  mov     rcx, [rsp+128h+var_E0]
0x14001b73a  mov     r9, r15
0x14001b73d  mov     [rsp+128h+var_F0], rdi
0x14001b742  mov     [rsp+128h+var_F8], rcx
0x14001b747  mov     rcx, rbp
0x14001b74a  mov     [rsp+128h+var_100], esi
0x14001b74e  mov     [rsp+128h+var_108], rax
0x14001b753  call    WPP_SF_qsdqq
0x14001b758  mov     rdi, [rsp+128h+var_D8]
0x14001b75d  mov     rsi, [rsp+128h+var_E0]
0x14001b762  jmp     loc_14001B4EA
0x14001b767  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b76e  lea     rax, WPP_GLOBAL_Control
0x14001b775  cmp     rcx, rax
0x14001b778  jz      short loc_14001B7A4
  ... truncated ...
```
