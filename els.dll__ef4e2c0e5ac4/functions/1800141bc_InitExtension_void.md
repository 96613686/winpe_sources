# InitExtension(void)

- ea: `0x1800141bc`
- end: `0x180014354`
- name: `?InitExtension@@YAXXZ`
- size: `408`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18001435c`

## callees

- `0x180007060`
- `0x1800141bc`
- `0x180014a6c`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180014279`
- `KERNEL32!CreateFileW` at `0x180014279`
- `KERNEL32!GetSystemDirectoryW` at `0x180014222`
- `KERNEL32!GetSystemDirectoryW` at `0x180014222`
- `KERNEL32!CloseHandle` at `0x18001432e`
- `KERNEL32!CloseHandle` at `0x18001432e`
- `KERNEL32!GetProcAddress` at `0x180014303`
- `KERNEL32!GetProcAddress` at `0x18001431e`
- `KERNEL32!GetProcAddress` at `0x180014303`
- `KERNEL32!GetProcAddress` at `0x18001431e`
- `WINTRUST!WTGetSignatureInfo` at `0x1800142c8`
- `WINTRUST!WTGetSignatureInfo` at `0x1800142c8`

## string_xrefs

- `0x180014228`: `elsext.dll`

## pseudocode

```c
void InitExtension(void)
{
  HANDLE FileW; // rbx
  HMODULE LibraryW; // rax
  int v2; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v3[23]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  memset_0(FileName, 0, 0x20Au);
  memset_0(&v2, 0, 0x58u);
  GetSystemDirectoryW(Buffer, 0x104u);
  StringCchPrintfW(FileName, 0x105u, L"%s\\%s", Buffer, L"elsext.dll");
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    memset_0(v3, 0, 0x54u);
    v2 = 88;
    if ( (int)WTGetSignatureInfo(FileName, FileW, 6147, &v2, 0, 0) >= 0 && (unsigned int)(v3[0] - 5) <= 1 && v3[20] )
    {
      LibraryW = IsolationAwareLoadLibraryW(FileName);
      g_hinstExtension = LibraryW;
      if ( LibraryW )
      {
        GetDescriptionStrPtr = (int (*)(struct _EVENTLOGRECORD *, unsigned int, unsigned __int16 **))GetProcAddress(LibraryW, "GetDescriptionStr");
        GetCategoryStrPtr = (int (*)(struct _EVENTLOGRECORD *, unsigned __int16 *, unsigned int))GetProcAddress(
                                                                                                   g_hinstExtension,
                                                                                                   "GetCategoryStr");
      }
    }
    CloseHandle(FileW);
  }
}

```

## disassembly

