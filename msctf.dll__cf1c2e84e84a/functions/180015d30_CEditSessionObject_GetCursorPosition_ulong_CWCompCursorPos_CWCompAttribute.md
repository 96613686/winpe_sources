# CEditSessionObject::_GetCursorPosition(ulong,CWCompCursorPos &,CWCompAttribute &)

- ea: `0x180015d30`
- end: `0x1800162a0`
- name: `?_GetCursorPosition@CEditSessionObject@@IEAAJKAEAVCWCompCursorPos@@AEAVCWCompAttribute@@@Z`
- size: `1392`
- prototype: `__int64 __fastcall(CEditSessionObject *__hidden this, unsigned int, struct CWCompCursorPos *, struct CWCompAttribute *)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012c64`
- `0x1800132a8`

## callees

- `0x180015850`
- `0x180015d30`
- `0x180016744`
- `0x1800185f0`
- `0x18001a460`
- `0x18001cc80`
- `0x180020ce0`
- `0x180044464`
- `0x18005db30`
- `0x18009ead2`
- `0x18009eaea`
- `0x1800e0c3c`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001601f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001601f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f9f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800160d6`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800160d6`
- `USER32!SendMessageW` at `0x1800160f1`
- `USER32!SendMessageW` at `0x1800160f1`
- `IMM32!ImmLockIMC` at `0x180015d9b`
- `IMM32!ImmLockIMC` at `0x180016096`
- `IMM32!ImmLockIMC` at `0x180015d9b`
- `IMM32!ImmLockIMC` at `0x180016096`
- `IMM32!ImmRequestMessageW` at `0x180016106`
- `IMM32!ImmRequestMessageW` at `0x180016106`
- `IMM32!ImmUnlockIMC` at `0x18001602e`
- `IMM32!ImmUnlockIMC` at `0x1800160c3`
- `IMM32!ImmUnlockIMC` at `0x180016114`
- `IMM32!ImmUnlockIMC` at `0x18001611f`
- `IMM32!ImmUnlockIMC` at `0x18001602e`
- `IMM32!ImmUnlockIMC` at `0x1800160c3`
- `IMM32!ImmUnlockIMC` at `0x180016114`
- `IMM32!ImmUnlockIMC` at `0x18001611f`
- `IMM32!ImmLockIMCC` at `0x180015de6`
- `IMM32!ImmLockIMCC` at `0x180015de6`
- `IMM32!ImmUnlockIMCC` at `0x180016015`
- `IMM32!ImmUnlockIMCC` at `0x180016015`
- `IMM32!ImmGetAppCompatFlags` at `0x180015eab`
- `IMM32!ImmGetAppCompatFlags` at `0x180016058`
- `IMM32!ImmGetAppCompatFlags` at `0x180015eab`
- `IMM32!ImmGetAppCompatFlags` at `0x180016058`

## pseudocode

