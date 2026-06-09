# FatFlushFat

- ea: `0x14003e4b4`
- end: `0x14003e786`
- name: `FatFlushFat`
- size: `722`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140005a94`
- `0x140024bd4`
- `0x14002c234`
- `0x14003dba0`
- `0x14003e94c`
- `0x140042ec8`
- `0x14004af08`

## callees

- `0x140005288`
- `0x14003e4b4`
- `0x14004a37c`

## import_xrefs

- `ntoskrnl!CcRepinBcb` at `0x14003e5e2`
- `ntoskrnl!CcRepinBcb` at `0x14003e724`
- `ntoskrnl!CcRepinBcb` at `0x14003e5e2`
- `ntoskrnl!CcRepinBcb` at `0x14003e724`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x14003e60b`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x14003e74d`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x14003e60b`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x14003e74d`
- `ntoskrnl!CcPinRead` at `0x14003e5ba`
- `ntoskrnl!CcPinRead` at `0x14003e6fc`
- `ntoskrnl!CcPinRead` at `0x14003e5ba`
- `ntoskrnl!CcPinRead` at `0x14003e6fc`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14003e5d1`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14003e713`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14003e5d1`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14003e713`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005ebcf`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005ebcf`
- `ntoskrnl!CcUnpinData` at `0x14003e5f3`
- `ntoskrnl!CcUnpinData` at `0x14003e735`
- `ntoskrnl!CcUnpinData` at `0x14003e5f3`
- `ntoskrnl!CcUnpinData` at `0x14003e735`
- `ntoskrnl!ExRaiseStatus` at `0x14003e6b9`
- `ntoskrnl!ExRaiseStatus` at `0x14003e6b9`

## pseudocode

```c
__int64 __fastcall FatFlushFat(__int64 a1, __int64 a2)
{
  unsigned int Status; // esi
  int v6; // eax
  unsigned int v7; // r14d
  unsigned int v8; // r15d
  int v9; // r9d
  union _LARGE_INTEGER v10; // rdx
  int v11; // r8d
  int v12; // eax
  PVOID BcbVoid; // [rsp+38h] [rbp-50h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+40h] [rbp-48h] BYREF
  PVOID Buffer; // [rsp+48h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+50h] [rbp-38h] BYREF

  BcbVoid = 0;
  Buffer = 0;
  IoStatus = 0;
  FileOffset.QuadPart = 0;
  if ( (*(_DWORD *)(a2 + 200) & 0x4000) != 0 )
    return 0;
  FatVerifyVcb(a1, a2);
  if ( *(_DWORD *)(a2 + 204) != 1 )
    return 3221225624LL;
  Status = 0;
  if ( *(_BYTE *)(a2 + 376) == 12 )
  {
    v9 = *(unsigned __int16 *)(a2 + 288);
    v10.QuadPart = v9 * (unsigned int)*(unsigned __int16 *)(a2 + 292);
    FileOffset = v10;
    v11 = *(unsigned __int16 *)(a2 + 302);
    if ( (_WORD)v11 )
      v12 = *(unsigned __int16 *)(a2 + 302);
    else
      v12 = *(_DWORD *)(a2 + 316);
    if ( ((v10.QuadPart ^ (v10.QuadPart + (unsigned int)(v9 * v12) - 1LL)) & 0xFFFFFFFFFFFC0000uLL) != 0 )
    {
      *(_DWORD *)(a1 + 72) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
    if ( !(_WORD)v11 )
      v11 = *(_DWORD *)(a2 + 316);
    if ( CcPinRead(*(PFILE_OBJECT *)(a2 + 728), &FileOffset, v9 * v11, 9u, &BcbVoid, &Buffer) )
    {
      CcSetDirtyPinnedData(BcbVoid, 0);
      CcRepinBcb(BcbVoid);
      CcUnpinData(BcbVoid);
      CcUnpinRepinnedBcb(BcbVoid, 1u, &IoStatus);
      if ( IoStatus.Status < 0 )
        return (unsigned int)IoStatus.Status;
    }
  }
  else
  {
    v6 = *(unsigned __int16 *)(a2 + 302);
    if ( !(_WORD)v6 )
      v6 = *(_DWORD *)(a2 + 316);
    v7 = (*(unsigned __int16 *)(a2 + 288) * (v6 + (unsigned int)*(unsigned __int16 *)(a2 + 292)) + 4095) >> 12;
    v8 = 0;
    FileOffset.QuadPart = 0;
    while ( v8 < v7 )
    {
      if ( CcPinRead(*(PFILE_OBJECT *)(a2 + 728), &FileOffset, 0x1000u, 9u, &BcbVoid, &Buffer) )
      {
        CcSetDirtyPinnedData(BcbVoid, 0);
        CcRepinBcb(BcbVoid);
        CcUnpinData(BcbVoid);
        CcUnpinRepinnedBcb(BcbVoid, 1u, &IoStatus);
        if ( IoStatus.Status < 0 )
          Status = IoStatus.Status;
      }
      ++v8;
      FileOffset.LowPart += 4096;
    }
  }
  return Status;
}

```

## disassembly

```asm
0x14003e4b4  mov     rax, rsp
0x14003e4b7  mov     [rax+10h], rdx
0x14003e4bb  mov     [rax+8], rcx
0x14003e4bf  push    rbx
0x14003e4c0  push    rsi
0x14003e4c1  push    rdi
0x14003e4c2  push    r14
0x14003e4c4  push    r15
0x14003e4c6  sub     rsp, 60h
0x14003e4ca  mov     rbx, rdx
0x14003e4cd  mov     r14, rcx
0x14003e4d0  xor     edi, edi
0x14003e4d2  mov     [rax-50h], rdi
0x14003e4d6  mov     [rax-40h], rdi
0x14003e4da  xorps   xmm0, xmm0
0x14003e4dd  movups  xmmword ptr [rax-38h], xmm0
0x14003e4e1  mov     [rax-48h], rdi
0x14003e4e5  mov     eax, [rdx+0C8h]
0x14003e4eb  bt      eax, 0Eh
0x14003e4ef  jnb     short loc_14003E4F8
0x14003e4f1  xor     eax, eax
0x14003e4f3  jmp     loc_14003E779
0x14003e4f8  call    FatVerifyVcb
0x14003e4fd  jmp     short loc_14003E519
0x14003e4ff  mov     r14, [rsp+88h+arg_0]
0x14003e507  mov     dword ptr [r14+48h], 0
0x14003e50f  xor     edi, edi
0x14003e511  mov     rbx, [rsp+88h+arg_8]
0x14003e519  cmp     dword ptr [rbx+0CCh], 1
0x14003e520  jz      short loc_14003E52C
0x14003e522  mov     eax, 0C0000098h
0x14003e527  jmp     loc_14003E779
0x14003e52c  mov     esi, edi
0x14003e52e  cmp     byte ptr [rbx+178h], 0Ch
0x14003e535  jz      loc_14003E667
0x14003e53b  movzx   eax, word ptr [rbx+12Eh]
0x14003e542  movzx   ecx, word ptr [rbx+120h]
0x14003e549  test    ax, ax
0x14003e54c  jnz     short loc_14003E554
0x14003e54e  mov     eax, [rbx+13Ch]
0x14003e554  movzx   r14d, word ptr [rbx+124h]
0x14003e55c  add     r14d, eax
0x14003e55f  imul    r14d, ecx
0x14003e563  add     r14d, 0FFFh
0x14003e56a  shr     r14d, 0Ch
0x14003e56e  mov     [rsp+88h+arg_18], r14d
0x14003e576  mov     r15d, edi
0x14003e579  mov     [rsp+88h+arg_10], edi
0x14003e580  mov     qword ptr [rsp+88h+FileOffset], rdi
0x14003e585  cmp     r15d, r14d
0x14003e588  jnb     loc_14003E777
0x14003e58e  lea     rax, [rsp+88h+var_40]
0x14003e593  mov     [rsp+88h+Buffer], rax; Buffer
0x14003e598  lea     rax, [rsp+88h+BcbVoid]
0x14003e59d  mov     [rsp+88h+Bcb], rax; Bcb
0x14003e5a2  mov     r9d, 9; Flags
0x14003e5a8  mov     r8d, 1000h; Length
0x14003e5ae  lea     rdx, [rsp+88h+FileOffset]; FileOffset
0x14003e5b3  mov     rcx, [rbx+2D8h]; FileObject
0x14003e5ba  call    cs:__imp_CcPinRead
0x14003e5c1  nop     dword ptr [rax+rax+00h]
0x14003e5c6  test    al, al
0x14003e5c8  jz      short loc_14003E624
0x14003e5ca  xor     edx, edx; Lsn
0x14003e5cc  mov     rcx, [rsp+88h+BcbVoid]; BcbVoid
0x14003e5d1  call    cs:__imp_CcSetDirtyPinnedData
0x14003e5d8  nop     dword ptr [rax+rax+00h]
0x14003e5dd  mov     rcx, [rsp+88h+BcbVoid]; Bcb
0x14003e5e2  call    cs:__imp_CcRepinBcb
0x14003e5e9  nop     dword ptr [rax+rax+00h]
0x14003e5ee  mov     rcx, [rsp+88h+BcbVoid]; Bcb
0x14003e5f3  call    cs:__imp_CcUnpinData
0x14003e5fa  nop     dword ptr [rax+rax+00h]
0x14003e5ff  lea     r8, [rsp+88h+IoStatus]; IoStatus
0x14003e604  mov     dl, 1; WriteThrough
0x14003e606  mov     rcx, [rsp+88h+BcbVoid]; Bcb
0x14003e60b  call    cs:__imp_CcUnpinRepinnedBcb
0x14003e612  nop     dword ptr [rax+rax+00h]
0x14003e617  cmp     dword ptr [rsp+88h+IoStatus], edi
0x14003e61b  cmovl   esi, dword ptr [rsp+88h+IoStatus]
0x14003e620  mov     [rsp+88h+var_58], esi
0x14003e624  jmp     short loc_14003E64F
0x14003e626  mov     rax, [rsp+88h+arg_0]
0x14003e62e  mov     esi, [rax+48h]
0x14003e631  mov     [rsp+88h+var_58], esi
0x14003e635  xor     edi, edi
0x14003e637  mov     rbx, [rsp+88h+arg_8]
0x14003e63f  mov     r14d, [rsp+88h+arg_18]
0x14003e647  mov     r15d, [rsp+88h+arg_10]
0x14003e64f  inc     r15d
0x14003e652  mov     [rsp+88h+arg_10], r15d
0x14003e65a  add     dword ptr [rsp+88h+FileOffset], 1000h
0x14003e662  jmp     loc_14003E585
0x14003e667  movzx   r9d, word ptr [rbx+120h]
0x14003e66f  movzx   edx, word ptr [rbx+124h]
0x14003e676  imul    edx, r9d
0x14003e67a  mov     qword ptr [rsp+88h+FileOffset], rdx
0x14003e67f  movzx   r8d, word ptr [rbx+12Eh]
0x14003e687  test    r8w, r8w
0x14003e68b  jnz     short loc_14003E695
0x14003e68d  mov     eax, [rbx+13Ch]
0x14003e693  jmp     short loc_14003E698
0x14003e695  mov     eax, r8d
0x14003e698  imul    eax, r9d
0x14003e69c  mov     ecx, eax
0x14003e69e  dec     rcx
0x14003e6a1  add     rcx, rdx
0x14003e6a4  xor     rcx, rdx
0x14003e6a7  test    rcx, 0FFFFFFFFFFFC0000h
0x14003e6ae  jz      short loc_14003E6C5
0x14003e6b0  mov     ecx, 0C0000102h; Status
0x14003e6b5  mov     [r14+48h], ecx
0x14003e6b9  call    cs:__imp_ExRaiseStatus
0x14003e6c5  test    r8w, r8w
0x14003e6c9  jnz     short loc_14003E6D2
0x14003e6cb  mov     r8d, [rbx+13Ch]
0x14003e6d2  imul    r8d, r9d; Length
0x14003e6d6  lea     rax, [rsp+88h+var_40]
0x14003e6db  mov     [rsp+88h+Buffer], rax; Buffer
0x14003e6e0  lea     rax, [rsp+88h+BcbVoid]
0x14003e6e5  mov     [rsp+88h+Bcb], rax; Bcb
0x14003e6ea  mov     r9d, 9; Flags
0x14003e6f0  lea     rdx, [rsp+88h+FileOffset]; FileOffset
0x14003e6f5  mov     rcx, [rbx+2D8h]; FileObject
0x14003e6fc  call    cs:__imp_CcPinRead
0x14003e703  nop     dword ptr [rax+rax+00h]
0x14003e708  test    al, al
0x14003e70a  jz      short loc_14003E766
0x14003e70c  xor     edx, edx; Lsn
0x14003e70e  mov     rcx, [rsp+88h+BcbVoid]; BcbVoid
0x14003e713  call    cs:__imp_CcSetDirtyPinnedData
0x14003e71a  nop     dword ptr [rax+rax+00h]
0x14003e71f  mov     rcx, [rsp+88h+BcbVoid]; Bcb
0x14003e724  call    cs:__imp_CcRepinBcb
0x14003e72b  nop     dword ptr [rax+rax+00h]
0x14003e730  mov     rcx, [rsp+88h+BcbVoid]; Bcb
0x14003e735  call    cs:__imp_CcUnpinData
0x14003e73c  nop     dword ptr [rax+rax+00h]
0x14003e741  lea     r8, [rsp+88h+IoStatus]; IoStatus
0x14003e746  mov     dl, 1; WriteThrough
0x14003e748  mov     rcx, [rsp+88h+BcbVoid]; Bcb
0x14003e74d  call    cs:__imp_CcUnpinRepinnedBcb
0x14003e754  nop     dword ptr [rax+rax+00h]
0x14003e759  cmp     dword ptr [rsp+88h+IoStatus], edi
0x14003e75d  cmovl   esi, dword ptr [rsp+88h+IoStatus]
0x14003e762  mov     [rsp+88h+var_58], esi
0x14003e766  jmp     short loc_14003E777
0x14003e768  mov     rax, [rsp+88h+arg_0]
0x14003e770  mov     esi, [rax+48h]
0x14003e773  mov     [rsp+88h+var_58], esi
0x14003e777  mov     eax, esi
0x14003e779  add     rsp, 60h
0x14003e77d  pop     r15
0x14003e77f  pop     r14
0x14003e781  pop     rdi
0x14003e782  pop     rsi
0x14003e783  pop     rbx
0x14003e784  retn
0x14005ebc1  push    rbp
0x14005ebc3  sub     rsp, 30h
0x14005ebc7  mov     rbp, rdx
0x14005ebca  mov     rcx, [rcx]
0x14005ebcd  mov     ecx, [rcx]; Exception
0x14005ebcf  call    cs:__imp_FsRtlIsNtstatusExpected
0x14005ebd6  nop     dword ptr [rax+rax+00h]
0x14005ebdb  xor     ecx, ecx
0x14005ebdd  test    al, al
0x14005ebdf  setnz   cl
0x14005ebe2  mov     eax, ecx
0x14005ebe4  add     rsp, 30h
0x14005ebe8  pop     rbp
0x14005ebe9  retn
0x14005ebeb  push    rbp
0x14005ebed  sub     rsp, 30h
0x14005ebf1  mov     rbp, rdx
0x14005ebf4  mov     rdx, rcx
0x14005ebf7  mov     rcx, [rbp+90h]
0x14005ebfe  call    FatExceptionFilter
0x14005ec03  nop
0x14005ec04  add     rsp, 30h
0x14005ec08  pop     rbp
0x14005ec09  retn
0x14005ec0b  push    rbp
0x14005ec0d  sub     rsp, 30h
0x14005ec11  mov     rbp, rdx
0x14005ec14  mov     rdx, rcx
0x14005ec17  mov     rcx, [rbp+90h]
0x14005ec1e  call    FatExceptionFilter
0x14005ec23  nop
0x14005ec24  add     rsp, 30h
0x14005ec28  pop     rbp
0x14005ec29  retn
```
