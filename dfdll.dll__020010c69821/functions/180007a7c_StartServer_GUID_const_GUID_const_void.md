# StartServer(_GUID const &,_GUID const &,void * *)

- ea: `0x180007a7c`
- end: `0x180008938`
- name: `?StartServer@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `3772`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180008938`

## callees

- `0x180001a64`
- `0x180001fc8`
- `0x180002238`
- `0x180002604`
- `0x180003c40`
- `0x1800077d0`
- `0x180007a7c`
- `0x180012b30`
- `0x180014750`
- `0x18001ece3`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007c98`
- `KERNEL32!GetLastError` at `0x18000869c`
- `KERNEL32!GetLastError` at `0x180007c98`
- `KERNEL32!GetLastError` at `0x18000869c`
- `KERNEL32!CloseHandle` at `0x180008728`
- `KERNEL32!CloseHandle` at `0x18000873c`
- `KERNEL32!CloseHandle` at `0x180008728`
- `KERNEL32!CloseHandle` at `0x18000873c`
- `KERNEL32!Sleep` at `0x180008780`
- `KERNEL32!Sleep` at `0x180008780`
- `KERNEL32!CreateProcessW` at `0x180008692`
- `KERNEL32!CreateProcessW` at `0x180008692`
- `KERNEL32!GetSystemInfo` at `0x180007cf8`
- `KERNEL32!GetSystemInfo` at `0x180007cf8`
- `KERNEL32!GetModuleHandleW` at `0x180007c8d`
- `KERNEL32!GetModuleHandleW` at `0x180007c8d`
- `KERNEL32!GetProcAddress` at `0x180007cdd`
- `KERNEL32!GetProcAddress` at `0x180007cdd`
- `ole32!CoCreateInstance` at `0x180008761`
- `ole32!CoCreateInstance` at `0x180008761`

## string_xrefs

- `0x180007c86`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StartServer(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  const struct std::nothrow_t *v5; // rdx
  signed int ModuleFolderPath; // edi
  struct std::nothrow_t *v7; // rdx
  __int64 v8; // r8
  const unsigned __int16 *v9; // rax
  __int64 v10; // r8
  const unsigned __int16 *v11; // rax
  __int64 v12; // r8
  const unsigned __int16 *v13; // rax
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  const struct std::nothrow_t *v16; // rdx
  FARPROC ProcAddress; // rax
  int v18; // esi
  const struct std::nothrow_t *v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  void **v22; // rax
  int v23; // ecx
  const struct std::nothrow_t *v24; // rdx
  unsigned int v25; // r15d
  unsigned __int16 *v26; // rsi
  __int64 v27; // rdx
  unsigned __int16 *v28; // rsi
  unsigned __int16 *v29; // rax
  __int64 v30; // r8
  const unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rax
  __int64 v33; // rdx
  WCHAR *v34; // r10
  const unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rax
  __int64 v37; // rcx
  const unsigned __int16 *v38; // rax
  signed int v39; // eax
  int v40; // ebx
  HRESULT Instance; // eax
  void **v43; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v44; // [rsp+68h] [rbp-98h]
  int v45; // [rsp+70h] [rbp-90h]
  void **v46; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v47; // [rsp+80h] [rbp-80h]
  int v48; // [rsp+88h] [rbp-78h]
  void **v49; // [rsp+90h] [rbp-70h] BYREF
  void **v50; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v51; // [rsp+A0h] [rbp-60h] BYREF
  int v52; // [rsp+A8h] [rbp-58h] BYREF
  int v53; // [rsp+B0h] [rbp-50h]
  void **v54; // [rsp+B8h] [rbp-48h] BYREF
  void **v55; // [rsp+C0h] [rbp-40h]
  LPCWSTR lpCurrentDirectory; // [rsp+C8h] [rbp-38h]
  int v57; // [rsp+D0h] [rbp-30h]
  int v58; // [rsp+D8h] [rbp-28h]
  void **v59; // [rsp+E0h] [rbp-20h] BYREF
  void **v60; // [rsp+E8h] [rbp-18h]
  LPCWSTR lpApplicationName; // [rsp+F0h] [rbp-10h]
  int v62; // [rsp+F8h] [rbp-8h]
  int v63; // [rsp+100h] [rbp+0h]
  void **v64; // [rsp+108h] [rbp+8h] BYREF
  void **v65; // [rsp+110h] [rbp+10h]
  struct std::nothrow_t *v66; // [rsp+118h] [rbp+18h]
  int v67; // [rsp+120h] [rbp+20h]
  int v68; // [rsp+128h] [rbp+28h]
  unsigned int v69; // [rsp+130h] [rbp+30h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+138h] [rbp+38h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+150h] [rbp+50h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v74; // [rsp+248h] [rbp+148h] BYREF

  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset(&StartupInfo.cb + 1, 0, 0x64u);
  v64 = &Dfdll::CString::`vftable';
  v66 = 0;
  v67 = 0;
  v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v68 = 0;
  StartupInfo.cb = 104;
  ModuleFolderPath = Dfdll::CModule::GetModuleFolderPath(g_hModule, (struct Dfdll::CString *)&v64);
  if ( ModuleFolderPath < 0 )
  {
    v64 = &Dfdll::CString::`vftable';
    v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v66 )
      operator delete(v66, v5);
    return (unsigned int)ModuleFolderPath;
  }
  v7 = v66;
  if ( !v66 )
  {
    ModuleFolderPath = -2147024809;
    goto LABEL_25;
  }
  v8 = 0x7FFFFFFF;
  v9 = L"dfsvc.exe";
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  ModuleFolderPath = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
  {
LABEL_25:
    v64 = &Dfdll::CString::`vftable';
    v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v7 )
      operator delete(v7, v7);
    return (unsigned int)ModuleFolderPath;
  }
  if ( (v8 != 0 ? 0x7FFFFFFF - (_DWORD)v8 : 0) != 0 )
  {
    if ( v68 && *((_WORD *)v66 + (unsigned int)(v68 - 1)) != 92 )
    {
      v10 = 0x7FFFFFFF;
      v11 = L"\\";
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v10;
      }
      while ( v10 );
      ModuleFolderPath = v10 == 0 ? 0x80070057 : 0;
      if ( !v10 )
        goto LABEL_25;
      ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v64, L"\\", v10 != 0 ? 0x7FFFFFFF - v10 : 0);
      v7 = v66;
      if ( ModuleFolderPath < 0 )
        goto LABEL_25;
    }
    v12 = 0x7FFFFFFF;
    v13 = L"dfsvc.exe";
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
    ModuleFolderPath = v12 == 0 ? 0x80070057 : 0;
    if ( !v12 )
      goto LABEL_25;
    ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v64, L"dfsvc.exe", v12 != 0 ? 0x7FFFFFFF - v12 : 0);
    if ( ModuleFolderPath < 0 )
    {
      v7 = v66;
      goto LABEL_25;
    }
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "GetNativeSystemInfo");
    if ( ProcAddress )
    {
      ((void (__fastcall *)(_SYSTEM_INFO *))ProcAddress)(&SystemInfo);
      goto LABEL_38;
    }
  }
  else
  {
    LastError = GetLastError();
    ModuleFolderPath = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      ModuleFolderPath = LastError;
    if ( ModuleFolderPath < 0 )
    {
      v64 = &Dfdll::CString::`vftable';
      v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v66 )
        operator delete(v66, v16);
      return (unsigned int)ModuleFolderPath;
    }
  }
  GetSystemInfo(&SystemInfo);
LABEL_38:
  if ( SystemInfo.wProcessorArchitecture )
  {
    v18 = 196;
    if ( SystemInfo.wProcessorArchitecture == 6 )
      v18 = 194;
  }
  else
  {
    v18 = 200;
  }
  v47 = 0;
  v48 = 0;
  v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v74 = 0;
  v44 = 0;
  v45 = 0;
  v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v69 = 0;
  ModuleFolderPath = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v46, 0x104u);
  if ( ModuleFolderPath < 0 )
  {
    v44 = 0;
    v45 = 0;
    v43 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v47 )
      operator delete(v47, v19);
    v47 = 0;
    v48 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v64 = &Dfdll::CString::`vftable';
    v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v66 )
      operator delete(v66, v19);
    return (unsigned int)ModuleFolderPath;
  }
  ModuleFolderPath = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v43, 0x104u);
  if ( ModuleFolderPath < 0 )
  {
    v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v44 )
      operator delete(v44, v20);
    v44 = 0;
    v45 = 0;
    v43 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v47 )
      operator delete(v47, v20);
    v47 = 0;
    v48 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v64 = &Dfdll::CString::`vftable';
    v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v66 )
      operator delete(v66, v20);
    return (unsigned int)ModuleFolderPath;
  }
  ModuleFolderPath = GetRequestedRuntimeInfo_0(v66, 0, 0, 0, v18, v47, v48, &v74, v44, v45, &v69);
  if ( ModuleFolderPath < 0 )
  {
    v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v44 )
      operator delete(v44, v21);
    v44 = 0;
    v45 = 0;
    v43 = &Dfdll::CObject::`vftable';
    v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v47 )
      operator delete(v47, v21);
    v47 = 0;
    v48 = 0;
    v46 = &Dfdll::CObject::`vftable';
    v64 = &Dfdll::CString::`vftable';
    v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v66 )
      operator delete(v66, v21);
    return (unsigned int)ModuleFolderPath;
  }
  v49 = &Dfdll::CString::`vftable';
  v51 = 0;
  v52 = 0;
  v22 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v50 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v23 = 0;
  v53 = 0;
  v54 = &Dfdll::CString::`vftable';
  lpCurrentDirectory = 0;
  v57 = 0;
  v55 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v59 = &Dfdll::CString::`vftable';
  lpApplicationName = 0;
  v62 = 0;
  v60 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v63 = 0;
  v58 = 0;
  if ( !v47 )
  {
    lpCurrentDirectory = 0;
    v57 = 0;
    goto LABEL_68;
  }
  ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v54, v47, v74);
  if ( ModuleFolderPath >= 0 )
  {
    v23 = v53;
    v22 = v50;
LABEL_68:
    v25 = v69;
    v26 = v44;
    if ( v44 )
    {
      if ( v23 )
      {
        ModuleFolderPath = ((__int64 (__fastcall *)(void ***, _QWORD))v22[5])(&v50, 0);
        if ( ModuleFolderPath < 0 )
          goto LABEL_77;
      }
      v53 = 0;
      ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v49, v26, v25);
      if ( ModuleFolderPath >= 0 )
      {
LABEL_90:
        v28 = v51;
        if ( !v51 || !lpCurrentDirectory )
        {
          ModuleFolderPath = -2147024809;
LABEL_113:
          v59 = &Dfdll::CString::`vftable';
          v60 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( lpApplicationName )
            operator delete((void *)lpApplicationName, (const struct std::nothrow_t *)v27);
          lpApplicationName = 0;
          v62 = 0;
          v60 = &Dfdll::CObject::`vftable';
          v59 = &Dfdll::CObject::`vftable';
          v54 = &Dfdll::CString::`vftable';
          v55 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( lpCurrentDirectory )
            operator delete((void *)lpCurrentDirectory, (const struct std::nothrow_t *)v27);
          lpCurrentDirectory = 0;
          v57 = 0;
          v55 = &Dfdll::CObject::`vftable';
          v54 = &Dfdll::CObject::`vftable';
          v49 = &Dfdll::CString::`vftable';
          v50 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v51 )
            operator delete(v51, (const struct std::nothrow_t *)v27);
          v51 = 0;
          v52 = 0;
          v50 = &Dfdll::CObject::`vftable';
          v49 = &Dfdll::CObject::`vftable';
          v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v44 )
            operator delete(v44, (const struct std::nothrow_t *)v27);
          v44 = 0;
          v45 = 0;
          v43 = &Dfdll::CObject::`vftable';
          v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v47 )
            operator delete(v47, (const struct std::nothrow_t *)v27);
          v47 = 0;
          v48 = 0;
          v46 = &Dfdll::CObject::`vftable';
          v64 = &Dfdll::CString::`vftable';
          v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v66 )
            operator delete(v66, (const struct std::nothrow_t *)v27);
          return (unsigned int)ModuleFolderPath;
        }
        v27 = 0x7FFFFFFF;
        v29 = v51;
        do
        {
          if ( !*v29 )
            break;
          ++v29;
          --v27;
        }
        while ( v27 );
        ModuleFolderPath = v27 == 0 ? 0x80070057 : 0;
        v30 = (0x7FFFFFFF - v27) & -(__int64)(v27 != 0);
        if ( !v27 )
          goto LABEL_113;
        if ( (_DWORD)v30 )
        {
          if ( *v51 != 92 || (v28 = v51 + 1, (_DWORD)v30 != 1) )
          {
            if ( v58 && lpCurrentDirectory[v58 - 1] != 92 )
            {
              v27 = 0x7FFFFFFF;
              v31 = L"\\";
              do
              {
                if ( !*v31 )
                  break;
                ++v31;
                --v27;
              }
              while ( v27 );
              ModuleFolderPath = v27 == 0 ? 0x80070057 : 0;
              if ( !v27 )
                goto LABEL_113;
              ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v54, L"\\", v27 != 0 ? 0x7FFFFFFF - v27 : 0);
              if ( ModuleFolderPath < 0 )
                goto LABEL_113;
            }
            if ( v28 )
            {
              v27 = 0x7FFFFFFF;
              v32 = v28;
              do
              {
                if ( !*v32 )
                  break;
                ++v32;
                --v27;
              }
              while ( v27 );
              ModuleFolderPath = v27 == 0 ? 0x80070057 : 0;
              if ( !v27 )
                goto LABEL_113;
              ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v54, v28, v27 != 0 ? 0x7FFFFFFF - v27 : 0);
              if ( ModuleFolderPath < 0 )
                goto LABEL_113;
            }
          }
        }
        ModuleFolderPath = Dfdll::CString::Assign((Dfdll::CString *)&v59, lpCurrentDirectory);
        if ( ModuleFolderPath < 0 )
        {
          v59 = &Dfdll::CString::`vftable';
          v60 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( lpApplicationName )
            operator delete((void *)lpApplicationName, (const struct std::nothrow_t *)v33);
          lpApplicationName = 0;
          v62 = 0;
          v60 = &Dfdll::CObject::`vftable';
          v59 = &Dfdll::CObject::`vftable';
          v54 = &Dfdll::CString::`vftable';
          v55 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( lpCurrentDirectory )
            operator delete((void *)lpCurrentDirectory, (const struct std::nothrow_t *)v33);
          lpCurrentDirectory = 0;
          v57 = 0;
          v55 = &Dfdll::CObject::`vftable';
          v54 = &Dfdll::CObject::`vftable';
          v49 = &Dfdll::CString::`vftable';
          v50 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v51 )
            operator delete(v51, (const struct std::nothrow_t *)v33);
          v51 = 0;
          v52 = 0;
          v50 = &Dfdll::CObject::`vftable';
          v49 = &Dfdll::CObject::`vftable';
          v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v44 )
            operator delete(v44, (const struct std::nothrow_t *)v33);
          v44 = 0;
          v45 = 0;
          v43 = &Dfdll::CObject::`vftable';
          v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v47 )
            operator delete(v47, (const struct std::nothrow_t *)v33);
          v47 = 0;
          v48 = 0;
          v46 = &Dfdll::CObject::`vftable';
          v64 = &Dfdll::CString::`vftable';
          v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v66 )
            operator delete(v66, (const struct std::nothrow_t *)v33);
          return (unsigned int)ModuleFolderPath;
        }
        v34 = (WCHAR *)lpApplicationName;
        if ( !lpApplicationName )
        {
          ModuleFolderPath = -2147024809;
LABEL_159:
          v59 = &Dfdll::CString::`vftable';
          v60 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v34 )
            operator delete(v34, (const struct std::nothrow_t *)v33);
          lpApplicationName = 0;
          v62 = 0;
          v60 = &Dfdll::CObject::`vftable';
          v59 = &Dfdll::CObject::`vftable';
          v54 = &Dfdll::CString::`vftable';
          v55 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( lpCurrentDirectory )
            operator delete((void *)lpCurrentDirectory, (const struct std::nothrow_t *)v33);
          lpCurrentDirectory = 0;
          v57 = 0;
          v55 = &Dfdll::CObject::`vftable';
          v54 = &Dfdll::CObject::`vftable';
          v49 = &Dfdll::CString::`vftable';
          v50 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v51 )
            operator delete(v51, (const struct std::nothrow_t *)v33);
          v51 = 0;
          v52 = 0;
          v50 = &Dfdll::CObject::`vftable';
          v49 = &Dfdll::CObject::`vftable';
          v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v44 )
            operator delete(v44, (const struct std::nothrow_t *)v33);
          v44 = 0;
          v45 = 0;
          v43 = &Dfdll::CObject::`vftable';
          v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v47 )
            operator delete(v47, (const struct std::nothrow_t *)v33);
          v47 = 0;
          v48 = 0;
          v46 = &Dfdll::CObject::`vftable';
          v64 = &Dfdll::CString::`vftable';
          v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( v66 )
            operator delete(v66, (const struct std::nothrow_t *)v33);
          return (unsigned int)ModuleFolderPath;
        }
        v33 = 0x7FFFFFFF;
        v35 = L"dfsvc.exe";
        do
        {
          if ( !*v35 )
            break;
          ++v35;
          --v33;
        }
        while ( v33 );
        ModuleFolderPath = v33 == 0 ? 0x80070057 : 0;
        if ( !v33 )
          goto LABEL_159;
        if ( (v33 != 0 ? 0x7FFFFFFF - (_DWORD)v33 : 0) != 0 )
        {
          if ( v63 && lpApplicationName[v63 - 1] != 92 )
          {
            v33 = 0x7FFFFFFF;
            v36 = L"\\";
            do
            {
              if ( !*v36 )
                break;
              ++v36;
              --v33;
            }
            while ( v33 );
            ModuleFolderPath = v33 == 0 ? 0x80070057 : 0;
            if ( !v33 )
              goto LABEL_159;
            ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v59, L"\\", v33 != 0 ? 0x7FFFFFFF - v33 : 0);
            v34 = (WCHAR *)lpApplicationName;
            if ( ModuleFolderPath < 0 )
              goto LABEL_159;
          }
          v37 = 0x7FFFFFFF;
          v38 = L"dfsvc.exe";
          do
          {
            if ( !*v38 )
              break;
            ++v38;
            --v37;
          }
          while ( v37 );
          ModuleFolderPath = v37 == 0 ? 0x80070057 : 0;
          v33 = (0x7FFFFFFF - v37) & ((unsigned __int128)-(__int128)(unsigned __int64)v37 >> 64);
          if ( !v37 )
            goto LABEL_159;
          ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v59, L"dfsvc.exe", v33);
          v34 = (WCHAR *)lpApplicationName;
          if ( ModuleFolderPath < 0 )
            goto LABEL_159;
        }
        if ( CreateProcessW(v34, 0, 0, 0, 0, 0x1000000u, 0, lpCurrentDirectory, &StartupInfo, &ProcessInformation) )
          goto LABEL_178;
        v39 = GetLastError();
        ModuleFolderPath = (unsigned __int16)v39 | 0x80070000;
        if ( v39 <= 0 )
          ModuleFolderPath = v39;
        if ( ModuleFolderPath >= 0 )
        {
LABEL_178:
          if ( (unsigned __int64)ProcessInformation.hProcess - 1 > 0xFFFFFFFFFFFFFFFDuLL )
          {
            ModuleFolderPath = -2147023537;
            Dfdll::CString::~CString((Dfdll::CString *)&v59);
            Dfdll::CString::~CString((Dfdll::CString *)&v54);
            Dfdll::CString::~CString((Dfdll::CString *)&v49);
            v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
            Dfdll::CBufferBase::Release((Dfdll::CBufferBase *)&v43);
            v43 = &Dfdll::CObject::`vftable';
            v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
            Dfdll::CBufferBase::Release((Dfdll::CBufferBase *)&v46);
            v46 = &Dfdll::CObject::`vftable';
            goto LABEL_177;
          }
          CloseHandle(ProcessInformation.hProcess);
          if ( (unsigned __int64)ProcessInformation.hThread - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(ProcessInformation.hThread);
          v40 = 750;
          do
          {
            --v40;
            Instance = CoCreateInstance(a1, 0, 4u, a2, a3);
            ModuleFolderPath = Instance;
            if ( !Instance )
              break;
            if ( Instance == -2147221232 )
              break;
            if ( Instance == -2147467262 )
              break;
            Sleep(0x14u);
          }
          while ( v40 > 0 );
        }
        Dfdll::CString::~CString((Dfdll::CString *)&v59);
        Dfdll::CString::~CString((Dfdll::CString *)&v54);
        Dfdll::CString::~CString((Dfdll::CString *)&v49);
        v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
        Dfdll::CBufferBase::Release((Dfdll::CBufferBase *)&v43);
        v43 = &Dfdll::CObject::`vftable';
        v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
        Dfdll::CBufferBase::Release((Dfdll::CBufferBase *)&v46);
        v46 = &Dfdll::CObject::`vftable';
LABEL_177:
        Dfdll::CString::~CString((Dfdll::CString *)&v64);
        return (unsigned int)ModuleFolderPath;
      }
    }
    else
    {
      if ( v23 )
      {
        ModuleFolderPath = ((__int64 (__fastcall *)(void ***, _QWORD))v22[5])(&v50, 0);
        if ( ModuleFolderPath < 0 )
          goto LABEL_76;
        v22 = v50;
      }
      v53 = 0;
      ((void (__fastcall *)(void ***, unsigned __int16 **, int *))v22[11])(&v50, &v51, &v52);
      v51 = 0;
      v52 = 0;
      ModuleFolderPath = 0;
    }
LABEL_76:
    if ( ModuleFolderPath < 0 )
    {
LABEL_77:
      v59 = &Dfdll::CString::`vftable';
      v60 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpApplicationName )
        operator delete((void *)lpApplicationName, (const struct std::nothrow_t *)v27);
      lpApplicationName = 0;
      v62 = 0;
      v60 = &Dfdll::CObject::`vftable';
      v59 = &Dfdll::CObject::`vftable';
      v54 = &Dfdll::CString::`vftable';
      v55 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpCurrentDirectory )
        operator delete((void *)lpCurrentDirectory, (const struct std::nothrow_t *)v27);
      lpCurrentDirectory = 0;
      v57 = 0;
      v55 = &Dfdll::CObject::`vftable';
      v54 = &Dfdll::CObject::`vftable';
      v49 = &Dfdll::CString::`vftable';
      v50 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v51 )
        operator delete(v51, (const struct std::nothrow_t *)v27);
      v51 = 0;
      v52 = 0;
      v50 = &Dfdll::CObject::`vftable';
      v49 = &Dfdll::CObject::`vftable';
      v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v44 )
        operator delete(v44, (const struct std::nothrow_t *)v27);
      v44 = 0;
      v45 = 0;
      v43 = &Dfdll::CObject::`vftable';
      v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v47 )
        operator delete(v47, (const struct std::nothrow_t *)v27);
      v47 = 0;
      v48 = 0;
      v46 = &Dfdll::CObject::`vftable';
      v64 = &Dfdll::CString::`vftable';
      v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v66 )
        operator delete(v66, (const struct std::nothrow_t *)v27);
      return (unsigned int)ModuleFolderPath;
    }
    goto LABEL_90;
  }
  v59 = &Dfdll::CString::`vftable';
  v60 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( lpApplicationName )
    operator delete((void *)lpApplicationName, v24);
  lpApplicationName = 0;
  v62 = 0;
  v60 = &Dfdll::CObject::`vftable';
  v59 = &Dfdll::CObject::`vftable';
  v54 = &Dfdll::CString::`vftable';
  v55 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( lpCurrentDirectory )
    operator delete((void *)lpCurrentDirectory, v24);
  lpCurrentDirectory = 0;
  v57 = 0;
  v55 = &Dfdll::CObject::`vftable';
  v54 = &Dfdll::CObject::`vftable';
  v49 = &Dfdll::CString::`vftable';
  v50 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v51 )
    operator delete(v51, v24);
  v51 = 0;
  v52 = 0;
  v50 = &Dfdll::CObject::`vftable';
  v49 = &Dfdll::CObject::`vftable';
  v43 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v44 )
    operator delete(v44, v24);
  v44 = 0;
  v45 = 0;
  v43 = &Dfdll::CObject::`vftable';
  v46 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v47 )
    operator delete(v47, v24);
  v47 = 0;
  v48 = 0;
  v46 = &Dfdll::CObject::`vftable';
  v64 = &Dfdll::CString::`vftable';
  v65 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v66 )
    operator delete(v66, v24);
  return (unsigned int)ModuleFolderPath;
}

```

