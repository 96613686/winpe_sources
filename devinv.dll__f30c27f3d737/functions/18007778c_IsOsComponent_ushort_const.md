# _IsOsComponent(ushort const *)

- ea: `0x18007778c`
- end: `0x180077b49`
- name: `?_IsOsComponent@@YAHPEBG@Z`
- size: `957`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180074370`
- `0x1800763b0`

## callees

- `0x180005e40`
- `0x1800061f0`
- `0x18000642c`
- `0x180006494`
- `0x18007400c`
- `0x18007778c`
- `0x180116010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007790b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077972`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007790b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077972`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800777fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800779ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800777fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800779ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007784b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077931`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077a08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007784b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077931`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077a08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077981`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077981`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800778a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800778a6`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x1800778e7`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x1800778e7`

## string_xrefs

- `0x1800777f6`: `ntdll.dll`
- `0x1800779b3`: `sfc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _IsOsComponent(LPCWSTR lpFileName)
{
  __int64 FileW; // rdi
  __int64 v3; // rbx
  HMODULE Library; // rbx
  HMODULE v5; // rcx
  unsigned __int8 (*ProcAddress)(void); // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  HMODULE v9; // rcx
  signed int v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int LastError; // eax
  int v15; // edx
  unsigned int v16; // r8d
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  DWORD FileSystemFlags; // [rsp+40h] [rbp-258h] BYREF
  DWORD MaximumComponentLength[3]; // [rsp+44h] [rbp-254h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+50h] [rbp-248h] BYREF

  FileW = 4;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180157DA4 > *(_DWORD *)(v3 + 4) )
    goto LABEL_46;
  while ( 1 )
  {
    if ( dword_180157DA8 > *(_DWORD *)(v3 + FileW) )
    {
      Init_thread_header(&dword_180157DA8);
      if ( dword_180157DA8 == -1 )
      {
        atexit(_IsOsComponent_::_2_::_dynamic_atexit_destructor_for__NtdllModule__);
        Init_thread_footer(&dword_180157DA8);
      }
    }
    if ( hModule )
      goto LABEL_10;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v5 = hModule;
    if ( Library != hModule )
    {
      if ( hModule && !((unsigned __int8 (__fastcall *)(void ***))*off_180155A70)(&off_180155A70) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v15, v16);
LABEL_53:
        v17 = GetLastError();
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
        JUMPOUT(0x180077B48LL);
      }
      v5 = Library;
      hModule = Library;
    }
    if ( !v5 )
    {
LABEL_10:
      ProcAddress = (unsigned __int8 (*)(void))qword_180157AD8;
    }
    else
    {
      ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(v5, "RtlIsStateSeparationEnabled");
      qword_180157AD8 = (__int64)ProcAddress;
    }
    v3 = 0;
    if ( ProcAddress )
    {
      if ( ProcAddress() )
      {
        MaximumComponentLength[0] = 0;
        FileSystemFlags = 0;
        FileW = (__int64)CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x80u, 0);
        if ( FileW != -1 )
        {
          if ( GetVolumeInformationByHandleW(
                 (HANDLE)FileW,
                 VolumeNameBuffer,
                 0x105u,
                 0,
                 MaximumComponentLength,
                 &FileSystemFlags,
                 0,
                 0) )
          {
            if ( (FileSystemFlags & 0x80000) == 0 || (unsigned int)_o__wcsicmp(VolumeNameBuffer, L"MAINOS") )
            {
              if ( !qword_180157AE0 )
              {
                v7 = GetProcAddress(hModule, "RtlGetDeviceFamilyInfoEnum");
                qword_180157AE0 = (__int64)v7;
                if ( v7 )
                  ((void (__fastcall *)(_QWORD, int *, _QWORD))v7)(0, &dword_180157ACC, 0);
                else
                  qword_180157AE0 = 1;
              }
              if ( dword_180157ACC == 5 && !(unsigned int)_o__wcsicmp(VolumeNameBuffer, L"System Boot") )
                v3 = 1;
            }
            else
            {
              v3 = 1;
            }
          }
          CloseHandle((HANDLE)FileW);
          if ( (_DWORD)v3 )
            return (unsigned int)v3;
        }
      }
    }
    v8 = (FARPROC)qword_180157AD0;
    if ( qword_180157AD0 )
      goto LABEL_36;
    if ( byte_180157AC8 )
    {
      v9 = (HMODULE)qword_180155A68;
    }
    else
    {
      FileW = (__int64)LoadLibraryExW(L"sfc.dll", 0, 0x800u);
      v9 = (HMODULE)qword_180155A68;
      if ( FileW != qword_180155A68 )
      {
        if ( qword_180155A68 && !((unsigned __int8 (__fastcall *)(void ***))*off_180155A60)(&off_180155A60) )
          goto LABEL_53;
        v9 = (HMODULE)FileW;
        qword_180155A68 = FileW;
      }
      if ( v9 )
      {
        v8 = GetProcAddress(v9, "SfcIsFileProtected");
        qword_180157AD0 = (__int64)v8;
        v9 = (HMODULE)qword_180155A68;
      }
      else
      {
        v8 = (FARPROC)qword_180157AD0;
      }
      if ( v8 )
      {
LABEL_36:
        LODWORD(v3) = ((__int64 (__fastcall *)(_QWORD, LPCWSTR))v8)(0, lpFileName);
        return (unsigned int)v3;
      }
    }
    byte_180157AC8 = 1;
    if ( !v9 )
      return (unsigned int)v3;
    if ( ((unsigned __int8 (__fastcall *)(void ***))*off_180155A60)(&off_180155A60) )
    {
      qword_180155A68 = 0;
      return (unsigned int)v3;
    }
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
LABEL_46:
    Init_thread_header(&dword_180157DA4);
    if ( dword_180157DA4 == -1 )
    {
      atexit(_IsOsComponent_::_2_::_dynamic_atexit_destructor_for__SfcModule__);
      Init_thread_footer(&dword_180157DA4);
    }
  }
}