```c
__int64 __fastcall CEditSessionObject::_GetCursorPosition(
        CEditSessionObject *this,
        unsigned int a2,
        struct CWCompCursorPos *a3,
        struct ITfRange *a4)
{
  HIMC v4; // r13
  int AllTextRange; // ebx
  LPINPUTCONTEXT v7; // rax
  HWND *p_hWnd; // r12
  HIMCC v9; // rax
  signed int v10; // esi
  __int64 *v11; // r15
  __int64 v12; // r15
  struct TLS *TLS; // rax
  __int64 v14; // rsi
  __int64 v15; // r13
  unsigned __int16 v16; // bx
  int v17; // esi
  LPARAM v18; // r13
  struct CWCompAttribute *v19; // r14
  __int64 v20; // rcx
  unsigned int v21; // esi
  struct ITfContext *v22; // rdx
  void *v23; // rcx
  SIZE_T v24; // rdx
  HLOCAL v25; // rax
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  _DWORD *v30; // rcx
  HIMC v31; // rcx
  int AppCompatFlags; // eax
  HIMC v34; // rsi
  LPINPUTCONTEXT v35; // rax
  int v36; // eax
  LRESULT v37; // rax
  HIMC v38; // rcx
  LRESULT v39; // rax
  HIMC v40; // rcx
  CEditSessionObject *v41; // rcx
  unsigned __int8 v42; // r8
  unsigned __int16 v43; // ax
  CEditSessionObject *v44; // rcx
  unsigned __int8 v45; // r8
  LPARAM v46; // [rsp+40h] [rbp-C0h] BYREF
  struct ITfRange *v47; // [rsp+48h] [rbp-B8h] BYREF
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v49; // [rsp+54h] [rbp-ACh]
  TF_HALTCOND v50; // [rsp+58h] [rbp-A8h] BYREF
  HIMC v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int128 v53; // [rsp+78h] [rbp-88h] BYREF
  void **v54; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v55; // [rsp+90h] [rbp-70h]
  HIMCC v56; // [rsp+98h] [rbp-68h]
  signed int v57; // [rsp+A0h] [rbp-60h]
  HIMCC v58; // [rsp+A8h] [rbp-58h]
  HIMC v59; // [rsp+B0h] [rbp-50h]
  _DWORD lParam[5]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v61; // [rsp+CCh] [rbp-34h]
  _BYTE v62[4]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v63; // [rsp+E4h] [rbp-1Ch]

  v4 = (HIMC)*((_QWORD *)this + 4);
  v47 = a4;
  v49 = a2;
  v46 = (LPARAM)this;
  AllTextRange = -2147467259;
  v59 = v4;
  *(_QWORD *)&v50.aHaltPos = 0;
  v51 = v4;
  v52 = 0;
  v50.pHaltRange = (ITfRange *)&IMCLock::`vftable';
  if ( !v4 )
    goto LABEL_4;
  v7 = ImmLockIMC(v4);
  *(_QWORD *)&v50.aHaltPos = v7;
  p_hWnd = &v7->hWnd;
  if ( !v7 )
  {
    LODWORD(v52) = -2147467259;
LABEL_4:
    IMCLock::~IMCLock((IMCLock *)&v50);
    return (unsigned int)AllTextRange;
  }
  v9 = *(HIMCC *)&v7[1].lfFont.W.lfWidth;
  v10 = 0;
  v58 = v9;
  v11 = 0;
  v55 = 0;
  v56 = v9;
  v57 = 0;
  if ( v9 )
  {
    v55 = (__int64 *)ImmLockIMCC(v9);
    v11 = v55;
    v10 = v55 == 0 ? 0x80004005 : 0;
    v57 = v10;
  }
  v54 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
  if ( v11 )
  {
    if ( v10 >= 0 )
    {
      v12 = *v11;
      if ( !v12 )
      {
LABEL_63:
        InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v54);
        goto LABEL_4;
      }
      TLS = TLS::GetTLS();
      if ( !TLS )
      {
        AllTextRange = -2147024882;
        goto LABEL_63;
      }
      v14 = *((_QWORD *)TLS + 1);
      if ( !v14 )
      {
        CicTrace(2u, "ImmIfEditSessionCallBack::_GetCursorPosition. _pProfile==NULL.");
        InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v54);
        if ( !p_hWnd )
          return (unsigned int)AllTextRange;
        v31 = v4;
        goto LABEL_42;
      }
      v15 = *(_QWORD *)(v14 + 8);
      v16 = 0;
      if ( v15 )
      {
        if ( (*(_BYTE *)(v14 + 24) & 2) != 0 )
        {
          v16 = *(_WORD *)(v14 + 32);
        }
        else
        {
          memset_0(v62, 0, 0x58u);
          if ( (*(int (__fastcall **)(__int64, GUID *, _BYTE *))(*(_QWORD *)v15 + 80LL))(
                 v15,
                 &GUID_TFCAT_TIP_KEYBOARD,
                 v62) < 0 )
          {
            CicTrace(2u, "CicProfile::GetLangId: failed for GetCurrentLanguage");
          }
          else
          {
            v43 = v63;
            *(_DWORD *)(v14 + 24) |= 2u;
            v16 = v43;
            *(_WORD *)(v14 + 32) = v43;
          }
        }
      }
      v17 = 0;
      if ( (*(_BYTE *)(v12 + 192) & 1) == 0 )
      {
LABEL_18:
        v18 = v46;
        if ( (ImmGetAppCompatFlags(*(_QWORD *)(v46 + 32)) & 0x5000000) != 0 && v17 != 2 )
        {
          v19 = (struct CWCompAttribute *)v47;
          if ( (unsigned int)MyMsimtfIsWindowFiltered(*p_hWnd) )
          {
            LODWORD(v46) = 0;
            if ( !(unsigned int)CEditSessionObject::_FindCompAttr(v44, (struct CWCompAttribute *)v47, v45, (int *)&v46) )
              goto LABEL_62;
          }
        }
        else
        {
          v19 = (struct CWCompAttribute *)v47;
        }
        if ( (v16 & 0x3FF) == 0x11 )
        {
          v40 = *(HIMC *)(v18 + 32);
          LODWORD(v46) = 0;
          UIComposition::SendMessageToUI(v40, 0x11u, (LPARAM)&v46);
          if ( (*(_BYTE *)(v12 + 192) & 1) != 0 && (_DWORD)v46 == 3 && v17 == 1 )
          {
            LODWORD(v46) = 0;
            if ( !(unsigned int)CEditSessionObject::_FindCompAttr(v41, v19, v42, (int *)&v46) )
            {
LABEL_62:
              CompData<unsigned long>::SetAtZero(a3, (unsigned int)v46);
              AllTextRange = 0;
              goto LABEL_63;
            }
          }
        }
        v20 = *(_QWORD *)(v18 + 8);
        v21 = v49;
        v48 = 0;
        v53 = 0;
        AllTextRange = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, int *))(*(_QWORD *)v20 + 40LL))(
                         v20,
                         v49,
                         0xFFFFFFFFLL,
                         1,
                         &v53,
                         &v48);
        if ( AllTextRange < 0 )
          goto LABEL_37;
        v22 = *(struct ITfContext **)(v18 + 8);
        v50.pHaltRange = (ITfRange *)v53;
        v47 = 0;
        LODWORD(v46) = 0;
        v50.dwFlags = 0;
        v50.aHaltPos = DWORD2(v53) != 1;
        AllTextRange = CEditSessionObject::GetAllTextRange(v21, v22, &v47, (int *)&v46, &v50);
        if ( AllTextRange < 0 )
        {
LABEL_35:
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v53 + 16LL))(v53);
          if ( v47 )
            ((void (__fastcall *)(struct ITfRange *))v47->lpVtbl->Release)(v47);
