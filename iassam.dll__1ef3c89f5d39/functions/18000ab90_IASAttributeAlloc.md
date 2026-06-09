# IASAttributeAlloc

- ea: `0x18000ab90`
- end: `0x18000ac0a`
- name: `IASAttributeAlloc`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d55c`
- `0x1800169e0`
- `0x18001a434`
- `0x180020e00`
- `0x1800247a0`

## callees

- `0x18000ab90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000abb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000abb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abe6`

## pseudocode

```c
__int64 __fastcall IASAttributeAlloc(int a1, LPVOID *a2)
{
  LPVOID *i; // rbx
  _OWORD *v5; // rax
  _DWORD *v6; // rax

  for ( i = a2; ; ++i )
  {
    if ( !a1 )
      return 0;
    v5 = CoTaskMemAlloc(0x28u);
    *i = v5;
    if ( !v5 )
      break;
    *v5 = 0;
    --a1;
    v5[1] = 0;
    *((_QWORD *)v5 + 4) = 0;
    v6 = *i;
    *v6 = 1;
  }
  while ( i > a2 )
    CoTaskMemFree(*--i);
  return 8;
}

```

## disassembly

```asm
0x18000ab90  mov     [rsp+arg_0], rbx
0x18000ab95  mov     [rsp+arg_8], rsi
0x18000ab9a  push    rdi
0x18000ab9b  sub     rsp, 20h
0x18000ab9f  mov     rdi, rdx
0x18000aba2  mov     esi, ecx
0x18000aba4  mov     rbx, rdx
0x18000aba7  test    esi, esi
0x18000aba9  jz      short loc_18000ABF8
0x18000abab  mov     ecx, 28h ; '('; cb
0x18000abb0  call    cs:__imp_CoTaskMemAlloc
0x18000abb6  mov     [rbx], rax
0x18000abb9  test    rax, rax
0x18000abbc  jz      short loc_18000ABEC
0x18000abbe  xorps   xmm0, xmm0
0x18000abc1  xor     ecx, ecx
0x18000abc3  movups  xmmword ptr [rax], xmm0
0x18000abc6  dec     esi
0x18000abc8  movups  xmmword ptr [rax+10h], xmm0
0x18000abcc  mov     [rax+20h], rcx
0x18000abd0  mov     rax, [rbx]
0x18000abd3  add     rbx, 8
0x18000abd7  mov     dword ptr [rax], 1
0x18000abdd  jmp     short loc_18000ABA7
0x18000abdf  sub     rbx, 8
0x18000abe3  mov     rcx, [rbx]; pv
0x18000abe6  call    cs:__imp_CoTaskMemFree
0x18000abec  cmp     rbx, rdi
0x18000abef  ja      short loc_18000ABDF
0x18000abf1  mov     eax, 8
0x18000abf6  jmp     short loc_18000ABFA
0x18000abf8  xor     eax, eax
0x18000abfa  mov     rbx, [rsp+28h+arg_0]
0x18000abff  mov     rsi, [rsp+28h+arg_8]
0x18000ac04  add     rsp, 20h
0x18000ac08  pop     rdi
0x18000ac09  retn
```
