# NatCreateAddressPool

- ea: `0x1400128ec`
- end: `0x140013084`
- name: `NatCreateAddressPool`
- size: `1944`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000bed0`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140010ce4`
- `0x1400128ec`
- `0x14001308c`
- `0x140013550`
- `0x14001379c`

## import_xrefs

- `ntoskrnl!RtlClearAllBits` at `0x140012ce1`
- `ntoskrnl!RtlClearAllBits` at `0x140012ce1`
- `ntoskrnl!ExAllocatePool2` at `0x140012970`
- `ntoskrnl!ExAllocatePool2` at `0x140012b59`
- `ntoskrnl!ExAllocatePool2` at `0x140012caf`
- `ntoskrnl!ExAllocatePool2` at `0x140012970`
- `ntoskrnl!ExAllocatePool2` at `0x140012b59`
- `ntoskrnl!ExAllocatePool2` at `0x140012caf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012bff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012bff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e1d`

## pseudocode

```c
__int64 __fastcall NatCreateAddressPool(__int64 a1)
{
  __int64 v2; // rcx
  _QWORD *Pool2; // rdi
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  __int64 i; // r8
  char v7; // si
  unsigned int v8; // r9d
  __int64 v9; // rbp
  __int64 v10; // rdx
  unsigned int *v11; // r11
  unsigned __int32 v12; // r8d
  unsigned int *v13; // rcx
  _DWORD *v14; // rsi
  unsigned int v15; // ebp
  __int64 v16; // r14
  __int64 v17; // r13
  unsigned int v18; // r8d
  unsigned __int32 v19; // ecx
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rdi
  unsigned __int32 v23; // r15d
  __int64 v24; // rax
  __int64 v25; // rsi
  int AddressPoolEntry; // edi
  int v27; // r8d
  __int64 v29; // rsi
  __int64 v30; // rbp
  int v31; // esi
  unsigned int v32; // [rsp+80h] [rbp+8h]
  __int64 v33; // [rsp+88h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
  }
  v2 = *(unsigned int *)(a1 + 60);
  v33 = 0;
  if ( (unsigned int)v2 > 1 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 8 * v2, 1095917902);
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          v5 = 51;
          goto LABEL_78;
        }
      }
      return 3221225495LL;
    }
    LODWORD(v2) = *(_DWORD *)(a1 + 60);
    for ( i = 0; (unsigned int)i < (unsigned int)v2; LODWORD(v2) = *(_DWORD *)(a1 + 60) )
    {
      Pool2[i] = *(_QWORD *)(a1 + 64) + 12 * i;
      i = (unsigned int)(i + 1);
    }
    do
    {
      if ( (_DWORD)v2 == 1 )
        break;
      v7 = 0;
      v8 = 0;
      do
      {
        v9 = v8;
        v10 = ++v8;
        v11 = (unsigned int *)Pool2[v9];
        v12 = _byteswap_ulong(*v11);
        while ( (unsigned int)v10 < (unsigned int)v2 )
        {
          v13 = (unsigned int *)Pool2[v10];
          if ( v12 > _byteswap_ulong(*v13) )
          {
            Pool2[v9] = v13;
            v7 = 1;
            Pool2[v10] = v11;
            v11 = v13;
            v12 = _byteswap_ulong(*v13);
          }
          LODWORD(v2) = *(_DWORD *)(a1 + 60);
          v10 = (unsigned int)(v10 + 1);
        }
      }
      while ( v8 < (int)v2 - 1 );
    }
    while ( v7 );
  }
  else
  {
    Pool2 = (_QWORD *)(a1 + 64);
  }
  if ( (_DWORD)v2 )
  {
    v14 = (_DWORD *)ExAllocatePool2(64, 24LL * (unsigned int)v2, 1296458062);
    if ( !v14 )
    {
      ExFreePoolWithTag(Pool2, 0);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v5 = 52;
        goto LABEL_78;
      }
      return 3221225495LL;
    }
  }
  else
  {
    v14 = 0;
  }
  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( !*(_DWORD *)(a1 + 60) )
    goto LABEL_59;
  do
  {
    v18 = _byteswap_ulong(*(_DWORD *)Pool2[v16]);
    v32 = v18;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, v15);
      v18 = v32;
    }
    if ( !v15 )
      goto LABEL_46;
    v19 = _byteswap_ulong(v14[6 * v17 + 1]);
    if ( v18 > v19 + 1 )
    {
      v17 = (unsigned int)(v17 + 1);
LABEL_46:
      v20 = 3 * v17;
      ++v15;
      v14[2 * v20] = *(_DWORD *)Pool2[v16];
      v14[2 * v20 + 1] = *(_DWORD *)(Pool2[v16] + 4LL);
      v14[2 * v20 + 2] = *(_DWORD *)(Pool2[v16] + 8LL);
      goto LABEL_47;
    }
    if ( v19 < _byteswap_ulong(*(_DWORD *)(Pool2[v16] + 4LL)) )
      v14[6 * v17 + 1] = *(_DWORD *)(Pool2[v16] + 4LL);
    if ( _byteswap_ulong(v14[6 * v17 + 2]) < _byteswap_ulong(*(_DWORD *)(Pool2[v16] + 8LL)) )
      v14[6 * v17 + 2] = *(_DWORD *)(Pool2[v16] + 8LL);
LABEL_47:
    v21 = *(_DWORD *)(a1 + 60);
    v16 = (unsigned int)(v16 + 1);
  }
  while ( (unsigned int)v16 < v21 );
  if ( v21 > 1 )
    ExFreePoolWithTag(Pool2, 0);
  v22 = 0;
  if ( v15 )
  {
    while ( 1 )
    {
      v23 = _byteswap_ulong(v14[6 * v22 + 1]) + 1 - _byteswap_ulong(v14[6 * v22]);
      if ( v23 >= 0x10000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, v23);
        }
        v23 = 0x10000;
        v14[6 * v22 + 1] = _byteswap_ulong(_byteswap_ulong(v14[6 * v22]) + 0x10000);
      }
      v24 = ExAllocatePool2(64, 8 * (((unsigned __int64)v23 + 31) >> 2) + 16, 1296195918);
      *(_QWORD *)&v14[6 * v22 + 4] = v24;
      if ( !v24 )
        break;
      *(_QWORD *)(v24 + 8) = v24 + 16;
      **(_DWORD **)&v14[6 * v22 + 4] = v23;
      RtlClearAllBits(*(PRTL_BITMAP *)&v14[6 * v22 + 4]);
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= v15 )
        goto LABEL_59;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 3221225495LL);
    }
    while ( 1 )
    {
      v22 = (unsigned int)(v22 - 1);
      if ( (int)v22 < 0 )
        break;
      ExFreePoolWithTag(*(PVOID *)&v14[6 * v22 + 4], 0);
    }
    ExFreePoolWithTag(v14, 0);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v5 = 56;
LABEL_78:
      WPP_SF_d(v4->AttachedDevice, v5, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 3221225495LL);
    }
    return 3221225495LL;
  }
LABEL_59:
  *(_QWORD *)(a1 + 136) = v14;
  v25 = 0;
  *(_DWORD *)(a1 + 132) = v15;
  AddressPoolEntry = 0;
  if ( *(_DWORD *)(a1 + 112) )
  {
    while ( 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_dddd(
          WPP_GLOBAL_Control->AttachedDevice,
          57,
          WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
          (unsigned __int8)*(_DWORD *)(*(_QWORD *)(a1 + 120) + 8 * v25),
          *(unsigned __int8 *)(*(_QWORD *)(a1 + 120) + 8 * v25 + 1),
          *(unsigned __int8 *)(*(_QWORD *)(a1 + 120) + 8 * v25 + 2),
          HIBYTE(*(_DWORD *)(*(_QWORD *)(a1 + 120) + 8 * v25)));
      }
      v27 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 8 * v25);
      AddressPoolEntry = NatCreateAddressPoolEntry(a1, v27, v27, 8, 0, (__int64)&v33);
      if ( AddressPoolEntry < 0 )
        break;
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= *(_DWORD *)(a1 + 112) )
        goto LABEL_84;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        58,
        WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
        (unsigned int)AddressPoolEntry);
    }
  }
LABEL_84:
  v29 = 0;
  if ( *(_DWORD *)(a1 + 88) )
  {
    while ( 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_dddd(
          WPP_GLOBAL_Control->AttachedDevice,
          59,
          WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
          (unsigned __int8)*(_DWORD *)(*(_QWORD *)(a1 + 96) + 12 * v29),
          *(unsigned __int8 *)(*(_QWORD *)(a1 + 96) + 12 * v29 + 1),
          *(unsigned __int8 *)(*(_QWORD *)(a1 + 96) + 12 * v29 + 2),
          HIBYTE(*(_DWORD *)(*(_QWORD *)(a1 + 96) + 12 * v29)));
      }
      v30 = 3 * v29;
      AddressPoolEntry = NatCreateAddressPoolEntry(
                           a1,
                           *(_DWORD *)(*(_QWORD *)(a1 + 96) + 12 * v29),
                           *(_DWORD *)(*(_QWORD *)(a1 + 96) + 12 * v29 + 4),
                           1,
                           0,
                           (__int64)&v33);
      if ( AddressPoolEntry < 0 )
        break;
      v29 = (unsigned int)(v29 + 1);
      *(_QWORD *)(v33 + 64) = *(_QWORD *)(a1 + 96) + 4 * v30;
      if ( (unsigned int)v29 >= *(_DWORD *)(a1 + 88) )
        goto LABEL_96;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        60,
        WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
        (unsigned int)AddressPoolEntry);
    }
  }
LABEL_96:
  v31 = *(_DWORD *)(a1 + 72);
  if ( v31 )
  {
    while ( 1 )
    {
      AddressPoolEntry = NatCreateStaticPortMapping(a1, *(_QWORD *)(a1 + 80) + 16LL * (unsigned int)--v31);
      if ( AddressPoolEntry < 0 )
        break;
      if ( !v31 )
        goto LABEL_99;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        61,
        WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
        (unsigned int)AddressPoolEntry);
    }
LABEL_109:
    NatDeleteAddressPool(a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        62,
        WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
        (unsigned int)AddressPoolEntry);
    }
    return (unsigned int)AddressPoolEntry;
  }
  else
  {
    if ( AddressPoolEntry < 0 )
      goto LABEL_109;
LABEL_99:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 0);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400128ec  mov     [rsp+arg_10], rbx
0x1400128f1  push    rbp
0x1400128f2  push    rsi
0x1400128f3  push    rdi
0x1400128f4  push    r12
0x1400128f6  push    r13
0x1400128f8  push    r14
0x1400128fa  push    r15
0x1400128fc  sub     rsp, 40h
0x140012900  mov     rbx, rcx
0x140012903  mov     rcx, cs:WPP_GLOBAL_Control
0x14001290a  lea     rbp, WPP_GLOBAL_Control
0x140012911  lea     r14, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140012918  mov     r15d, 1
0x14001291e  cmp     rcx, rbp
0x140012921  jz      short loc_140012941
0x140012923  mov     eax, [rcx+2Ch]
0x140012926  test    r15b, al
0x140012929  jz      short loc_140012941
0x14001292b  cmp     byte ptr [rcx+29h], 6
0x14001292f  jb      short loc_140012941
0x140012931  mov     rcx, [rcx+18h]
0x140012935  lea     edx, [r15+30h]
0x140012939  mov     r8, r14
0x14001293c  call    WPP_SF_
0x140012941  mov     ecx, [rbx+3Ch]
0x140012944  mov     [rsp+78h+arg_8], 0
0x140012950  cmp     ecx, r15d
0x140012953  ja      short loc_14001295E
0x140012955  lea     rdi, [rbx+40h]
0x140012959  jmp     loc_140012A6E
0x14001295e  mov     rdx, rcx
0x140012961  mov     r8d, 4152614Eh
0x140012967  shl     rdx, 3
0x14001296b  mov     ecx, 40h ; '@'
0x140012970  call    cs:__imp_ExAllocatePool2
0x140012977  nop     dword ptr [rax+rax+00h]
0x14001297c  mov     rdi, rax
0x14001297f  test    rax, rax
0x140012982  jnz     short loc_1400129E7
0x140012984  mov     rcx, cs:WPP_GLOBAL_Control
0x14001298b  cmp     rcx, rbp
0x14001298e  jz      loc_140012E5E
0x140012994  mov     eax, [rcx+2Ch]
0x140012997  test    r15b, al
0x14001299a  jz      short loc_1400129B4
0x14001299c  mov     r12b, 2
0x14001299f  cmp     [rcx+29h], r12b
0x1400129a3  jb      short loc_1400129B4
0x1400129a5  mov     rcx, [rcx+18h]
0x1400129a9  lea     edx, [rdi+32h]
0x1400129ac  mov     r8, r14
0x1400129af  call    WPP_SF_
0x1400129b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129bb  cmp     rcx, rbp
0x1400129be  jz      loc_140012E5E
0x1400129c4  mov     eax, [rcx+2Ch]
0x1400129c7  test    r15b, al
0x1400129ca  jz      loc_140012E5E
0x1400129d0  cmp     byte ptr [rcx+29h], 6
0x1400129d4  jb      loc_140012E5E
0x1400129da  mov     edx, 33h ; '3'
0x1400129df  mov     r8, r14
0x1400129e2  jmp     loc_140012E4F
0x1400129e7  mov     ecx, [rbx+3Ch]
0x1400129ea  xor     r8d, r8d
0x1400129ed  test    ecx, ecx
0x1400129ef  jz      short loc_140012A0C
0x1400129f1  mov     rax, [rbx+40h]
0x1400129f5  lea     rcx, [r8+r8*2]
0x1400129f9  lea     rcx, [rax+rcx*4]
0x1400129fd  mov     [rdi+r8*8], rcx
0x140012a01  add     r8d, r15d
0x140012a04  mov     ecx, [rbx+3Ch]
0x140012a07  cmp     r8d, ecx
0x140012a0a  jb      short loc_1400129F1
0x140012a0c  lea     eax, [rcx-1]
0x140012a0f  test    eax, eax
0x140012a11  jz      short loc_140012A67
0x140012a13  xor     sil, sil
0x140012a16  xor     r9d, r9d
0x140012a19  mov     ebp, r9d
0x140012a1c  lea     edx, [r9+1]
0x140012a20  mov     r9d, edx
0x140012a23  mov     r11, [rdi+rbp*8]
0x140012a27  mov     r8d, [r11]
0x140012a2a  bswap   r8d
0x140012a2d  jmp     short loc_140012A56
0x140012a2f  mov     rcx, [rdi+rdx*8]
0x140012a33  mov     eax, [rcx]
0x140012a35  bswap   eax
0x140012a37  cmp     r8d, eax
0x140012a3a  jbe     short loc_140012A50
0x140012a3c  mov     [rdi+rbp*8], rcx
0x140012a40  mov     sil, r15b
0x140012a43  mov     [rdi+rdx*8], r11
0x140012a47  mov     r11, rcx
0x140012a4a  mov     r8d, [rcx]
0x140012a4d  bswap   r8d
0x140012a50  mov     ecx, [rbx+3Ch]
0x140012a53  add     edx, r15d
0x140012a56  cmp     edx, ecx
0x140012a58  jb      short loc_140012A2F
0x140012a5a  lea     eax, [rcx-1]
0x140012a5d  cmp     r9d, eax
0x140012a60  jb      short loc_140012A19
0x140012a62  test    sil, sil
0x140012a65  jnz     short loc_140012A0C
0x140012a67  lea     rbp, WPP_GLOBAL_Control
0x140012a6e  test    ecx, ecx
0x140012a70  jnz     loc_140012B44
0x140012a76  xor     esi, esi
0x140012a78  xor     ebp, ebp
0x140012a7a  xor     r14d, r14d
0x140012a7d  xor     r13d, r13d
0x140012a80  mov     r12b, 2
0x140012a83  cmp     [rbx+3Ch], ebp
0x140012a86  jbe     loc_140012CFE
0x140012a8c  lea     r12, WPP_GLOBAL_Control
0x140012a93  mov     rax, [rdi+r14*8]
0x140012a97  mov     r8d, [rax]
0x140012a9a  bswap   r8d
0x140012a9d  mov     [rsp+78h+arg_0], r8d
0x140012aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140012aac  cmp     rcx, r12
0x140012aaf  jz      short loc_140012ADE
0x140012ab1  mov     eax, [rcx+2Ch]
0x140012ab4  test    al, 1
0x140012ab6  jz      short loc_140012ADE
0x140012ab8  cmp     byte ptr [rcx+29h], 5
0x140012abc  jb      short loc_140012ADE
0x140012abe  mov     rcx, [rcx+18h]
0x140012ac2  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140012ac9  mov     edx, 35h ; '5'
0x140012ace  mov     r9d, ebp
0x140012ad1  call    WPP_SF_d
0x140012ad6  mov     r8d, [rsp+78h+arg_0]
0x140012ade  test    ebp, ebp
0x140012ae0  jz      loc_140012BB3
0x140012ae6  lea     rdx, ds:0[r13*2]
0x140012aee  add     rdx, r13
0x140012af1  mov     ecx, [rsi+rdx*8+4]
0x140012af5  bswap   ecx
0x140012af7  lea     eax, [rcx+1]
0x140012afa  cmp     r8d, eax
0x140012afd  ja      loc_140012BB0
0x140012b03  mov     rax, [rdi+r14*8]
0x140012b07  mov     r8d, [rax+4]
0x140012b0b  mov     eax, r8d
0x140012b0e  bswap   eax
0x140012b10  cmp     ecx, eax
0x140012b12  jnb     short loc_140012B19
0x140012b14  mov     [rsi+rdx*8+4], r8d
0x140012b19  mov     rax, [rdi+r14*8]
0x140012b1d  mov     r15d, 1
0x140012b23  mov     r8d, [rax+8]
0x140012b27  mov     ecx, r8d
0x140012b2a  mov     eax, [rsi+rdx*8+8]
0x140012b2e  bswap   ecx
0x140012b30  bswap   eax
0x140012b32  cmp     eax, ecx
0x140012b34  jnb     loc_140012BE6
0x140012b3a  mov     [rsi+rdx*8+8], r8d
0x140012b3f  jmp     loc_140012BE6
0x140012b44  mov     eax, ecx
0x140012b46  mov     r8d, 4D46614Eh
0x140012b4c  mov     ecx, 40h ; '@'
0x140012b51  lea     rdx, [rax+rax*2]
0x140012b55  shl     rdx, 3
0x140012b59  call    cs:__imp_ExAllocatePool2
0x140012b60  nop     dword ptr [rax+rax+00h]
0x140012b65  mov     rsi, rax
0x140012b68  test    rax, rax
0x140012b6b  jnz     loc_140012A78
0x140012b71  xor     edx, edx; Tag
0x140012b73  mov     rcx, rdi; P
0x140012b76  call    cs:__imp_ExFreePoolWithTag
0x140012b7d  nop     dword ptr [rax+rax+00h]
0x140012b82  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b89  cmp     rcx, rbp
0x140012b8c  jz      loc_140012E5E
0x140012b92  mov     eax, [rcx+2Ch]
0x140012b95  test    r15b, al
0x140012b98  jz      loc_140012E5E
0x140012b9e  cmp     byte ptr [rcx+29h], 6
0x140012ba2  jb      loc_140012E5E
0x140012ba8  lea     edx, [rsi+34h]
0x140012bab  jmp     loc_1400129DF
0x140012bb0  inc     r13d
0x140012bb3  mov     rax, [rdi+r14*8]
0x140012bb7  lea     rdx, ds:0[r13*2]
0x140012bbf  add     rdx, r13
0x140012bc2  mov     r15d, 1
0x140012bc8  add     ebp, r15d
0x140012bcb  mov     ecx, [rax]
0x140012bcd  mov     [rsi+rdx*8], ecx
0x140012bd0  mov     rax, [rdi+r14*8]
0x140012bd4  mov     ecx, [rax+4]
0x140012bd7  mov     [rsi+rdx*8+4], ecx
0x140012bdb  mov     rax, [rdi+r14*8]
0x140012bdf  mov     ecx, [rax+8]
0x140012be2  mov     [rsi+rdx*8+8], ecx
0x140012be6  mov     eax, [rbx+3Ch]
0x140012be9  add     r14d, r15d
0x140012bec  cmp     r14d, eax
0x140012bef  jb      loc_140012A93
0x140012bf5  cmp     eax, r15d
0x140012bf8  jbe     short loc_140012C0B
0x140012bfa  xor     edx, edx; Tag
0x140012bfc  mov     rcx, rdi; P
0x140012bff  call    cs:__imp_ExFreePoolWithTag
0x140012c06  nop     dword ptr [rax+rax+00h]
0x140012c0b  xor     edi, edi
0x140012c0d  mov     r12b, 2
0x140012c10  test    ebp, ebp
0x140012c12  jz      loc_140012CFE
0x140012c18  lea     r14, [rdi+rdi*2]
0x140012c1c  mov     eax, [rsi+r14*8]
0x140012c20  bswap   eax
0x140012c22  sub     r15d, eax
0x140012c25  mov     eax, [rsi+r14*8+4]
0x140012c2a  bswap   eax
0x140012c2c  add     r15d, eax
0x140012c2f  cmp     r15d, 10000h
0x140012c36  jb      short loc_140012C8A
0x140012c38  mov     rcx, cs:WPP_GLOBAL_Control
0x140012c3f  lea     r13, WPP_GLOBAL_Control
0x140012c46  cmp     rcx, r13
0x140012c49  jz      short loc_140012C70
0x140012c4b  mov     eax, [rcx+2Ch]
0x140012c4e  test    al, 1
0x140012c50  jz      short loc_140012C70
0x140012c52  cmp     [rcx+29h], r12b
0x140012c56  jb      short loc_140012C70
0x140012c58  mov     rcx, [rcx+18h]
0x140012c5c  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140012c63  mov     edx, 36h ; '6'
0x140012c68  mov     r9d, r15d
0x140012c6b  call    WPP_SF_d
0x140012c70  mov     eax, [rsi+r14*8]
0x140012c74  mov     r15d, 10000h
0x140012c7a  bswap   eax
0x140012c7c  add     eax, 10000h
0x140012c81  bswap   eax
0x140012c83  mov     [rsi+r14*8+4], eax
0x140012c88  jmp     short loc_140012C91
0x140012c8a  lea     r13, WPP_GLOBAL_Control
0x140012c91  mov     edx, r15d
0x140012c94  mov     ecx, 40h ; '@'
0x140012c99  add     rdx, 1Fh
0x140012c9d  mov     r8d, 4D42614Eh
0x140012ca3  shr     rdx, 2
0x140012ca7  lea     rdx, ds:10h[rdx*8]
0x140012caf  call    cs:__imp_ExAllocatePool2
0x140012cb6  nop     dword ptr [rax+rax+00h]
0x140012cbb  mov     [rsi+r14*8+10h], rax
0x140012cc0  mov     rcx, rax
0x140012cc3  test    rax, rax
0x140012cc6  jz      loc_140012DC4
0x140012ccc  add     rax, 10h
0x140012cd0  mov     [rcx+8], rax
0x140012cd4  mov     rax, [rsi+r14*8+10h]
0x140012cd9  mov     [rax], r15d
0x140012cdc  mov     rcx, [rsi+r14*8+10h]; BitMapHeader
0x140012ce1  call    cs:__imp_RtlClearAllBits
0x140012ce8  nop     dword ptr [rax+rax+00h]
0x140012ced  mov     r15d, 1
0x140012cf3  add     edi, r15d
0x140012cf6  cmp     edi, ebp
0x140012cf8  jb      loc_140012C18
0x140012cfe  mov     [rbx+88h], rsi
0x140012d05  lea     r14, WPP_GLOBAL_Control
0x140012d0c  xor     esi, esi
0x140012d0e  mov     [rbx+84h], ebp
0x140012d14  xor     edi, edi
0x140012d16  cmp     [rbx+70h], esi
0x140012d19  jbe     loc_140012E9A
0x140012d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d26  cmp     rcx, r14
0x140012d29  jz      short loc_140012D7B
0x140012d2b  mov     eax, [rcx+2Ch]
0x140012d2e  test    r15b, al
0x140012d31  jz      short loc_140012D7B
0x140012d33  cmp     byte ptr [rcx+29h], 5
0x140012d37  jb      short loc_140012D7B
0x140012d39  mov     rax, [rbx+78h]
0x140012d3d  mov     rcx, [rcx+18h]
0x140012d41  mov     edx, [rax+rsi*8]
0x140012d44  mov     r11d, edx
0x140012d47  movzx   r8d, byte ptr [rax+rsi*8+2]
0x140012d4d  movzx   r10d, byte ptr [rax+rsi*8+1]
0x140012d53  shr     r11d, 18h
0x140012d57  mov     [rsp+78h+var_48], r11d
0x140012d5c  mov     dword ptr [rsp+78h+var_50], r8d
0x140012d61  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140012d68  movzx   r9d, dl
0x140012d6c  mov     edx, 39h ; '9'
0x140012d71  mov     dword ptr [rsp+78h+var_58], r10d
0x140012d76  call    WPP_SF_dddd
0x140012d7b  mov     rax, [rbx+78h]
  ... truncated ...
```
