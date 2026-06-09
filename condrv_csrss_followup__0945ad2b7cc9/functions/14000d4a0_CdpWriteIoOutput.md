# CdpWriteIoOutput

- ea: `0x14000d4a0`
- end: `0x14000d5b4`
- name: `CdpWriteIoOutput`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ca90`
- `0x14000cd40`

## callees

- `0x140001154`
- `0x140001500`
- `0x14000d4a0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000d53a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000d53a`

## pseudocode

```c
__int64 __fastcall CdpWriteIoOutput(__int64 a1, char a2, char **a3, _QWORD *a4)
{
  char *v5; // r12
  unsigned int v6; // edi
  unsigned int v7; // r14d
  struct _MDL *v8; // rbx
  unsigned int ByteCount; // eax
  unsigned int v10; // esi
  char *v11; // rax
  char *v12; // rcx

  v5 = *a3;
  v6 = *((_DWORD *)a3 + 2);
  v7 = *((_DWORD *)a3 + 3);
  v8 = *(struct _MDL **)(*(_QWORD *)(a1 + 184) + 32LL);
  if ( v8 )
  {
    do
    {
      if ( !v7 )
        break;
      ByteCount = v8->ByteCount;
      if ( v7 < ByteCount )
        break;
      v7 -= ByteCount;
      v8 = v8->Next;
    }
    while ( v8 );
    while ( v8 && v6 )
    {
      v10 = v6;
      if ( v6 >= v8->ByteCount - v7 )
        v10 = v8->ByteCount - v7;
      v11 = (char *)((v8->MdlFlags & 5) != 0
                   ? v8->MappedSystemVa
                   : MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000010u));
      if ( !v11 )
        break;
      v12 = &v11[v7];
      if ( a2 )
        RtlCopyFromUser(v12, v5, v10);
      else
        RtlCopyVolatileMemory(v12, v5, v10);
      v7 = 0;
      v5 += v10;
      v6 -= v10;
      v8 = v8->Next;
    }
  }
  if ( a4 )
    *a4 = v5 - *a3;
  return 0;
}

```

## disassembly

```asm
0x14000d4a0  mov     [rsp+arg_0], rbx
0x14000d4a5  mov     [rsp+arg_8], rsi
0x14000d4aa  mov     [rsp+arg_18], r9
0x14000d4af  mov     [rsp+arg_10], r8
0x14000d4b4  push    rdi
0x14000d4b5  push    r12
0x14000d4b7  push    r13
0x14000d4b9  push    r14
0x14000d4bb  push    r15
0x14000d4bd  sub     rsp, 30h
0x14000d4c1  movzx   r13d, dl
0x14000d4c5  mov     r12, [r8]
0x14000d4c8  mov     edi, [r8+8]
0x14000d4cc  mov     r14d, [r8+0Ch]
0x14000d4d0  mov     rbx, [rcx+0B8h]
0x14000d4d7  mov     rbx, [rbx+20h]
0x14000d4db  test    rbx, rbx
0x14000d4de  jz      loc_14000D582
0x14000d4e4  test    r14d, r14d
0x14000d4e7  jz      short loc_14000D500
0x14000d4e9  mov     eax, [rbx+28h]
0x14000d4ec  cmp     r14d, eax
0x14000d4ef  jb      short loc_14000D500
0x14000d4f1  sub     r14d, eax
0x14000d4f4  mov     rbx, [rbx]
0x14000d4f7  test    rbx, rbx
0x14000d4fa  jnz     short loc_14000D4E4
0x14000d4fc  nop     dword ptr [rax+00h]
0x14000d500  test    rbx, rbx
0x14000d503  jz      short loc_14000D582
0x14000d505  test    edi, edi
0x14000d507  jz      short loc_14000D582
0x14000d509  mov     eax, [rbx+28h]
0x14000d50c  sub     eax, r14d
0x14000d50f  mov     esi, edi
0x14000d511  cmp     edi, eax
0x14000d513  cmovnb  esi, eax
0x14000d516  test    byte ptr [rbx+0Ah], 5
0x14000d51a  jnz     short loc_14000D57C
0x14000d51c  mov     [rsp+58h+Priority], 40000010h; Priority
0x14000d524  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000d52c  xor     r9d, r9d; RequestedAddress
0x14000d52f  xor     edx, edx; AccessMode
0x14000d531  mov     r8d, 1; CacheType
0x14000d537  mov     rcx, rbx; MemoryDescriptorList
0x14000d53a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000d541  nop     dword ptr [rax+rax+00h]
0x14000d546  test    rax, rax
0x14000d549  jz      short loc_14000D582
0x14000d54b  mov     r15d, esi
0x14000d54e  mov     ecx, r14d
0x14000d551  add     rcx, rax; void *
0x14000d554  mov     r8d, r15d; Size
0x14000d557  mov     rdx, r12; Src
0x14000d55a  test    r13b, r13b
0x14000d55d  jz      short loc_14000D566
0x14000d55f  call    RtlCopyFromUser
0x14000d564  jmp     short loc_14000D56B
0x14000d566  call    RtlCopyVolatileMemory
0x14000d56b  jmp     short loc_14000D56F
0x14000d56d  jmp     short loc_14000D58E
0x14000d56f  xor     r14d, r14d
0x14000d572  add     r12, r15
0x14000d575  sub     edi, esi
0x14000d577  mov     rbx, [rbx]
0x14000d57a  jmp     short loc_14000D500
0x14000d57c  mov     rax, [rbx+18h]
0x14000d580  jmp     short loc_14000D546
0x14000d582  mov     r9, [rsp+58h+arg_18]
0x14000d587  test    r9, r9
0x14000d58a  jnz     short loc_14000D5A7
0x14000d58c  xor     eax, eax
0x14000d58e  mov     rbx, [rsp+58h+arg_0]
0x14000d593  mov     rsi, [rsp+58h+arg_8]
0x14000d598  add     rsp, 30h
0x14000d59c  pop     r15
0x14000d59e  pop     r14
0x14000d5a0  pop     r13
0x14000d5a2  pop     r12
0x14000d5a4  pop     rdi
0x14000d5a5  retn
0x14000d5a7  mov     rax, [rsp+58h+arg_10]
0x14000d5ac  sub     r12, [rax]
0x14000d5af  mov     [r9], r12
0x14000d5b2  jmp     short loc_14000D58C
```
