# RasEapTlsInvokeConfigUI(ulong,HWND__ *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18006c46c`
- end: `0x18006c7b8`
- name: `?RasEapTlsInvokeConfigUI@@YAKKPEAUHWND__@@KPEAEKPEAPEAEPEAK@Z`
- size: `844`
- prototype: `unsigned int(unsigned int, HWND, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18005a020`

## callees

- `0x180004bd0`
- `0x180005ac0`
- `0x180007910`
- `0x180007c60`
- `0x18001dec0`
- `0x18001ea34`
- `0x180020624`
- `0x180033230`
- `0x180036254`
- `0x180069bac`
- `0x18006c46c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c5b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c5b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c706`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c59d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c59d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c786`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c790`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c786`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c790`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x18006c6fa`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x18006c6fa`

## pseudocode

```c
__int64 __fastcall RasEapTlsInvokeConfigUI(
        __int64 a1,
        HWND a2,
        int a3,
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
0x18006c46c  mov     rax, rsp
0x18006c46f  mov     [rax+10h], rbx
0x18006c473  mov     [rax+18h], rsi
0x18006c477  mov     [rax+8], ecx
0x18006c47a  push    rbp
0x18006c47b  push    rdi
0x18006c47c  push    r12
0x18006c47e  push    r14
0x18006c480  push    r15
0x18006c482  lea     rbp, [rax-138h]
0x18006c489  sub     rsp, 210h
0x18006c490  mov     edi, r8d
0x18006c493  mov     [rbp+130h+arg_0], 0
0x18006c49d  mov     r12, rdx
0x18006c4a0  lea     rcx, [rsp+230h+var_1D0]; void *
0x18006c4a5  mov     esi, 1B0h
0x18006c4aa  xor     edx, edx; Val
0x18006c4ac  mov     r8d, esi; Size
0x18006c4af  mov     r15, r9
0x18006c4b2  call    memset_0
0x18006c4b7  mov     eax, 1
0x18006c4bc  mov     edx, eax; int
0x18006c4be  mov     ecx, eax; int
0x18006c4c0  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x18006c4c5  mov     rbx, [rbp+130h+arg_28]
0x18006c4cc  lea     rcx, [rsp+230h+var_1D0]; void *
0x18006c4d1  mov     r14, [rbp+130h+arg_30]
0x18006c4d8  mov     r8d, esi; Size
0x18006c4db  xor     edx, edx; Val
0x18006c4dd  mov     qword ptr [rbx], 0
0x18006c4e4  mov     dword ptr [r14], 0
0x18006c4eb  call    memset_0
0x18006c4f0  mov     eax, dword ptr [rsp+230h+var_1D0]
0x18006c4f4  mov     ecx, 1
0x18006c4f9  mov     esi, edi
0x18006c4fb  mov     edx, 80000h
0x18006c500  and     esi, ecx
0x18006c502  cmovnz  eax, ecx
0x18006c505  mov     ecx, edi
0x18006c507  mov     dword ptr [rsp+230h+var_1D0], eax
0x18006c50b  and     ecx, edx
0x18006c50d  jz      short loc_18006C517
0x18006c50f  mov     eax, esi
0x18006c511  or      eax, edx
0x18006c513  mov     dword ptr [rsp+230h+var_1D0], eax
0x18006c517  mov     eax, esi
0x18006c519  or      eax, edx
0x18006c51b  test    ecx, ecx
0x18006c51d  mov     ecx, 2000000h
0x18006c522  cmovz   eax, esi
0x18006c525  test    ecx, edi
0x18006c527  jz      short loc_18006C52F
0x18006c529  or      eax, ecx
0x18006c52b  mov     dword ptr [rsp+230h+var_1D0], eax
0x18006c52f  mov     r8d, [rbp+130h+arg_20]; unsigned int
0x18006c536  lea     r9, [rsp+230h+var_1B8]; struct _EAPTLS_CONN_PROPERTIES **
0x18006c53b  mov     rdx, r15; unsigned __int8 *
0x18006c53e  mov     ecx, edi; unsigned int
0x18006c540  call    ?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)
0x18006c545  mov     [rbp+130h+arg_0], eax
0x18006c54b  test    eax, eax
0x18006c54d  jnz     loc_18006C749
0x18006c553  mov     rcx, [rsp+230h+var_1B8]; struct _EAPTLS_CONN_PROPERTIES *
0x18006c558  lea     rdx, [rbp+130h+var_1B0]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x18006c55c  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x18006c561  mov     [rbp+130h+arg_0], eax
0x18006c567  test    dil, 2
0x18006c56b  jnz     loc_18006C726
0x18006c571  test    eax, eax
0x18006c573  jnz     loc_18006C749
0x18006c579  mov     rcx, [rbp+130h+var_1B0]
0x18006c57d  mov     eax, [rcx+0Ch]
0x18006c580  test    eax, eax
0x18006c582  jz      loc_18006C621
0x18006c588  shl     rax, 3
0x18006c58c  mov     ecx, 0FFFFFFFFh
0x18006c591  cmp     rax, rcx
0x18006c594  ja      short loc_18006C5E3
0x18006c596  mov     edx, eax; uBytes
0x18006c598  mov     ecx, 40h ; '@'; uFlags
0x18006c59d  call    cs:__imp_LocalAlloc
0x18006c5a3  mov     [rsp+230h+hMem], rax
0x18006c5a8  mov     rdx, rax
0x18006c5ab  test    rax, rax
0x18006c5ae  jnz     short loc_18006C5DD
0x18006c5b0  call    cs:__imp_GetLastError
0x18006c5b6  mov     [rbp+130h+arg_0], eax
0x18006c5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c5c3  lea     rdx, WPP_GLOBAL_Control
0x18006c5ca  cmp     rcx, rdx
0x18006c5cd  jz      loc_18006C749
0x18006c5d3  mov     edx, 0D3h
0x18006c5d8  mov     r9d, eax
0x18006c5db  jmp     short loc_18006C60C
0x18006c5dd  mov     rcx, [rbp+130h+var_1B0]
0x18006c5e1  jmp     short loc_18006C626
0x18006c5e3  mov     r9d, 216h
0x18006c5e9  mov     [rbp+130h+arg_0], r9d
0x18006c5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c5f7  lea     rdx, WPP_GLOBAL_Control
0x18006c5fe  cmp     rcx, rdx
0x18006c601  jz      loc_18006C749
0x18006c607  mov     edx, 0D2h
0x18006c60c  mov     rcx, [rcx+10h]
0x18006c610  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006c617  call    WPP_SF_d
0x18006c61c  jmp     loc_18006C749
0x18006c621  mov     rdx, [rsp+230h+hMem]
0x18006c626  mov     [rsp+230h+var_1D8], 0; unsigned int *
0x18006c62f  lea     rax, [rcx+10h]
0x18006c633  mov     [rsp+230h+var_1E0], 0; struct _EAPTLS_FILTER_PROP *
0x18006c63c  lea     r8, [rbp+130h+arg_0]
0x18006c643  mov     [rsp+230h+var_1E8], 0; int
0x18006c64b  lea     r9, [rsp+230h+var_1C8]; struct _EAPTLS_CERT_NODE **
0x18006c650  mov     [rsp+230h+var_1F0], r8; unsigned int *
0x18006c655  lea     r8, aRoot; "ROOT"
0x18006c65c  mov     [rsp+230h+var_1F8], r8; unsigned __int16 *
0x18006c661  mov     r8d, 1; int
0x18006c667  mov     [rsp+230h+var_200], rax; struct _EAPTLS_HASH *
0x18006c66c  mov     eax, [rcx+0Ch]
0x18006c66f  xor     ecx, ecx; int
0x18006c671  mov     [rsp+230h+var_208], eax; unsigned int
0x18006c675  mov     [rsp+230h+dwInitParam], rdx; struct _EAPTLS_CERT_NODE **
0x18006c67a  mov     edx, esi; int
0x18006c67c  call    ?CreateCertList@@YAXHHHPEAPEAU_EAPTLS_CERT_NODE@@0KPEAU_EAPTLS_HASH@@PEBGPEAKHPEAU_EAPTLS_FILTER_PROP@@3@Z; CreateCertList(int,int,int,_EAPTLS_CERT_NODE * *,_EAPTLS_CERT_NODE * *,ulong,_EAPTLS_HASH *,ushort const *,ulong *,int,_EAPTLS_FILTER_PROP *,ulong *)
0x18006c681  mov     r9d, [rbp+130h+arg_0]
0x18006c688  test    r9d, r9d
0x18006c68b  jz      short loc_18006C6BE
0x18006c68d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c694  lea     rdx, WPP_GLOBAL_Control
0x18006c69b  cmp     rcx, rdx
0x18006c69e  jz      loc_18006C749
0x18006c6a4  mov     rcx, [rcx+10h]
0x18006c6a8  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006c6af  mov     edx, 0D4h
0x18006c6b4  call    WPP_SF_d
0x18006c6b9  jmp     loc_18006C749
0x18006c6be  mov     rcx, [rbp+130h+var_1B0]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18006c6c2  test    rcx, rcx
0x18006c6c5  jz      short loc_18006C6DA
0x18006c6c7  lea     r8, [rbp+130h+var_A0]; unsigned int *
0x18006c6ce  lea     rdx, [rbp+130h+var_98]; unsigned __int8 **
0x18006c6d5  call    ?isCertFilterLogicPresentInV1@@YAHPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAEPEAK@Z; isCertFilterLogicPresentInV1(_EAPTLS_CONN_PROPERTIES_V1 *,uchar * *,ulong *)
0x18006c6da  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006c6e1  lea     rax, [rsp+230h+var_1D0]
0x18006c6e6  lea     r9, ?ConnDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18006c6ed  mov     [rsp+230h+dwInitParam], rax; dwInitParam
0x18006c6f2  mov     r8, r12; hWndParent
0x18006c6f5  mov     edx, 3E8h; lpTemplateName
0x18006c6fa  call    cs:__imp_DialogBoxParamW
0x18006c700  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006c704  jnz     short loc_18006C714
0x18006c706  call    cs:__imp_GetLastError
0x18006c70c  mov     [rbp+130h+arg_0], eax
0x18006c712  jmp     short loc_18006C749
0x18006c714  cmp     rax, 1
0x18006c718  jz      short loc_18006C72A
0x18006c71a  mov     [rbp+130h+arg_0], 4C7h
0x18006c724  jmp     short loc_18006C749
0x18006c726  test    eax, eax
0x18006c728  jnz     short loc_18006C749
0x18006c72a  mov     rcx, [rbp+130h+var_1B0]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18006c72e  mov     rdx, rbx; struct _EAPTLS_CONN_PROPERTIES **
0x18006c731  call    ?ConnPropGetV0Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; ConnPropGetV0Struct(_EAPTLS_CONN_PROPERTIES_V1 *,_EAPTLS_CONN_PROPERTIES * *)
0x18006c736  mov     [rbp+130h+arg_0], eax
0x18006c73c  test    eax, eax
0x18006c73e  jnz     short loc_18006C749
0x18006c740  mov     rax, [rbx]
0x18006c743  mov     ecx, [rax+4]
0x18006c746  mov     [r14], ecx
0x18006c749  mov     edx, 1; int
0x18006c74e  xor     ecx, ecx; int
0x18006c750  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x18006c755  lea     rcx, [rbp+130h+var_1A8]; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006c759  call    ?FreeTLSCertFilterDialog@@YAXPEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z; FreeTLSCertFilterDialog(_EAPTLS_CERT_FILTER_DIALOG *)
0x18006c75e  mov     rcx, [rsp+230h+var_1C8]; hMem
0x18006c763  call    ?FreeCertList@@YAXPEAU_EAPTLS_CERT_NODE@@@Z; FreeCertList(_EAPTLS_CERT_NODE *)
0x18006c768  mov     rcx, [rsp+230h+hMem]; hMem
0x18006c76d  test    rcx, rcx
0x18006c770  jz      short loc_18006C781
0x18006c772  call    cs:__imp_LocalFree
0x18006c778  mov     [rsp+230h+hMem], 0
0x18006c781  mov     rcx, [rsp+230h+var_1B8]; hMem
0x18006c786  call    cs:__imp_LocalFree
0x18006c78c  mov     rcx, [rbp+130h+var_1B0]; hMem
0x18006c790  call    cs:__imp_LocalFree
0x18006c796  mov     eax, [rbp+130h+arg_0]
0x18006c79c  lea     r11, [rsp+230h+var_20]
0x18006c7a4  mov     rbx, [r11+38h]
0x18006c7a8  mov     rsi, [r11+40h]
0x18006c7ac  mov     rsp, r11
0x18006c7af  pop     r15
0x18006c7b1  pop     r14
0x18006c7b3  pop     r12
0x18006c7b5  pop     rdi
0x18006c7b6  pop     rbp
0x18006c7b7  retn
```
