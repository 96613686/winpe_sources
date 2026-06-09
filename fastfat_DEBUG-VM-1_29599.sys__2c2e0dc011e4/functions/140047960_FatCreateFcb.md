# FatCreateFcb

- ea: `0x140047960`
- end: `0x140047d1e`
- name: `FatCreateFcb`
- size: `958`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000363c`
- `0x140029774`
- `0x14002b790`
- `0x14003a3e0`
- `0x140040674`

## callees

- `0x1400062c8`
- `0x14000656c`
- `0x14000c680`
- `0x140031938`
- `0x1400471f8`
- `0x140047960`
- `0x140049380`
- `0x140049428`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140047ba3`
- `ntoskrnl!KeInitializeEvent` at `0x140047ba3`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x140047b3f`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x140047b3f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047a2f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047a2f`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140047cd5`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140047cd5`
- `ntoskrnl!FsRtlInitializeFileLock` at `0x140047cc1`
- `ntoskrnl!FsRtlInitializeFileLock` at `0x140047cc1`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14005fb0d`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14005fb0d`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x14005fb23`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x14005fb23`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fb39`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005fb39`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140047c1d`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140047c1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fb9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fb9f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400479c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400479eb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400479c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400479eb`

## pseudocode

```c
_DWORD *__fastcall FatCreateFcb(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9,
        char a10)
{
  _DWORD *PoolWithTag; // rdi
  PVOID v14; // rax
  __int64 Resource; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  __int64 v19; // r8
  union _LARGE_INTEGER v20; // rax
  __int64 v21; // rcx
  union _LARGE_INTEGER v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  char v25; // cl
  __int64 v26; // rdx
  char v27; // cl
  __int64 v28; // rdx
  int v29; // ecx
  __int64 v30; // rcx
  union _LARGE_INTEGER SystemTime; // [rsp+20h] [rbp-68h] BYREF
  _DWORD *v33; // [rsp+28h] [rbp-60h]
  _DWORD *v34; // [rsp+30h] [rbp-58h]
  _DWORD *v35; // [rsp+38h] [rbp-50h]
  _DWORD *v36; // [rsp+40h] [rbp-48h]
  __int64 v37; // [rsp+48h] [rbp-40h]
  __int64 v38; // [rsp+50h] [rbp-38h]
  __int128 v39; // [rsp+58h] [rbp-30h]
  POOL_TYPE PoolType; // [rsp+90h] [rbp+8h]

  v39 = 0;
  v37 = 0;
  v38 = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  if ( a9 )
  {
    PoolType = 512;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)528, 0x278u, 0x46746146u);
    *(_QWORD *)&v39 = PoolWithTag;
  }
  else
  {
    PoolType = PagedPool;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, 0x278u, 0x46746146u);
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, 0x278u);
    *(_QWORD *)&v39 = PoolWithTag;
  }
  memset(PoolWithTag, 0, 0x278u);
  v14 = ExAllocateFromNPagedLookasideList(&FatNonPagedFcbLookasideList);
  *((_QWORD *)PoolWithTag + 15) = v14;
  *((_QWORD *)&v39 + 1) = v14;
  memset(v14, 0, 0x78u);
  *PoolWithTag = 41420034;
  PoolWithTag[49] = 1;
  if ( a9 )
    PoolWithTag[48] |= 0x84u;
  Resource = FatAllocateResource();
  *((_QWORD *)PoolWithTag + 1) = Resource;
  v37 = Resource;
  if ( a10 )
  {
    *((_QWORD *)PoolWithTag + 2) = Resource;
  }
  else
  {
    v16 = FatAllocateResource();
    *((_QWORD *)PoolWithTag + 2) = v16;
    v38 = v16;
  }
  v17 = a3 + 320;
  v18 = *(_QWORD **)(a3 + 328);
  if ( *v18 != a3 + 320 )
    __fastfail(3u);
  *((_QWORD *)PoolWithTag + 20) = v17;
  *((_QWORD *)PoolWithTag + 21) = v18;
  *v18 = PoolWithTag + 40;
  *(_QWORD *)(a3 + 328) = PoolWithTag + 40;
  v36 = PoolWithTag + 40;
  *((_QWORD *)PoolWithTag + 22) = a3;
  *((_QWORD *)PoolWithTag + 23) = a2;
  PoolWithTag[62] = a4;
  PoolWithTag[61] = a5;
  *((_BYTE *)PoolWithTag + 546) = *(_BYTE *)(a6 + 11);
  *((_QWORD *)PoolWithTag + 34) = FatFatTimeToNtTime(v17, *(unsigned int *)(a6 + 22), 0);
  if ( (byte_140017D4C & 1) != 0 )
  {
    v20.QuadPart = 0;
    SystemTime.QuadPart = 0;
    v21 = *(unsigned __int16 *)(a6 + 16);
    if ( ((unsigned __int16)v21 & *(_WORD *)(a6 + 18)) == 0 )
    {
      ExLocalTimeToSystemTime(&FatJanOne1980, &SystemTime);
      v20 = SystemTime;
    }
    if ( *(_WORD *)(a6 + 18) )
      v20.QuadPart = FatFatDateToNtTime(v21, *(unsigned __int16 *)(a6 + 18));
    *((union _LARGE_INTEGER *)PoolWithTag + 33) = v20;
    if ( *(_WORD *)(a6 + 16) )
    {
      LOBYTE(v19) = *(_BYTE *)(a6 + 13);
      v22.QuadPart = FatFatTimeToNtTime(v21, *(unsigned int *)(a6 + 14), v19);
    }
    else
    {
      v22 = SystemTime;
    }
    *((union _LARGE_INTEGER *)PoolWithTag + 32) = v22;
  }
  v23 = *((_QWORD *)PoolWithTag + 15);
  *(_DWORD *)(v23 + 40) = 1;
  *(_QWORD *)(v23 + 48) = 0;
  *(_DWORD *)(v23 + 56) = 0;
  KeInitializeEvent((PRKEVENT)(v23 + 64), SynchronizationEvent, 0);
  v24 = *((_QWORD *)PoolWithTag + 15);
  *((_BYTE *)PoolWithTag + 4) |= 0x40u;
  *((_BYTE *)PoolWithTag + 6) |= 2u;
  v25 = *((_BYTE *)PoolWithTag + 6);
  *((_BYTE *)PoolWithTag + 7) = *((_BYTE *)PoolWithTag + 7) & 0xF | 0x50;
  *((_QWORD *)PoolWithTag + 8) = PoolWithTag + 14;
  *((_QWORD *)PoolWithTag + 7) = PoolWithTag + 14;
  v26 = v24 + 40;
  if ( v26 )
    *((_QWORD *)PoolWithTag + 6) = v26;
  *((_QWORD *)PoolWithTag + 9) = 0;
  *((_QWORD *)PoolWithTag + 10) = 0;
  *((_QWORD *)PoolWithTag + 11) = 0;
  *((_QWORD *)PoolWithTag + 12) = 0;
  PoolWithTag[26] = 0;
  *((_QWORD *)PoolWithTag + 14) = 0;
  if ( a9 )
  {
    v27 = v25 | 8;
    *((_BYTE *)PoolWithTag + 6) = v27;
    *((_BYTE *)PoolWithTag + 6) = v27 & 0xFD;
  }
  FsRtlInitializeLargeMcb((PLARGE_MCB)PoolWithTag + 9, PoolType);
  v35 = PoolWithTag + 72;
  PoolWithTag[8] = *(_DWORD *)(a6 + 28);
  PoolWithTag[10] = *(_DWORD *)(a6 + 28);
  PoolWithTag[70] = *(_DWORD *)(a6 + 28);
  v29 = *(unsigned __int16 *)(a6 + 26);
  PoolWithTag[32] = v29;
  if ( *(_BYTE *)(a2 + 376) == 32 )
  {
    v29 += *(unsigned __int16 *)(a6 + 20) << 16;
    PoolWithTag[32] = v29;
  }
  *((_QWORD *)PoolWithTag + 3) = -(__int64)(v29 != 0);
  if ( (*(_DWORD *)(a2 + 200) & 0x400000) != 0 && (*(_BYTE *)(a6 + 12) & 1) != 0 )
  {
    if ( a8 )
    {
      LOBYTE(v28) = 1;
      if ( (unsigned __int8)FatFileExtensionIsPfile(a8, v28) )
      {
        PoolWithTag[48] |= 0x20000u;
        PoolWithTag[48] |= 0x40000u;
      }
    }
  }
  FsRtlInitializeFileLock((PFILE_LOCK)(PoolWithTag + 80), 0, 0);
  v34 = PoolWithTag + 80;
  FsRtlInitializeOplock((POPLOCK)PoolWithTag + 11);
  v33 = PoolWithTag + 22;
  *((_BYTE *)PoolWithTag + 5) = 1;
  FatConstructNamesInFcb(v30, PoolWithTag, a6, a7);
  *((_BYTE *)PoolWithTag + 496) = 1;
  return PoolWithTag;
}

```