LABEL_37:
          if ( v55 )
          {
            if ( !ImmUnlockIMCC(v58) )
              GetLastError();
          }
          if ( !p_hWnd )
            return (unsigned int)AllTextRange;
          v31 = v59;
LABEL_42:
          ImmUnlockIMC(v31);
          return (unsigned int)AllTextRange;
        }
        if ( *((_DWORD *)a3 + 4) )
        {
          v30 = (_DWORD *)*((_QWORD *)a3 + 1);
        }
        else
        {
          if ( *((int *)a3 + 6) >= 1 )
          {
LABEL_30:
            v26 = *((_DWORD *)a3 + 4);
            if ( v26 > 0 )
              memmove_0(
                (void *)(*((_QWORD *)a3 + 1) + *((int *)a3 + 5)),
                *((const void **)a3 + 1),
                *((_DWORD *)a3 + 5) * v26);
            v27 = *((_DWORD *)a3 + 4);
            v28 = v27 + 1;
            v29 = *((_DWORD *)a3 + 5) * v27;
            *((_DWORD *)a3 + 4) = v28;
            v30 = (_DWORD *)(*((_QWORD *)a3 + 1) + v29);
            goto LABEL_33;
          }
          v23 = (void *)*((_QWORD *)a3 + 1);
          v24 = *((unsigned int *)a3 + 5);
          if ( v23 )
            v25 = LocalReAlloc(v23, v24, 0x42u);
          else
            v25 = LocalAlloc(0, v24);
          if ( v25 )
          {
            *((_QWORD *)a3 + 1) = v25;
            *((_DWORD *)a3 + 6) = 1;
            goto LABEL_30;
          }
          v30 = 0;
        }
