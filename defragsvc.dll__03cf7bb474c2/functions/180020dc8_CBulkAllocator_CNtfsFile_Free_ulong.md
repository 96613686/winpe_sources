# CBulkAllocator<CNtfsFile>::Free(ulong *)

- ea: `0x180020dc8`
- end: `0x180020ebd`
- name: `?Free@?$CBulkAllocator@VCNtfsFile@@@@QEAAJPEAK@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003d84`

## callees

- `0x180020dc8`

## import_xrefs

- `ntdll!RtlClearBits` at `0x180020e3e`
- `ntdll!RtlClearBits` at `0x180020e3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020ea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020ea3`

## pseudocode

```c
__int64 __fastcall CBulkAllocator<CNtfsFile>::Free(__int64 a1, unsigned int *a2)
{
  unsigned int v4; // edx
  int v5; // ecx
  int v6; // r9d
  __int64 v7; // rdx
  ULONG v8; // r9d
  __int64 v9; // rbp
  struct _RTL_BITMAP *v10; // rsi
  unsigned int v11; // ebx
  bool v12; // zf
  void *v14; // rcx

  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( !*(_DWORD *)(a1 + 28) )
    return (unsigned int)-2147467259;
  v4 = *a2;
  if ( (v4 & 0xF0000000) == *(_DWORD *)(a1 + 28)
    && v4
    && (v5 = (unsigned __int16)v4 - 1,
        v6 = -((unsigned __int16)v4 != 0),
        v7 = HIWORD(v4) & 0xFFF,
        v8 = v5 & v6,
        v9 = (unsigned int)v7,
        (v10 = *(struct _RTL_BITMAP **)(*(_QWORD *)(a1 + 8) + 8 * v7)) != 0)
    && v8 < *(_DWORD *)(a1 + 20) )
  {
    v11 = 0;
    RtlClearBits(v10 + 1, v8, 1u);
    if ( v10[2].SizeOfBitMap == *(_DWORD *)(a1 + 20) )
      ++*(_DWORD *)(a1 + 24);
    v12 = v10[2].SizeOfBitMap-- == 1;
    if ( v12 && *(_DWORD *)(a1 + 24) > 1u )
    {
      CoTaskMemFree(v10->Buffer);
      v14 = *(void **)&v10->SizeOfBitMap;
      v10->Buffer = 0;
      CoTaskMemFree(v14);
      *(_QWORD *)&v10->SizeOfBitMap = 0;
      CoTaskMemFree(v10);
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v9) = 0;
      --*(_DWORD *)(a1 + 24);
    }
    else if ( (unsigned int)v9 < *(_DWORD *)(a1 + 16) )
    {
      *(_DWORD *)(a1 + 16) = v9;
    }
    *a2 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x180020dc8  mov     [rsp+arg_0], rbx
0x180020dcd  mov     [rsp+arg_10], rbp
0x180020dd2  push    rsi
0x180020dd3  push    rdi
0x180020dd4  push    r14
0x180020dd6  sub     rsp, 20h
0x180020dda  mov     r14, rdx
0x180020ddd  mov     rdi, rcx
0x180020de0  test    rdx, rdx
0x180020de3  jz      loc_180020E6F
0x180020de9  cmp     dword ptr [rcx+1Ch], 0
0x180020ded  jbe     loc_180020EB6
0x180020df3  mov     edx, [rdx]
0x180020df5  mov     eax, edx
0x180020df7  and     eax, 0F0000000h
0x180020dfc  cmp     eax, [rcx+1Ch]
0x180020dff  jnz     short loc_180020E6F
0x180020e01  test    edx, edx
0x180020e03  jz      short loc_180020E6F
0x180020e05  movzx   eax, dx
0x180020e08  lea     ecx, [rax-1]
0x180020e0b  neg     eax
0x180020e0d  mov     rax, [rdi+8]
0x180020e11  sbb     r9d, r9d
0x180020e14  shr     edx, 10h
0x180020e17  and     edx, 0FFFh
0x180020e1d  and     r9d, ecx
0x180020e20  mov     ebp, edx
0x180020e22  mov     rsi, [rax+rdx*8]
0x180020e26  test    rsi, rsi
0x180020e29  jz      short loc_180020E6F
0x180020e2b  cmp     r9d, [rdi+14h]
0x180020e2f  jnb     short loc_180020E6F
0x180020e31  xor     ebx, ebx
0x180020e33  lea     rcx, [rsi+10h]; BitMapHeader
0x180020e37  mov     edx, r9d; StartingIndex
0x180020e3a  lea     r8d, [rbx+1]; NumberToClear
0x180020e3e  call    cs:__imp_RtlClearBits
0x180020e44  mov     eax, [rdi+14h]
0x180020e47  cmp     [rsi+20h], eax
0x180020e4a  jz      short loc_180020E76
0x180020e4c  add     dword ptr [rsi+20h], 0FFFFFFFFh
0x180020e50  jz      short loc_180020E80
0x180020e52  cmp     ebp, [rdi+10h]
0x180020e55  jb      short loc_180020E7B
0x180020e57  mov     [r14], ebx
0x180020e5a  mov     rbp, [rsp+38h+arg_10]
0x180020e5f  mov     eax, ebx
0x180020e61  mov     rbx, [rsp+38h+arg_0]
0x180020e66  add     rsp, 20h
0x180020e6a  pop     r14
0x180020e6c  pop     rdi
0x180020e6d  pop     rsi
0x180020e6e  retn
0x180020e6f  mov     ebx, 80070057h
0x180020e74  jmp     short loc_180020E5A
0x180020e76  inc     dword ptr [rdi+18h]
0x180020e79  jmp     short loc_180020E4C
0x180020e7b  mov     [rdi+10h], ebp
0x180020e7e  jmp     short loc_180020E57
0x180020e80  cmp     dword ptr [rdi+18h], 1
0x180020e84  jbe     short loc_180020E52
0x180020e86  mov     rcx, [rsi+8]; pv
0x180020e8a  call    cs:__imp_CoTaskMemFree
0x180020e90  mov     rcx, [rsi]; pv
0x180020e93  mov     [rsi+8], rbx
0x180020e97  call    cs:__imp_CoTaskMemFree
0x180020e9d  mov     rcx, rsi; pv
0x180020ea0  mov     [rsi], rbx
0x180020ea3  call    cs:__imp_CoTaskMemFree
0x180020ea9  mov     rax, [rdi+8]
0x180020ead  mov     [rax+rbp*8], rbx
0x180020eb1  dec     dword ptr [rdi+18h]
0x180020eb4  jmp     short loc_180020E57
0x180020eb6  mov     ebx, 80004005h
0x180020ebb  jmp     short loc_180020E5A
```
