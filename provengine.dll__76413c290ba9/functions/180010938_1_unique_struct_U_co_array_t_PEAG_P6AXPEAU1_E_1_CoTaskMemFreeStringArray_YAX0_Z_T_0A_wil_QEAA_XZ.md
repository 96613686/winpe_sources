# ??1?$unique_struct@U?$co_array_t@PEAG@@P6AXPEAU1@@_E$1?CoTaskMemFreeStringArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ

- ea: `0x180010938`
- end: `0x180010990`
- name: `??1?$unique_struct@U?$co_array_t@PEAG@@P6AXPEAU1@@_E$1?CoTaskMemFreeStringArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ`
- size: `88`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044752`

## callees

- `0x180010938`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010973`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010973`

## pseudocode

```c
void __fastcall __1__unique_struct_U__co_array_t_PEAG__P6AXPEAU1___E_1_CoTaskMemFreeStringArray__YAX0_Z__T_0A__wil__QEAA_XZ(
        __int64 a1)
{
  __int64 i; // rsi

  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
  {
    CoTaskMemFree(*(LPVOID *)(*(_QWORD *)a1 + 8 * i));
    *(_QWORD *)(*(_QWORD *)a1 + 8 * i) = 0;
  }
  CoTaskMemFree(*(LPVOID *)a1);
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180010938  mov     [rsp+arg_0], rbx
0x18001093d  mov     [rsp+arg_8], rsi
0x180010942  push    rdi
0x180010943  sub     rsp, 20h
0x180010947  xor     esi, esi
0x180010949  mov     rdi, rcx
0x18001094c  cmp     [rcx+8], esi
0x18001094f  jbe     short loc_180010970
0x180010951  mov     rcx, [rdi]
0x180010954  mov     rcx, [rcx+rsi*8]; pv
0x180010958  call    cs:__imp_CoTaskMemFree
0x18001095e  mov     rax, [rdi]
0x180010961  mov     qword ptr [rax+rsi*8], 0
0x180010969  inc     esi
0x18001096b  cmp     esi, [rdi+8]
0x18001096e  jb      short loc_180010951
0x180010970  mov     rcx, [rdi]; pv
0x180010973  call    cs:__imp_CoTaskMemFree
0x180010979  mov     rbx, [rsp+28h+arg_0]
0x18001097e  mov     rsi, [rsp+28h+arg_8]
0x180010983  mov     qword ptr [rdi], 0
0x18001098a  add     rsp, 20h
0x18001098e  pop     rdi
0x18001098f  retn
```
