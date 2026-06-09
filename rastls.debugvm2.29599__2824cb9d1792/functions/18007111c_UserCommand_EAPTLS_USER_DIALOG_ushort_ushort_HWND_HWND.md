# UserCommand(_EAPTLS_USER_DIALOG *,ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x18007111c`
- end: `0x1800714a9`
- name: `?UserCommand@@YAHPEAU_EAPTLS_USER_DIALOG@@GGPEAUHWND__@@1@Z`
- size: `909`
- prototype: `__int64 __usercall@<rax>(struct _EAPTLS_USER_DIALOG *@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800714b0`

## callees

- `0x180004bd0`
- `0x180035680`
- `0x180036254`
- `0x18006eab8`
- `0x18006f2b4`
- `0x18007001c`
- `0x180070ee4`
- `0x18007111c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007141d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007141d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007124f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007124f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071398`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071376`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071376`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071436`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071436`
- `CRYPT32!CertCloseStore` at `0x1800712d7`
- `CRYPT32!CertCloseStore` at `0x1800712d7`
- `CRYPT32!CertFindCertificateInStore` at `0x1800712aa`
- `CRYPT32!CertFindCertificateInStore` at `0x1800712aa`
- `CRYPT32!CertFreeCertificateContext` at `0x1800712f0`
- `CRYPT32!CertFreeCertificateContext` at `0x1800712f0`
- `CRYPT32!CertOpenStore` at `0x18007122f`
- `CRYPT32!CertOpenStore` at `0x18007122f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x1800711f6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x1800713f6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x1800711f6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x1800713f6`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18007126e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x1800712cc`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18007126e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x1800712cc`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180071476`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180071476`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180071330`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180071330`

## pseudocode