LABEL_33:
        if ( v30 )
          *v30 = v46;
        goto LABEL_35;
      }
      CicTrace(8u, "CicInputContext::InquireIMECharPosition langid=0x%08x, m_fQueryPos=%d", v16, *(_DWORD *)(v12 + 152));
      if ( *(_DWORD *)(v12 + 152)
        || (AppCompatFlags = ImmGetAppCompatFlags(0), (v16 & 0x3FF) == 0x12) && (AppCompatFlags & 0xD000000) == 0 )
      {
LABEL_17:
        v17 = *(_DWORD *)(v12 + 152);
        goto LABEL_18;
      }
      v34 = *(HIMC *)(v12 + 32);
      lParam[0] = 36;
      *(_OWORD *)&lParam[1] = 0;
      v61 = 0;
      if ( v34 )
      {
        v35 = ImmLockIMC(v34);
        if ( v35 )
        {
          v37 = SendMessageW(v35->hWnd, WM_MSIME_QUERYPOSITION, 1u, (LPARAM)lParam);
          v38 = v34;
          if ( v37 || (v39 = ImmRequestMessageW(v34, 6u, (LPARAM)lParam), v38 = v34, v39) )
          {
            ImmUnlockIMC(v38);
            v36 = 2;
            goto LABEL_48;
          }
          ImmUnlockIMC(v34);
        }
      }
      v36 = 1;
