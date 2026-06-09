# TxfFreeTopsRange

- ea: `0x140100b14`
- end: `0x140100e32`
- name: `TxfFreeTopsRange`
- size: `798`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140039038`
- `0x14010adfc`
- `0x14029afbc`

## callees

- `0x140100b14`
- `0x14020bb70`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x140100d09`
- `ntoskrnl!RtlClearBits` at `0x140100d5c`
- `ntoskrnl!RtlClearBits` at `0x140100d09`
- `ntoskrnl!RtlClearBits` at `0x140100d5c`
- `ntoskrnl!CcPinRead` at `0x140100c76`
- `ntoskrnl!CcPinRead` at `0x140100c76`
- `ntoskrnl!CcPurgeCacheSection` at `0x140100c3d`
- `ntoskrnl!CcPurgeCacheSection` at `0x140100c3d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140100e0b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140100e0b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140100da6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140100da6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140100cf0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140100d43`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140100cf0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140100d43`
- `ntoskrnl!CcUnpinData` at `0x140100cae`
- `ntoskrnl!CcUnpinData` at `0x140100cae`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100cd3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100d20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100d79`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100cd3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100d20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140100d79`
- `ntoskrnl!CcFlushCache` at `0x140100c9e`
- `ntoskrnl!CcFlushCache` at `0x140100c9e`

## pseudocode

```c
char __fastcall TxfFreeTopsRange(__int64 a1, __int64 a2, unsigned __int64 *a3, unsigned int a4, unsigned int a5)
{
  unsigned int v6; // r14d
  __int64 v8; // r13
  unsigned __int64 v10; // r15
  ULONG v11; // esi
  __int64 v12; // r8
  char result; // al
  unsigned __int64 v14; // r8
  const signed __int64 **v15; // r9
  unsigned __int64 v16; // rdx
  ULONG v17; // ebx
  int v18; // ebx
  __int64 i; // rcx
  _QWORD *v20; // rdx
  ULONG v21; // r8d
  PVOID Buffer; // [rsp+30h] [rbp-10h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+80h] [rbp+40h] BYREF
  PVOID Bcb; // [rsp+90h] [rbp+50h] BYREF

  v6 = a5;
  v8 = a4;
  v10 = *a3 >> 12;
  Bcb = 0;
  Buffer = 0;
  FileOffset.QuadPart = 0;
  v11 = (a4 + 4095) >> 12;
  if ( (a5 & 1) != 0 )
  {
    a5 &= 0x10u;
    if ( (v6 & 0x10) == 0 )
    {
      v12 = v6 >> 3;
      LOBYTE(v12) = (v6 & 8) != 0;
      result = NtfsAcquireScbPagingResourceExclusive(0, *(_QWORD *)(a1 + 280), v12);
      if ( !result )
        return result;
    }
    v14 = *a3;
    v15 = (const signed __int64 **)(a1 + 344);
    v16 = (*a3 + 4095) & 0xFFFFFFFFFFFFF000uLL;
    if ( v16 == *a3 )
    {
      v16 = *a3;
    }
    else if ( !_bittest64(*v15, (unsigned int)(v10 - 1)) )
    {
      v16 = v14 & 0xFFFFFFFFFFFFF000uLL;
    }
    FileOffset.QuadPart = v16;
    if ( ((v14 + v8) & 0xFFFFFFFFFFFFF000uLL) == v14 + v8 )
    {
      v17 = v8 + *(_DWORD *)a3 - v16;
    }
    else
    {
      v18 = v8 + *(_DWORD *)a3;
      if ( !_bittest64(*v15, (unsigned int)v10 + v11) )
        v18 += 4095;
      v17 = (v18 & 0xFFFFF000) - FileOffset.LowPart;
    }
    if ( v17 )
    {
      CcPurgeCacheSection(
        (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(a1 + 280) + 288LL) + 16LL),
        &FileOffset,
        v17,
        0);
      CcPinRead(*(PFILE_OBJECT *)(*(_QWORD *)(a1 + 280) + 280LL), &FileOffset, v17, 5u, &Bcb, &Buffer);
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(a1 + 280) + 288LL) + 16LL), &FileOffset, v17, 0);
      CcUnpinData(Bcb);
      Bcb = 0;
    }
    if ( !a5 )
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a1 + 280) + 16LL));
    if ( (v6 & 0x20) == 0 )
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 368), 1u);
    RtlClearBits((PRTL_BITMAP)(a1 + 336), v10, v11);
    if ( (v6 & 0x20) == 0 )
      ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
  }
  if ( (v6 & 2) != 0 )
  {
    if ( (v6 & 0x20) == 0 )
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 368), 1u);
    RtlClearBits((PRTL_BITMAP)(a1 + 304), v10, v11);
    *(_DWORD *)(a1 + 300) += v11;
    if ( (v6 & 0x20) == 0 )
      ExReleaseResourceLite(*(PERESOURCE *)(a1 + 368));
  }
  if ( (v6 & 4) != 0 && *(_QWORD *)(a2 + 296) )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 6312LL));
    for ( i = *(_QWORD *)(a2 + 296); i; i = *(_QWORD *)(i + 24) )
    {
      v20 = *(_QWORD **)(a2 + 296);
      v21 = (unsigned __int64)v11 <= v20[1] ? v11 : *((_DWORD *)v20 + 2);
      if ( *v20 )
        *(_QWORD *)(*v20 + 16LL) -= (unsigned __int64)v21 << 12;
      *(_QWORD *)(*(_QWORD *)(a2 + 296) + 8LL) -= v21;
      v11 -= v21;
      if ( !v11 )
        break;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 6312LL));
  }
  return 1;
}

