# UpdateRegistryforReachableGateway

- ea: `0x180036bb8`
- end: `0x180036d58`
- name: `UpdateRegistryforReachableGateway`
- size: `416`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800205e4`
- `0x18003e2f4`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x180036bb8`
- `0x180047e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036d0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036d3b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036d0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036d3b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180036bdd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180036bf1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180036bdd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180036bf1`

## pseudocode

```c
int __fastcall UpdateRegistryforReachableGateway(__int64 a1)
{
  void *v2; // rax
  unsigned int v3; // r8d
  __int64 v4; // r9
  DWORD cbData; // edi
  __int64 v6; // rdx
  char *v7; // rdx
  const BYTE *lpData; // rsi
  bool v9; // zf
  __int64 v10; // r8
  char *v11; // rbp
  unsigned int v12; // r8d
  __int64 v13; // rax
  const void *v14; // rdx
  unsigned int Data; // [rsp+50h] [rbp+8h] BYREF
  LPVOID v17; // [rsp+58h] [rbp+10h] BYREF

  Data = 0;
  RegDeleteValueW(*(HKEY *)(a1 + 728), L"DhcpGatewayHardware");
  LODWORD(v2) = RegDeleteValueW(*(HKEY *)(a1 + 728), L"DhcpGatewayHardwareCount");
  v3 = *(_DWORD *)(a1 + 1912);
  if ( v3 )
  {
    v4 = *(_QWORD *)(a1 + 1904);
    if ( v4 )
    {
      cbData = 0;
      Data = 0;
      v6 = 0;
      do
      {
        cbData += *(_DWORD *)(v4 + 24 * v6 + 16) + 8;
        v6 = (unsigned int)(v6 + 1);
        Data = v6;
      }
      while ( (unsigned int)v6 < v3 );
      v2 = DhcpAlloc(cbData);
      v17 = v2;
      v7 = (char *)v2;
      lpData = (const BYTE *)v2;
      if ( v2 )
      {
        v9 = *(_DWORD *)(a1 + 1912) == 0;
        Data = 0;
        if ( !v9 )
        {
          v10 = 0;
          do
          {
            v11 = v7 + 8;
            *(_DWORD *)v7 = *(_DWORD *)(*(_QWORD *)(a1 + 1904) + 24 * v10);
            *((_DWORD *)v7 + 1) = *(_DWORD *)(*(_QWORD *)(a1 + 1904) + 24LL * Data + 16);
            v12 = Data;
            v13 = *(_QWORD *)(a1 + 1904);
            v14 = *(const void **)(v13 + 24LL * Data + 8);
            if ( v14 )
            {
              memcpy_0(v11, v14, *(unsigned int *)(v13 + 24LL * Data + 16));
              v12 = Data;
              v7 = &v11[*(unsigned int *)(*(_QWORD *)(a1 + 1904) + 24LL * Data + 16)];
            }
            else
            {
              v7 = v11;
            }
            v10 = v12 + 1;
            Data = v10;
          }
          while ( (unsigned int)v10 < *(_DWORD *)(a1 + 1912) );
        }
        RegSetValueExW(*(HKEY *)(a1 + 728), L"DhcpGatewayHardware", 0, 3u, lpData, cbData);
        RegSetValueExW(*(HKEY *)(a1 + 728), L"DhcpGatewayHardwareCount", 0, 4u, (const BYTE *)&Data, 4u);
        LODWORD(v2) = DhcpPunycodeFree(&v17);
      }
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x180036bb8  mov     [rsp+arg_10], rbx
0x180036bbd  push    rbp
0x180036bbe  push    rsi
0x180036bbf  push    rdi
0x180036bc0  sub     rsp, 30h
0x180036bc4  mov     rbx, rcx
0x180036bc7  mov     [rsp+48h+Data], 0
0x180036bcf  mov     rcx, [rcx+2D8h]; hKey
0x180036bd6  lea     rdx, aDhcpgatewayhar; "DhcpGatewayHardware"
0x180036bdd  call    cs:__imp_RegDeleteValueW
0x180036be3  mov     rcx, [rbx+2D8h]; hKey
0x180036bea  lea     rdx, aDhcpgatewayhar_0; "DhcpGatewayHardwareCount"
0x180036bf1  call    cs:__imp_RegDeleteValueW
0x180036bf7  mov     r8d, [rbx+778h]
0x180036bfe  test    r8d, r8d
0x180036c01  jz      loc_180036D4B
0x180036c07  mov     r9, [rbx+770h]
0x180036c0e  test    r9, r9
0x180036c11  jz      loc_180036D4B
0x180036c17  xor     edi, edi
0x180036c19  mov     [rsp+48h+Data], edi
0x180036c1d  test    r8d, r8d
0x180036c20  jz      short loc_180036C3B
0x180036c22  xor     edx, edx
0x180036c24  add     edi, 8
0x180036c27  lea     rcx, [rdx+rdx*2]
0x180036c2b  add     edi, [r9+rcx*8+10h]
0x180036c30  inc     edx
0x180036c32  mov     [rsp+48h+Data], edx
0x180036c36  cmp     edx, r8d
0x180036c39  jb      short loc_180036C24
0x180036c3b  mov     ecx, edi
0x180036c3d  call    DhcpAlloc
0x180036c42  mov     [rsp+48h+arg_8], rax
0x180036c47  mov     rdx, rax
0x180036c4a  mov     rsi, rax
0x180036c4d  test    rax, rax
0x180036c50  jz      loc_180036D4B
0x180036c56  cmp     dword ptr [rbx+778h], 0
0x180036c5d  mov     [rsp+48h+Data], 0
0x180036c65  jbe     loc_180036CEC
0x180036c6b  xor     r8d, r8d
0x180036c6e  mov     rax, [rbx+770h]
0x180036c75  lea     rcx, [r8+r8*2]
0x180036c79  lea     rbp, [rdx+8]
0x180036c7d  mov     ecx, [rax+rcx*8]
0x180036c80  mov     [rdx], ecx
0x180036c82  mov     eax, [rsp+48h+Data]
0x180036c86  lea     rcx, [rax+rax*2]
0x180036c8a  mov     rax, [rbx+770h]
0x180036c91  mov     ecx, [rax+rcx*8+10h]
0x180036c95  mov     [rdx+4], ecx
0x180036c98  mov     r8d, [rsp+48h+Data]
0x180036c9d  mov     rax, [rbx+770h]
0x180036ca4  lea     rcx, [r8+r8*2]
0x180036ca8  mov     rdx, [rax+rcx*8+8]; Src
0x180036cad  test    rdx, rdx
0x180036cb0  jz      short loc_180036CD8
0x180036cb2  mov     r8d, [rax+rcx*8+10h]; Size
0x180036cb7  mov     rcx, rbp; void *
0x180036cba  call    memcpy_0
0x180036cbf  mov     r8d, [rsp+48h+Data]
0x180036cc4  mov     rax, [rbx+770h]
0x180036ccb  lea     rcx, [r8+r8*2]
0x180036ccf  mov     edx, [rax+rcx*8+10h]
0x180036cd3  add     rdx, rbp
0x180036cd6  jmp     short loc_180036CDB
0x180036cd8  mov     rdx, rbp
0x180036cdb  inc     r8d
0x180036cde  mov     [rsp+48h+Data], r8d
0x180036ce3  cmp     r8d, [rbx+778h]
0x180036cea  jb      short loc_180036C6E
0x180036cec  mov     rcx, [rbx+2D8h]; hKey
0x180036cf3  lea     rdx, aDhcpgatewayhar; "DhcpGatewayHardware"
0x180036cfa  mov     [rsp+48h+cbData], edi; cbData
0x180036cfe  mov     r9d, 3; dwType
0x180036d04  xor     r8d, r8d; Reserved
0x180036d07  mov     [rsp+48h+lpData], rsi; lpData
0x180036d0c  call    cs:__imp_RegSetValueExW
0x180036d12  mov     rcx, [rbx+2D8h]; hKey
0x180036d19  lea     rax, [rsp+48h+Data]
0x180036d1e  mov     [rsp+48h+cbData], 4; cbData
0x180036d26  lea     rdx, aDhcpgatewayhar_0; "DhcpGatewayHardwareCount"
0x180036d2d  mov     r9d, 4; dwType
0x180036d33  mov     [rsp+48h+lpData], rax; lpData
0x180036d38  xor     r8d, r8d; Reserved
0x180036d3b  call    cs:__imp_RegSetValueExW
0x180036d41  lea     rcx, [rsp+48h+arg_8]
0x180036d46  call    DhcpPunycodeFree
0x180036d4b  mov     rbx, [rsp+48h+arg_10]
0x180036d50  add     rsp, 30h
0x180036d54  pop     rdi
0x180036d55  pop     rsi
0x180036d56  pop     rbp
0x180036d57  retn
```
