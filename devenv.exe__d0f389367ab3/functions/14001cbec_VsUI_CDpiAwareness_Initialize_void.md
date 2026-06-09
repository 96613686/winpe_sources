# VsUI::CDpiAwareness::Initialize(void)

- ea: `0x14001cbec`
- end: `0x14001cd7c`
- name: `?Initialize@CDpiAwareness@VsUI@@CAXXZ`
- size: `400`
- prototype: `void(void)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001ca30`
- `0x1400289bc`
- `0x14002e088`
- `0x14002efa4`
- `0x14002f3a0`

## callees

- `0x14001cbec`
- `0x14001cd7c`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14001cc13`
- `KERNEL32!LoadLibraryW` at `0x14001cccd`
- `KERNEL32!LoadLibraryW` at `0x14001cc13`
- `KERNEL32!LoadLibraryW` at `0x14001cccd`
- `KERNEL32!GetProcAddress` at `0x14001cc4e`
- `KERNEL32!GetProcAddress` at `0x14001cc5e`
- `KERNEL32!GetProcAddress` at `0x14001cc75`
- `KERNEL32!GetProcAddress` at `0x14001cc85`
- `KERNEL32!GetProcAddress` at `0x14001cc9c`
- `KERNEL32!GetProcAddress` at `0x14001ccac`
- `KERNEL32!GetProcAddress` at `0x14001cd08`
- `KERNEL32!GetProcAddress` at `0x14001cd1f`
- `KERNEL32!GetProcAddress` at `0x14001cc4e`
- `KERNEL32!GetProcAddress` at `0x14001cc5e`
- `KERNEL32!GetProcAddress` at `0x14001cc75`
- `KERNEL32!GetProcAddress` at `0x14001cc85`
- `KERNEL32!GetProcAddress` at `0x14001cc9c`
- `KERNEL32!GetProcAddress` at `0x14001ccac`
- `KERNEL32!GetProcAddress` at `0x14001cd08`
- `KERNEL32!GetProcAddress` at `0x14001cd1f`
- `USER32!ReleaseDC` at `0x14001cd69`
- `USER32!ReleaseDC` at `0x14001cd69`
- `USER32!GetDC` at `0x14001cd2e`
- `USER32!GetDC` at `0x14001cd2e`
- `GDI32!GetDeviceCaps` at `0x14001cd44`
- `GDI32!GetDeviceCaps` at `0x14001cd58`
- `GDI32!GetDeviceCaps` at `0x14001cd44`
- `GDI32!GetDeviceCaps` at `0x14001cd58`

## string_xrefs

- `0x14001cbff`: `user32.dll`
- `0x14001cc54`: `GetThreadDpiAwarenessContext`
- `0x14001cc8b`: `SetThreadDpiAwarenessContext`
- `0x14001cca2`: `SetThreadDpiHostingBehavior`
- `0x14001ccb9`: `shcore.dll`

## pseudocode

```c
void VsUI::CDpiAwareness::Initialize(void)
{
  LPCWSTR *SystemPath; // rax
  HMODULE LibraryW; // rbx
  _QWORD *v2; // rdx
  LPCWSTR *v3; // rax
  HMODULE v4; // rbx
  _QWORD *v5; // rdx
  HDC DC; // rax
  HDC v7; // rbx
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  if ( !VsUI::CDpiAwareness::s_isInitialized )
  {
    SystemPath = (LPCWSTR *)VsUI::CDpiAwareness::GetSystemPath(&v8, L"user32.dll");
    LibraryW = LoadLibraryW(*SystemPath);
    v2 = (_QWORD *)(v8 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 - 24 + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 8LL))(*v2);
    }
    if ( LibraryW )
    {
      GetProcAddress(LibraryW, "GetDpiForWindow");
      VsUI::CDpiAwareness::s_pGetTDAC = (struct DPI_AWARENESS_CONTEXT__ *(*)(void))GetProcAddress(
                                                                                     LibraryW,
                                                                                     "GetThreadDpiAwarenessContext");
      GetProcAddress(LibraryW, "GetWindowDpiAwarenessContext");
      VsUI::CDpiAwareness::s_pSetPDAC = (int (*)(struct DPI_AWARENESS_CONTEXT__ *))GetProcAddress(
                                                                                     LibraryW,
                                                                                     "SetProcessDpiAwarenessContext");
      GetProcAddress(LibraryW, "SetThreadDpiAwarenessContext");
      VsUI::CDpiAwareness::s_pSetTDHB = (enum DPI_HOSTING_BEHAVIOR (*)(enum DPI_HOSTING_BEHAVIOR))GetProcAddress(
                                                                                                    LibraryW,
                                                                                                    "SetThreadDpiHostingBehavior");
    }
    v3 = (LPCWSTR *)VsUI::CDpiAwareness::GetSystemPath(&v8, L"shcore.dll");
    v4 = LoadLibraryW(*v3);
    v5 = (_QWORD *)(v8 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 - 24 + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
    }
    if ( v4 )
    {
      VsUI::CDpiAwareness::s_pGetDFM = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                 v4,
                                                                                                 "GetDpiForMonitor");
      VsUI::CDpiAwareness::s_pSetPDAC_Win81 = (int (*)(enum PROCESS_DPI_AWARENESS))GetProcAddress(
                                                                                     v4,
                                                                                     "SetProcessDpiAwareness");
    }
    DC = GetDC(0);
    v7 = DC;
    if ( DC )
    {
      VsUI::CDpiAwareness::s_DeviceDpiX = GetDeviceCaps(DC, 88);
      VsUI::CDpiAwareness::s_DeviceDpiY = GetDeviceCaps(v7, 90);
      ReleaseDC(0, v7);
    }
    VsUI::CDpiAwareness::s_isInitialized = 1;
  }
}

