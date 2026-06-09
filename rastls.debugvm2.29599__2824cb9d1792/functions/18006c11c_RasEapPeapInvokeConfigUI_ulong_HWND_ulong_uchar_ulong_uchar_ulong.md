# RasEapPeapInvokeConfigUI(ulong,HWND__ *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18006c11c`
- end: `0x18006c464`
- name: `?RasEapPeapInvokeConfigUI@@YAKKPEAUHWND__@@KPEAEKPEAPEAEPEAK@Z`
- size: `840`
- prototype: `unsigned int(unsigned int, HWND, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18005a020`

## callees

- `0x180003000`
- `0x1800030d0`
- `0x180004bd0`
- `0x180005ac0`
- `0x1800060f0`
- `0x1800075b0`
- `0x18001f020`
- `0x180020624`
- `0x180033230`
- `0x180036254`
- `0x18006c11c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c3e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c206`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c206`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c42f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c42f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c447`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x18006c3d8`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x18006c3d8`

## pseudocode

```c
__int64 __fastcall RasEapPeapInvokeConfigUI(
        __int64 a1,
        HWND a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned __int8 **v10; // r14
  unsigned int *v11; // r15
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  char *v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  struct _EAPTLS_CERT_NODE **v18; // rdx
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rdx
  const unsigned __int16 *v24; // rcx
  __int64 *v25; // r10
  unsigned __int8 **v26; // rcx
  INT_PTR v27; // rax
  _DWORD *v28; // rax
  LPARAM dwInitParam; // [rsp+60h] [rbp-91h] BYREF
  HLOCAL v31; // [rsp+68h] [rbp-89h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-81h]
  HLOCAL v33; // [rsp+78h] [rbp-79h] BYREF
  HLOCAL v34; // [rsp+80h] [rbp-71h] BYREF
  unsigned int ConnectionData; // [rsp+140h] [rbp+4Fh] BYREF

  ConnectionData = 0;
  memset_0(&dwInitParam, 0, 0x90u);
  EapTlsInitialize2(1, 1);
  v10 = a6;
  v11 = a7;
  *a6 = 0;
  *v11 = 0;
  memset_0(&dwInitParam, 0, 0x90u);
  v12 = dwInitParam;
  v13 = a3 & 1;
  if ( (a3 & 1) != 0 )
    v12 = 1;
  LODWORD(dwInitParam) = v12;
  if ( (a3 & 0x80) != 0 )
    LODWORD(dwInitParam) = v13 | 2;
  v14 = v13 | 2;
  if ( (a3 & 0x80) == 0 )
    v14 = a3 & 1;
  if ( (a3 & 0x2000000) != 0 )
    LODWORD(dwInitParam) = v14 | 0x2000000;
  ConnectionData = PeapReadConnectionData(a3, a4, a5, (BYTE **)&v33);
  if ( !ConnectionData )
  {
    v15 = (char *)v33;
    v16 = *((unsigned int *)v33 + 7);
    if ( (_DWORD)v16 )
    {
      v17 = 8 * v16;
      if ( v17 > 0xFFFFFFFF )
      {
        v22 = 534;
        ConnectionData = 534;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_39;
        v21 = 225;
        goto LABEL_18;
      }
      hMem = LocalAlloc(0x40u, (unsigned int)v17);
      v18 = (struct _EAPTLS_CERT_NODE **)hMem;
      if ( !hMem )
      {
        LastError = GetLastError();
        ConnectionData = LastError;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_39;
        v21 = 226;
        v22 = LastError;
LABEL_18:
        WPP_SF_d(*((_QWORD *)v20 + 2), v21, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v22);
        goto LABEL_39;
      }
      v15 = (char *)v33;
    }
    else
    {
      v18 = (struct _EAPTLS_CERT_NODE **)hMem;
    }
    CreateCertList(
      0,
      v13,
      1,
      (struct _EAPTLS_CERT_NODE **)&v31,
      v18,
      *((_DWORD *)v15 + 7),
      (struct _EAPTLS_HASH *)(v15 + 32),
      L"ROOT",
      &ConnectionData,
      1,
      0,
      0);
    if ( ConnectionData )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          227,
          &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
          ConnectionData);
    }
    else
    {
      ConnectionData = PeapEapInfoGetList(v24, v23, (struct _PEAP_EAP_INFO **)&v34);
      if ( ConnectionData )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      }
      else
      {
        a6 = 0;
        if ( *((_DWORD *)v33 + 2) )
        {
          PeapGetFirstEntryConnProp((struct _PEAP_CONN_PROPERTIES *)v33, (struct _PEAP_ENTRY_CONN_PROPERTIES **)&a6);
          v26 = a6;
          while ( v25 )
          {
            if ( *((_DWORD *)v25 + 2) == *((_DWORD *)a6 + 2) )
            {
              if ( *((_DWORD *)a6 + 1) <= 0x10u )
              {
                v25[17] = 0;
                *((_DWORD *)v25 + 36) = 0;
              }
              else
              {
                v25[17] = (__int64)a6 + 12;
                *((_DWORD *)v25 + 36) = *((_DWORD *)v26 + 1) - 15;
              }
              break;
            }
            v25 = (__int64 *)*v25;
          }
        }
        ConnectionData = 0;
        v27 = DialogBoxParamW(g_hInstance, (LPCWSTR)0x3EC, a2, PeapConnDialogProc, (LPARAM)&dwInitParam);
        if ( v27 == -1 )
        {
          ConnectionData = GetLastError();
        }
        else if ( v27 == 1 )
        {
          v28 = v33;
          *v10 = (unsigned __int8 *)v33;
          *v11 = v28[1];
          v33 = 0;
        }
        else
        {
          ConnectionData = 1223;
        }
      }
    }
  }
LABEL_39:
  EapTlsInitialize2(0, 1);
  FreeCertList(v31);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  PeapEapInfoFreeList(v34);
  LocalFree(v33);
  return ConnectionData;
}

```

