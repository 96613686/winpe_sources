# ProcessMakeCallCompleteRequest

- ea: `0x140011500`
- end: `0x140011af9`
- name: `ProcessMakeCallCompleteRequest`
- size: `1529`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002060`

## callees

- `0x1400018b0`
- `0x140002030`
- `0x140002bd8`
- `0x140002c08`
- `0x140002f88`
- `0x140002fc4`
- `0x140003788`
- `0x140005ef0`
- `0x140011500`
- `0x140019e70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400115b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011674`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001196f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011a12`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400115b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011674`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001196f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011a12`
- `ntoskrnl!IofCompleteRequest` at `0x140011a9e`
- `ntoskrnl!IofCompleteRequest` at `0x140011a9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400115fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011660`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011916`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400115fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011660`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011916`
- `NETIO!HfGetPointerFromHandle32` at `0x1400115d8`
- `NETIO!HfGetPointerFromHandle32` at `0x1400115d8`

## pseudocode

```c
__int64 __fastcall ProcessMakeCallCompleteRequest(__int64 a1)
{
  int PointerFromHandle32; // r13d
  unsigned int *v3; // r12
  KIRQL v4; // di
  KIRQL v5; // al
  __int64 v6; // r8
  volatile signed __int32 *v7; // rcx
  volatile signed __int32 *v8; // rcx
  volatile signed __int32 *v9; // rax
  __int64 v10; // r8
  volatile signed __int32 *v11; // rdx
  char *v12; // r9
  KIRQL v13; // di
  __int64 v14; // r8
  KIRQL NewIrql; // [rsp+B8h] [rbp+48h]
  volatile signed __int32 *v18; // [rsp+C0h] [rbp+50h] BYREF

  v18 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 184) + 16LL) == 104 )
  {
    v3 = *(unsigned int **)(a1 + 24);
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 62);
    PointerFromHandle32 = HfGetPointerFromHandle32(*((_QWORD *)SstpGlobals + 63), *v3, &v18);
    if ( PointerFromHandle32 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v4);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)PointerFromHandle32;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
    else
    {
      _InterlockedIncrement(v18);
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v4);
      v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v18 + 4);
      NewIrql = v5;
      *((_DWORD *)v18 + 5272) &= ~0x2000u;
      *((_DWORD *)v18 + 29) = v3[1];
      v7 = v18;
      if ( *((_BYTE *)v18 + 21092) )
      {
        LOBYTE(v6) = v5;
        InitiateSstpContextCleanup((__int64)v18, 4, v6);
        DereferenceRefCount(v18);
        PointerFromHandle32 = -1073741823;
      }
      else
      {
        *(_QWORD *)(a1 + 120) = v18;
        *((_QWORD *)v7 + 8) = a1;
        *((_QWORD *)v18 + 2638) = *((_QWORD *)v3 + 1);
        *((_QWORD *)v18 + 2639) = *((_QWORD *)v3 + 2);
        *((_DWORD *)v18 + 5282) = v3[7];
        *((_DWORD *)v18 + 5272) |= 2u;
        v8 = v18;
        *(_OWORD *)((char *)v18 + 297) = *((_OWORD *)v3 + 2);
        *(volatile signed __int32 *)((char *)v8 + 313) = v3[12];
        v9 = v18;
        *(_OWORD *)((char *)v18 + 317) = *(_OWORD *)(v3 + 13);
        *(_OWORD *)((char *)v9 + 333) = *(_OWORD *)(v3 + 17);
        *(_OWORD *)(v18 + 121) = *(_OWORD *)(v3 + 22);
        *((_BYTE *)v18 + 296) = *((_BYTE *)v3 + 84);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_DDDDDDDDDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              69,
              *((unsigned __int8 *)v3 + 102),
              v3[22],
              *((_WORD *)v3 + 46),
              *((_WORD *)v3 + 47),
              *((_BYTE *)v3 + 96),
              *((_BYTE *)v3 + 97),
              *((_BYTE *)v3 + 98),
              *((_BYTE *)v3 + 99),
              *((_BYTE *)v3 + 100),
              *((_BYTE *)v3 + 101),
              *((_BYTE *)v3 + 102),
              *((_BYTE *)v3 + 103));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              WPP_SF_DDDDDDDDDDD(
                WPP_GLOBAL_Control->AttachedDevice,
                70,
                *((unsigned __int8 *)v18 + 498),
                *((_DWORD *)v18 + 121),
                *((_WORD *)v18 + 244),
                *((_WORD *)v18 + 245),
                *((_BYTE *)v18 + 492),
                *((_BYTE *)v18 + 493),
                *((_BYTE *)v18 + 494),
                *((_BYTE *)v18 + 495),
                *((_BYTE *)v18 + 496),
                *((_BYTE *)v18 + 497),
                *((_BYTE *)v18 + 498),
                *((_BYTE *)v18 + 499));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF__guid_(
                WPP_GLOBAL_Control->AttachedDevice,
                71,
                WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
                v18 + 121);
            }
          }
        }
        KeReleaseSpinLock((PKSPIN_LOCK)v18 + 4, NewIrql);
        if ( (unsigned __int8)SetCancelRoutineSafe(a1, &DispatchIncomingCallConnectedCancelIrp) )
        {
          v11 = v18 + 121;
          v12 = (char *)v18 + 297;
          LOBYTE(v11) = 1;
          LOBYTE(v12) = *((_BYTE *)v18 + 296);
          PointerFromHandle32 = (*((__int64 (__fastcall **)(volatile signed __int32 *, volatile signed __int32 *, __int64, char *, char *, char *, volatile signed __int32 *))SstpGlobals
                                 + 65))(
                                  v18,
                                  v11,
                                  1,
                                  v12,
                                  (char *)v18 + 297,
                                  (char *)v18 + 317,
                                  v18 + 121);
          if ( PointerFromHandle32 < 0 )
          {
            v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v18 + 4);
            *((_DWORD *)v18 + 5274) = PointerFromHandle32;
            *((_DWORD *)v18 + 5272) &= ~2u;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF__guid_D(
                WPP_GLOBAL_Control->AttachedDevice,
                73,
                WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
                v18 + 121,
                PointerFromHandle32);
            }
            LOBYTE(v14) = v13;
            InitiateSstpContextCleanup((__int64)v18, 4, v14);
            _InterlockedExchange64((volatile __int64 *)(a1 + 104), 0);
            *(_DWORD *)(a1 + 48) = PointerFromHandle32;
            *(_QWORD *)(a1 + 56) = 0;
            IofCompleteRequest((PIRP)a1, 0);
            PointerFromHandle32 = 259;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
          }
          LOBYTE(v10) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v18 + 4);
          *((_QWORD *)v18 + 8) = 0;
          *((_DWORD *)v18 + 5274) = -1073741536;
          InitiateSstpContextCleanup((__int64)v18, 4, v10);
          DereferenceRefCount(v18);
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
    PointerFromHandle32 = -1073741811;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  return (unsigned int)PointerFromHandle32;
}

