# NtOfsCreateAttributeEx

- ea: `0x14000363c`
- end: `0x140003e94`
- name: `NtOfsCreateAttributeEx`
- size: `2136`
- prototype: ``
- caller_count: `8`
- callee_count: `28`
- tags: `file_ops`

## callers

- `0x140050780`
- `0x140050cf0`
- `0x140053a88`
- `0x140053b10`
- `0x140053c18`
- `0x140054480`
- `0x14005489c`
- `0x140056ccc`

## callees

- `0x140001858`
- `0x1400018a4`
- `0x1400019b8`
- `0x14000363c`
- `0x140005288`
- `0x14000c212`
- `0x14000c680`
- `0x140020458`
- `0x1400226b8`
- `0x140023ad4`
- `0x140024228`
- `0x1400247f4`
- `0x14002486c`
- `0x14002ca48`
- `0x1400302d8`
- `0x14003062c`
- `0x1400319bc`
- `0x140031e8c`
- `0x140033270`
- `0x14003db44`
- `0x14003e870`
- `0x140044bac`
- `0x140044df4`
- `0x1400465f4`
- `0x140047058`
- `0x140047960`
- `0x140048184`
- `0x140048e6c`

## import_xrefs

- `ntoskrnl!IoCreateStreamFileObject` at `0x140003afc`
- `ntoskrnl!IoCreateStreamFileObject` at `0x140003cdd`
- `ntoskrnl!IoCreateStreamFileObject` at `0x140003afc`
- `ntoskrnl!IoCreateStreamFileObject` at `0x140003cdd`
- `ntoskrnl!CcPreparePinWrite` at `0x1400038b8`
- `ntoskrnl!CcPreparePinWrite` at `0x1400038b8`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1400036d6`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1400036d6`
- `ntoskrnl!ObfReferenceObject` at `0x1400039d1`
- `ntoskrnl!ObfReferenceObject` at `0x1400039d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003a10`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003a10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003948`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cd94`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ce92`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003948`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cd94`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ce92`
- `ntoskrnl!CcUnpinData` at `0x14000383d`
- `ntoskrnl!CcUnpinData` at `0x1400038e3`
- `ntoskrnl!CcUnpinData` at `0x140003918`
- `ntoskrnl!CcUnpinData` at `0x140003933`
- `ntoskrnl!CcUnpinData` at `0x140003e01`
- `ntoskrnl!CcUnpinData` at `0x140003e5e`
- `ntoskrnl!CcUnpinData` at `0x14000cd58`
- `ntoskrnl!CcUnpinData` at `0x14000cd75`
- `ntoskrnl!CcUnpinData` at `0x14000cdf9`
- `ntoskrnl!CcUnpinData` at `0x14000383d`
- `ntoskrnl!CcUnpinData` at `0x1400038e3`
- `ntoskrnl!CcUnpinData` at `0x140003918`
- `ntoskrnl!CcUnpinData` at `0x140003933`
- `ntoskrnl!CcUnpinData` at `0x140003e01`
- `ntoskrnl!CcUnpinData` at `0x140003e5e`
- `ntoskrnl!CcUnpinData` at `0x14000cd58`
- `ntoskrnl!CcUnpinData` at `0x14000cd75`
- `ntoskrnl!CcUnpinData` at `0x14000cdf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce3b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ce67`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ce67`

## pseudocode

```c
__int64 __fastcall NtOfsCreateAttributeEx(
        _WORD *a1,
        __int64 a2,
        PCUNICODE_STRING ConstantNameA,
        int a4,
        int a5,
        int a6,
        __int64 *a7)
{
  __int64 v9; // r15
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // eax
  int v13; // esi
  int v14; // r15d
  __int64 v15; // rcx
  __int64 v16; // r13
  __int64 v17; // r8
  __int64 v18; // r9
  void *v19; // rcx
  int v20; // esi
  __int64 v21; // rcx
  int v22; // ecx
  __int64 v23; // rsi
  PFILE_OBJECT v24; // r15
  __int64 v25; // rdx
  int v26; // r8d
  int v27; // ecx
  int v28; // ecx
  __int64 Fcb; // rsi
  PFILE_OBJECT StreamFileObject; // r15
  __int64 v31; // rdx
  int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  PVOID v36; // rcx
  __int64 v38; // [rsp+0h] [rbp-138h] BYREF
  __int64 v39; // [rsp+38h] [rbp-100h]
  __int64 v40; // [rsp+40h] [rbp-F8h]
  char v41; // [rsp+60h] [rbp-D8h]
  char v42; // [rsp+61h] [rbp-D7h]
  char v43; // [rsp+62h] [rbp-D6h]
  unsigned int v44; // [rsp+64h] [rbp-D4h]
  char v45; // [rsp+68h] [rbp-D0h]
  PVOID Bcb; // [rsp+70h] [rbp-C8h] BYREF
  PVOID v47; // [rsp+78h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+80h] [rbp-B8h] BYREF
  PFILE_OBJECT v49; // [rsp+88h] [rbp-B0h]
  PVOID Buffer[2]; // [rsp+90h] [rbp-A8h] BYREF
  __int64 *v51; // [rsp+A0h] [rbp-98h]
  struct _UNICODE_STRING v52[8]; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v53; // [rsp+158h] [rbp+20h] BYREF

  LODWORD(v53) = a4;
  v51 = &v38;
  if ( (byte_140017D4D & 2) == 0
    || *a1 != 1288
    || a1[1] != 144
    || *(_WORD *)a2 == 1284
    || (unsigned __int16)(*(_WORD *)a2 - 1282) > 1u )
  {
    return (unsigned int)-1073741811;
  }
  v9 = *(_QWORD *)(a2 + 184);
  if ( FsRtlAreNamesEqual(ConstantNameA, &_EFS, 1u, 0) )
  {
    v44 = 0;
    if ( *(_WORD *)a2 == 1282 )
    {
      v48 = 0;
      Bcb = 0;
      v47 = 0;
      FatAcquireExclusiveFcb(a1, a2, v10, v11);
      v13 = 0x8000;
      if ( (unsigned int)(a5 - 1) <= 1 )
      {
        if ( (*(_DWORD *)(a2 + 192) & 0x8000) != 0 )
        {
LABEL_15:
          FatOpenFileHeader(a1, 0, a2);
          *a7 = a2;
          v44 = 0;
          local_unwind_0(v51, &loc_140003E7C);
          goto LABEL_16;
        }
        if ( a5 == 2 )
        {
          v13 = -1073741772;
          v44 = -1073741772;
          local_unwind_0(v51, &loc_140003E7C);
          goto LABEL_15;
        }
      }
LABEL_16:
      FatGetDirentFromFcbOrDcb((_DWORD)a1, a2, 0, (unsigned int)&v48, (__int64)&Bcb);
      FatSetDirtyBcb(a1, Bcb, *(_QWORD *)(a2 + 184), 0);
      *(_DWORD *)(a2 + 192) |= v13;
      *(_BYTE *)(a2 + 5) = 2;
      v14 = *(_DWORD *)(v9 + 372);
      *(_DWORD *)(a2 + 132) = v14;
      *(_BYTE *)(a2 + 136) = 0;
      *(_DWORD *)(v48 + 28) = (v14 + 15) & 0xFFFFFFF0;
      *(_BYTE *)(v48 + 12) = *(_BYTE *)(v48 + 12) & 0x1B
                           | (4 * (*(_BYTE *)(a2 + 136) & 1 | (4 * (*(_BYTE *)(a2 + 136) & 0xFE))));
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
      FatAddFileAllocation((_DWORD)a1);
      if ( (v13 & *(_DWORD *)(a2 + 192)) != 0 )
      {
        Buffer[0] = 0;
        FatOpenFileHeader(a1, 0, a2);
        if ( CcPreparePinWrite(*(PFILE_OBJECT *)(a2 + 424), &FatLargeZero, *(_DWORD *)(a2 + 132), 0, 1u, &v47, Buffer) )
        {
          memset(Buffer[0], 0, *(unsigned int *)(a2 + 132));
          CcUnpinData(v47);
          v47 = 0;
        }
      }
      FatFlushFile(v15, a2, 1);
      *a7 = a2;
      v44 = 0;
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
      if ( v47 )
      {
        CcUnpinData(v47);
        v47 = 0;
      }
LABEL_25:
      ExReleaseResourceLite(*(PERESOURCE *)(a2 + 8));
      return v44;
    }
    if ( *(_WORD *)a2 == 1283 )
    {
      memset(v52, 0, 0x50u);
      v47 = 0;
      Bcb = 0;
      LODWORD(v53) = 0;
      v48 = 0;
      v43 = 0;
      v42 = 0;
      v41 = 0;
      v49 = 0;
      v45 = 0;
      v16 = *(_QWORD *)(a2 + 184);
      FatAcquireExclusiveFcb(a1, a2, v17, v18);
      v44 = -1073741823;
      v19 = *(void **)(a2 + 360);
      if ( v19 )
      {
        ObfReferenceObject(v19);
        ++*(_DWORD *)(a2 + 352);
        *a7 = *(_QWORD *)(a2 + 368);
      }
      else
      {
        RtlInitUnicodeString(&v52[3], _EFS.Buffer);
        *(_OWORD *)Buffer = *(_OWORD *)&_EFS_SHORT;
        FatStringTo8dot3(v21, Buffer, &v52[2]);
        LOBYTE(v52[0].Buffer) = 0;
        FatLocateDirent((__int64)a1, a2, (__int64)v52, 0, 0, &v47, &Bcb, (unsigned int *)&v53, 0, 0, 0);
        if ( !v47 )
        {
          if ( a5 == 2 )
          {
            v20 = -1073741772;
            v44 = -1073741772;
          }
          else
          {
            LODWORD(v53) = FatCreateNewDirent((int)a1, a2, 1u);
            v40 = (__int64)Buffer;
            LOBYTE(v39) = 1;
            FatPrepareWriteDirectoryFile(a1, a2, (unsigned int)v53, 32, &Bcb, &v47);
            FatConstructDirent(v27, (_DWORD)v47, (unsigned int)&_EFS_SHORT, 0, 0, 0, 6, 1, 0);
            Fcb = FatCreateFcb(v28, v16, a2, v53, v53, (__int64)v47, 0, 0, 0, 0);
            v48 = Fcb;
            v43 = 1;
            *(_DWORD *)(Fcb + 192) |= 0x10000u;
            StreamFileObject = IoCreateStreamFileObject(0, *(PDEVICE_OBJECT *)(v16 + 768));
            v49 = StreamFileObject;
            FatPreallocateCloseContext();
            v41 = 1;
            StreamFileObject->SectionObjectPointer = *(PSECTION_OBJECT_POINTERS *)(Fcb + 120);
            *(_WORD *)&StreamFileObject->ReadAccess = 257;
            StreamFileObject->DeleteAccess = 1;
            FatSetFullNameInFcb(a1, Fcb, &_EFS);
            FatSetFileObject(StreamFileObject, v31, Fcb, 0);
            v43 = 0;
            *(_DWORD *)(Fcb + 24) = 0;
            *(_DWORD *)(Fcb + 32) = 0;
            FatAddFileAllocation((_DWORD)a1);
            v45 = 1;
            *(_DWORD *)(a2 + 192) |= 2u;
            if ( !StreamFileObject->PrivateCacheMap )
            {
              *(_QWORD *)(Fcb + 40) = FatMaxLarge;
              *(_DWORD *)(Fcb + 280) = -1;
              LOBYTE(v32) = 1;
              FatInitializeCacheMap((int)StreamFileObject, Fcb + 24, v32, (int)&qword_140017DB0, (PVOID)Fcb);
              v42 = 1;
            }
            FatSetFileSizeInDirent(a1, Fcb);
            *(_QWORD *)(a2 + 360) = StreamFileObject;
            ++*(_DWORD *)(Fcb + 232);
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 184) + 280LL));
            ++*(_DWORD *)(a2 + 352);
            *(_QWORD *)(a2 + 368) = Fcb;
            v49 = 0;
            v48 = 0;
            v41 = 0;
            v45 = 0;
            v42 = 0;
            *a7 = Fcb;
            v20 = 0;
            v44 = 0;
            if ( Bcb )
            {
              CcUnpinData(Bcb);
              Bcb = 0;
            }
            Bcb = 0;
            FatUnpinRepinnedBcbs(a1, v33, v34, v35);
          }
          goto LABEL_43;
        }
        v23 = FatCreateFcb(v22, v16, a2, v53, v53, (__int64)v47, 0, 0, 0, 0);
        v48 = v23;
        v43 = 1;
        *(_DWORD *)(v23 + 192) |= 0x10000u;
        FatSetFullFileNameInFcb((int)a1);
        v24 = IoCreateStreamFileObject(0, *(PDEVICE_OBJECT *)(v16 + 768));
        v49 = v24;
        v24->SectionObjectPointer = *(PSECTION_OBJECT_POINTERS *)(v23 + 120);
        *(_WORD *)&v24->ReadAccess = 257;
        v24->DeleteAccess = 1;
        FatPreallocateCloseContext();
        v41 = 1;
        FatSetFileObject(v24, v25, v23, 0);
        v43 = 0;
        if ( *(_QWORD *)(v23 + 24) == -1 )
        {
          FatLookupFileAllocationSize(a1, v23);
          *(_DWORD *)(v23 + 32) = *(_DWORD *)(v23 + 24);
        }
        if ( !v24->PrivateCacheMap )
        {
          *(_QWORD *)(v23 + 40) = FatMaxLarge;
          *(_DWORD *)(v23 + 280) = -1;
          LOBYTE(v26) = 1;
          FatInitializeCacheMap((int)v24, v23 + 24, v26, (int)&qword_140017DB0, (PVOID)v23);
          v42 = 1;
        }
        v24->SectionObjectPointer = *(PSECTION_OBJECT_POINTERS *)(v23 + 120);
        *(_QWORD *)(a2 + 360) = v24;
        v49 = 0;
        ++*(_DWORD *)(v23 + 232);
        ++*(_DWORD *)(a2 + 352);
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 184) + 280LL));
        *(_QWORD *)(a2 + 368) = v23;
        v48 = 0;
        v41 = 0;
        v42 = 0;
        *a7 = v23;
      }
      v20 = 0;
      v44 = 0;
