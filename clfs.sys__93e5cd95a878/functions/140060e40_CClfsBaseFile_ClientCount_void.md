# CClfsBaseFile::ClientCount(void)

- ea: `0x140060e40`
- end: `0x140060ec7`
- name: `?ClientCount@CClfsBaseFile@@QEAAEXZ`
- size: `135`
- prototype: `unsigned __int8 __fastcall(CClfsBaseFile *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140044bf0`
- `0x140045e80`
- `0x140060c54`
- `0x140063c24`

## callees

- `0x140060e40`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140060eab`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140060eab`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140060e56`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140060e56`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::ClientCount(PERESOURCE *this)
{
  unsigned __int8 v2; // di
  PERESOURCE v3; // rcx
  ERESOURCE_THREAD OwnerThread; // rdx
  unsigned int v5; // eax
  unsigned int TableSize; // ecx
  ERESOURCE_THREAD v7; // rcx

  v2 = 0;
  ExAcquireResourceSharedLite(this[4], 1u);
  if ( *((_WORD *)this + 20) )
  {
    v3 = this[6];
    OwnerThread = v3->OwnerEntry.OwnerThread;
    if ( OwnerThread )
    {
      v5 = *(_DWORD *)(OwnerThread + 40);
      TableSize = v3->OwnerEntry.TableSize;
      if ( v5 < TableSize && v5 >= 0x70 && TableSize - v5 >= 0x1338 )
      {
        v7 = OwnerThread + v5;
        if ( v7 )
          v2 = *(_BYTE *)(v7 + 4916);
      }
    }
  }
  ExReleaseResourceForThreadLite(this[4], (ERESOURCE_THREAD)KeGetCurrentThread());
  return v2;
}

```

## disassembly

```asm
0x140060e40  mov     [rsp+arg_0], rbx
0x140060e45  push    rdi
0x140060e46  sub     rsp, 20h
0x140060e4a  mov     rbx, rcx
0x140060e4d  mov     dl, 1; Wait
0x140060e4f  mov     rcx, [rcx+20h]; Resource
0x140060e53  xor     dil, dil
0x140060e56  call    cs:__imp_ExAcquireResourceSharedLite
0x140060e5d  nop     dword ptr [rax+rax+00h]
0x140060e62  xor     eax, eax
0x140060e64  cmp     ax, [rbx+28h]
0x140060e68  jz      short loc_140060E9E
0x140060e6a  mov     rcx, [rbx+30h]
0x140060e6e  mov     rdx, [rcx+30h]
0x140060e72  test    rdx, rdx
0x140060e75  jz      short loc_140060E9E
0x140060e77  mov     eax, [rdx+28h]
0x140060e7a  mov     ecx, [rcx+38h]
0x140060e7d  cmp     eax, ecx
0x140060e7f  jnb     short loc_140060E9E
0x140060e81  cmp     eax, 70h ; 'p'
0x140060e84  jb      short loc_140060E9E
0x140060e86  sub     ecx, eax
0x140060e88  cmp     ecx, 1338h
0x140060e8e  jb      short loc_140060E9E
0x140060e90  mov     ecx, eax
0x140060e92  add     rcx, rdx
0x140060e95  jz      short loc_140060E9E
0x140060e97  movzx   edi, byte ptr [rcx+1334h]
0x140060e9e  mov     rdx, gs:188h; ResourceThreadId
0x140060ea7  mov     rcx, [rbx+20h]; Resource
0x140060eab  call    cs:__imp_ExReleaseResourceForThreadLite
0x140060eb2  nop     dword ptr [rax+rax+00h]
0x140060eb7  mov     rbx, [rsp+28h+arg_0]
0x140060ebc  movzx   eax, dil
0x140060ec0  add     rsp, 20h
0x140060ec4  pop     rdi
0x140060ec5  retn
```
