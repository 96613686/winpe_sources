# RuntimeRequest::FindVersionedRuntime(int,int *)

- ea: `0x1800297ac`
- end: `0x180029939`
- name: `?FindVersionedRuntime@RuntimeRequest@@QEAAJHPEAH@Z`
- size: `397`
- prototype: `__int64 __fastcall(unsigned __int16 **this, int, int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008624`
- `0x18002b5b8`
- `0x18002ba30`

## callees

- `0x180003840`
- `0x180003890`
- `0x180009af4`
- `0x1800297ac`
- `0x180029b38`
- `0x18002a3b8`
- `0x18002a570`
- `0x18002a8b4`
- `0x18002b19c`
- `0x18003e758`
- `0x180041ac0`
- `0x180045030`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x180029838`
- `KERNEL32!SetErrorMode` at `0x180029842`
- `KERNEL32!SetErrorMode` at `0x180029838`
- `KERNEL32!SetErrorMode` at `0x180029842`
- `USER32!LoadStringW` at `0x18002988e`
- `USER32!LoadStringW` at `0x1800298a9`
- `USER32!LoadStringW` at `0x18002988e`
- `USER32!LoadStringW` at `0x1800298a9`

## string_xrefs

- `0x18002986b`: `A fatal error occurred. However, mscorees.dll could not be loaded to display the appropriate error message.\n\nPlease reinstall the .NET Framework.`

## pseudocode

```c
__int64 __fastcall RuntimeRequest::FindVersionedRuntime(unsigned __int16 **this, int a2, int *a3)
{
  __int64 v6; // rcx
  unsigned __int16 *InstallRoot; // rdi
  UINT v9; // eax
  char v10; // bl
  unsigned int v11; // r9d
  WCHAR *v12; // r8
  WCHAR *v13; // rdx
  HINSTANCE ResourceInst; // rax
  HINSTANCE v15; // rax
  unsigned int ShimMBRTLStyle; // eax
  int VersionedRuntime; // ebx
  WCHAR v18[256]; // [rsp+30h] [rbp-428h] BYREF
  WCHAR Buffer[256]; // [rsp+230h] [rbp-228h] BYREF

  if ( CLRFullPath::GetFullPath((CLRFullPath *)this) )
    return 0;
  InstallRoot = GetInstallRoot(*(_DWORD *)(v6 + 108));
  memset_thunk_772440563353939046(Buffer, 0, 0x200u);
  memset_thunk_772440563353939046(v18, 0, 0x200u);
  if ( InstallRoot )
  {
    if ( RuntimeRequest::ComputeVersionString((const unsigned __int16 **)this, a2) < 0
      || (VersionedRuntime = RuntimeRequest::LoadVersionedRuntime((RuntimeRequest *)this, InstallRoot, 0, a3),
          VersionedRuntime < 0) )
    {
      VersionedRuntime = -2146232576;
    }
    operator delete(InstallRoot);
  }
  else
  {
    if ( a2 )
    {
      if ( !(unsigned int)NoGuiFromShim() )
      {
        v9 = SetErrorMode(0);
        v10 = v9;
        SetErrorMode(v9);
        if ( (v10 & 1) == 0 )
        {
          if ( GetResourceInst() )
          {
            ResourceInst = GetResourceInst();
            LoadStringW(ResourceInst, 1u, Buffer, 256);
            v15 = GetResourceInst();
            LoadStringW(v15, 2u, v18, 256);
            ShimMBRTLStyle = GetShimMBRTLStyle();
            v12 = v18;
            v11 = ShimMBRTLStyle | 0x10;
            v13 = Buffer;
          }
          else
          {
            v11 = 16;
            v12 = (WCHAR *)L"Error";
            v13 = (WCHAR *)L"A fatal error occurred. However, mscorees.dll could not be loaded to display the appropriate "
                            "error message.\n"
                            "\n"
                            "Please reinstall the .NET Framework.";
          }
          UtilMessageBoxNonLocalized(0, v13, v12, v11, 0, 1);
        }
      }
    }
    return (unsigned int)-2146232574;
  }
  return (unsigned int)VersionedRuntime;
}

