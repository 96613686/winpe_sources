# FatSqmAddToStreamEx

- ea: `0x14004ce78`
- end: `0x14004d13d`
- name: `FatSqmAddToStreamEx`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14004d144`

## callees

- `0x14000c230`
- `0x14000c380`
- `0x14000c680`
- `0x14004ce78`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14004d0dd`
- `ntoskrnl!EtwWrite` at `0x14004d0dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d0f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d10b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d0f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d10b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004cf6b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004cf6b`

## pseudocode

```c
__int64 __fastcall FatSqmAddToStreamEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v5; // r9
  unsigned int i; // r8d
  __int64 v7; // rax
  __int64 v9; // rax
  unsigned int v10; // edi
  _DWORD *PoolWithTag; // rax
  _DWORD *v12; // rsi
  _DWORD *v13; // rdi
  unsigned int v14; // r15d
  _WORD *v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // r14d
  unsigned int v18; // ebx
  unsigned int v19; // [rsp+30h] [rbp-99h] BYREF
  ULONG v20; // [rsp+38h] [rbp-91h] BYREF
  int v21; // [rsp+3Ch] [rbp-8Dh] BYREF
  int v22; // [rsp+40h] [rbp-89h] BYREF
  int v23; // [rsp+48h] [rbp-81h] BYREF
  int v24; // [rsp+4Ch] [rbp-7Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[8]; // [rsp+50h] [rbp-79h] BYREF

  v19 = 6;
  v22 = 12545;
  v21 = 17;
  memset(UserData, 0, sizeof(UserData));
  v23 = 0;
  v24 = 0;
  v20 = 0;
  if ( !a4 )
    return 3221225485LL;
  v5 = 0;
  for ( i = 0; i < 6; ++i )
  {
    if ( *(_DWORD *)(a4 + 16LL * i + 4) == 1 )
      goto LABEL_6;
    if ( *(_DWORD *)(a4 + 16LL * i + 4) != 2 )
    {
      if ( *(_DWORD *)(a4 + 16LL * i + 4) != 3 )
        return 3221225485LL;
LABEL_6:
      v7 = 16;
      goto LABEL_7;
    }
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*(_QWORD *)(a4 + 16LL * i + 8) + 2 * v9) );
    v7 = (2 * v9 + 17) & 0xFFFFFFF8LL;
LABEL_7:
    v5 += v7;
  }
  if ( v5 > 0xFFFFFFFF )
    return 2147483653LL;
  v10 = v5;
  v20 = v5;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, (unsigned int)v5, 0x20746146u);
  v12 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( !PoolWithTag )
      return 3221225626LL;
LABEL_16:
    v13 = v12;
    v14 = 0;
    while ( 1 )
    {
      *v13 = *(_DWORD *)(a4 + 16LL * v14 + 4);
      switch ( *(_DWORD *)(a4 + 16LL * v14 + 4) )
      {
        case 1:
          v13[2] = *(_DWORD *)(a4 + 16LL * v14 + 8);
          break;
        case 2:
          v15 = *(_WORD **)(a4 + 16LL * v14 + 8);
          v16 = -1;
          do
            ++v16;
          while ( v15[v16] );
          v17 = (2 * v16 + 17) & 0xFFFFFFF8;
          memmove(v13 + 2, v15, 2LL * (unsigned int)(v16 + 1));
          goto LABEL_28;
        case 3:
          *((_QWORD *)v13 + 1) = *(_QWORD *)(a4 + 16LL * v14 + 8);
          break;
        default:
          ExFreePoolWithTag(v12, 0x20746146u);
          return 3221225485LL;
      }
      v17 = 16;
LABEL_28:
      v13[1] = v17;
      ++v14;
      v13 = (_DWORD *)((char *)v13 + v17);
      if ( v14 >= v19 )
      {
        UserData[0].Ptr = (ULONGLONG)&v21;
        *(_QWORD *)&UserData[0].Size = 4;
        UserData[1].Ptr = (ULONGLONG)&unk_1400172F0;
        *(_QWORD *)&UserData[1].Size = 16;
        UserData[2].Ptr = (ULONGLONG)&v22;
        *(_QWORD *)&UserData[2].Size = 4;
        UserData[3].Ptr = (ULONGLONG)&v23;
        UserData[4].Ptr = (ULONGLONG)&v19;
        UserData[5].Ptr = (ULONGLONG)&v20;
        UserData[6].Size = v20;
        UserData[7].Ptr = (ULONGLONG)&v24;
        *(_QWORD *)&UserData[3].Size = 4;
        *(_QWORD *)&UserData[4].Size = 4;
        *(_QWORD *)&UserData[5].Size = 4;
        UserData[6].Ptr = (ULONGLONG)v12;
        UserData[6].Reserved = 0;
        *(_QWORD *)&UserData[7].Size = 4;
        v18 = EtwWrite(RegHandle, &SQM_ADD_STREAMROW_EX, 0, 8u, UserData);
        ExFreePoolWithTag(v12, 0x20746146u);
        return v18;
      }
    }
  }
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, v10);
    goto LABEL_16;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004ce78  push    rbp
0x14004ce7a  push    rbx
0x14004ce7b  push    rsi
0x14004ce7c  push    rdi
0x14004ce7d  push    r12
0x14004ce7f  push    r13
0x14004ce81  push    r14
0x14004ce83  push    r15
0x14004ce85  lea     rbp, [rsp-1Fh]
0x14004ce8a  sub     rsp, 0E8h
0x14004ce91  mov     rax, cs:__security_cookie
0x14004ce98  xor     rax, rsp
0x14004ce9b  mov     [rbp+57h+var_50], rax
0x14004ce9f  xor     edx, edx; Val
0x14004cea1  mov     [rsp+120h+var_F0], 6
0x14004cea9  mov     r8d, 80h; Size
0x14004ceaf  mov     [rsp+120h+var_E0], 3101h
0x14004ceb7  lea     rcx, [rbp+57h+var_D0]; void *
0x14004cebb  mov     [rsp+120h+var_E4], 11h
0x14004cec3  mov     rbx, r9
0x14004cec6  call    memset
0x14004cecb  xor     r12d, r12d
0x14004cece  mov     [rsp+120h+var_D8], r12d
0x14004ced3  mov     [rbp+57h+var_D4], r12d
0x14004ced7  mov     [rsp+120h+var_E8], r12d
0x14004cedc  test    rbx, rbx
0x14004cedf  jz      loc_14004D117
0x14004cee5  mov     r9d, r12d
0x14004cee8  lea     r13d, [r12+10h]
0x14004ceed  mov     r8d, r12d
0x14004cef0  mov     r10d, 0FFFFFFF8h
0x14004cef6  mov     edx, r8d
0x14004cef9  add     rdx, rdx
0x14004cefc  mov     ecx, [rbx+rdx*8+4]
0x14004cf00  sub     ecx, 1
0x14004cf03  jz      short loc_14004CF13
0x14004cf05  sub     ecx, 1
0x14004cf08  jz      short loc_14004CF36
0x14004cf0a  cmp     ecx, 1
0x14004cf0d  jnz     loc_14004D117
0x14004cf13  mov     rax, r13
0x14004cf16  add     r9, rax
0x14004cf19  inc     r8d
0x14004cf1c  cmp     r8d, 6
0x14004cf20  jb      short loc_14004CEF6
0x14004cf22  mov     eax, 0FFFFFFFFh
0x14004cf27  cmp     r9, rax
0x14004cf2a  jbe     short loc_14004CF56
0x14004cf2c  mov     eax, 80000005h
0x14004cf31  jmp     loc_14004D11C
0x14004cf36  mov     rcx, [rbx+rdx*8+8]
0x14004cf3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004cf3f  inc     rax
0x14004cf42  cmp     [rcx+rax*2], r12w
0x14004cf47  jnz     short loc_14004CF3F
0x14004cf49  lea     rax, ds:11h[rax*2]
0x14004cf51  and     rax, r10
0x14004cf54  jmp     short loc_14004CF16
0x14004cf56  mov     edi, r9d
0x14004cf59  mov     r8d, 20746146h; Tag
0x14004cf5f  mov     edx, r9d; NumberOfBytes
0x14004cf62  mov     ecx, 401h; PoolType
0x14004cf67  mov     [rsp+120h+var_E8], edi
0x14004cf6b  call    cs:__imp_ExAllocatePoolWithTag
0x14004cf72  nop     dword ptr [rax+rax+00h]
0x14004cf77  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x14004cf7e  mov     rsi, rax
0x14004cf81  jnz     short loc_14004CFD4
0x14004cf83  test    rax, rax
0x14004cf86  jz      short loc_14004CFD9
0x14004cf88  mov     r8d, edi; Size
0x14004cf8b  xor     edx, edx; Val
0x14004cf8d  mov     rcx, rax; void *
0x14004cf90  call    memset
0x14004cf95  mov     rdi, rsi
0x14004cf98  mov     r15d, r12d
0x14004cf9b  cmp     [rsp+120h+var_F0], r12d
0x14004cfa0  jbe     loc_14004D03A
0x14004cfa6  mov     ecx, r15d
0x14004cfa9  add     rcx, rcx
0x14004cfac  mov     eax, [rbx+rcx*8+4]
0x14004cfb0  mov     [rdi], eax
0x14004cfb2  mov     edx, [rbx+rcx*8+4]
0x14004cfb6  sub     edx, 1
0x14004cfb9  jz      short loc_14004D018
0x14004cfbb  sub     edx, 1
0x14004cfbe  jz      short loc_14004CFE3
0x14004cfc0  cmp     edx, 1
0x14004cfc3  jnz     loc_14004D103
0x14004cfc9  mov     rax, [rbx+rcx*8+8]
0x14004cfce  mov     [rdi+8], rax
0x14004cfd2  jmp     short loc_14004D01F
0x14004cfd4  test    rsi, rsi
0x14004cfd7  jnz     short loc_14004CF95
0x14004cfd9  mov     eax, 0C000009Ah
0x14004cfde  jmp     loc_14004D11C
0x14004cfe3  mov     rdx, [rbx+rcx*8+8]; Src
0x14004cfe8  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004cfec  inc     rax
0x14004cfef  cmp     [rdx+rax*2], r12w
0x14004cff4  jnz     short loc_14004CFEC
0x14004cff6  lea     r14d, ds:11h[rax*2]
0x14004cffe  mov     ecx, 0FFFFFFF8h
0x14004d003  lea     r8d, [rax+1]
0x14004d007  and     r14d, ecx
0x14004d00a  lea     rcx, [rdi+8]; void *
0x14004d00e  add     r8, r8; Size
0x14004d011  call    memmove
0x14004d016  jmp     short loc_14004D022
0x14004d018  mov     eax, [rbx+rcx*8+8]
0x14004d01c  mov     [rdi+8], eax
0x14004d01f  mov     r14d, r13d
0x14004d022  mov     [rdi+4], r14d
0x14004d026  inc     r15d
0x14004d029  mov     eax, r14d
0x14004d02c  add     rdi, rax
0x14004d02f  cmp     r15d, [rsp+120h+var_F0]
0x14004d034  jb      loc_14004CFA6
0x14004d03a  mov     rcx, cs:RegHandle; RegHandle
0x14004d041  lea     rax, [rsp+120h+var_E4]
0x14004d046  mov     [rbp+57h+var_D0.Ptr], rax
0x14004d04a  lea     rdx, SQM_ADD_STREAMROW_EX; EventDescriptor
0x14004d051  lea     rax, unk_1400172F0
0x14004d058  mov     qword ptr [rbp+57h+var_D0.Size], 4
0x14004d060  mov     [rbp+57h+var_C0], rax
0x14004d064  mov     r9d, 8; UserDataCount
0x14004d06a  lea     rax, [rsp+120h+var_E0]
0x14004d06f  mov     [rbp+57h+var_B8], r13
0x14004d073  mov     [rbp+57h+var_B0], rax
0x14004d077  xor     r8d, r8d; ActivityId
0x14004d07a  lea     rax, [rsp+120h+var_D8]
0x14004d07f  mov     [rbp+57h+var_A8], 4
0x14004d087  mov     [rbp+57h+var_A0], rax
0x14004d08b  lea     rax, [rsp+120h+var_F0]
0x14004d090  mov     [rbp+57h+var_90], rax
0x14004d094  lea     rax, [rsp+120h+var_E8]
0x14004d099  mov     [rbp+57h+var_80], rax
0x14004d09d  mov     eax, [rsp+120h+var_E8]
0x14004d0a1  mov     [rbp+57h+var_68], eax
0x14004d0a4  lea     rax, [rbp+57h+var_D4]
0x14004d0a8  mov     [rbp+57h+var_60], rax
0x14004d0ac  lea     rax, [rbp+57h+var_D0]
0x14004d0b0  mov     [rsp+120h+UserData], rax; UserData
0x14004d0b5  mov     [rbp+57h+var_98], 4
0x14004d0bd  mov     [rbp+57h+var_88], 4
0x14004d0c5  mov     [rbp+57h+var_78], 4
0x14004d0cd  mov     [rbp+57h+var_70], rsi
0x14004d0d1  mov     [rbp+57h+var_64], r12d
0x14004d0d5  mov     [rbp+57h+var_58], 4
0x14004d0dd  call    cs:__imp_EtwWrite
0x14004d0e4  nop     dword ptr [rax+rax+00h]
0x14004d0e9  mov     edx, 20746146h; Tag
0x14004d0ee  mov     rcx, rsi; P
0x14004d0f1  mov     ebx, eax
0x14004d0f3  call    cs:__imp_ExFreePoolWithTag
0x14004d0fa  nop     dword ptr [rax+rax+00h]
0x14004d0ff  mov     eax, ebx
0x14004d101  jmp     short loc_14004D11C
0x14004d103  mov     edx, 20746146h; Tag
0x14004d108  mov     rcx, rsi; P
0x14004d10b  call    cs:__imp_ExFreePoolWithTag
0x14004d112  nop     dword ptr [rax+rax+00h]
0x14004d117  mov     eax, 0C000000Dh
0x14004d11c  mov     rcx, [rbp+57h+var_50]
0x14004d120  xor     rcx, rsp; StackCookie
0x14004d123  call    __security_check_cookie
0x14004d128  add     rsp, 0E8h
0x14004d12f  pop     r15
0x14004d131  pop     r14
0x14004d133  pop     r13
0x14004d135  pop     r12
0x14004d137  pop     rdi
0x14004d138  pop     rsi
0x14004d139  pop     rbx
0x14004d13a  pop     rbp
0x14004d13b  retn
```
