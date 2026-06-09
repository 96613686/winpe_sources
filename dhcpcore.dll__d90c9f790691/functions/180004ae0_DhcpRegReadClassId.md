# DhcpRegReadClassId

- ea: `0x180004ae0`
- end: `0x180004c4c`
- name: `DhcpRegReadClassId`
- size: `364`
- prototype: `int __fastcall(__int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180003910`
- `0x1800227ac`
- `0x1800407c0`

## callees

- `0x180004ae0`
- `0x180004efc`
- `0x180005178`
- `0x1800056d4`
- `0x1800057f0`
- `0x180005da4`
- `0x180040eb4`

## string_xrefs

- `0x180004bb9`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpClassIdBin`
- `0x180004bf1`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpClassIdBin`

## pseudocode

```c
int __fastcall DhcpRegReadClassId(__int64 a1)
{
  void *v1; // r15
  void *v3; // rbx
  int result; // eax
  __int64 v5; // rcx
  LPVOID v6; // rsi
  int v7; // edi
  __int64 v8; // rax
  struct HKEY__ hKey; // [rsp+70h] [rbp+38h] BYREF
  int v10; // [rsp+78h] [rbp+40h]
  LPVOID v11; // [rsp+80h] [rbp+48h] BYREF
  void *Src; // [rsp+88h] [rbp+50h] BYREF

  v1 = *(void **)(a1 + 56);
  *(_QWORD *)(a1 + 736) = 0;
  *(_DWORD *)(a1 + 744) = 0;
  v11 = 0;
  hKey.unused = 0;
  v10 = 0;
  Src = 0;
  if ( (unsigned int)GetRegistryString(DhcpGlobalParametersKey, L"DhcpClientClassLocation", &Src, 0) || (v3 = Src) == 0 )
  {
    v3 = 0;
    Src = 0;
    result = DhcpRegReadFromLocation(
               L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpClassIdBin",
               v1,
               (LPDWORD)&hKey);
  }
  else
  {
    result = DhcpRegReadFromAnyLocation(Src, v1, &hKey);
  }
  v6 = v11;
  v7 = result;
  if ( result || !v11 )
  {
    result = FixupDhcpClassId((DWORD)v1);
    v7 = result;
    if ( !result )
    {
      if ( v3 )
        result = DhcpRegReadFromAnyLocation(v3, v1, &hKey);
      else
        result = DhcpRegReadFromLocation(
                   L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpClassIdBin",
                   v1,
                   (LPDWORD)&hKey);
      v6 = v11;
      v7 = result;
    }
  }
  if ( v3 )
    result = DhcpPunycodeFree(&Src);
  if ( !v7 && v6 )
  {
    v8 = DhcpAddClass(v5, v6, (unsigned int)hKey.unused);
    *(_QWORD *)(a1 + 736) = v8;
    if ( v8 )
      *(_DWORD *)(struct HKEY__ *)(a1 + 744) = hKey;
    return DhcpPunycodeFree(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180004ae0  push    rbp
0x180004ae2  push    rbx
0x180004ae3  push    rsi
0x180004ae4  push    rdi
0x180004ae5  push    r14
0x180004ae7  push    r15
0x180004ae9  mov     rbp, rsp
0x180004aec  sub     rsp, 38h
0x180004af0  mov     r15, [rcx+38h]
0x180004af4  lea     r8, [rbp+Src]
0x180004af8  mov     r14, rcx
0x180004afb  mov     qword ptr [rcx+2E0h], 0
0x180004b06  mov     dword ptr [rcx+2E8h], 0
0x180004b10  lea     rdx, aDhcpclientclas; "DhcpClientClassLocation"
0x180004b17  mov     rcx, cs:DhcpGlobalParametersKey; hKey
0x180004b1e  xor     r9d, r9d
0x180004b21  mov     [rbp+arg_10], 0
0x180004b29  mov     [rbp+arg_0.unused], 0
0x180004b30  mov     [rbp+arg_8], 0
0x180004b37  mov     [rbp+Src], 0
0x180004b3f  call    GetRegistryString
0x180004b44  test    eax, eax
0x180004b46  jnz     short loc_180004B9F
0x180004b48  mov     rbx, [rbp+Src]
0x180004b4c  test    rbx, rbx
0x180004b4f  jz      short loc_180004B9F
0x180004b51  lea     rax, [rbp+arg_0]
0x180004b55  mov     rdx, r15; void *
0x180004b58  lea     r9, [rbp+arg_8]
0x180004b5c  mov     [rsp+38h+hKey], rax; hKey
0x180004b61  lea     r8, [rbp+arg_10]
0x180004b65  mov     rcx, rbx; Src
0x180004b68  call    DhcpRegReadFromAnyLocation
0x180004b6d  mov     rsi, [rbp+arg_10]
0x180004b71  mov     edi, eax
0x180004b73  test    eax, eax
0x180004b75  jz      short loc_180004BC7
0x180004b77  mov     rcx, r15; ReservedMustBeZero
0x180004b7a  call    FixupDhcpClassId
0x180004b7f  mov     edi, eax
0x180004b81  test    eax, eax
0x180004b83  jz      short loc_180004BCE
0x180004b85  test    rbx, rbx
0x180004b88  jnz     short loc_180004C05
0x180004b8a  test    edi, edi
0x180004b8c  jz      loc_180004C13
0x180004b92  add     rsp, 38h
0x180004b96  pop     r15
0x180004b98  pop     r14
0x180004b9a  pop     rdi
0x180004b9b  pop     rsi
0x180004b9c  pop     rbx
0x180004b9d  pop     rbp
0x180004b9e  retn
0x180004b9f  xor     ebx, ebx
0x180004ba1  lea     rax, [rbp+arg_0]
0x180004ba5  lea     r9, [rbp+arg_8]
0x180004ba9  mov     [rbp+Src], rbx
0x180004bad  lea     r8, [rbp+arg_10]
0x180004bb1  mov     [rsp+38h+hKey], rax; LPDWORD
0x180004bb6  mov     rdx, r15; void *
0x180004bb9  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x180004bc0  call    DhcpRegReadFromLocation
0x180004bc5  jmp     short loc_180004B6D
0x180004bc7  test    rsi, rsi
0x180004bca  jnz     short loc_180004B85
0x180004bcc  jmp     short loc_180004B77
0x180004bce  lea     rax, [rbp+arg_0]
0x180004bd2  mov     rdx, r15; void *
0x180004bd5  mov     [rsp+38h+hKey], rax; LPDWORD
0x180004bda  lea     r9, [rbp+arg_8]
0x180004bde  lea     r8, [rbp+arg_10]
0x180004be2  test    rbx, rbx
0x180004be5  jz      short loc_180004BF1
0x180004be7  mov     rcx, rbx; Src
0x180004bea  call    DhcpRegReadFromAnyLocation
0x180004bef  jmp     short loc_180004BFD
0x180004bf1  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x180004bf8  call    DhcpRegReadFromLocation
0x180004bfd  mov     rsi, [rbp+arg_10]
0x180004c01  mov     edi, eax
0x180004c03  jmp     short loc_180004B85
0x180004c05  lea     rcx, [rbp+Src]
0x180004c09  call    DhcpPunycodeFree
0x180004c0e  jmp     loc_180004B8A
0x180004c13  test    rsi, rsi
0x180004c16  jz      loc_180004B92
0x180004c1c  mov     r8d, [rbp+arg_0.unused]
0x180004c20  mov     rdx, rsi
0x180004c23  call    DhcpAddClass
0x180004c28  mov     [r14+2E0h], rax
0x180004c2f  test    rax, rax
0x180004c32  jz      short loc_180004C3E
0x180004c34  mov     eax, [rbp+arg_0.unused]
0x180004c37  mov     [r14+2E8h], eax
0x180004c3e  lea     rcx, [rbp+arg_10]
0x180004c42  call    DhcpPunycodeFree
0x180004c47  jmp     loc_180004B92
```
