# CDynamicArray::Find(void const *)

- ea: `0x180005c60`
- end: `0x180005cb2`
- name: `?Find@CDynamicArray@@UEBAHPEBX@Z`
- size: `82`
- prototype: `__int64 __fastcall(CDynamicArray *this, const void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005cb8`

## callees

- `0x180005c60`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180005c91`
- `ntdll!RtlCompareMemory` at `0x180005c91`

## pseudocode

```c
__int64 __fastcall CDynamicArray::Find(CDynamicArray *this, const void *a2)
{
  int v4; // edi
  SIZE_T v5; // rbx

  if ( *((_QWORD *)this + 3) )
  {
    v4 = *((_DWORD *)this + 4);
    while ( v4 )
    {
      v5 = *((_QWORD *)this + 1);
      if ( RtlCompareMemory((const void *)(*((_QWORD *)this + 3) + v5 * (unsigned int)--v4), a2, v5) == v5 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005c60  push    rbx
0x180005c62  push    rbp
0x180005c63  push    rsi
0x180005c64  push    rdi
0x180005c65  sub     rsp, 28h
0x180005c69  cmp     qword ptr [rcx+18h], 0
0x180005c6e  mov     rbp, rdx
0x180005c71  mov     rsi, rcx
0x180005c74  jz      short loc_180005CA0
0x180005c76  mov     edi, [rcx+10h]
0x180005c79  jmp     short loc_180005C9C
0x180005c7b  mov     rbx, [rsi+8]
0x180005c7f  dec     edi
0x180005c81  mov     ecx, edi
0x180005c83  mov     r8, rbx; Length
0x180005c86  imul    rcx, rbx
0x180005c8a  mov     rdx, rbp; Source2
0x180005c8d  add     rcx, [rsi+18h]; Source1
0x180005c91  call    cs:__imp_RtlCompareMemory
0x180005c97  cmp     rax, rbx
0x180005c9a  jz      short loc_180005CAB
0x180005c9c  test    edi, edi
0x180005c9e  jnz     short loc_180005C7B
0x180005ca0  xor     eax, eax
0x180005ca2  add     rsp, 28h
0x180005ca6  pop     rdi
0x180005ca7  pop     rsi
0x180005ca8  pop     rbp
0x180005ca9  pop     rbx
0x180005caa  retn
0x180005cab  mov     eax, 1
0x180005cb0  jmp     short loc_180005CA2
```