```

## disassembly

```asm
0x14001cbec  push    rbx
0x14001cbee  sub     rsp, 20h
0x14001cbf2  cmp     cs:?s_isInitialized@CDpiAwareness@VsUI@@0_NA, 0; bool VsUI::CDpiAwareness::s_isInitialized
0x14001cbf9  jnz     loc_14001CD76
0x14001cbff  lea     rdx, aUser32Dll_0; "user32.dll"
0x14001cc06  lea     rcx, [rsp+28h+arg_0]
0x14001cc0b  call    ?GetSystemPath@CDpiAwareness@VsUI@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; VsUI::CDpiAwareness::GetSystemPath(ushort const *)
0x14001cc10  mov     rcx, [rax]; lpLibFileName
0x14001cc13  call    cs:__imp_LoadLibraryW
0x14001cc19  mov     rdx, [rsp+28h+arg_0]
0x14001cc1e  mov     rbx, rax
0x14001cc21  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001cc25  or      ecx, 0FFFFFFFFh
0x14001cc28  lock xadd [rdx+10h], ecx
0x14001cc2d  sub     ecx, 1
0x14001cc30  jg      short loc_14001CC3F
0x14001cc32  lfence
0x14001cc35  mov     rcx, [rdx]
0x14001cc38  mov     r8, [rcx]
0x14001cc3b  call    qword ptr [r8+8]
0x14001cc3f  test    rbx, rbx
0x14001cc42  jz      short loc_14001CCB9
0x14001cc44  lea     rdx, aGetdpiforwindo; "GetDpiForWindow"
0x14001cc4b  mov     rcx, rbx; hModule
0x14001cc4e  call    cs:__imp_GetProcAddress
0x14001cc54  lea     rdx, aGetthreaddpiaw; "GetThreadDpiAwarenessContext"
0x14001cc5b  mov     rcx, rbx; hModule
0x14001cc5e  call    cs:__imp_GetProcAddress
0x14001cc64  lea     rdx, aGetwindowdpiaw; "GetWindowDpiAwarenessContext"
0x14001cc6b  mov     rcx, rbx; hModule
0x14001cc6e  mov     cs:?s_pGetTDAC@CDpiAwareness@VsUI@@0P6APEAUDPI_AWARENESS_CONTEXT__@@XZEA, rax; DPI_AWARENESS_CONTEXT__ * (*VsUI::CDpiAwareness::s_pGetTDAC)(void)
0x14001cc75  call    cs:__imp_GetProcAddress
0x14001cc7b  lea     rdx, aSetprocessdpia_0; "SetProcessDpiAwarenessContext"
0x14001cc82  mov     rcx, rbx; hModule
0x14001cc85  call    cs:__imp_GetProcAddress
0x14001cc8b  lea     rdx, aSetthreaddpiaw; "SetThreadDpiAwarenessContext"
0x14001cc92  mov     rcx, rbx; hModule
0x14001cc95  mov     cs:?s_pSetPDAC@CDpiAwareness@VsUI@@0P6AHPEAUDPI_AWARENESS_CONTEXT__@@@ZEA, rax; int (*VsUI::CDpiAwareness::s_pSetPDAC)(DPI_AWARENESS_CONTEXT__ *)
0x14001cc9c  call    cs:__imp_GetProcAddress
0x14001cca2  lea     rdx, aSetthreaddpiho; "SetThreadDpiHostingBehavior"
0x14001cca9  mov     rcx, rbx; hModule
0x14001ccac  call    cs:__imp_GetProcAddress
0x14001ccb2  mov     cs:?s_pSetTDHB@CDpiAwareness@VsUI@@0P6A?AW4DPI_HOSTING_BEHAVIOR@@W43@@ZEA, rax; DPI_HOSTING_BEHAVIOR (*VsUI::CDpiAwareness::s_pSetTDHB)(DPI_HOSTING_BEHAVIOR)
0x14001ccb9  lea     rdx, aShcoreDll; "shcore.dll"
0x14001ccc0  lea     rcx, [rsp+28h+arg_0]
0x14001ccc5  call    ?GetSystemPath@CDpiAwareness@VsUI@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; VsUI::CDpiAwareness::GetSystemPath(ushort const *)
0x14001ccca  mov     rcx, [rax]; lpLibFileName
0x14001cccd  call    cs:__imp_LoadLibraryW
0x14001ccd3  mov     rdx, [rsp+28h+arg_0]
0x14001ccd8  mov     rbx, rax
0x14001ccdb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001ccdf  or      ecx, 0FFFFFFFFh
0x14001cce2  lock xadd [rdx+10h], ecx
0x14001cce7  sub     ecx, 1
0x14001ccea  jg      short loc_14001CCF9
0x14001ccec  lfence
0x14001ccef  mov     rcx, [rdx]
0x14001ccf2  mov     r8, [rcx]
0x14001ccf5  call    qword ptr [r8+8]
0x14001ccf9  test    rbx, rbx
0x14001ccfc  jz      short loc_14001CD2C
0x14001ccfe  lea     rdx, aGetdpiformonit; "GetDpiForMonitor"
0x14001cd05  mov     rcx, rbx; hModule
0x14001cd08  call    cs:__imp_GetProcAddress
0x14001cd0e  lea     rdx, aSetprocessdpia; "SetProcessDpiAwareness"
0x14001cd15  mov     rcx, rbx; hModule
0x14001cd18  mov     cs:?s_pGetDFM@CDpiAwareness@VsUI@@0P6AJPEAUHMONITOR__@@W4_MONITOR_DPI_TYPE@@PEAI2@ZEA, rax; long (*VsUI::CDpiAwareness::s_pGetDFM)(HMONITOR__ *,_MONITOR_DPI_TYPE,uint *,uint *)
0x14001cd1f  call    cs:__imp_GetProcAddress
0x14001cd25  mov     cs:?s_pSetPDAC_Win81@CDpiAwareness@VsUI@@0P6AJW4PROCESS_DPI_AWARENESS@@@ZEA, rax; long (*VsUI::CDpiAwareness::s_pSetPDAC_Win81)(PROCESS_DPI_AWARENESS)
0x14001cd2c  xor     ecx, ecx; hWnd
0x14001cd2e  call    cs:__imp_GetDC
0x14001cd34  mov     rbx, rax
0x14001cd37  test    rax, rax
0x14001cd3a  jz      short loc_14001CD6F
0x14001cd3c  mov     edx, 58h ; 'X'; index
0x14001cd41  mov     rcx, rax; hdc
0x14001cd44  call    cs:__imp_GetDeviceCaps
0x14001cd4a  mov     edx, 5Ah ; 'Z'; index
0x14001cd4f  mov     rcx, rbx; hdc
0x14001cd52  mov     cs:?s_DeviceDpiX@CDpiAwareness@VsUI@@0HA, eax; int VsUI::CDpiAwareness::s_DeviceDpiX
0x14001cd58  call    cs:__imp_GetDeviceCaps
0x14001cd5e  mov     rdx, rbx; hDC
0x14001cd61  xor     ecx, ecx; hWnd
0x14001cd63  mov     cs:?s_DeviceDpiY@CDpiAwareness@VsUI@@0HA, eax; int VsUI::CDpiAwareness::s_DeviceDpiY
0x14001cd69  call    cs:__imp_ReleaseDC
0x14001cd6f  mov     cs:?s_isInitialized@CDpiAwareness@VsUI@@0_NA, 1; bool VsUI::CDpiAwareness::s_isInitialized
0x14001cd76  add     rsp, 20h
0x14001cd7a  pop     rbx
0x14001cd7b  retn
```
