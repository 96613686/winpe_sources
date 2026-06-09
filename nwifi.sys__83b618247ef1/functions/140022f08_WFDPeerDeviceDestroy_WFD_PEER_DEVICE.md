# WFDPeerDeviceDestroy(_WFD_PEER_DEVICE *)

- ea: `0x140022f08`
- end: `0x140022fb5`
- name: `?WFDPeerDeviceDestroy@@YAXPEAU_WFD_PEER_DEVICE@@@Z`
- size: `173`
- prototype: `void __fastcall(struct _WFD_PEER_DEVICE *)`
- caller_count: `13`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140022dd4`
- `0x14007de4c`
- `0x14007e374`
- `0x14007f384`
- `0x14007fa04`
- `0x14008159c`
- `0x1400818d8`
- `0x140081b44`
- `0x140081e30`
- `0x140084de4`
- `0x1400859fc`
- `0x140088730`
- `0x14008afa0`

## callees

- `0x140022f08`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022f50`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022f8a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022f50`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022f8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022f61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022fa0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022f61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022fa0`

## pseudocode

```c
void __fastcall WFDPeerDeviceDestroy(struct _WFD_PEER_DEVICE *a1)
{
  __int64 v2; // rcx
  struct _WFD_PEER_DEVICE **v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = *(_QWORD *)a1;
  if ( *(struct _WFD_PEER_DEVICE **)(v2 + 8) != a1 || (v3 = (struct _WFD_PEER_DEVICE **)*((_QWORD *)a1 + 1), *v3 != a1) )
    __fastfail(3u);
  *v3 = (struct _WFD_PEER_DEVICE *)v2;
  *(_QWORD *)(v2 + 8) = v3;
  v4 = *((_QWORD *)a1 + 54);
  if ( v4 )
  {
    v5 = v4 - 16;
    if ( *(_QWORD *)v5 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v5, (PVOID)v5);
    else
      ExFreePoolWithTag((PVOID)v5, *(_DWORD *)(v5 + 8));
    *((_QWORD *)a1 + 54) = 0;
  }
  if ( *((_QWORD *)a1 - 2) )
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)a1 - 2), (char *)a1 - 16);
  else
    ExFreePoolWithTag((char *)a1 - 16, *((_DWORD *)a1 - 2));
}

```

## disassembly

```asm
0x140022f08  push    rbx
0x140022f0a  sub     rsp, 20h
0x140022f0e  mov     rbx, rcx
0x140022f11  mov     rcx, [rcx]
0x140022f14  cmp     [rcx+8], rbx
0x140022f18  jnz     loc_140022FAE
0x140022f1e  mov     rax, [rbx+8]
0x140022f22  cmp     [rax], rbx
0x140022f25  jnz     loc_140022FAE
0x140022f2b  mov     [rax], rcx
0x140022f2e  mov     [rcx+8], rax
0x140022f32  mov     rcx, [rbx+1B0h]
0x140022f39  test    rcx, rcx
0x140022f3c  jz      short loc_140022F78
0x140022f3e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140022f42  mov     rax, [rcx]
0x140022f45  test    rax, rax
0x140022f48  jz      short loc_140022F5E
0x140022f4a  mov     rdx, rcx; Entry
0x140022f4d  mov     rcx, rax; Lookaside
0x140022f50  call    cs:__imp_ExFreeToNPagedLookasideList
0x140022f57  nop     dword ptr [rax+rax+00h]
0x140022f5c  jmp     short loc_140022F6D
0x140022f5e  mov     edx, [rcx+8]; Tag
0x140022f61  call    cs:__imp_ExFreePoolWithTag
0x140022f68  nop     dword ptr [rax+rax+00h]
0x140022f6d  mov     qword ptr [rbx+1B0h], 0
0x140022f78  lea     rcx, [rbx-10h]; P
0x140022f7c  mov     rax, [rcx]
0x140022f7f  test    rax, rax
0x140022f82  jz      short loc_140022F9D
0x140022f84  mov     rdx, rcx; Entry
0x140022f87  mov     rcx, rax; Lookaside
0x140022f8a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140022f91  nop     dword ptr [rax+rax+00h]
0x140022f96  add     rsp, 20h
0x140022f9a  pop     rbx
0x140022f9b  retn
0x140022f9d  mov     edx, [rcx+8]; Tag
0x140022fa0  call    cs:__imp_ExFreePoolWithTag
0x140022fa7  nop     dword ptr [rax+rax+00h]
0x140022fac  jmp     short loc_140022F96
0x140022fae  mov     ecx, 3
0x140022fb3  int     29h; Win8: RtlFailFast(ecx)
```
