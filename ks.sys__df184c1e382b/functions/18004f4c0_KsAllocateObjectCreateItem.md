# KsAllocateObjectCreateItem

- ea: `0x18004f4c0`
- end: `0x18004f63d`
- name: `KsAllocateObjectCreateItem`
- size: `381`
- prototype: `NTSTATUS __stdcall(KSDEVICE_HEADER Header, PKSOBJECT_CREATE_ITEM CreateItem, BOOLEAN AllocateEntry, PFNKSITEMFREECALLBACK ItemFreeCallback)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004f3c8`

## callees

- `0x18001a000`
- `0x18004f4c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18004f5a8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18004f5a8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18004f5e6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18004f5e6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004f5d0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004f5d0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18004f613`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18004f613`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004f61f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004f61f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004f4f8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004f52b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004f4f8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004f52b`

## pseudocode

```c
NTSTATUS __stdcall KsAllocateObjectCreateItem(
        KSDEVICE_HEADER Header,
        PKSOBJECT_CREATE_ITEM CreateItem,
        BOOLEAN AllocateEntry,
        PFNKSITEMFREECALLBACK ItemFreeCallback)
{
  UNICODE_STRING *p_ObjectClass; // r14
  __int64 Length; // r12
  char *PoolWithTag; // rax
  char *v11; // rbx
  char *v12; // rax
  PKSOBJECT_CREATE_ITEM v14; // rsi
  int v15; // eax
  KSDEVICE_HEADER *v16; // rax

  if ( AllocateEntry )
  {
    p_ObjectClass = &CreateItem->ObjectClass;
    Length = CreateItem->ObjectClass.Length;
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, Length + 88, 0x6563534Bu);
    v11 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, Length + 88);
  }
  else
  {
    v12 = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x28u, 0x6563534Bu);
    v11 = v12;
    if ( !ExPoolZeroingNativelySupported && v12 )
    {
      *(_OWORD *)v12 = 0;
      *((_OWORD *)v12 + 1) = 0;
      *((_QWORD *)v12 + 4) = 0;
    }
    p_ObjectClass = &CreateItem->ObjectClass;
  }
  if ( !v11 )
    return -1073741670;
  if ( AllocateEntry )
  {
    v14 = (PKSOBJECT_CREATE_ITEM)(v11 + 40);
    *(_OWORD *)(v11 + 40) = *(_OWORD *)&CreateItem->Create;
    *(UNICODE_STRING *)(v11 + 56) = CreateItem->ObjectClass;
    *(_OWORD *)(v11 + 72) = *(_OWORD *)&CreateItem->SecurityDescriptor;
    *((_QWORD *)v11 + 8) = v11 + 88;
    *((_WORD *)v11 + 29) = p_ObjectClass->Length;
    RtlCopyUnicodeString((PUNICODE_STRING)(v11 + 56), p_ObjectClass);
    v15 = 1;
  }
  else
  {
    v15 = 0;
    v14 = CreateItem;
    ItemFreeCallback = 0;
  }
  *((_QWORD *)v11 + 2) = v14;
  *((_QWORD *)v11 + 3) = ItemFreeCallback;
  *((_DWORD *)v11 + 9) = v15;
  *((_DWORD *)v11 + 8) = 1;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)Header + 208));
  v16 = (KSDEVICE_HEADER *)*((_QWORD *)Header + 1);
  if ( *v16 != Header )
    __fastfail(3u);
  *(_QWORD *)v11 = Header;
  *((_QWORD *)v11 + 1) = v16;
  *v16 = v11;
  *((_QWORD *)Header + 1) = v11;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)((char *)Header + 208));
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x18004f4c0  push    rbx
0x18004f4c2  push    rbp
0x18004f4c3  push    rsi
0x18004f4c4  push    rdi
0x18004f4c5  push    r12
0x18004f4c7  push    r14
0x18004f4c9  push    r15
0x18004f4cb  sub     rsp, 20h
0x18004f4cf  mov     sil, r8b
0x18004f4d2  mov     rdi, rcx
0x18004f4d5  test    r8b, r8b
0x18004f4d8  mov     ecx, 401h; PoolType
0x18004f4dd  mov     r8d, 6563534Bh; Tag
0x18004f4e3  mov     r15, r9
0x18004f4e6  mov     rbp, rdx
0x18004f4e9  jz      short loc_18004F526
0x18004f4eb  lea     r14, [rdx+10h]
0x18004f4ef  movzx   r12d, word ptr [r14]
0x18004f4f3  lea     rdx, [r12+58h]; NumberOfBytes
0x18004f4f8  call    cs:__imp_ExAllocatePoolWithTag
0x18004f4ff  nop     dword ptr [rax+rax+00h]
0x18004f504  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18004f50b  mov     rbx, rax
0x18004f50e  jnz     short loc_18004F55C
0x18004f510  test    rax, rax
0x18004f513  jz      short loc_18004F55C
0x18004f515  lea     r8, [r12+58h]; Size
0x18004f51a  xor     edx, edx; Val
0x18004f51c  mov     rcx, rax; void *
0x18004f51f  call    memset
0x18004f524  jmp     short loc_18004F55C
0x18004f526  mov     edx, 28h ; '('; NumberOfBytes
0x18004f52b  call    cs:__imp_ExAllocatePoolWithTag
0x18004f532  nop     dword ptr [rax+rax+00h]
0x18004f537  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18004f53e  mov     rbx, rax
0x18004f541  jnz     short loc_18004F558
0x18004f543  test    rax, rax
0x18004f546  jz      short loc_18004F558
0x18004f548  xorps   xmm0, xmm0
0x18004f54b  xor     eax, eax
0x18004f54d  movups  xmmword ptr [rbx], xmm0
0x18004f550  movups  xmmword ptr [rbx+10h], xmm0
0x18004f554  mov     [rbx+20h], rax
0x18004f558  lea     r14, [rbp+10h]
0x18004f55c  test    rbx, rbx
0x18004f55f  jnz     short loc_18004F56B
0x18004f561  mov     eax, 0C000009Ah
0x18004f566  jmp     loc_18004F62D
0x18004f56b  mov     r12d, 1
0x18004f571  test    sil, sil
0x18004f574  jz      short loc_18004F5B9
0x18004f576  movups  xmm0, xmmword ptr [rbp+0]
0x18004f57a  lea     rsi, [rbx+28h]
0x18004f57e  mov     rdx, r14; SourceString
0x18004f581  lea     rax, [rsi+30h]
0x18004f585  movups  xmmword ptr [rsi], xmm0
0x18004f588  lea     rcx, [rsi+10h]; DestinationString
0x18004f58c  movups  xmm1, xmmword ptr [rbp+10h]
0x18004f590  movups  xmmword ptr [rsi+10h], xmm1
0x18004f594  movups  xmm0, xmmword ptr [rbp+20h]
0x18004f598  movups  xmmword ptr [rsi+20h], xmm0
0x18004f59c  mov     [rsi+18h], rax
0x18004f5a0  movzx   eax, word ptr [r14]
0x18004f5a4  mov     [rsi+12h], ax
0x18004f5a8  call    cs:__imp_RtlCopyUnicodeString
0x18004f5af  nop     dword ptr [rax+rax+00h]
0x18004f5b4  mov     eax, r12d
0x18004f5b7  jmp     short loc_18004F5C1
0x18004f5b9  xor     eax, eax
0x18004f5bb  mov     rsi, rbp
0x18004f5be  xor     r15d, r15d
0x18004f5c1  mov     [rbx+10h], rsi
0x18004f5c5  mov     [rbx+18h], r15
0x18004f5c9  mov     [rbx+24h], eax
0x18004f5cc  mov     [rbx+20h], r12d
0x18004f5d0  call    cs:__imp_KeEnterCriticalRegion
0x18004f5d7  nop     dword ptr [rax+rax+00h]
0x18004f5dc  lea     rsi, [rdi+0D0h]
0x18004f5e3  mov     rcx, rsi; FastMutex
0x18004f5e6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x18004f5ed  nop     dword ptr [rax+rax+00h]
0x18004f5f2  mov     rax, [rdi+8]
0x18004f5f6  cmp     [rax], rdi
0x18004f5f9  jz      short loc_18004F602
0x18004f5fb  mov     ecx, 3
0x18004f600  int     29h; Win8: RtlFailFast(ecx)
0x18004f602  mov     [rbx], rdi
0x18004f605  mov     rcx, rsi; FastMutex
0x18004f608  mov     [rbx+8], rax
0x18004f60c  mov     [rax], rbx
0x18004f60f  mov     [rdi+8], rbx
0x18004f613  call    cs:__imp_ExReleaseFastMutexUnsafe
0x18004f61a  nop     dword ptr [rax+rax+00h]
0x18004f61f  call    cs:__imp_KeLeaveCriticalRegion
0x18004f626  nop     dword ptr [rax+rax+00h]
0x18004f62b  xor     eax, eax
0x18004f62d  add     rsp, 20h
0x18004f631  pop     r15
0x18004f633  pop     r14
0x18004f635  pop     r12
0x18004f637  pop     rdi
0x18004f638  pop     rsi
0x18004f639  pop     rbp
0x18004f63a  pop     rbx
0x18004f63b  retn
```
