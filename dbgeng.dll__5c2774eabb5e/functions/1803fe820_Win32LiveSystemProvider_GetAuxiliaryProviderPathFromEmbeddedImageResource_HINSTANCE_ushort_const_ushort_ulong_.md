# Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(HINSTANCE__ *,ushort const *,ushort *,ulong,int *)

- ea: `0x1803fe820`
- end: `0x1803fea31`
- name: `?GetAuxiliaryProviderPathFromEmbeddedImageResource@Win32LiveSystemProvider@@AEAAJPEAUHINSTANCE__@@PEBGPEAGKPEAH@Z`
- size: `529`
- prototype: `int(Win32LiveSystemProvider *__hidden this, HINSTANCE, const unsigned __int16 *, unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1803fd800`

## callees

- `0x1800f0f40`
- `0x1803fe820`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x1803fe8d8`
- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x1803fe8d8`
- `api-ms-win-core-libraryloader-l1-1-0!SizeofResource` at `0x1803fe8a4`
- `api-ms-win-core-libraryloader-l1-1-0!SizeofResource` at `0x1803fe8a4`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x1803fe8c0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x1803fe8c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fe9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fe9da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fe9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fe9da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803fe9be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803fe9f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803fe9be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803fe9f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1803fe9ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1803fe9ab`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1803fe935`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1803fe935`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1803fe974`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1803fe974`

## pseudocode

```c
int __fastcall Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(
        Win32LiveSystemProvider *this,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int *a6)
{
  __int64 (__fastcall *v6)(HINSTANCE, const char *, __int64); // rax
  int result; // eax
  HRSRC v11; // rax
  HRSRC v12; // rsi
  DWORD v13; // ebp
  HGLOBAL Resource; // rax
  const void *v15; // rdi
  unsigned int (__fastcall *v16)(__int64, WCHAR *); // rax
  HANDLE FileW; // rax
  void *v18; // rbx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-258h] BYREF
  WCHAR PathName[264]; // [rsp+50h] [rbp-248h] BYREF

  v6 = (__int64 (__fastcall *)(HINSTANCE, const char *, __int64))*((_QWORD *)this + 49);
  if ( !v6 )
    return -2147467263;
  if ( a5 < 0x104 )
    return -2147467259;
  v11 = (HRSRC)v6(a2, "MINIDUMP_EMBEDDED_AUXILIARY_PROVIDER", 10);
  v12 = v11;
  if ( v11 )
  {
    v13 = SizeofResource(a2, v11);
    if ( v13 )
    {
      Resource = LoadResource(a2, v12);
      if ( Resource )
      {
        v15 = LockResource(Resource);
        if ( v15 )
        {
          v16 = (unsigned int (__fastcall *)(__int64, WCHAR *))*((_QWORD *)this + 54);
          if ( v16 || (v16 = (unsigned int (__fastcall *)(__int64, WCHAR *))*((_QWORD *)this + 53)) != 0 )
          {
            if ( v16(261, PathName) )
            {
              if ( GetTempFileNameW(PathName, L"MDP", 0, a4) )
              {
                FileW = CreateFileW(a4, 0xC0000000, 1u, 0, 2u, 0x100u, 0);
                v18 = FileW;
                if ( FileW != (HANDLE)-1LL )
                {
                  *a6 = 1;
                  NumberOfBytesWritten = 0;
                  if ( WriteFile(FileW, v15, v13, &NumberOfBytesWritten, 0) )
                  {
                    CloseHandle(v18);
                    return 0;
                  }
                  CloseHandle(v18);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1803fe820  mov     [rsp+arg_10], rbx
0x1803fe825  push    rbp
0x1803fe826  push    rsi
0x1803fe827  push    rdi
0x1803fe828  push    r14
0x1803fe82a  push    r15
0x1803fe82c  sub     rsp, 270h
0x1803fe833  mov     rax, cs:__security_cookie
0x1803fe83a  xor     rax, rsp
0x1803fe83d  mov     [rsp+298h+var_38], rax
0x1803fe845  mov     rax, [rcx+188h]
0x1803fe84c  mov     r14, r9
0x1803fe84f  mov     r15, [rsp+298h+arg_28]
0x1803fe857  mov     rdi, rdx
0x1803fe85a  mov     rbx, rcx
0x1803fe85d  test    rax, rax
0x1803fe860  jnz     short loc_1803FE86C
0x1803fe862  mov     eax, 80004001h
0x1803fe867  jmp     loc_1803FEA09
0x1803fe86c  cmp     [rsp+298h+arg_20], 104h
0x1803fe877  jb      loc_1803FEA04
0x1803fe87d  mov     r8d, 0Ah
0x1803fe883  lea     rdx, aMinidumpEmbedd; "MINIDUMP_EMBEDDED_AUXILIARY_PROVIDER"
0x1803fe88a  mov     rcx, rdi
0x1803fe88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fe892  mov     rsi, rax
0x1803fe895  test    rax, rax
0x1803fe898  jz      loc_1803FE9CA
0x1803fe89e  mov     rdx, rax; hResInfo
0x1803fe8a1  mov     rcx, rdi; hModule
0x1803fe8a4  call    cs:__imp_SizeofResource
0x1803fe8ab  nop     dword ptr [rax+rax+00h]
0x1803fe8b0  mov     ebp, eax
0x1803fe8b2  test    eax, eax
0x1803fe8b4  jz      loc_1803FE9CA
0x1803fe8ba  mov     rdx, rsi; hResInfo
0x1803fe8bd  mov     rcx, rdi; hModule
0x1803fe8c0  call    cs:__imp_LoadResource
0x1803fe8c7  nop     dword ptr [rax+rax+00h]
0x1803fe8cc  test    rax, rax
0x1803fe8cf  jz      loc_1803FE9CA
0x1803fe8d5  mov     rcx, rax; hResData
0x1803fe8d8  call    cs:__imp_LockResource
0x1803fe8df  nop     dword ptr [rax+rax+00h]
0x1803fe8e4  mov     rdi, rax
0x1803fe8e7  test    rax, rax
0x1803fe8ea  jz      loc_1803FE9CA
0x1803fe8f0  mov     rax, [rbx+1B0h]
0x1803fe8f7  test    rax, rax
0x1803fe8fa  jnz     short loc_1803FE90C
0x1803fe8fc  mov     rax, [rbx+1A8h]
0x1803fe903  test    rax, rax
0x1803fe906  jz      loc_1803FE9CA
0x1803fe90c  lea     rdx, [rsp+298h+PathName]
0x1803fe911  mov     ecx, 105h
0x1803fe916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fe91b  test    eax, eax
0x1803fe91d  jz      loc_1803FE9CA
0x1803fe923  mov     r9, r14; lpTempFileName
0x1803fe926  lea     rdx, aMdp; "MDP"
0x1803fe92d  xor     r8d, r8d; uUnique
0x1803fe930  lea     rcx, [rsp+298h+PathName]; lpPathName
0x1803fe935  call    cs:__imp_GetTempFileNameW
0x1803fe93c  nop     dword ptr [rax+rax+00h]
0x1803fe941  test    eax, eax
0x1803fe943  jz      loc_1803FE9CA
0x1803fe949  xor     r9d, r9d; lpSecurityAttributes
0x1803fe94c  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x1803fe955  mov     [rsp+298h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x1803fe95d  mov     edx, 0C0000000h; dwDesiredAccess
0x1803fe962  mov     rcx, r14; lpFileName
0x1803fe965  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x1803fe96d  lea     esi, [r9+1]
0x1803fe971  mov     r8d, esi; dwShareMode
0x1803fe974  call    cs:__imp_CreateFileW
0x1803fe97b  nop     dword ptr [rax+rax+00h]
0x1803fe980  mov     rbx, rax
0x1803fe983  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1803fe987  jz      short loc_1803FE9CA
0x1803fe989  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1803fe98e  mov     [r15], esi
0x1803fe991  mov     r8d, ebp; nNumberOfBytesToWrite
0x1803fe994  mov     [rsp+298h+NumberOfBytesWritten], 0
0x1803fe99c  mov     rdx, rdi; lpBuffer
0x1803fe99f  mov     qword ptr [rsp+298h+dwCreationDisposition], 0; lpOverlapped
0x1803fe9a8  mov     rcx, rax; hFile
0x1803fe9ab  call    cs:__imp_WriteFile
0x1803fe9b2  nop     dword ptr [rax+rax+00h]
0x1803fe9b7  mov     rcx, rbx; hObject
0x1803fe9ba  test    eax, eax
0x1803fe9bc  jnz     short loc_1803FE9F4
0x1803fe9be  call    cs:__imp_CloseHandle
0x1803fe9c5  nop     dword ptr [rax+rax+00h]
0x1803fe9ca  call    cs:__imp_GetLastError
0x1803fe9d1  nop     dword ptr [rax+rax+00h]
0x1803fe9d6  test    eax, eax
0x1803fe9d8  jz      short loc_1803FEA04
0x1803fe9da  call    cs:__imp_GetLastError
0x1803fe9e1  nop     dword ptr [rax+rax+00h]
0x1803fe9e6  test    eax, eax
0x1803fe9e8  jle     short loc_1803FEA09
0x1803fe9ea  movzx   eax, ax
0x1803fe9ed  or      eax, 80070000h
0x1803fe9f2  jmp     short loc_1803FEA09
0x1803fe9f4  call    cs:__imp_CloseHandle
0x1803fe9fb  nop     dword ptr [rax+rax+00h]
0x1803fea00  xor     eax, eax
0x1803fea02  jmp     short loc_1803FEA09
0x1803fea04  mov     eax, 80004005h
0x1803fea09  mov     rcx, [rsp+298h+var_38]
0x1803fea11  xor     rcx, rsp; StackCookie
0x1803fea14  call    __security_check_cookie
0x1803fea19  mov     rbx, [rsp+298h+arg_10]
0x1803fea21  add     rsp, 270h
0x1803fea28  pop     r15
0x1803fea2a  pop     r14
0x1803fea2c  pop     rdi
0x1803fea2d  pop     rsi
0x1803fea2e  pop     rbp
0x1803fea2f  retn
```
