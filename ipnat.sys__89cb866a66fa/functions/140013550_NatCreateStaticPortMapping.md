# NatCreateStaticPortMapping

- ea: `0x140013550`
- end: `0x140013796`
- name: `NatCreateStaticPortMapping`
- size: `582`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400128ec`
- `0x14001e1f0`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140011e00`
- `0x14001308c`
- `0x140013550`
- `0x1400138fc`
- `0x140013ccc`
- `0x14001d05c`

## pseudocode

```c
__int64 __fastcall NatCreateStaticPortMapping(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  unsigned int v6; // eax
  __int64 Timer_high; // rdx
  unsigned int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v14[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int16 v15; // [rsp+A8h] [rbp+38h] BYREF
  unsigned int v16; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v17; // [rsp+B8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
  }
  v4 = *(unsigned int *)(a2 + 4);
  v5 = *(unsigned int *)(a2 + 12);
  v14[0] = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  if ( !(_DWORD)v4 )
  {
    v6 = NatAcquireFromAddressPool(a1, v5, v4, &v17);
    v8 = v6;
    if ( v6 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (Timer_high & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v10 = 75;
          v11 = v6;
LABEL_23:
          WPP_SF_d(v9->AttachedDevice, v10, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, v11);
          goto LABEL_24;
        }
      }
    }
    goto LABEL_24;
  }
  v12 = NatLookupAddressPoolEntry(*(_QWORD *)(a1 + 144), v5, v4, v14);
  v17 = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
    }
    v8 = NatCreateAddressPoolEntry(a1, *(_DWORD *)(a2 + 12), *(_DWORD *)(a2 + 4), 0, v14, &v17);
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v10 = 77;
        v11 = v8;
        goto LABEL_23;
      }
    }
LABEL_24:
    if ( (v8 & 0x80000000) != 0 )
      goto LABEL_31;
    goto LABEL_25;
  }
  if ( *(int *)(v12 + 72) >= 0 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 76));
LABEL_25:
  LOBYTE(Timer_high) = *(_BYTE *)a2;
  v8 = NatCreateTicket(
         a1,
         Timer_high,
         *(unsigned int *)(a2 + 12),
         *(_WORD *)(a2 + 8),
         0,
         0,
         3,
         v17,
         *(_WORD *)(a2 + 2),
         &v16,
         &v15);
  if ( v8
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, v8);
  }
  NatDereferenceAddressPoolEntry(a1, v17);
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140013550  mov     [rsp-28h+arg_0], rbx
0x140013555  push    rbp
0x140013556  push    rsi
0x140013557  push    rdi
0x140013558  push    r12
0x14001355a  push    r13
0x14001355c  mov     rbp, rsp
0x14001355f  sub     rsp, 70h
0x140013563  mov     rdi, rdx
0x140013566  mov     rsi, rcx
0x140013569  mov     rcx, cs:WPP_GLOBAL_Control
0x140013570  lea     r12, WPP_GLOBAL_Control
0x140013577  lea     r13, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x14001357e  cmp     rcx, r12
0x140013581  jz      short loc_1400135A1
0x140013583  mov     eax, [rcx+2Ch]
0x140013586  test    al, 1
0x140013588  jz      short loc_1400135A1
0x14001358a  cmp     byte ptr [rcx+29h], 6
0x14001358e  jb      short loc_1400135A1
0x140013590  mov     rcx, [rcx+18h]
0x140013594  mov     edx, 4Ah ; 'J'
0x140013599  mov     r8, r13
0x14001359c  call    WPP_SF_
0x1400135a1  mov     r8d, [rdi+4]
0x1400135a5  xor     eax, eax
0x1400135a7  mov     edx, [rdi+0Ch]
0x1400135aa  mov     [rbp+var_10], 0
0x1400135b2  mov     [rbp+arg_10], 0
0x1400135b9  mov     [rbp+arg_8], ax
0x1400135bd  mov     [rbp+arg_18], rax
0x1400135c1  test    r8d, r8d
0x1400135c4  jnz     short loc_14001360F
0x1400135c6  lea     r9, [rbp+arg_18]
0x1400135ca  mov     rcx, rsi
0x1400135cd  call    NatAcquireFromAddressPool
0x1400135d2  mov     ebx, eax
0x1400135d4  test    eax, eax
0x1400135d6  jz      loc_1400136BC
0x1400135dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135e3  cmp     rcx, r12
0x1400135e6  jz      loc_1400136BC
0x1400135ec  mov     edx, [rcx+2Ch]
0x1400135ef  test    dl, 1
0x1400135f2  jz      loc_1400136BC
0x1400135f8  cmp     byte ptr [rcx+29h], 2
0x1400135fc  jb      loc_1400136BC
0x140013602  mov     edx, 4Bh ; 'K'
0x140013607  mov     r9d, eax
0x14001360a  jmp     loc_1400136B0
0x14001360f  mov     rcx, [rsi+90h]
0x140013616  lea     r9, [rbp+var_10]
0x14001361a  call    NatLookupAddressPoolEntry
0x14001361f  mov     [rbp+arg_18], rax
0x140013623  test    rax, rax
0x140013626  jz      short loc_14001363B
0x140013628  cmp     dword ptr [rax+48h], 0
0x14001362c  jl      loc_1400136C4
0x140013632  lock inc dword ptr [rax+4Ch]
0x140013636  jmp     loc_1400136C4
0x14001363b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013642  cmp     rcx, r12
0x140013645  jz      short loc_140013665
0x140013647  mov     eax, [rcx+2Ch]
0x14001364a  test    al, 1
0x14001364c  jz      short loc_140013665
0x14001364e  cmp     byte ptr [rcx+29h], 2
0x140013652  jb      short loc_140013665
0x140013654  mov     rcx, [rcx+18h]
0x140013658  mov     edx, 4Ch ; 'L'
0x14001365d  mov     r8, r13
0x140013660  call    WPP_SF_
0x140013665  mov     r8d, [rdi+4]
0x140013669  lea     rax, [rbp+arg_18]
0x14001366d  mov     edx, [rdi+0Ch]
0x140013670  xor     r9d, r9d
0x140013673  mov     [rsp+70h+var_48], rax
0x140013678  mov     rcx, rsi
0x14001367b  lea     rax, [rbp+var_10]
0x14001367f  mov     [rsp+70h+var_50], rax
0x140013684  call    NatCreateAddressPoolEntry
0x140013689  mov     ebx, eax
0x14001368b  test    eax, eax
0x14001368d  jz      short loc_1400136BC
0x14001368f  mov     rcx, cs:WPP_GLOBAL_Control
0x140013696  cmp     rcx, r12
0x140013699  jz      short loc_1400136BC
0x14001369b  mov     eax, [rcx+2Ch]
0x14001369e  test    al, 1
0x1400136a0  jz      short loc_1400136BC
0x1400136a2  cmp     byte ptr [rcx+29h], 2
0x1400136a6  jb      short loc_1400136BC
0x1400136a8  mov     edx, 4Dh ; 'M'
0x1400136ad  mov     r9d, ebx
0x1400136b0  mov     rcx, [rcx+18h]
0x1400136b4  mov     r8, r13
0x1400136b7  call    WPP_SF_d
0x1400136bc  test    ebx, ebx
0x1400136be  js      loc_140013752
0x1400136c4  movzx   r9d, word ptr [rdi+8]
0x1400136c9  lea     rax, [rbp+arg_8]
0x1400136cd  mov     r8d, [rdi+0Ch]
0x1400136d1  mov     rcx, rsi
0x1400136d4  mov     dl, [rdi]
0x1400136d6  mov     [rsp+70h+var_20], rax
0x1400136db  lea     rax, [rbp+arg_10]
0x1400136df  mov     [rsp+70h+var_28], rax
0x1400136e4  movzx   eax, word ptr [rdi+2]
0x1400136e8  mov     [rsp+70h+var_30], ax
0x1400136ed  mov     rax, [rbp+arg_18]
0x1400136f1  mov     [rsp+70h+var_38], rax
0x1400136f6  mov     [rsp+70h+var_40], 3
0x1400136fe  mov     dword ptr [rsp+70h+var_48], 0
0x140013706  mov     dword ptr [rsp+70h+var_50], 0
0x14001370e  call    NatCreateTicket
0x140013713  mov     ebx, eax
0x140013715  test    eax, eax
0x140013717  jz      short loc_140013746
0x140013719  mov     rcx, cs:WPP_GLOBAL_Control
0x140013720  cmp     rcx, r12
0x140013723  jz      short loc_140013746
0x140013725  mov     eax, [rcx+2Ch]
0x140013728  test    al, 1
0x14001372a  jz      short loc_140013746
0x14001372c  cmp     byte ptr [rcx+29h], 2
0x140013730  jb      short loc_140013746
0x140013732  mov     rcx, [rcx+18h]
0x140013736  mov     edx, 4Eh ; 'N'
0x14001373b  mov     r9d, ebx
0x14001373e  mov     r8, r13
0x140013741  call    WPP_SF_d
0x140013746  mov     rdx, [rbp+arg_18]
0x14001374a  mov     rcx, rsi
0x14001374d  call    NatDereferenceAddressPoolEntry
0x140013752  mov     rcx, cs:WPP_GLOBAL_Control
0x140013759  cmp     rcx, r12
0x14001375c  jz      short loc_14001377F
0x14001375e  mov     eax, [rcx+2Ch]
0x140013761  test    al, 1
0x140013763  jz      short loc_14001377F
0x140013765  cmp     byte ptr [rcx+29h], 6
0x140013769  jb      short loc_14001377F
0x14001376b  mov     rcx, [rcx+18h]
0x14001376f  mov     edx, 4Fh ; 'O'
0x140013774  mov     r9d, ebx
0x140013777  mov     r8, r13
0x14001377a  call    WPP_SF_d
0x14001377f  mov     eax, ebx
0x140013781  mov     rbx, [rsp+70h+arg_0]
0x140013789  add     rsp, 70h
0x14001378d  pop     r13
0x14001378f  pop     r12
0x140013791  pop     rdi
0x140013792  pop     rsi
0x140013793  pop     rbp
0x140013794  retn
```
