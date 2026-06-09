# CmpRmAnalysisPhase

- ea: `0x140805f74`
- end: `0x1408061ae`
- name: `CmpRmAnalysisPhase`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1408e5618`

## callees

- `0x140805f74`
- `0x140a2ceb8`
- `0x140bb19f0`
- `0x140bfaa50`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1408060f5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1408060f5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14080611b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x14080611b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x14080603e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x14080603e`

## pseudocode

```c
__int64 __fastcall CmpRmAnalysisPhase(__int64 a1, CLFS_LSN a2)
{
  _QWORD *v2; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // r14
  _QWORD *v6; // r15
  NTSTATUS v7; // eax
  int v8; // edi
  __int64 v9; // rax
  _DWORD *v10; // rcx
  __int64 NextElement; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // rdx
  PVOID pvReadContext; // [rsp+50h] [rbp-9h] BYREF
  __int64 v17; // [rsp+58h] [rbp-1h] BYREF
  CLFS_LSN plsnPrevious; // [rsp+60h] [rbp+7h] BYREF
  CLFS_LSN plsnUndoNext; // [rsp+68h] [rbp+Fh] BYREF
  CLFS_LSN plsnRecord; // [rsp+70h] [rbp+17h] BYREF
  CLS_RECORD_TYPE peRecordType; // [rsp+C0h] [rbp+67h] BYREF
  CLFS_LSN plsnFirst; // [rsp+C8h] [rbp+6Fh] BYREF
  ULONG pcbBuffer; // [rsp+D0h] [rbp+77h] BYREF
  PVOID ppvReadBuffer; // [rsp+D8h] [rbp+7Fh] BYREF

  plsnFirst = a2;
  v2 = (_QWORD *)(a1 + 16);
  pvReadContext = 0;
  ppvReadBuffer = 0;
  v4 = *(_QWORD **)(a1 + 16);
  pcbBuffer = 0;
  plsnUndoNext.ullOffset = 0;
  plsnPrevious.ullOffset = 0;
  plsnRecord.ullOffset = 0;
  peRecordType = 0;
  v17 = 0;
  if ( v4 == v2 )
  {
    v5 = 0;
    v6 = 0;
  }
  else
  {
    v4[1] = *(_QWORD *)(a1 + 24);
    **(_QWORD **)(a1 + 24) = *v2;
    v5 = *v2;
    v6 = *(_QWORD **)(*v2 + 8LL);
    v2[1] = v2;
    *v2 = v2;
  }
  v7 = ClfsReadLogRecord(
         *(PVOID *)(a1 + 96),
         &plsnFirst,
         ClfsContextForward,
         &ppvReadBuffer,
         &pcbBuffer,
         &peRecordType,
         &plsnUndoNext,
         &plsnPrevious,
         &pvReadContext);
  v8 = v7;
  while ( v7 >= 0 )
  {
    if ( (peRecordType & 1) != 0 && pcbBuffer >= 0x30 )
    {
      v8 = CmpTransSearchAddTransFromRm(a1, 0, (int)ppvReadBuffer + 16, 1, (__int64)&v17);
      if ( v8 < 0 )
        break;
      v9 = v17;
      if ( !v17 )
      {
        v8 = -1072103422;
        break;
      }
      v10 = ppvReadBuffer;
      if ( *((_DWORD *)ppvReadBuffer + 2) == 16 )
      {
        *(_DWORD *)(v17 + 48) |= 4u;
        v10 = ppvReadBuffer;
      }
      if ( v10[2] == 8 )
      {
        *(_DWORD *)(v9 + 48) |= 2u;
        v10 = ppvReadBuffer;
      }
      if ( v10[2] == 4 )
        *(_DWORD *)(v9 + 48) |= 1u;
    }
    peRecordType = 1;
    v7 = ClfsReadNextLogRecord(
           pvReadContext,
           &ppvReadBuffer,
           &pcbBuffer,
           &peRecordType,
           0,
           &plsnUndoNext,
           &plsnPrevious,
           &plsnRecord);
    v8 = v7;
    if ( v7 == -1073741807 )
    {
      v8 = 0;
LABEL_24:
      v17 = 0;
      while ( 1 )
      {
        NextElement = CmListGetNextElement(v2, &v17, 0);
        v13 = (_QWORD *)NextElement;
        if ( !NextElement )
          goto LABEL_17;
        if ( (*(_DWORD *)(NextElement + 48) & 7) != 1 )
        {
          v14 = *(_QWORD *)NextElement;
          if ( *(_QWORD **)(*v13 + 8LL) != v13 || (v15 = (_QWORD *)v13[1], (_QWORD *)*v15 != v13) )
            __fastfail(3u);
          *v15 = v14;
          *(_QWORD *)(v14 + 8) = v15;
          ExFreePoolWithTag(v13, 0x72544D43u);
          goto LABEL_24;
        }
      }
    }
  }
LABEL_17:
  if ( pvReadContext )
    ClfsTerminateReadLog(pvReadContext);
  if ( v5 )
  {
    *v6 = v2;
    *(_QWORD *)(v5 + 8) = *(_QWORD *)(a1 + 24);
    **(_QWORD **)(a1 + 24) = v5;
    *(_QWORD *)(a1 + 24) = v6;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140805f74  mov     qword ptr [rsp-8+plsnFirst], rdx
0x140805f79  push    rbp
0x140805f7a  push    rbx
0x140805f7b  push    rsi
0x140805f7c  push    rdi
0x140805f7d  push    r14
0x140805f7f  push    r15
0x140805f81  lea     rbp, [rsp-2Fh]
0x140805f86  sub     rsp, 88h
0x140805f8d  lea     rbx, [rcx+10h]
0x140805f91  mov     [rbp+57h+pvReadContext], 0
0x140805f99  mov     rsi, rcx
0x140805f9c  mov     [rbp+57h+ppvReadBuffer], 0
0x140805fa4  mov     rcx, [rbx]
0x140805fa7  mov     [rbp+57h+pcbBuffer], 0
0x140805fae  mov     qword ptr [rbp+57h+var_48], 0
0x140805fb6  mov     qword ptr [rbp+57h+var_50], 0
0x140805fbe  mov     qword ptr [rbp+57h+plsnRecord], 0
0x140805fc6  mov     [rbp+57h+arg_0], 0
0x140805fca  mov     [rbp+57h+var_58], 0
0x140805fd2  cmp     rcx, rbx
0x140805fd5  jnz     short loc_140805FDF
0x140805fd7  xor     r14d, r14d
0x140805fda  xor     r15d, r15d
0x140805fdd  jmp     short loc_140805FFF
0x140805fdf  mov     rax, [rsi+18h]
0x140805fe3  mov     [rcx+8], rax
0x140805fe7  mov     rcx, [rsi+18h]
0x140805feb  mov     rax, [rbx]
0x140805fee  mov     [rcx], rax
0x140805ff1  mov     r14, [rbx]
0x140805ff4  mov     r15, [r14+8]
0x140805ff8  mov     [rbx+8], rbx
0x140805ffc  mov     [rbx], rbx
0x140805fff  mov     rcx, [rsi+60h]; pvMarshalContext
0x140806003  lea     rax, [rbp+57h+pvReadContext]
0x140806007  mov     [rsp+0B0h+ppvReadContext], rax; ppvReadContext
0x14080600c  lea     r9, [rbp+57h+ppvReadBuffer]; ppvReadBuffer
0x140806010  lea     rax, [rbp+57h+var_50]
0x140806014  mov     r8d, 3; peContextMode
0x14080601a  mov     [rsp+0B0h+plsnPrevious], rax; plsnPrevious
0x14080601f  lea     rdx, [rbp+57h+plsnFirst]; plsnFirst
0x140806023  lea     rax, [rbp+57h+var_48]
0x140806027  mov     [rsp+0B0h+plsnUndoNext], rax; plsnUndoNext
0x14080602c  lea     rax, [rbp+57h+arg_0]
0x140806030  mov     [rsp+0B0h+peRecordType], rax; peRecordType
0x140806035  lea     rax, [rbp+57h+pcbBuffer]
0x140806039  mov     [rsp+0B0h+pcbReadBuffer], rax; pcbReadBuffer
0x14080603e  call    cs:__imp_ClfsReadLogRecord
0x140806045  nop     dword ptr [rax+rax+00h]
0x14080604a  mov     edi, eax
0x14080604c  jmp     loc_14080610A
0x140806051  test    [rbp+57h+arg_0], 1
0x140806055  jz      short loc_1408060BD
0x140806057  cmp     [rbp+57h+pcbBuffer], 30h ; '0'
0x14080605b  jb      short loc_1408060BD
0x14080605d  mov     r8, [rbp+57h+ppvReadBuffer]
0x140806061  lea     rax, [rbp+57h+var_58]
0x140806065  xor     edx, edx
0x140806067  mov     [rsp+0B0h+pcbReadBuffer], rax
0x14080606c  add     r8, 10h
0x140806070  mov     rcx, rsi
0x140806073  lea     r9d, [rdx+1]
0x140806077  call    CmpTransSearchAddTransFromRm
0x14080607c  mov     edi, eax
0x14080607e  test    eax, eax
0x140806080  js      loc_140806112
0x140806086  mov     rax, [rbp+57h+var_58]
0x14080608a  test    rax, rax
0x14080608d  jz      loc_140806155
0x140806093  mov     rcx, [rbp+57h+ppvReadBuffer]
0x140806097  cmp     dword ptr [rcx+8], 10h
0x14080609b  jnz     short loc_1408060A5
0x14080609d  or      dword ptr [rax+30h], 4
0x1408060a1  mov     rcx, [rbp+57h+ppvReadBuffer]
0x1408060a5  cmp     dword ptr [rcx+8], 8
0x1408060a9  jnz     short loc_1408060B3
0x1408060ab  or      dword ptr [rax+30h], 2
0x1408060af  mov     rcx, [rbp+57h+ppvReadBuffer]
0x1408060b3  cmp     dword ptr [rcx+8], 4
0x1408060b7  jnz     short loc_1408060BD
0x1408060b9  or      dword ptr [rax+30h], 1
0x1408060bd  mov     rcx, [rbp+57h+pvReadContext]; pvReadContext
0x1408060c1  lea     rax, [rbp+57h+plsnRecord]
0x1408060c5  mov     [rsp+0B0h+plsnPrevious], rax; plsnRecord
0x1408060ca  lea     r9, [rbp+57h+arg_0]; peRecordType
0x1408060ce  lea     rax, [rbp+57h+var_50]
0x1408060d2  mov     [rbp+57h+arg_0], 1
0x1408060d6  mov     [rsp+0B0h+plsnUndoNext], rax; plsnPrevious
0x1408060db  lea     r8, [rbp+57h+pcbBuffer]; pcbBuffer
0x1408060df  lea     rax, [rbp+57h+var_48]
0x1408060e3  mov     [rsp+0B0h+peRecordType], rax; plsnUndoNext
0x1408060e8  lea     rdx, [rbp+57h+ppvReadBuffer]; ppvBuffer
0x1408060ec  mov     [rsp+0B0h+pcbReadBuffer], 0; plsnUser
0x1408060f5  call    cs:__imp_ClfsReadNextLogRecord
0x1408060fc  nop     dword ptr [rax+rax+00h]
0x140806101  mov     edi, eax
0x140806103  cmp     eax, 0C0000011h
0x140806108  jz      short loc_14080615C
0x14080610a  test    eax, eax
0x14080610c  jns     loc_140806051
0x140806112  mov     rcx, [rbp+57h+pvReadContext]; pvCursorContext
0x140806116  test    rcx, rcx
0x140806119  jz      short loc_140806127
0x14080611b  call    cs:__imp_ClfsTerminateReadLog
0x140806122  nop     dword ptr [rax+rax+00h]
0x140806127  test    r14, r14
0x14080612a  jz      short loc_140806142
0x14080612c  mov     [r15], rbx
0x14080612f  mov     rax, [rsi+18h]
0x140806133  mov     [r14+8], rax
0x140806137  mov     rax, [rsi+18h]
0x14080613b  mov     [rax], r14
0x14080613e  mov     [rsi+18h], r15
0x140806142  mov     eax, edi
0x140806144  add     rsp, 88h
0x14080614b  pop     r15
0x14080614d  pop     r14
0x14080614f  pop     rdi
0x140806150  pop     rsi
0x140806151  pop     rbx
0x140806152  pop     rbp
0x140806153  retn
0x140806155  mov     edi, 0C0190002h
0x14080615a  jmp     short loc_140806112
0x14080615c  xor     edi, edi
0x14080615e  mov     [rbp+57h+var_58], rdi
0x140806162  xor     r8d, r8d
0x140806165  lea     rdx, [rbp+57h+var_58]
0x140806169  mov     rcx, rbx
0x14080616c  call    CmListGetNextElement
0x140806171  mov     rcx, rax; P
0x140806174  test    rax, rax
0x140806177  jz      short loc_140806112
0x140806179  mov     eax, [rax+30h]
0x14080617c  and     al, 7
0x14080617e  cmp     al, 1
0x140806180  jz      short loc_140806162
0x140806182  mov     rax, [rcx]
0x140806185  cmp     [rax+8], rcx
0x140806189  jnz     short loc_1408061A7
0x14080618b  mov     rdx, [rcx+8]
0x14080618f  cmp     [rdx], rcx
0x140806192  jnz     short loc_1408061A7
0x140806194  mov     [rdx], rax
0x140806197  mov     [rax+8], rdx
0x14080619b  mov     edx, 72544D43h; Tag
0x1408061a0  call    ExFreePoolWithTag
0x1408061a5  jmp     short loc_14080615E
0x1408061a7  mov     ecx, 3
0x1408061ac  int     29h; Win8: RtlFailFast(ecx)
```
