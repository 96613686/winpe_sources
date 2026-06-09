# CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)

- ea: `0x140061d00`
- end: `0x140061dec`
- name: `?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(CClfsBaseFile *__hidden this, struct _CLFS_CONTAINER_CONTEXT **)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400035a8`
- `0x140007034`
- `0x14000dcd8`
- `0x14000dfa4`
- `0x14000e254`
- `0x140033ca4`
- `0x1400346c4`
- `0x140038fac`
- `0x140040444`
- `0x140044450`
- `0x1400456a0`
- `0x140046060`
- `0x14005fff0`
- `0x140060efc`
- `0x140061f34`

## callees

- `0x140061d00`
- `0x140061e00`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140061dbe`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140061dbe`
- `ntoskrnl!RtlCompareMemory` at `0x140061d9f`
- `ntoskrnl!RtlCompareMemory` at `0x140061d9f`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::ReleaseContainerContext(CClfsBaseFile *this, struct _CLFS_CONTAINER_CONTEXT **a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rax
  unsigned int v7; // r8d
  int Symbol; // esi
  void *Source1; // [rsp+30h] [rbp+8h] BYREF

  Source1 = 0;
  if ( !*((_WORD *)this + 20) )
    return 3222929421LL;
  v4 = *((_QWORD *)this + 6);
  v5 = *(_QWORD *)(v4 + 48);
  if ( !v5 )
    return 3222929421LL;
  v6 = *(unsigned int *)(v5 + 40);
  v7 = *(_DWORD *)(v4 + 56);
  if ( (unsigned int)v6 >= v7 || (unsigned int)v6 < 0x70 || v7 - (unsigned int)v6 < 0x1338 || !(v5 + v6) )
    return 3222929421LL;
  Symbol = CClfsBaseFile::GetSymbol(
             this,
             *(_DWORD *)(v5 + v6 + 4LL * *((unsigned int *)*a2 + 4) + 808),
             *((_DWORD *)*a2 + 4),
             (struct _CLFS_CONTAINER_CONTEXT **)&Source1);
  if ( Symbol >= 0 )
  {
    if ( RtlCompareMemory(Source1, *a2, 0x30u) == 48 )
    {
      ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 4), (ERESOURCE_THREAD)KeGetCurrentThread());
      *a2 = 0;
    }
    else
    {
      return (unsigned int)-1073741816;
    }
  }
  return (unsigned int)Symbol;
}

```

## disassembly

```asm
0x140061d00  mov     [rsp+arg_10], rbx
0x140061d05  mov     [rsp+arg_18], rbp
0x140061d0a  push    rdi
0x140061d0b  sub     rsp, 20h
0x140061d0f  xor     ebp, ebp
0x140061d11  mov     rdi, rdx
0x140061d14  mov     rbx, rcx
0x140061d17  mov     [rsp+28h+Source1], rbp
0x140061d1c  cmp     bp, [rcx+28h]
0x140061d20  jz      short loc_140061D4D
0x140061d22  mov     r8, [rcx+30h]
0x140061d26  mov     r9, [r8+30h]
0x140061d2a  test    r9, r9
0x140061d2d  jz      short loc_140061D4D
0x140061d2f  mov     eax, [r9+28h]
0x140061d33  mov     r8d, [r8+38h]
0x140061d37  cmp     eax, r8d
0x140061d3a  jnb     short loc_140061D4D
0x140061d3c  cmp     eax, 70h ; 'p'
0x140061d3f  jb      short loc_140061D4D
0x140061d41  sub     r8d, eax
0x140061d44  cmp     r8d, 1338h
0x140061d4b  jnb     short loc_140061D63
0x140061d4d  mov     eax, 0C01A000Dh
0x140061d52  mov     rbx, [rsp+28h+arg_10]
0x140061d57  mov     rbp, [rsp+28h+arg_18]
0x140061d5c  add     rsp, 20h
0x140061d60  pop     rdi
0x140061d61  retn
0x140061d63  mov     r10, rax
0x140061d66  add     r10, r9
0x140061d69  jz      short loc_140061D4D
0x140061d6b  mov     rax, [rdx]
0x140061d6e  lea     r9, [rsp+28h+Source1]; struct _CLFS_CONTAINER_CONTEXT **
0x140061d73  mov     [rsp+28h+arg_8], rsi
0x140061d78  mov     edx, [rax+10h]
0x140061d7b  mov     r8d, edx; unsigned int
0x140061d7e  mov     edx, [r10+rdx*4+328h]; int
0x140061d86  call    ?GetSymbol@CClfsBaseFile@@QEAAJJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::GetSymbol(long,ulong,_CLFS_CONTAINER_CONTEXT * *)
0x140061d8b  mov     esi, eax
0x140061d8d  test    eax, eax
0x140061d8f  js      short loc_140061DCD
0x140061d91  mov     rdx, [rdi]; Source2
0x140061d94  mov     r8d, 30h ; '0'; Length
0x140061d9a  mov     rcx, [rsp+28h+Source1]; Source1
0x140061d9f  call    cs:__imp_RtlCompareMemory
0x140061da6  nop     dword ptr [rax+rax+00h]
0x140061dab  cmp     rax, 30h ; '0'
0x140061daf  jnz     short loc_140061DE5
0x140061db1  mov     rdx, gs:188h; ResourceThreadId
0x140061dba  mov     rcx, [rbx+20h]; Resource
0x140061dbe  call    cs:__imp_ExReleaseResourceForThreadLite
0x140061dc5  nop     dword ptr [rax+rax+00h]
0x140061dca  mov     [rdi], rbp
0x140061dcd  mov     rbx, [rsp+28h+arg_10]
0x140061dd2  mov     eax, esi
0x140061dd4  mov     rsi, [rsp+28h+arg_8]
0x140061dd9  mov     rbp, [rsp+28h+arg_18]
0x140061dde  add     rsp, 20h
0x140061de2  pop     rdi
0x140061de3  retn
0x140061de5  mov     esi, 0C0000008h
0x140061dea  jmp     short loc_140061DCD
```
