# FatNonCachedNonAlignedRead

- ea: `0x14002e0cc`
- end: `0x14002e4aa`
- name: `FatNonCachedNonAlignedRead`
- size: `990`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14004573c`

## callees

- `0x14000c380`
- `0x14000c680`
- `0x14002221c`
- `0x14002d4a8`
- `0x14002d5a8`
- `0x14002d918`
- `0x14002e0cc`
- `0x14002e7dc`
- `0x14003958c`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002e445`
- `ntoskrnl!IoFreeMdl` at `0x14005cd84`
- `ntoskrnl!IoFreeMdl` at `0x14002e445`
- `ntoskrnl!IoFreeMdl` at `0x14005cd84`
- `ntoskrnl!IoAllocateMdl` at `0x14002e3cd`
- `ntoskrnl!IoAllocateMdl` at `0x14002e3cd`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002e410`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002e410`
- `ntoskrnl!KeFlushIoBuffers` at `0x14002e48a`
- `ntoskrnl!KeFlushIoBuffers` at `0x14005cdea`
- `ntoskrnl!KeFlushIoBuffers` at `0x14002e48a`
- `ntoskrnl!KeFlushIoBuffers` at `0x14005cdea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e468`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cdbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e468`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cdbd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002e16b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002e16b`
- `ntoskrnl!ExRaiseStatus` at `0x14002e20b`
- `ntoskrnl!ExRaiseStatus` at `0x14002e318`
- `ntoskrnl!ExRaiseStatus` at `0x14002e3f7`
- `ntoskrnl!ExRaiseStatus` at `0x14002e20b`
- `ntoskrnl!ExRaiseStatus` at `0x14002e318`
- `ntoskrnl!ExRaiseStatus` at `0x14002e3f7`

## pseudocode

