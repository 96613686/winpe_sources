# CKSAutomationThunk::ThunkEnableEventIrp(_IRP *,_IRP_STATUS,long *)

- ea: `0x140002dc8`
- end: `0x140003307`
- name: `?ThunkEnableEventIrp@CKSAutomationThunk@@IEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `1343`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, NTSTATUS *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140002160`
- `0x140002380`

## callees

- `0x1400010f4`
- `0x140002dc8`
- `0x140003ac0`
- `0x14000a008`
- `0x14000a06c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002fad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002fad`
- `ntoskrnl!ProbeForWrite` at `0x140002f32`
- `ntoskrnl!ProbeForWrite` at `0x140002f32`
- `ntoskrnl!ExRaiseStatus` at `0x140002e60`
- `ntoskrnl!ExRaiseStatus` at `0x140002ece`
- `ntoskrnl!ExRaiseStatus` at `0x140002f01`
- `ntoskrnl!ExRaiseStatus` at `0x140002feb`
- `ntoskrnl!ExRaiseStatus` at `0x1400030f1`
- `ntoskrnl!ExRaiseStatus` at `0x140003183`
- `ntoskrnl!ExRaiseStatus` at `0x140003238`
- `ntoskrnl!ExRaiseStatus` at `0x140002e60`
- `ntoskrnl!ExRaiseStatus` at `0x140002ece`
- `ntoskrnl!ExRaiseStatus` at `0x140002f01`
- `ntoskrnl!ExRaiseStatus` at `0x140002feb`
- `ntoskrnl!ExRaiseStatus` at `0x1400030f1`
- `ntoskrnl!ExRaiseStatus` at `0x140003183`
- `ntoskrnl!ExRaiseStatus` at `0x140003238`
- `ntoskrnl!ProbeForRead` at `0x140002e76`
- `ntoskrnl!ProbeForRead` at `0x140002f1c`
- `ntoskrnl!ProbeForRead` at `0x140002e76`
- `ntoskrnl!ProbeForRead` at `0x140002f1c`
- `ntoskrnl!ExAllocatePool2` at `0x140002f4c`
- `ntoskrnl!ExAllocatePool2` at `0x14000312e`
- `ntoskrnl!ExAllocatePool2` at `0x140002f4c`
- `ntoskrnl!ExAllocatePool2` at `0x14000312e`
- `ntoskrnl!ExFreePool` at `0x1400030a0`
- `ntoskrnl!ExFreePool` at `0x1400030c8`
- `ntoskrnl!ExFreePool` at `0x140003276`
- `ntoskrnl!ExFreePool` at `0x14000328c`
- `ntoskrnl!ExFreePool` at `0x1400032ab`
- `ntoskrnl!ExFreePool` at `0x1400030a0`
- `ntoskrnl!ExFreePool` at `0x1400030c8`
- `ntoskrnl!ExFreePool` at `0x140003276`
- `ntoskrnl!ExFreePool` at `0x14000328c`
- `ntoskrnl!ExFreePool` at `0x1400032ab`
- `ks!KsSynchronousIoControlDevice` at `0x140003085`
- `ks!KsSynchronousIoControlDevice` at `0x140003085`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::ThunkEnableEventIrp(__int64 a1, __int64 a2, __int64 a3, NTSTATUS *a4)
{
  unsigned int v6; // edi
  __int64 v7; // rbx
  SIZE_T OutSize; // r15
  unsigned int v10; // esi
  char v11; // r13
  SIZE_T v12; // rcx
  void *OutBuffer; // r13
  _QWORD *PoolWithTag; // rax
  _QWORD *v15; // rbx
  __int64 v16; // r9
  __int64 v17; // rax
  unsigned int i; // edx
  ULONG BytesReturned; // [rsp+44h] [rbp-94h] BYREF
  int ULongFromUser; // [rsp+48h] [rbp-90h]
  int v21; // [rsp+4Ch] [rbp-8Ch]
  __int64 v22; // [rsp+50h] [rbp-88h]
  __int128 v23; // [rsp+58h] [rbp-80h] BYREF
  unsigned int v24; // [rsp+68h] [rbp-70h]
  PVOID P; // [rsp+70h] [rbp-68h]
  PVOID v26; // [rsp+78h] [rbp-60h]
  __int128 v27; // [rsp+80h] [rbp-58h] BYREF
  __int128 v28; // [rsp+90h] [rbp-48h]
  unsigned int NumberOfBytes; // [rsp+E0h] [rbp+8h]
  ULONG NumberOfBytesa; // [rsp+E0h] [rbp+8h]
  unsigned int Size; // [rsp+F0h] [rbp+18h]

  v6 = 0;
  BytesReturned = 0;
  v7 = *(_QWORD *)(a2 + 184);
  v22 = v7;
  OutSize = *(unsigned int *)(v7 + 8);
  if ( (int)OutSize + 16 < (unsigned int)OutSize )
  {
    *a4 = -1073741811;
    return 0;
  }
  if ( *(_QWORD *)(a2 + 24) )
    return 1;
  v10 = 1;
  v21 = 1;
  v11 = 0;
  P = 0;
  v26 = 0;
  v12 = *(unsigned int *)(v7 + 16);
  Size = *(_DWORD *)(v7 + 16);
  NumberOfBytes = (OutSize + 23) & 0xFFFFFFF8;
  if ( (unsigned int)v12 < 0x18 )
    ExRaiseStatus(-1073741306);
  ProbeForRead(*(volatile void **)(v7 + 32), v12, 1u);
  ULongFromUser = RtlReadULongFromUser(*(_QWORD *)(v7 + 32) + 20LL);
  if ( (ULongFromUser & 0xEFFFFFFF) == 1 || (ULongFromUser & 0xEFFFFFFF) == 2 || (ULongFromUser & 0xEFFFFFFF) == 4 )
  {
    if ( (unsigned int)OutSize < 0x10 )
      ExRaiseStatus(-1073741306);
    if ( NumberOfBytes < (int)OutSize + 16 || NumberOfBytes + Size < NumberOfBytes )
      ExRaiseStatus(-1073741306);
    *(_QWORD *)(a2 + 24) = ExAllocatePool2(97, NumberOfBytes + Size, 1886409547);
    *(_DWORD *)(a2 + 16) |= 0x30u;
    v23 = 0;
    RtlCopyFromUser(&v23, *(void **)(a2 + 112), 0x10u);
    v16 = *(_QWORD *)(a2 + 24);
    *(_DWORD *)v16 = v23;
    if ( (_DWORD)v23 == 1 )
    {
      *(_QWORD *)(v16 + 8) = DWORD1(v23);
      for ( i = 0; ; ++i )
      {
        v24 = i;
        if ( i >= 2 )
          break;
        *(_QWORD *)(v16 + 8LL * i + 16) = *((unsigned int *)&v23 + i + 2);
      }
    }
    else
    {
      if ( (_DWORD)v23 != 2 )
        ExRaiseStatus(-1073741811);
      *(_QWORD *)(v16 + 8) = DWORD1(v23);
      *(_QWORD *)(v16 + 16) = *((_QWORD *)&v23 + 1);
    }
    if ( (unsigned int)OutSize > 0x10 )
      RtlCopyFromUser((void *)(v16 + 32), (void *)(*(_QWORD *)(a2 + 112) + 16LL), OutSize - 16);
    RtlCopyFromUser((void *)(NumberOfBytes + *(_QWORD *)(a2 + 24)), *(void **)(v22 + 32), Size);
    *(_DWORD *)(*(_QWORD *)(a2 + 24) + NumberOfBytes + 20LL) = ULongFromUser;
    v17 = *(_QWORD *)(a2 + 184);
    *(_OWORD *)(v17 - 72) = *(_OWORD *)v17;
    *(_OWORD *)(v17 - 56) = *(_OWORD *)(v17 + 16);
    *(_OWORD *)(v17 - 40) = *(_OWORD *)(v17 + 32);
    *(_QWORD *)(v17 - 24) = *(_QWORD *)(v17 + 48);
    *(_BYTE *)(v17 - 69) = 0;
    *(_DWORD *)(*(_QWORD *)(a2 + 184) - 64LL) = OutSize + 16;
    v10 = 5;
    v21 = 5;
  }
  else if ( (ULongFromUser & 0xEFFFFFFF) == 0x400 )
  {
    if ( Size < 0x20 )
      ExRaiseStatus(-1073741306);
    v27 = 0;
    v28 = 0;
    NumberOfBytesa = Size + 8;
    if ( Size + 8 < 0x28 )
      ExRaiseStatus(-1073741306);
    if ( (_DWORD)OutSize )
    {
      ProbeForRead(*(volatile void **)(a2 + 112), OutSize, 1u);
      ProbeForWrite(*(volatile void **)(a2 + 112), OutSize, 1u);
      OutBuffer = (void *)ExAllocatePool2(99, OutSize, 1886409547);
      v26 = OutBuffer;
      RtlCopyFromUser(OutBuffer, *(void **)(a2 + 112), OutSize);
      v7 = v22;
    }
    else
    {
      OutBuffer = 0;
    }
    RtlCopyFromUser(&v27, *(void **)(v7 + 32), 0x20u);
    DWORD1(v28) = ULongFromUser;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, NumberOfBytesa, 0x6271534Bu);
    v15 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, NumberOfBytesa);
    P = v15;
    if ( !v15 )
      ExRaiseStatus(-1073741670);
    *(_OWORD *)v15 = v27;
    v15[2] = v28;
    v15[3] = DWORD2(v28);
    v15[4] = HIDWORD(v28);
    if ( Size > 0x20 )
      RtlCopyFromUser(v15 + 5, (void *)(*(_QWORD *)(v22 + 32) + 32LL), Size - 32LL);
    *a4 = KsSynchronousIoControlDevice(
            *(PFILE_OBJECT *)(v22 + 48),
            0,
            0x2F0007u,
            v15,
            NumberOfBytesa,
            OutBuffer,
            OutSize,
            &BytesReturned);
    *(_QWORD *)(a2 + 56) = BytesReturned;
    ExFreePool(v15);
    P = 0;
    if ( OutBuffer )
    {
      RtlCopyToUser(*(void **)(a2 + 112), OutBuffer, OutSize);
      ExFreePool(OutBuffer);
      v26 = 0;
    }
    v11 = 1;
  }
  if ( v11 )
    return 0;
  if ( *a4 >= 0 )
    return v10;
  return v6;
}

