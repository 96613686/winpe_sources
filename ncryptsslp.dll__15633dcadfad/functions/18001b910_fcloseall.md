# _fcloseall

- ea: `0x18001b910`
- end: `0x18001b9d0`
- name: `_fcloseall`
- size: `192`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b850`

## callees

- `0x180015c20`
- `0x1800160b4`
- `0x1800160d4`
- `0x18001b910`
- `0x18001c098`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b988`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b988`

## pseudocode

```c
int __cdecl fcloseall()
{
  int v0; // edi
  int i; // ebx
  __int64 v2; // rax

  v0 = 0;
  _acrt_lock(8);
  for ( i = 3; i != nstream; ++i )
  {
    v2 = *((_QWORD *)_piob + i);
    if ( v2 )
    {
      if ( (*(_DWORD *)(v2 + 20) & 0x2000) != 0 && fclose(*((FILE **)_piob + i)) != -1 )
        ++v0;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)_piob + i) + 48LL));
      free_base(*((void **)_piob + i));
      *((_QWORD *)_piob + i) = 0;
    }
  }
  _acrt_unlock(8);
  return v0;
}

```

## disassembly

```asm
0x18001b910  mov     [rsp+arg_8], rbx
0x18001b915  mov     [rsp+arg_10], rsi
0x18001b91a  push    rdi
0x18001b91b  sub     rsp, 30h
0x18001b91f  xor     edi, edi
0x18001b921  lea     ecx, [rdi+8]
0x18001b924  call    __acrt_lock
0x18001b929  nop
0x18001b92a  lea     ebx, [rdi+3]
0x18001b92d  mov     [rsp+38h+var_18], ebx
0x18001b931  cmp     ebx, cs:_nstream
0x18001b937  jz      short loc_18001B9B4
0x18001b939  movsxd  rsi, ebx
0x18001b93c  mov     rax, cs:__piob
0x18001b943  mov     rax, [rax+rsi*8]
0x18001b947  test    rax, rax
0x18001b94a  jnz     short loc_18001B94E
0x18001b94c  jmp     short loc_18001B9AD
0x18001b94e  mov     [rsp+38h+arg_0], rax
0x18001b953  mov     eax, [rax+14h]
0x18001b956  nop
0x18001b957  shr     eax, 0Dh
0x18001b95a  test    al, 1
0x18001b95c  jz      short loc_18001B979
0x18001b95e  mov     rcx, cs:__piob
0x18001b965  mov     rcx, [rcx+rsi*8]; Stream
0x18001b969  call    fclose
0x18001b96e  cmp     eax, 0FFFFFFFFh
0x18001b971  jz      short loc_18001B979
0x18001b973  inc     edi
0x18001b975  mov     [rsp+38h+var_14], edi
0x18001b979  mov     rax, cs:__piob
0x18001b980  mov     rcx, [rax+rsi*8]
0x18001b984  add     rcx, 30h ; '0'; lpCriticalSection
0x18001b988  call    cs:__imp_DeleteCriticalSection
0x18001b98e  mov     rcx, cs:__piob
0x18001b995  mov     rcx, [rcx+rsi*8]; Block
0x18001b999  call    _free_base
0x18001b99e  mov     rax, cs:__piob
0x18001b9a5  mov     qword ptr [rax+rsi*8], 0
0x18001b9ad  inc     ebx
0x18001b9af  jmp     loc_18001B92D
0x18001b9b4  mov     ecx, 8
0x18001b9b9  call    __acrt_unlock
0x18001b9be  mov     eax, edi
0x18001b9c0  mov     rbx, [rsp+38h+arg_8]
0x18001b9c5  mov     rsi, [rsp+38h+arg_10]
0x18001b9ca  add     rsp, 30h
0x18001b9ce  pop     rdi
0x18001b9cf  retn
0x180025ee0  push    rbp
0x180025ee2  sub     rsp, 20h
0x180025ee6  mov     rbp, rdx
0x180025ee9  mov     ecx, 8
0x180025eee  add     rsp, 20h
0x180025ef2  pop     rbp
0x180025ef3  jmp     __acrt_unlock
```
