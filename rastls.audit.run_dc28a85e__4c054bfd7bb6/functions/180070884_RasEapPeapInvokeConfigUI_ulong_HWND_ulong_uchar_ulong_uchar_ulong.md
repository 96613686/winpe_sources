# RasEapPeapInvokeConfigUI(ulong,HWND__ *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180070884`
- end: `0x180070bf1`
- name: `?RasEapPeapInvokeConfigUI@@YAKKPEAUHWND__@@KPEAEKPEAPEAEPEAK@Z`
- size: `877`
- prototype: `unsigned int(unsigned int, HWND, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18005d3c0`

## callees

- `0x180003118`
- `0x180003240`
- `0x180005010`
- `0x180005f80`
- `0x180006620`
- `0x180007d00`
- `0x180020d80`
- `0x180022680`
- `0x180035b28`
- `0x180038e64`
- `0x180070884`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070b5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007096e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007096e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070baf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070bcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070baf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070bcd`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x180070b4c`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x180070b4c`

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
0x180070884  mov     [rsp-8+arg_0], ecx
0x180070888  push    rbp
0x180070889  push    rbx
0x18007088a  push    rsi
0x18007088b  push    rdi
0x18007088c  push    r12
0x18007088e  push    r13
0x180070890  push    r14
0x180070892  push    r15
0x180070894  lea     rbp, [rsp-7]
0x180070899  sub     rsp, 0F8h
0x1800708a0  mov     edi, r8d
0x1800708a3  lea     rcx, [rsp+130h+var_D0]; void *
0x1800708a8  mov     r12, rdx
0x1800708ab  mov     ebx, 90h
0x1800708b0  xor     r13d, r13d
0x1800708b3  mov     r8d, ebx; Size
0x1800708b6  xor     edx, edx; Val
0x1800708b8  mov     [rbp+3Fh+arg_0], r13d
0x1800708bc  mov     rsi, r9
0x1800708bf  call    memset_0
0x1800708c4  lea     eax, [r13+1]
0x1800708c8  mov     edx, eax; int
0x1800708ca  mov     ecx, eax; int
0x1800708cc  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x1800708d1  mov     r14, [rbp+3Fh+arg_28]
0x1800708d5  lea     rcx, [rsp+130h+var_D0]; void *
0x1800708da  mov     r15, [rbp+3Fh+arg_30]
0x1800708de  mov     r8d, ebx; Size
0x1800708e1  xor     edx, edx; Val
0x1800708e3  mov     [r14], r13
0x1800708e6  mov     [r15], r13d
0x1800708e9  call    memset_0
0x1800708ee  mov     eax, dword ptr [rsp+130h+var_D0]
0x1800708f2  lea     ecx, [r13+1]
0x1800708f6  mov     ebx, edi
0x1800708f8  and     ebx, ecx
0x1800708fa  cmovnz  eax, ecx
0x1800708fd  mov     ecx, edi
0x1800708ff  mov     dword ptr [rsp+130h+var_D0], eax
0x180070903  and     ecx, 80h
0x180070909  jz      short loc_180070914
0x18007090b  mov     eax, ebx
0x18007090d  or      eax, 2
0x180070910  mov     dword ptr [rsp+130h+var_D0], eax
0x180070914  mov     eax, ebx
0x180070916  or      eax, 2
0x180070919  test    ecx, ecx
0x18007091b  mov     ecx, 2000000h
0x180070920  cmovz   eax, ebx
0x180070923  test    ecx, edi
0x180070925  jz      short loc_18007092D
0x180070927  or      eax, ecx
0x180070929  mov     dword ptr [rsp+130h+var_D0], eax
0x18007092d  mov     r8d, [rbp+3Fh+arg_20]; unsigned int
0x180070931  lea     r9, [rbp+3Fh+var_B8]; struct _PEAP_CONN_PROPERTIES **
0x180070935  mov     rdx, rsi; unsigned __int8 *
0x180070938  mov     ecx, edi; unsigned int
0x18007093a  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x18007093f  mov     [rbp+3Fh+arg_0], eax
0x180070942  test    eax, eax
0x180070944  jnz     loc_180070B8F
0x18007094a  mov     rcx, [rbp+3Fh+var_B8]
0x18007094e  mov     eax, [rcx+1Ch]
0x180070951  test    eax, eax
0x180070953  jz      loc_1800709F8
0x180070959  shl     rax, 3
0x18007095d  mov     ecx, 0FFFFFFFFh
0x180070962  cmp     rax, rcx
0x180070965  ja      short loc_1800709BD
0x180070967  mov     edx, eax; uBytes
0x180070969  mov     ecx, 40h ; '@'; uFlags
0x18007096e  call    cs:__imp_LocalAlloc
0x180070975  nop     dword ptr [rax+rax+00h]
0x18007097a  mov     [rsp+130h+hMem], rax
0x18007097f  mov     rdx, rax
0x180070982  test    rax, rax
0x180070985  jnz     short loc_1800709B7
0x180070987  call    cs:__imp_GetLastError
0x18007098e  nop     dword ptr [rax+rax+00h]
0x180070993  mov     [rbp+3Fh+arg_0], eax
0x180070996  mov     rcx, cs:WPP_GLOBAL_Control
0x18007099d  lea     rdx, WPP_GLOBAL_Control
0x1800709a4  cmp     rcx, rdx
0x1800709a7  jz      loc_180070B8F
0x1800709ad  mov     edx, 0E2h
0x1800709b2  mov     r9d, eax
0x1800709b5  jmp     short loc_1800709E3
0x1800709b7  mov     rcx, [rbp+3Fh+var_B8]
0x1800709bb  jmp     short loc_1800709FD
0x1800709bd  mov     r9d, 216h
0x1800709c3  mov     [rbp+3Fh+arg_0], r9d
0x1800709c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800709ce  lea     rdx, WPP_GLOBAL_Control
0x1800709d5  cmp     rcx, rdx
0x1800709d8  jz      loc_180070B8F
0x1800709de  mov     edx, 0E1h
0x1800709e3  mov     rcx, [rcx+10h]
0x1800709e7  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800709ee  call    WPP_SF_d
0x1800709f3  jmp     loc_180070B8F
0x1800709f8  mov     rdx, [rsp+130h+hMem]
0x1800709fd  mov     [rsp+130h+var_D8], r13; unsigned int *
0x180070a02  lea     rax, [rcx+20h]
0x180070a06  mov     [rsp+130h+var_E0], r13; struct _EAPTLS_FILTER_PROP *
0x180070a0b  lea     r8, [rbp+3Fh+arg_0]
0x180070a0f  mov     [rsp+130h+var_E8], 1; int
0x180070a17  lea     r9, [rsp+130h+var_C8]; struct _EAPTLS_CERT_NODE **
0x180070a1c  mov     [rsp+130h+var_F0], r8; unsigned int *
0x180070a21  lea     r8, aRoot; "ROOT"
0x180070a28  mov     [rsp+130h+var_F8], r8; unsigned __int16 *
0x180070a2d  mov     r8d, 1; int
0x180070a33  mov     [rsp+130h+var_100], rax; struct _EAPTLS_HASH *
0x180070a38  mov     eax, [rcx+1Ch]
0x180070a3b  xor     ecx, ecx; int
0x180070a3d  mov     [rsp+130h+var_108], eax; unsigned int
0x180070a41  mov     [rsp+130h+dwInitParam], rdx; struct _EAPTLS_CERT_NODE **
0x180070a46  mov     edx, ebx; int
0x180070a48  call    ?CreateCertList@@YAXHHHPEAPEAU_EAPTLS_CERT_NODE@@0KPEAU_EAPTLS_HASH@@PEBGPEAKHPEAU_EAPTLS_FILTER_PROP@@3@Z; CreateCertList(int,int,int,_EAPTLS_CERT_NODE * *,_EAPTLS_CERT_NODE * *,ulong,_EAPTLS_HASH *,ushort const *,ulong *,int,_EAPTLS_FILTER_PROP *,ulong *)
0x180070a4d  mov     r9d, [rbp+3Fh+arg_0]
0x180070a51  test    r9d, r9d
0x180070a54  jz      short loc_180070A87
0x180070a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a5d  lea     rdx, WPP_GLOBAL_Control
0x180070a64  cmp     rcx, rdx
0x180070a67  jz      loc_180070B8F
0x180070a6d  mov     rcx, [rcx+10h]
0x180070a71  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180070a78  mov     edx, 0E3h
0x180070a7d  call    WPP_SF_d
0x180070a82  jmp     loc_180070B8F
0x180070a87  lea     r8, [rbp+3Fh+var_B0]; struct _PEAP_EAP_INFO **
0x180070a8b  call    ?PeapEapInfoGetList@@YAKPEBGHPEAPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoGetList(ushort const *,int,_PEAP_EAP_INFO * *)
0x180070a90  mov     [rbp+3Fh+arg_0], eax
0x180070a93  test    eax, eax
0x180070a95  jz      short loc_180070AC8
0x180070a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a9e  lea     rdx, WPP_GLOBAL_Control
0x180070aa5  cmp     rcx, rdx
0x180070aa8  jz      loc_180070B8F
0x180070aae  mov     rcx, [rcx+10h]
0x180070ab2  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180070ab9  mov     edx, 0E4h
0x180070abe  call    WPP_SF_
0x180070ac3  jmp     loc_180070B8F
0x180070ac8  mov     rcx, [rbp+3Fh+var_B8]; struct _PEAP_CONN_PROPERTIES *
0x180070acc  mov     [rbp+3Fh+arg_28], r13
0x180070ad0  cmp     [rcx+8], r13d
0x180070ad4  jz      short loc_180070B28
0x180070ad6  mov     r10, [rbp+3Fh+var_B0]
0x180070ada  lea     rdx, [rbp+3Fh+arg_28]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x180070ade  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x180070ae3  mov     rcx, [rbp+3Fh+arg_28]
0x180070ae7  test    r10, r10
0x180070aea  jz      short loc_180070B28
0x180070aec  mov     eax, [rcx+8]
0x180070aef  cmp     [r10+8], eax
0x180070af3  jz      short loc_180070AFA
0x180070af5  mov     r10, [r10]
0x180070af8  jmp     short loc_180070AE7
0x180070afa  cmp     dword ptr [rcx+4], 10h
0x180070afe  jbe     short loc_180070B1A
0x180070b00  lea     rax, [rcx+0Ch]
0x180070b04  mov     [r10+88h], rax
0x180070b0b  mov     eax, [rcx+4]
0x180070b0e  sub     eax, 0Fh
0x180070b11  mov     [r10+90h], eax
0x180070b18  jmp     short loc_180070B28
0x180070b1a  mov     [r10+88h], r13
0x180070b21  mov     [r10+90h], r13d
0x180070b28  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180070b2f  lea     rax, [rsp+130h+var_D0]
0x180070b34  lea     r9, ?PeapConnDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180070b3b  mov     [rsp+130h+dwInitParam], rax; dwInitParam
0x180070b40  mov     r8, r12; hWndParent
0x180070b43  mov     [rbp+3Fh+arg_0], r13d
0x180070b47  mov     edx, 3ECh; lpTemplateName
0x180070b4c  call    cs:__imp_DialogBoxParamW
0x180070b53  nop     dword ptr [rax+rax+00h]
0x180070b58  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180070b5c  jnz     short loc_180070B6F
0x180070b5e  call    cs:__imp_GetLastError
0x180070b65  nop     dword ptr [rax+rax+00h]
0x180070b6a  mov     [rbp+3Fh+arg_0], eax
0x180070b6d  jmp     short loc_180070B8F
0x180070b6f  cmp     rax, 1
0x180070b73  jz      short loc_180070B7E
0x180070b75  mov     [rbp+3Fh+arg_0], 4C7h
0x180070b7c  jmp     short loc_180070B8F
0x180070b7e  mov     rax, [rbp+3Fh+var_B8]
0x180070b82  mov     [r14], rax
0x180070b85  mov     eax, [rax+4]
0x180070b88  mov     [r15], eax
0x180070b8b  mov     [rbp+3Fh+var_B8], r13
0x180070b8f  mov     edx, 1; int
0x180070b94  xor     ecx, ecx; int
0x180070b96  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180070b9b  mov     rcx, [rsp+130h+var_C8]; hMem
0x180070ba0  call    ?FreeCertList@@YAXPEAU_EAPTLS_CERT_NODE@@@Z; FreeCertList(_EAPTLS_CERT_NODE *)
0x180070ba5  mov     rcx, [rsp+130h+hMem]; hMem
0x180070baa  test    rcx, rcx
0x180070bad  jz      short loc_180070BC0
0x180070baf  call    cs:__imp_LocalFree
0x180070bb6  nop     dword ptr [rax+rax+00h]
0x180070bbb  mov     [rsp+130h+hMem], r13
0x180070bc0  mov     rcx, [rbp+3Fh+var_B0]; hMem
0x180070bc4  call    ?PeapEapInfoFreeList@@YAXPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoFreeList(_PEAP_EAP_INFO *)
0x180070bc9  mov     rcx, [rbp+3Fh+var_B8]; hMem
0x180070bcd  call    cs:__imp_LocalFree
0x180070bd4  nop     dword ptr [rax+rax+00h]
0x180070bd9  mov     eax, [rbp+3Fh+arg_0]
0x180070bdc  add     rsp, 0F8h
0x180070be3  pop     r15
0x180070be5  pop     r14
0x180070be7  pop     r13
0x180070be9  pop     r12
0x180070beb  pop     rdi
0x180070bec  pop     rsi
0x180070bed  pop     rbx
0x180070bee  pop     rbp
0x180070bef  retn
```
