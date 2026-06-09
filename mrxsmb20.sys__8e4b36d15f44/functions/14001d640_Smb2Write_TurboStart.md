# Smb2Write_TurboStart

- ea: `0x14001d640`
- end: `0x14001d93d`
- name: `Smb2Write_TurboStart`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14001d640`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14001d773`
- `ntoskrnl!IoBuildPartialMdl` at `0x14001d773`
- `rdbss!RxAllocateMdl2` at `0x14001d74a`
- `rdbss!RxAllocateMdl2` at `0x14001d74a`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x14001d82f`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x14001d82f`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001d6b6`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001d6b6`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001d67e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001d67e`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001d893`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001d893`

## pseudocode

```c
__int64 __fastcall Smb2Write_TurboStart(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rdx
  __int64 v3; // rbp
  __int64 v5; // rcx
  bool v6; // r13
  __int64 v7; // r12
  __int64 v8; // rdi
  __int64 v9; // rdx
  _DWORD *ConfigurationBlock; // rsi
  struct _MDL *v11; // r14
  ULONG v12; // esi
  struct _MDL *Mdl2; // rax
  struct _MDL *v14; // r15
  __int64 v15; // rcx
  __int64 v16; // r14
  __int16 v17; // ax
  int v19; // eax

  v1 = *(_QWORD *)(a1 + 96);
  v2 = a1 + 160;
  v3 = *(_QWORD *)(a1 + 48);
  v5 = *(_QWORD *)(a1 + 160);
  v6 = 0;
  v7 = *(_QWORD *)(v1 + 392);
  v8 = v5 - 8;
  if ( v5 == v2 )
    v8 = 0;
  ConfigurationBlock = (_DWORD *)MRxSmbGetConfigurationBlock(v5);
  if ( *(_QWORD *)(a1 + 56) )
    __int2c();
  if ( (*(_DWORD *)(a1 + 68) & 0x1000000) != 0 )
    __int2c();
  if ( (*(_DWORD *)(a1 + 68) & 0x800) != 0 )
    __int2c();
  LOBYTE(v9) = 39;
  RDR_PERF_ENTER(a1 + 512, v9);
  if ( ConfigurationBlock[1] && *(_DWORD *)(v3 + 568) >= *ConfigurationBlock && *(_DWORD *)(v7 + 320) == 2 )
    v6 = *(_WORD *)(v8 + 784) >= 0x410u;
  *(_QWORD *)(a1 + 1032) = 0;
  v11 = *(struct _MDL **)(v3 + 544);
  *(_QWORD *)(a1 + 1024) = v11;
  v12 = *(_DWORD *)(v3 + 568);
  if ( v12 > 0x10000 )
    __int2c();
  if ( *(_DWORD *)(v8 + 1388) != 1 )
    __int2c();
  if ( *(_DWORD *)(v8 + 1384) )
    __int2c();
  if ( *(_DWORD *)(v8 + 1392) )
    __int2c();
  *(_DWORD *)(v8 + 1396) = v12;
  Mdl2 = (struct _MDL *)RxAllocateMdl2((char *)v11->StartVa + v11->ByteOffset, v12, 0, 0, 0);
  v14 = Mdl2;
  if ( !Mdl2 )
    return 3221225626LL;
  IoBuildPartialMdl(v11, Mdl2, (char *)v11->StartVa + v11->ByteOffset, v12);
  *(_QWORD *)(*(_QWORD *)(v8 + 96) + 24LL) = *(_QWORD *)(v8 + 88);
  *(_QWORD *)(*(_QWORD *)(v8 + 96) + 32LL) = *(_QWORD *)(v8 + 88) & 0xFFFFFFFFFFFFF000uLL;
  *(_DWORD *)(*(_QWORD *)(v8 + 96) + 44LL) = *(_DWORD *)(v8 + 88) & 0xFFF;
  *(_DWORD *)(*(_QWORD *)(v8 + 96) + 40LL) = 112;
  v15 = *(_QWORD *)(v8 + 96);
  if ( v6 )
  {
    v19 = *(unsigned __int16 *)(v8 + 784) + 112;
    *(_DWORD *)(v8 + 728) = v19;
    *(_DWORD *)(v15 + 40) = v19;
    *(_DWORD *)(v8 + 776) = v12;
    *(_QWORD *)(v8 + 768) = v14;
  }
  else
  {
    *(_QWORD *)v15 = v14;
    *(_DWORD *)(v8 + 728) = v12 + *(_DWORD *)(*(_QWORD *)(v8 + 96) + 40LL);
  }
  v16 = *(_QWORD *)(v8 + 88);
  *(_DWORD *)(v8 + 748) = 0;
  *(_DWORD *)(v8 + 744) = v12;
  *(_QWORD *)(v16 + 72) = *(_QWORD *)(v3 + 560);
  if ( v6 )
  {
    SmbCseEstimateMemoryDescriptorSize(
      v7,
      v12,
      (*(_BYTE *)(*(_QWORD *)(a1 + 72) + 736LL) & 0x40) != 0,
      0,
      v16 + 106,
      v16 + 96);
    *(_DWORD *)(v16 + 68) = 0;
    *(_WORD *)(v16 + 66) = 0;
    *(_DWORD *)(v16 + 100) = v12;
    *(_WORD *)(v16 + 104) = 112;
    v17 = *(_WORD *)(v8 + 784);
  }
  else
  {
    v17 = 0;
    *(_DWORD *)(v16 + 68) = v12;
    *(_WORD *)(v16 + 104) = 0;
    *(_WORD *)(v16 + 66) = 112;
    *(_DWORD *)(v16 + 100) = 0;
    *(_DWORD *)(v16 + 96) = 0;
  }
  *(_WORD *)(v16 + 106) = v17;
  _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                  * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                 % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL)
                                                                             + 1488LL))
                                                  + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                  + 124));
  return SmbCseSubmitBufferContext(v8);
}

