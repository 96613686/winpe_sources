# FlushAndPurgeCacheForCopyChunk

- ea: `0x140013d10`
- end: `0x140013eb6`
- name: `FlushAndPurgeCacheForCopyChunk`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400146a0`

## callees

- `0x140008030`
- `0x140008190`
- `0x140013d10`
- `0x140017220`

## import_xrefs

- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140013e0a`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140013e54`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140013e0a`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140013e54`
- `ntoskrnl!MmIsFileSectionActive` at `0x140013d53`
- `ntoskrnl!MmIsFileSectionActive` at `0x140013dcf`
- `ntoskrnl!MmIsFileSectionActive` at `0x140013d53`
- `ntoskrnl!MmIsFileSectionActive` at `0x140013dcf`

## pseudocode

```c
__int64 __fastcall FlushAndPurgeCacheForCopyChunk(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v7; // rcx
  __int64 v9; // r8
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int i; // r14d
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+68h] [rbp+10h] BYREF

  v7 = *(_QWORD *)(a2 + 304) + 8LL;
  v15 = 0;
  IoStatus = 0;
  MmIsFileSectionActive(v7, 7, &v15);
  if ( v15 && *(_DWORD *)(a2 + 484) )
    return 3221226549LL;
  LOBYTE(v9) = 1;
  RxAcquirePagingIoResource(a1, a2, v9);
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(v11, CcPurgeRequest, a1 + 412, a2);
  if ( ++*(_DWORD *)(a2 + 636) <= 0x10u
    || (v12 = *(_QWORD *)(a2 + 304) + 8LL, v15 = 0, MmIsFileSectionActive(v12, 7, &v15), v15)
    || *(_DWORD *)(a2 + 184) != *(_DWORD *)(a2 + 188) )
  {
    for ( i = 0; i < a4; ++i )
    {
      CcCoherencyFlushAndPurgeCache(
        (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a2 + 304) + 8LL),
        (PLARGE_INTEGER)(24LL * i + a3 + 8),
        *(_DWORD *)(24LL * i + a3 + 16),
        &IoStatus,
        0);
      if ( IoStatus.Status < 0 )
        break;
    }
  }
  else
  {
    CcCoherencyFlushAndPurgeCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a2 + 304) + 8LL), 0, 0, &IoStatus, 0);
  }
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(v11, CcPurgeCompletion, a1 + 412, a2);
  RxReleasePagingIoResource(a1, a2);
  return (unsigned int)IoStatus.Status;
}