## disassembly

```asm
0x140047960  mov     r11, rsp
0x140047963  mov     [r11+10h], rbx
0x140047967  mov     [r11+18h], rsi
0x14004796b  mov     [r11+8], rcx
0x14004796f  push    rdi
0x140047970  push    r13
0x140047972  push    r15
0x140047974  sub     rsp, 70h
0x140047978  mov     r15d, r9d
0x14004797b  mov     rsi, r8
0x14004797e  mov     r13, rdx
0x140047981  xorps   xmm0, xmm0
0x140047984  movdqu  [rsp+88h+var_30], xmm0
0x14004798a  xor     eax, eax
0x14004798c  mov     [r11-40h], rax
0x140047990  mov     [r11-38h], rax
0x140047994  mov     [r11-48h], rax
0x140047998  mov     [r11-50h], rax
0x14004799c  mov     [r11-58h], rax
0x1400479a0  mov     [r11-60h], rax
0x1400479a4  mov     ebx, 278h
0x1400479a9  mov     r8d, 46746146h; Tag
0x1400479af  mov     edx, ebx; NumberOfBytes
0x1400479b1  cmp     [rsp+88h+arg_40], al
0x1400479b8  jz      short loc_1400479DB
0x1400479ba  mov     dword ptr [r11+8], 200h
0x1400479c2  lea     ecx, [rbx-68h]; PoolType
0x1400479c5  call    cs:__imp_ExAllocatePoolWithTag
0x1400479cc  nop     dword ptr [rax+rax+00h]
0x1400479d1  mov     rdi, rax
0x1400479d4  mov     qword ptr [rsp+88h+var_30], rax
0x1400479d9  jmp     short loc_140047A1B
0x1400479db  mov     [rsp+88h+PoolType], 1
0x1400479e6  mov     ecx, 411h; PoolType
0x1400479eb  call    cs:__imp_ExAllocatePoolWithTag
0x1400479f2  nop     dword ptr [rax+rax+00h]
0x1400479f7  mov     rdi, rax
0x1400479fa  xor     eax, eax
0x1400479fc  cmp     cs:ExPoolZeroingNativelySupported, al
0x140047a02  jnz     short loc_140047A16
0x140047a04  test    rdi, rdi
0x140047a07  jz      short loc_140047A16
0x140047a09  mov     r8, rbx; Size
0x140047a0c  xor     edx, edx; Val
0x140047a0e  mov     rcx, rdi; void *
0x140047a11  call    memset
0x140047a16  mov     qword ptr [rsp+88h+var_30], rdi
0x140047a1b  mov     r8, rbx; Size
0x140047a1e  xor     edx, edx; Val
0x140047a20  mov     rcx, rdi; void *
0x140047a23  call    memset
0x140047a28  lea     rcx, FatNonPagedFcbLookasideList; Lookaside
0x140047a2f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140047a36  nop     dword ptr [rax+rax+00h]
0x140047a3b  mov     [rdi+78h], rax
0x140047a3f  mov     qword ptr [rsp+88h+var_30+8], rax
0x140047a44  xor     edx, edx; Val
0x140047a46  lea     r8d, [rdx+78h]; Size
0x140047a4a  mov     rcx, rax; void *
0x140047a4d  call    memset
0x140047a52  mov     dword ptr [rdi], 2780502h
0x140047a58  mov     dword ptr [rdi+0C4h], 1
0x140047a62  xor     ebx, ebx
0x140047a64  cmp     [rsp+88h+arg_40], bl
0x140047a6b  jz      short loc_140047A77
0x140047a6d  or      dword ptr [rdi+0C0h], 84h
0x140047a77  call    FatAllocateResource
0x140047a7c  mov     [rdi+8], rax
0x140047a80  mov     [rsp+88h+var_40], rax
0x140047a85  cmp     [rsp+88h+arg_48], bl
0x140047a8c  jz      short loc_140047A94
0x140047a8e  mov     [rdi+10h], rax
0x140047a92  jmp     short loc_140047AA2
0x140047a94  call    FatAllocateResource
0x140047a99  mov     [rdi+10h], rax
0x140047a9d  mov     [rsp+88h+var_38], rax
0x140047aa2  lea     rcx, [rsi+140h]
0x140047aa9  mov     rdx, [rcx+8]
0x140047aad  cmp     [rdx], rcx
0x140047ab0  jz      short loc_140047AB9
0x140047ab2  mov     ecx, 3
0x140047ab7  int     29h; Win8: RtlFailFast(ecx)
0x140047ab9  lea     rax, [rdi+0A0h]
0x140047ac0  mov     [rax], rcx
0x140047ac3  mov     [rax+8], rdx
0x140047ac7  mov     [rdx], rax
0x140047aca  mov     [rcx+8], rax
0x140047ace  mov     [rsp+88h+var_48], rax
0x140047ad3  mov     [rdi+0B0h], rsi
0x140047ada  mov     [rdi+0B8h], r13
0x140047ae1  mov     [rdi+0F8h], r15d
0x140047ae8  mov     eax, [rsp+88h+arg_20]
0x140047aef  mov     [rdi+0F4h], eax
0x140047af5  mov     rsi, [rsp+88h+arg_28]
0x140047afd  mov     al, [rsi+0Bh]
0x140047b00  mov     [rdi+222h], al
0x140047b06  xor     r8d, r8d
0x140047b09  mov     edx, [rsi+16h]
0x140047b0c  call    FatFatTimeToNtTime
0x140047b11  mov     [rdi+110h], rax
0x140047b18  test    cs:byte_140017D4C, 1
0x140047b1f  jz      short loc_140047B86
0x140047b21  mov     rax, rbx
0x140047b24  mov     qword ptr [rsp+88h+SystemTime], rbx
0x140047b29  movzx   ecx, word ptr [rsi+10h]
0x140047b2d  test    [rsi+12h], cx
0x140047b31  jnz     short loc_140047B50
0x140047b33  lea     rdx, [rsp+88h+SystemTime]; SystemTime
0x140047b38  lea     rcx, FatJanOne1980; LocalTime
0x140047b3f  call    cs:__imp_ExLocalTimeToSystemTime
0x140047b46  nop     dword ptr [rax+rax+00h]
0x140047b4b  mov     rax, qword ptr [rsp+88h+SystemTime]
0x140047b50  cmp     [rsi+12h], bx
0x140047b54  jz      short loc_140047B5F
0x140047b56  movzx   edx, word ptr [rsi+12h]
0x140047b5a  call    FatFatDateToNtTime
0x140047b5f  mov     [rdi+108h], rax
0x140047b66  cmp     [rsi+10h], bx
0x140047b6a  jz      short loc_140047B7A
0x140047b6c  mov     r8b, [rsi+0Dh]
0x140047b70  mov     edx, [rsi+0Eh]
0x140047b73  call    FatFatTimeToNtTime
0x140047b78  jmp     short loc_140047B7F
0x140047b7a  mov     rax, qword ptr [rsp+88h+SystemTime]
0x140047b7f  mov     [rdi+100h], rax
0x140047b86  mov     rcx, [rdi+78h]
0x140047b8a  mov     dword ptr [rcx+28h], 1
0x140047b91  mov     [rcx+30h], rbx
0x140047b95  mov     [rcx+38h], ebx
0x140047b98  add     rcx, 40h ; '@'; Event
0x140047b9c  xor     r8d, r8d; State
0x140047b9f  lea     edx, [r8+1]; Type
0x140047ba3  call    cs:__imp_KeInitializeEvent
0x140047baa  nop     dword ptr [rax+rax+00h]
0x140047baf  mov     rdx, [rdi+78h]
0x140047bb3  or      byte ptr [rdi+4], 40h
0x140047bb7  or      byte ptr [rdi+6], 2
0x140047bbb  mov     cl, [rdi+6]
0x140047bbe  mov     al, [rdi+7]
0x140047bc1  and     al, 0Fh
0x140047bc3  or      al, 50h
0x140047bc5  mov     [rdi+7], al
0x140047bc8  lea     rax, [rdi+38h]
0x140047bcc  mov     [rax+8], rax
0x140047bd0  mov     [rax], rax
0x140047bd3  add     rdx, 28h ; '('
0x140047bd7  jz      short loc_140047BDD
0x140047bd9  mov     [rdi+30h], rdx
0x140047bdd  mov     [rdi+48h], rbx
0x140047be1  mov     [rdi+50h], rbx
0x140047be5  lea     r15, [rdi+58h]
0x140047be9  mov     [r15], rbx
0x140047bec  mov     [rdi+60h], rbx
0x140047bf0  mov     [rdi+68h], ebx
0x140047bf3  mov     [rdi+70h], rbx
0x140047bf7  cmp     [rsp+88h+arg_40], bl
0x140047bfe  jz      short loc_140047C0C
0x140047c00  or      cl, 8
0x140047c03  mov     [rdi+6], cl
0x140047c06  and     cl, 0FDh
0x140047c09  mov     [rdi+6], cl
0x140047c0c  lea     rbx, [rdi+120h]
0x140047c13  mov     edx, [rsp+88h+PoolType]; PoolType
0x140047c1a  mov     rcx, rbx; Mcb
0x140047c1d  call    cs:__imp_FsRtlInitializeLargeMcb
0x140047c24  nop     dword ptr [rax+rax+00h]
0x140047c29  mov     [rsp+88h+var_50], rbx
0x140047c2e  mov     eax, [rsi+1Ch]
0x140047c31  mov     [rdi+20h], eax
0x140047c34  mov     eax, [rsi+1Ch]
0x140047c37  mov     [rdi+28h], eax
0x140047c3a  mov     eax, [rsi+1Ch]
0x140047c3d  mov     [rdi+118h], eax
0x140047c43  movzx   ecx, word ptr [rsi+1Ah]
0x140047c47  mov     [rdi+80h], ecx
0x140047c4d  cmp     byte ptr [r13+178h], 20h ; ' '
0x140047c55  jnz     short loc_140047C66
0x140047c57  movzx   eax, word ptr [rsi+14h]
0x140047c5b  shl     eax, 10h
0x140047c5e  add     ecx, eax
0x140047c60  mov     [rdi+80h], ecx
0x140047c66  neg     ecx
0x140047c68  sbb     rax, rax
0x140047c6b  mov     [rdi+18h], rax
0x140047c6f  mov     eax, [r13+0C8h]
0x140047c76  bt      eax, 16h
0x140047c7a  jnb     short loc_140047CB2
0x140047c7c  test    byte ptr [rsi+0Ch], 1
0x140047c80  jz      short loc_140047CB2
0x140047c82  mov     rcx, [rsp+88h+arg_38]
0x140047c8a  test    rcx, rcx
0x140047c8d  jz      short loc_140047CB2
0x140047c8f  mov     dl, 1
0x140047c91  call    FatFileExtensionIsPfile
0x140047c96  test    al, al
0x140047c98  jz      short loc_140047CB2
0x140047c9a  bts     dword ptr [rdi+0C0h], 11h
0x140047ca2  mov     eax, [rdi+0C0h]
0x140047ca8  bts     eax, 12h
0x140047cac  mov     [rdi+0C0h], eax
0x140047cb2  lea     rbx, [rdi+140h]
0x140047cb9  xor     r8d, r8d; UnlockRoutine
0x140047cbc  xor     edx, edx; CompleteLockIrpRoutine
0x140047cbe  mov     rcx, rbx; FileLock
0x140047cc1  call    cs:__imp_FsRtlInitializeFileLock
0x140047cc8  nop     dword ptr [rax+rax+00h]
0x140047ccd  mov     [rsp+88h+var_58], rbx
0x140047cd2  mov     rcx, r15; Oplock
0x140047cd5  call    cs:__imp_FsRtlInitializeOplock
0x140047cdc  nop     dword ptr [rax+rax+00h]
0x140047ce1  mov     [rsp+88h+var_60], r15
0x140047ce6  mov     byte ptr [rdi+5], 1
0x140047cea  mov     r9, [rsp+88h+arg_30]
0x140047cf2  mov     r8, rsi
0x140047cf5  mov     rdx, rdi
0x140047cf8  call    FatConstructNamesInFcb
0x140047cfd  mov     byte ptr [rdi+1F0h], 1
0x140047d04  mov     rax, rdi
0x140047d07  lea     r11, [rsp+88h+var_18]
0x140047d0c  mov     rbx, [r11+28h]
0x140047d10  mov     rsi, [r11+30h]
0x140047d14  mov     rsp, r11
0x140047d17  pop     r15
0x140047d19  pop     r13
0x140047d1b  pop     rdi
0x140047d1c  retn
0x14005faef  push    rbx
0x14005faf1  push    rbp
0x14005faf2  sub     rsp, 28h
0x14005faf6  mov     rbp, rdx
0x14005faf9  movzx   eax, cl
0x14005fafc  test    cl, cl
0x14005fafe  jz      loc_14005FBB3
0x14005fb04  mov     rcx, [rbp+28h]; Oplock
0x14005fb08  test    rcx, rcx
0x14005fb0b  jz      short loc_14005FB1A
0x14005fb0d  call    cs:__imp_FsRtlUninitializeOplock
0x14005fb14  nop     dword ptr [rax+rax+00h]
0x14005fb19  nop
0x14005fb1a  mov     rcx, [rbp+30h]; FileLock
0x14005fb1e  test    rcx, rcx
0x14005fb21  jz      short loc_14005FB30
0x14005fb23  call    cs:__imp_FsRtlUninitializeFileLock
0x14005fb2a  nop     dword ptr [rax+rax+00h]
0x14005fb2f  nop
0x14005fb30  mov     rcx, [rbp+38h]; Mcb
0x14005fb34  test    rcx, rcx
0x14005fb37  jz      short loc_14005FB46
0x14005fb39  call    cs:__imp_FsRtlUninitializeLargeMcb
0x14005fb40  nop     dword ptr [rax+rax+00h]
0x14005fb45  nop
0x14005fb46  mov     rax, [rbp+40h]
0x14005fb4a  test    rax, rax
0x14005fb4d  jz      short loc_14005FB71
0x14005fb4f  mov     rdx, [rax]
0x14005fb52  mov     rcx, [rax+8]
0x14005fb56  cmp     [rdx+8], rax
0x14005fb5a  jnz     short loc_14005FB6A
0x14005fb5c  cmp     [rcx], rax
0x14005fb5f  jnz     short loc_14005FB6A
0x14005fb61  mov     [rcx], rdx
0x14005fb64  mov     [rdx+8], rcx
0x14005fb68  jmp     short loc_14005FB71
0x14005fb6a  mov     ecx, 3
0x14005fb6f  int     29h; Win8: RtlFailFast(ecx)
0x14005fb71  mov     rcx, [rbp+48h]; Entry
0x14005fb75  test    rcx, rcx
0x14005fb78  jz      short loc_14005FB80
0x14005fb7a  call    FatFreeResource
0x14005fb7f  nop
0x14005fb80  mov     rcx, [rbp+50h]; Entry
0x14005fb84  test    rcx, rcx
0x14005fb87  jz      short loc_14005FB8F
0x14005fb89  call    FatFreeResource
0x14005fb8e  nop
0x14005fb8f  xor     ebx, ebx
0x14005fb91  mov     eax, ebx
0x14005fb93  mov     rcx, [rbp+rbx*8+58h]; P
0x14005fb98  test    rcx, rcx
0x14005fb9b  jz      short loc_14005FBAC
0x14005fb9d  xor     edx, edx; Tag
0x14005fb9f  call    cs:__imp_ExFreePoolWithTag
0x14005fba6  nop     dword ptr [rax+rax+00h]
0x14005fbab  nop
0x14005fbac  inc     ebx
0x14005fbae  cmp     ebx, 2
0x14005fbb1  jb      short loc_14005FB91
0x14005fbb3  add     rsp, 28h
0x14005fbb7  pop     rbp
0x14005fbb8  pop     rbx
0x14005fbb9  retn
```
