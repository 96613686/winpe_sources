# _fcloseall

- ea: `0x18001ec94`
- end: `0x18001ed3f`
- name: `_fcloseall`
- size: `171`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c270`

## callees

- `0x18000f264`
- `0x1800189e8`
- `0x180018c14`
- `0x18001ec94`
- `0x18001fe98`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001ecfa`
- `KERNEL32!DeleteCriticalSection` at `0x18001ecfa`

## pseudocode

```c
int __cdecl fcloseall()
{
  int v0; // edi
  int i; // ebx
  __int64 v2; // rcx

  v0 = 0;
  lock(1);
  for ( i = 3; i < nstream; ++i )
  {
    v2 = *(_QWORD *)(_piob + 8LL * i);
    if ( v2 )
    {
      if ( (*(_BYTE *)(v2 + 24) & 0x83) != 0 && fclose((FILE *)v2) != -1 )
        ++v0;
      if ( i >= 20 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(_piob + 8LL * i) + 48LL));
        free(*(void **)(_piob + 8LL * i));
        *(_QWORD *)(_piob + 8LL * i) = 0;
      }
    }
  }
  unlock(1);
  return v0;
}

```

## disassembly

```asm
0x18001ec94  mov     [rsp+arg_0], rbx
0x18001ec99  mov     [rsp+arg_8], rsi
0x18001ec9e  push    rdi
0x18001ec9f  sub     rsp, 30h
0x18001eca3  xor     edi, edi
0x18001eca5  lea     ecx, [rdi+1]
0x18001eca8  call    _lock
0x18001ecad  nop
0x18001ecae  lea     ebx, [rdi+3]
0x18001ecb1  mov     [rsp+38h+var_18], ebx
0x18001ecb5  cmp     ebx, cs:_nstream
0x18001ecbb  jge     short loc_18001ED23
0x18001ecbd  movsxd  rsi, ebx
0x18001ecc0  mov     rax, cs:__piob
0x18001ecc7  mov     rcx, [rax+rsi*8]; Stream
0x18001eccb  test    rcx, rcx
0x18001ecce  jz      short loc_18001ED1F
0x18001ecd0  test    byte ptr [rcx+18h], 83h
0x18001ecd4  jz      short loc_18001ECE6
0x18001ecd6  call    fclose
0x18001ecdb  cmp     eax, 0FFFFFFFFh
0x18001ecde  jz      short loc_18001ECE6
0x18001ece0  inc     edi
0x18001ece2  mov     [rsp+38h+var_14], edi
0x18001ece6  cmp     ebx, 14h
0x18001ece9  jl      short loc_18001ED1F
0x18001eceb  mov     rax, cs:__piob
0x18001ecf2  mov     rcx, [rax+rsi*8]
0x18001ecf6  add     rcx, 30h ; '0'; lpCriticalSection
0x18001ecfa  call    cs:__imp_DeleteCriticalSection
0x18001ed00  mov     rcx, cs:__piob
0x18001ed07  mov     rcx, [rcx+rsi*8]; Block
0x18001ed0b  call    free
0x18001ed10  mov     rax, cs:__piob
0x18001ed17  mov     qword ptr [rax+rsi*8], 0
0x18001ed1f  inc     ebx
0x18001ed21  jmp     short loc_18001ECB1
0x18001ed23  mov     ecx, 1
0x18001ed28  call    _unlock
0x18001ed2d  mov     eax, edi
0x18001ed2f  mov     rbx, [rsp+38h+arg_0]
0x18001ed34  mov     rsi, [rsp+38h+arg_8]
0x18001ed39  add     rsp, 30h
0x18001ed3d  pop     rdi
0x18001ed3e  retn
0x180043865  push    rbp
0x180043867  sub     rsp, 20h
0x18004386b  mov     rbp, rdx
0x18004386e  mov     ecx, 1
0x180043873  add     rsp, 20h
0x180043877  pop     rbp
0x180043878  jmp     _unlock
```
