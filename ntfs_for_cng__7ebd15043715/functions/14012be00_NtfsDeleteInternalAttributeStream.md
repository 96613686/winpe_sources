# NtfsDeleteInternalAttributeStream

- ea: `0x14012be00`
- end: `0x14012c089`
- name: `NtfsDeleteInternalAttributeStream`
- size: `649`
- prototype: `char __fastcall(__int64, __int64, char, char)`
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a600`
- `0x14001ca10`
- `0x140029d80`
- `0x1400ba87c`
- `0x1400cb1a4`
- `0x1400cc78c`
- `0x140100a0c`
- `0x14010a8e8`
- `0x140138c20`
- `0x140139e3c`
- `0x140145d8c`
- `0x1401919d0`
- `0x140192f44`
- `0x140194c68`
- `0x14019dc78`
- `0x1401a2cb0`
- `0x1401e7e28`
- `0x1401ea058`
- `0x1401f3390`
- `0x1401f5088`
- `0x1401f63f8`
- `0x14021d6f8`
- `0x140235e08`
- `0x14023fc38`
- `0x14024113c`
- `0x140248584`
- `0x14024f868`
- `0x140263ac0`
- `0x140265544`
- `0x1402682f8`

## callees

- `0x14012be00`
- `0x14012c090`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012bfff`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012bfff`
- `ntoskrnl!ObfDereferenceObject` at `0x14012bf5b`
- `ntoskrnl!ObfDereferenceObject` at `0x14012bf5b`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012bf20`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012bf20`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14012c078`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14012c078`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012be8e`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012be8e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012befa`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012befa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012bfc0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012bfc0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012bf43`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012c067`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012bf43`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012c067`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012be69`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012c046`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012be69`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012c046`

## pseudocode

```c
char __fastcall NtfsDeleteInternalAttributeStream(__int64 a1, __int64 a2, char a3, char a4)
{
  __int64 v6; // rbx
  unsigned __int8 v8; // r15
  __int64 v9; // rdi
  __int64 v10; // rax
  union _LARGE_INTEGER *v11; // rdx
  BOOLEAN v13; // r15
  __int64 v14; // r14
  PERESOURCE *v15; // r12

  v6 = a2;
  if ( !*(_QWORD *)(a2 + 280) || (*(_DWORD *)(a2 + 200) & 0x400) != 0 )
    return 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    v13 = 0;
    if ( *(_WORD *)a2 == 1794 )
      v14 = a2;
    else
      v14 = *(_QWORD *)(a2 + 184);
    v15 = (PERESOURCE *)(v14 + 112);
    while ( 1 )
    {
      if ( (*(_DWORD *)(v14 + 16) & 0x200) != 0 )
      {
        if ( !a1
          || (*(_DWORD *)(a1 + 16) & 0x40000000) == 0
          && (v15 = (PERESOURCE *)(v14 + 112), (*(_DWORD *)(*(_QWORD *)(a1 + 144) + 16LL) & 0x40000000) == 0) )
        {
          if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v14 + 96) + 2160LL)) )
            break;
        }
      }
      if ( v13 )
        goto LABEL_4;
      v15 = (PERESOURCE *)(v14 + 112);
      v13 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v14 + 112), 0);
      if ( !v13 )
        return 0;
    }
    if ( v13 )
      ExReleaseResourceLite(*v15);
    return 0;
  }
  else
  {
LABEL_4:
    if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v6 + 184) + 104LL) + 64LL))
      || (v8 = 0, !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v6 + 192) + 2160LL)))
      && (*(_DWORD *)(a1 + 16) & 0x40000000) == 0 )
    {
      ExAcquirePushLockExclusiveEx(*(_QWORD *)(v6 + 184) + 200LL, 0);
      v8 = 1;
    }
    NtfsUnlockSystemFilePages(a1, v6, v8, 1);
    v9 = *(_QWORD *)(v6 + 280);
    *(_QWORD *)(v6 + 280) = 0;
    v10 = *(_QWORD *)(v9 + 24);
    if ( v10 && (*(_DWORD *)(v10 + 200) & 0x4000) == 0 )
    {
      *(_DWORD *)(v9 + 88) = 0;
      *(_QWORD *)(v9 + 96) = 0;
    }
    if ( v8 )
      ExReleasePushLockEx(*(_QWORD *)(v6 + 184) + 200LL, 0);
    if ( *(_QWORD *)(v9 + 48) )
    {
      v11 = &NtfsLarge0;
      if ( !a3 )
        v11 = 0;
      CcUninitializeCacheMap((PFILE_OBJECT)v9, v11, 0);
    }
    if ( *(_QWORD *)(v6 + 16) )
    {
      if ( *(_WORD *)v6 != 1794 )
        v6 = *(_QWORD *)(v6 + 184);
      ExReleaseResourceLite(*(PERESOURCE *)(v6 + 112));
    }
    if ( a4 )
      ObDereferenceObjectDeferDelete((PVOID)v9);
    else
      ObfDereferenceObject((PVOID)v9);
    return 1;
  }
}

