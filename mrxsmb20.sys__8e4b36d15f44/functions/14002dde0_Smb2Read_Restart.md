# Smb2Read_Restart

- ea: `0x14002dde0`
- end: `0x14002e1dc`
- name: `Smb2Read_Restart`
- size: `1020`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x14001a6e0`
- `0x14001a8d0`
- `0x1400287a0`
- `0x140029cb0`
- `0x14002dde0`
- `0x14002e258`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002defa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002defa`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x14002dfd1`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x14002dfd1`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14002dee1`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14002dee1`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002df32`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002df61`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002df32`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002df61`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14002e13f`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14002e13f`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x14002e018`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x14002e018`

## pseudocode

```c
__int64 __fastcall Smb2Read_Restart(__int64 a1)
{
  __int64 v1; // rbp
  char v2; // r12
  __int64 v3; // rdi
  __int64 v5; // r13
  unsigned int v6; // esi
  __int64 v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r14
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rdx
  int BufferDescriptors; // edi
  char v18; // r13
  unsigned int v19; // r15d
  ULONG Length; // ebp
  int v21; // ecx
  unsigned __int64 v22; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // rax
  __int64 v25; // rdx
  char v26; // r14
  __int64 v28; // [rsp+50h] [rbp-58h]
  unsigned __int16 v29; // [rsp+B0h] [rbp+8h] BYREF
  int v30; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v31; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v32; // [rsp+C8h] [rbp+20h]

  v1 = *(_QWORD *)(a1 + 48);
  v2 = 0;
  v3 = *(_QWORD *)(a1 + 2464);
  v31 = v1;
  v28 = *(_QWORD *)(*(_QWORD *)(v1 + 72) + 48LL);
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL);
  v30 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      (unsigned int)WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
      v1,
      a1,
      *(_QWORD *)(v1 + 56) + 360LL);
  }
  if ( v3 )
  {
    v6 = *(_DWORD *)(v3 + 12);
  }
  else
  {
    v6 = *(_DWORD *)(v1 + 568);
    v3 = v1 + 560;
  }
  v7 = *(_QWORD *)v3;
  v8 = *(_QWORD *)(a1 + 160);
  v32 = *(_QWORD *)v3;
  v9 = v8 - 8;
  if ( v8 == a1 + 160 )
    v9 = 0;
  if ( v9 )
  {
    do
    {
      v10 = *(_QWORD *)(v9 + 8);
      v11 = 0;
      if ( v10 != a1 + 160 )
        v11 = v10 - 8;
      ProcessChunkAndUpdateBlockState_0(a1, (_DWORD *)v9);
      SmbCseFinalizeBufferContext(v9);
      if ( v9 == a1 + 1056 )
        *(_BYTE *)(a1 + 1052) = 0;
      else
        ExFreePoolWithTag((PVOID)v9, 0x6D536352u);
      v9 = v11;
    }
    while ( v11 );
    v1 = v31;
    v2 = 0;
    v7 = v32;
  }
  v31 = 0;
  if ( *(_DWORD *)MRxSmbGetConfigurationBlock(v8)
    && (unsigned int)(*(_DWORD *)(v5 + 320) - 2) <= 1
    && v6 >= *(_DWORD *)MRxSmbGetConfigurationBlock(v13)
    && ((*(_DWORD *)(a1 + 68) & 0x1000000) == 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 748LL) & 1) != 0)
    && (*(_DWORD *)(a1 + 68) & 0x800) == 0
    && !*(_QWORD *)(a1 + 56) )
  {
    v15 = v6;
    if ( v6 > 0x10000 )
      v15 = 0x10000;
    LOBYTE(v14) = (*(_BYTE *)(*(_QWORD *)(a1 + 72) + 736LL) & 0x40) != 0;
    SmbCseEstimateMemoryDescriptorSize(v5, v15, v14, 0, &v29, &v30);
  }
  LOBYTE(v12) = v29 != 0;
  BufferDescriptors = AllocateReadBufferDescriptors(a1, v12);
  if ( BufferDescriptors < 0 )
    return (unsigned int)BufferDescriptors;
  v18 = 0;
  if ( (*(_DWORD *)(v1 + 120) & 0x1000000) != 0 )
  {
    LOWORD(v16) = 3;
    if ( (unsigned __int8)SmbCeCheckServerEntryDialect(*(_QWORD *)(a1 + 72), v16, 0, 2) )
      v2 = 1;
  }
  v19 = 0;
  if ( !v6 )
    return (unsigned int)BufferDescriptors;
  while ( 1 )
  {
    Length = v6;
    if ( v6 > 0x10000 )
      Length = 0x10000;
    v21 = *(_DWORD *)(a1 + 8 * ((unsigned __int64)v19 >> 16) + 2496);
    if ( v21 == -1 )
      break;
    v22 = (unsigned int)(v21 + 1073741667);
    if ( (unsigned int)v22 <= 0x2F )
    {
      v23 = 0x900281000001LL;
      if ( _bittest64(&v23, v22) )
        break;
    }
    v24 = (unsigned int)(v21 + 1073741309);
    if ( (unsigned int)v24 <= 0x3E )
    {
      v25 = 0x4208040000000601LL;
      if ( _bittest64(&v25, v24) )
        break;
    }
    if ( v21 == -1073740964
      || v21 == -1073741507
      || (unsigned int)(v21 + 1073740698) <= 1
      || v21 == -1073740672
      || v21 == -2146893022
      || v21 == -1073741073
      || v21 == -2147483631
      || v21 == -1073741810
      || v21 == -1073741202
      || v21 == -1069481983 )
    {
      break;
    }
LABEL_53:
    v7 = v32;
    v19 += Length;
    v6 -= Length;
    if ( !v6 )
      goto LABEL_59;
  }
  BufferDescriptors = Smb2Read_BuildChunk(&v31, a1, (__int128 *)(v28 + 28), v7, v19, Length, v30, v29, v2);
  if ( BufferDescriptors < 0 )
    goto LABEL_59;
  v26 = v31;
  BufferDescriptors = SmbCseSubmitBufferContext(v31);
  if ( BufferDescriptors >= 0 )
  {
    v18 = 1;
    if ( *(_BYTE *)(a1 + 1040) == 1 )
      return 259;
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_DiqD(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      (unsigned int)WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
      Length,
      v19,
      v26,
      BufferDescriptors);
  }
LABEL_59:
  if ( v18 != 1 )
    return (unsigned int)BufferDescriptors;
  return 259;
}

```