```

## disassembly

```asm
0x140011500  mov     [rsp-38h+arg_18], rbx
0x140011505  mov     [rsp-38h+Irp], rcx
0x14001150a  push    rbp
0x14001150b  push    rsi
0x14001150c  push    rdi
0x14001150d  push    r12
0x14001150f  push    r13
0x140011511  push    r14
0x140011513  push    r15
0x140011515  mov     rbp, rsp
0x140011518  sub     rsp, 70h
0x14001151c  mov     rbx, rcx
0x14001151f  mov     [rbp+arg_10], 0
0x140011527  mov     rcx, cs:WPP_GLOBAL_Control
0x14001152e  lea     rsi, WPP_GLOBAL_Control
0x140011535  cmp     rcx, rsi
0x140011538  jz      short loc_14001155B
0x14001153a  mov     eax, [rcx+2Ch]
0x14001153d  and     eax, 82h
0x140011542  cmp     al, 82h
0x140011544  jnz     short loc_14001155B
0x140011546  mov     rcx, [rcx+18h]
0x14001154a  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011551  mov     edx, 42h ; 'B'
0x140011556  call    WPP_SF_
0x14001155b  mov     rax, [rbx+0B8h]
0x140011562  cmp     dword ptr [rax+10h], 68h ; 'h'
0x140011566  jz      short loc_1400115A1
0x140011568  mov     rcx, cs:WPP_GLOBAL_Control
0x14001156f  cmp     rcx, rsi
0x140011572  jz      short loc_140011596
0x140011574  mov     eax, [rcx+2Ch]
0x140011577  test    al, 2
0x140011579  jz      short loc_140011596
0x14001157b  cmp     byte ptr [rcx+29h], 1
0x14001157f  jb      short loc_140011596
0x140011581  mov     rcx, [rcx+18h]
0x140011585  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001158c  mov     edx, 43h ; 'C'
0x140011591  call    WPP_SF_
0x140011596  mov     r13d, 0C000000Dh
0x14001159c  jmp     loc_140011AB0
0x1400115a1  mov     rcx, cs:SstpGlobals
0x1400115a8  mov     r12, [rbx+18h]
0x1400115ac  add     rcx, 1F0h; SpinLock
0x1400115b3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400115ba  nop     dword ptr [rax+rax+00h]
0x1400115bf  mov     rcx, cs:SstpGlobals
0x1400115c6  lea     r8, [rbp+arg_10]
0x1400115ca  mov     edx, [r12]
0x1400115ce  mov     dil, al
0x1400115d1  mov     rcx, [rcx+1F8h]
0x1400115d8  call    cs:__imp_HfGetPointerFromHandle32
0x1400115df  nop     dword ptr [rax+rax+00h]
0x1400115e4  mov     r13d, eax
0x1400115e7  mov     dl, dil; NewIrql
0x1400115ea  test    eax, eax
0x1400115ec  jz      short loc_14001164B
0x1400115ee  mov     rcx, cs:SstpGlobals
0x1400115f5  add     rcx, 1F0h; SpinLock
0x1400115fc  call    cs:__imp_KeReleaseSpinLock
0x140011603  nop     dword ptr [rax+rax+00h]
0x140011608  mov     rcx, cs:WPP_GLOBAL_Control
0x14001160f  cmp     rcx, rsi
0x140011612  jz      loc_140011ADD
0x140011618  mov     edx, [rcx+2Ch]
0x14001161b  test    dl, 2
0x14001161e  jz      loc_140011AB0
0x140011624  cmp     byte ptr [rcx+29h], 1
0x140011628  jb      loc_140011AB0
0x14001162e  mov     rcx, [rcx+18h]
0x140011632  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011639  mov     edx, 44h ; 'D'
0x14001163e  mov     r9d, r13d
0x140011641  call    WPP_SF_d
0x140011646  jmp     loc_140011AB0
0x14001164b  mov     rax, [rbp+arg_10]
0x14001164f  lock inc dword ptr [rax]
0x140011652  mov     rcx, cs:SstpGlobals
0x140011659  add     rcx, 1F0h; SpinLock
0x140011660  call    cs:__imp_KeReleaseSpinLock
0x140011667  nop     dword ptr [rax+rax+00h]
0x14001166c  mov     rcx, [rbp+arg_10]
0x140011670  add     rcx, 20h ; ' '; SpinLock
0x140011674  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001167b  nop     dword ptr [rax+rax+00h]
0x140011680  mov     rcx, [rbp+arg_10]
0x140011684  mov     [rbp+NewIrql], al
0x140011687  btr     dword ptr [rcx+5260h], 0Dh
0x14001168f  mov     rcx, [rbp+arg_10]
0x140011693  mov     edx, [r12+4]
0x140011698  mov     [rcx+74h], edx
0x14001169b  mov     rcx, [rbp+arg_10]
0x14001169f  cmp     byte ptr [rcx+5264h], 0
0x1400116a6  jz      short loc_1400116C9
0x1400116a8  mov     r8b, al
0x1400116ab  mov     edx, 4
0x1400116b0  call    InitiateSstpContextCleanup
0x1400116b5  mov     rcx, [rbp+arg_10]
0x1400116b9  call    DereferenceRefCount
0x1400116be  mov     r13d, 0C0000001h
0x1400116c4  jmp     loc_140011AB0
0x1400116c9  mov     [rbx+78h], rcx
0x1400116cd  mov     [rcx+40h], rbx
0x1400116d1  mov     rax, [rbp+arg_10]
0x1400116d5  mov     rcx, [r12+8]
0x1400116da  mov     [rax+5270h], rcx
0x1400116e1  mov     rcx, [r12+10h]
0x1400116e6  mov     rax, [rbp+arg_10]
0x1400116ea  mov     [rax+5278h], rcx
0x1400116f1  mov     rax, [rbp+arg_10]
0x1400116f5  mov     ecx, [r12+1Ch]
0x1400116fa  mov     [rax+5288h], ecx
0x140011700  mov     rax, [rbp+arg_10]
0x140011704  or      dword ptr [rax+5260h], 2
0x14001170b  mov     rcx, [rbp+arg_10]
0x14001170f  movups  xmm0, xmmword ptr [r12+20h]
0x140011715  movups  xmmword ptr [rcx+129h], xmm0
0x14001171c  mov     eax, [r12+30h]
0x140011721  mov     [rcx+139h], eax
0x140011727  mov     rax, [rbp+arg_10]
0x14001172b  movups  xmm0, xmmword ptr [r12+34h]
0x140011731  movups  xmmword ptr [rax+13Dh], xmm0
0x140011738  movups  xmm1, xmmword ptr [r12+44h]
0x14001173e  movups  xmmword ptr [rax+14Dh], xmm1
0x140011745  mov     rax, [rbp+arg_10]
0x140011749  movups  xmm0, xmmword ptr [r12+58h]
0x14001174f  movdqu  xmmword ptr [rax+1E4h], xmm0
0x140011757  mov     rax, [rbp+arg_10]
0x14001175b  mov     cl, [r12+54h]
0x140011760  mov     [rax+128h], cl
0x140011766  mov     rcx, cs:WPP_GLOBAL_Control
0x14001176d  cmp     rcx, rsi
0x140011770  jz      loc_14001190B
0x140011776  mov     eax, [rcx+2Ch]
0x140011779  test    al, 2
0x14001177b  jz      loc_14001180F
0x140011781  cmp     byte ptr [rcx+29h], 3
0x140011785  jb      loc_14001180F
0x14001178b  movzx   r9d, byte ptr [r12+65h]
0x140011791  mov     edx, 45h ; 'E'
0x140011796  movzx   eax, byte ptr [r12+67h]
0x14001179c  movzx   r8d, byte ptr [r12+66h]
0x1400117a2  movzx   r10d, byte ptr [r12+64h]
0x1400117a8  movzx   r11d, byte ptr [r12+63h]
0x1400117ae  movzx   ebx, byte ptr [r12+62h]
0x1400117b4  movzx   edi, byte ptr [r12+61h]
0x1400117ba  movzx   esi, byte ptr [r12+60h]
0x1400117c0  movzx   r14d, word ptr [r12+5Eh]
0x1400117c6  movzx   r15d, word ptr [r12+5Ch]
0x1400117cc  mov     rcx, [rcx+18h]
0x1400117d0  mov     [rsp+70h+var_8], eax
0x1400117d4  mov     [rsp+70h+var_10], r8d
0x1400117d9  mov     [rsp+70h+var_18], r9d
0x1400117de  mov     r9d, [r12+58h]
0x1400117e3  mov     [rsp+70h+var_20], r10d
0x1400117e8  mov     [rsp+70h+var_28], r11d
0x1400117ed  mov     [rsp+70h+var_30], ebx
0x1400117f1  mov     [rsp+70h+var_38], edi
0x1400117f5  mov     dword ptr [rsp+70h+var_40], esi
0x1400117f9  mov     dword ptr [rsp+70h+var_48], r14d
0x1400117fe  mov     dword ptr [rsp+70h+var_50], r15d
0x140011803  call    WPP_SF_DDDDDDDDDDD
0x140011808  lea     rsi, WPP_GLOBAL_Control
0x14001180f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011816  cmp     rcx, rsi
0x140011819  jz      loc_14001190B
0x14001181f  mov     eax, [rcx+2Ch]
0x140011822  test    al, 2
0x140011824  jz      loc_1400118D2
0x14001182a  cmp     byte ptr [rcx+29h], 3
0x14001182e  jb      loc_1400118D2
0x140011834  mov     r9, [rbp+arg_10]
0x140011838  mov     edx, 46h ; 'F'
0x14001183d  mov     rcx, [rcx+18h]
0x140011841  movzx   eax, byte ptr [r9+1F3h]
0x140011849  movzx   r8d, byte ptr [r9+1F2h]
0x140011851  movzx   r10d, byte ptr [r9+1F1h]
0x140011859  movzx   r11d, byte ptr [r9+1F0h]
0x140011861  movzx   ebx, byte ptr [r9+1EFh]
0x140011869  movzx   edi, byte ptr [r9+1EEh]
0x140011871  movzx   esi, byte ptr [r9+1EDh]
0x140011879  movzx   r14d, byte ptr [r9+1ECh]
0x140011881  movzx   r15d, word ptr [r9+1EAh]
0x140011889  movzx   r12d, word ptr [r9+1E8h]
0x140011891  mov     r9d, [r9+1E4h]
0x140011898  mov     [rsp+70h+var_8], eax
0x14001189c  mov     [rsp+70h+var_10], r8d
0x1400118a1  mov     [rsp+70h+var_18], r10d
0x1400118a6  mov     [rsp+70h+var_20], r11d
0x1400118ab  mov     [rsp+70h+var_28], ebx
0x1400118af  mov     [rsp+70h+var_30], edi
0x1400118b3  mov     [rsp+70h+var_38], esi
0x1400118b7  mov     dword ptr [rsp+70h+var_40], r14d
0x1400118bc  mov     dword ptr [rsp+70h+var_48], r15d
0x1400118c1  mov     dword ptr [rsp+70h+var_50], r12d
0x1400118c6  call    WPP_SF_DDDDDDDDDDD
0x1400118cb  lea     rsi, WPP_GLOBAL_Control
0x1400118d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118d9  cmp     rcx, rsi
0x1400118dc  jz      short loc_14001190B
0x1400118de  mov     eax, [rcx+2Ch]
0x1400118e1  test    al, 2
0x1400118e3  jz      short loc_14001190B
0x1400118e5  cmp     byte ptr [rcx+29h], 3
0x1400118e9  jb      short loc_14001190B
0x1400118eb  mov     r9, [rbp+arg_10]
0x1400118ef  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400118f6  mov     rcx, [rcx+18h]
0x1400118fa  add     r9, 1E4h
0x140011901  mov     edx, 47h ; 'G'
0x140011906  call    WPP_SF__guid_
0x14001190b  mov     rcx, [rbp+arg_10]
0x14001190f  mov     dl, [rbp+NewIrql]; NewIrql
0x140011912  add     rcx, 20h ; ' '; SpinLock
0x140011916  call    cs:__imp_KeReleaseSpinLock
0x14001191d  nop     dword ptr [rax+rax+00h]
0x140011922  mov     rbx, [rbp+Irp]
0x140011926  lea     rdx, DispatchIncomingCallConnectedCancelIrp
0x14001192d  mov     rcx, rbx
0x140011930  call    SetCancelRoutineSafe
0x140011935  test    al, al
0x140011937  jnz     short loc_1400119B4
0x140011939  mov     rcx, cs:WPP_GLOBAL_Control
0x140011940  cmp     rcx, rsi
0x140011943  jz      short loc_140011967
0x140011945  mov     eax, [rcx+2Ch]
0x140011948  test    al, 2
0x14001194a  jz      short loc_140011967
0x14001194c  cmp     byte ptr [rcx+29h], 1
0x140011950  jb      short loc_140011967
0x140011952  mov     rcx, [rcx+18h]
0x140011956  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001195d  mov     edx, 48h ; 'H'
0x140011962  call    WPP_SF_
0x140011967  mov     rcx, [rbp+arg_10]
0x14001196b  add     rcx, 20h ; ' '; SpinLock
0x14001196f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011976  nop     dword ptr [rax+rax+00h]
0x14001197b  mov     rcx, [rbp+arg_10]
0x14001197f  mov     edx, 4
0x140011984  mov     r8b, al
0x140011987  mov     qword ptr [rcx+40h], 0
0x14001198f  mov     rcx, [rbp+arg_10]
0x140011993  mov     dword ptr [rcx+5268h], 0C0000120h
0x14001199d  mov     rcx, [rbp+arg_10]
0x1400119a1  call    InitiateSstpContextCleanup
0x1400119a6  mov     rcx, [rbp+arg_10]
0x1400119aa  call    DereferenceRefCount
0x1400119af  jmp     loc_140011AB0
0x1400119b4  mov     rcx, [rbp+arg_10]
0x1400119b8  mov     rax, cs:SstpGlobals
0x1400119bf  lea     rdx, [rcx+1E4h]
0x1400119c6  mov     rax, [rax+208h]
0x1400119cd  lea     r8, [rcx+13Dh]
0x1400119d4  mov     [rsp+70h+var_40], rdx
0x1400119d9  lea     r9, [rcx+129h]
0x1400119e0  mov     [rsp+70h+var_48], r8
0x1400119e5  mov     r8d, 1
0x1400119eb  mov     [rsp+70h+var_50], r9
0x1400119f0  mov     dl, r8b
0x1400119f3  mov     r9b, [rcx+128h]
0x1400119fa  call    _guard_dispatch_icall
0x1400119ff  mov     r13d, eax
0x140011a02  test    eax, eax
0x140011a04  jns     loc_140011AB0
0x140011a0a  mov     rcx, [rbp+arg_10]
0x140011a0e  add     rcx, 20h ; ' '; SpinLock
0x140011a12  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011a19  nop     dword ptr [rax+rax+00h]
0x140011a1e  mov     rcx, [rbp+arg_10]
0x140011a22  mov     dil, al
0x140011a25  mov     [rcx+5268h], r13d
0x140011a2c  mov     rcx, [rbp+arg_10]
0x140011a30  and     dword ptr [rcx+5260h], 0FFFFFFFDh
0x140011a37  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a3e  cmp     rcx, rsi
0x140011a41  jz      short loc_140011A76
0x140011a43  mov     edx, [rcx+2Ch]
0x140011a46  test    dl, 2
0x140011a49  jz      short loc_140011A76
0x140011a4b  cmp     byte ptr [rcx+29h], 1
0x140011a4f  jb      short loc_140011A76
0x140011a51  mov     r9, [rbp+arg_10]
0x140011a55  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011a5c  mov     rcx, [rcx+18h]
0x140011a60  add     r9, 1E4h
0x140011a67  mov     edx, 49h ; 'I'
0x140011a6c  mov     dword ptr [rsp+70h+var_50], r13d
0x140011a71  call    WPP_SF__guid_D
0x140011a76  mov     rcx, [rbp+arg_10]
0x140011a7a  mov     r8b, dil
0x140011a7d  mov     edx, 4
0x140011a82  call    InitiateSstpContextCleanup
0x140011a87  xor     eax, eax
0x140011a89  xor     edx, edx; PriorityBoost
0x140011a8b  xchg    rax, [rbx+68h]
0x140011a8f  mov     rcx, rbx; Irp
0x140011a92  mov     [rbx+30h], r13d
0x140011a96  mov     qword ptr [rbx+38h], 0
  ... truncated ...
```
