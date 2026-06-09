# RasEapTlsInvokeConfigUI(ulong,HWND__ *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180070bf8`
- end: `0x180070f6f`
- name: `?RasEapTlsInvokeConfigUI@@YAKKPEAUHWND__@@KPEAEKPEAPEAEPEAK@Z`
- size: `887`
- prototype: `unsigned int(unsigned int, HWND, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18005d3c0`

## callees

- `0x180005010`
- `0x180005f80`
- `0x1800080a0`
- `0x180008420`
- `0x18001fa30`
- `0x18002077c`
- `0x180022680`
- `0x180035b28`
- `0x180038e64`
- `0x18006dff8`
- `0x180070bf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ea4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070d29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070d29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070f16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070f30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070f16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070f30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070f40`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x180070e92`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x180070e92`

## pseudocode

```c
__int64 __fastcall RasEapTlsInvokeConfigUI(
        __int64 a1,
        HWND a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        struct _EAPTLS_CONN_PROPERTIES **a6,
        unsigned int *a7)
{
  struct _EAPTLS_CONN_PROPERTIES **v10; // rbx
  unsigned int *v11; // r14
  int v12; // eax
  int v13; // esi
  int v14; // eax
  unsigned int V1Struct; // eax
  char *v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  struct _EAPTLS_CERT_NODE **v19; // rdx
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  INT_PTR v24; // rax
  LPARAM dwInitParam; // [rsp+68h] [rbp-A0h] BYREF
  HLOCAL v27; // [rsp+70h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-90h]
  HLOCAL v29; // [rsp+80h] [rbp-88h] BYREF
  HLOCAL v30; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v31[264]; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v32; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int8 *v33; // [rsp+1A0h] [rbp+98h] BYREF
  unsigned int ConnectionData; // [rsp+248h] [rbp+140h] BYREF

  ConnectionData = 0;
  memset_0(&dwInitParam, 0, 0x1B0u);
  EapTlsInitialize2(1, 1);
  v10 = a6;
  v11 = a7;
  *a6 = 0;
  *v11 = 0;
  memset_0(&dwInitParam, 0, 0x1B0u);
  v12 = dwInitParam;
  v13 = a3 & 1;
  if ( (a3 & 1) != 0 )
    v12 = 1;
  LODWORD(dwInitParam) = v12;
  if ( (a3 & 0x80000) != 0 )
    LODWORD(dwInitParam) = v13 | 0x80000;
  v14 = v13 | 0x80000;
  if ( (a3 & 0x80000) == 0 )
    v14 = a3 & 1;
  if ( (a3 & 0x2000000) != 0 )
    LODWORD(dwInitParam) = v14 | 0x2000000;
  ConnectionData = EapTlsReadConnectionData(a3, a4, a5, (struct _EAPTLS_CONN_PROPERTIES **)&v29);
  if ( !ConnectionData )
  {
    V1Struct = ConnPropGetV1Struct((struct _EAPTLS_CONN_PROPERTIES *)v29, (struct _EAPTLS_CONN_PROPERTIES_V1 **)&v30);
    ConnectionData = V1Struct;
    if ( (a3 & 2) != 0 )
    {
      if ( V1Struct )
        goto LABEL_34;
    }
    else
    {
      if ( V1Struct )
        goto LABEL_34;
      v16 = (char *)v30;
      v17 = *((unsigned int *)v30 + 3);
      if ( (_DWORD)v17 )
      {
        v18 = 8 * v17;
        if ( v18 > 0xFFFFFFFF )
        {
          v23 = 534;
          ConnectionData = 534;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_34;
          v22 = 210;
          goto LABEL_20;
        }
        hMem = LocalAlloc(0x40u, (unsigned int)v18);
        v19 = (struct _EAPTLS_CERT_NODE **)hMem;
        if ( !hMem )
        {
          LastError = GetLastError();
          ConnectionData = LastError;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_34;
          v22 = 211;
          v23 = LastError;
LABEL_20:
          WPP_SF_d(*((_QWORD *)v21 + 2), v22, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v23);
          goto LABEL_34;
        }
        v16 = (char *)v30;
      }
      else
      {
        v19 = (struct _EAPTLS_CERT_NODE **)hMem;
      }
      CreateCertList(
        0,
        v13,
        1,
        (struct _EAPTLS_CERT_NODE **)&v27,
        v19,
        *((_DWORD *)v16 + 3),
        (struct _EAPTLS_HASH *)(v16 + 16),
        L"ROOT",
        &ConnectionData,
        0,
        0,
        0);
      if ( ConnectionData )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            212,
            &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
            ConnectionData);
        goto LABEL_34;
      }
      if ( v30 )
        isCertFilterLogicPresentInV1((struct _EAPTLS_CONN_PROPERTIES_V1 *)v30, &v33, &v32);
      v24 = DialogBoxParamW(g_hInstance, (LPCWSTR)0x3E8, a2, ConnDialogProc, (LPARAM)&dwInitParam);
      if ( v24 == -1 )
      {
        ConnectionData = GetLastError();
        goto LABEL_34;
      }
      if ( v24 != 1 )
      {
        ConnectionData = 1223;
        goto LABEL_34;
      }
    }
    ConnectionData = ConnPropGetV0Struct((struct _EAPTLS_CONN_PROPERTIES_V1 *)v30, v10);
    if ( !ConnectionData )
      *v11 = *((_DWORD *)*v10 + 1);
  }
LABEL_34:
  EapTlsInitialize2(0, 1);
  FreeTLSCertFilterDialog((struct _EAPTLS_CERT_FILTER_DIALOG *)v31);
  FreeCertList(v27);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  LocalFree(v29);
  LocalFree(v30);
  return ConnectionData;
}

```

