# GetRegistryClassIdName

- ea: `0x18000ec24`
- end: `0x18000ecde`
- name: `GetRegistryClassIdName`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18000eb30`

## callees

- `0x180002160`
- `0x18000ec24`
- `0x18000f7d4`
- `0x180011298`

## string_xrefs

- `0x18000ec4e`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpClassId`

## pseudocode

```c
__int64 __fastcall GetRegistryClassIdName(void *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  __int64 v5; // r9
  DWORD v6; // [rsp+58h] [rbp+28h] BYREF
  DWORD v7; // [rsp+60h] [rbp+30h] BYREF
  BYTE *v8; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v3 = DhcpRegReadFromLocation(
         L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpClassId",
         a1,
         &v8,
         &v6,
         &v7);
  if ( v3 )
  {
    if ( v8 )
      DhcpFree(&v8);
    return v3;
  }
  else
  {
    v5 = v6;
    if ( v6 == 1 )
    {
      *a2 = v8;
      return 0;
    }
    else
    {
      if ( v8 )
      {
        DhcpFree(&v8);
        v5 = v6;
      }
      if ( (xmmword_18001E1E0 & 2) != 0 )
        WPP_SF_l(1025, 10, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, v5);
      return 13;
    }
  }
}

```

## disassembly

```asm
0x18000ec24  push    rbp
0x18000ec26  push    rbx
0x18000ec27  push    rdi
0x18000ec28  mov     rbp, rsp
0x18000ec2b  sub     rsp, 30h
0x18000ec2f  mov     rdi, rdx
0x18000ec32  mov     qword ptr [rdx], 0
0x18000ec39  mov     rdx, rcx
0x18000ec3c  mov     [rbp+arg_8], 0
0x18000ec43  lea     rax, [rbp+arg_10]
0x18000ec47  mov     [rbp+arg_10], 0
0x18000ec4e  lea     rcx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18000ec55  mov     [rbp+arg_18], 0
0x18000ec5d  lea     r9, [rbp+arg_8]
0x18000ec61  mov     [rsp+30h+var_10], rax; LPDWORD
0x18000ec66  lea     r8, [rbp+arg_18]
0x18000ec6a  call    DhcpRegReadFromLocation
0x18000ec6f  mov     ebx, eax
0x18000ec71  test    eax, eax
0x18000ec73  jz      short loc_18000EC89
0x18000ec75  cmp     [rbp+arg_18], 0
0x18000ec7a  jz      short loc_18000EC85
0x18000ec7c  lea     rcx, [rbp+arg_18]
0x18000ec80  call    DhcpFree
0x18000ec85  mov     eax, ebx
0x18000ec87  jmp     short loc_18000ECD6
0x18000ec89  mov     r9d, [rbp+arg_8]
0x18000ec8d  cmp     r9d, 1
0x18000ec91  jz      short loc_18000ECCD
0x18000ec93  cmp     [rbp+arg_18], 0
0x18000ec98  jz      short loc_18000ECA7
0x18000ec9a  lea     rcx, [rbp+arg_18]
0x18000ec9e  call    DhcpFree
0x18000eca3  mov     r9d, [rbp+arg_8]
0x18000eca7  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000ecae  jz      short loc_18000ECC6
0x18000ecb0  mov     edx, 0Ah
0x18000ecb5  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000ecbc  mov     ecx, 401h
0x18000ecc1  call    WPP_SF_l
0x18000ecc6  mov     eax, 0Dh
0x18000eccb  jmp     short loc_18000ECD6
0x18000eccd  mov     rax, [rbp+arg_18]
0x18000ecd1  mov     [rdi], rax
0x18000ecd4  xor     eax, eax
0x18000ecd6  add     rsp, 30h
0x18000ecda  pop     rdi
0x18000ecdb  pop     rbx
0x18000ecdc  pop     rbp
0x18000ecdd  retn
```
