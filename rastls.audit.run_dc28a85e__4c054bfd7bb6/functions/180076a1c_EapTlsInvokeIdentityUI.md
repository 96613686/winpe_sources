# EapTlsInvokeIdentityUI

- ea: `0x180076a1c`
- end: `0x180076d6f`
- name: `EapTlsInvokeIdentityUI`
- size: `851`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180020fe0`
- `0x180051c1c`
- `0x18005363c`
- `0x18005388c`
- `0x180059600`

## callees

- `0x180005f80`
- `0x180007d00`
- `0x1800080a0`
- `0x180008420`
- `0x180014a70`
- `0x180033f40`
- `0x180076a1c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076d4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076bed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076bed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076b5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076b5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076b9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076b9c`

## string_xrefs

- `0x180076b4c`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`
- `0x180076b95`: `UseSoftTokenWithMachineAuthentication`

## pseudocode

```c
__int64 __fastcall EapTlsInvokeIdentityUI(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        int Data,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        HWND hWndParent,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11,
        unsigned __int8 *Src,
        unsigned int a13,
        HLOCAL *a14,
        _DWORD *a15,
        unsigned __int16 **a16,
        HLOCAL hMem,
        HKEY hKey)
{
  _DWORD *pcbData; // rdi
  HLOCAL *v20; // r13
  _DWORD *v21; // rax
  unsigned __int16 **v22; // r14
  unsigned int ConnectionData; // eax
  _DWORD *v24; // rsi
  unsigned int V1Struct; // ebx
  unsigned int CertInfo; // eax
  _DWORD *v27; // rcx
  _DWORD *v28; // rax
  DWORD v30[2]; // [rsp+70h] [rbp-10h] BYREF
  HLOCAL v31; // [rsp+78h] [rbp-8h] BYREF
  DWORD Type; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+C8h] [rbp+48h] BYREF
  int v34; // [rsp+D0h] [rbp+50h]

  v34 = a3;
  pcbData = 0;
  hMem = 0;
  v31 = 0;
  *(_QWORD *)v30 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  EapTlsInitialize2(1, 1);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_c4e812f99669349517681909258710e2_Traceguids);
  v20 = a14;
  v21 = a15;
  v22 = a16;
  *a14 = 0;
  *v21 = 0;
  if ( v22 )
    *v22 = 0;
  ConnectionData = EapTlsReadConnectionData(a4, a10, a11, (struct _EAPTLS_CONN_PROPERTIES **)&v31);
  v24 = v31;
  V1Struct = ConnectionData;
  if ( !ConnectionData )
  {
    V1Struct = ConnPropGetV1Struct((struct _EAPTLS_CONN_PROPERTIES *)v31, (struct _EAPTLS_CONN_PROPERTIES_V1 **)v30);
    if ( V1Struct || (V1Struct = EapTlsReadUserData(Src, a13, (struct _EAPTLS_USER_PROPERTIES **)&hMem)) != 0 )
    {
      pcbData = *(_DWORD **)v30;
    }
    else
    {
      pcbData = *(_DWORD **)v30;
      if ( (a4 & 0x20) != 0
        && (*(_BYTE *)(*(_QWORD *)v30 + 8LL) & 1) == 0
        && !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\13",
              0,
              0x20019u,
              &hKey) )
      {
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"UseSoftTokenWithMachineAuthentication", 0, &Type, (LPBYTE)&Data, &cbData)
          && Type == 4
          && Data == 1 )
        {
          pcbData[2] |= 0x11u;
          v24[2] |= 0x11u;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_c4e812f99669349517681909258710e2_Traceguids);
        }
        RegCloseKey(hKey);
      }
      if ( (a4 & 4) != 0 && Src && (v24[2] & 1) != 0 )
      {
        V1Struct = 785;
      }
      else
      {
        CertInfo = GetCertInfo(
                     0,
                     0,
                     v34,
                     a4,
                     a6,
                     a7,
                     hWndParent,
                     L"MY",
                     (DWORD)pcbData,
                     a9,
                     (struct _EAPTLS_USER_PROPERTIES **)&hMem,
                     v22,
                     0,
                     0);
        V1Struct = CertInfo;
        if ( CertInfo )
        {
          if ( CertInfo == -2146435070 || CertInfo == -2146434962 )
            V1Struct = 802;
        }
        else
        {
          *((_QWORD *)hMem + 5) = (unsigned int)-(**((_WORD **)hMem + 5) != 0);
          v27 = a15;
          *((_QWORD *)hMem + 7) = (unsigned int)-(**((_WORD **)hMem + 7) != 0);
          v28 = hMem;
          *v20 = hMem;
          *v27 = v28[2];
          hMem = 0;
        }
      }
    }
  }
  EapTlsInitialize2(0, 1);
  LocalFree(0);
  LocalFree(hMem);
  LocalFree(v24);
  LocalFree(pcbData);
  LocalFree(0);
  return V1Struct;
}

```

