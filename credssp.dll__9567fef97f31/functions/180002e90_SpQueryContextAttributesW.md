# SpQueryContextAttributesW

- ea: `0x180002e90`
- end: `0x180002f0a`
- name: `SpQueryContextAttributesW`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e90`

## import_xrefs

- `SspiCli!QueryContextAttributesW` at `0x180002ef9`
- `SspiCli!QueryContextAttributesW` at `0x180002ef9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002ec8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002ec8`

## pseudocode

```c
SECURITY_STATUS __fastcall SpQueryContextAttributesW(__int64 a1, signed int a2, _QWORD *a3)
{
  __int64 v4; // rbx
  _OWORD *v6; // rax
  struct _SecHandle *v7; // rcx

  if ( !a1 )
    return -2146893055;
  v4 = *(_QWORD *)(a1 + 8);
  if ( a2 >= 0 )
  {
    if ( (*(_DWORD *)(v4 + 32) & 1) == 0 )
      return -2146893055;
    v7 = *(struct _SecHandle **)(a1 + 8);
    return QueryContextAttributesW(v7, a2, a3);
  }
  a2 &= ~0x80000000;
  if ( a2 )
  {
    v7 = (struct _SecHandle *)(v4 + 16);
    return QueryContextAttributesW(v7, a2, a3);
  }
  if ( (*(_DWORD *)(v4 + 32) & 4) == 0 )
    return -2146893055;
  v6 = LocalAlloc(0x40u, 0x10u);
  if ( !v6 )
    return -2146893056;
  *v6 = *(_OWORD *)(v4 + 16);
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x180002e90  mov     [rsp+arg_0], rbx
0x180002e95  push    rdi
0x180002e96  sub     rsp, 20h
0x180002e9a  mov     rdi, r8
0x180002e9d  test    rcx, rcx
0x180002ea0  jz      short loc_180002EB9
0x180002ea2  mov     rbx, [rcx+8]
0x180002ea6  test    edx, edx
0x180002ea8  jns     short loc_180002EEF
0x180002eaa  and     edx, 7FFFFFFFh
0x180002eb0  jnz     short loc_180002EE9
0x180002eb2  mov     eax, [rbx+20h]
0x180002eb5  test    al, 4
0x180002eb7  jnz     short loc_180002EC0
0x180002eb9  mov     eax, 80090301h
0x180002ebe  jmp     short loc_180002EFF
0x180002ec0  mov     edx, 10h; uBytes
0x180002ec5  lea     ecx, [rdx+30h]; uFlags
0x180002ec8  call    cs:__imp_LocalAlloc
0x180002ece  test    rax, rax
0x180002ed1  jnz     short loc_180002EDA
0x180002ed3  mov     eax, 80090300h
0x180002ed8  jmp     short loc_180002EFF
0x180002eda  movups  xmm0, xmmword ptr [rbx+10h]
0x180002ede  movdqu  xmmword ptr [rax], xmm0
0x180002ee2  mov     [rdi], rax
0x180002ee5  xor     eax, eax
0x180002ee7  jmp     short loc_180002EFF
0x180002ee9  lea     rcx, [rbx+10h]
0x180002eed  jmp     short loc_180002EF9
0x180002eef  mov     eax, [rbx+20h]
0x180002ef2  test    al, 1
0x180002ef4  jz      short loc_180002EB9
0x180002ef6  mov     rcx, rbx; phContext
0x180002ef9  call    cs:__imp_QueryContextAttributesW
0x180002eff  mov     rbx, [rsp+28h+arg_0]
0x180002f04  add     rsp, 20h
0x180002f08  pop     rdi
0x180002f09  retn
```
