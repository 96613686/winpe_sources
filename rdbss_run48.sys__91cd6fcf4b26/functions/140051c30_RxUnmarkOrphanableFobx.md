# RxUnmarkOrphanableFobx

- ea: `0x140051c30`
- end: `0x140051c73`
- name: `RxUnmarkOrphanableFobx`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140051c30`

## import_xrefs

- `ntoskrnl!IoUpdateShareAccess` at `0x140051c61`
- `ntoskrnl!IoUpdateShareAccess` at `0x140051c61`

## pseudocode

```c
void __fastcall RxUnmarkOrphanableFobx(__int64 a1)
{
  int v1; // r8d
  __int64 v2; // rax
  __int64 v3; // rdx

  v1 = *(_DWORD *)(a1 + 72);
  if ( (v1 & 0x40000000) != 0 )
  {
    v2 = *(_QWORD *)(a1 + 32);
    v3 = *(_QWORD *)(v2 + 32);
    *(_DWORD *)(a1 + 72) = v1 & 0xBFFFFFFF;
    --*(_DWORD *)(v2 + 96);
    --*(_DWORD *)(v2 + 100);
    IoUpdateShareAccess(*(PFILE_OBJECT *)(a1 + 48), (PSHARE_ACCESS)(v3 + 424));
  }
}

```

## disassembly

```asm
0x140051c30  sub     rsp, 28h
0x140051c34  mov     r8d, [rcx+48h]
0x140051c38  bt      r8d, 1Eh
0x140051c3d  jnb     short loc_140051C6D
0x140051c3f  mov     rax, [rcx+20h]
0x140051c43  btr     r8d, 1Eh
0x140051c48  mov     rdx, [rax+20h]
0x140051c4c  mov     [rcx+48h], r8d
0x140051c50  add     rdx, 1A8h; ShareAccess
0x140051c57  dec     dword ptr [rax+60h]
0x140051c5a  dec     dword ptr [rax+64h]
0x140051c5d  mov     rcx, [rcx+30h]; FileObject
0x140051c61  call    cs:__imp_IoUpdateShareAccess
0x140051c68  nop     dword ptr [rax+rax+00h]
0x140051c6d  add     rsp, 28h
0x140051c71  retn
```
