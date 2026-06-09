# Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~Map<ushort const *,MyDataEntry *,HashWSTR,EmptyMapBase>(void)

- ea: `0x1800065f0`
- end: `0x180006677`
- name: `??1?$Map@PEBGPEAUMyDataEntry@@VHashWSTR@@VEmptyMapBase@@@@QEAA@XZ`
- size: `135`
- prototype: `__int64 *__fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021b38`
- `0x180035214`
- `0x180037990`
- `0x180039dc0`
- `0x180056476`
- `0x1800564c2`

## callees

- `0x1800065f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000663d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000663d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006650`

## pseudocode

```c
__int64 *__fastcall Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>::~Map<unsigned short const *,MyDataEntry *,HashWSTR,EmptyMapBase>(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 *v3; // rcx
  __int64 *v4; // rdx
  __int64 v5; // rax
  _QWORD *i; // rcx
  _QWORD *v7; // rcx
  __int64 *result; // rax

  v2 = a1 + 24;
  while ( 1 )
  {
    v3 = *(__int64 **)v2;
    if ( *(_QWORD *)v2 == v2 )
      break;
    if ( v3 )
    {
      v4 = (__int64 *)v3[1];
      v5 = *v3;
      *v4 = *v3;
      *(_QWORD *)(v5 + 8) = v4;
      *v3 = (__int64)v3;
      v3[1] = (__int64)v3;
      CoTaskMemFree(v3);
    }
  }
  for ( i = *(_QWORD **)(a1 + 16); i; i = *(_QWORD **)(a1 + 16) )
  {
    *(_QWORD *)(a1 + 16) = i[2];
    CoTaskMemFree(i);
  }
  CoTaskMemFree(*(LPVOID *)a1);
  v7 = *(_QWORD **)(v2 + 8);
  result = *(__int64 **)v2;
  *v7 = *(_QWORD *)v2;
  result[1] = (__int64)v7;
  *(_QWORD *)v2 = v2;
  *(_QWORD *)(v2 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x1800065f0  mov     [rsp+arg_0], rbx
0x1800065f5  push    rdi
0x1800065f6  sub     rsp, 20h
0x1800065fa  mov     rdi, rcx
0x1800065fd  lea     rbx, [rcx+18h]
0x180006601  mov     rcx, [rbx]; pv
0x180006604  cmp     rcx, rbx
0x180006607  jz      short loc_18000662C
0x180006609  test    rcx, rcx
0x18000660c  jz      short loc_180006601
0x18000660e  mov     rdx, [rcx+8]
0x180006612  mov     rax, [rcx]
0x180006615  mov     [rdx], rax
0x180006618  mov     [rax+8], rdx
0x18000661c  mov     [rcx], rcx
0x18000661f  mov     [rcx+8], rcx
0x180006623  call    cs:__imp_CoTaskMemFree
0x180006629  nop
0x18000662a  jmp     short loc_180006601
0x18000662c  mov     rcx, [rdi+10h]; pv
0x180006630  test    rcx, rcx
0x180006633  jz      short loc_18000664D
0x180006635  mov     rax, [rcx+10h]
0x180006639  mov     [rdi+10h], rax
0x18000663d  call    cs:__imp_CoTaskMemFree
0x180006643  nop
0x180006644  mov     rcx, [rdi+10h]
0x180006648  test    rcx, rcx
0x18000664b  jnz     short loc_180006635
0x18000664d  mov     rcx, [rdi]; pv
0x180006650  call    cs:__imp_CoTaskMemFree
0x180006656  nop
0x180006657  mov     rcx, [rbx+8]
0x18000665b  mov     rax, [rbx]
0x18000665e  mov     [rcx], rax
0x180006661  mov     [rax+8], rcx
0x180006665  mov     [rbx], rbx
0x180006668  mov     [rbx+8], rbx
0x18000666c  mov     rbx, [rsp+28h+arg_0]
0x180006671  add     rsp, 20h
0x180006675  pop     rdi
0x180006676  retn
```
