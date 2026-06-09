# Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(HINSTANCE__ *,ushort const *,ushort *,ulong,int *)

- ea: `0x1800125a4`
- end: `0x180012774`
- name: `?GetAuxiliaryProviderPathFromEmbeddedImageResource@Win32LiveSystemProvider@@AEAAJPEAUHINSTANCE__@@PEBGPEAGKPEAH@Z`
- size: `464`
- prototype: `int(Win32LiveSystemProvider *__hidden this, HINSTANCE, const unsigned __int16 *, unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180012404`

## callees

- `0x180001710`
- `0x1800125a4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x18001263e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x18001263e`
- `api-ms-win-core-libraryloader-l1-1-0!SizeofResource` at `0x180012628`
- `api-ms-win-core-libraryloader-l1-1-0!SizeofResource` at `0x180012628`
- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x180012650`
- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x180012650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001272a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001272a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001271a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001273e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001271a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001273e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800126a7`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800126a7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001270d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001270d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800126dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800126dc`

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
0x1800125a4  mov     [rsp+arg_10], rbx
0x1800125a9  push    rbp
0x1800125aa  push    rsi
0x1800125ab  push    rdi
0x1800125ac  push    r14
0x1800125ae  push    r15
0x1800125b0  sub     rsp, 270h
0x1800125b7  mov     rax, cs:__security_cookie
0x1800125be  xor     rax, rsp
0x1800125c1  mov     [rsp+298h+var_38], rax
0x1800125c9  mov     rax, [rcx+188h]
0x1800125d0  mov     r14, r9
0x1800125d3  mov     r15, [rsp+298h+arg_28]
0x1800125db  mov     rdi, rdx
0x1800125de  mov     rbx, rcx
0x1800125e1  test    rax, rax
0x1800125e4  jnz     short loc_1800125F0
0x1800125e6  mov     eax, 80004001h
0x1800125eb  jmp     loc_18001274D
0x1800125f0  cmp     [rsp+298h+arg_20], 104h
0x1800125fb  jb      loc_180012748
0x180012601  mov     r8d, 0Ah
0x180012607  lea     rdx, aMinidumpEmbedd; "MINIDUMP_EMBEDDED_AUXILIARY_PROVIDER"
0x18001260e  mov     rcx, rdi
0x180012611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012616  mov     rsi, rax
0x180012619  test    rax, rax
0x18001261c  jz      loc_180012720
0x180012622  mov     rdx, rax; hResInfo
0x180012625  mov     rcx, rdi; hModule
0x180012628  call    cs:__imp_SizeofResource
0x18001262e  mov     ebp, eax
0x180012630  test    eax, eax
0x180012632  jz      loc_180012720
0x180012638  mov     rdx, rsi; hResInfo
0x18001263b  mov     rcx, rdi; hModule
0x18001263e  call    cs:__imp_LoadResource
0x180012644  test    rax, rax
0x180012647  jz      loc_180012720
0x18001264d  mov     rcx, rax; hResData
0x180012650  call    cs:__imp_LockResource
0x180012656  mov     rdi, rax
0x180012659  test    rax, rax
0x18001265c  jz      loc_180012720
0x180012662  mov     rax, [rbx+1B0h]
0x180012669  test    rax, rax
0x18001266c  jnz     short loc_18001267E
0x18001266e  mov     rax, [rbx+1A8h]
0x180012675  test    rax, rax
0x180012678  jz      loc_180012720
0x18001267e  lea     rdx, [rsp+298h+PathName]
0x180012683  mov     ecx, 105h
0x180012688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001268d  test    eax, eax
0x18001268f  jz      loc_180012720
0x180012695  mov     r9, r14; lpTempFileName
0x180012698  lea     rdx, PrefixString; "MDP"
0x18001269f  xor     r8d, r8d; uUnique
0x1800126a2  lea     rcx, [rsp+298h+PathName]; lpPathName
0x1800126a7  call    cs:__imp_GetTempFileNameW
0x1800126ad  test    eax, eax
0x1800126af  jz      short loc_180012720
0x1800126b1  xor     r9d, r9d; lpSecurityAttributes
0x1800126b4  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x1800126bd  mov     [rsp+298h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x1800126c5  mov     edx, 0C0000000h; dwDesiredAccess
0x1800126ca  mov     rcx, r14; lpFileName
0x1800126cd  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x1800126d5  lea     esi, [r9+1]
0x1800126d9  mov     r8d, esi; dwShareMode
0x1800126dc  call    cs:__imp_CreateFileW
0x1800126e2  mov     rbx, rax
0x1800126e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800126e9  jz      short loc_180012720
0x1800126eb  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800126f0  mov     [r15], esi
0x1800126f3  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800126f6  mov     [rsp+298h+NumberOfBytesWritten], 0
0x1800126fe  mov     rdx, rdi; lpBuffer
0x180012701  mov     qword ptr [rsp+298h+dwCreationDisposition], 0; lpOverlapped
0x18001270a  mov     rcx, rax; hFile
0x18001270d  call    cs:__imp_WriteFile
0x180012713  mov     rcx, rbx; hObject
0x180012716  test    eax, eax
0x180012718  jnz     short loc_18001273E
0x18001271a  call    cs:__imp_CloseHandle
0x180012720  call    cs:__imp_GetLastError
0x180012726  test    eax, eax
0x180012728  jz      short loc_180012748
0x18001272a  call    cs:__imp_GetLastError
0x180012730  test    eax, eax
0x180012732  jle     short loc_18001274D
0x180012734  movzx   eax, ax
0x180012737  or      eax, 80070000h
0x18001273c  jmp     short loc_18001274D
0x18001273e  call    cs:__imp_CloseHandle
0x180012744  xor     eax, eax
0x180012746  jmp     short loc_18001274D
0x180012748  mov     eax, 80004005h
0x18001274d  mov     rcx, [rsp+298h+var_38]
0x180012755  xor     rcx, rsp; StackCookie
0x180012758  call    __security_check_cookie
0x18001275d  mov     rbx, [rsp+298h+arg_10]
0x180012765  add     rsp, 270h
0x18001276c  pop     r15
0x18001276e  pop     r14
0x180012770  pop     rdi
0x180012771  pop     rsi
0x180012772  pop     rbp
0x180012773  retn
```
