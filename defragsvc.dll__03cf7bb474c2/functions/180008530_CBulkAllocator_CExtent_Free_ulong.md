# CBulkAllocator<_CExtent>::Free(ulong *)

- ea: `0x180008530`
- end: `0x180008663`
- name: `?Free@?$CBulkAllocator@U_CExtent@@@@QEAAJPEAK@Z`
- size: `307`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006bf8`
- `0x18001f468`
- `0x180034a60`
- `0x1800630d0`

## callees

- `0x180008530`

## import_xrefs

- `ntdll!RtlClearBits` at `0x1800085d1`
- `ntdll!RtlClearBits` at `0x1800085d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000860b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000860b`

## pseudocode

```c
__int64 __fastcall CBulkAllocator<_CExtent>::Free(__int64 a1, unsigned int *a2)
{
  int v4; // ecx
  unsigned int v5; // edx
  ULONG v6; // r9d
  __int64 v7; // rdx
  unsigned int v8; // r14d
  __int64 v9; // r15
  struct _RTL_BITMAP *v10; // rsi
  bool v11; // zf
  void *v12; // rcx
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  v4 = *(_DWORD *)(a1 + 28);
  if ( !v4 )
    return 2147500037LL;
  v5 = *a2;
  if ( (v5 & 0xF0000000) != v4 || !v5 )
    return 2147942487LL;
  v6 = 0;
  if ( (_WORD)v5 )
    v6 = (unsigned __int16)v5 - 1;
  v7 = HIWORD(v5) & 0xFFF;
  v8 = v7;
  v9 = 8 * v7;
  v10 = *(struct _RTL_BITMAP **)(8 * v7 + *(_QWORD *)(a1 + 8));
  if ( !v10 || v6 >= *(_DWORD *)(a1 + 20) )
    return 2147942487LL;
  RtlClearBits(v10 + 1, v6, 1u);
  if ( v10[2].SizeOfBitMap == *(_DWORD *)(a1 + 20) )
    ++*(_DWORD *)(a1 + 24);
  v11 = v10[2].SizeOfBitMap-- == 1;
  if ( v11 && *(_DWORD *)(a1 + 24) > 1u )
  {
    CoTaskMemFree(v10->Buffer);
    v12 = *(void **)&v10->SizeOfBitMap;
    v10->Buffer = 0;
    CoTaskMemFree(v12);
    *(_QWORD *)&v10->SizeOfBitMap = 0;
    CoTaskMemFree(v10);
    *(_QWORD *)(v9 + *(_QWORD *)(a1 + 8)) = 0;
    --*(_DWORD *)(a1 + 24);
  }
  else if ( v8 < *(_DWORD *)(a1 + 16) )
  {
    *(_DWORD *)(a1 + 16) = v8;
  }
  result = 0;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180008530  push    rbx
0x180008532  push    rdi
0x180008533  sub     rsp, 38h
0x180008537  mov     rdi, rdx
0x18000853a  mov     rbx, rcx
0x18000853d  test    rdx, rdx
0x180008540  jz      loc_18000864E
0x180008546  mov     ecx, [rcx+1Ch]
0x180008549  test    ecx, ecx
0x18000854b  jz      loc_180008655
0x180008551  mov     edx, [rdx]
0x180008553  mov     eax, edx
0x180008555  and     eax, 0F0000000h
0x18000855a  cmp     eax, ecx
0x18000855c  jnz     loc_18000864E
0x180008562  test    edx, edx
0x180008564  jz      loc_18000864E
0x18000856a  mov     [rsp+48h+arg_10], rsi
0x18000856f  movzx   ecx, dx
0x180008572  mov     [rsp+48h+var_18], r12
0x180008577  xor     r12d, r12d
0x18000857a  test    ecx, ecx
0x18000857c  mov     [rsp+48h+var_20], r14
0x180008581  mov     r9d, r12d
0x180008584  mov     [rsp+48h+var_28], r15
0x180008589  lea     eax, [rcx-1]
0x18000858c  cmovnz  r9d, eax
0x180008590  mov     rax, [rbx+8]
0x180008594  shr     edx, 10h
0x180008597  and     edx, 0FFFh
0x18000859d  mov     r14d, edx
0x1800085a0  lea     r15, ds:0[rdx*8]
0x1800085a8  mov     rsi, [r15+rax]
0x1800085ac  test    rsi, rsi
0x1800085af  jz      loc_18000865C
0x1800085b5  cmp     r9d, [rbx+14h]
0x1800085b9  jnb     loc_18000865C
0x1800085bf  lea     rcx, [rsi+10h]; BitMapHeader
0x1800085c3  mov     [rsp+48h+arg_0], rbp
0x1800085c8  mov     r8d, 1; NumberToClear
0x1800085ce  mov     edx, r9d; StartingIndex
0x1800085d1  call    cs:__imp_RtlClearBits
0x1800085d7  mov     eax, [rbx+14h]
0x1800085da  cmp     [rsi+20h], eax
0x1800085dd  jnz     short loc_1800085E2
0x1800085df  inc     dword ptr [rbx+18h]
0x1800085e2  add     dword ptr [rsi+20h], 0FFFFFFFFh
0x1800085e6  jnz     short loc_180008642
0x1800085e8  cmp     dword ptr [rbx+18h], 1
0x1800085ec  jbe     short loc_180008642
0x1800085ee  mov     rcx, [rsi+8]; pv
0x1800085f2  call    cs:__imp_CoTaskMemFree
0x1800085f8  mov     rcx, [rsi]; pv
0x1800085fb  mov     [rsi+8], r12
0x1800085ff  call    cs:__imp_CoTaskMemFree
0x180008605  mov     rcx, rsi; pv
0x180008608  mov     [rsi], r12
0x18000860b  call    cs:__imp_CoTaskMemFree
0x180008611  mov     rax, [rbx+8]
0x180008615  mov     [r15+rax], r12
0x180008619  dec     dword ptr [rbx+18h]
0x18000861c  mov     rbp, [rsp+48h+arg_0]
0x180008621  mov     eax, r12d
0x180008624  mov     [rdi], r12d
0x180008627  mov     r14, [rsp+48h+var_20]
0x18000862c  mov     r12, [rsp+48h+var_18]
0x180008631  mov     rsi, [rsp+48h+arg_10]
0x180008636  mov     r15, [rsp+48h+var_28]
0x18000863b  add     rsp, 38h
0x18000863f  pop     rdi
0x180008640  pop     rbx
0x180008641  retn
0x180008642  cmp     r14d, [rbx+10h]
0x180008646  jnb     short loc_18000861C
0x180008648  mov     [rbx+10h], r14d
0x18000864c  jmp     short loc_18000861C
0x18000864e  mov     eax, 80070057h
0x180008653  jmp     short loc_18000863B
0x180008655  mov     eax, 80004005h
0x18000865a  jmp     short loc_18000863B
0x18000865c  mov     eax, 80070057h
0x180008661  jmp     short loc_180008627
```