LABEL_48:
      *(_DWORD *)(v12 + 152) = v36;
      goto LABEL_17;
    }
  }
  else
  {
    v10 = -2147467259;
  }
  InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v54);
  if ( p_hWnd )
    ImmUnlockIMC(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180015d30  push    rbp
0x180015d32  push    rbx
0x180015d33  push    rsi
0x180015d34  push    rdi
0x180015d35  push    r12
0x180015d37  push    r13
0x180015d39  push    r14
0x180015d3b  push    r15
0x180015d3d  lea     rbp, [rsp-58h]
0x180015d42  sub     rsp, 158h
0x180015d49  mov     rax, cs:__security_cookie
0x180015d50  xor     rax, rsp
0x180015d53  mov     [rbp+90h+var_50], rax
0x180015d57  mov     r13, [rcx+20h]
0x180015d5b  lea     rax, ??_7IMCLock@@6B@; const IMCLock::`vftable'
0x180015d62  xor     r14d, r14d
0x180015d65  mov     [rsp+190h+var_148], r9
0x180015d6a  mov     [rsp+190h+var_13C], edx
0x180015d6e  mov     rdi, r8
0x180015d71  mov     [rsp+190h+var_150], rcx
0x180015d76  mov     ebx, 80004005h
0x180015d7b  mov     [rbp+90h+var_E0], r13
0x180015d7f  mov     qword ptr [rsp+190h+var_138.aHaltPos], r14
0x180015d84  mov     [rsp+190h+var_128], r13
0x180015d89  mov     [rsp+190h+var_120], r14
0x180015d8e  mov     [rsp+190h+var_138.pHaltRange], rax
0x180015d93  test    r13, r13
0x180015d96  jz      short loc_180015DB2
0x180015d98  mov     rcx, r13; HIMC
0x180015d9b  call    cs:__imp_ImmLockIMC
0x180015da1  mov     qword ptr [rsp+190h+var_138.aHaltPos], rax
0x180015da6  mov     r12, rax
0x180015da9  test    rax, rax
0x180015dac  jnz     short loc_180015DC1
0x180015dae  mov     dword ptr [rsp+190h+var_120], ebx
0x180015db2  lea     rcx, [rsp+190h+var_138]; this
0x180015db7  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x180015dbc  jmp     loc_180016034
0x180015dc1  mov     rax, [rax+188h]
0x180015dc8  mov     esi, r14d
0x180015dcb  mov     [rbp+90h+var_E8], rax
0x180015dcf  mov     r15, r14
0x180015dd2  mov     [rbp+90h+var_100], r14
0x180015dd6  mov     [rbp+90h+var_F8], rax
0x180015dda  mov     [rbp+90h+var_F0], r14d
0x180015dde  test    rax, rax
0x180015de1  jz      short loc_180015E02
0x180015de3  mov     rcx, rax; HIMCC
0x180015de6  call    cs:__imp_ImmLockIMCC
0x180015dec  mov     rcx, rax
0x180015def  mov     [rbp+90h+var_100], rax
0x180015df3  neg     rcx
0x180015df6  mov     r15, rax
0x180015df9  sbb     esi, esi
0x180015dfb  not     esi
0x180015dfd  and     esi, ebx
0x180015dff  mov     [rbp+90h+var_F0], esi
0x180015e02  lea     rax, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x180015e09  mov     [rbp+90h+var_108], rax
0x180015e0d  test    r15, r15
0x180015e10  jz      loc_1800160B0
0x180015e16  test    esi, esi
0x180015e18  js      loc_1800160B2
0x180015e1e  mov     r15, [r15]
0x180015e21  test    r15, r15
0x180015e24  jz      loc_18001618D
0x180015e2a  call    ?GetTLS@TLS@@SAPEAV1@XZ; TLS::GetTLS(void)
0x180015e2f  test    rax, rax
0x180015e32  jz      loc_180016263
0x180015e38  mov     rsi, [rax+8]
0x180015e3c  test    rsi, rsi
0x180015e3f  jz      loc_180016219
0x180015e45  mov     r13, [rsi+8]
0x180015e49  mov     ebx, r14d
0x180015e4c  mov     r14d, 2
0x180015e52  test    r13, r13
0x180015e55  jz      short loc_180015E65
0x180015e57  test    [rsi+18h], r14b
0x180015e5b  jz      loc_18001619B
0x180015e61  movzx   ebx, word ptr [rsi+20h]
0x180015e65  xor     esi, esi
0x180015e67  lea     r13d, [rsi+1]
0x180015e6b  test    [r15+0C0h], r13b
0x180015e72  jz      short loc_180015EA2
0x180015e74  mov     r9d, [r15+98h]
0x180015e7b  lea     rdx, aCicinputcontex_30; "CicInputContext::InquireIMECharPosition"...
0x180015e82  movzx   r8d, bx
0x180015e86  lea     ecx, [rsi+8]; unsigned int
0x180015e89  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180015e8e  cmp     [r15+98h], esi
0x180015e95  jz      loc_180016056
0x180015e9b  mov     esi, [r15+98h]
0x180015ea2  mov     r13, [rsp+190h+var_150]
0x180015ea7  mov     rcx, [r13+20h]
0x180015eab  call    cs:__imp_ImmGetAppCompatFlags
0x180015eb1  test    eax, 5000000h
0x180015eb6  jz      short loc_180015EC1
0x180015eb8  cmp     esi, r14d
0x180015ebb  jnz     loc_1800161E1
0x180015ec1  mov     r14, [rsp+190h+var_148]
0x180015ec6  mov     eax, 3FFh
0x180015ecb  mov     edx, 11h; wParam
0x180015ed0  and     bx, ax
0x180015ed3  cmp     bx, dx
0x180015ed6  jz      loc_18001612A
0x180015edc  mov     rcx, [r13+8]
0x180015ee0  lea     rdx, [rsp+190h+var_140]
0x180015ee5  mov     esi, [rsp+190h+var_13C]
0x180015ee9  xorps   xmm0, xmm0
0x180015eec  mov     [rsp+190h+var_168], rdx
0x180015ef1  mov     r9d, 1
0x180015ef7  lea     rdx, [rsp+190h+var_118]
0x180015efc  mov     [rsp+190h+var_140], 0
0x180015f04  movups  [rsp+190h+var_118], xmm0
0x180015f09  mov     rax, [rcx]
0x180015f0c  or      r8d, 0FFFFFFFFh
0x180015f10  mov     [rsp+190h+var_170], rdx
0x180015f15  mov     edx, esi
0x180015f17  mov     rax, [rax+28h]
0x180015f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f20  mov     ebx, eax
0x180015f22  test    eax, eax
0x180015f24  js      loc_18001600A
0x180015f2a  mov     rax, qword ptr [rsp+190h+var_118]
0x180015f2f  lea     r9, [rsp+190h+var_150]; int *
0x180015f34  mov     rdx, [r13+8]; struct ITfContext *
0x180015f38  lea     r8, [rsp+190h+var_148]; struct ITfRange **
0x180015f3d  mov     [rsp+190h+var_138.pHaltRange], rax
0x180015f42  mov     ecx, esi; unsigned int
0x180015f44  xor     eax, eax
0x180015f46  mov     [rsp+190h+var_148], 0
0x180015f4f  cmp     dword ptr [rbp+90h+var_118+8], 1
0x180015f53  mov     dword ptr [rsp+190h+var_150], 0
0x180015f5b  setnz   al
0x180015f5e  mov     [rsp+190h+var_138.dwFlags], 0
0x180015f66  mov     [rsp+190h+var_138.aHaltPos], eax
0x180015f6a  lea     rax, [rsp+190h+var_138]
0x180015f6f  mov     [rsp+190h+var_170], rax; struct TF_HALTCOND *
0x180015f74  call    ?GetAllTextRange@CEditSessionObject@@SAJKPEAUITfContext@@PEAPEAUITfRange@@PEAJPEAUTF_HALTCOND@@@Z; CEditSessionObject::GetAllTextRange(ulong,ITfContext *,ITfRange * *,long *,TF_HALTCOND *)
0x180015f79  mov     ebx, eax
0x180015f7b  test    eax, eax
0x180015f7d  js      short loc_180015FE3
0x180015f7f  cmp     dword ptr [rdi+10h], 0
0x180015f83  jnz     loc_180016244
0x180015f89  cmp     dword ptr [rdi+18h], 1
0x180015f8d  jge     short loc_180015FB9
0x180015f8f  mov     rcx, [rdi+8]; hMem
0x180015f93  mov     edx, [rdi+14h]; uBytes
0x180015f96  test    rcx, rcx
0x180015f99  jnz     loc_1800160D0
0x180015f9f  call    cs:__imp_LocalAlloc
0x180015fa5  test    rax, rax
0x180015fa8  jz      loc_18001627D
0x180015fae  mov     [rdi+8], rax
0x180015fb2  mov     dword ptr [rdi+18h], 1
0x180015fb9  mov     eax, [rdi+10h]
0x180015fbc  test    eax, eax
0x180015fbe  jg      loc_180016284
0x180015fc4  mov     ecx, [rdi+10h]
0x180015fc7  lea     eax, [rcx+1]
0x180015fca  imul    ecx, [rdi+14h]
0x180015fce  mov     [rdi+10h], eax
0x180015fd1  movsxd  rcx, ecx
0x180015fd4  add     rcx, [rdi+8]
0x180015fd8  test    rcx, rcx
0x180015fdb  jz      short loc_180015FE3
0x180015fdd  mov     eax, dword ptr [rsp+190h+var_150]
0x180015fe1  mov     [rcx], eax
0x180015fe3  mov     rcx, qword ptr [rsp+190h+var_118]
0x180015fe8  mov     rax, [rcx]
0x180015feb  mov     rax, [rax+10h]
0x180015fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ff4  mov     rcx, [rsp+190h+var_148]
0x180015ff9  test    rcx, rcx
0x180015ffc  jz      short loc_18001600A
0x180015ffe  mov     rax, [rcx]
0x180016001  mov     rax, [rax+10h]
0x180016005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001600a  cmp     [rbp+90h+var_100], 0
0x18001600f  jz      short loc_180016025
0x180016011  mov     rcx, [rbp+90h+var_E8]; HIMCC
0x180016015  call    cs:__imp_ImmUnlockIMCC
0x18001601b  test    eax, eax
0x18001601d  jnz     short loc_180016025
0x18001601f  call    cs:__imp_GetLastError
0x180016025  test    r12, r12
0x180016028  jz      short loc_180016034
0x18001602a  mov     rcx, [rbp+90h+var_E0]; HIMC
0x18001602e  call    cs:__imp_ImmUnlockIMC
0x180016034  mov     eax, ebx
0x180016036  mov     rcx, [rbp+90h+var_50]
0x18001603a  xor     rcx, rsp; StackCookie
0x18001603d  call    __security_check_cookie
0x180016042  add     rsp, 158h
0x180016049  pop     r15
0x18001604b  pop     r14
0x18001604d  pop     r13
0x18001604f  pop     r12
0x180016051  pop     rdi
0x180016052  pop     rsi
0x180016053  pop     rbx
0x180016054  pop     rbp
0x180016055  retn
0x180016056  xor     ecx, ecx
0x180016058  call    cs:__imp_ImmGetAppCompatFlags
0x18001605e  movzx   ecx, bx
0x180016061  mov     edx, 3FFh
0x180016066  and     cx, dx
0x180016069  cmp     cx, 12h
0x18001606d  jz      loc_18001626D
0x180016073  mov     rsi, [r15+20h]
0x180016077  xorps   xmm0, xmm0
0x18001607a  mov     dword ptr [rbp+90h+lParam], 24h ; '$'
0x180016081  xorps   xmm1, xmm1
0x180016084  movdqu  xmmword ptr [rbp+90h+lParam+4], xmm0
0x180016089  movdqu  [rbp+90h+var_C4], xmm1
0x18001608e  test    rsi, rsi
0x180016091  jz      short loc_1800160A1
0x180016093  mov     rcx, rsi; HIMC
0x180016096  call    cs:__imp_ImmLockIMC
0x18001609c  test    rax, rax
0x18001609f  jnz     short loc_1800160E1
0x1800160a1  mov     eax, r13d
0x1800160a4  mov     [r15+98h], eax
0x1800160ab  jmp     loc_180015E9B
0x1800160b0  mov     esi, ebx
0x1800160b2  lea     rcx, [rbp+90h+var_108]; this
0x1800160b6  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x1800160bb  test    r12, r12
0x1800160be  jz      short loc_1800160C9
0x1800160c0  mov     rcx, r13; HIMC
0x1800160c3  call    cs:__imp_ImmUnlockIMC
0x1800160c9  mov     eax, esi
0x1800160cb  jmp     loc_180016036
0x1800160d0  mov     r8d, 42h ; 'B'; uFlags
0x1800160d6  call    cs:__imp_LocalReAlloc
0x1800160dc  jmp     loc_180015FA5
0x1800160e1  mov     edx, cs:?WM_MSIME_QUERYPOSITION@@3IA; Msg
0x1800160e7  lea     r9, [rbp+90h+lParam]; lParam
0x1800160eb  mov     rcx, [rax]; hWnd
0x1800160ee  mov     r8, r13; wParam
0x1800160f1  call    cs:__imp_SendMessageW
0x1800160f7  mov     rcx, rsi; HIMC
0x1800160fa  test    rax, rax
0x1800160fd  jnz     short loc_180016114
0x1800160ff  lea     r8, [rbp+90h+lParam]; LPARAM
0x180016103  lea     edx, [rax+6]; WPARAM
0x180016106  call    cs:__imp_ImmRequestMessageW
0x18001610c  mov     rcx, rsi; HIMC
0x18001610f  test    rax, rax
0x180016112  jz      short loc_18001611F
0x180016114  call    cs:__imp_ImmUnlockIMC
0x18001611a  mov     eax, r14d
0x18001611d  jmp     short loc_1800160A4
0x18001611f  call    cs:__imp_ImmUnlockIMC
0x180016125  jmp     loc_1800160A1
0x18001612a  mov     rcx, [r13+20h]; HIMC
0x18001612e  lea     r8, [rsp+190h+var_150]; lParam
0x180016133  mov     dword ptr [rsp+190h+var_150], 0
0x18001613b  call    ?SendMessageToUI@UIComposition@@CAJPEAUHIMC__@@_K_J@Z; UIComposition::SendMessageToUI(HIMC__ *,unsigned __int64,__int64)
0x180016140  test    byte ptr [r15+0C0h], 1
0x180016148  jz      loc_180015EDC
0x18001614e  cmp     dword ptr [rsp+190h+var_150], 3
0x180016153  jnz     loc_180015EDC
0x180016159  cmp     esi, 1
0x18001615c  jnz     loc_180015EDC
0x180016162  lea     r9, [rsp+190h+var_150]; int *
0x180016167  mov     dword ptr [rsp+190h+var_150], 0
0x18001616f  mov     rdx, r14; struct CWCompAttribute *
0x180016172  call    ?_FindCompAttr@CEditSessionObject@@AEAAJAEAVCWCompAttribute@@EPEAH@Z; CEditSessionObject::_FindCompAttr(CWCompAttribute &,uchar,int *)
0x180016177  test    eax, eax
0x180016179  jnz     loc_180015EDC
0x18001617f  mov     edx, dword ptr [rsp+190h+var_150]
0x180016183  mov     rcx, rdi
0x180016186  call    ?SetAtZero@?$CompData@K@@QEAAXK@Z; CompData<ulong>::SetAtZero(ulong)
0x18001618b  xor     ebx, ebx
0x18001618d  lea     rcx, [rbp+90h+var_108]; this
0x180016191  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x180016196  jmp     loc_180015DB2
0x18001619b  xor     edx, edx; Val
0x18001619d  lea     rcx, [rbp+90h+var_B0]; void *
0x1800161a1  lea     r8d, [rdx+58h]; Size
0x1800161a5  call    memset_0
0x1800161aa  mov     rax, [r13+0]
0x1800161ae  lea     r8, [rbp+90h+var_B0]
0x1800161b2  lea     rdx, GUID_TFCAT_TIP_KEYBOARD
0x1800161b9  mov     rcx, r13
0x1800161bc  mov     rax, [rax+50h]
0x1800161c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161c5  test    eax, eax
0x1800161c7  js      loc_18001624D
0x1800161cd  movzx   eax, [rbp+90h+var_AC]
0x1800161d1  or      [rsi+18h], r14d
0x1800161d5  movzx   ebx, ax
0x1800161d8  mov     [rsi+20h], ax
0x1800161dc  jmp     loc_180015E65
0x1800161e1  mov     rcx, [r12]; HWND
0x1800161e5  call    ?MyMsimtfIsWindowFiltered@@YAHPEAUHWND__@@@Z; MyMsimtfIsWindowFiltered(HWND__ *)
0x1800161ea  mov     r14, [rsp+190h+var_148]
0x1800161ef  test    eax, eax
  ... truncated ...
```
