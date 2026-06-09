# RasEapCreateConnectionPropertiesXml

- ea: `0x180005be0`
- end: `0x180005f72`
- name: `RasEapCreateConnectionPropertiesXml`
- size: `914`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005010`
- `0x180005be0`
- `0x180005f80`
- `0x180006620`
- `0x180006960`
- `0x180007d00`
- `0x180007d30`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005e6e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005e6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f42`

## pseudocode

```c
__int64 __fastcall RasEapCreateConnectionPropertiesXml(
        unsigned int a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        LPVOID *a5)
{
  struct _EAPTLS_CONTROL_BLOCK *v9; // rax
  unsigned int ConnectionPropertiesXml; // ebx
  struct IXMLDOMDocument2 **ppv; // rsi
  unsigned int ConnectionData; // eax
  struct _PEAP_CONN_PROPERTIES *v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  struct _EAPTLS_CONTROL_BLOCK *v18; // r10
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rax
  char *v22; // rdx
  char *v24; // rcx
  unsigned int Instance; // eax
  unsigned int v26; // eax
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF

  EapTlsInitialize2(1, 0);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a1);
    v9 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( !a4 )
      goto LABEL_5;
  }
  else if ( a4 )
  {
LABEL_5:
    ConnectionPropertiesXml = 160;
    goto LABEL_6;
  }
  ppv = (struct IXMLDOMDocument2 **)a5;
  if ( !a5 )
    goto LABEL_5;
  if ( *a5 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*a5 + 16LL))(*a5);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)v9 + 2), 136, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a1);
    v9 = WPP_GLOBAL_Control;
  }
  if ( a1 != 25 )
  {
    if ( a1 == 13 )
    {
      ConnectionPropertiesXml = EapTlsCreateConnectionPropertiesXml(0xDu, a2, a3, a4, ppv);
    }
    else
    {
      if ( v9 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)v9 + 2), 137, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a1);
      ConnectionPropertiesXml = 50;
    }
    goto LABEL_6;
  }
  hMem = 0;
  ConnectionData = PeapReadConnectionData(a2, a3, a4, (struct _PEAP_CONN_PROPERTIES **)&hMem);
  v14 = (struct _PEAP_CONN_PROPERTIES *)hMem;
  ConnectionPropertiesXml = ConnectionData;
  if ( ConnectionData )
  {
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_59;
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = 130;
    v17 = ConnectionData;
    goto LABEL_58;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    v18 = WPP_GLOBAL_Control;
  }
  if ( v14 )
  {
    v20 = *((_DWORD *)v14 + 2);
    if ( !v20 )
      goto LABEL_40;
    if ( v20 != 1 )
    {
      if ( v18 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)v18 + 2), 53, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
        v18 = WPP_GLOBAL_Control;
      }
      ConnectionPropertiesXml = 50;
      goto LABEL_56;
    }
    v21 = -1;
    v22 = (char *)v14 + 24 * *((unsigned int *)v14 + 7);
    while ( *(_WORD *)&v22[2 * v21++ + 34] != 0 )
      ;
    v24 = &v22[2 * v21 + 34];
    if ( !v24 )
    {
      if ( v18 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(*((_QWORD *)v18 + 2), 51, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, 0);
LABEL_54:
        v18 = WPP_GLOBAL_Control;
        goto LABEL_55;
      }
      goto LABEL_55;
    }
    if ( *(_DWORD *)v24 == 1 )
    {
LABEL_40:
      if ( *(_DWORD *)v14 == 1 && (unsigned int)(*((_DWORD *)v14 + 4) - 1) <= 1 )
      {
        if ( v18 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)v18 + 2), 132, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
        Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument3, (LPVOID *)ppv);
        ConnectionPropertiesXml = Instance;
        if ( Instance )
        {
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_59;
          v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v16 = 133;
          v17 = Instance;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
          v26 = PopulateXMLDomFromPeapBlob(v14, ppv, a2);
          ConnectionPropertiesXml = v26;
          if ( !v26 || WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_59;
          v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v16 = 135;
          v17 = v26;
        }
        goto LABEL_58;
      }
      if ( v18 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_55;
      v19 = 54;
      goto LABEL_53;
    }
    if ( v18 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v19 = 52;
      goto LABEL_53;
    }
  }
  else if ( v18 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v19 = 50;
LABEL_53:
    WPP_SF_(*((_QWORD *)v18 + 2), v19, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    goto LABEL_54;
  }
LABEL_55:
  ConnectionPropertiesXml = 160;
LABEL_56:
  if ( v18 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    goto LABEL_59;
  v15 = *((_QWORD *)v18 + 2);
  v16 = 131;
  v17 = 25;
LABEL_58:
  WPP_SF_d(v15, v16, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v17);
LABEL_59:
  if ( v14 )
    LocalFree(v14);
LABEL_6:
  EapTlsInitialize2(0, 0);
  return ConnectionPropertiesXml;
}

```

