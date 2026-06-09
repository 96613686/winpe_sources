# DepFSDismountDependencyList

- ea: `0x18000aecc`
- end: `0x18000b1cc`
- name: `DepFSDismountDependencyList`
- size: `768`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18000b450`
- `0x18000b5f0`
- `0x18000fa10`

## callees

- `0x180001020`
- `0x1800010b8`
- `0x1800010fc`
- `0x18000aa48`
- `0x18000aecc`
- `0x18000b1d4`
- `0x18000f73c`
- `0x18000f91c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000af96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b004`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b05b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b16e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000af96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b004`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b05b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b16e`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000af8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000aff8`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b04f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b162`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000af8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000aff8`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b04f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b162`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000af6a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b0e4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000af6a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b0e4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000af55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b0ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000af55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b0ce`

## pseudocode

```c
__int64 __fastcall DepFSDismountDependencyList(__int64 a1, __int64 a2, char a3)
{
  int v6; // r14d
  char v7; // bp
  unsigned int v8; // r15d
  __int16 v9; // ax
  __int64 v10; // rsi
  int v11; // eax
  __int64 v12; // rax
  unsigned int i; // esi
  __int16 v14; // cx
  __int64 v15; // rax
  __int64 v16; // rcx

  v6 = 0;
  v7 = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, a1);
  }
  v8 = 0;
  if ( !*(_DWORD *)(a1 + 4) )
    goto LABEL_36;
  while ( 1 )
  {
    v9 = *(_WORD *)(a1 + 16LL * v8 + 8);
    if ( (v9 & 1) != 0 )
      break;
    if ( (v9 & 2) != 0 )
    {
      v12 = *(_QWORD *)(a1 + 16LL * v8 + 16);
      if ( v12 != a2 )
      {
        if ( v12 )
        {
          if ( v7 )
          {
            ExReleaseResourceLite(&Resource);
            KeLeaveCriticalRegion();
            v7 = 0;
          }
          v6 = DepFSDismountDependency(*(char **)(a1 + 16LL * v8 + 16));
          if ( v6 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                32,
                WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids,
                (unsigned int)v6);
            }
            if ( !a3 )
              goto LABEL_34;
          }
        }
      }
    }
LABEL_31:
    if ( ++v8 >= *(_DWORD *)(a1 + 4) )
      goto LABEL_34;
  }
  if ( (v9 & 0x10) == 0 )
  {
    v10 = *(_QWORD *)(a1 + 16LL * v8 + 16);
    if ( !v7 )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&Resource, 1u);
    }
    v11 = *(_DWORD *)(v10 + 56);
    if ( (v11 & 0x25) != 0 )
    {
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      v7 = 0;
    }
    else
    {
      *(_DWORD *)(v10 + 56) = v11 | 4;
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      v7 = 0;
      v6 = DepFSSendDismountRequest(v10);
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids,
            (unsigned int)v6);
        }
        if ( !a3 )
          goto LABEL_35;
      }
    }
    DereferenceVolumeContext(v10);
    *(_QWORD *)(a1 + 16LL * v8 + 16) = 0;
    goto LABEL_31;
  }
  v6 = -1073741790;
LABEL_34:
  if ( v7 )
    goto LABEL_36;
LABEL_35:
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
LABEL_36:
  for ( i = 0; i < *(_DWORD *)(a1 + 4); ++i )
  {
    v14 = *(_WORD *)(a1 + 16LL * i + 8);
    if ( (v14 & 2) != 0 )
    {
      v15 = *(_QWORD *)(a1 + 16LL * i + 16);
      if ( v15 )
      {
        if ( (v14 & 0x100) != 0 )
          _InterlockedDecrement((volatile signed __int32 *)(v15 + 96));
        DereferenceDependencyContext(*(PVOID *)(a1 + 16LL * i + 16));
        *(_QWORD *)(a1 + 16LL * i + 16) = 0;
      }
    }
    if ( (*(_BYTE *)(a1 + 16LL * i + 8) & 1) != 0 )
    {
      v16 = *(_QWORD *)(a1 + 16LL * i + 16);
      if ( v16 )
      {
        DereferenceVolumeContext(v16);
        *(_QWORD *)(a1 + 16LL * i + 16) = 0;
      }
    }
  }
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, a1, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000aecc  push    rbx
0x18000aece  push    rbp
0x18000aecf  push    rsi
0x18000aed0  push    rdi
0x18000aed1  push    r12
0x18000aed3  push    r13
0x18000aed5  push    r14
0x18000aed7  push    r15
0x18000aed9  sub     rsp, 38h
0x18000aedd  mov     r12b, r8b
0x18000aee0  mov     r13, rdx
0x18000aee3  mov     rbx, rcx
0x18000aee6  xor     r14d, r14d
0x18000aee9  mov     bpl, 1
0x18000aeec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aef3  lea     rsi, WPP_GLOBAL_Control
0x18000aefa  cmp     rcx, rsi
0x18000aefd  jz      short loc_18000AF23
0x18000aeff  mov     eax, [rcx+2Ch]
0x18000af02  test    al, 10h
0x18000af04  jz      short loc_18000AF23
0x18000af06  cmp     byte ptr [rcx+29h], 4
0x18000af0a  jb      short loc_18000AF23
0x18000af0c  mov     rcx, [rcx+18h]
0x18000af10  lea     edx, [r14+1Eh]
0x18000af14  mov     r9, rbx
0x18000af17  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000af1e  call    WPP_SF_q
0x18000af23  xor     r15d, r15d
0x18000af26  cmp     [rbx+4], r14d
0x18000af2a  jbe     loc_18000B0F0
0x18000af30  mov     edi, r15d
0x18000af33  add     rdi, rdi
0x18000af36  movzx   eax, word ptr [rbx+rdi*8+8]
0x18000af3b  test    al, 1
0x18000af3d  jz      loc_18000B030
0x18000af43  test    al, 10h
0x18000af45  jnz     loc_18000B0C0
0x18000af4b  mov     rsi, [rbx+rdi*8+10h]
0x18000af50  test    bpl, bpl
0x18000af53  jnz     short loc_18000AF76
0x18000af55  call    cs:__imp_KeEnterCriticalRegion
0x18000af5c  nop     dword ptr [rax+rax+00h]
0x18000af61  mov     dl, 1; Wait
0x18000af63  lea     rcx, Resource; Resource
0x18000af6a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000af71  nop     dword ptr [rax+rax+00h]
0x18000af76  mov     eax, [rsi+38h]
0x18000af79  lea     rcx, Resource; Resource
0x18000af80  test    al, 25h
0x18000af82  jnz     short loc_18000AFF8
0x18000af84  or      eax, 4
0x18000af87  mov     [rsi+38h], eax
0x18000af8a  call    cs:__imp_ExReleaseResourceLite
0x18000af91  nop     dword ptr [rax+rax+00h]
0x18000af96  call    cs:__imp_KeLeaveCriticalRegion
0x18000af9d  nop     dword ptr [rax+rax+00h]
0x18000afa2  mov     rcx, rsi
0x18000afa5  xor     bpl, bpl
0x18000afa8  call    DepFSSendDismountRequest
0x18000afad  mov     r14d, eax
0x18000afb0  test    eax, eax
0x18000afb2  jns     short loc_18000B013
0x18000afb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afbb  lea     rax, WPP_GLOBAL_Control
0x18000afc2  cmp     rcx, rax
0x18000afc5  jz      short loc_18000AFED
0x18000afc7  mov     edx, [rcx+2Ch]
0x18000afca  test    dl, 1
0x18000afcd  jz      short loc_18000AFED
0x18000afcf  cmp     byte ptr [rcx+29h], 2
0x18000afd3  jb      short loc_18000AFED
0x18000afd5  mov     rcx, [rcx+18h]
0x18000afd9  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000afe0  mov     edx, 1Fh
0x18000afe5  mov     r9d, r14d
0x18000afe8  call    WPP_SF_D
0x18000afed  test    r12b, r12b
0x18000aff0  jz      loc_18000B0CB
0x18000aff6  jmp     short loc_18000B013
0x18000aff8  call    cs:__imp_ExReleaseResourceLite
0x18000afff  nop     dword ptr [rax+rax+00h]
0x18000b004  call    cs:__imp_KeLeaveCriticalRegion
0x18000b00b  nop     dword ptr [rax+rax+00h]
0x18000b010  xor     bpl, bpl
0x18000b013  mov     rcx, rsi
0x18000b016  call    DereferenceVolumeContext
0x18000b01b  mov     qword ptr [rbx+rdi*8+10h], 0
0x18000b024  lea     rsi, WPP_GLOBAL_Control
0x18000b02b  jmp     loc_18000B0B1
0x18000b030  test    al, 2
0x18000b032  jz      short loc_18000B0B1
0x18000b034  mov     rax, [rbx+rdi*8+10h]
0x18000b039  cmp     rax, r13
0x18000b03c  jz      short loc_18000B0B1
0x18000b03e  test    rax, rax
0x18000b041  jz      short loc_18000B0B1
0x18000b043  test    bpl, bpl
0x18000b046  jz      short loc_18000B06A
0x18000b048  lea     rcx, Resource; Resource
0x18000b04f  call    cs:__imp_ExReleaseResourceLite
0x18000b056  nop     dword ptr [rax+rax+00h]
0x18000b05b  call    cs:__imp_KeLeaveCriticalRegion
0x18000b062  nop     dword ptr [rax+rax+00h]
0x18000b067  xor     bpl, bpl
0x18000b06a  mov     rcx, [rbx+rdi*8+10h]; P
0x18000b06f  call    DepFSDismountDependency
0x18000b074  mov     r14d, eax
0x18000b077  test    eax, eax
0x18000b079  jns     short loc_18000B0B1
0x18000b07b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b082  cmp     rcx, rsi
0x18000b085  jz      short loc_18000B0AC
0x18000b087  mov     eax, [rcx+2Ch]
0x18000b08a  test    al, 1
0x18000b08c  jz      short loc_18000B0AC
0x18000b08e  cmp     byte ptr [rcx+29h], 2
0x18000b092  jb      short loc_18000B0AC
0x18000b094  mov     rcx, [rcx+18h]
0x18000b098  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b09f  mov     edx, 20h ; ' '
0x18000b0a4  mov     r9d, r14d
0x18000b0a7  call    WPP_SF_D
0x18000b0ac  test    r12b, r12b
0x18000b0af  jz      short loc_18000B0C6
0x18000b0b1  inc     r15d
0x18000b0b4  cmp     r15d, [rbx+4]
0x18000b0b8  jb      loc_18000AF30
0x18000b0be  jmp     short loc_18000B0C6
0x18000b0c0  mov     r14d, 0C0000022h
0x18000b0c6  test    bpl, bpl
0x18000b0c9  jnz     short loc_18000B0F0
0x18000b0cb  mov     bpl, 1
0x18000b0ce  call    cs:__imp_KeEnterCriticalRegion
0x18000b0d5  nop     dword ptr [rax+rax+00h]
0x18000b0da  mov     dl, bpl; Wait
0x18000b0dd  lea     rcx, Resource; Resource
0x18000b0e4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000b0eb  nop     dword ptr [rax+rax+00h]
0x18000b0f0  xor     esi, esi
0x18000b0f2  xor     r15d, r15d
0x18000b0f5  cmp     [rbx+4], r15d
0x18000b0f9  jbe     short loc_18000B15B
0x18000b0fb  mov     edi, esi
0x18000b0fd  add     rdi, rdi
0x18000b100  movzx   ecx, word ptr [rbx+rdi*8+8]
0x18000b105  test    cl, 2
0x18000b108  jz      short loc_18000B134
0x18000b10a  mov     rax, [rbx+rdi*8+10h]
0x18000b10f  test    rax, rax
0x18000b112  jz      short loc_18000B134
0x18000b114  bt      cx, 8
0x18000b119  jnb     short loc_18000B11F
0x18000b11b  lock dec dword ptr [rax+60h]
0x18000b11f  mov     rcx, [rbx+rdi*8+10h]; P
0x18000b124  xor     r8d, r8d
0x18000b127  mov     dl, bpl
0x18000b12a  call    DereferenceDependencyContext
0x18000b12f  mov     [rbx+rdi*8+10h], r15
0x18000b134  test    byte ptr [rbx+rdi*8+8], 1
0x18000b139  jz      short loc_18000B14F
0x18000b13b  mov     rcx, [rbx+rdi*8+10h]
0x18000b140  test    rcx, rcx
0x18000b143  jz      short loc_18000B14F
0x18000b145  call    DereferenceVolumeContext
0x18000b14a  mov     [rbx+rdi*8+10h], r15
0x18000b14f  inc     esi
0x18000b151  cmp     esi, [rbx+4]
0x18000b154  jb      short loc_18000B0FB
0x18000b156  test    bpl, bpl
0x18000b159  jz      short loc_18000B17A
0x18000b15b  lea     rcx, Resource; Resource
0x18000b162  call    cs:__imp_ExReleaseResourceLite
0x18000b169  nop     dword ptr [rax+rax+00h]
0x18000b16e  call    cs:__imp_KeLeaveCriticalRegion
0x18000b175  nop     dword ptr [rax+rax+00h]
0x18000b17a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b181  lea     rax, WPP_GLOBAL_Control
0x18000b188  cmp     rcx, rax
0x18000b18b  jz      short loc_18000B1B7
0x18000b18d  mov     eax, [rcx+2Ch]
0x18000b190  test    al, 10h
0x18000b192  jz      short loc_18000B1B7
0x18000b194  cmp     byte ptr [rcx+29h], 4
0x18000b198  jb      short loc_18000B1B7
0x18000b19a  mov     rcx, [rcx+18h]
0x18000b19e  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b1a5  mov     edx, 21h ; '!'
0x18000b1aa  mov     [rsp+78h+var_58], r14d
0x18000b1af  mov     r9, rbx
0x18000b1b2  call    WPP_SF_qD
0x18000b1b7  mov     eax, r14d
0x18000b1ba  add     rsp, 38h
0x18000b1be  pop     r15
0x18000b1c0  pop     r14
0x18000b1c2  pop     r13
0x18000b1c4  pop     r12
0x18000b1c6  pop     rdi
0x18000b1c7  pop     rsi
0x18000b1c8  pop     rbp
0x18000b1c9  pop     rbx
0x18000b1ca  retn
```
