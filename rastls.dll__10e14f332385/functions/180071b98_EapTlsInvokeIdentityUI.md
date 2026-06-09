# EapTlsInvokeIdentityUI

- ea: `0x180071b98`
- end: `0x180071eb6`
- name: `EapTlsInvokeIdentityUI`
- size: `798`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18001f2a0`
- `0x18004efe4`
- `0x1800508cc`
- `0x180050b0c`
- `0x1800564d0`

## callees

- `0x180005ac0`
- `0x1800075b0`
- `0x180007910`
- `0x180007c60`
- `0x1800136f0`
- `0x1800316cc`
- `0x180071b98`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071e9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071d59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071d59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071cd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071cd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180071d0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180071d0e`

## string_xrefs

- `0x180071cc8`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`
- `0x180071d07`: `UseSoftTokenWithMachineAuthentication`

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
0x180071b98  mov     [rsp-38h+arg_10], r8d
0x180071b9d  mov     [rsp-38h+cbData], edx
0x180071ba1  mov     [rsp-38h+Type], ecx
0x180071ba5  push    rbp
0x180071ba6  push    rbx
0x180071ba7  push    rsi
0x180071ba8  push    rdi
0x180071ba9  push    r13
0x180071bab  push    r14
0x180071bad  push    r15
0x180071baf  mov     rbp, rsp
0x180071bb2  sub     rsp, 80h
0x180071bb9  xor     edi, edi
0x180071bbb  mov     [rbp+hMem], 0
0x180071bc6  mov     r15d, r9d
0x180071bc9  mov     [rbp+var_8], 0
0x180071bd1  mov     qword ptr [rbp+var_10], rdi
0x180071bd5  mov     [rbp+hKey], rdi
0x180071bdc  lea     eax, [rdi+1]
0x180071bdf  mov     [rbp+Type], edi
0x180071be2  mov     edx, eax; int
0x180071be4  mov     [rbp+Data], edi
0x180071be7  mov     ecx, eax; int
0x180071be9  mov     [rbp+cbData], edi
0x180071bec  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180071bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180071bf8  lea     rax, WPP_GLOBAL_Control
0x180071bff  cmp     rcx, rax
0x180071c02  jz      short loc_180071C17
0x180071c04  mov     rcx, [rcx+10h]
0x180071c08  lea     edx, [rdi+66h]
0x180071c0b  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180071c12  call    WPP_SF_
0x180071c17  mov     r13, [rbp+arg_68]
0x180071c1e  mov     rax, [rbp+arg_70]
0x180071c25  mov     r14, [rbp+arg_78]
0x180071c2c  mov     [r13+0], rdi
0x180071c30  mov     [rax], edi
0x180071c32  test    r14, r14
0x180071c35  jz      short loc_180071C3A
0x180071c37  mov     [r14], rdi
0x180071c3a  mov     r8d, [rbp+arg_50]; unsigned int
0x180071c41  lea     r9, [rbp+var_8]; struct _EAPTLS_CONN_PROPERTIES **
0x180071c45  mov     rdx, [rbp+arg_48]; unsigned __int8 *
0x180071c4c  mov     ecx, r15d; unsigned int
0x180071c4f  call    ?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)
0x180071c54  mov     rsi, [rbp+var_8]
0x180071c58  mov     ebx, eax
0x180071c5a  test    eax, eax
0x180071c5c  jnz     loc_180071E67
0x180071c62  lea     rdx, [rbp+var_10]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x180071c66  mov     rcx, rsi; struct _EAPTLS_CONN_PROPERTIES *
0x180071c69  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x180071c6e  mov     ebx, eax
0x180071c70  test    eax, eax
0x180071c72  jnz     loc_180071E63
0x180071c78  mov     edx, [rbp+arg_60]; unsigned int
0x180071c7e  lea     r8, [rbp+hMem]; struct _EAPTLS_USER_PROPERTIES **
0x180071c85  mov     rcx, [rbp+Src]; Src
0x180071c8c  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x180071c91  mov     ebx, eax
0x180071c93  test    eax, eax
0x180071c95  jnz     loc_180071E63
0x180071c9b  mov     rdi, qword ptr [rbp+var_10]
0x180071c9f  test    r15b, 20h
0x180071ca3  jz      loc_180071D5F
0x180071ca9  test    byte ptr [rdi+8], 1
0x180071cad  jnz     loc_180071D5F
0x180071cb3  lea     rax, [rbp+hKey]
0x180071cba  mov     r9d, 20019h; samDesired
0x180071cc0  xor     r8d, r8d; ulOptions
0x180071cc3  mov     [rsp+80h+phkResult], rax; phkResult
0x180071cc8  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x180071ccf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071cd6  call    cs:__imp_RegOpenKeyExW
0x180071cdc  test    eax, eax
0x180071cde  jnz     short loc_180071D5F
0x180071ce0  mov     rcx, [rbp+hKey]; hKey
0x180071ce7  lea     rax, [rbp+cbData]
0x180071ceb  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180071cf0  lea     r9, [rbp+Type]; lpType
0x180071cf4  lea     rax, [rbp+Data]
0x180071cf8  mov     [rbp+cbData], 4
0x180071cff  xor     r8d, r8d; lpReserved
0x180071d02  mov     [rsp+80h+phkResult], rax; lpData
0x180071d07  lea     rdx, aUsesofttokenwi; "UseSoftTokenWithMachineAuthentication"
0x180071d0e  call    cs:__imp_RegQueryValueExW
0x180071d14  test    eax, eax
0x180071d16  jnz     short loc_180071D52
0x180071d18  cmp     [rbp+Type], 4
0x180071d1c  jnz     short loc_180071D52
0x180071d1e  cmp     [rbp+Data], 1
0x180071d22  jnz     short loc_180071D52
0x180071d24  or      dword ptr [rdi+8], 11h
0x180071d28  or      dword ptr [rsi+8], 11h
0x180071d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180071d33  lea     rax, WPP_GLOBAL_Control
0x180071d3a  cmp     rcx, rax
0x180071d3d  jz      short loc_180071D52
0x180071d3f  mov     rcx, [rcx+10h]
0x180071d43  lea     edx, [rbx+67h]
0x180071d46  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180071d4d  call    WPP_SF_
0x180071d52  mov     rcx, [rbp+hKey]; hKey
0x180071d59  call    cs:__imp_RegCloseKey
0x180071d5f  test    r15b, 4
0x180071d63  jz      short loc_180071D7F
0x180071d65  cmp     [rbp+Src], 0
0x180071d6d  jz      short loc_180071D7F
0x180071d6f  test    byte ptr [rsi+8], 1
0x180071d73  jz      short loc_180071D7F
0x180071d75  mov     ebx, 311h
0x180071d7a  jmp     loc_180071E67
0x180071d7f  mov     r8d, [rbp+arg_10]; int
0x180071d83  lea     rax, [rbp+hMem]
0x180071d8a  mov     [rsp+80h+var_18], 0; struct _CERT_CONTEXT ***
0x180071d93  mov     r9d, r15d; unsigned int
0x180071d96  mov     [rsp+80h+var_20], 0; unsigned int *
0x180071d9f  xor     edx, edx; int
0x180071da1  mov     [rsp+80h+var_28], r14; unsigned __int16 **
0x180071da6  xor     ecx, ecx; int
0x180071da8  mov     [rsp+80h+var_30], rax; struct _EAPTLS_USER_PROPERTIES **
0x180071dad  mov     eax, [rbp+arg_40]
0x180071db3  mov     [rsp+80h+var_38], eax; unsigned int
0x180071db7  lea     rax, aMy_1; "MY"
0x180071dbe  mov     qword ptr [rsp+80h+pcbData], rdi; pcbData
0x180071dc3  mov     [rsp+80h+var_48], rax; unsigned __int16 *
0x180071dc8  mov     rax, [rbp+arg_38]
0x180071dcc  mov     [rsp+80h+hWndParent], rax; hWndParent
0x180071dd1  mov     rax, [rbp+arg_30]
0x180071dd5  mov     [rsp+80h+lpcbData], rax; unsigned __int16 *
0x180071dda  mov     rax, [rbp+arg_28]
0x180071dde  mov     [rsp+80h+phkResult], rax; unsigned __int16 *
0x180071de3  call    ?GetCertInfo@@YAKHHHKPEBG0PEAUHWND__@@0PEAU_EAPTLS_CONN_PROPERTIES_V1@@KPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAPEAGPEAKPEAPEAPEBU_CERT_CONTEXT@@@Z; GetCertInfo(int,int,int,ulong,ushort const *,ushort const *,HWND__ *,ushort const *,_EAPTLS_CONN_PROPERTIES_V1 *,ulong,_EAPTLS_USER_PROPERTIES * *,ushort * *,ulong *,_CERT_CONTEXT const * * *)
0x180071de8  mov     ebx, eax
0x180071dea  test    eax, eax
0x180071dec  jz      short loc_180071E03
0x180071dee  cmp     eax, 80100002h
0x180071df3  jz      short loc_180071DFC
0x180071df5  cmp     eax, 8010006Eh
0x180071dfa  jnz     short loc_180071E67
0x180071dfc  mov     ebx, 322h
0x180071e01  jmp     short loc_180071E67
0x180071e03  mov     rdx, [rbp+hMem]
0x180071e0a  mov     r8d, 0FFFFFFFFh
0x180071e10  mov     rax, [rdx+28h]
0x180071e14  movzx   ecx, word ptr [rax]
0x180071e17  neg     cx
0x180071e1a  sbb     rax, rax
0x180071e1d  and     rax, r8
0x180071e20  mov     [rdx+28h], rax
0x180071e24  mov     rdx, [rbp+hMem]
0x180071e2b  mov     rax, [rdx+38h]
0x180071e2f  movzx   ecx, word ptr [rax]
0x180071e32  neg     cx
0x180071e35  mov     rcx, [rbp+arg_70]
0x180071e3c  sbb     rax, rax
0x180071e3f  and     rax, r8
0x180071e42  mov     [rdx+38h], rax
0x180071e46  mov     rax, [rbp+hMem]
0x180071e4d  mov     [r13+0], rax
0x180071e51  mov     eax, [rax+8]
0x180071e54  mov     [rcx], eax
0x180071e56  mov     [rbp+hMem], 0
0x180071e61  jmp     short loc_180071E67
0x180071e63  mov     rdi, qword ptr [rbp+var_10]
0x180071e67  mov     edx, 1; int
0x180071e6c  xor     ecx, ecx; int
0x180071e6e  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180071e73  xor     ecx, ecx; hMem
0x180071e75  call    cs:__imp_LocalFree
0x180071e7b  mov     rcx, [rbp+hMem]; hMem
0x180071e82  call    cs:__imp_LocalFree
0x180071e88  mov     rcx, rsi; hMem
0x180071e8b  call    cs:__imp_LocalFree
0x180071e91  mov     rcx, rdi; hMem
0x180071e94  call    cs:__imp_LocalFree
0x180071e9a  xor     ecx, ecx; hMem
0x180071e9c  call    cs:__imp_LocalFree
0x180071ea2  mov     eax, ebx
0x180071ea4  add     rsp, 80h
0x180071eab  pop     r15
0x180071ead  pop     r14
0x180071eaf  pop     r13
0x180071eb1  pop     rdi
0x180071eb2  pop     rsi
0x180071eb3  pop     rbx
0x180071eb4  pop     rbp
0x180071eb5  retn
```