```asm
0x1800141bc  mov     [rsp-8+arg_0], rbx
0x1800141c1  push    rbp
0x1800141c2  lea     rbp, [rsp-3D0h]
0x1800141ca  sub     rsp, 4D0h
0x1800141d1  mov     rax, cs:__security_cookie
0x1800141d8  xor     rax, rsp
0x1800141db  mov     [rbp+3D0h+var_10], rax
0x1800141e2  mov     ebx, 20Ah
0x1800141e7  lea     rcx, [rbp+3D0h+Buffer]; void *
0x1800141ee  mov     r8d, ebx; Size
0x1800141f1  xor     edx, edx; Val
0x1800141f3  call    memset_0
0x1800141f8  mov     r8d, ebx; Size
0x1800141fb  lea     rcx, [rbp+3D0h+FileName]; void *
0x1800141ff  xor     edx, edx; Val
0x180014201  call    memset_0
0x180014206  xor     edx, edx; Val
0x180014208  lea     rcx, [rsp+4D0h+var_490]; void *
0x18001420d  lea     r8d, [rdx+58h]; Size
0x180014211  call    memset_0
0x180014216  mov     edx, 104h; uSize
0x18001421b  lea     rcx, [rbp+3D0h+Buffer]; lpBuffer
0x180014222  call    cs:__imp_GetSystemDirectoryW
0x180014228  lea     rax, aElsextDll; "elsext.dll"
0x18001422f  mov     edx, 105h; unsigned __int64
0x180014234  lea     r9, [rbp+3D0h+Buffer]
0x18001423b  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rax
0x180014240  lea     r8, aSS; "%s\\%s"
0x180014247  lea     rcx, [rbp+3D0h+FileName]; unsigned __int16 *
0x18001424b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014250  xor     r9d, r9d; lpSecurityAttributes
0x180014253  mov     [rsp+4D0h+hTemplateFile], 0; hTemplateFile
0x18001425c  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180014264  lea     rcx, [rbp+3D0h+FileName]; lpFileName
0x180014268  mov     edx, 80000000h; dwDesiredAccess
0x18001426d  mov     [rsp+4D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180014275  lea     r8d, [r9+1]; dwShareMode
0x180014279  call    cs:__imp_CreateFileW
0x18001427f  mov     rbx, rax
0x180014282  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014286  jz      loc_180014334
0x18001428c  xor     edx, edx; Val
0x18001428e  lea     rcx, [rsp+4D0h+var_48C]; void *
0x180014293  lea     r8d, [rdx+54h]; Size
0x180014297  call    memset_0
0x18001429c  lea     r9, [rsp+4D0h+var_490]
0x1800142a1  mov     qword ptr [rsp+4D0h+dwFlagsAndAttributes], 0
0x1800142aa  mov     r8d, 1803h
0x1800142b0  mov     [rsp+4D0h+var_490], 58h ; 'X'
0x1800142b8  mov     rdx, rbx
0x1800142bb  mov     qword ptr [rsp+4D0h+dwCreationDisposition], 0
0x1800142c4  lea     rcx, [rbp+3D0h+FileName]
0x1800142c8  call    cs:__imp_WTGetSignatureInfo
0x1800142ce  test    eax, eax
0x1800142d0  js      short loc_18001432B
0x1800142d2  mov     eax, [rsp+4D0h+var_48C]
0x1800142d6  add     eax, 0FFFFFFFBh
0x1800142d9  cmp     eax, 1
0x1800142dc  ja      short loc_18001432B
0x1800142de  cmp     [rbp+3D0h+var_43C], 0
0x1800142e2  jz      short loc_18001432B
0x1800142e4  lea     rcx, [rbp+3D0h+FileName]; lpLibFileName
0x1800142e8  call    IsolationAwareLoadLibraryW
0x1800142ed  mov     cs:?g_hinstExtension@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstExtension
0x1800142f4  test    rax, rax
0x1800142f7  jz      short loc_18001432B
0x1800142f9  lea     rdx, ProcName; "GetDescriptionStr"
0x180014300  mov     rcx, rax; hModule
0x180014303  call    cs:__imp_GetProcAddress
0x180014309  mov     rcx, cs:?g_hinstExtension@@3PEAUHINSTANCE__@@EA; hModule
0x180014310  lea     rdx, aGetcategorystr; "GetCategoryStr"
0x180014317  mov     cs:?GetDescriptionStrPtr@@3P6AHPEAU_EVENTLOGRECORD@@KPEAPEAG@ZEA, rax; int (*GetDescriptionStrPtr)(_EVENTLOGRECORD *,ulong,ushort * *)
0x18001431e  call    cs:__imp_GetProcAddress
0x180014324  mov     cs:?GetCategoryStrPtr@@3P6AHPEAU_EVENTLOGRECORD@@PEAGK@ZEA, rax; int (*GetCategoryStrPtr)(_EVENTLOGRECORD *,ushort *,ulong)
0x18001432b  mov     rcx, rbx; hObject
0x18001432e  call    cs:__imp_CloseHandle
0x180014334  mov     rcx, [rbp+3D0h+var_10]
0x18001433b  xor     rcx, rsp; StackCookie
0x18001433e  call    __security_check_cookie
0x180014343  mov     rbx, [rsp+4D0h+arg_0]
0x18001434b  add     rsp, 4D0h
0x180014352  pop     rbp
0x180014353  retn
```
