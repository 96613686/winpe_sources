# CFreeSlabManager::RemoveInvalidClusterRegion(__MIDL___MIDL_itf_dfengine_np_0000_0000_0001)

- ea: `0x1800564b0`
- end: `0x180056558`
- name: `?RemoveInvalidClusterRegion@CFreeSlabManager@@UEAAJU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@@Z`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800564b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005654b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005654b`

## string_xrefs

- `0x1800564d3`: `CFreeSlabManager::RemoveInvalidClusterRegion`

## pseudocode

```c
__int64 __fastcall CFreeSlabManager::RemoveInvalidClusterRegion(__int64 a1, _QWORD *a2)
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
    "CFreeSlabManager::RemoveInvalidClusterRegion",
    1074,
    1);
  v5 = *(_QWORD **)(a1 + 112);
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
      *(_QWORD *)(a1 + 112) = v8;
    CoTaskMemFree(v5);
    v4 = v9;
  }
  else
  {
LABEL_6:
    v9 = 1;
    v10 = 1110;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v4;
}

```

## disassembly

```asm
0x1800564b0  mov     [rsp+arg_0], rbx
0x1800564b5  mov     [rsp+arg_8], rsi
0x1800564ba  push    rdi
0x1800564bb  sub     rsp, 60h
0x1800564bf  mov     rdi, rdx
0x1800564c2  mov     rsi, rcx
0x1800564c5  mov     ebx, 1
0x1800564ca  mov     r9d, ebx; unsigned __int16
0x1800564cd  mov     r8d, 432h; unsigned __int16
0x1800564d3  lea     rdx, aCfreeslabmanag_24; "CFreeSlabManager::RemoveInvalidClusterR"...
0x1800564da  lea     rcx, [rsp+68h+var_48]; this
0x1800564df  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800564e4  nop
0x1800564e5  mov     rcx, [rsi+70h]; pv
0x1800564e9  test    rcx, rcx
0x1800564ec  jz      short loc_18005650E
0x1800564ee  xor     edx, edx
0x1800564f0  mov     r8, [rdi]
0x1800564f3  cmp     [rcx], r8
0x1800564f6  jnz     short loc_180056502
0x1800564f8  mov     rax, [rdi+8]
0x1800564fc  cmp     [rcx+8], rax
0x180056500  jz      short loc_180056538
0x180056502  mov     rdx, rcx
0x180056505  mov     rcx, [rcx+10h]
0x180056509  test    rcx, rcx
0x18005650c  jnz     short loc_1800564F3
0x18005650e  mov     [rsp+68h+var_48], ebx
0x180056512  mov     eax, 456h
0x180056517  mov     [rsp+68h+var_44], ax
0x18005651c  lea     rcx, [rsp+68h+var_48]; this
0x180056521  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180056526  mov     eax, ebx
0x180056528  mov     rbx, [rsp+68h+arg_0]
0x18005652d  mov     rsi, [rsp+68h+arg_8]
0x180056532  add     rsp, 60h
0x180056536  pop     rdi
0x180056537  retn
0x180056538  mov     rax, [rcx+10h]
0x18005653c  test    rdx, rdx
0x18005653f  jz      short loc_180056547
0x180056541  mov     [rdx+10h], rax
0x180056545  jmp     short loc_18005654B
0x180056547  mov     [rsi+70h], rax
0x18005654b  call    cs:__imp_CoTaskMemFree
0x180056551  mov     ebx, [rsp+68h+var_48]
0x180056555  jmp     short loc_18005651C
```
