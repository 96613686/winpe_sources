# FatPinEaRange

- ea: `0x14003685c`
- end: `0x140036a63`
- name: `FatPinEaRange`
- size: `519`
- prototype: `BOOLEAN __fastcall(__int64, struct _FILE_OBJECT *, __int64, __int64, unsigned int, SIZE_T NumberOfBytes, NTSTATUS Status)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140034678`
- `0x1400356f0`
- `0x140035e50`
- `0x140036a6c`

## callees

- `0x14000c380`
- `0x14000c680`
- `0x14003685c`

## import_xrefs

- `ntoskrnl!CcPinRead` at `0x1400369c2`
- `ntoskrnl!CcPinRead` at `0x1400369c2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400368dc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036942`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400368dc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036942`
- `ntoskrnl!ExRaiseStatus` at `0x140036a3e`
- `ntoskrnl!ExRaiseStatus` at `0x140036a56`
- `ntoskrnl!ExRaiseStatus` at `0x140036a3e`
- `ntoskrnl!ExRaiseStatus` at `0x140036a56`

## pseudocode

```c
BOOLEAN __fastcall FatPinEaRange(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        SIZE_T NumberOfBytes,
        NTSTATUS Status)
{
  unsigned int v7; // edi
  unsigned int v10; // eax
  unsigned int v11; // ebp
  char *v12; // r12
  char *PoolWithTag; // rax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  SIZE_T v16; // r14
  PVOID *v17; // rax
  PVOID *Bcb; // r15
  __int64 v19; // r14
  unsigned int v20; // r9d
  ULONG v21; // eax
  BOOLEAN result; // al
  PVOID Src; // [rsp+30h] [rbp-58h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+38h] [rbp-50h] BYREF
  char NumberOfBytesa; // [rsp+B8h] [rbp+30h]

  v7 = NumberOfBytes;
  FileOffset.QuadPart = 0;
  Src = 0;
  if ( !(_DWORD)NumberOfBytes
    || (v10 = *(_DWORD *)(a3 + 24), v11 = a5, a5 >= v10)
    || v10 - a5 < (unsigned int)NumberOfBytes )
  {
    *(_DWORD *)(a1 + 72) = Status;
    ExRaiseStatus(Status);
  }
  NumberOfBytesa = 1;
  v12 = 0;
  if ( v7 + (a5 & 0x3FFFF) > 0x40000 )
  {
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, v7, 0x64746146u);
    v12 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v7);
    *(_QWORD *)a4 = v12;
    *(_BYTE *)(a4 + 18) = 1;
  }
  v14 = a5 & 0xFFF;
  v15 = (v14 + v7 + 4095) >> 12;
  *(_WORD *)(a4 + 16) = v15;
  if ( (unsigned __int16)v15 <= 8u )
  {
    Bcb = (PVOID *)(a4 + 32);
  }
  else
  {
    v16 = 8LL * (unsigned __int16)v15;
    v17 = (PVOID *)ExAllocatePoolWithTag((POOL_TYPE)1041, v16, 0x62746146u);
    Bcb = v17;
    if ( !ExPoolZeroingNativelySupported && v17 )
      memset(v17, 0, v16);
  }
  *(_QWORD *)(a4 + 24) = Bcb;
  LODWORD(v19) = 4096 - v14;
  *(_DWORD *)(a4 + 8) = a5;
  *(_DWORD *)(a4 + 12) = v7;
  do
  {
    v20 = *(_DWORD *)(a1 + 68);
    FileOffset.QuadPart = v11;
    v21 = v7;
    if ( (unsigned int)v19 <= v7 )
      v21 = v19;
    v19 = v21;
    result = CcPinRead(a2, &FileOffset, v21, (v20 >> 1) & 1, Bcb, &Src);
    if ( !result )
    {
      *(_DWORD *)(a1 + 72) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
    ++Bcb;
    if ( *(_BYTE *)(a4 + 18) == 1 )
    {
      result = (unsigned __int8)memmove(v12, Src, (unsigned int)v19);
      v12 += v19;
    }
    v11 += v19;
    v7 -= v19;
    if ( NumberOfBytesa )
    {
      result = 0;
      LODWORD(v19) = 4096;
      NumberOfBytesa = 0;
      if ( !*(_BYTE *)(a4 + 18) )
      {
        result = (unsigned __int8)Src;
        *(_QWORD *)a4 = Src;
      }
    }
  }
  while ( v7 );
  return result;
}

