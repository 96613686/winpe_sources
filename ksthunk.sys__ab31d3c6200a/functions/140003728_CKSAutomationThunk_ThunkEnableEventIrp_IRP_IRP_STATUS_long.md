# CKSAutomationThunk::ThunkEnableEventIrp(_IRP *,_IRP_STATUS,long *)

- ea: `0x140003728`
- end: `0x140003d48`
- name: `?ThunkEnableEventIrp@CKSAutomationThunk@@IEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `1568`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400021e0`
- `0x140002c80`

## callees

- `0x1400010f4`
- `0x140002f5c`
- `0x140003728`
- `0x140004240`
- `0x140004540`
- `0x14000b008`
- `0x14000b06c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140003956`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140003956`
- `ntoskrnl!ProbeForRead` at `0x1400037db`
- `ntoskrnl!ProbeForRead` at `0x140003897`
- `ntoskrnl!ProbeForRead` at `0x140003b3a`
- `ntoskrnl!ProbeForRead` at `0x1400037db`
- `ntoskrnl!ProbeForRead` at `0x140003897`
- `ntoskrnl!ProbeForRead` at `0x140003b3a`
- `ntoskrnl!ProbeForWrite` at `0x1400038ad`
- `ntoskrnl!ProbeForWrite` at `0x1400038ad`
- `ntoskrnl!ExRaiseStatus` at `0x1400037bd`
- `ntoskrnl!ExRaiseStatus` at `0x140003848`
- `ntoskrnl!ExRaiseStatus` at `0x14000387c`
- `ntoskrnl!ExRaiseStatus` at `0x140003990`
- `ntoskrnl!ExRaiseStatus` at `0x140003ab7`
- `ntoskrnl!ExRaiseStatus` at `0x140003b72`
- `ntoskrnl!ExRaiseStatus` at `0x140003ca0`
- `ntoskrnl!ExRaiseStatus` at `0x1400037bd`
- `ntoskrnl!ExRaiseStatus` at `0x140003848`
- `ntoskrnl!ExRaiseStatus` at `0x14000387c`
- `ntoskrnl!ExRaiseStatus` at `0x140003990`
- `ntoskrnl!ExRaiseStatus` at `0x140003ab7`
- `ntoskrnl!ExRaiseStatus` at `0x140003b72`
- `ntoskrnl!ExRaiseStatus` at `0x140003ca0`
- `ntoskrnl!ExAllocatePool2` at `0x1400038c7`
- `ntoskrnl!ExAllocatePool2` at `0x140003af0`
- `ntoskrnl!ExAllocatePool2` at `0x1400038c7`
- `ntoskrnl!ExAllocatePool2` at `0x140003af0`
- `ntoskrnl!ExFreePool` at `0x140003a59`
- `ntoskrnl!ExFreePool` at `0x140003a91`
- `ntoskrnl!ExFreePool` at `0x140003cb9`
- `ntoskrnl!ExFreePool` at `0x140003ccf`
- `ntoskrnl!ExFreePool` at `0x140003cee`
- `ntoskrnl!ExFreePool` at `0x140003a59`
- `ntoskrnl!ExFreePool` at `0x140003a91`
- `ntoskrnl!ExFreePool` at `0x140003cb9`
- `ntoskrnl!ExFreePool` at `0x140003ccf`
- `ntoskrnl!ExFreePool` at `0x140003cee`
- `ks!KsSynchronousIoControlDevice` at `0x140003a36`
- `ks!KsSynchronousIoControlDevice` at `0x140003a36`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::ThunkEnableEventIrp(__int64 a1, __int64 a2, __int64 a3, int *a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rsi
  SIZE_T OutSize; // r15
  unsigned int v9; // r14d
  void *OutBuffer; // r12
  SIZE_T v11; // rax
  unsigned int v12; // r13d
  int IsEnabledDeviceUsageNoInline; // ecx
  __int64 v14; // rax
  int ULongFromUser; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // r13
  int v20; // eax
  void *v21; // rdx
  int v22; // eax
  __int128 *v23; // rcx
  _QWORD *PoolWithTag; // rax
  _QWORD *v25; // rsi
  int v26; // eax
  size_t v27; // r8
  __int64 v28; // r13
  void *v29; // rdx
  void *v30; // rcx
  NTSTATUS v31; // eax
  int *v32; // r13
  int v33; // eax
  void *v34; // rcx
  SIZE_T v35; // r12
  __int64 v36; // rsi
  __int64 v37; // rsi
  unsigned int v38; // edx
  __int64 v39; // rax
  char v40; // [rsp+40h] [rbp-A8h]
  ULONG BytesReturned; // [rsp+44h] [rbp-A4h] BYREF
  int v42; // [rsp+48h] [rbp-A0h]
  __int64 v43; // [rsp+50h] [rbp-98h]
  __int128 v44; // [rsp+58h] [rbp-90h] BYREF
  unsigned int v45; // [rsp+68h] [rbp-80h]
  int v46; // [rsp+6Ch] [rbp-7Ch]
  PVOID P; // [rsp+70h] [rbp-78h]
  PVOID v48; // [rsp+78h] [rbp-70h]
  size_t Size; // [rsp+80h] [rbp-68h]
  __int128 v50; // [rsp+88h] [rbp-60h] BYREF
  __int128 v51; // [rsp+98h] [rbp-50h]
  unsigned int NumberOfBytes; // [rsp+F0h] [rbp+8h]
  ULONG NumberOfBytesa; // [rsp+F0h] [rbp+8h]
  int v54; // [rsp+100h] [rbp+18h]

  v5 = 0;
  BytesReturned = 0;
  v6 = *(_QWORD *)(a2 + 184);
  v43 = v6;
  OutSize = *(unsigned int *)(v6 + 8);
  v46 = OutSize + 16;
  if ( (int)OutSize + 16 < (unsigned int)OutSize )
  {
    *a4 = -1073741811;
    return 0;
  }
  if ( *(_QWORD *)(a2 + 24) )
    return 1;
  v9 = 1;
  v42 = 1;
  v40 = 0;
  P = 0;
  OutBuffer = 0;
  v48 = 0;
  v11 = *(unsigned int *)(v6 + 16);
  NumberOfBytes = *(_DWORD *)(v6 + 16);
  v12 = (OutSize + 23) & 0xFFFFFFF8;
  if ( (unsigned int)v11 < 0x18 )
    ExRaiseStatus(-1073741306);
  Size = *(unsigned int *)(v6 + 16);
  ProbeForRead(*(volatile void **)(v6 + 32), v11, 1u);
  IsEnabledDeviceUsageNoInline = Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline();
  v14 = *(_QWORD *)(v6 + 32);
  if ( IsEnabledDeviceUsageNoInline )
    ULongFromUser = RtlReadULongFromUser(v14 + 20);
  else
    ULongFromUser = *(_DWORD *)(v14 + 20);
  v54 = ULongFromUser;
  v16 = (ULongFromUser & 0xEFFFFFFF) - 1;
  if ( !v16 || (v17 = v16 - 1) == 0 || (v18 = v17 - 2) == 0 )
  {
    if ( (unsigned int)OutSize < 0x10 )
      ExRaiseStatus(-1073741306);
    if ( v12 < (int)OutSize + 16 || v12 + NumberOfBytes < v12 )
      ExRaiseStatus(-1073741306);
    *(_QWORD *)(a2 + 24) = ExAllocatePool2(97, v12 + NumberOfBytes, 1886409547);
    *(_DWORD *)(a2 + 16) |= 0x30u;
    v44 = 0;
    if ( (unsigned int)Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline() )
    {
      RtlCopyFromUser(&v44, *(void **)(a2 + 112), 0x10u);
      v35 = OutSize;
    }
    else
    {
      v35 = OutSize;
      ProbeForRead(*(volatile void **)(a2 + 112), OutSize, 1u);
      v44 = *(_OWORD *)*(_QWORD *)(a2 + 112);
    }
    v36 = *(_QWORD *)(a2 + 24);
    *(_DWORD *)v36 = v44;
    if ( (_DWORD)v44 == 1 )
    {
      *(_QWORD *)(v36 + 8) = DWORD1(v44);
      v38 = 0;
      v45 = 0;
      while ( v38 < 2 )
      {
        *(_QWORD *)(v36 + 8LL * v38 + 16) = *((unsigned int *)&v44 + v38 + 2);
        v45 = ++v38;
      }
    }
    else
    {
      if ( (_DWORD)v44 != 2 )
        ExRaiseStatus(-1073741811);
      *(_QWORD *)(v36 + 8) = DWORD1(v44);
      *(_QWORD *)(v36 + 16) = *((_QWORD *)&v44 + 1);
    }
    if ( (unsigned int)Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( (unsigned int)OutSize > 0x10 )
        RtlCopyFromUser((void *)(v36 + 32), (void *)(*(_QWORD *)(a2 + 112) + 16LL), v35 - 16);
      v37 = v12;
      RtlCopyFromUser((void *)(v12 + *(_QWORD *)(a2 + 24)), *(void **)(v43 + 32), Size);
    }
    else
    {
      if ( (unsigned int)OutSize > 0x10 )
        memmove((void *)(v36 + 32), (const void *)(*(_QWORD *)(a2 + 112) + 16LL), v35 - 16);
      v37 = v12;
      memmove((void *)(v12 + *(_QWORD *)(a2 + 24)), *(const void **)(v43 + 32), Size);
    }
    *(_DWORD *)(v37 + *(_QWORD *)(a2 + 24) + 20) = v54;
    v39 = *(_QWORD *)(a2 + 184);
    *(_OWORD *)(v39 - 72) = *(_OWORD *)v39;
    *(_OWORD *)(v39 - 56) = *(_OWORD *)(v39 + 16);
    *(_OWORD *)(v39 - 40) = *(_OWORD *)(v39 + 32);
    *(_QWORD *)(v39 - 24) = *(_QWORD *)(v39 + 48);
    *(_BYTE *)(v39 - 69) = 0;
    *(_DWORD *)(*(_QWORD *)(a2 + 184) - 64LL) = v46;
    v9 = 5;
    v42 = 5;
    goto LABEL_62;
  }
  if ( v18 != 1020 )
  {
LABEL_62:
    v32 = a4;
    goto LABEL_64;
  }
  v19 = NumberOfBytes;
  if ( NumberOfBytes < 0x20 )
    ExRaiseStatus(-1073741306);
  v50 = 0;
  v51 = 0;
  NumberOfBytesa = NumberOfBytes + 8;
  if ( (unsigned int)(v19 + 8) < 0x28 )
    ExRaiseStatus(-1073741306);
  if ( (_DWORD)OutSize )
  {
    ProbeForRead(*(volatile void **)(a2 + 112), OutSize, 1u);
    ProbeForWrite(*(volatile void **)(a2 + 112), OutSize, 1u);
    OutBuffer = (void *)ExAllocatePool2(99, OutSize, 1886409547);
    v48 = OutBuffer;
    v20 = Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline();
    v21 = *(void **)(a2 + 112);
    if ( v20 )
      RtlCopyFromUser(OutBuffer, v21, OutSize);
    else
      memmove(OutBuffer, v21, OutSize);
  }
  v22 = Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline();
  v23 = *(__int128 **)(v6 + 32);
  if ( v22 )
  {
    RtlCopyFromUser(&v50, *(void **)(v6 + 32), 0x20u);
  }
  else
  {
    v50 = *v23;
    v51 = v23[1];
  }
  DWORD1(v51) = v54;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, NumberOfBytesa, 0x6271534Bu);
  v25 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, (unsigned int)(v19 + 8));
  P = v25;
  if ( !v25 )
    ExRaiseStatus(-1073741670);
  *(_OWORD *)v25 = v50;
  v25[2] = v51;
  v25[3] = DWORD2(v51);
  v25[4] = HIDWORD(v51);
  if ( (unsigned int)v19 <= 0x20 )
  {
    v28 = v43;
  }
  else
  {
    v26 = Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline();
    v27 = v19 - 32;
    v28 = v43;
    v29 = (void *)(*(_QWORD *)(v43 + 32) + 32LL);
    v30 = v25 + 5;
    if ( v26 )
      RtlCopyFromUser(v30, v29, v27);
    else
      memmove(v30, v29, v27);
  }
  v31 = KsSynchronousIoControlDevice(
          *(PFILE_OBJECT *)(v28 + 48),
          0,
          0x2F0007u,
          v25,
          NumberOfBytesa,
          OutBuffer,
          OutSize,
          &BytesReturned);
  v32 = a4;
  *a4 = v31;
  *(_QWORD *)(a2 + 56) = BytesReturned;
  ExFreePool(v25);
  P = 0;
  if ( OutBuffer )
  {
    v33 = Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline();
    v34 = *(void **)(a2 + 112);
    if ( v33 )
      RtlCopyToUser(v34, OutBuffer, OutSize);
    else
      memmove(v34, OutBuffer, OutSize);
    ExFreePool(OutBuffer);
    v48 = 0;
  }
  v40 = 1;
LABEL_64:
  if ( v40 )
    return 0;
  if ( *v32 >= 0 )
    return v9;
  return v5;
}

```