```

## disassembly

```asm
0x14012be00  push    rbx
0x14012be02  push    rbp
0x14012be03  push    rsi
0x14012be04  push    rdi
0x14012be05  sub     rsp, 28h
0x14012be09  cmp     qword ptr [rdx+118h], 0
0x14012be11  movzx   esi, r9b
0x14012be15  movzx   ebp, r8b
0x14012be19  mov     rbx, rdx
0x14012be1c  mov     rdi, rcx
0x14012be1f  jz      loc_14012BF87
0x14012be25  test    dword ptr [rdx+0C8h], 400h
0x14012be2f  jnz     loc_14012BF87
0x14012be35  cmp     qword ptr [rdx+10h], 0
0x14012be3a  mov     [rsp+48h+arg_8], r13
0x14012be3f  mov     r13d, 702h
0x14012be45  mov     [rsp+48h+arg_0], r12
0x14012be4a  mov     [rsp+48h+arg_10], r14
0x14012be4f  mov     [rsp+48h+var_28], r15
0x14012be54  jnz     loc_14012BF93
0x14012be5a  mov     rax, [rbx+0B8h]
0x14012be61  mov     rcx, [rax+68h]
0x14012be65  add     rcx, 40h ; '@'; Resource
0x14012be69  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14012be70  nop     dword ptr [rax+rax+00h]
0x14012be75  test    al, al
0x14012be77  jz      loc_14012BFEF
0x14012be7d  mov     rcx, [rbx+0C0h]
0x14012be84  xor     r15b, r15b
0x14012be87  add     rcx, 870h; Resource
0x14012be8e  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14012be95  nop     dword ptr [rax+rax+00h]
0x14012be9a  test    eax, eax
0x14012be9c  jz      loc_14012BFE1
0x14012bea2  mov     r9d, 1
0x14012bea8  movzx   r8d, r15b
0x14012beac  mov     rdx, rbx
0x14012beaf  mov     rcx, rdi
0x14012beb2  call    NtfsUnlockSystemFilePages
0x14012beb7  mov     rdi, [rbx+118h]
0x14012bebe  xor     r12d, r12d
0x14012bec1  mov     [rbx+118h], r12
0x14012bec8  mov     rax, [rdi+18h]
0x14012becc  test    rax, rax
0x14012becf  jz      short loc_14012BEE5
0x14012bed1  test    dword ptr [rax+0C8h], 4000h
0x14012bedb  jnz     short loc_14012BEE5
0x14012bedd  mov     [rdi+58h], r12d
0x14012bee1  mov     [rdi+60h], r12
0x14012bee5  test    r15b, r15b
0x14012bee8  jz      short loc_14012BF06
0x14012beea  mov     rcx, [rbx+0B8h]
0x14012bef1  xor     edx, edx
0x14012bef3  add     rcx, 0C8h
0x14012befa  call    cs:__imp_ExReleasePushLockEx
0x14012bf01  nop     dword ptr [rax+rax+00h]
0x14012bf06  cmp     [rdi+30h], r12
0x14012bf0a  jz      short loc_14012BF2C
0x14012bf0c  test    bpl, bpl
0x14012bf0f  lea     rdx, NtfsLarge0
0x14012bf16  mov     rcx, rdi; FileObject
0x14012bf19  cmovz   rdx, r12; TruncateSize
0x14012bf1d  xor     r8d, r8d; UninitializeEvent
0x14012bf20  call    cs:__imp_CcUninitializeCacheMap
0x14012bf27  nop     dword ptr [rax+rax+00h]
0x14012bf2c  cmp     [rbx+10h], r12
0x14012bf30  jz      short loc_14012BF4F
0x14012bf32  cmp     r13w, [rbx]
0x14012bf36  jz      short loc_14012BF3F
0x14012bf38  mov     rbx, [rbx+0B8h]
0x14012bf3f  mov     rcx, [rbx+70h]; Resource
0x14012bf43  call    cs:__imp_ExReleaseResourceLite
0x14012bf4a  nop     dword ptr [rax+rax+00h]
0x14012bf4f  mov     rcx, rdi; Object
0x14012bf52  test    sil, sil
0x14012bf55  jnz     loc_14012C078
0x14012bf5b  call    cs:__imp_ObfDereferenceObject
0x14012bf62  nop     dword ptr [rax+rax+00h]
0x14012bf67  mov     al, 1
0x14012bf69  mov     r14, [rsp+48h+arg_10]
0x14012bf6e  mov     r12, [rsp+48h+arg_0]
0x14012bf73  mov     r15, [rsp+48h+var_28]
0x14012bf78  mov     r13, [rsp+48h+arg_8]
0x14012bf7d  add     rsp, 28h
0x14012bf81  pop     rdi
0x14012bf82  pop     rsi
0x14012bf83  pop     rbp
0x14012bf84  pop     rbx
0x14012bf85  retn
0x14012bf87  xor     al, al
0x14012bf89  add     rsp, 28h
0x14012bf8d  pop     rdi
0x14012bf8e  pop     rsi
0x14012bf8f  pop     rbp
0x14012bf90  pop     rbx
0x14012bf91  retn
0x14012bf93  xor     r15b, r15b
0x14012bf96  cmp     r13w, [rdx]
0x14012bf9a  jnz     short loc_14012BFD8
0x14012bf9c  mov     r14, rbx
0x14012bf9f  lea     r12, [r14+70h]
0x14012bfa3  test    dword ptr [r14+10h], 200h
0x14012bfab  jnz     short loc_14012C013
0x14012bfad  test    r15b, r15b
0x14012bfb0  jnz     loc_14012BE5A
0x14012bfb6  mov     rcx, [r14+70h]; Resource
0x14012bfba  lea     r12, [r14+70h]
0x14012bfbe  xor     edx, edx; Wait
0x14012bfc0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14012bfc7  nop     dword ptr [rax+rax+00h]
0x14012bfcc  movzx   r15d, al
0x14012bfd0  test    al, al
0x14012bfd2  jnz     short loc_14012BFA3
0x14012bfd4  xor     al, al
0x14012bfd6  jmp     short loc_14012BF69
0x14012bfd8  mov     r14, [rdx+0B8h]
0x14012bfdf  jmp     short loc_14012BF9F
0x14012bfe1  mov     eax, [rdi+10h]
0x14012bfe4  bt      rax, 1Eh
0x14012bfe9  jb      loc_14012BEA2
0x14012bfef  mov     rcx, [rbx+0B8h]
0x14012bff6  xor     edx, edx
0x14012bff8  add     rcx, 0C8h
0x14012bfff  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012c006  nop     dword ptr [rax+rax+00h]
0x14012c00b  mov     r15b, 1
0x14012c00e  jmp     loc_14012BEA2
0x14012c013  test    rdi, rdi
0x14012c016  jz      short loc_14012C03B
0x14012c018  mov     eax, [rdi+10h]
0x14012c01b  bt      rax, 1Eh
0x14012c020  jb      short loc_14012BFAD
0x14012c022  mov     rax, [rdi+90h]
0x14012c029  lea     r12, [r14+70h]
0x14012c02d  mov     ecx, [rax+10h]
0x14012c030  bt      rcx, 1Eh
0x14012c035  jb      loc_14012BFAD
0x14012c03b  mov     rcx, [r14+60h]
0x14012c03f  add     rcx, 870h; Resource
0x14012c046  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14012c04d  nop     dword ptr [rax+rax+00h]
0x14012c052  test    al, al
0x14012c054  jnz     loc_14012BFAD
0x14012c05a  test    r15b, r15b
0x14012c05d  jz      loc_14012BFD4
0x14012c063  mov     rcx, [r12]; Resource
0x14012c067  call    cs:__imp_ExReleaseResourceLite
0x14012c06e  nop     dword ptr [rax+rax+00h]
0x14012c073  jmp     loc_14012BFD4
0x14012c078  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14012c07f  nop     dword ptr [rax+rax+00h]
0x14012c084  jmp     loc_14012BF67
```
