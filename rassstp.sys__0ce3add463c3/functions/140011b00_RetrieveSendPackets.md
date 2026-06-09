# RetrieveSendPackets

- ea: `0x140011b00`
- end: `0x14001219b`
- name: `RetrieveSendPackets`
- size: `1691`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140012290`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140002f88`
- `0x1400039a0`
- `0x140005ef0`
- `0x14000e008`
- `0x14000e0a8`
- `0x140011b00`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011dd9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011e27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011ff6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012083`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400120e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011dd9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011e27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011ff6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012083`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400120e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011cd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001213e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011cd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001213e`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x14001215e`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x14001215e`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x140011f6c`
- `NETIO!RtlCopyMdlToBufferToMode` at `0x140011f6c`
- `NETIO!HfGetPointerFromHandle32` at `0x140011b69`
- `NETIO!HfGetPointerFromHandle32` at `0x140011b69`

## pseudocode

```c
char __fastcall RetrieveSendPackets(__int64 a1, unsigned int a2, __int64 a3, unsigned int a4)
{
  unsigned int v5; // esi
  KIRQL v6; // r14
  __int64 v7; // rbx
  struct _NET_BUFFER_LIST *v9; // r15
  int v10; // r12d
  KIRQL i; // al
  __int64 v12; // r8
  KIRQL v13; // r14
  __int64 v14; // rbx
  __int64 v15; // r12
  __int64 *j; // r14
  unsigned int v17; // edx
  __int64 v18; // r9
  volatile signed __int32 *v19; // [rsp+30h] [rbp-78h] BYREF
  int v20; // [rsp+38h] [rbp-70h]
  unsigned int v21; // [rsp+3Ch] [rbp-6Ch]
  unsigned int v22; // [rsp+40h] [rbp-68h]
  PNET_BUFFER_LIST NetBufferLists; // [rsp+48h] [rbp-60h]
  __int64 v24; // [rsp+50h] [rbp-58h]
  int PointerFromHandle32; // [rsp+58h] [rbp-50h]
  _QWORD v26[2]; // [rsp+60h] [rbp-48h] BYREF
  _DWORD *v27; // [rsp+70h] [rbp-38h]

  v27 = (_DWORD *)a1;
  v19 = 0;
  v5 = 0;
  v21 = 0;
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 62);
  PointerFromHandle32 = HfGetPointerFromHandle32(*((_QWORD *)SstpGlobals + 63), a2, &v19);
  if ( PointerFromHandle32 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
    v7 = a1;
  }
  else
  {
    v9 = 0;
    NetBufferLists = 0;
    v10 = 0;
    v20 = 0;
    _InterlockedIncrement(v19);
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v6);
    for ( i = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v19 + 4); ; i = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v19 + 4) )
    {
      v13 = i;
      v14 = *((_QWORD *)v19 + 12);
      if ( !v14 )
        goto LABEL_24;
      if ( a4 < v5 )
        break;
      v26[1] = *((_QWORD *)v19 + 12);
      *((_QWORD *)v19 + 12) = *(_QWORD *)v14;
      KeReleaseSpinLock((PKSPIN_LOCK)v19 + 4, i);
      if ( *(_BYTE *)(v14 + 8) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF__guid_(
            WPP_GLOBAL_Control->AttachedDevice,
            60,
            WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
            v19 + 121);
        }
        if ( *(unsigned __int16 *)(v14 + 16) > a4 - v5 )
        {
          v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v19 + 4);
          *(_QWORD *)v14 = *((_QWORD *)v19 + 12);
          *((_QWORD *)v19 + 12) = v14;
LABEL_24:
          v7 = a1;
          goto LABEL_25;
        }
        RtlCopyToUser((void *)(a3 + v5), (void *)(v14 + 18), *(unsigned __int16 *)(v14 + 16));
        v5 += *(unsigned __int16 *)(v14 + 16);
        v21 = v5;
        (*((void (__fastcall **)(__int64))SstpGlobals + 68))(v14);
      }
      else
      {
        v15 = v14 - 96;
        v26[0] = 0;
        for ( j = *(__int64 **)(v14 - 96 + 112); j; j = (__int64 *)*j )
        {
          *(_QWORD *)(v15 + 112) = j;
          v17 = *((_DWORD *)j + 6);
          LODWORD(v24) = v17;
          if ( v17 <= 0xFFB )
          {
            if ( a4 - v5 < v17 + 4 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF__guid_(
                  WPP_GLOBAL_Control->AttachedDevice,
                  64,
                  WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
                  v19 + 121);
              }
              v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v19 + 4);
              *(_QWORD *)v14 = *((_QWORD *)v19 + 12);
              *((_QWORD *)v19 + 12) = v14;
              v10 = v20;
              goto LABEL_24;
            }
            LOWORD(v22) = 16;
            HIWORD(v22) = __ROR2__(v17 + 4, 8);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF__guid_(
                WPP_GLOBAL_Control->AttachedDevice,
                62,
                WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
                v19 + 121);
            }
            RtlWriteULongToUser(a3 + v5, v22);
            v5 += 4;
            v21 = v5;
            v24 = (unsigned int)v24;
            LOBYTE(v18) = 1;
            RtlCopyMdlToBufferToMode(j[1], *((unsigned int *)j + 4), a3 + v5, v18, (unsigned int)v24, v26);
            if ( v24 == v26[0] )
            {
              v5 += LODWORD(v26[0]);
              v21 = v5;
            }
          }
        }
        ++v20;
        *(_DWORD *)(v15 + 140) = 0;
        NetBufferLists = (PNET_BUFFER_LIST)(v14 - 96);
        if ( v9 )
          *(_QWORD *)v15 = v9;
        v9 = (struct _NET_BUFFER_LIST *)(v14 - 96);
        v10 = v20;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
    *v27 = -1073741811;
    v7 = a1;
    *(_QWORD *)(a1 + 8) = v5;
LABEL_25:
    if ( *((_QWORD *)v19 + 12) )
    {
      *((_BYTE *)v19 + 88) = 1;
    }
    else
    {
      *((_BYTE *)v19 + 88) = 0;
      *((_QWORD *)v19 + 13) = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF__guid_l(WPP_GLOBAL_Control->AttachedDevice, 4, v12, v19 + 121, *((unsigned __int8 *)v19 + 88));
    }
    KeReleaseSpinLock((PKSPIN_LOCK)v19 + 4, v13);
    if ( v9 )
      NdisMCoSendNetBufferListsComplete(*((NDIS_HANDLE *)v19 + 5), v9, 0);
    DereferenceRefCount(v19);
    for ( ; v10; --v10 )
      DereferenceRefCount((char *)SstpGlobals + 144);
  }
  *v27 = PointerFromHandle32;
  *(_QWORD *)(v7 + 8) = v5;
  return 1;
}

```

