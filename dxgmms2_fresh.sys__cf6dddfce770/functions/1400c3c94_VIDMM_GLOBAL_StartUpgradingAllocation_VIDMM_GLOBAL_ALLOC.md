# VIDMM_GLOBAL::StartUpgradingAllocation(VIDMM_GLOBAL_ALLOC *)

- ea: `0x1400c3c94`
- end: `0x1400c41e9`
- name: `?StartUpgradingAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@@Z`
- size: `1365`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *this, struct VIDMM_LOCAL_ALLOC **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400ac7f8`

## callees

- `0x14000cf94`
- `0x1400333c8`
- `0x140058f50`
- `0x140059030`
- `0x140059080`
- `0x1400c3c94`
- `0x1401104dc`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400c4043`
- `ntoskrnl!KeStackAttachProcess` at `0x1400c4043`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c4196`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c4196`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400c40e7`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400c40e7`
- `ntoskrnl!MmSizeOfMdl` at `0x1400c3db1`
- `ntoskrnl!MmSizeOfMdl` at `0x1400c3fa1`
- `ntoskrnl!MmSizeOfMdl` at `0x1400c3db1`
- `ntoskrnl!MmSizeOfMdl` at `0x1400c3fa1`
- `ntoskrnl!MmUnlockPages` at `0x1400c3f09`
- `ntoskrnl!MmUnlockPages` at `0x1400c3f09`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3f1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3f1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c3f42`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3e04`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3f64`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3fbb`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3e04`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3f64`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3fbb`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::StartUpgradingAllocation(VIDMM_GLOBAL *this, struct VIDMM_LOCAL_ALLOC **a2)
{
  SIZE_T v5; // r13
  struct VIDMM_LOCAL_ALLOC **v6; // r15
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
  struct VIDMM_LOCAL_ALLOC **v36; // [rsp+58h] [rbp-A0h]
  __int64 v37; // [rsp+60h] [rbp-98h]
  unsigned int *v39; // [rsp+70h] [rbp-88h]
  struct _KAPC_STATE ApcState; // [rsp+98h] [rbp-60h] BYREF

  v5 = *((_QWORD *)*a2 + 2);
  v6 = a2 + 6;
  v36 = a2 + 6;
  v7 = (unsigned int *)((char *)this + 40824);
  if ( (byte_140087205 & 0x40) != 0 )
    McTemplateK0ppxx_EtwWriteTransfer(
      *((_QWORD *)*v6 + 2),
      (unsigned int)&VidMmUpgradeAllocationStart,
      (unsigned int)*v6,
      (_DWORD)a2,
      v5,
      v5 / *v7,
      *((_QWORD *)*v6 + 2));
  else
    v36 = a2 + 6;
  *((_QWORD *)this + 5099) = a2;
  *((_QWORD *)this + 5090) = 0;
  v8 = *((_QWORD *)*v6 + 2);
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
  KeStackAttachProcess(*(PRKPROCESS *)(*((_QWORD *)*v36 + 1) + 16LL), &ApcState);
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
0x1400c3c94  mov     [rsp+arg_10], rbx
0x1400c3c99  mov     [rsp+arg_18], rsi
0x1400c3c9e  push    rdi
0x1400c3c9f  push    r12
0x1400c3ca1  push    r13
0x1400c3ca3  push    r14
0x1400c3ca5  push    r15
0x1400c3ca7  sub     rsp, 0D0h
0x1400c3cae  mov     rax, cs:__security_cookie
0x1400c3cb5  xor     rax, rsp
0x1400c3cb8  mov     [rsp+0F8h+var_30], rax
0x1400c3cc0  mov     rsi, rdx
0x1400c3cc3  mov     r12, rcx
0x1400c3cc6  mov     [rsp+0F8h+var_90], rcx
0x1400c3ccb  mov     [rsp+0F8h+var_70], rcx
0x1400c3cd3  mov     rbx, rcx
0x1400c3cd6  mov     [rsp+0F8h+var_78], rdx
0x1400c3cde  mov     rax, [rdx]
0x1400c3ce1  mov     r13, [rax+10h]
0x1400c3ce5  lea     r15, [rdx+30h]
0x1400c3ce9  mov     [rsp+0F8h+var_A0], r15
0x1400c3cee  lea     r14, [rcx+9F78h]
0x1400c3cf5  test    cs:byte_140087205, 40h
0x1400c3cfc  jz      short loc_1400C3D30
0x1400c3cfe  mov     r8, [r15]
0x1400c3d01  mov     ecx, [r14]
0x1400c3d04  xor     edx, edx
0x1400c3d06  mov     rax, r13
0x1400c3d09  div     rcx
0x1400c3d0c  mov     rcx, [r8+10h]
0x1400c3d10  mov     [rsp+0F8h+var_C8], rcx
0x1400c3d15  mov     qword ptr [rsp+0F8h+var_D0], rax
0x1400c3d1a  mov     qword ptr [rsp+0F8h+var_D8], r13
0x1400c3d1f  mov     r9, rsi
0x1400c3d22  lea     rdx, VidMmUpgradeAllocationStart
0x1400c3d29  call    McTemplateK0ppxx_EtwWriteTransfer
0x1400c3d2e  jmp     short loc_1400C3D35
0x1400c3d30  mov     [rsp+0F8h+var_A0], r15
0x1400c3d35  mov     [r12+9F58h], rsi
0x1400c3d3d  xor     edi, edi
0x1400c3d3f  mov     [r12+9F10h], rdi
0x1400c3d47  mov     rax, [r15]
0x1400c3d4a  mov     r15, [rax+10h]
0x1400c3d4e  mov     [rsp+0F8h+var_A8], r15
0x1400c3d53  mov     [r12+9F20h], r15
0x1400c3d5b  mov     [r12+9FA0h], rdi
0x1400c3d63  lea     rcx, [r15+0FFFFh]
0x1400c3d6a  and     rcx, 0FFFFFFFFFFFF0000h
0x1400c3d71  sub     rcx, r15
0x1400c3d74  mov     [rsp+0F8h+var_98], rcx
0x1400c3d79  mov     eax, [r14]
0x1400c3d7c  add     rcx, rax
0x1400c3d7f  mov     rax, r13
0x1400c3d82  cmp     rcx, r13
0x1400c3d85  cmovb   rax, rcx
0x1400c3d89  mov     [r12+9F18h], rax
0x1400c3d91  mov     [r12+9F40h], rax
0x1400c3d99  add     rax, r15
0x1400c3d9c  mov     [r12+9F28h], rax
0x1400c3da4  mov     [r12+9F68h], edi
0x1400c3dac  mov     rdx, r13; Length
0x1400c3daf  xor     ecx, ecx; Base
0x1400c3db1  call    cs:__imp_MmSizeOfMdl
0x1400c3db8  nop     dword ptr [rax+rax+00h]
0x1400c3dbd  mov     r14, rax
0x1400c3dc0  mov     rcx, [r12+9F48h]; P
0x1400c3dc8  test    rcx, rcx
0x1400c3dcb  jz      short loc_1400C3DF6
0x1400c3dcd  cmp     rax, [r12+9F50h]
0x1400c3dd5  jbe     loc_1400C3E9C
0x1400c3ddb  test    rcx, rcx
0x1400c3dde  jz      short loc_1400C3DF6
0x1400c3de0  xor     edx, edx; Tag
0x1400c3de2  call    cs:__imp_ExFreePoolWithTag
0x1400c3de9  nop     dword ptr [rax+rax+00h]
0x1400c3dee  mov     [r12+9F50h], rdi
0x1400c3df6  mov     r8d, 61306956h
0x1400c3dfc  mov     rdx, r14
0x1400c3dff  mov     ecx, 40h ; '@'
0x1400c3e04  call    cs:__imp_ExAllocatePool2
0x1400c3e0b  nop     dword ptr [rax+rax+00h]
0x1400c3e10  mov     r9, rax
0x1400c3e13  mov     [r12+9F48h], rax
0x1400c3e1b  test    rax, rax
0x1400c3e1e  jz      loc_1400C41B6
0x1400c3e24  mov     [r12+9F50h], r14
0x1400c3e2c  mov     [rax], rdi
0x1400c3e2f  mov     r8d, r15d
0x1400c3e32  mov     edx, r8d
0x1400c3e35  and     edx, 0FFFh
0x1400c3e3b  add     rdx, 0FFFh
0x1400c3e42  add     rdx, r13
0x1400c3e45  shr     rdx, 0Ch
0x1400c3e49  add     dx, 6
0x1400c3e4d  shl     dx, 3
0x1400c3e51  mov     [rax+8], dx
0x1400c3e55  mov     [rax+0Ah], di
0x1400c3e59  mov     rax, r15
0x1400c3e5c  and     rax, 0FFFFFFFFFFFFF000h
0x1400c3e62  mov     [r9+20h], rax
0x1400c3e66  and     r8d, 0FFFh
0x1400c3e6d  mov     [r9+2Ch], r8d
0x1400c3e71  mov     [r9+28h], r13d
0x1400c3e75  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400c3e78  call    ?VidMmGetFullPfnArray@@YAPEB_KPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetFullPfnArray(VIDMM_GLOBAL_ALLOC const *)
0x1400c3e7d  mov     r8, r13
0x1400c3e80  shr     r8, 0Ch
0x1400c3e84  shl     r8, 3; Size
0x1400c3e88  mov     rcx, [r12+9F48h]
0x1400c3e90  add     rcx, 30h ; '0'; void *
0x1400c3e94  mov     rdx, rax; Src
0x1400c3e97  call    memmove
0x1400c3e9c  mov     ecx, [r12+9F78h]
0x1400c3ea4  xor     edx, edx
0x1400c3ea6  mov     rax, r13
0x1400c3ea9  div     rcx
0x1400c3eac  lea     r14d, [rax+1]
0x1400c3eb0  mov     dword ptr [rsp+0F8h+var_B0], r14d
0x1400c3eb5  add     r12, 9F70h
0x1400c3ebc  mov     [rsp+0F8h+var_88], r12
0x1400c3ec1  mov     eax, [r12]
0x1400c3ec5  cmp     r14d, eax
0x1400c3ec8  ja      short loc_1400C3ED6
0x1400c3eca  cmp     ecx, [rbx+9F74h]
0x1400c3ed0  jz      loc_1400C3FEB
0x1400c3ed6  mov     [rbx+9F74h], ecx
0x1400c3edc  cmp     [rbx+9F80h], rdi
0x1400c3ee3  jz      short loc_1400C3F4E
0x1400c3ee5  test    eax, eax
0x1400c3ee7  jz      short loc_1400C3F39
0x1400c3ee9  mov     r15d, edi
0x1400c3eec  mov     ecx, r15d
0x1400c3eef  mov     rax, [rbx+9F80h]
0x1400c3ef6  mov     r14, [rax+rcx*8]
0x1400c3efa  test    r14, r14
0x1400c3efd  jz      short loc_1400C3F26
0x1400c3eff  test    byte ptr [r14+0Ah], 2
0x1400c3f04  jz      short loc_1400C3F15
0x1400c3f06  mov     rcx, r14; MemoryDescriptorList
0x1400c3f09  call    cs:__imp_MmUnlockPages
0x1400c3f10  nop     dword ptr [rax+rax+00h]
0x1400c3f15  xor     edx, edx; Tag
0x1400c3f17  mov     rcx, r14; P
0x1400c3f1a  call    cs:__imp_ExFreePoolWithTag
0x1400c3f21  nop     dword ptr [rax+rax+00h]
0x1400c3f26  inc     r15d
0x1400c3f29  cmp     r15d, [r12]
0x1400c3f2d  jb      short loc_1400C3EEC
0x1400c3f2f  mov     r15, [rsp+0F8h+var_A8]
0x1400c3f34  mov     r14d, dword ptr [rsp+0F8h+var_B0]
0x1400c3f39  xor     edx, edx; Tag
0x1400c3f3b  mov     rcx, [rbx+9F80h]; P
0x1400c3f42  call    cs:__imp_ExFreePoolWithTag
0x1400c3f49  nop     dword ptr [rax+rax+00h]
0x1400c3f4e  add     r14d, 5
0x1400c3f52  mov     edx, r14d
0x1400c3f55  shl     rdx, 3
0x1400c3f59  mov     ecx, 40h ; '@'
0x1400c3f5e  mov     r8d, 61306956h
0x1400c3f64  call    cs:__imp_ExAllocatePool2
0x1400c3f6b  nop     dword ptr [rax+rax+00h]
0x1400c3f70  mov     [rbx+9F80h], rax
0x1400c3f77  test    rax, rax
0x1400c3f7a  jz      loc_1400C41B6
0x1400c3f80  mov     [r12], r14d
0x1400c3f84  mov     r14d, edi
0x1400c3f87  cmp     r14d, [r12]
0x1400c3f8b  jnb     short loc_1400C3FEB
0x1400c3f8d  mov     ecx, [rbx+9F74h]
0x1400c3f93  lea     edx, [rcx+10000h]
0x1400c3f99  test    r14d, r14d
0x1400c3f9c  cmovnz  edx, ecx; Length
0x1400c3f9f  xor     ecx, ecx; Base
0x1400c3fa1  call    cs:__imp_MmSizeOfMdl
0x1400c3fa8  nop     dword ptr [rax+rax+00h]
0x1400c3fad  mov     rdx, rax
0x1400c3fb0  mov     ecx, 40h ; '@'
0x1400c3fb5  mov     r8d, 61306956h
0x1400c3fbb  call    cs:__imp_ExAllocatePool2
0x1400c3fc2  nop     dword ptr [rax+rax+00h]
0x1400c3fc7  mov     edx, r14d
0x1400c3fca  mov     rcx, [rbx+9F80h]
0x1400c3fd1  mov     [rcx+rdx*8], rax
0x1400c3fd5  mov     rax, [rbx+9F80h]
0x1400c3fdc  cmp     [rax+rdx*8], rdi
0x1400c3fe0  jz      loc_1400C41B6
0x1400c3fe6  inc     r14d
0x1400c3fe9  jmp     short loc_1400C3F87
0x1400c3feb  mov     [rsp+0F8h+var_80], r13
0x1400c3ff0  mov     r12, r13
0x1400c3ff3  mov     [rsp+0F8h+var_B0], r13
0x1400c3ff8  mov     r14d, [rbx+9F74h]
0x1400c3fff  add     r14, [rsp+0F8h+var_98]
0x1400c4004  mov     [rsp+0F8h+var_98], r15
0x1400c4009  mov     r15d, edi
0x1400c400c  mov     [rsp+0F8h+var_B8], edi
0x1400c4010  xorps   xmm0, xmm0
0x1400c4013  movups  xmmword ptr [rsp+0F8h+ApcState.ApcListHead.Flink], xmm0
0x1400c401b  movups  xmmword ptr [rsp+0F8h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400c4023  movups  xmmword ptr [rsp+0F8h+ApcState.Process], xmm0
0x1400c402b  mov     rax, [rsp+0F8h+var_A0]
0x1400c4030  mov     rax, [rax]
0x1400c4033  mov     rcx, [rax+8]
0x1400c4037  lea     rdx, [rsp+0F8h+ApcState]; ApcState
0x1400c403f  mov     rcx, [rcx+10h]; PROCESS
0x1400c4043  call    cs:__imp_KeStackAttachProcess
0x1400c404a  nop     dword ptr [rax+rax+00h]
0x1400c404f  mov     r8, [rsp+0F8h+var_A8]
0x1400c4054  test    r12, r12
0x1400c4057  jz      loc_1400C4156
0x1400c405d  mov     rax, [rsp+0F8h+var_88]
0x1400c4062  cmp     r15d, [rax]
0x1400c4065  jnb     loc_1400C4156
0x1400c406b  mov     ecx, r15d
0x1400c406e  mov     rax, [rsp+0F8h+var_90]
0x1400c4073  mov     rax, [rax+9F80h]
0x1400c407a  mov     r9, [rax+rcx*8]
0x1400c407e  cmp     r14, r12
0x1400c4081  cmovnb  r14, r12
0x1400c4085  mov     [rsp+0F8h+var_A0], r14
0x1400c408a  mov     [r9], rdi
0x1400c408d  mov     edx, r8d
0x1400c4090  mov     ecx, edx
0x1400c4092  and     ecx, 0FFFh
0x1400c4098  add     rcx, 0FFFh
0x1400c409f  add     rcx, r14
0x1400c40a2  shr     rcx, 0Ch
0x1400c40a6  add     cx, 6
0x1400c40aa  shl     cx, 3
0x1400c40ae  mov     [r9+8], cx
0x1400c40b3  mov     [r9+0Ah], di
0x1400c40b8  mov     rax, r8
0x1400c40bb  and     rax, 0FFFFFFFFFFFFF000h
0x1400c40c1  mov     [r9+20h], rax
0x1400c40c5  and     edx, 0FFFh
0x1400c40cb  mov     [r9+2Ch], edx
0x1400c40cf  mov     [r9+28h], r14d
0x1400c40d3  mov     r8d, [rsi+18h]
0x1400c40d7  shr     r8d, 5
0x1400c40db  not     r8d
0x1400c40de  and     r8d, 2; Operation
0x1400c40e2  xor     edx, edx; AccessMode
0x1400c40e4  mov     rcx, r9; MemoryDescriptorList
0x1400c40e7  call    cs:__imp_MmProbeAndLockPages
0x1400c40ee  nop     dword ptr [rax+rax+00h]
0x1400c40f3  mov     r8, [rsp+0F8h+var_A8]
0x1400c40f8  jmp     short loc_1400C412D
0x1400c40fa  xor     edi, edi
0x1400c40fc  mov     r13, [rsp+0F8h+var_80]
0x1400c4101  mov     r12, [rsp+0F8h+var_B0]
0x1400c4106  mov     r14, [rsp+0F8h+var_A0]
0x1400c410b  mov     r8, [rsp+0F8h+var_98]
0x1400c4110  mov     r15d, [rsp+0F8h+var_B8]
0x1400c4115  mov     rsi, [rsp+0F8h+var_78]
0x1400c411d  mov     rax, [rsp+0F8h+var_70]
0x1400c4125  mov     [rsp+0F8h+var_90], rax
0x1400c412a  mov     rbx, rax
0x1400c412d  sub     r12, r14
0x1400c4130  mov     [rsp+0F8h+var_B0], r12
0x1400c4135  add     r8, r14
0x1400c4138  mov     [rsp+0F8h+var_A8], r8
0x1400c413d  mov     [rsp+0F8h+var_98], r8
0x1400c4142  mov     r14d, [rbx+9F74h]
0x1400c4149  inc     r15d
0x1400c414c  mov     [rsp+0F8h+var_B8], r15d
0x1400c4151  jmp     loc_1400C4054
0x1400c4156  mov     [rbx+9F6Ch], r15d
0x1400c415d  mov     [rsp+0F8h+var_D0], dil; bool
0x1400c4162  mov     [rsp+0F8h+var_D8], dil; bool
0x1400c4167  mov     r9, r13; unsigned __int64
0x1400c416a  xor     r8d, r8d; unsigned __int64
0x1400c416d  mov     rdx, [rsi+30h]; struct VIDMM_LOCAL_ALLOC *
0x1400c4171  mov     rcx, [rsp+0F8h+var_90]; this
0x1400c4176  call    ?UnlockAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_K1_N2@Z; VIDMM_GLOBAL::UnlockAllocation(VIDMM_LOCAL_ALLOC *,unsigned __int64,unsigned __int64,bool,bool)
0x1400c417b  mov     rcx, [rsi+0E8h]
0x1400c4182  mov     rax, [rcx]
0x1400c4185  mov     rax, [rax+58h]
0x1400c4189  call    _guard_dispatch_icall
0x1400c418e  lea     rcx, [rsp+0F8h+ApcState]; ApcState
0x1400c4196  call    cs:__imp_KeUnstackDetachProcess
0x1400c419d  nop     dword ptr [rax+rax+00h]
0x1400c41a2  bts     dword ptr [rsi+18h], 1Fh
0x1400c41a7  mov     rax, [rbx+9F48h]
0x1400c41ae  mov     [rsi+40h], rax
0x1400c41b2  xor     eax, eax
0x1400c41b4  jmp     short loc_1400C41BB
0x1400c41b6  mov     eax, 0C0000017h
0x1400c41bb  mov     rcx, [rsp+0F8h+var_30]
0x1400c41c3  xor     rcx, rsp; StackCookie
0x1400c41c6  call    __security_check_cookie
0x1400c41cb  lea     r11, [rsp+0F8h+var_28]
0x1400c41d3  mov     rbx, [r11+40h]
0x1400c41d7  mov     rsi, [r11+48h]
0x1400c41db  mov     rsp, r11
0x1400c41de  pop     r15
0x1400c41e0  pop     r14
0x1400c41e2  pop     r13
0x1400c41e4  pop     r12
0x1400c41e6  pop     rdi
0x1400c41e7  retn
  ... truncated ...
```
