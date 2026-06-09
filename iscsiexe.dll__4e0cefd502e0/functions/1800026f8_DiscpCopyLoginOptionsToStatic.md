# DiscpCopyLoginOptionsToStatic

- ea: `0x1800026f8`
- end: `0x180002782`
- name: `DiscpCopyLoginOptionsToStatic`
- size: `138`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001df4`
- `0x180002474`

## callees

- `0x1800026f8`
- `0x18001d38c`

## pseudocode

```c
void *__fastcall DiscpCopyLoginOptionsToStatic(__int64 a1, __int64 a2)
{
  const void *v4; // rdx
  void *result; // rax
  unsigned int v6; // ebx
  const void *v7; // rdx

  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(a2 + 32);
  v4 = *(const void **)(a2 + 48);
  if ( v4 )
  {
    result = memcpy_0((void *)(a1 + 52), v4, *(unsigned int *)(a2 + 36));
    *(_DWORD *)(a1 + 44) = 52;
    v6 = *(_DWORD *)(a2 + 36) + 52;
  }
  else
  {
    v6 = 52;
    *(_DWORD *)(a1 + 44) = 0;
  }
  v7 = *(const void **)(a2 + 56);
  if ( v7 )
    result = memcpy_0((void *)(a1 + v6), v7, *(unsigned int *)(a2 + 40));
  else
    v6 = 0;
  *(_DWORD *)(a1 + 48) = v6;
  return result;
}

```

## disassembly

```asm
0x1800026f8  mov     [rsp+arg_0], rbx
0x1800026fd  mov     [rsp+arg_8], rsi
0x180002702  push    rdi
0x180002703  sub     rsp, 20h
0x180002707  movups  xmm0, xmmword ptr [rdx]
0x18000270a  mov     rsi, rdx
0x18000270d  mov     rdi, rcx
0x180002710  movups  xmmword ptr [rcx], xmm0
0x180002713  movups  xmm1, xmmword ptr [rdx+10h]
0x180002717  movups  xmmword ptr [rcx+10h], xmm1
0x18000271b  movups  xmm0, xmmword ptr [rdx+20h]
0x18000271f  movups  xmmword ptr [rcx+20h], xmm0
0x180002723  mov     rdx, [rdx+30h]; Src
0x180002727  test    rdx, rdx
0x18000272a  jz      short loc_180002748
0x18000272c  mov     r8d, [rsi+24h]; Size
0x180002730  add     rcx, 34h ; '4'; void *
0x180002734  call    memcpy_0
0x180002739  mov     dword ptr [rdi+2Ch], 34h ; '4'
0x180002740  mov     ebx, [rsi+24h]
0x180002743  add     ebx, 34h ; '4'
0x180002746  jmp     short loc_180002754
0x180002748  mov     ebx, 34h ; '4'
0x18000274d  mov     dword ptr [rcx+2Ch], 0
0x180002754  mov     rdx, [rsi+38h]; Src
0x180002758  test    rdx, rdx
0x18000275b  jz      short loc_18000276D
0x18000275d  mov     r8d, [rsi+28h]; Size
0x180002761  mov     ecx, ebx
0x180002763  add     rcx, rdi; void *
0x180002766  call    memcpy_0
0x18000276b  jmp     short loc_18000276F
0x18000276d  xor     ebx, ebx
0x18000276f  mov     [rdi+30h], ebx
0x180002772  mov     rbx, [rsp+28h+arg_0]
0x180002777  mov     rsi, [rsp+28h+arg_8]
0x18000277c  add     rsp, 20h
0x180002780  pop     rdi
0x180002781  retn
```
