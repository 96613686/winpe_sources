# EKUAddCommandDialog(_EAPTLS_CERT_FILTER_DIALOG *,ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x18006c5e8`
- end: `0x18006ca0f`
- name: `?EKUAddCommandDialog@@YAHPEAU_EAPTLS_CERT_FILTER_DIALOG@@GGPEAUHWND__@@1@Z`
- size: `1063`
- prototype: `int(struct _EAPTLS_CERT_FILTER_DIALOG *, unsigned __int16, unsigned __int16, HWND, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006ca20`

## callees

- `0x180010140`
- `0x180011a00`
- `0x1800215b0`
- `0x180025308`
- `0x180032764`
- `0x180038270`
- `0x180038e64`
- `0x18006c5e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c82a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c841`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c82a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c841`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006c89f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006c89f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c68c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c7a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c7bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c8f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c68c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c7a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c7bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006c8f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c6c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c6d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c8cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c8e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c6c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c6d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c8cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c8e0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006c9fe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006c9fe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c6ae`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c7da`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c7f2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c87a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c980`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c99d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c6ae`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c7da`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c7f2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c87a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c980`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006c99d`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18006c8c0`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18006c8c0`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18006c732`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18006c732`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006c672`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006c76e`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006c780`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006c672`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006c76e`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006c780`

## pseudocode

```c
__int64 __fastcall EKUAddCommandDialog(struct _EAPTLS_CERT_FILTER_DIALOG *a1, __int16 a2, unsigned __int16 a3, HWND a4)
{
  __int64 v7; // rax
  int v8; // edi
  WCHAR *v9; // rax
  const WCHAR *v10; // rbx
  int WindowTextLengthW; // edi
  int v12; // eax
  int v13; // edi
  int v14; // ebx
  WCHAR *v15; // r15
  unsigned int i; // edi
  _QWORD *v17; // rbx
  _QWORD *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // r9
  BOOL v21; // edx
  WCHAR *lpString; // [rsp+28h] [rbp-D8h]
  WCHAR String[512]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[520]; // [rsp+430h] [rbp+330h] BYREF

  if ( !a1 )
    return 0;
  if ( a3 == 2 )
    goto LABEL_12;
  if ( a3 == 1056 || a3 == 1057 )
  {
    if ( a2 == 768 )
    {
      memset_0(String, 0, 0x202u);
      memset_0(Buffer, 0, 0x402u);
      GetWindowTextW(*((HWND *)a1 + 12), String, 257);
      GetWindowTextW(*((HWND *)a1 + 13), Buffer, 513);
      v19 = -1;
      do
        ++v19;
      while ( String[v19] );
      if ( !(unsigned int)isValidEKUName(String, v19) )
        goto LABEL_33;
      do
        ++v20;
      while ( Buffer[v20] );
      if ( (unsigned int)isValidEKUOID(Buffer, v20) )
        v21 = 1;
      else
LABEL_33:
        v21 = 0;
      EnableWindow(*((HWND *)a1 + 14), v21);
      return 1;
    }
    return 0;
  }
  if ( a3 != 1058 )
    return 0;
  v7 = *((_QWORD *)a1 + 10);
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 32) )
    {
      v8 = GetWindowTextLengthW(*((HWND *)a1 + 13)) + 1;
      v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * v8);
      v10 = v9;
      if ( v9 )
      {
        GetWindowTextW(*((HWND *)a1 + 13), v9, v8);
        LocalFree(*(HLOCAL *)(*((_QWORD *)a1 + 10) + 24LL));
        LocalFree(*(HLOCAL *)(*((_QWORD *)a1 + 10) + 16LL));
        *(_QWORD *)(*((_QWORD *)a1 + 10) + 16LL) = v10;
        *(_QWORD *)(*((_QWORD *)a1 + 10) + 24LL) = StrdupWtoA(v10);
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            183,
            &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
            *(_QWORD *)(*((_QWORD *)a1 + 10) + 16LL));
      }
    }
    goto LABEL_12;
  }
  WindowTextLengthW = GetWindowTextLengthW(*((HWND *)a1 + 12));
  v12 = GetWindowTextLengthW(*((HWND *)a1 + 13));
  if ( WindowTextLengthW > 0 && v12 > 0 )
  {
    v13 = WindowTextLengthW + 1;
    v14 = v12 + 1;
    v15 = (WCHAR *)LocalAlloc(0x40u, 2LL * v13);
    lpString = (WCHAR *)LocalAlloc(0x40u, 2LL * v14);
    GetWindowTextW(*((HWND *)a1 + 12), v15, v13);
    GetWindowTextW(*((HWND *)a1 + 13), lpString, v14);
    for ( i = 0; ; ++i )
    {
      if ( i >= 2 )
      {
        v18 = LocalAlloc(0x40u, 0x30u);
        v18[1] = v15;
        v18[2] = lpString;
        *((_DWORD *)v18 + 8) = 1;
        v18[3] = StrdupWtoA(lpString);
        *((_QWORD *)a1 + 10) = v18;
        SortedEKUInsert((struct _EAPTLS_EKU_NODE **)a1 + 9, (struct _EAPTLS_EKU_NODE *)v18);
        break;
      }
      v17 = *(_QWORD **)((char *)a1 + (-(__int64)(i != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 72);
      if ( v17 )
LABEL_22:
        v17 = (_QWORD *)*v17;
      if ( v17 && (int)_o__wcsicmp(v17[1], v15) <= 0 )
      {
        if ( !(unsigned int)_o__wcsicmp(v17[1], v15) )
        {
          memset_0(String, 0, sizeof(String));
          GetWindowTextW(a4, String, 511);
          LoadStringW(g_hInstance, 0x4C0u, Buffer, 512);
          MessageBoxW(a4, Buffer, String, 0x10u);
          LocalFree(v15);
          LocalFree(lpString);
          return 1;
        }
        goto LABEL_22;
      }
    }
  }
LABEL_12:
  EndDialog(a4, a3);
  return 1;
}

```

