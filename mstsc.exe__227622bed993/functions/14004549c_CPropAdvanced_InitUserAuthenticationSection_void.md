# CPropAdvanced::InitUserAuthenticationSection(void)

- ea: `0x14004549c`
- end: `0x1400459a4`
- name: `?InitUserAuthenticationSection@CPropAdvanced@@AEAAHXZ`
- size: `1288`
- prototype: `__int64 __fastcall(CPropAdvanced *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140045a64`

## callees

- `0x140004703`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e158`
- `0x14004549c`
- `0x140045dac`
- `0x14004622c`
- `0x1400fa960`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!GetWindowTextW` at `0x140045664`
- `USER32!GetWindowTextW` at `0x140045664`
- `USER32!ShowWindow` at `0x1400458b2`
- `USER32!ShowWindow` at `0x1400458b2`
- `USER32!GetDlgItem` at `0x140045562`
- `USER32!GetDlgItem` at `0x1400458a0`
- `USER32!GetDlgItem` at `0x140045562`
- `USER32!GetDlgItem` at `0x1400458a0`
- `KERNEL32!GetLastError` at `0x1400454e9`
- `KERNEL32!GetLastError` at `0x140045629`
- `KERNEL32!GetLastError` at `0x140045692`
- `KERNEL32!GetLastError` at `0x140045834`
- `KERNEL32!GetLastError` at `0x1400458e7`
- `KERNEL32!GetLastError` at `0x140045935`
- `KERNEL32!GetLastError` at `0x1400454e9`
- `KERNEL32!GetLastError` at `0x140045629`
- `KERNEL32!GetLastError` at `0x140045692`
- `KERNEL32!GetLastError` at `0x140045834`
- `KERNEL32!GetLastError` at `0x1400458e7`
- `KERNEL32!GetLastError` at `0x140045935`
- `ole32!CoCreateInstance` at `0x140045597`
- `ole32!CoCreateInstance` at `0x140045597`

## string_xrefs

