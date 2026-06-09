# DhcpInitOptionDefList

- ea: `0x180018cd4`
- end: `0x180018fb4`
- name: `DhcpInitOptionDefList`
- size: `736`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180011454`

## callees

- `0x180005670`
- `0x180006440`
- `0x1800069d0`
- `0x180010e00`
- `0x180011efc`
- `0x180018cd4`
- `0x180018fbc`
- `0x180047e3c`
- `0x18004d1a0`

## string_xrefs

- `0x180018d66`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DhcpDomain`
- `0x180018d55`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DhcpDomain`
- `0x180018d00`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DhcpNameServer`
- `0x180018cf7`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DhcpNameServer`
- `0x180018dc4`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces\Tcpip_?\DhcpNameServerList`
- `0x180018dce`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces\Tcpip_?\DhcpNameServerList`
- `0x180018e87`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces\Tcpip_?\DhcpNameServerList`
- `0x180018ed3`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpRequestOptions`

## pseudocode

```c
__int64 DhcpInitOptionDefList()
{
  int IsWCOSSystem; // eax
  const wchar_t *psz; // rcx
  unsigned int v2; // eax
  int v3; // eax
  const wchar_t *v4; // rcx
  unsigned int v5; // eax
  int v6; // esi
  const wchar_t *v7; // rdi
  unsigned int v8; // eax
  int v9; // eax
  int v10; // ebx
  HRESULT v11; // eax
  unsigned int v12; // esi
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  _QWORD *v15; // rax
  int v16; // edi
  const wchar_t *v17; // rbx
  const wchar_t *v18; // rcx
  unsigned int v19; // eax
  int v20; // eax
  unsigned int v21; // edi
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  _QWORD *v24; // rax
  int v26; // [rsp+70h] [rbp+30h] BYREF
  size_t pcchLength; // [rsp+78h] [rbp+38h] BYREF

  IsWCOSSystem = DhcpIsWCOSSystem();
  psz = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DhcpNameServer";
  if ( !IsWCOSSystem )
    psz = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DhcpNameServer";
  v2 = DhcpAddOptionDef((__int64)psz, 6, 0, 0, 0, 0, psz, 3);
  if ( v2 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 15, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, v2);
  v3 = DhcpIsWCOSSystem();
  v4 = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DhcpDomain";
  if ( !v3 )
    v4 = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DhcpDomain";
  v5 = DhcpAddOptionDef((__int64)v4, 15, 0, 0, 0, 0, v4, 1);
  if ( v5 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 16, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, v5);
  v26 = 0;
  v6 = 0;
  v7 = L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces\\Tcpip_?\\DhcpNameServerList";
  v8 = WxStringCchLengthDWordW(
         L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces\\Tcpip_?\\DhcpNameServerList",
         512,
         &v26);
  v9 = WX_WIN32_FROM_HR(v8);
  v10 = v26;
  while ( v10 && v9 >= 0 )
  {
    pcchLength = 0;
    v7 += (unsigned int)(v10 + 1);
    v26 = 0;
    v6 += 2 * v10 + 2;
    if ( !v7 )
    {
      v11 = -2147024809;
      HIDWORD(pcchLength) = 77;
LABEL_15:
      v10 = v26;
      goto LABEL_19;
    }
    v11 = StringCchLengthW(v7, 0x200u, &pcchLength);
    if ( v11 < 0 )
    {
      HIDWORD(pcchLength) = 81;
      goto LABEL_15;
    }
    v10 = pcchLength;
LABEL_19:
    v9 = WX_WIN32_FROM_HR((unsigned int)v11);
  }
  v12 = v6 + 2;
  v13 = DhcpAlloc(v12 + 64);
  v14 = v13;
  if ( v13 )
  {
    v13[6] = v13 + 8;
    v13[2] = 44;
    v13[3] = 0;
    *((_DWORD *)v13 + 8) = 0;
    *((_DWORD *)v13 + 14) = 3;
    v13[5] = 0;
    memcpy_0(
      v13 + 8,
      L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces\\Tcpip_?\\DhcpNameServerList",
      v12);
    v15 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v14 = &DhcpGlobalOptionDefList;
      v14[1] = v15;
      *v15 = v14;
      off_1800610C0[0] = (_UNKNOWN **)v14;
      goto LABEL_26;
    }
    goto LABEL_36;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 17, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
LABEL_26:
  v16 = 0;
  v17 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpRequestOptions";
  v18 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpRequestOptions";
  while ( 1 )
  {
    v26 = 0;
    v19 = WxStringCchLengthDWordW(v18, 512, &v26);
    v20 = WX_WIN32_FROM_HR(v19);
    if ( !v26 || v20 < 0 )
      break;
    v17 += (unsigned int)(v26 + 1);
    v18 = v17;
    v16 += 2 * v26 + 2;
  }
  v21 = v16 + 2;
  v22 = DhcpAlloc(v21 + 64);
  v23 = v22;
  if ( v22 )
  {
    v22[5] = v22 + 8;
    v22[2] = 55;
    v22[3] = 0;
    *((_DWORD *)v22 + 8) = 0;
    *((_DWORD *)v22 + 14) = 0;
    memcpy_0(v22 + 8, L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpRequestOptions", v21);
    v23[6] = 0;
    v24 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v23 = &DhcpGlobalOptionDefList;
      v23[1] = v24;
      *v24 = v23;
      off_1800610C0[0] = (_UNKNOWN **)v23;
      return 0;
    }
LABEL_36:
    __fastfail(3u);
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 18, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
  return 0;
}

```

## disassembly

```asm
0x180018cd4  mov     [rsp-28h+arg_10], rbx
0x180018cd9  push    rbp
0x180018cda  push    rsi
0x180018cdb  push    rdi
0x180018cdc  push    r14
0x180018cde  push    r15
0x180018ce0  mov     rbp, rsp
0x180018ce3  sub     rsp, 40h
0x180018ce7  call    DhcpIsWCOSSystem
0x180018cec  xor     r14d, r14d
0x180018cef  mov     [rsp+40h+var_8], 3; int
0x180018cf7  lea     rdx, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180018cfe  test    eax, eax
0x180018d00  lea     rcx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180018d07  cmovz   rcx, rdx; int
0x180018d0b  xor     r9d, r9d; int
0x180018d0e  mov     [rsp+40h+psz], rcx; psz
0x180018d13  lea     edx, [r14+6]; int
0x180018d17  mov     [rsp+40h+Src], r14; Src
0x180018d1c  xor     r8d, r8d; int
0x180018d1f  mov     [rsp+40h+var_20], r14d; int
0x180018d24  call    DhcpAddOptionDef
0x180018d29  lea     ebx, [r14+0Fh]
0x180018d2d  test    eax, eax
0x180018d2f  jz      short loc_180018D50
0x180018d31  test    byte ptr cs:xmmword_1800616A0, 2
0x180018d38  jz      short loc_180018D50
0x180018d3a  mov     edx, ebx
0x180018d3c  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x180018d43  mov     ecx, 401h
0x180018d48  mov     r9d, eax
0x180018d4b  call    WPP_SF_D
0x180018d50  call    DhcpIsWCOSSystem
0x180018d55  lea     r8, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180018d5c  mov     [rsp+40h+var_8], 1; int
0x180018d64  test    eax, eax
0x180018d66  lea     rcx, aSystemCurrentc_16; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180018d6d  mov     edx, ebx; int
0x180018d6f  cmovz   rcx, r8; int
0x180018d73  xor     r9d, r9d; int
0x180018d76  mov     [rsp+40h+psz], rcx; psz
0x180018d7b  xor     r8d, r8d; int
0x180018d7e  mov     [rsp+40h+Src], r14; Src
0x180018d83  mov     [rsp+40h+var_20], r14d; int
0x180018d88  call    DhcpAddOptionDef
0x180018d8d  test    eax, eax
0x180018d8f  jz      short loc_180018DB3
0x180018d91  test    byte ptr cs:xmmword_1800616A0, 2
0x180018d98  jz      short loc_180018DB3
0x180018d9a  mov     edx, 10h
0x180018d9f  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x180018da6  mov     ecx, 401h
0x180018dab  mov     r9d, eax
0x180018dae  call    WPP_SF_D
0x180018db3  mov     r15d, 200h
0x180018db9  mov     [rbp+arg_0], r14d
0x180018dbd  mov     edx, r15d
0x180018dc0  lea     r8, [rbp+arg_0]
0x180018dc4  lea     rcx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Ne"...
0x180018dcb  mov     esi, r14d
0x180018dce  lea     rdi, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Ne"...
0x180018dd5  call    WxStringCchLengthDWordW
0x180018dda  mov     ecx, eax
0x180018ddc  call    WX_WIN32_FROM_HR
0x180018de1  mov     ebx, [rbp+arg_0]
0x180018de4  jmp     short loc_180018E3F
0x180018de6  test    eax, eax
0x180018de8  js      short loc_180018E43
0x180018dea  mov     dword ptr [rbp+pcchLength+4], r14d
0x180018dee  lea     eax, [rbx+1]
0x180018df1  lea     esi, [rsi+rbx*2]
0x180018df4  mov     [rbp+38h], r14
0x180018df8  lea     rdi, [rdi+rax*2]
0x180018dfc  mov     [rbp+arg_0], r14d
0x180018e00  add     esi, 2
0x180018e03  test    rdi, rdi
0x180018e06  jnz     short loc_180018E19
0x180018e08  mov     eax, 80070057h
0x180018e0d  mov     dword ptr [rbp+pcchLength+4], 4Dh ; 'M'
0x180018e14  mov     ebx, [rbp+arg_0]
0x180018e17  jmp     short loc_180018E38
0x180018e19  lea     r8, [rbp+pcchLength]; pcchLength
0x180018e1d  mov     rdx, r15; cchMax
0x180018e20  mov     rcx, rdi; psz
0x180018e23  call    StringCchLengthW
0x180018e28  test    eax, eax
0x180018e2a  jns     short loc_180018E35
0x180018e2c  mov     dword ptr [rbp+pcchLength+4], 51h ; 'Q'
0x180018e33  jmp     short loc_180018E14
0x180018e35  mov     ebx, dword ptr [rbp+pcchLength]
0x180018e38  mov     ecx, eax
0x180018e3a  call    WX_WIN32_FROM_HR
0x180018e3f  test    ebx, ebx
0x180018e41  jnz     short loc_180018DE6
0x180018e43  add     esi, 2
0x180018e46  lea     ecx, [rsi+40h]
0x180018e49  call    DhcpAlloc
0x180018e4e  lea     r15, DhcpGlobalOptionDefList
0x180018e55  mov     rbx, rax
0x180018e58  test    rax, rax
0x180018e5b  jnz     short loc_180018E80
0x180018e5d  test    byte ptr cs:xmmword_1800616A0, 2
0x180018e64  jz      short loc_180018ED3
0x180018e66  lea     edx, [rax+11h]
0x180018e69  mov     ecx, 401h
0x180018e6e  lea     r9d, [rax+8]
0x180018e72  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x180018e79  call    WPP_SF_D
0x180018e7e  jmp     short loc_180018ED3
0x180018e80  lea     rcx, [rax+40h]; void *
0x180018e84  mov     r8d, esi; Size
0x180018e87  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Ne"...
0x180018e8e  mov     [rax+30h], rcx
0x180018e92  mov     qword ptr [rax+10h], 2Ch ; ','
0x180018e9a  mov     [rax+18h], r14
0x180018e9e  mov     [rax+20h], r14d
0x180018ea2  mov     dword ptr [rax+38h], 3
0x180018ea9  mov     [rax+28h], r14
0x180018ead  call    memcpy_0
0x180018eb2  mov     rax, cs:off_1800610C0
0x180018eb9  cmp     [rax], r15
0x180018ebc  jnz     loc_180018FAD
0x180018ec2  mov     [rbx], r15
0x180018ec5  mov     [rbx+8], rax
0x180018ec9  mov     [rax], rbx
0x180018ecc  mov     cs:off_1800610C0, rbx
0x180018ed3  lea     rsi, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x180018eda  mov     edi, r14d
0x180018edd  mov     rbx, rsi
0x180018ee0  mov     rcx, rsi
0x180018ee3  jmp     short loc_180018EF9
0x180018ee5  test    eax, eax
0x180018ee7  js      short loc_180018F19
0x180018ee9  lea     eax, [rdx+1]
0x180018eec  lea     rbx, [rbx+rax*2]
0x180018ef0  lea     edi, [rdi+rdx*2]
0x180018ef3  mov     rcx, rbx
0x180018ef6  add     edi, 2
0x180018ef9  lea     r8, [rbp+arg_0]
0x180018efd  mov     [rbp+arg_0], r14d
0x180018f01  mov     edx, 200h
0x180018f06  call    WxStringCchLengthDWordW
0x180018f0b  mov     ecx, eax
0x180018f0d  call    WX_WIN32_FROM_HR
0x180018f12  mov     edx, [rbp+arg_0]
0x180018f15  test    edx, edx
0x180018f17  jnz     short loc_180018EE5
0x180018f19  add     edi, 2
0x180018f1c  lea     ecx, [rdi+40h]
0x180018f1f  call    DhcpAlloc
0x180018f24  mov     rbx, rax
0x180018f27  test    rax, rax
0x180018f2a  jnz     short loc_180018F4F
0x180018f2c  test    byte ptr cs:xmmword_1800616A0, 2
0x180018f33  jz      short loc_180018F97
0x180018f35  lea     edx, [rax+12h]
0x180018f38  mov     ecx, 401h
0x180018f3d  lea     r9d, [rax+8]
0x180018f41  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x180018f48  call    WPP_SF_D
0x180018f4d  jmp     short loc_180018F97
0x180018f4f  lea     rcx, [rax+40h]; void *
0x180018f53  mov     r8d, edi; Size
0x180018f56  mov     rdx, rsi; Src
0x180018f59  mov     [rax+28h], rcx
0x180018f5d  mov     qword ptr [rax+10h], 37h ; '7'
0x180018f65  mov     [rax+18h], r14
0x180018f69  mov     [rax+20h], r14d
0x180018f6d  mov     [rax+38h], r14d
0x180018f71  call    memcpy_0
0x180018f76  mov     [rbx+30h], r14
0x180018f7a  mov     rax, cs:off_1800610C0
0x180018f81  cmp     [rax], r15
0x180018f84  jnz     short loc_180018FAD
0x180018f86  mov     [rbx], r15
0x180018f89  mov     [rbx+8], rax
0x180018f8d  mov     [rax], rbx
0x180018f90  mov     cs:off_1800610C0, rbx
0x180018f97  mov     rbx, [rsp+40h+arg_10]
0x180018f9f  xor     eax, eax
0x180018fa1  add     rsp, 40h
0x180018fa5  pop     r15
0x180018fa7  pop     r14
0x180018fa9  pop     rdi
0x180018faa  pop     rsi
0x180018fab  pop     rbp
0x180018fac  retn
0x180018fad  mov     ecx, 3
0x180018fb2  int     29h; Win8: RtlFailFast(ecx)
```
