# RasEapCreateConnectionPropertiesXml

- ea: `0x180005730`
- end: `0x180005ab5`
- name: `RasEapCreateConnectionPropertiesXml`
- size: `901`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004bd0`
- `0x180005730`
- `0x180005ac0`
- `0x1800060f0`
- `0x180006400`
- `0x1800075b0`
- `0x1800075e0`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800059bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800059bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a8b`

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
0x180005730  mov     [rsp+arg_8], rbx
0x180005735  mov     [rsp+arg_18], rbp
0x18000573a  push    rdi
0x18000573b  push    r14
0x18000573d  push    r15
0x18000573f  sub     rsp, 30h
0x180005743  mov     r14d, edx
0x180005746  mov     edi, ecx
0x180005748  xor     edx, edx; int
0x18000574a  mov     ecx, 1; int
0x18000574f  mov     ebp, r9d
0x180005752  mov     rbx, r8
0x180005755  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x18000575a  mov     rax, cs:WPP_GLOBAL_Control
0x180005761  lea     r15, WPP_GLOBAL_Control
0x180005768  cmp     rax, r15
0x18000576b  jz      short loc_18000578C
0x18000576d  mov     rcx, [rax+10h]
0x180005771  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005778  mov     edx, 8Ah
0x18000577d  mov     r9d, edi
0x180005780  call    WPP_SF_d
0x180005785  mov     rax, cs:WPP_GLOBAL_Control
0x18000578c  mov     [rsp+48h+arg_0], rsi
0x180005791  test    rbx, rbx
0x180005794  jnz     short loc_1800057C3
0x180005796  test    ebp, ebp
0x180005798  jz      short loc_1800057C7
0x18000579a  mov     ebx, 0A0h
0x18000579f  xor     edx, edx; int
0x1800057a1  xor     ecx, ecx; int
0x1800057a3  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x1800057a8  mov     rsi, [rsp+48h+arg_0]
0x1800057ad  mov     eax, ebx
0x1800057af  mov     rbx, [rsp+48h+arg_8]
0x1800057b4  mov     rbp, [rsp+48h+arg_18]
0x1800057b9  add     rsp, 30h
0x1800057bd  pop     r15
0x1800057bf  pop     r14
0x1800057c1  pop     rdi
0x1800057c2  retn
0x1800057c3  test    ebp, ebp
0x1800057c5  jz      short loc_18000579A
0x1800057c7  mov     rsi, [rsp+48h+arg_20]
0x1800057cc  test    rsi, rsi
0x1800057cf  jz      short loc_18000579A
0x1800057d1  mov     rcx, [rsi]
0x1800057d4  test    rcx, rcx
0x1800057d7  jz      short loc_1800057EC
0x1800057d9  mov     rax, [rcx]
0x1800057dc  mov     rax, [rax+10h]
0x1800057e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e5  mov     rax, cs:WPP_GLOBAL_Control
0x1800057ec  cmp     rax, r15
0x1800057ef  jz      short loc_180005810
0x1800057f1  mov     rcx, [rax+10h]
0x1800057f5  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800057fc  mov     edx, 88h
0x180005801  mov     r9d, edi
0x180005804  call    WPP_SF_d
0x180005809  mov     rax, cs:WPP_GLOBAL_Control
0x180005810  cmp     edi, 19h
0x180005813  jz      short loc_180005845
0x180005815  cmp     edi, 0Dh
0x180005818  jz      loc_180005A96
0x18000581e  cmp     rax, r15
0x180005821  jz      short loc_18000583B
0x180005823  mov     rcx, [rax+10h]
0x180005827  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000582e  mov     edx, 89h
0x180005833  mov     r9d, edi
0x180005836  call    WPP_SF_d
0x18000583b  mov     ebx, 32h ; '2'
0x180005840  jmp     loc_18000579F
0x180005845  lea     r9, [rsp+48h+hMem]; struct _PEAP_CONN_PROPERTIES **
0x18000584a  mov     [rsp+48h+hMem], 0
0x180005853  mov     r8d, ebp; unsigned int
0x180005856  mov     rdx, rbx; unsigned __int8 *
0x180005859  mov     ecx, r14d; unsigned int
0x18000585c  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x180005861  mov     rdi, [rsp+48h+hMem]
0x180005866  mov     ebx, eax
0x180005868  test    eax, eax
0x18000586a  jz      short loc_18000588D
0x18000586c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005873  cmp     rcx, r15
0x180005876  jz      loc_180005A7F
0x18000587c  mov     rcx, [rcx+10h]
0x180005880  mov     edx, 82h
0x180005885  mov     r9d, eax
0x180005888  jmp     loc_180005A73
0x18000588d  mov     r10, cs:WPP_GLOBAL_Control
0x180005894  cmp     r10, r15
0x180005897  jz      short loc_1800058B5
0x180005899  mov     rcx, [r10+10h]
0x18000589d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800058a4  mov     edx, 31h ; '1'
0x1800058a9  call    WPP_SF_
0x1800058ae  mov     r10, cs:WPP_GLOBAL_Control
0x1800058b5  test    rdi, rdi
0x1800058b8  jnz     short loc_1800058CD
0x1800058ba  cmp     r10, r15
0x1800058bd  jz      loc_180005A5A
0x1800058c3  mov     edx, 32h ; '2'
0x1800058c8  jmp     loc_180005A43
0x1800058cd  mov     ecx, [rdi+8]
0x1800058d0  test    ecx, ecx
0x1800058d2  jz      loc_180005971
0x1800058d8  cmp     ecx, 1
0x1800058db  jz      short loc_180005908
0x1800058dd  cmp     r10, r15
0x1800058e0  jz      short loc_1800058FE
0x1800058e2  mov     rcx, [r10+10h]
0x1800058e6  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800058ed  mov     edx, 35h ; '5'
0x1800058f2  call    WPP_SF_
0x1800058f7  mov     r10, cs:WPP_GLOBAL_Control
0x1800058fe  mov     ebx, 32h ; '2'
0x180005903  jmp     loc_180005A5F
0x180005908  mov     eax, [rdi+1Ch]
0x18000590b  lea     rcx, [rax+rax*2]
0x18000590f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005916  lea     rdx, [rdi+rcx*8]
0x18000591a  cmp     word ptr [rdx+rax*2+22h], 0
0x180005920  lea     rax, [rax+1]
0x180005924  jnz     short loc_18000591A
0x180005926  lea     rcx, [rdx+22h]
0x18000592a  lea     rcx, [rcx+rax*2]
0x18000592e  test    rcx, rcx
0x180005931  jz      short loc_18000594B
0x180005933  cmp     dword ptr [rcx], 1
0x180005936  jz      short loc_180005971
0x180005938  cmp     r10, r15
0x18000593b  jz      loc_180005A5A
0x180005941  mov     edx, 34h ; '4'
0x180005946  jmp     loc_180005A43
0x18000594b  cmp     r10, r15
0x18000594e  jz      loc_180005A5A
0x180005954  mov     rcx, [r10+10h]
0x180005958  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000595f  mov     edx, 33h ; '3'
0x180005964  xor     r9d, r9d
0x180005967  call    WPP_SF_d
0x18000596c  jmp     loc_180005A53
0x180005971  cmp     dword ptr [rdi], 1
0x180005974  jnz     loc_180005A39
0x18000597a  mov     eax, [rdi+10h]
0x18000597d  dec     eax
0x18000597f  cmp     eax, 1
0x180005982  ja      loc_180005A39
0x180005988  cmp     r10, r15
0x18000598b  jz      short loc_1800059A2
0x18000598d  mov     rcx, [r10+10h]
0x180005991  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005998  mov     edx, 84h
0x18000599d  call    WPP_SF_
0x1800059a2  lea     r9, IID_IXMLDOMDocument3; riid
0x1800059a9  mov     [rsp+48h+ppv], rsi; ppv
0x1800059ae  xor     edx, edx; pUnkOuter
0x1800059b0  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800059b7  mov     r8d, 1; dwClsContext
0x1800059bd  call    cs:__imp_CoCreateInstance
0x1800059c3  mov     ebx, eax
0x1800059c5  test    eax, eax
0x1800059c7  jz      short loc_1800059EA
0x1800059c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059d0  cmp     rcx, r15
0x1800059d3  jz      loc_180005A7F
0x1800059d9  mov     rcx, [rcx+10h]
0x1800059dd  mov     edx, 85h
0x1800059e2  mov     r9d, eax
0x1800059e5  jmp     loc_180005A73
0x1800059ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059f1  cmp     rcx, r15
0x1800059f4  jz      short loc_180005A0B
0x1800059f6  mov     rcx, [rcx+10h]
0x1800059fa  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005a01  mov     edx, 86h
0x180005a06  call    WPP_SF_
0x180005a0b  mov     r8d, r14d; unsigned int
0x180005a0e  mov     rdx, rsi; struct IXMLDOMDocument2 **
0x180005a11  mov     rcx, rdi; struct _PEAP_CONN_PROPERTIES *
0x180005a14  call    ?PopulateXMLDomFromPeapBlob@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAUIXMLDOMDocument2@@K@Z; PopulateXMLDomFromPeapBlob(_PEAP_CONN_PROPERTIES *,IXMLDOMDocument2 * *,ulong)
0x180005a19  mov     ebx, eax
0x180005a1b  test    eax, eax
0x180005a1d  jz      short loc_180005A7F
0x180005a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a26  cmp     rcx, r15
0x180005a29  jz      short loc_180005A7F
0x180005a2b  mov     rcx, [rcx+10h]
0x180005a2f  mov     edx, 87h
0x180005a34  mov     r9d, eax
0x180005a37  jmp     short loc_180005A73
0x180005a39  cmp     r10, r15
0x180005a3c  jz      short loc_180005A5A
0x180005a3e  mov     edx, 36h ; '6'
0x180005a43  mov     rcx, [r10+10h]
0x180005a47  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005a4e  call    WPP_SF_
0x180005a53  mov     r10, cs:WPP_GLOBAL_Control
0x180005a5a  mov     ebx, 0A0h
0x180005a5f  cmp     r10, r15
0x180005a62  jz      short loc_180005A7F
0x180005a64  mov     rcx, [r10+10h]
0x180005a68  mov     edx, 83h
0x180005a6d  mov     r9d, 19h
0x180005a73  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005a7a  call    WPP_SF_d
0x180005a7f  test    rdi, rdi
0x180005a82  jz      loc_18000579F
0x180005a88  mov     rcx, rdi; hMem
0x180005a8b  call    cs:__imp_LocalFree
0x180005a91  jmp     loc_18000579F
0x180005a96  mov     r9d, ebp; unsigned int
0x180005a99  mov     [rsp+48h+ppv], rsi; struct IXMLDOMDocument2 **
0x180005a9e  mov     r8, rbx; unsigned __int8 *
0x180005aa1  mov     edx, r14d; unsigned int
0x180005aa4  mov     ecx, 0Dh; unsigned int
0x180005aa9  call    ?EapTlsCreateConnectionPropertiesXml@@YAKKKPEAEKPEAPEAUIXMLDOMDocument2@@@Z; EapTlsCreateConnectionPropertiesXml(ulong,ulong,uchar *,ulong,IXMLDOMDocument2 * *)
0x180005aae  mov     ebx, eax
0x180005ab0  jmp     loc_18000579F
```