## disassembly

```asm
0x14002dde0  mov     r11, rsp
0x14002dde3  push    rbx
0x14002dde4  push    rbp
0x14002dde5  push    rsi
0x14002dde6  push    rdi
0x14002dde7  push    r12
0x14002dde9  push    r13
0x14002ddeb  push    r14
0x14002dded  push    r15
0x14002ddef  sub     rsp, 68h
0x14002ddf3  mov     rbp, [rcx+30h]
0x14002ddf7  xor     r12d, r12d
0x14002ddfa  mov     rdi, [rcx+9A0h]
0x14002de01  mov     rbx, rcx
0x14002de04  mov     [rsp+0A8h+arg_10], rbp
0x14002de0c  mov     rax, [rbp+48h]
0x14002de10  mov     rax, [rax+30h]
0x14002de14  mov     [rsp+0A8h+var_58], rax
0x14002de19  mov     rax, [rcx+60h]
0x14002de1d  mov     r13, [rax+188h]
0x14002de24  mov     [r11+10h], r12d
0x14002de28  mov     [r11+8], r12w
0x14002de2d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002de34  lea     rax, WPP_GLOBAL_Control
0x14002de3b  lea     edx, [r12+1]
0x14002de40  cmp     rcx, rax
0x14002de43  jz      short loc_14002DE7C
0x14002de45  mov     eax, [rcx+2Ch]
0x14002de48  test    dl, al
0x14002de4a  jz      short loc_14002DE7C
0x14002de4c  cmp     [rcx+29h], dl
0x14002de4f  jb      short loc_14002DE7C
0x14002de51  mov     rax, [rbp+38h]
0x14002de55  lea     edx, [r12+13h]
0x14002de5a  mov     rcx, [rcx+18h]
0x14002de5e  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14002de65  add     rax, 168h
0x14002de6b  mov     r9, rbp
0x14002de6e  mov     [r11-80h], rax
0x14002de72  mov     qword ptr [rsp+0A8h+var_88], rbx
0x14002de77  call    WPP_SF_qqZ
0x14002de7c  test    rdi, rdi
0x14002de7f  jz      short loc_14002DE86
0x14002de81  mov     esi, [rdi+0Ch]
0x14002de84  jmp     short loc_14002DE93
0x14002de86  mov     esi, [rbp+238h]
0x14002de8c  lea     rdi, [rbp+230h]
0x14002de93  mov     r14, [rdi]
0x14002de96  lea     r15, [rbx+0A0h]
0x14002de9d  mov     rcx, [r15]
0x14002dea0  cmp     rcx, r15
0x14002dea3  mov     [rsp+0A8h+arg_18], r14
0x14002deab  lea     rdi, [rcx-8]
0x14002deaf  cmovz   rdi, r12
0x14002deb3  test    rdi, rdi
0x14002deb6  jz      short loc_14002DF2A
0x14002deb8  lea     r12, [rbx+420h]
0x14002debf  xor     ebp, ebp
0x14002dec1  mov     rdx, [rdi+8]
0x14002dec5  mov     r14, rbp
0x14002dec8  cmp     rdx, r15
0x14002decb  mov     rcx, rbx
0x14002dece  lea     rax, [rdx-8]
0x14002ded2  mov     rdx, rdi
0x14002ded5  cmovnz  r14, rax
0x14002ded9  call    ProcessChunkAndUpdateBlockState_0
0x14002dede  mov     rcx, rdi
0x14002dee1  call    cs:__imp_SmbCseFinalizeBufferContext
0x14002dee8  nop     dword ptr [rax+rax+00h]
0x14002deed  cmp     rdi, r12
0x14002def0  jz      short loc_14002DF08
0x14002def2  mov     edx, 6D536352h; Tag
0x14002def7  mov     rcx, rdi; P
0x14002defa  call    cs:__imp_ExFreePoolWithTag
0x14002df01  nop     dword ptr [rax+rax+00h]
0x14002df06  jmp     short loc_14002DF0F
0x14002df08  mov     [rbx+41Ch], bpl
0x14002df0f  mov     rdi, r14
0x14002df12  test    r14, r14
0x14002df15  jnz     short loc_14002DEC1
0x14002df17  mov     rbp, [rsp+0A8h+arg_10]
0x14002df1f  xor     r12d, r12d
0x14002df22  mov     r14, [rsp+0A8h+arg_18]
0x14002df2a  mov     [rsp+0A8h+arg_10], r12
0x14002df32  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002df39  nop     dword ptr [rax+rax+00h]
0x14002df3e  mov     edi, 10000h
0x14002df43  mov     r15d, 1
0x14002df49  cmp     [rax], r12d
0x14002df4c  jbe     loc_14002DFDD
0x14002df52  mov     eax, [r13+140h]
0x14002df59  sub     eax, 2
0x14002df5c  cmp     eax, r15d
0x14002df5f  ja      short loc_14002DFDD
0x14002df61  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002df68  nop     dword ptr [rax+rax+00h]
0x14002df6d  cmp     esi, [rax]
0x14002df6f  jb      short loc_14002DFDD
0x14002df71  mov     eax, [rbx+44h]
0x14002df74  bt      eax, 18h
0x14002df78  jnb     short loc_14002DF89
0x14002df7a  mov     rax, [rbx+48h]
0x14002df7e  mov     ecx, [rax+2ECh]
0x14002df84  test    r15b, cl
0x14002df87  jz      short loc_14002DFDD
0x14002df89  mov     eax, [rbx+44h]
0x14002df8c  bt      eax, 0Bh
0x14002df90  jb      short loc_14002DFDD
0x14002df92  cmp     [rbx+38h], r12
0x14002df96  jnz     short loc_14002DFDD
0x14002df98  mov     rax, [rbx+48h]
0x14002df9c  cmp     esi, edi
0x14002df9e  mov     edx, esi
0x14002dfa0  mov     rcx, r13
0x14002dfa3  cmova   edx, edi
0x14002dfa6  xor     r9d, r9d
0x14002dfa9  mov     r8b, [rax+2E0h]
0x14002dfb0  lea     rax, [rsp+0A8h+arg_8]
0x14002dfb8  mov     qword ptr [rsp+0A8h+Length], rax
0x14002dfbd  lea     rax, [rsp+0A8h+arg_0]
0x14002dfc5  shr     r8b, 6
0x14002dfc9  and     r8b, r15b
0x14002dfcc  mov     qword ptr [rsp+0A8h+var_88], rax
0x14002dfd1  call    cs:__imp_SmbCseEstimateMemoryDescriptorSize
0x14002dfd8  nop     dword ptr [rax+rax+00h]
0x14002dfdd  cmp     [rsp+0A8h+arg_0], r12w
0x14002dfe6  mov     rcx, rbx
0x14002dfe9  setnz   dl
0x14002dfec  call    AllocateReadBufferDescriptors
0x14002dff1  mov     edi, eax
0x14002dff3  test    eax, eax
0x14002dff5  js      loc_14002E1C8
0x14002dffb  test    dword ptr [rbp+78h], 1000000h
0x14002e002  mov     r13b, r12b
0x14002e005  jz      short loc_14002E02A
0x14002e007  mov     rcx, [rbx+48h]
0x14002e00b  mov     r9d, 2
0x14002e011  xor     r8d, r8d
0x14002e014  mov     dx, 3
0x14002e018  call    cs:__imp_SmbCeCheckServerEntryDialect
0x14002e01f  nop     dword ptr [rax+rax+00h]
0x14002e024  test    al, al
0x14002e026  cmovnz  r12d, r15d
0x14002e02a  xor     eax, eax
0x14002e02c  mov     r15d, eax
0x14002e02f  test    esi, esi
0x14002e031  jz      loc_14002E1C8
0x14002e037  mov     eax, 10000h
0x14002e03c  mov     ebp, esi
0x14002e03e  cmp     esi, eax
0x14002e040  cmova   ebp, eax
0x14002e043  mov     eax, r15d
0x14002e046  mov     [rsp+0A8h+var_50], rax
0x14002e04b  shr     rax, 10h
0x14002e04f  mov     ecx, [rbx+rax*8+9C0h]
0x14002e056  cmp     ecx, 0FFFFFFFFh
0x14002e059  jz      loc_14002E0E8
0x14002e05f  lea     eax, [rcx+3FFFFF63h]
0x14002e065  cmp     eax, 2Fh ; '/'
0x14002e068  ja      short loc_14002E07A
0x14002e06a  mov     rdx, 900281000001h
0x14002e074  bt      rdx, rax
0x14002e078  jb      short loc_14002E0E8
0x14002e07a  lea     eax, [rcx+3FFFFDFDh]
0x14002e080  cmp     eax, 3Eh ; '>'
0x14002e083  ja      short loc_14002E095
0x14002e085  mov     rdx, 4208040000000601h
0x14002e08f  bt      rdx, rax
0x14002e093  jb      short loc_14002E0E8
0x14002e095  cmp     ecx, 0C000035Ch
0x14002e09b  jz      short loc_14002E0E8
0x14002e09d  cmp     ecx, 0C000013Dh
0x14002e0a3  jz      short loc_14002E0E8
0x14002e0a5  lea     eax, [rcx+3FFFFB9Ah]
0x14002e0ab  cmp     eax, 1
0x14002e0ae  jbe     short loc_14002E0E8
0x14002e0b0  cmp     ecx, 0C0000480h
0x14002e0b6  jz      short loc_14002E0E8
0x14002e0b8  cmp     ecx, 80090322h
0x14002e0be  jz      short loc_14002E0E8
0x14002e0c0  cmp     ecx, 0C00002EFh
0x14002e0c6  jz      short loc_14002E0E8
0x14002e0c8  cmp     ecx, 80000011h
0x14002e0ce  jz      short loc_14002E0E8
0x14002e0d0  cmp     ecx, 0C000000Eh
0x14002e0d6  jz      short loc_14002E0E8
0x14002e0d8  cmp     ecx, 0C000026Eh
0x14002e0de  jz      short loc_14002E0E8
0x14002e0e0  cmp     ecx, 0C0410001h
0x14002e0e6  jnz     short loc_14002E15D
0x14002e0e8  movzx   eax, [rsp+0A8h+arg_0]
0x14002e0f0  lea     rcx, [rsp+0A8h+arg_10]; int
0x14002e0f8  mov     r8, [rsp+0A8h+var_58]
0x14002e0fd  mov     r9, r14; int
0x14002e100  mov     [rsp+0A8h+var_68], r12d; int
0x14002e105  add     r8, 1Ch; int
0x14002e109  mov     [rsp+0A8h+var_70], ax; __int16
0x14002e10e  mov     rdx, rbx; int
0x14002e111  mov     eax, [rsp+0A8h+arg_8]
0x14002e118  mov     [rsp+0A8h+var_78], eax; int
0x14002e11c  mov     [rsp+0A8h+Length], ebp; Length
0x14002e120  mov     [rsp+0A8h+var_88], r15d; int
0x14002e125  call    Smb2Read_BuildChunk
0x14002e12a  mov     edi, eax
0x14002e12c  test    eax, eax
0x14002e12e  js      loc_14002E1BD
0x14002e134  mov     r14, [rsp+0A8h+arg_10]
0x14002e13c  mov     rcx, r14
0x14002e13f  call    cs:__imp_SmbCseSubmitBufferContext
0x14002e146  nop     dword ptr [rax+rax+00h]
0x14002e14b  mov     edi, eax
0x14002e14d  test    eax, eax
0x14002e14f  js      short loc_14002E172
0x14002e151  mov     r13b, 1
0x14002e154  cmp     [rbx+410h], r13b
0x14002e15b  jz      short loc_14002E1C3
0x14002e15d  mov     r14, [rsp+0A8h+arg_18]
0x14002e165  add     r15d, ebp
0x14002e168  sub     esi, ebp
0x14002e16a  jnz     loc_14002E037
0x14002e170  jmp     short loc_14002E1BD
0x14002e172  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e179  lea     rax, WPP_GLOBAL_Control
0x14002e180  cmp     rcx, rax
0x14002e183  jz      short loc_14002E1BD
0x14002e185  mov     eax, [rcx+2Ch]
0x14002e188  test    al, 1
0x14002e18a  jz      short loc_14002E1BD
0x14002e18c  cmp     byte ptr [rcx+29h], 1
0x14002e190  jb      short loc_14002E1BD
0x14002e192  mov     rax, [rsp+0A8h+var_50]
0x14002e197  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14002e19e  mov     rcx, [rcx+18h]
0x14002e1a2  mov     edx, 14h
0x14002e1a7  mov     [rsp+0A8h+var_78], edi
0x14002e1ab  mov     r9d, ebp
0x14002e1ae  mov     qword ptr [rsp+0A8h+Length], r14
0x14002e1b3  mov     qword ptr [rsp+0A8h+var_88], rax
0x14002e1b8  call    WPP_SF_DiqD
0x14002e1bd  cmp     r13b, 1
0x14002e1c1  jnz     short loc_14002E1C8
0x14002e1c3  mov     edi, 103h
0x14002e1c8  mov     eax, edi
0x14002e1ca  add     rsp, 68h
0x14002e1ce  pop     r15
0x14002e1d0  pop     r14
0x14002e1d2  pop     r13
0x14002e1d4  pop     r12
0x14002e1d6  pop     rdi
0x14002e1d7  pop     rsi
0x14002e1d8  pop     rbp
0x14002e1d9  pop     rbx
0x14002e1da  retn
```
