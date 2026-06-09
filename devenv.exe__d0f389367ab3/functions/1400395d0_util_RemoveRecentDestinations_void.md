# util_RemoveRecentDestinations(void)

- ea: `0x1400395d0`
- end: `0x140039725`
- name: `?util_RemoveRecentDestinations@@YAJXZ`
- size: `341`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140001040`
- `0x1400395d0`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x140039611`
- `KERNEL32!GetVersionExW` at `0x140039611`
- `KERNEL32!LoadLibraryW` at `0x140039644`
- `KERNEL32!LoadLibraryW` at `0x140039644`
- `KERNEL32!GetProcAddress` at `0x140039659`
- `KERNEL32!GetProcAddress` at `0x140039659`
- `ole32!CoTaskMemFree` at `0x140039700`
- `ole32!CoTaskMemFree` at `0x140039700`
- `ole32!CoCreateInstance` at `0x1400396b5`
- `ole32!CoCreateInstance` at `0x1400396b5`

## string_xrefs

- `0x14003963d`: `shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 util_RemoveRecentDestinations(void)
{
  HRESULT v0; // ebx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF

  v0 = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  GetVersionExW(&VersionInformation);
  if ( VersionInformation.dwMajorVersion > 6
    || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion )
  {
    pv = 0;
    if ( byte_14009F200 )
    {
      ProcAddress = (FARPROC)qword_14009F1F8;
    }
    else
    {
      LibraryW = LoadLibraryW(L"shell32.dll");
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "GetCurrentProcessExplicitAppUserModelID");
        qword_14009F1F8 = (__int64)ProcAddress;
      }
      else
      {
        ProcAddress = (FARPROC)qword_14009F1F8;
      }
      byte_14009F200 = 1;
    }
    if ( ProcAddress )
    {
      v0 = ((__int64 (__fastcall *)(LPVOID *))ProcAddress)(&pv);
      if ( v0 >= 0 )
      {
        ppv = 0;
        v0 = CoCreateInstance(&CLSID_ApplicationDestinations, 0, 1u, &GUID_12337d35_94c6_48a0_bce7_6a9c69d4d600, &ppv);
        if ( v0 >= 0 )
        {
          v0 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 24LL))(ppv, pv);
          if ( v0 >= 0 )
            v0 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 40LL))(ppv);
        }
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else
    {
      v0 = -2147467259;
    }
    CoTaskMemFree(pv);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400395d0  mov     [rsp-8+arg_0], rbx
0x1400395d5  push    rbp
0x1400395d6  lea     rbp, [rsp-70h]
0x1400395db  sub     rsp, 170h
0x1400395e2  mov     rax, cs:__security_cookie
0x1400395e9  xor     rax, rsp
0x1400395ec  mov     [rbp+70h+var_10], rax
0x1400395f0  xor     ebx, ebx
0x1400395f2  xor     edx, edx; Val
0x1400395f4  mov     r8d, 110h; Size
0x1400395fa  lea     rcx, [rsp+170h+VersionInformation.dwMajorVersion]; void *
0x1400395ff  call    memset_0
0x140039604  mov     [rsp+170h+VersionInformation.dwOSVersionInfoSize], 114h
0x14003960c  lea     rcx, [rsp+170h+VersionInformation]; lpVersionInformation
0x140039611  call    cs:__imp_GetVersionExW
0x140039617  cmp     [rsp+170h+VersionInformation.dwMajorVersion], 6
0x14003961c  ja      short loc_14003962F
0x14003961e  jnz     loc_140039706
0x140039624  cmp     [rsp+170h+VersionInformation.dwMinorVersion], 1
0x140039629  jb      loc_140039706
0x14003962f  and     [rsp+170h+pv], rbx
0x140039634  cmp     cs:byte_14009F200, 0
0x14003963b  jnz     short loc_140039678
0x14003963d  lea     rcx, LibFileName; "shell32.dll"
0x140039644  call    cs:__imp_LoadLibraryW
0x14003964a  test    rax, rax
0x14003964d  jz      short loc_140039668
0x14003964f  lea     rdx, aGetcurrentproc; "GetCurrentProcessExplicitAppUserModelID"
0x140039656  mov     rcx, rax; hModule
0x140039659  call    cs:__imp_GetProcAddress
0x14003965f  mov     cs:qword_14009F1F8, rax
0x140039666  jmp     short loc_14003966F
0x140039668  mov     rax, cs:qword_14009F1F8
0x14003966f  mov     cs:byte_14009F200, 1
0x140039676  jmp     short loc_14003967F
0x140039678  mov     rax, cs:qword_14009F1F8
0x14003967f  test    rax, rax
0x140039682  jz      short loc_1400396F6
0x140039684  lea     rcx, [rsp+170h+pv]
0x140039689  call    rax
0x14003968b  mov     ebx, eax
0x14003968d  test    eax, eax
0x14003968f  js      short loc_1400396FB
0x140039691  and     [rsp+170h+var_140], 0
0x140039697  lea     rax, [rsp+170h+var_140]
0x14003969c  mov     [rsp+170h+ppv], rax; ppv
0x1400396a1  lea     r9, _GUID_12337d35_94c6_48a0_bce7_6a9c69d4d600; riid
0x1400396a8  xor     edx, edx; pUnkOuter
0x1400396aa  lea     r8d, [rdx+1]; dwClsContext
0x1400396ae  lea     rcx, CLSID_ApplicationDestinations; rclsid
0x1400396b5  call    cs:__imp_CoCreateInstance
0x1400396bb  mov     ebx, eax
0x1400396bd  test    eax, eax
0x1400396bf  js      short loc_1400396E4
0x1400396c1  mov     rcx, [rsp+170h+var_140]
0x1400396c6  mov     rax, [rcx]
0x1400396c9  mov     rdx, [rsp+170h+pv]
0x1400396ce  call    qword ptr [rax+18h]
0x1400396d1  mov     ebx, eax
0x1400396d3  test    eax, eax
0x1400396d5  js      short loc_1400396E4
0x1400396d7  mov     rcx, [rsp+170h+var_140]
0x1400396dc  mov     rax, [rcx]
0x1400396df  call    qword ptr [rax+28h]
0x1400396e2  mov     ebx, eax
0x1400396e4  mov     rcx, [rsp+170h+var_140]
0x1400396e9  test    rcx, rcx
0x1400396ec  jz      short loc_1400396FB
0x1400396ee  mov     rax, [rcx]
0x1400396f1  call    qword ptr [rax+10h]
0x1400396f4  jmp     short loc_1400396FB
0x1400396f6  mov     ebx, 80004005h
0x1400396fb  mov     rcx, [rsp+170h+pv]; pv
0x140039700  call    cs:__imp_CoTaskMemFree
0x140039706  mov     eax, ebx
0x140039708  mov     rcx, [rbp+70h+var_10]
0x14003970c  xor     rcx, rsp; StackCookie
0x14003970f  call    __security_check_cookie
0x140039714  mov     rbx, [rsp+170h+arg_0]
0x14003971c  add     rsp, 170h
0x140039723  pop     rbp
0x140039724  retn
```
