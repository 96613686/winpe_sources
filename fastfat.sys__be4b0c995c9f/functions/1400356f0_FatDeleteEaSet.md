# FatDeleteEaSet

- ea: `0x1400356f0`
- end: `0x140035db8`
- name: `FatDeleteEaSet`
- size: `1736`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, SIZE_T)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140035608`

## callees

- `0x1400019b8`
- `0x14000c680`
- `0x1400210d0`
- `0x140022740`
- `0x14002393c`
- `0x1400356f0`
- `0x1400367d8`
- `0x14003685c`
- `0x140036c78`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x140035a19`
- `ntoskrnl!CcFlushCache` at `0x140035a19`
- `ntoskrnl!CcPurgeCacheSection` at `0x140035a35`
- `ntoskrnl!CcPurgeCacheSection` at `0x140035a35`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035b41`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140035b41`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035b76`
- `ntoskrnl!ExReleaseResourceLite` at `0x140035b76`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140035d51`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140035d6c`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d8a6`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d8c0`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140035d51`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140035d6c`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d8a6`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005d8c0`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140035a83`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140035ad9`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140035a83`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140035ad9`
- `ntoskrnl!CcSetFileSizes` at `0x140035b66`
- `ntoskrnl!CcSetFileSizes` at `0x14005d7df`
- `ntoskrnl!CcSetFileSizes` at `0x140035b66`
- `ntoskrnl!CcSetFileSizes` at `0x14005d7df`
- `ntoskrnl!ExRaiseStatus` at `0x1400358a1`
- `ntoskrnl!ExRaiseStatus` at `0x1400359b8`
- `ntoskrnl!ExRaiseStatus` at `0x140035a5b`
- `ntoskrnl!ExRaiseStatus` at `0x140035d94`
- `ntoskrnl!ExRaiseStatus` at `0x140035dab`
- `ntoskrnl!ExRaiseStatus` at `0x1400358a1`
- `ntoskrnl!ExRaiseStatus` at `0x1400359b8`
- `ntoskrnl!ExRaiseStatus` at `0x140035a5b`
- `ntoskrnl!ExRaiseStatus` at `0x140035d94`
- `ntoskrnl!ExRaiseStatus` at `0x140035dab`

## pseudocode

```c
void __fastcall FatDeleteEaSet(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned __int16 a5)
{
  struct _FILE_OBJECT *v7; // r12
  __int64 v8; // r13
  int v9; // edx
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // r9d
  int i; // eax
  bool v17; // zf
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rbx
  __int64 v21; // rcx
  int v22; // r8d
  _WORD *v23; // rdx
  int v25; // r15d
  _WORD *v26; // rcx
  _WORD *v27; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  SIZE_T NumberOfBytes; // [rsp+50h] [rbp-210h]
  SIZE_T NumberOfBytesc; // [rsp+50h] [rbp-210h]
  SIZE_T NumberOfBytesa; // [rsp+50h] [rbp-210h]
  SIZE_T NumberOfBytesb; // [rsp+50h] [rbp-210h]
  SIZE_T NumberOfBytesd; // [rsp+50h] [rbp-210h]
  char v37; // [rsp+68h] [rbp-1F8h]
  int v38; // [rsp+74h] [rbp-1ECh]
  union _LARGE_INTEGER FileOffset; // [rsp+80h] [rbp-1E0h] BYREF
  _WORD *j; // [rsp+88h] [rbp-1D8h]
  __int64 v41; // [rsp+90h] [rbp-1D0h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+98h] [rbp-1C8h] BYREF
  LARGE_MCB Mcb; // [rsp+A8h] [rbp-1B8h] BYREF
  LARGE_MCB v44; // [rsp+C8h] [rbp-198h] BYREF
  int v45[2]; // [rsp+E8h] [rbp-178h]
  __int64 v46; // [rsp+F0h] [rbp-170h]
  __int64 v47; // [rsp+F8h] [rbp-168h]
  struct _FILE_OBJECT *v48; // [rsp+100h] [rbp-160h]
  int v49[24]; // [rsp+108h] [rbp-158h] BYREF
  int v50[24]; // [rsp+168h] [rbp-F8h] BYREF
  int v51[28]; // [rsp+1C8h] [rbp-98h] BYREF
  int v54; // [rsp+288h] [rbp+28h]
  int v56; // [rsp+290h] [rbp+30h]
  int v57; // [rsp+290h] [rbp+30h]

  FileOffset.QuadPart = 0;
  memset(&Mcb, 0, sizeof(Mcb));
  memset(&v44, 0, sizeof(v44));
  if ( (unsigned __int16)(a5 - 1) > 0x77FEu )
  {
    *(_DWORD *)(a1 + 72) = -1073741743;
    ExRaiseStatus(-1073741743);
  }
  v56 = 1 << *(_BYTE *)(a2 + 378);
  v37 = 0;
  v48 = *(struct _FILE_OBJECT **)(a2 + 776);
  v7 = v48;
  v41 = *(_QWORD *)(a2 + 784);
  v8 = v41;
  *(_QWORD *)v45 = ((2 * a5) & 0xFFFFFF00) + 512;
  memset(v49, 0, sizeof(v49));
  memset(v50, 0, sizeof(v50));
  memset(v51, 0, 0x60u);
  LODWORD(NumberOfBytes) = 512;
  FatPinEaRange(a1, (int)v48, v41, (int)v49, 0, NumberOfBytes, -1073741743);
  IoStatus.Pointer = *(PVOID *)v49;
  LODWORD(NumberOfBytesc) = 256;
  FatPinEaRange(a1, (int)v48, v41, (int)v50, ((2 * a5) & 0xFFFFFF00) + 512, NumberOfBytesc, -1073741743);
  v47 = a5 & 0x7F;
  v9 = *(unsigned __int16 *)(*(_QWORD *)v50 + 2 * v47);
  if ( (_WORD)v9 == 0xFFFF )
  {
    *(_DWORD *)(a1 + 72) = -1073741743;
    ExRaiseStatus(-1073741743);
  }
  v10 = a5 >> 7;
  v46 = v10;
  v11 = v9 + *((unsigned __int16 *)IoStatus.Pointer + v10 + 16);
  LOBYTE(v10) = *(_BYTE *)(a2 + 378);
  v12 = v11 << v10;
  FatUnpinEaRange(v10, v49);
  FatUnpinEaRange(v13, v50);
  LODWORD(NumberOfBytesa) = v56;
  FatPinEaRange(a1, (int)v48, v41, (int)v51, v12, NumberOfBytesa, -1073741762);
  if ( **(_WORD **)v51 != 16709 || *(_WORD *)(*(_QWORD *)v51 + 2LL) != a5 )
  {
    *(_DWORD *)(a1 + 72) = -1073741762;
    ExRaiseStatus(-1073741762);
  }
  v14 = *(unsigned __int8 *)(a2 + 378);
  v15 = v56;
  v57 = (unsigned __int16)((unsigned int)(*(unsigned __int8 *)(*(_QWORD *)v51 + 26LL)
                                        + 25
                                        + v56
                                        + ((*(unsigned __int8 *)(*(_QWORD *)v51 + 27LL)
                                          + ((*(unsigned __int8 *)(*(_QWORD *)v51 + 28LL)
                                            + (*(unsigned __int8 *)(*(_QWORD *)v51 + 29LL) << 8)) << 8)) << 8)) >> v14);
  v54 = v57 << v14;
  if ( v57 << v14 > v15 && *(_DWORD *)(v41 + 32) - v12 < (unsigned int)(v57 << v14) )
  {
    *(_DWORD *)(a1 + 72) = -1073741762;
    ExRaiseStatus(-1073741762);
  }
  FatUnpinEaRange(v14, v51);
  FileOffset.QuadPart = v12 & 0xFFFFF000;
  IoStatus = 0;
  for ( i = 5; ; i = v38 )
  {
    v17 = i == 1;
    v18 = i - 1;
    v38 = v18;
    if ( v17 )
      break;
    IoStatus.Status = 0;
    CcFlushCache(v7->SectionObjectPointer, 0, 0, &IoStatus);
    if ( CcPurgeCacheSection(v7->SectionObjectPointer, &FileOffset, 0, 0) )
    {
      v18 = v38;
      break;
    }
  }
  if ( !v18 )
  {
    *(_DWORD *)(a1 + 72) = -1073741797;
    ExRaiseStatus(-1073741797);
  }
  FileOffset.LowPart = *(_DWORD *)(v8 + 32) - v54;
  FsRtlInitializeLargeMcb(&Mcb, PagedPool);
  FatSplitAllocation(a1, a2, v8 + 288, v12, (__int64)&Mcb);
  if ( v12 + v54 != *(_DWORD *)(v8 + 32) )
  {
    FsRtlInitializeLargeMcb(&v44, PagedPool);
    v37 = 1;
    FatSplitAllocation(a1, a2, (unsigned int)&Mcb, v54, (__int64)&v44);
    FatMergeAllocation(a1, a2, v8 + 288, &v44);
  }
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v8 + 16), 1u);
  *(_DWORD *)(v8 + 32) -= v54;
  *(_QWORD *)(v8 + 24) = *(_QWORD *)(v8 + 32);
  CcSetFileSizes(v7, (PCC_FILE_SIZES)(v8 + 24));
  ExReleaseResourceLite(*(PERESOURCE *)(v8 + 16));
  *(_DWORD *)(a4 + 28) = *(_DWORD *)(v8 + 32);
  LOBYTE(v19) = 1;
  FatSetDirtyBcb(a1, a3, a2, v19);
  memset(v49, 0, sizeof(v49));
  LODWORD(NumberOfBytesb) = 512;
  FatPinEaRange(a1, (int)v7, v8, (int)v49, 0, NumberOfBytesb, -1073741743);
  v20 = *(_QWORD *)v49;
  memset(v50, 0, sizeof(v50));
  LODWORD(NumberOfBytesd) = 256;
  FatPinEaRange(a1, (int)v7, v8, (int)v50, v45[0], NumberOfBytesd, -1073741743);
  v22 = 239 - (unsigned __int16)v46;
  v23 = (_WORD *)(v20 + 32 + 2LL * ((unsigned int)(unsigned __int16)v46 + 1));
  for ( j = v23; v22--; j = v23 )
    *v23++ -= v57;
  FatMarkEaRangeDirty(v21, v7, v49);
  v25 = 127 - (unsigned __int16)v47;
  v26 = (_WORD *)(*(_QWORD *)v50 + 2 * v47);
  *v26 = -1;
  v27 = v26 + 1;
  for ( j = v27; v25--; j = v27 )
  {
    if ( *v27 != 0xFFFF )
      *v27 -= v57;
    ++v27;
  }
  FatMarkEaRangeDirty(v27, v7, v50);
  FatDeallocateDiskSpace(a1, a2, &Mcb, 0);
  FatUnpinEaRange(v29, v49);
  FatUnpinEaRange(v30, v50);
  FatUnpinEaRange(v31, v51);
  FsRtlUninitializeLargeMcb(&Mcb);
  if ( v37 )
    FsRtlUninitializeLargeMcb(&v44);
}

