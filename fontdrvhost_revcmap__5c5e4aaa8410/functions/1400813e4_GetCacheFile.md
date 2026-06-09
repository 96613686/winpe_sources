# GetCacheFile

- ea: `0x1400813e4`
- end: `0x14008145a`
- name: `GetCacheFile`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140090198`

## callees

- `0x14007e568`
- `0x140080f78`
- `0x1400813e4`

## pseudocode

```c
__int64 __fastcall GetCacheFile(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rax

  v3 = 0;
  if ( a1 )
  {
    v4 = MemoryMapFile(a1 + 32, a2, a1 + 40);
    *(_QWORD *)(a1 + 24) = v4;
    if ( v4 )
    {
      if ( *(_DWORD *)(a1 + 32) )
      {
        *(_DWORD *)(a1 + 36) = 0;
        v3 = v4;
      }
    }
  }
  if ( !v3 && a1 )
    EnhancedUnmapRW(a1 + 24, *(_QWORD *)(a1 + 40), *(unsigned int *)(a1 + 32));
  return v3;
}

```

## disassembly

```asm
0x1400813e4  mov     rax, rsp
0x1400813e7  mov     [rax+10h], rbx
0x1400813eb  mov     [rax+18h], rsi
0x1400813ef  mov     [rax+8], rcx
0x1400813f3  push    rdi
0x1400813f4  sub     rsp, 30h
0x1400813f8  mov     rbx, rcx
0x1400813fb  xor     edi, edi
0x1400813fd  mov     [rax-18h], rdi
0x140081401  test    rcx, rcx
0x140081404  jz      short loc_14008142C
0x140081406  lea     r8, [rcx+28h]
0x14008140a  add     rcx, 20h ; ' '
0x14008140e  call    MemoryMapFile
0x140081413  mov     [rbx+18h], rax
0x140081417  test    rax, rax
0x14008141a  jz      short loc_14008142C
0x14008141c  cmp     [rbx+20h], edi
0x14008141f  jz      short loc_14008142C
0x140081421  mov     [rbx+24h], edi
0x140081424  mov     rdi, rax
0x140081427  mov     [rsp+38h+var_18], rax
0x14008142c  test    rdi, rdi
0x14008142f  jnz     short loc_140081447
0x140081431  test    rbx, rbx
0x140081434  jz      short loc_140081447
0x140081436  lea     rcx, [rbx+18h]
0x14008143a  mov     r8d, [rbx+20h]
0x14008143e  mov     rdx, [rbx+28h]
0x140081442  call    EnhancedUnmapRW
0x140081447  mov     rax, rdi
0x14008144a  mov     rbx, [rsp+38h+arg_8]
0x14008144f  mov     rsi, [rsp+38h+arg_10]
0x140081454  add     rsp, 30h
0x140081458  pop     rdi
0x140081459  retn
0x140097a7e  push    rbp
0x140097a80  sub     rsp, 20h
0x140097a84  mov     rbp, rdx
0x140097a87  cmp     qword ptr [rbp+20h], 0
0x140097a8c  jnz     short loc_140097AA9
0x140097a8e  mov     rdx, [rbp+40h]
0x140097a92  test    rdx, rdx
0x140097a95  jz      short loc_140097AA9
0x140097a97  lea     rcx, [rdx+18h]
0x140097a9b  mov     r8d, [rdx+20h]
0x140097a9f  mov     rdx, [rdx+28h]
0x140097aa3  call    EnhancedUnmapRW
0x140097aa8  nop
0x140097aa9  add     rsp, 20h
0x140097aad  pop     rbp
0x140097aae  retn
```