## disassembly

```asm
0x180076a1c  mov     [rsp-38h+arg_10], r8d
0x180076a21  mov     [rsp-38h+cbData], edx
0x180076a25  mov     [rsp-38h+Type], ecx
0x180076a29  push    rbp
0x180076a2a  push    rbx
0x180076a2b  push    rsi
0x180076a2c  push    rdi
0x180076a2d  push    r13
0x180076a2f  push    r14
0x180076a31  push    r15
0x180076a33  mov     rbp, rsp
0x180076a36  sub     rsp, 80h
0x180076a3d  xor     edi, edi
0x180076a3f  mov     [rbp+hMem], 0
0x180076a4a  mov     r15d, r9d
0x180076a4d  mov     [rbp+var_8], 0
0x180076a55  mov     qword ptr [rbp+var_10], rdi
0x180076a59  mov     [rbp+hKey], rdi
0x180076a60  lea     eax, [rdi+1]
0x180076a63  mov     [rbp+Type], edi
0x180076a66  mov     edx, eax; int
0x180076a68  mov     [rbp+Data], edi
0x180076a6b  mov     ecx, eax; int
0x180076a6d  mov     [rbp+cbData], edi
0x180076a70  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180076a75  mov     rcx, cs:WPP_GLOBAL_Control
0x180076a7c  lea     rax, WPP_GLOBAL_Control
0x180076a83  cmp     rcx, rax
0x180076a86  jz      short loc_180076A9B
0x180076a88  mov     rcx, [rcx+10h]
0x180076a8c  lea     edx, [rdi+66h]
0x180076a8f  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180076a96  call    WPP_SF_
0x180076a9b  mov     r13, [rbp+arg_68]
0x180076aa2  mov     rax, [rbp+arg_70]
0x180076aa9  mov     r14, [rbp+arg_78]
0x180076ab0  mov     [r13+0], rdi
0x180076ab4  mov     [rax], edi
0x180076ab6  test    r14, r14
0x180076ab9  jz      short loc_180076ABE
0x180076abb  mov     [r14], rdi
0x180076abe  mov     r8d, [rbp+arg_50]; unsigned int
0x180076ac5  lea     r9, [rbp+var_8]; struct _EAPTLS_CONN_PROPERTIES **
0x180076ac9  mov     rdx, [rbp+arg_48]; unsigned __int8 *
0x180076ad0  mov     ecx, r15d; unsigned int
0x180076ad3  call    ?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)
0x180076ad8  mov     rsi, [rbp+var_8]
0x180076adc  mov     ebx, eax
0x180076ade  test    eax, eax
0x180076ae0  jnz     loc_180076D01
0x180076ae6  lea     rdx, [rbp+var_10]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x180076aea  mov     rcx, rsi; struct _EAPTLS_CONN_PROPERTIES *
0x180076aed  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x180076af2  mov     ebx, eax
0x180076af4  test    eax, eax
0x180076af6  jnz     loc_180076CFD
0x180076afc  mov     edx, [rbp+arg_60]; unsigned int
0x180076b02  lea     r8, [rbp+hMem]; struct _EAPTLS_USER_PROPERTIES **
0x180076b09  mov     rcx, [rbp+Src]; Src
0x180076b10  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x180076b15  mov     ebx, eax
0x180076b17  test    eax, eax
0x180076b19  jnz     loc_180076CFD
0x180076b1f  mov     rdi, qword ptr [rbp+var_10]
0x180076b23  test    r15b, 20h
0x180076b27  jz      loc_180076BF9
0x180076b2d  test    byte ptr [rdi+8], 1
0x180076b31  jnz     loc_180076BF9
0x180076b37  lea     rax, [rbp+hKey]
0x180076b3e  mov     r9d, 20019h; samDesired
0x180076b44  xor     r8d, r8d; ulOptions
0x180076b47  mov     [rsp+80h+phkResult], rax; phkResult
0x180076b4c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x180076b53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076b5a  call    cs:__imp_RegOpenKeyExW
0x180076b61  nop     dword ptr [rax+rax+00h]
0x180076b66  test    eax, eax
0x180076b68  jnz     loc_180076BF9
0x180076b6e  mov     rcx, [rbp+hKey]; hKey
0x180076b75  lea     rax, [rbp+cbData]
0x180076b79  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180076b7e  lea     r9, [rbp+Type]; lpType
0x180076b82  lea     rax, [rbp+Data]
0x180076b86  mov     [rbp+cbData], 4
0x180076b8d  xor     r8d, r8d; lpReserved
0x180076b90  mov     [rsp+80h+phkResult], rax; lpData
0x180076b95  lea     rdx, aUsesofttokenwi; "UseSoftTokenWithMachineAuthentication"
0x180076b9c  call    cs:__imp_RegQueryValueExW
0x180076ba3  nop     dword ptr [rax+rax+00h]
0x180076ba8  test    eax, eax
0x180076baa  jnz     short loc_180076BE6
0x180076bac  cmp     [rbp+Type], 4
0x180076bb0  jnz     short loc_180076BE6
0x180076bb2  cmp     [rbp+Data], 1
0x180076bb6  jnz     short loc_180076BE6
0x180076bb8  or      dword ptr [rdi+8], 11h
0x180076bbc  or      dword ptr [rsi+8], 11h
0x180076bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180076bc7  lea     rax, WPP_GLOBAL_Control
0x180076bce  cmp     rcx, rax
0x180076bd1  jz      short loc_180076BE6
0x180076bd3  mov     rcx, [rcx+10h]
0x180076bd7  lea     edx, [rbx+67h]
0x180076bda  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180076be1  call    WPP_SF_
0x180076be6  mov     rcx, [rbp+hKey]; hKey
0x180076bed  call    cs:__imp_RegCloseKey
0x180076bf4  nop     dword ptr [rax+rax+00h]
0x180076bf9  test    r15b, 4
0x180076bfd  jz      short loc_180076C19
0x180076bff  cmp     [rbp+Src], 0
0x180076c07  jz      short loc_180076C19
0x180076c09  test    byte ptr [rsi+8], 1
0x180076c0d  jz      short loc_180076C19
0x180076c0f  mov     ebx, 311h
0x180076c14  jmp     loc_180076D01
0x180076c19  mov     r8d, [rbp+arg_10]; int
0x180076c1d  lea     rax, [rbp+hMem]
0x180076c24  mov     [rsp+80h+var_18], 0; struct _CERT_CONTEXT ***
0x180076c2d  mov     r9d, r15d; unsigned int
0x180076c30  mov     [rsp+80h+var_20], 0; unsigned int *
0x180076c39  xor     edx, edx; int
0x180076c3b  mov     [rsp+80h+var_28], r14; unsigned __int16 **
0x180076c40  xor     ecx, ecx; int
0x180076c42  mov     [rsp+80h+var_30], rax; struct _EAPTLS_USER_PROPERTIES **
0x180076c47  mov     eax, [rbp+arg_40]
0x180076c4d  mov     [rsp+80h+var_38], eax; unsigned int
0x180076c51  lea     rax, aMy_1; "MY"
0x180076c58  mov     qword ptr [rsp+80h+pcbData], rdi; pcbData
0x180076c5d  mov     [rsp+80h+var_48], rax; unsigned __int16 *
0x180076c62  mov     rax, [rbp+arg_38]
0x180076c66  mov     [rsp+80h+hWndParent], rax; hWndParent
0x180076c6b  mov     rax, [rbp+arg_30]
0x180076c6f  mov     [rsp+80h+lpcbData], rax; unsigned __int16 *
0x180076c74  mov     rax, [rbp+arg_28]
0x180076c78  mov     [rsp+80h+phkResult], rax; unsigned __int16 *
0x180076c7d  call    ?GetCertInfo@@YAKHHHKPEBG0PEAUHWND__@@0PEAU_EAPTLS_CONN_PROPERTIES_V1@@KPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAPEAGPEAKPEAPEAPEBU_CERT_CONTEXT@@@Z; GetCertInfo(int,int,int,ulong,ushort const *,ushort const *,HWND__ *,ushort const *,_EAPTLS_CONN_PROPERTIES_V1 *,ulong,_EAPTLS_USER_PROPERTIES * *,ushort * *,ulong *,_CERT_CONTEXT const * * *)
0x180076c82  mov     ebx, eax
0x180076c84  test    eax, eax
0x180076c86  jz      short loc_180076C9D
0x180076c88  cmp     eax, 80100002h
0x180076c8d  jz      short loc_180076C96
0x180076c8f  cmp     eax, 8010006Eh
0x180076c94  jnz     short loc_180076D01
0x180076c96  mov     ebx, 322h
0x180076c9b  jmp     short loc_180076D01
0x180076c9d  mov     rdx, [rbp+hMem]
0x180076ca4  mov     r8d, 0FFFFFFFFh
0x180076caa  mov     rax, [rdx+28h]
0x180076cae  movzx   ecx, word ptr [rax]
0x180076cb1  neg     cx
0x180076cb4  sbb     rax, rax
0x180076cb7  and     rax, r8
0x180076cba  mov     [rdx+28h], rax
0x180076cbe  mov     rdx, [rbp+hMem]
0x180076cc5  mov     rax, [rdx+38h]
0x180076cc9  movzx   ecx, word ptr [rax]
0x180076ccc  neg     cx
0x180076ccf  mov     rcx, [rbp+arg_70]
0x180076cd6  sbb     rax, rax
0x180076cd9  and     rax, r8
0x180076cdc  mov     [rdx+38h], rax
0x180076ce0  mov     rax, [rbp+hMem]
0x180076ce7  mov     [r13+0], rax
0x180076ceb  mov     eax, [rax+8]
0x180076cee  mov     [rcx], eax
0x180076cf0  mov     [rbp+hMem], 0
0x180076cfb  jmp     short loc_180076D01
0x180076cfd  mov     rdi, qword ptr [rbp+var_10]
0x180076d01  mov     edx, 1; int
0x180076d06  xor     ecx, ecx; int
0x180076d08  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180076d0d  xor     ecx, ecx; hMem
0x180076d0f  call    cs:__imp_LocalFree
0x180076d16  nop     dword ptr [rax+rax+00h]
0x180076d1b  mov     rcx, [rbp+hMem]; hMem
0x180076d22  call    cs:__imp_LocalFree
0x180076d29  nop     dword ptr [rax+rax+00h]
0x180076d2e  mov     rcx, rsi; hMem
0x180076d31  call    cs:__imp_LocalFree
0x180076d38  nop     dword ptr [rax+rax+00h]
0x180076d3d  mov     rcx, rdi; hMem
0x180076d40  call    cs:__imp_LocalFree
0x180076d47  nop     dword ptr [rax+rax+00h]
0x180076d4c  xor     ecx, ecx; hMem
0x180076d4e  call    cs:__imp_LocalFree
0x180076d55  nop     dword ptr [rax+rax+00h]
0x180076d5a  mov     eax, ebx
0x180076d5c  add     rsp, 80h
0x180076d63  pop     r15
0x180076d65  pop     r14
0x180076d67  pop     r13
0x180076d69  pop     rdi
0x180076d6a  pop     rsi
0x180076d6b  pop     rbx
0x180076d6c  pop     rbp
0x180076d6d  retn
```
