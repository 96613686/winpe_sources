# CClfsBaseFile::ContainerCount(void)

- ea: `0x140062df0`
- end: `0x140062e7d`
- name: `?ContainerCount@CClfsBaseFile@@QEAAKXZ`
- size: `141`
- prototype: `unsigned int __fastcall(CClfsBaseFile *__hidden this)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x140005f1c`
- `0x140008eac`
- `0x1400092d8`
- `0x14000e254`
- `0x14000fee8`
- `0x140033ca4`
- `0x1400394e4`
- `0x140039784`
- `0x14005ed70`
- `0x14005fff0`
- `0x140060a70`
- `0x140061950`
- `0x140063dcc`
- `0x140076e00`

## callees

- `0x140062df0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140062e5f`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140062e5f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140062e0b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140062e0b`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::ContainerCount(CClfsBaseFile *this)
{
  struct _ERESOURCE *v2; // rcx
  unsigned int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // ecx
  __int64 v8; // rcx

  v2 = (struct _ERESOURCE *)*((_QWORD *)this + 4);
  if ( !v2 )
    return 0;
  v3 = 0;
  ExAcquireResourceSharedLite(v2, 1u);
  if ( *((_WORD *)this + 20) )
  {
    v4 = *((_QWORD *)this + 6);
    v5 = *(_QWORD *)(v4 + 48);
    if ( v5 )
    {
      v6 = *(_DWORD *)(v5 + 40);
      v7 = *(_DWORD *)(v4 + 56);
      if ( v6 < v7 && v6 >= 0x70 && v7 - v6 >= 0x1338 )
      {
        v8 = v5 + v6;
        if ( v8 )
          v3 = *(_DWORD *)(v8 + 300);
      }
    }
  }
  ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 4), (ERESOURCE_THREAD)KeGetCurrentThread());
  return v3;
}

```

## disassembly

```asm
0x140062df0  push    rbx
0x140062df2  sub     rsp, 20h
0x140062df6  mov     rbx, rcx
0x140062df9  mov     rcx, [rcx+20h]; Resource
0x140062dfd  test    rcx, rcx
0x140062e00  jz      short loc_140062E79
0x140062e02  mov     [rsp+28h+arg_0], rdi
0x140062e07  mov     dl, 1; Wait
0x140062e09  xor     edi, edi
0x140062e0b  call    cs:__imp_ExAcquireResourceSharedLite
0x140062e12  nop     dword ptr [rax+rax+00h]
0x140062e17  xor     eax, eax
0x140062e19  cmp     ax, [rbx+28h]
0x140062e1d  jz      short loc_140062E52
0x140062e1f  mov     rcx, [rbx+30h]
0x140062e23  mov     rdx, [rcx+30h]
0x140062e27  test    rdx, rdx
0x140062e2a  jz      short loc_140062E52
0x140062e2c  mov     eax, [rdx+28h]
0x140062e2f  mov     ecx, [rcx+38h]
0x140062e32  cmp     eax, ecx
0x140062e34  jnb     short loc_140062E52
0x140062e36  cmp     eax, 70h ; 'p'
0x140062e39  jb      short loc_140062E52
0x140062e3b  sub     ecx, eax
0x140062e3d  cmp     ecx, 1338h
0x140062e43  jb      short loc_140062E52
0x140062e45  mov     ecx, eax
0x140062e47  add     rcx, rdx
0x140062e4a  jz      short loc_140062E52
0x140062e4c  mov     edi, [rcx+12Ch]
0x140062e52  mov     rdx, gs:188h; ResourceThreadId
0x140062e5b  mov     rcx, [rbx+20h]; Resource
0x140062e5f  call    cs:__imp_ExReleaseResourceForThreadLite
0x140062e66  nop     dword ptr [rax+rax+00h]
0x140062e6b  mov     eax, edi
0x140062e6d  mov     rdi, [rsp+28h+arg_0]
0x140062e72  add     rsp, 20h
0x140062e76  pop     rbx
0x140062e77  retn
0x140062e79  xor     eax, eax
0x140062e7b  jmp     short loc_140062E72
```
