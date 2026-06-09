# CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)

- ea: `0x180002eb0`
- end: `0x180002f4e`
- name: `?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z`
- size: `158`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180002f54`
- `0x180004ef4`
- `0x180005a6c`
- `0x180005ef4`

## callees

- `0x180002e34`
- `0x180002eb0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002f31`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002f31`
- `KERNEL32!HeapFree` at `0x180002f1a`
- `KERNEL32!HeapFree` at `0x180002f1a`

## pseudocode

```c
void __fastcall CleanupJsonObject(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned __int64 v3; // rdi
  struct JsonKeyValuePair **v4; // rax
  void *v5; // r8

  v1 = *a1;
  if ( *a1 )
  {
    if ( !*(_QWORD *)(v1 + 16) )
      goto LABEL_10;
    v3 = 0;
    do
    {
      v4 = 0;
      if ( v3 < *(_QWORD *)(v1 + 16) )
      {
        if ( !is_mul_ok(*(_QWORD *)(v1 + 8), v3)
          || (v4 = (struct JsonKeyValuePair **)(*(_QWORD *)(v1 + 40) + *(_QWORD *)(v1 + 8) * v3),
              (unsigned __int64)v4 < *(_QWORD *)(v1 + 40)) )
        {
          v4 = 0;
        }
      }
      CleanupJsonKeyValuePair(v4);
      v1 = *a1;
      ++v3;
    }
    while ( v3 < *(_QWORD *)(*a1 + 16) );
    if ( v1 )
    {
LABEL_10:
      v5 = *(void **)(v1 + 40);
      if ( v5 )
        HeapFree(*(HANDLE *)v1, 0, v5);
      *(_OWORD *)v1 = 0;
      *(_OWORD *)(v1 + 16) = 0;
      *(_OWORD *)(v1 + 32) = 0;
      operator delete((void *)v1);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x180002eb0  mov     [rsp+arg_8], rbx
0x180002eb5  mov     [rsp+arg_10], rsi
0x180002eba  push    rdi
0x180002ebb  sub     rsp, 20h
0x180002ebf  mov     rbx, [rcx]
0x180002ec2  mov     rsi, rcx
0x180002ec5  test    rbx, rbx
0x180002ec8  jz      short loc_180002F3E
0x180002eca  cmp     qword ptr [rbx+10h], 0
0x180002ecf  jbe     short loc_180002F0C
0x180002ed1  xor     edi, edi
0x180002ed3  xor     eax, eax
0x180002ed5  cmp     rdi, [rbx+10h]
0x180002ed9  jnb     short loc_180002EF3
0x180002edb  mov     rax, rdi
0x180002ede  mul     qword ptr [rbx+8]
0x180002ee2  test    rdx, rdx
0x180002ee5  jnz     short loc_180002EF1
0x180002ee7  add     rax, [rbx+28h]
0x180002eeb  cmp     rax, [rbx+28h]
0x180002eef  jnb     short loc_180002EF3
0x180002ef1  xor     eax, eax
0x180002ef3  mov     rcx, rax; struct JsonKeyValuePair **
0x180002ef6  call    ?CleanupJsonKeyValuePair@@YAXPEAPEAUJsonKeyValuePair@@@Z; CleanupJsonKeyValuePair(JsonKeyValuePair * *)
0x180002efb  mov     rbx, [rsi]
0x180002efe  inc     rdi
0x180002f01  cmp     rdi, [rbx+10h]
0x180002f05  jb      short loc_180002ED3
0x180002f07  test    rbx, rbx
0x180002f0a  jz      short loc_180002F3E
0x180002f0c  mov     r8, [rbx+28h]; lpMem
0x180002f10  test    r8, r8
0x180002f13  jz      short loc_180002F20
0x180002f15  mov     rcx, [rbx]; hHeap
0x180002f18  xor     edx, edx; dwFlags
0x180002f1a  call    cs:__imp_HeapFree
0x180002f20  xorps   xmm0, xmm0
0x180002f23  mov     rcx, rbx
0x180002f26  movups  xmmword ptr [rbx], xmm0
0x180002f29  movups  xmmword ptr [rbx+10h], xmm0
0x180002f2d  movups  xmmword ptr [rbx+20h], xmm0
0x180002f31  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002f37  mov     qword ptr [rsi], 0
0x180002f3e  mov     rbx, [rsp+28h+arg_8]
0x180002f43  mov     rsi, [rsp+28h+arg_10]
0x180002f48  add     rsp, 20h
0x180002f4c  pop     rdi
0x180002f4d  retn
```
