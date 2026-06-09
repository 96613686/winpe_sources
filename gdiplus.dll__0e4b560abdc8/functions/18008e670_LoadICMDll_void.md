# LoadICMDll(void)

- ea: `0x18008e670`
- end: `0x18008e868`
- name: `?LoadICMDll@@YAJXZ`
- size: `504`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18008d538`
- `0x18008e33c`
- `0x180106fe4`
- `0x18014fb68`

## callees

- `0x18008e670`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e6f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e715`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e736`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e757`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e778`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e799`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e7ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e7db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e6f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e715`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e736`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e757`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e778`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e799`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e7ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e7db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008e6d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008e6d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e67d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e67d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e69d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e69d`

## string_xrefs

- `0x18008e6cb`: `mscms.dll`
- `0x18008e707`: `OpenColorProfileW`
- `0x18008e6ea`: `OpenColorProfileA`
- `0x18008e728`: `CreateMultiProfileTransform`
- `0x18008e78b`: `DeleteColorTransform`

## pseudocode

```c
__int64 LoadICMDll(void)
{
  unsigned int v0; // edi
  HMODULE Library; // rax
  int (*ProcAddress)(void *, unsigned __int8 *, unsigned int *); // rax

  EnterCriticalSection(&LoadLibraryCriticalSection::critSec);
  if ( IcmState == 1 )
    goto LABEL_2;
  v0 = -2147467259;
  if ( IcmState != 2 )
  {
    IcmState = 2;
    Library = LoadLibraryExW(L"mscms.dll", 0, 0);
    ghInstICMDll = Library;
    if ( Library )
    {
      pfnOpenColorProfile = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(Library, "OpenColorProfileA");
      pfnOpenColorProfileW = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(ghInstICMDll, "OpenColorProfileW");
      pfnCreateMultiProfileTransform = (void *(*)(void **, unsigned int, unsigned int *, unsigned int, unsigned int, unsigned int))GetProcAddress(ghInstICMDll, "CreateMultiProfileTransform");
      pfnTranslateBitmapBits = (int (*)(void *, void *, enum BMFORMAT, unsigned int, unsigned int, unsigned int, void *, enum BMFORMAT, unsigned int, int (*)(unsigned int, unsigned int, __int64), unsigned int))GetProcAddress(ghInstICMDll, "TranslateBitmapBits");
      pfnCloseColorProfile = (int (*)(void *))GetProcAddress(ghInstICMDll, "CloseColorProfile");
      pfnDeleteColorTransform = (int (*)(void *))GetProcAddress(ghInstICMDll, "DeleteColorTransform");
      pfnGetStandardColorSpaceProfileW = (int (*)(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *))GetProcAddress(ghInstICMDll, "GetStandardColorSpaceProfileW");
      ProcAddress = (int (*)(void *, unsigned __int8 *, unsigned int *))GetProcAddress(
                                                                          ghInstICMDll,
                                                                          "GetColorProfileFromHandle");
      pfnGetColorProfileFromHandle = ProcAddress;
      if ( pfnOpenColorProfile )
      {
        if ( pfnOpenColorProfileW
          && pfnCloseColorProfile
          && pfnCreateMultiProfileTransform
          && pfnDeleteColorTransform
          && pfnTranslateBitmapBits
          && pfnGetStandardColorSpaceProfileW
          && ProcAddress )
        {
          IcmState = 1;
LABEL_2:
          v0 = 0;
        }
      }
    }
  }
  LeaveCriticalSection(&LoadLibraryCriticalSection::critSec);
  return v0;
}

```

## disassembly