```

## disassembly

```asm
0x140100b14  mov     [rsp-38h+arg_8], rbx
0x140100b19  push    rbp
0x140100b1a  push    rsi
0x140100b1b  push    rdi
0x140100b1c  push    r12
0x140100b1e  push    r13
0x140100b20  push    r14
0x140100b22  push    r15
0x140100b24  mov     rbp, rsp
0x140100b27  sub     rsp, 40h
0x140100b2b  mov     r15, [r8]
0x140100b2e  mov     rbx, r8
0x140100b31  mov     r14d, [rbp+arg_20]
0x140100b35  mov     r12, rdx
0x140100b38  mov     r13d, r9d
0x140100b3b  mov     rdi, rcx
0x140100b3e  shr     r15, 0Ch
0x140100b42  mov     [rbp+arg_10], 0
0x140100b4a  mov     [rbp+var_10], 0
0x140100b52  lea     esi, [r13+0FFFh]
0x140100b59  mov     qword ptr [rbp+FileOffset], 0
0x140100b61  shr     esi, 0Ch
0x140100b64  test    r14b, 1
0x140100b68  jz      loc_140100D2C
0x140100b6e  mov     eax, r14d
0x140100b71  and     eax, 10h
0x140100b74  mov     [rbp+arg_20], eax
0x140100b77  jnz     short loc_140100B9A
0x140100b79  mov     rdx, [rcx+118h]
0x140100b80  mov     r8d, r14d
0x140100b83  shr     r8d, 3
0x140100b87  xor     ecx, ecx
0x140100b89  and     r8b, 1
0x140100b8d  call    NtfsAcquireScbPagingResourceExclusive
0x140100b92  test    al, al
0x140100b94  jz      loc_140100E19
0x140100b9a  mov     r8, [rbx]
0x140100b9d  lea     r9, [rdi+158h]
0x140100ba4  mov     r10, 0FFFFFFFFFFFFF000h
0x140100bab  lea     rdx, [r8+0FFFh]
0x140100bb2  and     rdx, r10
0x140100bb5  cmp     rdx, r8
0x140100bb8  jnz     short loc_140100BBF
0x140100bba  mov     rdx, r8
0x140100bbd  jmp     short loc_140100BD7
0x140100bbf  mov     rax, [r9]
0x140100bc2  lea     ecx, [r15-1]
0x140100bc6  bt      [rax], rcx
0x140100bca  setb    al
0x140100bcd  test    al, al
0x140100bcf  jnz     short loc_140100BD7
0x140100bd1  mov     rdx, r8
0x140100bd4  and     rdx, r10
0x140100bd7  lea     rcx, [r8+r13]
0x140100bdb  mov     qword ptr [rbp+FileOffset], rdx
0x140100bdf  mov     rax, rcx
0x140100be2  and     rax, r10
0x140100be5  cmp     rax, rcx
0x140100be8  jnz     short loc_140100BF3
0x140100bea  mov     ebx, [rbx]
0x140100bec  sub     ebx, edx
0x140100bee  add     ebx, r13d
0x140100bf1  jmp     short loc_140100C19
0x140100bf3  mov     rax, [r9]
0x140100bf6  lea     ecx, [r15+rsi]
0x140100bfa  bt      [rax], rcx
0x140100bfe  mov     ebx, [rbx]
0x140100c00  setb    cl
0x140100c03  add     ebx, r13d
0x140100c06  test    cl, cl
0x140100c08  jnz     short loc_140100C10
0x140100c0a  add     ebx, 0FFFh
0x140100c10  and     ebx, 0FFFFF000h
0x140100c16  sub     ebx, dword ptr [rbp+FileOffset]
0x140100c19  test    ebx, ebx
0x140100c1b  jz      loc_140100CC2
0x140100c21  mov     rax, [rdi+118h]
0x140100c28  lea     rdx, [rbp+FileOffset]; FileOffset
0x140100c2c  xor     r9d, r9d; Flags
0x140100c2f  mov     r8d, ebx; Length
0x140100c32  mov     rcx, [rax+120h]
0x140100c39  add     rcx, 10h; SectionObjectPointer
0x140100c3d  call    cs:__imp_CcPurgeCacheSection
0x140100c44  nop     dword ptr [rax+rax+00h]
0x140100c49  mov     rcx, [rdi+118h]
0x140100c50  lea     rax, [rbp+var_10]
0x140100c54  mov     [rsp+40h+Buffer], rax; Buffer
0x140100c59  lea     rdx, [rbp+FileOffset]; FileOffset
0x140100c5d  lea     rax, [rbp+arg_10]
0x140100c61  mov     r9d, 5; Flags
0x140100c67  mov     r8d, ebx; Length
0x140100c6a  mov     [rsp+40h+Bcb], rax; Bcb
0x140100c6f  mov     rcx, [rcx+118h]; FileObject
0x140100c76  call    cs:__imp_CcPinRead
0x140100c7d  nop     dword ptr [rax+rax+00h]
0x140100c82  mov     rax, [rdi+118h]
0x140100c89  lea     rdx, [rbp+FileOffset]; FileOffset
0x140100c8d  xor     r9d, r9d; IoStatus
0x140100c90  mov     r8d, ebx; Length
0x140100c93  mov     rcx, [rax+120h]
0x140100c9a  add     rcx, 10h; SectionObjectPointer
0x140100c9e  call    cs:__imp_CcFlushCache
0x140100ca5  nop     dword ptr [rax+rax+00h]
0x140100caa  mov     rcx, [rbp+arg_10]; Bcb
0x140100cae  call    cs:__imp_CcUnpinData
0x140100cb5  nop     dword ptr [rax+rax+00h]
0x140100cba  mov     [rbp+arg_10], 0
0x140100cc2  cmp     [rbp+arg_20], 0
0x140100cc6  jnz     short loc_140100CDF
0x140100cc8  mov     rcx, [rdi+118h]
0x140100ccf  mov     rcx, [rcx+10h]; Resource
0x140100cd3  call    cs:__imp_ExReleaseResourceLite
0x140100cda  nop     dword ptr [rax+rax+00h]
0x140100cdf  mov     ebx, r14d
0x140100ce2  and     ebx, 20h
0x140100ce5  jnz     short loc_140100CFC
0x140100ce7  mov     rcx, [rdi+170h]; Resource
0x140100cee  mov     dl, 1; Wait
0x140100cf0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140100cf7  nop     dword ptr [rax+rax+00h]
0x140100cfc  mov     r8d, esi; NumberToClear
0x140100cff  lea     rcx, [rdi+150h]; BitMapHeader
0x140100d06  mov     edx, r15d; StartingIndex
0x140100d09  call    cs:__imp_RtlClearBits
0x140100d10  nop     dword ptr [rax+rax+00h]
0x140100d15  test    ebx, ebx
0x140100d17  jnz     short loc_140100D2C
0x140100d19  mov     rcx, [rdi+170h]; Resource
0x140100d20  call    cs:__imp_ExReleaseResourceLite
0x140100d27  nop     dword ptr [rax+rax+00h]
0x140100d2c  test    r14b, 2
0x140100d30  jz      short loc_140100D85
0x140100d32  mov     ebx, r14d
0x140100d35  and     ebx, 20h
0x140100d38  jnz     short loc_140100D4F
0x140100d3a  mov     rcx, [rdi+170h]; Resource
0x140100d41  mov     dl, 1; Wait
0x140100d43  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140100d4a  nop     dword ptr [rax+rax+00h]
0x140100d4f  lea     rcx, [rdi+130h]; BitMapHeader
0x140100d56  mov     r8d, esi; NumberToClear
0x140100d59  mov     edx, r15d; StartingIndex
0x140100d5c  call    cs:__imp_RtlClearBits
0x140100d63  nop     dword ptr [rax+rax+00h]
0x140100d68  add     [rdi+12Ch], esi
0x140100d6e  test    ebx, ebx
0x140100d70  jnz     short loc_140100D85
0x140100d72  mov     rcx, [rdi+170h]; Resource
0x140100d79  call    cs:__imp_ExReleaseResourceLite
0x140100d80  nop     dword ptr [rax+rax+00h]
0x140100d85  test    r14b, 4
0x140100d89  jz      loc_140100E17
0x140100d8f  cmp     qword ptr [r12+128h], 0
0x140100d98  jz      short loc_140100E17
0x140100d9a  mov     rcx, [rdi+10h]
0x140100d9e  mov     ebx, 18A8h
0x140100da3  add     rcx, rbx; FastMutex
0x140100da6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140100dad  nop     dword ptr [rax+rax+00h]
0x140100db2  mov     rcx, [r12+128h]
0x140100dba  jmp     short loc_140100DFF
0x140100dbc  mov     rdx, [r12+128h]
0x140100dc4  mov     eax, esi
0x140100dc6  cmp     rax, [rdx+8]
0x140100dca  jbe     short loc_140100DD2
0x140100dcc  mov     r8d, [rdx+8]
0x140100dd0  jmp     short loc_140100DD5
0x140100dd2  mov     r8d, esi
0x140100dd5  mov     r9, [rdx]
0x140100dd8  mov     edx, r8d
0x140100ddb  test    r9, r9
0x140100dde  jz      short loc_140100DEA
0x140100de0  mov     eax, edx
0x140100de2  shl     rax, 0Ch
0x140100de6  sub     [r9+10h], rax
0x140100dea  mov     rax, [r12+128h]
0x140100df2  sub     [rax+8], rdx
0x140100df6  sub     esi, r8d
0x140100df9  jz      short loc_140100E04
0x140100dfb  mov     rcx, [rcx+18h]
0x140100dff  test    rcx, rcx
0x140100e02  jnz     short loc_140100DBC
0x140100e04  mov     rcx, [rdi+10h]
0x140100e08  add     rcx, rbx; FastMutex
0x140100e0b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140100e12  nop     dword ptr [rax+rax+00h]
0x140100e17  mov     al, 1
0x140100e19  mov     rbx, [rsp+40h+arg_8]
0x140100e21  add     rsp, 40h
0x140100e25  pop     r15
0x140100e27  pop     r14
0x140100e29  pop     r13
0x140100e2b  pop     r12
0x140100e2d  pop     rdi
0x140100e2e  pop     rsi
0x140100e2f  pop     rbp
0x140100e30  retn
```
