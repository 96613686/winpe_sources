# EapTlsCreateConnectionPropertiesXml(ulong,ulong,uchar *,ulong,IXMLDOMDocument2 * *)

- ea: `0x180007d30`
- end: `0x180008093`
- name: `?EapTlsCreateConnectionPropertiesXml@@YAKKKPEAEKPEAPEAUIXMLDOMDocument2@@@Z`
- size: `867`
- prototype: `unsigned int(unsigned int, unsigned int, unsigned __int8 *, unsigned int, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005be0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180007d30`
- `0x180008240`
- `0x180008420`
- `0x1800086a0`
- `0x180038e4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007fbf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007fbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007dec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ea6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008042`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000807e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007dec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ea6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008042`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000807e`

## pseudocode

```c
__int64 __fastcall EapTlsCreateConnectionPropertiesXml(
        unsigned int a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        LPVOID *ppv)
{
  struct _EAPTLS_CONN_PROPERTIES *v6; // rsi
  size_t v9; // rdi
  unsigned int v10; // r14d
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  DWORD LastError; // eax
  unsigned int v14; // edi
  struct _EAPTLS_CONTROL_BLOCK *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  int v19; // eax
  int v20; // eax
  _DWORD *v21; // rax
  unsigned int V1Struct; // eax
  struct _EAPTLS_CONTROL_BLOCK *v23; // rcx
  __int64 v24; // rdx
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF

  v6 = 0;
  v9 = a4;
  hMem = 0;
  if ( a4 >= 0x28 && a3 )
  {
    v10 = a4 + 8;
    v11 = LocalAlloc(0x40u, a4 + 8);
    v12 = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      v14 = LastError;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_22;
      v16 = 126;
      goto LABEL_21;
    }
    memcpy_0(v11, a3, v9);
    if ( !(unsigned int)IsEaptlsConnDataValid((struct _EAPTLS_CONN_PROPERTIES *)v12, v9) )
    {
      v14 = 13;
      LocalFree(v12);
      goto LABEL_23;
    }
    v12[1] = v10;
    if ( !*v12 && v12[3] )
    {
      v17 = -1;
      while ( *((_WORD *)v12 + v17++ + 19) != 0 )
        ;
      *(_DWORD *)((char *)v12 + 2 * v17 + 38) = 1;
    }
    if ( *v12 != 2 )
    {
      v19 = v12[2];
      *v12 = 2;
      if ( (v19 & 1) != 0 )
        v12[2] = v19 | 0x10;
    }
    v20 = v12[2];
    if ( (v20 & 0x20) != 0 )
      v12[2] = v20 & 0xFFFFFDFF;
LABEL_29:
    v6 = (struct _EAPTLS_CONN_PROPERTIES *)v12;
    LocalFree(0);
LABEL_30:
    if ( (*(_DWORD *)v6 & 0xFFFFFFFD) != 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a1);
      v14 = 160;
      goto LABEL_48;
    }
    V1Struct = ConnPropGetV1Struct(v6, (struct _EAPTLS_CONN_PROPERTIES_V1 **)&hMem);
    v14 = V1Struct;
    if ( V1Struct )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v24 = 125;
LABEL_47:
        WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, V1Struct);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      V1Struct = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument3, ppv);
      v14 = V1Struct;
      if ( !V1Struct )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
        V1Struct = PopulateXMLDomFromTLSBlob(
                     a2,
                     (struct _EAPTLS_CONN_PROPERTIES_V1 *)hMem,
                     (struct IXMLDOMDocument2 **)ppv);
        v14 = V1Struct;
        if ( !V1Struct )
          goto LABEL_48;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_48;
        v24 = 129;
        goto LABEL_47;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v24 = 127;
        goto LABEL_47;
      }
    }
LABEL_48:
    LocalFree(v6);
    goto LABEL_49;
  }
  v21 = LocalAlloc(0x40u, 0x30u);
  v12 = v21;
  if ( v21 )
  {
    *v21 = 2;
    v21[1] = 48;
    if ( (a2 & 0x80u) != 0 )
      v21[2] |= 0x15u;
    if ( (a2 & 1) != 0 )
    {
      v21[2] |= 1u;
      v21[2] |= 4u;
    }
    goto LABEL_29;
  }
  LastError = GetLastError();
  v14 = LastError;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    goto LABEL_22;
  v16 = 125;
LABEL_21:
  WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, LastError);
LABEL_22:
  LocalFree(0);
  if ( !v14 )
    goto LABEL_30;
LABEL_23:
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v14);
LABEL_49:
  if ( hMem )
    LocalFree(hMem);
  return v14;
}

```

