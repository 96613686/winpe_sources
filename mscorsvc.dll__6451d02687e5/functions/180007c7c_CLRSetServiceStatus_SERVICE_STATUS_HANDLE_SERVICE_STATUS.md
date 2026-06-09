# CLRSetServiceStatus(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)

- ea: `0x180007c7c`
- end: `0x180007d02`
- name: `?CLRSetServiceStatus@@YAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(struct SERVICE_STATUS_HANDLE__ *, struct _SERVICE_STATUS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001a790`

## callees

- `0x180007c7c`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007cb0`
- `KERNEL32!LoadLibraryExW` at `0x180007cb0`
- `KERNEL32!GetProcAddress` at `0x180007cc5`
- `KERNEL32!GetProcAddress` at `0x180007cc5`

## string_xrefs

- `0x180007ca7`: `advapi32.dll`
- `0x180007cbb`: `SetServiceStatus`

## pseudocode

```c
__int64 __fastcall CLRSetServiceStatus(struct SERVICE_STATUS_HANDLE__ *a1, struct _SERVICE_STATUS *a2)
{
  FARPROC ProcAddress; // rax
  struct SERVICE_STATUS_HANDLE__ *v4; // rdi
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF40;
  v4 = NGENService::g_hServiceStatusHandle;
  if ( qword_18006FF40 )
    return ((__int64 (__fastcall *)(struct SERVICE_STATUS_HANDLE__ *, struct _SERVICE_STATUS *))ProcAddress)(v4, a2);
  if ( !bSetServiceStatusProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF40)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "SetServiceStatus"), qword_18006FF40 = (__int64)ProcAddress),
        bSetServiceStatusProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(struct SERVICE_STATUS_HANDLE__ *, struct _SERVICE_STATUS *))ProcAddress)(v4, a2);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007c7c  mov     [rsp+arg_0], rbx
0x180007c81  push    rdi
0x180007c82  sub     rsp, 20h
0x180007c86  mov     rax, cs:qword_18006FF40
0x180007c8d  mov     rbx, rdx
0x180007c90  mov     rdi, cs:?g_hServiceStatusHandle@NGENService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * NGENService::g_hServiceStatusHandle
0x180007c97  test    rax, rax
0x180007c9a  jnz     short loc_180007CEB
0x180007c9c  cmp     cs:?bSetServiceStatusProbed@@3_NA, al; bool bSetServiceStatusProbed
0x180007ca2  jnz     short loc_180007CE7
0x180007ca4  xor     r8d, r8d; dwFlags
0x180007ca7  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180007cae  xor     edx, edx; hFile
0x180007cb0  call    cs:__imp_LoadLibraryExW
0x180007cb6  test    rax, rax
0x180007cb9  jz      short loc_180007CD4
0x180007cbb  lea     rdx, aSetservicestat_0; "SetServiceStatus"
0x180007cc2  mov     rcx, rax; hModule
0x180007cc5  call    cs:__imp_GetProcAddress
0x180007ccb  mov     cs:qword_18006FF40, rax
0x180007cd2  jmp     short loc_180007CDB
0x180007cd4  mov     rax, cs:qword_18006FF40
0x180007cdb  mov     cs:?bSetServiceStatusProbed@@3_NA, 1; bool bSetServiceStatusProbed
0x180007ce2  test    rax, rax
0x180007ce5  jnz     short loc_180007CEB
0x180007ce7  xor     eax, eax
0x180007ce9  jmp     short loc_180007CF7
0x180007ceb  mov     rdx, rbx
0x180007cee  mov     rcx, rdi
0x180007cf1  call    cs:__guard_dispatch_icall_fptr
0x180007cf7  mov     rbx, [rsp+28h+arg_0]
0x180007cfc  add     rsp, 20h
0x180007d00  pop     rdi
0x180007d01  retn
```