```

## disassembly

```asm
0x1800297ac  mov     [rsp+arg_18], rbx
0x1800297b1  push    rbp
0x1800297b2  push    rsi
0x1800297b3  push    rdi
0x1800297b4  sub     rsp, 440h
0x1800297bb  mov     rax, cs:__security_cookie
0x1800297c2  xor     rax, rsp
0x1800297c5  mov     [rsp+458h+var_28], rax
0x1800297cd  mov     rbp, r8
0x1800297d0  mov     esi, edx
0x1800297d2  mov     rbx, rcx
0x1800297d5  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x1800297da  test    rax, rax
0x1800297dd  jz      short loc_1800297E6
0x1800297df  xor     eax, eax
0x1800297e1  jmp     loc_180029916
0x1800297e6  mov     ecx, [rcx+6Ch]
0x1800297e9  call    ?GetInstallRoot@@YAPEAGW4VERSION_ARCHITECTURE@@@Z; GetInstallRoot(VERSION_ARCHITECTURE)
0x1800297ee  xor     edx, edx; Val
0x1800297f0  lea     rcx, [rsp+458h+Buffer]; void *
0x1800297f8  mov     r8d, 200h; Size
0x1800297fe  mov     rdi, rax
0x180029801  call    memset$thunk$772440563353939046
0x180029806  xor     edx, edx; Val
0x180029808  lea     rcx, [rsp+458h+var_428]; void *
0x18002980d  mov     r8d, 200h; Size
0x180029813  call    memset$thunk$772440563353939046
0x180029818  test    rdi, rdi
0x18002981b  jnz     loc_1800298E2
0x180029821  test    esi, esi
0x180029823  jz      loc_1800298DB
0x180029829  call    ?NoGuiFromShim@@YAHXZ; NoGuiFromShim(void)
0x18002982e  test    eax, eax
0x180029830  jnz     loc_1800298DB
0x180029836  xor     ecx, ecx; uMode
0x180029838  call    cs:__imp_SetErrorMode
0x18002983e  mov     ecx, eax; uMode
0x180029840  mov     ebx, eax
0x180029842  call    cs:__imp_SetErrorMode
0x180029848  mov     edi, 1
0x18002984d  test    dil, bl
0x180029850  jnz     loc_1800298DB
0x180029856  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x18002985b  test    rax, rax
0x18002985e  jnz     short loc_180029874
0x180029860  lea     r9d, [rdi+0Fh]
0x180029864  lea     r8, aError; "Error"
0x18002986b  lea     rdx, aAFatalErrorOcc; "A fatal error occurred. However, mscore"...
0x180029872  jmp     short loc_1800298C7
0x180029874  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x180029879  mov     ebx, 100h
0x18002987e  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x180029886  mov     r9d, ebx; cchBufferMax
0x180029889  mov     rcx, rax; hInstance
0x18002988c  mov     edx, edi; uID
0x18002988e  call    cs:__imp_LoadStringW
0x180029894  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x180029899  mov     rcx, rax; hInstance
0x18002989c  lea     r8, [rsp+458h+var_428]; lpBuffer
0x1800298a1  mov     r9d, ebx; cchBufferMax
0x1800298a4  mov     edx, 2; uID
0x1800298a9  call    cs:__imp_LoadStringW
0x1800298af  call    ?GetShimMBRTLStyle@@YAIXZ; GetShimMBRTLStyle(void)
0x1800298b4  or      eax, 10h
0x1800298b7  lea     r8, [rsp+458h+var_428]; unsigned __int16 *
0x1800298bc  mov     r9d, eax; unsigned int
0x1800298bf  lea     rdx, [rsp+458h+Buffer]; unsigned __int16 *
0x1800298c7  mov     [rsp+458h+var_430], edi; int
0x1800298cb  xor     ecx, ecx; HWND
0x1800298cd  mov     qword ptr [rsp+458h+var_438], 0; int
0x1800298d6  call    ?UtilMessageBoxNonLocalized@@YAHPEAUHWND__@@PEBG1IHHZZ; UtilMessageBoxNonLocalized(HWND__ *,ushort const *,ushort const *,uint,int,int,...)
0x1800298db  mov     ebx, 80131702h
0x1800298e0  jmp     short loc_180029914
0x1800298e2  mov     edx, esi; int
0x1800298e4  mov     rcx, rbx; this
0x1800298e7  call    ?ComputeVersionString@RuntimeRequest@@QEAAJH@Z; RuntimeRequest::ComputeVersionString(int)
0x1800298ec  test    eax, eax
0x1800298ee  js      short loc_180029907
0x1800298f0  mov     r9, rbp; int *
0x1800298f3  xor     r8d, r8d; unsigned __int16 *
0x1800298f6  mov     rdx, rdi; unsigned __int16 *
0x1800298f9  mov     rcx, rbx; this
0x1800298fc  call    ?LoadVersionedRuntime@RuntimeRequest@@QEAAJPEAG0PEAH@Z; RuntimeRequest::LoadVersionedRuntime(ushort *,ushort *,int *)
0x180029901  mov     ebx, eax
0x180029903  test    eax, eax
0x180029905  jns     short loc_18002990C
0x180029907  mov     ebx, 80131700h
0x18002990c  mov     rcx, rdi; void *
0x18002990f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029914  mov     eax, ebx
0x180029916  mov     rcx, [rsp+458h+var_28]
0x18002991e  xor     rcx, rsp; StackCookie
0x180029921  call    __security_check_cookie
0x180029926  mov     rbx, [rsp+458h+arg_18]
0x18002992e  add     rsp, 440h
0x180029935  pop     rdi
0x180029936  pop     rsi
0x180029937  pop     rbp
0x180029938  retn
```