```

## disassembly

```asm
0x140013d10  mov     [rsp+arg_10], rbx
0x140013d15  mov     [rsp+arg_18], rbp
0x140013d1a  push    rsi
0x140013d1b  push    rdi
0x140013d1c  push    r15
0x140013d1e  sub     rsp, 40h
0x140013d22  mov     rdi, rcx
0x140013d25  mov     rbp, r8
0x140013d28  mov     rcx, [rdx+130h]
0x140013d2f  lea     r8, [rsp+58h+arg_8]
0x140013d34  mov     rbx, rdx
0x140013d37  xorps   xmm0, xmm0
0x140013d3a  xor     r15d, r15d
0x140013d3d  add     rcx, 8
0x140013d41  mov     edx, 7
0x140013d46  mov     [rsp+58h+arg_8], r15d
0x140013d4b  mov     esi, r9d
0x140013d4e  movups  xmmword ptr [rsp+58h+IoStatus], xmm0
0x140013d53  call    cs:__imp_MmIsFileSectionActive
0x140013d5a  nop     dword ptr [rax+rax+00h]
0x140013d5f  cmp     [rsp+58h+arg_8], r15d
0x140013d64  jz      short loc_140013D79
0x140013d66  cmp     [rbx+1E4h], r15d
0x140013d6d  jbe     short loc_140013D79
0x140013d6f  mov     eax, 0C0000435h
0x140013d74  jmp     loc_140013EA2
0x140013d79  mov     r8b, 1
0x140013d7c  mov     rdx, rbx
0x140013d7f  mov     rcx, rdi
0x140013d82  call    RxAcquirePagingIoResource
0x140013d87  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140013d8e  jz      short loc_140013DA6
0x140013d90  lea     r8, [rdi+19Ch]
0x140013d97  mov     r9, rbx
0x140013d9a  lea     rdx, CcPurgeRequest
0x140013da1  call    McTemplateK0p_EtwWriteTransfer
0x140013da6  inc     dword ptr [rbx+27Ch]
0x140013dac  cmp     dword ptr [rbx+27Ch], 10h
0x140013db3  jbe     short loc_140013E18
0x140013db5  mov     rcx, [rbx+130h]
0x140013dbc  lea     r8, [rsp+58h+arg_8]
0x140013dc1  add     rcx, 8
0x140013dc5  mov     [rsp+58h+arg_8], r15d
0x140013dca  mov     edx, 7
0x140013dcf  call    cs:__imp_MmIsFileSectionActive
0x140013dd6  nop     dword ptr [rax+rax+00h]
0x140013ddb  cmp     [rsp+58h+arg_8], r15d
0x140013de0  jnz     short loc_140013E18
0x140013de2  mov     eax, [rbx+0BCh]
0x140013de8  cmp     [rbx+0B8h], eax
0x140013dee  jnz     short loc_140013E18
0x140013df0  mov     rcx, [rbx+130h]
0x140013df7  lea     r9, [rsp+58h+IoStatus]; IoStatus
0x140013dfc  add     rcx, 8; SectionObjectPointer
0x140013e00  mov     [rsp+58h+Flags], r15d; Flags
0x140013e05  xor     r8d, r8d; Length
0x140013e08  xor     edx, edx; FileOffset
0x140013e0a  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x140013e11  nop     dword ptr [rax+rax+00h]
0x140013e16  jmp     short loc_140013E74
0x140013e18  mov     [rsp+58h+arg_0], r14
0x140013e1d  mov     r14d, r15d
0x140013e20  test    esi, esi
0x140013e22  jz      short loc_140013E6F
0x140013e24  mov     eax, r14d
0x140013e27  lea     rdx, [rbp+8]
0x140013e2b  lea     r9, [rsp+58h+IoStatus]; IoStatus
0x140013e30  mov     [rsp+58h+Flags], r15d; Flags
0x140013e35  lea     rcx, [rax+rax*2]
0x140013e39  lea     r8, ds:0[rcx*8]
0x140013e41  mov     rcx, [rbx+130h]
0x140013e48  add     rdx, r8; FileOffset
0x140013e4b  add     rcx, 8; SectionObjectPointer
0x140013e4f  mov     r8d, [r8+rbp+10h]; Length
0x140013e54  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x140013e5b  nop     dword ptr [rax+rax+00h]
0x140013e60  cmp     dword ptr [rsp+58h+IoStatus], r15d
0x140013e65  jl      short loc_140013E6F
0x140013e67  inc     r14d
0x140013e6a  cmp     r14d, esi
0x140013e6d  jb      short loc_140013E24
0x140013e6f  mov     r14, [rsp+58h+arg_0]
0x140013e74  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140013e7b  jz      short loc_140013E93
0x140013e7d  lea     r8, [rdi+19Ch]
0x140013e84  mov     r9, rbx
0x140013e87  lea     rdx, CcPurgeCompletion
0x140013e8e  call    McTemplateK0p_EtwWriteTransfer
0x140013e93  mov     rdx, rbx
0x140013e96  mov     rcx, rdi
0x140013e99  call    RxReleasePagingIoResource
0x140013e9e  mov     eax, dword ptr [rsp+58h+IoStatus]
0x140013ea2  mov     rbx, [rsp+58h+arg_10]
0x140013ea7  mov     rbp, [rsp+58h+arg_18]
0x140013eac  add     rsp, 40h
0x140013eb0  pop     r15
0x140013eb2  pop     rdi
0x140013eb3  pop     rsi
0x140013eb4  retn
```