```c
void __fastcall FatNonCachedNonAlignedRead(__int64 a1, IRP *a2, __int64 a3, int a4, ULONG a5)
{
  __int64 v6; // rbx
  ULONG v9; // r14d
  ULONG v10; // r13d
  __int64 v11; // rcx
  PVOID PoolWithTag; // rax
  void *v13; // rsi
  ULONG v14; // r13d
  int v15; // r12d
  int *v16; // rsi
  ULONG v17; // ebx
  int v18; // eax
  unsigned int v19; // r13d
  void *v20; // r12
  struct _MDL *v21; // r13
  unsigned int v22; // r12d
  char *v23; // rcx
  struct _MDL *Mdl; // rax
  __int64 v25; // rdx
  PIRP Irp; // [rsp+20h] [rbp-A8h]
  _BYTE v27[4]; // [rsp+40h] [rbp-88h] BYREF
  int v28; // [rsp+44h] [rbp-84h]
  ULONG v29; // [rsp+48h] [rbp-80h]
  int v30; // [rsp+4Ch] [rbp-7Ch] BYREF
  int v31; // [rsp+50h] [rbp-78h]
  ULONG v32; // [rsp+54h] [rbp-74h]
  size_t Size; // [rsp+58h] [rbp-70h]
  LARGE_INTEGER v34; // [rsp+60h] [rbp-68h] BYREF
  void *Src; // [rsp+68h] [rbp-60h]
  void *v36; // [rsp+70h] [rbp-58h]
  struct _MDL *MdlAddress; // [rsp+78h] [rbp-50h]
  PVOID v38; // [rsp+80h] [rbp-48h]
  int v40; // [rsp+E0h] [rbp+18h]
  PVOID UserBuffer; // [rsp+E0h] [rbp+18h]
  char v42; // [rsp+E8h] [rbp+20h] BYREF

  v28 = a4;
  v6 = a3;
  v34.QuadPart = 0;
  v30 = 0;
  v42 = 0;
  v27[0] = 0;
  v9 = a5;
  v32 = a5;
  v31 = a4;
  v10 = *(unsigned __int16 *)(*(_QWORD *)(a3 + 184) + 288LL);
  v29 = v10;
  FatLockUserBuffer(a1, a2, IoWriteAccess, a5);
  v36 = FatMapUserBuffer(v11, (__int64)a2);
  Size = (v10 + 4095) & 0xFFFFF000;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1556, Size, 0x4F746146u);
  v13 = PoolWithTag;
  Src = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, Size);
  v14 = v10 - 1;
  LODWORD(Size) = a4 & v14;
  if ( (a4 & v14) == 0 )
  {
    v15 = ~v14;
    v16 = (int *)&a2->IoStatus.0;
    v18 = v28;
    goto LABEL_13;
  }
  FatLookupFileAllocation(a1, v6, a4, (unsigned int)&v34, (__int64)&v30, (__int64)&v42, (__int64)v27, 0);
  if ( !v42 )
  {
    FatPopUpFileCorrupt(a1, (struct _UNICODE_STRING *)v6);
    *(_DWORD *)(a1 + 72) = -1073741566;
    ExRaiseStatus(-1073741566);
  }
  v15 = ~v14;
  FatSingleNonAlignedSync(a1, *(_QWORD *)(v6 + 184), v13, (LARGE_INTEGER)(v34.QuadPart & (int)~v14), v29, a2);
  v16 = (int *)&a2->IoStatus.0;
  if ( a2->IoStatus.Status >= 0 )
  {
    v17 = v9;
    if ( v9 >= v29 - (unsigned int)Size )
      v17 = v29 - Size;
    memmove(v36, (char *)Src + (unsigned int)Size, v17);
    v18 = v17 + v28;
    v28 += v17;
    v9 -= v17;
    a5 = v9;
    if ( v9 )
    {
      v6 = a3;
LABEL_13:
      v19 = v9 & v14;
      if ( !v19 )
        goto LABEL_18;
      v40 = (v9 & v15) + v18;
      FatLookupFileAllocation(a1, v6, v40, (unsigned int)&v34, (__int64)&v30, (__int64)&v42, (__int64)v27, 0);
      if ( !v42 )
      {
        FatPopUpFileCorrupt(a1, (struct _UNICODE_STRING *)v6);
        *(_DWORD *)(a1 + 72) = -1073741566;
        ExRaiseStatus(-1073741566);
      }
      v20 = Src;
      FatSingleNonAlignedSync(a1, *(_QWORD *)(v6 + 184), Src, v34, v29, a2);
      if ( *v16 >= 0 )
      {
        memmove((char *)v36 + (unsigned int)(v40 - v31), v20, v19);
        v9 -= v19;
        a5 = v9;
        if ( v9 )
        {
LABEL_18:
          MdlAddress = a2->MdlAddress;
          v21 = MdlAddress;
          a2->MdlAddress = 0;
          UserBuffer = a2->UserBuffer;
          v38 = UserBuffer;
          v22 = v28;
          v23 = (char *)v21->StartVa + v21->ByteOffset + (unsigned __int64)(unsigned int)(v28 - v31);
          a2->UserBuffer = v23;
          Mdl = IoAllocateMdl(v23, v9, 0, 0, a2);
          if ( !Mdl )
          {
            a2->MdlAddress = v21;
            a2->UserBuffer = UserBuffer;
            *(_DWORD *)(a1 + 72) = -1073741670;
            ExRaiseStatus(-1073741670);
          }
          IoBuildPartialMdl(v21, Mdl, a2->UserBuffer, v9);
          LODWORD(Irp) = v9;
          FatNonCachedIo(a1, a2, v6, v22, (SIZE_T)Irp, v9, 0);
          IoFreeMdl(a2->MdlAddress);
          a2->MdlAddress = v21;
          a2->UserBuffer = UserBuffer;
        }
      }
    }
  }
  ExFreePoolWithTag(Src, 0);
  if ( *v16 >= 0 )
  {
    a2->IoStatus.Information = v32;
    LOBYTE(v25) = 1;
    KeFlushIoBuffers(a2->MdlAddress, v25, 0);
  }
}

```

