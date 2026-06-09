# CCfgArray<TMetabase_XMLtable::TProperty>::InsertAt(TMetabase_XMLtable::TProperty const &,ulong)

- ea: `0x18000c008`
- end: `0x18000c0a2`
- name: `?InsertAt@?$CCfgArray@VTProperty@TMetabase_XMLtable@@@@QEAAJAEBVTProperty@TMetabase_XMLtable@@K@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d110`

## callees

- `0x180006608`
- `0x18000c008`

## pseudocode

```c
__int64 __fastcall CCfgArray<TMetabase_XMLtable::TProperty>::InsertAt(__int64 a1, __int64 a2, unsigned int a3)
{
  int v3; // eax
  unsigned int v4; // r10d
  __int64 v6; // rdi
  unsigned int v8; // edx
  __int64 result; // rax
  unsigned int i; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx

  v3 = *(_DWORD *)(a1 + 8);
  v4 = 0;
  v6 = a3;
  if ( *(_DWORD *)(a1 + 12) != v3 )
    goto LABEL_5;
  v8 = 1;
  if ( v3 )
    v8 = 2 * v3;
  result = CCfgArray<TMetabase_XMLtable::TProperty>::AllocNewSize(a1, v8);
  v4 = result;
  if ( (int)result >= 0 )
  {
LABEL_5:
    for ( i = *(_DWORD *)(a1 + 12); i > (unsigned int)v6; --i )
    {
      v11 = *(_QWORD *)a1;
      v12 = 2LL * i;
      *(_QWORD *)(v11 + 8 * v12 + 8) = *(_QWORD *)(*(_QWORD *)a1 + 16LL * (i - 1) + 8);
      *(_DWORD *)(v11 + 8 * v12) = *(_DWORD *)(v11 + 16LL * (i - 1));
    }
    v13 = *(_QWORD *)a1;
    v14 = 2 * v6;
    *(_QWORD *)(v13 + 8 * v14 + 8) = *(_QWORD *)(a2 + 8);
    *(_DWORD *)(v13 + 8 * v14) = *(_DWORD *)a2;
    result = v4;
    ++*(_DWORD *)(a1 + 12);
  }
  return result;
}

```

## disassembly

```asm
0x18000c008  mov     [rsp+arg_0], rbx
0x18000c00d  mov     [rsp+arg_8], rsi
0x18000c012  push    rdi
0x18000c013  sub     rsp, 20h
0x18000c017  mov     eax, [rcx+8]
0x18000c01a  xor     r10d, r10d
0x18000c01d  mov     rsi, rdx
0x18000c020  mov     edi, r8d
0x18000c023  mov     rbx, rcx
0x18000c026  cmp     [rcx+0Ch], eax
0x18000c029  jnz     short loc_18000C042
0x18000c02b  lea     edx, [r10+1]
0x18000c02f  test    eax, eax
0x18000c031  jz      short loc_18000C036
0x18000c033  lea     edx, [rax+rax]
0x18000c036  call    ?AllocNewSize@?$CCfgArray@VTProperty@TMetabase_XMLtable@@@@AEAAJK@Z; CCfgArray<TMetabase_XMLtable::TProperty>::AllocNewSize(ulong)
0x18000c03b  mov     r10d, eax
0x18000c03e  test    eax, eax
0x18000c040  js      short loc_18000C092
0x18000c042  mov     eax, [rbx+0Ch]
0x18000c045  cmp     eax, edi
0x18000c047  jbe     short loc_18000C075
0x18000c049  mov     r8, [rbx]
0x18000c04c  lea     r9d, [rax-1]
0x18000c050  mov     ecx, eax
0x18000c052  add     rcx, rcx
0x18000c055  mov     edx, r9d
0x18000c058  add     rdx, rdx
0x18000c05b  mov     rax, [r8+rdx*8+8]
0x18000c060  mov     [r8+rcx*8+8], rax
0x18000c065  mov     eax, [r8+rdx*8]
0x18000c069  mov     [r8+rcx*8], eax
0x18000c06d  mov     eax, r9d
0x18000c070  cmp     r9d, edi
0x18000c073  ja      short loc_18000C049
0x18000c075  mov     rax, [rsi+8]
0x18000c079  mov     rdx, rdi
0x18000c07c  mov     rcx, [rbx]
0x18000c07f  add     rdx, rdx
0x18000c082  mov     [rcx+rdx*8+8], rax
0x18000c087  mov     eax, [rsi]
0x18000c089  mov     [rcx+rdx*8], eax
0x18000c08c  mov     eax, r10d
0x18000c08f  inc     dword ptr [rbx+0Ch]
0x18000c092  mov     rbx, [rsp+28h+arg_0]
0x18000c097  mov     rsi, [rsp+28h+arg_8]
0x18000c09c  add     rsp, 20h
0x18000c0a0  pop     rdi
0x18000c0a1  retn
```
