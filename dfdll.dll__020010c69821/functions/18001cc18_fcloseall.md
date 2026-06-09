# _fcloseall

- ea: `0x18001cc18`
- end: `0x18001ccca`
- name: `_fcloseall`
- size: `178`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b400`

## callees

- `0x180018bd8`
- `0x180018c38`
- `0x180019608`
- `0x18001cc18`
- `0x18001e174`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001cc8b`
- `KERNEL32!DeleteCriticalSection` at `0x18001cc8b`

## pseudocode

```c
int __cdecl fcloseall()
{
  int i; // ebx
  __int64 v1; // rax
  int v3; // [rsp+20h] [rbp-18h]

  v3 = 0;
  _acrt_lock(8);
  for ( i = 3; i != nstream; ++i )
  {
    v1 = *((_QWORD *)_piob + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 20) & 0x2000) != 0 && fclose(*((FILE **)_piob + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)_piob + i) + 48LL));
      free_base(*((void **)_piob + i));
      *((_QWORD *)_piob + i) = 0;
    }
  }
  _acrt_unlock(8);
  return v3;
}

```

## disassembly

```asm
0x18001cc18  mov     [rsp+arg_0], rbx
0x18001cc1d  push    rdi
0x18001cc1e  sub     rsp, 30h
0x18001cc22  and     [rsp+38h+var_18], 0
0x18001cc27  mov     ecx, 8
0x18001cc2c  call    __acrt_lock
0x18001cc31  nop
0x18001cc32  mov     ebx, 3
0x18001cc37  mov     [rsp+38h+var_14], ebx
0x18001cc3b  cmp     ebx, cs:_nstream
0x18001cc41  jz      short loc_18001CCB1
0x18001cc43  movsxd  rdi, ebx
0x18001cc46  mov     rax, cs:__piob
0x18001cc4d  mov     rax, [rax+rdi*8]
0x18001cc51  test    rax, rax
0x18001cc54  jnz     short loc_18001CC58
0x18001cc56  jmp     short loc_18001CCAD
0x18001cc58  mov     ecx, [rax+14h]
0x18001cc5b  shr     ecx, 0Dh
0x18001cc5e  test    cl, 1
0x18001cc61  jz      short loc_18001CC7C
0x18001cc63  mov     rcx, cs:__piob
0x18001cc6a  mov     rcx, [rcx+rdi*8]; Stream
0x18001cc6e  call    fclose
0x18001cc73  cmp     eax, 0FFFFFFFFh
0x18001cc76  jz      short loc_18001CC7C
0x18001cc78  inc     [rsp+38h+var_18]
0x18001cc7c  mov     rax, cs:__piob
0x18001cc83  mov     rcx, [rax+rdi*8]
0x18001cc87  add     rcx, 30h ; '0'; lpCriticalSection
0x18001cc8b  call    cs:__imp_DeleteCriticalSection
0x18001cc91  mov     rcx, cs:__piob
0x18001cc98  mov     rcx, [rcx+rdi*8]; Block
0x18001cc9c  call    _free_base
0x18001cca1  mov     rax, cs:__piob
0x18001cca8  and     qword ptr [rax+rdi*8], 0
0x18001ccad  inc     ebx
0x18001ccaf  jmp     short loc_18001CC37
0x18001ccb1  mov     ecx, 8
0x18001ccb6  call    __acrt_unlock
0x18001ccbb  mov     eax, [rsp+38h+var_18]
0x18001ccbf  mov     rbx, [rsp+38h+arg_0]
0x18001ccc4  add     rsp, 30h
0x18001ccc8  pop     rdi
0x18001ccc9  retn
0x18001f82d  push    rbp
0x18001f82f  sub     rsp, 20h
0x18001f833  mov     rbp, rdx
0x18001f836  mov     ecx, 8
0x18001f83b  add     rsp, 20h
0x18001f83f  pop     rbp
0x18001f840  jmp     __acrt_unlock
```