## disassembly

```asm
0x180070bf8  mov     rax, rsp
0x180070bfb  mov     [rax+10h], rbx
0x180070bff  mov     [rax+18h], rsi
0x180070c03  mov     [rax+8], ecx
0x180070c06  push    rbp
0x180070c07  push    rdi
0x180070c08  push    r12
0x180070c0a  push    r14
0x180070c0c  push    r15
0x180070c0e  lea     rbp, [rax-138h]
0x180070c15  sub     rsp, 210h
0x180070c1c  mov     edi, r8d
0x180070c1f  mov     [rbp+130h+arg_0], 0
0x180070c29  mov     r12, rdx
0x180070c2c  lea     rcx, [rsp+230h+var_1D0]; void *
0x180070c31  mov     esi, 1B0h
0x180070c36  xor     edx, edx; Val
0x180070c38  mov     r8d, esi; Size
0x180070c3b  mov     r15, r9
0x180070c3e  call    memset_0
0x180070c43  mov     eax, 1
0x180070c48  mov     edx, eax; int
0x180070c4a  mov     ecx, eax; int
0x180070c4c  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180070c51  mov     rbx, [rbp+130h+arg_28]
0x180070c58  lea     rcx, [rsp+230h+var_1D0]; void *
0x180070c5d  mov     r14, [rbp+130h+arg_30]
0x180070c64  mov     r8d, esi; Size
0x180070c67  xor     edx, edx; Val
0x180070c69  mov     qword ptr [rbx], 0
0x180070c70  mov     dword ptr [r14], 0
0x180070c77  call    memset_0
0x180070c7c  mov     eax, dword ptr [rsp+230h+var_1D0]
0x180070c80  mov     ecx, 1
0x180070c85  mov     esi, edi
0x180070c87  mov     edx, 80000h
0x180070c8c  and     esi, ecx
0x180070c8e  cmovnz  eax, ecx
0x180070c91  mov     ecx, edi
0x180070c93  mov     dword ptr [rsp+230h+var_1D0], eax
0x180070c97  and     ecx, edx
0x180070c99  jz      short loc_180070CA3
0x180070c9b  mov     eax, esi
0x180070c9d  or      eax, edx
0x180070c9f  mov     dword ptr [rsp+230h+var_1D0], eax
0x180070ca3  mov     eax, esi
0x180070ca5  or      eax, edx
0x180070ca7  test    ecx, ecx
0x180070ca9  mov     ecx, 2000000h
0x180070cae  cmovz   eax, esi
0x180070cb1  test    ecx, edi
0x180070cb3  jz      short loc_180070CBB
0x180070cb5  or      eax, ecx
0x180070cb7  mov     dword ptr [rsp+230h+var_1D0], eax
0x180070cbb  mov     r8d, [rbp+130h+arg_20]; unsigned int
0x180070cc2  lea     r9, [rsp+230h+var_1B8]; struct _EAPTLS_CONN_PROPERTIES **
0x180070cc7  mov     rdx, r15; unsigned __int8 *
0x180070cca  mov     ecx, edi; unsigned int
0x180070ccc  call    ?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)
0x180070cd1  mov     [rbp+130h+arg_0], eax
0x180070cd7  test    eax, eax
0x180070cd9  jnz     loc_180070EED
0x180070cdf  mov     rcx, [rsp+230h+var_1B8]; struct _EAPTLS_CONN_PROPERTIES *
0x180070ce4  lea     rdx, [rbp+130h+var_1B0]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x180070ce8  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x180070ced  mov     [rbp+130h+arg_0], eax
0x180070cf3  test    dil, 2
0x180070cf7  jnz     loc_180070ECA
0x180070cfd  test    eax, eax
0x180070cff  jnz     loc_180070EED
0x180070d05  mov     rcx, [rbp+130h+var_1B0]
0x180070d09  mov     eax, [rcx+0Ch]
0x180070d0c  test    eax, eax
0x180070d0e  jz      loc_180070DB9
0x180070d14  shl     rax, 3
0x180070d18  mov     ecx, 0FFFFFFFFh
0x180070d1d  cmp     rax, rcx
0x180070d20  ja      short loc_180070D7B
0x180070d22  mov     edx, eax; uBytes
0x180070d24  mov     ecx, 40h ; '@'; uFlags
0x180070d29  call    cs:__imp_LocalAlloc
0x180070d30  nop     dword ptr [rax+rax+00h]
0x180070d35  mov     [rsp+230h+hMem], rax
0x180070d3a  mov     rdx, rax
0x180070d3d  test    rax, rax
0x180070d40  jnz     short loc_180070D75
0x180070d42  call    cs:__imp_GetLastError
0x180070d49  nop     dword ptr [rax+rax+00h]
0x180070d4e  mov     [rbp+130h+arg_0], eax
0x180070d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180070d5b  lea     rdx, WPP_GLOBAL_Control
0x180070d62  cmp     rcx, rdx
0x180070d65  jz      loc_180070EED
0x180070d6b  mov     edx, 0D3h
0x180070d70  mov     r9d, eax
0x180070d73  jmp     short loc_180070DA4
0x180070d75  mov     rcx, [rbp+130h+var_1B0]
0x180070d79  jmp     short loc_180070DBE
0x180070d7b  mov     r9d, 216h
0x180070d81  mov     [rbp+130h+arg_0], r9d
0x180070d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180070d8f  lea     rdx, WPP_GLOBAL_Control
0x180070d96  cmp     rcx, rdx
0x180070d99  jz      loc_180070EED
0x180070d9f  mov     edx, 0D2h
0x180070da4  mov     rcx, [rcx+10h]
0x180070da8  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180070daf  call    WPP_SF_d
0x180070db4  jmp     loc_180070EED
0x180070db9  mov     rdx, [rsp+230h+hMem]
0x180070dbe  mov     [rsp+230h+var_1D8], 0; unsigned int *
0x180070dc7  lea     rax, [rcx+10h]
0x180070dcb  mov     [rsp+230h+var_1E0], 0; struct _EAPTLS_FILTER_PROP *
0x180070dd4  lea     r8, [rbp+130h+arg_0]
0x180070ddb  mov     [rsp+230h+var_1E8], 0; int
0x180070de3  lea     r9, [rsp+230h+var_1C8]; struct _EAPTLS_CERT_NODE **
0x180070de8  mov     [rsp+230h+var_1F0], r8; unsigned int *
0x180070ded  lea     r8, aRoot; "ROOT"
0x180070df4  mov     [rsp+230h+var_1F8], r8; unsigned __int16 *
0x180070df9  mov     r8d, 1; int
0x180070dff  mov     [rsp+230h+var_200], rax; struct _EAPTLS_HASH *
0x180070e04  mov     eax, [rcx+0Ch]
0x180070e07  xor     ecx, ecx; int
0x180070e09  mov     [rsp+230h+var_208], eax; unsigned int
0x180070e0d  mov     [rsp+230h+dwInitParam], rdx; struct _EAPTLS_CERT_NODE **
0x180070e12  mov     edx, esi; int
0x180070e14  call    ?CreateCertList@@YAXHHHPEAPEAU_EAPTLS_CERT_NODE@@0KPEAU_EAPTLS_HASH@@PEBGPEAKHPEAU_EAPTLS_FILTER_PROP@@3@Z; CreateCertList(int,int,int,_EAPTLS_CERT_NODE * *,_EAPTLS_CERT_NODE * *,ulong,_EAPTLS_HASH *,ushort const *,ulong *,int,_EAPTLS_FILTER_PROP *,ulong *)
0x180070e19  mov     r9d, [rbp+130h+arg_0]
0x180070e20  test    r9d, r9d
0x180070e23  jz      short loc_180070E56
0x180070e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180070e2c  lea     rdx, WPP_GLOBAL_Control
0x180070e33  cmp     rcx, rdx
0x180070e36  jz      loc_180070EED
0x180070e3c  mov     rcx, [rcx+10h]
0x180070e40  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180070e47  mov     edx, 0D4h
0x180070e4c  call    WPP_SF_d
0x180070e51  jmp     loc_180070EED
0x180070e56  mov     rcx, [rbp+130h+var_1B0]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x180070e5a  test    rcx, rcx
0x180070e5d  jz      short loc_180070E72
0x180070e5f  lea     r8, [rbp+130h+var_A0]; unsigned int *
0x180070e66  lea     rdx, [rbp+130h+var_98]; unsigned __int8 **
0x180070e6d  call    ?isCertFilterLogicPresentInV1@@YAHPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAEPEAK@Z; isCertFilterLogicPresentInV1(_EAPTLS_CONN_PROPERTIES_V1 *,uchar * *,ulong *)
0x180070e72  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180070e79  lea     rax, [rsp+230h+var_1D0]
0x180070e7e  lea     r9, ?ConnDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180070e85  mov     [rsp+230h+dwInitParam], rax; dwInitParam
0x180070e8a  mov     r8, r12; hWndParent
0x180070e8d  mov     edx, 3E8h; lpTemplateName
0x180070e92  call    cs:__imp_DialogBoxParamW
0x180070e99  nop     dword ptr [rax+rax+00h]
0x180070e9e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180070ea2  jnz     short loc_180070EB8
0x180070ea4  call    cs:__imp_GetLastError
0x180070eab  nop     dword ptr [rax+rax+00h]
0x180070eb0  mov     [rbp+130h+arg_0], eax
0x180070eb6  jmp     short loc_180070EED
0x180070eb8  cmp     rax, 1
0x180070ebc  jz      short loc_180070ECE
0x180070ebe  mov     [rbp+130h+arg_0], 4C7h
0x180070ec8  jmp     short loc_180070EED
0x180070eca  test    eax, eax
0x180070ecc  jnz     short loc_180070EED
0x180070ece  mov     rcx, [rbp+130h+var_1B0]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x180070ed2  mov     rdx, rbx; struct _EAPTLS_CONN_PROPERTIES **
0x180070ed5  call    ?ConnPropGetV0Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; ConnPropGetV0Struct(_EAPTLS_CONN_PROPERTIES_V1 *,_EAPTLS_CONN_PROPERTIES * *)
0x180070eda  mov     [rbp+130h+arg_0], eax
0x180070ee0  test    eax, eax
0x180070ee2  jnz     short loc_180070EED
0x180070ee4  mov     rax, [rbx]
0x180070ee7  mov     ecx, [rax+4]
0x180070eea  mov     [r14], ecx
0x180070eed  mov     edx, 1; int
0x180070ef2  xor     ecx, ecx; int
0x180070ef4  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180070ef9  lea     rcx, [rbp+130h+var_1A8]; struct _EAPTLS_CERT_FILTER_DIALOG *
0x180070efd  call    ?FreeTLSCertFilterDialog@@YAXPEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z; FreeTLSCertFilterDialog(_EAPTLS_CERT_FILTER_DIALOG *)
0x180070f02  mov     rcx, [rsp+230h+var_1C8]; hMem
0x180070f07  call    ?FreeCertList@@YAXPEAU_EAPTLS_CERT_NODE@@@Z; FreeCertList(_EAPTLS_CERT_NODE *)
0x180070f0c  mov     rcx, [rsp+230h+hMem]; hMem
0x180070f11  test    rcx, rcx
0x180070f14  jz      short loc_180070F2B
0x180070f16  call    cs:__imp_LocalFree
0x180070f1d  nop     dword ptr [rax+rax+00h]
0x180070f22  mov     [rsp+230h+hMem], 0
0x180070f2b  mov     rcx, [rsp+230h+var_1B8]; hMem
0x180070f30  call    cs:__imp_LocalFree
0x180070f37  nop     dword ptr [rax+rax+00h]
0x180070f3c  mov     rcx, [rbp+130h+var_1B0]; hMem
0x180070f40  call    cs:__imp_LocalFree
0x180070f47  nop     dword ptr [rax+rax+00h]
0x180070f4c  mov     eax, [rbp+130h+arg_0]
0x180070f52  lea     r11, [rsp+230h+var_20]
0x180070f5a  mov     rbx, [r11+38h]
0x180070f5e  mov     rsi, [r11+40h]
0x180070f62  mov     rsp, r11
0x180070f65  pop     r15
0x180070f67  pop     r14
0x180070f69  pop     r12
0x180070f6b  pop     rdi
0x180070f6c  pop     rbp
0x180070f6d  retn
```
