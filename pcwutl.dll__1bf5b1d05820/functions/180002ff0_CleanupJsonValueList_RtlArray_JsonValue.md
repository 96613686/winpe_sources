# CleanupJsonValueList(RtlArray<JsonValue *> * *)

- ea: `0x180002ff0`
- end: `0x18000308e`
- name: `?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180002f54`
- `0x180005ef4`
- `0x1800063a0`

## callees

- `0x180002f54`
- `0x180002ff0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003071`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003071`
- `KERNEL32!HeapFree` at `0x18000305a`
- `KERNEL32!HeapFree` at `0x18000305a`

## pseudocode

```c
void __fastcall CleanupJsonValueList(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned __int64 v3; // rdi
  struct JsonValue **v4; // rax
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
          || (v4 = (struct JsonValue **)(*(_QWORD *)(v1 + 40) + *(_QWORD *)(v1 + 8) * v3),
              (unsigned __int64)v4 < *(_QWORD *)(v1 + 40)) )
        {
          v4 = 0;
        }
      }
      CleanupJsonValue(v4);
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
0x180002ff0  mov     [rsp+arg_8], rbx
0x180002ff5  mov     [rsp+arg_10], rsi
0x180002ffa  push    rdi
0x180002ffb  sub     rsp, 20h
0x180002fff  mov     rbx, [rcx]
0x180003002  mov     rsi, rcx
0x180003005  test    rbx, rbx
0x180003008  jz      short loc_18000307E
0x18000300a  cmp     qword ptr [rbx+10h], 0
0x18000300f  jbe     short loc_18000304C
0x180003011  xor     edi, edi
0x180003013  xor     eax, eax
0x180003015  cmp     rdi, [rbx+10h]
0x180003019  jnb     short loc_180003033
0x18000301b  mov     rax, rdi
0x18000301e  mul     qword ptr [rbx+8]
0x180003022  test    rdx, rdx
0x180003025  jnz     short loc_180003031
0x180003027  add     rax, [rbx+28h]
0x18000302b  cmp     rax, [rbx+28h]
0x18000302f  jnb     short loc_180003033
0x180003031  xor     eax, eax
0x180003033  mov     rcx, rax; struct JsonValue **
0x180003036  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x18000303b  mov     rbx, [rsi]
0x18000303e  inc     rdi
0x180003041  cmp     rdi, [rbx+10h]
0x180003045  jb      short loc_180003013
0x180003047  test    rbx, rbx
0x18000304a  jz      short loc_18000307E
0x18000304c  mov     r8, [rbx+28h]; lpMem
0x180003050  test    r8, r8
0x180003053  jz      short loc_180003060
0x180003055  mov     rcx, [rbx]; hHeap
0x180003058  xor     edx, edx; dwFlags
0x18000305a  call    cs:__imp_HeapFree
0x180003060  xorps   xmm0, xmm0
0x180003063  mov     rcx, rbx
0x180003066  movups  xmmword ptr [rbx], xmm0
0x180003069  movups  xmmword ptr [rbx+10h], xmm0
0x18000306d  movups  xmmword ptr [rbx+20h], xmm0
0x180003071  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003077  mov     qword ptr [rsi], 0
0x18000307e  mov     rbx, [rsp+28h+arg_8]
0x180003083  mov     rsi, [rsp+28h+arg_10]
0x180003088  add     rsp, 20h
0x18000308c  pop     rdi
0x18000308d  retn
```
