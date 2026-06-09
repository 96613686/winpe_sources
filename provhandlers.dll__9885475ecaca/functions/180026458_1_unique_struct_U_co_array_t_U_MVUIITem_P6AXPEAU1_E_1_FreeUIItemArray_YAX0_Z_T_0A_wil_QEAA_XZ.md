# ??1?$unique_struct@U?$co_array_t@U_MVUIITem@@@@P6AXPEAU1@@_E$1?FreeUIItemArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ

- ea: `0x180026458`
- end: `0x1800264b7`
- name: `??1?$unique_struct@U?$co_array_t@U_MVUIITem@@@@P6AXPEAU1@@_E$1?FreeUIItemArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ceb3`

## callees

- `0x180026458`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002647e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002649a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002647e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002649a`

## pseudocode

```c
void __fastcall __1__unique_struct_U__co_array_t_U_MVUIITem____P6AXPEAU1___E_1_FreeUIItemArray__YAX0_Z__T_0A__wil__QEAA_XZ(
        __int64 a1)
{
  unsigned int i; // esi
  __int64 v3; // rbx

  for ( i = 0; i < *(_DWORD *)(a1 + 8); *(_QWORD *)(*(_QWORD *)a1 + 8 * v3 + 8) = 0 )
  {
    v3 = 2LL * i;
    CoTaskMemFree(*(LPVOID *)(*(_QWORD *)a1 + 16LL * i++ + 8));
  }
  CoTaskMemFree(*(LPVOID *)a1);
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180026458  mov     [rsp+arg_0], rbx
0x18002645d  mov     [rsp+arg_8], rsi
0x180026462  push    rdi
0x180026463  sub     rsp, 20h
0x180026467  xor     esi, esi
0x180026469  mov     rdi, rcx
0x18002646c  cmp     [rcx+8], esi
0x18002646f  jbe     short loc_180026497
0x180026471  mov     rcx, [rdi]
0x180026474  mov     ebx, esi
0x180026476  add     rbx, rbx
0x180026479  mov     rcx, [rcx+rbx*8+8]; pv
0x18002647e  call    cs:__imp_CoTaskMemFree
0x180026484  mov     rax, [rdi]
0x180026487  inc     esi
0x180026489  mov     qword ptr [rax+rbx*8+8], 0
0x180026492  cmp     esi, [rdi+8]
0x180026495  jb      short loc_180026471
0x180026497  mov     rcx, [rdi]; pv
0x18002649a  call    cs:__imp_CoTaskMemFree
0x1800264a0  mov     rbx, [rsp+28h+arg_0]
0x1800264a5  mov     rsi, [rsp+28h+arg_8]
0x1800264aa  mov     qword ptr [rdi], 0
0x1800264b1  add     rsp, 20h
0x1800264b5  pop     rdi
0x1800264b6  retn
```
