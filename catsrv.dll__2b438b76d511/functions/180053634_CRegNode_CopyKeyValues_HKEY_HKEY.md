# CRegNode::CopyKeyValues(HKEY__ *,HKEY__ *)

- ea: `0x180053634`
- end: `0x18005377d`
- name: `?CopyKeyValues@CRegNode@@AEAAJPEAUHKEY__@@0@Z`
- size: `329`
- prototype: `__int64 __fastcall(CRegNode *this, HKEY, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053450`

## callees

- `0x180053634`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800536de`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800536de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005370f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005370f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005374f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005374f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053686`

## pseudocode

```c
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

  Type = 0;
  cchValueName = 2000;
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
0x180053634  mov     [rsp-8+arg_0], rbx
0x180053639  push    rbp
0x18005363a  push    rsi
0x18005363b  push    rdi
0x18005363c  push    r12
0x18005363e  push    r14
0x180053640  lea     rbp, [rsp-730h]
0x180053648  sub     rsp, 830h
0x18005364f  mov     rax, cs:__security_cookie
0x180053656  xor     rax, rsp
0x180053659  mov     [rbp+750h+var_30], rax
0x180053660  mov     r12d, 7D0h
0x180053666  mov     [rsp+850h+Type], 0
0x18005366e  mov     ecx, 0FA0h; cb
0x180053673  mov     [rsp+850h+cchValueName], r12d
0x180053678  mov     rsi, r8
0x18005367b  mov     [rsp+850h+cbData], 0
0x180053683  mov     r14, rdx
0x180053686  call    cs:__imp_CoTaskMemAlloc
0x18005368c  mov     rdi, rax
0x18005368f  test    rax, rax
0x180053692  jnz     short loc_18005369E
0x180053694  mov     eax, 8007000Eh
0x180053699  jmp     loc_180053757
0x18005369e  xor     ebx, ebx
0x1800536a0  lea     rax, [rsp+850h+cbData]
0x1800536a5  mov     [rsp+850h+cbData], r12d
0x1800536aa  mov     [rsp+850h+lpcbData], rax; lpcbData
0x1800536af  lea     r9, [rsp+850h+cchValueName]; lpcchValueName
0x1800536b4  lea     rax, [rsp+850h+Data]
0x1800536b9  mov     [rsp+850h+cchValueName], r12d
0x1800536be  mov     [rsp+850h+lpData], rax; lpData
0x1800536c3  mov     r8, rdi; lpValueName
0x1800536c6  lea     rax, [rsp+850h+Type]
0x1800536cb  mov     edx, ebx; dwIndex
0x1800536cd  mov     [rsp+850h+lpType], rax; lpType
0x1800536d2  mov     rcx, r14; hKey
0x1800536d5  mov     [rsp+850h+lpReserved], 0; lpReserved
0x1800536de  call    cs:__imp_RegEnumValueW
0x1800536e4  cmp     eax, 103h
0x1800536e9  jz      short loc_18005374A
0x1800536eb  test    eax, eax
0x1800536ed  jnz     short loc_180053730
0x1800536ef  mov     eax, [rsp+850h+cbData]
0x1800536f3  xor     r8d, r8d; Reserved
0x1800536f6  mov     r9d, [rsp+850h+Type]; dwType
0x1800536fb  mov     rdx, rdi; lpValueName
0x1800536fe  mov     dword ptr [rsp+850h+lpType], eax; cbData
0x180053702  mov     rcx, rsi; hKey
0x180053705  lea     rax, [rsp+850h+Data]
0x18005370a  mov     [rsp+850h+lpReserved], rax; lpData
0x18005370f  call    cs:__imp_RegSetValueExW
0x180053715  test    eax, eax
0x180053717  jnz     short loc_18005371D
0x180053719  inc     ebx
0x18005371b  jmp     short loc_1800536A0
0x18005371d  cmp     eax, 522h
0x180053722  jz      short loc_180053743
0x180053724  cmp     eax, 5
0x180053727  jz      short loc_180053743
0x180053729  mov     ebx, 80110025h
0x18005372e  jmp     short loc_18005374C
0x180053730  cmp     eax, 522h
0x180053735  jz      short loc_180053743
0x180053737  cmp     eax, 5
0x18005373a  jz      short loc_180053743
0x18005373c  mov     ebx, 8011002Bh
0x180053741  jmp     short loc_18005374C
0x180053743  mov     ebx, 80110823h
0x180053748  jmp     short loc_18005374C
0x18005374a  xor     ebx, ebx
0x18005374c  mov     rcx, rdi; pv
0x18005374f  call    cs:__imp_CoTaskMemFree
0x180053755  mov     eax, ebx
0x180053757  mov     rcx, [rbp+750h+var_30]
0x18005375e  xor     rcx, rsp; StackCookie
0x180053761  call    __security_check_cookie
0x180053766  mov     rbx, [rsp+850h+arg_0]
0x18005376e  add     rsp, 830h
0x180053775  pop     r14
0x180053777  pop     r12
0x180053779  pop     rdi
0x18005377a  pop     rsi
0x18005377b  pop     rbp
0x18005377c  retn
```
