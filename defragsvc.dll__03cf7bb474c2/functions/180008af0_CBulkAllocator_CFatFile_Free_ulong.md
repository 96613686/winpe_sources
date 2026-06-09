# CBulkAllocator<CFatFile>::Free(ulong *)

- ea: `0x180008af0`
- end: `0x180008c2a`
- name: `?Free@?$CBulkAllocator@VCFatFile@@@@QEAAJPEAK@Z`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008980`
- `0x1800164ac`

## callees

- `0x180008af0`

## import_xrefs

- `ntdll!RtlClearBits` at `0x180008b90`
- `ntdll!RtlClearBits` at `0x180008b90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bca`

## pseudocode

```c
__int64 __fastcall CBulkAllocator<CFatFile>::Free(__int64 a1, unsigned int *a2)
{
  int v4; // ecx
  unsigned int v5; // edx
  ULONG v6; // r9d
  __int64 v7; // rdx
  unsigned int v8; // ebp
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
0x180008af0  push    rbx
0x180008af2  push    rdi
0x180008af3  sub     rsp, 38h
0x180008af7  mov     rdi, rdx
0x180008afa  mov     rbx, rcx
0x180008afd  test    rdx, rdx
0x180008b00  jz      loc_180008C17
0x180008b06  mov     ecx, [rcx+1Ch]
0x180008b09  test    ecx, ecx
0x180008b0b  jz      loc_180008C01
0x180008b11  mov     edx, [rdx]
0x180008b13  mov     eax, edx
0x180008b15  and     eax, 0F0000000h
0x180008b1a  cmp     eax, ecx
0x180008b1c  jnz     loc_180008C17
0x180008b22  test    edx, edx
0x180008b24  jz      loc_180008C17
0x180008b2a  mov     [rsp+48h+arg_0], rbp
0x180008b2f  movzx   ecx, dx
0x180008b32  mov     [rsp+48h+arg_10], rsi
0x180008b37  mov     [rsp+48h+var_18], r12
0x180008b3c  xor     r12d, r12d
0x180008b3f  test    ecx, ecx
0x180008b41  mov     [rsp+48h+var_28], r15
0x180008b46  lea     eax, [rcx-1]
0x180008b49  mov     r9d, r12d
0x180008b4c  cmovnz  r9d, eax
0x180008b50  mov     rax, [rbx+8]
0x180008b54  shr     edx, 10h
0x180008b57  and     edx, 0FFFh
0x180008b5d  mov     ebp, edx
0x180008b5f  lea     r15, ds:0[rdx*8]
0x180008b67  mov     rsi, [r15+rax]
0x180008b6b  test    rsi, rsi
0x180008b6e  jz      loc_180008C23
0x180008b74  cmp     r9d, [rbx+14h]
0x180008b78  jnb     loc_180008C23
0x180008b7e  lea     rcx, [rsi+10h]; BitMapHeader
0x180008b82  mov     [rsp+48h+var_20], r14
0x180008b87  mov     r8d, 1; NumberToClear
0x180008b8d  mov     edx, r9d; StartingIndex
0x180008b90  call    cs:__imp_RtlClearBits
0x180008b96  mov     eax, [rbx+14h]
0x180008b99  cmp     [rsi+20h], eax
0x180008b9c  jnz     short loc_180008BA1
0x180008b9e  inc     dword ptr [rbx+18h]
0x180008ba1  add     dword ptr [rsi+20h], 0FFFFFFFFh
0x180008ba5  jnz     short loc_180008C0D
0x180008ba7  cmp     dword ptr [rbx+18h], 1
0x180008bab  jbe     short loc_180008C0D
0x180008bad  mov     rcx, [rsi+8]; pv
0x180008bb1  call    cs:__imp_CoTaskMemFree
0x180008bb7  mov     rcx, [rsi]; pv
0x180008bba  mov     [rsi+8], r12
0x180008bbe  call    cs:__imp_CoTaskMemFree
0x180008bc4  mov     rcx, rsi; pv
0x180008bc7  mov     [rsi], r12
0x180008bca  call    cs:__imp_CoTaskMemFree
0x180008bd0  mov     rax, [rbx+8]
0x180008bd4  mov     [r15+rax], r12
0x180008bd8  dec     dword ptr [rbx+18h]
0x180008bdb  mov     r14, [rsp+48h+var_20]
0x180008be0  mov     eax, r12d
0x180008be3  mov     [rdi], r12d
0x180008be6  mov     r12, [rsp+48h+var_18]
0x180008beb  mov     rsi, [rsp+48h+arg_10]
0x180008bf0  mov     rbp, [rsp+48h+arg_0]
0x180008bf5  mov     r15, [rsp+48h+var_28]
0x180008bfa  add     rsp, 38h
0x180008bfe  pop     rdi
0x180008bff  pop     rbx
0x180008c00  retn
0x180008c01  mov     eax, 80004005h
0x180008c06  add     rsp, 38h
0x180008c0a  pop     rdi
0x180008c0b  pop     rbx
0x180008c0c  retn
0x180008c0d  cmp     ebp, [rbx+10h]
0x180008c10  jnb     short loc_180008BDB
0x180008c12  mov     [rbx+10h], ebp
0x180008c15  jmp     short loc_180008BDB
0x180008c17  mov     eax, 80070057h
0x180008c1c  add     rsp, 38h
0x180008c20  pop     rdi
0x180008c21  pop     rbx
0x180008c22  retn
0x180008c23  mov     eax, 80070057h
0x180008c28  jmp     short loc_180008BE6
```