## disassembly

```asm
0x180007d30  mov     rax, rsp
0x180007d33  push    rdi
0x180007d34  sub     rsp, 60h
0x180007d38  mov     [rax+8], rbx
0x180007d3c  mov     [rax+10h], rbp
0x180007d40  mov     rbp, r8
0x180007d43  mov     [rax+18h], rsi
0x180007d47  xor     esi, esi
0x180007d49  mov     [rax-10h], r12
0x180007d4d  mov     r12d, ecx
0x180007d50  mov     [rax-18h], r13
0x180007d54  lea     r13, WPP_GLOBAL_Control
0x180007d5b  mov     [rax-20h], r14
0x180007d5f  mov     [rax-28h], r15
0x180007d63  mov     r15d, edx
0x180007d66  mov     edi, r9d
0x180007d69  mov     [rax-38h], rsi
0x180007d6d  cmp     r9d, 28h ; '('
0x180007d71  jb      loc_180007E53
0x180007d77  test    r8, r8
0x180007d7a  jz      loc_180007E53
0x180007d80  lea     r14d, [rdi+8]
0x180007d84  mov     ecx, 40h ; '@'; uFlags
0x180007d89  mov     edx, r14d; uBytes
0x180007d8c  call    cs:__imp_LocalAlloc
0x180007d93  nop     dword ptr [rax+rax+00h]
0x180007d98  mov     rbx, rax
0x180007d9b  test    rax, rax
0x180007d9e  jnz     short loc_180007DC8
0x180007da0  call    cs:__imp_GetLastError
0x180007da7  nop     dword ptr [rax+rax+00h]
0x180007dac  mov     edi, eax
0x180007dae  mov     rcx, cs:WPP_GLOBAL_Control
0x180007db5  cmp     rcx, r13
0x180007db8  jz      loc_180007EA3
0x180007dbe  mov     edx, 7Eh ; '~'
0x180007dc3  jmp     loc_180007E90
0x180007dc8  mov     r8, rdi; Size
0x180007dcb  mov     rdx, rbp; Src
0x180007dce  mov     rcx, rbx; void *
0x180007dd1  call    memcpy_0
0x180007dd6  mov     edx, edi; unsigned int
0x180007dd8  mov     rcx, rbx; struct _EAPTLS_CONN_PROPERTIES *
0x180007ddb  call    ?IsEaptlsConnDataValid@@YAHPEAU_EAPTLS_CONN_PROPERTIES@@K@Z; IsEaptlsConnDataValid(_EAPTLS_CONN_PROPERTIES *,ulong)
0x180007de0  test    eax, eax
0x180007de2  jnz     short loc_180007DFD
0x180007de4  mov     rcx, rbx; hMem
0x180007de7  mov     edi, 0Dh
0x180007dec  call    cs:__imp_LocalFree
0x180007df3  nop     dword ptr [rax+rax+00h]
0x180007df8  jmp     loc_180007EB6
0x180007dfd  mov     [rbx+4], r14d
0x180007e01  cmp     [rbx], esi
0x180007e03  jnz     short loc_180007E24
0x180007e05  cmp     [rbx+0Ch], esi
0x180007e08  jz      short loc_180007E24
0x180007e0a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007e11  cmp     [rbx+rax*2+26h], si
0x180007e16  lea     rax, [rax+1]
0x180007e1a  jnz     short loc_180007E11
0x180007e1c  mov     dword ptr [rbx+rax*2+26h], 1
0x180007e24  cmp     dword ptr [rbx], 2
0x180007e27  jz      short loc_180007E3C
0x180007e29  mov     eax, [rbx+8]
0x180007e2c  mov     dword ptr [rbx], 2
0x180007e32  test    al, 1
0x180007e34  jz      short loc_180007E3C
0x180007e36  or      eax, 10h
0x180007e39  mov     [rbx+8], eax
0x180007e3c  mov     eax, [rbx+8]
0x180007e3f  test    al, 20h
0x180007e41  jz      loc_180007F07
0x180007e47  btr     eax, 9
0x180007e4b  mov     [rbx+8], eax
0x180007e4e  jmp     loc_180007F07
0x180007e53  mov     edx, 30h ; '0'; uBytes
0x180007e58  mov     ecx, 40h ; '@'; uFlags
0x180007e5d  call    cs:__imp_LocalAlloc
0x180007e64  nop     dword ptr [rax+rax+00h]
0x180007e69  mov     rbx, rax
0x180007e6c  test    rax, rax
0x180007e6f  jnz     short loc_180007EE3
0x180007e71  call    cs:__imp_GetLastError
0x180007e78  nop     dword ptr [rax+rax+00h]
0x180007e7d  mov     edi, eax
0x180007e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e86  cmp     rcx, r13
0x180007e89  jz      short loc_180007EA3
0x180007e8b  mov     edx, 7Dh ; '}'
0x180007e90  mov     rcx, [rcx+10h]
0x180007e94  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180007e9b  mov     r9d, eax
0x180007e9e  call    WPP_SF_d
0x180007ea3  mov     rcx, rbx; hMem
0x180007ea6  call    cs:__imp_LocalFree
0x180007ead  nop     dword ptr [rax+rax+00h]
0x180007eb2  test    edi, edi
0x180007eb4  jz      short loc_180007F18
0x180007eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ebd  cmp     rcx, r13
0x180007ec0  jz      loc_18000804E
0x180007ec6  mov     rcx, [rcx+10h]
0x180007eca  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180007ed1  mov     edx, 7Bh ; '{'
0x180007ed6  mov     r9d, edi
0x180007ed9  call    WPP_SF_d
0x180007ede  jmp     loc_18000804E
0x180007ee3  mov     dword ptr [rax], 2
0x180007ee9  mov     dword ptr [rax+4], 30h ; '0'
0x180007ef0  test    r15b, r15b
0x180007ef3  jns     short loc_180007EF9
0x180007ef5  or      dword ptr [rax+8], 15h
0x180007ef9  test    r15b, 1
0x180007efd  jz      short loc_180007F07
0x180007eff  or      dword ptr [rax+8], 1
0x180007f03  or      dword ptr [rax+8], 4
0x180007f07  xor     ecx, ecx; hMem
0x180007f09  mov     rsi, rbx
0x180007f0c  call    cs:__imp_LocalFree
0x180007f13  nop     dword ptr [rax+rax+00h]
0x180007f18  test    dword ptr [rsi], 0FFFFFFFDh
0x180007f1e  jz      short loc_180007F4E
0x180007f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f27  cmp     rcx, r13
0x180007f2a  jz      short loc_180007F44
0x180007f2c  mov     rcx, [rcx+10h]
0x180007f30  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180007f37  mov     edx, 7Ch ; '|'
0x180007f3c  mov     r9d, r12d
0x180007f3f  call    WPP_SF_d
0x180007f44  mov     edi, 0A0h
0x180007f49  jmp     loc_18000803F
0x180007f4e  lea     rdx, [rsp+68h+hMem]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x180007f53  mov     rcx, rsi; struct _EAPTLS_CONN_PROPERTIES *
0x180007f56  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x180007f5b  mov     edi, eax
0x180007f5d  test    eax, eax
0x180007f5f  jz      short loc_180007F7B
0x180007f61  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f68  cmp     rcx, r13
0x180007f6b  jz      loc_18000803F
0x180007f71  mov     edx, 7Dh ; '}'
0x180007f76  jmp     loc_18000802C
0x180007f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f82  cmp     rcx, r13
0x180007f85  jz      short loc_180007F9C
0x180007f87  mov     rcx, [rcx+10h]
0x180007f8b  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180007f92  mov     edx, 7Eh ; '~'
0x180007f97  call    WPP_SF_
0x180007f9c  mov     rbx, [rsp+68h+arg_20]
0x180007fa4  lea     r9, IID_IXMLDOMDocument3; riid
0x180007fab  xor     edx, edx; pUnkOuter
0x180007fad  mov     [rsp+68h+ppv], rbx; ppv
0x180007fb2  mov     r8d, 1; dwClsContext
0x180007fb8  lea     rcx, CLSID_DOMDocument60; rclsid
0x180007fbf  call    cs:__imp_CoCreateInstance
0x180007fc6  nop     dword ptr [rax+rax+00h]
0x180007fcb  mov     edi, eax
0x180007fcd  test    eax, eax
0x180007fcf  jz      short loc_180007FE4
0x180007fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fd8  cmp     rcx, r13
0x180007fdb  jz      short loc_18000803F
0x180007fdd  mov     edx, 7Fh
0x180007fe2  jmp     short loc_18000802C
0x180007fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007feb  cmp     rcx, r13
0x180007fee  jz      short loc_180008005
0x180007ff0  mov     rcx, [rcx+10h]
0x180007ff4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180007ffb  mov     edx, 80h
0x180008000  call    WPP_SF_
0x180008005  mov     rdx, [rsp+68h+hMem]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18000800a  mov     r8, rbx; struct IXMLDOMDocument2 **
0x18000800d  mov     ecx, r15d; unsigned int
0x180008010  call    ?PopulateXMLDomFromTLSBlob@@YAKKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAUIXMLDOMDocument2@@@Z; PopulateXMLDomFromTLSBlob(ulong,_EAPTLS_CONN_PROPERTIES_V1 *,IXMLDOMDocument2 * *)
0x180008015  mov     edi, eax
0x180008017  test    eax, eax
0x180008019  jz      short loc_18000803F
0x18000801b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008022  cmp     rcx, r13
0x180008025  jz      short loc_18000803F
0x180008027  mov     edx, 81h
0x18000802c  mov     rcx, [rcx+10h]
0x180008030  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180008037  mov     r9d, eax
0x18000803a  call    WPP_SF_d
0x18000803f  mov     rcx, rsi; hMem
0x180008042  call    cs:__imp_LocalFree
0x180008049  nop     dword ptr [rax+rax+00h]
0x18000804e  mov     rcx, [rsp+68h+hMem]; hMem
0x180008053  mov     r15, [rsp+68h+var_28]
0x180008058  mov     r14, [rsp+68h+var_20]
0x18000805d  mov     r13, [rsp+68h+var_18]
0x180008062  mov     r12, [rsp+68h+var_10]
0x180008067  mov     rsi, [rsp+68h+arg_10]
0x18000806f  mov     rbp, [rsp+68h+arg_8]
0x180008074  mov     rbx, [rsp+68h+arg_0]
0x180008079  test    rcx, rcx
0x18000807c  jz      short loc_18000808A
0x18000807e  call    cs:__imp_LocalFree
0x180008085  nop     dword ptr [rax+rax+00h]
0x18000808a  mov     eax, edi
0x18000808c  add     rsp, 60h
0x180008090  pop     rdi
0x180008091  retn
```
