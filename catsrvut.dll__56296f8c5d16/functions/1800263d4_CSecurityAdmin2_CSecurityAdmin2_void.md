# CSecurityAdmin2::CSecurityAdmin2(void)

- ea: `0x1800263d4`
- end: `0x1800264fc`
- name: `??0CSecurityAdmin2@@QEAA@XZ`
- size: `296`
- prototype: `CSecurityAdmin2 *__fastcall(CSecurityAdmin2 *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026924`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002644e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002646d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002648a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800264a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800264b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800264cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800264e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002644e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002646d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002648a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800264a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800264b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800264cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800264e2`

## pseudocode

```c
CSecurityAdmin2 *__fastcall CSecurityAdmin2::CSecurityAdmin2(CSecurityAdmin2 *this)
{
  LPVOID *ppv; // rbx
  LPVOID *v3; // rdi
  LPVOID *v4; // rsi
  LPVOID *v5; // r14
  LPVOID *v6; // r15
  LPVOID *v7; // rbp

  *(_QWORD *)this = &CSecurityAdmin2::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  ppv = (LPVOID *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  v3 = (LPVOID *)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  v4 = (LPVOID *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  v5 = (LPVOID *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  v6 = (LPVOID *)((char *)this + 56);
  *((_QWORD *)this + 7) = 0;
  v7 = (LPVOID *)((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)this + 2);
  CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, ppv);
  CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, v3);
  CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, v4);
  CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, v5);
  CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, v6);
  CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, v7);
  return this;
}

```

## disassembly

```asm
0x1800263d4  push    rbx
0x1800263d6  push    rbp
0x1800263d7  push    rsi
0x1800263d8  push    rdi
0x1800263d9  push    r12
0x1800263db  push    r13
0x1800263dd  push    r14
0x1800263df  push    r15
0x1800263e1  sub     rsp, 38h
0x1800263e5  mov     r12, rcx
0x1800263e8  lea     rax, ??_7CSecurityAdmin2@@6B@; const CSecurityAdmin2::`vftable'
0x1800263ef  mov     [rcx], rax
0x1800263f2  lea     r13, CLSID_STDispenser
0x1800263f9  xor     ecx, ecx
0x1800263fb  lea     r9, IID_ISimpleTableDispenser; riid
0x180026402  xor     edx, edx; pUnkOuter
0x180026404  lea     rax, [r12+10h]
0x180026409  mov     [r12+8], ecx
0x18002640e  mov     [rax], rcx
0x180026411  lea     rbx, [r12+18h]
0x180026416  lea     r8d, [rcx+1]; dwClsContext
0x18002641a  mov     [rbx], rcx
0x18002641d  lea     rdi, [r12+20h]
0x180026422  mov     [rsp+78h+ppv], rax; ppv
0x180026427  mov     [rdi], rcx
0x18002642a  lea     rsi, [r12+28h]
0x18002642f  mov     [rsi], rcx
0x180026432  lea     r14, [r12+30h]
0x180026437  mov     [r14], rcx
0x18002643a  lea     r15, [r12+38h]
0x18002643f  mov     [r15], rcx
0x180026442  lea     rbp, [r12+40h]
0x180026447  mov     [rbp+0], rcx
0x18002644b  mov     rcx, r13; rclsid
0x18002644e  call    cs:__imp_CoCreateInstance
0x180026454  mov     [rsp+78h+ppv], rbx; ppv
0x180026459  lea     r9, IID_ISimpleTableDispenser; riid
0x180026460  mov     ebx, 1
0x180026465  xor     edx, edx; pUnkOuter
0x180026467  mov     r8d, ebx; dwClsContext
0x18002646a  mov     rcx, r13; rclsid
0x18002646d  call    cs:__imp_CoCreateInstance
0x180026473  mov     [rsp+78h+ppv], rdi; ppv
0x180026478  mov     r8d, ebx; dwClsContext
0x18002647b  lea     rdi, IID_ISimpleTableDispenser
0x180026482  xor     edx, edx; pUnkOuter
0x180026484  mov     r9, rdi; riid
0x180026487  mov     rcx, r13; rclsid
0x18002648a  call    cs:__imp_CoCreateInstance
0x180026490  mov     r9, rdi; riid
0x180026493  mov     [rsp+78h+ppv], rsi; ppv
0x180026498  mov     r8d, ebx; dwClsContext
0x18002649b  xor     edx, edx; pUnkOuter
0x18002649d  mov     rcx, r13; rclsid
0x1800264a0  call    cs:__imp_CoCreateInstance
0x1800264a6  mov     r9, rdi; riid
0x1800264a9  mov     [rsp+78h+ppv], r14; ppv
0x1800264ae  mov     r8d, ebx; dwClsContext
0x1800264b1  xor     edx, edx; pUnkOuter
0x1800264b3  mov     rcx, r13; rclsid
0x1800264b6  call    cs:__imp_CoCreateInstance
0x1800264bc  mov     r9, rdi; riid
0x1800264bf  mov     [rsp+78h+ppv], r15; ppv
0x1800264c4  mov     r8d, ebx; dwClsContext
0x1800264c7  xor     edx, edx; pUnkOuter
0x1800264c9  mov     rcx, r13; rclsid
0x1800264cc  call    cs:__imp_CoCreateInstance
0x1800264d2  mov     r9, rdi; riid
0x1800264d5  mov     [rsp+78h+ppv], rbp; ppv
0x1800264da  mov     r8d, ebx; dwClsContext
0x1800264dd  xor     edx, edx; pUnkOuter
0x1800264df  mov     rcx, r13; rclsid
0x1800264e2  call    cs:__imp_CoCreateInstance
0x1800264e8  mov     rax, r12
0x1800264eb  add     rsp, 38h
0x1800264ef  pop     r15
0x1800264f1  pop     r14
0x1800264f3  pop     r13
0x1800264f5  pop     r12
0x1800264f7  pop     rdi
0x1800264f8  pop     rsi
0x1800264f9  pop     rbp
0x1800264fa  pop     rbx
0x1800264fb  retn
```
