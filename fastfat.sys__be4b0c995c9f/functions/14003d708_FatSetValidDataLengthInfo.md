# FatSetValidDataLengthInfo

- ea: `0x14003d708`
- end: `0x14003d87a`
- name: `FatSetValidDataLengthInfo`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140039e94`

## callees

- `0x140001d4c`
- `0x14003d708`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14003d7ec`
- `ntoskrnl!CcFlushCache` at `0x14003d7ec`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003d80a`
- `ntoskrnl!CcPurgeCacheSection` at `0x14003d80a`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14003d7a2`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14003d7a2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003d7cc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003d7cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003d85d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e8de`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003d85d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e8de`
- `ntoskrnl!CcSetFileSizes` at `0x14003d833`
- `ntoskrnl!CcSetFileSizes` at `0x14003d833`

## pseudocode

```c
__int64 __fastcall FatSetValidDataLengthInfo(__int64 a1, __int64 a2, struct _FILE_OBJECT *a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // edi
  BOOLEAN v9; // r12
  union _LARGE_INTEGER *v10; // r10
  DWORD LowPart; // r15d

  v8 = 0;
  v9 = 0;
  if ( !a5 || (*(_DWORD *)(a5 + 4) & 0x20000) == 0 )
    goto LABEL_17;
  if ( *(_WORD *)a4 != 1282 )
  {
    v8 = -1073741808;
    goto LABEL_18;
  }
  if ( !(unsigned __int8)FatIsIoRangeValid(a1, **(_QWORD **)(a2 + 24), 0, *(unsigned int *)(a4 + 132)) )
  {
    v8 = -1073741697;
    goto LABEL_18;
  }
  LowPart = v10->LowPart;
  if ( v10->LowPart >= *(_DWORD *)(a4 + 40) && LowPart <= *(_DWORD *)(a4 + 32) )
  {
    if ( !MmCanFileBeTruncated(a3->SectionObjectPointer, v10) )
    {
      v8 = -1073741245;
      goto LABEL_18;
    }
    if ( a3->SectionObjectPointer->DataSectionObject )
    {
      v9 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a4 + 16), 1u);
      CcFlushCache(a3->SectionObjectPointer, 0, 0, (PIO_STATUS_BLOCK)(a2 + 48));
      if ( *(int *)(a2 + 48) < 0 )
        goto LABEL_18;
      CcPurgeCacheSection(a3->SectionObjectPointer, 0, 0, 0);
    }
    *(_DWORD *)(a4 + 40) = LowPart;
    *(_DWORD *)(a4 + 280) = LowPart;
    if ( a3->SectionObjectPointer->SharedCacheMap )
      CcSetFileSizes(a3, (PCC_FILE_SIZES)(a4 + 24));
    a3->Flags |= 0x1000u;
    v8 = 0;
  }
  else
  {
LABEL_17:
    v8 = -1073741811;
  }
LABEL_18:
  if ( v9 )
    ExReleaseResourceLite(*(PERESOURCE *)(a4 + 16));
  return v8;
}

```

## disassembly

