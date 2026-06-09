# FatGetEaFile

- ea: `0x140035e50`
- end: `0x14003638b`
- name: `FatGetEaFile`
- size: `1339`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, char, char)`
- caller_count: `5`
- callee_count: `20`
- tags: ``

## callers

- `0x140035234`
- `0x140035608`
- `0x140036394`
- `0x1400364fc`
- `0x14003abc8`

## callees

- `0x140005c80`
- `0x14000c680`
- `0x140020734`
- `0x1400210d0`
- `0x1400226b8`
- `0x140023f58`
- `0x140024020`
- `0x140024228`
- `0x1400302d8`
- `0x14003062c`
- `0x140031468`
- `0x1400319bc`
- `0x140032dec`
- `0x140035e50`
- `0x1400367d8`
- `0x14003685c`
- `0x140036c78`
- `0x1400465f4`
- `0x1400468c4`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x140036338`
- `ntoskrnl!CcFlushCache` at `0x140036338`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140036004`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140036004`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035f52`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003635e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d9a7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d9e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035f52`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003635e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d9a7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d9e2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140036012`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140036012`
- `ntoskrnl!CcUnpinData` at `0x14005d95b`
- `ntoskrnl!CcUnpinData` at `0x14005d95b`
- `ntoskrnl!ExRaiseStatus` at `0x140035ee7`
- `ntoskrnl!ExRaiseStatus` at `0x140035f2b`
- `ntoskrnl!ExRaiseStatus` at `0x140035f7a`
- `ntoskrnl!ExRaiseStatus` at `0x140035ee7`
- `ntoskrnl!ExRaiseStatus` at `0x140035f2b`
- `ntoskrnl!ExRaiseStatus` at `0x140035f7a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d9bd`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d9bd`

## pseudocode

```c
__int64 __fastcall FatGetEaFile(__int64 a1, __int64 a2, PVOID *a3, PVOID *a4, char a5, char a6)
{
  char v10; // bl
  __int64 v11; // r8
  __int64 v12; // r9
  struct _CC_FILE_SIZES **v13; // rdi
  struct _CC_FILE_SIZES *v14; // rax
  __int64 v15; // rcx
  struct _ERESOURCE *v16; // rcx
  int v17; // r9d
  __int64 v18; // rcx
  char v19; // cl
  struct _CC_FILE_SIZES *v20; // rbx
  int v21; // ecx
  __int64 v22; // rcx
  PFILE_OBJECT v23; // rbx
  _WORD *v24; // rdi
  int v25; // eax
  __int64 v26; // rcx
  __int16 v27; // dx
  unsigned int v28; // r15d
  _WORD *i; // rax
  __int64 v30; // rcx
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-110h]
  __int64 Status; // [rsp+30h] [rbp-108h]
  unsigned int Size; // [rsp+58h] [rbp-E0h]
  __int64 v35; // [rsp+60h] [rbp-D8h] BYREF
  _WORD *v36; // [rsp+68h] [rbp-D0h]
  int v37; // [rsp+70h] [rbp-C8h] BYREF
  unsigned int v38; // [rsp+74h] [rbp-C4h]
  PFILE_OBJECT v39; // [rsp+78h] [rbp-C0h]
  __int64 v40; // [rsp+80h] [rbp-B8h] BYREF
  __int128 v41; // [rsp+88h] [rbp-B0h] BYREF
  void *v42[19]; // [rsp+A0h] [rbp-98h] BYREF

  v39 = 0;
  v10 = 0;
  memset(v42, 0, 0x60u);
  v41 = 0;
  v13 = (struct _CC_FILE_SIZES **)(a2 + 784);
  if ( !*(_QWORD *)(a2 + 776) )
  {
    if ( !(unsigned __int8)FatAcquireExclusiveFcb(a1, *v13) )
    {
      *(_DWORD *)(a1 + 72) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
    goto LABEL_13;
  }
  if ( a6 )
  {
    if ( (unsigned __int8)FatAcquireExclusiveFcb(a1, *v13) )
      goto LABEL_9;
LABEL_8:
    *(_DWORD *)(a1 + 72) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  if ( !(unsigned __int8)FatAcquireSharedFcb(a1, *v13, v11, v12) )
    goto LABEL_8;
LABEL_9:
  if ( !*(_QWORD *)(a2 + 776) && !a6 )
  {
    ExReleaseResourceLite((PERESOURCE)(*v13)->FileSize.QuadPart);
    if ( !(unsigned __int8)FatAcquireExclusiveFcb(a1, *v13) )
    {
      *(_DWORD *)(a1 + 72) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
  }
LABEL_13:
  v14 = *v13;
  if ( *(_QWORD *)(a2 + 776) )
  {
    FatVerifyFcb(a1, *v13);
    FatGetDirentFromFcbOrDcb(a1, (unsigned int)*v13, 0, (_DWORD)a3, (__int64)a4);
  }
  else
  {
    LODWORD(v35) = 0;
    v14[8].AllocationSize.HighPart = 1;
    *((_QWORD *)&v41 + 1) = "EA DATA. SF";
    LODWORD(v41) = 786443;
    v16 = *(struct _ERESOURCE **)(*(_QWORD *)(a2 + 208) + 8LL);
    if ( a5 )
      ExAcquireResourceExclusiveLite(v16, 1u);
    else
      ExAcquireResourceSharedLite(v16, 1u);
    v10 = 1;
    FatLocateSimpleOemDirent(a1, (*v13)[7].FileSize.QuadPart, (__int64)a4, (__int64)&v35);
    if ( *a3 )
    {
      FatPinMappedData(a1, (*v13)[7].FileSize.QuadPart, v35, v17, a4);
      (*v13)[5].FileSize.LowPart = *((unsigned __int16 *)*a3 + 13);
      (*v13)[10].AllocationSize.HighPart = v35;
      (*v13)[1].AllocationSize.QuadPart = -1;
      FatLookupFileAllocationSize(a1, *v13);
      v18 = *((unsigned int *)*a3 + 7);
      (*v13)[1].AllocationSize.QuadPart = v18;
      (*v13)[1].FileSize.QuadPart = v18;
      v39 = FatOpenEaFile(v18, *v13);
      *(_QWORD *)(a2 + 776) = v39;
    }
    else if ( a5 )
    {
      v36 = 0;
      v37 = 0;
      v19 = *(_BYTE *)(a2 + 378);
      Size = -(1 << v19) & ((1 << v19) + 1023);
      v38 = Size >> v19;
      FatAllocateDiskSpace(a1, a2, 0, (__int64)&(*v13)[12]);
      v20 = *v13;
      v20[10].AllocationSize.HighPart = FatCreateNewDirent(a1, (*v13)[7].FileSize.QuadPart, 1u);
      FatPrepareWriteDirectoryFile(
        a1,
        (*v13)[7].FileSize.QuadPart,
        (*v13)[10].AllocationSize.HighPart,
        0x20u,
        a4,
        a3,
        Status,
        1,
        &v37);
      FatConstructDirent(v21, (unsigned int)*a3, (unsigned int)&v41, 0, 0, 0, 39, 1, 0);
      *((_DWORD *)*a3 + 7) = Size;
      v22 = *((unsigned int *)*a3 + 7);
      (*v13)[1].AllocationSize.QuadPart = v22;
      (*v13)[1].FileSize.QuadPart = v22;
      v23 = FatOpenEaFile(v22, *v13);
      v39 = v23;
      v40 = 0;
      FatLookupMcbEntry(a2, &(*v13)[12], 0, &v40, 0, 0);
      *((_WORD *)*a3 + 13) = ((v40 - *(_QWORD *)(a2 + 352)) >> *(_BYTE *)(a2 + 378)) + 2;
      (*v13)[5].FileSize.LowPart = *((unsigned __int16 *)*a3 + 13);
      LODWORD(NumberOfBytes) = Size;
      FatPinEaRange(a1, (int)v23, (int)*v13, (int)v42, 0, NumberOfBytes, -1073741762);
      v24 = v42[0];
      memset(v42[0], 0, Size);
      *v24 = 17477;
      v25 = 240;
      v26 = (__int64)(v24 + 16);
      v27 = v38;
      while ( 1 )
      {
        v36 = (_WORD *)v26;
        if ( !v25 )
          break;
        *(_WORD *)v26 = v27;
        --v25;
        v26 += 2;
      }
      v28 = (Size - 512) >> 1;
      for ( i = v24 + 256; ; ++i )
      {
        v36 = i;
        if ( !v28 )
          break;
        v26 = 0xFFFF;
        *i = -1;
        --v28;
      }
      FatMarkEaRangeDirty(v26, v23, v42);
      FatUnpinEaRange(v30, v42);
      CcFlushCache(v23->SectionObjectPointer, 0, 0, 0);
      *(_QWORD *)(a2 + 776) = v23;
      v10 = 1;
    }
  }
  if ( v10 )
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a2 + 208) + 8LL));
  return FatUnpinEaRange(v15, v42);
}

