# NTSetSharedAccess

- ea: `0x14004ffb0`
- end: `0x140050063`
- name: `NTSetSharedAccess`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400031bc`

## callees

- `0x14004ffb0`

## import_xrefs

- `ntoskrnl!IoSetShareAccess` at `0x14004ffe8`
- `ntoskrnl!IoSetShareAccess` at `0x14004ffe8`
- `ntoskrnl!SeAssignSecurity` at `0x140050029`
- `ntoskrnl!SeAssignSecurity` at `0x140050029`
- `ntoskrnl!IoRemoveShareAccess` at `0x140050055`
- `ntoskrnl!IoRemoveShareAccess` at `0x140050055`

## pseudocode

```c
__int64 __fastcall NTSetSharedAccess(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  struct _SHARE_ACCESS *v4; // rsi
  NTSTATUS v6; // ebx

  v3 = *(_QWORD *)(a2 + 184);
  v4 = (struct _SHARE_ACCESS *)(a3 + 136);
  IoSetShareAccess(1u, (*(_BYTE *)(v3 + 26) & 3) != 0, *(PFILE_OBJECT *)(v3 + 48), (PSHARE_ACCESS)(a3 + 136));
  v6 = SeAssignSecurity(
         0,
         *(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8LL) + 64LL),
         (PSECURITY_DESCRIPTOR *)(a3 + 168),
         0,
         (PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8LL) + 32LL),
         &GenericMapping,
         (POOL_TYPE)512);
  if ( v6 < 0 )
    IoRemoveShareAccess(*(PFILE_OBJECT *)(v3 + 48), v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14004ffb0  mov     [rsp+arg_0], rbx
0x14004ffb5  mov     [rsp+arg_8], rsi
0x14004ffba  push    rdi
0x14004ffbb  sub     rsp, 40h
0x14004ffbf  mov     rdi, [rdx+0B8h]
0x14004ffc6  lea     rsi, [r8+88h]
0x14004ffcd  mov     edx, 0
0x14004ffd2  mov     rbx, r8
0x14004ffd5  mov     r9, rsi; ShareAccess
0x14004ffd8  mov     ecx, 1; DesiredAccess
0x14004ffdd  test    byte ptr [rdi+1Ah], 3
0x14004ffe1  mov     r8, [rdi+30h]; FileObject
0x14004ffe5  setnz   dl; DesiredShareAccess
0x14004ffe8  call    cs:__imp_IoSetShareAccess
0x14004ffef  nop     dword ptr [rax+rax+00h]
0x14004fff4  mov     rax, [rdi+8]
0x14004fff8  lea     rcx, GenericMapping
0x14004ffff  mov     [rsp+48h+PoolType], 200h; PoolType
0x140050007  lea     r8, [rbx+0A8h]; NewDescriptor
0x14005000e  mov     [rsp+48h+GenericMapping], rcx; GenericMapping
0x140050013  xor     r9d, r9d; IsDirectoryObject
0x140050016  xor     ecx, ecx; ParentDescriptor
0x140050018  mov     rdx, [rax+8]
0x14005001c  lea     rax, [rdx+20h]
0x140050020  mov     rdx, [rdx+40h]; ExplicitDescriptor
0x140050024  mov     [rsp+48h+SubjectContext], rax; SubjectContext
0x140050029  call    cs:__imp_SeAssignSecurity
0x140050030  nop     dword ptr [rax+rax+00h]
0x140050035  mov     ebx, eax
0x140050037  test    eax, eax
0x140050039  js      short loc_14005004E
0x14005003b  mov     rsi, [rsp+48h+arg_8]
0x140050040  mov     eax, ebx
0x140050042  mov     rbx, [rsp+48h+arg_0]
0x140050047  add     rsp, 40h
0x14005004b  pop     rdi
0x14005004c  retn
0x14005004e  mov     rcx, [rdi+30h]; FileObject
0x140050052  mov     rdx, rsi; ShareAccess
0x140050055  call    cs:__imp_IoRemoveShareAccess
0x14005005c  nop     dword ptr [rax+rax+00h]
0x140050061  jmp     short loc_14005003B
```
