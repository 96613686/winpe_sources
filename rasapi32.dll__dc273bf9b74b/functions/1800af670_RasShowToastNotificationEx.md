# RasShowToastNotificationEx

- ea: `0x1800af670`
- end: `0x1800afa8d`
- name: `RasShowToastNotificationEx`
- size: `1053`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800af5b4`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x18007e650`
- `0x18007f140`
- `0x1800a97d0`
- `0x1800aa15c`
- `0x1800adfec`
- `0x1800af670`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af9c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800af8a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800af8a0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800af8ae`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800af8ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af77b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af77b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800afa05`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800afa05`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800af74e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800af74e`

## pseudocode

```c
__int64 __fastcall RasShowToastNotificationEx(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v7; // r13
  _QWORD *v8; // rcx
  unsigned int v9; // r14d
  unsigned int v10; // esi
  HRESULT v11; // edi
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned int v15; // ebx
  unsigned __int64 v16; // rdi
  int v17; // r12d
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  __int64 (__fastcall *v20)(__int64, const wchar_t *, const wchar_t *, _QWORD, int, HLOCAL, unsigned __int16 *, _QWORD, struct _FILETIME *, _DWORD, _DWORD, _QWORD, __int64, _QWORD, unsigned int, int *); // rax
  unsigned __int16 *v21; // rbx
  unsigned int v22; // ebx
  __int64 v24[2]; // [rsp+90h] [rbp-80h] BYREF
  struct _FILETIME v25; // [rsp+A0h] [rbp-70h] BYREF
  int v26; // [rsp+A8h] [rbp-68h]
  int v27; // [rsp+B0h] [rbp-60h] BYREF
  unsigned int v28; // [rsp+B4h] [rbp-5Ch]
  struct _FILETIME FileTime; // [rsp+B8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+C0h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp-48h] BYREF
  unsigned __int16 *v32; // [rsp+D0h] [rbp-40h]
  __int64 v33; // [rsp+D8h] [rbp-38h]
  struct _SYSTEMTIME SystemTime; // [rsp+E0h] [rbp-30h] BYREF

  v33 = a5;
  v7 = a4;
  v28 = a3;
  v32 = a2;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  hMem = 0;
  ppv = 0;
  v24[0] = 0;
  if ( a5 )
  {
    v10 = 0;
    v9 = 0;
  }
  else
  {
    v9 = g_SupressToast;
    v10 = 1;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_Dd(v8[2], 21, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, v10, v9);
  v11 = CoInitializeEx(0, 0);
  if ( v11 >= 0 )
  {
    v11 = CoCreateInstance(
            &GUID_CWindowsPushNotificationPlatform,
            0,
            4u,
            &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
            &ppv);
    if ( v11 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, v24);
      v27 = 0;
      v11 = v12;
      if ( v12 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, unsigned __int16 *, _QWORD))(*(_QWORD *)v24[0] + 80LL))(
                v24[0],
                L"System",
                L"Windows.SystemToast.RasToastNotifier",
                0,
                v32,
                0);
        if ( v13 < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids,
            (_DWORD)a1,
            v13);
        }
        v14 = ConstructToastXmlString(a3, a1, v10, (unsigned __int16 **)&hMem);
        v11 = v14;
        if ( v14 >= 0 )
        {
          v15 = 0;
          LODWORD(v16) = 0;
          SystemTime = 0;
          FileTime = 0;
          v17 = 0;
          GetSystemTime(&SystemTime);
          if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
          {
            v25 = FileTime;
            v18 = *(_QWORD *)&FileTime + 10000000 * v7;
            if ( v18 >= *(_QWORD *)&FileTime )
            {
              v15 = FileTime.dwLowDateTime + 10000000 * v7;
              v16 = HIDWORD(v18);
              v17 = 1;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids,
                  (unsigned int)v7);
              }
            }
          }
          v19 = *(_QWORD *)v24[0];
          v25 = (struct _FILETIME)__PAIR64__(v15, v17);
          v20 = *(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, int, HLOCAL, unsigned __int16 *, _QWORD, struct _FILETIME *, _DWORD, _DWORD, _QWORD, __int64, _QWORD, unsigned int, int *))(v19 + 64);
          v21 = v32;
          v26 = v16;
          v11 = v20(
                  v24[0],
                  L"System",
                  L"Windows.SystemToast.RasToastNotifier",
                  0,
                  1,
                  hMem,
                  v32,
                  0,
                  &v25,
                  0,
                  0,
                  0,
                  v33,
                  0,
                  v9,
                  &v27);
          TelemetryEventWriteToastNotification(a1, v21, v28, v9);
          if ( v10 )
            g_SupressToast = 1;
          LocalFree(hMem);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, a1);
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids,
            (unsigned int)v14);
        }
      }
    }
  }
  CoUninitialize();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids,
      (unsigned int)v11);
  }
  v22 = (unsigned __int16)v11;
  if ( (v11 & 0x1FFF0000) != 0x70000 )
    v22 = v11;
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(v24);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>((__int64 *)&ppv);
  return v22;
}

```

