# CActiveXInstallBroker::InstallFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong)

- ea: `0x140004e20`
- end: `0x140005101`
- name: `?InstallFile@CActiveXInstallBroker@@QEAAJPEAGPEAUHWND__@@0000K@Z`
- size: `737`
- prototype: `__int64 __usercall@<rax>(CActiveXInstallBroker *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HWND@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140007fe0`

## callees

- `0x140004a18`
- `0x140004e20`
- `0x1400088a8`
- `0x140008b44`
- `0x140008f78`
- `0x140009b50`
- `0x14000bb30`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140004fdd`
- `KERNEL32!GetProcAddress` at `0x140004fdd`
- `KERNEL32!LoadLibraryExW` at `0x140004f9a`
- `KERNEL32!LoadLibraryExW` at `0x140004f9a`
- `KERNEL32!LeaveCriticalSection` at `0x1400050e3`
- `KERNEL32!LeaveCriticalSection` at `0x1400050e3`
- `KERNEL32!EnterCriticalSection` at `0x140004e5e`
- `KERNEL32!EnterCriticalSection` at `0x140004e5e`
- `KERNEL32!GetLastError` at `0x140004faf`
- `KERNEL32!GetLastError` at `0x140004faf`
- `ole32!CoTaskMemFree` at `0x1400050b4`
- `ole32!CoTaskMemFree` at `0x1400050c8`
- `ole32!CoTaskMemFree` at `0x1400050b4`
- `ole32!CoTaskMemFree` at `0x1400050c8`
- `urlmon!CoInternetSetFeatureEnabled` at `0x14000505e`
- `urlmon!CoInternetSetFeatureEnabled` at `0x14000508b`
- `urlmon!CoInternetSetFeatureEnabled` at `0x14000505e`
- `urlmon!CoInternetSetFeatureEnabled` at `0x14000508b`
- `urlmon!__imp_CoInternetApproveExtension` at `0x140005075`
- `urlmon!__imp_CoInternetApproveExtension` at `0x140005075`

## string_xrefs

- `0x140004f8d`: `IEAdvpack.Dll`
- `0x140004fd3`: `AdvInstallFileW`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::InstallFile(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        HWND a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned int a8)
{
  unsigned __int16 *v8; // r14
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  unsigned __int16 *v10; // rbp
  signed int HasExtensionW; // ebx
  const unsigned __int16 *v15; // r15
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // eax
  int v19; // eax
  int v20; // r8d
  const unsigned __int16 *v21; // r12
  int v22; // eax
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+8h] BYREF
  HWND v29; // [rsp+A0h] [rbp+18h]
  unsigned __int16 *v30; // [rsp+A8h] [rbp+20h]

  v30 = a4;
  v29 = a3;
  v8 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v10 = 0;
  lpFileName = 0;
  pv = 0;
  if ( !*(_DWORD *)this )
  {
    HasExtensionW = -2147024882;
    goto LABEL_38;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)this + 12) < 2 )
  {
    HasExtensionW = -2147019873;
    goto LABEL_38;
  }
  if ( !a2 || !a5 || (v15 = a7) == 0 )
  {
    HasExtensionW = -2147024809;
    goto LABEL_33;
  }
  v16 = *((_QWORD *)this + 8) - (_QWORD)a2;
  do
  {
    v17 = *(unsigned __int16 *)((char *)a2 + v16);
    v18 = *a2 - v17;
    if ( v18 )
      break;
    ++a2;
  }
  while ( v17 );
  if ( v18 )
  {
    HasExtensionW = -2147024891;
    goto LABEL_38;
  }
  v19 = CatDirAndFileW(a4, a5, (unsigned __int16 **)&lpFileName);
  v8 = (unsigned __int16 *)lpFileName;
  if ( !v19 )
  {
LABEL_31:
    HasExtensionW = -2147024882;
    goto LABEL_33;
  }
  HasExtensionW = VerifyFileHasExtensionW(lpFileName);
  if ( HasExtensionW >= 0 )
  {
    HasExtensionW = CActiveXInstallBroker::FileIsAuthorized(this, v8, v20);
    if ( HasExtensionW >= 0 )
    {
      v21 = a6;
      v22 = CatDirAndFileW(a6, v15, (unsigned __int16 **)&pv);
      v10 = (unsigned __int16 *)pv;
      if ( v22 )
      {
        HasExtensionW = VerifyFileHasExtensionW((LPCWSTR)pv);
        if ( HasExtensionW < 0 )
          goto LABEL_33;
        if ( !*((_DWORD *)this + 35) && !(unsigned int)ContainingPathIsTamperProof(v10) )
          goto LABEL_27;
        HasExtensionW = AddToFileListW(v10, (struct sFNAME **)this + 16);
        if ( HasExtensionW >= 0 )
        {
          Library = (HMODULE)*((_QWORD *)this + 14);
          if ( !Library
            && (Library = LoadLibraryExW(L"IEAdvpack.Dll", 0, 0x800u), (*((_QWORD *)this + 14) = Library) == 0)
            || (ProcAddress = GetProcAddress(Library, "AdvInstallFileW")) == 0 )
          {
            LastError = GetLastError();
            HasExtensionW = LastError;
            if ( LastError > 0 )
              HasExtensionW = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_33;
          }
          HasExtensionW = ((__int64 (__fastcall *)(HWND, unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, _DWORD))ProcAddress)(
                            v29,
                            v30,
                            a5,
                            v21,
                            v15,
                            a8,
                            0);
          if ( HasExtensionW >= 0 )
          {
            HasExtensionW = EnsureACILCanReadFile(v21, v15);
            if ( HasExtensionW >= 0 )
            {
              if ( CoInternetSetFeatureEnabled(FEATURE_ADDON_MANAGEMENT, 2u, 1) >= 0 )
              {
                CoInternetApproveExtension((char *)this + 88, 1);
                CoInternetSetFeatureEnabled(FEATURE_ADDON_MANAGEMENT, 2u, 0);
              }
              *((_DWORD *)this + 12) = 7;
              goto LABEL_33;
            }
LABEL_27:
            HasExtensionW = -2147024891;
          }
        }
LABEL_33:
        if ( v10 )
          CoTaskMemFree(v10);
        goto LABEL_35;
      }
      goto LABEL_31;
    }
  }
LABEL_35:
  if ( v8 )
    CoTaskMemFree(v8);
LABEL_38:
  if ( *(_DWORD *)this )
    LeaveCriticalSection(v9);
  return (unsigned int)HasExtensionW;
}

```

