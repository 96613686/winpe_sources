# SetTermsrvAppInstallMode

- ea: `0x18002fbd0`
- end: `0x18002fce8`
- name: `SetTermsrvAppInstallMode`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002fbd0`
- `0x18002fcf0`
- `0x18007a7dd`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002fccd`
- `ntdll!RtlNtStatusToDosError` at `0x18002fccd`
- `ntdll!RtlSetLastWin32Error` at `0x18002fcd5`
- `ntdll!RtlSetLastWin32Error` at `0x18002fcd5`
- `ntdll!CsrClientCallServer` at `0x18002fc4b`
- `ntdll!CsrClientCallServer` at `0x18002fc4b`
- `ntdll!RtlGetSuiteMask` at `0x18002fc0b`
- `ntdll!RtlGetSuiteMask` at `0x18002fc0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fc8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fc8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fc75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fc75`

## string_xrefs

- `0x18002fc68`: `tsappcmp.dll`
- `0x18002fc80`: `TermsrvUpdateAllUserMenu`

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
0x18002fbd0  mov     [rsp+arg_0], rbx
0x18002fbd5  push    rdi
0x18002fbd6  sub     rsp, 400h
0x18002fbdd  mov     rax, cs:__security_cookie
0x18002fbe4  xor     rax, rsp
0x18002fbe7  mov     [rsp+408h+var_18], rax
0x18002fbef  mov     edi, ecx
0x18002fbf1  mov     [rsp+408h+var_3E8], 0
0x18002fbf9  lea     rcx, [rsp+408h+ApiMessage]; void *
0x18002fbfe  xor     edx, edx; Val
0x18002fc00  mov     r8d, 3B8h; Size
0x18002fc06  call    memset_0
0x18002fc0b  call    cs:__imp_RtlGetSuiteMask
0x18002fc11  test    al, 10h
0x18002fc13  jz      loc_18002FCDB
0x18002fc19  lea     rcx, [rsp+408h+var_3E8]
0x18002fc1e  call    IsTSAppCompatEnabled
0x18002fc23  test    eax, eax
0x18002fc25  js      loc_18002FCCB
0x18002fc2b  cmp     [rsp+408h+var_3E8], 0
0x18002fc30  jz      loc_18002FCDB
0x18002fc36  xor     edx, edx; CaptureBuffer
0x18002fc38  mov     [rsp+408h+var_398], edi
0x18002fc3c  mov     r8d, 10015h; ApiNumber
0x18002fc42  lea     rcx, [rsp+408h+ApiMessage]; ApiMessage
0x18002fc47  lea     r9d, [rdx+4]; DataLength
0x18002fc4b  call    cs:__imp_CsrClientCallServer
0x18002fc51  test    eax, eax
0x18002fc53  js      short loc_18002FCCB
0x18002fc55  mov     rax, cs:gpTermsrvUpdateAllUserMenu
0x18002fc5c  mov     ebx, 1
0x18002fc61  test    rax, rax
0x18002fc64  jnz     short loc_18002FC9C
0x18002fc66  xor     edx, edx; hFile
0x18002fc68  lea     rcx, LibFileName; "tsappcmp.dll"
0x18002fc6f  mov     r8d, 800h; dwFlags
0x18002fc75  call    cs:__imp_LoadLibraryExW
0x18002fc7b  test    rax, rax
0x18002fc7e  jz      short loc_18002FCDF
0x18002fc80  lea     rdx, aTermsrvupdatea; "TermsrvUpdateAllUserMenu"
0x18002fc87  mov     rcx, rax; hModule
0x18002fc8a  call    cs:__imp_GetProcAddress
0x18002fc90  mov     cs:gpTermsrvUpdateAllUserMenu, rax
0x18002fc97  test    rax, rax
0x18002fc9a  jz      short loc_18002FCA8
0x18002fc9c  xor     ecx, ecx
0x18002fc9e  cmp     edi, ebx
0x18002fca0  setnz   cl
0x18002fca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fca8  mov     eax, ebx
0x18002fcaa  mov     rcx, [rsp+408h+var_18]
0x18002fcb2  xor     rcx, rsp; StackCookie
0x18002fcb5  call    __security_check_cookie
0x18002fcba  mov     rbx, [rsp+408h+arg_0]
0x18002fcc2  add     rsp, 400h
0x18002fcc9  pop     rdi
0x18002fcca  retn
0x18002fccb  mov     ecx, eax; Status
0x18002fccd  call    cs:__imp_RtlNtStatusToDosError
0x18002fcd3  mov     ecx, eax; LastError
0x18002fcd5  call    cs:__imp_RtlSetLastWin32Error
0x18002fcdb  xor     ebx, ebx
0x18002fcdd  jmp     short loc_18002FCA8
0x18002fcdf  mov     rax, cs:gpTermsrvUpdateAllUserMenu
0x18002fce6  jmp     short loc_18002FC97
```
