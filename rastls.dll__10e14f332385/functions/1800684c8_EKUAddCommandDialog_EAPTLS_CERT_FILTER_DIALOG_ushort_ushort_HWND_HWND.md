# EKUAddCommandDialog(_EAPTLS_CERT_FILTER_DIALOG *,ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x1800684c8`
- end: `0x180068860`
- name: `?EKUAddCommandDialog@@YAHPEAU_EAPTLS_CERT_FILTER_DIALOG@@GGPEAUHWND__@@1@Z`
- size: `920`
- prototype: `int(struct _EAPTLS_CERT_FILTER_DIALOG *, unsigned __int16, unsigned __int16, HWND, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180068870`

## callees

- `0x18000f350`
- `0x180010a50`
- `0x18001fc24`
- `0x180022ef4`
- `0x180030058`
- `0x180035680`
- `0x180036254`
- `0x1800684c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800686bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800686ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800686bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800686ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180068720`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180068720`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068566`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006864e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068664`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068762`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068566`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006864e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068664`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006858c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006859a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068744`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006874f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006858c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006859a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068744`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006874f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x180068855`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x180068855`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006857e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x180068679`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006868b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x180068701`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x1800687e3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x1800687fa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006857e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x180068679`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006868b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x180068701`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x1800687e3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x1800687fa`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18006873b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18006873b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x1800685f0`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x1800685f0`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180068552`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180068625`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180068631`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180068552`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180068625`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x180068631`

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
0x1800684c8  mov     [rsp-8+arg_8], rbx
0x1800684cd  push    rbp
0x1800684ce  push    rsi
0x1800684cf  push    rdi
0x1800684d0  push    r13
0x1800684d2  push    r15
0x1800684d4  lea     rbp, [rsp-750h]
0x1800684dc  sub     rsp, 850h
0x1800684e3  mov     rax, cs:__security_cookie
0x1800684ea  xor     rax, rsp
0x1800684ed  mov     [rbp+770h+var_30], rax
0x1800684f4  xor     r15d, r15d
0x1800684f7  movzx   eax, r8w
0x1800684fb  mov     [rsp+870h+var_850], ax
0x180068500  mov     r13, r9
0x180068503  mov     rsi, rcx
0x180068506  test    rcx, rcx
0x180068509  jnz     short loc_180068512
0x18006850b  xor     eax, eax
0x18006850d  jmp     loc_1800685FB
0x180068512  mov     ecx, eax
0x180068514  sub     ecx, 2
0x180068517  jz      loc_1800685E8
0x18006851d  sub     ecx, 41Eh
0x180068523  jz      loc_1800687A0
0x180068529  sub     ecx, 1
0x18006852c  jz      loc_1800687A0
0x180068532  cmp     ecx, 1
0x180068535  jnz     short loc_18006850B
0x180068537  mov     rax, [rsi+50h]
0x18006853b  test    rax, rax
0x18006853e  jz      loc_180068621
0x180068544  cmp     [rax+20h], r15d
0x180068548  jz      loc_1800685E8
0x18006854e  mov     rcx, [rsi+68h]; hWnd
0x180068552  call    cs:__imp_GetWindowTextLengthW
0x180068558  mov     ecx, 40h ; '@'; uFlags
0x18006855d  lea     edi, [rax+1]
0x180068560  movsxd  rdx, edi
0x180068563  add     rdx, rdx; uBytes
0x180068566  call    cs:__imp_LocalAlloc
0x18006856c  mov     rbx, rax
0x18006856f  test    rax, rax
0x180068572  jz      short loc_1800685E8
0x180068574  mov     rcx, [rsi+68h]; hWnd
0x180068578  mov     r8d, edi; nMaxCount
0x18006857b  mov     rdx, rax; lpString
0x18006857e  call    cs:__imp_GetWindowTextW
0x180068584  mov     rcx, [rsi+50h]
0x180068588  mov     rcx, [rcx+18h]; hMem
0x18006858c  call    cs:__imp_LocalFree
0x180068592  mov     rcx, [rsi+50h]
0x180068596  mov     rcx, [rcx+10h]; hMem
0x18006859a  call    cs:__imp_LocalFree
0x1800685a0  mov     rcx, [rsi+50h]
0x1800685a4  mov     [rcx+10h], rbx
0x1800685a8  mov     rcx, rbx; lpWideCharStr
0x1800685ab  call    ?StrdupWtoA@@YAPEADPEAG@Z; StrdupWtoA(ushort *)
0x1800685b0  mov     rcx, [rsi+50h]
0x1800685b4  mov     [rcx+18h], rax
0x1800685b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800685bf  lea     rax, WPP_GLOBAL_Control
0x1800685c6  cmp     rcx, rax
0x1800685c9  jz      short loc_1800685E8
0x1800685cb  mov     r9, [rsi+50h]
0x1800685cf  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800685d6  mov     rcx, [rcx+10h]
0x1800685da  mov     edx, 0B7h
0x1800685df  mov     r9, [r9+10h]
0x1800685e3  call    WPP_SF_S
0x1800685e8  movzx   edx, [rsp+870h+var_850]; nResult
0x1800685ed  mov     rcx, r13; hDlg
0x1800685f0  call    cs:__imp_EndDialog
0x1800685f6  mov     eax, 1
0x1800685fb  mov     rcx, [rbp+770h+var_30]
0x180068602  xor     rcx, rsp; StackCookie
0x180068605  call    __security_check_cookie
0x18006860a  mov     rbx, [rsp+870h+arg_8]
0x180068612  add     rsp, 850h
0x180068619  pop     r15
0x18006861b  pop     r13
0x18006861d  pop     rdi
0x18006861e  pop     rsi
0x18006861f  pop     rbp
0x180068620  retn
0x180068621  mov     rcx, [rsi+60h]; hWnd
0x180068625  call    cs:__imp_GetWindowTextLengthW
0x18006862b  mov     rcx, [rsi+68h]; hWnd
0x18006862f  mov     edi, eax
0x180068631  call    cs:__imp_GetWindowTextLengthW
0x180068637  mov     ebx, eax
0x180068639  test    edi, edi
0x18006863b  jle     short loc_1800685E8
0x18006863d  test    eax, eax
0x18006863f  jle     short loc_1800685E8
0x180068641  inc     edi
0x180068643  mov     ecx, 40h ; '@'; uFlags
0x180068648  movsxd  rdx, edi
0x18006864b  add     rdx, rdx; uBytes
0x18006864e  call    cs:__imp_LocalAlloc
0x180068654  inc     ebx
0x180068656  mov     ecx, 40h ; '@'; uFlags
0x18006865b  movsxd  rdx, ebx
0x18006865e  mov     r15, rax
0x180068661  add     rdx, rdx; uBytes
0x180068664  call    cs:__imp_LocalAlloc
0x18006866a  mov     rcx, [rsi+60h]; hWnd
0x18006866e  mov     r8d, edi; nMaxCount
0x180068671  mov     rdx, r15; lpString
0x180068674  mov     [rsp+870h+lpString], rax
0x180068679  call    cs:__imp_GetWindowTextW
0x18006867f  mov     rdx, [rsp+870h+lpString]; lpString
0x180068684  mov     r8d, ebx; nMaxCount
0x180068687  mov     rcx, [rsi+68h]; hWnd
0x18006868b  call    cs:__imp_GetWindowTextW
0x180068691  xor     edi, edi
0x180068693  cmp     edi, 2
0x180068696  jnb     loc_18006875A
0x18006869c  mov     eax, edi
0x18006869e  neg     eax
0x1800686a0  sbb     rcx, rcx
0x1800686a3  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800686a7  mov     rbx, [rcx+rsi+48h]
0x1800686ac  test    rbx, rbx
0x1800686af  jnz     short loc_1800686D8
0x1800686b1  test    rbx, rbx
0x1800686b4  jz      short loc_1800686DD
0x1800686b6  mov     rcx, [rbx+8]
0x1800686ba  mov     rdx, r15
0x1800686bd  call    cs:__imp__o__wcsicmp
0x1800686c3  test    eax, eax
0x1800686c5  jg      short loc_1800686DD
0x1800686c7  mov     rcx, [rbx+8]
0x1800686cb  mov     rdx, r15
0x1800686ce  call    cs:__imp__o__wcsicmp
0x1800686d4  test    eax, eax
0x1800686d6  jz      short loc_1800686E1
0x1800686d8  mov     rbx, [rbx]
0x1800686db  jmp     short loc_1800686B1
0x1800686dd  inc     edi
0x1800686df  jmp     short loc_180068693
0x1800686e1  xor     edx, edx; Val
0x1800686e3  lea     rcx, [rsp+870h+String]; void *
0x1800686e8  mov     r8d, 400h; Size
0x1800686ee  call    memset_0
0x1800686f3  mov     r8d, 1FFh; nMaxCount
0x1800686f9  lea     rdx, [rsp+870h+String]; lpString
0x1800686fe  mov     rcx, r13; hWnd
0x180068701  call    cs:__imp_GetWindowTextW
0x180068707  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006870e  lea     r8, [rbp+770h+Buffer]; lpBuffer
0x180068715  mov     r9d, 200h; cchBufferMax
0x18006871b  mov     edx, 4C0h; uID
0x180068720  call    cs:__imp_LoadStringW
0x180068726  mov     r9d, 10h; uType
0x18006872c  lea     r8, [rsp+870h+String]; lpCaption
0x180068731  lea     rdx, [rbp+770h+Buffer]; lpText
0x180068738  mov     rcx, r13; hWnd
0x18006873b  call    cs:__imp_MessageBoxW
0x180068741  mov     rcx, r15; hMem
0x180068744  call    cs:__imp_LocalFree
0x18006874a  mov     rcx, [rsp+870h+lpString]; hMem
0x18006874f  call    cs:__imp_LocalFree
0x180068755  jmp     loc_1800685F6
0x18006875a  mov     edx, 30h ; '0'; uBytes
0x18006875f  lea     ecx, [rdx+10h]; uFlags
0x180068762  call    cs:__imp_LocalAlloc
0x180068768  mov     rbx, rax
0x18006876b  mov     [rax+8], r15
0x18006876f  mov     rax, [rsp+870h+lpString]
0x180068774  mov     rcx, rax; lpWideCharStr
0x180068777  mov     [rbx+10h], rax
0x18006877b  mov     dword ptr [rbx+20h], 1
0x180068782  call    ?StrdupWtoA@@YAPEADPEAG@Z; StrdupWtoA(ushort *)
0x180068787  mov     [rbx+18h], rax
0x18006878b  lea     rcx, [rsi+48h]; struct _EAPTLS_EKU_NODE **
0x18006878f  mov     rdx, rbx; struct _EAPTLS_EKU_NODE *
0x180068792  mov     [rsi+50h], rbx
0x180068796  call    ?SortedEKUInsert@@YAXPEAPEAU_EAPTLS_EKU_NODE@@PEAU1@@Z; SortedEKUInsert(_EAPTLS_EKU_NODE * *,_EAPTLS_EKU_NODE *)
0x18006879b  jmp     loc_1800685E8
0x1800687a0  mov     eax, 300h
0x1800687a5  cmp     ax, dx
0x1800687a8  jnz     loc_18006850B
0x1800687ae  xor     edx, edx; Val
0x1800687b0  lea     rcx, [rsp+870h+String]; void *
0x1800687b5  mov     r8d, 202h; Size
0x1800687bb  call    memset_0
0x1800687c0  xor     edx, edx; Val
0x1800687c2  lea     rcx, [rbp+770h+Buffer]; void *
0x1800687c9  mov     r8d, 402h; Size
0x1800687cf  call    memset_0
0x1800687d4  mov     rcx, [rsi+60h]; hWnd
0x1800687d8  lea     rdx, [rsp+870h+String]; lpString
0x1800687dd  mov     r8d, 101h; nMaxCount
0x1800687e3  call    cs:__imp_GetWindowTextW
0x1800687e9  mov     rcx, [rsi+68h]; hWnd
0x1800687ed  lea     rdx, [rbp+770h+Buffer]; lpString
0x1800687f4  mov     r8d, 201h; nMaxCount
0x1800687fa  call    cs:__imp_GetWindowTextW
0x180068800  or      r9, 0FFFFFFFFFFFFFFFFh
0x180068804  lea     rax, [rsp+870h+String]
0x180068809  mov     rdx, r9
0x18006880c  inc     rdx; unsigned int
0x18006880f  cmp     [rax+rdx*2], r15w
0x180068814  jnz     short loc_18006880C
0x180068816  lea     rcx, [rsp+870h+String]; unsigned __int16 *
0x18006881b  call    ?isValidEKUName@@YAHPEAGK@Z; isValidEKUName(ushort *,ulong)
0x180068820  test    eax, eax
0x180068822  jz      short loc_18006884F
0x180068824  lea     rax, [rbp+770h+Buffer]
0x18006882b  inc     r9
0x18006882e  cmp     [rax+r9*2], r15w
0x180068833  jnz     short loc_18006882B
0x180068835  mov     edx, r9d; unsigned int
0x180068838  lea     rcx, [rbp+770h+Buffer]; unsigned __int16 *
0x18006883f  call    ?isValidEKUOID@@YAHPEAGK@Z; isValidEKUOID(ushort *,ulong)
0x180068844  test    eax, eax
0x180068846  jz      short loc_18006884F
0x180068848  mov     edx, 1
0x18006884d  jmp     short loc_180068851
0x18006884f  xor     edx, edx; bEnable
0x180068851  mov     rcx, [rsi+70h]; hWnd
0x180068855  call    cs:__imp_EnableWindow
0x18006885b  jmp     loc_1800685F6
```
