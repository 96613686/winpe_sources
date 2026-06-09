# CTieredFreeSpaceManager::RemoveInvalidClusterRegion(__MIDL___MIDL_itf_dfengine_np_0000_0000_0001)

- ea: `0x1800596a0`
- end: `0x18005974e`
- name: `?RemoveInvalidClusterRegion@CTieredFreeSpaceManager@@UEAAJU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@@Z`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800596a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059741`

## string_xrefs

- `0x1800596c3`: `CTieredFreeSpaceManager::RemoveInvalidClusterRegion`

## pseudocode

```c
__int64 __fastcall CTieredFreeSpaceManager::RemoveInvalidClusterRegion(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  _QWORD *v6; // rdx
  __int64 v8; // rax
  int v9; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]

  v4 = 1;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v9,
    "CTieredFreeSpaceManager::RemoveInvalidClusterRegion",
    518,
    1);
  v5 = *(_QWORD **)(a1 + 160);
  if ( v5 )
  {
    v6 = 0;
    while ( *v5 != *a2 || v5[1] != a2[1] )
    {
      v6 = v5;
      v5 = (_QWORD *)v5[2];
      if ( !v5 )
        goto LABEL_6;
    }
    v8 = v5[2];
    if ( v6 )
      v6[2] = v8;
    else
      *(_QWORD *)(a1 + 160) = v8;
    CoTaskMemFree(v5);
    v4 = v9;
  }
  else
  {
LABEL_6:
    v9 = 1;
    v10 = 554;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v4;
}

```

## disassembly

```asm
0x1800596a0  mov     [rsp+arg_0], rbx
0x1800596a5  mov     [rsp+arg_8], rsi
0x1800596aa  push    rdi
0x1800596ab  sub     rsp, 60h
0x1800596af  mov     rdi, rdx
0x1800596b2  mov     rsi, rcx
0x1800596b5  mov     ebx, 1
0x1800596ba  mov     r9d, ebx; unsigned __int16
0x1800596bd  mov     r8d, 206h; unsigned __int16
0x1800596c3  lea     rdx, aCtieredfreespa_4; "CTieredFreeSpaceManager::RemoveInvalidC"...
0x1800596ca  lea     rcx, [rsp+68h+var_48]; this
0x1800596cf  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800596d4  nop
0x1800596d5  mov     rcx, [rsi+0A0h]; pv
0x1800596dc  test    rcx, rcx
0x1800596df  jz      short loc_180059701
0x1800596e1  xor     edx, edx
0x1800596e3  mov     r8, [rdi]
0x1800596e6  cmp     [rcx], r8
0x1800596e9  jnz     short loc_1800596F5
0x1800596eb  mov     rax, [rdi+8]
0x1800596ef  cmp     [rcx+8], rax
0x1800596f3  jz      short loc_18005972B
0x1800596f5  mov     rdx, rcx
0x1800596f8  mov     rcx, [rcx+10h]
0x1800596fc  test    rcx, rcx
0x1800596ff  jnz     short loc_1800596E6
0x180059701  mov     [rsp+68h+var_48], ebx
0x180059705  mov     eax, 22Ah
0x18005970a  mov     [rsp+68h+var_44], ax
0x18005970f  lea     rcx, [rsp+68h+var_48]; this
0x180059714  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180059719  mov     eax, ebx
0x18005971b  mov     rbx, [rsp+68h+arg_0]
0x180059720  mov     rsi, [rsp+68h+arg_8]
0x180059725  add     rsp, 60h
0x180059729  pop     rdi
0x18005972a  retn
0x18005972b  mov     rax, [rcx+10h]
0x18005972f  test    rdx, rdx
0x180059732  jz      short loc_18005973A
0x180059734  mov     [rdx+10h], rax
0x180059738  jmp     short loc_180059741
0x18005973a  mov     [rsi+0A0h], rax
0x180059741  call    cs:__imp_CoTaskMemFree
0x180059747  mov     ebx, [rsp+68h+var_48]
0x18005974b  jmp     short loc_18005970F
```
