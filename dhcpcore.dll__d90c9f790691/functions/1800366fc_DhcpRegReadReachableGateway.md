# DhcpRegReadReachableGateway

- ea: `0x1800366fc`
- end: `0x1800368c8`
- name: `DhcpRegReadReachableGateway`
- size: `460`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800026fc`

## callees

- `0x1800057f0`
- `0x180005994`
- `0x180006440`
- `0x1800366fc`
- `0x180047e3c`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800367b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800367b5`

## pseudocode

```c
BOOL __fastcall DhcpRegReadReachableGateway(__int64 a1)
{
  HKEY v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // edi
  HKEY v5; // rcx
  __int64 v6; // r12
  BYTE *v7; // rsi
  LPVOID v8; // rax
  __int64 v9; // r15
  void *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // xmm1_8
  __int64 v13; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-30h] BYREF
  BYTE *v16; // [rsp+38h] [rbp-28h] BYREF
  LPVOID v17; // [rsp+40h] [rbp-20h] BYREF
  __int128 v18; // [rsp+48h] [rbp-18h]
  __int64 v19; // [rsp+58h] [rbp-8h]
  DWORD v20; // [rsp+A0h] [rbp+40h] BYREF
  DWORD v21; // [rsp+A8h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+50h] BYREF
  DWORD Type; // [rsp+B8h] [rbp+58h] BYREF

  v20 = 0;
  v2 = *(HKEY *)(a1 + 728);
  v21 = 0;
  v16 = 0;
  v17 = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  v3 = DhcpQueryRegistryValue(v2, L"DhcpGatewayHardware", &v21, &v20, &v16);
  if ( v3 )
  {
LABEL_13:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 102, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v3);
    return DhcpPunycodeFree(&v17);
  }
  v4 = v20;
  if ( !v20 || v21 != 3 )
    goto LABEL_12;
  v5 = *(HKEY *)(a1 + 728);
  cbData = 4;
  v3 = RegQueryValueExW(v5, L"DhcpGatewayHardwareCount", 0, &Type, Data, &cbData);
  if ( v3 )
    goto LABEL_13;
  if ( Type != 4 )
  {
LABEL_12:
    v3 = 87;
    goto LABEL_13;
  }
  v6 = 0;
  v7 = v16;
  v17 = v16;
  v8 = DhcpAlloc(24LL * *(unsigned int *)Data);
  *(_QWORD *)(a1 + 1904) = v8;
  if ( !v8 )
    goto LABEL_13;
  while ( v4 )
  {
    DWORD1(v18) = 0;
    HIDWORD(v19) = 0;
    if ( v4 < 8 )
      break;
    v9 = *((unsigned int *)v7 + 1);
    LODWORD(v18) = *(_DWORD *)v7;
    LODWORD(v19) = v9;
    v10 = DhcpAlloc((unsigned int)v9);
    *((_QWORD *)&v18 + 1) = v10;
    if ( v4 < (unsigned int)v9 )
      break;
    if ( !v10 )
      goto LABEL_13;
    memcpy_0(v10, v7 + 8, (unsigned int)v9);
    v11 = 3 * v6;
    v12 = v19;
    v4 += -8 - v9;
    v13 = *(_QWORD *)(a1 + 1904);
    v7 += v9 + 8;
    v6 = (unsigned int)(v6 + 1);
    *(_OWORD *)(v13 + 8 * v11) = v18;
    *(_QWORD *)(v13 + 8 * v11 + 16) = v12;
    *(_DWORD *)(a1 + 1912) = v6;
  }
  return DhcpPunycodeFree(&v17);
}

```

## disassembly

