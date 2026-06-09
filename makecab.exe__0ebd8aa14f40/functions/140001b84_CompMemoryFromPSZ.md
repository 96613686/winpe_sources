# CompMemoryFromPSZ

- ea: `0x140001b84`
- end: `0x140001c77`
- name: `CompMemoryFromPSZ`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002700`
- `0x1400084d8`

## callees

- `0x140001b84`
- `0x140008620`

## import_xrefs

- `msvcrt!atoi` at `0x140001b95`
- `msvcrt!atoi` at `0x140001ba4`
- `msvcrt!atoi` at `0x140001bb6`
- `msvcrt!atoi` at `0x140001b95`
- `msvcrt!atoi` at `0x140001ba4`
- `msvcrt!atoi` at `0x140001bb6`

## string_xrefs

- `0x140001bf6`: `Compression Memory not in range (%1..%2): %3`
- `0x140001c5d`: `Compression Memory not in range (%1..%2): %3`

## pseudocode

```c
__int64 __fastcall CompMemoryFromPSZ(const char *a1, __int64 a2)
{
  int v4; // ebx
  int v5; // edi
  int v6; // eax
  __int64 result; // rax
  int v8; // r9d
  int v9; // edx
  char v10; // cl
  int i; // r8d

  v4 = atoi(a1);
  v5 = atoi("10");
  v6 = atoi("21");
  if ( v5 <= v4 && v4 <= v6 )
    return (unsigned int)v4;
  v8 = 1 << v5;
  if ( v4 < 1 << v5 )
  {
    ErrSet(a2, "Compression Memory not in range (%1..%2): %3", "%s%s%s", "10", "21", a1);
    return 0xFFFFFFFFLL;
  }
  v9 = 1 << v6;
  if ( ((v4 - 1) & v4) != 0 )
  {
    v10 = 0;
    for ( i = v4; v4; v4 >>= 1 )
      ++v10;
    v4 = ~((1 << v10) - 1) & ((1 << v10) - 1 + i);
  }
  if ( v8 > v4 || v4 > v9 )
  {
    ErrSet(a2, "Compression Memory not in range (%1..%2): %3", "%d%d%s", v8, v9, a1);
    return 0xFFFFFFFFLL;
  }
  for ( result = 0; ; result = (unsigned int)(result + 1) )
  {
    v4 >>= 1;
    if ( !v4 )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x140001b84  push    rbx
0x140001b86  push    rbp
0x140001b87  push    rsi
0x140001b88  push    rdi
0x140001b89  push    r14
0x140001b8b  sub     rsp, 30h
0x140001b8f  mov     rbp, rdx
0x140001b92  mov     rsi, rcx
0x140001b95  call    cs:__imp_atoi
0x140001b9b  lea     rcx, a10; "10"
0x140001ba2  mov     ebx, eax
0x140001ba4  call    cs:__imp_atoi
0x140001baa  lea     r14, a21; "21"
0x140001bb1  mov     edi, eax
0x140001bb3  mov     rcx, r14; String
0x140001bb6  call    cs:__imp_atoi
0x140001bbc  cmp     edi, ebx
0x140001bbe  jg      short loc_140001BCB
0x140001bc0  cmp     ebx, eax
0x140001bc2  jg      short loc_140001BCB
0x140001bc4  mov     eax, ebx
0x140001bc6  jmp     loc_140001C6C
0x140001bcb  mov     r10d, 1
0x140001bd1  mov     ecx, edi
0x140001bd3  mov     r9d, r10d
0x140001bd6  shl     r9d, cl
0x140001bd9  cmp     ebx, r9d
0x140001bdc  jge     short loc_140001C07
0x140001bde  mov     [rsp+58h+var_30], rsi
0x140001be3  lea     r9, a10; "10"
0x140001bea  lea     r8, aSSS; "%s%s%s"
0x140001bf1  mov     [rsp+58h+var_38], r14
0x140001bf6  lea     rdx, aCompressionMem; "Compression Memory not in range (%1..%2"...
0x140001bfd  mov     rcx, rbp
0x140001c00  call    ErrSet
0x140001c05  jmp     short loc_140001C69
0x140001c07  mov     ecx, eax
0x140001c09  mov     edx, r10d
0x140001c0c  shl     edx, cl
0x140001c0e  lea     eax, [rbx-1]
0x140001c11  test    ebx, eax
0x140001c13  jz      short loc_140001C34
0x140001c15  xor     ecx, ecx
0x140001c17  mov     r8d, ebx
0x140001c1a  test    ebx, ebx
0x140001c1c  jz      short loc_140001C25
0x140001c1e  add     ecx, r10d
0x140001c21  sar     ebx, 1
0x140001c23  jnz     short loc_140001C1E
0x140001c25  mov     eax, r10d
0x140001c28  shl     eax, cl
0x140001c2a  dec     eax
0x140001c2c  lea     ebx, [rax+r8]
0x140001c30  not     eax
0x140001c32  and     ebx, eax
0x140001c34  cmp     r9d, ebx
0x140001c37  jg      short loc_140001C4A
0x140001c39  cmp     ebx, edx
0x140001c3b  jg      short loc_140001C4A
0x140001c3d  xor     eax, eax
0x140001c3f  jmp     short loc_140001C44
0x140001c41  add     eax, r10d
0x140001c44  sar     ebx, 1
0x140001c46  jnz     short loc_140001C41
0x140001c48  jmp     short loc_140001C6C
0x140001c4a  mov     [rsp+58h+var_30], rsi
0x140001c4f  lea     r8, aDDS; "%d%d%s"
0x140001c56  mov     dword ptr [rsp+58h+var_38], edx
0x140001c5a  mov     rcx, rbp
0x140001c5d  lea     rdx, aCompressionMem; "Compression Memory not in range (%1..%2"...
0x140001c64  call    ErrSet
0x140001c69  or      eax, 0FFFFFFFFh
0x140001c6c  add     rsp, 30h
0x140001c70  pop     r14
0x140001c72  pop     rdi
0x140001c73  pop     rsi
0x140001c74  pop     rbp
0x140001c75  pop     rbx
0x140001c76  retn
```