```

## disassembly

```asm
0x18007778c  push    rbx
0x18007778e  push    rsi
0x18007778f  push    rdi
0x180077790  push    r14
0x180077792  sub     rsp, 278h
0x180077799  mov     rax, cs:__security_cookie
0x1800777a0  xor     rax, rsp
0x1800777a3  mov     [rsp+298h+var_38], rax
0x1800777ab  mov     rsi, rcx
0x1800777ae  mov     ecx, cs:_tls_index
0x1800777b4  mov     rax, gs:58h
0x1800777bd  mov     edi, 4
0x1800777c2  mov     rbx, [rax+rcx*8]
0x1800777c6  mov     eax, [rbx+rdi]
0x1800777c9  cmp     cs:dword_180157DA4, eax
0x1800777cf  jg      loc_180077AA9
0x1800777d5  mov     eax, [rbx+rdi]
0x1800777d8  cmp     cs:dword_180157DA8, eax
0x1800777de  jg      loc_180077ADF
0x1800777e4  cmp     cs:hModule, 0
0x1800777ec  jnz     short loc_18007785A
0x1800777ee  xor     edx, edx; hFile
0x1800777f0  mov     r8d, 800h; dwFlags
0x1800777f6  lea     rcx, LibFileName; "ntdll.dll"
0x1800777fd  call    cs:__imp_LoadLibraryExW
0x180077803  mov     rbx, rax
0x180077806  mov     rcx, cs:hModule
0x18007780d  cmp     rax, rcx
0x180077810  jz      short loc_18007783F
0x180077812  test    rcx, rcx
0x180077815  jz      short loc_180077835
0x180077817  mov     rcx, cs:off_180155A70
0x18007781e  mov     rax, [rcx]
0x180077821  lea     rcx, off_180155A70
0x180077828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007782d  test    al, al
0x18007782f  jz      loc_180077B15
0x180077835  mov     rcx, rbx; hModule
0x180077838  mov     cs:hModule, rbx
0x18007783f  test    rcx, rcx
0x180077842  jz      short loc_18007785A
0x180077844  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18007784b  call    cs:__imp_GetProcAddress
0x180077851  mov     cs:qword_180157AD8, rax
0x180077858  jmp     short loc_180077861
0x18007785a  mov     rax, cs:qword_180157AD8
0x180077861  xor     ebx, ebx
0x180077863  lea     r14d, [rbx+1]
0x180077867  test    rax, rax
0x18007786a  jz      loc_18007798F
0x180077870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077875  test    al, al
0x180077877  jz      loc_18007798F
0x18007787d  mov     [rsp+298h+MaximumComponentLength], ebx
0x180077881  mov     [rsp+298h+FileSystemFlags], ebx
0x180077885  mov     [rsp+298h+hTemplateFile], rbx; hTemplateFile
0x18007788a  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180077892  mov     [rsp+298h+dwCreationDisposition], 3; dwCreationDisposition
0x18007789a  xor     r9d, r9d; lpSecurityAttributes
0x18007789d  xor     edx, edx; dwDesiredAccess
0x18007789f  lea     r8d, [rbx+7]; dwShareMode
0x1800778a3  mov     rcx, rsi; lpFileName
0x1800778a6  call    cs:__imp_CreateFileW
0x1800778ac  mov     rdi, rax
0x1800778af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800778b3  jz      loc_18007798F
0x1800778b9  mov     [rsp+298h+nFileSystemNameSize], ebx; nFileSystemNameSize
0x1800778bd  mov     [rsp+298h+hTemplateFile], rbx; lpFileSystemNameBuffer
0x1800778c2  lea     rax, [rsp+298h+FileSystemFlags]
0x1800778c7  mov     qword ptr [rsp+298h+dwFlagsAndAttributes], rax; lpFileSystemFlags
0x1800778cc  lea     rax, [rsp+298h+MaximumComponentLength]
0x1800778d1  mov     qword ptr [rsp+298h+dwCreationDisposition], rax; lpMaximumComponentLength
0x1800778d6  xor     r9d, r9d; lpVolumeSerialNumber
0x1800778d9  mov     r8d, 105h; nVolumeNameSize
0x1800778df  lea     rdx, [rsp+298h+VolumeNameBuffer]; lpVolumeNameBuffer
0x1800778e4  mov     rcx, rdi; hFile
0x1800778e7  call    cs:__imp_GetVolumeInformationByHandleW
0x1800778ed  test    eax, eax
0x1800778ef  jz      loc_18007797E
0x1800778f5  test    [rsp+298h+FileSystemFlags], 80000h
0x1800778fd  jz      short loc_18007791A
0x1800778ff  lea     rdx, aMainos; "MAINOS"
0x180077906  lea     rcx, [rsp+298h+VolumeNameBuffer]
0x18007790b  call    cs:__imp__o__wcsicmp
0x180077911  test    eax, eax
0x180077913  jnz     short loc_18007791A
0x180077915  mov     ebx, r14d
0x180077918  jmp     short loc_18007797E
0x18007791a  cmp     cs:qword_180157AE0, rbx
0x180077921  jnz     short loc_18007795D
0x180077923  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18007792a  mov     rcx, cs:hModule; hModule
0x180077931  call    cs:__imp_GetProcAddress
0x180077937  mov     cs:qword_180157AE0, rax
0x18007793e  test    rax, rax
0x180077941  jz      short loc_180077956
0x180077943  xor     r8d, r8d
0x180077946  lea     rdx, dword_180157ACC
0x18007794d  xor     ecx, ecx
0x18007794f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077954  jmp     short loc_18007795D
0x180077956  mov     cs:qword_180157AE0, r14
0x18007795d  cmp     cs:dword_180157ACC, 5
0x180077964  jnz     short loc_18007797E
0x180077966  lea     rdx, aSystemBoot; "System Boot"
0x18007796d  lea     rcx, [rsp+298h+VolumeNameBuffer]
0x180077972  call    cs:__imp__o__wcsicmp
0x180077978  test    eax, eax
0x18007797a  cmovz   ebx, r14d
0x18007797e  mov     rcx, rdi; hObject
0x180077981  call    cs:__imp_CloseHandle
0x180077987  test    ebx, ebx
0x180077989  jnz     loc_180077A36
0x18007798f  mov     rax, cs:qword_180157AD0
0x180077996  test    rax, rax
0x180077999  jnz     loc_180077A2A
0x18007799f  cmp     cs:byte_180157AC8, al
0x1800779a5  jnz     loc_180077A55
0x1800779ab  xor     edx, edx; hFile
0x1800779ad  mov     r8d, 800h; dwFlags
0x1800779b3  lea     rcx, aSfcDll; "sfc.dll"
0x1800779ba  call    cs:__imp_LoadLibraryExW
0x1800779c0  mov     rdi, rax
0x1800779c3  mov     rcx, cs:qword_180155A68
0x1800779ca  cmp     rax, rcx
0x1800779cd  jz      short loc_1800779FC
0x1800779cf  test    rcx, rcx
0x1800779d2  jz      short loc_1800779F2
0x1800779d4  mov     rcx, cs:off_180155A60
0x1800779db  mov     rax, [rcx]
0x1800779de  lea     rcx, off_180155A60
0x1800779e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779ea  test    al, al
0x1800779ec  jz      loc_180077B2F
0x1800779f2  mov     rcx, rdi; hModule
0x1800779f5  mov     cs:qword_180155A68, rcx
0x1800779fc  test    rcx, rcx
0x1800779ff  jz      short loc_180077A1E
0x180077a01  lea     rdx, aSfcisfileprote; "SfcIsFileProtected"
0x180077a08  call    cs:__imp_GetProcAddress
0x180077a0e  mov     cs:qword_180157AD0, rax
0x180077a15  mov     rcx, cs:qword_180155A68
0x180077a1c  jmp     short loc_180077A25
0x180077a1e  mov     rax, cs:qword_180157AD0
0x180077a25  test    rax, rax
0x180077a28  jz      short loc_180077A5C
0x180077a2a  mov     rdx, rsi
0x180077a2d  xor     ecx, ecx
0x180077a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a34  mov     ebx, eax
0x180077a36  mov     eax, ebx
0x180077a38  mov     rcx, [rsp+298h+var_38]
0x180077a40  xor     rcx, rsp; StackCookie
0x180077a43  call    __security_check_cookie
0x180077a48  add     rsp, 278h
0x180077a4f  pop     r14
0x180077a51  pop     rdi
0x180077a52  pop     rsi
0x180077a53  pop     rbx
0x180077a54  retn
0x180077a55  mov     rcx, cs:qword_180155A68
0x180077a5c  mov     cs:byte_180157AC8, r14b
0x180077a63  test    rcx, rcx
0x180077a66  jz      short loc_180077A8D
0x180077a68  mov     rax, cs:off_180155A60
0x180077a6f  lea     rcx, off_180155A60
0x180077a76  mov     rax, [rax]
0x180077a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a7e  test    al, al
0x180077a80  jz      short loc_180077A8F
0x180077a82  mov     cs:qword_180155A68, 0
0x180077a8d  jmp     short loc_180077A36
0x180077a8f  call    cs:__imp_GetLastError
0x180077a95  test    eax, eax
0x180077a97  jle     short loc_180077AA1
0x180077a99  movzx   eax, ax
0x180077a9c  or      eax, 80070000h
0x180077aa1  mov     ecx, eax; this
0x180077aa3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180077aa8  nop
0x180077aa9  lea     rcx, dword_180157DA4
0x180077ab0  call    _Init_thread_header
0x180077ab5  cmp     cs:dword_180157DA4, 0FFFFFFFFh
0x180077abc  jnz     loc_1800777D5
0x180077ac2  lea     rcx, __IsOsComponent____2____dynamic_atexit_destructor_for__SfcModule__; void (__cdecl *)()
0x180077ac9  call    atexit
0x180077ace  lea     rcx, dword_180157DA4
0x180077ad5  call    _Init_thread_footer
0x180077ada  jmp     loc_1800777D5
0x180077adf  lea     rcx, dword_180157DA8
0x180077ae6  call    _Init_thread_header
0x180077aeb  cmp     cs:dword_180157DA8, 0FFFFFFFFh
0x180077af2  jnz     loc_1800777E4
0x180077af8  lea     rcx, __IsOsComponent____2____dynamic_atexit_destructor_for__NtdllModule__; void (__cdecl *)()
0x180077aff  call    atexit
0x180077b04  lea     rcx, dword_180157DA8
0x180077b0b  call    _Init_thread_footer
0x180077b10  jmp     loc_1800777E4
0x180077b15  call    cs:__imp_GetLastError
0x180077b1b  test    eax, eax
0x180077b1d  jle     short loc_180077B27
0x180077b1f  movzx   eax, ax
0x180077b22  or      eax, 80070000h
0x180077b27  mov     ecx, eax; this
0x180077b29  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180077b2e  nop
0x180077b2f  call    cs:__imp_GetLastError
0x180077b35  test    eax, eax
0x180077b37  jle     short loc_180077B41
0x180077b39  movzx   eax, ax
0x180077b3c  or      eax, 80070000h
0x180077b41  mov     ecx, eax; this
0x180077b43  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
