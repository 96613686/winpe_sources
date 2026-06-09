# PSetupElevatedLegacyPrintDriverInstallW(HWND__ *,HINSTANCE__ *,ushort const *,uint)

- ea: `0x18002c0f0`
- end: `0x18002c3c7`
- name: `?PSetupElevatedLegacyPrintDriverInstallW@@YAKPEAUHWND__@@PEAUHINSTANCE__@@PEBGI@Z`
- size: `727`
- prototype: `unsigned int(HWND, HINSTANCE, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x18000c368`
- `0x18000f698`
- `0x18001c5c0`
- `0x180026820`
- `0x180027750`
- `0x1800284d0`
- `0x1800288a0`
- `0x18002a104`
- `0x18002b6f0`
- `0x18002c0f0`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18002c3c0`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18002c3c0`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18002c37f`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18002c37f`
- `SETUPAPI!SetupOpenFileQueue` at `0x18002c1a0`
- `SETUPAPI!SetupOpenFileQueue` at `0x18002c1a0`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18002c1c8`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18002c1c8`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002c376`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002c376`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18002c349`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18002c349`
- `SETUPAPI!SetupCloseFileQueue` at `0x18002c38e`
- `SETUPAPI!SetupCloseFileQueue` at `0x18002c38e`

## pseudocode

```c
__int64 __fastcall PSetupElevatedLegacyPrintDriverInstallW(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  __int64 result; // rax
  signed int LastErrorAsFailHR; // ebx
  int v6; // eax
  void *v7; // rdi
  NCoreLibrary *v8; // rcx
  HSPFILEQ v9; // r14
  NCoreLibrary *v10; // rcx
  HDEVINFO DeviceInfoList; // rsi
  NCoreLibrary *v12; // rcx
  NCoreLibrary *v13; // rcx
  NCoreLibrary *v14; // rcx
  NCoreLibrary *v15; // rcx
  struct _PSETUP_LOCAL_DATA *v16; // r15
  int v17; // eax
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  void *v19; // [rsp+58h] [rbp-A8h] BYREF
  void *v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+70h] [rbp-90h] BYREF

  v20[0] = 0;
  v19 = 0;
  LODWORD(v18) = 0;
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
    return 2147943660LL;
  if ( a3 )
  {
    v6 = CheckElevatedLUAAndInitialize(a3, 0x658u, 0, v20, &v19);
    v7 = v19;
    LastErrorAsFailHR = v6;
    if ( v6 >= 0 )
    {
      v9 = SetupOpenFileQueue();
      if ( v9 != (HSPFILEQ)-1LL || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v8), LastErrorAsFailHR >= 0) )
      {
        DeviceInfoList = SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, *(HWND *)v7);
        if ( DeviceInfoList != (HDEVINFO)-1LL
          || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v10), LastErrorAsFailHR >= 0) )
        {
          if ( (unsigned int)SetAltPlatform(DeviceInfoList, 0, 0)
            || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v12), LastErrorAsFailHR >= 0) )
          {
            if ( (unsigned int)PSetupBuildDriversFromPath(DeviceInfoList, (unsigned __int16 *)v7 + 545)
              || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13), LastErrorAsFailHR >= 0) )
            {
              if ( (unsigned int)PreSelectDriverEx((int)DeviceInfoList, 0, (LPCWSTR)v7 + 12, *((_DWORD *)v7 + 2), 0)
                || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v14), LastErrorAsFailHR >= 0) )
              {
                v16 = (struct _PSETUP_LOCAL_DATA *)BuildInternalData((int)DeviceInfoList, 0);
                if ( v16 || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v15), LastErrorAsFailHR >= 0) )
                {
                  v17 = LegacyPrintDriverInstall(
                          DeviceInfoList,
                          v16,
                          *(_QWORD *)v7,
                          *((_DWORD *)v7 + 2),
                          *((_DWORD *)v7 + 3),
                          (LPWSTR)(((unsigned __int64)v7 + 1054) & -(__int64)(*((_WORD *)v7 + 527) != 0)),
                          (const WCHAR *)(((unsigned __int64)v7 + 534) & -(__int64)(*((_WORD *)v7 + 267) != 0)),
                          *((_DWORD *)v7 + 4),
                          *((_DWORD *)v7 + 5),
                          (unsigned int *)&v18);
                  LastErrorAsFailHR = v17;
                  if ( v17 > 0 )
                    LastErrorAsFailHR = (unsigned __int16)v17 | 0x80070000;
                  if ( LastErrorAsFailHR >= 0 )
                    *((_DWORD *)v7 + 403) = v18;
                  if ( v16 )
                    DestroyLocalData(v16);
                }
              }
            }
          }
          if ( DeviceInfoList != (HDEVINFO)-1LL )
          {
            memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
            DeviceInstallParams.cbSize = 584;
            if ( SetupDiGetDeviceInstallParamsW(DeviceInfoList, 0, &DeviceInstallParams)
              && DeviceInstallParams.FileQueue == v9 )
            {
              DeviceInstallParams.FlagsEx &= ~0x10000000u;
              DeviceInstallParams.Flags &= ~8u;
              DeviceInstallParams.FileQueue = (HSPFILEQ)-1LL;
              SetupDiSetDeviceInstallParamsW(DeviceInfoList, 0, &DeviceInstallParams);
            }
            SetupDiDestroyDeviceInfoList(DeviceInfoList);
          }
        }
        if ( v9 != (HSPFILEQ)-1LL )
          SetupCloseFileQueue(v9);
      }
    }
    if ( v7 )
      *((_DWORD *)v7 + 404) = LastErrorAsFailHR;
  }
  else
  {
    LastErrorAsFailHR = -2147024809;
  }
  FreeSharedMemory(&v19, v20);
  result = StatusFromHResult((unsigned int)LastErrorAsFailHR);
  if ( (_WORD)LastErrorAsFailHR )
    ExitProcess(result);
  return result;
}

```

