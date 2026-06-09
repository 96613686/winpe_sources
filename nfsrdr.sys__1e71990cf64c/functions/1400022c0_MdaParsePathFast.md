# MdaParsePathFast

- ea: `0x1400022c0`
- end: `0x1400029bf`
- name: `MdaParsePathFast`
- size: `1791`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PUNICODE_STRING Destination, __int64, __int64)`
- caller_count: `5`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140018a7c`
- `0x14001bbbc`
- `0x14001c694`
- `0x140025be0`
- `0x1400316d0`

## callees

- `0x1400022c0`
- `0x1400029d0`
- `0x140003380`
- `0x140003510`
- `0x140005c90`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400173f8`
- `0x140035384`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400028ce`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400028ea`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400028ce`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400028ea`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400024a0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400024a0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002362`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400024ca`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400026ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002362`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400024ca`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400026ac`
- `ntoskrnl!KeReleaseMutex` at `0x14000253e`
- `ntoskrnl!KeReleaseMutex` at `0x14000254f`
- `ntoskrnl!KeReleaseMutex` at `0x140002562`
- `ntoskrnl!KeReleaseMutex` at `0x14000272e`
- `ntoskrnl!KeReleaseMutex` at `0x140002797`
- `ntoskrnl!KeReleaseMutex` at `0x14000253e`
- `ntoskrnl!KeReleaseMutex` at `0x14000254f`
- `ntoskrnl!KeReleaseMutex` at `0x140002562`
- `ntoskrnl!KeReleaseMutex` at `0x14000272e`
- `ntoskrnl!KeReleaseMutex` at `0x140002797`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002888`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002888`
- `ntoskrnl!ExAllocatePool2` at `0x1400027e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400027e2`

## pseudocode