LABEL_43:
      v36 = Bcb;
      if ( Bcb )
      {
        if ( v20 )
        {
          *(_BYTE *)v47 = -27;
          v36 = Bcb;
        }
        if ( v36 )
          CcUnpinData(v36);
        Bcb = 0;
      }
      goto LABEL_25;
    }
    return (unsigned int)-1073741811;
  }
  v12 = -1073740761;
  if ( a5 >= 2 )
    return (unsigned int)-1073741772;
  return v12;
}

```

## disassembly

```asm
0x14000363c  mov     dword ptr [rsp+arg_18], r9d
0x140003641  mov     [rsp+arg_8], rdx
0x140003646  mov     [rsp+arg_0], rcx
0x14000364b  push    rbx
0x14000364c  push    rsi
0x14000364d  push    rdi
0x14000364e  push    r12
0x140003650  push    r13
0x140003652  push    r14
0x140003654  push    r15
0x140003656  sub     rsp, 100h
0x14000365d  mov     [rsp+138h+var_98], rsp
0x140003665  mov     r10, r8
0x140003668  mov     rdi, rdx
0x14000366b  mov     r14, rcx
0x14000366e  test    cs:byte_140017D4D, 2
0x140003675  jz      loc_140003E74
0x14000367b  mov     eax, 508h
0x140003680  cmp     [rcx], ax
0x140003683  jnz     loc_140003E74
0x140003689  mov     eax, 90h
0x14000368e  cmp     [rcx+2], ax
0x140003692  jnz     loc_140003E74
0x140003698  movzx   eax, word ptr [rdx]
0x14000369b  mov     ecx, 504h
0x1400036a0  cmp     ax, cx
0x1400036a3  jz      loc_140003E74
0x1400036a9  lea     esi, [rcx-2]
0x1400036ac  sub     ax, si
0x1400036af  mov     r12d, 1
0x1400036b5  cmp     ax, r12w
0x1400036b9  ja      loc_140003E74
0x1400036bf  mov     r15, [rdx+0B8h]
0x1400036c6  xor     r9d, r9d; UpcaseTable
0x1400036c9  mov     r8b, r12b; IgnoreCase
0x1400036cc  lea     rdx, $EFS; ConstantNameB
0x1400036d3  mov     rcx, r10; ConstantNameA
0x1400036d6  call    cs:__imp_FsRtlAreNamesEqual
0x1400036dd  nop     dword ptr [rax+rax+00h]
0x1400036e2  xor     ebx, ebx
0x1400036e4  test    al, al
0x1400036e6  jnz     short loc_140003706
0x1400036e8  mov     eax, 0C0000427h
0x1400036ed  mov     esi, 0C0000034h
0x1400036f2  cmp     [rsp+138h+arg_20], 2
0x1400036fa  cmovge  eax, esi
0x1400036fd  mov     [rsp+138h+var_D4], eax
0x140003701  jmp     loc_140003E7C
0x140003706  mov     [rsp+138h+var_D4], ebx
0x14000370a  movzx   eax, word ptr [rdi]
0x14000370d  cmp     ax, si
0x140003710  jnz     loc_140003959
0x140003716  mov     [rsp+138h+var_B8], rbx
0x14000371e  mov     [rsp+138h+Bcb], rbx
0x140003723  mov     [rsp+138h+var_C0], rbx
0x140003728  mov     rdx, rdi
0x14000372b  mov     rcx, r14
0x14000372e  call    FatAcquireExclusiveFcb
0x140003733  nop
0x140003734  mov     ecx, [rsp+138h+arg_20]
0x14000373b  lea     eax, [rcx-1]
0x14000373e  mov     esi, 8000h
0x140003743  cmp     eax, r12d
0x140003746  ja      short loc_1400037A4
0x140003748  mov     eax, [rdi+0C0h]
0x14000374e  test    esi, eax
0x140003750  jnz     short loc_140003774
0x140003752  cmp     ecx, 2
0x140003755  jnz     short loc_1400037A4
0x140003757  mov     esi, 0C0000034h
0x14000375c  mov     [rsp+138h+var_D4], esi
0x140003760  lea     rdx, loc_140003E7C
0x140003767  mov     rcx, [rsp+138h+var_98]
0x14000376f  call    _local_unwind_0
0x140003774  mov     r8, rdi
0x140003777  xor     edx, edx
0x140003779  mov     rcx, r14
0x14000377c  call    FatOpenFileHeader
0x140003781  mov     rax, [rsp+138h+arg_30]
0x140003789  mov     [rax], rdi
0x14000378c  mov     [rsp+138h+var_D4], ebx
0x140003790  lea     rdx, loc_140003E7C
0x140003797  mov     rcx, [rsp+138h+var_98]
0x14000379f  call    _local_unwind_0
0x1400037a4  lea     rax, [rsp+138h+Bcb]
0x1400037a9  mov     qword ptr [rsp+138h+Flags], rax
0x1400037ae  lea     r9, [rsp+138h+var_B8]
0x1400037b6  xor     r8d, r8d
0x1400037b9  mov     rdx, rdi
0x1400037bc  mov     rcx, r14
0x1400037bf  call    FatGetDirentFromFcbOrDcb
0x1400037c4  xor     r9d, r9d
0x1400037c7  mov     r8, [rdi+0B8h]
0x1400037ce  mov     rdx, [rsp+138h+Bcb]
0x1400037d3  mov     rcx, r14
0x1400037d6  call    FatSetDirtyBcb
0x1400037db  or      [rdi+0C0h], esi
0x1400037e1  mov     byte ptr [rdi+5], 2
0x1400037e5  mov     r15d, [r15+174h]
0x1400037ec  mov     [rdi+84h], r15d
0x1400037f3  mov     [rdi+88h], bl
0x1400037f9  lea     ecx, [r15+0Fh]
0x1400037fd  and     ecx, 0FFFFFFF0h
0x140003800  mov     rax, [rsp+138h+var_B8]
0x140003808  mov     [rax+1Ch], ecx
0x14000380b  mov     al, [rdi+88h]
0x140003811  mov     rdx, [rsp+138h+var_B8]
0x140003819  mov     cl, al
0x14000381b  and     cl, 0FEh
0x14000381e  shl     cl, 2
0x140003821  and     al, r12b
0x140003824  or      cl, al
0x140003826  shl     cl, 2
0x140003829  mov     al, [rdx+0Ch]
0x14000382c  and     al, 1Bh
0x14000382e  or      cl, al
0x140003830  mov     [rdx+0Ch], cl
0x140003833  mov     rcx, [rsp+138h+Bcb]; Bcb
0x140003838  test    rcx, rcx
0x14000383b  jz      short loc_14000384E
0x14000383d  call    cs:__imp_CcUnpinData
0x140003844  nop     dword ptr [rax+rax+00h]
0x140003849  mov     [rsp+138h+Bcb], rbx
0x14000384e  mov     r9d, r15d
0x140003851  mov     r8, [rdi+1A8h]
0x140003858  mov     rdx, rdi
0x14000385b  mov     rcx, r14
0x14000385e  call    FatAddFileAllocation
0x140003863  test    [rdi+0C0h], esi
0x140003869  jz      loc_1400038F4
0x14000386f  mov     [rsp+138h+var_A8], rbx
0x140003877  mov     r8, rdi
0x14000387a  xor     edx, edx
0x14000387c  mov     rcx, r14
0x14000387f  call    FatOpenFileHeader
0x140003884  lea     rax, [rsp+138h+var_A8]
0x14000388c  mov     [rsp+138h+Buffer], rax; Buffer
0x140003891  lea     rax, [rsp+138h+var_C0]
0x140003896  mov     [rsp+138h+var_110], rax; Bcb
0x14000389b  mov     [rsp+138h+Flags], r12d; Flags
0x1400038a0  xor     r9d, r9d; Zero
0x1400038a3  mov     r8d, [rdi+84h]; Length
0x1400038aa  lea     rdx, FatLargeZero; FileOffset
0x1400038b1  mov     rcx, [rdi+1A8h]; FileObject
0x1400038b8  call    cs:__imp_CcPreparePinWrite
0x1400038bf  nop     dword ptr [rax+rax+00h]
0x1400038c4  test    al, al
0x1400038c6  jz      short loc_1400038F4
0x1400038c8  mov     r8d, [rdi+84h]; Size
0x1400038cf  xor     edx, edx; Val
0x1400038d1  mov     rcx, [rsp+138h+var_A8]; void *
0x1400038d9  call    memset
0x1400038de  mov     rcx, [rsp+138h+var_C0]; Bcb
0x1400038e3  call    cs:__imp_CcUnpinData
0x1400038ea  nop     dword ptr [rax+rax+00h]
0x1400038ef  mov     [rsp+138h+var_C0], rbx
0x1400038f4  mov     r8d, r12d
0x1400038f7  mov     rdx, rdi
0x1400038fa  call    FatFlushFile
0x1400038ff  mov     rax, [rsp+138h+arg_30]
0x140003907  mov     [rax], rdi
0x14000390a  mov     [rsp+138h+var_D4], ebx
0x14000390e  mov     rcx, [rsp+138h+Bcb]; Bcb
0x140003913  test    rcx, rcx
0x140003916  jz      short loc_140003929
0x140003918  call    cs:__imp_CcUnpinData
0x14000391f  nop     dword ptr [rax+rax+00h]
0x140003924  mov     [rsp+138h+Bcb], rbx
0x140003929  mov     rcx, [rsp+138h+var_C0]; Bcb
0x14000392e  test    rcx, rcx
0x140003931  jz      short loc_140003944
0x140003933  call    cs:__imp_CcUnpinData
0x14000393a  nop     dword ptr [rax+rax+00h]
0x14000393f  mov     [rsp+138h+var_C0], rbx
0x140003944  mov     rcx, [rdi+8]; Resource
0x140003948  call    cs:__imp_ExReleaseResourceLite
0x14000394f  nop     dword ptr [rax+rax+00h]
0x140003954  jmp     loc_140003E7C
0x140003959  mov     ecx, 503h
0x14000395e  cmp     ax, cx
0x140003961  jnz     loc_140003E74
0x140003967  xor     edx, edx; Val
0x140003969  lea     r8d, [rdx+50h]; Size
0x14000396d  lea     rcx, [rsp+138h+var_88]; void *
0x140003975  call    memset
0x14000397a  mov     [rsp+138h+var_C0], rbx
0x14000397f  mov     [rsp+138h+Bcb], rbx
0x140003984  mov     dword ptr [rsp+138h+arg_18], ebx
0x14000398b  mov     [rsp+138h+var_B8], rbx
0x140003993  mov     [rsp+138h+var_D6], bl
0x140003997  mov     [rsp+138h+var_D7], bl
0x14000399b  mov     [rsp+138h+var_D8], bl
0x14000399f  mov     [rsp+138h+var_B0], rbx
0x1400039a7  mov     [rsp+138h+var_D0], bl
0x1400039ab  mov     r13, [rdi+0B8h]
0x1400039b2  mov     rdx, rdi
0x1400039b5  mov     rcx, r14
0x1400039b8  call    FatAcquireExclusiveFcb
0x1400039bd  mov     [rsp+138h+var_D4], 0C0000001h
0x1400039c5  mov     rcx, [rdi+168h]; Object
0x1400039cc  test    rcx, rcx
0x1400039cf  jz      short loc_140003A01
0x1400039d1  call    cs:__imp_ObfReferenceObject
0x1400039d8  nop     dword ptr [rax+rax+00h]
0x1400039dd  add     [rdi+160h], r12d
0x1400039e4  mov     rcx, [rdi+170h]
0x1400039eb  mov     rax, [rsp+138h+arg_30]
0x1400039f3  mov     [rax], rcx
0x1400039f6  mov     esi, ebx
0x1400039f8  mov     [rsp+138h+var_D4], ebx
0x1400039fc  jmp     loc_140003E3A
0x140003a01  mov     rdx, cs:$EFS.Buffer; SourceString
0x140003a08  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x140003a10  call    cs:__imp_RtlInitUnicodeString
0x140003a17  nop     dword ptr [rax+rax+00h]
0x140003a1c  movups  xmm0, xmmword ptr cs:$EFS_SHORT
0x140003a23  movdqu  xmmword ptr [rsp+138h+var_A8], xmm0
0x140003a2c  lea     r8, [rsp+138h+var_68]
0x140003a34  lea     rdx, [rsp+138h+var_A8]
0x140003a3c  call    FatStringTo8dot3
0x140003a41  mov     [rsp+138h+var_80], bl
0x140003a48  mov     [rsp+138h+var_E8], rbx; __int64
0x140003a4d  mov     [rsp+138h+SourceString], rbx; SourceString
0x140003a52  mov     [rsp+138h+var_F8], rbx; __int64
0x140003a57  lea     rax, [rsp+138h+arg_18]
0x140003a5f  mov     [rsp+138h+var_100], rax; __int64
0x140003a64  lea     rax, [rsp+138h+Bcb]
0x140003a69  mov     [rsp+138h+Buffer], rax; __int64
0x140003a6e  lea     rax, [rsp+138h+var_C0]
0x140003a73  mov     [rsp+138h+var_110], rax; __int64
0x140003a78  mov     qword ptr [rsp+138h+Flags], rbx; __int64
0x140003a7d  xor     r9d, r9d; int
0x140003a80  lea     r8, [rsp+138h+var_88]; int
0x140003a88  mov     rdx, rdi; int
0x140003a8b  mov     rcx, r14; int
0x140003a8e  call    FatLocateDirent
0x140003a93  mov     rax, [rsp+138h+var_C0]
0x140003a98  test    rax, rax
0x140003a9b  jz      loc_140003BF0
0x140003aa1  mov     byte ptr [rsp+138h+SourceString], bl
0x140003aa5  mov     byte ptr [rsp+138h+var_F8], bl
0x140003aa9  mov     [rsp+138h+var_100], rbx
0x140003aae  mov     [rsp+138h+Buffer], rbx
0x140003ab3  mov     [rsp+138h+var_110], rax
0x140003ab8  mov     r9d, dword ptr [rsp+138h+arg_18]
0x140003ac0  mov     [rsp+138h+Flags], r9d
0x140003ac5  mov     r8, rdi
0x140003ac8  mov     rdx, r13
0x140003acb  call    FatCreateFcb
0x140003ad0  mov     rsi, rax
0x140003ad3  mov     [rsp+138h+var_B8], rax
0x140003adb  mov     [rsp+138h+var_D6], r12b
0x140003ae0  bts     dword ptr [rax+0C0h], 10h
0x140003ae8  mov     rdx, rax
0x140003aeb  mov     rcx, r14; int
0x140003aee  call    FatSetFullFileNameInFcb
0x140003af3  mov     rdx, [r13+300h]; DeviceObject
0x140003afa  xor     ecx, ecx; FileObject
0x140003afc  call    cs:__imp_IoCreateStreamFileObject
0x140003b03  nop     dword ptr [rax+rax+00h]
0x140003b08  mov     r15, rax
0x140003b0b  mov     [rsp+138h+var_B0], rax
0x140003b13  mov     rcx, [rsi+78h]
0x140003b17  mov     [rax+28h], rcx
0x140003b1b  mov     word ptr [rax+4Ah], 101h
0x140003b21  mov     [rax+4Ch], r12b
0x140003b25  call    FatPreallocateCloseContext
0x140003b2a  mov     [rsp+138h+var_D8], r12b
0x140003b2f  xor     r9d, r9d
0x140003b32  mov     r8, rsi
0x140003b35  mov     rcx, r15
0x140003b38  call    FatSetFileObject
0x140003b3d  mov     [rsp+138h+var_D6], bl
0x140003b41  lea     r12, [rsi+18h]
0x140003b45  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x140003b4a  jnz     short loc_140003B5E
0x140003b4c  mov     rdx, rsi
0x140003b4f  mov     rcx, r14
0x140003b52  call    FatLookupFileAllocationSize
0x140003b57  mov     eax, [r12]
0x140003b5b  mov     [rsi+20h], eax
0x140003b5e  cmp     [r15+30h], rbx
0x140003b62  jnz     short loc_140003B98
0x140003b64  mov     rax, cs:FatMaxLarge
0x140003b6b  mov     [rsi+28h], rax
0x140003b6f  mov     dword ptr [rsi+118h], 0FFFFFFFFh
0x140003b79  mov     qword ptr [rsp+138h+Flags], rsi; PVOID
0x140003b7e  lea     r9, qword_140017DB0; int
0x140003b85  mov     r8b, 1; int
0x140003b88  mov     rdx, r12; int
0x140003b8b  mov     rcx, r15; int
0x140003b8e  call    FatInitializeCacheMap
0x140003b93  mov     [rsp+138h+var_D7], 1
0x140003b98  mov     rax, [rsi+78h]
0x140003b9c  mov     [r15+28h], rax
0x140003ba0  mov     [rdi+168h], r15
0x140003ba7  mov     [rsp+138h+var_B0], rbx
0x140003baf  inc     dword ptr [rsi+0E8h]
0x140003bb5  inc     dword ptr [rdi+160h]
0x140003bbb  mov     rax, [rdi+0B8h]
  ... truncated ...
```