## disassembly

```asm
0x140004e20  mov     rax, rsp
0x140004e23  mov     [rax+20h], r9
0x140004e27  mov     [rax+18h], r8
0x140004e2b  push    rbx
0x140004e2c  push    rbp
0x140004e2d  push    rsi
0x140004e2e  push    rdi
0x140004e2f  push    r12
0x140004e31  push    r14
0x140004e33  push    r15
0x140004e35  sub     rsp, 50h
0x140004e39  xor     r14d, r14d
0x140004e3c  lea     rsi, [rcx+8]
0x140004e40  xor     ebp, ebp
0x140004e42  mov     [rax-48h], r14
0x140004e46  mov     r12, r9
0x140004e49  mov     rbx, rdx
0x140004e4c  mov     rdi, rcx
0x140004e4f  mov     [rax+8], rbp
0x140004e53  cmp     [rcx], ebp
0x140004e55  jz      loc_1400050D6
0x140004e5b  mov     rcx, rsi; lpCriticalSection
0x140004e5e  call    cs:__imp_EnterCriticalSection
0x140004e65  nop     dword ptr [rax+rax+00h]
0x140004e6a  cmp     dword ptr [rdi+30h], 2
0x140004e6e  jge     short loc_140004E7A
0x140004e70  mov     ebx, 8007139Fh
0x140004e75  jmp     loc_1400050DB
0x140004e7a  test    rbx, rbx
0x140004e7d  jz      loc_1400050A7
0x140004e83  cmp     [rsp+88h+arg_20], rbp
0x140004e8b  jz      loc_1400050A7
0x140004e91  mov     r15, [rsp+88h+arg_30]
0x140004e99  test    r15, r15
0x140004e9c  jz      loc_1400050A7
0x140004ea2  mov     rdx, [rdi+40h]
0x140004ea6  sub     rdx, rbx
0x140004ea9  movzx   eax, word ptr [rbx]
0x140004eac  movzx   ecx, word ptr [rbx+rdx]
0x140004eb0  sub     eax, ecx
0x140004eb2  jnz     short loc_140004EBC
0x140004eb4  add     rbx, 2
0x140004eb8  test    ecx, ecx
0x140004eba  jnz     short loc_140004EA9
0x140004ebc  test    eax, eax
0x140004ebe  jz      short loc_140004ECA
0x140004ec0  mov     ebx, 80070005h
0x140004ec5  jmp     loc_1400050DB
0x140004eca  mov     rdx, [rsp+88h+arg_20]; unsigned __int16 *
0x140004ed2  lea     r8, [rsp+88h+lpFileName]; unsigned __int16 **
0x140004ed7  mov     rcx, r12; unsigned __int16 *
0x140004eda  call    ?CatDirAndFileW@@YAHPEBG0PEAPEAG@Z; CatDirAndFileW(ushort const *,ushort const *,ushort * *)
0x140004edf  mov     r14, [rsp+88h+lpFileName]
0x140004ee4  test    eax, eax
0x140004ee6  jz      loc_1400050A0
0x140004eec  mov     rcx, r14; lpFileName
0x140004eef  call    ?VerifyFileHasExtensionW@@YAJPEBG@Z; VerifyFileHasExtensionW(ushort const *)
0x140004ef4  mov     ebx, eax
0x140004ef6  test    eax, eax
0x140004ef8  js      loc_1400050C0
0x140004efe  mov     rdx, r14; unsigned __int16 *
0x140004f01  mov     rcx, rdi; this
0x140004f04  call    ?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x140004f09  mov     ebx, eax
0x140004f0b  test    eax, eax
0x140004f0d  js      loc_1400050C0
0x140004f13  mov     r12, [rsp+88h+arg_28]
0x140004f1b  lea     r8, [rsp+88h+pv]; unsigned __int16 **
0x140004f23  mov     rcx, r12; unsigned __int16 *
0x140004f26  mov     rdx, r15; unsigned __int16 *
0x140004f29  call    ?CatDirAndFileW@@YAHPEBG0PEAPEAG@Z; CatDirAndFileW(ushort const *,ushort const *,ushort * *)
0x140004f2e  mov     rbp, [rsp+88h+pv]
0x140004f36  test    eax, eax
0x140004f38  jz      loc_1400050A0
0x140004f3e  mov     rcx, rbp; lpFileName
0x140004f41  call    ?VerifyFileHasExtensionW@@YAJPEBG@Z; VerifyFileHasExtensionW(ushort const *)
0x140004f46  mov     ebx, eax
0x140004f48  test    eax, eax
0x140004f4a  js      loc_1400050AC
0x140004f50  cmp     dword ptr [rdi+8Ch], 0
0x140004f57  jnz     short loc_140004F69
0x140004f59  mov     rcx, rbp; unsigned __int16 *
0x140004f5c  call    ?ContainingPathIsTamperProof@@YAHPEBG@Z; ContainingPathIsTamperProof(ushort const *)
0x140004f61  test    eax, eax
0x140004f63  jz      loc_140005043
0x140004f69  lea     rdx, [rdi+80h]; struct sFNAME **
0x140004f70  mov     rcx, rbp; unsigned __int16 *
0x140004f73  call    ?AddToFileListW@@YAJPEBGPEAPEAUsFNAME@@@Z; AddToFileListW(ushort const *,sFNAME * *)
0x140004f78  mov     ebx, eax
0x140004f7a  test    eax, eax
0x140004f7c  js      loc_1400050AC
0x140004f82  mov     rax, [rdi+70h]
0x140004f86  test    rax, rax
0x140004f89  jnz     short loc_140004FD3
0x140004f8b  xor     edx, edx; hFile
0x140004f8d  lea     rcx, LibFileName; "IEAdvpack.Dll"
0x140004f94  mov     r8d, 800h; dwFlags
0x140004f9a  call    cs:__imp_LoadLibraryExW
0x140004fa1  nop     dword ptr [rax+rax+00h]
0x140004fa6  mov     [rdi+70h], rax
0x140004faa  test    rax, rax
0x140004fad  jnz     short loc_140004FD3
0x140004faf  call    cs:__imp_GetLastError
0x140004fb6  nop     dword ptr [rax+rax+00h]
0x140004fbb  mov     ebx, eax
0x140004fbd  test    eax, eax
0x140004fbf  jle     loc_1400050AC
0x140004fc5  movzx   ebx, ax
0x140004fc8  or      ebx, 80070000h
0x140004fce  jmp     loc_1400050AC
0x140004fd3  lea     rdx, ProcName; "AdvInstallFileW"
0x140004fda  mov     rcx, rax; hModule
0x140004fdd  call    cs:__imp_GetProcAddress
0x140004fe4  nop     dword ptr [rax+rax+00h]
0x140004fe9  mov     r10, rax
0x140004fec  test    rax, rax
0x140004fef  jz      short loc_140004FAF
0x140004ff1  mov     eax, [rsp+88h+arg_38]
0x140004ff8  mov     r9, r12
0x140004ffb  mov     r8, [rsp+88h+arg_20]
0x140005003  mov     rdx, [rsp+88h+arg_18]
0x14000500b  mov     rcx, [rsp+88h+arg_10]
0x140005013  mov     [rsp+88h+var_58], 0
0x14000501b  mov     [rsp+88h+var_60], eax
0x14000501f  mov     rax, r10
0x140005022  mov     [rsp+88h+var_68], r15
0x140005027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000502c  mov     ebx, eax
0x14000502e  test    eax, eax
0x140005030  js      short loc_1400050AC
0x140005032  mov     rdx, r15; unsigned __int16 *
0x140005035  mov     rcx, r12; unsigned __int16 *
0x140005038  call    ?EnsureACILCanReadFile@@YAJPEBG0@Z; EnsureACILCanReadFile(ushort const *,ushort const *)
0x14000503d  mov     ebx, eax
0x14000503f  test    eax, eax
0x140005041  jns     short loc_14000504A
0x140005043  mov     ebx, 80070005h
0x140005048  jmp     short loc_1400050AC
0x14000504a  mov     r15d, 1
0x140005050  mov     r8d, r15d; fEnable
0x140005053  lea     r12d, [r15+0Ch]
0x140005057  mov     ecx, r12d; FeatureEntry
0x14000505a  lea     edx, [r15+1]; dwFlags
0x14000505e  call    cs:__imp_CoInternetSetFeatureEnabled
0x140005065  nop     dword ptr [rax+rax+00h]
0x14000506a  test    eax, eax
0x14000506c  js      short loc_140005097
0x14000506e  lea     rcx, [rdi+58h]
0x140005072  mov     edx, r15d
0x140005075  call    cs:__imp_CoInternetApproveExtension
0x14000507c  nop     dword ptr [rax+rax+00h]
0x140005081  xor     r8d, r8d; fEnable
0x140005084  lea     edx, [r15+1]; dwFlags
0x140005088  mov     ecx, r12d; FeatureEntry
0x14000508b  call    cs:__imp_CoInternetSetFeatureEnabled
0x140005092  nop     dword ptr [rax+rax+00h]
0x140005097  mov     dword ptr [rdi+30h], 7
0x14000509e  jmp     short loc_1400050AC
0x1400050a0  mov     ebx, 8007000Eh
0x1400050a5  jmp     short loc_1400050AC
0x1400050a7  mov     ebx, 80070057h
0x1400050ac  test    rbp, rbp
0x1400050af  jz      short loc_1400050C0
0x1400050b1  mov     rcx, rbp; pv
0x1400050b4  call    cs:__imp_CoTaskMemFree
0x1400050bb  nop     dword ptr [rax+rax+00h]
0x1400050c0  test    r14, r14
0x1400050c3  jz      short loc_1400050DB
0x1400050c5  mov     rcx, r14; pv
0x1400050c8  call    cs:__imp_CoTaskMemFree
0x1400050cf  nop     dword ptr [rax+rax+00h]
0x1400050d4  jmp     short loc_1400050DB
0x1400050d6  mov     ebx, 8007000Eh
0x1400050db  cmp     dword ptr [rdi], 0
0x1400050de  jz      short loc_1400050EF
0x1400050e0  mov     rcx, rsi; lpCriticalSection
0x1400050e3  call    cs:__imp_LeaveCriticalSection
0x1400050ea  nop     dword ptr [rax+rax+00h]
0x1400050ef  mov     eax, ebx
0x1400050f1  add     rsp, 50h
0x1400050f5  pop     r15
0x1400050f7  pop     r14
0x1400050f9  pop     r12
0x1400050fb  pop     rdi
0x1400050fc  pop     rsi
0x1400050fd  pop     rbp
0x1400050fe  pop     rbx
0x1400050ff  retn
```
