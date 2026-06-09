# StartWsdpService(void)

- ea: `0x180019b24`
- end: `0x180019bf4`
- name: `?StartWsdpService@@YAXXZ`
- size: `208`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180016e1c`

## callees

- `0x180001710`
- `0x180019b24`
- `0x180036010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180019bd1`
- `KERNEL32!FreeLibrary` at `0x180019bd1`
- `KERNEL32!LoadLibraryExW` at `0x180019b69`
- `KERNEL32!LoadLibraryExW` at `0x180019b69`
- `KERNEL32!GetProcAddress` at `0x180019b85`
- `KERNEL32!GetProcAddress` at `0x180019ba0`
- `KERNEL32!GetProcAddress` at `0x180019b85`
- `KERNEL32!GetProcAddress` at `0x180019ba0`
- `ntdll!RtlGetNtProductType` at `0x180019b44`
- `ntdll!RtlGetNtProductType` at `0x180019b44`

## string_xrefs

- `0x180019b62`: `mswsock.dll`
- `0x180019b7b`: `StartWsdpService`
- `0x180019b92`: `StopWsdpService`

## pseudocode

```c
void StartWsdpService(void)
{
  HMODULE Library; // rax
  void (*ProcAddress)(void); // rax
  _NT_PRODUCT_TYPE ProductType; // [rsp+20h] [rbp-18h] BYREF

  ProductType = 0;
  if ( RtlGetNtProductType(&ProductType) )
  {
    if ( ProductType != NtProductWinNt )
    {
      Library = LoadLibraryExW(L"mswsock.dll", 0, 0);
      ghMsTcpDll = Library;
      if ( Library )
      {
        gpfnStartWsdpSvc = (int (*)(void))GetProcAddress(Library, "StartWsdpService");
        ProcAddress = (void (*)(void))GetProcAddress(ghMsTcpDll, "StopWsdpService");
        gpfnStopWsdpSvc = ProcAddress;
        if ( !gpfnStartWsdpSvc || !ProcAddress || gpfnStartWsdpSvc() )
        {
          FreeLibrary(ghMsTcpDll);
          ghMsTcpDll = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180019b24  sub     rsp, 38h
0x180019b28  mov     rax, cs:__security_cookie
0x180019b2f  xor     rax, rsp
0x180019b32  mov     [rsp+38h+var_10], rax
0x180019b37  mov     [rsp+38h+ProductType], 0
0x180019b3f  lea     rcx, [rsp+38h+ProductType]; ProductType
0x180019b44  call    cs:__imp_RtlGetNtProductType
0x180019b4a  test    al, al
0x180019b4c  jz      loc_180019BE2
0x180019b52  cmp     [rsp+38h+ProductType], 1
0x180019b57  jz      loc_180019BE2
0x180019b5d  xor     r8d, r8d; dwFlags
0x180019b60  xor     edx, edx; hFile
0x180019b62  lea     rcx, aMswsockDll; "mswsock.dll"
0x180019b69  call    cs:__imp_LoadLibraryExW
0x180019b6f  mov     cs:?ghMsTcpDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghMsTcpDll
0x180019b76  test    rax, rax
0x180019b79  jz      short loc_180019BE2
0x180019b7b  lea     rdx, aStartwsdpservi; "StartWsdpService"
0x180019b82  mov     rcx, rax; hModule
0x180019b85  call    cs:__imp_GetProcAddress
0x180019b8b  mov     cs:?gpfnStartWsdpSvc@@3P6AHXZEA, rax; int (*gpfnStartWsdpSvc)(void)
0x180019b92  lea     rdx, aStopwsdpservic; "StopWsdpService"
0x180019b99  mov     rcx, cs:?ghMsTcpDll@@3PEAUHINSTANCE__@@EA; hModule
0x180019ba0  call    cs:__imp_GetProcAddress
0x180019ba6  mov     cs:?gpfnStopWsdpSvc@@3P6AXXZEA, rax; void (*gpfnStopWsdpSvc)(void)
0x180019bad  mov     rcx, cs:?gpfnStartWsdpSvc@@3P6AHXZEA; int (*gpfnStartWsdpSvc)(void)
0x180019bb4  test    rcx, rcx
0x180019bb7  jz      short loc_180019BCA
0x180019bb9  test    rax, rax
0x180019bbc  jz      short loc_180019BCA
0x180019bbe  mov     rax, rcx
0x180019bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bc6  test    eax, eax
0x180019bc8  jz      short loc_180019BE2
0x180019bca  mov     rcx, cs:?ghMsTcpDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180019bd1  call    cs:__imp_FreeLibrary
0x180019bd7  mov     cs:?ghMsTcpDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghMsTcpDll
0x180019be2  mov     rcx, [rsp+38h+var_10]
0x180019be7  xor     rcx, rsp; StackCookie
0x180019bea  call    __security_check_cookie
0x180019bef  add     rsp, 38h
0x180019bf3  retn
```
