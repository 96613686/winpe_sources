# CdpFreeConnection

- ea: `0x14000bd90`
- end: `0x14000be67`
- name: `CdpFreeConnection`
- size: `215`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b3a0`
- `0x14000b820`
- `0x14000c0f0`

## callees

- `0x14000b020`
- `0x14000bd90`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000be37`
- `ntoskrnl!ObfDereferenceObject` at `0x14000be37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000be48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000be48`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bdbb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bdbb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000be19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000be19`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000bdab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000bdab`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bdd4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bdd4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000be08`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000be08`

## pseudocode

```c
void __fastcall CdpFreeConnection(char *P)
{
  char v2; // di
  char **v3; // rdx
  PVOID *v4; // rcx
  void *v5; // rcx

  if ( *((_QWORD *)P + 3) )
  {
    v2 = 0;
    if ( KeGetCurrentIrql() <= 1u )
    {
      KeEnterCriticalRegion();
      v2 = 1;
    }
    ExAcquirePushLockExclusiveEx(*((_QWORD *)P + 3) + 40LL, 0);
    v3 = (char **)*((_QWORD *)P + 1);
    if ( v3[1] != P + 8 || (v4 = (PVOID *)*((_QWORD *)P + 2), *v4 != P + 8) )
      __fastfail(3u);
    *v4 = v3;
    v3[1] = (char *)v4;
    ExReleasePushLockExclusiveEx(*((_QWORD *)P + 3) + 40LL, 0);
    if ( v2 )
      KeLeaveCriticalRegion();
    CdDereferenceServer(*((char **)P + 3));
  }
  v5 = (void *)*((_QWORD *)P + 4);
  if ( v5 )
    ObfDereferenceObject(v5);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000bd90  mov     [rsp+arg_0], rbx
0x14000bd95  push    rdi
0x14000bd96  sub     rsp, 20h
0x14000bd9a  cmp     qword ptr [rcx+18h], 0
0x14000bd9f  mov     rbx, rcx
0x14000bda2  jz      loc_14000BE2E
0x14000bda8  xor     dil, dil
0x14000bdab  call    cs:__imp_KeGetCurrentIrql
0x14000bdb2  nop     dword ptr [rax+rax+00h]
0x14000bdb7  cmp     al, 1
0x14000bdb9  ja      short loc_14000BDCA
0x14000bdbb  call    cs:__imp_KeEnterCriticalRegion
0x14000bdc2  nop     dword ptr [rax+rax+00h]
0x14000bdc7  mov     dil, 1
0x14000bdca  mov     rcx, [rbx+18h]
0x14000bdce  xor     edx, edx
0x14000bdd0  add     rcx, 28h ; '('
0x14000bdd4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000bddb  nop     dword ptr [rax+rax+00h]
0x14000bde0  mov     rdx, [rbx+8]
0x14000bde4  lea     rax, [rbx+8]
0x14000bde8  cmp     [rdx+8], rax
0x14000bdec  jnz     short loc_14000BE60
0x14000bdee  mov     rcx, [rax+8]
0x14000bdf2  cmp     [rcx], rax
0x14000bdf5  jnz     short loc_14000BE60
0x14000bdf7  mov     [rcx], rdx
0x14000bdfa  mov     [rdx+8], rcx
0x14000bdfe  xor     edx, edx
0x14000be00  mov     rcx, [rbx+18h]
0x14000be04  add     rcx, 28h ; '('
0x14000be08  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000be0f  nop     dword ptr [rax+rax+00h]
0x14000be14  test    dil, dil
0x14000be17  jz      short loc_14000BE25
0x14000be19  call    cs:__imp_KeLeaveCriticalRegion
0x14000be20  nop     dword ptr [rax+rax+00h]
0x14000be25  mov     rcx, [rbx+18h]; P
0x14000be29  call    CdDereferenceServer
0x14000be2e  mov     rcx, [rbx+20h]; Object
0x14000be32  test    rcx, rcx
0x14000be35  jz      short loc_14000BE43
0x14000be37  call    cs:__imp_ObfDereferenceObject
0x14000be3e  nop     dword ptr [rax+rax+00h]
0x14000be43  xor     edx, edx; Tag
0x14000be45  mov     rcx, rbx; P
0x14000be48  call    cs:__imp_ExFreePoolWithTag
0x14000be4f  nop     dword ptr [rax+rax+00h]
0x14000be54  mov     rbx, [rsp+28h+arg_0]
0x14000be59  add     rsp, 20h
0x14000be5d  pop     rdi
0x14000be5e  retn
0x14000be60  mov     ecx, 3
0x14000be65  int     29h; Win8: RtlFailFast(ecx)
```
