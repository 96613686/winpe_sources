# VIDMM_GLOBAL::StartUpgradingAllocation(VIDMM_GLOBAL_ALLOC *)

- ea: `0x1400bfba4`
- end: `0x1400c00f9`
- name: `?StartUpgradingAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@@Z`
- size: `1365`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *this, struct VIDMM_LOCAL_ALLOC **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400ab448`

## callees

- `0x14000d244`
- `0x140034ad8`
- `0x140058680`
- `0x140058760`
- `0x1400587c0`
- `0x1400bfba4`
- `0x14010c8cc`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400bff53`
- `ntoskrnl!KeStackAttachProcess` at `0x1400bff53`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c00a6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c00a6`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400bfff7`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400bfff7`
- `ntoskrnl!MmSizeOfMdl` at `0x1400bfcc1`
- `ntoskrnl!MmSizeOfMdl` at `0x1400bfeb1`
- `ntoskrnl!MmSizeOfMdl` at `0x1400bfcc1`
- `ntoskrnl!MmSizeOfMdl` at `0x1400bfeb1`
- `ntoskrnl!MmUnlockPages` at `0x1400bfe19`
- `ntoskrnl!MmUnlockPages` at `0x1400bfe19`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bfcf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bfe2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bfe52`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bfcf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bfe2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bfe52`
- `ntoskrnl!ExAllocatePool2` at `0x1400bfd14`
- `ntoskrnl!ExAllocatePool2` at `0x1400bfe74`
- `ntoskrnl!ExAllocatePool2` at `0x1400bfecb`
- `ntoskrnl!ExAllocatePool2` at `0x1400bfd14`
- `ntoskrnl!ExAllocatePool2` at `0x1400bfe74`
- `ntoskrnl!ExAllocatePool2` at `0x1400bfecb`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::StartUpgradingAllocation(VIDMM_GLOBAL *this, struct VIDMM_LOCAL_ALLOC **a2)
{
  SIZE_T v5; // r13
  char *v6; // r15
  unsigned int *v7; // r14
  __int64 v8; // r15
  SIZE_T v9; // rax
  SIZE_T v10; // rax
  SIZE_T v11; // r14
  void *v12; // rcx
  __int64 Pool2; // rax
  const unsigned __int64 *FullPfnArray; // rax
  unsigned int v15; // ecx
  unsigned int v16; // r14d
  unsigned int *v17; // r12
  unsigned int v18; // eax
  unsigned int v19; // r15d
  __int64 v20; // rax
  _BYTE *v21; // r14
  unsigned int v22; // r14d
  __int64 v23; // rax
  unsigned int i; // r14d
  unsigned int v25; // ecx
  SIZE_T v26; // rdx
  SIZE_T v27; // rax
  SIZE_T v28; // r12
  SIZE_T v29; // r14
  unsigned int v30; // r15d
  __int64 v31; // r8
  struct _MDL *v32; // r9
  unsigned int v34; // [rsp+48h] [rbp-B0h]
  __int64 v35; // [rsp+50h] [rbp-A8h]
  char *v36; // [rsp+58h] [rbp-A0h]
  __int64 v37; // [rsp+60h] [rbp-98h]
  unsigned int *v39; // [rsp+70h] [rbp-88h]
  struct _KAPC_STATE ApcState; // [rsp+98h] [rbp-60h] BYREF

  v5 = *((_QWORD *)*a2 + 2);
  v6 = (char *)(a2 + 6);
  v36 = (char *)(a2 + 6);
  v7 = (unsigned int *)((char *)this + 40824);
  if ( (byte_140086205 & 0x40) != 0 )
    McTemplateK0ppxx_EtwWriteTransfer(
      *(_QWORD *)(*(_QWORD *)v6 + 16LL),
      (unsigned int)VidMmUpgradeAllocationStart,
      *(_QWORD *)v6,
      (_DWORD)a2,
      v5,
      v5 / *v7,
      *(_QWORD *)(*(_QWORD *)v6 + 16LL));
  else
    v36 = (char *)(a2 + 6);
  *((_QWORD *)this + 5099) = a2;
  *((_QWORD *)this + 5090) = 0;
  v8 = *(_QWORD *)(*(_QWORD *)v6 + 16LL);
  v35 = v8;
  *((_QWORD *)this + 5092) = v8;
  *((_QWORD *)this + 5108) = 0;
  v37 = ((v8 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL) - v8;
  v9 = v5;
  if ( (unsigned __int64)*v7 + v37 < v5 )
    v9 = *v7 + v37;
  *((_QWORD *)this + 5091) = v9;
  *((_QWORD *)this + 5096) = v9;
  *((_QWORD *)this + 5093) = v8 + v9;
  *((_DWORD *)this + 10202) = 0;
  v10 = MmSizeOfMdl(0, v5);
  v11 = v10;
  v12 = (void *)*((_QWORD *)this + 5097);
  if ( v12 )
  {
    if ( v10 <= *((_QWORD *)this + 5098) )
      goto LABEL_11;
    ExFreePoolWithTag(v12, 0);
    *((_QWORD *)this + 5098) = 0;
  }
  Pool2 = ExAllocatePool2(64, v11, 1630562646);
  *((_QWORD *)this + 5097) = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  *((_QWORD *)this + 5098) = v11;
  *(_QWORD *)Pool2 = 0;
  *(_WORD *)(Pool2 + 8) = 8 * (((v5 + (v8 & 0xFFF) + 4095) >> 12) + 6);
  *(_WORD *)(Pool2 + 10) = 0;
  *(_QWORD *)(Pool2 + 32) = v8 & 0xFFFFFFFFFFFFF000uLL;
  *(_DWORD *)(Pool2 + 44) = v8 & 0xFFF;
  *(_DWORD *)(Pool2 + 40) = v5;
  FullPfnArray = VidMmGetFullPfnArray((const struct VIDMM_GLOBAL_ALLOC *)a2);
  memmove((void *)(*((_QWORD *)this + 5097) + 48LL), FullPfnArray, 8 * (v5 >> 12));
LABEL_11:
  v15 = *((_DWORD *)this + 10206);
  v16 = v5 / v15 + 1;
  v34 = v16;
  v17 = (unsigned int *)((char *)this + 40816);
  v39 = v17;
  v18 = *v17;
  if ( v16 > *v17 || v15 != *((_DWORD *)this + 10205) )
  {
    *((_DWORD *)this + 10205) = v15;
    if ( *((_QWORD *)this + 5104) )
    {
      if ( v18 )
      {
        v19 = 0;
        do
        {
          v20 = *((_QWORD *)this + 5104);
          v21 = *(_BYTE **)(v20 + 8LL * v19);
          if ( v21 )
          {
            if ( (v21[10] & 2) != 0 )
              MmUnlockPages(*(PMDL *)(v20 + 8LL * v19));
            ExFreePoolWithTag(v21, 0);
          }
          ++v19;
        }
        while ( v19 < *v17 );
        v16 = v34;
      }
      ExFreePoolWithTag(*((PVOID *)this + 5104), 0);
    }
    v22 = v16 + 5;
    v23 = ExAllocatePool2(64, 8LL * v22, 1630562646);
    *((_QWORD *)this + 5104) = v23;
    if ( v23 )
    {
      *v17 = v22;
      for ( i = 0; i < *v17; ++i )
      {
        v25 = *((_DWORD *)this + 10205);
        v26 = v25 + 0x10000;
        if ( i )
          v26 = v25;
        v27 = MmSizeOfMdl(0, v26);
        *(_QWORD *)(*((_QWORD *)this + 5104) + 8LL * i) = ExAllocatePool2(64, v27, 1630562646);
        if ( !*(_QWORD *)(*((_QWORD *)this + 5104) + 8LL * i) )
          return 3221225495LL;
      }
      goto LABEL_30;
    }
    return 3221225495LL;
  }
LABEL_30:
  v28 = v5;
  v29 = v37 + *((unsigned int *)this + 10205);
  v30 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  KeStackAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(*(_QWORD *)v36 + 8LL) + 16LL), &ApcState);
  v31 = v35;
  while ( v28 && v30 < *v39 )
  {
    v32 = *(struct _MDL **)(*((_QWORD *)this + 5104) + 8LL * v30);
    if ( v29 >= v28 )
      v29 = v28;
    v32->Next = 0;
    v32->Size = 8 * (((v29 + (v31 & 0xFFF) + 4095) >> 12) + 6);
    v32->MdlFlags = 0;
    v32->StartVa = (PVOID)(v31 & 0xFFFFFFFFFFFFF000uLL);
    v32->ByteOffset = v31 & 0xFFF;
    v32->ByteCount = v29;
    MmProbeAndLockPages(v32, 0, (LOCK_OPERATION)(~(unsigned __int8)(*((_DWORD *)a2 + 6) >> 5) & 2));
    v28 -= v29;
    v31 = v29 + v35;
    v35 += v29;
    v29 = *((unsigned int *)this + 10205);
    ++v30;
  }
  *((_DWORD *)this + 10203) = v30;
  VIDMM_GLOBAL::UnlockAllocation(this, a2[6], 0, v5, 0, 0);
  (*(void (__fastcall **)(struct VIDMM_LOCAL_ALLOC *))(*(_QWORD *)a2[29] + 88LL))(a2[29]);
  KeUnstackDetachProcess(&ApcState);
  *((_DWORD *)a2 + 6) |= 0x80000000;
  a2[8] = (struct VIDMM_LOCAL_ALLOC *)*((_QWORD *)this + 5097);
  return 0;
}

```

