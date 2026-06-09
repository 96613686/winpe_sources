# CRasLogger::CRasLogger(void)

- ea: `0x18000b824`
- end: `0x18000b85c`
- name: `??0CRasLogger@@QEAA@XZ`
- size: `56`
- prototype: `LPVOID *__fastcall(LPVOID *ppv)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800063dc`
- `0x180008194`
- `0x180009924`
- `0x18000a918`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b846`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b846`

## pseudocode

```c
LPVOID *__fastcall CRasLogger::CRasLogger(LPVOID *ppv)
{
  CoCreateInstance(&CLSID_NDFEtw, 0, 1u, &IID_INDFEtw, ppv);
  return ppv;
}

```

## disassembly

```asm
0x18000b824  push    rbx
0x18000b826  sub     rsp, 30h
0x18000b82a  xor     edx, edx; pUnkOuter
0x18000b82c  mov     [rsp+38h+ppv], rcx; ppv
0x18000b831  mov     rbx, rcx
0x18000b834  lea     r9, IID_INDFEtw; riid
0x18000b83b  lea     rcx, CLSID_NDFEtw; rclsid
0x18000b842  lea     r8d, [rdx+1]; dwClsContext
0x18000b846  call    cs:__imp_CoCreateInstance
0x18000b84d  nop     dword ptr [rax+rax+00h]
0x18000b852  mov     rax, rbx
0x18000b855  add     rsp, 30h
0x18000b859  pop     rbx
0x18000b85a  retn
```