```

## disassembly

```asm
0x1400356f0  mov     rax, rsp
0x1400356f3  mov     [rax+20h], r9
0x1400356f7  mov     [rax+18h], r8
0x1400356fb  mov     [rax+10h], rdx
0x1400356ff  mov     [rax+8], rcx
0x140035703  push    rbx
0x140035704  push    rsi
0x140035705  push    rdi
0x140035706  push    r12
0x140035708  push    r13
0x14003570a  push    r14
0x14003570c  push    r15
0x14003570e  sub     rsp, 200h
0x140035715  mov     r14, rdx
0x140035718  mov     rdi, rcx
0x14003571b  xor     edx, edx; Val
0x14003571d  mov     qword ptr [rsp+238h+FileOffset], rdx
0x140035722  xorps   xmm0, xmm0
0x140035725  movups  xmmword ptr [rax-1B8h], xmm0
0x14003572c  movups  xmmword ptr [rax-1A8h], xmm0
0x140035733  xorps   xmm1, xmm1
0x140035736  movups  xmmword ptr [rax-198h], xmm1
0x14003573d  movups  xmmword ptr [rax-188h], xmm1
0x140035744  movzx   r15d, word ptr [rsp+238h+arg_20]
0x14003574d  movzx   eax, r15w
0x140035751  lea     r8d, [rdx+1]
0x140035755  sub     ax, r8w
0x140035759  mov     ecx, 77FEh
0x14003575e  cmp     ax, cx
0x140035761  ja      loc_140035DA1
0x140035767  mov     cl, [r14+17Ah]
0x14003576e  mov     eax, r8d
0x140035771  shl     eax, cl
0x140035773  mov     dword ptr [rsp+238h+arg_28], eax
0x14003577a  mov     [rsp+238h+var_1F2], dl
0x14003577e  mov     [rsp+238h+var_1F3], dl
0x140035782  mov     [rsp+238h+var_1F8], dl
0x140035786  mov     [rsp+238h+var_1F4], dl
0x14003578a  mov     [rsp+238h+var_1F5], dl
0x14003578e  mov     [rsp+238h+var_1F7], dl
0x140035792  mov     [rsp+238h+var_1F6], dl
0x140035796  mov     [rsp+238h+var_1E8], edx
0x14003579a  mov     r12, [r14+308h]
0x1400357a1  mov     [rsp+238h+var_160], r12
0x1400357a9  mov     r13, [r14+310h]
0x1400357b0  mov     [rsp+238h+var_1D0], r13
0x1400357b5  mov     [rsp+238h+var_1E4], edx
0x1400357b9  mov     ebx, r15d
0x1400357bc  add     rbx, rbx
0x1400357bf  and     ebx, 0FFFFFF00h
0x1400357c5  add     ebx, 200h
0x1400357cb  mov     qword ptr [rsp+238h+var_178], rbx
0x1400357d3  lea     esi, [rdx+60h]
0x1400357d6  mov     r8d, esi; Size
0x1400357d9  lea     rcx, [rsp+238h+var_158]; void *
0x1400357e1  call    memset
0x1400357e6  mov     r8d, esi; Size
0x1400357e9  xor     edx, edx; Val
0x1400357eb  lea     rcx, [rsp+238h+var_F8]; void *
0x1400357f3  call    memset
0x1400357f8  mov     r8d, esi; Size
0x1400357fb  xor     edx, edx; Val
0x1400357fd  lea     rcx, [rsp+238h+var_98]; void *
0x140035805  call    memset
0x14003580a  nop
0x14003580b  mov     esi, 0C0000051h
0x140035810  mov     [rsp+238h+Status], esi; Status
0x140035814  mov     dword ptr [rsp+238h+NumberOfBytes], 200h; NumberOfBytes
0x14003581c  mov     [rsp+238h+var_218], 0; int
0x140035824  lea     r9, [rsp+238h+var_158]; int
0x14003582c  mov     r8, r13; int
0x14003582f  mov     rdx, r12; int
0x140035832  mov     rcx, rdi; int
0x140035835  call    FatPinEaRange
0x14003583a  mov     rax, qword ptr [rsp+238h+var_158]
0x140035842  mov     qword ptr [rsp+238h+IoStatus], rax
0x140035847  mov     [rsp+238h+Status], esi; Status
0x14003584b  mov     dword ptr [rsp+238h+NumberOfBytes], 100h; NumberOfBytes
0x140035853  mov     [rsp+238h+var_218], ebx; int
0x140035857  lea     r9, [rsp+238h+var_F8]; int
0x14003585f  mov     r8, r13; int
0x140035862  mov     rdx, r12; int
0x140035865  mov     rcx, rdi; int
0x140035868  call    FatPinEaRange
0x14003586d  movzx   eax, r15w
0x140035871  mov     r15d, 7Fh
0x140035877  and     ax, r15w
0x14003587b  movzx   ecx, ax
0x14003587e  mov     [rsp+238h+var_168], rcx
0x140035886  mov     rax, qword ptr [rsp+238h+var_F8]
0x14003588e  movzx   edx, word ptr [rax+rcx*2]
0x140035892  mov     eax, 0FFFFh
0x140035897  cmp     dx, ax
0x14003589a  jnz     short loc_1400358AD
0x14003589c  mov     [rdi+48h], esi
0x14003589f  mov     ecx, esi; Status
0x1400358a1  call    cs:__imp_ExRaiseStatus
0x1400358ad  movzx   eax, word ptr [rsp+238h+arg_20]
0x1400358b5  shr     ax, 7
0x1400358b9  movzx   ecx, ax
0x1400358bc  mov     [rsp+238h+var_170], rcx
0x1400358c4  mov     rax, qword ptr [rsp+238h+IoStatus]
0x1400358c9  movzx   ebx, word ptr [rax+rcx*2+20h]
0x1400358ce  add     ebx, edx
0x1400358d0  mov     cl, [r14+17Ah]
0x1400358d7  shl     ebx, cl
0x1400358d9  mov     [rsp+238h+var_1E4], ebx
0x1400358dd  lea     rdx, [rsp+238h+var_158]
0x1400358e5  call    FatUnpinEaRange
0x1400358ea  lea     rdx, [rsp+238h+var_F8]
0x1400358f2  call    FatUnpinEaRange
0x1400358f7  mov     [rsp+238h+Status], 0C000003Eh; Status
0x1400358ff  mov     eax, dword ptr [rsp+238h+arg_28]
0x140035906  mov     dword ptr [rsp+238h+NumberOfBytes], eax; NumberOfBytes
0x14003590a  mov     [rsp+238h+var_218], ebx; int
0x14003590e  lea     r9, [rsp+238h+var_98]; int
0x140035916  mov     r8, r13; int
0x140035919  mov     rdx, r12; int
0x14003591c  mov     rcx, rdi; int
0x14003591f  call    FatPinEaRange
0x140035924  mov     rdx, qword ptr [rsp+238h+var_98]
0x14003592c  mov     eax, 4145h
0x140035931  cmp     [rdx], ax
0x140035934  jnz     loc_140035D8C
0x14003593a  movzx   eax, word ptr [rsp+238h+arg_20]
0x140035942  cmp     [rdx+2], ax
0x140035946  jnz     loc_140035D8C
0x14003594c  movzx   ecx, byte ptr [r14+17Ah]
0x140035954  movzx   r8d, byte ptr [rdx+1Dh]
0x140035959  shl     r8d, 8
0x14003595d  movzx   eax, byte ptr [rdx+1Ch]
0x140035961  add     r8d, eax
0x140035964  shl     r8d, 8
0x140035968  movzx   eax, byte ptr [rdx+1Bh]
0x14003596c  add     r8d, eax
0x14003596f  shl     r8d, 8
0x140035973  movzx   edx, byte ptr [rdx+1Ah]
0x140035977  mov     r9d, dword ptr [rsp+238h+arg_28]
0x14003597f  add     r8d, r9d
0x140035982  add     edx, 19h
0x140035985  add     r8d, edx
0x140035988  shr     r8d, cl
0x14003598b  movzx   eax, r8w
0x14003598f  mov     dword ptr [rsp+238h+arg_28], eax
0x140035996  mov     edx, eax
0x140035998  shl     edx, cl
0x14003599a  mov     [rsp+238h+arg_20], edx
0x1400359a1  cmp     edx, r9d
0x1400359a4  jbe     short loc_1400359C4
0x1400359a6  mov     eax, [r13+20h]
0x1400359aa  sub     eax, ebx
0x1400359ac  cmp     eax, edx
0x1400359ae  jnb     short loc_1400359C4
0x1400359b0  mov     ecx, 0C000003Eh; Status
0x1400359b5  mov     [rdi+48h], ecx
0x1400359b8  call    cs:__imp_ExRaiseStatus
0x1400359c4  lea     rdx, [rsp+238h+var_98]
0x1400359cc  call    FatUnpinEaRange
0x1400359d1  mov     dword ptr [rsp+238h+FileOffset], ebx
0x1400359d5  mov     dword ptr [rsp+238h+FileOffset+4], 0
0x1400359dd  mov     eax, ebx
0x1400359df  and     eax, 0FFFFF000h
0x1400359e4  mov     dword ptr [rsp+238h+FileOffset], eax
0x1400359e8  xorps   xmm0, xmm0
0x1400359eb  movups  xmmword ptr [rsp+238h+IoStatus], xmm0
0x1400359f0  mov     eax, 5
0x1400359f5  mov     [rsp+238h+var_1EC], eax
0x1400359f9  add     eax, 0FFFFFFFFh
0x1400359fc  mov     [rsp+238h+var_1EC], eax
0x140035a00  jz      short loc_140035A4F
0x140035a02  mov     dword ptr [rsp+238h+IoStatus], 0
0x140035a0a  lea     r9, [rsp+238h+IoStatus]; IoStatus
0x140035a0f  xor     r8d, r8d; Length
0x140035a12  xor     edx, edx; FileOffset
0x140035a14  mov     rcx, [r12+28h]; SectionObjectPointer
0x140035a19  call    cs:__imp_CcFlushCache
0x140035a20  nop     dword ptr [rax+rax+00h]
0x140035a25  xor     r9d, r9d; Flags
0x140035a28  xor     r8d, r8d; Length
0x140035a2b  lea     rdx, [rsp+238h+FileOffset]; FileOffset
0x140035a30  mov     rcx, [r12+28h]; SectionObjectPointer
0x140035a35  call    cs:__imp_CcPurgeCacheSection
0x140035a3c  nop     dword ptr [rax+rax+00h]
0x140035a41  test    al, al
0x140035a43  jnz     short loc_140035A4B
0x140035a45  mov     eax, [rsp+238h+var_1EC]
0x140035a49  jmp     short loc_1400359F9
0x140035a4b  mov     eax, [rsp+238h+var_1EC]
0x140035a4f  test    eax, eax
0x140035a51  jnz     short loc_140035A67
0x140035a53  mov     ecx, 0C000001Bh; Status
0x140035a58  mov     [rdi+48h], ecx
0x140035a5b  call    cs:__imp_ExRaiseStatus
0x140035a67  mov     eax, [r13+20h]
0x140035a6b  sub     eax, [rsp+238h+arg_20]
0x140035a72  mov     dword ptr [rsp+238h+FileOffset], eax
0x140035a76  mov     edx, 1; PoolType
0x140035a7b  lea     rcx, [rsp+238h+Mcb]; Mcb
0x140035a83  call    cs:__imp_FsRtlInitializeLargeMcb
0x140035a8a  nop     dword ptr [rax+rax+00h]
0x140035a8f  mov     [rsp+238h+var_1F2], 1
0x140035a94  lea     r8, [r13+120h]
0x140035a9b  lea     rcx, [rsp+238h+Mcb]
0x140035aa3  mov     qword ptr [rsp+238h+var_218], rcx
0x140035aa8  mov     r9d, ebx
0x140035aab  mov     rdx, r14
0x140035aae  mov     rcx, rdi
0x140035ab1  call    FatSplitAllocation
0x140035ab6  mov     [rsp+238h+var_1F3], 1
0x140035abb  mov     eax, [rsp+238h+arg_20]
0x140035ac2  add     eax, ebx
0x140035ac4  mov     ebx, 1
0x140035ac9  cmp     eax, [r13+20h]
0x140035acd  jz      short loc_140035B33
0x140035acf  mov     edx, ebx; PoolType
0x140035ad1  lea     rcx, [rsp+238h+var_198]; Mcb
0x140035ad9  call    cs:__imp_FsRtlInitializeLargeMcb
0x140035ae0  nop     dword ptr [rax+rax+00h]
0x140035ae5  mov     [rsp+238h+var_1F8], bl
0x140035ae9  lea     rax, [rsp+238h+var_198]
0x140035af1  mov     qword ptr [rsp+238h+var_218], rax
0x140035af6  mov     r9d, [rsp+238h+arg_20]
0x140035afe  lea     r8, [rsp+238h+Mcb]
0x140035b06  mov     rdx, r14
0x140035b09  mov     rcx, rdi
0x140035b0c  call    FatSplitAllocation
0x140035b11  mov     [rsp+238h+var_1F4], bl
0x140035b15  lea     r9, [rsp+238h+var_198]
0x140035b1d  lea     r8, [r13+120h]
0x140035b24  mov     rdx, r14
0x140035b27  mov     rcx, rdi
0x140035b2a  call    FatMergeAllocation
0x140035b2f  mov     [rsp+238h+var_1F5], bl
0x140035b33  mov     eax, [r13+20h]
0x140035b37  mov     [rsp+238h+var_1E8], eax
0x140035b3b  mov     dl, bl; Wait
0x140035b3d  mov     rcx, [r13+10h]; Resource
0x140035b41  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140035b48  nop     dword ptr [rax+rax+00h]
0x140035b4d  mov     eax, [rsp+238h+arg_20]
0x140035b54  sub     [r13+20h], eax
0x140035b58  lea     rdx, [r13+18h]; FileSizes
0x140035b5c  mov     rax, [r13+20h]
0x140035b60  mov     [rdx], rax
0x140035b63  mov     rcx, r12; FileObject
0x140035b66  call    cs:__imp_CcSetFileSizes
0x140035b6d  nop     dword ptr [rax+rax+00h]
0x140035b72  mov     rcx, [r13+10h]; Resource
0x140035b76  call    cs:__imp_ExReleaseResourceLite
0x140035b7d  nop     dword ptr [rax+rax+00h]
0x140035b82  mov     [rsp+238h+var_1F6], bl
0x140035b86  mov     eax, [r13+20h]
0x140035b8a  mov     rcx, [rsp+238h+arg_18]
0x140035b92  mov     [rcx+1Ch], eax
0x140035b95  mov     r9b, bl
0x140035b98  mov     r8, r14
0x140035b9b  mov     rdx, [rsp+238h+arg_10]
0x140035ba3  mov     rcx, rdi
0x140035ba6  call    FatSetDirtyBcb
0x140035bab  xor     edx, edx; Val
0x140035bad  lea     r8d, [rdx+60h]; Size
0x140035bb1  lea     rcx, [rsp+238h+var_158]; void *
0x140035bb9  call    memset
0x140035bbe  mov     [rsp+238h+Status], esi; Status
0x140035bc2  mov     dword ptr [rsp+238h+NumberOfBytes], 200h; NumberOfBytes
0x140035bca  mov     [rsp+238h+var_218], 0; int
0x140035bd2  lea     r9, [rsp+238h+var_158]; int
0x140035bda  mov     r8, r13; int
0x140035bdd  mov     rdx, r12; int
0x140035be0  mov     rcx, rdi; int
0x140035be3  call    FatPinEaRange
0x140035be8  mov     rbx, qword ptr [rsp+238h+var_158]
0x140035bf0  xor     edx, edx; Val
0x140035bf2  lea     r8d, [rdx+60h]; Size
0x140035bf6  lea     rcx, [rsp+238h+var_F8]; void *
0x140035bfe  call    memset
0x140035c03  mov     [rsp+238h+Status], esi; Status
0x140035c07  mov     dword ptr [rsp+238h+NumberOfBytes], 100h; NumberOfBytes
0x140035c0f  mov     rax, qword ptr [rsp+238h+var_178]
0x140035c17  mov     [rsp+238h+var_218], eax; int
0x140035c1b  lea     r9, [rsp+238h+var_F8]; int
0x140035c23  mov     r8, r13; int
0x140035c26  mov     rdx, r12; int
0x140035c29  mov     rcx, rdi; int
0x140035c2c  call    FatPinEaRange
0x140035c31  xor     esi, esi
0x140035c33  mov     [rsp+238h+var_1F0], esi
0x140035c37  mov     [rsp+238h+var_1D8], rsi
0x140035c3c  movzx   eax, word ptr [rsp+238h+var_170]
0x140035c44  mov     r8d, 0EFh
0x140035c4a  sub     r8d, eax
0x140035c4d  mov     [rsp+238h+var_1F0], r8d
0x140035c52  inc     eax
0x140035c54  add     rbx, 20h ; ' '
0x140035c58  lea     rdx, [rbx+rax*2]
0x140035c5c  mov     [rsp+238h+var_1D8], rdx
0x140035c61  mov     ebx, dword ptr [rsp+238h+arg_28]
0x140035c68  or      r13d, 0FFFFFFFFh
0x140035c6c  mov     eax, r8d
0x140035c6f  add     r8d, r13d
  ... truncated ...
```
