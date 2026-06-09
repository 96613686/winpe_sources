# CClfsBaseFile::GetUsn(void)

- ea: `0x1400677b8`
- end: `0x14006784b`
- name: `?GetUsn@CClfsBaseFile@@QEAAEXZ`
- size: `147`
- prototype: `unsigned __int8 __fastcall(CClfsBaseFile *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140005f1c`
- `0x14000d004`
- `0x14000e254`
- `0x140044450`
- `0x140067608`
- `0x140076e00`

## callees

- `0x14000b6b0`
- `0x1400677b8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140067830`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140067830`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400677d3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400677d3`

## pseudocode

```c
char __fastcall CClfsBaseFile::GetUsn(PERESOURCE *this)
{
  char v2; // di
  __int64 v3; // rax
  PERESOURCE v4; // rcx
  ERESOURCE_THREAD OwnerThread; // rdx
  __int64 v6; // rax
  unsigned int TableSize; // ecx

  v2 = 0;
  ExAcquireResourceSharedLite(this[4], 1u);
  v3 = 0;
  if ( *((_WORD *)this + 20) )
  {
    v4 = this[6];
    OwnerThread = v4->OwnerEntry.OwnerThread;
    if ( OwnerThread )
    {
      v6 = *(unsigned int *)(OwnerThread + 40);
      TableSize = v4->OwnerEntry.TableSize;
      if ( (unsigned int)v6 < TableSize && (unsigned int)v6 >= 0x70 && TableSize - (unsigned int)v6 >= 0x1338 )
        v3 = OwnerThread + v6;
      else
        v3 = 0;
    }
  }
  if ( v3 )
    v2 = *(_BYTE *)(v3 + 4915);
  ExReleaseResourceForThreadLite(this[4], (ERESOURCE_THREAD)KeGetCurrentThread());
  return v2;
}

```

## disassembly

```asm
0x1400677b8  mov     [rsp+arg_8], rbx
0x1400677bd  mov     [rsp+arg_0], rcx
0x1400677c2  push    rdi
0x1400677c3  sub     rsp, 20h
0x1400677c7  mov     rbx, rcx
0x1400677ca  xor     dil, dil
0x1400677cd  mov     dl, 1; Wait
0x1400677cf  mov     rcx, [rcx+20h]; Resource
0x1400677d3  call    cs:__imp_ExAcquireResourceSharedLite
0x1400677da  nop     dword ptr [rax+rax+00h]
0x1400677df  nop
0x1400677e0  xor     eax, eax
0x1400677e2  cmp     ax, [rbx+28h]
0x1400677e6  jz      short loc_140067810
0x1400677e8  mov     rcx, [rbx+30h]
0x1400677ec  mov     rdx, [rcx+30h]
0x1400677f0  test    rdx, rdx
0x1400677f3  jz      short loc_140067810
0x1400677f5  mov     eax, [rdx+28h]
0x1400677f8  mov     ecx, [rcx+38h]
0x1400677fb  cmp     eax, ecx
0x1400677fd  jnb     short loc_14006780E
0x1400677ff  cmp     eax, 70h ; 'p'
0x140067802  jb      short loc_14006780E
0x140067804  sub     ecx, eax
0x140067806  cmp     ecx, 1338h
0x14006780c  jnb     short loc_14006781E
0x14006780e  xor     eax, eax
0x140067810  test    rax, rax
0x140067813  jz      short loc_140067823
0x140067815  mov     dil, [rax+1333h]
0x14006781c  jmp     short loc_140067823
0x14006781e  add     rax, rdx
0x140067821  jmp     short loc_140067810
0x140067823  mov     rdx, gs:188h; ResourceThreadId
0x14006782c  mov     rcx, [rbx+20h]; Resource
0x140067830  call    cs:__imp_ExReleaseResourceForThreadLite
0x140067837  nop     dword ptr [rax+rax+00h]
0x14006783c  mov     al, dil
0x14006783f  mov     rbx, [rsp+28h+arg_8]
0x140067844  add     rsp, 20h
0x140067848  pop     rdi
0x140067849  retn
0x14007aed7  push    rbp
0x14007aed9  sub     rsp, 20h
0x14007aedd  mov     rbp, rdx
0x14007aee0  mov     rcx, [rbp+30h]; this
0x14007aee4  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14007aee9  nop
0x14007aeea  add     rsp, 20h
0x14007aeee  pop     rbp
0x14007aeef  retn
```
