# ScopeWarden__lambda_172b3fc694a75670e74f2c2a788e5205___::_ScopeWarden__lambda_172b3fc694a75670e74f2c2a788e5205___

- ea: `0x1802ce7d0`
- end: `0x1802ce86a`
- name: `ScopeWarden__lambda_172b3fc694a75670e74f2c2a788e5205___::_ScopeWarden__lambda_172b3fc694a75670e74f2c2a788e5205___`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18012d088`
- `0x180327e94`

## callees

- `0x180104d30`
- `0x1802ce7d0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce7f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce838`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce84a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce7f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce838`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ce84a`

## pseudocode

```c
_DWORD *__fastcall ScopeWarden__lambda_172b3fc694a75670e74f2c2a788e5205___::_ScopeWarden__lambda_172b3fc694a75670e74f2c2a788e5205___(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  _DWORD *result; // rax
  __int64 v3; // rbx
  __int64 v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    try
    {
      result = (_DWORD *)*v1;
      if ( !*(_DWORD *)*v1 )
      {
        v3 = v1[1];
        CoTaskMemFree(*(LPVOID *)(v3 + 8));
        v4 = *(_QWORD *)(v3 + 168);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        CoTaskMemFree(*(LPVOID *)(v3 + 40));
        *(_QWORD *)(v3 + 40) = 0;
        CoTaskMemFree(*(LPVOID *)(v3 + 56));
        *(_QWORD *)(v3 + 56) = 0;
        CoTaskMemFree(*(LPVOID *)(v3 + 64));
        *(_QWORD *)(v3 + 64) = 0;
        CoTaskMemFree(*(LPVOID *)(v3 + 72));
        *(_QWORD *)(v3 + 72) = 0;
        result = (_DWORD *)FreeCDPComEndpoint(v3 + 80);
      }
    }
    catch ( ... )
    {
    }
  }
  return result;
}

```

## disassembly

```asm
0x1802ce7d0  push    rbx
0x1802ce7d2  sub     rsp, 20h
0x1802ce7d6  mov     rbx, [rcx]
0x1802ce7d9  test    rbx, rbx
0x1802ce7dc  jz      loc_1802CE864
0x1802ce7e2  mov     rax, [rbx]
0x1802ce7e5  cmp     dword ptr [rax], 0
0x1802ce7e8  jnz     short loc_1802CE862
0x1802ce7ea  mov     rbx, [rbx+8]
0x1802ce7ee  mov     rcx, [rbx+8]; pv
0x1802ce7f2  call    cs:__imp_CoTaskMemFree
0x1802ce7f8  mov     rcx, [rbx+0A8h]
0x1802ce7ff  test    rcx, rcx
0x1802ce802  jz      short loc_1802CE810
0x1802ce804  mov     rax, [rcx]
0x1802ce807  mov     rax, [rax+10h]
0x1802ce80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ce810  mov     rcx, [rbx+28h]; pv
0x1802ce814  call    cs:__imp_CoTaskMemFree
0x1802ce81a  mov     qword ptr [rbx+28h], 0
0x1802ce822  mov     rcx, [rbx+38h]; pv
0x1802ce826  call    cs:__imp_CoTaskMemFree
0x1802ce82c  mov     qword ptr [rbx+38h], 0
0x1802ce834  mov     rcx, [rbx+40h]; pv
0x1802ce838  call    cs:__imp_CoTaskMemFree
0x1802ce83e  mov     qword ptr [rbx+40h], 0
0x1802ce846  mov     rcx, [rbx+48h]; pv
0x1802ce84a  call    cs:__imp_CoTaskMemFree
0x1802ce850  mov     qword ptr [rbx+48h], 0
0x1802ce858  lea     rcx, [rbx+50h]
0x1802ce85c  call    FreeCDPComEndpoint
0x1802ce861  nop
0x1802ce862  jmp     short $+2
0x1802ce864  add     rsp, 20h
0x1802ce868  pop     rbx
0x1802ce869  retn
```