## disassembly

```asm
0x180007a7c  mov     [rsp-8+arg_8], rbx
0x180007a81  mov     [rsp-8+rclsid], rcx
0x180007a86  push    rbp
0x180007a87  push    rsi
0x180007a88  push    rdi
0x180007a89  push    r12
0x180007a8b  push    r13
0x180007a8d  push    r14
0x180007a8f  push    r15
0x180007a91  lea     rbp, [rsp-0F0h]
0x180007a99  sub     rsp, 1F0h
0x180007aa0  mov     r12, r8
0x180007aa3  mov     r13, rdx
0x180007aa6  xorps   xmm0, xmm0
0x180007aa9  xor     eax, eax
0x180007aab  movups  xmmword ptr [rbp+120h+ProcessInformation.hProcess], xmm0
0x180007aaf  mov     qword ptr [rbp+120h+ProcessInformation.dwProcessId], rax
0x180007ab3  xor     edx, edx; Val
0x180007ab5  lea     r8d, [rax+64h]; Size
0x180007ab9  lea     rcx, [rbp+120h+StartupInfo+4]; void *
0x180007ac0  call    memset
0x180007ac5  lea     r14, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180007acc  mov     [rbp+120h+var_118], r14
0x180007ad0  xor     r15d, r15d
0x180007ad3  mov     [rbp+120h+var_108], r15
0x180007ad7  mov     [rbp+120h+var_100], r15d
0x180007adb  lea     rsi, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180007ae2  mov     [rbp+120h+var_110], rsi
0x180007ae6  mov     [rbp+120h+var_F8], r15d
0x180007aea  mov     [rbp+120h+StartupInfo.cb], 68h ; 'h'
0x180007af4  lea     rdx, [rbp+120h+var_118]; struct Dfdll::CString *
0x180007af8  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180007aff  call    ?GetModuleFolderPath@CModule@Dfdll@@SAJPEAUHINSTANCE__@@AEAVCString@2@@Z; Dfdll::CModule::GetModuleFolderPath(HINSTANCE__ *,Dfdll::CString &)
0x180007b04  mov     edi, eax
0x180007b06  test    eax, eax
0x180007b08  jns     short loc_180007B26
0x180007b0a  mov     [rbp+120h+var_118], r14
0x180007b0e  mov     [rbp+120h+var_110], rsi
0x180007b12  mov     rcx, [rbp+120h+var_108]; void *
0x180007b16  test    rcx, rcx
0x180007b19  jz      short loc_180007B21
0x180007b1b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007b20  nop
0x180007b21  jmp     loc_18000891B
0x180007b26  mov     rdx, [rbp+120h+var_108]
0x180007b2a  test    rdx, rdx
0x180007b2d  jnz     short loc_180007B39
0x180007b2f  mov     edi, 80070057h
0x180007b34  jmp     loc_180007C55
0x180007b39  mov     ebx, 7FFFFFFFh
0x180007b3e  mov     r8d, ebx
0x180007b41  lea     rax, aDfsvcExe; "dfsvc.exe"
0x180007b48  cmp     [rax], r15w
0x180007b4c  jz      short loc_180007B58
0x180007b4e  add     rax, 2
0x180007b52  sub     r8, 1
0x180007b56  jnz     short loc_180007B48
0x180007b58  mov     rax, r8
0x180007b5b  neg     rax
0x180007b5e  sbb     edi, edi
0x180007b60  not     edi
0x180007b62  mov     r14d, 80070057h
0x180007b68  and     edi, r14d
0x180007b6b  mov     rax, r8
0x180007b6e  mov     rcx, rbx
0x180007b71  sub     rcx, r8
0x180007b74  neg     rax
0x180007b77  sbb     r9, r9
0x180007b7a  and     r9, rcx
0x180007b7d  test    r8, r8
0x180007b80  jz      loc_180007C55
0x180007b86  test    r9d, r9d
0x180007b89  jz      loc_180007C77
0x180007b8f  mov     eax, [rbp+120h+var_F8]
0x180007b92  test    eax, eax
0x180007b94  jz      short loc_180007BFA
0x180007b96  dec     eax
0x180007b98  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x180007b9d  jz      short loc_180007BFA
0x180007b9f  mov     r8, rbx
0x180007ba2  lea     rax, asc_180020AE0; "\\"
0x180007ba9  cmp     [rax], r15w
0x180007bad  jz      short loc_180007BB9
0x180007baf  add     rax, 2
0x180007bb3  sub     r8, 1
0x180007bb7  jnz     short loc_180007BA9
0x180007bb9  mov     rax, r8
0x180007bbc  neg     rax
0x180007bbf  sbb     edi, edi
0x180007bc1  not     edi
0x180007bc3  and     edi, r14d
0x180007bc6  mov     rax, r8
0x180007bc9  mov     rcx, rbx
0x180007bcc  sub     rcx, r8
0x180007bcf  neg     rax
0x180007bd2  sbb     r9, r9
0x180007bd5  and     r9, rcx
0x180007bd8  test    r8, r8
0x180007bdb  jz      short loc_180007C55
0x180007bdd  mov     r8d, r9d; unsigned int
0x180007be0  lea     rdx, asc_180020AE0; "\\"
0x180007be7  lea     rcx, [rbp+120h+var_118]; this
0x180007beb  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x180007bf0  mov     edi, eax
0x180007bf2  mov     rdx, [rbp+120h+var_108]
0x180007bf6  test    eax, eax
0x180007bf8  js      short loc_180007C55
0x180007bfa  mov     r8, rbx
0x180007bfd  lea     rax, aDfsvcExe; "dfsvc.exe"
0x180007c04  cmp     [rax], r15w
0x180007c08  jz      short loc_180007C14
0x180007c0a  add     rax, 2
0x180007c0e  sub     r8, 1
0x180007c12  jnz     short loc_180007C04
0x180007c14  mov     rax, r8
0x180007c17  neg     rax
0x180007c1a  sbb     edi, edi
0x180007c1c  not     edi
0x180007c1e  and     edi, r14d
0x180007c21  mov     rax, r8
0x180007c24  mov     rcx, rbx
0x180007c27  sub     rcx, r8
0x180007c2a  neg     rax
0x180007c2d  sbb     r9, r9
0x180007c30  and     r9, rcx
0x180007c33  test    r8, r8
0x180007c36  jz      short loc_180007C55
0x180007c38  mov     r8d, r9d; unsigned int
0x180007c3b  lea     rdx, aDfsvcExe; "dfsvc.exe"
0x180007c42  lea     rcx, [rbp+120h+var_118]; this
0x180007c46  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x180007c4b  mov     edi, eax
0x180007c4d  test    eax, eax
0x180007c4f  jns     short loc_180007C77
0x180007c51  mov     rdx, [rbp+120h+var_108]; struct std::nothrow_t *
0x180007c55  lea     r8, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180007c5c  mov     [rbp+120h+var_118], r8
0x180007c60  mov     [rbp+120h+var_110], rsi
0x180007c64  test    rdx, rdx
0x180007c67  jz      short loc_180007C72
0x180007c69  mov     rcx, rdx; void *
0x180007c6c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007c71  nop
0x180007c72  jmp     loc_18000891B
0x180007c77  xorps   xmm0, xmm0
0x180007c7a  movups  xmmword ptr [rbp+120h+SystemInfo], xmm0
0x180007c7e  movups  xmmword ptr [rbp+120h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180007c82  movups  xmmword ptr [rbp+120h+SystemInfo.dwNumberOfProcessors], xmm0
0x180007c86  lea     rcx, ModuleName; "kernel32.dll"
0x180007c8d  call    cs:__imp_GetModuleHandleW
0x180007c93  test    rax, rax
0x180007c96  jnz     short loc_180007CD3
0x180007c98  call    cs:__imp_GetLastError
0x180007c9e  movzx   edi, ax
0x180007ca1  or      edi, 80070000h
0x180007ca7  test    eax, eax
0x180007ca9  cmovle  edi, eax
0x180007cac  test    edi, edi
0x180007cae  jns     short loc_180007CF4
0x180007cb0  lea     r8, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180007cb7  mov     [rbp+120h+var_118], r8
0x180007cbb  mov     [rbp+120h+var_110], rsi
0x180007cbf  mov     rcx, [rbp+120h+var_108]; void *
0x180007cc3  test    rcx, rcx
0x180007cc6  jz      short loc_180007CCE
0x180007cc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007ccd  nop
0x180007cce  jmp     loc_18000891B
0x180007cd3  lea     rdx, ProcName; "GetNativeSystemInfo"
0x180007cda  mov     rcx, rax; hModule
0x180007cdd  call    cs:__imp_GetProcAddress
0x180007ce3  test    rax, rax
0x180007ce6  jz      short loc_180007CF4
0x180007ce8  lea     rcx, [rbp+120h+SystemInfo]
0x180007cec  call    cs:__guard_dispatch_icall_fptr
0x180007cf2  jmp     short loc_180007CFE
0x180007cf4  lea     rcx, [rbp+120h+SystemInfo]; lpSystemInfo
0x180007cf8  call    cs:__imp_GetSystemInfo
0x180007cfe  movzx   eax, word ptr [rbp+120h+SystemInfo]
0x180007d02  test    ax, ax
0x180007d05  jnz     short loc_180007D0E
0x180007d07  mov     esi, 0C8h
0x180007d0c  jmp     short loc_180007D1D
0x180007d0e  mov     esi, 0C4h
0x180007d13  lea     ecx, [rsi-2]
0x180007d16  cmp     ax, 6
0x180007d1a  cmovz   esi, ecx
0x180007d1d  mov     [rbp+120h+var_1A0], r15
0x180007d21  mov     [rbp+120h+var_198], r15d
0x180007d25  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180007d2c  mov     [rsp+220h+var_1A8], rax
0x180007d31  mov     [rbp+120h+arg_18], r15d
0x180007d38  mov     [rsp+220h+var_1B8], r15
0x180007d3d  mov     [rsp+220h+var_1B0], r15d
0x180007d42  mov     [rsp+220h+var_1C0], rax
0x180007d47  mov     [rbp+120h+var_F0], r15d
0x180007d4b  mov     edx, 104h; unsigned int
0x180007d50  lea     rcx, [rsp+220h+var_1A8]; this
0x180007d55  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180007d5a  mov     edi, eax
0x180007d5c  test    eax, eax
0x180007d5e  jns     short loc_180007DD4
0x180007d60  lea     rsi, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180007d67  mov     [rsp+220h+var_1C0], rsi
0x180007d6c  mov     rcx, [rsp+220h+var_1B8]; void *
0x180007d71  test    rcx, rcx
0x180007d74  jz      short loc_180007D7B
0x180007d76  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007d7b  mov     [rsp+220h+var_1B8], r15
0x180007d80  mov     [rsp+220h+var_1B0], r15d
0x180007d85  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180007d8c  mov     [rsp+220h+var_1C0], rbx
0x180007d91  mov     [rsp+220h+var_1A8], rsi
0x180007d96  mov     rcx, [rbp+120h+var_1A0]; void *
0x180007d9a  test    rcx, rcx
0x180007d9d  jz      short loc_180007DA4
0x180007d9f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007da4  mov     [rbp+120h+var_1A0], r15
0x180007da8  mov     [rbp+120h+var_198], r15d
0x180007dac  mov     [rsp+220h+var_1A8], rbx
0x180007db1  lea     r8, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180007db8  mov     [rbp+120h+var_118], r8
0x180007dbc  mov     [rbp+120h+var_110], rsi
0x180007dc0  mov     rcx, [rbp+120h+var_108]; void *
0x180007dc4  test    rcx, rcx
0x180007dc7  jz      short loc_180007DCF
0x180007dc9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007dce  nop
0x180007dcf  jmp     loc_18000891B
0x180007dd4  mov     edx, 104h; unsigned int
0x180007dd9  lea     rcx, [rsp+220h+var_1C0]; this
0x180007dde  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180007de3  mov     edi, eax
0x180007de5  test    eax, eax
0x180007de7  jns     short loc_180007E5D
0x180007de9  lea     rsi, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180007df0  mov     [rsp+220h+var_1C0], rsi
0x180007df5  mov     rcx, [rsp+220h+var_1B8]; void *
0x180007dfa  test    rcx, rcx
0x180007dfd  jz      short loc_180007E04
0x180007dff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007e04  mov     [rsp+220h+var_1B8], r15
0x180007e09  mov     [rsp+220h+var_1B0], r15d
0x180007e0e  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180007e15  mov     [rsp+220h+var_1C0], rbx
0x180007e1a  mov     [rsp+220h+var_1A8], rsi
0x180007e1f  mov     rcx, [rbp+120h+var_1A0]; void *
0x180007e23  test    rcx, rcx
0x180007e26  jz      short loc_180007E2D
0x180007e28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007e2d  mov     [rbp+120h+var_1A0], r15
0x180007e31  mov     [rbp+120h+var_198], r15d
0x180007e35  mov     [rsp+220h+var_1A8], rbx
0x180007e3a  lea     r8, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180007e41  mov     [rbp+120h+var_118], r8
0x180007e45  mov     [rbp+120h+var_110], rsi
0x180007e49  mov     rcx, [rbp+120h+var_108]; void *
0x180007e4d  test    rcx, rcx
0x180007e50  jz      short loc_180007E58
0x180007e52  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007e57  nop
0x180007e58  jmp     loc_18000891B
0x180007e5d  lea     rax, [rbp+120h+var_F0]
0x180007e61  mov     [rsp+220h+var_1D0], rax
0x180007e66  mov     eax, [rsp+220h+var_1B0]
0x180007e6a  mov     dword ptr [rsp+220h+lpProcessInformation], eax
0x180007e6e  mov     rax, [rsp+220h+var_1B8]
0x180007e73  mov     [rsp+220h+lpStartupInfo], rax
0x180007e78  lea     rax, [rbp+120h+arg_18]
0x180007e7f  mov     [rsp+220h+lpCurrentDirectory], rax
0x180007e84  mov     eax, [rbp+120h+var_198]
0x180007e87  mov     dword ptr [rsp+220h+lpEnvironment], eax
0x180007e8b  mov     rax, [rbp+120h+var_1A0]
0x180007e8f  mov     qword ptr [rsp+220h+dwCreationFlags], rax
0x180007e94  mov     [rsp+220h+bInheritHandles], esi
0x180007e98  xor     r9d, r9d
0x180007e9b  xor     r8d, r8d
0x180007e9e  xor     edx, edx
0x180007ea0  mov     rcx, [rbp+120h+var_108]
0x180007ea4  call    GetRequestedRuntimeInfo_0
0x180007ea9  mov     edi, eax
0x180007eab  test    eax, eax
0x180007ead  jns     short loc_180007F23
0x180007eaf  lea     rsi, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180007eb6  mov     [rsp+220h+var_1C0], rsi
0x180007ebb  mov     rcx, [rsp+220h+var_1B8]; void *
0x180007ec0  test    rcx, rcx
0x180007ec3  jz      short loc_180007ECA
0x180007ec5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007eca  mov     [rsp+220h+var_1B8], r15
0x180007ecf  mov     [rsp+220h+var_1B0], r15d
0x180007ed4  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180007edb  mov     [rsp+220h+var_1C0], rbx
0x180007ee0  mov     [rsp+220h+var_1A8], rsi
0x180007ee5  mov     rcx, [rbp+120h+var_1A0]; void *
0x180007ee9  test    rcx, rcx
0x180007eec  jz      short loc_180007EF3
0x180007eee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007ef3  mov     [rbp+120h+var_1A0], r15
0x180007ef7  mov     [rbp+120h+var_198], r15d
  ... truncated ...
```