## disassembly

```asm
0x14002e0cc  mov     r11, rsp
0x14002e0cf  mov     [r11+18h], r8
0x14002e0d3  mov     [r11+10h], rdx
0x14002e0d7  push    rbx
0x14002e0d8  push    rsi
0x14002e0d9  push    rdi
0x14002e0da  push    r12
0x14002e0dc  push    r13
0x14002e0de  push    r14
0x14002e0e0  push    r15
0x14002e0e2  sub     rsp, 90h
0x14002e0e9  mov     r12d, r9d
0x14002e0ec  mov     [rsp+0C8h+var_84], r9d
0x14002e0f1  mov     rbx, r8
0x14002e0f4  mov     rdi, rdx
0x14002e0f7  mov     r15, rcx
0x14002e0fa  xor     eax, eax
0x14002e0fc  mov     [r11-68h], rax
0x14002e100  mov     [rsp+0C8h+var_7C], eax
0x14002e104  mov     [r11+20h], al
0x14002e108  mov     [rsp+0C8h+var_88], al
0x14002e10c  mov     r14d, [r11+28h]
0x14002e110  mov     [rsp+0C8h+var_74], r14d
0x14002e115  mov     [rsp+0C8h+var_78], r9d
0x14002e11a  mov     rax, [r8+0B8h]
0x14002e121  movzx   r13d, word ptr [rax+120h]
0x14002e129  mov     [rsp+0C8h+var_80], r13d
0x14002e12e  mov     r9d, r14d
0x14002e131  mov     r8d, 1
0x14002e137  call    FatLockUserBuffer
0x14002e13c  mov     rdx, rdi
0x14002e13f  call    FatMapUserBuffer
0x14002e144  mov     [rsp+0C8h+var_58], rax
0x14002e149  lea     eax, [r13+0FFFh]
0x14002e150  mov     ecx, 0FFFFF000h
0x14002e155  and     rax, rcx
0x14002e158  mov     [rsp+0C8h+Size], rax
0x14002e15d  mov     r8d, 4F746146h; Tag
0x14002e163  mov     rdx, rax; NumberOfBytes
0x14002e166  mov     ecx, 614h; PoolType
0x14002e16b  call    cs:__imp_ExAllocatePoolWithTag
0x14002e172  nop     dword ptr [rax+rax+00h]
0x14002e177  mov     rsi, rax
0x14002e17a  mov     [rsp+0C8h+Src], rax
0x14002e17f  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14002e186  jnz     short loc_14002E19D
0x14002e188  test    rax, rax
0x14002e18b  jz      short loc_14002E19D
0x14002e18d  mov     r8, [rsp+0C8h+Size]; Size
0x14002e192  xor     edx, edx; Val
0x14002e194  mov     rcx, rax; void *
0x14002e197  call    memset
0x14002e19c  nop
0x14002e19d  dec     r13d
0x14002e1a0  mov     eax, r13d
0x14002e1a3  and     eax, r12d
0x14002e1a6  mov     dword ptr [rsp+0C8h+Size], eax
0x14002e1aa  jz      loc_14002E29A
0x14002e1b0  mov     [rsp+0C8h+var_90], 0
0x14002e1b9  lea     rax, [rsp+0C8h+var_88]
0x14002e1be  mov     qword ptr [rsp+0C8h+var_98], rax
0x14002e1c3  lea     rax, [rsp+0C8h+arg_18]
0x14002e1cb  mov     qword ptr [rsp+0C8h+var_A0], rax
0x14002e1d0  lea     rax, [rsp+0C8h+var_7C]
0x14002e1d5  mov     [rsp+0C8h+Irp], rax
0x14002e1da  lea     r9, [rsp+0C8h+var_68]
0x14002e1df  mov     r8d, r12d
0x14002e1e2  mov     rdx, rbx
0x14002e1e5  mov     rcx, r15
0x14002e1e8  call    FatLookupFileAllocation
0x14002e1ed  mov     rcx, r15
0x14002e1f0  cmp     [rsp+0C8h+arg_18], 0
0x14002e1f8  jnz     short loc_14002E217
0x14002e1fa  mov     rdx, rbx
0x14002e1fd  call    FatPopUpFileCorrupt
0x14002e202  mov     ecx, 0C0000102h; Status
0x14002e207  mov     [r15+48h], ecx
0x14002e20b  call    cs:__imp_ExRaiseStatus
0x14002e217  mov     r12d, r13d
0x14002e21a  not     r12d
0x14002e21d  movsxd  r9, r12d
0x14002e220  and     r9, [rsp+0C8h+var_68]
0x14002e225  mov     qword ptr [rsp+0C8h+var_A0], rdi
0x14002e22a  mov     eax, [rsp+0C8h+var_80]
0x14002e22e  mov     dword ptr [rsp+0C8h+Irp], eax
0x14002e232  mov     r8, rsi
0x14002e235  mov     rdx, [rbx+0B8h]
0x14002e23c  call    FatSingleNonAlignedSync
0x14002e241  lea     rsi, [rdi+30h]
0x14002e245  cmp     dword ptr [rsi], 0
0x14002e248  jl      loc_14002E461
0x14002e24e  mov     eax, [rsp+0C8h+var_80]
0x14002e252  mov     ecx, dword ptr [rsp+0C8h+Size]
0x14002e256  sub     eax, ecx
0x14002e258  mov     ebx, r14d
0x14002e25b  cmp     r14d, eax
0x14002e25e  cmovnb  ebx, eax
0x14002e261  mov     r8d, ebx; Size
0x14002e264  mov     edx, ecx
0x14002e266  add     rdx, [rsp+0C8h+Src]; Src
0x14002e26b  mov     rcx, [rsp+0C8h+var_58]; void *
0x14002e270  call    memmove
0x14002e275  mov     eax, [rsp+0C8h+var_84]
0x14002e279  add     eax, ebx
0x14002e27b  mov     [rsp+0C8h+var_84], eax
0x14002e27f  sub     r14d, ebx
0x14002e282  mov     [rsp+0C8h+arg_20], r14d
0x14002e28a  jz      loc_14002E461
0x14002e290  mov     rbx, qword ptr [rsp+0C8h+arg_10]
0x14002e298  jmp     short loc_14002E2A8
0x14002e29a  mov     r12d, r13d
0x14002e29d  not     r12d
0x14002e2a0  lea     rsi, [rdi+30h]
0x14002e2a4  mov     eax, [rsp+0C8h+var_84]
0x14002e2a8  and     r13d, r14d
0x14002e2ab  jz      loc_14002E37F
0x14002e2b1  and     r12d, r14d
0x14002e2b4  lea     r8d, [r12+rax]
0x14002e2b8  mov     [rsp+0C8h+arg_10], r8d
0x14002e2c0  mov     [rsp+0C8h+var_90], 0
0x14002e2c9  lea     rax, [rsp+0C8h+var_88]
0x14002e2ce  mov     qword ptr [rsp+0C8h+var_98], rax
0x14002e2d3  lea     rax, [rsp+0C8h+arg_18]
0x14002e2db  mov     qword ptr [rsp+0C8h+var_A0], rax
0x14002e2e0  lea     rax, [rsp+0C8h+var_7C]
0x14002e2e5  mov     [rsp+0C8h+Irp], rax
0x14002e2ea  lea     r9, [rsp+0C8h+var_68]
0x14002e2ef  mov     rdx, rbx
0x14002e2f2  mov     rcx, r15
0x14002e2f5  call    FatLookupFileAllocation
0x14002e2fa  mov     rcx, r15
0x14002e2fd  cmp     [rsp+0C8h+arg_18], 0
0x14002e305  jnz     short loc_14002E324
0x14002e307  mov     rdx, rbx
0x14002e30a  call    FatPopUpFileCorrupt
0x14002e30f  mov     ecx, 0C0000102h; Status
0x14002e314  mov     [r15+48h], ecx
0x14002e318  call    cs:__imp_ExRaiseStatus
0x14002e324  mov     qword ptr [rsp+0C8h+var_A0], rdi
0x14002e329  mov     eax, [rsp+0C8h+var_80]
0x14002e32d  mov     dword ptr [rsp+0C8h+Irp], eax
0x14002e331  mov     r9, [rsp+0C8h+var_68]
0x14002e336  mov     r12, [rsp+0C8h+Src]
0x14002e33b  mov     r8, r12
0x14002e33e  mov     rdx, [rbx+0B8h]
0x14002e345  call    FatSingleNonAlignedSync
0x14002e34a  cmp     dword ptr [rsi], 0
0x14002e34d  jl      loc_14002E461
0x14002e353  mov     r8d, r13d; Size
0x14002e356  mov     ecx, [rsp+0C8h+arg_10]
0x14002e35d  sub     ecx, [rsp+0C8h+var_78]
0x14002e361  add     rcx, [rsp+0C8h+var_58]; void *
0x14002e366  mov     rdx, r12; Src
0x14002e369  call    memmove
0x14002e36e  sub     r14d, r13d
0x14002e371  mov     [rsp+0C8h+arg_20], r14d
0x14002e379  jz      loc_14002E461
0x14002e37f  mov     r13, [rdi+8]
0x14002e383  mov     [rsp+0C8h+var_50], r13
0x14002e388  mov     qword ptr [rdi+8], 0
0x14002e390  mov     rax, [rdi+70h]
0x14002e394  mov     qword ptr [rsp+0C8h+arg_10], rax
0x14002e39c  mov     [rsp+0C8h+var_48], rax
0x14002e3a4  mov     r12d, [rsp+0C8h+var_84]
0x14002e3a9  mov     ecx, r12d
0x14002e3ac  sub     ecx, [rsp+0C8h+var_78]
0x14002e3b0  mov     eax, [r13+2Ch]
0x14002e3b4  add     rcx, rax
0x14002e3b7  add     rcx, [r13+20h]; VirtualAddress
0x14002e3bb  mov     [rdi+70h], rcx
0x14002e3bf  mov     [rsp+0C8h+Irp], rdi; Irp
0x14002e3c4  xor     r9d, r9d; ChargeQuota
0x14002e3c7  xor     r8d, r8d; SecondaryBuffer
0x14002e3ca  mov     edx, r14d; Length
0x14002e3cd  call    cs:__imp_IoAllocateMdl
0x14002e3d4  nop     dword ptr [rax+rax+00h]
0x14002e3d9  test    rax, rax
0x14002e3dc  jnz     short loc_14002E403
0x14002e3de  mov     [rdi+8], r13
0x14002e3e2  mov     rax, qword ptr [rsp+0C8h+arg_10]
0x14002e3ea  mov     [rdi+70h], rax
0x14002e3ee  mov     ecx, 0C000009Ah; Status
0x14002e3f3  mov     [r15+48h], ecx
0x14002e3f7  call    cs:__imp_ExRaiseStatus
0x14002e403  mov     r9d, r14d; Length
0x14002e406  mov     r8, [rdi+70h]; VirtualAddress
0x14002e40a  mov     rdx, rax; TargetMdl
0x14002e40d  mov     rcx, r13; SourceMdl
0x14002e410  call    cs:__imp_IoBuildPartialMdl
0x14002e417  nop     dword ptr [rax+rax+00h]
0x14002e41c  nop
0x14002e41d  mov     dword ptr [rsp+0C8h+var_98], 0; char
0x14002e425  mov     [rsp+0C8h+var_A0], r14d; int
0x14002e42a  mov     dword ptr [rsp+0C8h+Irp], r14d; NumberOfBytes
0x14002e42f  mov     r9d, r12d; int
0x14002e432  mov     r8, rbx; int
0x14002e435  mov     rdx, rdi; int
0x14002e438  mov     rcx, r15; int
0x14002e43b  call    FatNonCachedIo
0x14002e440  nop
0x14002e441  mov     rcx, [rdi+8]; Mdl
0x14002e445  call    cs:__imp_IoFreeMdl
0x14002e44c  nop     dword ptr [rax+rax+00h]
0x14002e451  mov     [rdi+8], r13
0x14002e455  mov     rax, qword ptr [rsp+0C8h+arg_10]
0x14002e45d  mov     [rdi+70h], rax
0x14002e461  xor     edx, edx; Tag
0x14002e463  mov     rcx, [rsp+0C8h+Src]; P
0x14002e468  call    cs:__imp_ExFreePoolWithTag
0x14002e46f  nop     dword ptr [rax+rax+00h]
0x14002e474  cmp     dword ptr [rsi], 0
0x14002e477  jl      short loc_14002E496
0x14002e479  mov     eax, [rsp+0C8h+var_74]
0x14002e47d  mov     [rdi+38h], rax
0x14002e481  xor     r8d, r8d
0x14002e484  mov     dl, 1
0x14002e486  mov     rcx, [rdi+8]
0x14002e48a  call    cs:__imp_KeFlushIoBuffers
0x14002e491  nop     dword ptr [rax+rax+00h]
0x14002e496  add     rsp, 90h
0x14002e49d  pop     r15
0x14002e49f  pop     r14
0x14002e4a1  pop     r13
0x14002e4a3  pop     r12
0x14002e4a5  pop     rdi
0x14002e4a6  pop     rsi
0x14002e4a7  pop     rbx
0x14002e4a8  retn
0x14005cd6f  push    rbx
0x14005cd71  push    rbp
0x14005cd72  sub     rsp, 48h
0x14005cd76  mov     rbp, rdx
0x14005cd79  mov     rbx, [rbp+0D8h]
0x14005cd80  mov     rcx, [rbx+8]; Mdl
0x14005cd84  call    cs:__imp_IoFreeMdl
0x14005cd8b  nop     dword ptr [rax+rax+00h]
0x14005cd90  mov     rax, [rbp+78h]
0x14005cd94  mov     [rbx+8], rax
0x14005cd98  mov     rax, [rbp+80h]
0x14005cd9f  mov     [rbx+70h], rax
0x14005cda3  add     rsp, 48h
0x14005cda7  pop     rbp
0x14005cda8  pop     rbx
0x14005cda9  retn
0x14005cdab  push    rbx
0x14005cdad  push    rbp
0x14005cdae  sub     rsp, 48h
0x14005cdb2  mov     rbp, rdx
0x14005cdb5  mov     bl, cl
0x14005cdb7  xor     edx, edx; Tag
0x14005cdb9  mov     rcx, [rbp+68h]; P
0x14005cdbd  call    cs:__imp_ExFreePoolWithTag
0x14005cdc4  nop     dword ptr [rax+rax+00h]
0x14005cdc9  test    bl, bl
0x14005cdcb  jnz     short loc_14005CDF7
0x14005cdcd  mov     rcx, [rbp+0D8h]
0x14005cdd4  cmp     dword ptr [rcx+30h], 0
0x14005cdd8  jl      short loc_14005CDF7
0x14005cdda  mov     eax, [rbp+54h]
0x14005cddd  mov     [rcx+38h], rax
0x14005cde1  xor     r8d, r8d
0x14005cde4  mov     dl, 1
0x14005cde6  mov     rcx, [rcx+8]
0x14005cdea  call    cs:__imp_KeFlushIoBuffers
0x14005cdf1  nop     dword ptr [rax+rax+00h]
0x14005cdf6  nop
0x14005cdf7  add     rsp, 48h
0x14005cdfb  pop     rbp
0x14005cdfc  pop     rbx
0x14005cdfd  retn
```
