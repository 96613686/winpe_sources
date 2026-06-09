# HvSocketProviderDestructor

- ea: `0x14000a500`
- end: `0x14000a5c3`
- name: `HvSocketProviderDestructor`
- size: `195`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000a500`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a52c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a53f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a552`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a565`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a578`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a58b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a52c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a53f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a552`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a565`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a578`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000a58b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a5a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a5a5`
- `NETIO!NetioShutdownWorkQueue` at `0x14000a519`
- `NETIO!NetioShutdownWorkQueue` at `0x14000a519`

## pseudocode

```c
void __fastcall HvSocketProviderDestructor(__int64 a1)
{
  void *v2; // rcx

  if ( *(_BYTE *)(a1 + 1008) )
    NetioShutdownWorkQueue(a1 + 960);
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 192));
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 320));
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 448));
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 576));
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 704));
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 832));
  v2 = *(void **)(a1 + 1448);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  VmbusProviderContext = 0;
}

```

## disassembly

```asm
0x14000a500  push    rbx
0x14000a502  sub     rsp, 20h
0x14000a506  cmp     byte ptr [rcx+3F0h], 0
0x14000a50d  mov     rbx, rcx
0x14000a510  jz      short loc_14000A525
0x14000a512  add     rcx, 3C0h
0x14000a519  call    cs:__imp_NetioShutdownWorkQueue
0x14000a520  nop     dword ptr [rax+rax+00h]
0x14000a525  lea     rcx, [rbx+0C0h]; Lookaside
0x14000a52c  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000a533  nop     dword ptr [rax+rax+00h]
0x14000a538  lea     rcx, [rbx+140h]; Lookaside
0x14000a53f  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000a546  nop     dword ptr [rax+rax+00h]
0x14000a54b  lea     rcx, [rbx+1C0h]; Lookaside
0x14000a552  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000a559  nop     dword ptr [rax+rax+00h]
0x14000a55e  lea     rcx, [rbx+240h]; Lookaside
0x14000a565  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000a56c  nop     dword ptr [rax+rax+00h]
0x14000a571  lea     rcx, [rbx+2C0h]; Lookaside
0x14000a578  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000a57f  nop     dword ptr [rax+rax+00h]
0x14000a584  lea     rcx, [rbx+340h]; Lookaside
0x14000a58b  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000a592  nop     dword ptr [rax+rax+00h]
0x14000a597  mov     rcx, [rbx+5A8h]; P
0x14000a59e  test    rcx, rcx
0x14000a5a1  jz      short loc_14000A5B1
0x14000a5a3  xor     edx, edx; Tag
0x14000a5a5  call    cs:__imp_ExFreePoolWithTag
0x14000a5ac  nop     dword ptr [rax+rax+00h]
0x14000a5b1  mov     cs:VmbusProviderContext, 0
0x14000a5bc  add     rsp, 20h
0x14000a5c0  pop     rbx
0x14000a5c1  retn
```