## disassembly

```asm
0x18002c0f0  push    rbp
0x18002c0f2  push    rbx
0x18002c0f3  push    rsi
0x18002c0f4  push    rdi
0x18002c0f5  push    r14
0x18002c0f7  push    r15
0x18002c0f9  lea     rbp, [rsp-1D8h]
0x18002c101  sub     rsp, 2D8h
0x18002c108  mov     rax, cs:__security_cookie
0x18002c10f  xor     rax, rsp
0x18002c112  mov     [rbp+200h+var_40], rax
0x18002c119  mov     rbx, r8
0x18002c11c  mov     [rsp+300h+var_2A0], 0
0x18002c125  mov     [rsp+300h+var_2A8], 0
0x18002c12e  mov     dword ptr [rsp+300h+var_2B0], 0
0x18002c136  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x18002c13b  test    al, al
0x18002c13d  jz      short loc_18002C163
0x18002c13f  mov     eax, 800704ECh
0x18002c144  mov     rcx, [rbp+200h+var_40]
0x18002c14b  xor     rcx, rsp; StackCookie
0x18002c14e  call    __security_check_cookie
0x18002c153  add     rsp, 2D8h
0x18002c15a  pop     r15
0x18002c15c  pop     r14
0x18002c15e  pop     rdi
0x18002c15f  pop     rsi
0x18002c160  pop     rbx
0x18002c161  pop     rbp
0x18002c162  retn
0x18002c163  test    rbx, rbx
0x18002c166  jnz     short loc_18002C172
0x18002c168  mov     ebx, 80070057h
0x18002c16d  jmp     loc_18002C39F
0x18002c172  lea     rax, [rsp+300h+var_2A8]
0x18002c177  xor     r8d, r8d; int
0x18002c17a  lea     r9, [rsp+300h+var_2A0]; void **
0x18002c17f  mov     [rsp+300h+AlternateDefaultCatalogFile], rax; void **
0x18002c184  mov     edx, 658h; dwNumberOfBytesToMap
0x18002c189  mov     rcx, rbx; lpName
0x18002c18c  call    ?CheckElevatedLUAAndInitialize@@YAJPEBG_KHPEAPEAX2@Z; CheckElevatedLUAAndInitialize(ushort const *,unsigned __int64,int,void * *,void * *)
0x18002c191  mov     rdi, [rsp+300h+var_2A8]
0x18002c196  mov     ebx, eax
0x18002c198  test    eax, eax
0x18002c19a  js      loc_18002C394
0x18002c1a0  call    cs:__imp_SetupOpenFileQueue
0x18002c1a6  mov     r14, rax
0x18002c1a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c1ad  jnz     short loc_18002C1BE
0x18002c1af  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002c1b4  mov     ebx, eax
0x18002c1b6  test    eax, eax
0x18002c1b8  js      loc_18002C394
0x18002c1be  mov     rdx, [rdi]; hwndParent
0x18002c1c1  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x18002c1c8  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18002c1ce  mov     rsi, rax
0x18002c1d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c1d5  jnz     short loc_18002C1E6
0x18002c1d7  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002c1dc  mov     ebx, eax
0x18002c1de  test    eax, eax
0x18002c1e0  js      loc_18002C385
0x18002c1e6  mov     r8d, [rdi+8]
0x18002c1ea  mov     r9, r14
0x18002c1ed  xor     edx, edx; lpString1
0x18002c1ef  mov     [rsp+300h+AlternateDefaultCatalogFile], 0; AlternateDefaultCatalogFile
0x18002c1f8  mov     rcx, rsi; DeviceInfoSet
0x18002c1fb  call    SetAltPlatform
0x18002c200  test    eax, eax
0x18002c202  jnz     short loc_18002C213
0x18002c204  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002c209  mov     ebx, eax
0x18002c20b  test    eax, eax
0x18002c20d  js      loc_18002C31F
0x18002c213  lea     rdx, [rdi+442h]; unsigned __int16 *
0x18002c21a  mov     r8d, 1
0x18002c220  mov     rcx, rsi; DeviceInfoSet
0x18002c223  call    PSetupBuildDriversFromPath
0x18002c228  test    eax, eax
0x18002c22a  jnz     short loc_18002C23B
0x18002c22c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002c231  mov     ebx, eax
0x18002c233  test    eax, eax
0x18002c235  js      loc_18002C31F
0x18002c23b  mov     eax, [rdi+8]
0x18002c23e  lea     r8, [rdi+18h]; LPCWSTR
0x18002c242  mov     dword ptr [rsp+300h+pName], 0; int
0x18002c24a  xor     r9d, r9d
0x18002c24d  xor     edx, edx; lpString1
0x18002c24f  mov     dword ptr [rsp+300h+AlternateDefaultCatalogFile], eax; int
0x18002c253  mov     rcx, rsi; int
0x18002c256  call    PreSelectDriverEx
0x18002c25b  test    eax, eax
0x18002c25d  jnz     short loc_18002C26E
0x18002c25f  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002c264  mov     ebx, eax
0x18002c266  test    eax, eax
0x18002c268  js      loc_18002C31F
0x18002c26e  mov     r8d, [rdi+8]
0x18002c272  xor     edx, edx; int
0x18002c274  mov     rcx, rsi; int
0x18002c277  call    BuildInternalData
0x18002c27c  mov     r15, rax
0x18002c27f  test    rax, rax
0x18002c282  jnz     short loc_18002C293
0x18002c284  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002c289  mov     ebx, eax
0x18002c28b  test    eax, eax
0x18002c28d  js      loc_18002C31F
0x18002c293  lea     rdx, [rdi+216h]
0x18002c29a  movzx   ecx, word ptr [rdx]
0x18002c29d  lea     r8, [rdi+41Eh]
0x18002c2a4  movzx   eax, word ptr [r8]
0x18002c2a8  neg     cx
0x18002c2ab  sbb     r9, r9
0x18002c2ae  and     r9, rdx
0x18002c2b1  mov     rdx, r15; struct _PSETUP_LOCAL_DATA *
0x18002c2b4  neg     ax
0x18002c2b7  lea     rax, [rsp+300h+var_2B0]
0x18002c2bc  mov     [rsp+300h+var_2B8], rax; __int64
0x18002c2c1  sbb     rcx, rcx
0x18002c2c4  mov     eax, [rdi+14h]
0x18002c2c7  and     rcx, r8
0x18002c2ca  mov     r8, [rdi]; Owner
0x18002c2cd  mov     [rsp+300h+var_2C0], eax; int
0x18002c2d1  mov     eax, [rdi+10h]
0x18002c2d4  mov     dword ptr [rsp+300h+var_2C8], eax; char
0x18002c2d8  mov     eax, [rdi+0Ch]
0x18002c2db  mov     [rsp+300h+var_2D0], r9; __int64
0x18002c2e0  mov     r9d, [rdi+8]
0x18002c2e4  mov     [rsp+300h+pName], rcx; pName
0x18002c2e9  mov     rcx, rsi; DeviceInfoSet
0x18002c2ec  mov     dword ptr [rsp+300h+AlternateDefaultCatalogFile], eax; int
0x18002c2f0  call    LegacyPrintDriverInstall
0x18002c2f5  mov     ebx, eax
0x18002c2f7  test    eax, eax
0x18002c2f9  jle     short loc_18002C304
0x18002c2fb  movzx   ebx, ax
0x18002c2fe  or      ebx, 80070000h
0x18002c304  test    ebx, ebx
0x18002c306  js      short loc_18002C312
0x18002c308  mov     eax, dword ptr [rsp+300h+var_2B0]
0x18002c30c  mov     [rdi+64Ch], eax
0x18002c312  test    r15, r15
0x18002c315  jz      short loc_18002C31F
0x18002c317  mov     rcx, r15; hMem
0x18002c31a  call    DestroyLocalData
0x18002c31f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002c323  jz      short loc_18002C385
0x18002c325  xor     edx, edx; Val
0x18002c327  lea     rcx, [rsp+300h+DeviceInstallParams.Flags]; void *
0x18002c32c  mov     r8d, 244h; Size
0x18002c332  call    memset_0
0x18002c337  lea     r8, [rsp+300h+DeviceInstallParams]; DeviceInstallParams
0x18002c33c  mov     [rsp+300h+DeviceInstallParams.cbSize], 248h
0x18002c344  xor     edx, edx; DeviceInfoData
0x18002c346  mov     rcx, rsi; DeviceInfoSet
0x18002c349  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x18002c34f  test    eax, eax
0x18002c351  jz      short loc_18002C37C
0x18002c353  cmp     [rbp+200h+DeviceInstallParams.FileQueue], r14
0x18002c357  jnz     short loc_18002C37C
0x18002c359  btr     [rsp+300h+DeviceInstallParams.FlagsEx], 1Ch
0x18002c35f  lea     r8, [rsp+300h+DeviceInstallParams]; DeviceInstallParams
0x18002c364  and     [rsp+300h+DeviceInstallParams.Flags], 0FFFFFFF7h
0x18002c369  xor     edx, edx; DeviceInfoData
0x18002c36b  mov     rcx, rsi; DeviceInfoSet
0x18002c36e  mov     [rbp+200h+DeviceInstallParams.FileQueue], 0FFFFFFFFFFFFFFFFh
0x18002c376  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x18002c37c  mov     rcx, rsi; DeviceInfoSet
0x18002c37f  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18002c385  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002c389  jz      short loc_18002C394
0x18002c38b  mov     rcx, r14; QueueHandle
0x18002c38e  call    cs:__imp_SetupCloseFileQueue
0x18002c394  test    rdi, rdi
0x18002c397  jz      short loc_18002C39F
0x18002c399  mov     [rdi+650h], ebx
0x18002c39f  lea     rdx, [rsp+300h+var_2A0]; void **
0x18002c3a4  lea     rcx, [rsp+300h+var_2A8]; void **
0x18002c3a9  call    ?FreeSharedMemory@@YAXPEAPEAX0@Z; FreeSharedMemory(void * *,void * *)
0x18002c3ae  mov     ecx, ebx
0x18002c3b0  call    StatusFromHResult
0x18002c3b5  test    bx, bx
0x18002c3b8  jz      loc_18002C144
0x18002c3be  mov     ecx, eax; uExitCode
0x18002c3c0  call    cs:__imp_ExitProcess
```