## disassembly

```asm
0x1400bfba4  mov     [rsp+arg_10], rbx
0x1400bfba9  mov     [rsp+arg_18], rsi
0x1400bfbae  push    rdi
0x1400bfbaf  push    r12
0x1400bfbb1  push    r13
0x1400bfbb3  push    r14
0x1400bfbb5  push    r15
0x1400bfbb7  sub     rsp, 0D0h
0x1400bfbbe  mov     rax, cs:__security_cookie
0x1400bfbc5  xor     rax, rsp
0x1400bfbc8  mov     [rsp+0F8h+var_30], rax
0x1400bfbd0  mov     rsi, rdx
0x1400bfbd3  mov     r12, rcx
0x1400bfbd6  mov     [rsp+0F8h+var_90], rcx
0x1400bfbdb  mov     [rsp+0F8h+var_70], rcx
0x1400bfbe3  mov     rbx, rcx
0x1400bfbe6  mov     [rsp+0F8h+var_78], rdx
0x1400bfbee  mov     rax, [rdx]
0x1400bfbf1  mov     r13, [rax+10h]
0x1400bfbf5  lea     r15, [rdx+30h]
0x1400bfbf9  mov     [rsp+0F8h+var_A0], r15
0x1400bfbfe  lea     r14, [rcx+9F78h]
0x1400bfc05  test    cs:byte_140086205, 40h
0x1400bfc0c  jz      short loc_1400BFC40
0x1400bfc0e  mov     r8, [r15]
0x1400bfc11  mov     ecx, [r14]
0x1400bfc14  xor     edx, edx
0x1400bfc16  mov     rax, r13
0x1400bfc19  div     rcx
0x1400bfc1c  mov     rcx, [r8+10h]
0x1400bfc20  mov     [rsp+0F8h+var_C8], rcx
0x1400bfc25  mov     qword ptr [rsp+0F8h+var_D0], rax
0x1400bfc2a  mov     qword ptr [rsp+0F8h+var_D8], r13
0x1400bfc2f  mov     r9, rsi
0x1400bfc32  lea     rdx, VidMmUpgradeAllocationStart
0x1400bfc39  call    McTemplateK0ppxx_EtwWriteTransfer
0x1400bfc3e  jmp     short loc_1400BFC45
0x1400bfc40  mov     [rsp+0F8h+var_A0], r15
0x1400bfc45  mov     [r12+9F58h], rsi
0x1400bfc4d  xor     edi, edi
0x1400bfc4f  mov     [r12+9F10h], rdi
0x1400bfc57  mov     rax, [r15]
0x1400bfc5a  mov     r15, [rax+10h]
0x1400bfc5e  mov     [rsp+0F8h+var_A8], r15
0x1400bfc63  mov     [r12+9F20h], r15
0x1400bfc6b  mov     [r12+9FA0h], rdi
0x1400bfc73  lea     rcx, [r15+0FFFFh]
0x1400bfc7a  and     rcx, 0FFFFFFFFFFFF0000h
0x1400bfc81  sub     rcx, r15
0x1400bfc84  mov     [rsp+0F8h+var_98], rcx
0x1400bfc89  mov     eax, [r14]
0x1400bfc8c  add     rcx, rax
0x1400bfc8f  mov     rax, r13
0x1400bfc92  cmp     rcx, r13
0x1400bfc95  cmovb   rax, rcx
0x1400bfc99  mov     [r12+9F18h], rax
0x1400bfca1  mov     [r12+9F40h], rax
0x1400bfca9  add     rax, r15
0x1400bfcac  mov     [r12+9F28h], rax
0x1400bfcb4  mov     [r12+9F68h], edi
0x1400bfcbc  mov     rdx, r13; Length
0x1400bfcbf  xor     ecx, ecx; Base
0x1400bfcc1  call    cs:__imp_MmSizeOfMdl
0x1400bfcc8  nop     dword ptr [rax+rax+00h]
0x1400bfccd  mov     r14, rax
0x1400bfcd0  mov     rcx, [r12+9F48h]; P
0x1400bfcd8  test    rcx, rcx
0x1400bfcdb  jz      short loc_1400BFD06
0x1400bfcdd  cmp     rax, [r12+9F50h]
0x1400bfce5  jbe     loc_1400BFDAC
0x1400bfceb  test    rcx, rcx
0x1400bfcee  jz      short loc_1400BFD06
0x1400bfcf0  xor     edx, edx; Tag
0x1400bfcf2  call    cs:__imp_ExFreePoolWithTag
0x1400bfcf9  nop     dword ptr [rax+rax+00h]
0x1400bfcfe  mov     [r12+9F50h], rdi
0x1400bfd06  mov     r8d, 61306956h
0x1400bfd0c  mov     rdx, r14
0x1400bfd0f  mov     ecx, 40h ; '@'
0x1400bfd14  call    cs:__imp_ExAllocatePool2
0x1400bfd1b  nop     dword ptr [rax+rax+00h]
0x1400bfd20  mov     r9, rax
0x1400bfd23  mov     [r12+9F48h], rax
0x1400bfd2b  test    rax, rax
0x1400bfd2e  jz      loc_1400C00C6
0x1400bfd34  mov     [r12+9F50h], r14
0x1400bfd3c  mov     [rax], rdi
0x1400bfd3f  mov     r8d, r15d
0x1400bfd42  mov     edx, r8d
0x1400bfd45  and     edx, 0FFFh
0x1400bfd4b  add     rdx, 0FFFh
0x1400bfd52  add     rdx, r13
0x1400bfd55  shr     rdx, 0Ch
0x1400bfd59  add     dx, 6
0x1400bfd5d  shl     dx, 3
0x1400bfd61  mov     [rax+8], dx
0x1400bfd65  mov     [rax+0Ah], di
0x1400bfd69  mov     rax, r15
0x1400bfd6c  and     rax, 0FFFFFFFFFFFFF000h
0x1400bfd72  mov     [r9+20h], rax
0x1400bfd76  and     r8d, 0FFFh
0x1400bfd7d  mov     [r9+2Ch], r8d
0x1400bfd81  mov     [r9+28h], r13d
0x1400bfd85  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400bfd88  call    ?VidMmGetFullPfnArray@@YAPEB_KPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetFullPfnArray(VIDMM_GLOBAL_ALLOC const *)
0x1400bfd8d  mov     r8, r13
0x1400bfd90  shr     r8, 0Ch
0x1400bfd94  shl     r8, 3; Size
0x1400bfd98  mov     rcx, [r12+9F48h]
0x1400bfda0  add     rcx, 30h ; '0'; void *
0x1400bfda4  mov     rdx, rax; Src
0x1400bfda7  call    memmove
0x1400bfdac  mov     ecx, [r12+9F78h]
0x1400bfdb4  xor     edx, edx
0x1400bfdb6  mov     rax, r13
0x1400bfdb9  div     rcx
0x1400bfdbc  lea     r14d, [rax+1]
0x1400bfdc0  mov     dword ptr [rsp+0F8h+var_B0], r14d
0x1400bfdc5  add     r12, 9F70h
0x1400bfdcc  mov     [rsp+0F8h+var_88], r12
0x1400bfdd1  mov     eax, [r12]
0x1400bfdd5  cmp     r14d, eax
0x1400bfdd8  ja      short loc_1400BFDE6
0x1400bfdda  cmp     ecx, [rbx+9F74h]
0x1400bfde0  jz      loc_1400BFEFB
0x1400bfde6  mov     [rbx+9F74h], ecx
0x1400bfdec  cmp     [rbx+9F80h], rdi
0x1400bfdf3  jz      short loc_1400BFE5E
0x1400bfdf5  test    eax, eax
0x1400bfdf7  jz      short loc_1400BFE49
0x1400bfdf9  mov     r15d, edi
0x1400bfdfc  mov     ecx, r15d
0x1400bfdff  mov     rax, [rbx+9F80h]
0x1400bfe06  mov     r14, [rax+rcx*8]
0x1400bfe0a  test    r14, r14
0x1400bfe0d  jz      short loc_1400BFE36
0x1400bfe0f  test    byte ptr [r14+0Ah], 2
0x1400bfe14  jz      short loc_1400BFE25
0x1400bfe16  mov     rcx, r14; MemoryDescriptorList
0x1400bfe19  call    cs:__imp_MmUnlockPages
0x1400bfe20  nop     dword ptr [rax+rax+00h]
0x1400bfe25  xor     edx, edx; Tag
0x1400bfe27  mov     rcx, r14; P
0x1400bfe2a  call    cs:__imp_ExFreePoolWithTag
0x1400bfe31  nop     dword ptr [rax+rax+00h]
0x1400bfe36  inc     r15d
0x1400bfe39  cmp     r15d, [r12]
0x1400bfe3d  jb      short loc_1400BFDFC
0x1400bfe3f  mov     r15, [rsp+0F8h+var_A8]
0x1400bfe44  mov     r14d, dword ptr [rsp+0F8h+var_B0]
0x1400bfe49  xor     edx, edx; Tag
0x1400bfe4b  mov     rcx, [rbx+9F80h]; P
0x1400bfe52  call    cs:__imp_ExFreePoolWithTag
0x1400bfe59  nop     dword ptr [rax+rax+00h]
0x1400bfe5e  add     r14d, 5
0x1400bfe62  mov     edx, r14d
0x1400bfe65  shl     rdx, 3
0x1400bfe69  mov     ecx, 40h ; '@'
0x1400bfe6e  mov     r8d, 61306956h
0x1400bfe74  call    cs:__imp_ExAllocatePool2
0x1400bfe7b  nop     dword ptr [rax+rax+00h]
0x1400bfe80  mov     [rbx+9F80h], rax
0x1400bfe87  test    rax, rax
0x1400bfe8a  jz      loc_1400C00C6
0x1400bfe90  mov     [r12], r14d
0x1400bfe94  mov     r14d, edi
0x1400bfe97  cmp     r14d, [r12]
0x1400bfe9b  jnb     short loc_1400BFEFB
0x1400bfe9d  mov     ecx, [rbx+9F74h]
0x1400bfea3  lea     edx, [rcx+10000h]
0x1400bfea9  test    r14d, r14d
0x1400bfeac  cmovnz  edx, ecx; Length
0x1400bfeaf  xor     ecx, ecx; Base
0x1400bfeb1  call    cs:__imp_MmSizeOfMdl
0x1400bfeb8  nop     dword ptr [rax+rax+00h]
0x1400bfebd  mov     rdx, rax
0x1400bfec0  mov     ecx, 40h ; '@'
0x1400bfec5  mov     r8d, 61306956h
0x1400bfecb  call    cs:__imp_ExAllocatePool2
0x1400bfed2  nop     dword ptr [rax+rax+00h]
0x1400bfed7  mov     edx, r14d
0x1400bfeda  mov     rcx, [rbx+9F80h]
0x1400bfee1  mov     [rcx+rdx*8], rax
0x1400bfee5  mov     rax, [rbx+9F80h]
0x1400bfeec  cmp     [rax+rdx*8], rdi
0x1400bfef0  jz      loc_1400C00C6
0x1400bfef6  inc     r14d
0x1400bfef9  jmp     short loc_1400BFE97
0x1400bfefb  mov     [rsp+0F8h+var_80], r13
0x1400bff00  mov     r12, r13
0x1400bff03  mov     [rsp+0F8h+var_B0], r13
0x1400bff08  mov     r14d, [rbx+9F74h]
0x1400bff0f  add     r14, [rsp+0F8h+var_98]
0x1400bff14  mov     [rsp+0F8h+var_98], r15
0x1400bff19  mov     r15d, edi
0x1400bff1c  mov     [rsp+0F8h+var_B8], edi
0x1400bff20  xorps   xmm0, xmm0
0x1400bff23  movups  xmmword ptr [rsp+0F8h+ApcState.ApcListHead.Flink], xmm0
0x1400bff2b  movups  xmmword ptr [rsp+0F8h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400bff33  movups  xmmword ptr [rsp+0F8h+ApcState.Process], xmm0
0x1400bff3b  mov     rax, [rsp+0F8h+var_A0]
0x1400bff40  mov     rax, [rax]
0x1400bff43  mov     rcx, [rax+8]
0x1400bff47  lea     rdx, [rsp+0F8h+ApcState]; ApcState
0x1400bff4f  mov     rcx, [rcx+10h]; PROCESS
0x1400bff53  call    cs:__imp_KeStackAttachProcess
0x1400bff5a  nop     dword ptr [rax+rax+00h]
0x1400bff5f  mov     r8, [rsp+0F8h+var_A8]
0x1400bff64  test    r12, r12
0x1400bff67  jz      loc_1400C0066
0x1400bff6d  mov     rax, [rsp+0F8h+var_88]
0x1400bff72  cmp     r15d, [rax]
0x1400bff75  jnb     loc_1400C0066
0x1400bff7b  mov     ecx, r15d
0x1400bff7e  mov     rax, [rsp+0F8h+var_90]
0x1400bff83  mov     rax, [rax+9F80h]
0x1400bff8a  mov     r9, [rax+rcx*8]
0x1400bff8e  cmp     r14, r12
0x1400bff91  cmovnb  r14, r12
0x1400bff95  mov     [rsp+0F8h+var_A0], r14
0x1400bff9a  mov     [r9], rdi
0x1400bff9d  mov     edx, r8d
0x1400bffa0  mov     ecx, edx
0x1400bffa2  and     ecx, 0FFFh
0x1400bffa8  add     rcx, 0FFFh
0x1400bffaf  add     rcx, r14
0x1400bffb2  shr     rcx, 0Ch
0x1400bffb6  add     cx, 6
0x1400bffba  shl     cx, 3
0x1400bffbe  mov     [r9+8], cx
0x1400bffc3  mov     [r9+0Ah], di
0x1400bffc8  mov     rax, r8
0x1400bffcb  and     rax, 0FFFFFFFFFFFFF000h
0x1400bffd1  mov     [r9+20h], rax
0x1400bffd5  and     edx, 0FFFh
0x1400bffdb  mov     [r9+2Ch], edx
0x1400bffdf  mov     [r9+28h], r14d
0x1400bffe3  mov     r8d, [rsi+18h]
0x1400bffe7  shr     r8d, 5
0x1400bffeb  not     r8d
0x1400bffee  and     r8d, 2; Operation
0x1400bfff2  xor     edx, edx; AccessMode
0x1400bfff4  mov     rcx, r9; MemoryDescriptorList
0x1400bfff7  call    cs:__imp_MmProbeAndLockPages
0x1400bfffe  nop     dword ptr [rax+rax+00h]
0x1400c0003  mov     r8, [rsp+0F8h+var_A8]
0x1400c0008  jmp     short loc_1400C003D
0x1400c000a  xor     edi, edi
0x1400c000c  mov     r13, [rsp+0F8h+var_80]
0x1400c0011  mov     r12, [rsp+0F8h+var_B0]
0x1400c0016  mov     r14, [rsp+0F8h+var_A0]
0x1400c001b  mov     r8, [rsp+0F8h+var_98]
0x1400c0020  mov     r15d, [rsp+0F8h+var_B8]
0x1400c0025  mov     rsi, [rsp+0F8h+var_78]
0x1400c002d  mov     rax, [rsp+0F8h+var_70]
0x1400c0035  mov     [rsp+0F8h+var_90], rax
0x1400c003a  mov     rbx, rax
0x1400c003d  sub     r12, r14
0x1400c0040  mov     [rsp+0F8h+var_B0], r12
0x1400c0045  add     r8, r14
0x1400c0048  mov     [rsp+0F8h+var_A8], r8
0x1400c004d  mov     [rsp+0F8h+var_98], r8
0x1400c0052  mov     r14d, [rbx+9F74h]
0x1400c0059  inc     r15d
0x1400c005c  mov     [rsp+0F8h+var_B8], r15d
0x1400c0061  jmp     loc_1400BFF64
0x1400c0066  mov     [rbx+9F6Ch], r15d
0x1400c006d  mov     [rsp+0F8h+var_D0], dil; bool
0x1400c0072  mov     [rsp+0F8h+var_D8], dil; bool
0x1400c0077  mov     r9, r13; unsigned __int64
0x1400c007a  xor     r8d, r8d; unsigned __int64
0x1400c007d  mov     rdx, [rsi+30h]; struct VIDMM_LOCAL_ALLOC *
0x1400c0081  mov     rcx, [rsp+0F8h+var_90]; this
0x1400c0086  call    ?UnlockAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_K1_N2@Z; VIDMM_GLOBAL::UnlockAllocation(VIDMM_LOCAL_ALLOC *,unsigned __int64,unsigned __int64,bool,bool)
0x1400c008b  mov     rcx, [rsi+0E8h]
0x1400c0092  mov     rax, [rcx]
0x1400c0095  mov     rax, [rax+58h]
0x1400c0099  call    _guard_dispatch_icall
0x1400c009e  lea     rcx, [rsp+0F8h+ApcState]; ApcState
0x1400c00a6  call    cs:__imp_KeUnstackDetachProcess
0x1400c00ad  nop     dword ptr [rax+rax+00h]
0x1400c00b2  bts     dword ptr [rsi+18h], 1Fh
0x1400c00b7  mov     rax, [rbx+9F48h]
0x1400c00be  mov     [rsi+40h], rax
0x1400c00c2  xor     eax, eax
0x1400c00c4  jmp     short loc_1400C00CB
0x1400c00c6  mov     eax, 0C0000017h
0x1400c00cb  mov     rcx, [rsp+0F8h+var_30]
0x1400c00d3  xor     rcx, rsp; StackCookie
0x1400c00d6  call    __security_check_cookie
0x1400c00db  lea     r11, [rsp+0F8h+var_28]
0x1400c00e3  mov     rbx, [r11+40h]
0x1400c00e7  mov     rsi, [r11+48h]
0x1400c00eb  mov     rsp, r11
0x1400c00ee  pop     r15
0x1400c00f0  pop     r14
0x1400c00f2  pop     r13
0x1400c00f4  pop     r12
0x1400c00f6  pop     rdi
0x1400c00f7  retn
  ... truncated ...
```
