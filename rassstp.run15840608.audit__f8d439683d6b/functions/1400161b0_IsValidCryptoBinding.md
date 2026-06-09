# IsValidCryptoBinding

- ea: `0x1400161b0`
- end: `0x14001640e`
- name: `IsValidCryptoBinding`
- size: `606`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140017388`
- `0x140017550`

## callees

- `0x140002f88`
- `0x1400144c4`
- `0x1400161b0`
- `0x140018170`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016346`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001635a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016346`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001635a`
- `ntoskrnl!RtlCompareMemory` at `0x1400163a6`
- `ntoskrnl!RtlCompareMemory` at `0x1400163a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400162d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400162d1`

## pseudocode

```c
char __fastcall IsValidCryptoBinding(__int64 a1, __int64 a2, KIRQL a3)
{
  char v3; // r9
  SIZE_T v6; // rbp
  char v7; // di
  __int16 v9; // r11
  __int64 v10; // rax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  void *Source1; // [rsp+50h] [rbp-38h] BYREF
  __int16 v15; // [rsp+90h] [rbp+8h] BYREF
  unsigned __int16 v16; // [rsp+A8h] [rbp+20h] BYREF

  v3 = *(_BYTE *)(a1 + 176);
  Source1 = 0;
  v15 = 0;
  v16 = 0;
  v6 = *(unsigned __int16 *)(a1 + 360);
  v7 = 1;
  v9 = 20;
  if ( v3 != 1 )
    v9 = 32;
  v10 = 177;
  if ( v3 != 1 )
    v10 = 197;
  if ( !(unsigned __int8)GenerateSstpCallConnected(
                           a2,
                           a2,
                           (unsigned int)&v16,
                           v3,
                           a1 + v10,
                           v9,
                           a1 + 144,
                           (__int64)&Source1,
                           (__int64)&v15) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 0;
    }
    v12 = 85;
LABEL_31:
    WPP_SF__guid_(v11->AttachedDevice, v12, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    return 0;
  }
  if ( v15 != (_WORD)v6 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 0;
    }
    v12 = 86;
    goto LABEL_31;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), a3);
  if ( (unsigned int)ComputeCompoundMac(a1, a2, v16, Source1, &v15) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
    KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
    return 0;
  }
  KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
  if ( v15 != (_WORD)v6 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 0;
    }
    v12 = 88;
    goto LABEL_31;
  }
  if ( RtlCompareMemory(Source1, (const void *)(a1 + 327), v6) != v6 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 0;
    }
    v12 = 89;
    goto LABEL_31;
  }
  return v7;
}

```

## disassembly

