# NGENService::ServiceUninstall(void)

- ea: `0x18001bc48`
- end: `0x18001bcfc`
- name: `?ServiceUninstall@NGENService@@YAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(NGENService *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800084f0`
- `0x18001b9d0`

## callees

- `0x180007914`
- `0x18001a690`
- `0x18001bc48`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001bc84`
- `KERNEL32!LoadLibraryExW` at `0x18001bc84`
- `KERNEL32!GetLastError` at `0x18001bcca`
- `KERNEL32!GetLastError` at `0x18001bcca`
- `KERNEL32!GetProcAddress` at `0x18001bc99`
- `KERNEL32!GetProcAddress` at `0x18001bc99`

## string_xrefs

- `0x18001bc7b`: `advapi32.dll`
- `0x18001bc8f`: `DeleteService`

## pseudocode

```c
__int64 __fastcall NGENService::ServiceUninstall(NGENService *this, struct SC_HANDLE__ **a2)
{
  signed int v2; // ebx
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  signed int LastError; // eax
  struct SC_HANDLE__ *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = 0;
  v2 = NGENService::OpenNGENService((NGENService *)&v7, a2);
  if ( v2 >= 0 )
  {
    ProcAddress = (FARPROC)qword_18006FEF8;
    if ( (qword_18006FEF8
       || !bDeleteServiceProbed
       && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
         ? (ProcAddress = (FARPROC)qword_18006FEF8)
         : (FARPROC)(ProcAddress = GetProcAddress(Library, "DeleteService"), qword_18006FEF8 = (__int64)ProcAddress),
           bDeleteServiceProbed = 1,
           ProcAddress))
      && ((unsigned int (__fastcall *)(struct SC_HANDLE__ *))ProcAddress)(v7) )
    {
      v2 = 0;
    }
    else
    {
      LastError = GetLastError();
      v2 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v2 = LastError;
    }
  }
  if ( v7 )
    CLRCloseServiceHandle(v7);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001bc48  push    rbx
0x18001bc4a  sub     rsp, 20h
0x18001bc4e  and     [rsp+28h+arg_0], 0
0x18001bc54  lea     rcx, [rsp+28h+arg_0]; this
0x18001bc59  call    ?OpenNGENService@NGENService@@YAJPEAPEAUSC_HANDLE__@@@Z; NGENService::OpenNGENService(SC_HANDLE__ * *)
0x18001bc5e  mov     ebx, eax
0x18001bc60  test    eax, eax
0x18001bc62  js      short loc_18001BCE2
0x18001bc64  mov     rax, cs:qword_18006FEF8
0x18001bc6b  test    rax, rax
0x18001bc6e  jnz     short loc_18001BCBB
0x18001bc70  cmp     cs:?bDeleteServiceProbed@@3_NA, al; bool bDeleteServiceProbed
0x18001bc76  jnz     short loc_18001BCCA
0x18001bc78  xor     r8d, r8d; dwFlags
0x18001bc7b  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18001bc82  xor     edx, edx; hFile
0x18001bc84  call    cs:__imp_LoadLibraryExW
0x18001bc8a  test    rax, rax
0x18001bc8d  jz      short loc_18001BCA8
0x18001bc8f  lea     rdx, aDeleteservice; "DeleteService"
0x18001bc96  mov     rcx, rax; hModule
0x18001bc99  call    cs:__imp_GetProcAddress
0x18001bc9f  mov     cs:qword_18006FEF8, rax
0x18001bca6  jmp     short loc_18001BCAF
0x18001bca8  mov     rax, cs:qword_18006FEF8
0x18001bcaf  mov     cs:?bDeleteServiceProbed@@3_NA, 1; bool bDeleteServiceProbed
0x18001bcb6  test    rax, rax
0x18001bcb9  jz      short loc_18001BCCA
0x18001bcbb  mov     rcx, [rsp+28h+arg_0]
0x18001bcc0  call    cs:__guard_dispatch_icall_fptr
0x18001bcc6  test    eax, eax
0x18001bcc8  jnz     short loc_18001BCE0
0x18001bcca  call    cs:__imp_GetLastError
0x18001bcd0  movzx   ebx, ax
0x18001bcd3  or      ebx, 80070000h
0x18001bcd9  test    eax, eax
0x18001bcdb  cmovle  ebx, eax
0x18001bcde  jmp     short loc_18001BCE2
0x18001bce0  xor     ebx, ebx
0x18001bce2  cmp     [rsp+28h+arg_0], 0
0x18001bce8  jz      short loc_18001BCF4
0x18001bcea  mov     rcx, [rsp+28h+arg_0]; struct SC_HANDLE__ *
0x18001bcef  call    ?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z; CLRCloseServiceHandle(SC_HANDLE__ *)
0x18001bcf4  mov     eax, ebx
0x18001bcf6  add     rsp, 20h
0x18001bcfa  pop     rbx
0x18001bcfb  retn
```
