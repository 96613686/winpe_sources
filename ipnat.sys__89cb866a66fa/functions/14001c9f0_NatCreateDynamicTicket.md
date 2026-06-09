# NatCreateDynamicTicket

- ea: `0x14001c9f0`
- end: `0x14001d055`
- name: `NatCreateDynamicTicket`
- size: `1637`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002b38`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14001c9f0`
- `0x14001df0c`
- `0x14001ecb0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001cee2`
- `ntoskrnl!ExAllocatePool2` at `0x14001cee2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cce1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cdce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ce68`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cefc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cffb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cce1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cdce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ce68`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cefc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cffb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ccb4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ccb4`

## pseudocode

```c
__int64 __fastcall NatCreateDynamicTicket(unsigned __int8 *a1, unsigned int a2, __int64 a3)
{
  int v6; // r11d
  int v7; // r14d
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // r8d
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // ebp
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  int v17; // r9d
  unsigned __int8 v18; // cl
  unsigned int v19; // esi
  KIRQL v20; // di
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned __int64 v23; // rdx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  __int64 Pool2; // rax
  _QWORD *v27; // r9
  __int64 v28; // r10
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  _QWORD *v32; // rcx
  __int64 v33; // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
  }
  v6 = *a1;
  v33 = 0;
  if ( (_BYTE)v6 != 6 && (_BYTE)v6 != 17 || (v7 = *((unsigned __int16 *)a1 + 1), !(_WORD)v7) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225485LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v9 = 12;
LABEL_70:
    WPP_SF_d(v8->AttachedDevice, v9, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    return 3221225485LL;
  }
  v10 = *((_DWORD *)a1 + 1);
  if ( v10 > 0x15555555 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225990LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225990LL);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225990LL;
    }
    v12 = 14;
LABEL_43:
    WPP_SF_d(v11->AttachedDevice, v12, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225990LL);
    return 3221225990LL;
  }
  v13 = 6 * v10 + 8;
  if ( v13 < 6 * v10 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225621LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225621LL);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225621LL;
    }
    v15 = 16;
LABEL_81:
    WPP_SF_d(v14->AttachedDevice, v15, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225621LL);
    return 3221225621LL;
  }
  if ( a2 < v13 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225990LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225990LL);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225990LL;
    }
    v12 = 18;
    goto LABEL_43;
  }
  v17 = 0;
  if ( v10 )
  {
    while ( 1 )
    {
      v18 = a1[6 * v17 + 8];
      if ( v18 != 6 && v18 != 17 )
        break;
      if ( !*(_WORD *)&a1[6 * v17 + 10]
        || !*(_WORD *)&a1[6 * v17 + 12]
        || _byteswap_ushort(*(_WORD *)&a1[6 * v17 + 10]) > _byteswap_ushort(*(_WORD *)&a1[6 * v17 + 12]) )
      {
        break;
      }
      if ( ++v17 >= v10 )
        goto LABEL_52;
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225485LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225485LL);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225485LL;
    }
    v9 = 20;
    goto LABEL_70;
  }
LABEL_52:
  v19 = v7 | (v6 << 16);
  v20 = KeAcquireSpinLockRaiseToDpc(&DynamicTicketLock);
  if ( NatLookupDynamicTicket(v19, &v33) )
  {
    KeReleaseSpinLock(&DynamicTicketLock, v20);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, v21, v22, v19);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225473LL);
      }
    }
    return 3221225473LL;
  }
  if ( v13 + 40 < v13 )
  {
    KeReleaseSpinLock(&DynamicTicketLock, v20);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225621LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225621LL);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225621LL;
    }
    v15 = 24;
    goto LABEL_81;
  }
  v23 = v13 + 40LL;
  if ( v23 > 0x7FFFFFFF )
  {
    KeReleaseSpinLock(&DynamicTicketLock, v20);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225495LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225495LL;
    }
    v25 = 26;
LABEL_101:
    WPP_SF_d(v24->AttachedDevice, v25, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225495LL);
    return 3221225495LL;
  }
  Pool2 = ExAllocatePool2(64, v23, 1413767502);
  v27 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    KeReleaseSpinLock(&DynamicTicketLock, v20);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 3221225495LL;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225495LL);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225495LL;
    }
    v25 = 28;
    goto LABEL_101;
  }
  *(_DWORD *)(Pool2 + 16) = v19;
  v28 = 0;
  *(_QWORD *)(Pool2 + 32) = a3;
  *(_DWORD *)(Pool2 + 20) = *((_DWORD *)a1 + 1);
  for ( *(_QWORD *)(Pool2 + 24) = Pool2 + 40;
        (unsigned int)v28 < *((_DWORD *)a1 + 1);
        *(_WORD *)(v27[3] + 2 * v29 + 4) = *(_WORD *)&a1[2 * v30 + 12] )
  {
    v29 = 3 * v28;
    *(_BYTE *)(v27[3] + 2 * v29) = a1[6 * v28 + 8];
    *(_WORD *)(v27[3] + 2 * v29 + 2) = *(_WORD *)&a1[6 * v28 + 10];
    v30 = 3 * v28;
    v28 = (unsigned int)(v28 + 1);
  }
  v31 = v33;
  v32 = *(_QWORD **)(v33 + 8);
  if ( *v32 != v33 )
    __fastfail(3u);
  v27[1] = v32;
  *v27 = v31;
  *v32 = v27;
  *(_QWORD *)(v31 + 8) = v27;
  KeReleaseSpinLock(&DynamicTicketLock, v20);
  _InterlockedAdd(&DynamicTicketCount, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001c9f0  push    rbx
0x14001c9f2  push    rbp
0x14001c9f3  push    rsi
0x14001c9f4  push    rdi
0x14001c9f5  push    r12
0x14001c9f7  push    r13
0x14001c9f9  push    r14
0x14001c9fb  push    r15
0x14001c9fd  sub     rsp, 38h
0x14001ca01  mov     r15, r8
0x14001ca04  mov     edi, edx
0x14001ca06  mov     rbx, rcx
0x14001ca09  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca10  lea     r13, WPP_GLOBAL_Control
0x14001ca17  lea     rsi, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001ca1e  mov     r12d, 1
0x14001ca24  cmp     rcx, r13
0x14001ca27  jz      short loc_14001CA48
0x14001ca29  mov     eax, [rcx+2Ch]
0x14001ca2c  test    r12b, al
0x14001ca2f  jz      short loc_14001CA48
0x14001ca31  cmp     byte ptr [rcx+29h], 6
0x14001ca35  jb      short loc_14001CA48
0x14001ca37  mov     rcx, [rcx+18h]
0x14001ca3b  lea     edx, [r12+9]
0x14001ca40  mov     r8, rsi
0x14001ca43  call    WPP_SF_
0x14001ca48  movzx   r11d, byte ptr [rbx]
0x14001ca4c  xor     edx, edx
0x14001ca4e  mov     [rsp+78h+arg_0], rdx
0x14001ca56  cmp     r11b, 6
0x14001ca5a  jz      short loc_14001CA62
0x14001ca5c  cmp     r11b, 11h
0x14001ca60  jnz     short loc_14001CA6D
0x14001ca62  movzx   r14d, word ptr [rbx+2]
0x14001ca67  test    r14w, r14w
0x14001ca6b  jnz     short loc_14001CAD2
0x14001ca6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca74  cmp     rcx, r13
0x14001ca77  jz      loc_14001CDB3
0x14001ca7d  mov     eax, [rcx+2Ch]
0x14001ca80  test    r12b, al
0x14001ca83  jz      short loc_14001CAA2
0x14001ca85  cmp     byte ptr [rcx+29h], 2
0x14001ca89  jb      short loc_14001CAA2
0x14001ca8b  mov     rcx, [rcx+18h]
0x14001ca8f  mov     edx, 0Bh
0x14001ca94  mov     r9d, 0C000000Dh
0x14001ca9a  mov     r8, rsi
0x14001ca9d  call    WPP_SF_d
0x14001caa2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001caa9  cmp     rcx, r13
0x14001caac  jz      loc_14001CDB3
0x14001cab2  mov     eax, [rcx+2Ch]
0x14001cab5  test    r12b, al
0x14001cab8  jz      loc_14001CDB3
0x14001cabe  cmp     byte ptr [rcx+29h], 6
0x14001cac2  jb      loc_14001CDB3
0x14001cac8  mov     edx, 0Ch
0x14001cacd  jmp     loc_14001CDA1
0x14001cad2  mov     r8d, [rbx+4]
0x14001cad6  cmp     r8d, 15555555h
0x14001cadd  jbe     short loc_14001CB44
0x14001cadf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cae6  cmp     rcx, r13
0x14001cae9  jz      loc_14001CC1F
0x14001caef  mov     eax, [rcx+2Ch]
0x14001caf2  test    r12b, al
0x14001caf5  jz      short loc_14001CB14
0x14001caf7  cmp     byte ptr [rcx+29h], 2
0x14001cafb  jb      short loc_14001CB14
0x14001cafd  mov     rcx, [rcx+18h]
0x14001cb01  mov     edx, 0Dh
0x14001cb06  mov     r9d, 0C0000206h
0x14001cb0c  mov     r8, rsi
0x14001cb0f  call    WPP_SF_d
0x14001cb14  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cb1b  cmp     rcx, r13
0x14001cb1e  jz      loc_14001CC1F
0x14001cb24  mov     eax, [rcx+2Ch]
0x14001cb27  test    r12b, al
0x14001cb2a  jz      loc_14001CC1F
0x14001cb30  cmp     byte ptr [rcx+29h], 6
0x14001cb34  jb      loc_14001CC1F
0x14001cb3a  mov     edx, 0Eh
0x14001cb3f  jmp     loc_14001CC0D
0x14001cb44  lea     eax, [r8+r8*2]
0x14001cb48  add     eax, eax
0x14001cb4a  lea     ebp, [rax+8]
0x14001cb4d  cmp     ebp, eax
0x14001cb4f  jnb     short loc_14001CBB9
0x14001cb51  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cb58  cmp     rcx, r13
0x14001cb5b  jz      loc_14001CE44
0x14001cb61  mov     eax, [rcx+2Ch]
0x14001cb64  test    r12b, al
0x14001cb67  jz      short loc_14001CB86
0x14001cb69  cmp     byte ptr [rcx+29h], 2
0x14001cb6d  jb      short loc_14001CB86
0x14001cb6f  mov     rcx, [rcx+18h]
0x14001cb73  mov     edx, 0Fh
0x14001cb78  mov     r9d, 0C0000095h
0x14001cb7e  mov     r8, rsi
0x14001cb81  call    WPP_SF_d
0x14001cb86  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cb8d  cmp     rcx, r13
0x14001cb90  jz      loc_14001CE44
0x14001cb96  mov     eax, [rcx+2Ch]
0x14001cb99  test    r12b, al
0x14001cb9c  jz      loc_14001CE44
0x14001cba2  cmp     byte ptr [rcx+29h], 6
0x14001cba6  jb      loc_14001CE44
0x14001cbac  mov     edx, 10h
0x14001cbb1  mov     r8, rsi
0x14001cbb4  jmp     loc_14001CE35
0x14001cbb9  cmp     edi, ebp
0x14001cbbb  jnb     short loc_14001CC29
0x14001cbbd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbc4  cmp     rcx, r13
0x14001cbc7  jz      short loc_14001CC1F
0x14001cbc9  mov     eax, [rcx+2Ch]
0x14001cbcc  test    r12b, al
0x14001cbcf  jz      short loc_14001CBEE
0x14001cbd1  cmp     byte ptr [rcx+29h], 2
0x14001cbd5  jb      short loc_14001CBEE
0x14001cbd7  mov     rcx, [rcx+18h]
0x14001cbdb  mov     edx, 11h
0x14001cbe0  mov     r9d, 0C0000206h
0x14001cbe6  mov     r8, rsi
0x14001cbe9  call    WPP_SF_d
0x14001cbee  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbf5  cmp     rcx, r13
0x14001cbf8  jz      short loc_14001CC1F
0x14001cbfa  mov     eax, [rcx+2Ch]
0x14001cbfd  test    r12b, al
0x14001cc00  jz      short loc_14001CC1F
0x14001cc02  cmp     byte ptr [rcx+29h], 6
0x14001cc06  jb      short loc_14001CC1F
0x14001cc08  mov     edx, 12h
0x14001cc0d  mov     rcx, [rcx+18h]
0x14001cc11  mov     r9d, 0C0000206h
0x14001cc17  mov     r8, rsi
0x14001cc1a  call    WPP_SF_d
0x14001cc1f  mov     eax, 0C0000206h
0x14001cc24  jmp     loc_14001D043
0x14001cc29  mov     r9d, edx
0x14001cc2c  test    r8d, r8d
0x14001cc2f  jz      short loc_14001CCA1
0x14001cc31  mov     eax, r9d
0x14001cc34  lea     r10, [rax+rax*2]
0x14001cc38  mov     cl, [rbx+r10*2+8]
0x14001cc3d  cmp     cl, 6
0x14001cc40  jz      short loc_14001CC4B
0x14001cc42  cmp     cl, 11h
0x14001cc45  jnz     loc_14001CD51
0x14001cc4b  cmp     [rbx+r10*2+0Ah], dx
0x14001cc51  jz      loc_14001CD51
0x14001cc57  lea     rcx, [rax+rax*2]
0x14001cc5b  cmp     [rbx+rcx*2+0Ch], dx
0x14001cc60  jz      loc_14001CD51
0x14001cc66  movzx   eax, byte ptr [rbx+rcx*2+0Ch]
0x14001cc6b  movzx   edx, byte ptr [rbx+r10*2+0Dh]
0x14001cc71  movzx   ecx, byte ptr [rbx+r10*2+0Ah]
0x14001cc77  shl     ax, 8
0x14001cc7b  or      dx, ax
0x14001cc7e  shl     cx, 8
0x14001cc82  movzx   eax, byte ptr [rbx+r10*2+0Bh]
0x14001cc88  or      cx, ax
0x14001cc8b  cmp     cx, dx
0x14001cc8e  ja      loc_14001CD51
0x14001cc94  add     r9d, r12d
0x14001cc97  mov     edx, 0
0x14001cc9c  cmp     r9d, r8d
0x14001cc9f  jb      short loc_14001CC31
0x14001cca1  mov     esi, r11d
0x14001cca4  shl     esi, 10h
0x14001cca7  or      esi, r14d
0x14001ccaa  lea     r14, DynamicTicketLock
0x14001ccb1  mov     rcx, r14; SpinLock
0x14001ccb4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ccbb  nop     dword ptr [rax+rax+00h]
0x14001ccc0  lea     rdx, [rsp+78h+arg_0]
0x14001ccc8  mov     ecx, esi
0x14001ccca  mov     dil, al
0x14001cccd  call    NatLookupDynamicTicket
0x14001ccd2  test    rax, rax
0x14001ccd5  jz      loc_14001CDBD
0x14001ccdb  mov     dl, dil; NewIrql
0x14001ccde  mov     rcx, r14; SpinLock
0x14001cce1  call    cs:__imp_KeReleaseSpinLock
0x14001cce8  nop     dword ptr [rax+rax+00h]
0x14001cced  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ccf4  mov     ebx, 0C0000001h
0x14001ccf9  cmp     rcx, r13
0x14001ccfc  jz      short loc_14001CD4A
0x14001ccfe  mov     eax, [rcx+2Ch]
0x14001cd01  test    r12b, al
0x14001cd04  jz      short loc_14001CD18
0x14001cd06  cmp     byte ptr [rcx+29h], 2
0x14001cd0a  jb      short loc_14001CD18
0x14001cd0c  mov     rcx, [rcx+18h]
0x14001cd10  mov     r9d, esi
0x14001cd13  call    WPP_SF_Dd
0x14001cd18  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd1f  cmp     rcx, r13
0x14001cd22  jz      short loc_14001CD4A
0x14001cd24  mov     edx, [rcx+2Ch]
0x14001cd27  test    r12b, dl
0x14001cd2a  jz      short loc_14001CD4A
0x14001cd2c  cmp     byte ptr [rcx+29h], 6
0x14001cd30  jb      short loc_14001CD4A
0x14001cd32  mov     rcx, [rcx+18h]
0x14001cd36  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001cd3d  mov     edx, 16h
0x14001cd42  mov     r9d, ebx
0x14001cd45  call    WPP_SF_d
0x14001cd4a  mov     eax, ebx
0x14001cd4c  jmp     loc_14001D043
0x14001cd51  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd58  cmp     rcx, r13
0x14001cd5b  jz      short loc_14001CDB3
0x14001cd5d  mov     eax, [rcx+2Ch]
0x14001cd60  test    r12b, al
0x14001cd63  jz      short loc_14001CD82
0x14001cd65  cmp     byte ptr [rcx+29h], 2
0x14001cd69  jb      short loc_14001CD82
0x14001cd6b  mov     rcx, [rcx+18h]
0x14001cd6f  mov     edx, 13h
0x14001cd74  mov     r9d, 0C000000Dh
0x14001cd7a  mov     r8, rsi
0x14001cd7d  call    WPP_SF_d
0x14001cd82  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd89  cmp     rcx, r13
0x14001cd8c  jz      short loc_14001CDB3
0x14001cd8e  mov     edx, [rcx+2Ch]
0x14001cd91  test    r12b, dl
0x14001cd94  jz      short loc_14001CDB3
0x14001cd96  cmp     byte ptr [rcx+29h], 6
0x14001cd9a  jb      short loc_14001CDB3
0x14001cd9c  mov     edx, 14h
0x14001cda1  mov     rcx, [rcx+18h]
0x14001cda5  mov     r9d, 0C000000Dh
0x14001cdab  mov     r8, rsi
0x14001cdae  call    WPP_SF_d
0x14001cdb3  mov     eax, 0C000000Dh
0x14001cdb8  jmp     loc_14001D043
0x14001cdbd  lea     eax, [rbp+28h]
0x14001cdc0  cmp     eax, ebp
0x14001cdc2  jnb     loc_14001CE4E
0x14001cdc8  mov     dl, dil; NewIrql
0x14001cdcb  mov     rcx, r14; SpinLock
0x14001cdce  call    cs:__imp_KeReleaseSpinLock
0x14001cdd5  nop     dword ptr [rax+rax+00h]
0x14001cdda  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cde1  cmp     rcx, r13
0x14001cde4  jz      short loc_14001CE44
0x14001cde6  mov     eax, [rcx+2Ch]
0x14001cde9  test    r12b, al
0x14001cdec  jz      short loc_14001CE0F
0x14001cdee  cmp     byte ptr [rcx+29h], 2
0x14001cdf2  jb      short loc_14001CE0F
0x14001cdf4  mov     rcx, [rcx+18h]
0x14001cdf8  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001cdff  mov     edx, 17h
0x14001ce04  mov     r9d, 0C0000095h
0x14001ce0a  call    WPP_SF_d
0x14001ce0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce16  cmp     rcx, r13
0x14001ce19  jz      short loc_14001CE44
0x14001ce1b  mov     edx, [rcx+2Ch]
0x14001ce1e  test    r12b, dl
0x14001ce21  jz      short loc_14001CE44
0x14001ce23  cmp     byte ptr [rcx+29h], 6
0x14001ce27  jb      short loc_14001CE44
0x14001ce29  mov     edx, 18h
0x14001ce2e  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001ce35  mov     rcx, [rcx+18h]
0x14001ce39  mov     r9d, 0C0000095h
0x14001ce3f  call    WPP_SF_d
0x14001ce44  mov     eax, 0C0000095h
0x14001ce49  jmp     loc_14001D043
0x14001ce4e  mov     edx, ebp
0x14001ce50  mov     ebp, 0C0000017h
0x14001ce55  add     rdx, 28h ; '('
0x14001ce59  cmp     rdx, 7FFFFFFFh
0x14001ce60  jbe     short loc_14001CED7
0x14001ce62  mov     dl, dil; NewIrql
0x14001ce65  mov     rcx, r14; SpinLock
0x14001ce68  call    cs:__imp_KeReleaseSpinLock
0x14001ce6f  nop     dword ptr [rax+rax+00h]
0x14001ce74  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce7b  cmp     rcx, r13
0x14001ce7e  jz      loc_14001CF6C
0x14001ce84  mov     eax, [rcx+2Ch]
0x14001ce87  test    r12b, al
0x14001ce8a  jz      short loc_14001CEA7
0x14001ce8c  cmp     byte ptr [rcx+29h], 2
0x14001ce90  jb      short loc_14001CEA7
0x14001ce92  mov     rcx, [rcx+18h]
0x14001ce96  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
  ... truncated ...
```