```c
__int64 __fastcall MdaParsePathFast(
        __int64 a1,
        struct _MRX_FCB_ *a2,
        UNICODE_STRING *a3,
        char a4,
        __int64 *a5,
        PUNICODE_STRING Destination,
        _BYTE *a7,
        __int64 *a8)
{
  PVOID *FileContextSupportPointer; // rax
  __int64 v11; // rsi
  __int64 v12; // rax
  struct _KMUTANT *v13; // r14
  unsigned int Lock; // ebx
  unsigned int i; // edi
  unsigned int v16; // r8d
  __int64 j; // rbx
  __int64 *v18; // r12
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  struct _KMUTANT *v22; // rcx
  __int64 v23; // rbx
  int Attributes; // edi
  unsigned __int16 v26; // cx
  unsigned __int16 v27; // dx
  char v28; // al
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rcx
  struct _KMUTANT *v32; // rcx
  unsigned __int16 v33; // cx
  unsigned __int16 v34; // dx
  __int64 v35; // rdi
  USHORT v36; // r14
  WCHAR *Pool2; // rax
  BOOLEAN v38; // r9
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  int v41[2]; // [rsp+50h] [rbp-39h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-31h] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-21h] BYREF
  PVOID *v45; // [rsp+D8h] [rbp+4Fh]

  FileContextSupportPointer = a2->Header.FileContextSupportPointer;
  *(_QWORD *)v41 = 0;
  v45 = FileContextSupportPointer;
  String2 = 0;
  v11 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  v12 = *(_QWORD *)(v11 + 32);
  String2 = *a3;
  String2.Length = 0;
  v13 = *(struct _KMUTANT **)(*(_QWORD *)(v12 + 40) + 72LL);
  KeWaitForSingleObject(v13, Executive, 0, 0, 0);
  Lock = v13[1].Header.Lock;
  if ( !dword_1400411C4 || dword_1400411C4 > Lock )
  {
    for ( i = 15; i; --i )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids,
          i,
          *((_DWORD *)PowerOf2Primes + i));
      }
      v16 = *((_DWORD *)PowerOf2Primes + i);
      if ( v16 < Lock )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
        {
          WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids, Lock, v16);
        }
        dword_1400411C4 = *((_DWORD *)PowerOf2Primes + i);
        break;
      }
    }
    v11 = a1;
  }
  for ( j = (__int64)v13[2].Header.WaitListHead.Flink->Flink; j; j = *(_QWORD *)j )
  {
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(j + 64), &String2, 0) )
    {
      v18 = a5;
      KeWaitForSingleObject(*(PVOID *)(j + 40), Executive, 0, 0, 0);
      v19 = *(_QWORD *)(j + 40);
      if ( *(_QWORD *)(v19 + 88) )
      {
        if ( *(_QWORD *)(v19 + 96) != j )
        {
          v20 = *(_QWORD *)(j + 16);
          if ( v20 )
          {
            v21 = *(_QWORD *)(j + 24);
            if ( v21 )
            {
              *(_QWORD *)(v21 + 16) = v20;
              *(_QWORD *)(*(_QWORD *)(j + 16) + 24LL) = *(_QWORD *)(j + 24);
            }
            else
            {
              *(_QWORD *)(v19 + 88) = v20;
              *(_QWORD *)(*(_QWORD *)(j + 16) + 24LL) = 0;
            }
          }
          *(_QWORD *)(*(_QWORD *)(v19 + 96) + 16LL) = j;
          *(_QWORD *)(j + 24) = *(_QWORD *)(v19 + 96);
          *(_QWORD *)(j + 16) = 0;
LABEL_30:
          *(_QWORD *)(v19 + 96) = j;
        }
        v22 = *(struct _KMUTANT **)(j + 40);
        ++*(_DWORD *)(j + 52);
        KeReleaseMutex(v22, 0);
        KeReleaseMutex(v13, 0);
        goto LABEL_33;
      }
      *(_QWORD *)(v19 + 88) = j;
      goto LABEL_30;
    }
  }
  KeReleaseMutex(v13, 0);
  v18 = a5;
  *a5 = 0;
  v23 = *(_QWORD *)(*(_QWORD *)(v11 + 32) + 40LL);
  HacReference(*(_QWORD *)(v23 + 40));
  j = *(_QWORD *)(v23 + 40);
LABEL_33:
  *v18 = j;
  Attributes = NfsGetAttributes(v11, a2, j);
  if ( Attributes >= 0 )
  {
    v26 = String2.Length >> 1;
    v27 = a3->Length >> 1;
    if ( (unsigned __int16)(String2.Length >> 1) >= v27 )
      goto LABEL_43;
    do
    {
      if ( String2.Buffer[v26] != 92 )
        break;
      ++v26;
    }
    while ( v26 < v27 );
    if ( v26 < v27 )
    {
      do
      {
        if ( String2.Buffer[v26] == 92 )
          break;
        ++v26;
      }
      while ( v26 < v27 );
      String2.Length = 2 * v26;
      v28 = 0;
    }
    else
    {
LABEL_43:
      v28 = 1;
    }
    while ( 1 )
    {
      if ( v28 )
        return (unsigned int)Attributes;
      Attributes = CaseInsensitiveLookup(v11, (_DWORD)a2, (unsigned int)&String2, j, a4, (__int64)v41);
      if ( Attributes < 0 )
        goto LABEL_37;
      HacDereference(v45, j);
      j = *(_QWORD *)v41;
      *v18 = *(_QWORD *)v41;
      KeWaitForSingleObject(*(PVOID *)(j + 40), Executive, 0, 0, 0);
      v29 = *(_QWORD *)(j + 40);
      if ( *(_QWORD *)(v29 + 88) )
      {
        if ( *(_QWORD *)(v29 + 96) == j )
          goto LABEL_58;
        v30 = *(_QWORD *)(j + 16);
        if ( v30 )
        {
          v31 = *(_QWORD *)(j + 24);
          if ( v31 )
          {
            *(_QWORD *)(v31 + 16) = v30;
            *(_QWORD *)(*(_QWORD *)(j + 16) + 24LL) = *(_QWORD *)(j + 24);
          }
          else
          {
            *(_QWORD *)(v29 + 88) = v30;
            *(_QWORD *)(*(_QWORD *)(j + 16) + 24LL) = 0;
          }
        }
        *(_QWORD *)(*(_QWORD *)(v29 + 96) + 16LL) = j;
        *(_QWORD *)(j + 24) = *(_QWORD *)(v29 + 96);
        *(_QWORD *)(j + 16) = 0;
      }
      else
      {
        *(_QWORD *)(v29 + 88) = j;
      }
      *(_QWORD *)(v29 + 96) = j;
LABEL_58:
      v32 = *(struct _KMUTANT **)(j + 40);
      if ( *(_DWORD *)(j + 128) == 5 )
      {
        v35 = *(_QWORD *)(v11 + 40);
        KeReleaseMutex(v32, 0);
        if ( (*(_DWORD *)(v35 + 32) & 0x200) != 0 )
        {
          v36 = a3->Length - String2.Length + 530;
          Destination->Length = 0;
          Pool2 = (WCHAR *)ExAllocatePool2(258, v36, 827483726);
          Destination->Buffer = Pool2;
          if ( Pool2 )
          {
            if ( (*(_DWORD *)(v35 + 32) & 0x100000) != 0 || (v38 = 1, !a4) )
              v38 = 0;
            Destination->MaximumLength = v36;
            Attributes = MdaResolveSymbolicLink(a1, a2, j, v38, Destination, 0, a8, 0, (__int64)a7);
            if ( Attributes < 0 )
            {
              v39 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                v40 = 12;
                goto LABEL_76;
              }
              goto LABEL_77;
            }
            Source = 0;
            Source.MaximumLength = a3->Length - String2.Length;
            Source.Length = Source.MaximumLength;
            Source.Buffer = &String2.Buffer[(unsigned __int64)String2.Length >> 1];
            Attributes = RtlAppendUnicodeStringToString(Destination, &Source);
            if ( Attributes < 0 || (Attributes = RtlAppendUnicodeStringToString(Destination, &Slash), Attributes < 0) )
            {
              v39 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                v40 = 13;
LABEL_76:
                WPP_SF_d(
                  v39->AttachedDevice,
                  v40,
                  WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                  (unsigned int)Attributes);
              }
LABEL_77:
              ExFreePoolWithTag(Destination->Buffer, 0);
            }
            else
            {
              Attributes = 260;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            Attributes = -1073741670;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          Attributes = -1073741766;
        }
        HacDereference(v45, j);
        if ( !*a7 )
          *v18 = 0;
        return (unsigned int)Attributes;
      }
      KeReleaseMutex(v32, 0);
      Attributes = 0;
      v33 = String2.Length >> 1;
      v34 = a3->Length >> 1;
      if ( (unsigned __int16)(String2.Length >> 1) >= v34 )
        goto LABEL_63;
      do
      {
        if ( String2.Buffer[v33] != 92 )
          break;
        ++v33;
      }
      while ( v33 < v34 );
      if ( v33 < v34 )
      {
        do
        {
          if ( String2.Buffer[v33] == 92 )
            break;
          ++v33;
        }
        while ( v33 < v34 );
        String2.Length = 2 * v33;
        v28 = 0;
      }
      else
      {
LABEL_63:
        v28 = 1;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
      (unsigned int)Attributes);
LABEL_37:
  HacDereference(v45, j);
  return (unsigned int)Attributes;
}

```

