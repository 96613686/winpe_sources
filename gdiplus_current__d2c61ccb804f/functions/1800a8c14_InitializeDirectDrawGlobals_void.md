# InitializeDirectDrawGlobals(void)

- ea: `0x1800a8c14`
- end: `0x1800a8d83`
- name: `?InitializeDirectDrawGlobals@@YAHXZ`
- size: `367`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800a8758`

## callees

- `0x1800a8c14`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800a8c66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800a8c66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8c8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8cb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8ce0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8c8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8cb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a8ce0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8c43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8c43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8d70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8d70`

## string_xrefs

- `0x1800a8c54`: `ddraw.dll`
- `0x1800a8caf`: `DirectDrawCreateEx`

## pseudocode

```c
__int64 InitializeDirectDrawGlobals(void)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax

  if ( Globals::DirectDrawInitialized )
    return 1;
  if ( Globals::DirectDrawInitAttempted )
    return 0;
  EnterCriticalSection(&LoadLibraryCriticalSection::critSec);
  v1 = 1;
  Globals::DirectDrawInitAttempted = 1;
  Library = LoadLibraryExA("ddraw.dll", 0, 0);
  Globals::DdrawHandle = Library;
  if ( Library
    && (Globals::GetDdrawSurfaceFromDcFunction = (int (*)(HDC, struct IDirectDrawSurface **, HDC *))GetProcAddress(Library, "GetSurfaceFromDC")) != 0
    && (Globals::DirectDrawCreateExFunction = (int (*)(struct _GUID *, void *, const struct _GUID *, struct IUnknown *))GetProcAddress(Globals::DdrawHandle, "DirectDrawCreateEx")) != 0
    && (Globals::DirectDrawEnumerateExFunction = (int (*)(int (*)(struct _GUID *, char *, char *, void *, HMONITOR), void *, unsigned int))GetProcAddress(Globals::DdrawHandle, "DirectDrawEnumerateExA")) != 0
    && (int)((__int64 (__fastcall *)(_QWORD, struct IDirectDraw7 **, GUID *, _QWORD))Globals::DirectDrawCreateExFunction)(
              0,
              &Globals::DirectDraw,
              &IID_IDirectDraw7,
              0) >= 0
    && ((int (__fastcall *)(struct IDirectDraw7 *, _QWORD, __int64))Globals::DirectDraw->lpVtbl->SetCooperativeLevel)(
         Globals::DirectDraw,
         0,
         8) >= 0
    && ((__int64 (__fastcall *)(struct IDirectDraw7 *, GUID *, struct IDirect3D7 **))Globals::DirectDraw->lpVtbl->QueryInterface)(
         Globals::DirectDraw,
         &IID_IDirect3D7,
         &Globals::Direct3D) >= 0 )
  {
    Globals::DirectDrawInitialized = 1;
  }
  else
  {
    v1 = 0;
  }
  LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
  return v1;
}

```

## disassembly

