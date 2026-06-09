# Smb2Read_TurboStart

- ea: `0x14001e550`
- end: `0x14001e89d`
- name: `Smb2Read_TurboStart`
- size: `845`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14001e550`
- `0x1400297fc`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14001e69e`
- `ntoskrnl!IoBuildPartialMdl` at `0x14001e69e`
- `rdbss!RxAllocateMdl2` at `0x14001e675`
- `rdbss!RxAllocateMdl2` at `0x14001e675`
- `rdbss!RxLowIoGetBufferAddress` at `0x14001e7ed`
- `rdbss!RxLowIoGetBufferAddress` at `0x14001e7ed`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x14001e761`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x14001e761`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001e5b7`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001e5b7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e5c3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e5d4`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e5c3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e5d4`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001e7b1`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001e7b1`

## pseudocode

```c
__int64 __fastcall Smb2Read_TurboStart(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rbx
  __int64 v3; // r14
  bool v4; // r13
  __int64 v6; // r12
  __int64 v7; // rcx
  __int64 v8; // rcx
  ULONG v9; // esi
  struct _MDL *v10; // rbp
  struct _MDL *Mdl2; // rax
  struct _MDL *v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rbp
  __int16 v17; // ax
  PVOID BufferAddress; // rax

  v1 = *(_QWORD *)(a1 + 160);
  v2 = 0;
  v3 = *(_QWORD *)(a1 + 48);
  v4 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL);
  if ( v1 != a1 + 160 )
    v2 = v1 - 8;
  if ( *(_QWORD *)(a1 + 56) )
    __int2c();
  if ( (*(_DWORD *)(a1 + 68) & 0x1000000) != 0 )
    __int2c();
  if ( (*(_DWORD *)(a1 + 68) & 0x800) != 0 )
    __int2c();
  LOBYTE(v1) = 39;
  RDR_PERF_ENTER(a1 + 512, v1);
  if ( *(_DWORD *)MRxSmbGetConfigurationBlock(v7)
    && *(_DWORD *)(v3 + 568) >= *(_DWORD *)MRxSmbGetConfigurationBlock(v8)
    && *(_DWORD *)(v6 + 320) == 2 )
  {
    v4 = *(_WORD *)(v2 + 784) >= 0x410u;
  }
  v9 = *(_DWORD *)(v3 + 568);
  if ( v9 > 0x10000 )
    __int2c();
  if ( *(_DWORD *)(v2 + 1388) != 1 )
    __int2c();
  if ( *(_DWORD *)(v2 + 1384) )
    __int2c();
  if ( *(_DWORD *)(v2 + 1392) )
    __int2c();
  *(_DWORD *)(v2 + 1396) = v9;
  if ( *(_QWORD *)(a1 + 1024) )
    __int2c();
  if ( *(_QWORD *)(a1 + 1032) )
    __int2c();
  v10 = *(struct _MDL **)(v3 + 544);
  Mdl2 = (struct _MDL *)RxAllocateMdl2((char *)v10->StartVa + v10->ByteOffset, v9, 0, 0, 0);
  v12 = Mdl2;
  if ( !Mdl2 )
    return 3221225626LL;
  IoBuildPartialMdl(v10, Mdl2, (char *)v10->StartVa + v10->ByteOffset, v9);
  v13 = *(_QWORD *)(v2 + 96);
  v14 = *(_QWORD *)(v2 + 88);
  *(_DWORD *)(v2 + 748) = 0;
  *(_DWORD *)(v2 + 744) = v9;
  *(_QWORD *)(v13 + 24) = v14;
  *(_QWORD *)(*(_QWORD *)(v2 + 96) + 32LL) = *(_QWORD *)(v2 + 88) & 0xFFFFFFFFFFFFF000uLL;
  *(_DWORD *)(*(_QWORD *)(v2 + 96) + 44LL) = *(_DWORD *)(v2 + 88) & 0xFFF;
  *(_DWORD *)(*(_QWORD *)(v2 + 96) + 40LL) = 113;
  if ( !v4 )
  {
    *(_DWORD *)(v2 + 728) = 113;
    *(_QWORD *)(v2 + 720) = v12;
    BufferAddress = RxLowIoGetBufferAddress((PRX_CONTEXT)v3);
    *(_QWORD *)(v2 + 712) = BufferAddress;
    if ( BufferAddress )
      goto LABEL_28;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids, a1);
    }
    return 3221225626LL;
  }
  v15 = *(unsigned __int16 *)(v2 + 784);
  *(_DWORD *)(v2 + 776) = v9;
  *(_DWORD *)(v2 + 728) = v15 + 113;
  *(_QWORD *)(v2 + 768) = v12;