```

## disassembly

```asm
0x140035e50  mov     rax, rsp
0x140035e53  mov     [rax+20h], r9
0x140035e57  mov     [rax+10h], rdx
0x140035e5b  mov     [rax+8], rcx
0x140035e5f  push    rbx
0x140035e60  push    rsi
0x140035e61  push    rdi
0x140035e62  push    r12
0x140035e64  push    r13
0x140035e66  push    r14
0x140035e68  push    r15
0x140035e6a  sub     rsp, 100h
0x140035e71  mov     r13, r9
0x140035e74  mov     r12, r8
0x140035e77  mov     r14, rdx
0x140035e7a  mov     rsi, rcx
0x140035e7d  mov     [rsp+138h+var_C0], 0
0x140035e86  mov     [rsp+138h+var_E8], 0
0x140035e8b  xor     bl, bl
0x140035e8d  mov     [rsp+138h+var_E7], bl
0x140035e91  mov     [rsp+138h+var_E6], bl
0x140035e95  mov     [rsp+138h+var_E5], bl
0x140035e99  mov     [rsp+138h+var_E4], bl
0x140035e9d  xor     edx, edx; Val
0x140035e9f  lea     r8d, [rdx+60h]; Size
0x140035ea3  lea     rcx, [rax-98h]; void *
0x140035eaa  call    memset
0x140035eaf  nop
0x140035eb0  xorps   xmm0, xmm0
0x140035eb3  movups  [rsp+138h+var_B0], xmm0
0x140035ebb  lea     rdi, [r14+310h]
0x140035ec2  cmp     qword ptr [r14+308h], 0
0x140035eca  jnz     short loc_140035EF3
0x140035ecc  mov     rdx, [rdi]
0x140035ecf  mov     rcx, rsi
0x140035ed2  call    FatAcquireExclusiveFcb
0x140035ed7  test    al, al
0x140035ed9  jnz     loc_140035F86
0x140035edf  mov     ecx, 0C00000D8h; Status
0x140035ee4  mov     [rsi+48h], ecx
0x140035ee7  call    cs:__imp_ExRaiseStatus
0x140035ef3  mov     r15b, [rsp+138h+arg_28]
0x140035efb  test    r15b, r15b
0x140035efe  jz      short loc_140035F14
0x140035f00  mov     rdx, [rdi]
0x140035f03  mov     rcx, rsi
0x140035f06  call    FatAcquireExclusiveFcb
0x140035f0b  test    al, al
0x140035f0d  jz      short loc_140035F23
0x140035f0f  test    r15b, r15b
0x140035f12  jnz     short loc_140035F37
0x140035f14  mov     rdx, [rdi]
0x140035f17  mov     rcx, rsi
0x140035f1a  call    FatAcquireSharedFcb
0x140035f1f  test    al, al
0x140035f21  jnz     short loc_140035F37
0x140035f23  mov     ecx, 0C00000D8h; Status
0x140035f28  mov     [rsi+48h], ecx
0x140035f2b  call    cs:__imp_ExRaiseStatus
0x140035f37  mov     [rsp+138h+var_E8], 1
0x140035f3c  cmp     qword ptr [r14+308h], 0
0x140035f44  jnz     short loc_140035F8B
0x140035f46  test    r15b, r15b
0x140035f49  jnz     short loc_140035F8B
0x140035f4b  mov     rcx, [rdi]
0x140035f4e  mov     rcx, [rcx+8]; Resource
0x140035f52  call    cs:__imp_ExReleaseResourceLite
0x140035f59  nop     dword ptr [rax+rax+00h]
0x140035f5e  mov     [rsp+138h+var_E8], r15b
0x140035f63  mov     rdx, [rdi]
0x140035f66  mov     rcx, rsi
0x140035f69  call    FatAcquireExclusiveFcb
0x140035f6e  test    al, al
0x140035f70  jnz     short loc_140035F86
0x140035f72  mov     ecx, 0C00000D8h; Status
0x140035f77  mov     [rsi+48h], ecx
0x140035f7a  call    cs:__imp_ExRaiseStatus
0x140035f86  mov     [rsp+138h+var_E8], 1
0x140035f8b  mov     rax, [rdi]
0x140035f8e  cmp     qword ptr [r14+308h], 0
0x140035f96  jz      short loc_140035FBE
0x140035f98  mov     rdx, rax
0x140035f9b  mov     rcx, rsi
0x140035f9e  call    FatVerifyFcb
0x140035fa3  mov     [rsp+138h+var_118], r13
0x140035fa8  mov     r9, r12
0x140035fab  xor     r8d, r8d
0x140035fae  mov     rdx, [rdi]
0x140035fb1  mov     rcx, rsi
0x140035fb4  call    FatGetDirentFromFcbOrDcb
0x140035fb9  jmp     loc_14003634F
0x140035fbe  mov     dword ptr [rsp+138h+var_D8], 0
0x140035fc6  mov     dword ptr [rax+0C4h], 1
0x140035fd0  lea     rax, aEaDataSf_0; "EA DATA. SF"
0x140035fd7  mov     qword ptr [rsp+138h+var_B0+8], rax
0x140035fdf  mov     dword ptr [rsp+138h+var_B0], 0C000Bh
0x140035fea  mov     rax, [r14+0D0h]
0x140035ff1  mov     rcx, [rax+8]; Resource
0x140035ff5  mov     r15b, [rsp+138h+arg_20]
0x140035ffd  mov     dl, 1; Wait
0x140035fff  test    r15b, r15b
0x140036002  jz      short loc_140036012
0x140036004  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003600b  nop     dword ptr [rax+rax+00h]
0x140036010  jmp     short loc_14003601E
0x140036012  call    cs:__imp_ExAcquireResourceSharedLite
0x140036019  nop     dword ptr [rax+rax+00h]
0x14003601e  mov     bl, 1
0x140036020  mov     [rsp+138h+var_E7], bl
0x140036024  mov     rdx, [rdi]
0x140036027  lea     rax, [rsp+138h+var_D8]
0x14003602c  mov     [rsp+138h+NumberOfBytes], rax; __int64
0x140036031  mov     [rsp+138h+var_118], r13; __int64
0x140036036  mov     r9, r12
0x140036039  lea     r8, [rsp+138h+var_B0]
0x140036041  mov     rdx, [rdx+0B0h]; int
0x140036048  mov     rcx, rsi; int
0x14003604b  call    FatLocateSimpleOemDirent
0x140036050  xor     r8d, r8d
0x140036053  cmp     [r12], r8
0x140036057  jz      short loc_1400360D7
0x140036059  mov     rdx, [rdi]
0x14003605c  mov     [rsp+138h+var_118], r13; PVOID *
0x140036061  mov     r8d, dword ptr [rsp+138h+var_D8]; int
0x140036066  mov     rdx, [rdx+0B0h]; int
0x14003606d  mov     rcx, rsi; int
0x140036070  call    FatPinMappedData
0x140036075  mov     rax, [r12]
0x140036079  movzx   ecx, word ptr [rax+1Ah]
0x14003607d  mov     rax, [rdi]
0x140036080  mov     [rax+80h], ecx
0x140036086  mov     rcx, [rdi]
0x140036089  mov     eax, dword ptr [rsp+138h+var_D8]
0x14003608d  mov     [rcx+0F4h], eax
0x140036093  mov     rax, [rdi]
0x140036096  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x14003609e  mov     rdx, [rdi]
0x1400360a1  mov     rcx, rsi
0x1400360a4  call    FatLookupFileAllocationSize
0x1400360a9  mov     rax, [r12]
0x1400360ad  mov     ecx, [rax+1Ch]
0x1400360b0  mov     rax, [rdi]
0x1400360b3  mov     [rax+18h], rcx
0x1400360b7  mov     rax, [rdi]
0x1400360ba  mov     [rax+20h], rcx
0x1400360be  mov     rdx, [rdi]
0x1400360c1  call    FatOpenEaFile
0x1400360c6  mov     [rsp+138h+var_C0], rax
0x1400360cb  mov     [r14+308h], rax
0x1400360d2  jmp     loc_14003634F
0x1400360d7  test    r15b, r15b
0x1400360da  jz      loc_14003634F
0x1400360e0  mov     dword ptr [rsp+138h+Size], r8d
0x1400360e5  mov     [rsp+138h+var_D0], r8
0x1400360ea  mov     dword ptr [rsp+138h+Size+4], r8d
0x1400360ef  mov     [rsp+138h+var_C8], r8d
0x1400360f4  movzx   ecx, byte ptr [r14+17Ah]
0x1400360fc  mov     eax, 1
0x140036101  shl     eax, cl
0x140036103  lea     edx, [rax+3FFh]
0x140036109  neg     eax
0x14003610b  and     edx, eax
0x14003610d  mov     dword ptr [rsp+138h+Size], edx
0x140036111  mov     eax, edx
0x140036113  shr     eax, cl
0x140036115  mov     [rsp+138h+var_C4], eax
0x140036119  lea     r15d, [rdx-200h]
0x140036120  mov     rax, [rdi]
0x140036123  add     rax, 120h
0x140036129  mov     [rsp+138h+NumberOfBytes], rax; __int64
0x14003612e  mov     byte ptr [rsp+138h+var_118], r8b; char
0x140036133  lea     r9, [rsp+138h+Size]
0x140036138  mov     rdx, r14; int
0x14003613b  mov     rcx, rsi; int
0x14003613e  call    FatAllocateDiskSpace
0x140036143  mov     [rsp+138h+var_E6], bl
0x140036147  mov     rbx, [rdi]
0x14003614a  mov     r8d, 1; NumberToSet
0x140036150  mov     rdx, [rbx+0B0h]; int
0x140036157  mov     rcx, rsi; int
0x14003615a  call    FatCreateNewDirent
0x14003615f  mov     [rbx+0F4h], eax
0x140036165  mov     rdx, [rdi]
0x140036168  lea     rax, [rsp+138h+var_C8]
0x14003616d  mov     [rsp+138h+var_F8], rax
0x140036172  mov     [rsp+138h+var_100], 1
0x140036177  mov     [rsp+138h+NumberOfBytes], r12
0x14003617c  mov     [rsp+138h+var_118], r13
0x140036181  mov     r9d, 20h ; ' '
0x140036187  mov     r8d, [rdx+0F4h]
0x14003618e  mov     rdx, [rdx+0B0h]
0x140036195  mov     rcx, rsi
0x140036198  call    FatPrepareWriteDirectoryFile
0x14003619d  mov     [rsp+138h+var_E5], 1
0x1400361a2  mov     eax, 27h ; '''
0x1400361a7  xor     r13d, r13d
0x1400361aa  mov     [rsp+138h+var_F8], r13
0x1400361af  mov     [rsp+138h+var_100], 1
0x1400361b4  mov     word ptr [rsp+138h+Status], ax
0x1400361b9  mov     [rsp+138h+NumberOfBytes], r13
0x1400361be  mov     byte ptr [rsp+138h+var_118], r13b
0x1400361c3  xor     r9d, r9d
0x1400361c6  lea     r8, [rsp+138h+var_B0]
0x1400361ce  mov     rdx, [r12]
0x1400361d2  call    FatConstructDirent
0x1400361d7  mov     rcx, [r12]
0x1400361db  mov     eax, dword ptr [rsp+138h+Size]
0x1400361df  mov     [rcx+1Ch], eax
0x1400361e2  mov     rax, [r12]
0x1400361e6  mov     ecx, [rax+1Ch]
0x1400361e9  mov     rax, [rdi]
0x1400361ec  mov     [rax+18h], rcx
0x1400361f0  mov     rax, [rdi]
0x1400361f3  mov     [rax+20h], rcx
0x1400361f7  mov     [rsp+138h+var_E4], 1
0x1400361fc  mov     rdx, [rdi]
0x1400361ff  call    FatOpenEaFile
0x140036204  mov     rbx, rax
0x140036207  mov     [rsp+138h+var_C0], rax
0x14003620c  mov     [rsp+138h+var_B8], r13
0x140036214  mov     rdx, [rdi]
0x140036217  add     rdx, 120h
0x14003621e  mov     [rsp+138h+NumberOfBytes], r13
0x140036223  mov     [rsp+138h+var_118], r13
0x140036228  lea     r9, [rsp+138h+var_B8]
0x140036230  xor     r8d, r8d
0x140036233  mov     rcx, r14
0x140036236  call    FatLookupMcbEntry
0x14003623b  mov     rdx, [rsp+138h+var_B8]
0x140036243  sub     rdx, [r14+160h]
0x14003624a  mov     cl, [r14+17Ah]
0x140036251  sar     rdx, cl
0x140036254  add     dx, 2
0x140036258  mov     rax, [r12]
0x14003625c  mov     [rax+1Ah], dx
0x140036260  mov     rax, [r12]
0x140036264  movzx   ecx, word ptr [rax+1Ah]
0x140036268  mov     rax, [rdi]
0x14003626b  mov     [rax+80h], ecx
0x140036271  mov     dword ptr [rsp+138h+Status], 0C000003Eh; Status
0x140036279  mov     eax, dword ptr [rsp+138h+Size]
0x14003627d  mov     dword ptr [rsp+138h+NumberOfBytes], eax; NumberOfBytes
0x140036281  mov     dword ptr [rsp+138h+var_118], r13d; int
0x140036286  lea     r9, [rsp+138h+var_98]; int
0x14003628e  mov     r8, [rdi]; int
0x140036291  mov     rdx, rbx; int
0x140036294  mov     rcx, rsi; int
0x140036297  call    FatPinEaRange
0x14003629c  mov     rdi, [rsp+138h+var_98]
0x1400362a4  mov     r8d, dword ptr [rsp+138h+Size]; Size
0x1400362a9  xor     edx, edx; Val
0x1400362ab  mov     rcx, rdi; void *
0x1400362ae  call    memset
0x1400362b3  mov     eax, 4445h
0x1400362b8  mov     [rdi], ax
0x1400362bb  mov     eax, 0F0h
0x1400362c0  lea     rcx, [rdi+20h]
0x1400362c4  or      r8d, 0FFFFFFFFh
0x1400362c8  mov     edx, [rsp+138h+var_C4]
0x1400362cc  mov     [rsp+138h+var_D0], rcx
0x1400362d1  mov     dword ptr [rsp+138h+Size+4], eax
0x1400362d5  test    eax, eax
0x1400362d7  jz      short loc_1400362E5
0x1400362d9  mov     [rcx], dx
0x1400362dc  add     eax, r8d
0x1400362df  add     rcx, 2
0x1400362e3  jmp     short loc_1400362CC
0x1400362e5  shr     r15d, 1
0x1400362e8  lea     rax, [rdi+200h]
0x1400362ef  mov     [rsp+138h+var_D0], rax
0x1400362f4  mov     dword ptr [rsp+138h+Size+4], r15d
0x1400362f9  test    r15d, r15d
0x1400362fc  jz      short loc_14003630F
0x1400362fe  mov     ecx, 0FFFFh
0x140036303  mov     [rax], cx
0x140036306  add     r15d, r8d
0x140036309  add     rax, 2
0x14003630d  jmp     short loc_1400362EF
0x14003630f  lea     r8, [rsp+138h+var_98]
0x140036317  mov     rdx, rbx
0x14003631a  call    FatMarkEaRangeDirty
0x14003631f  lea     rdx, [rsp+138h+var_98]
0x140036327  call    FatUnpinEaRange
0x14003632c  xor     r9d, r9d; IoStatus
0x14003632f  xor     r8d, r8d; Length
0x140036332  xor     edx, edx; FileOffset
0x140036334  mov     rcx, [rbx+28h]; SectionObjectPointer
0x140036338  call    cs:__imp_CcFlushCache
0x14003633f  nop     dword ptr [rax+rax+00h]
0x140036344  mov     [r14+308h], rbx
0x14003634b  mov     bl, [rsp+138h+var_E7]
0x14003634f  test    bl, bl
0x140036351  jz      short loc_14003636A
0x140036353  mov     rcx, [r14+0D0h]
0x14003635a  mov     rcx, [rcx+8]; Resource
0x14003635e  call    cs:__imp_ExReleaseResourceLite
0x140036365  nop     dword ptr [rax+rax+00h]
0x14003636a  lea     rdx, [rsp+138h+var_98]
0x140036372  call    FatUnpinEaRange
0x140036377  add     rsp, 100h
  ... truncated ...
```