```

## disassembly

```asm
0x14003685c  mov     [rsp+FileObject], rdx
0x140036861  push    rbx
0x140036862  push    rbp
0x140036863  push    rsi
0x140036864  push    rdi
0x140036865  push    r12
0x140036867  push    r13
0x140036869  push    r14
0x14003686b  push    r15
0x14003686d  sub     rsp, 48h
0x140036871  mov     edi, dword ptr [rsp+88h+NumberOfBytes]
0x140036878  xor     r14d, r14d
0x14003687b  mov     qword ptr [rsp+88h+FileOffset], r14
0x140036880  mov     rsi, r9
0x140036883  mov     [rsp+88h+Src], r14
0x140036888  mov     r13, rcx
0x14003688b  test    edi, edi
0x14003688d  jz      loc_140036A4B
0x140036893  mov     eax, [r8+18h]
0x140036897  mov     ebp, [rsp+88h+arg_20]
0x14003689e  cmp     ebp, eax
0x1400368a0  jnb     loc_140036A4B
0x1400368a6  sub     eax, ebp
0x1400368a8  cmp     eax, edi
0x1400368aa  jb      loc_140036A4B
0x1400368b0  mov     eax, ebp
0x1400368b2  mov     byte ptr [rsp+88h+NumberOfBytes], 1
0x1400368ba  and     eax, 3FFFFh
0x1400368bf  mov     r12d, r14d
0x1400368c2  add     eax, edi
0x1400368c4  mov     r15d, 411h
0x1400368ca  cmp     eax, 40000h
0x1400368cf  jbe     short loc_14003690D
0x1400368d1  mov     r8d, 64746146h; Tag
0x1400368d7  mov     edx, edi; NumberOfBytes
0x1400368d9  mov     ecx, r15d; PoolType
0x1400368dc  call    cs:__imp_ExAllocatePoolWithTag
0x1400368e3  nop     dword ptr [rax+rax+00h]
0x1400368e8  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x1400368ef  mov     r12, rax
0x1400368f2  jnz     short loc_140036906
0x1400368f4  test    rax, rax
0x1400368f7  jz      short loc_140036906
0x1400368f9  mov     r8d, edi; Size
0x1400368fc  xor     edx, edx; Val
0x1400368fe  mov     rcx, rax; void *
0x140036901  call    memset
0x140036906  mov     [rsi], r12
0x140036909  mov     byte ptr [rsi+12h], 1
0x14003690d  mov     ebx, ebp
0x14003690f  lea     eax, [rdi+0FFFh]
0x140036915  and     ebx, 0FFFh
0x14003691b  mov     ecx, 8
0x140036920  add     eax, ebx
0x140036922  shr     eax, 0Ch
0x140036925  mov     [rsi+10h], ax
0x140036929  cmp     ax, cx
0x14003692c  jbe     short loc_14003696E
0x14003692e  movzx   r14d, ax
0x140036932  mov     r8d, 62746146h; Tag
0x140036938  shl     r14, 3
0x14003693c  mov     ecx, r15d; PoolType
0x14003693f  mov     rdx, r14; NumberOfBytes
0x140036942  call    cs:__imp_ExAllocatePoolWithTag
0x140036949  nop     dword ptr [rax+rax+00h]
0x14003694e  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140036955  mov     r15, rax
0x140036958  jnz     short loc_140036972
0x14003695a  test    rax, rax
0x14003695d  jz      short loc_140036972
0x14003695f  mov     r8, r14; Size
0x140036962  xor     edx, edx; Val
0x140036964  mov     rcx, rax; void *
0x140036967  call    memset
0x14003696c  jmp     short loc_140036972
0x14003696e  lea     r15, [rsi+20h]
0x140036972  mov     [rsi+18h], r15
0x140036976  mov     r14d, 1000h
0x14003697c  sub     r14d, ebx
0x14003697f  mov     [rsi+8], ebp
0x140036982  mov     [rsi+0Ch], edi
0x140036985  mov     r9d, [r13+44h]
0x140036989  lea     rdx, [rsp+88h+FileOffset]; FileOffset
0x14003698e  mov     rcx, [rsp+88h+FileObject]; FileObject
0x140036996  cmp     r14d, edi
0x140036999  mov     eax, ebp
0x14003699b  mov     qword ptr [rsp+88h+FileOffset], rax
0x1400369a0  mov     eax, edi
0x1400369a2  cmovbe  eax, r14d
0x1400369a6  shr     r9d, 1
0x1400369a9  mov     r14d, eax
0x1400369ac  and     r9d, 1; Flags
0x1400369b0  lea     rax, [rsp+88h+Src]
0x1400369b5  mov     r8d, r14d; Length
0x1400369b8  mov     [rsp+88h+Buffer], rax; Buffer
0x1400369bd  mov     [rsp+88h+Bcb], r15; Bcb
0x1400369c2  call    cs:__imp_CcPinRead
0x1400369c9  nop     dword ptr [rax+rax+00h]
0x1400369ce  test    al, al
0x1400369d0  jz      short loc_140036A35
0x1400369d2  add     r15, 8
0x1400369d6  cmp     byte ptr [rsi+12h], 1
0x1400369da  jnz     short loc_1400369EF
0x1400369dc  mov     rdx, [rsp+88h+Src]; Src
0x1400369e1  mov     r8d, r14d; Size
0x1400369e4  mov     rcx, r12; void *
0x1400369e7  call    memmove
0x1400369ec  add     r12, r14
0x1400369ef  add     ebp, r14d
0x1400369f2  sub     edi, r14d
0x1400369f5  cmp     byte ptr [rsp+88h+NumberOfBytes], 0
0x1400369fd  jz      short loc_140036A1B
0x1400369ff  xor     al, al
0x140036a01  mov     r14d, 1000h
0x140036a07  mov     byte ptr [rsp+88h+NumberOfBytes], al
0x140036a0e  cmp     [rsi+12h], al
0x140036a11  jnz     short loc_140036A1B
0x140036a13  mov     rax, [rsp+88h+Src]
0x140036a18  mov     [rsi], rax
0x140036a1b  test    edi, edi
0x140036a1d  jnz     loc_140036985
0x140036a23  add     rsp, 48h
0x140036a27  pop     r15
0x140036a29  pop     r14
0x140036a2b  pop     r13
0x140036a2d  pop     r12
0x140036a2f  pop     rdi
0x140036a30  pop     rsi
0x140036a31  pop     rbp
0x140036a32  pop     rbx
0x140036a33  retn
0x140036a35  mov     ecx, 0C00000D8h; Status
0x140036a3a  mov     [r13+48h], ecx
0x140036a3e  call    cs:__imp_ExRaiseStatus
0x140036a4b  mov     ecx, [rsp+88h+Status]; Status
0x140036a52  mov     [r13+48h], ecx
0x140036a56  call    cs:__imp_ExRaiseStatus
```
