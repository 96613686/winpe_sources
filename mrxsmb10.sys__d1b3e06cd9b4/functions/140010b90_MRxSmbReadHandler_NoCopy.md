# MRxSmbReadHandler_NoCopy

- ea: `0x140010b90`
- end: `0x140010f97`
- name: `MRxSmbReadHandler_NoCopy`
- size: `1031`
- prototype: `char __fastcall(__int64, unsigned int, __int64, unsigned int *, __int64, _QWORD *, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x14000dfa8`
- `0x14000ebd8`
- `0x140010b90`
- `0x140010fa0`
- `0x1400166c0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140010e85`
- `ntoskrnl!IoBuildPartialMdl` at `0x140010ef3`
- `ntoskrnl!IoBuildPartialMdl` at `0x140010e85`
- `ntoskrnl!IoBuildPartialMdl` at `0x140010ef3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010e1c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010e1c`
- `ntoskrnl!ExAllocatePool2` at `0x140010d5d`
- `ntoskrnl!ExAllocatePool2` at `0x140010d5d`

## pseudocode

```c
char __fastcall MRxSmbReadHandler_NoCopy(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7,
        __int64 a8)
{
  struct _MDL *v11; // r12
  char v12; // al
  char v13; // di
  unsigned int v14; // esi
  unsigned __int16 v15; // cx
  void *v16; // rbp
  unsigned int v17; // r14d
  __int64 Pool2; // rax
  __int64 v19; // r9
  __int64 v20; // r9
  __int64 v21; // r8
  int v22; // ecx
  __int64 v23; // rcx
  __int64 v24; // rcx

  v11 = *(struct _MDL **)(*(_QWORD *)(a1 + 24) + 544LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids);
  v12 = *(_BYTE *)(a1 + 388);
  if ( v12 == 10 )
  {
    v14 = 48;
    if ( a2 < 0x30 || *(_BYTE *)a8 != 5 )
      goto LABEL_7;
    v15 = *(_WORD *)(a8 + 14);
  }
  else
  {
    if ( v12 != 46 )
      goto LABEL_7;
    if ( a2 < 0x3B )
      goto LABEL_7;
    if ( *(_BYTE *)a8 != 12 )
      goto LABEL_7;
    v14 = *(unsigned __int16 *)(a8 + 13);
    if ( v14 > 0x3C )
      goto LABEL_7;
    v15 = *(_WORD *)(a8 + 11);
  }
  v16 = (void *)(*(unsigned int *)(a1 + 500) + *(_QWORD *)(a1 + 472));
  v17 = *(_DWORD *)(a1 + 496);
  if ( v15 <= v17 )
    v17 = v15;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LLLLq(WPP_GLOBAL_Control->AttachedDevice);
  *(_DWORD *)(a1 + 512) = v17;
  *(_QWORD *)(a1 + 440) = MRxSmbFinishNoCopyRead;
  *(_DWORD *)(a1 + 520) = v17;
  *(_DWORD *)(a1 + 524) = 0;
  if ( a2 >= v17 + v14 )
  {
    memmove(v16, (const void *)(a5 + v14), v17);
    *a4 = *(_DWORD *)(a1 + 520) + v14 + *(_DWORD *)(a1 + 524);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids);
    return 0;
  }
  if ( a2 < v14 )
  {
LABEL_7:
    *(_DWORD *)(a1 + 48) = -1073741629;
    return 2;
  }
  v13 = 1;
  if ( v17 )
  {
    *(_BYTE *)(a1 + 517) = 1;
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 672LL) & 8) != 0 )
    {
      Pool2 = ExAllocatePool2(66, v17, 1397976403);
      *(_QWORD *)(a1 + 840) = Pool2;
      if ( !Pool2 )
      {
        *(_DWORD *)(a1 + 48) = -1073741670;
        v13 = 2;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids, a1);
        }
        return v13;
      }
      v19 = *(unsigned int *)(a1 + 520);
      *(_QWORD *)(a1 + 528) = 0;
      *(_DWORD *)(a1 + 568) = v19;
      *(_QWORD *)(a1 + 560) = Pool2 & 0xFFFFFFFFFFFFF000uLL;
      *(_DWORD *)(a1 + 572) = Pool2 & 0xFFF;
      *(_WORD *)(a1 + 538) = 0;
      *(_WORD *)(a1 + 536) = 8 * ((((unsigned __int64)(Pool2 & 0xFFF) + v19 + 4095) >> 12) + 6);
      MmBuildMdlForNonPagedPool((PMDL)(a1 + 528));
    }
    else
    {
      v20 = *(unsigned int *)(a1 + 500);
      *(_QWORD *)(a1 + 528) = 0;
      v21 = v17 + 4096;
      *(_DWORD *)(a1 + 568) = v21;
      *(_WORD *)(a1 + 536) = 8 * (((unsigned __int64)(v21 + 4095) >> 12) + 6);
      *(_WORD *)(a1 + 538) = 0;
      *(_QWORD *)(a1 + 560) = 0;
      *(_DWORD *)(a1 + 572) = 0;
      IoBuildPartialMdl(v11, (PMDL)(a1 + 528), (char *)v11->StartVa + v11->ByteOffset + v20, *(_DWORD *)(a1 + 520));
    }
  }
  v22 = *(_DWORD *)(a1 + 524);
  if ( v22 )
  {
    *(_BYTE *)(a1 + 516) = 1;
    *(_QWORD *)(a1 + 736) = 0;
    v23 = (unsigned int)(v22 + 4096);
    *(_DWORD *)(a1 + 776) = v23;
    *(_WORD *)(a1 + 744) = 8 * (((unsigned __int64)(v23 + 4095) >> 12) + 6);
    *(_WORD *)(a1 + 746) = 0;
    *(_QWORD *)(a1 + 768) = 0;
    *(_DWORD *)(a1 + 780) = 0;
    IoBuildPartialMdl(
      *(PMDL *)(a1 + 896),
      (PMDL)(a1 + 736),
      (PVOID)(*(_QWORD *)(*(_QWORD *)(a1 + 896) + 32LL) + *(unsigned int *)(*(_QWORD *)(a1 + 896) + 44LL)),
      *(_DWORD *)(a1 + 524));
  }
  if ( *(_BYTE *)(a1 + 517) )
  {
    if ( *(_BYTE *)(a1 + 516) )
      *(_QWORD *)(a1 + 528) = a1 + 736;
    v24 = a1 + 528;
  }
  else
  {
    v24 = a1 + 736;
  }
  *a6 = v24;
  *a7 = *(_DWORD *)(a1 + 520) + *(_DWORD *)(a1 + 524);
  *a4 = v14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids);
  return v13;
}

```

