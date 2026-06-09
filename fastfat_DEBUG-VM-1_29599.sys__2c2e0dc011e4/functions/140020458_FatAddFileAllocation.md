# FatAddFileAllocation

- ea: `0x140020458`
- end: `0x14002072d`
- name: `FatAddFileAllocation`
- size: `725`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14000363c`
- `0x140004554`
- `0x140024228`
- `0x140029774`
- `0x14002cbe4`
- `0x14003816c`
- `0x14003ad44`
- `0x14003b9d0`
- `0x14004af08`

## callees

- `0x1400019b8`
- `0x140005c80`
- `0x140020458`
- `0x140020734`
- `0x1400210d0`
- `0x1400226b8`
- `0x140022740`
- `0x1400319bc`
- `0x140040330`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14002070d`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005addc`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005ae1d`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14002070d`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005addc`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005ae1d`
- `ntoskrnl!FsRtlTruncateLargeMcb` at `0x14005adf1`
- `ntoskrnl!FsRtlTruncateLargeMcb` at `0x14005ae32`
- `ntoskrnl!FsRtlTruncateLargeMcb` at `0x14005adf1`
- `ntoskrnl!FsRtlTruncateLargeMcb` at `0x14005ae32`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140020613`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140020613`
- `ntoskrnl!CcUnpinData` at `0x1400206ed`
- `ntoskrnl!CcUnpinData` at `0x14005ada0`
- `ntoskrnl!CcUnpinData` at `0x1400206ed`
- `ntoskrnl!CcUnpinData` at `0x14005ada0`
- `ntoskrnl!CcSetFileSizes` at `0x1400206af`
- `ntoskrnl!CcSetFileSizes` at `0x14005ad56`
- `ntoskrnl!CcSetFileSizes` at `0x1400206af`
- `ntoskrnl!CcSetFileSizes` at `0x14005ad56`

## pseudocode

```c
void __fastcall FatAddFileAllocation(__int64 a1, __int64 a2, struct _FILE_OBJECT *a3, DWORD a4)
{
  char v7; // r12
  __int64 v8; // rsi
  struct _CC_FILE_SIZES *v9; // rdi
  __int64 v10; // r9
  int v11; // eax
  DWORD v12; // ecx
  bool v13; // zf
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  DWORD v15; // [rsp+34h] [rbp-94h]
  PVOID Bcb; // [rsp+40h] [rbp-88h] BYREF
  int v17; // [rsp+48h] [rbp-80h] BYREF
  __int64 v18; // [rsp+50h] [rbp-78h] BYREF
  __int64 v19; // [rsp+58h] [rbp-70h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-68h] BYREF
  LARGE_MCB Mcb; // [rsp+70h] [rbp-58h] BYREF
  DWORD v22; // [rsp+E8h] [rbp+20h]

  v22 = a4;
  memset(&Mcb, 0, sizeof(Mcb));
  v18 = 0;
  Bcb = 0;
  v7 = 0;
  v8 = *(_QWORD *)(a2 + 184);
  v20[1] = v8;
  v9 = (struct _CC_FILE_SIZES *)(a2 + 24);
  if ( *(_QWORD *)(a2 + 24) == -1 )
  {
    FatLookupFileAllocationSize(a1, a2);
    a4 = v22;
  }
  if ( a4 > v9->AllocationSize.LowPart )
  {
    if ( v9->AllocationSize.LowPart )
    {
      v20[0] = 0;
      v17 = 0;
      FatLookupLastMcbEntry(*(_QWORD *)(a2 + 184), a2 + 288, &v17, v20, 0);
      v15 = v22 - v9->AllocationSize.LowPart;
      FsRtlInitializeLargeMcb(&Mcb, PagedPool);
      v7 = 1;
      FatAllocateDiskSpace(a1, v8, 0, (__int64)&Mcb);
      v12 = v15;
    }
    else
    {
      v19 = 0;
      FatGetDirentFromFcbOrDcb(a1, a2, 0, (unsigned int)&v18, (__int64)&Bcb);
      LOBYTE(v10) = 1;
      FatSetDirtyBcb(a1, Bcb, v8, v10);
      FatAllocateDiskSpace(a1, v8, 0, a2 + 288);
      FatLookupMcbEntry(*(_QWORD *)(a2 + 184), a2 + 288, 0, &v19, 0, 0);
      v11 = ((v19 - *(_QWORD *)(v8 + 352)) >> *(_BYTE *)(v8 + 378)) + 2;
      *(_DWORD *)(a2 + 128) = v11;
      *(_WORD *)(v18 + 26) = v11;
      if ( *(_BYTE *)(v8 + 376) == 32 )
        *(_WORD *)(v18 + 20) = *(_WORD *)(a2 + 130);
      v12 = v22;
      v15 = v22;
    }
    v13 = v12 + v9->AllocationSize.LowPart == 0;
    v9->AllocationSize.LowPart += v12;
    if ( v13 )
    {
      v15 = --v12;
      v9->AllocationSize.LowPart = -1;
    }
    if ( a3 )
    {
      SectionObjectPointer = a3->SectionObjectPointer;
      if ( SectionObjectPointer )
      {
        if ( SectionObjectPointer->SharedCacheMap )
        {
          CcSetFileSizes(a3, v9);
          v12 = v15;
        }
      }
    }
    if ( v9->AllocationSize.LowPart != v12 )
      FatMergeAllocation(a1, v8, a2 + 288, &Mcb);
    *(_DWORD *)(a2 + 192) |= 0x10u;
    if ( Bcb )
    {
      CcUnpinData(Bcb);
      Bcb = 0;
    }
    if ( v7 == 1 )
      FsRtlUninitializeLargeMcb(&Mcb);
  }
}