```

## disassembly

```asm
0x14001d640  push    rbx
0x14001d642  push    rbp
0x14001d643  push    rsi
0x14001d644  push    rdi
0x14001d645  push    r12
0x14001d647  push    r13
0x14001d649  push    r14
0x14001d64b  push    r15
0x14001d64d  sub     rsp, 38h
0x14001d651  mov     rax, [rcx+60h]
0x14001d655  lea     rdx, [rcx+0A0h]
0x14001d65c  mov     rbp, [rcx+30h]
0x14001d660  mov     rbx, rcx
0x14001d663  mov     rcx, [rdx]
0x14001d666  xor     r15d, r15d
0x14001d669  xor     r13b, r13b
0x14001d66c  mov     r12, [rax+188h]
0x14001d673  cmp     rcx, rdx
0x14001d676  lea     rdi, [rcx-8]
0x14001d67a  cmovz   rdi, r15
0x14001d67e  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001d685  nop     dword ptr [rax+rax+00h]
0x14001d68a  mov     rsi, rax
0x14001d68d  cmp     [rbx+38h], r15
0x14001d691  jnz     loc_14001D91A
0x14001d697  mov     ecx, [rbx+44h]
0x14001d69a  bt      ecx, 18h
0x14001d69e  jnb     short loc_14001D6A2
0x14001d6a0  int     2Ch; Windows NT - assertion failure
0x14001d6a2  mov     eax, [rbx+44h]
0x14001d6a5  bt      eax, 0Bh
0x14001d6a9  jnb     short loc_14001D6AD
0x14001d6ab  int     2Ch; Windows NT - assertion failure
0x14001d6ad  lea     rcx, [rbx+200h]
0x14001d6b4  mov     dl, 27h ; '''
0x14001d6b6  call    cs:__imp_RDR_PERF_ENTER
0x14001d6bd  nop     dword ptr [rax+rax+00h]
0x14001d6c2  cmp     [rsi+4], r15d
0x14001d6c6  jbe     short loc_14001D6E1
0x14001d6c8  mov     eax, [rsi]
0x14001d6ca  cmp     [rbp+238h], eax
0x14001d6d0  jb      short loc_14001D6E1
0x14001d6d2  cmp     dword ptr [r12+140h], 2
0x14001d6db  jz      loc_14001D8FC
0x14001d6e1  mov     [rbx+408h], r15
0x14001d6e8  mov     r14, [rbp+220h]
0x14001d6ef  mov     [rbx+400h], r14
0x14001d6f6  mov     esi, [rbp+238h]
0x14001d6fc  cmp     esi, 10000h
0x14001d702  ja      loc_14001D921
0x14001d708  cmp     dword ptr [rdi+56Ch], 1
0x14001d70f  jnz     loc_14001D928
0x14001d715  cmp     [rdi+568h], r15d
0x14001d71c  jnz     loc_14001D92F
0x14001d722  cmp     [rdi+570h], r15d
0x14001d729  jnz     loc_14001D936
0x14001d72f  mov     [rdi+574h], esi
0x14001d735  xor     r9d, r9d
0x14001d738  mov     ecx, [r14+2Ch]
0x14001d73c  xor     r8d, r8d
0x14001d73f  add     rcx, [r14+20h]
0x14001d743  mov     edx, esi
0x14001d745  mov     [rsp+78h+var_58], r15
0x14001d74a  call    cs:__imp_RxAllocateMdl2
0x14001d751  nop     dword ptr [rax+rax+00h]
0x14001d756  mov     r15, rax
0x14001d759  test    rax, rax
0x14001d75c  jz      loc_14001D8F5
0x14001d762  mov     r8d, [r14+2Ch]
0x14001d766  mov     r9d, esi; Length
0x14001d769  add     r8, [r14+20h]; VirtualAddress
0x14001d76d  mov     rdx, rax; TargetMdl
0x14001d770  mov     rcx, r14; SourceMdl
0x14001d773  call    cs:__imp_IoBuildPartialMdl
0x14001d77a  nop     dword ptr [rax+rax+00h]
0x14001d77f  mov     rcx, [rdi+60h]
0x14001d783  mov     edx, 70h ; 'p'
0x14001d788  mov     rax, [rdi+58h]
0x14001d78c  mov     [rcx+18h], rax
0x14001d790  mov     rax, [rdi+60h]
0x14001d794  mov     rcx, [rdi+58h]
0x14001d798  and     rcx, 0FFFFFFFFFFFFF000h
0x14001d79f  mov     [rax+20h], rcx
0x14001d7a3  mov     ecx, [rdi+58h]
0x14001d7a6  mov     rax, [rdi+60h]
0x14001d7aa  and     ecx, 0FFFh
0x14001d7b0  mov     [rax+2Ch], ecx
0x14001d7b3  mov     rax, [rdi+60h]
0x14001d7b7  mov     [rax+28h], edx
0x14001d7ba  mov     rcx, [rdi+60h]
0x14001d7be  test    r13b, r13b
0x14001d7c1  jnz     loc_14001D8D1
0x14001d7c7  mov     [rcx], r15
0x14001d7ca  mov     rax, [rdi+60h]
0x14001d7ce  mov     eax, [rax+28h]
0x14001d7d1  add     eax, esi
0x14001d7d3  mov     [rdi+2D8h], eax
0x14001d7d9  mov     r14, [rdi+58h]
0x14001d7dd  mov     dword ptr [rdi+2ECh], 0
0x14001d7e7  mov     [rdi+2E8h], esi
0x14001d7ed  mov     rax, [rbp+230h]
0x14001d7f4  mov     [r14+48h], rax
0x14001d7f8  lea     r15, [r14+6Ah]
0x14001d7fc  lea     rcx, [r14+60h]
0x14001d800  test    r13b, r13b
0x14001d803  jz      loc_14001D8B1
0x14001d809  mov     rax, [rbx+48h]
0x14001d80d  xor     r9d, r9d
0x14001d810  mov     [rsp+78h+var_50], rcx
0x14001d815  mov     edx, esi
0x14001d817  mov     rcx, r12
0x14001d81a  mov     [rsp+78h+var_58], r15
0x14001d81f  movzx   r8d, byte ptr [rax+2E0h]
0x14001d827  shr     r8b, 6
0x14001d82b  and     r8b, 1
0x14001d82f  call    cs:__imp_SmbCseEstimateMemoryDescriptorSize
0x14001d836  nop     dword ptr [rax+rax+00h]
0x14001d83b  xor     eax, eax
0x14001d83d  mov     dword ptr [r14+44h], 0
0x14001d845  mov     [r14+42h], ax
0x14001d84a  mov     [r14+64h], esi
0x14001d84e  mov     word ptr [r14+68h], 70h ; 'p'
0x14001d855  movzx   eax, word ptr [rdi+310h]
0x14001d85c  mov     [r15], ax
0x14001d860  xor     edx, edx
0x14001d862  mov     rax, [rbx+58h]
0x14001d866  mov     r9, [rax+1A8h]
0x14001d86d  mov     eax, gs:1A4h
0x14001d875  div     dword ptr [r9+5D0h]
0x14001d87c  mov     rax, [r9+5C8h]
0x14001d883  lea     rdx, [rdx+rdx*2]
0x14001d887  shl     rdx, 6
0x14001d88b  lock inc dword ptr [rdx+rax+7Ch]
0x14001d890  mov     rcx, rdi
0x14001d893  call    cs:__imp_SmbCseSubmitBufferContext
0x14001d89a  nop     dword ptr [rax+rax+00h]
0x14001d89f  add     rsp, 38h
0x14001d8a3  pop     r15
0x14001d8a5  pop     r14
0x14001d8a7  pop     r13
0x14001d8a9  pop     r12
0x14001d8ab  pop     rdi
0x14001d8ac  pop     rsi
0x14001d8ad  pop     rbp
0x14001d8ae  pop     rbx
0x14001d8af  retn
0x14001d8b1  xor     eax, eax
0x14001d8b3  mov     [r14+44h], esi
0x14001d8b7  mov     [r14+68h], ax
0x14001d8bc  mov     [r14+42h], dx
0x14001d8c1  mov     dword ptr [r14+64h], 0
0x14001d8c9  mov     dword ptr [rcx], 0
0x14001d8cf  jmp     short loc_14001D85C
0x14001d8d1  movzx   eax, word ptr [rdi+310h]
0x14001d8d8  add     eax, edx
0x14001d8da  mov     [rdi+2D8h], eax
0x14001d8e0  mov     [rcx+28h], eax
0x14001d8e3  mov     [rdi+308h], esi
0x14001d8e9  mov     [rdi+300h], r15
0x14001d8f0  jmp     loc_14001D7D9
0x14001d8f5  mov     eax, 0C000009Ah
0x14001d8fa  jmp     short loc_14001D89F
0x14001d8fc  mov     eax, 410h
0x14001d901  movzx   r13d, r13b
0x14001d905  cmp     [rdi+310h], ax
0x14001d90c  mov     ecx, 1
0x14001d911  cmovnb  r13d, ecx
0x14001d915  jmp     loc_14001D6E1
0x14001d91a  int     2Ch; Windows NT - assertion failure
0x14001d91c  jmp     loc_14001D697
0x14001d921  int     2Ch; Windows NT - assertion failure
0x14001d923  jmp     loc_14001D708
0x14001d928  int     2Ch; Windows NT - assertion failure
0x14001d92a  jmp     loc_14001D715
0x14001d92f  int     2Ch; Windows NT - assertion failure
0x14001d931  jmp     loc_14001D722
0x14001d936  int     2Ch; Windows NT - assertion failure
0x14001d938  jmp     loc_14001D72F
```
