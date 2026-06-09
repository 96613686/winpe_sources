# ??1?$unique_struct@U?$co_array_t@PEAG@@P6AXPEAU1@@_E$1?CoTaskMemFreeStringArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ

- ea: `0x18002cd2c`
- end: `0x18002cd84`
- name: `??1?$unique_struct@U?$co_array_t@PEAG@@P6AXPEAU1@@_E$1?CoTaskMemFreeStringArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ`
- size: `88`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d4da`

## callees

- `0x18002cd2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd67`

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
0x18002cd2c  mov     [rsp+arg_0], rbx
0x18002cd31  mov     [rsp+arg_8], rsi
0x18002cd36  push    rdi
0x18002cd37  sub     rsp, 20h
0x18002cd3b  xor     esi, esi
0x18002cd3d  mov     rdi, rcx
0x18002cd40  cmp     [rcx+8], esi
0x18002cd43  jbe     short loc_18002CD64
0x18002cd45  mov     rcx, [rdi]
0x18002cd48  mov     rcx, [rcx+rsi*8]; pv
0x18002cd4c  call    cs:__imp_CoTaskMemFree
0x18002cd52  mov     rax, [rdi]
0x18002cd55  mov     qword ptr [rax+rsi*8], 0
0x18002cd5d  inc     esi
0x18002cd5f  cmp     esi, [rdi+8]
0x18002cd62  jb      short loc_18002CD45
0x18002cd64  mov     rcx, [rdi]; pv
0x18002cd67  call    cs:__imp_CoTaskMemFree
0x18002cd6d  mov     rbx, [rsp+28h+arg_0]
0x18002cd72  mov     rsi, [rsp+28h+arg_8]
0x18002cd77  mov     qword ptr [rdi], 0
0x18002cd7e  add     rsp, 20h
0x18002cd82  pop     rdi
0x18002cd83  retn
```
