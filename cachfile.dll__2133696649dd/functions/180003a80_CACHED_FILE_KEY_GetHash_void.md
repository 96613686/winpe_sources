# CACHED_FILE_KEY::GetHash(void)

- ea: `0x180003a80`
- end: `0x180003abd`
- name: `?GetHash@CACHED_FILE_KEY@@UEBAKXZ`
- size: `61`
- prototype: `__int64 __fastcall(CACHED_FILE_KEY *this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003a80`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CACHED_FILE_KEY::GetHash(CACHED_FILE_KEY *this)
{
  unsigned int v1; // ebx
  unsigned __int16 *i; // rax
  unsigned __int16 v3; // cx

  v1 = 0;
  for ( i = (unsigned __int16 *)(*(__int64 (__fastcall **)(CACHED_FILE_KEY *))(*(_QWORD *)this + 40LL))(this); ; ++i )
  {
    v3 = *i;
    if ( !*i )
      break;
    v1 = v3 + 101 * v1;
  }
  return v1;
}

```

## disassembly

```asm
0x180003a80  mov     [rsp+arg_0], rbx
0x180003a85  push    rdi
0x180003a86  sub     rsp, 20h
0x180003a8a  mov     rax, [rcx]
0x180003a8d  xor     edi, edi
0x180003a8f  mov     ebx, edi
0x180003a91  mov     rax, [rax+28h]
0x180003a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a9a  jmp     short loc_180003AA8
0x180003a9c  imul    ebx, 65h ; 'e'
0x180003a9f  lea     rax, [rax+2]
0x180003aa3  movzx   ecx, cx
0x180003aa6  add     ebx, ecx
0x180003aa8  movzx   ecx, word ptr [rax]
0x180003aab  test    cx, cx
0x180003aae  jnz     short loc_180003A9C
0x180003ab0  mov     eax, ebx
0x180003ab2  mov     rbx, [rsp+28h+arg_0]
0x180003ab7  add     rsp, 20h
0x180003abb  pop     rdi
0x180003abc  retn
```
