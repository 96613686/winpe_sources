# BfsCreateGlobalFileEntry

- ea: `0x14000c5c4`
- end: `0x14000c7e2`
- name: `BfsCreateGlobalFileEntry`
- size: `542`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c0f4`

## callees

- `0x140001008`
- `0x14000c5c4`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14000c703`
- `ntoskrnl!RtlCreateHashTable` at `0x14000c703`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000c798`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000c798`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c71c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c76c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c783`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c71c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c76c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c783`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7aa`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000c6c9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000c6c9`
- `ntoskrnl!ExAllocatePool2` at `0x14000c602`
- `ntoskrnl!ExAllocatePool2` at `0x14000c67e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c6e3`
- `ntoskrnl!ExAllocatePool2` at `0x14000c602`
- `ntoskrnl!ExAllocatePool2` at `0x14000c67e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c6e3`

## pseudocode

```c
__int64 __fastcall BfsCreateGlobalFileEntry(PCUNICODE_STRING SourceString, int a2, struct _UNICODE_STRING **a3)
{
  __int64 Pool2; // rax
  int v7; // r8d
  int v8; // r9d
  struct _UNICODE_STRING *v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  __int64 v15; // rax
  PVOID *p_Buffer; // rdi
  PWSTR Buffer; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v18; // rcx
  int v20; // [rsp+20h] [rbp-50h]
  int v21; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+38h] [rbp-38h] BYREF
  int *v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+60h] [rbp-10h]

  Pool2 = ExAllocatePool2(256, 96, 1735616066);
  v9 = (struct _UNICODE_STRING *)Pool2;
  if ( !Pool2 )
  {
    v10 = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v21 = -1073741801;
      v23 = &v21;
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(-1073741801, (int)&byte_140016D91, v7, v8, v20, &v22);
    }
    goto LABEL_13;
  }
  *(_DWORD *)(Pool2 + 80) = a2;
  *(_BYTE *)(Pool2 + 40) = 0;
  *(_QWORD *)(Pool2 + 48) = 0;
  v11 = ExAllocatePool2(256, SourceString->Length + 2LL, 1316185666);
  v9[4].Buffer = (PWSTR)v11;
  if ( v11 )
  {
    v9[4].Length = SourceString->Length;
    v9[4].MaximumLength = SourceString->Length + 2;
    RtlCopyUnicodeString(v9 + 4, SourceString);
    v15 = ExAllocatePool2(256, 40, 1416848962);
    p_Buffer = (PVOID *)&v9[5].Buffer;
    v9[5].Buffer = (PWSTR)v15;
    if ( v15 )
    {
      if ( RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)&v9[5].Buffer, 0, 0) )
      {
        v10 = 0;
        goto LABEL_19;
      }
      ExFreePoolWithTag(*p_Buffer, 0);
      *p_Buffer = 0;
      v10 = -1073741823;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_12;
      v21 = -1073741823;
      goto LABEL_11;
    }
  }
  v14 = -1073741801;
  v10 = -1073741801;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v21 = -1073741801;
LABEL_11:
    v24 = 4;
    v23 = &v21;
    tlgWriteTransfer_EtwWriteTransfer(v14, (int)&byte_140016D91, v12, v13, v20, &v22);
  }
LABEL_12:
  ExFreePoolWithTag(v9, 0);
LABEL_13:
  Buffer = v9[4].Buffer;
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  v18 = (struct _RTL_DYNAMIC_HASH_TABLE *)v9[5].Buffer;
  if ( v18 )
  {
    RtlDeleteHashTable(v18);
    ExFreePoolWithTag(v9[5].Buffer, 0);
  }
  v9 = 0;
LABEL_19:
  *a3 = v9;
  return v10;
}

```

## disassembly

