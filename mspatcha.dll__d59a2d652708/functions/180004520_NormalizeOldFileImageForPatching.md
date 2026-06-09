# NormalizeOldFileImageForPatching

- ea: `0x180004520`
- end: `0x18000466f`
- name: `NormalizeOldFileImageForPatching`
- size: `335`
- prototype: `INT __stdcall(PVOID FileBuffer, ULONG FileSize, ULONG OptionFlags, PATCH_OPTION_DATA *OptionData, ULONG NewFileCoffBase, ULONG NewFileCoffTime, ULONG IgnoreRangeCount, PPATCH_IGNORE_RANGE IgnoreRangeArray, ULONG RetainRangeCount, PPATCH_RETAIN_RANGE RetainRangeArray)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, installer_update`

## callers

- `0x180001d10`
- `0x180002720`
- `0x180004180`

## callees

- `0x180001cae`
- `0x180004520`
- `0x180004d10`
- `0x180004f8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004642`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004642`

## pseudocode

```c
INT __stdcall NormalizeOldFileImageForPatching(
        PVOID FileBuffer,
        ULONG FileSize,
        ULONG OptionFlags,
        PATCH_OPTION_DATA *OptionData,
        ULONG NewFileCoffBase,
        ULONG NewFileCoffTime,
        ULONG IgnoreRangeCount,
        PPATCH_IGNORE_RANGE IgnoreRangeArray,
        ULONG RetainRangeCount,
        PPATCH_RETAIN_RANGE RetainRangeArray)
{
  unsigned __int64 v11; // r15
  int v13; // edi
  __int64 NtHeader; // rax
  ULONG i; // esi
  unsigned __int64 OffsetInOldFile; // rcx
  size_t LengthInBytes; // r8
  ULONG j; // esi
  unsigned __int64 v19; // rcx
  size_t v20; // r8

  v11 = FileSize;
  v13 = 0;
  if ( FileBuffer && FileSize )
  {
    NtHeader = GetNtHeader(FileBuffer, FileSize, OptionFlags, OptionData);
    if ( NtHeader )
      v13 = NormalizeCoffImage(NtHeader, (_DWORD)FileBuffer, v11, OptionFlags);
    for ( i = 0; i < IgnoreRangeCount; ++i )
    {
      OffsetInOldFile = IgnoreRangeArray[i].OffsetInOldFile;
      if ( OffsetInOldFile <= v11 )
      {
        LengthInBytes = IgnoreRangeArray[i].LengthInBytes;
        if ( LengthInBytes <= v11 - OffsetInOldFile )
        {
          memset_0((char *)FileBuffer + OffsetInOldFile, 0, LengthInBytes);
          v13 = 1;
        }
      }
    }
    for ( j = 0; j < RetainRangeCount; ++j )
    {
      v19 = RetainRangeArray[j].OffsetInOldFile;
      if ( v19 <= v11 )
      {
        v20 = RetainRangeArray[j].LengthInBytes;
        if ( v20 <= v11 - v19 )
        {
          memset_0((char *)FileBuffer + v19, 0, v20);
          v13 = 1;
        }
      }
    }
  }
  return (v13 != 0) + 1;
}

