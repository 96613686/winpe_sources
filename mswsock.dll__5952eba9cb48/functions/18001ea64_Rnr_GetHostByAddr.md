# Rnr_GetHostByAddr

- ea: `0x18001ea64`
- end: `0x18001ed72`
- name: `Rnr_GetHostByAddr`
- size: `782`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001f4e0`

## callees

- `0x180003804`
- `0x180016120`
- `0x1800164fc`
- `0x180016690`
- `0x18001ea64`
- `0x1800222f0`
- `0x18003847c`
- `0x180038a20`
- `0x18003a294`
- `0x18003ac78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ed09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ed09`
- `DNSAPI!DnsWriteReverseNameStringForIpAddressW` at `0x18001eb7a`
- `DNSAPI!DnsWriteReverseNameStringForIpAddressW` at `0x18001eb7a`
- `DNSAPI!DnsStringToAddress` at `0x18001eb4a`
- `DNSAPI!DnsStringToAddress` at `0x18001eb4a`
- `DNSAPI!DnsIp6AddressToReverseNameW` at `0x18001ebd1`
- `DNSAPI!DnsIp6AddressToReverseNameW` at `0x18001ebd1`

## pseudocode

```c
PCWSTR *__fastcall Rnr_GetHostByAddr(__int64 a1)
{
  unsigned __int64 v1; // rsi
  __int64 v2; // r14
  __int64 v3; // r15
  int v5; // edx
  int v6; // ecx
  int v7; // r8d
  PCWSTR *v9; // rbx
  __int64 v10; // rbx
  PCWSTR *v11; // rax
  DWORD v12; // ecx
  DWORD LastError; // eax
  int v14[4]; // [rsp+70h] [rbp-268h] BYREF
  _BYTE v15[12]; // [rsp+80h] [rbp-258h] BYREF
  int v16; // [rsp+8Ch] [rbp-24Ch]
  int v17; // [rsp+90h] [rbp-248h] BYREF
  unsigned int v18; // [rsp+98h] [rbp-240h] BYREF
  __int64 v19; // [rsp+9Ch] [rbp-23Ch]
  int v20; // [rsp+A4h] [rbp-234h]
  WCHAR v21[256]; // [rsp+B0h] [rbp-228h] BYREF

  v1 = *(unsigned int *)(a1 + 60);
  v2 = a1 + 184;
  v3 = *(_QWORD *)(a1 + 176);
  v14[0] = 0;
  v17 = 16;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_sqqqq(
      a1,
      11,
      (unsigned int)WPP_45d3a0903cdc3d772df6663ef7adae14_Traceguids,
      (unsigned int)"Rnr_GetHostByAddr",
      a1,
      0,
      0,
      0);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_qSD(v6, v5, v7, a1, v2, v1);
  }
  if ( !(unsigned __int8)RNRPROV_SockEnterApi() )
    return 0;
  v9 = 0;
  v14[0] = 0;
  if ( !(unsigned int)DnsStringToAddress(&v18, &v17, v2, v14) )
    goto LABEL_24;
  if ( v14[0] == 2 )
  {
    DnsWriteReverseNameStringForIpAddressW(v21, v18);
  }
  else
  {
    if ( v14[0] != 23 )
    {
LABEL_24:
      v12 = 11004;
      goto LABEL_25;
    }
    *(_DWORD *)v15 = v18;
    v16 = v20;
    *(_QWORD *)&v15[4] = v19;
    DnsIp6AddressToReverseNameW(v21, v15);
  }
  if ( (xmmword_180063D60 & 8) != 0 )
    WPP_SF_S(1027, 13, WPP_45d3a0903cdc3d772df6663ef7adae14_Traceguids, v21);
  v10 = (v1 >> 9) & 8;
  *(_QWORD *)v15 = v10;
  if ( v14[0] == 2 && (unsigned int)Rnr_CheckIfUseNbt(a1) )
  {
    v10 |= 0x20000uLL;
    *(_QWORD *)v15 = v10;
  }
  if ( (v1 & 0x400000) != 0 )
  {
    v10 |= 0x8000000uLL;
    *(_QWORD *)v15 = v10;
  }
  if ( (v3 & 1) != 0 )
  {
    v10 |= 0x4000000uLL;
    *(_QWORD *)v15 = v10;
  }
  if ( (v3 & 2) != 0 )
    *(_QWORD *)v15 = v10 | 0x2000000000000000LL;
  v11 = SaBlob_Query(
          v21,
          0xCu,
          (ULONG64 *)v15,
          0,
          1,
          *(_DWORD *)(a1 + 72),
          (HANDLE *)(a1 + 128),
          (_DWORD *)(a1 + 136),
          (_DWORD *)(a1 + 140),
          (_QWORD *)(a1 + 168),
          *(_DWORD *)(a1 + 144),
          *(_QWORD *)(a1 + 152),
          *(_DWORD *)(a1 + 160));
  v9 = v11;
  if ( !v11 )
    goto LABEL_24;
  Print_SaBlob("After GetHostByAddr()", v11);
  v12 = 0;
