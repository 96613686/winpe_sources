# NtfsDeleteInternalAttributeStream

- ea: `0x14012be50`
- end: `0x14012c0d9`
- name: `NtfsDeleteInternalAttributeStream`
- size: `649`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
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
- `0x140100a5c`
- `0x14010a938`
- `0x140138c70`
- `0x140139e8c`
- `0x140145ddc`
- `0x140191a20`
- `0x140192f94`
- `0x140194cb8`
- `0x14019dcc8`
- `0x1401a2d00`
- `0x1401e7e78`
- `0x1401ea0a8`
- `0x1401f33e0`
- `0x1401f50d8`
- `0x1401f6448`
- `0x14021d748`
- `0x140235e58`
- `0x14023fc88`
- `0x14024118c`
- `0x1402485d4`
- `0x14024f8b8`
- `0x140263b10`
- `0x140265594`
- `0x140268348`

## callees

- `0x14012be50`
- `0x14012c0e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012c04f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012c04f`
- `ntoskrnl!ObfDereferenceObject` at `0x14012bfab`
- `ntoskrnl!ObfDereferenceObject` at `0x14012bfab`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012bf70`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012bf70`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14012c0c8`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14012c0c8`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012bede`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012bede`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012bf4a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012bf4a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012c010`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012c010`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012bf93`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012c0b7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012bf93`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012c0b7`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012beb9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012c096`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012beb9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012c096`

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
0x14012be50  push    rbx
0x14012be52  push    rbp
0x14012be53  push    rsi
0x14012be54  push    rdi
0x14012be55  sub     rsp, 28h
0x14012be59  cmp     qword ptr [rdx+118h], 0
0x14012be61  movzx   esi, r9b
0x14012be65  movzx   ebp, r8b
0x14012be69  mov     rbx, rdx
0x14012be6c  mov     rdi, rcx
0x14012be6f  jz      loc_14012BFD7
0x14012be75  test    dword ptr [rdx+0C8h], 400h
0x14012be7f  jnz     loc_14012BFD7
0x14012be85  cmp     qword ptr [rdx+10h], 0
0x14012be8a  mov     [rsp+48h+arg_8], r13
0x14012be8f  mov     r13d, 702h
0x14012be95  mov     [rsp+48h+arg_0], r12
0x14012be9a  mov     [rsp+48h+arg_10], r14
0x14012be9f  mov     [rsp+48h+var_28], r15
0x14012bea4  jnz     loc_14012BFE3
0x14012beaa  mov     rax, [rbx+0B8h]
0x14012beb1  mov     rcx, [rax+68h]
0x14012beb5  add     rcx, 40h ; '@'; Resource
0x14012beb9  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14012bec0  nop     dword ptr [rax+rax+00h]
0x14012bec5  test    al, al
0x14012bec7  jz      loc_14012C03F
0x14012becd  mov     rcx, [rbx+0C0h]
0x14012bed4  xor     r15b, r15b
0x14012bed7  add     rcx, 870h; Resource
0x14012bede  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14012bee5  nop     dword ptr [rax+rax+00h]
0x14012beea  test    eax, eax
0x14012beec  jz      loc_14012C031
0x14012bef2  mov     r9d, 1
0x14012bef8  movzx   r8d, r15b
0x14012befc  mov     rdx, rbx
0x14012beff  mov     rcx, rdi
0x14012bf02  call    NtfsUnlockSystemFilePages
0x14012bf07  mov     rdi, [rbx+118h]
0x14012bf0e  xor     r12d, r12d
0x14012bf11  mov     [rbx+118h], r12
0x14012bf18  mov     rax, [rdi+18h]
0x14012bf1c  test    rax, rax
0x14012bf1f  jz      short loc_14012BF35
0x14012bf21  test    dword ptr [rax+0C8h], 4000h
0x14012bf2b  jnz     short loc_14012BF35
0x14012bf2d  mov     [rdi+58h], r12d
0x14012bf31  mov     [rdi+60h], r12
0x14012bf35  test    r15b, r15b
0x14012bf38  jz      short loc_14012BF56
0x14012bf3a  mov     rcx, [rbx+0B8h]
0x14012bf41  xor     edx, edx
0x14012bf43  add     rcx, 0C8h
0x14012bf4a  call    cs:__imp_ExReleasePushLockEx
0x14012bf51  nop     dword ptr [rax+rax+00h]
0x14012bf56  cmp     [rdi+30h], r12
0x14012bf5a  jz      short loc_14012BF7C
0x14012bf5c  test    bpl, bpl
0x14012bf5f  lea     rdx, NtfsLarge0
0x14012bf66  mov     rcx, rdi; FileObject
0x14012bf69  cmovz   rdx, r12; TruncateSize
0x14012bf6d  xor     r8d, r8d; UninitializeEvent
0x14012bf70  call    cs:__imp_CcUninitializeCacheMap
0x14012bf77  nop     dword ptr [rax+rax+00h]
0x14012bf7c  cmp     [rbx+10h], r12
0x14012bf80  jz      short loc_14012BF9F
0x14012bf82  cmp     r13w, [rbx]
0x14012bf86  jz      short loc_14012BF8F
0x14012bf88  mov     rbx, [rbx+0B8h]
0x14012bf8f  mov     rcx, [rbx+70h]; Resource
0x14012bf93  call    cs:__imp_ExReleaseResourceLite
0x14012bf9a  nop     dword ptr [rax+rax+00h]
0x14012bf9f  mov     rcx, rdi; Object
0x14012bfa2  test    sil, sil
0x14012bfa5  jnz     loc_14012C0C8
0x14012bfab  call    cs:__imp_ObfDereferenceObject
0x14012bfb2  nop     dword ptr [rax+rax+00h]
0x14012bfb7  mov     al, 1
0x14012bfb9  mov     r14, [rsp+48h+arg_10]
0x14012bfbe  mov     r12, [rsp+48h+arg_0]
0x14012bfc3  mov     r15, [rsp+48h+var_28]
0x14012bfc8  mov     r13, [rsp+48h+arg_8]
0x14012bfcd  add     rsp, 28h
0x14012bfd1  pop     rdi
0x14012bfd2  pop     rsi
0x14012bfd3  pop     rbp
0x14012bfd4  pop     rbx
0x14012bfd5  retn
0x14012bfd7  xor     al, al
0x14012bfd9  add     rsp, 28h
0x14012bfdd  pop     rdi
0x14012bfde  pop     rsi
0x14012bfdf  pop     rbp
0x14012bfe0  pop     rbx
0x14012bfe1  retn
0x14012bfe3  xor     r15b, r15b
0x14012bfe6  cmp     r13w, [rdx]
0x14012bfea  jnz     short loc_14012C028
0x14012bfec  mov     r14, rbx
0x14012bfef  lea     r12, [r14+70h]
0x14012bff3  test    dword ptr [r14+10h], 200h
0x14012bffb  jnz     short loc_14012C063
0x14012bffd  test    r15b, r15b
0x14012c000  jnz     loc_14012BEAA
0x14012c006  mov     rcx, [r14+70h]; Resource
0x14012c00a  lea     r12, [r14+70h]
0x14012c00e  xor     edx, edx; Wait
0x14012c010  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14012c017  nop     dword ptr [rax+rax+00h]
0x14012c01c  movzx   r15d, al
0x14012c020  test    al, al
0x14012c022  jnz     short loc_14012BFF3
0x14012c024  xor     al, al
0x14012c026  jmp     short loc_14012BFB9
0x14012c028  mov     r14, [rdx+0B8h]
0x14012c02f  jmp     short loc_14012BFEF
0x14012c031  mov     eax, [rdi+10h]
0x14012c034  bt      rax, 1Eh
0x14012c039  jb      loc_14012BEF2
0x14012c03f  mov     rcx, [rbx+0B8h]
0x14012c046  xor     edx, edx
0x14012c048  add     rcx, 0C8h
0x14012c04f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012c056  nop     dword ptr [rax+rax+00h]
0x14012c05b  mov     r15b, 1
0x14012c05e  jmp     loc_14012BEF2
0x14012c063  test    rdi, rdi
0x14012c066  jz      short loc_14012C08B
0x14012c068  mov     eax, [rdi+10h]
0x14012c06b  bt      rax, 1Eh
0x14012c070  jb      short loc_14012BFFD
0x14012c072  mov     rax, [rdi+90h]
0x14012c079  lea     r12, [r14+70h]
0x14012c07d  mov     ecx, [rax+10h]
0x14012c080  bt      rcx, 1Eh
0x14012c085  jb      loc_14012BFFD
0x14012c08b  mov     rcx, [r14+60h]
0x14012c08f  add     rcx, 870h; Resource
0x14012c096  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14012c09d  nop     dword ptr [rax+rax+00h]
0x14012c0a2  test    al, al
0x14012c0a4  jnz     loc_14012BFFD
0x14012c0aa  test    r15b, r15b
0x14012c0ad  jz      loc_14012C024
0x14012c0b3  mov     rcx, [r12]; Resource
0x14012c0b7  call    cs:__imp_ExReleaseResourceLite
0x14012c0be  nop     dword ptr [rax+rax+00h]
0x14012c0c3  jmp     loc_14012C024
0x14012c0c8  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14012c0cf  nop     dword ptr [rax+rax+00h]
0x14012c0d4  jmp     loc_14012BFB7
```
