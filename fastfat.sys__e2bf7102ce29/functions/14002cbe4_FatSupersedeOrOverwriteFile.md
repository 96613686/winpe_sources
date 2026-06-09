# FatSupersedeOrOverwriteFile

- ea: `0x14002cbe4`
- end: `0x14002d0cc`
- name: `FatSupersedeOrOverwriteFile`
- size: `1256`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x14002adec`
- `0x14002b790`

## callees

- `0x1400019b8`
- `0x140001d4c`
- `0x140020458`
- `0x140023ad4`
- `0x14002cbe4`
- `0x1400319bc`
- `0x140035234`
- `0x140035608`
- `0x14003db44`
- `0x140044bac`
- `0x1400475e8`
- `0x14004814c`
- `0x140049634`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x14002cce7`
- `ntoskrnl!CcPurgeCacheSection` at `0x14002cce7`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002cd62`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002cd62`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14002d07e`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14002d07e`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14002cc79`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14002cc79`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002cd8d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002cd8d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002ce2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005cc1b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002ce2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005cc1b`
- `ntoskrnl!CcUnpinData` at `0x14002d0a4`
- `ntoskrnl!CcUnpinData` at `0x14005cc6c`
- `ntoskrnl!CcUnpinData` at `0x14002d0a4`
- `ntoskrnl!CcUnpinData` at `0x14005cc6c`
- `ntoskrnl!CcSetFileSizes` at `0x14002ce08`
- `ntoskrnl!CcSetFileSizes` at `0x14002ce08`
- `ntoskrnl!ExRaiseStatus` at `0x14002cd7b`
- `ntoskrnl!ExRaiseStatus` at `0x14002cdf0`
- `ntoskrnl!ExRaiseStatus` at `0x14002cd7b`
- `ntoskrnl!ExRaiseStatus` at `0x14002cdf0`

## pseudocode

```c
__int64 __fastcall FatSupersedeOrOverwriteFile(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        unsigned __int16 a8,
        int a9,
        char a10)
{
  unsigned int v14; // ebx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  struct _LIST_ENTRY **v19; // r13
  NTSTATUS v20; // eax
  __int64 Blink_low; // rcx
  _DWORD *v22; // r12
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r9
  ULONG FilterMatch; // ebx
  char v28; // al
  char v29; // [rsp+50h] [rbp-78h]
  __int16 v30; // [rsp+54h] [rbp-74h] BYREF
  __int16 v31; // [rsp+58h] [rbp-70h]
  __int64 v32; // [rsp+60h] [rbp-68h] BYREF
  PVOID Bcb; // [rsp+68h] [rbp-60h] BYREF
  int v34; // [rsp+70h] [rbp-58h]
  unsigned int v35; // [rsp+74h] [rbp-54h]
  __int64 v36; // [rsp+78h] [rbp-50h]
  __int64 v37; // [rsp+80h] [rbp-48h]
  __int64 Ccb; // [rsp+88h] [rbp-40h]

  *(_OWORD *)a1 = 0;
  v32 = 0;
  v30 = 0;
  v29 = 0;
  v14 = 0;
  v35 = 0;
  v36 = 0;
  v31 = 0;
  Bcb = 0;
  if ( a10 && a7 )
  {
    *(_DWORD *)a1 = -1073741790;
  }
  else
  {
    if ( MmCanFileBeTruncated(*(PSECTION_OBJECT_POINTERS *)(a4 + 120), &FatLargeZero) )
    {
      Ccb = FatCreateCcb(v17, v16);
      v36 = Ccb;
      FatSetFileObject(a3, v18, a4, Ccb);
      a3->SectionObjectPointer = *(PSECTION_OBJECT_POINTERS *)(a4 + 120);
      v19 = (struct _LIST_ENTRY **)(a4 + 184);
      v37 = a4 + 184;
      _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)(a4 + 184) + 200LL), 0x200u);
      CcPurgeCacheSection(*(PSECTION_OBJECT_POINTERS *)(a4 + 120), 0, 0, 0);
      if ( a7 )
      {
        FatCreateEa(a2, (int)*v19, a4 + 480, (__int64)&v30);
        v31 = v30;
        v29 = 1;
        v14 = v35;
      }
      v20 = FsRtlCheckOplockEx((POPLOCK)(*(_QWORD *)(a4 + 176) + 88LL), *(PIRP *)(a2 + 40), 0x10u, 0, 0, 0);
      *(_DWORD *)a1 = v20;
      if ( v20 )
      {
        *(_DWORD *)(a2 + 72) = v20;
        ExRaiseStatus(v20);
      }
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a4 + 16), 1u);
      *(_DWORD *)(a4 + 32) = 0;
      *(_DWORD *)(a4 + 40) = 0;
      *(_DWORD *)(a4 + 280) = 0;
      Blink_low = LODWORD((*v19)[12].Blink);
      v22 = (_DWORD *)(a4 + 192);
      if ( (Blink_low & 0x400000) != 0 && (*v22 & 0x8000) != 0 )
        v14 = *(_DWORD *)(a4 + 132);
      if ( !(unsigned __int8)FatIsIoRangeValid(Blink_low, a5, 0, v14) )
      {
        *(_DWORD *)(a2 + 72) = -1073741697;
        ExRaiseStatus(-1073741697);
      }
      CcSetFileSizes(a3, (PCC_FILE_SIZES)(a4 + 24));
      FatTruncateFileAllocation(a2, a4, a5 + v14);
      ExReleaseResourceLite(*(PERESOURCE *)(a4 + 16));
      FatAddFileAllocation(a2);
      *v22 |= 2u;
      FatGetDirentFromFcbOrDcb(a2, a4, 0, (unsigned int)&v32, (__int64)&Bcb);
      *(_DWORD *)(v32 + 28) = 0;
      if ( ((__int64)(*v19)[12].Blink & 0x400000) != 0 && (*v22 & 0x8000) != 0 )
      {
        v24 = v32;
        *(_BYTE *)(a4 + 136) = ((*(_BYTE *)(v32 + 28) + 15) & 0xF0) - *(_BYTE *)(v32 + 28);
        *(_DWORD *)(v24 + 28) = (*(_DWORD *)(v24 + 28) + 15) & 0xFFFFFFF0;
        *(_DWORD *)(v32 + 28) += *(_DWORD *)(a4 + 132);
        *(_BYTE *)(v32 + 12) = *(_BYTE *)(v32 + 12) & 0x1B
                             | (4 * (*(_BYTE *)(a4 + 136) & 1 | (4 * (*(_BYTE *)(a4 + 136) & 0xFE))));
      }
      v25 = a8;
      LOWORD(v25) = a8 | 0x20;
      if ( a9 )
        *(_BYTE *)(v32 + 11) |= v25;
      else
        *(_BYTE *)(v32 + 11) = v25;
      LOBYTE(v25) = *(_BYTE *)(v32 + 11);
      *(_BYTE *)(a4 + 546) = v25;
      *(_QWORD *)(a4 + 272) = MEMORY[0xFFFFF78000000014];
      LOBYTE(v23) = 1;
      FatNtTimeToFatTime(v25, a4 + 272, v23, v32 + 22, 0);
      if ( (byte_140017D4C & 1) != 0 )
        *(_WORD *)(v32 + 18) = *(_WORD *)(v32 + 24);
      FilterMatch = 28;
      v34 = 28;
      if ( LOBYTE((*v19)[23].Blink) == 32 || !*(_WORD *)(v32 + 20) )
      {
        v28 = v29;
      }
      else
      {
        FatDeleteEa(a2);
        v28 = 1;
      }
      if ( v28 )
      {
        *(_WORD *)(v32 + 20) = v30;
        FilterMatch = 156;
        v34 = 156;
      }
      LOBYTE(v26) = 1;
      FatSetDirtyBcb(a2, Bcb, *v19, v26);
      v31 = 0;
      *(_DWORD *)(Ccb + 64) += *(_DWORD *)(a4 + 464);
      if ( !*(_QWORD *)(a4 + 536) )
        FatSetFullFileNameInFcb(a2);
      FsRtlNotifyFullReportChange(
        (PNOTIFY_SYNC)(*v19)[51].Flink,
        *v19 + 50,
        (PSTRING)(a4 + 528),
        *(_WORD *)(a4 + 528) - *(_WORD *)(a4 + 544),
        0,
        0,
        FilterMatch,
        3u,
        0);
      *(_DWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = a9 != 0 ? 3 : 0;
    }
    else
    {
      *(_DWORD *)a1 = -1073741245;
    }
    if ( Bcb )
    {
      CcUnpinData(Bcb);
      Bcb = 0;
    }
    _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(a4 + 184) + 200LL), 0xFFFFFDFF);
  }
  return a1;
}

