# CPropAdvanced::InitUserAuthenticationSection(void)

- ea: `0x14004760c`
- end: `0x140047b14`
- name: `?InitUserAuthenticationSection@CPropAdvanced@@AEAAHXZ`
- size: `1288`
- prototype: `__int64 __fastcall(CPropAdvanced *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140047bd4`

## callees

- `0x140004703`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e158`
- `0x14004760c`
- `0x140047f1c`
- `0x14004839c`
- `0x1400fcad0`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!GetWindowTextW` at `0x1400477d4`
- `USER32!GetWindowTextW` at `0x1400477d4`
- `USER32!ShowWindow` at `0x140047a22`
- `USER32!ShowWindow` at `0x140047a22`
- `USER32!GetDlgItem` at `0x1400476d2`
- `USER32!GetDlgItem` at `0x140047a10`
- `USER32!GetDlgItem` at `0x1400476d2`
- `USER32!GetDlgItem` at `0x140047a10`
- `KERNEL32!GetLastError` at `0x140047659`
- `KERNEL32!GetLastError` at `0x140047799`
- `KERNEL32!GetLastError` at `0x140047802`
- `KERNEL32!GetLastError` at `0x1400479a4`
- `KERNEL32!GetLastError` at `0x140047a57`
- `KERNEL32!GetLastError` at `0x140047aa5`
- `KERNEL32!GetLastError` at `0x140047659`
- `KERNEL32!GetLastError` at `0x140047799`
- `KERNEL32!GetLastError` at `0x140047802`
- `KERNEL32!GetLastError` at `0x1400479a4`
- `KERNEL32!GetLastError` at `0x140047a57`
- `KERNEL32!GetLastError` at `0x140047aa5`
- `ole32!CoCreateInstance` at `0x140047707`
- `ole32!CoCreateInstance` at `0x140047707`

## string_xrefs

- `0x140047883`: `String concatination for user authentication accessible name failed!`
- `0x140047939`: `Failed to set User Authentication section accessible name`

## pseudocode

```c
__int64 __fastcall CPropAdvanced::InitUserAuthenticationSection(CPropAdvanced *this)
{
  unsigned int v2; // r12d
  DWORD v3; // r14d
  unsigned int v4; // eax
  HWND *v5; // rax
  HWND *v6; // r13
  HWND v7; // rcx
  HWND DlgItem; // r14
  DWORD v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  int v12; // eax
  char v13; // bl
  unsigned int v14; // eax
  LPVOID v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  char v18; // bl
  unsigned int v19; // eax
  LPVOID v20; // rcx
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int *v23; // r14
  int v24; // r13d
  HWND v25; // rax
  DWORD v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  DWORD v30; // ebx
  unsigned int v31; // eax
  int nCmdShow; // [rsp+40h] [rbp-C0h]
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  GUID v35; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v36[3]; // [rsp+60h] [rbp-A0h] BYREF
  char v37; // [rsp+6Ch] [rbp-94h] BYREF
  WCHAR String; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[526]; // [rsp+72h] [rbp-8Eh] BYREF
  unsigned __int16 v40; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v41[526]; // [rsp+282h] [rbp+182h] BYREF
  unsigned __int16 v42; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v43[526]; // [rsp+492h] [rbp+392h] BYREF

  v2 = 0;
  if ( (unsigned int)CPropAdvanced::SetUserAuthenticationCheckbox(this, *(_DWORD *)(*(_QWORD *)this + 30692LL) != 0) )
  {
    v6 = (HWND *)((char *)this + 40);
    nCmdShow = 5;
    v7 = (HWND)*((_QWORD *)this + 5);
    *(_QWORD *)&v35.Data1 = (char *)this + 40;
    DlgItem = GetDlgItem(v7, 15052);
    if ( !DlgItem )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_b2859179a69931166002029bec6a3d1f_Traceguids,
          CurrentThreadActivityIdPrefix,
          15050,
          LastError);
      }
      goto LABEL_38;
    }
    ppv = 0;
    if ( CoCreateInstance(&CLSID_AccPropServices, 0, 0x15u, &GUID_6e26e776_04f0_495d_80e4_3330352e3169, &ppv) >= 0 )
    {
      v40 = 0;
      memset_0(v41, 0, 0x206u);
      v42 = 0;
      memset_0(v43, 0, 0x206u);
      if ( TSLoadString(*((HINSTANCE *)this + 4), 0x3AC2u, &v40, 260) )
      {
        String = 0;
        memset_0(v39, 0, 0x206u);
        if ( GetWindowTextW(DlgItem, &String, 520) )
        {
          v12 = StringCchPrintfW(&v42, 0x104u, (size_t *)L"%s %s", &v40, &String);
          v13 = v12;
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                (unsigned int)&WPP_b2859179a69931166002029bec6a3d1f_Traceguids,
                v14,
                (__int64)"String concatination for user authentication accessible name failed!",
                v13);
            }
            v15 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
            }
            goto LABEL_39;
          }
          v16 = *(_QWORD *)ppv;
          v35 = PROPID_ACC_NAME;
          v17 = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64, _QWORD, GUID *, unsigned __int16 *))(v16 + 56))(
                  ppv,
                  DlgItem,
                  4294967292LL,
                  0,
                  &v35,
                  &v42);
          v18 = v17;
          if ( v17 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              (unsigned int)&WPP_b2859179a69931166002029bec6a3d1f_Traceguids,
              v19,
              (__int64)"Failed to set User Authentication section accessible name",
              v18);
          }
          goto LABEL_32;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = GetLastError();
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          v11 = 25;
          goto LABEL_19;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = GetLastError();
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 24;
LABEL_19:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_b2859179a69931166002029bec6a3d1f_Traceguids, v10, v9);
      }
    }
LABEL_32:
    v20 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
LABEL_38:
    v2 = 1;
    *(_QWORD *)&v35.Data1 = v6;
LABEL_39:
    v5 = v6;
    goto LABEL_40;
  }
  nCmdShow = 0;
  v3 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_b2859179a69931166002029bec6a3d1f_Traceguids, v4, v3);
  }
  v5 = (HWND *)((char *)this + 40);
  *(_QWORD *)&v35.Data1 = (char *)this + 40;
LABEL_40:
  v36[0] = 15050;
  v23 = v36;
  v36[1] = 15051;
  v36[2] = 15052;
  do
  {
    v24 = *v23;
    v25 = GetDlgItem(*v5, *v23);
    if ( v25 )
    {
      if ( !ShowWindow(v25, nCmdShow) )
      {
        v2 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = GetLastError();
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DddD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v29, v27, v24, nCmdShow, v26);
        }
      }
    }
    else
    {
      v2 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = GetLastError();
        v31 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          &WPP_b2859179a69931166002029bec6a3d1f_Traceguids,
          v31,
          v24,
          v30);
      }
    }
    ++v23;
    v5 = *(HWND **)&v35.Data1;
  }
  while ( v23 != (int *)&v37 );
  return v2;
}

```

