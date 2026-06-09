# RasRemoveToastNotification

- ea: `0x1800af490`
- end: `0x1800af5ac`
- name: `RasRemoveToastNotification`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180089eac`

## callees

- `0x18004e580`
- `0x1800a97d0`
- `0x1800af490`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af4dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af4dd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800af537`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800af537`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800af4b3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800af4b3`

## pseudocode

```c
__int64 __fastcall RasRemoveToastNotification(__int64 a1)
{
  HRESULT v2; // edi
  unsigned int v3; // ebx
  __int64 v5; // [rsp+58h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  ppv = 0;
  v5 = 0;
  v2 = CoInitializeEx(0, 0);
  if ( v2 >= 0 )
  {
    v2 = CoCreateInstance(
           &GUID_CWindowsPushNotificationPlatform,
           0,
           4u,
           &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
           &ppv);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v5);
      if ( v2 >= 0 )
        v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, __int64, _QWORD))(*(_QWORD *)v5 + 80LL))(
               v5,
               L"System",
               L"Windows.SystemToast.RasToastNotifier",
               0,
               a1,
               0);
    }
  }
  CoUninitialize();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, (unsigned int)v2);
  }
  v3 = (unsigned __int16)v2;
  if ( (v2 & 0x1FFF0000) != 0x70000 )
    v3 = v2;
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v5);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>((__int64 *)&ppv);
  return v3;
}

```

## disassembly

```asm
0x1800af490  mov     [rsp+arg_0], rbx
0x1800af495  push    rdi
0x1800af496  sub     rsp, 40h
0x1800af49a  mov     rbx, rcx
0x1800af49d  mov     [rsp+48h+arg_10], 0
0x1800af4a6  xor     ecx, ecx; pvReserved
0x1800af4a8  mov     [rsp+48h+arg_8], 0
0x1800af4b1  xor     edx, edx; dwCoInit
0x1800af4b3  call    cs:__imp_CoInitializeEx
0x1800af4b9  mov     edi, eax
0x1800af4bb  test    eax, eax
0x1800af4bd  js      short loc_1800AF537
0x1800af4bf  xor     edx, edx; pUnkOuter
0x1800af4c1  lea     rax, [rsp+48h+arg_10]
0x1800af4c6  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800af4cd  mov     [rsp+48h+ppv], rax; ppv
0x1800af4d2  lea     rcx, ?GUID_CWindowsPushNotificationPlatform@@3U_GUID@@A; rclsid
0x1800af4d9  lea     r8d, [rdx+4]; dwClsContext
0x1800af4dd  call    cs:__imp_CoCreateInstance
0x1800af4e3  mov     edi, eax
0x1800af4e5  test    eax, eax
0x1800af4e7  js      short loc_1800AF537
0x1800af4e9  mov     rcx, [rsp+48h+arg_10]
0x1800af4ee  lea     rdx, [rsp+48h+arg_8]
0x1800af4f3  mov     rax, [rcx]
0x1800af4f6  mov     rax, [rax+18h]
0x1800af4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af4ff  mov     edi, eax
0x1800af501  test    eax, eax
0x1800af503  js      short loc_1800AF537
0x1800af505  mov     rcx, [rsp+48h+arg_8]
0x1800af50a  lea     r8, aWindowsSystemt; "Windows.SystemToast.RasToastNotifier"
0x1800af511  mov     [rsp+48h+var_20], 0
0x1800af51a  lea     rdx, aSystem_0; "System"
0x1800af521  xor     r9d, r9d
0x1800af524  mov     [rsp+48h+ppv], rbx
0x1800af529  mov     rax, [rcx]
0x1800af52c  mov     rax, [rax+50h]
0x1800af530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af535  mov     edi, eax
0x1800af537  call    cs:__imp_CoUninitialize
0x1800af53d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af544  lea     rax, WPP_GLOBAL_Control
0x1800af54b  cmp     rcx, rax
0x1800af54e  jz      short loc_1800AF577
0x1800af550  test    dword ptr [rcx+1Ch], 800h
0x1800af557  jz      short loc_1800AF577
0x1800af559  cmp     byte ptr [rcx+19h], 6
0x1800af55d  jb      short loc_1800AF577
0x1800af55f  mov     rcx, [rcx+10h]
0x1800af563  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af56a  mov     edx, 1Bh
0x1800af56f  mov     r9d, edi
0x1800af572  call    WPP_SF_d
0x1800af577  mov     ecx, edi
0x1800af579  movzx   ebx, di
0x1800af57c  and     ecx, 1FFF0000h
0x1800af582  cmp     ecx, 70000h
0x1800af588  lea     rcx, [rsp+48h+arg_8]
0x1800af58d  cmovnz  ebx, edi
0x1800af590  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x1800af595  lea     rcx, [rsp+48h+arg_10]
0x1800af59a  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x1800af59f  mov     eax, ebx
0x1800af5a1  mov     rbx, [rsp+48h+arg_0]
0x1800af5a6  add     rsp, 40h
0x1800af5aa  pop     rdi
0x1800af5ab  retn
```