```asm
0x18008e670  push    rdi
0x18008e672  sub     rsp, 20h
0x18008e676  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008e67d  call    cs:__imp_EnterCriticalSection
0x18008e684  nop     dword ptr [rax+rax+00h]
0x18008e689  mov     eax, cs:?IcmState@@3W4IcmDllLoadState@@A; IcmDllLoadState IcmState
0x18008e68f  cmp     eax, 1
0x18008e692  jnz     short loc_18008E6B2
0x18008e694  xor     edi, edi
0x18008e696  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008e69d  call    cs:__imp_LeaveCriticalSection
0x18008e6a4  nop     dword ptr [rax+rax+00h]
0x18008e6a9  mov     eax, edi
0x18008e6ab  add     rsp, 20h
0x18008e6af  pop     rdi
0x18008e6b0  retn
0x18008e6b2  mov     edi, 80004005h
0x18008e6b7  cmp     eax, 2
0x18008e6ba  jz      short loc_18008E696
0x18008e6bc  xor     r8d, r8d; dwFlags
0x18008e6bf  mov     cs:?IcmState@@3W4IcmDllLoadState@@A, 2; IcmDllLoadState IcmState
0x18008e6c9  xor     edx, edx; hFile
0x18008e6cb  lea     rcx, LibFileName; "mscms.dll"
0x18008e6d2  call    cs:__imp_LoadLibraryExW
0x18008e6d9  nop     dword ptr [rax+rax+00h]
0x18008e6de  mov     cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghInstICMDll
0x18008e6e5  test    rax, rax
0x18008e6e8  jz      short loc_18008E696
0x18008e6ea  lea     rdx, aOpencolorprofi; "OpenColorProfileA"
0x18008e6f1  mov     rcx, rax; hModule
0x18008e6f4  call    cs:__imp_GetProcAddress
0x18008e6fb  nop     dword ptr [rax+rax+00h]
0x18008e700  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18008e707  lea     rdx, aOpencolorprofi_0; "OpenColorProfileW"
0x18008e70e  mov     cs:?pfnOpenColorProfile@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*pfnOpenColorProfile)(tagPROFILE *,ulong,ulong,ulong)
0x18008e715  call    cs:__imp_GetProcAddress
0x18008e71c  nop     dword ptr [rax+rax+00h]
0x18008e721  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18008e728  lea     rdx, aCreatemultipro; "CreateMultiProfileTransform"
0x18008e72f  mov     cs:?pfnOpenColorProfileW@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x18008e736  call    cs:__imp_GetProcAddress
0x18008e73d  nop     dword ptr [rax+rax+00h]
0x18008e742  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18008e749  lea     rdx, aTranslatebitma; "TranslateBitmapBits"
0x18008e750  mov     cs:?pfnCreateMultiProfileTransform@@3P6APEAXPEAPEAXKPEAKKKK@ZEA, rax; void * (*pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x18008e757  call    cs:__imp_GetProcAddress
0x18008e75e  nop     dword ptr [rax+rax+00h]
0x18008e763  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18008e76a  lea     rdx, aClosecolorprof; "CloseColorProfile"
0x18008e771  mov     cs:?pfnTranslateBitmapBits@@3P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, rax; int (*pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x18008e778  call    cs:__imp_GetProcAddress
0x18008e77f  nop     dword ptr [rax+rax+00h]
0x18008e784  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18008e78b  lea     rdx, aDeletecolortra; "DeleteColorTransform"
0x18008e792  mov     cs:?pfnCloseColorProfile@@3P6AHPEAX@ZEA, rax; int (*pfnCloseColorProfile)(void *)
0x18008e799  call    cs:__imp_GetProcAddress
0x18008e7a0  nop     dword ptr [rax+rax+00h]
0x18008e7a5  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18008e7ac  lea     rdx, aGetstandardcol; "GetStandardColorSpaceProfileW"
0x18008e7b3  mov     cs:?pfnDeleteColorTransform@@3P6AHPEAX@ZEA, rax; int (*pfnDeleteColorTransform)(void *)
0x18008e7ba  call    cs:__imp_GetProcAddress
0x18008e7c1  nop     dword ptr [rax+rax+00h]
0x18008e7c6  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18008e7cd  lea     rdx, aGetcolorprofil; "GetColorProfileFromHandle"
0x18008e7d4  mov     cs:?pfnGetStandardColorSpaceProfileW@@3P6AHPEBGKPEAGPEAK@ZEA, rax; int (*pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x18008e7db  call    cs:__imp_GetProcAddress
0x18008e7e2  nop     dword ptr [rax+rax+00h]
0x18008e7e7  cmp     cs:?pfnOpenColorProfile@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, 0; void * (*pfnOpenColorProfile)(tagPROFILE *,ulong,ulong,ulong)
0x18008e7ef  mov     cs:?pfnGetColorProfileFromHandle@@3P6AHPEAXPEAEPEAK@ZEA, rax; int (*pfnGetColorProfileFromHandle)(void *,uchar *,ulong *)
0x18008e7f6  jz      loc_18008E696
0x18008e7fc  cmp     cs:?pfnOpenColorProfileW@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, 0; void * (*pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x18008e804  jz      loc_18008E696
0x18008e80a  cmp     cs:?pfnCloseColorProfile@@3P6AHPEAX@ZEA, 0; int (*pfnCloseColorProfile)(void *)
0x18008e812  jz      loc_18008E696
0x18008e818  cmp     cs:?pfnCreateMultiProfileTransform@@3P6APEAXPEAPEAXKPEAKKKK@ZEA, 0; void * (*pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x18008e820  jz      loc_18008E696
0x18008e826  cmp     cs:?pfnDeleteColorTransform@@3P6AHPEAX@ZEA, 0; int (*pfnDeleteColorTransform)(void *)
0x18008e82e  jz      loc_18008E696
0x18008e834  cmp     cs:?pfnTranslateBitmapBits@@3P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, 0; int (*pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x18008e83c  jz      loc_18008E696
0x18008e842  cmp     cs:?pfnGetStandardColorSpaceProfileW@@3P6AHPEBGKPEAGPEAK@ZEA, 0; int (*pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x18008e84a  jz      loc_18008E696
0x18008e850  test    rax, rax
0x18008e853  jz      loc_18008E696
0x18008e859  mov     cs:?IcmState@@3W4IcmDllLoadState@@A, 1; IcmDllLoadState IcmState
0x18008e863  jmp     loc_18008E694
```
