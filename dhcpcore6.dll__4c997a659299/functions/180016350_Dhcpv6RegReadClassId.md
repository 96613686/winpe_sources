# Dhcpv6RegReadClassId

- ea: `0x180016350`
- end: `0x180016437`
- name: `Dhcpv6RegReadClassId`
- size: `231`
- prototype: `int __fastcall(__int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18000bc88`
- `0x180014e18`
- `0x180029fe4`

## callees

- `0x180005200`
- `0x180005db8`
- `0x18000c740`
- `0x180016350`
- `0x180018fa4`

## string_xrefs

- `0x1800163c7`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces\?\Dhcpv6ClassIdBin`

## pseudocode

```c
int __fastcall Dhcpv6RegReadClassId(__int64 a1)
{
  wchar_t *v2; // rcx
  LPVOID v3; // rdi
  int result; // eax
  __int64 v5; // rcx
  int v6; // esi
  __int64 v7; // rax
  DWORD v8; // [rsp+60h] [rbp+28h] BYREF
  int v9; // [rsp+68h] [rbp+30h]
  LPVOID v10; // [rsp+70h] [rbp+38h] BYREF
  const void *v11; // [rsp+78h] [rbp+40h] BYREF

  *(_QWORD *)(a1 + 656) = 0;
  *(_DWORD *)(a1 + 664) = 0;
  v11 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( (unsigned int)GetRegistryString(Dhcpv6GlobalParametersKey, L"Dhcpv6ClientClassLocation")
    || (v2 = (wchar_t *)v10) == 0 )
  {
    v10 = 0;
    v2 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces\\?\\Dhcpv6ClassIdBin";
    v3 = 0;
  }
  else
  {
    v3 = v10;
  }
  result = DhcpRegReadFromAnyLocation(v2, &v8);
  v6 = result;
  if ( v3 )
    result = DhcpFree(&v10);
  if ( !v6 && v11 )
  {
    v7 = Dhcpv6AddClass(v5, v11, v8);
    *(_QWORD *)(a1 + 656) = v7;
    if ( v7 )
      *(_DWORD *)(a1 + 664) = v8;
    return DhcpFree((LPVOID *)&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180016350  push    rbp
0x180016352  push    rbx
0x180016353  push    rsi
0x180016354  push    rdi
0x180016355  mov     rbp, rsp
0x180016358  sub     rsp, 38h
0x18001635c  mov     rsi, [rcx+38h]
0x180016360  lea     r8, [rbp+arg_10]
0x180016364  mov     rbx, rcx
0x180016367  mov     qword ptr [rcx+290h], 0
0x180016372  mov     dword ptr [rcx+298h], 0
0x18001637c  lea     rdx, aDhcpv6clientcl; "Dhcpv6ClientClassLocation"
0x180016383  mov     rcx, cs:Dhcpv6GlobalParametersKey; hKey
0x18001638a  mov     [rbp+arg_18], 0
0x180016392  mov     [rbp+arg_0], 0
0x180016399  mov     [rbp+arg_8], 0
0x1800163a0  mov     [rbp+arg_10], 0
0x1800163a8  call    GetRegistryString
0x1800163ad  test    eax, eax
0x1800163af  jnz     short loc_1800163BF
0x1800163b1  mov     rcx, [rbp+arg_10]
0x1800163b5  test    rcx, rcx
0x1800163b8  jz      short loc_1800163BF
0x1800163ba  mov     rdi, rcx
0x1800163bd  jmp     short loc_1800163D0
0x1800163bf  mov     [rbp+arg_10], 0
0x1800163c7  lea     rcx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x1800163ce  xor     edi, edi
0x1800163d0  lea     rax, [rbp+arg_0]
0x1800163d4  mov     rdx, rsi
0x1800163d7  lea     r9, [rbp+arg_8]
0x1800163db  mov     [rsp+38h+var_18], rax; LPDWORD
0x1800163e0  lea     r8, [rbp+arg_18]
0x1800163e4  call    DhcpRegReadFromAnyLocation
0x1800163e9  mov     esi, eax
0x1800163eb  test    rdi, rdi
0x1800163ee  jz      short loc_1800163F9
0x1800163f0  lea     rcx, [rbp+arg_10]
0x1800163f4  call    DhcpFree
0x1800163f9  test    esi, esi
0x1800163fb  jnz     short loc_18001642D
0x1800163fd  mov     rdx, [rbp+arg_18]
0x180016401  test    rdx, rdx
0x180016404  jz      short loc_18001642D
0x180016406  mov     r8d, [rbp+arg_0]
0x18001640a  call    Dhcpv6AddClass
0x18001640f  mov     [rbx+290h], rax
0x180016416  test    rax, rax
0x180016419  jz      short loc_180016424
0x18001641b  mov     eax, [rbp+arg_0]
0x18001641e  mov     [rbx+298h], eax
0x180016424  lea     rcx, [rbp+arg_18]
0x180016428  call    DhcpFree
0x18001642d  add     rsp, 38h
0x180016431  pop     rdi
0x180016432  pop     rsi
0x180016433  pop     rbx
0x180016434  pop     rbp
0x180016435  retn
```