## disassembly

```asm
0x140011b00  mov     rax, rsp
0x140011b03  mov     [rax+10h], rbx
0x140011b07  mov     [rax+20h], r9d
0x140011b0b  mov     [rax+18h], r8
0x140011b0f  mov     [rax+8], rcx
0x140011b13  push    rsi
0x140011b14  push    r12
0x140011b16  push    r13
0x140011b18  push    r14
0x140011b1a  push    r15
0x140011b1c  sub     rsp, 80h
0x140011b23  mov     ebx, edx
0x140011b25  mov     [rsp+0A8h+var_38], rcx
0x140011b2a  mov     qword ptr [rax-78h], 0
0x140011b32  xor     esi, esi
0x140011b34  mov     [rax-6Ch], esi
0x140011b37  mov     rcx, cs:SstpGlobals
0x140011b3e  add     rcx, 1F0h; SpinLock
0x140011b45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011b4c  nop     dword ptr [rax+rax+00h]
0x140011b51  mov     r14b, al
0x140011b54  lea     r8, [rsp+0A8h+var_78]
0x140011b59  mov     edx, ebx
0x140011b5b  mov     rcx, cs:SstpGlobals
0x140011b62  mov     rcx, [rcx+1F8h]
0x140011b69  call    cs:__imp_HfGetPointerFromHandle32
0x140011b70  nop     dword ptr [rax+rax+00h]
0x140011b75  mov     [rsp+0A8h+var_50], eax
0x140011b79  mov     dl, r14b; NewIrql
0x140011b7c  test    eax, eax
0x140011b7e  jz      loc_140011C06
0x140011b84  mov     rcx, cs:SstpGlobals
0x140011b8b  add     rcx, 1F0h; SpinLock
0x140011b92  call    cs:__imp_KeReleaseSpinLock
0x140011b99  nop     dword ptr [rax+rax+00h]
0x140011b9e  lea     r13, WPP_GLOBAL_Control
0x140011ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x140011bac  cmp     rcx, r13
0x140011baf  jz      short loc_140011BD1
0x140011bb1  mov     eax, [rcx+2Ch]
0x140011bb4  test    al, 2
0x140011bb6  jz      short loc_140011BD1
0x140011bb8  cmp     byte ptr [rcx+29h], 1
0x140011bbc  jb      short loc_140011BD1
0x140011bbe  lea     edx, [rsi+3Ah]
0x140011bc1  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011bc8  mov     rcx, [rcx+18h]
0x140011bcc  call    WPP_SF_
0x140011bd1  mov     rbx, [rsp+0A8h+arg_0]
0x140011bd9  mov     rax, [rsp+0A8h+var_38]
0x140011bde  mov     ecx, [rsp+0A8h+var_50]
0x140011be2  mov     [rax], ecx
0x140011be4  mov     ecx, esi
0x140011be6  mov     [rbx+8], rcx
0x140011bea  mov     al, 1
0x140011bec  mov     rbx, [rsp+0A8h+arg_8]
0x140011bf4  add     rsp, 80h
0x140011bfb  pop     r15
0x140011bfd  pop     r14
0x140011bff  pop     r13
0x140011c01  pop     r12
0x140011c03  pop     rsi
0x140011c04  retn
0x140011c06  xor     r15d, r15d
0x140011c09  mov     [rsp+0A8h+NetBufferLists], r15
0x140011c0e  xor     r12d, r12d
0x140011c11  mov     [rsp+0A8h+var_70], r12d
0x140011c16  mov     rax, [rsp+0A8h+var_78]
0x140011c1b  lock inc dword ptr [rax]
0x140011c1e  mov     rcx, cs:SstpGlobals
0x140011c25  add     rcx, 1F0h; SpinLock
0x140011c2c  call    cs:__imp_KeReleaseSpinLock
0x140011c33  nop     dword ptr [rax+rax+00h]
0x140011c38  mov     rcx, [rsp+0A8h+var_78]
0x140011c3d  add     rcx, 20h ; ' '; SpinLock
0x140011c41  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011c48  nop     dword ptr [rax+rax+00h]
0x140011c4d  lea     r13, WPP_GLOBAL_Control
0x140011c54  mov     r14b, al
0x140011c57  mov     rcx, [rsp+0A8h+var_78]
0x140011c5c  mov     rbx, [rcx+60h]
0x140011c60  test    rbx, rbx
0x140011c63  jz      loc_140011E4B
0x140011c69  cmp     [rsp+0A8h+arg_18], esi
0x140011c70  jnb     short loc_140011CBE
0x140011c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c79  cmp     rcx, r13
0x140011c7c  jz      short loc_140011CA0
0x140011c7e  mov     eax, [rcx+2Ch]
0x140011c81  test    al, 2
0x140011c83  jz      short loc_140011CA0
0x140011c85  cmp     byte ptr [rcx+29h], 1
0x140011c89  jb      short loc_140011CA0
0x140011c8b  mov     edx, 3Bh ; ';'
0x140011c90  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011c97  mov     rcx, [rcx+18h]
0x140011c9b  call    WPP_SF_
0x140011ca0  mov     rax, [rsp+0A8h+var_38]
0x140011ca5  mov     dword ptr [rax], 0C000000Dh
0x140011cab  mov     eax, esi
0x140011cad  mov     rbx, [rsp+0A8h+arg_0]
0x140011cb5  mov     [rbx+8], rax
0x140011cb9  jmp     loc_140011E53
0x140011cbe  mov     [rsp+0A8h+var_40], rbx
0x140011cc3  mov     rax, [rbx]
0x140011cc6  mov     [rcx+60h], rax
0x140011cca  mov     rcx, [rsp+0A8h+var_78]
0x140011ccf  add     rcx, 20h ; ' '; SpinLock
0x140011cd3  mov     dl, r14b; NewIrql
0x140011cd6  call    cs:__imp_KeReleaseSpinLock
0x140011cdd  nop     dword ptr [rax+rax+00h]
0x140011ce2  cmp     byte ptr [rbx+8], 0
0x140011ce6  jz      loc_140011E7E
0x140011cec  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cf3  cmp     rcx, r13
0x140011cf6  jz      short loc_140011D28
0x140011cf8  test    dword ptr [rcx+2Ch], 100h
0x140011cff  jz      short loc_140011D28
0x140011d01  cmp     byte ptr [rcx+29h], 4
0x140011d05  jb      short loc_140011D28
0x140011d07  mov     r9, [rsp+0A8h+var_78]
0x140011d0c  add     r9, 1E4h
0x140011d13  mov     edx, 3Ch ; '<'
0x140011d18  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011d1f  mov     rcx, [rcx+18h]
0x140011d23  call    WPP_SF__guid_
0x140011d28  movzx   ecx, word ptr [rbx+10h]
0x140011d2c  mov     eax, [rsp+0A8h+arg_18]
0x140011d33  sub     eax, esi
0x140011d35  cmp     ecx, eax
0x140011d37  ja      loc_140011E1E
0x140011d3d  mov     r8d, ecx; Size
0x140011d40  lea     rdx, [rbx+12h]; Src
0x140011d44  mov     ecx, esi
0x140011d46  add     rcx, [rsp+0A8h+arg_10]; void *
0x140011d4e  call    RtlCopyToUser
0x140011d53  nop
0x140011d54  movzx   eax, word ptr [rbx+10h]
0x140011d58  add     esi, eax
0x140011d5a  mov     [rsp+0A8h+var_6C], esi
0x140011d5e  mov     rax, cs:SstpGlobals
0x140011d65  mov     rax, [rax+220h]
0x140011d6c  mov     rcx, rbx
0x140011d6f  call    _guard_dispatch_icall
0x140011d74  jmp     loc_1400120D7
0x140011d79  lea     rax, WPP_GLOBAL_Control
0x140011d80  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d87  cmp     rcx, rax
0x140011d8a  jz      short loc_140011DBA
0x140011d8c  mov     eax, [rcx+2Ch]
0x140011d8f  test    al, 2
0x140011d91  jz      short loc_140011DBA
0x140011d93  cmp     byte ptr [rcx+29h], 1
0x140011d97  jb      short loc_140011DBA
0x140011d99  mov     r9, [rsp+0A8h+var_78]
0x140011d9e  add     r9, 1E4h
0x140011da5  mov     edx, 3Dh ; '='
0x140011daa  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011db1  mov     rcx, [rcx+18h]
0x140011db5  call    WPP_SF__guid_
0x140011dba  mov     rbx, [rsp+0A8h+arg_0]
0x140011dc2  mov     dword ptr [rbx], 0C000000Dh
0x140011dc8  mov     qword ptr [rbx+8], 0
0x140011dd0  mov     rcx, [rsp+0A8h+var_78]
0x140011dd5  add     rcx, 20h ; ' '; SpinLock
0x140011dd9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011de0  nop     dword ptr [rax+rax+00h]
0x140011de5  mov     r14b, al
0x140011de8  mov     rax, [rsp+0A8h+var_78]
0x140011ded  mov     rcx, [rax+60h]
0x140011df1  mov     rdx, [rsp+0A8h+var_40]
0x140011df6  mov     [rdx], rcx
0x140011df9  mov     rax, [rsp+0A8h+var_78]
0x140011dfe  mov     [rax+60h], rdx
0x140011e02  lea     r13, WPP_GLOBAL_Control
0x140011e09  mov     edx, 4
0x140011e0e  mov     esi, [rsp+0A8h+var_6C]
0x140011e12  mov     r15, [rsp+0A8h+NetBufferLists]
0x140011e17  mov     r12d, [rsp+0A8h+var_70]
0x140011e1c  jmp     short loc_140011E58
0x140011e1e  mov     rcx, [rsp+0A8h+var_78]
0x140011e23  add     rcx, 20h ; ' '; SpinLock
0x140011e27  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011e2e  nop     dword ptr [rax+rax+00h]
0x140011e33  mov     r14b, al
0x140011e36  mov     rax, [rsp+0A8h+var_78]
0x140011e3b  mov     rcx, [rax+60h]
0x140011e3f  mov     [rbx], rcx
0x140011e42  mov     rax, [rsp+0A8h+var_78]
0x140011e47  mov     [rax+60h], rbx
0x140011e4b  mov     rbx, [rsp+0A8h+arg_0]
0x140011e53  mov     edx, 4
0x140011e58  mov     rax, [rsp+0A8h+var_78]
0x140011e5d  cmp     qword ptr [rax+60h], 0
0x140011e62  jnz     loc_1400120F1
0x140011e68  mov     byte ptr [rax+58h], 0
0x140011e6c  mov     rax, [rsp+0A8h+var_78]
0x140011e71  mov     qword ptr [rax+68h], 0
0x140011e79  jmp     loc_1400120FA
0x140011e7e  lea     r12, [rbx-60h]
0x140011e82  mov     [rsp+0A8h+var_48], 0
0x140011e8b  mov     r14, [r12+70h]
0x140011e90  test    r14, r14
0x140011e93  jz      loc_1400120B1
0x140011e99  mov     [r12+70h], r14
0x140011e9e  mov     edx, [r14+18h]
0x140011ea2  mov     dword ptr [rsp+0A8h+var_58], edx
0x140011ea6  cmp     edx, 0FFBh
0x140011eac  jbe     short loc_140011EB3
0x140011eae  mov     r14, [r14]
0x140011eb1  jmp     short loc_140011E90
0x140011eb3  mov     ecx, [rsp+0A8h+arg_18]
0x140011eba  sub     ecx, esi
0x140011ebc  lea     eax, [rdx+4]
0x140011ebf  cmp     ecx, eax
0x140011ec1  jb      loc_14001203E
0x140011ec7  xor     eax, eax
0x140011ec9  mov     [rsp+0A8h+var_68], eax
0x140011ecd  mov     word ptr [rsp+0A8h+var_68], 10h
0x140011ed4  movzx   eax, dx
0x140011ed7  mov     edx, 4
0x140011edc  add     ax, dx
0x140011edf  ror     ax, 8
0x140011ee3  mov     word ptr [rsp+0A8h+var_68+2], ax
0x140011ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x140011eef  cmp     rcx, r13
0x140011ef2  jz      short loc_140011F24
0x140011ef4  test    dword ptr [rcx+2Ch], 100h
0x140011efb  jz      short loc_140011F24
0x140011efd  cmp     [rcx+29h], dl
0x140011f00  jb      short loc_140011F24
0x140011f02  mov     r9, [rsp+0A8h+var_78]
0x140011f07  add     r9, 1E4h
0x140011f0e  mov     edx, 3Eh ; '>'
0x140011f13  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011f1a  mov     rcx, [rcx+18h]
0x140011f1e  call    WPP_SF__guid_
0x140011f23  nop
0x140011f24  mov     ecx, esi
0x140011f26  add     rcx, [rsp+0A8h+arg_10]
0x140011f2e  mov     edx, [rsp+0A8h+var_68]
0x140011f32  call    RtlWriteULongToUser
0x140011f37  add     esi, 4
0x140011f3a  mov     [rsp+0A8h+var_6C], esi
0x140011f3e  mov     r8d, esi
0x140011f41  mov     eax, dword ptr [rsp+0A8h+var_58]
0x140011f45  mov     [rsp+0A8h+var_58], rax
0x140011f4a  add     r8, [rsp+0A8h+arg_10]
0x140011f52  mov     edx, [r14+10h]
0x140011f56  lea     rcx, [rsp+0A8h+var_48]
0x140011f5b  mov     [rsp+0A8h+var_80], rcx
0x140011f60  mov     [rsp+0A8h+var_88], rax
0x140011f65  mov     r9b, 1
0x140011f68  mov     rcx, [r14+8]
0x140011f6c  call    cs:__imp_RtlCopyMdlToBufferToMode
0x140011f73  nop     dword ptr [rax+rax+00h]
0x140011f78  nop
0x140011f79  mov     rax, [rsp+0A8h+var_58]
0x140011f7e  cmp     rax, [rsp+0A8h+var_48]
0x140011f83  jnz     loc_140011EAE
0x140011f89  add     esi, dword ptr [rsp+0A8h+var_48]
0x140011f8d  mov     [rsp+0A8h+var_6C], esi
0x140011f91  jmp     loc_140011EAE
0x140011f96  lea     rax, WPP_GLOBAL_Control
0x140011f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011fa4  cmp     rcx, rax
0x140011fa7  jz      short loc_140011FD7
0x140011fa9  mov     eax, [rcx+2Ch]
0x140011fac  test    al, 2
0x140011fae  jz      short loc_140011FD7
0x140011fb0  cmp     byte ptr [rcx+29h], 1
0x140011fb4  jb      short loc_140011FD7
0x140011fb6  mov     r9, [rsp+0A8h+var_78]
0x140011fbb  add     r9, 1E4h
0x140011fc2  mov     edx, 3Fh ; '?'
0x140011fc7  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011fce  mov     rcx, [rcx+18h]
0x140011fd2  call    WPP_SF__guid_
0x140011fd7  mov     rbx, [rsp+0A8h+arg_0]
0x140011fdf  mov     dword ptr [rbx], 0C000000Dh
0x140011fe5  mov     qword ptr [rbx+8], 0
0x140011fed  mov     rcx, [rsp+0A8h+var_78]
0x140011ff2  add     rcx, 20h ; ' '; SpinLock
0x140011ff6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011ffd  nop     dword ptr [rax+rax+00h]
0x140012002  mov     r14b, al
0x140012005  mov     rax, [rsp+0A8h+var_78]
0x14001200a  mov     rcx, [rax+60h]
0x14001200e  mov     rdx, [rsp+0A8h+var_40]
0x140012013  mov     [rdx], rcx
0x140012016  mov     rax, [rsp+0A8h+var_78]
0x14001201b  mov     [rax+60h], rdx
0x14001201f  lea     r13, WPP_GLOBAL_Control
0x140012026  mov     edx, 4
0x14001202b  mov     esi, [rsp+0A8h+var_6C]
0x14001202f  mov     r15, [rsp+0A8h+NetBufferLists]
0x140012034  mov     r12d, [rsp+0A8h+var_70]
0x140012039  jmp     loc_140011E58
0x14001203e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012045  cmp     rcx, r13
  ... truncated ...
```