## disassembly

```asm
0x180005be0  mov     [rsp+arg_8], rbx
0x180005be5  mov     [rsp+arg_18], rbp
0x180005bea  push    rdi
0x180005beb  push    r14
0x180005bed  push    r15
0x180005bef  sub     rsp, 30h
0x180005bf3  mov     r14d, edx
0x180005bf6  mov     edi, ecx
0x180005bf8  xor     edx, edx; int
0x180005bfa  mov     ecx, 1; int
0x180005bff  mov     ebp, r9d
0x180005c02  mov     rbx, r8
0x180005c05  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180005c0a  mov     rax, cs:WPP_GLOBAL_Control
0x180005c11  lea     r15, WPP_GLOBAL_Control
0x180005c18  cmp     rax, r15
0x180005c1b  jz      short loc_180005C3C
0x180005c1d  mov     rcx, [rax+10h]
0x180005c21  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005c28  mov     edx, 8Ah
0x180005c2d  mov     r9d, edi
0x180005c30  call    WPP_SF_d
0x180005c35  mov     rax, cs:WPP_GLOBAL_Control
0x180005c3c  mov     [rsp+48h+arg_0], rsi
0x180005c41  test    rbx, rbx
0x180005c44  jnz     short loc_180005C74
0x180005c46  test    ebp, ebp
0x180005c48  jz      short loc_180005C78
0x180005c4a  mov     ebx, 0A0h
0x180005c4f  xor     edx, edx; int
0x180005c51  xor     ecx, ecx; int
0x180005c53  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180005c58  mov     rsi, [rsp+48h+arg_0]
0x180005c5d  mov     eax, ebx
0x180005c5f  mov     rbx, [rsp+48h+arg_8]
0x180005c64  mov     rbp, [rsp+48h+arg_18]
0x180005c69  add     rsp, 30h
0x180005c6d  pop     r15
0x180005c6f  pop     r14
0x180005c71  pop     rdi
0x180005c72  retn
0x180005c74  test    ebp, ebp
0x180005c76  jz      short loc_180005C4A
0x180005c78  mov     rsi, [rsp+48h+arg_20]
0x180005c7d  test    rsi, rsi
0x180005c80  jz      short loc_180005C4A
0x180005c82  mov     rcx, [rsi]
0x180005c85  test    rcx, rcx
0x180005c88  jz      short loc_180005C9D
0x180005c8a  mov     rax, [rcx]
0x180005c8d  mov     rax, [rax+10h]
0x180005c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c96  mov     rax, cs:WPP_GLOBAL_Control
0x180005c9d  cmp     rax, r15
0x180005ca0  jz      short loc_180005CC1
0x180005ca2  mov     rcx, [rax+10h]
0x180005ca6  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005cad  mov     edx, 88h
0x180005cb2  mov     r9d, edi
0x180005cb5  call    WPP_SF_d
0x180005cba  mov     rax, cs:WPP_GLOBAL_Control
0x180005cc1  cmp     edi, 19h
0x180005cc4  jz      short loc_180005CF6
0x180005cc6  cmp     edi, 0Dh
0x180005cc9  jz      loc_180005F53
0x180005ccf  cmp     rax, r15
0x180005cd2  jz      short loc_180005CEC
0x180005cd4  mov     rcx, [rax+10h]
0x180005cd8  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005cdf  mov     edx, 89h
0x180005ce4  mov     r9d, edi
0x180005ce7  call    WPP_SF_d
0x180005cec  mov     ebx, 32h ; '2'
0x180005cf1  jmp     loc_180005C4F
0x180005cf6  lea     r9, [rsp+48h+hMem]; struct _PEAP_CONN_PROPERTIES **
0x180005cfb  mov     [rsp+48h+hMem], 0
0x180005d04  mov     r8d, ebp; unsigned int
0x180005d07  mov     rdx, rbx; unsigned __int8 *
0x180005d0a  mov     ecx, r14d; unsigned int
0x180005d0d  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x180005d12  mov     rdi, [rsp+48h+hMem]
0x180005d17  mov     ebx, eax
0x180005d19  test    eax, eax
0x180005d1b  jz      short loc_180005D3E
0x180005d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d24  cmp     rcx, r15
0x180005d27  jz      loc_180005F36
0x180005d2d  mov     rcx, [rcx+10h]
0x180005d31  mov     edx, 82h
0x180005d36  mov     r9d, eax
0x180005d39  jmp     loc_180005F2A
0x180005d3e  mov     r10, cs:WPP_GLOBAL_Control
0x180005d45  cmp     r10, r15
0x180005d48  jz      short loc_180005D66
0x180005d4a  mov     rcx, [r10+10h]
0x180005d4e  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005d55  mov     edx, 31h ; '1'
0x180005d5a  call    WPP_SF_
0x180005d5f  mov     r10, cs:WPP_GLOBAL_Control
0x180005d66  test    rdi, rdi
0x180005d69  jnz     short loc_180005D7E
0x180005d6b  cmp     r10, r15
0x180005d6e  jz      loc_180005F11
0x180005d74  mov     edx, 32h ; '2'
0x180005d79  jmp     loc_180005EFA
0x180005d7e  mov     ecx, [rdi+8]
0x180005d81  test    ecx, ecx
0x180005d83  jz      loc_180005E22
0x180005d89  cmp     ecx, 1
0x180005d8c  jz      short loc_180005DB9
0x180005d8e  cmp     r10, r15
0x180005d91  jz      short loc_180005DAF
0x180005d93  mov     rcx, [r10+10h]
0x180005d97  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005d9e  mov     edx, 35h ; '5'
0x180005da3  call    WPP_SF_
0x180005da8  mov     r10, cs:WPP_GLOBAL_Control
0x180005daf  mov     ebx, 32h ; '2'
0x180005db4  jmp     loc_180005F16
0x180005db9  mov     eax, [rdi+1Ch]
0x180005dbc  lea     rcx, [rax+rax*2]
0x180005dc0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005dc7  lea     rdx, [rdi+rcx*8]
0x180005dcb  cmp     word ptr [rdx+rax*2+22h], 0
0x180005dd1  lea     rax, [rax+1]
0x180005dd5  jnz     short loc_180005DCB
0x180005dd7  lea     rcx, [rdx+22h]
0x180005ddb  lea     rcx, [rcx+rax*2]
0x180005ddf  test    rcx, rcx
0x180005de2  jz      short loc_180005DFC
0x180005de4  cmp     dword ptr [rcx], 1
0x180005de7  jz      short loc_180005E22
0x180005de9  cmp     r10, r15
0x180005dec  jz      loc_180005F11
0x180005df2  mov     edx, 34h ; '4'
0x180005df7  jmp     loc_180005EFA
0x180005dfc  cmp     r10, r15
0x180005dff  jz      loc_180005F11
0x180005e05  mov     rcx, [r10+10h]
0x180005e09  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005e10  mov     edx, 33h ; '3'
0x180005e15  xor     r9d, r9d
0x180005e18  call    WPP_SF_d
0x180005e1d  jmp     loc_180005F0A
0x180005e22  cmp     dword ptr [rdi], 1
0x180005e25  jnz     loc_180005EF0
0x180005e2b  mov     eax, [rdi+10h]
0x180005e2e  dec     eax
0x180005e30  cmp     eax, 1
0x180005e33  ja      loc_180005EF0
0x180005e39  cmp     r10, r15
0x180005e3c  jz      short loc_180005E53
0x180005e3e  mov     rcx, [r10+10h]
0x180005e42  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005e49  mov     edx, 84h
0x180005e4e  call    WPP_SF_
0x180005e53  lea     r9, IID_IXMLDOMDocument3; riid
0x180005e5a  mov     [rsp+48h+ppv], rsi; ppv
0x180005e5f  xor     edx, edx; pUnkOuter
0x180005e61  lea     rcx, CLSID_DOMDocument60; rclsid
0x180005e68  mov     r8d, 1; dwClsContext
0x180005e6e  call    cs:__imp_CoCreateInstance
0x180005e75  nop     dword ptr [rax+rax+00h]
0x180005e7a  mov     ebx, eax
0x180005e7c  test    eax, eax
0x180005e7e  jz      short loc_180005EA1
0x180005e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e87  cmp     rcx, r15
0x180005e8a  jz      loc_180005F36
0x180005e90  mov     rcx, [rcx+10h]
0x180005e94  mov     edx, 85h
0x180005e99  mov     r9d, eax
0x180005e9c  jmp     loc_180005F2A
0x180005ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ea8  cmp     rcx, r15
0x180005eab  jz      short loc_180005EC2
0x180005ead  mov     rcx, [rcx+10h]
0x180005eb1  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005eb8  mov     edx, 86h
0x180005ebd  call    WPP_SF_
0x180005ec2  mov     r8d, r14d; unsigned int
0x180005ec5  mov     rdx, rsi; struct IXMLDOMDocument2 **
0x180005ec8  mov     rcx, rdi; struct _PEAP_CONN_PROPERTIES *
0x180005ecb  call    ?PopulateXMLDomFromPeapBlob@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAUIXMLDOMDocument2@@K@Z; PopulateXMLDomFromPeapBlob(_PEAP_CONN_PROPERTIES *,IXMLDOMDocument2 * *,ulong)
0x180005ed0  mov     ebx, eax
0x180005ed2  test    eax, eax
0x180005ed4  jz      short loc_180005F36
0x180005ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005edd  cmp     rcx, r15
0x180005ee0  jz      short loc_180005F36
0x180005ee2  mov     rcx, [rcx+10h]
0x180005ee6  mov     edx, 87h
0x180005eeb  mov     r9d, eax
0x180005eee  jmp     short loc_180005F2A
0x180005ef0  cmp     r10, r15
0x180005ef3  jz      short loc_180005F11
0x180005ef5  mov     edx, 36h ; '6'
0x180005efa  mov     rcx, [r10+10h]
0x180005efe  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005f05  call    WPP_SF_
0x180005f0a  mov     r10, cs:WPP_GLOBAL_Control
0x180005f11  mov     ebx, 0A0h
0x180005f16  cmp     r10, r15
0x180005f19  jz      short loc_180005F36
0x180005f1b  mov     rcx, [r10+10h]
0x180005f1f  mov     edx, 83h
0x180005f24  mov     r9d, 19h
0x180005f2a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005f31  call    WPP_SF_d
0x180005f36  test    rdi, rdi
0x180005f39  jz      loc_180005C4F
0x180005f3f  mov     rcx, rdi; hMem
0x180005f42  call    cs:__imp_LocalFree
0x180005f49  nop     dword ptr [rax+rax+00h]
0x180005f4e  jmp     loc_180005C4F
0x180005f53  mov     r9d, ebp; unsigned int
0x180005f56  mov     [rsp+48h+ppv], rsi; struct IXMLDOMDocument2 **
0x180005f5b  mov     r8, rbx; unsigned __int8 *
0x180005f5e  mov     edx, r14d; unsigned int
0x180005f61  mov     ecx, 0Dh; unsigned int
0x180005f66  call    ?EapTlsCreateConnectionPropertiesXml@@YAKKKPEAEKPEAPEAUIXMLDOMDocument2@@@Z; EapTlsCreateConnectionPropertiesXml(ulong,ulong,uchar *,ulong,IXMLDOMDocument2 * *)
0x180005f6b  mov     ebx, eax
0x180005f6d  jmp     loc_180005C4F
```
