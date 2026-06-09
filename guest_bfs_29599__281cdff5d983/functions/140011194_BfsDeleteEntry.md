# BfsDeleteEntry

- ea: `0x140011194`
- end: `0x1400113fe`
- name: `BfsDeleteEntry`
- size: `618`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140009d2c`
- `0x14000c7e8`

## callees

- `0x14001093c`
- `0x140011194`
- `0x140011404`
- `0x140011838`
- `0x140011a24`
- `0x140011b1c`
- `0x140011bc8`
- `0x140012c40`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400112c7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400112c7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001136a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400113b1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001136a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400113b1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001121e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001121e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14001123e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14001123e`
- `ntoskrnl!RtlClearBits` at `0x14001132f`
- `ntoskrnl!RtlClearBits` at `0x14001132f`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011317`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011317`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001120d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400112b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001120d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400112b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001124a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011376`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400113bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001124a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011376`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400113bd`

## pseudocode

```c
__int64 __fastcall BfsDeleteEntry(__int64 a1, int a2, const UNICODE_STRING *a3, __int128 *a4)
{
  __int128 v4; // xmm1
  __int64 result; // rax
  PVOID *v8; // rdi
  _DWORD *Entry; // rsi
  int v10; // eax
  volatile signed __int32 *v11; // rcx
  NTSTATUS EntryBlock; // ebx
  ULONG *v13; // r14
  ULONG EntryIndex; // ebx
  ULONG *v15; // [rsp+20h] [rbp-50h] BYREF
  _RTL_BITMAP BitMapHeader; // [rsp+28h] [rbp-48h] BYREF
  __int128 v17; // [rsp+38h] [rbp-38h] BYREF
  UNICODE_STRING v18; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v19[24]; // [rsp+58h] [rbp-18h] BYREF
  PVOID *v20; // [rsp+A0h] [rbp+30h] BYREF
  PVOID *v21; // [rsp+B8h] [rbp+48h] BYREF

  v4 = *a4;
  v20 = 0;
  v17 = v4;
  v18 = 0;
  result = BfsCreateDirectory(a1 + 48, a3, 1, &v20);
  if ( (int)result >= 0 )
  {
    v8 = v20;
    v21 = v20;
    while ( 1 )
    {
      v17 = *(_OWORD *)BfsGetPathComponent(v19, &v17, &v18);
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx(v8, 0);
      Entry = (_DWORD *)BfsFindEntry(v8, &v18);
      ExReleasePushLockSharedEx(v8, 0);
      KeLeaveCriticalRegion();
      if ( !Entry )
        break;
      if ( (unsigned __int16)v17 < 2u )
      {
        LODWORD(v20) = 0;
        LODWORD(BitMapHeader.Buffer) = 0;
        *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
        v15 = 0;
        if ( *Entry != a2 )
        {
          EntryBlock = -1073741788;
LABEL_20:
          v11 = (volatile signed __int32 *)(v8 - 1);
LABEL_16:
          BfsDereferenceTableEntry(v11);
          return (unsigned int)EntryBlock;
        }
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v8, 0);
        EntryBlock = BfsGetEntryBlock(v8, Entry, &v15, &v20);
        if ( EntryBlock < 0 )
        {
          ExReleasePushLockExclusiveEx(v8, 0);
          KeLeaveCriticalRegion();
          goto LABEL_20;
        }
        v13 = v15;
        if ( *Entry == 1 )
        {
          EntryIndex = BfsGetEntryIndex(v15, Entry);
          RtlInitializeBitMap(&BitMapHeader, v13 + 3992, 0x1Eu);
          RtlClearBits(&BitMapHeader, EntryIndex, 1u);
          memset(Entry, 0, 0x214u);
        }
        else
        {
          *(_QWORD *)(Entry + 1) = 0;
        }
        EntryBlock = BfsWriteBlock(a1, (int)v20, v13);
        ExReleasePushLockExclusiveEx(v8, 0);
        KeLeaveCriticalRegion();
        BfsDereferenceTableEntry((volatile signed __int32 *)v8 - 2);
        if ( EntryBlock < 0 )
          return (unsigned int)EntryBlock;
      }
      else
      {
        v10 = BfsCreateDirectory((__int64)v8, &v18, 1, &v21);
        v11 = (volatile signed __int32 *)(v8 - 1);
        EntryBlock = v10;
        if ( v10 < 0 )
          goto LABEL_16;
        BfsDereferenceTableEntry(v11);
        v8 = v21;
      }
      if ( (unsigned __int16)v17 < 2u || v18.Length < 2u )
        return (unsigned int)EntryBlock;
    }
    BfsDereferenceTableEntry((volatile signed __int32 *)v8 - 2);
    return 3221226021LL;
  }
  return result;
}

