# UserCommand(_EAPTLS_USER_DIALOG *,ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x180075ef4`
- end: `0x1800762dc`
- name: `?UserCommand@@YAHPEAU_EAPTLS_USER_DIALOG@@GGPEAUHWND__@@1@Z`
- size: `1000`
- prototype: `__int64 __usercall@<rax>(struct _EAPTLS_USER_DIALOG *@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800762f0`

## callees

- `0x180005010`
- `0x180038270`
- `0x180038e64`
- `0x18007352c`
- `0x180073dec`
- `0x180074c34`
- `0x180075c6c`
- `0x180075ef4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007623d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007623d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180076033`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180076033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800761ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800761ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076184`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076184`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007625c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007625c`
- `CRYPT32!CertCloseStore` at `0x1800760d3`
- `CRYPT32!CertCloseStore` at `0x1800760d3`
- `CRYPT32!CertFindCertificateInStore` at `0x18007609a`
- `CRYPT32!CertFindCertificateInStore` at `0x18007609a`
- `CRYPT32!CertFreeCertificateContext` at `0x1800760f2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800760f2`
- `CRYPT32!CertOpenStore` at `0x18007600d`
- `CRYPT32!CertOpenStore` at `0x18007600d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x180075fce`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x180076210`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x180075fce`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x180076210`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x180076058`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x1800760c2`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x180076058`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x1800760c2`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x1800762a2`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x1800762a2`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180076138`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180076138`

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
0x180075ef4  mov     [rsp+arg_8], rbx
0x180075ef9  push    rbp
0x180075efa  push    rsi
0x180075efb  push    rdi
0x180075efc  push    r12
0x180075efe  push    r13
0x180075f00  push    r14
0x180075f02  push    r15
0x180075f04  sub     rsp, 660h
0x180075f0b  mov     rax, cs:__security_cookie
0x180075f12  xor     rax, rsp
0x180075f15  mov     [rsp+698h+var_48], rax
0x180075f1d  mov     r10, [rsp+698h+arg_20]
0x180075f25  mov     rdi, rcx
0x180075f28  movzx   r12d, r8w
0x180075f2c  mov     esi, 1
0x180075f31  mov     ecx, r12d
0x180075f34  mov     r14, r9
0x180075f37  sub     ecx, esi
0x180075f39  jz      loc_180076100
0x180075f3f  sub     ecx, esi
0x180075f41  jz      loc_18007629C
0x180075f47  sub     ecx, 3F1h
0x180075f4d  jz      short loc_180075FA0
0x180075f4f  sub     ecx, 186h
0x180075f55  jz      short loc_180075F5F
0x180075f57  cmp     ecx, 0C7h
0x180075f5d  jnz     short loc_180075F64
0x180075f5f  cmp     si, dx
0x180075f62  jz      short loc_180075F6B
0x180075f64  xor     eax, eax
0x180075f66  jmp     loc_1800762B0
0x180075f6b  mov     r9, [rdi+20h]
0x180075f6f  lea     r8, [rdi+10h]; struct _EAPTLS_CERT_NODE **
0x180075f73  add     r9, 10h; struct _EAPTLS_HASH *
0x180075f77  mov     rcx, r10; HWND
0x180075f7a  test    byte ptr [rdi], 4
0x180075f7d  jz      short loc_180075F8A
0x180075f7f  mov     rdx, [rdi+18h]; struct _EAPTLS_GROUPED_CERT_NODES *
0x180075f83  call    ?GroupCertSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_GROUPED_CERT_NODES@@PEAPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_HASH@@@Z; GroupCertSelected(HWND__ *,_EAPTLS_GROUPED_CERT_NODES *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *)
0x180075f88  jmp     short loc_180075F93
0x180075f8a  mov     rdx, [rdi+8]; struct _EAPTLS_CERT_NODE *
0x180075f8e  call    ?CertSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_NODE@@PEAPEAU2@PEAU_EAPTLS_HASH@@@Z; CertSelected(HWND__ *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *)
0x180075f93  mov     rcx, rdi; struct _EAPTLS_USER_DIALOG *
0x180075f96  call    ?DisplayCertInfo@@YAXPEAU_EAPTLS_USER_DIALOG@@@Z; DisplayCertInfo(_EAPTLS_USER_DIALOG *)
0x180075f9b  jmp     loc_1800762AE
0x180075fa0  xor     edx, edx; Val
0x180075fa2  lea     rcx, [rsp+698h+String]; void *
0x180075faa  mov     r8d, 400h; Size
0x180075fb0  call    memset_0
0x180075fb5  xorps   xmm0, xmm0
0x180075fb8  lea     rdx, [rsp+698h+String]; lpString
0x180075fc0  mov     r8d, 1FFh; nMaxCount
0x180075fc6  mov     rcx, r14; hWnd
0x180075fc9  movups  [rsp+698h+pvFindPara], xmm0
0x180075fce  call    cs:__imp_GetWindowTextW
0x180075fd5  nop     dword ptr [rax+rax+00h]
0x180075fda  xor     ebx, ebx
0x180075fdc  cmp     [rdi+10h], rbx
0x180075fe0  jz      loc_1800762AE
0x180075fe6  mov     eax, [rdi+38h]
0x180075fe9  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x180075fec  neg     eax
0x180075fee  mov     rax, [rdi+30h]
0x180075ff2  sbb     r9d, r9d
0x180075ff5  mov     [rsp+698h+pvPara], rax; pvPara
0x180075ffa  and     r9d, 0FFFF0000h
0x180076001  xor     r8d, r8d; hCryptProv
0x180076004  add     r9d, 28000h; dwFlags
0x18007600b  xor     edx, edx; dwEncodingType
0x18007600d  call    cs:__imp_CertOpenStore
0x180076014  nop     dword ptr [rax+rax+00h]
0x180076019  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180076020  lea     r8, [rsp+698h+Buffer]; lpBuffer
0x180076025  mov     r9d, 100h; cchBufferMax
0x18007602b  mov     edx, 644h; uID
0x180076030  mov     rbp, rax
0x180076033  call    cs:__imp_LoadStringW
0x18007603a  nop     dword ptr [rax+rax+00h]
0x18007603f  test    rbp, rbp
0x180076042  jnz     short loc_180076069
0x180076044  lea     r9d, [rbx+10h]; uType
0x180076048  mov     rcx, r14; hWnd
0x18007604b  lea     r8, [rsp+698h+String]; lpCaption
0x180076053  lea     rdx, [rsp+698h+Buffer]; lpText
0x180076058  call    cs:__imp_MessageBoxW
0x18007605f  nop     dword ptr [rax+rax+00h]
0x180076064  jmp     loc_1800762AE
0x180076069  mov     rcx, [rdi+10h]
0x18007606d  mov     r9d, 10000h; dwFindType
0x180076073  mov     [rsp+698h+pPrevCertContext], rbx; pPrevCertContext
0x180076078  xor     r8d, r8d; dwFindFlags
0x18007607b  xor     edx, edx; dwCertEncodingType
0x18007607d  mov     eax, [rcx+8]
0x180076080  mov     dword ptr [rsp+698h+pvFindPara], eax
0x180076084  lea     rax, [rcx+0Ch]
0x180076088  mov     qword ptr [rsp+698h+pvFindPara+8], rax
0x18007608d  mov     rcx, rbp; hCertStore
0x180076090  lea     rax, [rsp+698h+pvFindPara]
0x180076095  mov     [rsp+698h+pvPara], rax; pvFindPara
0x18007609a  call    cs:__imp_CertFindCertificateInStore
0x1800760a1  nop     dword ptr [rax+rax+00h]
0x1800760a6  mov     rdi, rax
0x1800760a9  mov     rcx, r14; HWND
0x1800760ac  test    rax, rax
0x1800760af  jnz     short loc_1800760E4
0x1800760b1  lea     r9d, [rax+10h]; uType
0x1800760b5  lea     r8, [rsp+698h+String]; lpCaption
0x1800760bd  lea     rdx, [rsp+698h+Buffer]; lpText
0x1800760c2  call    cs:__imp_MessageBoxW
0x1800760c9  nop     dword ptr [rax+rax+00h]
0x1800760ce  mov     edx, esi; dwFlags
0x1800760d0  mov     rcx, rbp; hCertStore
0x1800760d3  call    cs:__imp_CertCloseStore
0x1800760da  nop     dword ptr [rax+rax+00h]
0x1800760df  jmp     loc_1800762AE
0x1800760e4  mov     r8, rdi; struct _CERT_CONTEXT *
0x1800760e7  mov     rdx, rbp; void *
0x1800760ea  call    ?ShowCertDetails@@YAXPEAUHWND__@@PEAXPEBU_CERT_CONTEXT@@K@Z; ShowCertDetails(HWND__ *,void *,_CERT_CONTEXT const *,ulong)
0x1800760ef  mov     rcx, rdi; pCertContext
0x1800760f2  call    cs:__imp_CertFreeCertificateContext
0x1800760f9  nop     dword ptr [rax+rax+00h]
0x1800760fe  jmp     short loc_1800760CE
0x180076100  mov     r9, [rdi+20h]
0x180076104  lea     r8, [rdi+10h]; struct _EAPTLS_CERT_NODE **
0x180076108  mov     rcx, [rdi+40h]; HWND
0x18007610c  add     r9, 10h; struct _EAPTLS_HASH *
0x180076110  test    byte ptr [rdi], 4
0x180076113  jz      short loc_180076120
0x180076115  mov     rdx, [rdi+18h]; struct _EAPTLS_GROUPED_CERT_NODES *
0x180076119  call    ?GroupCertSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_GROUPED_CERT_NODES@@PEAPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_HASH@@@Z; GroupCertSelected(HWND__ *,_EAPTLS_GROUPED_CERT_NODES *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *)
0x18007611e  jmp     short loc_180076129
0x180076120  mov     rdx, [rdi+8]; struct _EAPTLS_CERT_NODE *
0x180076124  call    ?CertSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_NODE@@PEAPEAU2@PEAU_EAPTLS_HASH@@@Z; CertSelected(HWND__ *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *)
0x180076129  mov     rcx, [rdi+70h]; hWnd
0x18007612d  xor     ebx, ebx
0x18007612f  test    rcx, rcx
0x180076132  jz      loc_18007629C
0x180076138  call    cs:__imp_GetWindowTextLengthW
0x18007613f  nop     dword ptr [rax+rax+00h]
0x180076144  mov     rcx, [rdi+20h]
0x180076148  mov     [rsp+698h+var_668], eax
0x18007614c  mov     rdx, [rcx+38h]
0x180076150  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180076154  inc     rcx
0x180076157  cmp     [rdx+rcx*2], bx
0x18007615b  jnz     short loc_180076154
0x18007615d  lea     r15d, [rax+1]
0x180076161  add     r15d, ecx
0x180076164  mov     ecx, 0FFFFFFFFh
0x180076169  mov     eax, r15d
0x18007616c  add     rax, rax
0x18007616f  cmp     rax, rcx
0x180076172  ja      loc_18007626E
0x180076178  lea     r13d, [rax+48h]
0x18007617c  mov     ecx, 40h ; '@'; uFlags
0x180076181  mov     edx, r13d; uBytes
0x180076184  call    cs:__imp_LocalAlloc
0x18007618b  nop     dword ptr [rax+rax+00h]
0x180076190  mov     rbp, rax
0x180076193  test    rax, rax
0x180076196  jnz     short loc_1800761CA
0x180076198  lea     rax, WPP_GLOBAL_Control
0x18007619f  cmp     cs:WPP_GLOBAL_Control, rax
0x1800761a6  jz      loc_18007629C
0x1800761ac  call    cs:__imp_GetLastError
0x1800761b3  nop     dword ptr [rax+rax+00h]
0x1800761b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800761bf  lea     edx, [rbp+3Eh]
0x1800761c2  mov     r9d, eax
0x1800761c5  jmp     loc_18007628C
0x1800761ca  mov     rax, [rdi+20h]
0x1800761ce  lea     rdx, [rbp+46h]; lpString
0x1800761d2  mov     ebx, [rsp+698h+var_668]
0x1800761d6  inc     ebx
0x1800761d8  mov     r8d, ebx; nMaxCount
0x1800761db  movups  xmm0, xmmword ptr [rax]
0x1800761de  movups  xmmword ptr [rbp+0], xmm0
0x1800761e2  movups  xmm1, xmmword ptr [rax+10h]
0x1800761e6  movups  xmmword ptr [rbp+10h], xmm1
0x1800761ea  movups  xmm0, xmmword ptr [rax+20h]
0x1800761ee  movups  xmmword ptr [rbp+20h], xmm0
0x1800761f2  movups  xmm1, xmmword ptr [rax+30h]
0x1800761f6  movups  xmmword ptr [rbp+30h], xmm1
0x1800761fa  movsd   xmm0, qword ptr [rax+40h]
0x1800761ff  movsd   qword ptr [rbp+40h], xmm0
0x180076204  mov     [rbp+8], r13d
0x180076208  mov     [rbp+28h], rdx
0x18007620c  mov     rcx, [rdi+70h]; hWnd
0x180076210  call    cs:__imp_GetWindowTextW
0x180076217  nop     dword ptr [rax+rax+00h]
0x18007621c  mov     [rbp+30h], ebx
0x18007621f  lea     rcx, ds:46h[rbx*2]
0x180076227  add     rcx, rbp
0x18007622a  sub     r15d, ebx
0x18007622d  mov     [rbp+38h], rcx
0x180076231  mov     r8, [rdi+20h]
0x180076235  lea     edx, [rsi+r15]
0x180076239  mov     r8, [r8+38h]
0x18007623d  call    cs:__imp__o_wcscpy_s
0x180076244  nop     dword ptr [rax+rax+00h]
0x180076249  mov     rcx, [rdi+20h]; void *
0x18007624d  xor     edx, edx; Val
0x18007624f  mov     r8d, [rcx+8]; Size
0x180076253  call    memset_0
0x180076258  mov     rcx, [rdi+20h]; hMem
0x18007625c  call    cs:__imp_LocalFree
0x180076263  nop     dword ptr [rax+rax+00h]
0x180076268  mov     [rdi+20h], rbp
0x18007626c  jmp     short loc_18007629C
0x18007626e  mov     rcx, cs:WPP_GLOBAL_Control
0x180076275  lea     rax, WPP_GLOBAL_Control
0x18007627c  cmp     rcx, rax
0x18007627f  jz      short loc_18007629C
0x180076281  mov     edx, 3Dh ; '='
0x180076286  mov     r9d, 216h
0x18007628c  mov     rcx, [rcx+10h]
0x180076290  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180076297  call    WPP_SF_d
0x18007629c  mov     rdx, r12; nResult
0x18007629f  mov     rcx, r14; hDlg
0x1800762a2  call    cs:__imp_EndDialog
0x1800762a9  nop     dword ptr [rax+rax+00h]
0x1800762ae  mov     eax, esi
0x1800762b0  mov     rcx, [rsp+698h+var_48]
0x1800762b8  xor     rcx, rsp; StackCookie
0x1800762bb  call    __security_check_cookie
0x1800762c0  mov     rbx, [rsp+698h+arg_8]
0x1800762c8  add     rsp, 660h
0x1800762cf  pop     r15
0x1800762d1  pop     r14
0x1800762d3  pop     r13
0x1800762d5  pop     r12
0x1800762d7  pop     rdi
0x1800762d8  pop     rsi
0x1800762d9  pop     rbp
0x1800762da  retn
```
