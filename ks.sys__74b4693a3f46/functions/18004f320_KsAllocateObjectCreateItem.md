# KsAllocateObjectCreateItem

- ea: `0x18004f320`
- end: `0x18004f49d`
- name: `KsAllocateObjectCreateItem`
- size: `381`
- prototype: `NTSTATUS __stdcall(KSDEVICE_HEADER Header, PKSOBJECT_CREATE_ITEM CreateItem, BOOLEAN AllocateEntry, PFNKSITEMFREECALLBACK ItemFreeCallback)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004f228`

## callees

- `0x180019fc0`
- `0x18004f320`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18004f408`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18004f408`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18004f446`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18004f446`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004f430`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004f430`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18004f473`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18004f473`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004f47f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004f47f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004f358`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004f38b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004f358`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004f38b`

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
0x18004f320  push    rbx
0x18004f322  push    rbp
0x18004f323  push    rsi
0x18004f324  push    rdi
0x18004f325  push    r12
0x18004f327  push    r14
0x18004f329  push    r15
0x18004f32b  sub     rsp, 20h
0x18004f32f  mov     sil, r8b
0x18004f332  mov     rdi, rcx
0x18004f335  test    r8b, r8b
0x18004f338  mov     ecx, 401h; PoolType
0x18004f33d  mov     r8d, 6563534Bh; Tag
0x18004f343  mov     r15, r9
0x18004f346  mov     rbp, rdx
0x18004f349  jz      short loc_18004F386
0x18004f34b  lea     r14, [rdx+10h]
0x18004f34f  movzx   r12d, word ptr [r14]
0x18004f353  lea     rdx, [r12+58h]; NumberOfBytes
0x18004f358  call    cs:__imp_ExAllocatePoolWithTag
0x18004f35f  nop     dword ptr [rax+rax+00h]
0x18004f364  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18004f36b  mov     rbx, rax
0x18004f36e  jnz     short loc_18004F3BC
0x18004f370  test    rax, rax
0x18004f373  jz      short loc_18004F3BC
0x18004f375  lea     r8, [r12+58h]; Size
0x18004f37a  xor     edx, edx; Val
0x18004f37c  mov     rcx, rax; void *
0x18004f37f  call    memset
0x18004f384  jmp     short loc_18004F3BC
0x18004f386  mov     edx, 28h ; '('; NumberOfBytes
0x18004f38b  call    cs:__imp_ExAllocatePoolWithTag
0x18004f392  nop     dword ptr [rax+rax+00h]
0x18004f397  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18004f39e  mov     rbx, rax
0x18004f3a1  jnz     short loc_18004F3B8
0x18004f3a3  test    rax, rax
0x18004f3a6  jz      short loc_18004F3B8
0x18004f3a8  xorps   xmm0, xmm0
0x18004f3ab  xor     eax, eax
0x18004f3ad  movups  xmmword ptr [rbx], xmm0
0x18004f3b0  movups  xmmword ptr [rbx+10h], xmm0
0x18004f3b4  mov     [rbx+20h], rax
0x18004f3b8  lea     r14, [rbp+10h]
0x18004f3bc  test    rbx, rbx
0x18004f3bf  jnz     short loc_18004F3CB
0x18004f3c1  mov     eax, 0C000009Ah
0x18004f3c6  jmp     loc_18004F48D
0x18004f3cb  mov     r12d, 1
0x18004f3d1  test    sil, sil
0x18004f3d4  jz      short loc_18004F419
0x18004f3d6  movups  xmm0, xmmword ptr [rbp+0]
0x18004f3da  lea     rsi, [rbx+28h]
0x18004f3de  mov     rdx, r14; SourceString
0x18004f3e1  lea     rax, [rsi+30h]
0x18004f3e5  movups  xmmword ptr [rsi], xmm0
0x18004f3e8  lea     rcx, [rsi+10h]; DestinationString
0x18004f3ec  movups  xmm1, xmmword ptr [rbp+10h]
0x18004f3f0  movups  xmmword ptr [rsi+10h], xmm1
0x18004f3f4  movups  xmm0, xmmword ptr [rbp+20h]
0x18004f3f8  movups  xmmword ptr [rsi+20h], xmm0
0x18004f3fc  mov     [rsi+18h], rax
0x18004f400  movzx   eax, word ptr [r14]
0x18004f404  mov     [rsi+12h], ax
0x18004f408  call    cs:__imp_RtlCopyUnicodeString
0x18004f40f  nop     dword ptr [rax+rax+00h]
0x18004f414  mov     eax, r12d
0x18004f417  jmp     short loc_18004F421
0x18004f419  xor     eax, eax
0x18004f41b  mov     rsi, rbp
0x18004f41e  xor     r15d, r15d
0x18004f421  mov     [rbx+10h], rsi
0x18004f425  mov     [rbx+18h], r15
0x18004f429  mov     [rbx+24h], eax
0x18004f42c  mov     [rbx+20h], r12d
0x18004f430  call    cs:__imp_KeEnterCriticalRegion
0x18004f437  nop     dword ptr [rax+rax+00h]
0x18004f43c  lea     rsi, [rdi+0D0h]
0x18004f443  mov     rcx, rsi; FastMutex
0x18004f446  call    cs:__imp_ExAcquireFastMutexUnsafe
0x18004f44d  nop     dword ptr [rax+rax+00h]
0x18004f452  mov     rax, [rdi+8]
0x18004f456  cmp     [rax], rdi
0x18004f459  jz      short loc_18004F462
0x18004f45b  mov     ecx, 3
0x18004f460  int     29h; Win8: RtlFailFast(ecx)
0x18004f462  mov     [rbx], rdi
0x18004f465  mov     rcx, rsi; FastMutex
0x18004f468  mov     [rbx+8], rax
0x18004f46c  mov     [rax], rbx
0x18004f46f  mov     [rdi+8], rbx
0x18004f473  call    cs:__imp_ExReleaseFastMutexUnsafe
0x18004f47a  nop     dword ptr [rax+rax+00h]
0x18004f47f  call    cs:__imp_KeLeaveCriticalRegion
0x18004f486  nop     dword ptr [rax+rax+00h]
0x18004f48b  xor     eax, eax
0x18004f48d  add     rsp, 20h
0x18004f491  pop     r15
0x18004f493  pop     r14
0x18004f495  pop     r12
0x18004f497  pop     rdi
0x18004f498  pop     rsi
0x18004f499  pop     rbp
0x18004f49a  pop     rbx
0x18004f49b  retn
```