```

## disassembly

```asm
0x14002cbe4  mov     rax, rsp
0x14002cbe7  mov     [rax+20h], r9
0x14002cbeb  mov     [rax+18h], r8
0x14002cbef  mov     [rax+10h], rdx
0x14002cbf3  mov     [rax+8], rcx
0x14002cbf7  push    rbx
0x14002cbf8  push    rsi
0x14002cbf9  push    rdi
0x14002cbfa  push    r12
0x14002cbfc  push    r13
0x14002cbfe  push    r14
0x14002cc00  push    r15
0x14002cc02  sub     rsp, 90h
0x14002cc09  mov     rsi, r9
0x14002cc0c  mov     r13, r8
0x14002cc0f  mov     r14, rdx
0x14002cc12  mov     r15, rcx
0x14002cc15  xorps   xmm0, xmm0
0x14002cc18  movups  xmmword ptr [rcx], xmm0
0x14002cc1b  xor     edi, edi
0x14002cc1d  mov     [rax-68h], rdi
0x14002cc21  mov     [rax-74h], di
0x14002cc25  mov     [rax-78h], dil
0x14002cc29  mov     [rax-77h], dil
0x14002cc2d  mov     ebx, edi
0x14002cc2f  mov     [rax-54h], ebx
0x14002cc32  mov     [rax-50h], rdi
0x14002cc36  mov     [rax-70h], di
0x14002cc3a  mov     [rax-60h], rdi
0x14002cc3e  cmp     [rsp+0C8h+arg_48], dil
0x14002cc46  jz      short loc_14002CC6E
0x14002cc48  cmp     [rsp+0C8h+arg_30], edi
0x14002cc4f  jbe     short loc_14002CC6E
0x14002cc51  mov     dword ptr [rcx], 0C0000022h
0x14002cc57  mov     rax, r15
0x14002cc5a  add     rsp, 90h
0x14002cc61  pop     r15
0x14002cc63  pop     r14
0x14002cc65  pop     r13
0x14002cc67  pop     r12
0x14002cc69  pop     rdi
0x14002cc6a  pop     rsi
0x14002cc6b  pop     rbx
0x14002cc6c  retn
0x14002cc6e  lea     rdx, FatLargeZero; NewFileSize
0x14002cc75  mov     rcx, [r9+78h]; SectionPointer
0x14002cc79  call    cs:__imp_MmCanFileBeTruncated
0x14002cc80  nop     dword ptr [rax+rax+00h]
0x14002cc85  test    al, al
0x14002cc87  jnz     short loc_14002CC95
0x14002cc89  mov     dword ptr [r15], 0C0000243h
0x14002cc90  jmp     loc_14002D09A
0x14002cc95  call    FatCreateCcb
0x14002cc9a  mov     [rsp+0C8h+var_40], rax
0x14002cca2  mov     [rsp+0C8h+var_50], rax
0x14002cca7  mov     r9, rax
0x14002ccaa  mov     r8, rsi
0x14002ccad  mov     rcx, r13
0x14002ccb0  call    FatSetFileObject
0x14002ccb5  mov     r8, [rsi+78h]
0x14002ccb9  mov     [r13+28h], r8
0x14002ccbd  lea     r13, [rsi+0B8h]
0x14002ccc4  mov     [rsp+0C8h+var_48], r13
0x14002cccc  mov     rcx, [r13+0]
0x14002ccd0  lock or dword ptr [rcx+0C8h], 200h
0x14002ccdb  xor     r9d, r9d; Flags
0x14002ccde  xor     r8d, r8d; Length
0x14002cce1  xor     edx, edx; FileOffset
0x14002cce3  mov     rcx, [rsi+78h]; SectionObjectPointer
0x14002cce7  call    cs:__imp_CcPurgeCacheSection
0x14002ccee  nop     dword ptr [rax+rax+00h]
0x14002ccf3  mov     r9d, [rsp+0C8h+arg_30]
0x14002ccfb  test    r9d, r9d
0x14002ccfe  jz      short loc_14002CD42
0x14002cd00  lea     rax, [rsi+1E0h]
0x14002cd07  lea     rcx, [rsp+0C8h+var_74]
0x14002cd0c  mov     [rsp+0C8h+PostIrpRoutine], rcx; __int64
0x14002cd11  mov     [rsp+0C8h+CompletionRoutine], rax; __int64
0x14002cd16  mov     r8, [rsp+0C8h+arg_28]
0x14002cd1e  mov     rdx, [r13+0]; int
0x14002cd22  mov     rcx, r14; int
0x14002cd25  call    FatCreateEa
0x14002cd2a  movzx   eax, word ptr [rsp+0C8h+var_74]
0x14002cd2f  mov     word ptr [rsp+0C8h+var_74+4], ax
0x14002cd34  mov     bl, 1
0x14002cd36  mov     [rsp+0C8h+var_78], bl
0x14002cd3a  mov     [rsp+0C8h+var_76], bl
0x14002cd3e  mov     ebx, [rsp+0C8h+var_54]
0x14002cd42  mov     rcx, [rsi+0B0h]
0x14002cd49  add     rcx, 58h ; 'X'; Oplock
0x14002cd4d  mov     [rsp+0C8h+PostIrpRoutine], rdi; PostIrpRoutine
0x14002cd52  mov     [rsp+0C8h+CompletionRoutine], rdi; CompletionRoutine
0x14002cd57  xor     r9d, r9d; Context
0x14002cd5a  lea     r8d, [r9+10h]; Flags
0x14002cd5e  mov     rdx, [r14+28h]; Irp
0x14002cd62  call    cs:__imp_FsRtlCheckOplockEx
0x14002cd69  nop     dword ptr [rax+rax+00h]
0x14002cd6e  mov     [r15], eax
0x14002cd71  test    eax, eax
0x14002cd73  jz      short loc_14002CD87
0x14002cd75  mov     [r14+48h], eax
0x14002cd79  mov     ecx, eax; Status
0x14002cd7b  call    cs:__imp_ExRaiseStatus
0x14002cd87  mov     dl, 1; Wait
0x14002cd89  mov     rcx, [rsi+10h]; Resource
0x14002cd8d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002cd94  nop     dword ptr [rax+rax+00h]
0x14002cd99  mov     [rsp+0C8h+var_77], 1
0x14002cd9e  mov     [rsi+20h], edi
0x14002cda1  mov     [rsi+28h], edi
0x14002cda4  mov     [rsi+118h], edi
0x14002cdaa  mov     rax, [r13+0]
0x14002cdae  mov     ecx, [rax+0C8h]
0x14002cdb4  lea     r12, [rsi+0C0h]
0x14002cdbb  bt      ecx, 16h
0x14002cdbf  jnb     short loc_14002CDD1
0x14002cdc1  test    dword ptr [r12], 8000h
0x14002cdc9  jz      short loc_14002CDD1
0x14002cdcb  mov     ebx, [rsi+84h]
0x14002cdd1  mov     edx, [rsp+0C8h+arg_20]
0x14002cdd8  mov     r9d, ebx
0x14002cddb  xor     r8d, r8d
0x14002cdde  call    FatIsIoRangeValid
0x14002cde3  test    al, al
0x14002cde5  jnz     short loc_14002CDFC
0x14002cde7  mov     ecx, 0C000007Fh; Status
0x14002cdec  mov     [r14+48h], ecx
0x14002cdf0  call    cs:__imp_ExRaiseStatus
0x14002cdfc  lea     rdx, [rsi+18h]; FileSizes
0x14002ce00  mov     rcx, [rsp+0C8h+FileObject]; FileObject
0x14002ce08  call    cs:__imp_CcSetFileSizes
0x14002ce0f  nop     dword ptr [rax+rax+00h]
0x14002ce14  add     ebx, [rsp+0C8h+arg_20]
0x14002ce1b  mov     r8d, ebx
0x14002ce1e  mov     rdx, rsi
0x14002ce21  mov     rcx, r14
0x14002ce24  call    FatTruncateFileAllocation
0x14002ce29  mov     rcx, [rsi+10h]; Resource
0x14002ce2d  call    cs:__imp_ExReleaseResourceLite
0x14002ce34  nop     dword ptr [rax+rax+00h]
0x14002ce39  mov     [rsp+0C8h+var_77], dil
0x14002ce3e  mov     r9d, ebx
0x14002ce41  mov     r8, [rsp+0C8h+FileObject]
0x14002ce49  mov     rdx, rsi
0x14002ce4c  mov     rcx, r14
0x14002ce4f  call    FatAddFileAllocation
0x14002ce54  or      dword ptr [r12], 2
0x14002ce59  lea     rax, [rsp+0C8h+Bcb]
0x14002ce5e  mov     [rsp+0C8h+CompletionRoutine], rax
0x14002ce63  lea     r9, [rsp+0C8h+var_68]
0x14002ce68  xor     r8d, r8d
0x14002ce6b  mov     rdx, rsi
0x14002ce6e  mov     rcx, r14
0x14002ce71  call    FatGetDirentFromFcbOrDcb
0x14002ce76  mov     rax, [rsp+0C8h+var_68]
0x14002ce7b  mov     [rax+1Ch], edi
0x14002ce7e  mov     rax, [r13+0]
0x14002ce82  mov     ecx, [rax+0C8h]
0x14002ce88  bt      ecx, 16h
0x14002ce8c  jnb     short loc_14002CEEB
0x14002ce8e  test    dword ptr [r12], 8000h
0x14002ce96  jz      short loc_14002CEEB
0x14002ce98  mov     rdx, [rsp+0C8h+var_68]
0x14002ce9d  mov     cl, [rdx+1Ch]
0x14002cea0  lea     eax, [rcx+0Fh]
0x14002cea3  and     al, 0F0h
0x14002cea5  sub     al, cl
0x14002cea7  mov     [rsi+88h], al
0x14002cead  mov     eax, [rdx+1Ch]
0x14002ceb0  add     eax, 0Fh
0x14002ceb3  and     eax, 0FFFFFFF0h
0x14002ceb6  mov     [rdx+1Ch], eax
0x14002ceb9  mov     rcx, [rsp+0C8h+var_68]
0x14002cebe  mov     eax, [rsi+84h]
0x14002cec4  add     [rcx+1Ch], eax
0x14002cec7  mov     al, [rsi+88h]
0x14002cecd  mov     rdx, [rsp+0C8h+var_68]
0x14002ced2  mov     cl, al
0x14002ced4  and     cl, 0FEh
0x14002ced7  shl     cl, 2
0x14002ceda  and     al, 1
0x14002cedc  or      cl, al
0x14002cede  shl     cl, 2
0x14002cee1  mov     al, [rdx+0Ch]
0x14002cee4  and     al, 1Bh
0x14002cee6  or      cl, al
0x14002cee8  mov     [rdx+0Ch], cl
0x14002ceeb  movzx   ecx, [rsp+0C8h+arg_38]
0x14002cef3  or      cx, 20h
0x14002cef7  mov     [rsp+0C8h+arg_38], cx
0x14002ceff  mov     r12d, [rsp+0C8h+arg_40]
0x14002cf07  mov     rax, [rsp+0C8h+var_68]
0x14002cf0c  test    r12d, r12d
0x14002cf0f  jnz     short loc_14002CF16
0x14002cf11  mov     [rax+0Bh], cl
0x14002cf14  jmp     short loc_14002CF19
0x14002cf16  or      [rax+0Bh], cl
0x14002cf19  mov     rax, [rsp+0C8h+var_68]
0x14002cf1e  mov     cl, [rax+0Bh]
0x14002cf21  mov     [rsi+222h], cl
0x14002cf27  lea     rdx, [rsi+110h]
0x14002cf2e  mov     rax, ds:0FFFFF78000000014h
0x14002cf38  mov     [rdx], rax
0x14002cf3b  mov     r9, [rsp+0C8h+var_68]
0x14002cf40  add     r9, 16h
0x14002cf44  mov     [rsp+0C8h+CompletionRoutine], rdi
0x14002cf49  mov     r8b, 1
0x14002cf4c  call    FatNtTimeToFatTime
0x14002cf51  test    cs:byte_140017D4C, 1
0x14002cf58  jz      short loc_14002CF67
0x14002cf5a  mov     rcx, [rsp+0C8h+var_68]
0x14002cf5f  movzx   eax, word ptr [rcx+18h]
0x14002cf63  mov     [rcx+12h], ax
0x14002cf67  mov     ebx, 1Ch
0x14002cf6c  mov     [rsp+0C8h+var_58], ebx
0x14002cf70  mov     rdx, [r13+0]
0x14002cf74  cmp     byte ptr [rdx+178h], 20h ; ' '
0x14002cf7b  jz      short loc_14002CFE1
0x14002cf7d  mov     rax, [rsp+0C8h+var_68]
0x14002cf82  movzx   r8d, word ptr [rax+14h]
0x14002cf87  test    r8w, r8w
0x14002cf8b  jz      short loc_14002CFE1
0x14002cf8d  mov     al, 1
0x14002cf8f  mov     [rsp+0C8h+var_78], al
0x14002cf93  mov     [rsp+0C8h+var_76], al
0x14002cf97  mov     rcx, r14
0x14002cf9a  call    FatDeleteEa
0x14002cf9f  mov     al, [rsp+0C8h+var_78]
0x14002cfa3  jmp     short loc_14002CFE5
0x14002cfa5  mov     r14, [rsp+0C8h+arg_8]
0x14002cfad  mov     dword ptr [r14+48h], 0
0x14002cfb5  xor     edi, edi
0x14002cfb7  mov     r12d, [rsp+0C8h+arg_40]
0x14002cfbf  mov     rsi, [rsp+0C8h+arg_18]
0x14002cfc7  mov     r15, [rsp+0C8h+arg_0]
0x14002cfcf  mov     al, [rsp+0C8h+var_76]
0x14002cfd3  mov     ebx, [rsp+0C8h+var_58]
0x14002cfd7  mov     r13, [rsp+0C8h+var_48]
0x14002cfdf  jmp     short loc_14002CFE5
0x14002cfe1  mov     al, [rsp+0C8h+var_78]
0x14002cfe5  test    al, al
0x14002cfe7  jz      short loc_14002D000
0x14002cfe9  movzx   ecx, word ptr [rsp+0C8h+var_74]
0x14002cfee  mov     rax, [rsp+0C8h+var_68]
0x14002cff3  mov     [rax+14h], cx
0x14002cff7  mov     ebx, 9Ch
0x14002cffc  mov     [rsp+0C8h+var_58], ebx
0x14002d000  mov     r9b, 1
0x14002d003  mov     r8, [r13+0]
0x14002d007  mov     rdx, [rsp+0C8h+Bcb]
0x14002d00c  mov     rcx, r14
0x14002d00f  call    FatSetDirtyBcb
0x14002d014  mov     word ptr [rsp+0C8h+var_74+4], di
0x14002d019  mov     eax, [rsi+1D0h]
0x14002d01f  mov     rcx, [rsp+0C8h+var_40]
0x14002d027  add     [rcx+40h], eax
0x14002d02a  cmp     [rsi+218h], rdi
0x14002d031  jnz     short loc_14002D03E
0x14002d033  mov     rdx, rsi
0x14002d036  mov     rcx, r14; int
0x14002d039  call    FatSetFullFileNameInFcb
0x14002d03e  lea     r8, [rsi+210h]; FullTargetName
0x14002d045  mov     rcx, [r13+0]
0x14002d049  movzx   r9d, word ptr [r8]
0x14002d04d  sub     r9w, [rsi+220h]; TargetNameOffset
0x14002d055  lea     rdx, [rcx+320h]; NotifyList
0x14002d05c  mov     [rsp+0C8h+TargetContext], rdi; TargetContext
0x14002d061  mov     [rsp+0C8h+Action], 3; Action
0x14002d069  mov     [rsp+0C8h+FilterMatch], ebx; FilterMatch
0x14002d06d  mov     [rsp+0C8h+PostIrpRoutine], rdi; NormalizedParentName
0x14002d072  mov     [rsp+0C8h+CompletionRoutine], rdi; StreamName
0x14002d077  mov     rcx, [rcx+330h]; NotifySync
0x14002d07e  call    cs:__imp_FsRtlNotifyFullReportChange
0x14002d085  nop     dword ptr [rax+rax+00h]
0x14002d08a  mov     [r15], edi
0x14002d08d  neg     r12d
0x14002d090  sbb     rax, rax
0x14002d093  and     eax, 3
0x14002d096  mov     [r15+8], rax
0x14002d09a  mov     rcx, [rsp+0C8h+Bcb]; Bcb
0x14002d09f  test    rcx, rcx
0x14002d0a2  jz      short loc_14002D0B5
0x14002d0a4  call    cs:__imp_CcUnpinData
0x14002d0ab  nop     dword ptr [rax+rax+00h]
0x14002d0b0  mov     [rsp+0C8h+Bcb], rdi
0x14002d0b5  mov     rax, [rsi+0B8h]
0x14002d0bc  lock and dword ptr [rax+0C8h], 0FFFFFDFFh
0x14002d0c7  jmp     loc_14002CC57
0x14005cbfe  push    rbx
0x14005cc00  push    rbp
0x14005cc01  sub     rsp, 58h
0x14005cc05  mov     rbp, rdx
0x14005cc08  mov     bl, cl
0x14005cc0a  cmp     byte ptr [rbp+51h], 0
0x14005cc0e  jz      short loc_14005CC28
0x14005cc10  mov     rcx, [rbp+0E8h]
0x14005cc17  mov     rcx, [rcx+10h]; Resource
0x14005cc1b  call    cs:__imp_ExReleaseResourceLite
0x14005cc22  nop     dword ptr [rax+rax+00h]
0x14005cc27  nop
  ... truncated ...
```