- `0x140045713`: `String concatination for user authentication accessible name failed!`
- `0x1400457c9`: `Failed to set User Authentication section accessible name`

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
          v12 = StringCchPrintfW(&v42, 0x104u, L"%s %s", &v40, &String);
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
0x14004549c  push    rbp
0x14004549e  push    rbx
0x14004549f  push    rsi
0x1400454a0  push    r12
0x1400454a2  push    r13
0x1400454a4  push    r14
0x1400454a6  lea     rbp, [rsp-5B8h]
0x1400454ae  sub     rsp, 6B8h
0x1400454b5  mov     rax, cs:__security_cookie
0x1400454bc  xor     rax, rsp
0x1400454bf  mov     [rbp+5E0h+var_40], rax
0x1400454c6  mov     rax, [rcx]
0x1400454c9  xor     esi, esi
0x1400454cb  mov     edx, esi
0x1400454cd  mov     rbx, rcx
0x1400454d0  mov     r12d, esi
0x1400454d3  cmp     [rax+77E4h], esi
0x1400454d9  setnz   dl; unsigned int
0x1400454dc  call    ?SetUserAuthenticationCheckbox@CPropAdvanced@@AEAAHK@Z; CPropAdvanced::SetUserAuthenticationCheckbox(ulong)
0x1400454e1  test    eax, eax
0x1400454e3  jnz     short loc_140045548
0x1400454e5  mov     [rsp+6E0h+nCmdShow], esi
0x1400454e9  call    cs:__imp_GetLastError
0x1400454ef  mov     r14d, eax
0x1400454f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400454f9  lea     rsi, WPP_GLOBAL_Control
0x140045500  cmp     rcx, rsi
0x140045503  jz      short loc_14004553A
0x140045505  test    byte ptr [rcx+1Ch], 8
0x140045509  jz      short loc_14004553A
0x14004550b  cmp     byte ptr [rcx+19h], 2
0x14004550f  jb      short loc_14004553A
0x140045511  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140045516  mov     rcx, cs:WPP_GLOBAL_Control
0x14004551d  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x140045524  mov     edx, 17h
0x140045529  mov     dword ptr [rsp+6E0h+ppv], r14d
0x14004552e  mov     r9d, eax
0x140045531  mov     rcx, [rcx+10h]
0x140045535  call    WPP_SF_Dd
0x14004553a  lea     rax, [rbx+28h]
0x14004553e  mov     qword ptr [rsp+6E0h+var_690], rax
0x140045543  jmp     loc_14004587A
0x140045548  lea     r13, [rbx+28h]
0x14004554c  mov     [rsp+6E0h+nCmdShow], 5
0x140045554  mov     rcx, [r13+0]; hDlg
0x140045558  mov     edx, 3ACCh; nIDDlgItem
0x14004555d  mov     qword ptr [rsp+6E0h+var_690], r13
0x140045562  call    cs:__imp_GetDlgItem
0x140045568  mov     r14, rax
0x14004556b  test    rax, rax
0x14004556e  jz      loc_140045815
0x140045574  xor     edx, edx; pUnkOuter
0x140045576  mov     [rsp+6E0h+var_698], rsi
0x14004557b  lea     rax, [rsp+6E0h+var_698]
0x140045580  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x140045587  mov     [rsp+6E0h+ppv], rax; ppv
0x14004558c  lea     rcx, CLSID_AccPropServices; rclsid
0x140045593  lea     r8d, [rdx+15h]; dwClsContext
0x140045597  call    cs:__imp_CoCreateInstance
0x14004559d  lea     rsi, WPP_GLOBAL_Control
0x1400455a4  test    eax, eax
0x1400455a6  js      loc_1400457F8
0x1400455ac  xor     eax, eax
0x1400455ae  lea     rcx, [rbp+5E0h+var_45E]; void *
0x1400455b5  xor     edx, edx; Val
0x1400455b7  mov     [rbp+5E0h+var_460], ax
0x1400455be  mov     r8d, 206h; Size
0x1400455c4  call    memset_0
0x1400455c9  xor     eax, eax
0x1400455cb  lea     rcx, [rbp+5E0h+var_24E]; void *
0x1400455d2  xor     edx, edx; Val
0x1400455d4  mov     [rbp+5E0h+var_250], ax
0x1400455db  mov     r8d, 206h; Size
0x1400455e1  call    memset_0
0x1400455e6  mov     rcx, [rbx+20h]; HINSTANCE
0x1400455ea  lea     r8, [rbp+5E0h+var_460]; unsigned __int16 *
0x1400455f1  mov     r9d, 104h; int
0x1400455f7  mov     edx, 3AC2h; unsigned int
0x1400455fc  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140045601  test    eax, eax
0x140045603  jnz     short loc_14004563D
0x140045605  mov     rax, cs:WPP_GLOBAL_Control
0x14004560c  cmp     rax, rsi
0x14004560f  jz      loc_1400457F8
0x140045615  test    byte ptr [rax+1Ch], 1
0x140045619  jz      loc_1400457F8
0x14004561f  cmp     byte ptr [rax+19h], 2
0x140045623  jb      loc_1400457F8
0x140045629  call    cs:__imp_GetLastError
0x14004562f  mov     ebx, eax
0x140045631  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140045636  mov     edx, 18h
0x14004563b  jmp     short loc_1400456A4
0x14004563d  xor     eax, eax
0x14004563f  lea     rcx, [rsp+6E0h+var_66E]; void *
0x140045644  xor     edx, edx; Val
0x140045646  mov     [rsp+6E0h+String], ax
0x14004564b  mov     r8d, 206h; Size
0x140045651  call    memset_0
0x140045656  mov     r8d, 208h; nMaxCount
0x14004565c  lea     rdx, [rsp+6E0h+String]; lpString
0x140045661  mov     rcx, r14; hWnd
0x140045664  call    cs:__imp_GetWindowTextW
0x14004566a  test    eax, eax
0x14004566c  jnz     short loc_1400456C7
0x14004566e  mov     rax, cs:WPP_GLOBAL_Control
0x140045675  cmp     rax, rsi
0x140045678  jz      loc_1400457F8
0x14004567e  test    byte ptr [rax+1Ch], 1
0x140045682  jz      loc_1400457F8
0x140045688  cmp     byte ptr [rax+19h], 2
0x14004568c  jb      loc_1400457F8
0x140045692  call    cs:__imp_GetLastError
0x140045698  mov     ebx, eax
0x14004569a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004569f  mov     edx, 19h
0x1400456a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400456ab  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x1400456b2  mov     r9d, eax
0x1400456b5  mov     dword ptr [rsp+6E0h+ppv], ebx
0x1400456b9  mov     rcx, [rcx+10h]
0x1400456bd  call    WPP_SF_Dd
0x1400456c2  jmp     loc_1400457F8
0x1400456c7  lea     rax, [rsp+6E0h+String]
0x1400456cc  mov     edx, 104h; unsigned __int64
0x1400456d1  lea     r9, [rbp+5E0h+var_460]
0x1400456d8  mov     [rsp+6E0h+ppv], rax
0x1400456dd  lea     r8, aSS_2; "%s %s"
0x1400456e4  lea     rcx, [rbp+5E0h+var_250]; unsigned __int16 *
0x1400456eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400456f0  mov     ebx, eax
0x1400456f2  test    eax, eax
0x1400456f4  jns     short loc_140045766
0x1400456f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400456fd  cmp     rcx, rsi
0x140045700  jz      short loc_140045742
0x140045702  test    byte ptr [rcx+1Ch], 8
0x140045706  jz      short loc_140045742
0x140045708  cmp     byte ptr [rcx+19h], 2
0x14004570c  jb      short loc_140045742
0x14004570e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140045713  lea     rcx, aStringConcatin; "String concatination for user authentic"...
0x14004571a  mov     dword ptr [rsp+6E0h+var_6B8], ebx
0x14004571e  mov     [rsp+6E0h+ppv], rcx
0x140045723  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x14004572a  mov     rcx, cs:WPP_GLOBAL_Control
0x140045731  mov     edx, 1Ah
0x140045736  mov     r9d, eax
0x140045739  mov     rcx, [rcx+10h]
0x14004573d  call    WPP_SF_DsD
0x140045742  mov     rcx, [rsp+6E0h+var_698]
0x140045747  test    rcx, rcx
0x14004574a  jz      loc_140045877
0x140045750  mov     [rsp+6E0h+var_698], r12
0x140045755  mov     rax, [rcx]
0x140045758  mov     rax, [rax+10h]
0x14004575c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045761  jmp     loc_140045877
0x140045766  mov     rcx, [rsp+6E0h+var_698]
0x14004576b  lea     rdx, [rbp+5E0h+var_250]
0x140045772  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x140045779  mov     [rsp+6E0h+var_6B8], rdx
0x14004577e  xor     r9d, r9d
0x140045781  lea     rdx, [rsp+6E0h+var_690]
0x140045786  mov     r8d, 0FFFFFFFCh
0x14004578c  mov     rax, [rcx]
0x14004578f  mov     [rsp+6E0h+ppv], rdx
0x140045794  mov     rdx, r14
0x140045797  movdqu  [rsp+6E0h+var_690], xmm0
0x14004579d  mov     rax, [rax+38h]
0x1400457a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400457a6  mov     ebx, eax
0x1400457a8  test    eax, eax
0x1400457aa  jns     short loc_1400457F8
0x1400457ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457b3  cmp     rcx, rsi
0x1400457b6  jz      short loc_1400457F8
0x1400457b8  test    byte ptr [rcx+1Ch], 8
0x1400457bc  jz      short loc_1400457F8
0x1400457be  cmp     byte ptr [rcx+19h], 2
0x1400457c2  jb      short loc_1400457F8
0x1400457c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400457c9  lea     rcx, aFailedToSetUse; "Failed to set User Authentication secti"...
0x1400457d0  mov     dword ptr [rsp+6E0h+var_6B8], ebx
0x1400457d4  mov     [rsp+6E0h+ppv], rcx
0x1400457d9  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x1400457e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457e7  mov     edx, 1Bh
0x1400457ec  mov     r9d, eax
0x1400457ef  mov     rcx, [rcx+10h]
0x1400457f3  call    WPP_SF_DsD
0x1400457f8  mov     rcx, [rsp+6E0h+var_698]
0x1400457fd  test    rcx, rcx
0x140045800  jz      short loc_14004586C
0x140045802  mov     [rsp+6E0h+var_698], r12
0x140045807  mov     rax, [rcx]
0x14004580a  mov     rax, [rax+10h]
0x14004580e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045813  jmp     short loc_14004586C
0x140045815  mov     rax, cs:WPP_GLOBAL_Control
0x14004581c  lea     rsi, WPP_GLOBAL_Control
0x140045823  cmp     rax, rsi
0x140045826  jz      short loc_14004586C
0x140045828  test    byte ptr [rax+1Ch], 1
0x14004582c  jz      short loc_14004586C
0x14004582e  cmp     byte ptr [rax+19h], 2
0x140045832  jb      short loc_14004586C
0x140045834  call    cs:__imp_GetLastError
0x14004583a  mov     ebx, eax
0x14004583c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140045841  mov     rcx, cs:WPP_GLOBAL_Control
0x140045848  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x14004584f  mov     edx, 1Ch
0x140045854  mov     dword ptr [rsp+6E0h+var_6B8], ebx
0x140045858  mov     r9d, eax
0x14004585b  mov     dword ptr [rsp+6E0h+ppv], 3ACAh
0x140045863  mov     rcx, [rcx+10h]
0x140045867  call    WPP_SF_DLD
0x14004586c  mov     r12d, 1
0x140045872  mov     qword ptr [rsp+6E0h+var_690], r13
0x140045877  mov     rax, r13
0x14004587a  mov     [rsp+6E0h+var_680], 3ACAh
0x140045882  lea     r14, [rsp+6E0h+var_680]
0x140045887  mov     [rsp+6E0h+var_67C], 3ACBh
0x14004588f  mov     [rsp+6E0h+var_678], 3ACCh
0x140045897  mov     r13d, [r14]
0x14004589a  mov     edx, r13d; nIDDlgItem
0x14004589d  mov     rcx, [rax]; hDlg
0x1400458a0  call    cs:__imp_GetDlgItem
0x1400458a6  test    rax, rax
0x1400458a9  jz      short loc_14004591A
0x1400458ab  mov     edx, [rsp+6E0h+nCmdShow]; nCmdShow
0x1400458af  mov     rcx, rax; hWnd
0x1400458b2  call    cs:__imp_ShowWindow
0x1400458b8  test    eax, eax
0x1400458ba  jnz     loc_14004596A
0x1400458c0  xor     r12d, r12d
0x1400458c3  mov     rax, cs:WPP_GLOBAL_Control
0x1400458ca  cmp     rax, rsi
0x1400458cd  jz      loc_14004596A
0x1400458d3  test    byte ptr [rax+1Ch], 1
0x1400458d7  jz      loc_14004596A
0x1400458dd  cmp     byte ptr [rax+19h], 2
0x1400458e1  jb      loc_14004596A
0x1400458e7  call    cs:__imp_GetLastError
0x1400458ed  mov     ebx, eax
0x1400458ef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400458f4  mov     ecx, [rsp+6E0h+nCmdShow]
0x1400458f8  mov     r9d, eax
0x1400458fb  mov     [rsp+6E0h+var_6B0], ebx
0x1400458ff  mov     dword ptr [rsp+6E0h+var_6B8], ecx
0x140045903  mov     rcx, cs:WPP_GLOBAL_Control
0x14004590a  mov     dword ptr [rsp+6E0h+ppv], r13d
0x14004590f  mov     rcx, [rcx+10h]
0x140045913  call    WPP_SF_DddD
0x140045918  jmp     short loc_14004596A
0x14004591a  xor     r12d, r12d
0x14004591d  mov     rax, cs:WPP_GLOBAL_Control
0x140045924  cmp     rax, rsi
0x140045927  jz      short loc_14004596A
0x140045929  test    byte ptr [rax+1Ch], 1
0x14004592d  jz      short loc_14004596A
0x14004592f  cmp     byte ptr [rax+19h], 2
0x140045933  jb      short loc_14004596A
0x140045935  call    cs:__imp_GetLastError
0x14004593b  mov     ebx, eax
0x14004593d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140045942  mov     rcx, cs:WPP_GLOBAL_Control
0x140045949  lea     edx, [r12+1Eh]
0x14004594e  mov     dword ptr [rsp+6E0h+var_6B8], ebx
0x140045952  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x140045959  mov     r9d, eax
0x14004595c  mov     dword ptr [rsp+6E0h+ppv], r13d
0x140045961  mov     rcx, [rcx+10h]
0x140045965  call    WPP_SF_DLD
0x14004596a  lea     rax, [rsp+6E0h+var_674]
0x14004596f  add     r14, 4
0x140045973  cmp     r14, rax
0x140045976  mov     rax, qword ptr [rsp+6E0h+var_690]
0x14004597b  jnz     loc_140045897
0x140045981  mov     eax, r12d
0x140045984  mov     rcx, [rbp+5E0h+var_40]
0x14004598b  xor     rcx, rsp; StackCookie
0x14004598e  call    __security_check_cookie
0x140045993  add     rsp, 6B8h
0x14004599a  pop     r14
0x14004599c  pop     r13
0x14004599e  pop     r12
0x1400459a0  pop     rsi
0x1400459a1  pop     rbx
0x1400459a2  pop     rbp
0x1400459a3  retn
```
