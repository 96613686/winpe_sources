# NdisWanFreeRecvDesc

- ea: `0x140005750`
- end: `0x1400057d1`
- name: `NdisWanFreeRecvDesc`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `15`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140003620`
- `0x140004be0`
- `0x140005568`
- `0x140007710`
- `0x140008b48`
- `0x14000bfcc`
- `0x140011320`
- `0x140011540`
- `0x140025070`
- `0x140026970`
- `0x140029b70`
- `0x140029e70`
- `0x14002c9e0`
- `0x14002d324`
- `0x14002d7dc`

## callees

- `0x140005750`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400057c3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400057c3`
- `NDIS!NdisReturnNetBufferLists` at `0x140005796`
- `NDIS!NdisReturnNetBufferLists` at `0x140005796`
- `NDIS!NdisFreeNetBufferListContext` at `0x140005781`
- `NDIS!NdisFreeNetBufferListContext` at `0x140005781`
- `NDIS!NdisFreeNetBufferList` at `0x1400057ae`
- `NDIS!NdisFreeNetBufferList` at `0x1400057ae`

## pseudocode

```c
void __fastcall NdisWanFreeRecvDesc(__int64 a1)
{
  void *v1; // rdx
  struct _NET_BUFFER_LIST *v3; // rdi
  void *v4; // rbx

  v1 = *(void **)(a1 + 80);
  v3 = *(struct _NET_BUFFER_LIST **)(a1 + 104);
  if ( v1 )
    ExFreeToNPagedLookasideList(&RecvHeaderLookaside, v1);
  if ( (*(_DWORD *)(a1 + 48) & 1) != 0 )
  {
    NdisFreeNetBufferList(v3);
  }
  else
  {
    v4 = *(void **)(*(_QWORD *)(a1 + 32) + 56LL);
    NdisFreeNetBufferListContext(v3, 0x80u);
    NdisReturnNetBufferLists(v4, v3, 0);
  }
}

```

## disassembly

```asm
0x140005750  mov     [rsp+arg_0], rbx
0x140005755  push    rdi
0x140005756  sub     rsp, 20h
0x14000575a  mov     rdx, [rcx+50h]; Entry
0x14000575e  mov     rbx, rcx
0x140005761  mov     rdi, [rcx+68h]
0x140005765  test    rdx, rdx
0x140005768  jnz     short loc_1400057BC
0x14000576a  mov     eax, [rbx+30h]
0x14000576d  mov     rcx, rdi; NetBufferList
0x140005770  test    al, 1
0x140005772  jnz     short loc_1400057AE
0x140005774  mov     rax, [rbx+20h]
0x140005778  mov     edx, 80h; ContextSize
0x14000577d  mov     rbx, [rax+38h]
0x140005781  call    cs:__imp_NdisFreeNetBufferListContext
0x140005788  nop     dword ptr [rax+rax+00h]
0x14000578d  xor     r8d, r8d; ReturnFlags
0x140005790  mov     rdx, rdi; NetBufferLists
0x140005793  mov     rcx, rbx; NdisBindingHandle
0x140005796  call    cs:__imp_NdisReturnNetBufferLists
0x14000579d  nop     dword ptr [rax+rax+00h]
0x1400057a2  mov     rbx, [rsp+28h+arg_0]
0x1400057a7  add     rsp, 20h
0x1400057ab  pop     rdi
0x1400057ac  retn
0x1400057ae  call    cs:__imp_NdisFreeNetBufferList
0x1400057b5  nop     dword ptr [rax+rax+00h]
0x1400057ba  jmp     short loc_1400057A2
0x1400057bc  lea     rcx, RecvHeaderLookaside; Lookaside
0x1400057c3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400057ca  nop     dword ptr [rax+rax+00h]
0x1400057cf  jmp     short loc_14000576A
```
