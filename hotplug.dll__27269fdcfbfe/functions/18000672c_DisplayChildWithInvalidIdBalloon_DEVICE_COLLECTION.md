# DisplayChildWithInvalidIdBalloon(DEVICE_COLLECTION *)

- ea: `0x18000672c`
- end: `0x180006a62`
- name: `?DisplayChildWithInvalidIdBalloon@@YAXPEAUDEVICE_COLLECTION@@@Z`
- size: `822`
- prototype: `void __fastcall(struct DEVICE_COLLECTION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004c20`

## callees

- `0x180003048`
- `0x18000672c`
- `0x180008760`
- `0x180009010`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x180006948`
- `KERNEL32!OpenEventW` at `0x180006948`
- `KERNEL32!CloseHandle` at `0x180006967`
- `KERNEL32!CloseHandle` at `0x180006967`
- `KERNEL32!WaitForSingleObject` at `0x18000695e`
- `KERNEL32!WaitForSingleObject` at `0x18000695e`
- `KERNEL32!Sleep` at `0x18000692a`
- `KERNEL32!Sleep` at `0x18000692a`
- `USER32!GetSystemMetrics` at `0x1800068df`
- `USER32!GetSystemMetrics` at `0x1800068ec`
- `USER32!GetSystemMetrics` at `0x1800068df`
- `USER32!GetSystemMetrics` at `0x1800068ec`
- `USER32!DestroyIcon` at `0x180006a3d`
- `USER32!DestroyIcon` at `0x180006a3d`
- `USER32!LoadStringW` at `0x180006782`
- `USER32!LoadStringW` at `0x1800067ab`
- `USER32!LoadStringW` at `0x180006782`
- `USER32!LoadStringW` at `0x1800067ab`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800068a3`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800068a3`
- `SETUPAPI!SetupDiLoadDeviceIcon` at `0x18000690f`
- `SETUPAPI!SetupDiLoadDeviceIcon` at `0x18000690f`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800068d0`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800068d0`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180006918`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180006918`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800069a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800069a5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006a2d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006a2d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006974`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006974`

## string_xrefs

- `0x18000693d`: `ShellReadyEvent`

## pseudocode

```c
void __fastcall DisplayChildWithInvalidIdBalloon(struct DEVICE_COLLECTION *a1)
{
  __int64 v2; // rdi
  struct DEVICE_COLLECTION *v3; // rcx
  unsigned __int16 *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rcx
  int v10; // r14d
  const WCHAR *v11; // rsi
  HDEVINFO DeviceInfoList; // rdi
  UINT SystemMetrics; // ebx
  UINT v14; // eax
  HANDLE v15; // rax
  void *v16; // rbx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  HICON hIcon; // [rsp+38h] [rbp-C8h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[64]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v21[256]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v22[256]; // [rsp+2E0h] [rbp+1E0h] BYREF

  hIcon = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  if ( LoadStringW(hHotPlug, 0x8E1u, Buffer, 64) )
  {
    v2 = 256;
    if ( LoadStringW(hHotPlug, 0x8E2u, v22, 256) )
    {
      v3 = *(struct DEVICE_COLLECTION **)a1;
      v21[0] = 0;
      if ( v3 != a1 )
      {
        v4 = (unsigned __int16 *)*((_QWORD *)v3 + 53);
        if ( v4 )
        {
          v5 = -1;
          do
            ++v5;
          while ( v22[v5] );
          v6 = -1;
          do
            ++v6;
          while ( v4[v6] );
          if ( (unsigned __int64)(v6 + v5) >= 0x100 )
          {
            v7 = 2147483646;
            v8 = v21;
            do
            {
              if ( !v7 )
                break;
              if ( !*v4 )
                break;
              *v8++ = *v4++;
              --v7;
              --v2;
            }
            while ( v2 );
            v9 = v8 - 1;
            if ( v2 )
              v9 = v8;
            *v9 = 0;
          }
          else
          {
            StringCchPrintfW(v21, 0x100u, v22, v4);
          }
          if ( v21[0] )
          {
            v10 = 0;
            v11 = 0;
            if ( *(struct DEVICE_COLLECTION **)a1 != a1 )
              v11 = (const WCHAR *)(*(_QWORD *)a1 + 16LL);
            if ( v11 )
            {
              DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
              if ( DeviceInfoList != (HDEVINFO)-1LL )
              {
                DeviceInfoData.cbSize = 32;
                if ( SetupDiOpenDeviceInfoW(DeviceInfoList, v11, 0, 0, &DeviceInfoData) )
                {
                  SystemMetrics = GetSystemMetrics(50);
                  v14 = GetSystemMetrics(49);
                  SetupDiLoadDeviceIcon(DeviceInfoList, &DeviceInfoData, v14, SystemMetrics, 0, &hIcon);
                }
                SetupDiDestroyDeviceInfoList(DeviceInfoList);
              }
            }
            while ( 1 )
            {
              v15 = OpenEventW(0x100000u, 0, L"ShellReadyEvent");
              v16 = v15;
              if ( v15 )
                break;
              Sleep(0x1388u);
              if ( v10 > 120 )
                goto LABEL_37;
              ++v10;
            }
            WaitForSingleObject(v15, 0xFFFFFFFF);
            CloseHandle(v16);
            if ( CoInitializeEx(0, 6u) >= 0 )
            {
              ppv = 0;
              if ( CoCreateInstance(&CLSID_UserNotification, 0, 1u, &IID_IUserNotification, &ppv) >= 0 )
              {
                (*(void (__fastcall **)(LPVOID, HICON, WCHAR *))(*(_QWORD *)ppv + 40LL))(ppv, hIcon, Buffer);
                (*(void (__fastcall **)(LPVOID, WCHAR *, unsigned __int16 *, __int64))(*(_QWORD *)ppv + 24LL))(
                  ppv,
                  Buffer,
                  v21,
                  2);
                (*(void (__fastcall **)(LPVOID, __int64, __int64, _QWORD))(*(_QWORD *)ppv + 32LL))(
                  ppv,
                  20000,
                  0xFFFFFFFFLL,
                  0);
                (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 48LL))(ppv, 0, 0);
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
              }
              CoUninitialize();
            }
LABEL_37:
            if ( hIcon )
              DestroyIcon(hIcon);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000672c  push    rbp
0x18000672e  push    rbx
0x18000672f  push    rsi
0x180006730  push    rdi
0x180006731  push    r14
0x180006733  push    r15
0x180006735  lea     rbp, [rsp-3F8h]
0x18000673d  sub     rsp, 4F8h
0x180006744  mov     rax, cs:__security_cookie
0x18000674b  xor     rax, rsp
0x18000674e  mov     [rbp+420h+var_40], rax
0x180006755  xorps   xmm0, xmm0
0x180006758  lea     r8, [rsp+520h+Buffer]; lpBuffer
0x18000675d  xor     r15d, r15d
0x180006760  mov     rbx, rcx
0x180006763  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x18000676a  mov     edx, 8E1h; uID
0x18000676f  mov     [rsp+520h+var_4E8], r15
0x180006774  movups  xmmword ptr [rsp+520h+var_4E0.cbSize], xmm0
0x180006779  lea     r9d, [r15+40h]; cchBufferMax
0x18000677d  movups  xmmword ptr [rsp+520h+var_4E0.ClassGuid.Data4+4], xmm0
0x180006782  call    cs:__imp_LoadStringW
0x180006788  test    eax, eax
0x18000678a  jz      loc_180006A43
0x180006790  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x180006797  lea     r8, [rbp+420h+var_240]; lpBuffer
0x18000679e  mov     edi, 100h
0x1800067a3  mov     edx, 8E2h; uID
0x1800067a8  mov     r9d, edi; cchBufferMax
0x1800067ab  call    cs:__imp_LoadStringW
0x1800067b1  test    eax, eax
0x1800067b3  jz      loc_180006A43
0x1800067b9  mov     rcx, [rbx]
0x1800067bc  mov     eax, r15d
0x1800067bf  mov     [rbp+420h+var_440], r15w
0x1800067c4  jmp     short loc_1800067CF
0x1800067c6  test    eax, eax
0x1800067c8  jz      short loc_1800067D9
0x1800067ca  mov     rcx, [rcx]
0x1800067cd  inc     eax
0x1800067cf  cmp     rcx, rbx
0x1800067d2  jnz     short loc_1800067C6
0x1800067d4  jmp     loc_180006A43
0x1800067d9  mov     rcx, [rcx+1A8h]
0x1800067e0  test    rcx, rcx
0x1800067e3  jz      loc_180006A43
0x1800067e9  lea     rdx, [rbp+420h+var_240]
0x1800067f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800067f4  inc     rax
0x1800067f7  cmp     [rdx+rax*2], r15w
0x1800067fc  jnz     short loc_1800067F4
0x1800067fe  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180006802  inc     rdx
0x180006805  cmp     [rcx+rdx*2], r15w
0x18000680a  jnz     short loc_180006802
0x18000680c  add     rax, rdx
0x18000680f  cmp     rax, rdi
0x180006812  jnb     short loc_18000682C
0x180006814  mov     r9, rcx
0x180006817  lea     r8, [rbp+420h+var_240]; unsigned __int16 *
0x18000681e  lea     rcx, [rbp+420h+var_440]; unsigned __int16 *
0x180006822  mov     rdx, rdi; unsigned __int64
0x180006825  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000682a  jmp     short loc_180006868
0x18000682c  mov     edx, 7FFFFFFEh
0x180006831  lea     rax, [rbp+420h+var_440]
0x180006835  test    rdx, rdx
0x180006838  jz      short loc_180006859
0x18000683a  movzx   r8d, word ptr [rcx]
0x18000683e  test    r8w, r8w
0x180006842  jz      short loc_180006859
0x180006844  mov     [rax], r8w
0x180006848  add     rcx, 2
0x18000684c  add     rax, 2
0x180006850  dec     rdx
0x180006853  sub     rdi, 1
0x180006857  jnz     short loc_180006835
0x180006859  test    rdi, rdi
0x18000685c  lea     rcx, [rax-2]
0x180006860  cmovnz  rcx, rax
0x180006864  mov     [rcx], r15w
0x180006868  cmp     [rbp+420h+var_440], r15w
0x18000686d  jz      loc_180006A43
0x180006873  mov     rcx, [rbx]
0x180006876  mov     r14d, r15d
0x180006879  mov     eax, r15d
0x18000687c  jmp     short loc_180006887
0x18000687e  test    eax, eax
0x180006880  jz      short loc_18000688C
0x180006882  mov     rcx, [rcx]
0x180006885  inc     eax
0x180006887  cmp     rcx, rbx
0x18000688a  jnz     short loc_18000687E
0x18000688c  cmp     rcx, rbx
0x18000688f  lea     rax, [rcx+10h]
0x180006893  mov     rsi, r15
0x180006896  cmovnz  rsi, rax
0x18000689a  test    rsi, rsi
0x18000689d  jz      short loc_18000691E
0x18000689f  xor     edx, edx; hwndParent
0x1800068a1  xor     ecx, ecx; ClassGuid
0x1800068a3  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800068a9  mov     rdi, rax
0x1800068ac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800068b0  jz      short loc_18000691E
0x1800068b2  lea     rax, [rsp+520h+var_4E0]
0x1800068b7  mov     [rsp+520h+var_4E0.cbSize], 20h ; ' '
0x1800068bf  xor     r9d, r9d; OpenFlags
0x1800068c2  mov     [rsp+520h+DeviceInfoData], rax; DeviceInfoData
0x1800068c7  xor     r8d, r8d; hwndParent
0x1800068ca  mov     rdx, rsi; DeviceInstanceId
0x1800068cd  mov     rcx, rdi; DeviceInfoSet
0x1800068d0  call    cs:__imp_SetupDiOpenDeviceInfoW
0x1800068d6  test    eax, eax
0x1800068d8  jz      short loc_180006915
0x1800068da  mov     ecx, 32h ; '2'; nIndex
0x1800068df  call    cs:__imp_GetSystemMetrics
0x1800068e5  mov     ecx, 31h ; '1'; nIndex
0x1800068ea  mov     ebx, eax
0x1800068ec  call    cs:__imp_GetSystemMetrics
0x1800068f2  lea     rcx, [rsp+520h+var_4E8]
0x1800068f7  mov     r9d, ebx; cyIcon
0x1800068fa  mov     [rsp+520h+hIcon], rcx; hIcon
0x1800068ff  lea     rdx, [rsp+520h+var_4E0]; DeviceInfoData
0x180006904  mov     rcx, rdi; DeviceInfoSet
0x180006907  mov     dword ptr [rsp+520h+DeviceInfoData], r15d; Flags
0x18000690c  mov     r8d, eax; cxIcon
0x18000690f  call    cs:__imp_SetupDiLoadDeviceIcon
0x180006915  mov     rcx, rdi; DeviceInfoSet
0x180006918  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18000691e  mov     edi, 100000h
0x180006923  jmp     short loc_18000693D
0x180006925  mov     ecx, 1388h; dwMilliseconds
0x18000692a  call    cs:__imp_Sleep
0x180006930  cmp     r14d, 78h ; 'x'
0x180006934  jg      loc_180006A33
0x18000693a  inc     r14d
0x18000693d  lea     r8, aShellreadyeven; "ShellReadyEvent"
0x180006944  xor     edx, edx; bInheritHandle
0x180006946  mov     ecx, edi; dwDesiredAccess
0x180006948  call    cs:__imp_OpenEventW
0x18000694e  mov     rbx, rax
0x180006951  test    rax, rax
0x180006954  jz      short loc_180006925
0x180006956  or      edi, 0FFFFFFFFh
0x180006959  mov     rcx, rax; hHandle
0x18000695c  mov     edx, edi; dwMilliseconds
0x18000695e  call    cs:__imp_WaitForSingleObject
0x180006964  mov     rcx, rbx; hObject
0x180006967  call    cs:__imp_CloseHandle
0x18000696d  mov     edx, 6; dwCoInit
0x180006972  xor     ecx, ecx; pvReserved
0x180006974  call    cs:__imp_CoInitializeEx
0x18000697a  test    eax, eax
0x18000697c  js      loc_180006A33
0x180006982  xor     edx, edx; pUnkOuter
0x180006984  mov     [rsp+520h+ppv], r15
0x180006989  lea     rax, [rsp+520h+ppv]
0x18000698e  lea     r9, IID_IUserNotification; riid
0x180006995  mov     [rsp+520h+DeviceInfoData], rax; ppv
0x18000699a  lea     rcx, CLSID_UserNotification; rclsid
0x1800069a1  lea     r8d, [rdx+1]; dwClsContext
0x1800069a5  call    cs:__imp_CoCreateInstance
0x1800069ab  test    eax, eax
0x1800069ad  js      short loc_180006A2D
0x1800069af  mov     rcx, [rsp+520h+ppv]
0x1800069b4  lea     r8, [rsp+520h+Buffer]
0x1800069b9  mov     rdx, [rsp+520h+var_4E8]
0x1800069be  mov     rax, [rcx]
0x1800069c1  mov     rax, [rax+28h]
0x1800069c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ca  mov     rcx, [rsp+520h+ppv]
0x1800069cf  lea     r8, [rbp+420h+var_440]
0x1800069d3  mov     r9d, 2
0x1800069d9  lea     rdx, [rsp+520h+Buffer]
0x1800069de  mov     rax, [rcx]
0x1800069e1  mov     rax, [rax+18h]
0x1800069e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ea  mov     rcx, [rsp+520h+ppv]
0x1800069ef  xor     r9d, r9d
0x1800069f2  mov     r8d, edi
0x1800069f5  mov     edx, 4E20h
0x1800069fa  mov     rax, [rcx]
0x1800069fd  mov     rax, [rax+20h]
0x180006a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a06  mov     rcx, [rsp+520h+ppv]
0x180006a0b  xor     r8d, r8d
0x180006a0e  xor     edx, edx
0x180006a10  mov     rax, [rcx]
0x180006a13  mov     rax, [rax+30h]
0x180006a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1c  mov     rcx, [rsp+520h+ppv]
0x180006a21  mov     rax, [rcx]
0x180006a24  mov     rax, [rax+10h]
0x180006a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a2d  call    cs:__imp_CoUninitialize
0x180006a33  mov     rcx, [rsp+520h+var_4E8]; hIcon
0x180006a38  test    rcx, rcx
0x180006a3b  jz      short loc_180006A43
0x180006a3d  call    cs:__imp_DestroyIcon
0x180006a43  mov     rcx, [rbp+420h+var_40]
0x180006a4a  xor     rcx, rsp; StackCookie
0x180006a4d  call    __security_check_cookie
0x180006a52  add     rsp, 4F8h
0x180006a59  pop     r15
0x180006a5b  pop     r14
0x180006a5d  pop     rdi
0x180006a5e  pop     rsi
0x180006a5f  pop     rbx
0x180006a60  pop     rbp
0x180006a61  retn
```
