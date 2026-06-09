# NcaRpcAPIsShutdownSecurityMode(ulong)

- ea: `0x18001b010`
- end: `0x18001b057`
- name: `?NcaRpcAPIsShutdownSecurityMode@@YAXK@Z`
- size: `71`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b2b0`

## callees

- `0x18001b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b036`

## pseudocode

```c
void __fastcall NcaRpcAPIsShutdownSecurityMode(unsigned int a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rdi
  void *v3; // rcx

  v1 = 0;
  v2 = &qword_1800295D8[3 * a1];
  do
  {
    v3 = (void *)v2[v1];
    if ( v3 )
      LocalFree(v3);
    ++v1;
  }
  while ( v1 != 3 );
}

```

## disassembly

```asm
0x18001b010  mov     [rsp+arg_0], rbx
0x18001b015  push    rdi
0x18001b016  sub     rsp, 20h
0x18001b01a  mov     eax, ecx
0x18001b01c  xor     ebx, ebx
0x18001b01e  lea     rcx, [rax+rax*2]
0x18001b022  lea     rax, qword_1800295D8
0x18001b029  lea     rdi, [rax+rcx*8]
0x18001b02d  mov     rcx, [rdi+rbx*8]; hMem
0x18001b031  test    rcx, rcx
0x18001b034  jz      short loc_18001B042
0x18001b036  call    cs:__imp_LocalFree
0x18001b03d  nop     dword ptr [rax+rax+00h]
0x18001b042  inc     rbx
0x18001b045  cmp     rbx, 3
0x18001b049  jnz     short loc_18001B02D
0x18001b04b  mov     rbx, [rsp+28h+arg_0]
0x18001b050  add     rsp, 20h
0x18001b054  pop     rdi
0x18001b055  retn
```