## disassembly

```asm
0x1400022c0  mov     [rsp-8+arg_18], r9b
0x1400022c5  mov     [rsp-8+arg_10], r8
0x1400022ca  mov     qword ptr [rsp-8+arg_0], rcx
0x1400022cf  push    rbp
0x1400022d0  push    rbx
0x1400022d1  push    rsi
0x1400022d2  push    rdi
0x1400022d3  push    r13
0x1400022d5  push    r14
0x1400022d7  push    r15
0x1400022d9  lea     rbp, [rsp-7]
0x1400022de  sub     rsp, 90h
0x1400022e5  mov     rax, [rdx+50h]
0x1400022e9  xor     edi, edi
0x1400022eb  xorps   xmm0, xmm0
0x1400022ee  mov     qword ptr [rbp+37h+var_70], rdi
0x1400022f2  mov     [rbp+37h+arg_8], rax
0x1400022f6  mov     r15, r8
0x1400022f9  movups  xmmword ptr [rbp+37h+String2.Length], xmm0
0x1400022fd  mov     r13, rdx
0x140002300  mov     rsi, rcx
0x140002303  mov     rcx, cs:WPP_GLOBAL_Control
0x14000230a  lea     rax, WPP_GLOBAL_Control
0x140002311  cmp     rcx, rax
0x140002314  jz      short loc_140002332
0x140002316  mov     eax, [rcx+2Ch]
0x140002319  test    al, 8
0x14000231b  jz      short loc_140002332
0x14000231d  mov     rcx, [rcx+18h]
0x140002321  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140002328  mov     edx, 0Ah
0x14000232d  call    WPP_SF_
0x140002332  movups  xmm0, xmmword ptr [r15]
0x140002336  mov     rax, [rsi+20h]
0x14000233a  xor     r9d, r9d; Alertable
0x14000233d  xor     r8d, r8d; WaitMode
0x140002340  mov     [rsp+0C0h+var_38], r12
0x140002348  movups  xmmword ptr [rbp+37h+String2.Length], xmm0
0x14000234c  mov     [rbp+37h+String2.Length], di
0x140002350  xor     edx, edx; WaitReason
0x140002352  mov     rcx, [rax+28h]
0x140002356  mov     [rsp+0C0h+Timeout], rdi; Timeout
0x14000235b  mov     r14, [rcx+48h]
0x14000235f  mov     rcx, r14; Object
0x140002362  call    cs:__imp_KeWaitForSingleObject
0x140002369  nop     dword ptr [rax+rax+00h]
0x14000236e  mov     r10d, cs:dword_1400411C4
0x140002375  mov     ebx, [r14+38h]
0x140002379  test    r10d, r10d
0x14000237c  jz      short loc_140002387
0x14000237e  cmp     r10d, ebx
0x140002381  jbe     loc_14000243E
0x140002387  mov     edi, 0Fh
0x14000238c  lea     r12, PowerOf2Primes
0x140002393  lea     rdx, WPP_GLOBAL_Control
0x14000239a  test    edi, edi
0x14000239c  jz      loc_140002431
0x1400023a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023a9  cmp     rcx, rdx
0x1400023ac  jz      short loc_1400023E0
0x1400023ae  test    dword ptr [rcx+2Ch], 800h
0x1400023b5  jz      short loc_1400023E0
0x1400023b7  mov     rcx, [rcx+18h]
0x1400023bb  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x1400023c2  mov     eax, edi
0x1400023c4  mov     edx, 0Ah
0x1400023c9  mov     r9d, edi
0x1400023cc  mov     eax, [r12+rax*4]
0x1400023d0  mov     dword ptr [rsp+0C0h+Timeout], eax
0x1400023d4  call    WPP_SF_dd
0x1400023d9  lea     rdx, WPP_GLOBAL_Control
0x1400023e0  mov     eax, edi
0x1400023e2  mov     r8d, [r12+rax*4]
0x1400023e6  lea     rsi, [r12+rax*4]
0x1400023ea  cmp     r8d, ebx
0x1400023ed  jb      short loc_1400023F3
0x1400023ef  dec     edi
0x1400023f1  jmp     short loc_14000239A
0x1400023f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023fa  cmp     rcx, rdx
0x1400023fd  jz      short loc_140002425
0x1400023ff  test    dword ptr [rcx+2Ch], 800h
0x140002406  jz      short loc_140002425
0x140002408  mov     rcx, [rcx+18h]
0x14000240c  mov     edx, 0Bh
0x140002411  mov     dword ptr [rsp+0C0h+Timeout], r8d
0x140002416  mov     r9d, ebx
0x140002419  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140002420  call    WPP_SF_dd
0x140002425  mov     r10d, [rsi]
0x140002428  mov     cs:dword_1400411C4, r10d
0x14000242f  jmp     short loc_140002438
0x140002431  mov     r10d, cs:dword_1400411C4
0x140002438  mov     rsi, qword ptr [rbp+37h+arg_0]
0x14000243c  xor     edi, edi
0x14000243e  movzx   ecx, [rbp+37h+String2.Length]
0x140002442  test    cx, cx
0x140002445  jz      short loc_140002480
0x140002447  mov     rdx, [rbp+37h+String2.Buffer]
0x14000244b  mov     r9d, ecx
0x14000244e  shr     r9d, 1
0x140002451  mov     eax, edi
0x140002453  mov     r8d, edi
0x140002456  jz      short loc_140002474
0x140002458  nop     dword ptr [rax+rax+00000000h]
0x140002460  movzx   ecx, word ptr [rdx]
0x140002463  lea     rdx, [rdx+2]
0x140002467  xor     eax, ecx
0x140002469  inc     r8d
0x14000246c  ror     eax, 1Bh
0x14000246f  cmp     r8d, r9d
0x140002472  jb      short loc_140002460
0x140002474  test    r10d, r10d
0x140002477  jz      short loc_140002480
0x140002479  xor     edx, edx
0x14000247b  div     r10d
0x14000247e  jmp     short loc_140002482
0x140002480  mov     edx, edi
0x140002482  mov     rax, [r14+78h]
0x140002486  mov     ecx, edx
0x140002488  mov     rbx, [rax+rcx*8]
0x14000248c  test    rbx, rbx
0x14000248f  jz      loc_14000255D
0x140002495  lea     rcx, [rbx+40h]; String1
0x140002499  xor     r8d, r8d; CaseInSensitive
0x14000249c  lea     rdx, [rbp+37h+String2]; String2
0x1400024a0  call    cs:__imp_RtlCompareUnicodeString
0x1400024a7  nop     dword ptr [rax+rax+00h]
0x1400024ac  test    eax, eax
0x1400024ae  jz      short loc_1400024B5
0x1400024b0  mov     rbx, [rbx]
0x1400024b3  jmp     short loc_14000248C
0x1400024b5  mov     rcx, [rbx+28h]; Object
0x1400024b9  xor     r9d, r9d; Alertable
0x1400024bc  mov     r12, [rbp+37h+arg_20]
0x1400024c0  xor     r8d, r8d; WaitMode
0x1400024c3  xor     edx, edx; WaitReason
0x1400024c5  mov     [rsp+0C0h+Timeout], rdi; Timeout
0x1400024ca  call    cs:__imp_KeWaitForSingleObject
0x1400024d1  nop     dword ptr [rax+rax+00h]
0x1400024d6  mov     rdx, [rbx+28h]
0x1400024da  cmp     qword ptr [rdx+58h], 0
0x1400024df  jz      short loc_14000252D
0x1400024e1  cmp     [rdx+60h], rbx
0x1400024e5  jz      short loc_140002535
0x1400024e7  mov     rax, [rbx+10h]
0x1400024eb  test    rax, rax
0x1400024ee  jz      short loc_140002517
0x1400024f0  mov     rcx, [rbx+18h]
0x1400024f4  test    rcx, rcx
0x1400024f7  jz      short loc_14000250B
0x1400024f9  mov     [rcx+10h], rax
0x1400024fd  mov     rcx, [rbx+10h]
0x140002501  mov     rax, [rbx+18h]
0x140002505  mov     [rcx+18h], rax
0x140002509  jmp     short loc_140002517
0x14000250b  mov     [rdx+58h], rax
0x14000250f  mov     rax, [rbx+10h]
0x140002513  mov     [rax+18h], rdi
0x140002517  mov     rax, [rdx+60h]
0x14000251b  mov     [rax+10h], rbx
0x14000251f  mov     rax, [rdx+60h]
0x140002523  mov     [rbx+18h], rax
0x140002527  mov     [rbx+10h], rdi
0x14000252b  jmp     short loc_140002531
0x14000252d  mov     [rdx+58h], rbx
0x140002531  mov     [rdx+60h], rbx
0x140002535  mov     rcx, [rbx+28h]; Mutex
0x140002539  xor     edx, edx; Wait
0x14000253b  inc     dword ptr [rbx+34h]
0x14000253e  call    cs:__imp_KeReleaseMutex
0x140002545  nop     dword ptr [rax+rax+00h]
0x14000254a  xor     edx, edx; Wait
0x14000254c  mov     rcx, r14; Mutex
0x14000254f  call    cs:__imp_KeReleaseMutex
0x140002556  nop     dword ptr [rax+rax+00h]
0x14000255b  jmp     short loc_14000258B
0x14000255d  xor     edx, edx; Wait
0x14000255f  mov     rcx, r14; Mutex
0x140002562  call    cs:__imp_KeReleaseMutex
0x140002569  nop     dword ptr [rax+rax+00h]
0x14000256e  mov     r12, [rbp+37h+arg_20]
0x140002572  mov     [r12], rbx
0x140002576  mov     rax, [rsi+20h]
0x14000257a  mov     rbx, [rax+28h]
0x14000257e  mov     rcx, [rbx+28h]
0x140002582  call    HacReference
0x140002587  mov     rbx, [rbx+28h]
0x14000258b  mov     r8, rbx
0x14000258e  mov     [r12], rbx
0x140002592  mov     rdx, r13
0x140002595  mov     rcx, rsi
0x140002598  call    NfsGetAttributes
0x14000259d  mov     edi, eax
0x14000259f  test    eax, eax
0x1400025a1  jns     short loc_140002601
0x1400025a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025aa  lea     rax, WPP_GLOBAL_Control
0x1400025b1  cmp     rcx, rax
0x1400025b4  jz      short loc_1400025D8
0x1400025b6  mov     r9d, [rcx+2Ch]
0x1400025ba  test    r9b, 1
0x1400025be  jz      short loc_1400025D8
0x1400025c0  mov     rcx, [rcx+18h]
0x1400025c4  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400025cb  mov     edx, 0Bh
0x1400025d0  mov     r9d, edi
0x1400025d3  call    WPP_SF_d
0x1400025d8  mov     rcx, [rbp+37h+arg_8]
0x1400025dc  mov     rdx, rbx
0x1400025df  call    HacDereference
0x1400025e4  mov     r12, [rsp+0C0h+var_38]
0x1400025ec  mov     eax, edi
0x1400025ee  add     rsp, 90h
0x1400025f5  pop     r15
0x1400025f7  pop     r14
0x1400025f9  pop     r13
0x1400025fb  pop     rdi
0x1400025fc  pop     rsi
0x1400025fd  pop     rbx
0x1400025fe  pop     rbp
0x1400025ff  retn
0x140002601  movzx   ecx, [rbp+37h+String2.Length]
0x140002605  movzx   edx, word ptr [r15]
0x140002609  mov     r9, [rbp+37h+String2.Buffer]
0x14000260d  shr     cx, 1
0x140002610  shr     dx, 1
0x140002613  cmp     cx, dx
0x140002616  jnb     short loc_140002630
0x140002618  movzx   eax, cx
0x14000261b  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x140002621  jnz     short loc_14000262B
0x140002623  inc     cx
0x140002626  cmp     cx, dx
0x140002629  jb      short loc_140002618
0x14000262b  cmp     cx, dx
0x14000262e  jb      short loc_140002634
0x140002630  mov     al, 1
0x140002632  jmp     short loc_140002650
0x140002634  movzx   eax, cx
0x140002637  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14000263d  jz      short loc_140002647
0x14000263f  inc     cx
0x140002642  cmp     cx, dx
0x140002645  jb      short loc_140002634
0x140002647  add     cx, cx
0x14000264a  mov     [rbp+37h+String2.Length], cx
0x14000264e  xor     al, al
0x140002650  movzx   r14d, [rbp+37h+arg_18]
0x140002655  test    al, al
0x140002657  jnz     short loc_1400025E4
0x140002659  lea     rax, [rbp+37h+var_70]
0x14000265d  mov     r9, rbx
0x140002660  mov     [rsp+0C0h+var_98], rax
0x140002665  lea     r8, [rbp+37h+String2]
0x140002669  mov     rdx, r13
0x14000266c  mov     byte ptr [rsp+0C0h+Timeout], r14b
0x140002671  mov     rcx, rsi
0x140002674  call    CaseInsensitiveLookup
0x140002679  mov     edi, eax
0x14000267b  test    eax, eax
0x14000267d  js      loc_1400025D8
0x140002683  mov     rcx, [rbp+37h+arg_8]
0x140002687  mov     rdx, rbx
0x14000268a  call    HacDereference
0x14000268f  mov     rbx, qword ptr [rbp+37h+var_70]
0x140002693  xor     r9d, r9d; Alertable
0x140002696  mov     [r12], rbx
0x14000269a  xor     r8d, r8d; WaitMode
0x14000269d  xor     edx, edx; WaitReason
0x14000269f  mov     [rsp+0C0h+Timeout], 0; Timeout
0x1400026a8  mov     rcx, [rbx+28h]; Object
0x1400026ac  call    cs:__imp_KeWaitForSingleObject
0x1400026b3  nop     dword ptr [rax+rax+00h]
0x1400026b8  mov     rdx, [rbx+28h]
0x1400026bc  cmp     qword ptr [rdx+58h], 0
0x1400026c1  jz      short loc_140002717
0x1400026c3  cmp     [rdx+60h], rbx
0x1400026c7  jz      short loc_14000271F
0x1400026c9  mov     rax, [rbx+10h]
0x1400026cd  test    rax, rax
0x1400026d0  jz      short loc_1400026FD
0x1400026d2  mov     rcx, [rbx+18h]
0x1400026d6  test    rcx, rcx
0x1400026d9  jz      short loc_1400026ED
0x1400026db  mov     [rcx+10h], rax
0x1400026df  mov     rcx, [rbx+10h]
0x1400026e3  mov     rax, [rbx+18h]
0x1400026e7  mov     [rcx+18h], rax
0x1400026eb  jmp     short loc_1400026FD
0x1400026ed  mov     [rdx+58h], rax
0x1400026f1  mov     rax, [rbx+10h]
0x1400026f5  mov     qword ptr [rax+18h], 0
0x1400026fd  mov     rax, [rdx+60h]
0x140002701  mov     [rax+10h], rbx
0x140002705  mov     rax, [rdx+60h]
0x140002709  mov     [rbx+18h], rax
0x14000270d  mov     qword ptr [rbx+10h], 0
0x140002715  jmp     short loc_14000271B
0x140002717  mov     [rdx+58h], rbx
  ... truncated ...
```