LABEL_25:
  SetLastError(v12);
  if ( (xmmword_180063D60 & 8) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_qD(1027, 14, WPP_45d3a0903cdc3d772df6663ef7adae14_Traceguids, v9, LastError);
  }
  return v9;
}

```

## disassembly

```asm
0x18001ea64  mov     [rsp+arg_8], rbx
0x18001ea69  mov     [rsp+arg_10], rsi
0x18001ea6e  push    rdi
0x18001ea6f  push    r14
0x18001ea71  push    r15
0x18001ea73  sub     rsp, 2C0h
0x18001ea7a  mov     rax, cs:__security_cookie
0x18001ea81  xor     rax, rsp
0x18001ea84  mov     [rsp+2D8h+var_28], rax
0x18001ea8c  mov     esi, [rcx+3Ch]
0x18001ea8f  lea     r14, [rcx+0B8h]
0x18001ea96  mov     r15, [rcx+0B0h]
0x18001ea9d  mov     rdi, rcx
0x18001eaa0  mov     [rsp+2D8h+var_268], 0
0x18001eaa8  mov     [rsp+2D8h+var_248], 10h
0x18001eab3  mov     al, byte ptr cs:xmmword_180063D60
0x18001eab9  test    al, 2
0x18001eabb  jz      short loc_18001EB10
0x18001eabd  mov     [rsp+2D8h+var_2A0], 0
0x18001eac6  lea     r9, aRnrGethostbyad; "Rnr_GetHostByAddr"
0x18001eacd  mov     [rsp+2D8h+var_2A8], 0
0x18001ead6  lea     r8, WPP_45d3a0903cdc3d772df6663ef7adae14_Traceguids
0x18001eadd  mov     [rsp+2D8h+var_2B0], 0
0x18001eae6  mov     edx, 0Bh
0x18001eaeb  mov     [rsp+2D8h+var_2B8], rcx
0x18001eaf0  call    WPP_SF_sqqqq
0x18001eaf5  mov     al, byte ptr cs:xmmword_180063D60
0x18001eafb  test    al, 2
0x18001eafd  jz      short loc_18001EB10
0x18001eaff  mov     dword ptr [rsp+2D8h+var_2B0], esi
0x18001eb03  mov     r9, rdi
0x18001eb06  mov     [rsp+2D8h+var_2B8], r14
0x18001eb0b  call    WPP_SF_qSD
0x18001eb10  call    RNRPROV_SockEnterApi
0x18001eb15  test    al, al
0x18001eb17  jnz     short loc_18001EB20
0x18001eb19  xor     eax, eax
0x18001eb1b  jmp     loc_18001ED48
0x18001eb20  xor     ebx, ebx
0x18001eb22  lea     r9, [rsp+2D8h+var_268]
0x18001eb27  mov     dword ptr [rsp+2D8h+var_2B0], ebx
0x18001eb2b  lea     rdx, [rsp+2D8h+var_248]
0x18001eb33  mov     r8, r14
0x18001eb36  mov     dword ptr [rsp+2D8h+var_2B8], 1
0x18001eb3e  lea     rcx, [rsp+2D8h+var_240]
0x18001eb46  mov     [rsp+2D8h+var_268], ebx
0x18001eb4a  call    cs:__imp_DnsStringToAddress
0x18001eb51  nop     dword ptr [rax+rax+00h]
0x18001eb56  mov     r14d, 403h
0x18001eb5c  test    eax, eax
0x18001eb5e  jz      loc_18001ED04
0x18001eb64  cmp     [rsp+2D8h+var_268], 2
0x18001eb69  jnz     short loc_18001EB88
0x18001eb6b  mov     edx, [rsp+2D8h+var_240]
0x18001eb72  lea     rcx, [rsp+2D8h+var_228]
0x18001eb7a  call    cs:__imp_DnsWriteReverseNameStringForIpAddressW
0x18001eb81  nop     dword ptr [rax+rax+00h]
0x18001eb86  jmp     short loc_18001EBDD
0x18001eb88  cmp     [rsp+2D8h+var_268], 17h
0x18001eb8d  jnz     loc_18001ED04
0x18001eb93  mov     eax, [rsp+2D8h+var_240]
0x18001eb9a  lea     rdx, [rsp+2D8h+var_258]
0x18001eba2  movsd   xmm0, [rsp+2D8h+var_23C]
0x18001ebab  lea     rcx, [rsp+2D8h+var_228]
0x18001ebb3  mov     dword ptr [rsp+2D8h+var_258], eax
0x18001ebba  mov     eax, [rsp+2D8h+var_234]
0x18001ebc1  mov     [rsp+2D8h+var_24C], eax
0x18001ebc8  movsd   qword ptr [rsp+2D8h+var_258+4], xmm0
0x18001ebd1  call    cs:__imp_DnsIp6AddressToReverseNameW
0x18001ebd8  nop     dword ptr [rax+rax+00h]
0x18001ebdd  test    byte ptr cs:xmmword_180063D60, 8
0x18001ebe4  jz      short loc_18001EC02
0x18001ebe6  mov     edx, 0Dh
0x18001ebeb  lea     r9, [rsp+2D8h+var_228]
0x18001ebf3  mov     ecx, r14d
0x18001ebf6  lea     r8, WPP_45d3a0903cdc3d772df6663ef7adae14_Traceguids
0x18001ebfd  call    WPP_SF_S
0x18001ec02  mov     rbx, rsi
0x18001ec05  shr     rbx, 9
0x18001ec09  and     ebx, 8
0x18001ec0c  cmp     [rsp+2D8h+var_268], 2
0x18001ec11  mov     qword ptr [rsp+2D8h+var_258], rbx
0x18001ec19  jnz     short loc_18001EC34
0x18001ec1b  mov     rcx, rdi
0x18001ec1e  call    Rnr_CheckIfUseNbt
0x18001ec23  test    eax, eax
0x18001ec25  jz      short loc_18001EC34
0x18001ec27  bts     rbx, 11h
0x18001ec2c  mov     qword ptr [rsp+2D8h+var_258], rbx
0x18001ec34  bt      esi, 16h
0x18001ec38  jnb     short loc_18001EC47
0x18001ec3a  bts     rbx, 1Bh
0x18001ec3f  mov     qword ptr [rsp+2D8h+var_258], rbx
0x18001ec47  test    r15b, 1
0x18001ec4b  jz      short loc_18001EC5A
0x18001ec4d  bts     rbx, 1Ah
0x18001ec52  mov     qword ptr [rsp+2D8h+var_258], rbx
0x18001ec5a  test    r15b, 2
0x18001ec5e  jz      short loc_18001EC75
0x18001ec60  mov     rax, 2000000000000000h
0x18001ec6a  or      rbx, rax
0x18001ec6d  mov     qword ptr [rsp+2D8h+var_258], rbx
0x18001ec75  mov     eax, [rdi+0A0h]
0x18001ec7b  lea     rcx, [rdi+0A8h]
0x18001ec82  mov     [rsp+2D8h+var_278], eax
0x18001ec86  lea     r8, [rdi+8Ch]
0x18001ec8d  mov     rax, [rdi+98h]
0x18001ec94  lea     r9, [rdi+88h]
0x18001ec9b  mov     [rsp+2D8h+var_280], rax
0x18001eca0  lea     r10, [rdi+80h]
0x18001eca7  mov     eax, [rdi+90h]
0x18001ecad  mov     edx, 0Ch
0x18001ecb2  mov     [rsp+2D8h+var_288], eax
0x18001ecb6  mov     eax, [rdi+48h]
0x18001ecb9  mov     [rsp+2D8h+var_290], rcx
0x18001ecbe  lea     rcx, [rsp+2D8h+var_228]
0x18001ecc6  mov     [rsp+2D8h+var_298], r8
0x18001eccb  lea     r8, [rsp+2D8h+var_258]
0x18001ecd3  mov     [rsp+2D8h+var_2A0], r9
0x18001ecd8  xor     r9d, r9d
0x18001ecdb  mov     [rsp+2D8h+var_2A8], r10
0x18001ece0  mov     dword ptr [rsp+2D8h+var_2B0], eax
0x18001ece4  call    SaBlob_Query
0x18001ece9  mov     rbx, rax
0x18001ecec  test    rax, rax
0x18001ecef  jz      short loc_18001ED04
0x18001ecf1  mov     rdx, rax
0x18001ecf4  lea     rcx, aAfterGethostby; "After GetHostByAddr()"
0x18001ecfb  call    Print_SaBlob
0x18001ed00  xor     ecx, ecx
0x18001ed02  jmp     short loc_18001ED09
0x18001ed04  mov     ecx, 2AFCh; dwErrCode
0x18001ed09  call    cs:__imp_SetLastError
0x18001ed10  nop     dword ptr [rax+rax+00h]
0x18001ed15  test    byte ptr cs:xmmword_180063D60, 8
0x18001ed1c  jz      short loc_18001ED45
0x18001ed1e  call    cs:__imp_GetLastError
0x18001ed25  nop     dword ptr [rax+rax+00h]
0x18001ed2a  mov     edx, 0Eh
0x18001ed2f  lea     r8, WPP_45d3a0903cdc3d772df6663ef7adae14_Traceguids
0x18001ed36  mov     ecx, r14d
0x18001ed39  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x18001ed3d  mov     r9, rbx
0x18001ed40  call    WPP_SF_qD
0x18001ed45  mov     rax, rbx
0x18001ed48  mov     rcx, [rsp+2D8h+var_28]
0x18001ed50  xor     rcx, rsp; StackCookie
0x18001ed53  call    __security_check_cookie
0x18001ed58  lea     r11, [rsp+2D8h+var_18]
0x18001ed60  mov     rbx, [r11+28h]
0x18001ed64  mov     rsi, [r11+30h]
0x18001ed68  mov     rsp, r11
0x18001ed6b  pop     r15
0x18001ed6d  pop     r14
0x18001ed6f  pop     rdi
0x18001ed70  retn
```
