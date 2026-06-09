# NGENService::GetWindowsServiceStatus(_SERVICE_STATUS *)

- ea: `0x18001ada4`
- end: `0x18001ae6b`
- name: `?GetWindowsServiceStatus@NGENService@@YAJPEAU_SERVICE_STATUS@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(NGENService *__hidden this, struct _SERVICE_STATUS *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18001ae6c`
- `0x18001afbc`

## callees

- `0x180007914`
- `0x18001a690`
- `0x18001ada4`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001adeb`
- `KERNEL32!LoadLibraryExW` at `0x18001adeb`
- `KERNEL32!GetLastError` at `0x18001ae34`
- `KERNEL32!GetLastError` at `0x18001ae34`
- `KERNEL32!GetProcAddress` at `0x18001ae00`
- `KERNEL32!GetProcAddress` at `0x18001ae00`

## string_xrefs

- `0x18001ade2`: `advapi32.dll`
- `0x18001adf6`: `QueryServiceStatus`

## pseudocode

```c
__int64 __fastcall NGENService::GetWindowsServiceStatus(NGENService *this, struct SC_HANDLE__ **a2)
{
  signed int v3; // ebx
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  signed int LastError; // eax
  struct SC_HANDLE__ *v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v3 = NGENService::OpenNGENService((NGENService *)&v8, a2);
  if ( v3 >= 0 )
  {
    ProcAddress = (FARPROC)qword_18006FF28;
    if ( (qword_18006FF28
       || !bQueryServiceStatusProbed
       && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
         ? (ProcAddress = (FARPROC)qword_18006FF28)
         : (FARPROC)(ProcAddress = GetProcAddress(Library, "QueryServiceStatus"), qword_18006FF28 = (__int64)ProcAddress),
           bQueryServiceStatusProbed = 1,
           ProcAddress))
      && ((unsigned int (__fastcall *)(struct SC_HANDLE__ *, NGENService *))ProcAddress)(v8, this) )
    {
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
    }
  }
  if ( v8 )
    CLRCloseServiceHandle(v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001ada4  mov     [rsp+arg_0], rbx
0x18001ada9  push    rsi
0x18001adaa  sub     rsp, 20h
0x18001adae  and     [rsp+28h+arg_8], 0
0x18001adb4  mov     rsi, rcx
0x18001adb7  lea     rcx, [rsp+28h+arg_8]; this
0x18001adbc  call    ?OpenNGENService@NGENService@@YAJPEAPEAUSC_HANDLE__@@@Z; NGENService::OpenNGENService(SC_HANDLE__ * *)
0x18001adc1  mov     ebx, eax
0x18001adc3  test    eax, eax
0x18001adc5  js      loc_18001AE4C
0x18001adcb  mov     rax, cs:qword_18006FF28
0x18001add2  test    rax, rax
0x18001add5  jnz     short loc_18001AE22
0x18001add7  cmp     cs:?bQueryServiceStatusProbed@@3_NA, al; bool bQueryServiceStatusProbed
0x18001addd  jnz     short loc_18001AE34
0x18001addf  xor     r8d, r8d; dwFlags
0x18001ade2  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18001ade9  xor     edx, edx; hFile
0x18001adeb  call    cs:__imp_LoadLibraryExW
0x18001adf1  test    rax, rax
0x18001adf4  jz      short loc_18001AE0F
0x18001adf6  lea     rdx, aQueryservicest; "QueryServiceStatus"
0x18001adfd  mov     rcx, rax; hModule
0x18001ae00  call    cs:__imp_GetProcAddress
0x18001ae06  mov     cs:qword_18006FF28, rax
0x18001ae0d  jmp     short loc_18001AE16
0x18001ae0f  mov     rax, cs:qword_18006FF28
0x18001ae16  mov     cs:?bQueryServiceStatusProbed@@3_NA, 1; bool bQueryServiceStatusProbed
0x18001ae1d  test    rax, rax
0x18001ae20  jz      short loc_18001AE34
0x18001ae22  mov     rcx, [rsp+28h+arg_8]
0x18001ae27  mov     rdx, rsi
0x18001ae2a  call    cs:__guard_dispatch_icall_fptr
0x18001ae30  test    eax, eax
0x18001ae32  jnz     short loc_18001AE4A
0x18001ae34  call    cs:__imp_GetLastError
0x18001ae3a  movzx   ebx, ax
0x18001ae3d  or      ebx, 80070000h
0x18001ae43  test    eax, eax
0x18001ae45  cmovle  ebx, eax
0x18001ae48  jmp     short loc_18001AE4C
0x18001ae4a  xor     ebx, ebx
0x18001ae4c  cmp     [rsp+28h+arg_8], 0
0x18001ae52  jz      short loc_18001AE5E
0x18001ae54  mov     rcx, [rsp+28h+arg_8]; struct SC_HANDLE__ *
0x18001ae59  call    ?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z; CLRCloseServiceHandle(SC_HANDLE__ *)
0x18001ae5e  mov     eax, ebx
0x18001ae60  mov     rbx, [rsp+28h+arg_0]
0x18001ae65  add     rsp, 20h
0x18001ae69  pop     rsi
0x18001ae6a  retn
```
