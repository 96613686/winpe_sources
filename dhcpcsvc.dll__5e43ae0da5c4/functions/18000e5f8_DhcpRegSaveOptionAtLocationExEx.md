# DhcpRegSaveOptionAtLocationExEx

- ea: `0x18000e5f8`
- end: `0x18000e77e`
- name: `DhcpRegSaveOptionAtLocationExEx`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800088d0`

## callees

- `0x180002160`
- `0x180003210`
- `0x18000d4a4`
- `0x18000e1e0`
- `0x18000e5f8`
- `0x18000f528`
- `0x180012500`
- `0x180012850`
- `0x180012a00`

## string_xrefs

- `0x18000e619`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpRequestOptions`

## pseudocode

```c
__int64 __fastcall DhcpRegSaveOptionAtLocationExEx(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  unsigned int v4; // edi
  wchar_t *v5; // rsi
  HRESULT v7; // eax
  int v8; // ebp
  unsigned int v9; // eax
  unsigned int v10; // ebx
  LSTATUS v11; // eax
  const wchar_t *v12; // r14
  LSTATUS v13; // ebx
  LSTATUS v14; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  size_t pcchLength; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v20; // [rsp+80h] [rbp+18h] BYREF
  int v21; // [rsp+88h] [rbp+20h]

  v21 = a4;
  v4 = 0;
  v5 = (wchar_t *)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpRequestOptions";
  v20 = 0;
  while ( 1 )
  {
    pcchLength = 0;
    v21 = 0;
    if ( !v5 )
    {
      v7 = -2147024809;
      HIDWORD(pcchLength) = 77;
LABEL_4:
      v8 = v21;
      goto LABEL_8;
    }
    v7 = StringCchLengthW(v5, 0x7FFFFFFFu, &pcchLength);
    if ( v7 < 0 )
    {
      HIDWORD(pcchLength) = 81;
      goto LABEL_4;
    }
    v8 = pcchLength;
LABEL_8:
    v9 = WX_WIN32_FROM_HR((unsigned int)v7);
    v10 = v9;
    if ( v9 )
      break;
    if ( !v8 )
      return v4;
    v11 = DhcpRegExpandString(v5);
    v12 = v20;
    v13 = v11;
    if ( v11 )
    {
      if ( (xmmword_18001E1E0 & 2) != 0 )
        WPP_SF_SD(1025, 20, (unsigned int)WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, (_DWORD)v5, v11);
LABEL_18:
      v4 = v13;
      goto LABEL_19;
    }
    if ( *(_DWORD *)(a1 + 16) != 46 || *(_DWORD *)(a1 + 56) )
    {
      v14 = DhcpRegSaveOptionAtLocation(a1, v20);
      v13 = v14;
      if ( v14 )
      {
        if ( (xmmword_18001E1E0 & 2) != 0 )
          WPP_SF_lSD(v16, v15, v17, *(_DWORD *)(a1 + 16), (__int64)v12, v14);
        goto LABEL_18;
      }
    }
LABEL_19:
    if ( v12 )
      DhcpFree(&v20);
    v5 += (unsigned int)(v8 + 1);
  }
  if ( (xmmword_18001E1E0 & 2) != 0 )
    WPP_SF_d(1025, 19, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, v9);
  return v10;
}

```

## disassembly

