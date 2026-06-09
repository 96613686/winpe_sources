# NtOfsDeleteAttribute

- ea: `0x140003e9c`
- end: `0x1400040de`
- name: `NtOfsDeleteAttribute`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140053a88`

## callees

- `0x1400019b8`
- `0x140003e9c`
- `0x14000c680`
- `0x1400319bc`
- `0x14003e870`
- `0x1400465f4`

## import_xrefs

- `ntoskrnl!CcPreparePinWrite` at `0x140003f52`
- `ntoskrnl!CcPreparePinWrite` at `0x140003f52`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400040c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400040c3`
- `ntoskrnl!CcUnpinData` at `0x140003f76`
- `ntoskrnl!CcUnpinData` at `0x14000400a`
- `ntoskrnl!CcUnpinData` at `0x14000406c`
- `ntoskrnl!CcUnpinData` at `0x14000408a`
- `ntoskrnl!CcUnpinData` at `0x14000cebe`
- `ntoskrnl!CcUnpinData` at `0x14000cede`
- `ntoskrnl!CcUnpinData` at `0x140003f76`
- `ntoskrnl!CcUnpinData` at `0x14000400a`
- `ntoskrnl!CcUnpinData` at `0x14000406c`
- `ntoskrnl!CcUnpinData` at `0x14000408a`
- `ntoskrnl!CcUnpinData` at `0x14000cebe`
- `ntoskrnl!CcUnpinData` at `0x14000cede`
- `ntoskrnl!CcSetFileSizes` at `0x140004044`
- `ntoskrnl!CcSetFileSizes` at `0x140004044`

## pseudocode

```c
void __fastcall NtOfsDeleteAttribute(_WORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v6; // di
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  PVOID Buffer; // [rsp+40h] [rbp-28h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+48h] [rbp-20h] BYREF
  PVOID Bcb; // [rsp+78h] [rbp+10h] BYREF
  PVOID v13; // [rsp+80h] [rbp+18h] BYREF
  __int64 v14; // [rsp+88h] [rbp+20h] BYREF

  FileOffset.QuadPart = 0;
  v6 = 0;
  v13 = 0;
  Bcb = 0;
  Buffer = 0;
  v14 = 0;
  if ( (byte_140017D4D & 2) != 0 && *a1 == 1288 && a1[1] == 144 && *(_WORD *)a3 == 1282 )
  {
    FatAcquireExclusiveFcb(a1, a3, a3, a4);
    v6 = 1;
    v7 = *(_DWORD *)(a3 + 192);
    if ( (v7 & 0x10000) != 0 )
    {
      *(_DWORD *)(a3 + 192) = v7 | 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a3 + 176) + 360LL) + 73LL) = 1;
    }
    else
    {
      CcPreparePinWrite(*(PFILE_OBJECT *)(a3 + 424), &FileOffset, *(_DWORD *)(a3 + 132), 0, 1u, &Bcb, &Buffer);
      memset(Buffer, 0, *(unsigned int *)(a3 + 132));
      CcUnpinData(Bcb);
      Bcb = 0;
      FatFlushFile(v8, a3, 1);
      FatGetDirentFromFcbOrDcb((_DWORD)a1, a3, 0, (unsigned int)&v14, (__int64)&v13);
      FatSetDirtyBcb(a1, v13, *(_QWORD *)(a3 + 184), 0);
      *(_DWORD *)(a3 + 192) &= ~0x8000u;
      *(_DWORD *)(a3 + 132) = 0;
      *(_BYTE *)(a3 + 136) = 0;
      *(_DWORD *)(v14 + 28) = 0;
      *(_BYTE *)(v14 + 12) &= 0x1Bu;
      if ( v13 )
      {
        CcUnpinData(v13);
        v13 = 0;
      }
      *(_QWORD *)(a3 + 440) = 0;
      *(_QWORD *)(a3 + 432) = 0;
      *(_QWORD *)(a3 + 448) = FatMaxLarge;
      CcSetFileSizes(*(PFILE_OBJECT *)(a3 + 424), (PCC_FILE_SIZES)(a3 + 432));
      FatFlushFile(v9, a3, 1);
      *(_DWORD *)(a3 + 192) |= 2u;
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
      if ( v13 )
      {
        CcUnpinData(v13);
        v13 = 0;
      }
    }
  }
  if ( v6 )
    ExReleaseResourceLite(*(PERESOURCE *)(a3 + 8));
}

```

