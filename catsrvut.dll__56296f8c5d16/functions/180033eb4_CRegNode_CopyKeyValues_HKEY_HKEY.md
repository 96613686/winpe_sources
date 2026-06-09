# CRegNode::CopyKeyValues(HKEY__ *,HKEY__ *)

- ea: `0x180033eb4`
- end: `0x180033ffe`
- name: `?CopyKeyValues@CRegNode@@AEAAJPEAUHKEY__@@0@Z`
- size: `330`
- prototype: `int(CRegNode *__hidden this, HKEY, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033cd0`

## callees

- `0x180033eb4`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033fcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033fcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033f06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033f8f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033f8f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180033f5e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180033f5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRegNode::CopyKeyValues(CRegNode *this, HKEY a2, HKEY a3)
{
  WCHAR *v5; // rdi
  DWORD i; // ebx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[2000]; // [rsp+50h] [rbp-B0h] BYREF

  cchValueName = 2000;
  Type = 0;
  cbData = 0;
  v5 = (WCHAR *)CoTaskMemAlloc(0xFA0u);
  if ( !v5 )
    return 2147942414LL;
  for ( i = 0; ; ++i )
  {
    cbData = 2000;
    cchValueName = 2000;
    v8 = RegEnumValueW(a2, i, v5, &cchValueName, 0, &Type, Data, &cbData);
    if ( v8 == 259 )
      break;
    if ( v8 )
    {
      if ( v8 != 1314 && v8 != 5 )
      {
        v10 = -2146369493;
        goto LABEL_16;
      }
      goto LABEL_14;
    }
    v9 = RegSetValueExW(a3, v5, 0, Type, Data, cbData);
    if ( v9 )
    {
      if ( v9 != 1314 && v9 != 5 )
      {
        v10 = -2146369499;
        goto LABEL_16;
      }
LABEL_14:
      v10 = -2146367453;
      goto LABEL_16;
    }
  }
  v10 = 0;
LABEL_16:
  CoTaskMemFree(v5);
  return v10;
}

```

## disassembly

```asm
0x180033eb4  mov     [rsp-8+arg_0], rbx
0x180033eb9  push    rbp
0x180033eba  push    rsi
0x180033ebb  push    rdi
0x180033ebc  push    r12
0x180033ebe  push    r14
0x180033ec0  lea     rbp, [rsp-730h]
0x180033ec8  sub     rsp, 830h
0x180033ecf  mov     rax, cs:__security_cookie
0x180033ed6  xor     rax, rsp
0x180033ed9  mov     [rbp+750h+var_30], rax
0x180033ee0  mov     rsi, r8
0x180033ee3  mov     r14, rdx
0x180033ee6  mov     r12d, 7D0h
0x180033eec  mov     [rsp+850h+cchValueName], r12d
0x180033ef1  mov     [rsp+850h+Type], 0
0x180033ef9  mov     [rsp+850h+cbData], 0
0x180033f01  mov     ecx, 0FA0h; cb
0x180033f06  call    cs:__imp_CoTaskMemAlloc
0x180033f0c  mov     rdi, rax
0x180033f0f  test    rax, rax
0x180033f12  jnz     short loc_180033F1E
0x180033f14  mov     eax, 8007000Eh
0x180033f19  jmp     loc_180033FD8
0x180033f1e  xor     ebx, ebx
0x180033f20  mov     [rsp+850h+cbData], r12d
0x180033f25  mov     [rsp+850h+cchValueName], r12d
0x180033f2a  lea     rax, [rsp+850h+cbData]
0x180033f2f  mov     [rsp+850h+lpcbData], rax; lpcbData
0x180033f34  lea     rax, [rsp+850h+Data]
0x180033f39  mov     [rsp+850h+lpData], rax; lpData
0x180033f3e  lea     rax, [rsp+850h+Type]
0x180033f43  mov     [rsp+850h+lpType], rax; lpType
0x180033f48  mov     [rsp+850h+lpReserved], 0; lpReserved
0x180033f51  lea     r9, [rsp+850h+cchValueName]; lpcchValueName
0x180033f56  mov     r8, rdi; lpValueName
0x180033f59  mov     edx, ebx; dwIndex
0x180033f5b  mov     rcx, r14; hKey
0x180033f5e  call    cs:__imp_RegEnumValueW
0x180033f64  cmp     eax, 103h
0x180033f69  jz      short loc_180033FCA
0x180033f6b  test    eax, eax
0x180033f6d  jnz     short loc_180033FB0
0x180033f6f  mov     eax, [rsp+850h+cbData]
0x180033f73  mov     dword ptr [rsp+850h+lpType], eax; cbData
0x180033f77  lea     rax, [rsp+850h+Data]
0x180033f7c  mov     [rsp+850h+lpReserved], rax; lpData
0x180033f81  mov     r9d, [rsp+850h+Type]; dwType
0x180033f86  xor     r8d, r8d; Reserved
0x180033f89  mov     rdx, rdi; lpValueName
0x180033f8c  mov     rcx, rsi; hKey
0x180033f8f  call    cs:__imp_RegSetValueExW
0x180033f95  test    eax, eax
0x180033f97  jnz     short loc_180033F9D
0x180033f99  inc     ebx
0x180033f9b  jmp     short loc_180033F20
0x180033f9d  cmp     eax, 522h
0x180033fa2  jz      short loc_180033FC3
0x180033fa4  cmp     eax, 5
0x180033fa7  jz      short loc_180033FC3
0x180033fa9  mov     ebx, 80110025h
0x180033fae  jmp     short loc_180033FCC
0x180033fb0  cmp     eax, 522h
0x180033fb5  jz      short loc_180033FC3
0x180033fb7  cmp     eax, 5
0x180033fba  jz      short loc_180033FC3
0x180033fbc  mov     ebx, 8011002Bh
0x180033fc1  jmp     short loc_180033FCC
0x180033fc3  mov     ebx, 80110823h
0x180033fc8  jmp     short loc_180033FCC
0x180033fca  xor     ebx, ebx
0x180033fcc  mov     rcx, rdi; pv
0x180033fcf  call    cs:__imp_CoTaskMemFree
0x180033fd5  nop
0x180033fd6  mov     eax, ebx
0x180033fd8  mov     rcx, [rbp+750h+var_30]
0x180033fdf  xor     rcx, rsp; StackCookie
0x180033fe2  call    __security_check_cookie
0x180033fe7  mov     rbx, [rsp+850h+arg_0]
0x180033fef  add     rsp, 830h
0x180033ff6  pop     r14
0x180033ff8  pop     r12
0x180033ffa  pop     rdi
0x180033ffb  pop     rsi
0x180033ffc  pop     rbp
0x180033ffd  retn
```