```asm
0x1400161b0  mov     r11, rsp
0x1400161b3  mov     [r11+10h], rbx
0x1400161b7  push    rbp
0x1400161b8  push    rsi
0x1400161b9  push    rdi
0x1400161ba  push    r14
0x1400161bc  push    r15
0x1400161be  sub     rsp, 60h
0x1400161c2  mov     r9b, [rcx+0B0h]
0x1400161c9  lea     r10, [rcx+90h]
0x1400161d0  xor     eax, eax
0x1400161d2  mov     qword ptr [r11-38h], 0
0x1400161da  mov     [r11+8], ax
0x1400161df  mov     rsi, rcx
0x1400161e2  mov     [r11+20h], ax
0x1400161e7  mov     r15b, r8b
0x1400161ea  movzx   ebp, word ptr [rcx+168h]
0x1400161f1  lea     r8, [rsp+88h+arg_18]
0x1400161f9  mov     eax, 20h ; ' '
0x1400161fe  mov     dil, 1
0x140016201  cmp     r9b, dil
0x140016204  mov     r14, rdx
0x140016207  lea     r11d, [rax-0Ch]
0x14001620b  cmovnz  r11w, ax
0x140016210  mov     eax, 0B1h
0x140016215  lea     ecx, [rax+14h]
0x140016218  cmovnz  eax, ecx
0x14001621b  lea     rcx, [rsp+88h+arg_0]
0x140016223  mov     [rsp+88h+var_48], rcx
0x140016228  add     rax, rsi
0x14001622b  lea     rcx, [rsp+88h+Source1]
0x140016230  mov     [rsp+88h+var_50], rcx
0x140016235  mov     rcx, rdx
0x140016238  mov     [rsp+88h+var_58], r10
0x14001623d  mov     [rsp+88h+var_60], r11w
0x140016243  mov     [rsp+88h+var_68], rax
0x140016248  call    GenerateSstpCallConnected
0x14001624d  test    al, al
0x14001624f  jnz     short loc_140016287
0x140016251  mov     rcx, cs:WPP_GLOBAL_Control
0x140016258  lea     rax, WPP_GLOBAL_Control
0x14001625f  cmp     rcx, rax
0x140016262  jz      loc_1400163F3
0x140016268  mov     eax, [rcx+2Ch]
0x14001626b  test    al, 4
0x14001626d  jz      loc_1400163F3
0x140016273  cmp     [rcx+29h], dil
0x140016277  jb      loc_1400163F3
0x14001627d  mov     edx, 55h ; 'U'
0x140016282  jmp     loc_1400163DC
0x140016287  cmp     [rsp+88h+arg_0], bp
0x14001628f  jz      short loc_1400162C7
0x140016291  mov     rcx, cs:WPP_GLOBAL_Control
0x140016298  lea     rax, WPP_GLOBAL_Control
0x14001629f  cmp     rcx, rax
0x1400162a2  jz      loc_1400163F3
0x1400162a8  mov     eax, [rcx+2Ch]
0x1400162ab  test    al, 4
0x1400162ad  jz      loc_1400163F3
0x1400162b3  cmp     [rcx+29h], dil
0x1400162b7  jb      loc_1400163F3
0x1400162bd  mov     edx, 56h ; 'V'
0x1400162c2  jmp     loc_1400163DC
0x1400162c7  lea     rbx, [rsi+10h]
0x1400162cb  mov     dl, r15b; NewIrql
0x1400162ce  mov     rcx, rbx; SpinLock
0x1400162d1  call    cs:__imp_KeReleaseSpinLock
0x1400162d8  nop     dword ptr [rax+rax+00h]
0x1400162dd  movzx   r8d, [rsp+88h+arg_18]
0x1400162e6  lea     rax, [rsp+88h+arg_0]
0x1400162ee  mov     r9, [rsp+88h+Source1]
0x1400162f3  mov     rdx, r14
0x1400162f6  mov     rcx, rsi
0x1400162f9  mov     [rsp+88h+var_68], rax
0x1400162fe  call    ComputeCompoundMac
0x140016303  test    eax, eax
0x140016305  jz      short loc_140016357
0x140016307  mov     rcx, cs:WPP_GLOBAL_Control
0x14001630e  lea     rax, WPP_GLOBAL_Control
0x140016315  cmp     rcx, rax
0x140016318  jz      short loc_140016343
0x14001631a  mov     eax, [rcx+2Ch]
0x14001631d  test    al, 4
0x14001631f  jz      short loc_140016343
0x140016321  cmp     [rcx+29h], dil
0x140016325  jb      short loc_140016343
0x140016327  mov     rcx, [rcx+18h]
0x14001632b  lea     r9, [rsi+16Ch]
0x140016332  mov     edx, 57h ; 'W'
0x140016337  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14001633e  call    WPP_SF__guid_
0x140016343  mov     rcx, rbx; SpinLock
0x140016346  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001634d  nop     dword ptr [rax+rax+00h]
0x140016352  jmp     loc_1400163F3
0x140016357  mov     rcx, rbx; SpinLock
0x14001635a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016361  nop     dword ptr [rax+rax+00h]
0x140016366  cmp     [rsp+88h+arg_0], bp
0x14001636e  jz      short loc_140016397
0x140016370  mov     rcx, cs:WPP_GLOBAL_Control
0x140016377  lea     rax, WPP_GLOBAL_Control
0x14001637e  cmp     rcx, rax
0x140016381  jz      short loc_1400163F3
0x140016383  mov     eax, [rcx+2Ch]
0x140016386  test    al, 4
0x140016388  jz      short loc_1400163F3
0x14001638a  cmp     [rcx+29h], dil
0x14001638e  jb      short loc_1400163F3
0x140016390  mov     edx, 58h ; 'X'
0x140016395  jmp     short loc_1400163DC
0x140016397  mov     rcx, [rsp+88h+Source1]; Source1
0x14001639c  lea     rdx, [rsi+147h]; Source2
0x1400163a3  mov     r8, rbp; Length
0x1400163a6  call    cs:__imp_RtlCompareMemory
0x1400163ad  nop     dword ptr [rax+rax+00h]
0x1400163b2  cmp     rax, rbp
0x1400163b5  jz      short loc_1400163F6
0x1400163b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400163be  lea     rax, WPP_GLOBAL_Control
0x1400163c5  cmp     rcx, rax
0x1400163c8  jz      short loc_1400163F3
0x1400163ca  mov     eax, [rcx+2Ch]
0x1400163cd  test    al, 4
0x1400163cf  jz      short loc_1400163F3
0x1400163d1  cmp     [rcx+29h], dil
0x1400163d5  jb      short loc_1400163F3
0x1400163d7  mov     edx, 59h ; 'Y'
0x1400163dc  mov     rcx, [rcx+18h]
0x1400163e0  lea     r9, [rsi+16Ch]
0x1400163e7  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400163ee  call    WPP_SF__guid_
0x1400163f3  xor     dil, dil
0x1400163f6  mov     rbx, [rsp+88h+arg_8]
0x1400163fe  mov     al, dil
0x140016401  add     rsp, 60h
0x140016405  pop     r15
0x140016407  pop     r14
0x140016409  pop     rdi
0x14001640a  pop     rsi
0x14001640b  pop     rbp
0x14001640c  retn
```