## disassembly

```asm
0x1800af670  push    rbp
0x1800af672  push    rbx
0x1800af673  push    rsi
0x1800af674  push    rdi
0x1800af675  push    r12
0x1800af677  push    r13
0x1800af679  push    r14
0x1800af67b  push    r15
0x1800af67d  lea     rbp, [rsp+8]
0x1800af682  sub     rsp, 108h
0x1800af689  mov     rax, cs:__security_cookie
0x1800af690  xor     rax, rsp
0x1800af693  mov     [rbp+30h+var_50], rax
0x1800af697  mov     rbx, [rbp+30h+arg_20]
0x1800af69b  mov     r12d, r8d
0x1800af69e  mov     [rbp+30h+var_68], rbx
0x1800af6a2  mov     r15, rcx
0x1800af6a5  mov     r13d, r9d
0x1800af6a8  mov     [rbp+30h+var_8C], r8d
0x1800af6ac  mov     [rbp+30h+var_70], rdx
0x1800af6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af6b7  lea     rdx, WPP_GLOBAL_Control
0x1800af6be  cmp     rcx, rdx
0x1800af6c1  jz      short loc_1800AF6F5
0x1800af6c3  test    dword ptr [rcx+1Ch], 800h
0x1800af6ca  jz      short loc_1800AF6F5
0x1800af6cc  cmp     byte ptr [rcx+19h], 6
0x1800af6d0  jb      short loc_1800AF6F5
0x1800af6d2  mov     rcx, [rcx+10h]
0x1800af6d6  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af6dd  mov     edx, 14h
0x1800af6e2  call    WPP_SF_
0x1800af6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af6ee  lea     rdx, WPP_GLOBAL_Control
0x1800af6f5  xor     eax, eax
0x1800af6f7  mov     [rbp+30h+hMem], rax
0x1800af6fb  mov     [rbp+30h+var_78], rax
0x1800af6ff  mov     [rbp+30h+var_B0], rax
0x1800af703  test    rbx, rbx
0x1800af706  jnz     short loc_1800AF714
0x1800af708  mov     r14d, cs:?g_SupressToast@@3HA; int g_SupressToast
0x1800af70f  lea     esi, [rax+1]
0x1800af712  jmp     short loc_1800AF719
0x1800af714  xor     esi, esi
0x1800af716  xor     r14d, r14d
0x1800af719  cmp     rcx, rdx
0x1800af71c  jz      short loc_1800AF74A
0x1800af71e  test    dword ptr [rcx+1Ch], 800h
0x1800af725  jz      short loc_1800AF74A
0x1800af727  cmp     byte ptr [rcx+19h], 5
0x1800af72b  jb      short loc_1800AF74A
0x1800af72d  mov     rcx, [rcx+10h]
0x1800af731  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af738  mov     edx, 15h
0x1800af73d  mov     dword ptr [rsp+140h+ppv], r14d
0x1800af742  mov     r9d, esi
0x1800af745  call    WPP_SF_Dd
0x1800af74a  xor     edx, edx; dwCoInit
0x1800af74c  xor     ecx, ecx; pvReserved
0x1800af74e  call    cs:__imp_CoInitializeEx
0x1800af754  mov     edi, eax
0x1800af756  test    eax, eax
0x1800af758  js      loc_1800AFA05
0x1800af75e  xor     edx, edx; pUnkOuter
0x1800af760  lea     rax, [rbp+30h+var_78]
0x1800af764  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800af76b  mov     [rsp+140h+ppv], rax; ppv
0x1800af770  lea     rcx, ?GUID_CWindowsPushNotificationPlatform@@3U_GUID@@A; rclsid
0x1800af777  lea     r8d, [rdx+4]; dwClsContext
0x1800af77b  call    cs:__imp_CoCreateInstance
0x1800af781  mov     edi, eax
0x1800af783  test    eax, eax
0x1800af785  js      loc_1800AFA05
0x1800af78b  mov     rcx, [rbp+30h+var_78]
0x1800af78f  lea     rdx, [rbp+30h+var_B0]
0x1800af793  mov     rax, [rcx]
0x1800af796  mov     rax, [rax+18h]
0x1800af79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af79f  mov     [rbp+30h+var_90], 0
0x1800af7a6  mov     edi, eax
0x1800af7a8  test    eax, eax
0x1800af7aa  js      loc_1800AFA05
0x1800af7b0  mov     rcx, [rbp+30h+var_B0]
0x1800af7b4  lea     r8, aWindowsSystemt; "Windows.SystemToast.RasToastNotifier"
0x1800af7bb  mov     rdx, [rbp+30h+var_70]
0x1800af7bf  xor     r9d, r9d
0x1800af7c2  mov     [rsp+140h+var_118], 0
0x1800af7cb  mov     [rsp+140h+ppv], rdx
0x1800af7d0  lea     rdx, aSystem_0; "System"
0x1800af7d7  mov     rax, [rcx]
0x1800af7da  mov     rax, [rax+50h]
0x1800af7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af7e3  test    eax, eax
0x1800af7e5  jns     short loc_1800AF827
0x1800af7e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af7ee  lea     rbx, WPP_GLOBAL_Control
0x1800af7f5  cmp     rcx, rbx
0x1800af7f8  jz      short loc_1800AF82E
0x1800af7fa  test    dword ptr [rcx+1Ch], 800h
0x1800af801  jz      short loc_1800AF82E
0x1800af803  cmp     byte ptr [rcx+19h], 2
0x1800af807  jb      short loc_1800AF82E
0x1800af809  mov     rcx, [rcx+10h]
0x1800af80d  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af814  mov     edx, 16h
0x1800af819  mov     dword ptr [rsp+140h+ppv], eax
0x1800af81d  mov     r9, r15
0x1800af820  call    WPP_SF_Sd
0x1800af825  jmp     short loc_1800AF82E
0x1800af827  lea     rbx, WPP_GLOBAL_Control
0x1800af82e  lea     r9, [rbp+30h+hMem]; unsigned __int16 **
0x1800af832  mov     r8d, esi; int
0x1800af835  mov     rdx, r15; unsigned __int16 *
0x1800af838  mov     ecx, r12d; unsigned int
0x1800af83b  call    ?ConstructToastXmlString@@YAJKPEBGHPEAPEAG@Z; ConstructToastXmlString(ulong,ushort const *,int,ushort * *)
0x1800af840  mov     edi, eax
0x1800af842  test    eax, eax
0x1800af844  jns     short loc_1800AF88A
0x1800af846  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af84d  cmp     rcx, rbx
0x1800af850  jz      loc_1800AFA05
0x1800af856  test    dword ptr [rcx+1Ch], 800h
0x1800af85d  jz      loc_1800AFA05
0x1800af863  cmp     byte ptr [rcx+19h], 2
0x1800af867  jb      loc_1800AFA05
0x1800af86d  mov     rcx, [rcx+10h]
0x1800af871  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af878  mov     edx, 17h
0x1800af87d  mov     r9d, eax
0x1800af880  call    WPP_SF_d
0x1800af885  jmp     loc_1800AFA05
0x1800af88a  xorps   xmm0, xmm0
0x1800af88d  lea     rcx, [rbp+30h+SystemTime]; lpSystemTime
0x1800af891  xor     ebx, ebx
0x1800af893  xor     edi, edi
0x1800af895  movups  xmmword ptr [rbp+30h+SystemTime.wYear], xmm0
0x1800af899  mov     qword ptr [rbp+30h+FileTime.dwLowDateTime], rbx
0x1800af89d  xor     r12d, r12d
0x1800af8a0  call    cs:__imp_GetSystemTime
0x1800af8a6  lea     rdx, [rbp+30h+FileTime]; lpFileTime
0x1800af8aa  lea     rcx, [rbp+30h+SystemTime]; lpSystemTime
0x1800af8ae  call    cs:__imp_SystemTimeToFileTime
0x1800af8b4  test    eax, eax
0x1800af8b6  jz      short loc_1800AF91F
0x1800af8b8  mov     eax, [rbp+30h+FileTime.dwHighDateTime]
0x1800af8bb  mov     dword ptr [rbp+30h+var_A0+4], eax
0x1800af8be  mov     eax, [rbp+30h+FileTime.dwLowDateTime]
0x1800af8c1  imul    rdx, r13, 989680h
0x1800af8c8  mov     dword ptr [rbp+30h+var_A0], eax
0x1800af8cb  add     rdx, [rbp+30h+var_A0]
0x1800af8cf  cmp     rdx, [rbp+30h+var_A0]
0x1800af8d3  jb      short loc_1800AF91F
0x1800af8d5  mov     rdi, rdx
0x1800af8d8  mov     rbx, rdx
0x1800af8db  shr     rdi, 20h
0x1800af8df  mov     r12d, 1
0x1800af8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af8ec  lea     rax, WPP_GLOBAL_Control
0x1800af8f3  cmp     rcx, rax
0x1800af8f6  jz      short loc_1800AF91F
0x1800af8f8  test    dword ptr [rcx+1Ch], 800h
0x1800af8ff  jz      short loc_1800AF91F
0x1800af901  cmp     byte ptr [rcx+19h], 5
0x1800af905  jb      short loc_1800AF91F
0x1800af907  mov     rcx, [rcx+10h]
0x1800af90b  lea     edx, [r12+17h]
0x1800af910  mov     r9d, r13d
0x1800af913  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af91a  call    WPP_SF_d
0x1800af91f  mov     r9, [rbp+30h+hMem]
0x1800af923  lea     rdx, [rbp+30h+var_90]
0x1800af927  mov     rcx, [rbp+30h+var_B0]
0x1800af92b  lea     r10, [rbp+30h+var_A0]
0x1800af92f  mov     [rsp+140h+var_C8], rdx
0x1800af934  lea     r8, aWindowsSystemt; "Windows.SystemToast.RasToastNotifier"
0x1800af93b  mov     rdx, [rbp+30h+var_68]
0x1800af93f  mov     [rsp+140h+var_D0], r14d
0x1800af944  mov     rax, [rcx]
0x1800af947  mov     dword ptr [rbp+30h+var_A0], r12d
0x1800af94b  xor     r12d, r12d
0x1800af94e  mov     [rsp+140h+var_D8], r12
0x1800af953  mov     [rsp+140h+var_E0], rdx
0x1800af958  lea     rdx, aSystem_0; "System"
0x1800af95f  mov     rax, [rax+40h]
0x1800af963  mov     [rsp+140h+var_E8], r12
0x1800af968  lea     r13d, [r12+1]
0x1800af96d  mov     [rsp+140h+var_F0], r12d
0x1800af972  mov     [rsp+140h+var_F8], r12d
0x1800af977  mov     [rsp+140h+var_100], r10
0x1800af97c  mov     [rsp+140h+var_108], r12
0x1800af981  mov     dword ptr [rbp+30h+var_A0+4], ebx
0x1800af984  mov     rbx, [rbp+30h+var_70]
0x1800af988  mov     [rsp+140h+var_110], rbx
0x1800af98d  mov     [rsp+140h+var_118], r9
0x1800af992  xor     r9d, r9d
0x1800af995  mov     [rbp+30h+var_98], edi
0x1800af998  mov     dword ptr [rsp+140h+ppv], r13d
0x1800af99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af9a2  mov     r8d, [rbp+30h+var_8C]; unsigned int
0x1800af9a6  mov     r9d, r14d; int
0x1800af9a9  mov     rdx, rbx; unsigned __int16 *
0x1800af9ac  mov     rcx, r15; unsigned __int16 *
0x1800af9af  mov     edi, eax
0x1800af9b1  call    ?TelemetryEventWriteToastNotification@@YAXPEBG0IH@Z; TelemetryEventWriteToastNotification(ushort const *,ushort const *,uint,int)
0x1800af9b6  test    esi, esi
0x1800af9b8  jz      short loc_1800AF9C1
0x1800af9ba  mov     cs:?g_SupressToast@@3HA, r13d; int g_SupressToast
0x1800af9c1  mov     rcx, [rbp+30h+hMem]; hMem
0x1800af9c5  call    cs:__imp_LocalFree
0x1800af9cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af9d2  lea     rax, WPP_GLOBAL_Control
0x1800af9d9  cmp     rcx, rax
0x1800af9dc  jz      short loc_1800AFA05
0x1800af9de  test    dword ptr [rcx+1Ch], 800h
0x1800af9e5  jz      short loc_1800AFA05
0x1800af9e7  cmp     byte ptr [rcx+19h], 5
0x1800af9eb  jb      short loc_1800AFA05
0x1800af9ed  mov     rcx, [rcx+10h]
0x1800af9f1  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af9f8  mov     edx, 19h
0x1800af9fd  mov     r9, r15
0x1800afa00  call    WPP_SF_S
0x1800afa05  call    cs:__imp_CoUninitialize
0x1800afa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afa12  lea     rax, WPP_GLOBAL_Control
0x1800afa19  cmp     rcx, rax
0x1800afa1c  jz      short loc_1800AFA45
0x1800afa1e  test    dword ptr [rcx+1Ch], 800h
0x1800afa25  jz      short loc_1800AFA45
0x1800afa27  cmp     byte ptr [rcx+19h], 6
0x1800afa2b  jb      short loc_1800AFA45
0x1800afa2d  mov     rcx, [rcx+10h]
0x1800afa31  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800afa38  mov     edx, 1Ah
0x1800afa3d  mov     r9d, edi
0x1800afa40  call    WPP_SF_d
0x1800afa45  mov     ecx, edi
0x1800afa47  movzx   ebx, di
0x1800afa4a  and     ecx, 1FFF0000h
0x1800afa50  cmp     ecx, 70000h
0x1800afa56  lea     rcx, [rbp+30h+var_B0]
0x1800afa5a  cmovnz  ebx, edi
0x1800afa5d  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x1800afa62  lea     rcx, [rbp+30h+var_78]
0x1800afa66  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x1800afa6b  mov     eax, ebx
0x1800afa6d  mov     rcx, [rbp+30h+var_50]
0x1800afa71  xor     rcx, rsp; StackCookie
0x1800afa74  call    __security_check_cookie
0x1800afa79  add     rsp, 108h
0x1800afa80  pop     r15
0x1800afa82  pop     r14
0x1800afa84  pop     r13
0x1800afa86  pop     r12
0x1800afa88  pop     rdi
0x1800afa89  pop     rsi
0x1800afa8a  pop     rbx
0x1800afa8b  pop     rbp
0x1800afa8c  retn
```
