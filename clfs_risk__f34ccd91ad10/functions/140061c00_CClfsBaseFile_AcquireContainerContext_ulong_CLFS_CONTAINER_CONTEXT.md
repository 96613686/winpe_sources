# CClfsBaseFile::AcquireContainerContext(ulong,_CLFS_CONTAINER_CONTEXT * *)

- ea: `0x140061c00`
- end: `0x140061cf9`
- name: `?AcquireContainerContext@CClfsBaseFile@@QEAAJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(CClfsBaseFile *__hidden this, unsigned int, struct _CLFS_CONTAINER_CONTEXT **)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

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

- `0x140061c00`
- `0x140061e00`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140061c28`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140061c28`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140061cdc`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007a5e6`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140061cdc`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007a5e6`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::AcquireContainerContext(
        PERESOURCE *this,
        unsigned int a2,
        struct _CLFS_CONTAINER_CONTEXT **a3)
{
  __int64 v4; // rdi
  BOOLEAN v6; // si
  PERESOURCE v7; // rax
  ERESOURCE_THREAD OwnerThread; // rdx
  __int64 v9; // rcx
  unsigned int TableSize; // r8d
  __int64 v11; // rcx
  int v12; // edx
  int Symbol; // edi

  v4 = a2;
  v6 = ExAcquireResourceExclusiveLite(this[4], 1u);
  if ( (unsigned int)v4 >= 0x400 )
  {
    Symbol = -1072037875;
  }
  else
  {
    if ( *((_WORD *)this + 20)
      && (v7 = this[6], (OwnerThread = v7->OwnerEntry.OwnerThread) != 0)
      && (v9 = *(unsigned int *)(OwnerThread + 40), TableSize = v7->OwnerEntry.TableSize, (unsigned int)v9 < TableSize)
      && (unsigned int)v9 >= 0x70
      && TableSize - (unsigned int)v9 >= 0x1338 )
    {
      v11 = OwnerThread + v9;
    }
    else
    {
      v11 = 0;
    }
    if ( v11 )
    {
      v12 = *(_DWORD *)(v11 + 4 * v4 + 808);
      if ( v12 )
        Symbol = CClfsBaseFile::GetSymbol((CClfsBaseFile *)this, v12, v4, a3);
      else
        Symbol = -1073741816;
    }
    else
    {
      Symbol = -1072037875;
    }
  }
  if ( Symbol < 0 && v6 )
    ExReleaseResourceForThreadLite(this[4], (ERESOURCE_THREAD)KeGetCurrentThread());
  return (unsigned int)Symbol;
}

```

## disassembly

```asm
0x140061c00  mov     [rsp+arg_8], rbx
0x140061c05  mov     [rsp+arg_0], rcx
0x140061c0a  push    rsi
0x140061c0b  push    rdi
0x140061c0c  push    r14
0x140061c0e  sub     rsp, 30h
0x140061c12  mov     r14, r8
0x140061c15  mov     edi, edx
0x140061c17  mov     rbx, rcx
0x140061c1a  mov     [rsp+48h+var_28], 0
0x140061c22  mov     dl, 1; Wait
0x140061c24  mov     rcx, [rcx+20h]; Resource
0x140061c28  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140061c2f  nop     dword ptr [rax+rax+00h]
0x140061c34  movzx   esi, al
0x140061c37  mov     [rsp+48h+arg_18], al
0x140061c3b  cmp     edi, 400h
0x140061c41  jnb     short loc_140061CB6
0x140061c43  xor     eax, eax
0x140061c45  cmp     ax, [rbx+28h]
0x140061c49  jz      short loc_140061C75
0x140061c4b  mov     rax, [rbx+30h]
0x140061c4f  mov     rdx, [rax+30h]
0x140061c53  test    rdx, rdx
0x140061c56  jz      short loc_140061C75
0x140061c58  mov     ecx, [rdx+28h]
0x140061c5b  mov     r8d, [rax+38h]
0x140061c5f  cmp     ecx, r8d
0x140061c62  jnb     short loc_140061C75
0x140061c64  cmp     ecx, 70h ; 'p'
0x140061c67  jb      short loc_140061C75
0x140061c69  sub     r8d, ecx
0x140061c6c  cmp     r8d, 1338h
0x140061c73  jnb     short loc_140061CC1
0x140061c75  xor     ecx, ecx
0x140061c77  test    rcx, rcx
0x140061c7a  jz      short loc_140061C95
0x140061c7c  mov     rax, rdi
0x140061c7f  mov     edx, [rcx+rdi*4+328h]; int
0x140061c86  test    edx, edx
0x140061c88  jnz     short loc_140061CA0
0x140061c8a  mov     edi, 0C0000008h
0x140061c8f  mov     [rsp+48h+var_28], edi
0x140061c93  jmp     short loc_140061CC6
0x140061c95  mov     edi, 0C01A000Dh
0x140061c9a  mov     [rsp+48h+var_28], edi
0x140061c9e  jmp     short loc_140061CC6
0x140061ca0  mov     r9, r14; struct _CLFS_CONTAINER_CONTEXT **
0x140061ca3  mov     r8d, edi; unsigned int
0x140061ca6  mov     rcx, rbx; this
0x140061ca9  call    ?GetSymbol@CClfsBaseFile@@QEAAJJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::GetSymbol(long,ulong,_CLFS_CONTAINER_CONTEXT * *)
0x140061cae  mov     edi, eax
0x140061cb0  mov     [rsp+48h+var_28], eax
0x140061cb4  jmp     short loc_140061CC6
0x140061cb6  mov     edi, 0C01A000Dh
0x140061cbb  mov     [rsp+48h+var_28], edi
0x140061cbf  jmp     short loc_140061CC6
0x140061cc1  add     rcx, rdx
0x140061cc4  jmp     short loc_140061C77
0x140061cc6  test    edi, edi
0x140061cc8  jns     short loc_140061CE8
0x140061cca  test    sil, sil
0x140061ccd  jz      short loc_140061CE8
0x140061ccf  mov     rdx, gs:188h; ResourceThreadId
0x140061cd8  mov     rcx, [rbx+20h]; Resource
0x140061cdc  call    cs:__imp_ExReleaseResourceForThreadLite
0x140061ce3  nop     dword ptr [rax+rax+00h]
0x140061ce8  mov     eax, edi
0x140061cea  mov     rbx, [rsp+48h+arg_8]
0x140061cef  add     rsp, 30h
0x140061cf3  pop     r14
0x140061cf5  pop     rdi
0x140061cf6  pop     rsi
0x140061cf7  retn
0x14007a5c0  push    rbp
0x14007a5c2  sub     rsp, 20h
0x14007a5c6  mov     rbp, rdx
0x14007a5c9  cmp     dword ptr [rbp+20h], 0
0x14007a5cd  jge     short loc_14007A5F3
0x14007a5cf  cmp     byte ptr [rbp+68h], 0
0x14007a5d3  jz      short loc_14007A5F3
0x14007a5d5  mov     rdx, gs:188h; ResourceThreadId
0x14007a5de  mov     rcx, [rbp+50h]
0x14007a5e2  mov     rcx, [rcx+20h]; Resource
0x14007a5e6  call    cs:__imp_ExReleaseResourceForThreadLite
0x14007a5ed  nop     dword ptr [rax+rax+00h]
0x14007a5f2  nop
0x14007a5f3  add     rsp, 20h
0x14007a5f7  pop     rbp
0x14007a5f8  retn
```
