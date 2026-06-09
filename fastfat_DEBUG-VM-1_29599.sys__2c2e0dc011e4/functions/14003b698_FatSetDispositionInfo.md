# FatSetDispositionInfo

- ea: `0x14003b698`
- end: `0x14003b9c7`
- name: `FatSetDispositionInfo`
- size: `815`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140039e94`

## callees

- `0x1400019b8`
- `0x1400246bc`
- `0x1400319bc`
- `0x140031b84`
- `0x14003b698`
- `0x14003eb84`

## import_xrefs

- `ntoskrnl!CcRepinBcb` at `0x14003b869`
- `ntoskrnl!CcRepinBcb` at `0x14003b869`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x14003b8ae`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x14003b8ae`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14003b87f`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14003b87f`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003b8ca`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003b8ca`
- `ntoskrnl!CcPinMappedData` at `0x14003b7f1`
- `ntoskrnl!CcPinMappedData` at `0x14003b7f1`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x14003b986`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x14003b986`
- `ntoskrnl!MmFlushImageSection` at `0x14003b6e8`
- `ntoskrnl!MmFlushImageSection` at `0x14003b6e8`
- `ntoskrnl!CcUnpinData` at `0x14003b893`
- `ntoskrnl!CcUnpinData` at `0x14003b925`
- `ntoskrnl!CcUnpinData` at `0x14005e565`
- `ntoskrnl!CcUnpinData` at `0x14005e58b`
- `ntoskrnl!CcUnpinData` at `0x14003b893`
- `ntoskrnl!CcUnpinData` at `0x14003b925`
- `ntoskrnl!CcUnpinData` at `0x14005e565`
- `ntoskrnl!CcUnpinData` at `0x14005e58b`
- `ntoskrnl!ExRaiseStatus` at `0x14003b809`
- `ntoskrnl!ExRaiseStatus` at `0x14003b8d8`
- `ntoskrnl!ExRaiseStatus` at `0x14003b809`
- `ntoskrnl!ExRaiseStatus` at `0x14003b8d8`

## pseudocode

```c
__int64 __fastcall FatSetDispositionInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdi
  unsigned __int16 *v9; // r15
  int v10; // eax
  ULONG v11; // r14d
  NTSTATUS Status; // ecx
  NTSTATUS v13; // eax
  PVOID v14; // [rsp+50h] [rbp-58h] BYREF
  _BYTE *v15; // [rsp+58h] [rbp-50h] BYREF
  __int64 v16; // [rsp+60h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+68h] [rbp-40h] BYREF
  PVOID BcbVoid; // [rsp+B8h] [rbp+10h] BYREF

  v14 = 0;
  v16 = 0;
  if ( **(_BYTE **)(a2 + 24) )
  {
    if ( (*(_BYTE *)(a4 + 546) & 1) != 0
      || !MmFlushImageSection(*(PSECTION_OBJECT_POINTERS *)(a4 + 120), MmFlushForDelete)
      || *(_WORD *)a4 == 1284 )
    {
      return 3221225761LL;
    }
    if ( *(_WORD *)a4 == 1283 && !(unsigned __int8)FatIsDirectoryEmpty(a1, a4) )
      return 3221225729LL;
    v8 = *(_QWORD *)(a4 + 184);
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 192) + 16LL) + 52LL) & 4) != 0 )
    {
      BcbVoid = 0;
      v15 = 0;
      IoStatus = 0;
      v9 = (unsigned __int16 *)(v8 + 288);
      if ( *(_BYTE *)(v8 + 376) == 12 )
      {
        v10 = *(unsigned __int16 *)(v8 + 302);
        if ( !(_WORD)v10 )
          v10 = *(_DWORD *)(v8 + 316);
        v11 = *v9 * (v10 + *(unsigned __int16 *)(v8 + 292));
      }
      else
      {
        v11 = 4096;
      }
      FatReadVolumeFile(a1, v8, 0, v11, &BcbVoid, &v15);
      if ( !CcPinMappedData(*(PFILE_OBJECT *)(v8 + 728), &FatLargeZero, v11, (*(_DWORD *)(a1 + 68) >> 1) & 1, &BcbVoid) )
      {
        *(_DWORD *)(a1 + 72) = -1073741608;
        ExRaiseStatus(-1073741608);
      }
      v15 += *v9 * (unsigned __int64)*(unsigned __int16 *)(v8 + 292);
      *v15 = *v15;
      FatAddMcbEntry(
        v8,
        v8 + 384,
        *v9 * (unsigned int)*(unsigned __int16 *)(v8 + 292),
        *v9 * (unsigned int)*(unsigned __int16 *)(v8 + 292),
        *v9);
      CcRepinBcb(BcbVoid);
      CcSetDirtyPinnedData(BcbVoid, 0);
      CcUnpinData(BcbVoid);
      CcUnpinRepinnedBcb(BcbVoid, 1u, &IoStatus);
      Status = IoStatus.Status;
      if ( IoStatus.Status < 0 )
      {
        *(_DWORD *)(a1 + 72) = IoStatus.Status;
        v13 = FsRtlNormalizeNtstatus(Status, -1073741591);
        ExRaiseStatus(v13);
      }
    }
    else
    {
      FatGetDirentFromFcbOrDcb(a1, a4, 0, (unsigned int)&v16, (__int64)&v14);
      FatSetDirtyBcb(a1, v14, *(_QWORD *)(a4 + 184), 1);
      if ( v14 )
      {
        CcUnpinData(v14);
        v14 = 0;
      }
    }
    *(_DWORD *)(a4 + 192) |= 1u;
    *(_BYTE *)(a3 + 73) = 1;
    if ( *(_WORD *)a4 == 1283 )
      FsRtlNotifyFullChangeDirectory(
        *(PNOTIFY_SYNC *)(*(_QWORD *)(a4 + 184) + 816LL),
        (PLIST_ENTRY)(*(_QWORD *)(a4 + 184) + 800LL),
        *(PVOID *)(a3 + 24),
        0,
        0,
        0,
        0,
        0,
        0,
        0);
  }
  else
  {
    *(_DWORD *)(a4 + 192) &= ~1u;
    *(_BYTE *)(a3 + 73) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14003b698  mov     rax, rsp
0x14003b69b  mov     [rax+8], rbx
0x14003b69f  mov     [rax+18h], rsi
0x14003b6a3  push    rdi
0x14003b6a4  push    r12
0x14003b6a6  push    r13
0x14003b6a8  push    r14
0x14003b6aa  push    r15
0x14003b6ac  sub     rsp, 80h
0x14003b6b3  mov     rbx, r9
0x14003b6b6  mov     r13, r8
0x14003b6b9  mov     rsi, rcx
0x14003b6bc  xor     r12d, r12d
0x14003b6bf  mov     [rax-58h], r12
0x14003b6c3  mov     [rax-48h], r12
0x14003b6c7  mov     rax, [rdx+18h]
0x14003b6cb  cmp     [rax], r12b
0x14003b6ce  jz      loc_14003B99B
0x14003b6d4  test    byte ptr [r9+222h], 1
0x14003b6dc  jnz     loc_14003B994
0x14003b6e2  xor     edx, edx; FlushType
0x14003b6e4  mov     rcx, [r9+78h]; SectionObjectPointer
0x14003b6e8  call    cs:__imp_MmFlushImageSection
0x14003b6ef  nop     dword ptr [rax+rax+00h]
0x14003b6f4  test    al, al
0x14003b6f6  jz      loc_14003B994
0x14003b6fc  movzx   eax, word ptr [rbx]
0x14003b6ff  mov     ecx, 504h
0x14003b704  cmp     ax, cx
0x14003b707  jz      loc_14003B994
0x14003b70d  mov     ecx, 503h
0x14003b712  cmp     ax, cx
0x14003b715  jnz     short loc_14003B730
0x14003b717  mov     rdx, rbx; int
0x14003b71a  mov     rcx, rsi; int
0x14003b71d  call    FatIsDirectoryEmpty
0x14003b722  test    al, al
0x14003b724  jnz     short loc_14003B730
0x14003b726  mov     eax, 0C0000101h
0x14003b72b  jmp     loc_14003B9A9
0x14003b730  mov     rdi, [rbx+0B8h]
0x14003b737  mov     rax, [rdi+0C0h]
0x14003b73e  mov     rcx, [rax+10h]
0x14003b742  mov     eax, [rcx+34h]
0x14003b745  test    al, 4
0x14003b747  jz      loc_14003B8E5
0x14003b74d  mov     [rsp+0A8h+BcbVoid], r12
0x14003b755  mov     [rsp+0A8h+var_50], r12
0x14003b75a  xorps   xmm0, xmm0
0x14003b75d  movups  xmmword ptr [rsp+0A8h+IoStatus], xmm0
0x14003b762  lea     r15, [rdi+120h]
0x14003b769  cmp     byte ptr [rdi+178h], 0Ch
0x14003b770  jnz     short loc_14003B799
0x14003b772  movzx   eax, word ptr [rdi+12Eh]
0x14003b779  movzx   ecx, word ptr [r15]
0x14003b77d  test    ax, ax
0x14003b780  jnz     short loc_14003B788
0x14003b782  mov     eax, [rdi+13Ch]
0x14003b788  movzx   r14d, word ptr [rdi+124h]
0x14003b790  add     r14d, eax
0x14003b793  imul    r14d, ecx
0x14003b797  jmp     short loc_14003B79F
0x14003b799  mov     r14d, 1000h
0x14003b79f  lea     rax, [rsp+0A8h+var_50]
0x14003b7a4  mov     qword ptr [rsp+0A8h+IgnoreBuffer], rax
0x14003b7a9  lea     rax, [rsp+0A8h+BcbVoid]
0x14003b7b1  mov     [rsp+0A8h+Bcb], rax
0x14003b7b6  mov     r9d, r14d
0x14003b7b9  xor     r8d, r8d
0x14003b7bc  mov     rdx, rdi
0x14003b7bf  mov     rcx, rsi
0x14003b7c2  call    FatReadVolumeFile
0x14003b7c7  nop
0x14003b7c8  mov     r9d, [rsi+44h]
0x14003b7cc  shr     r9d, 1
0x14003b7cf  and     r9d, 1; Flags
0x14003b7d3  lea     rax, [rsp+0A8h+BcbVoid]
0x14003b7db  mov     [rsp+0A8h+Bcb], rax; Bcb
0x14003b7e0  mov     r8d, r14d; Length
0x14003b7e3  lea     rdx, FatLargeZero; FileOffset
0x14003b7ea  mov     rcx, [rdi+2D8h]; FileObject
0x14003b7f1  call    cs:__imp_CcPinMappedData
0x14003b7f8  nop     dword ptr [rax+rax+00h]
0x14003b7fd  test    al, al
0x14003b7ff  jnz     short loc_14003B815
0x14003b801  mov     ecx, 0C00000D8h; Status
0x14003b806  mov     [rsi+48h], ecx
0x14003b809  call    cs:__imp_ExRaiseStatus
0x14003b815  movzx   edx, word ptr [rdi+124h]
0x14003b81c  movzx   eax, word ptr [r15]
0x14003b820  imul    rdx, rax
0x14003b824  mov     r8, [rsp+0A8h+var_50]
0x14003b829  add     r8, rdx
0x14003b82c  mov     [rsp+0A8h+var_50], r8
0x14003b831  mov     al, [r8]
0x14003b834  mov     [r8], al
0x14003b837  movzx   r10d, word ptr [r15]
0x14003b83b  movzx   eax, word ptr [rdi+124h]
0x14003b842  imul    eax, r10d
0x14003b846  mov     r8d, eax
0x14003b849  mov     r9d, eax
0x14003b84c  lea     rdx, [rdi+180h]
0x14003b853  mov     dword ptr [rsp+0A8h+Bcb], r10d
0x14003b858  mov     rcx, rdi
0x14003b85b  call    FatAddMcbEntry
0x14003b860  nop
0x14003b861  mov     rcx, [rsp+0A8h+BcbVoid]; Bcb
0x14003b869  call    cs:__imp_CcRepinBcb
0x14003b870  nop     dword ptr [rax+rax+00h]
0x14003b875  xor     edx, edx; Lsn
0x14003b877  mov     rcx, [rsp+0A8h+BcbVoid]; BcbVoid
0x14003b87f  call    cs:__imp_CcSetDirtyPinnedData
0x14003b886  nop     dword ptr [rax+rax+00h]
0x14003b88b  mov     rcx, [rsp+0A8h+BcbVoid]; Bcb
0x14003b893  call    cs:__imp_CcUnpinData
0x14003b89a  nop     dword ptr [rax+rax+00h]
0x14003b89f  lea     r8, [rsp+0A8h+IoStatus]; IoStatus
0x14003b8a4  mov     dl, 1; WriteThrough
0x14003b8a6  mov     rcx, [rsp+0A8h+BcbVoid]; Bcb
0x14003b8ae  call    cs:__imp_CcUnpinRepinnedBcb
0x14003b8b5  nop     dword ptr [rax+rax+00h]
0x14003b8ba  mov     ecx, dword ptr [rsp+0A8h+IoStatus]; Exception
0x14003b8be  test    ecx, ecx
0x14003b8c0  jns     short loc_14003B936
0x14003b8c2  mov     [rsi+48h], ecx
0x14003b8c5  mov     edx, 0C00000E9h; GenericException
0x14003b8ca  call    cs:__imp_FsRtlNormalizeNtstatus
0x14003b8d1  nop     dword ptr [rax+rax+00h]
0x14003b8d6  mov     ecx, eax; Status
0x14003b8d8  call    cs:__imp_ExRaiseStatus
0x14003b8e5  lea     rax, [rsp+0A8h+var_58]
0x14003b8ea  mov     [rsp+0A8h+Bcb], rax
0x14003b8ef  lea     r9, [rsp+0A8h+var_48]
0x14003b8f4  xor     r8d, r8d
0x14003b8f7  mov     rdx, rbx
0x14003b8fa  mov     rcx, rsi
0x14003b8fd  call    FatGetDirentFromFcbOrDcb
0x14003b902  nop
0x14003b903  mov     r9b, 1
0x14003b906  mov     r8, [rbx+0B8h]
0x14003b90d  mov     rdx, [rsp+0A8h+var_58]
0x14003b912  mov     rcx, rsi
0x14003b915  call    FatSetDirtyBcb
0x14003b91a  nop
0x14003b91b  mov     rcx, [rsp+0A8h+var_58]; Bcb
0x14003b920  test    rcx, rcx
0x14003b923  jz      short loc_14003B936
0x14003b925  call    cs:__imp_CcUnpinData
0x14003b92c  nop     dword ptr [rax+rax+00h]
0x14003b931  mov     [rsp+0A8h+var_58], r12
0x14003b936  or      dword ptr [rbx+0C0h], 1
0x14003b93d  mov     byte ptr [r13+49h], 1
0x14003b942  mov     eax, 503h
0x14003b947  cmp     [rbx], ax
0x14003b94a  jnz     short loc_14003B9A7
0x14003b94c  mov     rcx, [rbx+0B8h]
0x14003b953  lea     rdx, [rcx+320h]; NotifyList
0x14003b95a  mov     [rsp+0A8h+SubjectContext], r12; SubjectContext
0x14003b95f  mov     [rsp+0A8h+TraverseCallback], r12; TraverseCallback
0x14003b964  mov     [rsp+0A8h+NotifyIrp], r12; NotifyIrp
0x14003b969  mov     [rsp+0A8h+CompletionFilter], r12d; CompletionFilter
0x14003b96e  mov     [rsp+0A8h+IgnoreBuffer], r12b; IgnoreBuffer
0x14003b973  mov     byte ptr [rsp+0A8h+Bcb], r12b; WatchTree
0x14003b978  xor     r9d, r9d; FullDirectoryName
0x14003b97b  mov     r8, [r13+18h]; FsContext
0x14003b97f  mov     rcx, [rcx+330h]; NotifySync
0x14003b986  call    cs:__imp_FsRtlNotifyFullChangeDirectory
0x14003b98d  nop     dword ptr [rax+rax+00h]
0x14003b992  jmp     short loc_14003B9A7
0x14003b994  mov     eax, 0C0000121h
0x14003b999  jmp     short loc_14003B9A9
0x14003b99b  and     dword ptr [r9+0C0h], 0FFFFFFFEh
0x14003b9a3  mov     [r8+49h], r12b
0x14003b9a7  xor     eax, eax
0x14003b9a9  lea     r11, [rsp+0A8h+var_28]
0x14003b9b1  mov     rbx, [r11+30h]
0x14003b9b5  mov     rsi, [r11+40h]
0x14003b9b9  mov     rsp, r11
0x14003b9bc  pop     r15
0x14003b9be  pop     r14
0x14003b9c0  pop     r13
0x14003b9c2  pop     r12
0x14003b9c4  pop     rdi
0x14003b9c5  retn
0x14005e549  push    rbp
0x14005e54b  sub     rsp, 50h
0x14005e54f  mov     rbp, rdx
0x14005e552  movzx   eax, cl
0x14005e555  test    cl, cl
0x14005e557  jz      short loc_14005E572
0x14005e559  mov     rcx, [rbp+0B8h]; Bcb
0x14005e560  test    rcx, rcx
0x14005e563  jz      short loc_14005E572
0x14005e565  call    cs:__imp_CcUnpinData
0x14005e56c  nop     dword ptr [rax+rax+00h]
0x14005e571  nop
0x14005e572  add     rsp, 50h
0x14005e576  pop     rbp
0x14005e577  retn
0x14005e579  push    rbp
0x14005e57b  sub     rsp, 50h
0x14005e57f  mov     rbp, rdx
0x14005e582  mov     rcx, [rbp+50h]; Bcb
0x14005e586  test    rcx, rcx
0x14005e589  jz      short loc_14005E598
0x14005e58b  call    cs:__imp_CcUnpinData
0x14005e592  nop     dword ptr [rax+rax+00h]
0x14005e597  nop
0x14005e598  add     rsp, 50h
0x14005e59c  pop     rbp
0x14005e59d  retn
```