```

## disassembly

```asm
0x180004520  push    rbx
0x180004522  push    rsi
0x180004523  push    rdi
0x180004524  push    r12
0x180004526  push    r13
0x180004528  push    r15
0x18000452a  sub     rsp, 58h
0x18000452e  mov     esi, r8d
0x180004531  mov     r15d, edx
0x180004534  mov     r12, rcx
0x180004537  xor     ebx, ebx
0x180004539  mov     edi, ebx
0x18000453b  lea     eax, [rbx+1]
0x18000453e  mov     [rsp+88h+arg_0], eax
0x180004545  test    rcx, rcx
0x180004548  jz      loc_180004653
0x18000454e  test    edx, edx
0x180004550  jz      loc_180004653
0x180004556  mov     edx, r15d
0x180004559  call    GetNtHeader
0x18000455e  mov     rcx, rax
0x180004561  test    rax, rax
0x180004564  jz      short loc_180004590
0x180004566  mov     eax, [rsp+88h+NewFileCoffTime]
0x18000456d  mov     [rsp+88h+var_58], eax
0x180004571  mov     eax, [rsp+88h+NewFileCoffBase]
0x180004578  mov     [rsp+88h+var_60], eax
0x18000457c  mov     r9d, esi
0x18000457f  mov     r8d, r15d
0x180004582  mov     rdx, r12
0x180004585  call    NormalizeCoffImage
0x18000458a  mov     edi, eax
0x18000458c  mov     [rsp+88h+var_44], eax
0x180004590  mov     esi, ebx
0x180004592  mov     [rsp+88h+var_48], ebx
0x180004596  mov     r13, [rsp+88h+IgnoreRangeArray]
0x18000459e  cmp     esi, [rsp+88h+IgnoreRangeCount]
0x1800045a5  jnb     short loc_1800045DE
0x1800045a7  mov     eax, esi
0x1800045a9  mov     ecx, [r13+rax*8+0]
0x1800045ae  cmp     rcx, r15
0x1800045b1  ja      short loc_1800045D6
0x1800045b3  mov     r8d, [r13+rax*8+4]; Size
0x1800045b8  mov     rax, r15
0x1800045bb  sub     rax, rcx
0x1800045be  cmp     r8, rax
0x1800045c1  ja      short loc_1800045D6
0x1800045c3  add     rcx, r12; void *
0x1800045c6  xor     edx, edx; Val
0x1800045c8  call    memset_0
0x1800045cd  mov     edi, 1
0x1800045d2  mov     [rsp+88h+var_44], edi
0x1800045d6  inc     esi
0x1800045d8  mov     [rsp+88h+var_48], esi
0x1800045dc  jmp     short loc_18000459E
0x1800045de  mov     esi, ebx
0x1800045e0  mov     [rsp+88h+var_48], ebx
0x1800045e4  mov     r13, [rsp+88h+RetainRangeArray]
0x1800045ec  cmp     esi, [rsp+88h+RetainRangeCount]
0x1800045f3  jnb     short loc_180004630
0x1800045f5  mov     eax, esi
0x1800045f7  lea     rdx, [rax+rax*2]
0x1800045fb  mov     ecx, [r13+rdx*4+0]
0x180004600  cmp     rcx, r15
0x180004603  ja      short loc_180004628
0x180004605  mov     r8d, [r13+rdx*4+4]; Size
0x18000460a  mov     rax, r15
0x18000460d  sub     rax, rcx
0x180004610  cmp     r8, rax
0x180004613  ja      short loc_180004628
0x180004615  add     rcx, r12; void *
0x180004618  xor     edx, edx; Val
0x18000461a  call    memset_0
0x18000461f  mov     edi, 1
0x180004624  mov     [rsp+88h+var_44], edi
0x180004628  inc     esi
0x18000462a  mov     [rsp+88h+var_48], esi
0x18000462e  jmp     short loc_1800045EC
0x180004630  mov     eax, [rsp+88h+arg_0]
0x180004637  jmp     short loc_180004653
0x180004639  cmp     eax, 0E0000001h
0x18000463e  jz      short loc_180004648
0x180004640  mov     ecx, eax; dwErrCode
0x180004642  call    cs:__imp_SetLastError
0x180004648  xor     eax, eax
0x18000464a  lea     edi, [rax+1]
0x18000464d  mov     [rsp+88h+var_44], edi
0x180004651  xor     ebx, ebx
0x180004653  test    eax, eax
0x180004655  jz      short loc_18000465F
0x180004657  neg     edi
0x180004659  sbb     ebx, ebx
0x18000465b  neg     ebx
0x18000465d  inc     ebx
0x18000465f  mov     eax, ebx
0x180004661  add     rsp, 58h
0x180004665  pop     r15
0x180004667  pop     r13
0x180004669  pop     r12
0x18000466b  pop     rdi
0x18000466c  pop     rsi
0x18000466d  pop     rbx
0x18000466e  retn
```