```

## disassembly

```asm
0x140011194  mov     [rsp-28h+arg_8], rbx
0x140011199  mov     [rsp-28h+arg_10], rsi
0x14001119e  push    rbp
0x14001119f  push    rdi
0x1400111a0  push    r12
0x1400111a2  push    r14
0x1400111a4  push    r15
0x1400111a6  mov     rbp, rsp
0x1400111a9  sub     rsp, 70h
0x1400111ad  movups  xmm1, xmmword ptr [r9]
0x1400111b1  mov     rax, r8
0x1400111b4  mov     [rbp+arg_0], 0
0x1400111bc  mov     r12d, edx
0x1400111bf  lea     r9, [rbp+arg_0]
0x1400111c3  mov     r15, rcx
0x1400111c6  xorps   xmm0, xmm0
0x1400111c9  add     rcx, 30h ; '0'
0x1400111cd  mov     r8d, 1
0x1400111d3  mov     rdx, rax
0x1400111d6  movdqu  [rbp+var_38], xmm1
0x1400111db  movups  [rbp+var_28], xmm0
0x1400111df  call    BfsCreateDirectory
0x1400111e4  test    eax, eax
0x1400111e6  js      loc_1400113E4
0x1400111ec  mov     rdi, [rbp+arg_0]
0x1400111f0  mov     [rbp+arg_18], rdi
0x1400111f4  lea     r8, [rbp+var_28]
0x1400111f8  lea     rdx, [rbp+var_38]
0x1400111fc  lea     rcx, [rbp+var_18]
0x140011200  call    BfsGetPathComponent
0x140011205  movups  xmm1, xmmword ptr [rax]
0x140011208  movdqu  [rbp+var_38], xmm1
0x14001120d  call    cs:__imp_KeEnterCriticalRegion
0x140011214  nop     dword ptr [rax+rax+00h]
0x140011219  xor     edx, edx
0x14001121b  mov     rcx, rdi
0x14001121e  call    cs:__imp_ExAcquirePushLockSharedEx
0x140011225  nop     dword ptr [rax+rax+00h]
0x14001122a  lea     rdx, [rbp+var_28]
0x14001122e  mov     rcx, rdi
0x140011231  call    BfsFindEntry
0x140011236  xor     edx, edx
0x140011238  mov     rcx, rdi
0x14001123b  mov     rsi, rax
0x14001123e  call    cs:__imp_ExReleasePushLockSharedEx
0x140011245  nop     dword ptr [rax+rax+00h]
0x14001124a  call    cs:__imp_KeLeaveCriticalRegion
0x140011251  nop     dword ptr [rax+rax+00h]
0x140011256  test    rsi, rsi
0x140011259  jz      loc_1400113D6
0x14001125f  cmp     word ptr [rbp+var_38], 2
0x140011264  jb      short loc_140011298
0x140011266  lea     r9, [rbp+arg_18]
0x14001126a  mov     r8d, 1
0x140011270  lea     rdx, [rbp+var_28]
0x140011274  mov     rcx, rdi
0x140011277  call    BfsCreateDirectory
0x14001127c  lea     rcx, [rdi-8]; Buffer
0x140011280  mov     ebx, eax
0x140011282  test    eax, eax
0x140011284  js      loc_1400113A3
0x14001128a  call    BfsDereferenceTableEntry
0x14001128f  mov     rdi, [rbp+arg_18]
0x140011293  jmp     loc_14001138F
0x140011298  xor     eax, eax
0x14001129a  mov     dword ptr [rbp+arg_0], 0
0x1400112a1  mov     qword ptr [rbp+BitMapHeader+4], rax
0x1400112a5  mov     qword ptr [rbp+BitMapHeader.SizeOfBitMap], rax
0x1400112a9  mov     [rbp+var_50], rax
0x1400112ad  cmp     [rsi], r12d
0x1400112b0  jnz     loc_1400113CB
0x1400112b6  call    cs:__imp_KeEnterCriticalRegion
0x1400112bd  nop     dword ptr [rax+rax+00h]
0x1400112c2  xor     edx, edx
0x1400112c4  mov     rcx, rdi
0x1400112c7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400112ce  nop     dword ptr [rax+rax+00h]
0x1400112d3  lea     r9, [rbp+arg_0]
0x1400112d7  mov     rdx, rsi
0x1400112da  lea     r8, [rbp+var_50]
0x1400112de  mov     rcx, rdi
0x1400112e1  call    BfsGetEntryBlock
0x1400112e6  mov     ebx, eax
0x1400112e8  test    eax, eax
0x1400112ea  js      loc_1400113AC
0x1400112f0  cmp     dword ptr [rsi], 1
0x1400112f3  mov     r14, [rbp+var_50]
0x1400112f7  jnz     short loc_14001134D
0x1400112f9  mov     rdx, rsi
0x1400112fc  mov     rcx, r14
0x1400112ff  call    BfsGetEntryIndex
0x140011304  lea     rdx, [r14+3E60h]; BitMapBuffer
0x14001130b  mov     r8d, 1Eh; SizeOfBitMap
0x140011311  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x140011315  mov     ebx, eax
0x140011317  call    cs:__imp_RtlInitializeBitMap
0x14001131e  nop     dword ptr [rax+rax+00h]
0x140011323  mov     r8d, 1; NumberToClear
0x140011329  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14001132d  mov     edx, ebx; StartingIndex
0x14001132f  call    cs:__imp_RtlClearBits
0x140011336  nop     dword ptr [rax+rax+00h]
0x14001133b  xor     edx, edx; Val
0x14001133d  mov     r8d, 214h; Size
0x140011343  mov     rcx, rsi; void *
0x140011346  call    memset
0x14001134b  jmp     short loc_140011355
0x14001134d  mov     qword ptr [rsi+4], 0
0x140011355  mov     edx, dword ptr [rbp+arg_0]
0x140011358  mov     r8, r14
0x14001135b  mov     rcx, r15
0x14001135e  call    BfsWriteBlock
0x140011363  xor     edx, edx
0x140011365  mov     rcx, rdi
0x140011368  mov     ebx, eax
0x14001136a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011371  nop     dword ptr [rax+rax+00h]
0x140011376  call    cs:__imp_KeLeaveCriticalRegion
0x14001137d  nop     dword ptr [rax+rax+00h]
0x140011382  lea     rcx, [rdi-8]; Buffer
0x140011386  call    BfsDereferenceTableEntry
0x14001138b  test    ebx, ebx
0x14001138d  js      short loc_1400113A8
0x14001138f  cmp     word ptr [rbp+var_38], 2
0x140011394  jb      short loc_1400113A8
0x140011396  cmp     word ptr [rbp+var_28], 2
0x14001139b  jnb     loc_1400111F4
0x1400113a1  jmp     short loc_1400113A8
0x1400113a3  call    BfsDereferenceTableEntry
0x1400113a8  mov     eax, ebx
0x1400113aa  jmp     short loc_1400113E4
0x1400113ac  xor     edx, edx
0x1400113ae  mov     rcx, rdi
0x1400113b1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400113b8  nop     dword ptr [rax+rax+00h]
0x1400113bd  call    cs:__imp_KeLeaveCriticalRegion
0x1400113c4  nop     dword ptr [rax+rax+00h]
0x1400113c9  jmp     short loc_1400113D0
0x1400113cb  mov     ebx, 0C0000024h
0x1400113d0  lea     rcx, [rdi-8]
0x1400113d4  jmp     short loc_1400113A3
0x1400113d6  lea     rcx, [rdi-8]; Buffer
0x1400113da  call    BfsDereferenceTableEntry
0x1400113df  mov     eax, 0C0000225h
0x1400113e4  lea     r11, [rsp+70h+var_s0]
0x1400113e9  mov     rbx, [r11+38h]
0x1400113ed  mov     rsi, [r11+40h]
0x1400113f1  mov     rsp, r11
0x1400113f4  pop     r15
0x1400113f6  pop     r14
0x1400113f8  pop     r12
0x1400113fa  pop     rdi
0x1400113fb  pop     rbp
0x1400113fc  retn
```
