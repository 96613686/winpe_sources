# CTransactionToAuditLog::~CTransactionToAuditLog(void)

- ea: `0x180021b64`
- end: `0x180021bc5`
- name: `??1CTransactionToAuditLog@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800233d0`

## callees

- `0x180021e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021bb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021bb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTransactionToAuditLog::~CTransactionToAuditLog(LPVOID *this)
{
  *this = &CTransactionToAuditLog::`vftable';
  CTransactionToAuditLog::CleanConnection((CTransactionToAuditLog *)this);
  CoTaskMemFree(this[3]);
  CoTaskMemFree(this[5]);
  CoTaskMemFree(this[6]);
  CoTaskMemFree(this[7]);
  CoTaskMemFree(this[8]);
  CoTaskMemFree(this[9]);
}

```

## disassembly

```asm
0x180021b64  push    rbx
0x180021b66  sub     rsp, 20h
0x180021b6a  mov     rbx, rcx
0x180021b6d  lea     rax, ??_7CTransactionToAuditLog@@6B@; const CTransactionToAuditLog::`vftable'
0x180021b74  mov     [rcx], rax
0x180021b77  call    ?CleanConnection@CTransactionToAuditLog@@UEAAJXZ; CTransactionToAuditLog::CleanConnection(void)
0x180021b7c  nop
0x180021b7d  mov     rcx, [rbx+18h]; pv
0x180021b81  call    cs:__imp_CoTaskMemFree
0x180021b87  nop
0x180021b88  mov     rcx, [rbx+28h]; pv
0x180021b8c  call    cs:__imp_CoTaskMemFree
0x180021b92  nop
0x180021b93  mov     rcx, [rbx+30h]; pv
0x180021b97  call    cs:__imp_CoTaskMemFree
0x180021b9d  nop
0x180021b9e  mov     rcx, [rbx+38h]; pv
0x180021ba2  call    cs:__imp_CoTaskMemFree
0x180021ba8  nop
0x180021ba9  mov     rcx, [rbx+40h]; pv
0x180021bad  call    cs:__imp_CoTaskMemFree
0x180021bb3  nop
0x180021bb4  mov     rcx, [rbx+48h]; pv
0x180021bb8  call    cs:__imp_CoTaskMemFree
0x180021bbe  nop
0x180021bbf  add     rsp, 20h
0x180021bc3  pop     rbx
0x180021bc4  retn
```
