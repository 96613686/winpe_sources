# FwRemoveConflicts(unsigned __int64,void (*)(void *),int (*)(void const *,void const *),int (*)(void *,void const *),FW_GENERIC_ARRAY_ *)

- ea: `0x18002b710`
- end: `0x18002b79e`
- name: `?FwRemoveConflicts@@YAX_KP6AXPEAX@ZP6AHPEBX3@ZP6AH13@ZPEAUFW_GENERIC_ARRAY_@@@Z`
- size: `142`
- prototype: `void __fastcall(unsigned __int64, void (*)(void *), int (*)(const void *, const void *), int (*)(void *, const void *), struct FW_GENERIC_ARRAY_ *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011790`

## callees

- `0x18001164c`
- `0x180029f30`
- `0x18002b334`
- `0x18002b710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002b73a`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002b73a`

## pseudocode

```c
void __fastcall FwRemoveConflicts(
        __int64 a1,
        void (*a2)(void *),
        int (*a3)(const void *, const void *),
        int (*a4)(void *, const void *),
        void **a5)
{
  unsigned int v5; // esi
  const struct ICF_AUTHORIZED_APP_ *v6; // rbx
  struct ICF_AUTHORIZED_APP_ *v7; // rax

  if ( *(_DWORD *)a5 > 1u )
  {
    qsort(a5[1], *(unsigned int *)a5, 0x70u, FwPrioritizeApps);
    v5 = 1;
    while ( v5 < *(_DWORD *)a5 )
    {
      v6 = (const struct ICF_AUTHORIZED_APP_ *)FwArrayAt(112, a5, v5);
      v7 = (struct ICF_AUTHORIZED_APP_ *)FwArrayAt(112, a5, v5 - 1);
      if ( (unsigned int)FwAuthorizedAppResolveConflict(v7, v6) )
        FwArrayErase(112, FwIcfAuthorizedAppDestroy, a5, v5);
      else
        ++v5;
    }
  }
}

```

## disassembly

```asm
0x18002b710  push    rbx
0x18002b712  push    rsi
0x18002b713  push    rdi
0x18002b714  push    r14
0x18002b716  sub     rsp, 28h
0x18002b71a  mov     rdi, [rsp+48h+arg_20]
0x18002b71f  cmp     dword ptr [rdi], 1
0x18002b722  jbe     short loc_18002B794
0x18002b724  mov     edx, [rdi]; NumOfElements
0x18002b726  lea     r9, FwPrioritizeApps; CompareFunction
0x18002b72d  mov     rcx, [rdi+8]; Base
0x18002b731  mov     r14d, 70h ; 'p'
0x18002b737  mov     r8d, r14d; SizeOfElements
0x18002b73a  call    cs:__imp_qsort
0x18002b740  lea     esi, [r14-6Fh]
0x18002b744  cmp     [rdi], esi
0x18002b746  jbe     short loc_18002B794
0x18002b748  mov     r8d, esi
0x18002b74b  mov     rdx, rdi
0x18002b74e  mov     rcx, r14
0x18002b751  call    FwArrayAt
0x18002b756  lea     r8d, [rsi-1]
0x18002b75a  mov     rdx, rdi
0x18002b75d  mov     rcx, r14
0x18002b760  mov     rbx, rax
0x18002b763  call    FwArrayAt
0x18002b768  mov     rdx, rbx; struct ICF_AUTHORIZED_APP_ *
0x18002b76b  mov     rcx, rax; struct ICF_AUTHORIZED_APP_ *
0x18002b76e  call    ?FwAuthorizedAppResolveConflict@@YAHPEAUICF_AUTHORIZED_APP_@@PEBU1@@Z; FwAuthorizedAppResolveConflict(ICF_AUTHORIZED_APP_ *,ICF_AUTHORIZED_APP_ const *)
0x18002b773  test    eax, eax
0x18002b775  jz      short loc_18002B78E
0x18002b777  mov     r9d, esi
0x18002b77a  lea     rdx, FwIcfAuthorizedAppDestroy
0x18002b781  mov     r8, rdi
0x18002b784  mov     rcx, r14
0x18002b787  call    FwArrayErase
0x18002b78c  jmp     short loc_18002B790
0x18002b78e  inc     esi
0x18002b790  cmp     esi, [rdi]
0x18002b792  jb      short loc_18002B748
0x18002b794  add     rsp, 28h
0x18002b798  pop     r14
0x18002b79a  pop     rdi
0x18002b79b  pop     rsi
0x18002b79c  pop     rbx
0x18002b79d  retn
```