```c
__int64 __fastcall UserCommand(struct _EAPTLS_USER_DIALOG *a1, __int16 a2, unsigned __int16 a3, HWND a4, HWND a5)
{
  INT_PTR v6; // r12
  struct _EAPTLS_CERT_NODE **v9; // r8
  struct _EAPTLS_HASH *v10; // r9
  HCERTSTORE v11; // rbp
  __int64 v12; // rcx
  const struct _CERT_CONTEXT *CertificateInStore; // rax
  unsigned int v14; // r9d
  const CERT_CONTEXT *v15; // rdi
  struct _EAPTLS_CERT_NODE **v16; // r8
  HWND v17; // rcx
  struct _EAPTLS_HASH *v18; // r9
  HWND v19; // rcx
  int WindowTextLengthW; // eax
  __int64 v21; // rcx
  unsigned int v22; // r15d
  unsigned __int64 v23; // rax
  int v24; // r13d
  char *v25; // rbp
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // rbx
  char *v32; // rcx
  int v33; // [rsp+30h] [rbp-668h]
  __int128 pvFindPara; // [rsp+38h] [rbp-660h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-648h] BYREF
  WCHAR String[512]; // [rsp+250h] [rbp-448h] BYREF

  v6 = a3;
  switch ( a3 )
  {
    case 1u:
      v16 = (struct _EAPTLS_CERT_NODE **)((char *)a1 + 16);
      v17 = (HWND)*((_QWORD *)a1 + 8);
      v18 = (struct _EAPTLS_HASH *)(*((_QWORD *)a1 + 4) + 16LL);
      if ( (*(_BYTE *)a1 & 4) != 0 )
        GroupCertSelected(v17, *((struct _EAPTLS_GROUPED_CERT_NODES **)a1 + 3), v16, v18);
      else
        CertSelected(v17, *((struct _EAPTLS_CERT_NODE **)a1 + 1), v16, v18);
      v19 = (HWND)*((_QWORD *)a1 + 14);
      if ( !v19 )
        goto LABEL_33;
      WindowTextLengthW = GetWindowTextLengthW(v19);
      v33 = WindowTextLengthW;
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)a1 + 4) + 56LL) + 2 * v21) );
      v22 = v21 + WindowTextLengthW + 1;
      v23 = 2LL * v22;
      if ( v23 > 0xFFFFFFFF )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_33;
        v28 = 61;
        v29 = 534;
      }
      else
      {
        v24 = v23 + 72;
        v25 = (char *)LocalAlloc(0x40u, (unsigned int)(v23 + 72));
        if ( v25 )
        {
          v30 = *((_QWORD *)a1 + 4);
          v31 = (unsigned int)(v33 + 1);
          *(_OWORD *)v25 = *(_OWORD *)v30;
          *((_OWORD *)v25 + 1) = *(_OWORD *)(v30 + 16);
          *((_OWORD *)v25 + 2) = *(_OWORD *)(v30 + 32);
          *((_OWORD *)v25 + 3) = *(_OWORD *)(v30 + 48);
          *((_QWORD *)v25 + 8) = *(_QWORD *)(v30 + 64);
          *((_DWORD *)v25 + 2) = v24;
          *((_QWORD *)v25 + 5) = v25 + 70;
          GetWindowTextW(*((HWND *)a1 + 14), (LPWSTR)v25 + 35, v33 + 1);
          *((_DWORD *)v25 + 12) = v31;
          v32 = &v25[2 * v31 + 70];
          *((_QWORD *)v25 + 7) = v32;
          _o_wcscpy_s(v32, v22 - v33, *(_QWORD *)(*((_QWORD *)a1 + 4) + 56LL));
          memset_0(*((void **)a1 + 4), 0, *(unsigned int *)(*((_QWORD *)a1 + 4) + 8LL));
          LocalFree(*((HLOCAL *)a1 + 4));
          *((_QWORD *)a1 + 4) = v25;
          goto LABEL_33;
        }
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
LABEL_33:
          EndDialog(a4, v6);
          return 1;
        }
        LastError = GetLastError();
        v27 = WPP_GLOBAL_Control;
        v28 = 62;
        v29 = LastError;
      }
      WPP_SF_d(*((_QWORD *)v27 + 2), v28, &WPP_c4e812f99669349517681909258710e2_Traceguids, v29);
      goto LABEL_33;
    case 2u:
      goto LABEL_33;
    case 0x3F3u:
      memset_0(String, 0, sizeof(String));
      pvFindPara = 0;
      GetWindowTextW(a4, String, 511);
      if ( *((_QWORD *)a1 + 2) )
      {
        v11 = CertOpenStore((LPCSTR)0xA, 0, 0, *((_DWORD *)a1 + 14) != 0 ? 98304 : 163840, *((const void **)a1 + 6));
        LoadStringW(g_hInstance, 0x644u, Buffer, 256);
        if ( v11 )
        {
          v12 = *((_QWORD *)a1 + 2);
          LODWORD(pvFindPara) = *(_DWORD *)(v12 + 8);
          *((_QWORD *)&pvFindPara + 1) = v12 + 12;
          CertificateInStore = CertFindCertificateInStore(v11, 0, 0, 0x10000u, &pvFindPara, 0);
          v15 = CertificateInStore;
          if ( CertificateInStore )
          {
            ShowCertDetails(a4, v11, CertificateInStore, v14);
            CertFreeCertificateContext(v15);
          }
          else
          {
            MessageBoxW(a4, Buffer, String, 0x10u);
          }
          CertCloseStore(v11, 1u);
        }
        else
        {
          MessageBoxW(a4, Buffer, String, 0x10u);
        }
      }
      break;
    default:
      if ( a3 != 1401 && a3 != 1600 || a2 != 1 )
        return 0;
      v9 = (struct _EAPTLS_CERT_NODE **)((char *)a1 + 16);
      v10 = (struct _EAPTLS_HASH *)(*((_QWORD *)a1 + 4) + 16LL);
      if ( (*(_BYTE *)a1 & 4) != 0 )
        GroupCertSelected(a5, *((struct _EAPTLS_GROUPED_CERT_NODES **)a1 + 3), v9, v10);
      else
        CertSelected(a5, *((struct _EAPTLS_CERT_NODE **)a1 + 1), v9, v10);
      DisplayCertInfo(a1);
      break;
  }
  return 1;
}

```

## disassembly