```asm
0x1800a8c14  push    rbx
0x1800a8c16  sub     rsp, 30h
0x1800a8c1a  cmp     cs:?DirectDrawInitialized@Globals@@3HA, 0; int Globals::DirectDrawInitialized
0x1800a8c21  jnz     short loc_1800A8C35
0x1800a8c23  cmp     cs:?DirectDrawInitAttempted@Globals@@3HA, 0; int Globals::DirectDrawInitAttempted
0x1800a8c2a  jz      short loc_1800A8C3C
0x1800a8c2c  xor     eax, eax
0x1800a8c2e  add     rsp, 30h
0x1800a8c32  pop     rbx
0x1800a8c33  retn
0x1800a8c35  mov     eax, 1
0x1800a8c3a  jmp     short loc_1800A8C2E
0x1800a8c3c  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a8c43  call    cs:__imp_EnterCriticalSection
0x1800a8c4a  nop     dword ptr [rax+rax+00h]
0x1800a8c4f  mov     ebx, 1
0x1800a8c54  lea     rcx, aDdrawDll; "ddraw.dll"
0x1800a8c5b  xor     r8d, r8d; dwFlags
0x1800a8c5e  mov     cs:?DirectDrawInitAttempted@Globals@@3HA, ebx; int Globals::DirectDrawInitAttempted
0x1800a8c64  xor     edx, edx; hFile
0x1800a8c66  call    cs:__imp_LoadLibraryExA
0x1800a8c6d  nop     dword ptr [rax+rax+00h]
0x1800a8c72  mov     cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Globals::DdrawHandle
0x1800a8c79  test    rax, rax
0x1800a8c7c  jz      loc_1800A8D67
0x1800a8c82  lea     rdx, aGetsurfacefrom; "GetSurfaceFromDC"
0x1800a8c89  mov     rcx, rax; hModule
0x1800a8c8c  call    cs:__imp_GetProcAddress
0x1800a8c93  nop     dword ptr [rax+rax+00h]
0x1800a8c98  mov     cs:?GetDdrawSurfaceFromDcFunction@Globals@@3P6AJPEAUHDC__@@PEAPEAUIDirectDrawSurface@@PEAPEAU2@@ZEA, rax; long (*Globals::GetDdrawSurfaceFromDcFunction)(HDC__ *,IDirectDrawSurface * *,HDC__ * *)
0x1800a8c9f  test    rax, rax
0x1800a8ca2  jz      loc_1800A8D67
0x1800a8ca8  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hModule
0x1800a8caf  lea     rdx, aDirectdrawcrea; "DirectDrawCreateEx"
0x1800a8cb6  call    cs:__imp_GetProcAddress
0x1800a8cbd  nop     dword ptr [rax+rax+00h]
0x1800a8cc2  mov     cs:?DirectDrawCreateExFunction@Globals@@3P6AJPEAU_GUID@@PEAXAEBU2@PEAUIUnknown@@@ZEA, rax; long (*Globals::DirectDrawCreateExFunction)(_GUID *,void *,_GUID const &,IUnknown *)
0x1800a8cc9  test    rax, rax
0x1800a8ccc  jz      loc_1800A8D67
0x1800a8cd2  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hModule
0x1800a8cd9  lea     rdx, aDirectdrawenum; "DirectDrawEnumerateExA"
0x1800a8ce0  call    cs:__imp_GetProcAddress
0x1800a8ce7  nop     dword ptr [rax+rax+00h]
0x1800a8cec  mov     cs:?DirectDrawEnumerateExFunction@Globals@@3P6AJP6AHPEAU_GUID@@PEAD1PEAXPEAUHMONITOR__@@@Z2K@ZEA, rax; long (*Globals::DirectDrawEnumerateExFunction)(int (*)(_GUID *,char *,char *,void *,HMONITOR__ *),void *,ulong)
0x1800a8cf3  test    rax, rax
0x1800a8cf6  jz      short loc_1800A8D67
0x1800a8cf8  mov     rax, cs:?DirectDrawCreateExFunction@Globals@@3P6AJPEAU_GUID@@PEAXAEBU2@PEAUIUnknown@@@ZEA; long (*Globals::DirectDrawCreateExFunction)(_GUID *,void *,_GUID const &,IUnknown *)
0x1800a8cff  lea     r8, IID_IDirectDraw7
0x1800a8d06  xor     r9d, r9d
0x1800a8d09  lea     rdx, ?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800a8d10  xor     ecx, ecx
0x1800a8d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8d17  test    eax, eax
0x1800a8d19  js      short loc_1800A8D67
0x1800a8d1b  mov     rcx, cs:?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800a8d22  lea     r8d, [rbx+7]
0x1800a8d26  xor     edx, edx
0x1800a8d28  mov     rax, [rcx]
0x1800a8d2b  mov     rax, [rax+0A0h]
0x1800a8d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8d37  test    eax, eax
0x1800a8d39  js      short loc_1800A8D67
0x1800a8d3b  mov     rcx, cs:?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800a8d42  lea     r8, ?Direct3D@Globals@@3PEAUIDirect3D7@@EA; IDirect3D7 * Globals::Direct3D
0x1800a8d49  lea     rdx, IID_IDirect3D7
0x1800a8d50  mov     rax, [rcx]
0x1800a8d53  mov     rax, [rax]
0x1800a8d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8d5b  test    eax, eax
0x1800a8d5d  js      short loc_1800A8D67
0x1800a8d5f  mov     cs:?DirectDrawInitialized@Globals@@3HA, ebx; int Globals::DirectDrawInitialized
0x1800a8d65  jmp     short loc_1800A8D69
0x1800a8d67  xor     ebx, ebx
0x1800a8d69  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a8d70  call    cs:__imp_LeaveCriticalSection
0x1800a8d77  nop     dword ptr [rax+rax+00h]
0x1800a8d7c  mov     eax, ebx
0x1800a8d7e  jmp     loc_1800A8C2E
```
