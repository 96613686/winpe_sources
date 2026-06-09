# FatPrepareWriteDirectoryFile

- ea: `0x140024228`
- end: `0x1400244b6`
- name: `FatPrepareWriteDirectoryFile`
- size: `654`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000363c`
- `0x140028cc0`
- `0x140029774`
- `0x14003062c`
- `0x140030b04`
- `0x140031468`
- `0x140031a40`
- `0x1400333d0`
- `0x140035e50`
- `0x14003bea4`
- `0x14004ab20`

## callees

- `0x1400019b8`
- `0x14000c680`
- `0x140020458`
- `0x140023ad4`
- `0x140023df4`
- `0x140024228`
- `0x14002475c`
- `0x14004707c`

## import_xrefs

- `ntoskrnl!CcPinRead` at `0x1400243cd`
- `ntoskrnl!CcPinRead` at `0x1400243cd`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14002442b`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14002442b`
- `ntoskrnl!CcUnpinData` at `0x140024463`
- `ntoskrnl!CcUnpinData` at `0x14005b739`
- `ntoskrnl!CcUnpinData` at `0x14005b756`
- `ntoskrnl!CcUnpinData` at `0x140024463`
- `ntoskrnl!CcUnpinData` at `0x14005b739`
- `ntoskrnl!CcUnpinData` at `0x14005b756`
- `ntoskrnl!CcSetFileSizes` at `0x1400242ff`
- `ntoskrnl!CcSetFileSizes` at `0x14005b79a`
- `ntoskrnl!CcSetFileSizes` at `0x1400242ff`
- `ntoskrnl!CcSetFileSizes` at `0x14005b79a`
- `ntoskrnl!ExRaiseStatus` at `0x1400242c5`
- `ntoskrnl!ExRaiseStatus` at `0x1400243e6`
- `ntoskrnl!ExRaiseStatus` at `0x1400242c5`
- `ntoskrnl!ExRaiseStatus` at `0x1400243e6`

## pseudocode

```c
_DWORD *__fastcall FatPrepareWriteDirectoryFile(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        ULONG a4,
        PVOID *a5,
        PVOID *a6,
        __int64 a7,
        char a8,
        _DWORD *a9)
{
  union _LARGE_INTEGER v10; // r13
  __int64 v13; // r9
  _DWORD *v14; // rsi
  union _LARGE_INTEGER v15; // r12
  unsigned int v16; // r13d
  __int64 v17; // rcx
  unsigned int v18; // r10d
  ULONG v19; // esi
  _DWORD *result; // rax
  PVOID BcbVoid; // [rsp+40h] [rbp-58h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+48h] [rbp-50h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-48h] BYREF
  int v24; // [rsp+B0h] [rbp+18h]
  char v25; // [rsp+D0h] [rbp+38h]

  v10.QuadPart = a3;
  v25 = 0;
  BcbVoid = 0;
  Buffer = 0;
  v24 = 4096;
  *a5 = 0;
  *a6 = 0;
  FatOpenDirectoryFile(a1);
  FileOffset = v10;
  v14 = (_DWORD *)(a2 + 24);
  v15.QuadPart = *(unsigned int *)(a2 + 24);
  v16 = a4 + v10.LowPart;
  if ( v16 > v15.LowPart )
  {
    if ( *(_WORD *)a2 == 1284 && *(_BYTE *)(*(_QWORD *)(a2 + 184) + 376LL) != 32 )
    {
      *(_DWORD *)(a1 + 72) = -1073741697;
      ExRaiseStatus(-1073741697);
    }
    FatAddFileAllocation(a1);
    *(_DWORD *)(a2 + 32) = *v14;
    CcSetFileSizes(*(PFILE_OBJECT *)(a2 + 344), (PCC_FILE_SIZES)(a2 + 24));
    FatCheckFreeDirentBitmap(v17, a2);
    v25 = 1;
    FileOffset = v15;
    a4 = *v14 - v15.LowPart;
  }
  while ( a4 )
  {
    BcbVoid = 0;
    v18 = v24;
    if ( FileOffset.QuadPart > v16 )
      v18 = 0x40000;
    v24 = v18;
    if ( FileOffset.QuadPart / v18 == (FileOffset.QuadPart + a4 - 1LL) / v18 )
      v19 = a4;
    else
      v19 = v18 - (FileOffset.LowPart & (v18 - 1));
    if ( !CcPinRead(*(PFILE_OBJECT *)(a2 + 344), &FileOffset, v19, (*(_DWORD *)(a1 + 68) >> 1) & 1, &BcbVoid, &Buffer) )
    {
      *(_DWORD *)(a1 + 72) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
    if ( !*a6 )
    {
      *a6 = Buffer;
      *a5 = BcbVoid;
    }
    if ( v25 )
    {
      memset(Buffer, 0, v19);
      CcSetDirtyPinnedData(BcbVoid, 0);
    }
    a4 -= v19;
    FileOffset.QuadPart += v19;
    if ( *a5 != BcbVoid )
    {
      FatRepinBcb(a1);
      if ( BcbVoid )
      {
        CcUnpinData(BcbVoid);
        BcbVoid = 0;
      }
    }
  }
  LOBYTE(v13) = a8;
  FatSetDirtyBcb(a1, *a5, *(_QWORD *)(a2 + 184), v13);
  result = a9;
  *a9 = 0;
  return result;
}

```

## disassembly

```asm
0x140024228  mov     rax, rsp
0x14002422b  mov     [rax+10h], rdx
0x14002422f  mov     [rax+8], rcx
0x140024233  push    rbx
0x140024234  push    rsi
0x140024235  push    rdi
0x140024236  push    r12
0x140024238  push    r13
0x14002423a  push    r14
0x14002423c  push    r15
0x14002423e  sub     rsp, 60h
0x140024242  mov     edi, r9d
0x140024245  mov     r13d, r8d
0x140024248  mov     rbx, rdx
0x14002424b  mov     r14, rcx
0x14002424e  xor     ecx, ecx
0x140024250  mov     [rax+38h], cl
0x140024253  mov     [rax-50h], rcx
0x140024257  mov     [rax-64h], ecx
0x14002425a  mov     [rax-68h], cl
0x14002425d  mov     [rax-58h], rcx
0x140024261  mov     [rax-48h], rcx
0x140024265  mov     dword ptr [rax+18h], 1000h
0x14002426c  mov     r15, [rsp+98h+arg_20]
0x140024274  mov     [r15], rcx
0x140024277  mov     rax, [rsp+98h+arg_28]
0x14002427f  mov     [rax], rcx
0x140024282  mov     rcx, r14
0x140024285  call    FatOpenDirectoryFile
0x14002428a  mov     qword ptr [rsp+98h+FileOffset], r13
0x14002428f  lea     rsi, [rbx+18h]
0x140024293  mov     r12d, [rsi]
0x140024296  add     r13d, edi
0x140024299  cmp     r13d, r12d
0x14002429c  jbe     loc_14002432C
0x1400242a2  mov     eax, 504h
0x1400242a7  cmp     [rbx], ax
0x1400242aa  jnz     short loc_1400242D1
0x1400242ac  mov     rax, [rbx+0B8h]
0x1400242b3  cmp     byte ptr [rax+178h], 20h ; ' '
0x1400242ba  jz      short loc_1400242D1
0x1400242bc  mov     ecx, 0C000007Fh; Status
0x1400242c1  mov     [r14+48h], ecx
0x1400242c5  call    cs:__imp_ExRaiseStatus
0x1400242d1  mov     [rsp+98h+var_64], r12d
0x1400242d6  mov     r9d, r13d
0x1400242d9  mov     r8, [rbx+158h]
0x1400242e0  mov     rdx, rbx
0x1400242e3  mov     rcx, r14
0x1400242e6  call    FatAddFileAllocation
0x1400242eb  mov     [rsp+98h+var_68], 1
0x1400242f0  mov     eax, [rsi]
0x1400242f2  mov     [rbx+20h], eax
0x1400242f5  mov     rdx, rsi; FileSizes
0x1400242f8  mov     rcx, [rbx+158h]; FileObject
0x1400242ff  call    cs:__imp_CcSetFileSizes
0x140024306  nop     dword ptr [rax+rax+00h]
0x14002430b  mov     rdx, rbx
0x14002430e  call    FatCheckFreeDirentBitmap
0x140024313  mov     [rsp+98h+arg_30], 1
0x14002431b  mov     qword ptr [rsp+98h+FileOffset], r12
0x140024320  mov     edi, [rsi]
0x140024322  sub     edi, r12d
0x140024325  mov     [rsp+98h+arg_18], edi
0x14002432c  mov     r12b, [rsp+98h+arg_30]
0x140024334  test    edi, edi
0x140024336  jz      loc_14002447D
0x14002433c  mov     [rsp+98h+BcbVoid], 0
0x140024345  mov     eax, r13d
0x140024348  mov     r10d, [rsp+98h+arg_10]
0x140024350  mov     edx, 40000h
0x140024355  mov     rcx, qword ptr [rsp+98h+FileOffset]
0x14002435a  cmp     rcx, rax
0x14002435d  cmovg   r10d, edx
0x140024361  mov     [rsp+98h+arg_10], r10d
0x140024369  mov     [rsp+98h+var_60], r10d
0x14002436e  mov     r9d, r10d
0x140024371  mov     eax, edi
0x140024373  dec     rax
0x140024376  add     rax, rcx
0x140024379  cqo
0x14002437b  idiv    r9
0x14002437e  mov     r8, rax
0x140024381  mov     rax, rcx
0x140024384  cqo
0x140024386  idiv    r9
0x140024389  cmp     rax, r8
0x14002438c  jnz     short loc_140024392
0x14002438e  mov     esi, edi
0x140024390  jmp     short loc_14002439F
0x140024392  lea     eax, [r10-1]
0x140024396  and     eax, dword ptr [rsp+98h+FileOffset]
0x14002439a  mov     esi, r10d
0x14002439d  sub     esi, eax
0x14002439f  mov     r9d, [r14+44h]
0x1400243a3  shr     r9d, 1
0x1400243a6  and     r9d, 1; Flags
0x1400243aa  lea     rax, [rsp+98h+var_48]
0x1400243af  mov     [rsp+98h+Buffer], rax; Buffer
0x1400243b4  lea     rax, [rsp+98h+BcbVoid]
0x1400243b9  mov     [rsp+98h+Bcb], rax; Bcb
0x1400243be  mov     r8d, esi; Length
0x1400243c1  lea     rdx, [rsp+98h+FileOffset]; FileOffset
0x1400243c6  mov     rcx, [rbx+158h]; FileObject
0x1400243cd  call    cs:__imp_CcPinRead
0x1400243d4  nop     dword ptr [rax+rax+00h]
0x1400243d9  test    al, al
0x1400243db  jnz     short loc_1400243F2
0x1400243dd  mov     ecx, 0C00000D8h; Status
0x1400243e2  mov     [r14+48h], ecx
0x1400243e6  call    cs:__imp_ExRaiseStatus
0x1400243f2  mov     rcx, [rsp+98h+arg_28]
0x1400243fa  cmp     qword ptr [rcx], 0
0x1400243fe  jnz     short loc_140024410
0x140024400  mov     rax, [rsp+98h+var_48]
0x140024405  mov     [rcx], rax
0x140024408  mov     rax, [rsp+98h+BcbVoid]
0x14002440d  mov     [r15], rax
0x140024410  test    r12b, r12b
0x140024413  jz      short loc_140024437
0x140024415  mov     r8d, esi; Size
0x140024418  xor     edx, edx; Val
0x14002441a  mov     rcx, [rsp+98h+var_48]; void *
0x14002441f  call    memset
0x140024424  xor     edx, edx; Lsn
0x140024426  mov     rcx, [rsp+98h+BcbVoid]; BcbVoid
0x14002442b  call    cs:__imp_CcSetDirtyPinnedData
0x140024432  nop     dword ptr [rax+rax+00h]
0x140024437  sub     edi, esi
0x140024439  mov     [rsp+98h+arg_18], edi
0x140024440  mov     eax, esi
0x140024442  add     qword ptr [rsp+98h+FileOffset], rax
0x140024447  mov     rdx, [rsp+98h+BcbVoid]
0x14002444c  cmp     [r15], rdx
0x14002444f  jz      short loc_140024478
0x140024451  mov     rcx, r14
0x140024454  call    FatRepinBcb
0x140024459  mov     rcx, [rsp+98h+BcbVoid]; Bcb
0x14002445e  test    rcx, rcx
0x140024461  jz      short loc_140024478
0x140024463  call    cs:__imp_CcUnpinData
0x14002446a  nop     dword ptr [rax+rax+00h]
0x14002446f  mov     [rsp+98h+BcbVoid], 0
0x140024478  jmp     loc_140024334
0x14002447d  mov     r9b, [rsp+98h+arg_38]
0x140024485  mov     r8, [rbx+0B8h]
0x14002448c  mov     rdx, [r15]
0x14002448f  mov     rcx, r14
0x140024492  call    FatSetDirtyBcb
0x140024497  mov     rax, [rsp+98h+arg_40]
0x14002449f  mov     dword ptr [rax], 0
0x1400244a5  add     rsp, 60h
0x1400244a9  pop     r15
0x1400244ab  pop     r14
0x1400244ad  pop     r13
0x1400244af  pop     r12
0x1400244b1  pop     rdi
0x1400244b2  pop     rsi
0x1400244b3  pop     rbx
0x1400244b4  retn
0x14005b712  push    rbx
0x14005b714  push    rbp
0x14005b715  sub     rsp, 38h
0x14005b719  mov     rbp, rdx
0x14005b71c  test    cl, cl
0x14005b71e  jz      loc_14005B7A7
0x14005b724  mov     rcx, [rbp+40h]; Bcb
0x14005b728  mov     rbx, [rbp+0C0h]
0x14005b72f  cmp     [rbx], rcx
0x14005b732  jz      short loc_14005B74D
0x14005b734  test    rcx, rcx
0x14005b737  jz      short loc_14005B74D
0x14005b739  call    cs:__imp_CcUnpinData
0x14005b740  nop     dword ptr [rax+rax+00h]
0x14005b745  mov     qword ptr [rbp+40h], 0
0x14005b74d  cmp     qword ptr [rbx], 0
0x14005b751  jz      short loc_14005B769
0x14005b753  mov     rcx, [rbx]; Bcb
0x14005b756  call    cs:__imp_CcUnpinData
0x14005b75d  nop     dword ptr [rax+rax+00h]
0x14005b762  mov     qword ptr [rbx], 0
0x14005b769  cmp     byte ptr [rbp+30h], 1
0x14005b76d  jnz     short loc_14005B7A7
0x14005b76f  mov     r8d, [rbp+34h]
0x14005b773  mov     rbx, [rbp+0A8h]
0x14005b77a  mov     rdx, rbx
0x14005b77d  mov     rcx, [rbp+0A0h]
0x14005b784  call    FatTruncateFileAllocation
0x14005b789  mov     eax, [rbx+18h]
0x14005b78c  mov     [rbx+20h], eax
0x14005b78f  lea     rdx, [rbx+18h]; FileSizes
0x14005b793  mov     rcx, [rbx+158h]; FileObject
0x14005b79a  call    cs:__imp_CcSetFileSizes
0x14005b7a1  nop     dword ptr [rax+rax+00h]
0x14005b7a6  nop
0x14005b7a7  add     rsp, 38h
0x14005b7ab  pop     rbp
0x14005b7ac  pop     rbx
0x14005b7ad  retn
```