```

## disassembly

```asm
0x140020458  mov     rax, rsp
0x14002045b  mov     [rax+20h], r9d
0x14002045f  mov     [rax+18h], r8
0x140020463  mov     [rax+10h], rdx
0x140020467  mov     [rax+8], rcx
0x14002046b  push    rbx
0x14002046c  push    rsi
0x14002046d  push    rdi
0x14002046e  push    r12
0x140020470  push    r13
0x140020472  push    r14
0x140020474  push    r15
0x140020476  sub     rsp, 90h
0x14002047d  mov     r15, r8
0x140020480  mov     rbx, rdx
0x140020483  mov     r14, rcx
0x140020486  xorps   xmm0, xmm0
0x140020489  movups  xmmword ptr [rax-58h], xmm0
0x14002048d  movups  xmmword ptr [rax-48h], xmm0
0x140020491  xor     ecx, ecx
0x140020493  mov     [rsp+0C8h+var_90], rcx
0x140020498  mov     [rax-78h], rcx
0x14002049c  mov     [rsp+0C8h+var_94], ecx
0x1400204a0  mov     [rsp+0C8h+Bcb], rcx
0x1400204a5  mov     [rsp+0C8h+var_98], cl
0x1400204a9  mov     [rsp+0C8h+var_96], cl
0x1400204ad  mov     [rsp+0C8h+var_95], cl
0x1400204b1  mov     r12b, cl
0x1400204b4  mov     [rsp+0C8h+var_97], cl
0x1400204b8  mov     rsi, [rdx+0B8h]
0x1400204bf  mov     [rsp+0C8h+var_60], rsi
0x1400204c4  lea     rdi, [rdx+18h]
0x1400204c8  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1400204cc  jnz     short loc_1400204E0
0x1400204ce  mov     rcx, r14
0x1400204d1  call    FatLookupFileAllocationSize
0x1400204d6  mov     r9d, [rsp+0C8h+arg_18]
0x1400204de  xor     ecx, ecx
0x1400204e0  mov     eax, [rdi]
0x1400204e2  cmp     r9d, eax
0x1400204e5  jbe     loc_140020719
0x1400204eb  lea     r13, [rbx+120h]
0x1400204f2  test    eax, eax
0x1400204f4  jnz     loc_1400205D5
0x1400204fa  mov     [rsp+0C8h+var_70], rcx
0x1400204ff  lea     rax, [rsp+0C8h+Bcb]
0x140020504  mov     qword ptr [rsp+0C8h+var_A8], rax
0x140020509  lea     r9, [rsp+0C8h+var_78]
0x14002050e  xor     r8d, r8d
0x140020511  mov     rdx, rbx
0x140020514  mov     rcx, r14
0x140020517  call    FatGetDirentFromFcbOrDcb
0x14002051c  mov     r9b, 1
0x14002051f  mov     r8, rsi
0x140020522  mov     rdx, [rsp+0C8h+Bcb]
0x140020527  mov     rcx, r14
0x14002052a  call    FatSetDirtyBcb
0x14002052f  mov     [rsp+0C8h+var_A0], r13; __int64
0x140020534  mov     [rsp+0C8h+var_A8], 0; char
0x140020539  lea     r9, [rsp+0C8h+arg_18]
0x140020541  xor     r8d, r8d
0x140020544  mov     rdx, rsi; int
0x140020547  mov     rcx, r14; int
0x14002054a  call    FatAllocateDiskSpace
0x14002054f  mov     [rsp+0C8h+var_98], 1
0x140020554  mov     [rsp+0C8h+var_90], r13
0x140020559  mov     [rsp+0C8h+var_A0], 0
0x140020562  mov     qword ptr [rsp+0C8h+var_A8], 0
0x14002056b  lea     r9, [rsp+0C8h+var_70]
0x140020570  xor     r8d, r8d
0x140020573  mov     rdx, r13
0x140020576  mov     rcx, [rbx+0B8h]
0x14002057d  call    FatLookupMcbEntry
0x140020582  mov     rax, [rsp+0C8h+var_70]
0x140020587  sub     rax, [rsi+160h]
0x14002058e  mov     cl, [rsi+17Ah]
0x140020594  sar     rax, cl
0x140020597  add     eax, 2
0x14002059a  mov     [rbx+80h], eax
0x1400205a0  movzx   ecx, ax
0x1400205a3  mov     rax, [rsp+0C8h+var_78]
0x1400205a8  mov     [rax+1Ah], cx
0x1400205ac  cmp     byte ptr [rsi+178h], 20h ; ' '
0x1400205b3  jnz     short loc_1400205C5
0x1400205b5  movzx   ecx, word ptr [rbx+82h]
0x1400205bc  mov     rax, [rsp+0C8h+var_78]
0x1400205c1  mov     [rax+14h], cx
0x1400205c5  mov     ecx, [rsp+0C8h+arg_18]
0x1400205cc  mov     [rsp+0C8h+var_94], ecx
0x1400205d0  jmp     loc_140020680
0x1400205d5  mov     [rsp+0C8h+var_68], rcx
0x1400205da  mov     [rsp+0C8h+var_80], ecx
0x1400205de  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x1400205e3  lea     r9, [rsp+0C8h+var_68]
0x1400205e8  lea     r8, [rsp+0C8h+var_80]
0x1400205ed  mov     rdx, r13
0x1400205f0  mov     rcx, [rbx+0B8h]
0x1400205f7  call    FatLookupLastMcbEntry
0x1400205fc  mov     eax, [rsp+0C8h+arg_18]
0x140020603  sub     eax, [rdi]
0x140020605  mov     [rsp+0C8h+var_94], eax
0x140020609  mov     edx, 1; PoolType
0x14002060e  lea     rcx, [rsp+0C8h+Mcb]; Mcb
0x140020613  call    cs:__imp_FsRtlInitializeLargeMcb
0x14002061a  nop     dword ptr [rax+rax+00h]
0x14002061f  mov     r12b, 1
0x140020622  mov     [rsp+0C8h+var_97], r12b
0x140020627  lea     rax, [rsp+0C8h+Mcb]
0x14002062c  mov     [rsp+0C8h+var_90], rax
0x140020631  mov     r8, [rsp+0C8h+var_68]
0x140020636  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14002063a  jz      short loc_140020655
0x14002063c  sub     r8, [rsi+160h]
0x140020643  inc     r8
0x140020646  mov     cl, [rsi+17Ah]
0x14002064c  sar     r8, cl
0x14002064f  add     r8d, 2
0x140020653  jmp     short loc_140020658
0x140020655  xor     r8d, r8d
0x140020658  lea     rax, [rsp+0C8h+Mcb]
0x14002065d  mov     [rsp+0C8h+var_A0], rax; __int64
0x140020662  mov     [rsp+0C8h+var_A8], 0; char
0x140020667  lea     r9, [rsp+0C8h+var_94]
0x14002066c  mov     rdx, rsi; int
0x14002066f  mov     rcx, r14; int
0x140020672  call    FatAllocateDiskSpace
0x140020677  mov     [rsp+0C8h+var_98], r12b
0x14002067c  mov     ecx, [rsp+0C8h+var_94]
0x140020680  add     [rdi], ecx
0x140020682  jnz     short loc_14002068F
0x140020684  or      eax, 0FFFFFFFFh
0x140020687  add     ecx, eax
0x140020689  mov     [rsp+0C8h+var_94], ecx
0x14002068d  mov     [rdi], eax
0x14002068f  mov     [rsp+0C8h+var_96], 1
0x140020694  test    r15, r15
0x140020697  jz      short loc_1400206C4
0x140020699  mov     rax, [r15+28h]
0x14002069d  test    rax, rax
0x1400206a0  jz      short loc_1400206C4
0x1400206a2  cmp     qword ptr [rax+8], 0
0x1400206a7  jz      short loc_1400206C4
0x1400206a9  mov     rdx, rdi; FileSizes
0x1400206ac  mov     rcx, r15; FileObject
0x1400206af  call    cs:__imp_CcSetFileSizes
0x1400206b6  nop     dword ptr [rax+rax+00h]
0x1400206bb  mov     [rsp+0C8h+var_95], 1
0x1400206c0  mov     ecx, [rsp+0C8h+var_94]
0x1400206c4  cmp     [rdi], ecx
0x1400206c6  jz      short loc_1400206DC
0x1400206c8  lea     r9, [rsp+0C8h+Mcb]
0x1400206cd  mov     r8, r13
0x1400206d0  mov     rdx, rsi
0x1400206d3  mov     rcx, r14
0x1400206d6  call    FatMergeAllocation
0x1400206db  nop
0x1400206dc  or      dword ptr [rbx+0C0h], 10h
0x1400206e3  mov     rcx, [rsp+0C8h+Bcb]; Bcb
0x1400206e8  test    rcx, rcx
0x1400206eb  jz      short loc_140020702
0x1400206ed  call    cs:__imp_CcUnpinData
0x1400206f4  nop     dword ptr [rax+rax+00h]
0x1400206f9  mov     [rsp+0C8h+Bcb], 0
0x140020702  cmp     r12b, 1
0x140020706  jnz     short loc_140020719
0x140020708  lea     rcx, [rsp+0C8h+Mcb]; Mcb
0x14002070d  call    cs:__imp_FsRtlUninitializeLargeMcb
0x140020714  nop     dword ptr [rax+rax+00h]
0x140020719  add     rsp, 90h
0x140020720  pop     r15
0x140020722  pop     r14
0x140020724  pop     r13
0x140020726  pop     r12
0x140020728  pop     rdi
0x140020729  pop     rsi
0x14002072a  pop     rbx
0x14002072b  retn
0x14005ad11  push    rbx
0x14005ad13  push    rbp
0x14005ad14  sub     rsp, 38h
0x14005ad18  mov     rbp, rdx
0x14005ad1b  mov     [rsp+48h+arg_8], rbp
0x14005ad20  mov     rbx, [rbp+0D8h]
0x14005ad27  or      dword ptr [rbx+0C0h], 10h
0x14005ad2e  test    cl, cl
0x14005ad30  jz      loc_14005ADFE
0x14005ad36  cmp     byte ptr [rbp+32h], 0
0x14005ad3a  jz      short loc_14005AD45
0x14005ad3c  mov     eax, [rbx+18h]
0x14005ad3f  sub     eax, [rbp+34h]
0x14005ad42  mov     [rbx+18h], eax
0x14005ad45  cmp     byte ptr [rbp+33h], 0
0x14005ad49  jz      short loc_14005AD63
0x14005ad4b  lea     rdx, [rbx+18h]; FileSizes
0x14005ad4f  mov     rcx, [rbp+0E0h]; FileObject
0x14005ad56  call    cs:__imp_CcSetFileSizes
0x14005ad5d  nop     dword ptr [rax+rax+00h]
0x14005ad62  nop
0x14005ad63  cmp     dword ptr [rbx+18h], 0
0x14005ad67  jnz     short loc_14005AD97
0x14005ad69  mov     rax, [rbp+50h]
0x14005ad6d  test    rax, rax
0x14005ad70  jz      short loc_14005AD97
0x14005ad72  mov     dword ptr [rbx+80h], 0
0x14005ad7c  xor     ecx, ecx
0x14005ad7e  mov     [rax+1Ah], cx
0x14005ad82  mov     rax, [rbp+68h]
0x14005ad86  cmp     byte ptr [rax+178h], 20h ; ' '
0x14005ad8d  jnz     short loc_14005AD97
0x14005ad8f  mov     rax, [rbp+50h]
0x14005ad93  mov     [rax+14h], cx
0x14005ad97  mov     rcx, [rbp+40h]; Bcb
0x14005ad9b  test    rcx, rcx
0x14005ad9e  jz      short loc_14005ADB4
0x14005ada0  call    cs:__imp_CcUnpinData
0x14005ada7  nop     dword ptr [rax+rax+00h]
0x14005adac  mov     qword ptr [rbp+40h], 0
0x14005adb4  cmp     byte ptr [rbp+30h], 0
0x14005adb8  jz      short loc_14005ADD2
0x14005adba  xor     r9d, r9d
0x14005adbd  mov     r8, [rbp+38h]
0x14005adc1  mov     rdx, [rbp+68h]
0x14005adc5  mov     rcx, [rbp+0D0h]
0x14005adcc  call    FatDeallocateDiskSpace
0x14005add1  nop
0x14005add2  mov     rcx, [rbp+38h]; Mcb
0x14005add6  cmp     byte ptr [rbp+31h], 1
0x14005adda  jnz     short loc_14005ADEA
0x14005addc  call    cs:__imp_FsRtlUninitializeLargeMcb
0x14005ade3  nop     dword ptr [rax+rax+00h]
0x14005ade8  jmp     short loc_14005ADFE
0x14005adea  test    rcx, rcx
0x14005aded  jz      short loc_14005ADFE
0x14005adef  xor     edx, edx; Vbn
0x14005adf1  call    cs:__imp_FsRtlTruncateLargeMcb
0x14005adf8  nop     dword ptr [rax+rax+00h]
0x14005adfd  nop
0x14005adfe  add     rsp, 38h
0x14005ae02  pop     rbp
0x14005ae03  pop     rbx
0x14005ae04  retn
0x14005ae06  push    rbp
0x14005ae08  sub     rsp, 30h
0x14005ae0c  mov     rbp, rdx
0x14005ae0f  mov     rbp, [rbp+58h]
0x14005ae13  mov     rcx, [rbp+38h]; Mcb
0x14005ae17  cmp     byte ptr [rbp+31h], 1
0x14005ae1b  jnz     short loc_14005AE2B
0x14005ae1d  call    cs:__imp_FsRtlUninitializeLargeMcb
0x14005ae24  nop     dword ptr [rax+rax+00h]
0x14005ae29  jmp     short loc_14005AE3F
0x14005ae2b  test    rcx, rcx
0x14005ae2e  jz      short loc_14005AE3F
0x14005ae30  xor     edx, edx; Vbn
0x14005ae32  call    cs:__imp_FsRtlTruncateLargeMcb
0x14005ae39  nop     dword ptr [rax+rax+00h]
0x14005ae3e  nop
0x14005ae3f  add     rsp, 30h
0x14005ae43  pop     rbp
0x14005ae44  retn
```