```asm
0x18000e5f8  mov     rax, rsp
0x18000e5fb  mov     [rax+8], rbx
0x18000e5ff  mov     [rax+10h], rbp
0x18000e603  mov     [rax+20h], r9d
0x18000e607  mov     [rax+18h], r8
0x18000e60b  push    rsi
0x18000e60c  push    rdi
0x18000e60d  push    r12
0x18000e60f  push    r14
0x18000e611  push    r15
0x18000e613  sub     rsp, 40h
0x18000e617  xor     edi, edi
0x18000e619  lea     rsi, Src; "System\\CurrentControlSet\\Services\\Tc"...
0x18000e620  mov     [rax+18h], rdi
0x18000e624  mov     r12, rdx
0x18000e627  mov     r15, rcx
0x18000e62a  mov     dword ptr [rsp+68h+pcchLength+4], 0
0x18000e632  mov     qword ptr [rsp+30h], 0
0x18000e63b  mov     [rsp+68h+arg_18], 0
0x18000e646  test    rsi, rsi
0x18000e649  jnz     short loc_18000E661
0x18000e64b  mov     eax, 80070057h
0x18000e650  mov     dword ptr [rsp+68h+pcchLength+4], 4Dh ; 'M'
0x18000e658  mov     ebp, [rsp+68h+arg_18]
0x18000e65f  jmp     short loc_18000E685
0x18000e661  lea     r8, [rsp+68h+pcchLength]; pcchLength
0x18000e666  mov     edx, 7FFFFFFFh; cchMax
0x18000e66b  mov     rcx, rsi; psz
0x18000e66e  call    StringCchLengthW
0x18000e673  test    eax, eax
0x18000e675  jns     short loc_18000E681
0x18000e677  mov     dword ptr [rsp+68h+pcchLength+4], 51h ; 'Q'
0x18000e67f  jmp     short loc_18000E658
0x18000e681  mov     ebp, dword ptr [rsp+68h+pcchLength]
0x18000e685  mov     ecx, eax
0x18000e687  call    WX_WIN32_FROM_HR
0x18000e68c  mov     ebx, eax
0x18000e68e  test    eax, eax
0x18000e690  jnz     loc_18000E741
0x18000e696  test    ebp, ebp
0x18000e698  jz      loc_18000E765
0x18000e69e  lea     r8, [rsp+68h+arg_10]
0x18000e6a6  mov     rdx, r12
0x18000e6a9  mov     rcx, rsi; Src
0x18000e6ac  call    DhcpRegExpandString
0x18000e6b1  mov     r14, [rsp+68h+arg_10]
0x18000e6b9  mov     ebx, eax
0x18000e6bb  test    eax, eax
0x18000e6bd  jz      short loc_18000E6E7
0x18000e6bf  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000e6c6  jz      short loc_18000E721
0x18000e6c8  mov     edx, 14h
0x18000e6cd  mov     dword ptr [rsp+68h+var_48], eax
0x18000e6d1  mov     ecx, 401h
0x18000e6d6  lea     r8, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x18000e6dd  mov     r9, rsi
0x18000e6e0  call    WPP_SF_SD
0x18000e6e5  jmp     short loc_18000E721
0x18000e6e7  cmp     dword ptr [r15+10h], 2Eh ; '.'
0x18000e6ec  jnz     short loc_18000E6F5
0x18000e6ee  cmp     dword ptr [r15+38h], 0
0x18000e6f3  jz      short loc_18000E723
0x18000e6f5  mov     rdx, r14
0x18000e6f8  mov     rcx, r15
0x18000e6fb  call    DhcpRegSaveOptionAtLocation
0x18000e700  mov     ebx, eax
0x18000e702  test    eax, eax
0x18000e704  jz      short loc_18000E723
0x18000e706  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000e70d  jz      short loc_18000E721
0x18000e70f  mov     r9d, [r15+10h]
0x18000e713  mov     [rsp+68h+var_40], eax
0x18000e717  mov     [rsp+68h+var_48], r14
0x18000e71c  call    WPP_SF_lSD
0x18000e721  mov     edi, ebx
0x18000e723  test    r14, r14
0x18000e726  jz      short loc_18000E735
0x18000e728  lea     rcx, [rsp+68h+arg_10]
0x18000e730  call    DhcpFree
0x18000e735  lea     eax, [rbp+1]
0x18000e738  lea     rsi, [rsi+rax*2]
0x18000e73c  jmp     loc_18000E62A
0x18000e741  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000e748  jz      short loc_18000E763
0x18000e74a  mov     edx, 13h
0x18000e74f  lea     r8, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x18000e756  mov     ecx, 401h
0x18000e75b  mov     r9d, ebx
0x18000e75e  call    WPP_SF_d
0x18000e763  mov     edi, ebx
0x18000e765  mov     rbx, [rsp+68h+arg_0]
0x18000e76a  mov     eax, edi
0x18000e76c  mov     rbp, [rsp+68h+arg_8]
0x18000e771  add     rsp, 40h
0x18000e775  pop     r15
0x18000e777  pop     r14
0x18000e779  pop     r12
0x18000e77b  pop     rdi
0x18000e77c  pop     rsi
0x18000e77d  retn
```
