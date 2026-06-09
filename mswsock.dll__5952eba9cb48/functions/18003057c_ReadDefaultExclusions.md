# ReadDefaultExclusions

- ea: `0x18003057c`
- end: `0x1800307ae`
- name: `ReadDefaultExclusions`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002ff9c`

## callees

- `0x18003057c`
- `0x180053010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180030742`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180030742`
- `ntdll!RtlFreeHeap` at `0x18003070d`
- `ntdll!RtlFreeHeap` at `0x180030790`
- `ntdll!RtlFreeHeap` at `0x18003070d`
- `ntdll!RtlFreeHeap` at `0x180030790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030647`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003068a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030647`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003068a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030603`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030678`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030603`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030678`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800305cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800305cb`

## string_xrefs

- `0x1800305a6`: `SYSTEM\CurrentControlSet\Control\ServiceProvider\Order`

## pseudocode

```c
LSTATUS ReadDefaultExclusions()
{
  LSTATUS result; // eax
  LSTATUS v1; // eax
  LSTATUS v2; // ebx
  BYTE *v3; // rdi
  int v4; // eax
  BYTE *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rsi
  unsigned int v8; // r15d
  const wchar_t *i; // r14
  __int64 v10; // rbx
  __int64 v11; // rax
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF
  wchar_t *EndPtr; // [rsp+88h] [rbp+58h] BYREF

  cbData = 0;
  hKey = 0;
  Type = 0;
  DefaultExclusions = 0;
  DefaultExclusionCount = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\ServiceProvider\\Order",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    cbData = 0;
    v1 = RegQueryValueExW(hKey, L"ExcludedProviders", 0, &Type, 0, &cbData);
    if ( v1 == 234 || !v1 )
    {
      v3 = (BYTE *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(SockPrivateHeap, 0, cbData);
      if ( v3 )
      {
        v2 = RegQueryValueExW(hKey, L"ExcludedProviders", 0, &Type, v3, &cbData);
        RegCloseKey(hKey);
        if ( !v2 )
        {
          v4 = 0;
          DefaultExclusionCount = 0;
          if ( *(_WORD *)v3 )
          {
            v5 = v3;
            do
            {
              ++v4;
              v6 = -1;
              do
                ++v6;
              while ( *(_WORD *)&v5[2 * v6] );
              v5 += 2 * v6 + 2;
            }
            while ( *(_WORD *)v5 );
            DefaultExclusionCount = v4;
          }
          DefaultExclusions = ((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(
                                SockPrivateHeap,
                                0,
                                4LL * (unsigned int)(v4 + 1));
          v7 = DefaultExclusions;
          if ( !DefaultExclusions )
          {
            RtlFreeHeap(SockPrivateHeap, 0, v3);
            result = 8;
            DefaultExclusionCount = 0;
            return result;
          }
          v8 = 0;
          for ( i = (const wchar_t *)v3; *i; i += v11 + 1 )
          {
            EndPtr = 0;
            v10 = v8++;
            *(_DWORD *)(v7 + 4 * v10) = wcstol(i, &EndPtr, 0);
            v11 = -1;
            do
              ++v11;
            while ( i[v11] );
            v7 = DefaultExclusions;
          }
          v2 = 0;
          *(_DWORD *)(v7 + 4LL * (unsigned int)DefaultExclusionCount) = 0;
        }
        RtlFreeHeap(SockPrivateHeap, 0, v3);
        return v2;
      }
      v2 = 8;
    }
    else
    {
      v2 = 0;
    }
    RegCloseKey(hKey);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18003057c  push    rbp
0x18003057e  push    rbx
0x18003057f  push    rsi
0x180030580  push    rdi
0x180030581  push    r12
0x180030583  push    r14
0x180030585  push    r15
0x180030587  mov     rbp, rsp
0x18003058a  sub     rsp, 30h
0x18003058e  xor     r12d, r12d
0x180030591  lea     rax, [rbp+hKey]
0x180030595  mov     r9d, 20019h; samDesired
0x18003059b  mov     [rbp+cbData], r12d
0x18003059f  xor     r8d, r8d; ulOptions
0x1800305a2  mov     [rbp+hKey], r12
0x1800305a6  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Ser"...
0x1800305ad  mov     [rbp+Type], r12d
0x1800305b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800305b8  mov     cs:DefaultExclusions, r12
0x1800305bf  mov     cs:DefaultExclusionCount, r12d
0x1800305c6  mov     [rsp+30h+phkResult], rax; phkResult
0x1800305cb  call    cs:__imp_RegOpenKeyExW
0x1800305d2  nop     dword ptr [rax+rax+00h]
0x1800305d7  test    eax, eax
0x1800305d9  jnz     loc_18003079E
0x1800305df  mov     rcx, [rbp+hKey]; hKey
0x1800305e3  lea     rax, [rbp+cbData]
0x1800305e7  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800305ec  lea     r9, [rbp+Type]; lpType
0x1800305f0  xor     r8d, r8d; lpReserved
0x1800305f3  mov     [rsp+30h+phkResult], r12; lpData
0x1800305f8  lea     rdx, aExcludedprovid; "ExcludedProviders"
0x1800305ff  mov     [rbp+cbData], r12d
0x180030603  call    cs:__imp_RegQueryValueExW
0x18003060a  nop     dword ptr [rax+rax+00h]
0x18003060f  cmp     eax, 0EAh
0x180030614  jz      short loc_18003061F
0x180030616  test    eax, eax
0x180030618  jz      short loc_18003061F
0x18003061a  mov     ebx, r12d
0x18003061d  jmp     short loc_180030643
0x18003061f  mov     r8d, [rbp+cbData]
0x180030623  xor     edx, edx
0x180030625  mov     rcx, cs:SockPrivateHeap
0x18003062c  mov     rax, cs:SockAllocateHeapRoutine
0x180030633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030638  mov     rdi, rax
0x18003063b  test    rax, rax
0x18003063e  jnz     short loc_180030658
0x180030640  lea     ebx, [rax+8]
0x180030643  mov     rcx, [rbp+hKey]; hKey
0x180030647  call    cs:__imp_RegCloseKey
0x18003064e  nop     dword ptr [rax+rax+00h]
0x180030653  jmp     loc_18003079C
0x180030658  mov     rcx, [rbp+hKey]; hKey
0x18003065c  lea     rax, [rbp+cbData]
0x180030660  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180030665  lea     r9, [rbp+Type]; lpType
0x180030669  xor     r8d, r8d; lpReserved
0x18003066c  mov     [rsp+30h+phkResult], rdi; lpData
0x180030671  lea     rdx, aExcludedprovid; "ExcludedProviders"
0x180030678  call    cs:__imp_RegQueryValueExW
0x18003067f  nop     dword ptr [rax+rax+00h]
0x180030684  mov     rcx, [rbp+hKey]; hKey
0x180030688  mov     ebx, eax
0x18003068a  call    cs:__imp_RegCloseKey
0x180030691  nop     dword ptr [rax+rax+00h]
0x180030696  test    ebx, ebx
0x180030698  jnz     loc_180030784
0x18003069e  mov     eax, r12d
0x1800306a1  mov     cs:DefaultExclusionCount, r12d
0x1800306a8  cmp     [rdi], r12w
0x1800306ac  jz      short loc_1800306D5
0x1800306ae  mov     rcx, rdi
0x1800306b1  inc     eax
0x1800306b3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800306b7  inc     rdx
0x1800306ba  cmp     [rcx+rdx*2], r12w
0x1800306bf  jnz     short loc_1800306B7
0x1800306c1  lea     rcx, [rcx+rdx*2]
0x1800306c5  add     rcx, 2
0x1800306c9  cmp     [rcx], r12w
0x1800306cd  jnz     short loc_1800306B1
0x1800306cf  mov     cs:DefaultExclusionCount, eax
0x1800306d5  mov     rcx, cs:SockPrivateHeap
0x1800306dc  lea     r8d, [rax+1]
0x1800306e0  mov     rax, cs:SockAllocateHeapRoutine
0x1800306e7  xor     edx, edx
0x1800306e9  shl     r8, 2
0x1800306ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306f2  mov     cs:DefaultExclusions, rax
0x1800306f9  mov     rsi, rax
0x1800306fc  test    rax, rax
0x1800306ff  jnz     short loc_180030725
0x180030701  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180030708  mov     r8, rdi; P
0x18003070b  xor     edx, edx; Flags
0x18003070d  call    cs:__imp_RtlFreeHeap
0x180030714  nop     dword ptr [rax+rax+00h]
0x180030719  lea     eax, [rsi+8]
0x18003071c  mov     cs:DefaultExclusionCount, r12d
0x180030723  jmp     short loc_18003079E
0x180030725  mov     r15d, r12d
0x180030728  mov     r14, rdi
0x18003072b  cmp     [rdi], r12w
0x18003072f  jz      short loc_180030777
0x180030731  xor     r8d, r8d; Radix
0x180030734  mov     [rbp+EndPtr], r12
0x180030738  lea     rdx, [rbp+EndPtr]; EndPtr
0x18003073c  mov     ebx, r15d
0x18003073f  mov     rcx, r14; String
0x180030742  call    cs:__imp_wcstol
0x180030749  nop     dword ptr [rax+rax+00h]
0x18003074e  inc     r15d
0x180030751  mov     [rsi+rbx*4], eax
0x180030754  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030758  inc     rax
0x18003075b  cmp     [r14+rax*2], r12w
0x180030760  jnz     short loc_180030758
0x180030762  mov     rsi, cs:DefaultExclusions
0x180030769  lea     r14, [r14+rax*2]
0x18003076d  add     r14, 2
0x180030771  cmp     [r14], r12w
0x180030775  jnz     short loc_180030731
0x180030777  mov     eax, cs:DefaultExclusionCount
0x18003077d  mov     ebx, r12d
0x180030780  mov     [rsi+rax*4], r12d
0x180030784  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003078b  mov     r8, rdi; P
0x18003078e  xor     edx, edx; Flags
0x180030790  call    cs:__imp_RtlFreeHeap
0x180030797  nop     dword ptr [rax+rax+00h]
0x18003079c  mov     eax, ebx
0x18003079e  add     rsp, 30h
0x1800307a2  pop     r15
0x1800307a4  pop     r14
0x1800307a6  pop     r12
0x1800307a8  pop     rdi
0x1800307a9  pop     rsi
0x1800307aa  pop     rbx
0x1800307ab  pop     rbp
0x1800307ac  retn
```
