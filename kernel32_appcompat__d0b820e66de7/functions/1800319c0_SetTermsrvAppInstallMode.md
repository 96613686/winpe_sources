# SetTermsrvAppInstallMode

- ea: `0x1800319c0`
- end: `0x180031b01`
- name: `SetTermsrvAppInstallMode`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800319c0`
- `0x180031b08`
- `0x18008275d`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180031ada`
- `ntdll!RtlNtStatusToDosError` at `0x180031ada`
- `ntdll!RtlSetLastWin32Error` at `0x180031ae8`
- `ntdll!RtlSetLastWin32Error` at `0x180031ae8`
- `ntdll!CsrClientCallServer` at `0x180031a41`
- `ntdll!CsrClientCallServer` at `0x180031a41`
- `ntdll!RtlGetSuiteMask` at `0x1800319fb`
- `ntdll!RtlGetSuiteMask` at `0x1800319fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031a90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031a90`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031a75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031a75`

## string_xrefs

- `0x180031a68`: `tsappcmp.dll`
- `0x180031a86`: `TermsrvUpdateAllUserMenu`

## pseudocode

```c
__int64 __fastcall SetTermsrvAppInstallMode(int a1)
{
  int v2; // eax
  FARPROC ProcAddress; // rax
  unsigned int v4; // ebx
  HMODULE Library; // rax
  ULONG v7; // eax
  _DWORD v8[4]; // [rsp+20h] [rbp-3E8h] BYREF
  _BYTE ApiMessage[64]; // [rsp+30h] [rbp-3D8h] BYREF
  int v10; // [rsp+70h] [rbp-398h]

  v8[0] = 0;
  memset_0(ApiMessage, 0, 0x3B8u);
  if ( (RtlGetSuiteMask() & 0x10) == 0 )
    return 0;
  v2 = IsTSAppCompatEnabled(v8);
  if ( v2 < 0 )
    goto LABEL_11;
  if ( !v8[0] )
    return 0;
  v10 = a1;
  v2 = CsrClientCallServer(ApiMessage, 0, (CSR_API_NUMBER)0x10015, 4u);
  if ( v2 < 0 )
  {
LABEL_11:
    v7 = RtlNtStatusToDosError(v2);
    RtlSetLastWin32Error(v7);
    return 0;
  }
  ProcAddress = (FARPROC)gpTermsrvUpdateAllUserMenu;
  v4 = 1;
  if ( gpTermsrvUpdateAllUserMenu
    || ((Library = LoadLibraryExW(L"tsappcmp.dll", 0, 0x800u)) == 0
      ? (ProcAddress = (FARPROC)gpTermsrvUpdateAllUserMenu)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "TermsrvUpdateAllUserMenu"),
                  gpTermsrvUpdateAllUserMenu = (__int64)ProcAddress),
        ProcAddress) )
  {
    ((void (__fastcall *)(bool))ProcAddress)(a1 != 1);
  }
  return v4;
}

```

## disassembly

```asm
0x1800319c0  mov     [rsp+arg_0], rbx
0x1800319c5  push    rdi
0x1800319c6  sub     rsp, 400h
0x1800319cd  mov     rax, cs:__security_cookie
0x1800319d4  xor     rax, rsp
0x1800319d7  mov     [rsp+408h+var_18], rax
0x1800319df  mov     edi, ecx
0x1800319e1  mov     [rsp+408h+var_3E8], 0
0x1800319e9  lea     rcx, [rsp+408h+ApiMessage]; void *
0x1800319ee  xor     edx, edx; Val
0x1800319f0  mov     r8d, 3B8h; Size
0x1800319f6  call    memset_0
0x1800319fb  call    cs:__imp_RtlGetSuiteMask
0x180031a02  nop     dword ptr [rax+rax+00h]
0x180031a07  test    al, 10h
0x180031a09  jz      loc_180031AF4
0x180031a0f  lea     rcx, [rsp+408h+var_3E8]
0x180031a14  call    IsTSAppCompatEnabled
0x180031a19  test    eax, eax
0x180031a1b  js      loc_180031AD8
0x180031a21  cmp     [rsp+408h+var_3E8], 0
0x180031a26  jz      loc_180031AF4
0x180031a2c  xor     edx, edx; CaptureBuffer
0x180031a2e  mov     [rsp+408h+var_398], edi
0x180031a32  mov     r8d, 10015h; ApiNumber
0x180031a38  lea     rcx, [rsp+408h+ApiMessage]; ApiMessage
0x180031a3d  lea     r9d, [rdx+4]; DataLength
0x180031a41  call    cs:__imp_CsrClientCallServer
0x180031a48  nop     dword ptr [rax+rax+00h]
0x180031a4d  test    eax, eax
0x180031a4f  js      loc_180031AD8
0x180031a55  mov     rax, cs:gpTermsrvUpdateAllUserMenu
0x180031a5c  mov     ebx, 1
0x180031a61  test    rax, rax
0x180031a64  jnz     short loc_180031AA8
0x180031a66  xor     edx, edx; hFile
0x180031a68  lea     rcx, aTsappcmpDll; "tsappcmp.dll"
0x180031a6f  mov     r8d, 800h; dwFlags
0x180031a75  call    cs:__imp_LoadLibraryExW
0x180031a7c  nop     dword ptr [rax+rax+00h]
0x180031a81  test    rax, rax
0x180031a84  jz      short loc_180031AF8
0x180031a86  lea     rdx, aTermsrvupdatea; "TermsrvUpdateAllUserMenu"
0x180031a8d  mov     rcx, rax; hModule
0x180031a90  call    cs:__imp_GetProcAddress
0x180031a97  nop     dword ptr [rax+rax+00h]
0x180031a9c  mov     cs:gpTermsrvUpdateAllUserMenu, rax
0x180031aa3  test    rax, rax
0x180031aa6  jz      short loc_180031AB4
0x180031aa8  xor     ecx, ecx
0x180031aaa  cmp     edi, ebx
0x180031aac  setnz   cl
0x180031aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ab4  mov     eax, ebx
0x180031ab6  mov     rcx, [rsp+408h+var_18]
0x180031abe  xor     rcx, rsp; StackCookie
0x180031ac1  call    __security_check_cookie
0x180031ac6  mov     rbx, [rsp+408h+arg_0]
0x180031ace  add     rsp, 400h
0x180031ad5  pop     rdi
0x180031ad6  retn
0x180031ad8  mov     ecx, eax; Status
0x180031ada  call    cs:__imp_RtlNtStatusToDosError
0x180031ae1  nop     dword ptr [rax+rax+00h]
0x180031ae6  mov     ecx, eax; LastError
0x180031ae8  call    cs:__imp_RtlSetLastWin32Error
0x180031aef  nop     dword ptr [rax+rax+00h]
0x180031af4  xor     ebx, ebx
0x180031af6  jmp     short loc_180031AB4
0x180031af8  mov     rax, cs:gpTermsrvUpdateAllUserMenu
0x180031aff  jmp     short loc_180031AA3
```
