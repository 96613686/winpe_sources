# CdpReadIoInput

- ea: `0x14000aa00`
- end: `0x14000ab21`
- name: `CdpReadIoInput`
- size: `289`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a390`
- `0x14000a5e0`
- `0x14000cc10`

## callees

- `0x140001500`
- `0x1400080c4`
- `0x14000aa00`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000aa93`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000aa93`

## pseudocode

```c
__int64 __fastcall CdpReadIoInput(__int64 a1, char a2, char **a3, _QWORD *a4)
{
  char *v5; // r12
  unsigned int v6; // edi
  unsigned int v7; // r14d
  struct _MDL *v8; // rbx
  unsigned int ByteCount; // eax
  unsigned int v10; // esi
  char *v11; // rax
  char *v12; // rdx

  v5 = *a3;
  v6 = *((_DWORD *)a3 + 2);
  v7 = *((_DWORD *)a3 + 3);
  v8 = *(struct _MDL **)(*(_QWORD *)(a1 + 184) + 24LL);
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
        RtlCopyToUser(v5, v12, v10);
      else
        RtlCopyVolatileMemory(v5, v12, v10);
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
0x14000aa00  mov     [rsp+arg_0], rbx
0x14000aa05  mov     [rsp+arg_8], rsi
0x14000aa0a  mov     [rsp+arg_18], r9
0x14000aa0f  mov     [rsp+arg_10], r8
0x14000aa14  push    rdi
0x14000aa15  push    r12
0x14000aa17  push    r13
0x14000aa19  push    r14
0x14000aa1b  push    r15
0x14000aa1d  sub     rsp, 30h
0x14000aa21  movzx   r13d, dl
0x14000aa25  mov     r12, [r8]
0x14000aa28  mov     edi, [r8+8]
0x14000aa2c  mov     r14d, [r8+0Ch]
0x14000aa30  mov     rbx, [rcx+0B8h]
0x14000aa37  mov     rbx, [rbx+18h]
0x14000aa3b  test    rbx, rbx
0x14000aa3e  jz      loc_14000AADB
0x14000aa44  test    r14d, r14d
0x14000aa47  jz      short loc_14000AA55
0x14000aa49  mov     eax, [rbx+28h]
0x14000aa4c  cmp     r14d, eax
0x14000aa4f  jnb     loc_14000AB00
0x14000aa55  test    rbx, rbx
0x14000aa58  jz      loc_14000AADB
0x14000aa5e  test    edi, edi
0x14000aa60  jz      short loc_14000AADB
0x14000aa62  mov     eax, [rbx+28h]
0x14000aa65  sub     eax, r14d
0x14000aa68  mov     esi, edi
0x14000aa6a  cmp     edi, eax
0x14000aa6c  cmovnb  esi, eax
0x14000aa6f  test    byte ptr [rbx+0Ah], 5
0x14000aa73  jnz     short loc_14000AAD5
0x14000aa75  mov     [rsp+58h+Priority], 40000010h; Priority
0x14000aa7d  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000aa85  xor     r9d, r9d; RequestedAddress
0x14000aa88  xor     edx, edx; AccessMode
0x14000aa8a  mov     r8d, 1; CacheType
0x14000aa90  mov     rcx, rbx; MemoryDescriptorList
0x14000aa93  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000aa9a  nop     dword ptr [rax+rax+00h]
0x14000aa9f  test    rax, rax
0x14000aaa2  jz      short loc_14000AADB
0x14000aaa4  mov     r15d, esi
0x14000aaa7  mov     edx, r14d
0x14000aaaa  add     rdx, rax; Src
0x14000aaad  mov     r8d, r15d; Size
0x14000aab0  mov     rcx, r12; void *
0x14000aab3  test    r13b, r13b
0x14000aab6  jnz     short loc_14000AABF
0x14000aab8  call    RtlCopyVolatileMemory
0x14000aabd  jmp     short loc_14000AAC4
0x14000aabf  call    RtlCopyToUser
0x14000aac4  jmp     short loc_14000AAC8
0x14000aac6  jmp     short loc_14000AAE7
0x14000aac8  xor     r14d, r14d
0x14000aacb  add     r12, r15
0x14000aace  sub     edi, esi
0x14000aad0  mov     rbx, [rbx]
0x14000aad3  jmp     short loc_14000AA55
0x14000aad5  mov     rax, [rbx+18h]
0x14000aad9  jmp     short loc_14000AA9F
0x14000aadb  mov     r9, [rsp+58h+arg_18]
0x14000aae0  test    r9, r9
0x14000aae3  jnz     short loc_14000AB14
0x14000aae5  xor     eax, eax
0x14000aae7  mov     rbx, [rsp+58h+arg_0]
0x14000aaec  mov     rsi, [rsp+58h+arg_8]
0x14000aaf1  add     rsp, 30h
0x14000aaf5  pop     r15
0x14000aaf7  pop     r14
0x14000aaf9  pop     r13
0x14000aafb  pop     r12
0x14000aafd  pop     rdi
0x14000aafe  retn
0x14000ab00  sub     r14d, eax
0x14000ab03  mov     rbx, [rbx]
0x14000ab06  test    rbx, rbx
0x14000ab09  jnz     loc_14000AA44
0x14000ab0f  jmp     loc_14000AA55
0x14000ab14  mov     rax, [rsp+58h+arg_10]
0x14000ab19  sub     r12, [rax]
0x14000ab1c  mov     [r9], r12
0x14000ab1f  jmp     short loc_14000AAE5
```
