# AIXPolicyHelper::GetIsDeviceITManaged(void)

- ea: `0x180074220`
- end: `0x1800742f9`
- name: `?GetIsDeviceITManaged@AIXPolicyHelper@@YA?AW4IsDeviceITManagedFlags@1@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180074f6c`

## callees

- `0x18002a3d0`
- `0x18002d848`
- `0x180074220`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800742bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800742bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180074290`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180074290`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180074275`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180074275`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x18007424f`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x18007424f`

## string_xrefs

- `0x180074289`: `ntdll.dll`
- `0x1800742a3`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
__int64 AIXPolicyHelper::GetIsDeviceITManaged()
{
  bool v0; // cf
  unsigned int v1; // ebx
  HMODULE ModuleHandleW; // rax
  const char *v3; // r9
  FARPROC ProcAddress; // rax
  DWORD nSize[4]; // [rsp+20h] [rbp-228h] BYREF
  WCHAR Buffer[256]; // [rsp+30h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  nSize[0] = 0;
  IsDeviceRegisteredWithManagement(nSize, 0, 0);
  v0 = nSize[0] != 0;
  nSize[0] = 256;
  v1 = v0 ? 2 : 0;
  if ( GetComputerNameExW(ComputerNamePhysicalDnsDomain, Buffer, nSize) && Buffer[0] )
    v1 |= 1u;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( !ModuleHandleW )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x143,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      v3);
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlIsFeatureEnabledForEnterprise");
  if ( !((unsigned __int8 (__fastcall *)(__int64))ProcAddress)(51549795) )
    v1 |= 4u;
  return v1;
}

```

## disassembly

```asm
0x180074220  mov     [rsp+arg_0], rbx
0x180074225  push    rdi
0x180074226  sub     rsp, 240h
0x18007422d  mov     rax, cs:__security_cookie
0x180074234  xor     rax, rsp
0x180074237  mov     [rsp+248h+var_18], rax
0x18007423f  xor     edi, edi
0x180074241  lea     rcx, [rsp+248h+nSize]
0x180074246  xor     r8d, r8d
0x180074249  mov     [rsp+248h+nSize], edi
0x18007424d  xor     edx, edx
0x18007424f  call    cs:__imp_IsDeviceRegisteredWithManagement
0x180074255  mov     eax, [rsp+248h+nSize]
0x180074259  lea     r8, [rsp+248h+nSize]; nSize
0x18007425e  neg     eax
0x180074260  mov     [rsp+248h+nSize], 100h
0x180074268  lea     rdx, [rsp+248h+Buffer]; lpBuffer
0x18007426d  sbb     ebx, ebx
0x18007426f  lea     ecx, [rdi+6]; NameType
0x180074272  and     ebx, 2
0x180074275  call    cs:__imp_GetComputerNameExW
0x18007427b  test    eax, eax
0x18007427d  jz      short loc_180074289
0x18007427f  cmp     [rsp+248h+Buffer], di
0x180074284  jz      short loc_180074289
0x180074286  or      ebx, 1
0x180074289  lea     rcx, ModuleName; "ntdll.dll"
0x180074290  call    cs:__imp_GetModuleHandleW
0x180074296  test    rax, rax
0x180074299  jnz     short loc_1800742B5
0x18007429b  mov     rcx, [rsp+248h]; this
0x1800742a3  lea     r8, aShellcommonInt_3; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x1800742aa  mov     edx, 143h; void *
0x1800742af  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800742b5  lea     rdx, aRtlisfeatureen; "RtlIsFeatureEnabledForEnterprise"
0x1800742bc  mov     rcx, rax; hModule
0x1800742bf  call    cs:__imp_GetProcAddress
0x1800742c5  mov     ecx, 3129663h
0x1800742ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742cf  test    al, al
0x1800742d1  jnz     short loc_1800742D6
0x1800742d3  or      ebx, 4
0x1800742d6  mov     eax, ebx
0x1800742d8  mov     rcx, [rsp+248h+var_18]
0x1800742e0  xor     rcx, rsp; StackCookie
0x1800742e3  call    __security_check_cookie
0x1800742e8  mov     rbx, [rsp+248h+arg_0]
0x1800742f0  add     rsp, 240h
0x1800742f7  pop     rdi
0x1800742f8  retn
```