```asm
0x14003d708  mov     [rsp+arg_18], r9
0x14003d70d  push    rbx
0x14003d70e  push    rsi
0x14003d70f  push    rdi
0x14003d710  push    r12
0x14003d712  push    r14
0x14003d714  push    r15
0x14003d716  sub     rsp, 38h
0x14003d71a  mov     rsi, r9
0x14003d71d  mov     r14, r8
0x14003d720  mov     rbx, rdx
0x14003d723  xor     edi, edi
0x14003d725  xor     r12b, r12b
0x14003d728  mov     [rsp+68h+var_48], r12b
0x14003d72d  mov     r10, [rdx+18h]
0x14003d731  mov     rax, [rsp+68h+arg_20]
0x14003d739  test    rax, rax
0x14003d73c  jz      loc_14003D84F
0x14003d742  mov     eax, [rax+4]
0x14003d745  bt      eax, 11h
0x14003d749  jnb     loc_14003D84F
0x14003d74f  mov     eax, 502h
0x14003d754  cmp     [r9], ax
0x14003d758  jz      short loc_14003D764
0x14003d75a  mov     edi, 0C0000010h
0x14003d75f  jmp     loc_14003D854
0x14003d764  mov     r9d, [r9+84h]
0x14003d76b  xor     r8d, r8d
0x14003d76e  mov     rdx, [r10]
0x14003d771  call    FatIsIoRangeValid
0x14003d776  test    al, al
0x14003d778  jnz     short loc_14003D784
0x14003d77a  mov     edi, 0C000007Fh
0x14003d77f  jmp     loc_14003D854
0x14003d784  mov     r15d, [r10]
0x14003d787  cmp     r15d, [rsi+28h]
0x14003d78b  jb      loc_14003D84F
0x14003d791  cmp     r15d, [rsi+20h]
0x14003d795  ja      loc_14003D84F
0x14003d79b  mov     rdx, r10; NewFileSize
0x14003d79e  mov     rcx, [r14+28h]; SectionPointer
0x14003d7a2  call    cs:__imp_MmCanFileBeTruncated
0x14003d7a9  nop     dword ptr [rax+rax+00h]
0x14003d7ae  test    al, al
0x14003d7b0  jnz     short loc_14003D7BC
0x14003d7b2  mov     edi, 0C0000243h
0x14003d7b7  jmp     loc_14003D854
0x14003d7bc  mov     rax, [r14+28h]
0x14003d7c0  cmp     qword ptr [rax], 0
0x14003d7c4  jz      short loc_14003D816
0x14003d7c6  mov     dl, 1; Wait
0x14003d7c8  mov     rcx, [rsi+10h]; Resource
0x14003d7cc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003d7d3  nop     dword ptr [rax+rax+00h]
0x14003d7d8  mov     r12b, al
0x14003d7db  mov     [rsp+68h+var_48], al
0x14003d7df  lea     r9, [rbx+30h]; IoStatus
0x14003d7e3  xor     r8d, r8d; Length
0x14003d7e6  xor     edx, edx; FileOffset
0x14003d7e8  mov     rcx, [r14+28h]; SectionObjectPointer
0x14003d7ec  call    cs:__imp_CcFlushCache
0x14003d7f3  nop     dword ptr [rax+rax+00h]
0x14003d7f8  cmp     dword ptr [rbx+30h], 0
0x14003d7fc  jl      short loc_14003D854
0x14003d7fe  xor     r9d, r9d; Flags
0x14003d801  xor     r8d, r8d; Length
0x14003d804  xor     edx, edx; FileOffset
0x14003d806  mov     rcx, [r14+28h]; SectionObjectPointer
0x14003d80a  call    cs:__imp_CcPurgeCacheSection
0x14003d811  nop     dword ptr [rax+rax+00h]
0x14003d816  mov     [rsi+28h], r15d
0x14003d81a  mov     [rsi+118h], r15d
0x14003d821  mov     rax, [r14+28h]
0x14003d825  cmp     qword ptr [rax+8], 0
0x14003d82a  jz      short loc_14003D83F
0x14003d82c  lea     rdx, [rsi+18h]; FileSizes
0x14003d830  mov     rcx, r14; FileObject
0x14003d833  call    cs:__imp_CcSetFileSizes
0x14003d83a  nop     dword ptr [rax+rax+00h]
0x14003d83f  mov     eax, [r14+50h]
0x14003d843  bts     eax, 0Ch
0x14003d847  mov     [r14+50h], eax
0x14003d84b  xor     edi, edi
0x14003d84d  jmp     short loc_14003D854
0x14003d84f  mov     edi, 0C000000Dh
0x14003d854  test    r12b, r12b
0x14003d857  jz      short loc_14003D869
0x14003d859  mov     rcx, [rsi+10h]; Resource
0x14003d85d  call    cs:__imp_ExReleaseResourceLite
0x14003d864  nop     dword ptr [rax+rax+00h]
0x14003d869  mov     eax, edi
0x14003d86b  add     rsp, 38h
0x14003d86f  pop     r15
0x14003d871  pop     r14
0x14003d873  pop     r12
0x14003d875  pop     rdi
0x14003d876  pop     rsi
0x14003d877  pop     rbx
0x14003d878  retn
0x14005e8c4  push    rbp
0x14005e8c6  sub     rsp, 20h
0x14005e8ca  mov     rbp, rdx
0x14005e8cd  cmp     byte ptr [rbp+20h], 0
0x14005e8d1  jz      short loc_14005E8EB
0x14005e8d3  mov     rcx, [rbp+88h]
0x14005e8da  mov     rcx, [rcx+10h]; Resource
0x14005e8de  call    cs:__imp_ExReleaseResourceLite
0x14005e8e5  nop     dword ptr [rax+rax+00h]
0x14005e8ea  nop
0x14005e8eb  add     rsp, 20h
0x14005e8ef  pop     rbp
0x14005e8f0  retn
```
