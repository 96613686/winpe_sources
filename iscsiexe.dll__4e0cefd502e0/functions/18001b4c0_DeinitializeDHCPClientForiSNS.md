# DeinitializeDHCPClientForiSNS

- ea: `0x18001b4c0`
- end: `0x18001b52c`
- name: `DeinitializeDHCPClientForiSNS`
- size: `108`
- prototype: `void __fastcall(_QWORD *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180009408`
- `0x18001b834`

## callees

- `0x18001b4c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b4f3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b513`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b4f3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b513`
- `WS2_32!__imp_WSACleanup` at `0x18001b519`
- `WS2_32!__imp_WSACleanup` at `0x18001b519`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b50a`

## pseudocode

```c
void __fastcall DeinitializeDHCPClientForiSNS(_QWORD *Block)
{
  _QWORD *i; // rax
  __int64 v3; // rcx
  _QWORD *v4; // rdx
  void *v5; // rcx

  if ( Block )
  {
    for ( i = (_QWORD *)*Block; i && i != Block; i = (_QWORD *)*Block )
    {
      v3 = *i;
      if ( *(_QWORD **)(*i + 8LL) != i || (v4 = (_QWORD *)i[1], (_QWORD *)*v4 != i) )
        __fastfail(3u);
      *v4 = v3;
      *(_QWORD *)(v3 + 8) = v4;
      free(i);
    }
    v5 = (void *)Block[2];
    if ( v5 )
      CloseHandle(v5);
    free(Block);
    WSACleanup();
  }
}

```

## disassembly

```asm
0x18001b4c0  test    rcx, rcx
0x18001b4c3  jz      short locret_18001B524
0x18001b4c5  push    rbx
0x18001b4c6  sub     rsp, 20h
0x18001b4ca  mov     rax, [rcx]
0x18001b4cd  mov     rbx, rcx
0x18001b4d0  jmp     short loc_18001B4FC
0x18001b4d2  cmp     rax, rbx
0x18001b4d5  jz      short loc_18001B501
0x18001b4d7  mov     rcx, [rax]
0x18001b4da  cmp     [rcx+8], rax
0x18001b4de  jnz     short loc_18001B525
0x18001b4e0  mov     rdx, [rax+8]
0x18001b4e4  cmp     [rdx], rax
0x18001b4e7  jnz     short loc_18001B525
0x18001b4e9  mov     [rdx], rcx
0x18001b4ec  mov     [rcx+8], rdx
0x18001b4f0  mov     rcx, rax; Block
0x18001b4f3  call    cs:__imp_free
0x18001b4f9  mov     rax, [rbx]
0x18001b4fc  test    rax, rax
0x18001b4ff  jnz     short loc_18001B4D2
0x18001b501  mov     rcx, [rbx+10h]; hObject
0x18001b505  test    rcx, rcx
0x18001b508  jz      short loc_18001B510
0x18001b50a  call    cs:__imp_CloseHandle
0x18001b510  mov     rcx, rbx; Block
0x18001b513  call    cs:__imp_free
0x18001b519  call    cs:__imp_WSACleanup
0x18001b51f  add     rsp, 20h
0x18001b523  pop     rbx
0x18001b524  retn
0x18001b525  mov     ecx, 3
0x18001b52a  int     29h; Win8: RtlFailFast(ecx)
```
