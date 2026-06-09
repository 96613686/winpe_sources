# InitializeClientSideSslProvCache(void)

- ea: `0x14000abc0`
- end: `0x14000ac36`
- name: `?InitializeClientSideSslProvCache@@YAJXZ`
- size: `118`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400217e0`

## callees

- `0x14000abc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac16`
- `ntoskrnl!ExAllocatePool2` at `0x14000abd4`
- `ntoskrnl!ExAllocatePool2` at `0x14000abd4`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000abf6`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000abf6`

## pseudocode

```c
__int64 InitializeClientSideSslProvCache(void)
{
  struct _ERESOURCE *Pool2; // rax
  unsigned int v2; // ebx

  Pool2 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1131180883);
  g_pSslProvCacheRWLock = Pool2;
  if ( !Pool2 )
    return 2148074240LL;
  v2 = ExInitializeResourceLite(Pool2);
  if ( v2 )
  {
    if ( g_pSslProvCacheRWLock )
    {
      ExFreePoolWithTag(g_pSslProvCacheRWLock, 0);
      g_pSslProvCacheRWLock = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000abc0  push    rbx
0x14000abc2  sub     rsp, 20h
0x14000abc6  mov     edx, 68h ; 'h'
0x14000abcb  mov     r8d, 436C7353h
0x14000abd1  lea     ecx, [rdx-28h]
0x14000abd4  call    cs:__imp_ExAllocatePool2
0x14000abdb  nop     dword ptr [rax+rax+00h]
0x14000abe0  mov     cs:?g_pSslProvCacheRWLock@@3PEAU_ERESOURCE@@EA, rax; _ERESOURCE * g_pSslProvCacheRWLock
0x14000abe7  test    rax, rax
0x14000abea  jnz     short loc_14000ABF3
0x14000abec  mov     eax, 80090300h
0x14000abf1  jmp     short loc_14000AC2F
0x14000abf3  mov     rcx, rax; Resource
0x14000abf6  call    cs:__imp_ExInitializeResourceLite
0x14000abfd  nop     dword ptr [rax+rax+00h]
0x14000ac02  mov     ebx, eax
0x14000ac04  test    eax, eax
0x14000ac06  jz      short loc_14000AC2D
0x14000ac08  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_ERESOURCE@@EA; P
0x14000ac0f  test    rcx, rcx
0x14000ac12  jz      short loc_14000AC2D
0x14000ac14  xor     edx, edx; Tag
0x14000ac16  call    cs:__imp_ExFreePoolWithTag
0x14000ac1d  nop     dword ptr [rax+rax+00h]
0x14000ac22  mov     cs:?g_pSslProvCacheRWLock@@3PEAU_ERESOURCE@@EA, 0; _ERESOURCE * g_pSslProvCacheRWLock
0x14000ac2d  mov     eax, ebx
0x14000ac2f  add     rsp, 20h
0x14000ac33  pop     rbx
0x14000ac34  retn
```