## disassembly

```asm
0x140003e9c  mov     rax, rsp
0x140003e9f  mov     [rax+8], rbx
0x140003ea3  mov     [rax+10h], rdx
0x140003ea7  push    rsi
0x140003ea8  push    rdi
0x140003ea9  push    r14
0x140003eab  sub     rsp, 50h
0x140003eaf  mov     rbx, r8
0x140003eb2  mov     rsi, rcx
0x140003eb5  xor     r14d, r14d
0x140003eb8  mov     [rax-20h], r14
0x140003ebc  mov     dil, r14b
0x140003ebf  mov     [rax+18h], r14
0x140003ec3  mov     [rax+10h], r14
0x140003ec7  mov     [rax-28h], r14
0x140003ecb  mov     [rax+20h], r14
0x140003ecf  test    cs:byte_140017D4D, 2
0x140003ed6  jz      loc_1400040BA
0x140003edc  mov     eax, 508h
0x140003ee1  cmp     [rcx], ax
0x140003ee4  jnz     loc_1400040BA
0x140003eea  mov     eax, 90h
0x140003eef  cmp     [rcx+2], ax
0x140003ef3  jnz     loc_1400040BA
0x140003ef9  mov     eax, 502h
0x140003efe  cmp     [r8], ax
0x140003f02  jnz     loc_1400040BA
0x140003f08  mov     rdx, rbx
0x140003f0b  call    FatAcquireExclusiveFcb
0x140003f10  lea     edi, [r14+1]
0x140003f14  mov     eax, [rbx+0C0h]
0x140003f1a  bt      eax, 10h
0x140003f1e  jb      loc_1400040A0
0x140003f24  lea     rax, [rsp+68h+var_28]
0x140003f29  mov     [rsp+68h+Buffer], rax; Buffer
0x140003f2e  lea     rax, [rsp+68h+arg_8]
0x140003f33  mov     [rsp+68h+Bcb], rax; Bcb
0x140003f38  mov     [rsp+68h+Flags], edi; Flags
0x140003f3c  xor     r9d, r9d; Zero
0x140003f3f  mov     r8d, [rbx+84h]; Length
0x140003f46  lea     rdx, [rsp+68h+FileOffset]; FileOffset
0x140003f4b  mov     rcx, [rbx+1A8h]; FileObject
0x140003f52  call    cs:__imp_CcPreparePinWrite
0x140003f59  nop     dword ptr [rax+rax+00h]
0x140003f5e  mov     r8d, [rbx+84h]; Size
0x140003f65  xor     edx, edx; Val
0x140003f67  mov     rcx, [rsp+68h+var_28]; void *
0x140003f6c  call    memset
0x140003f71  mov     rcx, [rsp+68h+arg_8]; Bcb
0x140003f76  call    cs:__imp_CcUnpinData
0x140003f7d  nop     dword ptr [rax+rax+00h]
0x140003f82  mov     [rsp+68h+arg_8], r14
0x140003f87  mov     r8d, edi
0x140003f8a  mov     rdx, rbx
0x140003f8d  call    FatFlushFile
0x140003f92  lea     rax, [rsp+68h+arg_10]
0x140003f9a  mov     qword ptr [rsp+68h+Flags], rax
0x140003f9f  lea     r9, [rsp+68h+arg_18]
0x140003fa7  xor     r8d, r8d
0x140003faa  mov     rdx, rbx
0x140003fad  mov     rcx, rsi
0x140003fb0  call    FatGetDirentFromFcbOrDcb
0x140003fb5  xor     r9d, r9d
0x140003fb8  mov     r8, [rbx+0B8h]
0x140003fbf  mov     rdx, [rsp+68h+arg_10]
0x140003fc7  mov     rcx, rsi
0x140003fca  call    FatSetDirtyBcb
0x140003fcf  btr     dword ptr [rbx+0C0h], 0Fh
0x140003fd7  mov     [rbx+84h], r14d
0x140003fde  mov     [rbx+88h], r14b
0x140003fe5  mov     rax, [rsp+68h+arg_18]
0x140003fed  mov     [rax+1Ch], r14d
0x140003ff1  mov     rax, [rsp+68h+arg_18]
0x140003ff9  and     byte ptr [rax+0Ch], 1Bh
0x140003ffd  mov     rcx, [rsp+68h+arg_10]; Bcb
0x140004005  test    rcx, rcx
0x140004008  jz      short loc_14000401E
0x14000400a  call    cs:__imp_CcUnpinData
0x140004011  nop     dword ptr [rax+rax+00h]
0x140004016  mov     [rsp+68h+arg_10], r14
0x14000401e  mov     [rbx+1B8h], r14
0x140004025  lea     rdx, [rbx+1B0h]; FileSizes
0x14000402c  mov     [rdx], r14
0x14000402f  mov     rax, cs:FatMaxLarge
0x140004036  mov     [rbx+1C0h], rax
0x14000403d  mov     rcx, [rbx+1A8h]; FileObject
0x140004044  call    cs:__imp_CcSetFileSizes
0x14000404b  nop     dword ptr [rax+rax+00h]
0x140004050  mov     r8d, edi
0x140004053  mov     rdx, rbx
0x140004056  call    FatFlushFile
0x14000405b  or      dword ptr [rbx+0C0h], 2
0x140004062  mov     rcx, [rsp+68h+arg_8]; Bcb
0x140004067  test    rcx, rcx
0x14000406a  jz      short loc_14000407D
0x14000406c  call    cs:__imp_CcUnpinData
0x140004073  nop     dword ptr [rax+rax+00h]
0x140004078  mov     [rsp+68h+arg_8], r14
0x14000407d  mov     rcx, [rsp+68h+arg_10]; Bcb
0x140004085  test    rcx, rcx
0x140004088  jz      short loc_1400040BA
0x14000408a  call    cs:__imp_CcUnpinData
0x140004091  nop     dword ptr [rax+rax+00h]
0x140004096  mov     [rsp+68h+arg_10], r14
0x14000409e  jmp     short loc_1400040BA
0x1400040a0  or      eax, edi
0x1400040a2  mov     [rbx+0C0h], eax
0x1400040a8  mov     rax, [rbx+0B0h]
0x1400040af  mov     rcx, [rax+168h]
0x1400040b6  mov     [rcx+49h], dil
0x1400040ba  test    dil, dil
0x1400040bd  jz      short loc_1400040CF
0x1400040bf  mov     rcx, [rbx+8]; Resource
0x1400040c3  call    cs:__imp_ExReleaseResourceLite
0x1400040ca  nop     dword ptr [rax+rax+00h]
0x1400040cf  mov     rbx, [rsp+68h+arg_0]
0x1400040d4  add     rsp, 50h
0x1400040d8  pop     r14
0x1400040da  pop     rdi
0x1400040db  pop     rsi
0x1400040dc  retn
0x14000ceac  push    rbp
0x14000ceae  sub     rsp, 40h
0x14000ceb2  mov     rbp, rdx
0x14000ceb5  mov     rcx, [rbp+78h]; Bcb
0x14000ceb9  test    rcx, rcx
0x14000cebc  jz      short loc_14000CED2
0x14000cebe  call    cs:__imp_CcUnpinData
0x14000cec5  nop     dword ptr [rax+rax+00h]
0x14000ceca  mov     qword ptr [rbp+78h], 0
0x14000ced2  mov     rcx, [rbp+80h]; Bcb
0x14000ced9  test    rcx, rcx
0x14000cedc  jz      short loc_14000CEEB
0x14000cede  call    cs:__imp_CcUnpinData
0x14000cee5  nop     dword ptr [rax+rax+00h]
0x14000ceea  nop
0x14000ceeb  add     rsp, 40h
0x14000ceef  pop     rbp
0x14000cef0  retn
```