## disassembly

```asm
0x140010b90  push    rbx
0x140010b92  push    rbp
0x140010b93  push    rsi
0x140010b94  push    rdi
0x140010b95  push    r12
0x140010b97  push    r14
0x140010b99  push    r15
0x140010b9b  sub     rsp, 40h
0x140010b9f  mov     rax, [rcx+18h]
0x140010ba3  mov     r15, r9
0x140010ba6  mov     edi, edx
0x140010ba8  mov     rbx, rcx
0x140010bab  mov     r12, [rax+220h]
0x140010bb2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010bb9  lea     r8, WPP_GLOBAL_Control
0x140010bc0  cmp     rcx, r8
0x140010bc3  jz      short loc_140010BEA
0x140010bc5  test    dword ptr [rcx+2Ch], 400h
0x140010bcc  jz      short loc_140010BEA
0x140010bce  mov     rcx, [rcx+18h]
0x140010bd2  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x140010bd9  mov     edx, 11h
0x140010bde  call    WPP_SF_
0x140010be3  lea     r8, WPP_GLOBAL_Control
0x140010bea  mov     al, [rbx+184h]
0x140010bf0  cmp     al, 0Ah
0x140010bf2  jz      short loc_140010C28
0x140010bf4  cmp     al, 2Eh ; '.'
0x140010bf6  jnz     short loc_140010BFD
0x140010bf8  cmp     edi, 3Bh ; ';'
0x140010bfb  jnb     short loc_140010C0C
0x140010bfd  mov     dword ptr [rbx+30h], 0C00000C3h
0x140010c04  mov     dil, 2
0x140010c07  jmp     loc_140010F84
0x140010c0c  mov     rax, [rsp+78h+arg_38]
0x140010c14  cmp     byte ptr [rax], 0Ch
0x140010c17  jnz     short loc_140010BFD
0x140010c19  movzx   esi, word ptr [rax+0Dh]
0x140010c1d  cmp     esi, 3Ch ; '<'
0x140010c20  ja      short loc_140010BFD
0x140010c22  movzx   ecx, word ptr [rax+0Bh]
0x140010c26  jmp     short loc_140010C42
0x140010c28  mov     esi, 30h ; '0'
0x140010c2d  cmp     edi, esi
0x140010c2f  jb      short loc_140010BFD
0x140010c31  mov     rax, [rsp+78h+arg_38]
0x140010c39  cmp     byte ptr [rax], 5
0x140010c3c  jnz     short loc_140010BFD
0x140010c3e  movzx   ecx, word ptr [rax+0Eh]
0x140010c42  mov     edx, [rbx+1F4h]
0x140010c48  mov     rbp, [rbx+1D8h]
0x140010c4f  mov     r9d, [rbx+1F0h]
0x140010c56  add     rbp, rdx
0x140010c59  movzx   eax, cx
0x140010c5c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010c63  cmp     eax, r9d
0x140010c66  mov     r14d, r9d
0x140010c69  cmovbe  r14d, eax
0x140010c6d  cmp     rcx, r8
0x140010c70  jz      short loc_140010C96
0x140010c72  test    dword ptr [rcx+2Ch], 400h
0x140010c79  jz      short loc_140010C96
0x140010c7b  mov     rcx, [rcx+18h]
0x140010c7f  mov     [rsp+78h+var_40], rbp
0x140010c84  mov     [rsp+78h+var_48], esi
0x140010c88  mov     [rsp+78h+var_50], r14d
0x140010c8d  mov     [rsp+78h+var_58], edx
0x140010c91  call    WPP_SF_LLLLq
0x140010c96  lea     rax, MRxSmbFinishNoCopyRead
0x140010c9d  mov     [rbx+200h], r14d
0x140010ca4  mov     [rbx+1B8h], rax
0x140010cab  lea     eax, [r14+rsi]
0x140010caf  mov     [rbx+208h], r14d
0x140010cb6  mov     dword ptr [rbx+20Ch], 0
0x140010cc0  cmp     edi, eax
0x140010cc2  jb      short loc_140010D23
0x140010cc4  mov     edx, esi
0x140010cc6  mov     rcx, rbp; void *
0x140010cc9  add     rdx, [rsp+78h+arg_20]; Src
0x140010cd1  mov     r8d, r14d; Size
0x140010cd4  call    memmove
0x140010cd9  mov     eax, [rbx+20Ch]
0x140010cdf  add     eax, esi
0x140010ce1  add     eax, [rbx+208h]
0x140010ce7  mov     [r15], eax
0x140010cea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010cf1  lea     rax, WPP_GLOBAL_Control
0x140010cf8  cmp     rcx, rax
0x140010cfb  jz      short loc_140010D1B
0x140010cfd  test    dword ptr [rcx+2Ch], 400h
0x140010d04  jz      short loc_140010D1B
0x140010d06  mov     rcx, [rcx+18h]
0x140010d0a  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x140010d11  mov     edx, 13h
0x140010d16  call    WPP_SF_
0x140010d1b  xor     dil, dil
0x140010d1e  jmp     loc_140010F84
0x140010d23  cmp     edi, esi
0x140010d25  jb      loc_140010BFD
0x140010d2b  mov     dil, 1
0x140010d2e  test    r14d, r14d
0x140010d31  jz      loc_140010E91
0x140010d37  mov     [rbx+205h], dil
0x140010d3e  mov     rax, [rbx+50h]
0x140010d42  test    byte ptr [rax+2A0h], 8
0x140010d49  jz      loc_140010E2A
0x140010d4f  mov     edx, r14d
0x140010d52  mov     ecx, 42h ; 'B'
0x140010d57  mov     r8d, 53536D53h
0x140010d5d  call    cs:__imp_ExAllocatePool2
0x140010d64  nop     dword ptr [rax+rax+00h]
0x140010d69  mov     [rbx+348h], rax
0x140010d70  mov     r10, rax
0x140010d73  test    rax, rax
0x140010d76  jnz     short loc_140010DC2
0x140010d78  mov     dword ptr [rbx+30h], 0C000009Ah
0x140010d7f  mov     dil, 2
0x140010d82  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010d89  lea     rax, WPP_GLOBAL_Control
0x140010d90  cmp     rcx, rax
0x140010d93  jz      loc_140010F84
0x140010d99  test    dword ptr [rcx+2Ch], 100h
0x140010da0  jz      loc_140010F84
0x140010da6  mov     rcx, [rcx+18h]
0x140010daa  lea     edx, [r10+14h]
0x140010dae  mov     r9, rbx
0x140010db1  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x140010db8  call    WPP_SF_q
0x140010dbd  jmp     loc_140010F84
0x140010dc2  mov     r9d, [rbx+208h]
0x140010dc9  lea     rcx, [rbx+210h]; MemoryDescriptorList
0x140010dd0  mov     r8d, r10d
0x140010dd3  mov     qword ptr [rcx], 0
0x140010dda  mov     eax, r8d
0x140010ddd  mov     [rcx+28h], r9d
0x140010de1  mov     r11d, 0FFFh
0x140010de7  and     r10, 0FFFFFFFFFFFFF000h
0x140010dee  and     rax, r11
0x140010df1  mov     [rcx+20h], r10
0x140010df5  lea     rdx, [r9+0FFFh]
0x140010dfc  and     r8d, r11d
0x140010dff  add     rdx, rax
0x140010e02  mov     [rcx+2Ch], r8d
0x140010e06  shr     rdx, 0Ch
0x140010e0a  xor     eax, eax
0x140010e0c  add     dx, 6
0x140010e10  mov     [rcx+0Ah], ax
0x140010e14  shl     dx, 3
0x140010e18  mov     [rcx+8], dx
0x140010e1c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140010e23  nop     dword ptr [rax+rax+00h]
0x140010e28  jmp     short loc_140010E91
0x140010e2a  mov     r9d, [rbx+1F4h]
0x140010e31  lea     rdx, [rbx+210h]; TargetMdl
0x140010e38  mov     qword ptr [rdx], 0
0x140010e3f  lea     r8d, [r14+1000h]
0x140010e46  lea     rax, [r8+0FFFh]
0x140010e4d  mov     [rdx+28h], r8d
0x140010e51  shr     rax, 0Ch
0x140010e55  mov     rcx, r12; SourceMdl
0x140010e58  add     ax, 6
0x140010e5c  shl     ax, 3
0x140010e60  mov     [rdx+8], ax
0x140010e64  xor     eax, eax
0x140010e66  mov     [rdx+0Ah], ax
0x140010e6a  mov     [rdx+20h], rax
0x140010e6e  mov     [rdx+2Ch], eax
0x140010e71  mov     r8d, [r12+2Ch]
0x140010e76  add     r8, [r12+20h]
0x140010e7b  add     r8, r9; VirtualAddress
0x140010e7e  mov     r9d, [rbx+208h]; Length
0x140010e85  call    cs:__imp_IoBuildPartialMdl
0x140010e8c  nop     dword ptr [rax+rax+00h]
0x140010e91  mov     ecx, [rbx+20Ch]
0x140010e97  test    ecx, ecx
0x140010e99  jz      short loc_140010EFF
0x140010e9b  mov     [rbx+204h], dil
0x140010ea2  lea     rdx, [rbx+2E0h]; TargetMdl
0x140010ea9  mov     qword ptr [rdx], 0
0x140010eb0  add     ecx, 1000h
0x140010eb6  mov     [rdx+28h], ecx
0x140010eb9  lea     rax, [rcx+0FFFh]
0x140010ec0  shr     rax, 0Ch
0x140010ec4  add     ax, 6
0x140010ec8  shl     ax, 3
0x140010ecc  mov     [rdx+8], ax
0x140010ed0  xor     eax, eax
0x140010ed2  mov     [rdx+0Ah], ax
0x140010ed6  mov     [rdx+20h], rax
0x140010eda  mov     [rdx+2Ch], eax
0x140010edd  mov     rcx, [rbx+380h]; SourceMdl
0x140010ee4  mov     r9d, [rbx+20Ch]; Length
0x140010eeb  mov     r8d, [rcx+2Ch]
0x140010eef  add     r8, [rcx+20h]; VirtualAddress
0x140010ef3  call    cs:__imp_IoBuildPartialMdl
0x140010efa  nop     dword ptr [rax+rax+00h]
0x140010eff  cmp     byte ptr [rbx+205h], 0
0x140010f06  jz      short loc_140010F28
0x140010f08  cmp     byte ptr [rbx+204h], 0
0x140010f0f  jz      short loc_140010F1F
0x140010f11  lea     rax, [rbx+2E0h]
0x140010f18  mov     [rbx+210h], rax
0x140010f1f  lea     rcx, [rbx+210h]
0x140010f26  jmp     short loc_140010F2F
0x140010f28  lea     rcx, [rbx+2E0h]
0x140010f2f  mov     rax, [rsp+78h+arg_28]
0x140010f37  mov     [rax], rcx
0x140010f3a  mov     ecx, [rbx+20Ch]
0x140010f40  add     ecx, [rbx+208h]
0x140010f46  mov     rax, [rsp+78h+arg_30]
0x140010f4e  mov     [rax], ecx
0x140010f50  mov     [r15], esi
0x140010f53  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010f5a  lea     rax, WPP_GLOBAL_Control
0x140010f61  cmp     rcx, rax
0x140010f64  jz      short loc_140010F84
0x140010f66  test    dword ptr [rcx+2Ch], 400h
0x140010f6d  jz      short loc_140010F84
0x140010f6f  mov     rcx, [rcx+18h]
0x140010f73  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x140010f7a  mov     edx, 15h
0x140010f7f  call    WPP_SF_
0x140010f84  mov     al, dil
0x140010f87  add     rsp, 40h
0x140010f8b  pop     r15
0x140010f8d  pop     r14
0x140010f8f  pop     r12
0x140010f91  pop     rdi
0x140010f92  pop     rsi
0x140010f93  pop     rbp
0x140010f94  pop     rbx
0x140010f95  retn
```