## disassembly

```asm
0x14004760c  push    rbp
0x14004760e  push    rbx
0x14004760f  push    rsi
0x140047610  push    r12
0x140047612  push    r13
0x140047614  push    r14
0x140047616  lea     rbp, [rsp-5B8h]
0x14004761e  sub     rsp, 6B8h
0x140047625  mov     rax, cs:__security_cookie
0x14004762c  xor     rax, rsp
0x14004762f  mov     [rbp+5E0h+var_40], rax
0x140047636  mov     rax, [rcx]
0x140047639  xor     esi, esi
0x14004763b  mov     edx, esi
0x14004763d  mov     rbx, rcx
0x140047640  mov     r12d, esi
0x140047643  cmp     [rax+77E4h], esi
0x140047649  setnz   dl; unsigned int
0x14004764c  call    ?SetUserAuthenticationCheckbox@CPropAdvanced@@AEAAHK@Z; CPropAdvanced::SetUserAuthenticationCheckbox(ulong)
0x140047651  test    eax, eax
0x140047653  jnz     short loc_1400476B8
0x140047655  mov     [rsp+6E0h+nCmdShow], esi
0x140047659  call    cs:__imp_GetLastError
0x14004765f  mov     r14d, eax
0x140047662  mov     rcx, cs:WPP_GLOBAL_Control
0x140047669  lea     rsi, WPP_GLOBAL_Control
0x140047670  cmp     rcx, rsi
0x140047673  jz      short loc_1400476AA
0x140047675  test    byte ptr [rcx+1Ch], 8
0x140047679  jz      short loc_1400476AA
0x14004767b  cmp     byte ptr [rcx+19h], 2
0x14004767f  jb      short loc_1400476AA
0x140047681  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140047686  mov     rcx, cs:WPP_GLOBAL_Control
0x14004768d  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x140047694  mov     edx, 17h
0x140047699  mov     dword ptr [rsp+6E0h+ppv], r14d
0x14004769e  mov     r9d, eax
0x1400476a1  mov     rcx, [rcx+10h]
0x1400476a5  call    WPP_SF_Dd
0x1400476aa  lea     rax, [rbx+28h]
0x1400476ae  mov     qword ptr [rsp+6E0h+var_690], rax
0x1400476b3  jmp     loc_1400479EA
0x1400476b8  lea     r13, [rbx+28h]
0x1400476bc  mov     [rsp+6E0h+nCmdShow], 5
0x1400476c4  mov     rcx, [r13+0]; hDlg
0x1400476c8  mov     edx, 3ACCh; nIDDlgItem
0x1400476cd  mov     qword ptr [rsp+6E0h+var_690], r13
0x1400476d2  call    cs:__imp_GetDlgItem
0x1400476d8  mov     r14, rax
0x1400476db  test    rax, rax
0x1400476de  jz      loc_140047985
0x1400476e4  xor     edx, edx; pUnkOuter
0x1400476e6  mov     [rsp+6E0h+var_698], rsi
0x1400476eb  lea     rax, [rsp+6E0h+var_698]
0x1400476f0  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x1400476f7  mov     [rsp+6E0h+ppv], rax; ppv
0x1400476fc  lea     rcx, CLSID_AccPropServices; rclsid
0x140047703  lea     r8d, [rdx+15h]; dwClsContext
0x140047707  call    cs:__imp_CoCreateInstance
0x14004770d  lea     rsi, WPP_GLOBAL_Control
0x140047714  test    eax, eax
0x140047716  js      loc_140047968
0x14004771c  xor     eax, eax
0x14004771e  lea     rcx, [rbp+5E0h+var_45E]; void *
0x140047725  xor     edx, edx; Val
0x140047727  mov     [rbp+5E0h+var_460], ax
0x14004772e  mov     r8d, 206h; Size
0x140047734  call    memset_0
0x140047739  xor     eax, eax
0x14004773b  lea     rcx, [rbp+5E0h+var_24E]; void *
0x140047742  xor     edx, edx; Val
0x140047744  mov     [rbp+5E0h+var_250], ax
0x14004774b  mov     r8d, 206h; Size
0x140047751  call    memset_0
0x140047756  mov     rcx, [rbx+20h]; HINSTANCE
0x14004775a  lea     r8, [rbp+5E0h+var_460]; unsigned __int16 *
0x140047761  mov     r9d, 104h; int
0x140047767  mov     edx, 3AC2h; unsigned int
0x14004776c  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140047771  test    eax, eax
0x140047773  jnz     short loc_1400477AD
0x140047775  mov     rax, cs:WPP_GLOBAL_Control
0x14004777c  cmp     rax, rsi
0x14004777f  jz      loc_140047968
0x140047785  test    byte ptr [rax+1Ch], 1
0x140047789  jz      loc_140047968
0x14004778f  cmp     byte ptr [rax+19h], 2
0x140047793  jb      loc_140047968
0x140047799  call    cs:__imp_GetLastError
0x14004779f  mov     ebx, eax
0x1400477a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400477a6  mov     edx, 18h
0x1400477ab  jmp     short loc_140047814
0x1400477ad  xor     eax, eax
0x1400477af  lea     rcx, [rsp+6E0h+var_66E]; void *
0x1400477b4  xor     edx, edx; Val
0x1400477b6  mov     [rsp+6E0h+String], ax
0x1400477bb  mov     r8d, 206h; Size
0x1400477c1  call    memset_0
0x1400477c6  mov     r8d, 208h; nMaxCount
0x1400477cc  lea     rdx, [rsp+6E0h+String]; lpString
0x1400477d1  mov     rcx, r14; hWnd
0x1400477d4  call    cs:__imp_GetWindowTextW
0x1400477da  test    eax, eax
0x1400477dc  jnz     short loc_140047837
0x1400477de  mov     rax, cs:WPP_GLOBAL_Control
0x1400477e5  cmp     rax, rsi
0x1400477e8  jz      loc_140047968
0x1400477ee  test    byte ptr [rax+1Ch], 1
0x1400477f2  jz      loc_140047968
0x1400477f8  cmp     byte ptr [rax+19h], 2
0x1400477fc  jb      loc_140047968
0x140047802  call    cs:__imp_GetLastError
0x140047808  mov     ebx, eax
0x14004780a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004780f  mov     edx, 19h
0x140047814  mov     rcx, cs:WPP_GLOBAL_Control
0x14004781b  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x140047822  mov     r9d, eax
0x140047825  mov     dword ptr [rsp+6E0h+ppv], ebx
0x140047829  mov     rcx, [rcx+10h]
0x14004782d  call    WPP_SF_Dd
0x140047832  jmp     loc_140047968
0x140047837  lea     rax, [rsp+6E0h+String]
0x14004783c  mov     edx, 104h; unsigned __int64
0x140047841  lea     r9, [rbp+5E0h+var_460]
0x140047848  mov     [rsp+6E0h+ppv], rax
0x14004784d  lea     r8, aSS_2; "%s %s"
0x140047854  lea     rcx, [rbp+5E0h+var_250]; unsigned __int16 *
0x14004785b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140047860  mov     ebx, eax
0x140047862  test    eax, eax
0x140047864  jns     short loc_1400478D6
0x140047866  mov     rcx, cs:WPP_GLOBAL_Control
0x14004786d  cmp     rcx, rsi
0x140047870  jz      short loc_1400478B2
0x140047872  test    byte ptr [rcx+1Ch], 8
0x140047876  jz      short loc_1400478B2
0x140047878  cmp     byte ptr [rcx+19h], 2
0x14004787c  jb      short loc_1400478B2
0x14004787e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140047883  lea     rcx, aStringConcatin; "String concatination for user authentic"...
0x14004788a  mov     dword ptr [rsp+6E0h+var_6B8], ebx
0x14004788e  mov     [rsp+6E0h+ppv], rcx
0x140047893  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x14004789a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400478a1  mov     edx, 1Ah
0x1400478a6  mov     r9d, eax
0x1400478a9  mov     rcx, [rcx+10h]
0x1400478ad  call    WPP_SF_DsD
0x1400478b2  mov     rcx, [rsp+6E0h+var_698]
0x1400478b7  test    rcx, rcx
0x1400478ba  jz      loc_1400479E7
0x1400478c0  mov     [rsp+6E0h+var_698], r12
0x1400478c5  mov     rax, [rcx]
0x1400478c8  mov     rax, [rax+10h]
0x1400478cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400478d1  jmp     loc_1400479E7
0x1400478d6  mov     rcx, [rsp+6E0h+var_698]
0x1400478db  lea     rdx, [rbp+5E0h+var_250]
0x1400478e2  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x1400478e9  mov     [rsp+6E0h+var_6B8], rdx
0x1400478ee  xor     r9d, r9d
0x1400478f1  lea     rdx, [rsp+6E0h+var_690]
0x1400478f6  mov     r8d, 0FFFFFFFCh
0x1400478fc  mov     rax, [rcx]
0x1400478ff  mov     [rsp+6E0h+ppv], rdx
0x140047904  mov     rdx, r14
0x140047907  movdqu  [rsp+6E0h+var_690], xmm0
0x14004790d  mov     rax, [rax+38h]
0x140047911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047916  mov     ebx, eax
0x140047918  test    eax, eax
0x14004791a  jns     short loc_140047968
0x14004791c  mov     rcx, cs:WPP_GLOBAL_Control
0x140047923  cmp     rcx, rsi
0x140047926  jz      short loc_140047968
0x140047928  test    byte ptr [rcx+1Ch], 8
0x14004792c  jz      short loc_140047968
0x14004792e  cmp     byte ptr [rcx+19h], 2
0x140047932  jb      short loc_140047968
0x140047934  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140047939  lea     rcx, aFailedToSetUse; "Failed to set User Authentication secti"...
0x140047940  mov     dword ptr [rsp+6E0h+var_6B8], ebx
0x140047944  mov     [rsp+6E0h+ppv], rcx
0x140047949  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x140047950  mov     rcx, cs:WPP_GLOBAL_Control
0x140047957  mov     edx, 1Bh
0x14004795c  mov     r9d, eax
0x14004795f  mov     rcx, [rcx+10h]
0x140047963  call    WPP_SF_DsD
0x140047968  mov     rcx, [rsp+6E0h+var_698]
0x14004796d  test    rcx, rcx
0x140047970  jz      short loc_1400479DC
0x140047972  mov     [rsp+6E0h+var_698], r12
0x140047977  mov     rax, [rcx]
0x14004797a  mov     rax, [rax+10h]
0x14004797e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047983  jmp     short loc_1400479DC
0x140047985  mov     rax, cs:WPP_GLOBAL_Control
0x14004798c  lea     rsi, WPP_GLOBAL_Control
0x140047993  cmp     rax, rsi
0x140047996  jz      short loc_1400479DC
0x140047998  test    byte ptr [rax+1Ch], 1
0x14004799c  jz      short loc_1400479DC
0x14004799e  cmp     byte ptr [rax+19h], 2
0x1400479a2  jb      short loc_1400479DC
0x1400479a4  call    cs:__imp_GetLastError
0x1400479aa  mov     ebx, eax
0x1400479ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400479b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400479b8  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x1400479bf  mov     edx, 1Ch
0x1400479c4  mov     dword ptr [rsp+6E0h+var_6B8], ebx
0x1400479c8  mov     r9d, eax
0x1400479cb  mov     dword ptr [rsp+6E0h+ppv], 3ACAh
0x1400479d3  mov     rcx, [rcx+10h]
0x1400479d7  call    WPP_SF_DLD
0x1400479dc  mov     r12d, 1
0x1400479e2  mov     qword ptr [rsp+6E0h+var_690], r13
0x1400479e7  mov     rax, r13
0x1400479ea  mov     [rsp+6E0h+var_680], 3ACAh
0x1400479f2  lea     r14, [rsp+6E0h+var_680]
0x1400479f7  mov     [rsp+6E0h+var_67C], 3ACBh
0x1400479ff  mov     [rsp+6E0h+var_678], 3ACCh
0x140047a07  mov     r13d, [r14]
0x140047a0a  mov     edx, r13d; nIDDlgItem
0x140047a0d  mov     rcx, [rax]; hDlg
0x140047a10  call    cs:__imp_GetDlgItem
0x140047a16  test    rax, rax
0x140047a19  jz      short loc_140047A8A
0x140047a1b  mov     edx, [rsp+6E0h+nCmdShow]; nCmdShow
0x140047a1f  mov     rcx, rax; hWnd
0x140047a22  call    cs:__imp_ShowWindow
0x140047a28  test    eax, eax
0x140047a2a  jnz     loc_140047ADA
0x140047a30  xor     r12d, r12d
0x140047a33  mov     rax, cs:WPP_GLOBAL_Control
0x140047a3a  cmp     rax, rsi
0x140047a3d  jz      loc_140047ADA
0x140047a43  test    byte ptr [rax+1Ch], 1
0x140047a47  jz      loc_140047ADA
0x140047a4d  cmp     byte ptr [rax+19h], 2
0x140047a51  jb      loc_140047ADA
0x140047a57  call    cs:__imp_GetLastError
0x140047a5d  mov     ebx, eax
0x140047a5f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140047a64  mov     ecx, [rsp+6E0h+nCmdShow]
0x140047a68  mov     r9d, eax
0x140047a6b  mov     [rsp+6E0h+var_6B0], ebx
0x140047a6f  mov     dword ptr [rsp+6E0h+var_6B8], ecx
0x140047a73  mov     rcx, cs:WPP_GLOBAL_Control
0x140047a7a  mov     dword ptr [rsp+6E0h+ppv], r13d
0x140047a7f  mov     rcx, [rcx+10h]
0x140047a83  call    WPP_SF_DddD
0x140047a88  jmp     short loc_140047ADA
0x140047a8a  xor     r12d, r12d
0x140047a8d  mov     rax, cs:WPP_GLOBAL_Control
0x140047a94  cmp     rax, rsi
0x140047a97  jz      short loc_140047ADA
0x140047a99  test    byte ptr [rax+1Ch], 1
0x140047a9d  jz      short loc_140047ADA
0x140047a9f  cmp     byte ptr [rax+19h], 2
0x140047aa3  jb      short loc_140047ADA
0x140047aa5  call    cs:__imp_GetLastError
0x140047aab  mov     ebx, eax
0x140047aad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140047ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x140047ab9  lea     edx, [r12+1Eh]
0x140047abe  mov     dword ptr [rsp+6E0h+var_6B8], ebx
0x140047ac2  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x140047ac9  mov     r9d, eax
0x140047acc  mov     dword ptr [rsp+6E0h+ppv], r13d
0x140047ad1  mov     rcx, [rcx+10h]
0x140047ad5  call    WPP_SF_DLD
0x140047ada  lea     rax, [rsp+6E0h+var_674]
0x140047adf  add     r14, 4
0x140047ae3  cmp     r14, rax
0x140047ae6  mov     rax, qword ptr [rsp+6E0h+var_690]
0x140047aeb  jnz     loc_140047A07
0x140047af1  mov     eax, r12d
0x140047af4  mov     rcx, [rbp+5E0h+var_40]
0x140047afb  xor     rcx, rsp; StackCookie
0x140047afe  call    __security_check_cookie
0x140047b03  add     rsp, 6B8h
0x140047b0a  pop     r14
0x140047b0c  pop     r13
0x140047b0e  pop     r12
0x140047b10  pop     rsi
0x140047b11  pop     rbx
0x140047b12  pop     rbp
0x140047b13  retn
```
