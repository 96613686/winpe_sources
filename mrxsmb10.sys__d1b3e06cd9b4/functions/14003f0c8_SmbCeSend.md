# SmbCeSend

- ea: `0x14003f0c8`
- end: `0x14003f413`
- name: `SmbCeSend`
- size: `843`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14003de00`
- `0x14003ffe0`
- `0x140045d50`
- `0x140046bb0`

## callees

- `0x1400054b0`
- `0x140005d10`
- `0x140005da0`
- `0x140008d00`
- `0x1400098d0`
- `0x140009f40`
- `0x14000a600`
- `0x14003ec3c`
- `0x14003f0c8`
- `0x14003f618`
- `0x140041468`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003f119`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003f119`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14003f324`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14003f324`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003f33b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003f33b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003f248`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003f248`
- `rdbss!RxPerProcessCountersEnabled` at `0x14003f2a4`
- `rdbss!RxPerProcessCountersEnabled` at `0x14003f2a4`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14003f376`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14003f3ae`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14003f3ca`

## pseudocode

```c
__int64 __fastcall SmbCeSend(char *pContext, int a2, __int64 a3, unsigned int a4)
{
  __int64 *v4; // rbp
  __int64 v5; // r15
  unsigned __int64 v7; // r13
  _WORD *v9; // rbx
  int v10; // edi
  __int64 v11; // r14
  __int64 *v12; // r12
  __int64 v13; // rbx
  int v14; // eax
  bool v15; // sf
  NTSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned __int64 v19; // r9
  unsigned int LockArray_high; // [rsp+80h] [rbp+8h]
  _WORD *v23; // [rsp+90h] [rbp+18h]

  v4 = (__int64 *)a3;
  v5 = *((_QWORD *)pContext + 10);
  v7 = a4;
  if ( (*(_BYTE *)(a3 + 10) & 5) != 0 )
    v9 = *(_WORD **)(a3 + 24);
  else
    v9 = MmMapLockedPagesSpecifyCache((PMDL)a3, 0, MmCached, 0, 0, 0x40000000u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v23 = v9;
  if ( !v9 )
    return (unsigned int)-1073741670;
  v10 = SmbCeIncrementPendingOperations(pContext, 3);
  if ( v10 )
    return (unsigned int)v10;
  v11 = *(_QWORD *)(v5 + 344);
  if ( *(_DWORD *)(v5 + 4) == 2
    && ((*((_DWORD *)pContext + 18) & 1) != 0 || (v10 = SmbCeAssociateExchangeWithMid((PVOID)v5)) == 0) )
  {
    v9[15] = *((_WORD *)pContext + 32);
    if ( (a2 & 0x10000000) == 0 )
    {
      v10 = SmbCeAssociateBufferWithExchange(v5, pContext, v4);
      if ( !v10 )
      {
        v12 = v4;
        goto LABEL_14;
      }
    }
  }
  v12 = 0;
  SmbCeDecrementPendingOperations(pContext, 2);
  if ( !v10 )
  {
LABEL_14:
    SmbCeSetExpiryTime(pContext);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)pContext + 17, -1431655766, -1431655766) != -1431655766 )
    {
      if ( v12 )
        SmbCeDecrementPendingOperations(pContext, 2);
      v10 = -1073741536;
      goto LABEL_38;
    }
    if ( (*(_BYTE *)(v5 + 672) & 8) == 0 )
      goto LABEL_26;
    v13 = *((_QWORD *)pContext + 10) + 400LL;
    if ( *((_QWORD *)pContext + 10) != -400 )
    {
      if ( a2 >= 0 )
      {
        v14 = SmbCopySendBufferForSecuritySignatures(v4, (unsigned int)v7, pContext + 328, pContext + 320);
        v4 = (__int64 *)*((_QWORD *)pContext + 41);
        v10 = v14;
      }
      v15 = v10 < 0;
      if ( v10 )
        goto LABEL_22;
      ExAcquireResourceExclusiveLite(&s_SmbSecuritySignatureResource, 1u);
      v16 = SmbAddSmbSecuritySignature(v13, v4, (_DWORD *)pContext + 60, v7);
      pContext[253] = 1;
      v10 = v16;
      *(_DWORD *)(v13 + 236) += 2;
    }
    v15 = v10 < 0;
LABEL_22:
    if ( v15 )
    {
      if ( v12 )
        SmbCeDecrementPendingOperations(pContext, 2);
LABEL_35:
      if ( ExIsResourceAcquiredExclusiveLite(&s_SmbSecuritySignatureResource) )
        ExReleaseResourceLite(&s_SmbSecuritySignatureResource);
      v9 = v23;
      goto LABEL_38;
    }
    v9 = v23;
LABEL_26:
    if ( !v10 )
    {
      if ( (unsigned __int8)RxPerProcessCountersEnabled() )
      {
        v17 = *((_QWORD *)pContext + 3);
        if ( v17 && *(int *)(v17 + 120) >= 0 )
        {
          if ( *(_DWORD *)(v11 + 368) )
            _InterlockedAdd(
              (volatile signed __int32 *)(v17 + 192),
              _InterlockedExchange((volatile __int32 *)(v11 + 368), 0));
          _InterlockedAdd((volatile signed __int32 *)(v17 + 192), v7);
        }
        else
        {
          _InterlockedAdd((volatile signed __int32 *)(v11 + 368), v7);
        }
      }
      v18 = (unsigned int)a2;
      LODWORD(v18) = a2 & 0x7FFFFFFF;
      pContext[304] = *((_BYTE *)v9 + 4);
      v10 = VctSend(v11, v5, v18, v4, v7, v12);
    }
    goto LABEL_35;
  }
LABEL_38:
  RxMiniSniffer((unsigned int)MRxSmbMiniSniffSend, v5, v7, (_DWORD)pContext, (__int64)v9);
  if ( !v10 || v10 == 259 )
  {
    v19 = (unsigned __int64)LockArray_high << 8;
    _InterlockedIncrement64((volatile signed __int64 *)(v19 + MRxSmbLegacyPerfCtrs + 56));
    _InterlockedAdd64((volatile signed __int64 *)(v19 + MRxSmbLegacyPerfCtrs + 48), v7);
  }
  else
  {
    *((_DWORD *)pContext + 10) = v10;
    _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)LockArray_high << 8) + MRxSmbLegacyPerfCtrs + 96));
  }
  SmbCeDecrementPendingOperationsAndFinalize(pContext);
  if ( (a2 & 0x10000000) == 0 )
    return 259;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003f0c8  mov     [rsp+arg_18], rbx
0x14003f0cd  mov     [rsp+arg_8], edx
0x14003f0d1  push    rbp
0x14003f0d2  push    rsi
0x14003f0d3  push    rdi
0x14003f0d4  push    r12
0x14003f0d6  push    r13
0x14003f0d8  push    r14
0x14003f0da  push    r15
0x14003f0dc  sub     rsp, 40h
0x14003f0e0  test    byte ptr [r8+0Ah], 5
0x14003f0e5  mov     rbp, r8
0x14003f0e8  mov     r15, [rcx+50h]
0x14003f0ec  mov     r12d, edx
0x14003f0ef  mov     r13d, r9d
0x14003f0f2  mov     rsi, rcx
0x14003f0f5  jz      short loc_14003F0FD
0x14003f0f7  mov     rbx, [r8+18h]
0x14003f0fb  jmp     short loc_14003F128
0x14003f0fd  xor     r9d, r9d; RequestedAddress
0x14003f100  mov     [rsp+78h+Priority], 40000000h; Priority
0x14003f108  xor     edx, edx; AccessMode
0x14003f10a  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14003f112  mov     rcx, rbp; MemoryDescriptorList
0x14003f115  lea     r8d, [r9+1]; CacheType
0x14003f119  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003f120  nop     dword ptr [rax+rax+00h]
0x14003f125  mov     rbx, rax
0x14003f128  mov     eax, gs:1A4h
0x14003f130  mov     [rsp+78h+arg_0], eax
0x14003f137  mov     [rsp+78h+arg_10], rbx
0x14003f13f  test    rbx, rbx
0x14003f142  jnz     short loc_14003F14E
0x14003f144  mov     edi, 0C000009Ah
0x14003f149  jmp     loc_14003F3F8
0x14003f14e  mov     edx, 3
0x14003f153  mov     rcx, rsi
0x14003f156  call    SmbCeIncrementPendingOperations
0x14003f15b  mov     edi, eax
0x14003f15d  test    eax, eax
0x14003f15f  jnz     loc_14003F3F8
0x14003f165  cmp     dword ptr [r15+4], 2
0x14003f16a  mov     r14, [r15+158h]
0x14003f171  jnz     short loc_14003F1B4
0x14003f173  mov     ecx, [rsi+48h]
0x14003f176  test    cl, 1
0x14003f179  jnz     short loc_14003F18C
0x14003f17b  mov     rdx, rsi
0x14003f17e  mov     rcx, r15; pContext
0x14003f181  call    SmbCeAssociateExchangeWithMid
0x14003f186  mov     edi, eax
0x14003f188  test    eax, eax
0x14003f18a  jnz     short loc_14003F1B4
0x14003f18c  movzx   eax, word ptr [rsi+40h]
0x14003f190  mov     [rbx+1Eh], ax
0x14003f194  bt      r12d, 1Ch
0x14003f199  jb      short loc_14003F1B4
0x14003f19b  mov     r8, rbp
0x14003f19e  mov     rdx, rsi
0x14003f1a1  mov     rcx, r15
0x14003f1a4  call    SmbCeAssociateBufferWithExchange
0x14003f1a9  mov     edi, eax
0x14003f1ab  test    eax, eax
0x14003f1ad  jnz     short loc_14003F1B4
0x14003f1af  mov     r12, rbp
0x14003f1b2  jmp     short loc_14003F1CC
0x14003f1b4  xor     r12d, r12d
0x14003f1b7  mov     rcx, rsi
0x14003f1ba  lea     edx, [r12+2]
0x14003f1bf  call    SmbCeDecrementPendingOperations
0x14003f1c4  test    edi, edi
0x14003f1c6  jnz     loc_14003F34F
0x14003f1cc  mov     rcx, rsi
0x14003f1cf  call    SmbCeSetExpiryTime
0x14003f1d4  mov     ecx, 0AAAAAAAAh
0x14003f1d9  mov     eax, ecx
0x14003f1db  lock cmpxchg [rsi+44h], ecx
0x14003f1e0  cmp     eax, 0AAAAAAAAh
0x14003f1e5  jnz     loc_14003F395
0x14003f1eb  test    byte ptr [r15+2A0h], 8
0x14003f1f3  jz      loc_14003F2A0
0x14003f1f9  mov     rbx, [rsi+50h]
0x14003f1fd  add     rbx, 190h
0x14003f204  mov     [rsp+78h+var_48], rbx
0x14003f209  jz      short loc_14003F279
0x14003f20b  cmp     [rsp+78h+arg_8], 0
0x14003f213  jl      short loc_14003F23B
0x14003f215  lea     rbx, [rsi+148h]
0x14003f21c  mov     edx, r13d
0x14003f21f  mov     r8, rbx
0x14003f222  lea     r9, [rsi+140h]
0x14003f229  mov     rcx, rbp
0x14003f22c  call    SmbCopySendBufferForSecuritySignatures
0x14003f231  mov     rbp, [rbx]
0x14003f234  mov     edi, eax
0x14003f236  mov     rbx, [rsp+78h+var_48]
0x14003f23b  test    edi, edi
0x14003f23d  jnz     short loc_14003F27B
0x14003f23f  mov     dl, 1; Wait
0x14003f241  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14003f248  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003f24f  nop     dword ptr [rax+rax+00h]
0x14003f254  lea     r8, [rsi+0F0h]
0x14003f25b  mov     r9d, r13d
0x14003f25e  mov     rdx, rbp
0x14003f261  mov     rcx, rbx
0x14003f264  call    SmbAddSmbSecuritySignature
0x14003f269  mov     byte ptr [rsi+0FDh], 1
0x14003f270  mov     edi, eax
0x14003f272  add     dword ptr [rbx+0ECh], 2
0x14003f279  test    edi, edi
0x14003f27b  jns     short loc_14003F298
0x14003f27d  test    r12, r12
0x14003f280  jz      loc_14003F31D
0x14003f286  mov     edx, 2
0x14003f28b  mov     rcx, rsi
0x14003f28e  call    SmbCeDecrementPendingOperations
0x14003f293  jmp     loc_14003F31D
0x14003f298  mov     rbx, [rsp+78h+arg_10]
0x14003f2a0  test    edi, edi
0x14003f2a2  jnz     short loc_14003F31D
0x14003f2a4  call    cs:__imp_RxPerProcessCountersEnabled
0x14003f2ab  nop     dword ptr [rax+rax+00h]
0x14003f2b0  test    al, al
0x14003f2b2  jz      short loc_14003F2ED
0x14003f2b4  mov     rcx, [rsi+18h]
0x14003f2b8  test    rcx, rcx
0x14003f2bb  jz      short loc_14003F2E5
0x14003f2bd  cmp     [rcx+78h], edi
0x14003f2c0  jl      short loc_14003F2E5
0x14003f2c2  cmp     [r14+170h], edi
0x14003f2c9  jz      short loc_14003F2DB
0x14003f2cb  xor     eax, eax
0x14003f2cd  xchg    eax, [r14+170h]
0x14003f2d4  lock add [rcx+0C0h], eax
0x14003f2db  lock add [rcx+0C0h], r13d
0x14003f2e3  jmp     short loc_14003F2ED
0x14003f2e5  lock add [r14+170h], r13d
0x14003f2ed  mov     r8d, [rsp+78h+arg_8]
0x14003f2f5  mov     r9, rbp
0x14003f2f8  mov     al, [rbx+4]
0x14003f2fb  btr     r8d, 1Fh
0x14003f300  mov     qword ptr [rsp+78h+Priority], r12
0x14003f305  mov     rdx, r15
0x14003f308  mov     rcx, r14
0x14003f30b  mov     [rsi+130h], al
0x14003f311  mov     [rsp+78h+BugCheckOnFailure], r13d
0x14003f316  call    VctSend
0x14003f31b  mov     edi, eax
0x14003f31d  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14003f324  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14003f32b  nop     dword ptr [rax+rax+00h]
0x14003f330  test    al, al
0x14003f332  jz      short loc_14003F347
0x14003f334  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14003f33b  call    cs:__imp_ExReleaseResourceLite
0x14003f342  nop     dword ptr [rax+rax+00h]
0x14003f347  mov     rbx, [rsp+78h+arg_10]
0x14003f34f  mov     r9, rsi
0x14003f352  mov     qword ptr [rsp+78h+BugCheckOnFailure], rbx
0x14003f357  mov     r8d, r13d
0x14003f35a  lea     rcx, MRxSmbMiniSniffSend; "Send"
0x14003f361  mov     rdx, r15
0x14003f364  call    RxMiniSniffer
0x14003f369  mov     ebx, 103h
0x14003f36e  test    edi, edi
0x14003f370  jz      short loc_14003F3AE
0x14003f372  cmp     edi, ebx
0x14003f374  jz      short loc_14003F3AE
0x14003f376  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14003f37d  mov     edx, [rsp+78h+arg_0]
0x14003f384  mov     [rsi+28h], edi
0x14003f387  shl     rdx, 8
0x14003f38b  mov     rcx, [rax]
0x14003f38e  lock inc dword ptr [rdx+rcx+60h]
0x14003f393  jmp     short loc_14003F3DD
0x14003f395  test    r12, r12
0x14003f398  jz      short loc_14003F3A7
0x14003f39a  mov     edx, 2
0x14003f39f  mov     rcx, rsi
0x14003f3a2  call    SmbCeDecrementPendingOperations
0x14003f3a7  mov     edi, 0C0000120h
0x14003f3ac  jmp     short loc_14003F34F
0x14003f3ae  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14003f3b5  mov     r9d, [rsp+78h+arg_0]
0x14003f3bd  shl     r9, 8
0x14003f3c1  mov     rcx, [rax]
0x14003f3c4  lock inc qword ptr [r9+rcx+38h]
0x14003f3ca  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14003f3d1  mov     r8, r13
0x14003f3d4  mov     rcx, [rax]
0x14003f3d7  lock add [r9+rcx+30h], r8
0x14003f3dd  mov     edx, 1
0x14003f3e2  mov     rcx, rsi; pContext
0x14003f3e5  call    SmbCeDecrementPendingOperationsAndFinalize
0x14003f3ea  test    [rsp+78h+arg_8], 10000000h
0x14003f3f5  cmovz   edi, ebx
0x14003f3f8  mov     rbx, [rsp+78h+arg_18]
0x14003f400  mov     eax, edi
0x14003f402  add     rsp, 40h
0x14003f406  pop     r15
0x14003f408  pop     r14
0x14003f40a  pop     r13
0x14003f40c  pop     r12
0x14003f40e  pop     rdi
0x14003f40f  pop     rsi
0x14003f410  pop     rbp
0x14003f411  retn
```
