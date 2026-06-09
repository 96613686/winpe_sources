# CmsTxMemLog::AllocateRedoBlock(CmsVolume *,CmsDurableLog *,ulong)

- ea: `0x140084ba0`
- end: `0x140084d54`
- name: `?AllocateRedoBlock@CmsTxMemLog@@SAPEAU_SmsRedoBlock@@PEAVCmsVolume@@PEAVCmsDurableLog@@K@Z`
- size: `436`
- prototype: `struct _SmsRedoBlock *__fastcall(struct CmsVolume *, struct CmsDurableLog *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140150590`

## callees

- `0x140084ba0`
- `0x140084d5c`
- `0x1400c8574`
- `0x140172940`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140084d29`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140084d29`
- `ntoskrnl!ExAllocatePool2` at `0x140084bc5`
- `ntoskrnl!ExAllocatePool2` at `0x140084c3a`
- `ntoskrnl!ExAllocatePool2` at `0x140084bc5`
- `ntoskrnl!ExAllocatePool2` at `0x140084c3a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140084c02`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140084c02`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f8074`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f8074`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140084d43`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140084d43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084c9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084c9e`

## string_xrefs

- `0x140084c4a`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
struct _SmsRedoBlock *__fastcall CmsTxMemLog::AllocateRedoBlock(struct CmsVolume *a1, struct CmsDurableLog *a2, int a3)
{
  struct _SmsRedoBlock *result; // rax
  struct _SmsRedoBlock *v6; // rbx
  __int64 EntryHeaderSize; // rsi
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 Pool2; // rax
  int v11; // ecx
  __int64 LogMetadataAddress; // rax
  int v13; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx

  result = (struct _SmsRedoBlock *)ExAllocatePool2(66, 72, 1766871885);
  v6 = result;
  if ( !result )
    return result;
  memset(result, 0, 0x48u);
  EntryHeaderSize = (unsigned int)LogGetEntryHeaderSize(*((_QWORD *)a2 + 9), (unsigned int)(a3 + 8));
  v8 = qword_140262440 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( (unsigned int)EntryHeaderSize > *(_DWORD *)v8 )
  {
    v8 = 0;
    v9 = EntryHeaderSize + 16;
    goto LABEL_4;
  }
  if ( !*(_BYTE *)(v8 + 8) )
  {
    if ( (int)*(_QWORD *)(v8 + 88) > (int)HIDWORD(*(_QWORD *)(v8 + 88)) )
    {
      v11 = _InterlockedDecrement((volatile signed __int32 *)(v8 + 88));
      if ( v11 >= *(_DWORD *)(v8 + 92) && v11 >= 0 )
      {
        Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v8 + 64));
        goto LABEL_13;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 88));
    }
LABEL_10:
    v9 = *(unsigned int *)(v8 + 4);
LABEL_4:
    Pool2 = ExAllocatePool2(66, v9, 1766871885);
    if ( (Pool2 & 0xF) != 0 )
      MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
    if ( !Pool2 )
      goto LABEL_12;
    goto LABEL_14;
  }
  v14 = (struct _NPAGED_LOOKASIDE_LIST *)(v8 + 64);
  if ( *(_BYTE *)(v8 + 9) )
    Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v14);
  else
    Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v14);
LABEL_13:
  if ( !Pool2 )
    goto LABEL_10;
LABEL_14:
  *(_QWORD *)Pool2 = v8;
  if ( Pool2 == -16 )
  {
LABEL_12:
    ExFreePoolWithTag(v6, 0);
    return 0;
  }
  *(_QWORD *)v6 = Pool2 + 16;
  LogMetadataAddress = MlLogGetLogMetadataAddress(*((_QWORD *)a2 + 9));
  *((_QWORD *)v6 + 1) = LogMetadataAddress;
  LogMetadataAddress += 8;
  *((_QWORD *)v6 + 2) = LogMetadataAddress;
  *(_OWORD *)LogMetadataAddress = 0;
  *(_OWORD *)(LogMetadataAddress + 16) = 0;
  *(_OWORD *)(LogMetadataAddress + 32) = 0;
  *(_QWORD *)(LogMetadataAddress + 48) = 0;
  result = v6;
  v13 = *(_DWORD *)v6 - *((_DWORD *)v6 + 2);
  *(_QWORD *)((char *)v6 + 28) = 8;
  *((_DWORD *)v6 + 6) = EntryHeaderSize + v13;
  *((_DWORD *)v6 + 9) = EntryHeaderSize;
  return result;
}

```

## disassembly

