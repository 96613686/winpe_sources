# Win32LiveSystemProvider::GetCpuPowerInfo(ulong,_PROCESSOR_POWER_INFORMATION *,ulong *)

- ea: `0x180012af0`
- end: `0x180012bc5`
- name: `?GetCpuPowerInfo@Win32LiveSystemProvider@@UEAAJKPEAU_PROCESSOR_POWER_INFORMATION@@PEAK@Z`
- size: `213`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, unsigned int, struct _PROCESSOR_POWER_INFORMATION *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180012af0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012b77`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012b77`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180012b1b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180012b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b37`

## string_xrefs

- `0x180012b12`: `powrprof.dll`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::GetCpuPowerInfo(
        Win32LiveSystemProvider *this,
        int a2,
        struct _PROCESSOR_POWER_INFORMATION *a3,
        unsigned int *a4)
{
  signed int result; // eax
  HMODULE Library; // rax
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD, struct _PROCESSOR_POWER_INFORMATION *, int); // rax
  int v11; // eax

  result = *((_DWORD *)this + 110);
  if ( result != 1 )
    goto LABEL_8;
  Library = LoadLibraryExA("powrprof.dll", 0, 0);
  *((_QWORD *)this + 56) = Library;
  if ( !Library )
  {
    if ( GetLastError() )
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
    }
    else
    {
      result = -2147467259;
    }
    *((_DWORD *)this + 110) = result;
LABEL_8:
    if ( result )
      return result;
    goto LABEL_9;
  }
  *((_QWORD *)this + 57) = GetProcAddress(Library, "CallNtPowerInformation");
  *((_DWORD *)this + 110) = 0;
LABEL_9:
  v10 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, struct _PROCESSOR_POWER_INFORMATION *, int))*((_QWORD *)this + 57);
  if ( !v10 )
    return -2147467263;
  v11 = v10(11, 0, 0, a3, 24 * a2);
  if ( v11 < 0 )
    return v11 | 0x10000000;
  *a4 = 1;
  return 0;
}

```

## disassembly

```asm
0x180012af0  push    rbx
0x180012af2  push    rbp
0x180012af3  push    rsi
0x180012af4  push    rdi
0x180012af5  sub     rsp, 38h
0x180012af9  mov     eax, [rcx+1B8h]
0x180012aff  mov     rdi, r9
0x180012b02  mov     rbp, r8
0x180012b05  mov     esi, edx
0x180012b07  mov     rbx, rcx
0x180012b0a  cmp     eax, 1
0x180012b0d  jnz     short loc_180012B56
0x180012b0f  xor     r8d, r8d; dwFlags
0x180012b12  lea     rcx, aPowrprofDll; "powrprof.dll"
0x180012b19  xor     edx, edx; hFile
0x180012b1b  call    cs:__imp_LoadLibraryExA
0x180012b21  mov     [rbx+1C0h], rax
0x180012b28  test    rax, rax
0x180012b2b  jnz     short loc_180012B6D
0x180012b2d  call    cs:__imp_GetLastError
0x180012b33  test    eax, eax
0x180012b35  jz      short loc_180012B4B
0x180012b37  call    cs:__imp_GetLastError
0x180012b3d  test    eax, eax
0x180012b3f  jle     short loc_180012B50
0x180012b41  movzx   eax, ax
0x180012b44  or      eax, 80070000h
0x180012b49  jmp     short loc_180012B50
0x180012b4b  mov     eax, 80004005h
0x180012b50  mov     [rbx+1B8h], eax
0x180012b56  test    eax, eax
0x180012b58  jnz     short loc_180012BBC
0x180012b5a  mov     rax, [rbx+1C8h]
0x180012b61  test    rax, rax
0x180012b64  jnz     short loc_180012B90
0x180012b66  mov     eax, 80004001h
0x180012b6b  jmp     short loc_180012BBC
0x180012b6d  lea     rdx, aCallntpowerinf; "CallNtPowerInformation"
0x180012b74  mov     rcx, rax; hModule
0x180012b77  call    cs:__imp_GetProcAddress
0x180012b7d  mov     [rbx+1C8h], rax
0x180012b84  mov     dword ptr [rbx+1B8h], 0
0x180012b8e  jmp     short loc_180012B5A
0x180012b90  lea     ecx, [rsi+rsi*2]
0x180012b93  xor     edx, edx
0x180012b95  shl     ecx, 3
0x180012b98  mov     r9, rbp
0x180012b9b  mov     [rsp+58h+var_38], ecx
0x180012b9f  xor     r8d, r8d
0x180012ba2  lea     ecx, [rdx+0Bh]
0x180012ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012baa  test    eax, eax
0x180012bac  jns     short loc_180012BB4
0x180012bae  bts     eax, 1Ch
0x180012bb2  jmp     short loc_180012BBC
0x180012bb4  mov     dword ptr [rdi], 1
0x180012bba  xor     eax, eax
0x180012bbc  add     rsp, 38h
0x180012bc0  pop     rdi
0x180012bc1  pop     rsi
0x180012bc2  pop     rbp
0x180012bc3  pop     rbx
0x180012bc4  retn
```
