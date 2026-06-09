# LIST_ARRAY::CheckRange(ulong,int)

- ea: `0x14000494c`
- end: `0x1400049aa`
- name: `?CheckRange@LIST_ARRAY@@AEAAJKH@Z`
- size: `94`
- prototype: `__int64 __fastcall(LIST_ARRAY *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400035a8`

## callees

- `0x14000494c`

## import_xrefs

- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x140004973`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x140004973`

## pseudocode

```c
__int64 __fastcall LIST_ARRAY::CheckRange(LIST_ARRAY *this, unsigned int a2, int a3)
{
  unsigned int v4; // eax
  int v5; // edi
  unsigned int v6; // ecx
  __int64 result; // rax

  if ( !a3 )
  {
    v6 = 0;
    result = 2147943813LL;
    if ( a2 > *(_DWORD *)this - 1 )
      return result;
    return v6;
  }
  v4 = *((_DWORD *)this + 1);
  if ( a2 <= v4 )
    return 0;
  v5 = 2 * v4;
  if ( BUFFER::Resize((LIST_ARRAY *)((char *)this + 8), 16 * v4 + 16) )
  {
    *((_DWORD *)this + 1) = v5 + 1;
    return 0;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x14000494c  mov     [rsp+arg_0], rbx
0x140004951  push    rdi
0x140004952  sub     rsp, 20h
0x140004956  mov     rbx, rcx
0x140004959  test    r8d, r8d
0x14000495c  jz      short loc_14000498E
0x14000495e  mov     eax, [rcx+4]
0x140004961  cmp     edx, eax
0x140004963  jbe     short loc_14000498A
0x140004965  lea     edi, [rax+rax]
0x140004968  add     rcx, 8
0x14000496c  lea     edx, ds:10h[rdi*8]
0x140004973  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x140004979  test    al, al
0x14000497b  jnz     short loc_140004984
0x14000497d  mov     ecx, 8007000Eh
0x140004982  jmp     short loc_14000499D
0x140004984  lea     eax, [rdi+1]
0x140004987  mov     [rbx+4], eax
0x14000498a  xor     ecx, ecx
0x14000498c  jmp     short loc_14000499D
0x14000498e  mov     eax, [rbx]
0x140004990  xor     ecx, ecx
0x140004992  dec     eax
0x140004994  cmp     edx, eax
0x140004996  mov     eax, 80070585h
0x14000499b  ja      short loc_14000499F
0x14000499d  mov     eax, ecx
0x14000499f  mov     rbx, [rsp+28h+arg_0]
0x1400049a4  add     rsp, 20h
0x1400049a8  pop     rdi
0x1400049a9  retn
```
