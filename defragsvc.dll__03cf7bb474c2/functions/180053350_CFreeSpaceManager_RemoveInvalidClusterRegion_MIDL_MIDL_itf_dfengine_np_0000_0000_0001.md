# CFreeSpaceManager::RemoveInvalidClusterRegion(__MIDL___MIDL_itf_dfengine_np_0000_0000_0001)

- ea: `0x180053350`
- end: `0x1800533fe`
- name: `?RemoveInvalidClusterRegion@CFreeSpaceManager@@UEAAJU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@@Z`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180053350`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800533f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800533f1`

## string_xrefs

- `0x180053373`: `CFreeSpaceManager::RemoveInvalidClusterRegion`

## pseudocode

```c
__int64 __fastcall CFreeSpaceManager::RemoveInvalidClusterRegion(__int64 a1, _QWORD *a2)
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
    "CFreeSpaceManager::RemoveInvalidClusterRegion",
    387,
    1);
  v5 = *(_QWORD **)(a1 + 208);
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
      *(_QWORD *)(a1 + 208) = v8;
    CoTaskMemFree(v5);
    v4 = v9;
  }
  else
  {
LABEL_6:
    v9 = 1;
    v10 = 423;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v4;
}

```

## disassembly

```asm
0x180053350  mov     [rsp+arg_0], rbx
0x180053355  mov     [rsp+arg_8], rsi
0x18005335a  push    rdi
0x18005335b  sub     rsp, 60h
0x18005335f  mov     rdi, rdx
0x180053362  mov     rsi, rcx
0x180053365  mov     ebx, 1
0x18005336a  mov     r9d, ebx; unsigned __int16
0x18005336d  mov     r8d, 183h; unsigned __int16
0x180053373  lea     rdx, aCfreespacemana_6; "CFreeSpaceManager::RemoveInvalidCluster"...
0x18005337a  lea     rcx, [rsp+68h+var_48]; this
0x18005337f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180053384  nop
0x180053385  mov     rcx, [rsi+0D0h]; pv
0x18005338c  test    rcx, rcx
0x18005338f  jz      short loc_1800533B1
0x180053391  xor     edx, edx
0x180053393  mov     r8, [rdi]
0x180053396  cmp     [rcx], r8
0x180053399  jnz     short loc_1800533A5
0x18005339b  mov     rax, [rdi+8]
0x18005339f  cmp     [rcx+8], rax
0x1800533a3  jz      short loc_1800533DB
0x1800533a5  mov     rdx, rcx
0x1800533a8  mov     rcx, [rcx+10h]
0x1800533ac  test    rcx, rcx
0x1800533af  jnz     short loc_180053396
0x1800533b1  mov     [rsp+68h+var_48], ebx
0x1800533b5  mov     eax, 1A7h
0x1800533ba  mov     [rsp+68h+var_44], ax
0x1800533bf  lea     rcx, [rsp+68h+var_48]; this
0x1800533c4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800533c9  mov     eax, ebx
0x1800533cb  mov     rbx, [rsp+68h+arg_0]
0x1800533d0  mov     rsi, [rsp+68h+arg_8]
0x1800533d5  add     rsp, 60h
0x1800533d9  pop     rdi
0x1800533da  retn
0x1800533db  mov     rax, [rcx+10h]
0x1800533df  test    rdx, rdx
0x1800533e2  jz      short loc_1800533EA
0x1800533e4  mov     [rdx+10h], rax
0x1800533e8  jmp     short loc_1800533F1
0x1800533ea  mov     [rsi+0D0h], rax
0x1800533f1  call    cs:__imp_CoTaskMemFree
0x1800533f7  mov     ebx, [rsp+68h+var_48]
0x1800533fb  jmp     short loc_1800533BF
```