## disassembly

```asm
0x140003728  mov     rax, rsp
0x14000372b  mov     [rax+20h], r9
0x14000372f  mov     [rax+18h], r8d
0x140003733  mov     [rax+10h], rdx
0x140003737  mov     [rax+8], rcx
0x14000373b  push    rbx
0x14000373c  push    rsi
0x14000373d  push    rdi
0x14000373e  push    r12
0x140003740  push    r13
0x140003742  push    r14
0x140003744  push    r15
0x140003746  sub     rsp, 0B0h
0x14000374d  mov     rdi, rdx
0x140003750  xor     ebx, ebx
0x140003752  mov     [rsp+0E8h+var_A4], ebx
0x140003756  mov     rsi, [rdx+0B8h]
0x14000375d  mov     [rsp+0E8h+var_98], rsi
0x140003762  mov     r15d, [rsi+8]
0x140003766  lea     ecx, [r15+10h]
0x14000376a  mov     [rsp+0E8h+var_7C], ecx
0x14000376e  cmp     ecx, r15d
0x140003771  jb      loc_140003D2B
0x140003777  cmp     [rdx+18h], rbx
0x14000377b  jz      short loc_140003785
0x14000377d  lea     eax, [rbx+1]
0x140003780  jmp     loc_140003D34
0x140003785  mov     r14d, 1
0x14000378b  mov     [rsp+0E8h+var_A0], r14d
0x140003790  mov     [rsp+0E8h+var_A8], bl
0x140003794  mov     [rsp+0E8h+P], rbx
0x140003799  mov     r12, rbx
0x14000379c  mov     [rsp+0E8h+var_70], rbx
0x1400037a1  mov     eax, [rsi+10h]
0x1400037a4  mov     dword ptr [rsp+0E8h+NumberOfBytes], eax
0x1400037ab  lea     r13d, [rcx+7]
0x1400037af  and     r13d, 0FFFFFFF8h
0x1400037b3  cmp     eax, 18h
0x1400037b6  jnb     short loc_1400037C9
0x1400037b8  mov     ecx, 0C0000206h; Status
0x1400037bd  call    cs:__imp_ExRaiseStatus
0x1400037c9  mov     [rsp+0E8h+Size], rax
0x1400037d1  mov     r8d, r14d; Alignment
0x1400037d4  mov     rdx, rax; Length
0x1400037d7  mov     rcx, [rsi+20h]; Address
0x1400037db  call    cs:__imp_ProbeForRead
0x1400037e2  nop     dword ptr [rax+rax+00h]
0x1400037e7  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x1400037ec  mov     ecx, eax
0x1400037ee  mov     rax, [rsi+20h]
0x1400037f2  test    ecx, ecx
0x1400037f4  jz      short loc_140003801
0x1400037f6  lea     rcx, [rax+14h]
0x1400037fa  call    RtlReadULongFromUser
0x1400037ff  jmp     short loc_140003804
0x140003801  mov     eax, [rax+14h]
0x140003804  mov     [rsp+0E8h+arg_10], eax
0x14000380b  btr     eax, 1Ch
0x14000380f  sub     eax, 1
0x140003812  jz      loc_140003AAC
0x140003818  sub     eax, 1
0x14000381b  jz      loc_140003AAC
0x140003821  sub     eax, 2
0x140003824  jz      loc_140003AAC
0x14000382a  cmp     eax, 3FCh
0x14000382f  jnz     loc_140003C91
0x140003835  mov     r13d, dword ptr [rsp+0E8h+NumberOfBytes]
0x14000383d  cmp     r13d, 20h ; ' '
0x140003841  jnb     short loc_140003854
0x140003843  mov     ecx, 0C0000206h; Status
0x140003848  call    cs:__imp_ExRaiseStatus
0x140003854  xorps   xmm0, xmm0
0x140003857  movups  [rsp+0E8h+var_60], xmm0
0x14000385f  movups  [rsp+0E8h+var_50], xmm0
0x140003867  lea     eax, [r13+8]
0x14000386b  mov     dword ptr [rsp+0E8h+NumberOfBytes], eax
0x140003872  cmp     eax, 28h ; '('
0x140003875  jnb     short loc_140003888
0x140003877  mov     ecx, 0C0000206h; Status
0x14000387c  call    cs:__imp_ExRaiseStatus
0x140003888  test    r15d, r15d
0x14000388b  jz      short loc_1400038FA
0x14000388d  mov     r8d, r14d; Alignment
0x140003890  mov     rdx, r15; Length
0x140003893  mov     rcx, [rdi+70h]; Address
0x140003897  call    cs:__imp_ProbeForRead
0x14000389e  nop     dword ptr [rax+rax+00h]
0x1400038a3  mov     r8d, r14d; Alignment
0x1400038a6  mov     rdx, r15; Length
0x1400038a9  mov     rcx, [rdi+70h]; Address
0x1400038ad  call    cs:__imp_ProbeForWrite
0x1400038b4  nop     dword ptr [rax+rax+00h]
0x1400038b9  mov     r8d, 7070534Bh
0x1400038bf  mov     rdx, r15
0x1400038c2  mov     ecx, 63h ; 'c'
0x1400038c7  call    cs:__imp_ExAllocatePool2
0x1400038ce  nop     dword ptr [rax+rax+00h]
0x1400038d3  mov     r12, rax
0x1400038d6  mov     [rsp+0E8h+var_70], rax
0x1400038db  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x1400038e0  mov     rdx, [rdi+70h]; Src
0x1400038e4  mov     r8, r15; Size
0x1400038e7  mov     rcx, r12; void *
0x1400038ea  test    eax, eax
0x1400038ec  jz      short loc_1400038F5
0x1400038ee  call    RtlCopyFromUser
0x1400038f3  jmp     short loc_1400038FA
0x1400038f5  call    memmove
0x1400038fa  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x1400038ff  mov     rcx, [rsi+20h]
0x140003903  test    eax, eax
0x140003905  jz      short loc_14000391F
0x140003907  mov     r8d, 20h ; ' '; Size
0x14000390d  mov     rdx, rcx; Src
0x140003910  lea     rcx, [rsp+0E8h+var_60]; void *
0x140003918  call    RtlCopyFromUser
0x14000391d  jmp     short loc_140003936
0x14000391f  movups  xmm0, xmmword ptr [rcx]
0x140003922  movups  [rsp+0E8h+var_60], xmm0
0x14000392a  movups  xmm1, xmmword ptr [rcx+10h]
0x14000392e  movups  [rsp+0E8h+var_50], xmm1
0x140003936  mov     ecx, [rsp+0E8h+arg_10]
0x14000393d  mov     dword ptr [rsp+0E8h+var_50+4], ecx
0x140003944  mov     edx, dword ptr [rsp+0E8h+NumberOfBytes]; NumberOfBytes
0x14000394b  mov     ecx, 600h; PoolType
0x140003950  mov     r8d, 6271534Bh; Tag
0x140003956  call    cs:__imp_ExAllocatePoolWithTag
0x14000395d  nop     dword ptr [rax+rax+00h]
0x140003962  mov     rsi, rax
0x140003965  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000396c  jnz     short loc_140003981
0x14000396e  test    rax, rax
0x140003971  jz      short loc_140003981
0x140003973  lea     r8d, [r13+8]; Size
0x140003977  xor     edx, edx; Val
0x140003979  mov     rcx, rax; void *
0x14000397c  call    memset
0x140003981  mov     [rsp+0E8h+P], rsi
0x140003986  test    rsi, rsi
0x140003989  jnz     short loc_14000399C
0x14000398b  mov     ecx, 0C000009Ah; Status
0x140003990  call    cs:__imp_ExRaiseStatus
0x14000399c  movups  xmm0, [rsp+0E8h+var_60]
0x1400039a4  movups  xmmword ptr [rsi], xmm0
0x1400039a7  mov     eax, dword ptr [rsp+0E8h+var_50]
0x1400039ae  mov     [rsi+10h], eax
0x1400039b1  mov     eax, dword ptr [rsp+0E8h+var_50+4]
0x1400039b8  mov     [rsi+14h], eax
0x1400039bb  mov     eax, dword ptr [rsp+0E8h+var_50+8]
0x1400039c2  mov     [rsi+18h], rax
0x1400039c6  mov     eax, dword ptr [rsp+0E8h+var_50+0Ch]
0x1400039cd  mov     [rsi+20h], rax
0x1400039d1  cmp     r13d, 20h ; ' '
0x1400039d5  jbe     short loc_140003A03
0x1400039d7  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x1400039dc  lea     r8, [r13-20h]; Size
0x1400039e0  mov     r13, [rsp+0E8h+var_98]
0x1400039e5  mov     rdx, [r13+20h]
0x1400039e9  add     rdx, 20h ; ' '; Src
0x1400039ed  lea     rcx, [rsi+28h]; void *
0x1400039f1  test    eax, eax
0x1400039f3  jz      short loc_1400039FC
0x1400039f5  call    RtlCopyFromUser
0x1400039fa  jmp     short loc_140003A08
0x1400039fc  call    memmove
0x140003a01  jmp     short loc_140003A08
0x140003a03  mov     r13, [rsp+0E8h+var_98]
0x140003a08  lea     rax, [rsp+0E8h+var_A4]
0x140003a0d  mov     [rsp+0E8h+BytesReturned], rax; BytesReturned
0x140003a12  mov     [rsp+0E8h+OutSize], r15d; OutSize
0x140003a17  mov     [rsp+0E8h+OutBuffer], r12; OutBuffer
0x140003a1c  mov     eax, dword ptr [rsp+0E8h+NumberOfBytes]
0x140003a23  mov     [rsp+0E8h+InSize], eax; InSize
0x140003a27  mov     r9, rsi; InBuffer
0x140003a2a  xor     edx, edx; RequestorMode
0x140003a2c  mov     r8d, 2F0007h; IoControl
0x140003a32  mov     rcx, [r13+30h]; FileObject
0x140003a36  call    cs:__imp_KsSynchronousIoControlDevice
0x140003a3d  nop     dword ptr [rax+rax+00h]
0x140003a42  mov     r13, [rsp+0E8h+arg_18]
0x140003a4a  mov     [r13+0], eax
0x140003a4e  mov     eax, [rsp+0E8h+var_A4]
0x140003a52  mov     [rdi+38h], rax
0x140003a56  mov     rcx, rsi; P
0x140003a59  call    cs:__imp_ExFreePool
0x140003a60  nop     dword ptr [rax+rax+00h]
0x140003a65  mov     [rsp+0E8h+P], rbx
0x140003a6a  test    r12, r12
0x140003a6d  jz      short loc_140003AA2
0x140003a6f  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x140003a74  mov     r8, r15; Size
0x140003a77  mov     rcx, [rdi+70h]; void *
0x140003a7b  mov     rdx, r12; Src
0x140003a7e  test    eax, eax
0x140003a80  jz      short loc_140003A89
0x140003a82  call    RtlCopyToUser
0x140003a87  jmp     short loc_140003A8E
0x140003a89  call    memmove
0x140003a8e  mov     rcx, r12; P
0x140003a91  call    cs:__imp_ExFreePool
0x140003a98  nop     dword ptr [rax+rax+00h]
0x140003a9d  mov     [rsp+0E8h+var_70], rbx
0x140003aa2  mov     [rsp+0E8h+var_A8], r14b
0x140003aa7  jmp     loc_140003C99
0x140003aac  cmp     r15d, 10h
0x140003ab0  jnb     short loc_140003AC3
0x140003ab2  mov     ecx, 0C0000206h; Status
0x140003ab7  call    cs:__imp_ExRaiseStatus
0x140003ac3  lea     eax, [r15+10h]
0x140003ac7  cmp     r13d, eax
0x140003aca  jb      loc_140003C9B
0x140003ad0  mov     ecx, dword ptr [rsp+0E8h+NumberOfBytes]
0x140003ad7  add     ecx, r13d
0x140003ada  cmp     ecx, r13d
0x140003add  jb      loc_140003C9B
0x140003ae3  mov     edx, ecx
0x140003ae5  mov     ecx, 61h ; 'a'
0x140003aea  mov     r8d, 7070534Bh
0x140003af0  call    cs:__imp_ExAllocatePool2
0x140003af7  nop     dword ptr [rax+rax+00h]
0x140003afc  mov     [rdi+18h], rax
0x140003b00  or      dword ptr [rdi+10h], 30h
0x140003b04  xorps   xmm0, xmm0
0x140003b07  movups  [rsp+0E8h+var_90], xmm0
0x140003b0c  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x140003b11  mov     rcx, [rdi+70h]; Address
0x140003b15  test    eax, eax
0x140003b17  jz      short loc_140003B31
0x140003b19  mov     r8d, 10h; Size
0x140003b1f  mov     rdx, rcx; Src
0x140003b22  lea     rcx, [rsp+0E8h+var_90]; void *
0x140003b27  call    RtlCopyFromUser
0x140003b2c  mov     r12, r15
0x140003b2f  jmp     short loc_140003B53
0x140003b31  mov     r12, r15
0x140003b34  mov     r8d, r14d; Alignment
0x140003b37  mov     rdx, r15; Length
0x140003b3a  call    cs:__imp_ProbeForRead
0x140003b41  nop     dword ptr [rax+rax+00h]
0x140003b46  mov     rax, [rdi+70h]
0x140003b4a  movups  xmm0, xmmword ptr [rax]
0x140003b4d  movdqu  [rsp+0E8h+var_90], xmm0
0x140003b53  mov     rsi, [rdi+18h]
0x140003b57  mov     rax, qword ptr [rsp+0E8h+var_90]
0x140003b5c  mov     [rsi], eax
0x140003b5e  mov     rax, qword ptr [rsp+0E8h+var_90]
0x140003b63  sub     eax, 1
0x140003b66  jz      short loc_140003BDB
0x140003b68  cmp     eax, 1
0x140003b6b  jz      short loc_140003B7E
0x140003b6d  mov     ecx, 0C000000Dh; Status
0x140003b72  call    cs:__imp_ExRaiseStatus
0x140003b7e  mov     eax, dword ptr [rsp+0E8h+var_90+4]
0x140003b82  mov     [rsi+8], rax
0x140003b86  mov     eax, dword ptr [rsp+0E8h+var_90+8]
0x140003b8a  mov     [rsi+10h], eax
0x140003b8d  mov     eax, dword ptr [rsp+0E8h+var_90+0Ch]
0x140003b91  mov     [rsi+14h], eax
0x140003b94  call    Feature_Servicing_KSTHUNK_UMA__private_IsEnabledDeviceUsageNoInline
0x140003b99  test    eax, eax
0x140003b9b  jnz     short loc_140003C02
0x140003b9d  cmp     r15d, 10h
0x140003ba1  jbe     short loc_140003BB9
0x140003ba3  lea     r8, [r12-10h]; Size
0x140003ba8  mov     rdx, [rdi+70h]
0x140003bac  add     rdx, 10h; Src
0x140003bb0  lea     rcx, [rsi+20h]; void *
0x140003bb4  call    memmove
0x140003bb9  mov     esi, r13d
0x140003bbc  mov     rcx, [rdi+18h]
0x140003bc0  add     rcx, rsi; void *
0x140003bc3  mov     r8, [rsp+0E8h+Size]; Size
0x140003bcb  mov     r13, [rsp+0E8h+var_98]
0x140003bd0  mov     rdx, [r13+20h]; Src
0x140003bd4  call    memmove
0x140003bd9  jmp     short loc_140003C3E
0x140003bdb  mov     eax, dword ptr [rsp+0E8h+var_90+4]
0x140003bdf  mov     [rsi+8], rax
0x140003be3  mov     edx, ebx
0x140003be5  mov     [rsp+0E8h+var_80], ebx
0x140003be9  cmp     edx, 2
0x140003bec  jnb     short loc_140003B94
0x140003bee  mov     ecx, edx
0x140003bf0  mov     eax, dword ptr [rsp+rcx*4+0E8h+var_90+8]
0x140003bf4  mov     [rsi+rcx*8+10h], rax
0x140003bf9  add     edx, r14d
0x140003bfc  mov     [rsp+0E8h+var_80], edx
0x140003c00  jmp     short loc_140003BE9
0x140003c02  cmp     r15d, 10h
0x140003c06  jbe     short loc_140003C1E
0x140003c08  lea     r8, [r12-10h]; Size
0x140003c0d  mov     rdx, [rdi+70h]
0x140003c11  add     rdx, 10h; Src
0x140003c15  lea     rcx, [rsi+20h]; void *
0x140003c19  call    RtlCopyFromUser
0x140003c1e  mov     esi, r13d
0x140003c21  mov     rcx, [rdi+18h]
0x140003c25  add     rcx, rsi; void *
0x140003c28  mov     r8, [rsp+0E8h+Size]; Size
0x140003c30  mov     r13, [rsp+0E8h+var_98]
  ... truncated ...
```
