# SmbCeInitializeTransactionParameters

- ea: `0x14004b830`
- end: `0x14004bc35`
- name: `SmbCeInitializeTransactionParameters`
- size: `1029`
- prototype: `__int64 __fastcall(struct _MDL *, unsigned __int16, __int64, unsigned int, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14004b5f0`

## callees

- `0x14004b830`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14004bbcb`
- `ntoskrnl!MmUnlockPages` at `0x14004bbee`
- `ntoskrnl!MmUnlockPages` at `0x14004bc15`
- `ntoskrnl!MmUnlockPages` at `0x14004bbcb`
- `ntoskrnl!MmUnlockPages` at `0x14004bbee`
- `ntoskrnl!MmUnlockPages` at `0x14004bc15`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004b94b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ba77`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004bae5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004b94b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ba77`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004bae5`
- `ntoskrnl!IoFreeMdl` at `0x14004b9bb`
- `ntoskrnl!IoFreeMdl` at `0x14004bb7f`
- `ntoskrnl!IoFreeMdl` at `0x14004bba5`
- `ntoskrnl!IoFreeMdl` at `0x14004bbda`
- `ntoskrnl!IoFreeMdl` at `0x14004bbfd`
- `ntoskrnl!IoFreeMdl` at `0x14004bc24`
- `ntoskrnl!IoFreeMdl` at `0x14004b9bb`
- `ntoskrnl!IoFreeMdl` at `0x14004bb7f`
- `ntoskrnl!IoFreeMdl` at `0x14004bba5`
- `ntoskrnl!IoFreeMdl` at `0x14004bbda`
- `ntoskrnl!IoFreeMdl` at `0x14004bbfd`
- `ntoskrnl!IoFreeMdl` at `0x14004bc24`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004b8f4`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004ba1b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004bb39`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004b8f4`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004ba1b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004bb39`
- `rdbss!RxAllocateMdl2` at `0x14004b8cc`
- `rdbss!RxAllocateMdl2` at `0x14004b9f1`
- `rdbss!RxAllocateMdl2` at `0x14004bb0b`
- `rdbss!RxAllocateMdl2` at `0x14004b8cc`
- `rdbss!RxAllocateMdl2` at `0x14004b9f1`
- `rdbss!RxAllocateMdl2` at `0x14004bb0b`

## pseudocode