```asm
0x14000c5c4  mov     [rsp-28h+arg_8], rbx
0x14000c5c9  push    rbp
0x14000c5ca  push    rsi
0x14000c5cb  push    rdi
0x14000c5cc  push    r12
0x14000c5ce  push    r14
0x14000c5d0  mov     rbp, rsp
0x14000c5d3  sub     rsp, 70h
0x14000c5d7  mov     rax, cs:__security_cookie
0x14000c5de  xor     rax, rsp
0x14000c5e1  mov     [rbp+var_8], rax
0x14000c5e5  mov     rsi, r8
0x14000c5e8  mov     r14d, edx
0x14000c5eb  mov     rdi, rcx
0x14000c5ee  mov     r12d, 100h
0x14000c5f4  mov     ecx, r12d
0x14000c5f7  mov     edx, 60h ; '`'
0x14000c5fc  mov     r8d, 67736642h
0x14000c602  call    cs:__imp_ExAllocatePool2
0x14000c609  nop     dword ptr [rax+rax+00h]
0x14000c60e  mov     rbx, rax
0x14000c611  test    rax, rax
0x14000c614  jnz     short loc_14000C659
0x14000c616  mov     eax, cs:dword_140019000
0x14000c61c  mov     ecx, 0C0000017h; int
0x14000c621  mov     edi, ecx
0x14000c623  cmp     eax, 3
0x14000c626  jbe     loc_14000C778
0x14000c62c  lea     rax, [rbp+var_40]
0x14000c630  mov     [rbp+var_40], ecx
0x14000c633  mov     [rbp+var_18], rax
0x14000c637  lea     rdx, byte_140016D91; int
0x14000c63e  lea     rax, [rbp+var_38]
0x14000c642  mov     [rbp+var_10], 4
0x14000c64a  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x14000c64f  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c654  jmp     loc_14000C778
0x14000c659  mov     [rax+50h], r14d
0x14000c65d  mov     r8d, 4E736642h
0x14000c663  mov     byte ptr [rax+28h], 0
0x14000c667  mov     r14d, 2
0x14000c66d  mov     qword ptr [rax+30h], 0
0x14000c675  mov     rcx, r12
0x14000c678  movzx   edx, word ptr [rdi]
0x14000c67b  add     rdx, r14
0x14000c67e  call    cs:__imp_ExAllocatePool2
0x14000c685  nop     dword ptr [rax+rax+00h]
0x14000c68a  mov     [rbx+48h], rax
0x14000c68e  test    rax, rax
0x14000c691  jnz     short loc_14000C6B1
0x14000c693  mov     eax, cs:dword_140019000
0x14000c699  mov     ecx, 0C0000017h
0x14000c69e  mov     edi, ecx
0x14000c6a0  cmp     eax, 3
0x14000c6a3  jbe     loc_14000C767
0x14000c6a9  mov     [rbp+var_40], ecx
0x14000c6ac  jmp     loc_14000C742
0x14000c6b1  movzx   eax, word ptr [rdi]
0x14000c6b4  lea     rcx, [rbx+40h]; DestinationString
0x14000c6b8  mov     [rcx], ax
0x14000c6bb  mov     rdx, rdi; SourceString
0x14000c6be  movzx   eax, word ptr [rdi]
0x14000c6c1  add     ax, r14w
0x14000c6c5  mov     [rbx+42h], ax
0x14000c6c9  call    cs:__imp_RtlCopyUnicodeString
0x14000c6d0  nop     dword ptr [rax+rax+00h]
0x14000c6d5  mov     edx, 28h ; '('
0x14000c6da  mov     r8d, 54736642h
0x14000c6e0  mov     rcx, r12
0x14000c6e3  call    cs:__imp_ExAllocatePool2
0x14000c6ea  nop     dword ptr [rax+rax+00h]
0x14000c6ef  lea     rdi, [rbx+58h]
0x14000c6f3  mov     [rdi], rax
0x14000c6f6  test    rax, rax
0x14000c6f9  jz      short loc_14000C693
0x14000c6fb  xor     r8d, r8d; Flags
0x14000c6fe  xor     edx, edx; Shift
0x14000c700  mov     rcx, rdi; HashTable
0x14000c703  call    cs:__imp_RtlCreateHashTable
0x14000c70a  nop     dword ptr [rax+rax+00h]
0x14000c70f  test    al, al
0x14000c711  jnz     loc_14000C7BA
0x14000c717  mov     rcx, [rdi]; P
0x14000c71a  xor     edx, edx; Tag
0x14000c71c  call    cs:__imp_ExFreePoolWithTag
0x14000c723  nop     dword ptr [rax+rax+00h]
0x14000c728  mov     qword ptr [rdi], 0
0x14000c72f  mov     edi, 0C0000001h
0x14000c734  mov     eax, cs:dword_140019000
0x14000c73a  cmp     eax, 3
0x14000c73d  jbe     short loc_14000C767
0x14000c73f  mov     [rbp+var_40], edi
0x14000c742  lea     rax, [rbp+var_40]
0x14000c746  mov     [rbp+var_10], 4
0x14000c74e  mov     [rbp+var_18], rax
0x14000c752  lea     rdx, byte_140016D91; int
0x14000c759  lea     rax, [rbp+var_38]
0x14000c75d  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x14000c762  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c767  xor     edx, edx; Tag
0x14000c769  mov     rcx, rbx; P
0x14000c76c  call    cs:__imp_ExFreePoolWithTag
0x14000c773  nop     dword ptr [rax+rax+00h]
0x14000c778  mov     rcx, [rbx+48h]; P
0x14000c77c  test    rcx, rcx
0x14000c77f  jz      short loc_14000C78F
0x14000c781  xor     edx, edx; Tag
0x14000c783  call    cs:__imp_ExFreePoolWithTag
0x14000c78a  nop     dword ptr [rax+rax+00h]
0x14000c78f  mov     rcx, [rbx+58h]; HashTable
0x14000c793  test    rcx, rcx
0x14000c796  jz      short loc_14000C7B6
0x14000c798  call    cs:__imp_RtlDeleteHashTable
0x14000c79f  nop     dword ptr [rax+rax+00h]
0x14000c7a4  mov     rcx, [rbx+58h]; P
0x14000c7a8  xor     edx, edx; Tag
0x14000c7aa  call    cs:__imp_ExFreePoolWithTag
0x14000c7b1  nop     dword ptr [rax+rax+00h]
0x14000c7b6  xor     ebx, ebx
0x14000c7b8  jmp     short loc_14000C7BC
0x14000c7ba  xor     edi, edi
0x14000c7bc  mov     [rsi], rbx
0x14000c7bf  mov     eax, edi
0x14000c7c1  mov     rcx, [rbp+var_8]
0x14000c7c5  xor     rcx, rsp; StackCookie
0x14000c7c8  call    __security_check_cookie
0x14000c7cd  mov     rbx, [rsp+70h+arg_8]
0x14000c7d5  add     rsp, 70h
0x14000c7d9  pop     r14
0x14000c7db  pop     r12
0x14000c7dd  pop     rdi
0x14000c7de  pop     rsi
0x14000c7df  pop     rbp
0x14000c7e0  retn
```
