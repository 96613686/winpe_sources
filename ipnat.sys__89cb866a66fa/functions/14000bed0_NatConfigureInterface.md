# NatConfigureInterface

- ea: `0x14000bed0`
- end: `0x14000c494`
- name: `NatConfigureInterface`
- size: `1476`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002b38`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000bc50`
- `0x14000bed0`
- `0x14000ccc8`
- `0x14000d50c`
- `0x1400128ec`
- `0x14001c45c`
- `0x14002c8c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000c01f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000c01f`
- `ntoskrnl!ExAllocatePool2` at `0x14000bfb1`
- `ntoskrnl!ExAllocatePool2` at `0x14000bfb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c070`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c3f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c070`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c3f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c346`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c3e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c346`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c3e4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000c330`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000c330`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bfde`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bfde`

## pseudocode

```c
__int64 __fastcall NatConfigureInterface(_DWORD *Src, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // edi
  _DWORD *Pool2; // rax
  _DWORD *v11; // rsi
  KIRQL v12; // r12
  __int64 v13; // rax
  __int64 v14; // rbx
  int AddressPool; // edi
  KSPIN_LOCK *v16; // r15
  int v17; // ecx
  int v18; // eax
  void *v19; // rcx
  int v20; // r14d
  _DWORD *v21; // rsi
  int v22; // eax
  __int64 v23; // rax
  _DWORD *v24; // rax
  __int64 v25; // rax
  char *v26; // rcx
  int v27; // eax
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // rax
  char *v32; // rcx
  __int64 v33; // rax
  char *v34; // rax
  BOOL v35; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
  v4 = Src[3];
  v5 = v4 + 8;
  if ( v4 >= v4 + 8 )
  {
    v6 = -1073741675;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v6;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 3221225621LL);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v6;
    }
    v8 = 18;
LABEL_109:
    WPP_SF_d(v7->AttachedDevice, v8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, v6);
    return v6;
  }
  if ( v5 >= 0x7FFFFFFF || (v9 = v4 + 8, Pool2 = (_DWORD *)ExAllocatePool2(64, v5, 1131700558), (v11 = Pool2) == 0) )
  {
    v6 = -1073741801;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v6;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v6;
    }
    v8 = 20;
    goto LABEL_109;
  }
  memmove(Pool2, Src, v9);
  v12 = KeAcquireSpinLockRaiseToDpc(&InterfaceLock);
  v13 = NatLookupInterface((unsigned int)*Src, 0);
  v14 = v13;
  if ( !v13 || *(_QWORD *)(v13 + 40) != a2 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, 3221225485LL);
    }
    KeReleaseSpinLock(&InterfaceLock, v12);
    ExFreePoolWithTag(v11, 0);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v6;
    }
    v8 = 22;
    goto LABEL_109;
  }
  AddressPool = 0;
  if ( *(int *)(v13 + 56) >= 0 )
    _InterlockedAdd((volatile signed __int32 *)(v13 + 16), 1u);
  v16 = (KSPIN_LOCK *)(v13 + 24);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v13 + 24));
  NatResetInterface(v14);
  if ( (*(_DWORD *)(v14 + 56) & 0x10) != 0 )
    _InterlockedDecrement(&FirewalledInterfaceCount);
  v17 = *(_DWORD *)(v14 + 56);
  *(_DWORD *)(v14 + 56) = v17 & 0xFFFFFF80;
  v18 = v17 ^ (v11[1] ^ v17) & 0x7F;
  *(_DWORD *)(v14 + 56) = v18;
  if ( (v18 & 0x10) != 0 )
    _InterlockedAdd(&FirewalledInterfaceCount, 1u);
  v19 = *(void **)(v14 + 48);
  if ( v19 )
    ExFreePoolWithTag(v19, 0);
  *(_QWORD *)(v14 + 48) = v11;
  v20 = 0;
  v21 = v11 + 2;
  *(_DWORD *)(v14 + 60) = 0;
  *(_QWORD *)(v14 + 64) = 0;
  *(_DWORD *)(v14 + 88) = 0;
  *(_QWORD *)(v14 + 96) = 0;
  *(_DWORD *)(v14 + 72) = 0;
  *(_QWORD *)(v14 + 80) = 0;
  if ( v21[2] )
  {
    while ( 1 )
    {
      if ( AddressPool < 0 )
      {
LABEL_74:
        v16 = (KSPIN_LOCK *)(v14 + 24);
        break;
      }
      v22 = v21[4 * v20 + 3];
      if ( v22 == -65534 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
        }
        *(_DWORD *)(v14 + 60) = v21[4 * v20 + 5];
        v33 = (unsigned int)v21[4 * v20 + 6];
        if ( (unsigned int)v33 >= v21[1] )
          v34 = 0;
        else
          v34 = (char *)v21 + v33;
        *(_QWORD *)(v14 + 64) = v34;
        goto LABEL_73;
      }
      if ( v22 == -65533 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
        }
        *(_DWORD *)(v14 + 72) = v21[4 * v20 + 5];
        v31 = (unsigned int)v21[4 * v20 + 6];
        if ( (unsigned int)v31 >= v21[1] )
          v32 = 0;
        else
          v32 = (char *)v21 + v31;
        *(_QWORD *)(v14 + 80) = v32;
        AddressPool = ShellSort(
                        v32,
                        (unsigned int)v21[4 * v20 + 4],
                        (unsigned int)v21[4 * v20 + 5],
                        NatComparePortMappingCallback);
        if ( AddressPool >= 0 )
          goto LABEL_73;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_73;
        }
        v29 = 25;
        v30 = (unsigned int)AddressPool;
      }
      else
      {
        if ( v22 != -65532 )
        {
          if ( v22 == -65531 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
            }
            v23 = (unsigned int)v21[4 * v20 + 6];
            if ( (unsigned int)v23 >= v21[1] )
              v24 = 0;
            else
              v24 = (_DWORD *)((char *)v21 + v23);
            *(_DWORD *)(v14 + 104) = *v24;
          }
          goto LABEL_73;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
        }
        *(_DWORD *)(v14 + 88) = v21[4 * v20 + 5];
        v25 = (unsigned int)v21[4 * v20 + 6];
        if ( (unsigned int)v25 >= v21[1] )
          v26 = 0;
        else
          v26 = (char *)v21 + v25;
        *(_QWORD *)(v14 + 96) = v26;
        v27 = ShellSort(
                v26,
                (unsigned int)v21[4 * v20 + 4],
                (unsigned int)v21[4 * v20 + 5],
                NatCompareAddressMappingCallback);
        AddressPool = v27;
        if ( v27 >= 0 )
          goto LABEL_73;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_73;
        }
        v29 = 27;
        v30 = (unsigned int)v27;
      }
      WPP_SF_d(v28->AttachedDevice, v29, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, v30);