```

## disassembly

```asm
0x140002dc8  mov     rax, rsp
0x140002dcb  mov     [rax+20h], r9
0x140002dcf  mov     [rax+18h], r8d
0x140002dd3  mov     [rax+10h], rdx
0x140002dd7  mov     [rax+8], rcx
0x140002ddb  push    rbx
0x140002ddc  push    rsi
0x140002ddd  push    rdi
0x140002dde  push    r12
0x140002de0  push    r13
0x140002de2  push    r14
0x140002de4  push    r15
0x140002de6  sub     rsp, 0A0h
0x140002ded  mov     r12, r9
0x140002df0  mov     r14, rdx
0x140002df3  xor     edi, edi
0x140002df5  mov     [rsp+0D8h+var_94], edi
0x140002df9  mov     rbx, [rdx+0B8h]
0x140002e00  mov     [rsp+0D8h+var_88], rbx
0x140002e05  mov     r15d, [rbx+8]
0x140002e09  lea     eax, [r15+10h]
0x140002e0d  cmp     eax, r15d
0x140002e10  jb      loc_1400032EA
0x140002e16  cmp     [rdx+18h], rdi
0x140002e1a  jz      short loc_140002E24
0x140002e1c  lea     eax, [rdi+1]
0x140002e1f  jmp     loc_1400032F3
0x140002e24  mov     esi, 1
0x140002e29  mov     [rsp+0D8h+var_8C], esi
0x140002e2d  mov     r13b, dil
0x140002e30  mov     [rsp+0D8h+var_98], dil
0x140002e35  mov     [rsp+0D8h+P], rdi
0x140002e3a  mov     [rsp+0D8h+var_60], rdi
0x140002e3f  mov     ecx, [rbx+10h]
0x140002e42  mov     dword ptr [rsp+0D8h+Size], ecx
0x140002e49  add     eax, 7
0x140002e4c  and     eax, 0FFFFFFF8h
0x140002e4f  mov     dword ptr [rsp+0D8h+NumberOfBytes], eax
0x140002e56  cmp     ecx, 18h
0x140002e59  jnb     short loc_140002E6C
0x140002e5b  mov     ecx, 0C0000206h; Status
0x140002e60  call    cs:__imp_ExRaiseStatus
0x140002e6c  mov     rdx, rcx; Length
0x140002e6f  mov     r8d, esi; Alignment
0x140002e72  mov     rcx, [rbx+20h]; Address
0x140002e76  call    cs:__imp_ProbeForRead
0x140002e7d  nop     dword ptr [rax+rax+00h]
0x140002e82  mov     rcx, [rbx+20h]
0x140002e86  add     rcx, 14h
0x140002e8a  call    RtlReadULongFromUser
0x140002e8f  mov     [rsp+0D8h+var_90], eax
0x140002e93  btr     eax, 1Ch
0x140002e97  sub     eax, 1
0x140002e9a  jz      loc_1400030E6
0x140002ea0  sub     eax, 1
0x140002ea3  jz      loc_1400030E6
0x140002ea9  sub     eax, 2
0x140002eac  jz      loc_1400030E6
0x140002eb2  cmp     eax, 3FCh
0x140002eb7  jnz     loc_14000322E
0x140002ebd  mov     eax, dword ptr [rsp+0D8h+Size]
0x140002ec4  cmp     eax, 20h ; ' '
0x140002ec7  jnb     short loc_140002EDA
0x140002ec9  mov     ecx, 0C0000206h; Status
0x140002ece  call    cs:__imp_ExRaiseStatus
0x140002eda  xorps   xmm0, xmm0
0x140002edd  movups  [rsp+0D8h+var_58], xmm0
0x140002ee5  movups  [rsp+0D8h+var_48], xmm0
0x140002eed  add     eax, 8
0x140002ef0  mov     dword ptr [rsp+0D8h+NumberOfBytes], eax
0x140002ef7  cmp     eax, 28h ; '('
0x140002efa  jnb     short loc_140002F0D
0x140002efc  mov     ecx, 0C0000206h; Status
0x140002f01  call    cs:__imp_ExRaiseStatus
0x140002f0d  test    r15d, r15d
0x140002f10  jz      short loc_140002F76
0x140002f12  mov     r8d, esi; Alignment
0x140002f15  mov     rdx, r15; Length
0x140002f18  mov     rcx, [r14+70h]; Address
0x140002f1c  call    cs:__imp_ProbeForRead
0x140002f23  nop     dword ptr [rax+rax+00h]
0x140002f28  mov     r8d, esi; Alignment
0x140002f2b  mov     rdx, r15; Length
0x140002f2e  mov     rcx, [r14+70h]; Address
0x140002f32  call    cs:__imp_ProbeForWrite
0x140002f39  nop     dword ptr [rax+rax+00h]
0x140002f3e  mov     r8d, 7070534Bh
0x140002f44  mov     rdx, r15
0x140002f47  mov     ecx, 63h ; 'c'
0x140002f4c  call    cs:__imp_ExAllocatePool2
0x140002f53  nop     dword ptr [rax+rax+00h]
0x140002f58  mov     r13, rax
0x140002f5b  mov     [rsp+0D8h+var_60], rax
0x140002f60  mov     r8, r15; Size
0x140002f63  mov     rdx, [r14+70h]; Src
0x140002f67  mov     rcx, rax; void *
0x140002f6a  call    RtlCopyFromUser
0x140002f6f  mov     rbx, [rsp+0D8h+var_88]
0x140002f74  jmp     short loc_140002F79
0x140002f76  mov     r13, rdi
0x140002f79  mov     r8d, 20h ; ' '; Size
0x140002f7f  mov     rdx, [rbx+20h]; Src
0x140002f83  lea     rcx, [rsp+0D8h+var_58]; void *
0x140002f8b  call    RtlCopyFromUser
0x140002f90  mov     ecx, [rsp+0D8h+var_90]
0x140002f94  mov     dword ptr [rsp+0D8h+var_48+4], ecx
0x140002f9b  mov     edx, dword ptr [rsp+0D8h+NumberOfBytes]; NumberOfBytes
0x140002fa2  mov     ecx, 600h; PoolType
0x140002fa7  mov     r8d, 6271534Bh; Tag
0x140002fad  call    cs:__imp_ExAllocatePoolWithTag
0x140002fb4  nop     dword ptr [rax+rax+00h]
0x140002fb9  mov     rbx, rax
0x140002fbc  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140002fc3  jnz     short loc_140002FDC
0x140002fc5  test    rax, rax
0x140002fc8  jz      short loc_140002FDC
0x140002fca  mov     r8d, dword ptr [rsp+0D8h+NumberOfBytes]; Size
0x140002fd2  xor     edx, edx; Val
0x140002fd4  mov     rcx, rax; void *
0x140002fd7  call    memset
0x140002fdc  mov     [rsp+0D8h+P], rbx
0x140002fe1  test    rbx, rbx
0x140002fe4  jnz     short loc_140002FF7
0x140002fe6  mov     ecx, 0C000009Ah; Status
0x140002feb  call    cs:__imp_ExRaiseStatus
0x140002ff7  movups  xmm0, [rsp+0D8h+var_58]
0x140002fff  movups  xmmword ptr [rbx], xmm0
0x140003002  mov     eax, dword ptr [rsp+0D8h+var_48]
0x140003009  mov     [rbx+10h], eax
0x14000300c  mov     eax, dword ptr [rsp+0D8h+var_48+4]
0x140003013  mov     [rbx+14h], eax
0x140003016  mov     eax, dword ptr [rsp+0D8h+var_48+8]
0x14000301d  mov     [rbx+18h], rax
0x140003021  mov     eax, dword ptr [rsp+0D8h+var_48+0Ch]
0x140003028  mov     [rbx+20h], rax
0x14000302c  mov     eax, dword ptr [rsp+0D8h+Size]
0x140003033  cmp     eax, 20h ; ' '
0x140003036  jbe     short loc_140003052
0x140003038  lea     r8, [rax-20h]; Size
0x14000303c  mov     rdx, [rsp+0D8h+var_88]
0x140003041  mov     rdx, [rdx+20h]
0x140003045  add     rdx, 20h ; ' '; Src
0x140003049  lea     rcx, [rbx+28h]; void *
0x14000304d  call    RtlCopyFromUser
0x140003052  lea     rax, [rsp+0D8h+var_94]
0x140003057  mov     [rsp+0D8h+BytesReturned], rax; BytesReturned
0x14000305c  mov     [rsp+0D8h+OutSize], r15d; OutSize
0x140003061  mov     [rsp+0D8h+OutBuffer], r13; OutBuffer
0x140003066  mov     eax, dword ptr [rsp+0D8h+NumberOfBytes]
0x14000306d  mov     [rsp+0D8h+InSize], eax; InSize
0x140003071  mov     r9, rbx; InBuffer
0x140003074  xor     edx, edx; RequestorMode
0x140003076  mov     r8d, 2F0007h; IoControl
0x14000307c  mov     rax, [rsp+0D8h+var_88]
0x140003081  mov     rcx, [rax+30h]; FileObject
0x140003085  call    cs:__imp_KsSynchronousIoControlDevice
0x14000308c  nop     dword ptr [rax+rax+00h]
0x140003091  mov     [r12], eax
0x140003095  mov     eax, [rsp+0D8h+var_94]
0x140003099  mov     [r14+38h], rax
0x14000309d  mov     rcx, rbx; P
0x1400030a0  call    cs:__imp_ExFreePool
0x1400030a7  nop     dword ptr [rax+rax+00h]
0x1400030ac  mov     [rsp+0D8h+P], rdi
0x1400030b1  test    r13, r13
0x1400030b4  jz      short loc_1400030D9
0x1400030b6  mov     r8, r15; Size
0x1400030b9  mov     rdx, r13; Src
0x1400030bc  mov     rcx, [r14+70h]; void *
0x1400030c0  call    RtlCopyToUser
0x1400030c5  mov     rcx, r13; P
0x1400030c8  call    cs:__imp_ExFreePool
0x1400030cf  nop     dword ptr [rax+rax+00h]
0x1400030d4  mov     [rsp+0D8h+var_60], rdi
0x1400030d9  mov     r13b, sil
0x1400030dc  mov     [rsp+0D8h+var_98], sil
0x1400030e1  jmp     loc_14000322E
0x1400030e6  cmp     r15d, 10h
0x1400030ea  jnb     short loc_1400030FD
0x1400030ec  mov     ecx, 0C0000206h; Status
0x1400030f1  call    cs:__imp_ExRaiseStatus
0x1400030fd  mov     ebx, dword ptr [rsp+0D8h+NumberOfBytes]
0x140003104  lea     eax, [r15+10h]
0x140003108  cmp     ebx, eax
0x14000310a  jb      loc_140003233
0x140003110  mov     ecx, dword ptr [rsp+0D8h+Size]
0x140003117  add     ecx, ebx
0x140003119  cmp     ecx, ebx
0x14000311b  jb      loc_140003233
0x140003121  mov     edx, ecx
0x140003123  mov     ecx, 61h ; 'a'
0x140003128  mov     r8d, 7070534Bh
0x14000312e  call    cs:__imp_ExAllocatePool2
0x140003135  nop     dword ptr [rax+rax+00h]
0x14000313a  mov     [r14+18h], rax
0x14000313e  or      dword ptr [r14+10h], 30h
0x140003143  xorps   xmm0, xmm0
0x140003146  movups  [rsp+0D8h+var_80], xmm0
0x14000314b  mov     r8d, 10h; Size
0x140003151  mov     rdx, [r14+70h]; Src
0x140003155  lea     rcx, [rsp+0D8h+var_80]; void *
0x14000315a  call    RtlCopyFromUser
0x14000315f  mov     r9, [r14+18h]
0x140003163  mov     rax, qword ptr [rsp+0D8h+var_80]
0x140003168  mov     [r9], eax
0x14000316b  mov     rax, qword ptr [rsp+0D8h+var_80]
0x140003170  sub     eax, 1
0x140003173  jz      loc_140003244
0x140003179  cmp     eax, 1
0x14000317c  jz      short loc_14000318F
0x14000317e  mov     ecx, 0C000000Dh; Status
0x140003183  call    cs:__imp_ExRaiseStatus
0x14000318f  mov     eax, dword ptr [rsp+0D8h+var_80+4]
0x140003193  mov     [r9+8], rax
0x140003197  mov     eax, dword ptr [rsp+0D8h+var_80+8]
0x14000319b  mov     [r9+10h], eax
0x14000319f  mov     eax, dword ptr [rsp+0D8h+var_80+0Ch]
0x1400031a3  mov     [r9+14h], eax
0x1400031a7  cmp     r15d, 10h
0x1400031ab  jbe     short loc_1400031C2
0x1400031ad  lea     r8, [r15-10h]; Size
0x1400031b1  mov     rdx, [r14+70h]
0x1400031b5  add     rdx, 10h; Src
0x1400031b9  lea     rcx, [r9+20h]; void *
0x1400031bd  call    RtlCopyFromUser
0x1400031c2  mov     r8d, dword ptr [rsp+0D8h+Size]; Size
0x1400031ca  mov     rcx, [r14+18h]
0x1400031ce  add     rcx, rbx; void *
0x1400031d1  mov     rax, [rsp+0D8h+var_88]
0x1400031d6  mov     rdx, [rax+20h]; Src
0x1400031da  call    RtlCopyFromUser
0x1400031df  mov     rax, [r14+18h]
0x1400031e3  mov     ecx, [rsp+0D8h+var_90]
0x1400031e7  mov     [rax+rbx+14h], ecx
0x1400031eb  mov     rax, [r14+0B8h]
0x1400031f2  movups  xmm0, xmmword ptr [rax]
0x1400031f5  movups  xmmword ptr [rax-48h], xmm0
0x1400031f9  movups  xmm1, xmmword ptr [rax+10h]
0x1400031fd  movups  xmmword ptr [rax-38h], xmm1
0x140003201  movups  xmm0, xmmword ptr [rax+20h]
0x140003205  movups  xmmword ptr [rax-28h], xmm0
0x140003209  movsd   xmm1, qword ptr [rax+30h]
0x14000320e  movsd   qword ptr [rax-18h], xmm1
0x140003213  mov     [rax-45h], dil
0x140003217  mov     rax, [r14+0B8h]
0x14000321e  lea     ecx, [r15+10h]
0x140003222  mov     [rax-40h], ecx
0x140003225  mov     esi, 5
0x14000322a  mov     [rsp+0D8h+var_8C], esi
0x14000322e  jmp     loc_1400032DA
0x140003233  mov     ecx, 0C0000206h; Status
0x140003238  call    cs:__imp_ExRaiseStatus
0x140003244  mov     eax, dword ptr [rsp+0D8h+var_80+4]
0x140003248  mov     [r9+8], rax
0x14000324c  mov     edx, edi
0x14000324e  mov     [rsp+0D8h+var_70], edx
0x140003252  cmp     edx, 2
0x140003255  jnb     loc_1400031A7
0x14000325b  mov     ecx, edx
0x14000325d  mov     eax, dword ptr [rsp+rcx*4+0D8h+var_80+8]
0x140003261  mov     [r9+rcx*8+10h], rax
0x140003266  add     edx, esi
0x140003268  jmp     short loc_14000324E
0x14000326a  mov     edi, eax
0x14000326c  mov     rcx, [rsp+0D8h+P]; P
0x140003271  test    rcx, rcx
0x140003274  jz      short loc_140003282
0x140003276  call    cs:__imp_ExFreePool
0x14000327d  nop     dword ptr [rax+rax+00h]
0x140003282  mov     rcx, [rsp+0D8h+var_60]; P
0x140003287  test    rcx, rcx
0x14000328a  jz      short loc_140003298
0x14000328c  call    cs:__imp_ExFreePool
0x140003293  nop     dword ptr [rax+rax+00h]
0x140003298  mov     rbx, [rsp+0D8h+arg_8]
0x1400032a0  cmp     qword ptr [rbx+18h], 0
0x1400032a5  jz      short loc_1400032C3
0x1400032a7  mov     rcx, [rbx+18h]; P
0x1400032ab  call    cs:__imp_ExFreePool
0x1400032b2  nop     dword ptr [rax+rax+00h]
0x1400032b7  mov     qword ptr [rbx+18h], 0
0x1400032bf  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x1400032c3  mov     r12, [rsp+0D8h+arg_18]
0x1400032cb  mov     [r12], edi
0x1400032cf  xor     edi, edi
0x1400032d1  mov     esi, [rsp+0D8h+var_8C]
0x1400032d5  mov     r13b, [rsp+0D8h+var_98]
0x1400032da  test    r13b, r13b
0x1400032dd  jnz     short loc_1400032F1
0x1400032df  cmp     [r12], edi
0x1400032e3  cmovge  edi, esi
0x1400032e6  mov     eax, edi
0x1400032e8  jmp     short loc_1400032F3
0x1400032ea  mov     dword ptr [r9], 0C000000Dh
0x1400032f1  xor     eax, eax
0x1400032f3  add     rsp, 0A0h
0x1400032fa  pop     r15
0x1400032fc  pop     r14
0x1400032fe  pop     r13
0x140003300  pop     r12
  ... truncated ...
```