## disassembly

```asm
0x18006c11c  mov     [rsp-8+arg_0], ecx
0x18006c120  push    rbp
0x18006c121  push    rbx
0x18006c122  push    rsi
0x18006c123  push    rdi
0x18006c124  push    r12
0x18006c126  push    r13
0x18006c128  push    r14
0x18006c12a  push    r15
0x18006c12c  lea     rbp, [rsp-7]
0x18006c131  sub     rsp, 0F8h
0x18006c138  mov     edi, r8d
0x18006c13b  lea     rcx, [rsp+130h+var_D0]; void *
0x18006c140  mov     r12, rdx
0x18006c143  mov     ebx, 90h
0x18006c148  xor     r13d, r13d
0x18006c14b  mov     r8d, ebx; Size
0x18006c14e  xor     edx, edx; Val
0x18006c150  mov     [rbp+3Fh+arg_0], r13d
0x18006c154  mov     rsi, r9
0x18006c157  call    memset_0
0x18006c15c  lea     eax, [r13+1]
0x18006c160  mov     edx, eax; int
0x18006c162  mov     ecx, eax; int
0x18006c164  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x18006c169  mov     r14, [rbp+3Fh+arg_28]
0x18006c16d  lea     rcx, [rsp+130h+var_D0]; void *
0x18006c172  mov     r15, [rbp+3Fh+arg_30]
0x18006c176  mov     r8d, ebx; Size
0x18006c179  xor     edx, edx; Val
0x18006c17b  mov     [r14], r13
0x18006c17e  mov     [r15], r13d
0x18006c181  call    memset_0
0x18006c186  mov     eax, dword ptr [rsp+130h+var_D0]
0x18006c18a  lea     ecx, [r13+1]
0x18006c18e  mov     ebx, edi
0x18006c190  and     ebx, ecx
0x18006c192  cmovnz  eax, ecx
0x18006c195  mov     ecx, edi
0x18006c197  mov     dword ptr [rsp+130h+var_D0], eax
0x18006c19b  and     ecx, 80h
0x18006c1a1  jz      short loc_18006C1AC
0x18006c1a3  mov     eax, ebx
0x18006c1a5  or      eax, 2
0x18006c1a8  mov     dword ptr [rsp+130h+var_D0], eax
0x18006c1ac  mov     eax, ebx
0x18006c1ae  or      eax, 2
0x18006c1b1  test    ecx, ecx
0x18006c1b3  mov     ecx, 2000000h
0x18006c1b8  cmovz   eax, ebx
0x18006c1bb  test    ecx, edi
0x18006c1bd  jz      short loc_18006C1C5
0x18006c1bf  or      eax, ecx
0x18006c1c1  mov     dword ptr [rsp+130h+var_D0], eax
0x18006c1c5  mov     r8d, [rbp+3Fh+arg_20]; unsigned int
0x18006c1c9  lea     r9, [rbp+3Fh+var_B8]; struct _PEAP_CONN_PROPERTIES **
0x18006c1cd  mov     rdx, rsi; unsigned __int8 *
0x18006c1d0  mov     ecx, edi; unsigned int
0x18006c1d2  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x18006c1d7  mov     [rbp+3Fh+arg_0], eax
0x18006c1da  test    eax, eax
0x18006c1dc  jnz     loc_18006C40F
0x18006c1e2  mov     rcx, [rbp+3Fh+var_B8]
0x18006c1e6  mov     eax, [rcx+1Ch]
0x18006c1e9  test    eax, eax
0x18006c1eb  jz      loc_18006C284
0x18006c1f1  shl     rax, 3
0x18006c1f5  mov     ecx, 0FFFFFFFFh
0x18006c1fa  cmp     rax, rcx
0x18006c1fd  ja      short loc_18006C249
0x18006c1ff  mov     edx, eax; uBytes
0x18006c201  mov     ecx, 40h ; '@'; uFlags
0x18006c206  call    cs:__imp_LocalAlloc
0x18006c20c  mov     [rsp+130h+hMem], rax
0x18006c211  mov     rdx, rax
0x18006c214  test    rax, rax
0x18006c217  jnz     short loc_18006C243
0x18006c219  call    cs:__imp_GetLastError
0x18006c21f  mov     [rbp+3Fh+arg_0], eax
0x18006c222  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c229  lea     rdx, WPP_GLOBAL_Control
0x18006c230  cmp     rcx, rdx
0x18006c233  jz      loc_18006C40F
0x18006c239  mov     edx, 0E2h
0x18006c23e  mov     r9d, eax
0x18006c241  jmp     short loc_18006C26F
0x18006c243  mov     rcx, [rbp+3Fh+var_B8]
0x18006c247  jmp     short loc_18006C289
0x18006c249  mov     r9d, 216h
0x18006c24f  mov     [rbp+3Fh+arg_0], r9d
0x18006c253  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c25a  lea     rdx, WPP_GLOBAL_Control
0x18006c261  cmp     rcx, rdx
0x18006c264  jz      loc_18006C40F
0x18006c26a  mov     edx, 0E1h
0x18006c26f  mov     rcx, [rcx+10h]
0x18006c273  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006c27a  call    WPP_SF_d
0x18006c27f  jmp     loc_18006C40F
0x18006c284  mov     rdx, [rsp+130h+hMem]
0x18006c289  mov     [rsp+130h+var_D8], r13; unsigned int *
0x18006c28e  lea     rax, [rcx+20h]
0x18006c292  mov     [rsp+130h+var_E0], r13; struct _EAPTLS_FILTER_PROP *
0x18006c297  lea     r8, [rbp+3Fh+arg_0]
0x18006c29b  mov     [rsp+130h+var_E8], 1; int
0x18006c2a3  lea     r9, [rsp+130h+var_C8]; struct _EAPTLS_CERT_NODE **
0x18006c2a8  mov     [rsp+130h+var_F0], r8; unsigned int *
0x18006c2ad  lea     r8, aRoot; "ROOT"
0x18006c2b4  mov     [rsp+130h+var_F8], r8; unsigned __int16 *
0x18006c2b9  mov     r8d, 1; int
0x18006c2bf  mov     [rsp+130h+var_100], rax; struct _EAPTLS_HASH *
0x18006c2c4  mov     eax, [rcx+1Ch]
0x18006c2c7  xor     ecx, ecx; int
0x18006c2c9  mov     [rsp+130h+var_108], eax; unsigned int
0x18006c2cd  mov     [rsp+130h+dwInitParam], rdx; struct _EAPTLS_CERT_NODE **
0x18006c2d2  mov     edx, ebx; int
0x18006c2d4  call    ?CreateCertList@@YAXHHHPEAPEAU_EAPTLS_CERT_NODE@@0KPEAU_EAPTLS_HASH@@PEBGPEAKHPEAU_EAPTLS_FILTER_PROP@@3@Z; CreateCertList(int,int,int,_EAPTLS_CERT_NODE * *,_EAPTLS_CERT_NODE * *,ulong,_EAPTLS_HASH *,ushort const *,ulong *,int,_EAPTLS_FILTER_PROP *,ulong *)
0x18006c2d9  mov     r9d, [rbp+3Fh+arg_0]
0x18006c2dd  test    r9d, r9d
0x18006c2e0  jz      short loc_18006C313
0x18006c2e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c2e9  lea     rdx, WPP_GLOBAL_Control
0x18006c2f0  cmp     rcx, rdx
0x18006c2f3  jz      loc_18006C40F
0x18006c2f9  mov     rcx, [rcx+10h]
0x18006c2fd  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006c304  mov     edx, 0E3h
0x18006c309  call    WPP_SF_d
0x18006c30e  jmp     loc_18006C40F
0x18006c313  lea     r8, [rbp+3Fh+var_B0]; struct _PEAP_EAP_INFO **
0x18006c317  call    ?PeapEapInfoGetList@@YAKPEBGHPEAPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoGetList(ushort const *,int,_PEAP_EAP_INFO * *)
0x18006c31c  mov     [rbp+3Fh+arg_0], eax
0x18006c31f  test    eax, eax
0x18006c321  jz      short loc_18006C354
0x18006c323  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c32a  lea     rdx, WPP_GLOBAL_Control
0x18006c331  cmp     rcx, rdx
0x18006c334  jz      loc_18006C40F
0x18006c33a  mov     rcx, [rcx+10h]
0x18006c33e  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006c345  mov     edx, 0E4h
0x18006c34a  call    WPP_SF_
0x18006c34f  jmp     loc_18006C40F
0x18006c354  mov     rcx, [rbp+3Fh+var_B8]; struct _PEAP_CONN_PROPERTIES *
0x18006c358  mov     [rbp+3Fh+arg_28], r13
0x18006c35c  cmp     [rcx+8], r13d
0x18006c360  jz      short loc_18006C3B4
0x18006c362  mov     r10, [rbp+3Fh+var_B0]
0x18006c366  lea     rdx, [rbp+3Fh+arg_28]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x18006c36a  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x18006c36f  mov     rcx, [rbp+3Fh+arg_28]
0x18006c373  test    r10, r10
0x18006c376  jz      short loc_18006C3B4
0x18006c378  mov     eax, [rcx+8]
0x18006c37b  cmp     [r10+8], eax
0x18006c37f  jz      short loc_18006C386
0x18006c381  mov     r10, [r10]
0x18006c384  jmp     short loc_18006C373
0x18006c386  cmp     dword ptr [rcx+4], 10h
0x18006c38a  jbe     short loc_18006C3A6
0x18006c38c  lea     rax, [rcx+0Ch]
0x18006c390  mov     [r10+88h], rax
0x18006c397  mov     eax, [rcx+4]
0x18006c39a  sub     eax, 0Fh
0x18006c39d  mov     [r10+90h], eax
0x18006c3a4  jmp     short loc_18006C3B4
0x18006c3a6  mov     [r10+88h], r13
0x18006c3ad  mov     [r10+90h], r13d
0x18006c3b4  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006c3bb  lea     rax, [rsp+130h+var_D0]
0x18006c3c0  lea     r9, ?PeapConnDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18006c3c7  mov     [rsp+130h+dwInitParam], rax; dwInitParam
0x18006c3cc  mov     r8, r12; hWndParent
0x18006c3cf  mov     [rbp+3Fh+arg_0], r13d
0x18006c3d3  mov     edx, 3ECh; lpTemplateName
0x18006c3d8  call    cs:__imp_DialogBoxParamW
0x18006c3de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006c3e2  jnz     short loc_18006C3EF
0x18006c3e4  call    cs:__imp_GetLastError
0x18006c3ea  mov     [rbp+3Fh+arg_0], eax
0x18006c3ed  jmp     short loc_18006C40F
0x18006c3ef  cmp     rax, 1
0x18006c3f3  jz      short loc_18006C3FE
0x18006c3f5  mov     [rbp+3Fh+arg_0], 4C7h
0x18006c3fc  jmp     short loc_18006C40F
0x18006c3fe  mov     rax, [rbp+3Fh+var_B8]
0x18006c402  mov     [r14], rax
0x18006c405  mov     eax, [rax+4]
0x18006c408  mov     [r15], eax
0x18006c40b  mov     [rbp+3Fh+var_B8], r13
0x18006c40f  mov     edx, 1; int
0x18006c414  xor     ecx, ecx; int
0x18006c416  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x18006c41b  mov     rcx, [rsp+130h+var_C8]; hMem
0x18006c420  call    ?FreeCertList@@YAXPEAU_EAPTLS_CERT_NODE@@@Z; FreeCertList(_EAPTLS_CERT_NODE *)
0x18006c425  mov     rcx, [rsp+130h+hMem]; hMem
0x18006c42a  test    rcx, rcx
0x18006c42d  jz      short loc_18006C43A
0x18006c42f  call    cs:__imp_LocalFree
0x18006c435  mov     [rsp+130h+hMem], r13
0x18006c43a  mov     rcx, [rbp+3Fh+var_B0]; hMem
0x18006c43e  call    ?PeapEapInfoFreeList@@YAXPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoFreeList(_PEAP_EAP_INFO *)
0x18006c443  mov     rcx, [rbp+3Fh+var_B8]; hMem
0x18006c447  call    cs:__imp_LocalFree
0x18006c44d  mov     eax, [rbp+3Fh+arg_0]
0x18006c450  add     rsp, 0F8h
0x18006c457  pop     r15
0x18006c459  pop     r14
0x18006c45b  pop     r13
0x18006c45d  pop     r12
0x18006c45f  pop     rdi
0x18006c460  pop     rsi
0x18006c461  pop     rbx
0x18006c462  pop     rbp
0x18006c463  retn
```
