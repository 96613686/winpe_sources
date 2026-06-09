# SmbCeSendToServer

- ea: `0x14003f41c`
- end: `0x14003f60f`
- name: `SmbCeSendToServer`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140012940`

## callees

- `0x140009f40`
- `0x14003ec3c`
- `0x14003f41c`
- `0x14003f618`
- `0x140041468`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003f468`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003f468`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14003f554`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14003f554`
- `ntoskrnl!IoFreeMdl` at `0x14003f590`
- `ntoskrnl!IoFreeMdl` at `0x14003f590`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003f56b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003f56b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003f4e9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003f4e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f581`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f581`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14003f59c`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14003f5bf`

## pseudocode

```c
__int64 __fastcall SmbCeSendToServer(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  __int64 *v4; // rbx
  unsigned __int64 v5; // r15
  PVOID v7; // r14
  unsigned int LockArray_high; // r12d
  void *v9; // rsi
  int v10; // edi
  unsigned __int64 v11; // r8
  void *v13; // [rsp+30h] [rbp-38h] BYREF
  int v14; // [rsp+78h] [rbp+10h] BYREF
  __int64 *v15; // [rsp+80h] [rbp+18h] BYREF

  v14 = a2;
  v4 = (__int64 *)a3;
  v5 = a4;
  if ( (*(_BYTE *)(a3 + 10) & 5) != 0 )
    v7 = *(PVOID *)(a3 + 24);
  else
    v7 = MmMapLockedPagesSpecifyCache((PMDL)a3, 0, MmCached, 0, 0, 0x40000000u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v9 = 0;
  v15 = v4;
  v13 = 0;
  if ( v7 )
  {
    if ( *(_QWORD *)(a1 + 344) )
    {
      if ( (*(_BYTE *)(a1 + 672) & 8) != 0 )
      {
        v14 = 0;
        if ( a1 != -400 )
        {
          if ( (unsigned int)SmbCopySendBufferForSecuritySignatures(v4, (unsigned int)v5, &v15, &v13) )
          {
            v4 = v15;
          }
          else
          {
            ExAcquireResourceExclusiveLite(&s_SmbSecuritySignatureResource, 1u);
            v4 = v15;
            SmbAddSmbSecuritySignature(a1 + 400, v15, &v14, v5);
            ++*(_DWORD *)(a1 + 636);
          }
          v9 = v13;
        }
      }
      v10 = VctSend(*(_QWORD *)(a1 + 344), a1, 0x10000000, v4, v5, 0);
      if ( ExIsResourceAcquiredExclusiveLite(&s_SmbSecuritySignatureResource) )
        ExReleaseResourceLite(&s_SmbSecuritySignatureResource);
      if ( v9 )
      {
        ExFreePoolWithTag(v9, 0);
        IoFreeMdl((PMDL)v4);
      }
      v11 = (unsigned __int64)LockArray_high << 8;
      if ( v10 >= 0 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v11 + MRxSmbLegacyPerfCtrs + 56));
        _InterlockedAdd64((volatile signed __int64 *)(v11 + MRxSmbLegacyPerfCtrs + 48), v5);
        RxMiniSniffer((unsigned int)MRxSmbMiniSniffSendSrv, a1, v5, 0, (__int64)v7);
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)(v11 + MRxSmbLegacyPerfCtrs + 96));
      }
    }
    else
    {
      return (unsigned int)-1073741300;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003f41c  mov     [rsp+arg_0], rbx
0x14003f421  mov     [rsp+arg_18], rbp
0x14003f426  mov     [rsp+arg_8], edx
0x14003f42a  push    rsi
0x14003f42b  push    rdi
0x14003f42c  push    r12
0x14003f42e  push    r14
0x14003f430  push    r15
0x14003f432  sub     rsp, 40h
0x14003f436  test    byte ptr [r8+0Ah], 5
0x14003f43b  mov     rbx, r8
0x14003f43e  mov     r15d, r9d
0x14003f441  mov     rbp, rcx
0x14003f444  jz      short loc_14003F44C
0x14003f446  mov     r14, [r8+18h]
0x14003f44a  jmp     short loc_14003F477
0x14003f44c  xor     r9d, r9d; RequestedAddress
0x14003f44f  mov     [rsp+68h+Priority], 40000000h; Priority
0x14003f457  xor     edx, edx; AccessMode
0x14003f459  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14003f461  mov     rcx, rbx; MemoryDescriptorList
0x14003f464  lea     r8d, [r9+1]; CacheType
0x14003f468  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003f46f  nop     dword ptr [rax+rax+00h]
0x14003f474  mov     r14, rax
0x14003f477  mov     r12d, gs:1A4h
0x14003f480  xor     esi, esi
0x14003f482  mov     [rsp+68h+arg_10], rbx
0x14003f48a  mov     [rsp+68h+var_38], rsi
0x14003f48f  test    r14, r14
0x14003f492  jnz     short loc_14003F49E
0x14003f494  mov     edi, 0C000009Ah
0x14003f499  jmp     loc_14003F5F3
0x14003f49e  cmp     [rbp+158h], rsi
0x14003f4a5  jz      loc_14003F5EE
0x14003f4ab  test    byte ptr [rbp+2A0h], 8
0x14003f4b2  jz      short loc_14003F525
0x14003f4b4  lea     rdi, [rbp+190h]
0x14003f4bb  mov     [rsp+68h+arg_8], esi
0x14003f4bf  test    rdi, rdi
0x14003f4c2  jz      short loc_14003F525
0x14003f4c4  lea     r9, [rsp+68h+var_38]
0x14003f4c9  mov     edx, r15d
0x14003f4cc  lea     r8, [rsp+68h+arg_10]
0x14003f4d4  mov     rcx, rbx
0x14003f4d7  call    SmbCopySendBufferForSecuritySignatures
0x14003f4dc  test    eax, eax
0x14003f4de  jnz     short loc_14003F518
0x14003f4e0  mov     dl, 1; Wait
0x14003f4e2  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14003f4e9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003f4f0  nop     dword ptr [rax+rax+00h]
0x14003f4f5  mov     rbx, [rsp+68h+arg_10]
0x14003f4fd  lea     r8, [rsp+68h+arg_8]
0x14003f502  mov     rdx, rbx
0x14003f505  mov     r9d, r15d
0x14003f508  mov     rcx, rdi
0x14003f50b  call    SmbAddSmbSecuritySignature
0x14003f510  inc     dword ptr [rdi+0ECh]
0x14003f516  jmp     short loc_14003F520
0x14003f518  mov     rbx, [rsp+68h+arg_10]
0x14003f520  mov     rsi, [rsp+68h+var_38]
0x14003f525  mov     rcx, [rbp+158h]
0x14003f52c  mov     r9, rbx
0x14003f52f  mov     qword ptr [rsp+68h+Priority], 0
0x14003f538  mov     r8d, 10000000h
0x14003f53e  mov     rdx, rbp
0x14003f541  mov     [rsp+68h+BugCheckOnFailure], r15d
0x14003f546  call    VctSend
0x14003f54b  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14003f552  mov     edi, eax
0x14003f554  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14003f55b  nop     dword ptr [rax+rax+00h]
0x14003f560  test    al, al
0x14003f562  jz      short loc_14003F577
0x14003f564  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x14003f56b  call    cs:__imp_ExReleaseResourceLite
0x14003f572  nop     dword ptr [rax+rax+00h]
0x14003f577  test    rsi, rsi
0x14003f57a  jz      short loc_14003F59C
0x14003f57c  xor     edx, edx; Tag
0x14003f57e  mov     rcx, rsi; P
0x14003f581  call    cs:__imp_ExFreePoolWithTag
0x14003f588  nop     dword ptr [rax+rax+00h]
0x14003f58d  mov     rcx, rbx; Mdl
0x14003f590  call    cs:__imp_IoFreeMdl
0x14003f597  nop     dword ptr [rax+rax+00h]
0x14003f59c  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14003f5a3  mov     r8d, r12d
0x14003f5a6  shl     r8, 8
0x14003f5aa  mov     rcx, [rax]
0x14003f5ad  test    edi, edi
0x14003f5af  jns     short loc_14003F5B9
0x14003f5b1  lock inc dword ptr [r8+rcx+60h]
0x14003f5b7  jmp     short loc_14003F5F3
0x14003f5b9  lock inc qword ptr [r8+rcx+38h]
0x14003f5bf  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14003f5c6  mov     rdx, r15
0x14003f5c9  mov     rcx, [rax]
0x14003f5cc  lock add [r8+rcx+30h], rdx
0x14003f5d2  xor     r9d, r9d
0x14003f5d5  mov     qword ptr [rsp+68h+BugCheckOnFailure], r14
0x14003f5da  mov     r8d, r15d
0x14003f5dd  lea     rcx, MRxSmbMiniSniffSendSrv; "SendToServer"
0x14003f5e4  mov     rdx, rbp
0x14003f5e7  call    RxMiniSniffer
0x14003f5ec  jmp     short loc_14003F5F3
0x14003f5ee  mov     edi, 0C000020Ch
0x14003f5f3  lea     r11, [rsp+68h+var_28]
0x14003f5f8  mov     eax, edi
0x14003f5fa  mov     rbx, [r11+30h]
0x14003f5fe  mov     rbp, [r11+48h]
0x14003f602  mov     rsp, r11
0x14003f605  pop     r15
0x14003f607  pop     r14
0x14003f609  pop     r12
0x14003f60b  pop     rdi
0x14003f60c  pop     rsi
0x14003f60d  retn
```