## disassembly

```asm
0x18006c5e8  mov     [rsp-8+arg_8], rbx
0x18006c5ed  push    rbp
0x18006c5ee  push    rsi
0x18006c5ef  push    rdi
0x18006c5f0  push    r13
0x18006c5f2  push    r15
0x18006c5f4  lea     rbp, [rsp-750h]
0x18006c5fc  sub     rsp, 850h
0x18006c603  mov     rax, cs:__security_cookie
0x18006c60a  xor     rax, rsp
0x18006c60d  mov     [rbp+770h+var_30], rax
0x18006c614  xor     r15d, r15d
0x18006c617  movzx   eax, r8w
0x18006c61b  mov     [rsp+870h+var_850], ax
0x18006c620  mov     r13, r9
0x18006c623  mov     rsi, rcx
0x18006c626  test    rcx, rcx
0x18006c629  jnz     short loc_18006C632
0x18006c62b  xor     eax, eax
0x18006c62d  jmp     loc_18006C743
0x18006c632  mov     ecx, eax
0x18006c634  sub     ecx, 2
0x18006c637  jz      loc_18006C72A
0x18006c63d  sub     ecx, 41Eh
0x18006c643  jz      loc_18006C93D
0x18006c649  sub     ecx, 1
0x18006c64c  jz      loc_18006C93D
0x18006c652  cmp     ecx, 1
0x18006c655  jnz     short loc_18006C62B
0x18006c657  mov     rax, [rsi+50h]
0x18006c65b  test    rax, rax
0x18006c65e  jz      loc_18006C76A
0x18006c664  cmp     [rax+20h], r15d
0x18006c668  jz      loc_18006C72A
0x18006c66e  mov     rcx, [rsi+68h]; hWnd
0x18006c672  call    cs:__imp_GetWindowTextLengthW
0x18006c679  nop     dword ptr [rax+rax+00h]
0x18006c67e  mov     ecx, 40h ; '@'; uFlags
0x18006c683  lea     edi, [rax+1]
0x18006c686  movsxd  rdx, edi
0x18006c689  add     rdx, rdx; uBytes
0x18006c68c  call    cs:__imp_LocalAlloc
0x18006c693  nop     dword ptr [rax+rax+00h]
0x18006c698  mov     rbx, rax
0x18006c69b  test    rax, rax
0x18006c69e  jz      loc_18006C72A
0x18006c6a4  mov     rcx, [rsi+68h]; hWnd
0x18006c6a8  mov     r8d, edi; nMaxCount
0x18006c6ab  mov     rdx, rax; lpString
0x18006c6ae  call    cs:__imp_GetWindowTextW
0x18006c6b5  nop     dword ptr [rax+rax+00h]
0x18006c6ba  mov     rcx, [rsi+50h]
0x18006c6be  mov     rcx, [rcx+18h]; hMem
0x18006c6c2  call    cs:__imp_LocalFree
0x18006c6c9  nop     dword ptr [rax+rax+00h]
0x18006c6ce  mov     rcx, [rsi+50h]
0x18006c6d2  mov     rcx, [rcx+10h]; hMem
0x18006c6d6  call    cs:__imp_LocalFree
0x18006c6dd  nop     dword ptr [rax+rax+00h]
0x18006c6e2  mov     rcx, [rsi+50h]
0x18006c6e6  mov     [rcx+10h], rbx
0x18006c6ea  mov     rcx, rbx; lpWideCharStr
0x18006c6ed  call    ?StrdupWtoA@@YAPEADPEAG@Z; StrdupWtoA(ushort *)
0x18006c6f2  mov     rcx, [rsi+50h]
0x18006c6f6  mov     [rcx+18h], rax
0x18006c6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c701  lea     rax, WPP_GLOBAL_Control
0x18006c708  cmp     rcx, rax
0x18006c70b  jz      short loc_18006C72A
0x18006c70d  mov     r9, [rsi+50h]
0x18006c711  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006c718  mov     rcx, [rcx+10h]
0x18006c71c  mov     edx, 0B7h
0x18006c721  mov     r9, [r9+10h]
0x18006c725  call    WPP_SF_S
0x18006c72a  movzx   edx, [rsp+870h+var_850]; nResult
0x18006c72f  mov     rcx, r13; hDlg
0x18006c732  call    cs:__imp_EndDialog
0x18006c739  nop     dword ptr [rax+rax+00h]
0x18006c73e  mov     eax, 1
0x18006c743  mov     rcx, [rbp+770h+var_30]
0x18006c74a  xor     rcx, rsp; StackCookie
0x18006c74d  call    __security_check_cookie
0x18006c752  mov     rbx, [rsp+870h+arg_8]
0x18006c75a  add     rsp, 850h
0x18006c761  pop     r15
0x18006c763  pop     r13
0x18006c765  pop     rdi
0x18006c766  pop     rsi
0x18006c767  pop     rbp
0x18006c768  retn
0x18006c76a  mov     rcx, [rsi+60h]; hWnd
0x18006c76e  call    cs:__imp_GetWindowTextLengthW
0x18006c775  nop     dword ptr [rax+rax+00h]
0x18006c77a  mov     rcx, [rsi+68h]; hWnd
0x18006c77e  mov     edi, eax
0x18006c780  call    cs:__imp_GetWindowTextLengthW
0x18006c787  nop     dword ptr [rax+rax+00h]
0x18006c78c  mov     ebx, eax
0x18006c78e  test    edi, edi
0x18006c790  jle     short loc_18006C72A
0x18006c792  test    eax, eax
0x18006c794  jle     short loc_18006C72A
0x18006c796  inc     edi
0x18006c798  mov     ecx, 40h ; '@'; uFlags
0x18006c79d  movsxd  rdx, edi
0x18006c7a0  add     rdx, rdx; uBytes
0x18006c7a3  call    cs:__imp_LocalAlloc
0x18006c7aa  nop     dword ptr [rax+rax+00h]
0x18006c7af  inc     ebx
0x18006c7b1  mov     ecx, 40h ; '@'; uFlags
0x18006c7b6  movsxd  rdx, ebx
0x18006c7b9  mov     r15, rax
0x18006c7bc  add     rdx, rdx; uBytes
0x18006c7bf  call    cs:__imp_LocalAlloc
0x18006c7c6  nop     dword ptr [rax+rax+00h]
0x18006c7cb  mov     rcx, [rsi+60h]; hWnd
0x18006c7cf  mov     r8d, edi; nMaxCount
0x18006c7d2  mov     rdx, r15; lpString
0x18006c7d5  mov     [rsp+870h+lpString], rax
0x18006c7da  call    cs:__imp_GetWindowTextW
0x18006c7e1  nop     dword ptr [rax+rax+00h]
0x18006c7e6  mov     rdx, [rsp+870h+lpString]; lpString
0x18006c7eb  mov     r8d, ebx; nMaxCount
0x18006c7ee  mov     rcx, [rsi+68h]; hWnd
0x18006c7f2  call    cs:__imp_GetWindowTextW
0x18006c7f9  nop     dword ptr [rax+rax+00h]
0x18006c7fe  xor     edi, edi
0x18006c800  cmp     edi, 2
0x18006c803  jnb     loc_18006C8F1
0x18006c809  mov     eax, edi
0x18006c80b  neg     eax
0x18006c80d  sbb     rcx, rcx
0x18006c810  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18006c814  mov     rbx, [rcx+rsi+48h]
0x18006c819  test    rbx, rbx
0x18006c81c  jnz     short loc_18006C851
0x18006c81e  test    rbx, rbx
0x18006c821  jz      short loc_18006C856
0x18006c823  mov     rcx, [rbx+8]
0x18006c827  mov     rdx, r15
0x18006c82a  call    cs:__imp__o__wcsicmp
0x18006c831  nop     dword ptr [rax+rax+00h]
0x18006c836  test    eax, eax
0x18006c838  jg      short loc_18006C856
0x18006c83a  mov     rcx, [rbx+8]
0x18006c83e  mov     rdx, r15
0x18006c841  call    cs:__imp__o__wcsicmp
0x18006c848  nop     dword ptr [rax+rax+00h]
0x18006c84d  test    eax, eax
0x18006c84f  jz      short loc_18006C85A
0x18006c851  mov     rbx, [rbx]
0x18006c854  jmp     short loc_18006C81E
0x18006c856  inc     edi
0x18006c858  jmp     short loc_18006C800
0x18006c85a  xor     edx, edx; Val
0x18006c85c  lea     rcx, [rsp+870h+String]; void *
0x18006c861  mov     r8d, 400h; Size
0x18006c867  call    memset_0
0x18006c86c  mov     r8d, 1FFh; nMaxCount
0x18006c872  lea     rdx, [rsp+870h+String]; lpString
0x18006c877  mov     rcx, r13; hWnd
0x18006c87a  call    cs:__imp_GetWindowTextW
0x18006c881  nop     dword ptr [rax+rax+00h]
0x18006c886  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006c88d  lea     r8, [rbp+770h+Buffer]; lpBuffer
0x18006c894  mov     r9d, 200h; cchBufferMax
0x18006c89a  mov     edx, 4C0h; uID
0x18006c89f  call    cs:__imp_LoadStringW
0x18006c8a6  nop     dword ptr [rax+rax+00h]
0x18006c8ab  mov     r9d, 10h; uType
0x18006c8b1  lea     r8, [rsp+870h+String]; lpCaption
0x18006c8b6  lea     rdx, [rbp+770h+Buffer]; lpText
0x18006c8bd  mov     rcx, r13; hWnd
0x18006c8c0  call    cs:__imp_MessageBoxW
0x18006c8c7  nop     dword ptr [rax+rax+00h]
0x18006c8cc  mov     rcx, r15; hMem
0x18006c8cf  call    cs:__imp_LocalFree
0x18006c8d6  nop     dword ptr [rax+rax+00h]
0x18006c8db  mov     rcx, [rsp+870h+lpString]; hMem
0x18006c8e0  call    cs:__imp_LocalFree
0x18006c8e7  nop     dword ptr [rax+rax+00h]
0x18006c8ec  jmp     loc_18006C73E
0x18006c8f1  mov     edx, 30h ; '0'; uBytes
0x18006c8f6  lea     ecx, [rdx+10h]; uFlags
0x18006c8f9  call    cs:__imp_LocalAlloc
0x18006c900  nop     dword ptr [rax+rax+00h]
0x18006c905  mov     rbx, rax
0x18006c908  mov     [rax+8], r15
0x18006c90c  mov     rax, [rsp+870h+lpString]
0x18006c911  mov     rcx, rax; lpWideCharStr
0x18006c914  mov     [rbx+10h], rax
0x18006c918  mov     dword ptr [rbx+20h], 1
0x18006c91f  call    ?StrdupWtoA@@YAPEADPEAG@Z; StrdupWtoA(ushort *)
0x18006c924  mov     [rbx+18h], rax
0x18006c928  lea     rcx, [rsi+48h]; struct _EAPTLS_EKU_NODE **
0x18006c92c  mov     rdx, rbx; struct _EAPTLS_EKU_NODE *
0x18006c92f  mov     [rsi+50h], rbx
0x18006c933  call    ?SortedEKUInsert@@YAXPEAPEAU_EAPTLS_EKU_NODE@@PEAU1@@Z; SortedEKUInsert(_EAPTLS_EKU_NODE * *,_EAPTLS_EKU_NODE *)
0x18006c938  jmp     loc_18006C72A
0x18006c93d  mov     eax, 300h
0x18006c942  cmp     ax, dx
0x18006c945  jnz     loc_18006C62B
0x18006c94b  xor     edx, edx; Val
0x18006c94d  lea     rcx, [rsp+870h+String]; void *
0x18006c952  mov     r8d, 202h; Size
0x18006c958  call    memset_0
0x18006c95d  xor     edx, edx; Val
0x18006c95f  lea     rcx, [rbp+770h+Buffer]; void *
0x18006c966  mov     r8d, 402h; Size
0x18006c96c  call    memset_0
0x18006c971  mov     rcx, [rsi+60h]; hWnd
0x18006c975  lea     rdx, [rsp+870h+String]; lpString
0x18006c97a  mov     r8d, 101h; nMaxCount
0x18006c980  call    cs:__imp_GetWindowTextW
0x18006c987  nop     dword ptr [rax+rax+00h]
0x18006c98c  mov     rcx, [rsi+68h]; hWnd
0x18006c990  lea     rdx, [rbp+770h+Buffer]; lpString
0x18006c997  mov     r8d, 201h; nMaxCount
0x18006c99d  call    cs:__imp_GetWindowTextW
0x18006c9a4  nop     dword ptr [rax+rax+00h]
0x18006c9a9  or      r9, 0FFFFFFFFFFFFFFFFh
0x18006c9ad  lea     rax, [rsp+870h+String]
0x18006c9b2  mov     rdx, r9
0x18006c9b5  inc     rdx; unsigned int
0x18006c9b8  cmp     [rax+rdx*2], r15w
0x18006c9bd  jnz     short loc_18006C9B5
0x18006c9bf  lea     rcx, [rsp+870h+String]; unsigned __int16 *
0x18006c9c4  call    ?isValidEKUName@@YAHPEAGK@Z; isValidEKUName(ushort *,ulong)
0x18006c9c9  test    eax, eax
0x18006c9cb  jz      short loc_18006C9F8
0x18006c9cd  lea     rax, [rbp+770h+Buffer]
0x18006c9d4  inc     r9
0x18006c9d7  cmp     [rax+r9*2], r15w
0x18006c9dc  jnz     short loc_18006C9D4
0x18006c9de  mov     edx, r9d; unsigned int
0x18006c9e1  lea     rcx, [rbp+770h+Buffer]; unsigned __int16 *
0x18006c9e8  call    ?isValidEKUOID@@YAHPEAGK@Z; isValidEKUOID(ushort *,ulong)
0x18006c9ed  test    eax, eax
0x18006c9ef  jz      short loc_18006C9F8
0x18006c9f1  mov     edx, 1
0x18006c9f6  jmp     short loc_18006C9FA
0x18006c9f8  xor     edx, edx; bEnable
0x18006c9fa  mov     rcx, [rsi+70h]; hWnd
0x18006c9fe  call    cs:__imp_EnableWindow
0x18006ca05  nop     dword ptr [rax+rax+00h]
0x18006ca0a  jmp     loc_18006C73E
```
