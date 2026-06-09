# EapTlsCreateConnectionPropertiesXml(ulong,ulong,uchar *,ulong,IXMLDOMDocument2 * *)

- ea: `0x1800075e0`
- end: `0x180007906`
- name: `?EapTlsCreateConnectionPropertiesXml@@YAKKKPEAEKPEAPEAUIXMLDOMDocument2@@@Z`
- size: `806`
- prototype: `unsigned int(unsigned int, unsigned int, unsigned __int8 *, unsigned int, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005730`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x1800075e0`
- `0x180007a90`
- `0x180007c60`
- `0x180007ec0`
- `0x18003623c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000764a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000764a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007709`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007845`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007845`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000763c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800076fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000763c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800076fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007690`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007690`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078f8`

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
0x1800075e0  mov     rax, rsp
0x1800075e3  push    rdi
0x1800075e4  sub     rsp, 60h
0x1800075e8  mov     [rax+8], rbx
0x1800075ec  mov     [rax+10h], rbp
0x1800075f0  mov     rbp, r8
0x1800075f3  mov     [rax+18h], rsi
0x1800075f7  xor     esi, esi
0x1800075f9  mov     [rax-10h], r12
0x1800075fd  mov     r12d, ecx
0x180007600  mov     [rax-18h], r13
0x180007604  lea     r13, WPP_GLOBAL_Control
0x18000760b  mov     [rax-20h], r14
0x18000760f  mov     [rax-28h], r15
0x180007613  mov     r15d, edx
0x180007616  mov     edi, r9d
0x180007619  mov     [rax-38h], rsi
0x18000761d  cmp     r9d, 28h ; '('
0x180007621  jb      loc_1800076F1
0x180007627  test    r8, r8
0x18000762a  jz      loc_1800076F1
0x180007630  lea     r14d, [rdi+8]
0x180007634  mov     ecx, 40h ; '@'; uFlags
0x180007639  mov     edx, r14d; uBytes
0x18000763c  call    cs:__imp_LocalAlloc
0x180007642  mov     rbx, rax
0x180007645  test    rax, rax
0x180007648  jnz     short loc_18000766C
0x18000764a  call    cs:__imp_GetLastError
0x180007650  mov     edi, eax
0x180007652  mov     rcx, cs:WPP_GLOBAL_Control
0x180007659  cmp     rcx, r13
0x18000765c  jz      loc_180007735
0x180007662  mov     edx, 7Eh ; '~'
0x180007667  jmp     loc_180007722
0x18000766c  mov     r8, rdi; Size
0x18000766f  mov     rdx, rbp; Src
0x180007672  mov     rcx, rbx; void *
0x180007675  call    memcpy_0
0x18000767a  mov     edx, edi; unsigned int
0x18000767c  mov     rcx, rbx; struct _EAPTLS_CONN_PROPERTIES *
0x18000767f  call    ?IsEaptlsConnDataValid@@YAHPEAU_EAPTLS_CONN_PROPERTIES@@K@Z; IsEaptlsConnDataValid(_EAPTLS_CONN_PROPERTIES *,ulong)
0x180007684  test    eax, eax
0x180007686  jnz     short loc_18000769B
0x180007688  mov     rcx, rbx; hMem
0x18000768b  mov     edi, 0Dh
0x180007690  call    cs:__imp_LocalFree
0x180007696  jmp     loc_180007742
0x18000769b  mov     [rbx+4], r14d
0x18000769f  cmp     [rbx], esi
0x1800076a1  jnz     short loc_1800076C2
0x1800076a3  cmp     [rbx+0Ch], esi
0x1800076a6  jz      short loc_1800076C2
0x1800076a8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800076af  cmp     [rbx+rax*2+26h], si
0x1800076b4  lea     rax, [rax+1]
0x1800076b8  jnz     short loc_1800076AF
0x1800076ba  mov     dword ptr [rbx+rax*2+26h], 1
0x1800076c2  cmp     dword ptr [rbx], 2
0x1800076c5  jz      short loc_1800076DA
0x1800076c7  mov     eax, [rbx+8]
0x1800076ca  mov     dword ptr [rbx], 2
0x1800076d0  test    al, 1
0x1800076d2  jz      short loc_1800076DA
0x1800076d4  or      eax, 10h
0x1800076d7  mov     [rbx+8], eax
0x1800076da  mov     eax, [rbx+8]
0x1800076dd  test    al, 20h
0x1800076df  jz      loc_180007793
0x1800076e5  btr     eax, 9
0x1800076e9  mov     [rbx+8], eax
0x1800076ec  jmp     loc_180007793
0x1800076f1  mov     edx, 30h ; '0'; uBytes
0x1800076f6  mov     ecx, 40h ; '@'; uFlags
0x1800076fb  call    cs:__imp_LocalAlloc
0x180007701  mov     rbx, rax
0x180007704  test    rax, rax
0x180007707  jnz     short loc_18000776F
0x180007709  call    cs:__imp_GetLastError
0x18000770f  mov     edi, eax
0x180007711  mov     rcx, cs:WPP_GLOBAL_Control
0x180007718  cmp     rcx, r13
0x18000771b  jz      short loc_180007735
0x18000771d  mov     edx, 7Dh ; '}'
0x180007722  mov     rcx, [rcx+10h]
0x180007726  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18000772d  mov     r9d, eax
0x180007730  call    WPP_SF_d
0x180007735  mov     rcx, rbx; hMem
0x180007738  call    cs:__imp_LocalFree
0x18000773e  test    edi, edi
0x180007740  jz      short loc_18000779E
0x180007742  mov     rcx, cs:WPP_GLOBAL_Control
0x180007749  cmp     rcx, r13
0x18000774c  jz      loc_1800078C8
0x180007752  mov     rcx, [rcx+10h]
0x180007756  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000775d  mov     edx, 7Bh ; '{'
0x180007762  mov     r9d, edi
0x180007765  call    WPP_SF_d
0x18000776a  jmp     loc_1800078C8
0x18000776f  mov     dword ptr [rax], 2
0x180007775  mov     dword ptr [rax+4], 30h ; '0'
0x18000777c  test    r15b, r15b
0x18000777f  jns     short loc_180007785
0x180007781  or      dword ptr [rax+8], 15h
0x180007785  test    r15b, 1
0x180007789  jz      short loc_180007793
0x18000778b  or      dword ptr [rax+8], 1
0x18000778f  or      dword ptr [rax+8], 4
0x180007793  xor     ecx, ecx; hMem
0x180007795  mov     rsi, rbx
0x180007798  call    cs:__imp_LocalFree
0x18000779e  test    dword ptr [rsi], 0FFFFFFFDh
0x1800077a4  jz      short loc_1800077D4
0x1800077a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077ad  cmp     rcx, r13
0x1800077b0  jz      short loc_1800077CA
0x1800077b2  mov     rcx, [rcx+10h]
0x1800077b6  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800077bd  mov     edx, 7Ch ; '|'
0x1800077c2  mov     r9d, r12d
0x1800077c5  call    WPP_SF_d
0x1800077ca  mov     edi, 0A0h
0x1800077cf  jmp     loc_1800078BF
0x1800077d4  lea     rdx, [rsp+68h+hMem]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x1800077d9  mov     rcx, rsi; struct _EAPTLS_CONN_PROPERTIES *
0x1800077dc  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x1800077e1  mov     edi, eax
0x1800077e3  test    eax, eax
0x1800077e5  jz      short loc_180007801
0x1800077e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077ee  cmp     rcx, r13
0x1800077f1  jz      loc_1800078BF
0x1800077f7  mov     edx, 7Dh ; '}'
0x1800077fc  jmp     loc_1800078AC
0x180007801  mov     rcx, cs:WPP_GLOBAL_Control
0x180007808  cmp     rcx, r13
0x18000780b  jz      short loc_180007822
0x18000780d  mov     rcx, [rcx+10h]
0x180007811  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180007818  mov     edx, 7Eh ; '~'
0x18000781d  call    WPP_SF_
0x180007822  mov     rbx, [rsp+68h+arg_20]
0x18000782a  lea     r9, IID_IXMLDOMDocument3; riid
0x180007831  xor     edx, edx; pUnkOuter
0x180007833  mov     [rsp+68h+ppv], rbx; ppv
0x180007838  mov     r8d, 1; dwClsContext
0x18000783e  lea     rcx, CLSID_DOMDocument60; rclsid
0x180007845  call    cs:__imp_CoCreateInstance
0x18000784b  mov     edi, eax
0x18000784d  test    eax, eax
0x18000784f  jz      short loc_180007864
0x180007851  mov     rcx, cs:WPP_GLOBAL_Control
0x180007858  cmp     rcx, r13
0x18000785b  jz      short loc_1800078BF
0x18000785d  mov     edx, 7Fh
0x180007862  jmp     short loc_1800078AC
0x180007864  mov     rcx, cs:WPP_GLOBAL_Control
0x18000786b  cmp     rcx, r13
0x18000786e  jz      short loc_180007885
0x180007870  mov     rcx, [rcx+10h]
0x180007874  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000787b  mov     edx, 80h
0x180007880  call    WPP_SF_
0x180007885  mov     rdx, [rsp+68h+hMem]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18000788a  mov     r8, rbx; struct IXMLDOMDocument2 **
0x18000788d  mov     ecx, r15d; unsigned int
0x180007890  call    ?PopulateXMLDomFromTLSBlob@@YAKKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAUIXMLDOMDocument2@@@Z; PopulateXMLDomFromTLSBlob(ulong,_EAPTLS_CONN_PROPERTIES_V1 *,IXMLDOMDocument2 * *)
0x180007895  mov     edi, eax
0x180007897  test    eax, eax
0x180007899  jz      short loc_1800078BF
0x18000789b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078a2  cmp     rcx, r13
0x1800078a5  jz      short loc_1800078BF
0x1800078a7  mov     edx, 81h
0x1800078ac  mov     rcx, [rcx+10h]
0x1800078b0  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800078b7  mov     r9d, eax
0x1800078ba  call    WPP_SF_d
0x1800078bf  mov     rcx, rsi; hMem
0x1800078c2  call    cs:__imp_LocalFree
0x1800078c8  mov     rcx, [rsp+68h+hMem]; hMem
0x1800078cd  mov     r15, [rsp+68h+var_28]
0x1800078d2  mov     r14, [rsp+68h+var_20]
0x1800078d7  mov     r13, [rsp+68h+var_18]
0x1800078dc  mov     r12, [rsp+68h+var_10]
0x1800078e1  mov     rsi, [rsp+68h+arg_10]
0x1800078e9  mov     rbp, [rsp+68h+arg_8]
0x1800078ee  mov     rbx, [rsp+68h+arg_0]
0x1800078f3  test    rcx, rcx
0x1800078f6  jz      short loc_1800078FE
0x1800078f8  call    cs:__imp_LocalFree
0x1800078fe  mov     eax, edi
0x180007900  add     rsp, 60h
0x180007904  pop     rdi
0x180007905  retn
```
