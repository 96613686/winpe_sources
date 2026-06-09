# CSecurityAdmin2::CSecurityAdmin2(void)

- ea: `0x18003378c`
- end: `0x1800338b4`
- name: `??0CSecurityAdmin2@@QEAA@XZ`
- size: `296`
- prototype: `CSecurityAdmin2 *__fastcall(CSecurityAdmin2 *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033ce4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033806`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033825`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033842`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033858`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003386e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033884`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003389a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033806`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033825`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033842`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033858`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003386e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033884`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003389a`

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
0x18003378c  push    rbx
0x18003378e  push    rbp
0x18003378f  push    rsi
0x180033790  push    rdi
0x180033791  push    r12
0x180033793  push    r13
0x180033795  push    r14
0x180033797  push    r15
0x180033799  sub     rsp, 38h
0x18003379d  mov     r12, rcx
0x1800337a0  lea     rax, ??_7CSecurityAdmin2@@6B@; const CSecurityAdmin2::`vftable'
0x1800337a7  mov     [rcx], rax
0x1800337aa  lea     r13, CLSID_STDispenser
0x1800337b1  xor     ecx, ecx
0x1800337b3  lea     r9, IID_ISimpleTableDispenser; riid
0x1800337ba  xor     edx, edx; pUnkOuter
0x1800337bc  lea     rax, [r12+10h]
0x1800337c1  mov     [r12+8], ecx
0x1800337c6  mov     [rax], rcx
0x1800337c9  lea     rbx, [r12+18h]
0x1800337ce  lea     r8d, [rcx+1]; dwClsContext
0x1800337d2  mov     [rbx], rcx
0x1800337d5  lea     rdi, [r12+20h]
0x1800337da  mov     [rsp+78h+ppv], rax; ppv
0x1800337df  mov     [rdi], rcx
0x1800337e2  lea     rsi, [r12+28h]
0x1800337e7  mov     [rsi], rcx
0x1800337ea  lea     r14, [r12+30h]
0x1800337ef  mov     [r14], rcx
0x1800337f2  lea     r15, [r12+38h]
0x1800337f7  mov     [r15], rcx
0x1800337fa  lea     rbp, [r12+40h]
0x1800337ff  mov     [rbp+0], rcx
0x180033803  mov     rcx, r13; rclsid
0x180033806  call    cs:__imp_CoCreateInstance
0x18003380c  mov     [rsp+78h+ppv], rbx; ppv
0x180033811  lea     r9, IID_ISimpleTableDispenser; riid
0x180033818  mov     ebx, 1
0x18003381d  xor     edx, edx; pUnkOuter
0x18003381f  mov     r8d, ebx; dwClsContext
0x180033822  mov     rcx, r13; rclsid
0x180033825  call    cs:__imp_CoCreateInstance
0x18003382b  mov     [rsp+78h+ppv], rdi; ppv
0x180033830  mov     r8d, ebx; dwClsContext
0x180033833  lea     rdi, IID_ISimpleTableDispenser
0x18003383a  xor     edx, edx; pUnkOuter
0x18003383c  mov     r9, rdi; riid
0x18003383f  mov     rcx, r13; rclsid
0x180033842  call    cs:__imp_CoCreateInstance
0x180033848  mov     r9, rdi; riid
0x18003384b  mov     [rsp+78h+ppv], rsi; ppv
0x180033850  mov     r8d, ebx; dwClsContext
0x180033853  xor     edx, edx; pUnkOuter
0x180033855  mov     rcx, r13; rclsid
0x180033858  call    cs:__imp_CoCreateInstance
0x18003385e  mov     r9, rdi; riid
0x180033861  mov     [rsp+78h+ppv], r14; ppv
0x180033866  mov     r8d, ebx; dwClsContext
0x180033869  xor     edx, edx; pUnkOuter
0x18003386b  mov     rcx, r13; rclsid
0x18003386e  call    cs:__imp_CoCreateInstance
0x180033874  mov     r9, rdi; riid
0x180033877  mov     [rsp+78h+ppv], r15; ppv
0x18003387c  mov     r8d, ebx; dwClsContext
0x18003387f  xor     edx, edx; pUnkOuter
0x180033881  mov     rcx, r13; rclsid
0x180033884  call    cs:__imp_CoCreateInstance
0x18003388a  mov     r9, rdi; riid
0x18003388d  mov     [rsp+78h+ppv], rbp; ppv
0x180033892  mov     r8d, ebx; dwClsContext
0x180033895  xor     edx, edx; pUnkOuter
0x180033897  mov     rcx, r13; rclsid
0x18003389a  call    cs:__imp_CoCreateInstance
0x1800338a0  mov     rax, r12
0x1800338a3  add     rsp, 38h
0x1800338a7  pop     r15
0x1800338a9  pop     r14
0x1800338ab  pop     r13
0x1800338ad  pop     r12
0x1800338af  pop     rdi
0x1800338b0  pop     rsi
0x1800338b1  pop     rbp
0x1800338b2  pop     rbx
0x1800338b3  retn
```
