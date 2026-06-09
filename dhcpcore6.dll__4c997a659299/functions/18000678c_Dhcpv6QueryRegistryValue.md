# Dhcpv6QueryRegistryValue

- ea: `0x18000678c`
- end: `0x1800068fc`
- name: `Dhcpv6QueryRegistryValue`
- size: `368`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, DWORD *, int *, BYTE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005bcc`

## callees

- `0x18000678c`
- `0x180007564`
- `0x18000c740`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006864`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006864`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006830`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006830`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068bb`

## pseudocode

```c
__int64 __fastcall Dhcpv6QueryRegistryValue(HKEY hKey, __int64 a2, DWORD *a3, int *a4, BYTE **a5)
{
  int v5; // edx
  BYTE **v7; // r12
  BYTE *v10; // rax
  int v11; // esi
  BYTE *v12; // rdi
  int v13; // ebx
  LSTATUS v14; // eax
  unsigned int v15; // ebx
  BYTE *lpData; // [rsp+30h] [rbp-10h] BYREF
  __int64 cbData; // [rsp+88h] [rbp+48h] BYREF
  DWORD Type; // [rsp+98h] [rbp+58h] BYREF

  cbData = a2;
  v5 = *a4;
  v7 = a5;
  lpData = 0;
  Type = 0;
  LODWORD(cbData) = v5;
  v10 = *a5;
  if ( v5 )
  {
    if ( v10 )
      return (unsigned int)RegQueryValueExW(hKey, L"Dhcpv6InterfaceOptions", 0, a3, v10, (LPDWORD)&cbData);
  }
  else if ( v10 )
  {
    return 87;
  }
  v11 = 0;
  if ( !v5 )
    LODWORD(cbData) = 32;
  v12 = 0;
  while ( 1 )
  {
    if ( v12 )
      DhcpFree((LPVOID *)&lpData);
    v13 = cbData;
    lpData = (BYTE *)DhcpAlloc((unsigned int)cbData);
    v12 = lpData;
    if ( !lpData )
      return 8;
    LODWORD(cbData) = v13;
    v14 = RegQueryValueExW(hKey, L"Dhcpv6InterfaceOptions", 0, &Type, lpData, (LPDWORD)&cbData);
    v15 = v14;
    if ( v14 != 234 )
      break;
    if ( (unsigned int)++v11 >= 3 )
      goto LABEL_13;
  }
  if ( v14 )
  {
LABEL_13:
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v12);
    return v15;
  }
  *a4 = cbData;
  *a3 = Type;
  *v7 = v12;
  return v15;
}

```

## disassembly

```asm
0x18000678c  mov     [rsp-38h+arg_0], rbx
0x180006791  mov     [rsp-38h+cbData], rdx
0x180006796  push    rbp
0x180006797  push    rsi
0x180006798  push    rdi
0x180006799  push    r12
0x18000679b  push    r13
0x18000679d  push    r14
0x18000679f  push    r15
0x1800067a1  mov     rbp, rsp
0x1800067a4  sub     rsp, 40h
0x1800067a8  mov     edx, [r9]
0x1800067ab  mov     r14, r9
0x1800067ae  mov     r12, [rbp+arg_20]
0x1800067b2  mov     r15, r8
0x1800067b5  mov     [rbp+var_10], 0
0x1800067bd  mov     r13, rcx
0x1800067c0  mov     [rbp+Type], 0
0x1800067c7  mov     dword ptr [rbp+cbData], edx
0x1800067ca  mov     rax, [r12]
0x1800067ce  test    edx, edx
0x1800067d0  jz      loc_1800068CB
0x1800067d6  test    rax, rax
0x1800067d9  jnz     loc_18000689D
0x1800067df  xor     esi, esi
0x1800067e1  test    edx, edx
0x1800067e3  jz      loc_1800068E2
0x1800067e9  xor     edi, edi
0x1800067eb  test    rdi, rdi
0x1800067ee  jnz     loc_1800068EE
0x1800067f4  mov     ebx, dword ptr [rbp+cbData]
0x1800067f7  mov     ecx, ebx
0x1800067f9  call    DhcpAlloc
0x1800067fe  mov     [rbp+var_10], rax
0x180006802  mov     rdi, rax
0x180006805  test    rax, rax
0x180006808  jz      loc_1800068DB
0x18000680e  lea     rax, [rbp+cbData]
0x180006812  mov     dword ptr [rbp+cbData], ebx
0x180006815  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000681a  lea     r9, [rbp+Type]; lpType
0x18000681e  xor     r8d, r8d; lpReserved
0x180006821  mov     [rsp+40h+lpData], rdi; lpData
0x180006826  lea     rdx, aDhcpv6interfac; "Dhcpv6InterfaceOptions"
0x18000682d  mov     rcx, r13; hKey
0x180006830  call    cs:__imp_RegQueryValueExW
0x180006837  nop     dword ptr [rax+rax+00h]
0x18000683c  mov     ebx, eax
0x18000683e  cmp     eax, 0EAh
0x180006843  jnz     short loc_18000684E
0x180006845  inc     esi
0x180006847  cmp     esi, 3
0x18000684a  jb      short loc_1800067EB
0x18000684c  jmp     short loc_180006852
0x18000684e  test    eax, eax
0x180006850  jz      short loc_18000688B
0x180006852  mov     rcx, gs:60h
0x18000685b  mov     r8, rdi; lpMem
0x18000685e  xor     edx, edx; dwFlags
0x180006860  mov     rcx, [rcx+30h]; hHeap
0x180006864  call    cs:__imp_HeapFree
0x18000686b  nop     dword ptr [rax+rax+00h]
0x180006870  mov     eax, ebx
0x180006872  mov     rbx, [rsp+40h+arg_0]
0x18000687a  add     rsp, 40h
0x18000687e  pop     r15
0x180006880  pop     r14
0x180006882  pop     r13
0x180006884  pop     r12
0x180006886  pop     rdi
0x180006887  pop     rsi
0x180006888  pop     rbp
0x180006889  retn
0x18000688b  mov     eax, dword ptr [rbp+cbData]
0x18000688e  mov     [r14], eax
0x180006891  mov     eax, [rbp+Type]
0x180006894  mov     [r15], eax
0x180006897  mov     [r12], rdi
0x18000689b  jmp     short loc_180006870
0x18000689d  lea     rcx, [rbp+cbData]
0x1800068a1  mov     r9, r15; lpType
0x1800068a4  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x1800068a9  lea     rdx, aDhcpv6interfac; "Dhcpv6InterfaceOptions"
0x1800068b0  mov     rcx, r13; hKey
0x1800068b3  mov     [rsp+40h+lpData], rax; lpData
0x1800068b8  xor     r8d, r8d; lpReserved
0x1800068bb  call    cs:__imp_RegQueryValueExW
0x1800068c2  nop     dword ptr [rax+rax+00h]
0x1800068c7  mov     ebx, eax
0x1800068c9  jmp     short loc_180006870
0x1800068cb  test    rax, rax
0x1800068ce  jz      loc_1800067DF
0x1800068d4  mov     ebx, 57h ; 'W'
0x1800068d9  jmp     short loc_180006870
0x1800068db  mov     ebx, 8
0x1800068e0  jmp     short loc_180006870
0x1800068e2  mov     dword ptr [rbp+cbData], 20h ; ' '
0x1800068e9  jmp     loc_1800067E9
0x1800068ee  lea     rcx, [rbp+var_10]
0x1800068f2  call    DhcpFree
0x1800068f7  jmp     loc_1800067F4
```