```asm
0x18007111c  mov     [rsp+arg_8], rbx
0x180071121  push    rbp
0x180071122  push    rsi
0x180071123  push    rdi
0x180071124  push    r12
0x180071126  push    r13
0x180071128  push    r14
0x18007112a  push    r15
0x18007112c  sub     rsp, 660h
0x180071133  mov     rax, cs:__security_cookie
0x18007113a  xor     rax, rsp
0x18007113d  mov     [rsp+698h+var_48], rax
0x180071145  mov     r10, [rsp+698h+arg_20]
0x18007114d  mov     rdi, rcx
0x180071150  movzx   r12d, r8w
0x180071154  mov     esi, 1
0x180071159  mov     ecx, r12d
0x18007115c  mov     r14, r9
0x18007115f  sub     ecx, esi
0x180071161  jz      loc_1800712F8
0x180071167  sub     ecx, esi
0x180071169  jz      loc_180071470
0x18007116f  sub     ecx, 3F1h
0x180071175  jz      short loc_1800711C8
0x180071177  sub     ecx, 186h
0x18007117d  jz      short loc_180071187
0x18007117f  cmp     ecx, 0C7h
0x180071185  jnz     short loc_18007118C
0x180071187  cmp     si, dx
0x18007118a  jz      short loc_180071193
0x18007118c  xor     eax, eax
0x18007118e  jmp     loc_18007147E
0x180071193  mov     r9, [rdi+20h]
0x180071197  lea     r8, [rdi+10h]; struct _EAPTLS_CERT_NODE **
0x18007119b  add     r9, 10h; struct _EAPTLS_HASH *
0x18007119f  mov     rcx, r10; HWND
0x1800711a2  test    byte ptr [rdi], 4
0x1800711a5  jz      short loc_1800711B2
0x1800711a7  mov     rdx, [rdi+18h]; struct _EAPTLS_GROUPED_CERT_NODES *
0x1800711ab  call    ?GroupCertSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_GROUPED_CERT_NODES@@PEAPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_HASH@@@Z; GroupCertSelected(HWND__ *,_EAPTLS_GROUPED_CERT_NODES *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *)
0x1800711b0  jmp     short loc_1800711BB
0x1800711b2  mov     rdx, [rdi+8]; struct _EAPTLS_CERT_NODE *
0x1800711b6  call    ?CertSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_NODE@@PEAPEAU2@PEAU_EAPTLS_HASH@@@Z; CertSelected(HWND__ *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *)
0x1800711bb  mov     rcx, rdi; struct _EAPTLS_USER_DIALOG *
0x1800711be  call    ?DisplayCertInfo@@YAXPEAU_EAPTLS_USER_DIALOG@@@Z; DisplayCertInfo(_EAPTLS_USER_DIALOG *)
0x1800711c3  jmp     loc_18007147C
0x1800711c8  xor     edx, edx; Val
0x1800711ca  lea     rcx, [rsp+698h+String]; void *
0x1800711d2  mov     r8d, 400h; Size
0x1800711d8  call    memset_0
0x1800711dd  xorps   xmm0, xmm0
0x1800711e0  lea     rdx, [rsp+698h+String]; lpString
0x1800711e8  mov     r8d, 1FFh; nMaxCount
0x1800711ee  mov     rcx, r14; hWnd
0x1800711f1  movups  [rsp+698h+pvFindPara], xmm0
0x1800711f6  call    cs:__imp_GetWindowTextW
0x1800711fc  xor     ebx, ebx
0x1800711fe  cmp     [rdi+10h], rbx
0x180071202  jz      loc_18007147C
0x180071208  mov     eax, [rdi+38h]
0x18007120b  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x18007120e  neg     eax
0x180071210  mov     rax, [rdi+30h]
0x180071214  sbb     r9d, r9d
0x180071217  mov     [rsp+698h+pvPara], rax; pvPara
0x18007121c  and     r9d, 0FFFF0000h
0x180071223  xor     r8d, r8d; hCryptProv
0x180071226  add     r9d, 28000h; dwFlags
0x18007122d  xor     edx, edx; dwEncodingType
0x18007122f  call    cs:__imp_CertOpenStore
0x180071235  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18007123c  lea     r8, [rsp+698h+Buffer]; lpBuffer
0x180071241  mov     r9d, 100h; cchBufferMax
0x180071247  mov     edx, 644h; uID
0x18007124c  mov     rbp, rax
0x18007124f  call    cs:__imp_LoadStringW
0x180071255  test    rbp, rbp
0x180071258  jnz     short loc_180071279
0x18007125a  lea     r9d, [rbx+10h]; uType
0x18007125e  mov     rcx, r14; hWnd
0x180071261  lea     r8, [rsp+698h+String]; lpCaption
0x180071269  lea     rdx, [rsp+698h+Buffer]; lpText
0x18007126e  call    cs:__imp_MessageBoxW
0x180071274  jmp     loc_18007147C
0x180071279  mov     rcx, [rdi+10h]
0x18007127d  mov     r9d, 10000h; dwFindType
0x180071283  mov     [rsp+698h+pPrevCertContext], rbx; pPrevCertContext
0x180071288  xor     r8d, r8d; dwFindFlags
0x18007128b  xor     edx, edx; dwCertEncodingType
0x18007128d  mov     eax, [rcx+8]
0x180071290  mov     dword ptr [rsp+698h+pvFindPara], eax
0x180071294  lea     rax, [rcx+0Ch]
0x180071298  mov     qword ptr [rsp+698h+pvFindPara+8], rax
0x18007129d  mov     rcx, rbp; hCertStore
0x1800712a0  lea     rax, [rsp+698h+pvFindPara]
0x1800712a5  mov     [rsp+698h+pvPara], rax; pvFindPara
0x1800712aa  call    cs:__imp_CertFindCertificateInStore
0x1800712b0  mov     rdi, rax
0x1800712b3  mov     rcx, r14; HWND
0x1800712b6  test    rax, rax
0x1800712b9  jnz     short loc_1800712E2
0x1800712bb  lea     r9d, [rax+10h]; uType
0x1800712bf  lea     r8, [rsp+698h+String]; lpCaption
0x1800712c7  lea     rdx, [rsp+698h+Buffer]; lpText
0x1800712cc  call    cs:__imp_MessageBoxW
0x1800712d2  mov     edx, esi; dwFlags
0x1800712d4  mov     rcx, rbp; hCertStore
0x1800712d7  call    cs:__imp_CertCloseStore
0x1800712dd  jmp     loc_18007147C
0x1800712e2  mov     r8, rdi; struct _CERT_CONTEXT *
0x1800712e5  mov     rdx, rbp; void *
0x1800712e8  call    ?ShowCertDetails@@YAXPEAUHWND__@@PEAXPEBU_CERT_CONTEXT@@K@Z; ShowCertDetails(HWND__ *,void *,_CERT_CONTEXT const *,ulong)
0x1800712ed  mov     rcx, rdi; pCertContext
0x1800712f0  call    cs:__imp_CertFreeCertificateContext
0x1800712f6  jmp     short loc_1800712D2
0x1800712f8  mov     r9, [rdi+20h]
0x1800712fc  lea     r8, [rdi+10h]; struct _EAPTLS_CERT_NODE **
0x180071300  mov     rcx, [rdi+40h]; HWND
0x180071304  add     r9, 10h; struct _EAPTLS_HASH *
0x180071308  test    byte ptr [rdi], 4
0x18007130b  jz      short loc_180071318
0x18007130d  mov     rdx, [rdi+18h]; struct _EAPTLS_GROUPED_CERT_NODES *
0x180071311  call    ?GroupCertSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_GROUPED_CERT_NODES@@PEAPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_HASH@@@Z; GroupCertSelected(HWND__ *,_EAPTLS_GROUPED_CERT_NODES *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *)
0x180071316  jmp     short loc_180071321
0x180071318  mov     rdx, [rdi+8]; struct _EAPTLS_CERT_NODE *
0x18007131c  call    ?CertSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_NODE@@PEAPEAU2@PEAU_EAPTLS_HASH@@@Z; CertSelected(HWND__ *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *)
0x180071321  mov     rcx, [rdi+70h]; hWnd
0x180071325  xor     ebx, ebx
0x180071327  test    rcx, rcx
0x18007132a  jz      loc_180071470
0x180071330  call    cs:__imp_GetWindowTextLengthW
0x180071336  mov     rcx, [rdi+20h]
0x18007133a  mov     [rsp+698h+var_668], eax
0x18007133e  mov     rdx, [rcx+38h]
0x180071342  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180071346  inc     rcx
0x180071349  cmp     [rdx+rcx*2], bx
0x18007134d  jnz     short loc_180071346
0x18007134f  lea     r15d, [rax+1]
0x180071353  add     r15d, ecx
0x180071356  mov     ecx, 0FFFFFFFFh
0x18007135b  mov     eax, r15d
0x18007135e  add     rax, rax
0x180071361  cmp     rax, rcx
0x180071364  ja      loc_180071442
0x18007136a  lea     r13d, [rax+48h]
0x18007136e  mov     ecx, 40h ; '@'; uFlags
0x180071373  mov     edx, r13d; uBytes
0x180071376  call    cs:__imp_LocalAlloc
0x18007137c  mov     rbp, rax
0x18007137f  test    rax, rax
0x180071382  jnz     short loc_1800713B0
0x180071384  lea     rax, WPP_GLOBAL_Control
0x18007138b  cmp     cs:WPP_GLOBAL_Control, rax
0x180071392  jz      loc_180071470
0x180071398  call    cs:__imp_GetLastError
0x18007139e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800713a5  lea     edx, [rbp+3Eh]
0x1800713a8  mov     r9d, eax
0x1800713ab  jmp     loc_180071460
0x1800713b0  mov     rax, [rdi+20h]
0x1800713b4  lea     rdx, [rbp+46h]; lpString
0x1800713b8  mov     ebx, [rsp+698h+var_668]
0x1800713bc  inc     ebx
0x1800713be  mov     r8d, ebx; nMaxCount
0x1800713c1  movups  xmm0, xmmword ptr [rax]
0x1800713c4  movups  xmmword ptr [rbp+0], xmm0
0x1800713c8  movups  xmm1, xmmword ptr [rax+10h]
0x1800713cc  movups  xmmword ptr [rbp+10h], xmm1
0x1800713d0  movups  xmm0, xmmword ptr [rax+20h]
0x1800713d4  movups  xmmword ptr [rbp+20h], xmm0
0x1800713d8  movups  xmm1, xmmword ptr [rax+30h]
0x1800713dc  movups  xmmword ptr [rbp+30h], xmm1
0x1800713e0  movsd   xmm0, qword ptr [rax+40h]
0x1800713e5  movsd   qword ptr [rbp+40h], xmm0
0x1800713ea  mov     [rbp+8], r13d
0x1800713ee  mov     [rbp+28h], rdx
0x1800713f2  mov     rcx, [rdi+70h]; hWnd
0x1800713f6  call    cs:__imp_GetWindowTextW
0x1800713fc  mov     [rbp+30h], ebx
0x1800713ff  lea     rcx, ds:46h[rbx*2]
0x180071407  add     rcx, rbp
0x18007140a  sub     r15d, ebx
0x18007140d  mov     [rbp+38h], rcx
0x180071411  mov     r8, [rdi+20h]
0x180071415  lea     edx, [rsi+r15]
0x180071419  mov     r8, [r8+38h]
0x18007141d  call    cs:__imp__o_wcscpy_s
0x180071423  mov     rcx, [rdi+20h]; void *
0x180071427  xor     edx, edx; Val
0x180071429  mov     r8d, [rcx+8]; Size
0x18007142d  call    memset_0
0x180071432  mov     rcx, [rdi+20h]; hMem
0x180071436  call    cs:__imp_LocalFree
0x18007143c  mov     [rdi+20h], rbp
0x180071440  jmp     short loc_180071470
0x180071442  mov     rcx, cs:WPP_GLOBAL_Control
0x180071449  lea     rax, WPP_GLOBAL_Control
0x180071450  cmp     rcx, rax
0x180071453  jz      short loc_180071470
0x180071455  mov     edx, 3Dh ; '='
0x18007145a  mov     r9d, 216h
0x180071460  mov     rcx, [rcx+10h]
0x180071464  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18007146b  call    WPP_SF_d
0x180071470  mov     rdx, r12; nResult
0x180071473  mov     rcx, r14; hDlg
0x180071476  call    cs:__imp_EndDialog
0x18007147c  mov     eax, esi
0x18007147e  mov     rcx, [rsp+698h+var_48]
0x180071486  xor     rcx, rsp; StackCookie
0x180071489  call    __security_check_cookie
0x18007148e  mov     rbx, [rsp+698h+arg_8]
0x180071496  add     rsp, 660h
0x18007149d  pop     r15
0x18007149f  pop     r14
0x1800714a1  pop     r13
0x1800714a3  pop     r12
0x1800714a5  pop     rdi
0x1800714a6  pop     rsi
0x1800714a7  pop     rbp
0x1800714a8  retn
```