```asm
0x1800366fc  push    rbp
0x1800366fe  push    rbx
0x1800366ff  push    rsi
0x180036700  push    rdi
0x180036701  push    r12
0x180036703  push    r14
0x180036705  push    r15
0x180036707  mov     rbp, rsp
0x18003670a  sub     rsp, 60h
0x18003670e  mov     r14, rcx
0x180036711  mov     [rbp+arg_0], 0
0x180036718  mov     rcx, [rcx+2D8h]
0x18003671f  lea     rax, [rbp+var_28]
0x180036723  lea     r9, [rbp+arg_0]
0x180036727  mov     [rsp+60h+lpData], rax
0x18003672c  lea     r8, [rbp+arg_8]
0x180036730  mov     [rbp+arg_8], 0
0x180036737  lea     rdx, aDhcpgatewayhar; "DhcpGatewayHardware"
0x18003673e  mov     [rbp+var_28], 0
0x180036746  mov     [rbp+var_20], 0
0x18003674e  mov     dword ptr [rbp+Data], 0
0x180036755  mov     [rbp+Type], 0
0x18003675c  mov     [rbp+cbData], 0
0x180036763  call    DhcpQueryRegistryValue
0x180036768  mov     ebx, eax
0x18003676a  test    eax, eax
0x18003676c  jnz     loc_18003688E
0x180036772  mov     edi, [rbp+arg_0]
0x180036775  test    edi, edi
0x180036777  jz      loc_180036889
0x18003677d  cmp     [rbp+arg_8], 3
0x180036781  jnz     loc_180036889
0x180036787  mov     rcx, [r14+2D8h]; hKey
0x18003678e  lea     rax, [rbp+cbData]
0x180036792  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180036797  lea     r9, [rbp+Type]; lpType
0x18003679b  lea     rax, [rbp+Data]
0x18003679f  mov     [rbp+cbData], 4
0x1800367a6  xor     r8d, r8d; lpReserved
0x1800367a9  mov     [rsp+60h+lpData], rax; lpData
0x1800367ae  lea     rdx, aDhcpgatewayhar_0; "DhcpGatewayHardwareCount"
0x1800367b5  call    cs:__imp_RegQueryValueExW
0x1800367bb  mov     ebx, eax
0x1800367bd  test    eax, eax
0x1800367bf  jnz     loc_18003688E
0x1800367c5  cmp     [rbp+Type], 4
0x1800367c9  jnz     loc_180036889
0x1800367cf  mov     eax, dword ptr [rbp+Data]
0x1800367d2  xor     r12d, r12d
0x1800367d5  mov     rsi, [rbp+var_28]
0x1800367d9  mov     [rbp+var_20], rsi
0x1800367dd  lea     rcx, [rax+rax*2]
0x1800367e1  shl     rcx, 3
0x1800367e5  call    DhcpAlloc
0x1800367ea  mov     [r14+770h], rax
0x1800367f1  test    rax, rax
0x1800367f4  jz      loc_18003688E
0x1800367fa  test    edi, edi
0x1800367fc  jz      loc_1800368B0
0x180036802  mov     dword ptr [rbp+var_18+4], 0
0x180036809  mov     dword ptr [rbp+var_8+4], 0
0x180036810  cmp     edi, 8
0x180036813  jb      loc_1800368B0
0x180036819  mov     r15d, [rsi+4]
0x18003681d  mov     eax, [rsi]
0x18003681f  mov     ecx, r15d
0x180036822  mov     dword ptr [rbp+var_18], eax
0x180036825  mov     dword ptr [rbp+var_8], r15d
0x180036829  call    DhcpAlloc
0x18003682e  mov     qword ptr [rbp+var_18+8], rax
0x180036832  cmp     edi, r15d
0x180036835  jb      short loc_1800368B0
0x180036837  test    rax, rax
0x18003683a  jz      short loc_18003688E
0x18003683c  lea     rdx, [rsi+8]; Src
0x180036840  mov     r8d, r15d; Size
0x180036843  mov     rcx, rax; void *
0x180036846  call    memcpy_0
0x18003684b  movups  xmm0, [rbp+var_18]
0x18003684f  lea     rcx, [r12+r12*2]
0x180036853  mov     eax, 0FFFFFFF8h
0x180036858  movsd   xmm1, [rbp+var_8]
0x18003685d  sub     eax, r15d
0x180036860  add     edi, eax
0x180036862  add     rsi, 8
0x180036866  mov     rax, [r14+770h]
0x18003686d  add     rsi, r15
0x180036870  inc     r12d
0x180036873  movups  xmmword ptr [rax+rcx*8], xmm0
0x180036877  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18003687d  mov     [r14+778h], r12d
0x180036884  jmp     loc_1800367FA
0x180036889  mov     ebx, 57h ; 'W'
0x18003688e  test    byte ptr cs:xmmword_1800616A0, 2
0x180036895  jz      short loc_1800368B0
0x180036897  mov     edx, 66h ; 'f'
0x18003689c  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800368a3  mov     ecx, 401h
0x1800368a8  mov     r9d, ebx
0x1800368ab  call    WPP_SF_D
0x1800368b0  lea     rcx, [rbp+var_20]
0x1800368b4  call    DhcpPunycodeFree
0x1800368b9  add     rsp, 60h
0x1800368bd  pop     r15
0x1800368bf  pop     r14
0x1800368c1  pop     r12
0x1800368c3  pop     rdi
0x1800368c4  pop     rsi
0x1800368c5  pop     rbx
0x1800368c6  pop     rbp
0x1800368c7  retn
```