```c
__int64 __fastcall SmbCeInitializeTransactionParameters(
        struct _MDL *a1,
        unsigned __int16 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  unsigned int v10; // edi
  struct _MDL *v11; // r12
  struct _MDL *v12; // r13
  struct _MDL *v13; // rax
  struct _MDL *v14; // rsi
  unsigned int v15; // r14d
  struct _MDL *v16; // rax
  struct _MDL *v18; // rax
  PVOID MappedSystemVa; // rax
  struct _MDL *Mdl2; // rax

  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( (*(_BYTE *)a7 & 2) != 0 )
  {
    if ( a1 && a2 )
    {
      Mdl2 = (struct _MDL *)RxAllocateMdl2(a1, a2, 0, 0, 0);
      v11 = Mdl2;
      if ( !Mdl2 )
      {
        v10 = -1073741670;
        goto LABEL_16;
      }
      MmProbeAndLockPages(Mdl2, 0, IoModifyAccess);
      if ( (v11->MdlFlags & 5) != 0 )
        MappedSystemVa = v11->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000000u);
      if ( !MappedSystemVa )
      {
        v10 = -1073741670;
LABEL_16:
        a1 = v11;
        v13 = v12;
        goto LABEL_3;
      }
    }
    if ( a3 && a4 )
    {
      v18 = (struct _MDL *)RxAllocateMdl2(a3, a4, 0, 0, 0);
      v12 = v18;
      if ( v18 )
      {
        v10 = 0;
        MmProbeAndLockPages(v18, 0, IoModifyAccess);
        if ( (v12->MdlFlags & 5) != 0 )
        {
          if ( !v12->MappedSystemVa )
            v10 = -1073741670;
        }
        else if ( !MmMapLockedPagesSpecifyCache(v12, 0, MmCached, 0, 0, 0x40000000u) )
        {
          v10 = -1073741670;
        }
      }
      else
      {
        v10 = -1073741670;
      }
    }
    goto LABEL_16;
  }
  *(_QWORD *)(a7 + 24) = a3;
  v13 = 0;
LABEL_3:
  v14 = 0;
  *(_DWORD *)(a7 + 16) = a4;
  *(_QWORD *)(a7 + 32) = v13;
  *(_WORD *)(a7 + 2) = a2;
  *(_QWORD *)(a7 + 8) = a1;
  if ( v10 || !a5 )
  {
    v15 = a6;
  }
  else
  {
    v15 = a6;
    if ( a6 )
    {
      v16 = (struct _MDL *)RxAllocateMdl2(a5, a6, 0, 0, 0);
      v14 = v16;
      if ( v16 )
      {
        MmProbeAndLockPages(v16, 0, IoModifyAccess);
        if ( (v14->MdlFlags & 5) != 0 )
        {
          if ( !v14->MappedSystemVa )
            v10 = -1073741670;
        }
        else if ( !MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000000u) )
        {
          v10 = -1073741670;
        }
      }
      else
      {
        v10 = -1073741670;
      }
    }
  }
  *(_QWORD *)(a7 + 40) = v14;
  *(_DWORD *)(a7 + 48) = v15;
  if ( v10 )
  {
    if ( (*(_BYTE *)a7 & 2) != 0 )
    {
      if ( v11 )
      {
        MmUnlockPages(v11);
        IoFreeMdl(v11);
      }
      if ( v12 )
      {
        MmUnlockPages(v12);
        IoFreeMdl(v12);
      }
    }
    if ( v14 )
    {
      MmUnlockPages(v14);
      IoFreeMdl(v14);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14004b830  mov     [rsp+arg_18], r9d
0x14004b835  mov     [rsp+arg_10], r8
0x14004b83a  mov     [rsp+arg_8], dx
0x14004b83f  push    rbx
0x14004b840  push    rsi
0x14004b841  push    rdi
0x14004b842  push    r12
0x14004b844  push    r13
0x14004b846  push    r14
0x14004b848  push    r15
0x14004b84a  sub     rsp, 50h
0x14004b84e  mov     r14d, r9d
0x14004b851  mov     rsi, r8
0x14004b854  movzx   r15d, dx
0x14004b858  xor     edi, edi
0x14004b85a  xor     r12d, r12d
0x14004b85d  mov     [rsp+88h+var_58], r12
0x14004b862  xor     r13d, r13d
0x14004b865  mov     [rsp+88h+var_50], r13
0x14004b86a  mov     rbx, [rsp+88h+arg_30]
0x14004b872  test    byte ptr [rbx], 2
0x14004b875  jnz     loc_14004B98F
0x14004b87b  mov     [rbx+18h], r8
0x14004b87f  xor     eax, eax
0x14004b881  xor     esi, esi
0x14004b883  mov     [rbx+10h], r14d
0x14004b887  mov     [rbx+20h], rax
0x14004b88b  mov     [rbx+2], r15w
0x14004b890  mov     [rbx+8], rcx
0x14004b894  test    edi, edi
0x14004b896  jnz     loc_14004B964
0x14004b89c  mov     rcx, [rsp+88h+arg_20]
0x14004b8a4  test    rcx, rcx
0x14004b8a7  jz      loc_14004B964
0x14004b8ad  mov     r14d, [rsp+88h+arg_28]
0x14004b8b5  test    r14d, r14d
0x14004b8b8  jz      loc_14004B96C
0x14004b8be  mov     qword ptr [rsp+88h+BugCheckOnFailure], rsi
0x14004b8c3  xor     r9d, r9d
0x14004b8c6  xor     r8d, r8d
0x14004b8c9  mov     edx, r14d
0x14004b8cc  call    cs:__imp_RxAllocateMdl2
0x14004b8d3  nop     dword ptr [rax+rax+00h]
0x14004b8d8  mov     rsi, rax
0x14004b8db  mov     [rsp+88h+var_48], rax
0x14004b8e0  test    rax, rax
0x14004b8e3  jz      loc_14004B9CB
0x14004b8e9  xor     edx, edx; AccessMode
0x14004b8eb  mov     r8d, 2; Operation
0x14004b8f1  mov     rcx, rax; MemoryDescriptorList
0x14004b8f4  call    cs:__imp_MmProbeAndLockPages
0x14004b8fb  nop     dword ptr [rax+rax+00h]
0x14004b900  jmp     short loc_14004B923
0x14004b902  mov     edi, eax
0x14004b904  mov     rbx, [rsp+88h+arg_30]
0x14004b90c  mov     r14d, [rsp+88h+arg_28]
0x14004b914  mov     r12, [rsp+88h+var_58]
0x14004b919  mov     r13, [rsp+88h+var_50]
0x14004b91e  mov     rsi, [rsp+88h+var_48]
0x14004b923  test    edi, edi
0x14004b925  jnz     loc_14004B9B8
0x14004b92b  test    byte ptr [rsi+0Ah], 5
0x14004b92f  jnz     short loc_14004B9A7
0x14004b931  mov     [rsp+88h+Priority], 40000000h; Priority
0x14004b939  mov     [rsp+88h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14004b93d  xor     r9d, r9d; RequestedAddress
0x14004b940  xor     edx, edx; AccessMode
0x14004b942  mov     r8d, 1; CacheType
0x14004b948  mov     rcx, rsi; MemoryDescriptorList
0x14004b94b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004b952  nop     dword ptr [rax+rax+00h]
0x14004b957  test    rax, rax
0x14004b95a  mov     eax, 0C000009Ah
0x14004b95f  cmovz   edi, eax
0x14004b962  jmp     short loc_14004B96C
0x14004b964  mov     r14d, [rsp+88h+arg_28]
0x14004b96c  mov     [rbx+28h], rsi
0x14004b970  mov     [rbx+30h], r14d
0x14004b974  test    edi, edi
0x14004b976  jnz     loc_14004BBBE
0x14004b97c  mov     eax, edi
0x14004b97e  add     rsp, 50h
0x14004b982  pop     r15
0x14004b984  pop     r14
0x14004b986  pop     r13
0x14004b988  pop     r12
0x14004b98a  pop     rdi
0x14004b98b  pop     rsi
0x14004b98c  pop     rbx
0x14004b98d  retn
0x14004b98f  test    rcx, rcx
0x14004b992  jnz     loc_14004BAF3
0x14004b998  test    edi, edi
0x14004b99a  jz      short loc_14004B9D2
0x14004b99c  mov     rcx, r12
0x14004b99f  mov     rax, r13
0x14004b9a2  jmp     loc_14004B881
0x14004b9a7  mov     rax, [rsi+18h]
0x14004b9ab  test    rax, rax
0x14004b9ae  mov     eax, 0C000009Ah
0x14004b9b3  cmovz   edi, eax
0x14004b9b6  jmp     short loc_14004B96C
0x14004b9b8  mov     rcx, rsi; Mdl
0x14004b9bb  call    cs:__imp_IoFreeMdl
0x14004b9c2  nop     dword ptr [rax+rax+00h]
0x14004b9c7  xor     esi, esi
0x14004b9c9  jmp     short loc_14004B96C
0x14004b9cb  mov     edi, 0C000009Ah
0x14004b9d0  jmp     short loc_14004B96C
0x14004b9d2  test    rsi, rsi
0x14004b9d5  jz      short loc_14004B99C
0x14004b9d7  test    r14d, r14d
0x14004b9da  jz      short loc_14004B99C
0x14004b9dc  mov     qword ptr [rsp+88h+BugCheckOnFailure], 0
0x14004b9e5  xor     r9d, r9d
0x14004b9e8  xor     r8d, r8d
0x14004b9eb  mov     edx, r14d
0x14004b9ee  mov     rcx, rsi
0x14004b9f1  call    cs:__imp_RxAllocateMdl2
0x14004b9f8  nop     dword ptr [rax+rax+00h]
0x14004b9fd  mov     r13, rax
0x14004ba00  mov     [rsp+88h+var_50], rax
0x14004ba05  test    rax, rax
0x14004ba08  jz      loc_14004BB98
0x14004ba0e  xor     edi, edi
0x14004ba10  xor     edx, edx; AccessMode
0x14004ba12  mov     r8d, 2; Operation
0x14004ba18  mov     rcx, rax; MemoryDescriptorList
0x14004ba1b  call    cs:__imp_MmProbeAndLockPages
0x14004ba22  nop     dword ptr [rax+rax+00h]
0x14004ba27  jmp     short loc_14004BA4E
0x14004ba29  mov     edi, eax
0x14004ba2b  mov     rbx, [rsp+88h+arg_30]
0x14004ba33  mov     r14d, [rsp+88h+arg_18]
0x14004ba3b  movzx   r15d, [rsp+88h+arg_8]
0x14004ba44  mov     r12, [rsp+88h+var_58]
0x14004ba49  mov     r13, [rsp+88h+var_50]
0x14004ba4e  test    edi, edi
0x14004ba50  jnz     loc_14004BBA2
0x14004ba56  test    byte ptr [r13+0Ah], 5
0x14004ba5b  jnz     short loc_14004BA93
0x14004ba5d  mov     [rsp+88h+Priority], 40000000h; Priority
0x14004ba65  mov     [rsp+88h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14004ba69  xor     r9d, r9d; RequestedAddress
0x14004ba6c  xor     edx, edx; AccessMode
0x14004ba6e  mov     r8d, 1; CacheType
0x14004ba74  mov     rcx, r13; MemoryDescriptorList
0x14004ba77  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004ba7e  nop     dword ptr [rax+rax+00h]
0x14004ba83  mov     edx, 0C000009Ah
0x14004ba88  test    rax, rax
0x14004ba8b  cmovz   edi, edx
0x14004ba8e  jmp     loc_14004B99C
0x14004ba93  mov     rax, [r13+18h]
0x14004ba97  mov     edx, 0C000009Ah
0x14004ba9c  test    rax, rax
0x14004ba9f  cmovz   edi, edx
0x14004baa2  jmp     loc_14004B99C
0x14004baa7  test    byte ptr [r12+0Ah], 5
0x14004baad  jz      short loc_14004BAC7
0x14004baaf  mov     rax, [r12+18h]
0x14004bab4  test    rax, rax
0x14004bab7  jnz     loc_14004B998
0x14004babd  mov     edi, 0C000009Ah
0x14004bac2  jmp     loc_14004B99C
0x14004bac7  mov     [rsp+88h+Priority], 40000000h; Priority
0x14004bacf  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004bad7  xor     r9d, r9d; RequestedAddress
0x14004bada  xor     edx, edx; AccessMode
0x14004badc  mov     r8d, 1; CacheType
0x14004bae2  mov     rcx, r12; MemoryDescriptorList
0x14004bae5  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004baec  nop     dword ptr [rax+rax+00h]
0x14004baf1  jmp     short loc_14004BAB4
0x14004baf3  test    r15w, r15w
0x14004baf7  jz      loc_14004B998
0x14004bafd  mov     edx, r15d
0x14004bb00  mov     qword ptr [rsp+88h+BugCheckOnFailure], rdi
0x14004bb05  xor     r9d, r9d
0x14004bb08  xor     r8d, r8d
0x14004bb0b  call    cs:__imp_RxAllocateMdl2
0x14004bb12  nop     dword ptr [rax+rax+00h]
0x14004bb17  mov     r12, rax
0x14004bb1a  mov     [rsp+88h+var_58], rax
0x14004bb1f  test    rax, rax
0x14004bb22  jnz     short loc_14004BB2E
0x14004bb24  mov     edi, 0C000009Ah
0x14004bb29  jmp     loc_14004B99C
0x14004bb2e  xor     edx, edx; AccessMode
0x14004bb30  mov     r8d, 2; Operation
0x14004bb36  mov     rcx, rax; MemoryDescriptorList
0x14004bb39  call    cs:__imp_MmProbeAndLockPages
0x14004bb40  nop     dword ptr [rax+rax+00h]
0x14004bb45  jmp     short loc_14004BB74
0x14004bb47  mov     edi, eax
0x14004bb49  mov     rbx, [rsp+88h+arg_30]
0x14004bb51  mov     r14d, [rsp+88h+arg_18]
0x14004bb59  mov     rsi, [rsp+88h+arg_10]
0x14004bb61  movzx   r15d, [rsp+88h+arg_8]
0x14004bb6a  mov     r12, [rsp+88h+var_58]
0x14004bb6f  mov     r13, [rsp+88h+var_50]
0x14004bb74  test    edi, edi
0x14004bb76  jz      loc_14004BAA7
0x14004bb7c  mov     rcx, r12; Mdl
0x14004bb7f  call    cs:__imp_IoFreeMdl
0x14004bb86  nop     dword ptr [rax+rax+00h]
0x14004bb8b  xor     r12d, r12d
0x14004bb8e  mov     [rsp+88h+var_58], r12
0x14004bb93  jmp     loc_14004B998
0x14004bb98  mov     edi, 0C000009Ah
0x14004bb9d  jmp     loc_14004B99C
0x14004bba2  mov     rcx, r13; Mdl
0x14004bba5  call    cs:__imp_IoFreeMdl
0x14004bbac  nop     dword ptr [rax+rax+00h]
0x14004bbb1  xor     r13d, r13d
0x14004bbb4  mov     [rsp+88h+var_50], r13
0x14004bbb9  jmp     loc_14004B99C
0x14004bbbe  test    byte ptr [rbx], 2
0x14004bbc1  jz      short loc_14004BC09
0x14004bbc3  test    r12, r12
0x14004bbc6  jz      short loc_14004BBE6
0x14004bbc8  mov     rcx, r12; MemoryDescriptorList
0x14004bbcb  call    cs:__imp_MmUnlockPages
0x14004bbd2  nop     dword ptr [rax+rax+00h]
0x14004bbd7  mov     rcx, r12; Mdl
0x14004bbda  call    cs:__imp_IoFreeMdl
0x14004bbe1  nop     dword ptr [rax+rax+00h]
0x14004bbe6  test    r13, r13
0x14004bbe9  jz      short loc_14004BC09
0x14004bbeb  mov     rcx, r13; MemoryDescriptorList
0x14004bbee  call    cs:__imp_MmUnlockPages
0x14004bbf5  nop     dword ptr [rax+rax+00h]
0x14004bbfa  mov     rcx, r13; Mdl
0x14004bbfd  call    cs:__imp_IoFreeMdl
0x14004bc04  nop     dword ptr [rax+rax+00h]
0x14004bc09  test    rsi, rsi
0x14004bc0c  jz      loc_14004B97C
0x14004bc12  mov     rcx, rsi; MemoryDescriptorList
0x14004bc15  call    cs:__imp_MmUnlockPages
0x14004bc1c  nop     dword ptr [rax+rax+00h]
0x14004bc21  mov     rcx, rsi; Mdl
0x14004bc24  call    cs:__imp_IoFreeMdl
0x14004bc2b  nop     dword ptr [rax+rax+00h]
0x14004bc30  jmp     loc_14004B97C
```