LABEL_28:
  v16 = *(_QWORD *)(v2 + 88);
  *(_QWORD *)(v16 + 72) = *(_QWORD *)(v3 + 560);
  *(_DWORD *)(v16 + 68) = v9;
  if ( v4 )
  {
    SmbCseEstimateMemoryDescriptorSize(
      v6,
      v9,
      (*(_BYTE *)(*(_QWORD *)(a1 + 72) + 736LL) & 0x40) != 0,
      0,
      v16 + 110,
      v16 + 100);
    *(_WORD *)(v16 + 108) = 112;
    v17 = *(_WORD *)(v2 + 784);
  }
  else
  {
    *(_DWORD *)(v16 + 100) = 0;
    v17 = 0;
    *(_WORD *)(v16 + 108) = 0;
  }
  *(_WORD *)(v16 + 110) = v17;
  _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                  * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                 % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL)
                                                                             + 1488LL))
                                                  + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                  + 120));
  return SmbCseSubmitBufferContext(v2);
}

```

## disassembly

```asm
0x14001e550  push    rbx
0x14001e552  push    rbp
0x14001e553  push    rsi
0x14001e554  push    rdi
0x14001e555  push    r12
0x14001e557  push    r13
0x14001e559  push    r14
0x14001e55b  push    r15
0x14001e55d  sub     rsp, 38h
0x14001e561  mov     rax, [rcx+60h]
0x14001e565  lea     r8, [rcx+0A0h]
0x14001e56c  mov     rdx, [r8]
0x14001e56f  xor     ebx, ebx
0x14001e571  mov     r14, [rcx+30h]
0x14001e575  xor     r13b, r13b
0x14001e578  cmp     rdx, r8
0x14001e57b  mov     rdi, rcx
0x14001e57e  mov     r12, [rax+188h]
0x14001e585  lea     rax, [rdx-8]
0x14001e589  cmovnz  rbx, rax
0x14001e58d  cmp     qword ptr [rcx+38h], 0
0x14001e592  jnz     loc_14001E80C
0x14001e598  mov     eax, [rcx+44h]
0x14001e59b  bt      eax, 18h
0x14001e59f  jnb     short loc_14001E5A3
0x14001e5a1  int     2Ch; Windows NT - assertion failure
0x14001e5a3  mov     eax, [rcx+44h]
0x14001e5a6  bt      eax, 0Bh
0x14001e5aa  jnb     short loc_14001E5AE
0x14001e5ac  int     2Ch; Windows NT - assertion failure
0x14001e5ae  add     rcx, 200h
0x14001e5b5  mov     dl, 27h ; '''
0x14001e5b7  call    cs:__imp_RDR_PERF_ENTER
0x14001e5be  nop     dword ptr [rax+rax+00h]
0x14001e5c3  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001e5ca  nop     dword ptr [rax+rax+00h]
0x14001e5cf  cmp     dword ptr [rax], 0
0x14001e5d2  jbe     short loc_14001E5FA
0x14001e5d4  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001e5db  nop     dword ptr [rax+rax+00h]
0x14001e5e0  mov     ecx, [rax]
0x14001e5e2  cmp     [r14+238h], ecx
0x14001e5e9  jb      short loc_14001E5FA
0x14001e5eb  cmp     dword ptr [r12+140h], 2
0x14001e5f4  jz      loc_14001E813
0x14001e5fa  mov     esi, [r14+238h]
0x14001e601  cmp     esi, 10000h
0x14001e607  ja      loc_14001E831
0x14001e60d  cmp     dword ptr [rbx+56Ch], 1
0x14001e614  jnz     loc_14001E838
0x14001e61a  cmp     dword ptr [rbx+568h], 0
0x14001e621  jnz     loc_14001E83F
0x14001e627  cmp     dword ptr [rbx+570h], 0
0x14001e62e  jnz     loc_14001E846
0x14001e634  mov     [rbx+574h], esi
0x14001e63a  cmp     qword ptr [rdi+400h], 0
0x14001e642  jnz     loc_14001E84D
0x14001e648  cmp     qword ptr [rdi+408h], 0
0x14001e650  jnz     loc_14001E854
0x14001e656  mov     rbp, [r14+220h]
0x14001e65d  xor     r9d, r9d
0x14001e660  xor     r8d, r8d
0x14001e663  mov     [rsp+78h+var_58], 0
0x14001e66c  mov     edx, esi
0x14001e66e  mov     ecx, [rbp+2Ch]
0x14001e671  add     rcx, [rbp+20h]
0x14001e675  call    cs:__imp_RxAllocateMdl2
0x14001e67c  nop     dword ptr [rax+rax+00h]
0x14001e681  mov     r15, rax
0x14001e684  test    rax, rax
0x14001e687  jz      loc_14001E893
0x14001e68d  mov     r8d, [rbp+2Ch]
0x14001e691  mov     r9d, esi; Length
0x14001e694  add     r8, [rbp+20h]; VirtualAddress
0x14001e698  mov     rdx, rax; TargetMdl
0x14001e69b  mov     rcx, rbp; SourceMdl
0x14001e69e  call    cs:__imp_IoBuildPartialMdl
0x14001e6a5  nop     dword ptr [rax+rax+00h]
0x14001e6aa  mov     rcx, [rbx+60h]
0x14001e6ae  xor     edx, edx
0x14001e6b0  mov     rax, [rbx+58h]
0x14001e6b4  mov     [rbx+2ECh], edx
0x14001e6ba  mov     [rbx+2E8h], esi
0x14001e6c0  mov     [rcx+18h], rax
0x14001e6c4  mov     rax, [rbx+60h]
0x14001e6c8  mov     rcx, [rbx+58h]
0x14001e6cc  and     rcx, 0FFFFFFFFFFFFF000h
0x14001e6d3  mov     [rax+20h], rcx
0x14001e6d7  mov     rax, [rbx+60h]
0x14001e6db  mov     ecx, [rbx+58h]
0x14001e6de  and     ecx, 0FFFh
0x14001e6e4  mov     [rax+2Ch], ecx
0x14001e6e7  mov     rax, [rbx+60h]
0x14001e6eb  mov     dword ptr [rax+28h], 71h ; 'q'
0x14001e6f2  test    r13b, r13b
0x14001e6f5  jz      loc_14001E7D9
0x14001e6fb  movzx   eax, word ptr [rbx+310h]
0x14001e702  add     eax, 71h ; 'q'
0x14001e705  mov     [rbx+308h], esi
0x14001e70b  mov     [rbx+2D8h], eax
0x14001e711  mov     [rbx+300h], r15
0x14001e718  mov     rbp, [rbx+58h]
0x14001e71c  mov     rax, [r14+230h]
0x14001e723  mov     [rbp+48h], rax
0x14001e727  lea     rcx, [rbp+64h]
0x14001e72b  mov     [rbp+44h], esi
0x14001e72e  lea     r14, [rbp+6Eh]
0x14001e732  test    r13b, r13b
0x14001e735  jz      loc_14001E7CF
0x14001e73b  mov     rax, [rdi+48h]
0x14001e73f  xor     r9d, r9d
0x14001e742  mov     [rsp+78h+var_50], rcx
0x14001e747  mov     edx, esi
0x14001e749  mov     rcx, r12
0x14001e74c  mov     [rsp+78h+var_58], r14
0x14001e751  movzx   r8d, byte ptr [rax+2E0h]
0x14001e759  shr     r8b, 6
0x14001e75d  and     r8b, 1
0x14001e761  call    cs:__imp_SmbCseEstimateMemoryDescriptorSize
0x14001e768  nop     dword ptr [rax+rax+00h]
0x14001e76d  mov     word ptr [rbp+6Ch], 70h ; 'p'
0x14001e773  movzx   eax, word ptr [rbx+310h]
0x14001e77a  mov     [r14], ax
0x14001e77e  xor     edx, edx
0x14001e780  mov     rax, [rdi+58h]
0x14001e784  mov     r8, [rax+1A8h]
0x14001e78b  mov     eax, gs:1A4h
0x14001e793  div     dword ptr [r8+5D0h]
0x14001e79a  mov     rax, [r8+5C8h]
0x14001e7a1  lea     rdx, [rdx+rdx*2]
0x14001e7a5  shl     rdx, 6
0x14001e7a9  lock inc dword ptr [rdx+rax+78h]
0x14001e7ae  mov     rcx, rbx
0x14001e7b1  call    cs:__imp_SmbCseSubmitBufferContext
0x14001e7b8  nop     dword ptr [rax+rax+00h]
0x14001e7bd  add     rsp, 38h
0x14001e7c1  pop     r15
0x14001e7c3  pop     r14
0x14001e7c5  pop     r13
0x14001e7c7  pop     r12
0x14001e7c9  pop     rdi
0x14001e7ca  pop     rsi
0x14001e7cb  pop     rbp
0x14001e7cc  pop     rbx
0x14001e7cd  retn
0x14001e7cf  mov     [rcx], edx
0x14001e7d1  mov     eax, edx
0x14001e7d3  mov     [rbp+6Ch], dx
0x14001e7d7  jmp     short loc_14001E77A
0x14001e7d9  mov     rcx, r14; RxContext
0x14001e7dc  mov     dword ptr [rbx+2D8h], 71h ; 'q'
0x14001e7e6  mov     [rbx+2D0h], r15
0x14001e7ed  call    cs:__imp_RxLowIoGetBufferAddress
0x14001e7f4  nop     dword ptr [rax+rax+00h]
0x14001e7f9  mov     [rbx+2C8h], rax
0x14001e800  test    rax, rax
0x14001e803  jz      short loc_14001E85B
0x14001e805  xor     edx, edx
0x14001e807  jmp     loc_14001E718
0x14001e80c  int     2Ch; Windows NT - assertion failure
0x14001e80e  jmp     loc_14001E598
0x14001e813  mov     eax, 410h
0x14001e818  movzx   r13d, r13b
0x14001e81c  cmp     [rbx+310h], ax
0x14001e823  mov     ecx, 1
0x14001e828  cmovnb  r13d, ecx
0x14001e82c  jmp     loc_14001E5FA
0x14001e831  int     2Ch; Windows NT - assertion failure
0x14001e833  jmp     loc_14001E60D
0x14001e838  int     2Ch; Windows NT - assertion failure
0x14001e83a  jmp     loc_14001E61A
0x14001e83f  int     2Ch; Windows NT - assertion failure
0x14001e841  jmp     loc_14001E627
0x14001e846  int     2Ch; Windows NT - assertion failure
0x14001e848  jmp     loc_14001E634
0x14001e84d  int     2Ch; Windows NT - assertion failure
0x14001e84f  jmp     loc_14001E648
0x14001e854  int     2Ch; Windows NT - assertion failure
0x14001e856  jmp     loc_14001E656
0x14001e85b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001e862  lea     rax, WPP_GLOBAL_Control
0x14001e869  cmp     rcx, rax
0x14001e86c  jz      short loc_14001E893
0x14001e86e  mov     eax, [rcx+2Ch]
0x14001e871  test    al, 1
0x14001e873  jz      short loc_14001E893
0x14001e875  cmp     byte ptr [rcx+29h], 1
0x14001e879  jb      short loc_14001E893
0x14001e87b  mov     rcx, [rcx+18h]
0x14001e87f  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14001e886  mov     edx, 2Dh ; '-'
0x14001e88b  mov     r9, rdi
0x14001e88e  call    WPP_SF_q
0x14001e893  mov     eax, 0C000009Ah
0x14001e898  jmp     loc_14001E7BD
```
