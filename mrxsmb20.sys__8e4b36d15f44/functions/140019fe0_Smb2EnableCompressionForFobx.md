# Smb2EnableCompressionForFobx

- ea: `0x140019fe0`
- end: `0x14001a29c`
- name: `Smb2EnableCompressionForFobx`
- size: `700`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019d60`
- `0x1400236b0`
- `0x140050010`

## callees

- `0x140019fe0`
- `0x14002ba84`
- `0x140033da8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0b4`
- `ntoskrnl!ExAllocatePool2` at `0x14001a06f`
- `ntoskrnl!ExAllocatePool2` at `0x14001a06f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a091`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a091`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a20f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a20f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a132`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a132`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x14001a01f`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x14001a01f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001a16b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001a17b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001a16b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001a17b`

## pseudocode

```c
__int64 __fastcall Smb2EnableCompressionForFobx(__int64 a1, __int64 a2)
{
  unsigned __int64 v3; // r13
  unsigned __int64 v4; // r12
  int v5; // ebp
  unsigned int v6; // esi
  unsigned int v7; // r15d
  __int64 v8; // rbx
  __int64 Pool2; // rax
  void *v10; // r14
  __int64 v12; // rsi
  KIRQL v13; // al
  __int64 v14; // r8
  __int64 v15; // rcx
  int v16; // ecx
  __int64 v17; // rcx
  KIRQL v18; // [rsp+70h] [rbp+8h]
  __int64 v19; // [rsp+78h] [rbp+10h]

  if ( a2 )
  {
    v3 = *(_QWORD *)a2;
    v4 = *(_QWORD *)(a2 + 8);
    v5 = *(_DWORD *)(a2 + 16);
    v6 = *(_DWORD *)(a2 + 24);
    v7 = *(_DWORD *)(a2 + 28);
  }
  else
  {
    v6 = 1;
    v3 = 0;
    v4 = 0;
    v7 = 0;
    v5 = 2;
    if ( (*(_BYTE *)(MRxSmbGetCompressionConfigBlock() + 26) & 4) == 0 )
      v5 = -1;
  }
  v8 = *(_QWORD *)(a1 + 56);
  if ( !v8 )
    return 0;
  v19 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 136LL);
  if ( !*(_QWORD *)(v19 + 96) )
  {
    Pool2 = ExAllocatePool2(64, 64, 1834182982);
    v10 = (void *)Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 32));
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v19 + 96), (signed __int64)v10, 0) )
      ExFreePoolWithTag(v10, 0x6D536946u);
  }
  if ( v6 + 1 > 2 )
    __int2c();
  if ( v6 == -1 )
  {
    *(_DWORD *)(v8 + 4) &= ~2u;
  }
  else if ( v6 == 1 )
  {
    *(_DWORD *)(v8 + 4) |= 2u;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_6016506345153a43e23e2141f162fbeb_Traceguids, v6, v8);
  }
  v12 = *(_QWORD *)(v19 + 96);
  if ( !v12 )
    __int2c();
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v12 + 32));
  v15 = (unsigned int)(v5 + 1);
  v18 = v13;
  if ( (unsigned int)v15 > 3 )
    __int2c();
  switch ( v5 )
  {
    case 1:
      if ( v3 <= v4 )
        __int2c();
      goto LABEL_33;
    case 2:
      v3 = *(_QWORD *)(MRxSmbGetConfigurationBlock(v15) + 48);
      v4 = *(_QWORD *)(MRxSmbGetConfigurationBlock(v17) + 56);
      if ( v3 <= v4 )
      {
        v3 = 524288000;
        v4 = 104857600;
      }
LABEL_33:
      *(_QWORD *)v12 = v3;
      *(_QWORD *)(v12 + 8) = 0;
      v16 = 1;
      *(_QWORD *)(v12 + 16) = 0;
      goto LABEL_34;
    case -1:
      *(_QWORD *)v12 = 0;
      v16 = 0;
      v4 = 0;
LABEL_34:
      *(_QWORD *)(v12 + 24) = v4;
      *(_DWORD *)(v12 + 40) = v16;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_iq(WPP_GLOBAL_Control->AttachedDevice, v12, v14, v3, v19);
      }
      break;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v12 + 32), v18);
  if ( v7 + 1 > 3 )
    __int2c();
  switch ( v7 )
  {
    case 0xFFFFFFFF:
      *(_DWORD *)(v8 + 48) = 0;
      break;
    case 1u:
      *(_DWORD *)(v8 + 48) = 1;
      break;
    case 2u:
      *(_DWORD *)(v8 + 48) = 2;
      break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_6016506345153a43e23e2141f162fbeb_Traceguids, v7, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x140019fe0  mov     [rsp+arg_10], rbx
0x140019fe5  push    rbp
0x140019fe6  push    rsi
0x140019fe7  push    rdi
0x140019fe8  push    r12
0x140019fea  push    r13
0x140019fec  push    r14
0x140019fee  push    r15
0x140019ff0  sub     rsp, 30h
0x140019ff4  xor     edi, edi
0x140019ff6  mov     r14, rcx
0x140019ff9  test    rdx, rdx
0x140019ffc  jz      short loc_14001A011
0x140019ffe  mov     r13, [rdx]
0x14001a001  mov     r12, [rdx+8]
0x14001a005  mov     ebp, [rdx+10h]
0x14001a008  mov     esi, [rdx+18h]
0x14001a00b  mov     r15d, [rdx+1Ch]
0x14001a00f  jmp     short loc_14001A03C
0x14001a011  mov     esi, 1
0x14001a016  xor     r13d, r13d
0x14001a019  xor     r12d, r12d
0x14001a01c  xor     r15d, r15d
0x14001a01f  call    cs:__imp_MRxSmbGetCompressionConfigBlock
0x14001a026  nop     dword ptr [rax+rax+00h]
0x14001a02b  mov     ebp, 2
0x14001a030  test    byte ptr [rax+1Ah], 4
0x14001a034  mov     eax, 0FFFFFFFFh
0x14001a039  cmovz   ebp, eax
0x14001a03c  mov     rbx, [r14+38h]
0x14001a040  test    rbx, rbx
0x14001a043  jz      loc_14001A281
0x14001a049  mov     rax, [r14+28h]
0x14001a04d  mov     rcx, [rax+88h]
0x14001a054  mov     [rsp+68h+arg_8], rcx
0x14001a059  mov     rax, [rcx+60h]
0x14001a05d  test    rax, rax
0x14001a060  jnz     short loc_14001A0C0
0x14001a062  mov     edx, 40h ; '@'
0x14001a067  mov     r8d, 6D536946h
0x14001a06d  mov     ecx, edx
0x14001a06f  call    cs:__imp_ExAllocatePool2
0x14001a076  nop     dword ptr [rax+rax+00h]
0x14001a07b  mov     r14, rax
0x14001a07e  test    rax, rax
0x14001a081  jnz     short loc_14001A08D
0x14001a083  mov     eax, 0C000009Ah
0x14001a088  jmp     loc_14001A283
0x14001a08d  lea     rcx, [rax+20h]; SpinLock
0x14001a091  call    cs:__imp_KeInitializeSpinLock
0x14001a098  nop     dword ptr [rax+rax+00h]
0x14001a09d  mov     rcx, [rsp+68h+arg_8]
0x14001a0a2  xor     eax, eax
0x14001a0a4  lock cmpxchg [rcx+60h], r14
0x14001a0aa  jz      short loc_14001A0C0
0x14001a0ac  mov     edx, 6D536946h; Tag
0x14001a0b1  mov     rcx, r14; P
0x14001a0b4  call    cs:__imp_ExFreePoolWithTag
0x14001a0bb  nop     dword ptr [rax+rax+00h]
0x14001a0c0  lea     eax, [rsi+1]
0x14001a0c3  cmp     eax, 2
0x14001a0c6  jbe     short loc_14001A0CA
0x14001a0c8  int     2Ch; Windows NT - assertion failure
0x14001a0ca  cmp     esi, 0FFFFFFFFh
0x14001a0cd  jz      short loc_14001A0DA
0x14001a0cf  cmp     esi, 1
0x14001a0d2  jnz     short loc_14001A0DE
0x14001a0d4  or      dword ptr [rbx+4], 2
0x14001a0d8  jmp     short loc_14001A0DE
0x14001a0da  and     dword ptr [rbx+4], 0FFFFFFFDh
0x14001a0de  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001a0e5  lea     rax, WPP_GLOBAL_Control
0x14001a0ec  cmp     rcx, rax
0x14001a0ef  jz      short loc_14001A11B
0x14001a0f1  mov     eax, [rcx+2Ch]
0x14001a0f4  test    al, 40h
0x14001a0f6  jz      short loc_14001A11B
0x14001a0f8  cmp     byte ptr [rcx+29h], 4
0x14001a0fc  jb      short loc_14001A11B
0x14001a0fe  mov     rcx, [rcx+18h]
0x14001a102  lea     r8, WPP_6016506345153a43e23e2141f162fbeb_Traceguids
0x14001a109  mov     edx, 16h
0x14001a10e  mov     [rsp+68h+var_48], rbx
0x14001a113  mov     r9d, esi
0x14001a116  call    WPP_SF_dq
0x14001a11b  mov     rsi, [rsp+68h+arg_8]
0x14001a120  mov     rsi, [rsi+60h]
0x14001a124  test    rsi, rsi
0x14001a127  jnz     short loc_14001A12B
0x14001a129  int     2Ch; Windows NT - assertion failure
0x14001a12b  lea     r14, [rsi+20h]
0x14001a12f  mov     rcx, r14; SpinLock
0x14001a132  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a139  nop     dword ptr [rax+rax+00h]
0x14001a13e  lea     ecx, [rbp+1]
0x14001a141  mov     [rsp+68h+arg_0], al
0x14001a145  cmp     ecx, 3
0x14001a148  jbe     short loc_14001A14C
0x14001a14a  int     2Ch; Windows NT - assertion failure
0x14001a14c  cmp     ebp, 1
0x14001a14f  jz      short loc_14001A19E
0x14001a151  cmp     ebp, 2
0x14001a154  jz      short loc_14001A16B
0x14001a156  cmp     ebp, 0FFFFFFFFh
0x14001a159  jnz     loc_14001A1FE
0x14001a15f  xor     ebp, ebp
0x14001a161  mov     [rsi], rbp
0x14001a164  mov     ecx, ebp
0x14001a166  mov     r12d, ebp
0x14001a169  jmp     short loc_14001A1B7
0x14001a16b  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001a172  nop     dword ptr [rax+rax+00h]
0x14001a177  mov     r13, [rax+30h]
0x14001a17b  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001a182  nop     dword ptr [rax+rax+00h]
0x14001a187  mov     r12, [rax+38h]
0x14001a18b  cmp     r13, r12
0x14001a18e  ja      short loc_14001A1A5
0x14001a190  mov     r13d, 1F400000h
0x14001a196  mov     r12d, 6400000h
0x14001a19c  jmp     short loc_14001A1A5
0x14001a19e  cmp     r13, r12
0x14001a1a1  ja      short loc_14001A1A5
0x14001a1a3  int     2Ch; Windows NT - assertion failure
0x14001a1a5  xor     ebp, ebp
0x14001a1a7  mov     [rsi], r13
0x14001a1aa  mov     [rsi+8], rbp
0x14001a1ae  mov     ecx, 1
0x14001a1b3  mov     [rsi+10h], rbp
0x14001a1b7  mov     eax, 18h
0x14001a1bc  mov     rdx, rsi
0x14001a1bf  mov     [rdx+rax], r12; __annotation("TMF:",
0x14001a1c3  mov     [rsi+28h], ecx
0x14001a1c6  lea     rsi, WPP_GLOBAL_Control
0x14001a1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1d4  cmp     rcx, rsi
0x14001a1d7  jz      short loc_14001A207
0x14001a1d9  mov     eax, [rcx+2Ch]
0x14001a1dc  test    al, 40h
0x14001a1de  jz      short loc_14001A207
0x14001a1e0  cmp     byte ptr [rcx+29h], 4
0x14001a1e4  jb      short loc_14001A207
0x14001a1e6  mov     rax, [rsp+68h+arg_8]
0x14001a1eb  mov     r9, r13
0x14001a1ee  mov     rcx, [rcx+18h]
0x14001a1f2  mov     [rsp+68h+var_48], rax
0x14001a1f7  call    WPP_SF_iq
0x14001a1fc  jmp     short loc_14001A207
0x14001a1fe  xor     ebp, ebp
0x14001a200  lea     rsi, WPP_GLOBAL_Control
0x14001a207  movzx   edx, [rsp+68h+arg_0]; NewIrql
0x14001a20c  mov     rcx, r14; SpinLock
0x14001a20f  call    cs:__imp_KeReleaseSpinLock
0x14001a216  nop     dword ptr [rax+rax+00h]
0x14001a21b  lea     eax, [r15+1]
0x14001a21f  cmp     eax, 3
0x14001a222  jbe     short loc_14001A226
0x14001a224  int     2Ch; Windows NT - assertion failure
0x14001a226  cmp     r15d, 0FFFFFFFFh
0x14001a22a  jz      short loc_14001A247
0x14001a22c  cmp     r15d, 1
0x14001a230  jz      short loc_14001A23E
0x14001a232  cmp     r15d, 2
0x14001a236  jnz     short loc_14001A24A
0x14001a238  mov     [rbx+30h], r15d
0x14001a23c  jmp     short loc_14001A24A
0x14001a23e  mov     dword ptr [rbx+30h], 1
0x14001a245  jmp     short loc_14001A24A
0x14001a247  mov     [rbx+30h], ebp
0x14001a24a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001a251  cmp     rcx, rsi
0x14001a254  jz      short loc_14001A281
0x14001a256  mov     edx, [rcx+2Ch]
0x14001a259  test    dl, 40h
0x14001a25c  jz      short loc_14001A281
0x14001a25e  cmp     byte ptr [rcx+29h], 4
0x14001a262  jb      short loc_14001A281
0x14001a264  mov     rcx, [rcx+18h]
0x14001a268  lea     r8, WPP_6016506345153a43e23e2141f162fbeb_Traceguids
0x14001a26f  mov     edx, 17h
0x14001a274  mov     [rsp+68h+var_48], rbx
0x14001a279  mov     r9d, r15d
0x14001a27c  call    WPP_SF_dq
0x14001a281  mov     eax, edi
0x14001a283  mov     rbx, [rsp+68h+arg_10]
0x14001a28b  add     rsp, 30h
0x14001a28f  pop     r15
0x14001a291  pop     r14
0x14001a293  pop     r13
0x14001a295  pop     r12
0x14001a297  pop     rdi
0x14001a298  pop     rsi
0x14001a299  pop     rbp
0x14001a29a  retn
```