LABEL_73:
      if ( (unsigned int)++v20 >= v21[2] )
        goto LABEL_74;
    }
  }
  v35 = !*(_DWORD *)(v14 + 88) && !*(_DWORD *)(v14 + 72);
  _InterlockedExchange((volatile __int32 *)(v14 + 128), v35);
  if ( AddressPool < 0 )
    goto LABEL_85;
  AddressPool = NatCreateAddressPool(v14);
  if ( AddressPool < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        29,
        WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids,
        (unsigned int)AddressPool);
    }
LABEL_85:
    NatResetInterface(v14);
  }
  KeReleaseSpinLockFromDpcLevel(v16);
  KeReleaseSpinLock(&InterfaceLock, v12);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 16), 0xFFFFFFFF) == 1 )
    NatCleanupInterface((PVOID)v14);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      30,
      WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids,
      (unsigned int)AddressPool);
  }
  return (unsigned int)AddressPool;
}

```

## disassembly

```asm
0x14000bed0  push    rbx
0x14000bed2  push    rbp
0x14000bed3  push    rsi
0x14000bed4  push    rdi
0x14000bed5  push    r12
0x14000bed7  push    r13
0x14000bed9  push    r14
0x14000bedb  push    r15
0x14000bedd  sub     rsp, 38h
0x14000bee1  mov     rbp, rdx
0x14000bee4  mov     rbx, rcx
0x14000bee7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000beee  lea     r14, WPP_GLOBAL_Control
0x14000bef5  lea     r15, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000befc  mov     r13d, 1
0x14000bf02  cmp     rcx, r14
0x14000bf05  jz      short loc_14000BF25
0x14000bf07  mov     eax, [rcx+2Ch]
0x14000bf0a  test    r13b, al
0x14000bf0d  jz      short loc_14000BF25
0x14000bf0f  cmp     byte ptr [rcx+29h], 6
0x14000bf13  jb      short loc_14000BF25
0x14000bf15  mov     rcx, [rcx+18h]
0x14000bf19  lea     edx, [r13+0Fh]
0x14000bf1d  mov     r8, r15
0x14000bf20  call    WPP_SF_
0x14000bf25  mov     eax, [rbx+0Ch]
0x14000bf28  lea     ecx, [rax+8]
0x14000bf2b  cmp     eax, ecx
0x14000bf2d  jbe     short loc_14000BF96
0x14000bf2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf36  mov     ebx, 0C0000095h
0x14000bf3b  cmp     rcx, r14
0x14000bf3e  jz      loc_14000C480
0x14000bf44  mov     eax, [rcx+2Ch]
0x14000bf47  test    r13b, al
0x14000bf4a  jz      short loc_14000BF66
0x14000bf4c  cmp     byte ptr [rcx+29h], 2
0x14000bf50  jb      short loc_14000BF66
0x14000bf52  mov     rcx, [rcx+18h]
0x14000bf56  mov     edx, 11h
0x14000bf5b  mov     r9d, ebx
0x14000bf5e  mov     r8, r15
0x14000bf61  call    WPP_SF_d
0x14000bf66  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf6d  cmp     rcx, r14
0x14000bf70  jz      loc_14000C480
0x14000bf76  mov     edx, [rcx+2Ch]
0x14000bf79  test    r13b, dl
0x14000bf7c  jz      loc_14000C480
0x14000bf82  cmp     byte ptr [rcx+29h], 6
0x14000bf86  jb      loc_14000C480
0x14000bf8c  mov     edx, 12h
0x14000bf91  jmp     loc_14000C471
0x14000bf96  cmp     ecx, 7FFFFFFFh
0x14000bf9c  jnb     loc_14000C422
0x14000bfa2  mov     edi, ecx
0x14000bfa4  mov     r8d, 4374614Eh
0x14000bfaa  mov     edx, ecx
0x14000bfac  mov     ecx, 40h ; '@'
0x14000bfb1  call    cs:__imp_ExAllocatePool2
0x14000bfb8  nop     dword ptr [rax+rax+00h]
0x14000bfbd  mov     rsi, rax
0x14000bfc0  test    rax, rax
0x14000bfc3  jz      loc_14000C422
0x14000bfc9  mov     r8d, edi; Size
0x14000bfcc  mov     rdx, rbx; Src
0x14000bfcf  mov     rcx, rax; void *
0x14000bfd2  call    memmove
0x14000bfd7  lea     rcx, InterfaceLock; SpinLock
0x14000bfde  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bfe5  nop     dword ptr [rax+rax+00h]
0x14000bfea  mov     ecx, [rbx]
0x14000bfec  xor     edx, edx
0x14000bfee  mov     r12b, al
0x14000bff1  call    NatLookupInterface
0x14000bff6  mov     rbx, rax
0x14000bff9  test    rax, rax
0x14000bffc  jz      loc_14000C3A7
0x14000c002  cmp     [rax+28h], rbp
0x14000c006  jnz     loc_14000C3A7
0x14000c00c  xor     edi, edi
0x14000c00e  cmp     [rax+38h], edi
0x14000c011  jl      short loc_14000C018
0x14000c013  lock add [rax+10h], r13d
0x14000c018  lea     r15, [rax+18h]
0x14000c01c  mov     rcx, r15; SpinLock
0x14000c01f  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000c026  nop     dword ptr [rax+rax+00h]
0x14000c02b  mov     rcx, rbx
0x14000c02e  call    NatResetInterface
0x14000c033  mov     eax, [rbx+38h]
0x14000c036  test    al, 10h
0x14000c038  jz      short loc_14000C041
0x14000c03a  lock dec cs:FirewalledInterfaceCount
0x14000c041  mov     ecx, [rbx+38h]
0x14000c044  mov     eax, ecx
0x14000c046  and     eax, 0FFFFFF80h
0x14000c049  mov     [rbx+38h], eax
0x14000c04c  mov     eax, ecx
0x14000c04e  xor     eax, [rsi+4]
0x14000c051  and     eax, 7Fh
0x14000c054  xor     eax, ecx
0x14000c056  mov     [rbx+38h], eax
0x14000c059  test    al, 10h
0x14000c05b  jz      short loc_14000C065
0x14000c05d  lock add cs:FirewalledInterfaceCount, r13d
0x14000c065  mov     rcx, [rbx+30h]; P
0x14000c069  test    rcx, rcx
0x14000c06c  jz      short loc_14000C07C
0x14000c06e  xor     edx, edx; Tag
0x14000c070  call    cs:__imp_ExFreePoolWithTag
0x14000c077  nop     dword ptr [rax+rax+00h]
0x14000c07c  mov     [rbx+30h], rsi
0x14000c080  xor     r14d, r14d
0x14000c083  add     rsi, 8
0x14000c087  mov     [rbx+3Ch], edi
0x14000c08a  mov     [rbx+40h], rdi
0x14000c08e  mov     [rbx+58h], edi
0x14000c091  mov     [rbx+60h], rdi
0x14000c095  mov     [rbx+48h], edi
0x14000c098  mov     [rbx+50h], rdi
0x14000c09c  cmp     [rsi+8], edi
0x14000c09f  jbe     loc_14000C2C1
0x14000c0a5  lea     r15, WPP_GLOBAL_Control
0x14000c0ac  test    edi, edi
0x14000c0ae  js      loc_14000C2BD
0x14000c0b4  mov     ebp, r14d
0x14000c0b7  add     rbp, rbp
0x14000c0ba  mov     eax, [rsi+rbp*8+0Ch]
0x14000c0be  cmp     eax, 0FFFF0002h
0x14000c0c3  jz      loc_14000C266
0x14000c0c9  cmp     eax, 0FFFF0003h
0x14000c0ce  jz      loc_14000C1CC
0x14000c0d4  cmp     eax, 0FFFF0004h
0x14000c0d9  jz      short loc_14000C12F
0x14000c0db  cmp     eax, 0FFFF0005h
0x14000c0e0  jnz     loc_14000C2B0
0x14000c0e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c0ed  cmp     rcx, r15
0x14000c0f0  jz      short loc_14000C115
0x14000c0f2  mov     eax, [rcx+2Ch]
0x14000c0f5  test    r13b, al
0x14000c0f8  jz      short loc_14000C115
0x14000c0fa  cmp     byte ptr [rcx+29h], 5
0x14000c0fe  jb      short loc_14000C115
0x14000c100  mov     rcx, [rcx+18h]
0x14000c104  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c10b  mov     edx, 1Ch
0x14000c110  call    WPP_SF_
0x14000c115  mov     eax, [rsi+rbp*8+18h]
0x14000c119  cmp     eax, [rsi+4]
0x14000c11c  jnb     short loc_14000C123
0x14000c11e  add     rax, rsi
0x14000c121  jmp     short loc_14000C125
0x14000c123  xor     eax, eax
0x14000c125  mov     eax, [rax]
0x14000c127  mov     [rbx+68h], eax
0x14000c12a  jmp     loc_14000C2B0
0x14000c12f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c136  cmp     rcx, r15
0x14000c139  jz      short loc_14000C15E
0x14000c13b  mov     eax, [rcx+2Ch]
0x14000c13e  test    r13b, al
0x14000c141  jz      short loc_14000C15E
0x14000c143  cmp     byte ptr [rcx+29h], 5
0x14000c147  jb      short loc_14000C15E
0x14000c149  mov     rcx, [rcx+18h]
0x14000c14d  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c154  mov     edx, 1Ah
0x14000c159  call    WPP_SF_
0x14000c15e  mov     eax, [rsi+rbp*8+14h]
0x14000c162  mov     [rbx+58h], eax
0x14000c165  mov     eax, [rsi+rbp*8+18h]
0x14000c169  cmp     eax, [rsi+4]
0x14000c16c  jnb     short loc_14000C174
0x14000c16e  lea     rcx, [rsi+rax]
0x14000c172  jmp     short loc_14000C176
0x14000c174  xor     ecx, ecx
0x14000c176  mov     [rbx+60h], rcx
0x14000c17a  lea     r9, NatCompareAddressMappingCallback
0x14000c181  mov     r8d, [rsi+rbp*8+14h]
0x14000c186  mov     edx, [rsi+rbp*8+10h]
0x14000c18a  call    ShellSort
0x14000c18f  mov     edi, eax
0x14000c191  test    eax, eax
0x14000c193  jns     loc_14000C2B0
0x14000c199  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c1a0  cmp     rcx, r15
0x14000c1a3  jz      loc_14000C2B0
0x14000c1a9  mov     edx, [rcx+2Ch]
0x14000c1ac  test    r13b, dl
0x14000c1af  jz      loc_14000C2B0
0x14000c1b5  cmp     byte ptr [rcx+29h], 2
0x14000c1b9  jb      loc_14000C2B0
0x14000c1bf  mov     edx, 1Bh
0x14000c1c4  mov     r9d, eax
0x14000c1c7  jmp     loc_14000C254
0x14000c1cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c1d3  cmp     rcx, r15
0x14000c1d6  jz      short loc_14000C1FB
0x14000c1d8  mov     eax, [rcx+2Ch]
0x14000c1db  test    r13b, al
0x14000c1de  jz      short loc_14000C1FB
0x14000c1e0  cmp     byte ptr [rcx+29h], 5
0x14000c1e4  jb      short loc_14000C1FB
0x14000c1e6  mov     rcx, [rcx+18h]
0x14000c1ea  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c1f1  mov     edx, 18h
0x14000c1f6  call    WPP_SF_
0x14000c1fb  mov     eax, [rsi+rbp*8+14h]
0x14000c1ff  mov     [rbx+48h], eax
0x14000c202  mov     eax, [rsi+rbp*8+18h]
0x14000c206  cmp     eax, [rsi+4]
0x14000c209  jnb     short loc_14000C211
0x14000c20b  lea     rcx, [rsi+rax]
0x14000c20f  jmp     short loc_14000C213
0x14000c211  xor     ecx, ecx
0x14000c213  mov     [rbx+50h], rcx
0x14000c217  lea     r9, NatComparePortMappingCallback
0x14000c21e  mov     r8d, [rsi+rbp*8+14h]
0x14000c223  mov     edx, [rsi+rbp*8+10h]
0x14000c227  call    ShellSort
0x14000c22c  mov     edi, eax
0x14000c22e  test    eax, eax
0x14000c230  jns     short loc_14000C2B0
0x14000c232  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c239  cmp     rcx, r15
0x14000c23c  jz      short loc_14000C2B0
0x14000c23e  mov     eax, [rcx+2Ch]
0x14000c241  test    r13b, al
0x14000c244  jz      short loc_14000C2B0
0x14000c246  cmp     byte ptr [rcx+29h], 2
0x14000c24a  jb      short loc_14000C2B0
0x14000c24c  mov     edx, 19h
0x14000c251  mov     r9d, edi
0x14000c254  mov     rcx, [rcx+18h]
0x14000c258  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c25f  call    WPP_SF_d
0x14000c264  jmp     short loc_14000C2B0
0x14000c266  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c26d  cmp     rcx, r15
0x14000c270  jz      short loc_14000C295
0x14000c272  mov     eax, [rcx+2Ch]
0x14000c275  test    r13b, al
0x14000c278  jz      short loc_14000C295
0x14000c27a  cmp     byte ptr [rcx+29h], 5
0x14000c27e  jb      short loc_14000C295
0x14000c280  mov     rcx, [rcx+18h]
0x14000c284  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c28b  mov     edx, 17h
0x14000c290  call    WPP_SF_
0x14000c295  mov     eax, [rsi+rbp*8+14h]
0x14000c299  mov     [rbx+3Ch], eax
0x14000c29c  mov     eax, [rsi+rbp*8+18h]
0x14000c2a0  cmp     eax, [rsi+4]
0x14000c2a3  jnb     short loc_14000C2AA
0x14000c2a5  add     rax, rsi
0x14000c2a8  jmp     short loc_14000C2AC
0x14000c2aa  xor     eax, eax
0x14000c2ac  mov     [rbx+40h], rax
0x14000c2b0  add     r14d, r13d
0x14000c2b3  cmp     r14d, [rsi+8]
0x14000c2b7  jb      loc_14000C0AC
0x14000c2bd  lea     r15, [rbx+18h]
0x14000c2c1  cmp     dword ptr [rbx+58h], 0
0x14000c2c5  jnz     short loc_14000C2D2
0x14000c2c7  cmp     dword ptr [rbx+48h], 0
0x14000c2cb  jnz     short loc_14000C2D2
0x14000c2cd  mov     eax, r13d
0x14000c2d0  jmp     short loc_14000C2D4
0x14000c2d2  xor     eax, eax
0x14000c2d4  xchg    eax, [rbx+80h]
0x14000c2da  test    edi, edi
0x14000c2dc  js      short loc_14000C325
0x14000c2de  mov     rcx, rbx
0x14000c2e1  call    NatCreateAddressPool
0x14000c2e6  mov     edi, eax
0x14000c2e8  test    eax, eax
0x14000c2ea  jns     short loc_14000C32D
0x14000c2ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c2f3  lea     rax, WPP_GLOBAL_Control
0x14000c2fa  cmp     rcx, rax
0x14000c2fd  jz      short loc_14000C325
0x14000c2ff  mov     eax, [rcx+2Ch]
0x14000c302  test    r13b, al
0x14000c305  jz      short loc_14000C325
0x14000c307  cmp     byte ptr [rcx+29h], 2
0x14000c30b  jb      short loc_14000C325
0x14000c30d  mov     rcx, [rcx+18h]
0x14000c311  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c318  mov     edx, 1Dh
0x14000c31d  mov     r9d, edi
0x14000c320  call    WPP_SF_d
0x14000c325  mov     rcx, rbx
0x14000c328  call    NatResetInterface
0x14000c32d  mov     rcx, r15; SpinLock
0x14000c330  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000c337  nop     dword ptr [rax+rax+00h]
0x14000c33c  mov     dl, r12b; NewIrql
  ... truncated ...
```
