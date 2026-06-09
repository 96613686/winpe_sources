# CdCommonClose

- ea: `0x14000c0c8`
- end: `0x14000c241`
- name: `CdCommonClose`
- size: `377`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001240`

## callees

- `0x140001160`
- `0x1400024e0`
- `0x14000c0c8`
- `0x14000c248`
- `0x14000c6d8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000c1b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c217`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c1b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c217`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c12d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c146`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c12d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c146`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000c188`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000c188`

## pseudocode

```c
__int64 __fastcall CdCommonClose(_DWORD *P, IRP *a2)
{
  _DWORD *v3; // rbx
  PFILE_OBJECT FileObject; // rdi
  int v5; // ebp
  _QWORD *FsContext; // r15
  int v7; // r13d
  char v8; // r12
  __int64 v9; // rsi
  _QWORD *v10; // rdi
  void *v11; // rcx
  int v12; // ecx

  v3 = P;
  if ( *((_QWORD *)P + 2)
    && (FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject, (v5 = (__int64)FileObject->FsContext2 & 7) != 0) )
  {
    FsContext = FileObject->FsContext;
    v7 = 0;
    v8 = 0;
    v9 = FsContext[15];
    v10 = (_QWORD *)((unsigned __int64)FileObject->FsContext2 & 0xFFFFFFFFFFFFFFF8uLL);
    if ( v10 )
    {
      v11 = (void *)v10[4];
      v7 = 1;
      if ( v11 )
      {
        ExFreePoolWithTag(v11, 0);
        v10[4] = 0;
      }
      ExFreePoolWithTag(v10, 0);
    }
    v12 = *(_DWORD *)(v9 + 52);
    if ( v12 == 2 && *((_DWORD *)FsContext + 41) == 1 && (unsigned int)(v5 - 3) <= 1 )
      goto LABEL_18;
    if ( !*(_DWORD *)(v9 + 56) && v12 != 2 )
    {
      ExAcquireResourceExclusiveLite(&Resource, 1u);
      if ( *(_DWORD *)(v9 + 56) || (unsigned int)(*(_DWORD *)(v9 + 52) - 1) <= 1 || (v3[8] & 0x20) == 0 )
        ExReleaseResourceLite(&Resource);
      else
        v8 = 1;
    }
    if ( !(unsigned __int8)CdCommonClosePrivate((_DWORD)v3, v9, (_DWORD)FsContext, v7, 1) )
    {
LABEL_18:
      CdQueueClose(v3);
      v3 = 0;
    }
    else if ( v8 )
    {
      CdCheckForDismount((__int64)v3, v9, 0);
    }
    CdCompleteRequest(v3, a2, 0);
    if ( v8 )
      ExReleaseResourceLite(&Resource);
  }
  else
  {
    CdCompleteRequest(P, a2, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c0c8  push    rbx
0x14000c0ca  push    rbp
0x14000c0cb  push    rsi
0x14000c0cc  push    rdi
0x14000c0cd  push    r12
0x14000c0cf  push    r13
0x14000c0d1  push    r14
0x14000c0d3  push    r15
0x14000c0d5  sub     rsp, 38h
0x14000c0d9  cmp     qword ptr [rcx+10h], 0
0x14000c0de  mov     r14, rdx
0x14000c0e1  mov     rbx, rcx
0x14000c0e4  jz      loc_14000C225
0x14000c0ea  mov     rax, [rdx+0B8h]
0x14000c0f1  mov     rdi, [rax+30h]
0x14000c0f5  mov     ebp, [rdi+20h]
0x14000c0f8  and     ebp, 7
0x14000c0fb  jz      loc_14000C225
0x14000c101  mov     r15, [rdi+18h]
0x14000c105  mov     r13d, 0
0x14000c10b  mov     rdi, [rdi+20h]
0x14000c10f  mov     r12b, r13b
0x14000c112  mov     rsi, [r15+78h]
0x14000c116  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14000c11a  jz      short loc_14000C152
0x14000c11c  mov     rcx, [rdi+20h]; P
0x14000c120  mov     r13d, 1
0x14000c126  test    rcx, rcx
0x14000c129  jz      short loc_14000C141
0x14000c12b  xor     edx, edx; Tag
0x14000c12d  call    cs:__imp_ExFreePoolWithTag
0x14000c134  nop     dword ptr [rax+rax+00h]
0x14000c139  mov     qword ptr [rdi+20h], 0
0x14000c141  xor     edx, edx; Tag
0x14000c143  mov     rcx, rdi; P
0x14000c146  call    cs:__imp_ExFreePoolWithTag
0x14000c14d  nop     dword ptr [rax+rax+00h]
0x14000c152  mov     ecx, [rsi+34h]
0x14000c155  lea     rdi, Resource
0x14000c15c  cmp     ecx, 2
0x14000c15f  jnz     short loc_14000C178
0x14000c161  cmp     dword ptr [r15+0A4h], 1
0x14000c169  jnz     short loc_14000C178
0x14000c16b  lea     eax, [rbp-3]
0x14000c16e  cmp     eax, 1
0x14000c171  ja      short loc_14000C178
0x14000c173  mov     r9b, 1
0x14000c176  jmp     short loc_14000C1DC
0x14000c178  cmp     dword ptr [rsi+38h], 0
0x14000c17c  jnz     short loc_14000C1BF
0x14000c17e  cmp     ecx, 2
0x14000c181  jz      short loc_14000C1BF
0x14000c183  mov     dl, 1; Wait
0x14000c185  mov     rcx, rdi; Resource
0x14000c188  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000c18f  nop     dword ptr [rax+rax+00h]
0x14000c194  cmp     dword ptr [rsi+38h], 0
0x14000c198  jnz     short loc_14000C1B0
0x14000c19a  mov     eax, [rsi+34h]
0x14000c19d  dec     eax
0x14000c19f  cmp     eax, 1
0x14000c1a2  jbe     short loc_14000C1B0
0x14000c1a4  mov     eax, [rbx+20h]
0x14000c1a7  test    al, 20h
0x14000c1a9  jz      short loc_14000C1B0
0x14000c1ab  mov     r12b, 1
0x14000c1ae  jmp     short loc_14000C1BF
0x14000c1b0  mov     rcx, rdi; Resource
0x14000c1b3  call    cs:__imp_ExReleaseResourceLite
0x14000c1ba  nop     dword ptr [rax+rax+00h]
0x14000c1bf  mov     r9d, r13d
0x14000c1c2  mov     [rsp+78h+var_58], 1
0x14000c1c7  mov     r8, r15
0x14000c1ca  mov     rdx, rsi
0x14000c1cd  mov     rcx, rbx
0x14000c1d0  call    CdCommonClosePrivate
0x14000c1d5  test    al, al
0x14000c1d7  jnz     short loc_14000C1EE
0x14000c1d9  xor     r9d, r9d
0x14000c1dc  mov     r8d, r13d
0x14000c1df  mov     rdx, r15
0x14000c1e2  mov     rcx, rbx; P
0x14000c1e5  call    CdQueueClose
0x14000c1ea  xor     ebx, ebx
0x14000c1ec  jmp     short loc_14000C201
0x14000c1ee  test    r12b, r12b
0x14000c1f1  jz      short loc_14000C201
0x14000c1f3  xor     r8d, r8d
0x14000c1f6  mov     rdx, rsi
0x14000c1f9  mov     rcx, rbx
0x14000c1fc  call    CdCheckForDismount
0x14000c201  xor     r8d, r8d
0x14000c204  mov     rdx, r14
0x14000c207  mov     rcx, rbx
0x14000c20a  call    CdCompleteRequest
0x14000c20f  test    r12b, r12b
0x14000c212  jz      short loc_14000C22D
0x14000c214  mov     rcx, rdi; Resource
0x14000c217  call    cs:__imp_ExReleaseResourceLite
0x14000c21e  nop     dword ptr [rax+rax+00h]
0x14000c223  jmp     short loc_14000C22D
0x14000c225  xor     r8d, r8d
0x14000c228  call    CdCompleteRequest
0x14000c22d  xor     eax, eax
0x14000c22f  add     rsp, 38h
0x14000c233  pop     r15
0x14000c235  pop     r14
0x14000c237  pop     r13
0x14000c239  pop     r12
0x14000c23b  pop     rdi
0x14000c23c  pop     rsi
0x14000c23d  pop     rbp
0x14000c23e  pop     rbx
0x14000c23f  retn
```
