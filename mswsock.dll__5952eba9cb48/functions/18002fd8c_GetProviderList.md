# GetProviderList

- ea: `0x18002fd8c`
- end: `0x18002ff26`
- name: `GetProviderList`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002ff9c`

## callees

- `0x180022bd2`
- `0x18002fd8c`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002fecc`
- `ntdll!RtlFreeHeap` at `0x18002fecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fe56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fe56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fead`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fe0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fe9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fe0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fe9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fdd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fdd6`

## string_xrefs

- `0x18002fdb6`: `SYSTEM\CurrentControlSet\Control\ServiceProvider\Order`

## pseudocode

```c
LSTATUS __fastcall GetProviderList(PVOID *a1, _DWORD *a2)
{
  LSTATUS result; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // ebx
  void *v7; // rax
  BYTE *v8; // rbx
  _WORD *v9; // rcx
  _WORD *v10; // rdx
  bool v11; // zf
  _WORD *v12; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  cbData = 0;
  hKey = 0;
  Type = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\ServiceProvider\\Order",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    cbData = 0;
    v5 = RegQueryValueExW(hKey, L"ProviderOrder", 0, &Type, 0, &cbData);
    v6 = v5;
    if ( v5 != 234 && v5 )
      goto LABEL_6;
    v7 = (void *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                   SockPrivateHeap,
                   0,
                   cbData + 16);
    *a1 = v7;
    v8 = (BYTE *)v7;
    if ( !v7 )
    {
      v6 = 8;
LABEL_6:
      RegCloseKey(hKey);
      return v6;
    }
    memset_0(v7, 0, cbData + 16);
    v6 = RegQueryValueExW(hKey, L"ProviderOrder", 0, &Type, v8, &cbData);
    RegCloseKey(hKey);
    v9 = *a1;
    if ( v6 )
    {
      RtlFreeHeap(SockPrivateHeap, 0, *a1);
      return v6;
    }
    *a2 = 0;
    if ( *v9 )
    {
      v10 = &v9[cbData];
      do
      {
        ++*a2;
        if ( v9 >= v10 )
          break;
        while ( 1 )
        {
          v11 = *v9 == 0;
          v12 = ++v9;
          if ( v11 )
            break;
          if ( v12 >= v10 )
            return 0;
        }
      }
      while ( v12 < v10 && *v12 );
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002fd8c  mov     [rsp-18h+arg_0], rbx
0x18002fd91  mov     [rsp-18h+arg_8], rsi
0x18002fd96  push    rbp
0x18002fd97  push    rdi
0x18002fd98  push    r14
0x18002fd9a  mov     rbp, rsp
0x18002fd9d  sub     rsp, 40h
0x18002fda1  xor     r14d, r14d
0x18002fda4  lea     rax, [rbp+hKey]
0x18002fda8  mov     rdi, rdx
0x18002fdab  mov     [rbp+cbData], r14d
0x18002fdaf  mov     rsi, rcx
0x18002fdb2  mov     [rbp+hKey], r14
0x18002fdb6  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Ser"...
0x18002fdbd  mov     [rbp+Type], r14d
0x18002fdc1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fdc8  mov     [rsp+40h+phkResult], rax; phkResult
0x18002fdcd  mov     r9d, 20019h; samDesired
0x18002fdd3  xor     r8d, r8d; ulOptions
0x18002fdd6  call    cs:__imp_RegOpenKeyExW
0x18002fddd  nop     dword ptr [rax+rax+00h]
0x18002fde2  test    eax, eax
0x18002fde4  jnz     loc_18002FF12
0x18002fdea  mov     rcx, [rbp+hKey]; hKey
0x18002fdee  lea     rax, [rbp+cbData]
0x18002fdf2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002fdf7  lea     r9, [rbp+Type]; lpType
0x18002fdfb  xor     r8d, r8d; lpReserved
0x18002fdfe  mov     [rsp+40h+phkResult], r14; lpData
0x18002fe03  lea     rdx, aProviderorder; "ProviderOrder"
0x18002fe0a  mov     [rbp+cbData], r14d
0x18002fe0e  call    cs:__imp_RegQueryValueExW
0x18002fe15  nop     dword ptr [rax+rax+00h]
0x18002fe1a  mov     ebx, eax
0x18002fe1c  cmp     eax, 0EAh
0x18002fe21  jz      short loc_18002FE27
0x18002fe23  test    eax, eax
0x18002fe25  jnz     short loc_18002FE52
0x18002fe27  mov     r8d, [rbp+cbData]
0x18002fe2b  xor     edx, edx
0x18002fe2d  mov     rcx, cs:SockPrivateHeap
0x18002fe34  add     r8d, 10h
0x18002fe38  mov     rax, cs:SockAllocateHeapRoutine
0x18002fe3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe44  mov     [rsi], rax
0x18002fe47  mov     rbx, rax
0x18002fe4a  test    rax, rax
0x18002fe4d  jnz     short loc_18002FE69
0x18002fe4f  lea     ebx, [rax+8]
0x18002fe52  mov     rcx, [rbp+hKey]; hKey
0x18002fe56  call    cs:__imp_RegCloseKey
0x18002fe5d  nop     dword ptr [rax+rax+00h]
0x18002fe62  mov     eax, ebx
0x18002fe64  jmp     loc_18002FF12
0x18002fe69  mov     r8d, [rbp+cbData]
0x18002fe6d  xor     edx, edx; Val
0x18002fe6f  add     r8d, 10h; Size
0x18002fe73  mov     rcx, rbx; void *
0x18002fe76  call    memset_0
0x18002fe7b  mov     rcx, [rbp+hKey]; hKey
0x18002fe7f  lea     rax, [rbp+cbData]
0x18002fe83  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002fe88  lea     r9, [rbp+Type]; lpType
0x18002fe8c  xor     r8d, r8d; lpReserved
0x18002fe8f  mov     [rsp+40h+phkResult], rbx; lpData
0x18002fe94  lea     rdx, aProviderorder; "ProviderOrder"
0x18002fe9b  call    cs:__imp_RegQueryValueExW
0x18002fea2  nop     dword ptr [rax+rax+00h]
0x18002fea7  mov     rcx, [rbp+hKey]; hKey
0x18002feab  mov     ebx, eax
0x18002fead  call    cs:__imp_RegCloseKey
0x18002feb4  nop     dword ptr [rax+rax+00h]
0x18002feb9  mov     rcx, [rsi]
0x18002febc  test    ebx, ebx
0x18002febe  jz      short loc_18002FEDA
0x18002fec0  mov     r8, rcx; P
0x18002fec3  xor     edx, edx; Flags
0x18002fec5  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002fecc  call    cs:__imp_RtlFreeHeap
0x18002fed3  nop     dword ptr [rax+rax+00h]
0x18002fed8  jmp     short loc_18002FE62
0x18002feda  mov     [rdi], r14d
0x18002fedd  cmp     [rcx], r14w
0x18002fee1  jz      short loc_18002FF10
0x18002fee3  mov     eax, [rbp+cbData]
0x18002fee6  lea     rdx, [rcx+rax*2]
0x18002feea  inc     dword ptr [rdi]
0x18002feec  cmp     rcx, rdx
0x18002feef  jnb     short loc_18002FF10
0x18002fef1  cmp     [rcx], r14w
0x18002fef5  lea     rax, [rcx+2]
0x18002fef9  mov     rcx, rax
0x18002fefc  jz      short loc_18002FF05
0x18002fefe  cmp     rax, rdx
0x18002ff01  jb      short loc_18002FEF1
0x18002ff03  jmp     short loc_18002FF10
0x18002ff05  cmp     rax, rdx
0x18002ff08  jnb     short loc_18002FF10
0x18002ff0a  cmp     [rax], r14w
0x18002ff0e  jnz     short loc_18002FEEA
0x18002ff10  xor     eax, eax
0x18002ff12  mov     rbx, [rsp+40h+arg_0]
0x18002ff17  mov     rsi, [rsp+40h+arg_8]
0x18002ff1c  add     rsp, 40h
0x18002ff20  pop     r14
0x18002ff22  pop     rdi
0x18002ff23  pop     rbp
0x18002ff24  retn
```
