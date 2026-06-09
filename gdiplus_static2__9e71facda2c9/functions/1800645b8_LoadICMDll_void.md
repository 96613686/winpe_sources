# LoadICMDll(void)

- ea: `0x1800645b8`
- end: `0x1800647b0`
- name: `?LoadICMDll@@YAJXZ`
- size: `504`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180062970`
- `0x1800642ac`
- `0x18011ecb0`
- `0x18015451c`

## callees

- `0x1800645b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006461a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006461a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006463c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006465d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006467e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006469f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800646c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800646e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064702`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064723`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006463c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006465d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006467e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006469f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800646c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800646e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064702`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064723`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800645c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800645c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800645e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800645e5`

## string_xrefs

- `0x180064632`: `OpenColorProfileA`
- `0x180064613`: `mscms.dll`
- `0x180064670`: `CreateMultiProfileTransform`
- `0x18006464f`: `OpenColorProfileW`
- `0x1800646d3`: `DeleteColorTransform`

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
0x1800645b8  push    rdi
0x1800645ba  sub     rsp, 20h
0x1800645be  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800645c5  call    cs:__imp_EnterCriticalSection
0x1800645cc  nop     dword ptr [rax+rax+00h]
0x1800645d1  mov     eax, cs:?IcmState@@3W4IcmDllLoadState@@A; IcmDllLoadState IcmState
0x1800645d7  cmp     eax, 1
0x1800645da  jnz     short loc_1800645FA
0x1800645dc  xor     edi, edi
0x1800645de  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800645e5  call    cs:__imp_LeaveCriticalSection
0x1800645ec  nop     dword ptr [rax+rax+00h]
0x1800645f1  mov     eax, edi
0x1800645f3  add     rsp, 20h
0x1800645f7  pop     rdi
0x1800645f8  retn
0x1800645fa  mov     edi, 80004005h
0x1800645ff  cmp     eax, 2
0x180064602  jz      short loc_1800645DE
0x180064604  xor     r8d, r8d; dwFlags
0x180064607  mov     cs:?IcmState@@3W4IcmDllLoadState@@A, 2; IcmDllLoadState IcmState
0x180064611  xor     edx, edx; hFile
0x180064613  lea     rcx, LibFileName; "mscms.dll"
0x18006461a  call    cs:__imp_LoadLibraryExW
0x180064621  nop     dword ptr [rax+rax+00h]
0x180064626  mov     cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghInstICMDll
0x18006462d  test    rax, rax
0x180064630  jz      short loc_1800645DE
0x180064632  lea     rdx, ProcName; "OpenColorProfileA"
0x180064639  mov     rcx, rax; hModule
0x18006463c  call    cs:__imp_GetProcAddress
0x180064643  nop     dword ptr [rax+rax+00h]
0x180064648  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x18006464f  lea     rdx, aOpencolorprofi_0; "OpenColorProfileW"
0x180064656  mov     cs:?pfnOpenColorProfile@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*pfnOpenColorProfile)(tagPROFILE *,ulong,ulong,ulong)
0x18006465d  call    cs:__imp_GetProcAddress
0x180064664  nop     dword ptr [rax+rax+00h]
0x180064669  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x180064670  lea     rdx, aCreatemultipro; "CreateMultiProfileTransform"
0x180064677  mov     cs:?pfnOpenColorProfileW@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, rax; void * (*pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x18006467e  call    cs:__imp_GetProcAddress
0x180064685  nop     dword ptr [rax+rax+00h]
0x18006468a  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x180064691  lea     rdx, aTranslatebitma; "TranslateBitmapBits"
0x180064698  mov     cs:?pfnCreateMultiProfileTransform@@3P6APEAXPEAPEAXKPEAKKKK@ZEA, rax; void * (*pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x18006469f  call    cs:__imp_GetProcAddress
0x1800646a6  nop     dword ptr [rax+rax+00h]
0x1800646ab  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x1800646b2  lea     rdx, aClosecolorprof; "CloseColorProfile"
0x1800646b9  mov     cs:?pfnTranslateBitmapBits@@3P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, rax; int (*pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x1800646c0  call    cs:__imp_GetProcAddress
0x1800646c7  nop     dword ptr [rax+rax+00h]
0x1800646cc  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x1800646d3  lea     rdx, aDeletecolortra; "DeleteColorTransform"
0x1800646da  mov     cs:?pfnCloseColorProfile@@3P6AHPEAX@ZEA, rax; int (*pfnCloseColorProfile)(void *)
0x1800646e1  call    cs:__imp_GetProcAddress
0x1800646e8  nop     dword ptr [rax+rax+00h]
0x1800646ed  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x1800646f4  lea     rdx, aGetstandardcol; "GetStandardColorSpaceProfileW"
0x1800646fb  mov     cs:?pfnDeleteColorTransform@@3P6AHPEAX@ZEA, rax; int (*pfnDeleteColorTransform)(void *)
0x180064702  call    cs:__imp_GetProcAddress
0x180064709  nop     dword ptr [rax+rax+00h]
0x18006470e  mov     rcx, cs:?ghInstICMDll@@3PEAUHINSTANCE__@@EA; hModule
0x180064715  lea     rdx, aGetcolorprofil; "GetColorProfileFromHandle"
0x18006471c  mov     cs:?pfnGetStandardColorSpaceProfileW@@3P6AHPEBGKPEAGPEAK@ZEA, rax; int (*pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x180064723  call    cs:__imp_GetProcAddress
0x18006472a  nop     dword ptr [rax+rax+00h]
0x18006472f  cmp     cs:?pfnOpenColorProfile@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, 0; void * (*pfnOpenColorProfile)(tagPROFILE *,ulong,ulong,ulong)
0x180064737  mov     cs:?pfnGetColorProfileFromHandle@@3P6AHPEAXPEAEPEAK@ZEA, rax; int (*pfnGetColorProfileFromHandle)(void *,uchar *,ulong *)
0x18006473e  jz      loc_1800645DE
0x180064744  cmp     cs:?pfnOpenColorProfileW@@3P6APEAXPEAUtagPROFILE@@KKK@ZEA, 0; void * (*pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x18006474c  jz      loc_1800645DE
0x180064752  cmp     cs:?pfnCloseColorProfile@@3P6AHPEAX@ZEA, 0; int (*pfnCloseColorProfile)(void *)
0x18006475a  jz      loc_1800645DE
0x180064760  cmp     cs:?pfnCreateMultiProfileTransform@@3P6APEAXPEAPEAXKPEAKKKK@ZEA, 0; void * (*pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x180064768  jz      loc_1800645DE
0x18006476e  cmp     cs:?pfnDeleteColorTransform@@3P6AHPEAX@ZEA, 0; int (*pfnDeleteColorTransform)(void *)
0x180064776  jz      loc_1800645DE
0x18006477c  cmp     cs:?pfnTranslateBitmapBits@@3P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA, 0; int (*pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x180064784  jz      loc_1800645DE
0x18006478a  cmp     cs:?pfnGetStandardColorSpaceProfileW@@3P6AHPEBGKPEAGPEAK@ZEA, 0; int (*pfnGetStandardColorSpaceProfileW)(ushort const *,ulong,ushort *,ulong *)
0x180064792  jz      loc_1800645DE
0x180064798  test    rax, rax
0x18006479b  jz      loc_1800645DE
0x1800647a1  mov     cs:?IcmState@@3W4IcmDllLoadState@@A, 1; IcmDllLoadState IcmState
0x1800647ab  jmp     loc_1800645DC
```