```asm
0x140084ba0  mov     [rsp+arg_8], rbx
0x140084ba5  mov     [rsp+arg_10], rbp
0x140084baa  push    rdi
0x140084bab  sub     rsp, 20h
0x140084baf  mov     edi, r8d
0x140084bb2  mov     rbp, rdx
0x140084bb5  mov     edx, 48h ; 'H'
0x140084bba  mov     r8d, 6950534Dh
0x140084bc0  mov     ecx, 42h ; 'B'
0x140084bc5  call    cs:__imp_ExAllocatePool2
0x140084bcc  nop     dword ptr [rax+rax+00h]
0x140084bd1  mov     rbx, rax
0x140084bd4  test    rax, rax
0x140084bd7  jz      loc_140084D19
0x140084bdd  xor     edx, edx; Val
0x140084bdf  mov     [rsp+28h+arg_0], rsi
0x140084be4  mov     r8d, 48h ; 'H'; Size
0x140084bea  mov     rcx, rax; void *
0x140084bed  call    memset
0x140084bf2  mov     rcx, [rbp+48h]
0x140084bf6  lea     edx, [rdi+8]
0x140084bf9  call    LogGetEntryHeaderSize
0x140084bfe  xor     ecx, ecx; ProcNumber
0x140084c00  mov     esi, eax
0x140084c02  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140084c09  nop     dword ptr [rax+rax+00h]
0x140084c0e  xor     edx, edx
0x140084c10  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140084c16  lea     rdi, [rdx+rdx*2]
0x140084c1a  shl     rdi, 6
0x140084c1e  add     rdi, cs:qword_140262440
0x140084c25  cmp     esi, [rdi]
0x140084c27  jbe     short loc_140084C57
0x140084c29  xor     edi, edi
0x140084c2b  lea     rdx, [rsi+10h]
0x140084c2f  mov     ecx, 42h ; 'B'
0x140084c34  mov     r8d, 6950534Dh
0x140084c3a  call    cs:__imp_ExAllocatePool2
0x140084c41  nop     dword ptr [rax+rax+00h]
0x140084c46  test    al, 0Fh
0x140084c48  jz      short loc_140084C94
0x140084c4a  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140084c51  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140084c57  cmp     byte ptr [rdi+8], 0
0x140084c5b  jnz     loc_140084D1B
0x140084c61  mov     rcx, [rdi+58h]
0x140084c65  mov     rax, rcx
0x140084c68  shr     rax, 20h
0x140084c6c  cmp     ecx, eax
0x140084c6e  jle     short loc_140084C8F
0x140084c70  nop
0x140084c71  mov     ecx, 0FFFFFFFFh
0x140084c76  lock xadd [rdi+58h], ecx
0x140084c7b  nop
0x140084c7c  dec     ecx
0x140084c7e  mov     eax, [rdi+5Ch]
0x140084c81  cmp     ecx, eax
0x140084c83  jge     loc_140084D37
0x140084c89  nop
0x140084c8a  lock inc dword ptr [rdi+58h]
0x140084c8e  nop
0x140084c8f  mov     edx, [rdi+4]
0x140084c92  jmp     short loc_140084C2F
0x140084c94  test    rax, rax
0x140084c97  jnz     short loc_140084CC7
0x140084c99  xor     edx, edx; Tag
0x140084c9b  mov     rcx, rbx; P
0x140084c9e  call    cs:__imp_ExFreePoolWithTag
0x140084ca5  nop     dword ptr [rax+rax+00h]
0x140084caa  xor     eax, eax
0x140084cac  mov     rsi, [rsp+28h+arg_0]
0x140084cb1  mov     rbx, [rsp+28h+arg_8]
0x140084cb6  mov     rbp, [rsp+28h+arg_10]
0x140084cbb  add     rsp, 20h
0x140084cbf  pop     rdi
0x140084cc0  retn
0x140084cc2  test    rax, rax
0x140084cc5  jz      short loc_140084C8F
0x140084cc7  lea     rdx, [rax+10h]
0x140084ccb  mov     [rax], rdi
0x140084cce  test    rdx, rdx
0x140084cd1  jz      short loc_140084C99
0x140084cd3  mov     [rbx], rdx
0x140084cd6  mov     rcx, [rbp+48h]
0x140084cda  call    MlLogGetLogMetadataAddress
0x140084cdf  mov     [rbx+8], rax
0x140084ce3  xor     ecx, ecx
0x140084ce5  add     rax, 8
0x140084ce9  xorps   xmm0, xmm0
0x140084cec  mov     [rbx+10h], rax
0x140084cf0  movups  xmmword ptr [rax], xmm0
0x140084cf3  movups  xmmword ptr [rax+10h], xmm0
0x140084cf7  movups  xmmword ptr [rax+20h], xmm0
0x140084cfb  mov     [rax+30h], rcx
0x140084cff  mov     rax, rbx
0x140084d02  mov     ecx, [rbx]
0x140084d04  sub     ecx, [rbx+8]
0x140084d07  add     ecx, esi
0x140084d09  mov     qword ptr [rbx+1Ch], 8
0x140084d11  mov     [rbx+18h], ecx
0x140084d14  mov     [rbx+24h], esi
0x140084d17  jmp     short loc_140084CAC
0x140084d19  jmp     short loc_140084CB1
0x140084d1b  cmp     byte ptr [rdi+9], 0
0x140084d1f  lea     rcx, [rdi+40h]; Lookaside
0x140084d23  jz      loc_1401F8074
0x140084d29  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140084d30  nop     dword ptr [rax+rax+00h]
0x140084d35  jmp     short loc_140084CC2
0x140084d37  test    ecx, ecx
0x140084d39  js      loc_140084C89
0x140084d3f  lea     rcx, [rdi+40h]; ListHead
0x140084d43  call    cs:__imp_ExpInterlockedPopEntrySList
0x140084d4a  nop     dword ptr [rax+rax+00h]
0x140084d4f  jmp     loc_140084CC2
0x1401f8074  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f807b  nop     dword ptr [rax+rax+00h]
0x1401f8080  nop
0x1401f8081  jmp     loc_140084CC2
```
