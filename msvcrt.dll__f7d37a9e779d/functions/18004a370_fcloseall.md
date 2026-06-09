# _fcloseall

- ea: `0x18004a370`
- end: `0x18004a41b`
- name: `_fcloseall`
- size: `171`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180040500`

## callees

- `0x18001d300`
- `0x18003e6c0`
- `0x18003e8e0`
- `0x18004a370`
- `0x1800506e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a3d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a3d6`

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
    v2 = *((_QWORD *)_piob + i);
    if ( v2 )
    {
      if ( (*(_BYTE *)(v2 + 24) & 0x83) != 0 && fclose((FILE *)v2) != -1 )
        ++v0;
      if ( i >= 20 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)_piob + i) + 48LL));
        free(*((void **)_piob + i));
        *((_QWORD *)_piob + i) = 0;
      }
    }
  }
  unlock(1);
  return v0;
}

```

## disassembly

```asm
0x18004a370  mov     [rsp+arg_0], rbx
0x18004a375  mov     [rsp+arg_8], rsi
0x18004a37a  push    rdi
0x18004a37b  sub     rsp, 30h
0x18004a37f  xor     edi, edi
0x18004a381  lea     ecx, [rdi+1]
0x18004a384  call    _lock
0x18004a389  nop
0x18004a38a  lea     ebx, [rdi+3]
0x18004a38d  mov     [rsp+38h+var_18], ebx
0x18004a391  cmp     ebx, cs:_nstream
0x18004a397  jge     short loc_18004A3FF
0x18004a399  movsxd  rsi, ebx
0x18004a39c  mov     rax, cs:__piob
0x18004a3a3  mov     rcx, [rax+rsi*8]; Stream
0x18004a3a7  test    rcx, rcx
0x18004a3aa  jz      short loc_18004A3FB
0x18004a3ac  test    byte ptr [rcx+18h], 83h
0x18004a3b0  jz      short loc_18004A3C2
0x18004a3b2  call    fclose
0x18004a3b7  cmp     eax, 0FFFFFFFFh
0x18004a3ba  jz      short loc_18004A3C2
0x18004a3bc  inc     edi
0x18004a3be  mov     [rsp+38h+var_14], edi
0x18004a3c2  cmp     ebx, 14h
0x18004a3c5  jl      short loc_18004A3FB
0x18004a3c7  mov     rax, cs:__piob
0x18004a3ce  mov     rcx, [rax+rsi*8]
0x18004a3d2  add     rcx, 30h ; '0'; lpCriticalSection
0x18004a3d6  call    cs:__imp_DeleteCriticalSection
0x18004a3dc  mov     rcx, cs:__piob
0x18004a3e3  mov     rcx, [rcx+rsi*8]; Block
0x18004a3e7  call    free
0x18004a3ec  mov     rax, cs:__piob
0x18004a3f3  mov     qword ptr [rax+rsi*8], 0
0x18004a3fb  inc     ebx
0x18004a3fd  jmp     short loc_18004A38D
0x18004a3ff  mov     ecx, 1
0x18004a404  call    _unlock
0x18004a409  mov     eax, edi
0x18004a40b  mov     rbx, [rsp+38h+arg_0]
0x18004a410  mov     rsi, [rsp+38h+arg_8]
0x18004a415  add     rsp, 30h
0x18004a419  pop     rdi
0x18004a41a  retn
0x18007be3a  push    rbp
0x18007be3c  sub     rsp, 20h
0x18007be40  mov     rbp, rdx
0x18007be43  mov     ecx, 1
0x18007be48  add     rsp, 20h
0x18007be4c  pop     rbp
0x18007be4d  jmp     _unlock
```
