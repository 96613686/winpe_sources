# InitializeDirectDrawGlobals(void)

- ea: `0x1800ca344`
- end: `0x1800ca4b3`
- name: `?InitializeDirectDrawGlobals@@YAHXZ`
- size: `367`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018a18`

## callees

- `0x1800ca344`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca3bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca3e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca410`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca3bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca3e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca410`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800ca396`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800ca396`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ca373`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ca373`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca4a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca4a0`

## string_xrefs

- `0x1800ca384`: `ddraw.dll`
- `0x1800ca3df`: `DirectDrawCreateEx`

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
    && (Globals::GetDdrawSurfaceFromDcFunction = (int (*)(struct HDC__ *, struct IDirectDrawSurface **, struct HDC__ **))GetProcAddress(Library, "GetSurfaceFromDC")) != 0
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
0x1800ca344  push    rbx
0x1800ca346  sub     rsp, 30h
0x1800ca34a  cmp     cs:?DirectDrawInitialized@Globals@@3HA, 0; int Globals::DirectDrawInitialized
0x1800ca351  jnz     short loc_1800CA365
0x1800ca353  cmp     cs:?DirectDrawInitAttempted@Globals@@3HA, 0; int Globals::DirectDrawInitAttempted
0x1800ca35a  jz      short loc_1800CA36C
0x1800ca35c  xor     eax, eax
0x1800ca35e  add     rsp, 30h
0x1800ca362  pop     rbx
0x1800ca363  retn
0x1800ca365  mov     eax, 1
0x1800ca36a  jmp     short loc_1800CA35E
0x1800ca36c  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800ca373  call    cs:__imp_EnterCriticalSection
0x1800ca37a  nop     dword ptr [rax+rax+00h]
0x1800ca37f  mov     ebx, 1
0x1800ca384  lea     rcx, aDdrawDll; "ddraw.dll"
0x1800ca38b  xor     r8d, r8d; dwFlags
0x1800ca38e  mov     cs:?DirectDrawInitAttempted@Globals@@3HA, ebx; int Globals::DirectDrawInitAttempted
0x1800ca394  xor     edx, edx; hFile
0x1800ca396  call    cs:__imp_LoadLibraryExA
0x1800ca39d  nop     dword ptr [rax+rax+00h]
0x1800ca3a2  mov     cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Globals::DdrawHandle
0x1800ca3a9  test    rax, rax
0x1800ca3ac  jz      loc_1800CA497
0x1800ca3b2  lea     rdx, aGetsurfacefrom; "GetSurfaceFromDC"
0x1800ca3b9  mov     rcx, rax; hModule
0x1800ca3bc  call    cs:__imp_GetProcAddress
0x1800ca3c3  nop     dword ptr [rax+rax+00h]
0x1800ca3c8  mov     cs:?GetDdrawSurfaceFromDcFunction@Globals@@3P6AJPEAUHDC__@@PEAPEAUIDirectDrawSurface@@PEAPEAU2@@ZEA, rax; long (*Globals::GetDdrawSurfaceFromDcFunction)(HDC__ *,IDirectDrawSurface * *,HDC__ * *)
0x1800ca3cf  test    rax, rax
0x1800ca3d2  jz      loc_1800CA497
0x1800ca3d8  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hModule
0x1800ca3df  lea     rdx, aDirectdrawcrea; "DirectDrawCreateEx"
0x1800ca3e6  call    cs:__imp_GetProcAddress
0x1800ca3ed  nop     dword ptr [rax+rax+00h]
0x1800ca3f2  mov     cs:?DirectDrawCreateExFunction@Globals@@3P6AJPEAU_GUID@@PEAXAEBU2@PEAUIUnknown@@@ZEA, rax; long (*Globals::DirectDrawCreateExFunction)(_GUID *,void *,_GUID const &,IUnknown *)
0x1800ca3f9  test    rax, rax
0x1800ca3fc  jz      loc_1800CA497
0x1800ca402  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hModule
0x1800ca409  lea     rdx, aDirectdrawenum; "DirectDrawEnumerateExA"
0x1800ca410  call    cs:__imp_GetProcAddress
0x1800ca417  nop     dword ptr [rax+rax+00h]
0x1800ca41c  mov     cs:?DirectDrawEnumerateExFunction@Globals@@3P6AJP6AHPEAU_GUID@@PEAD1PEAXPEAUHMONITOR__@@@Z2K@ZEA, rax; long (*Globals::DirectDrawEnumerateExFunction)(int (*)(_GUID *,char *,char *,void *,HMONITOR__ *),void *,ulong)
0x1800ca423  test    rax, rax
0x1800ca426  jz      short loc_1800CA497
0x1800ca428  mov     rax, cs:?DirectDrawCreateExFunction@Globals@@3P6AJPEAU_GUID@@PEAXAEBU2@PEAUIUnknown@@@ZEA; long (*Globals::DirectDrawCreateExFunction)(_GUID *,void *,_GUID const &,IUnknown *)
0x1800ca42f  lea     r8, IID_IDirectDraw7
0x1800ca436  xor     r9d, r9d
0x1800ca439  lea     rdx, ?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800ca440  xor     ecx, ecx
0x1800ca442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca447  test    eax, eax
0x1800ca449  js      short loc_1800CA497
0x1800ca44b  mov     rcx, cs:?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800ca452  lea     r8d, [rbx+7]
0x1800ca456  xor     edx, edx
0x1800ca458  mov     rax, [rcx]
0x1800ca45b  mov     rax, [rax+0A0h]
0x1800ca462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca467  test    eax, eax
0x1800ca469  js      short loc_1800CA497
0x1800ca46b  mov     rcx, cs:?DirectDraw@Globals@@3PEAUIDirectDraw7@@EA; IDirectDraw7 * Globals::DirectDraw
0x1800ca472  lea     r8, ?Direct3D@Globals@@3PEAUIDirect3D7@@EA; IDirect3D7 * Globals::Direct3D
0x1800ca479  lea     rdx, IID_IDirect3D7
0x1800ca480  mov     rax, [rcx]
0x1800ca483  mov     rax, [rax]
0x1800ca486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca48b  test    eax, eax
0x1800ca48d  js      short loc_1800CA497
0x1800ca48f  mov     cs:?DirectDrawInitialized@Globals@@3HA, ebx; int Globals::DirectDrawInitialized
0x1800ca495  jmp     short loc_1800CA499
0x1800ca497  xor     ebx, ebx
0x1800ca499  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800ca4a0  call    cs:__imp_LeaveCriticalSection
0x1800ca4a7  nop     dword ptr [rax+rax+00h]
0x1800ca4ac  mov     eax, ebx
0x1800ca4ae  jmp     loc_1800CA35E
```
