# NotifyDeviceNeedsReboot(void *,_SP_DEVINFO_DATA *)

- ea: `0x18000b710`
- end: `0x18000b861`
- name: `?NotifyDeviceNeedsReboot@@YAJPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b868`

## callees

- `0x1800037c4`
- `0x18000b710`
- `0x18000c008`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b76c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b76c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b801`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b73e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b73e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b828`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b836`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b828`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b836`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000b7c0`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000b7c0`

## string_xrefs

- `0x18000b737`: `pnpui.dll`

## pseudocode

```c
__int64 __fastcall NotifyDeviceNeedsReboot(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)
{
  HMODULE ModuleHandleW; // rbx
  unsigned __int16 *v5; // rsi
  signed int v6; // eax
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // r9
  unsigned __int16 *v11; // rdi
  signed int LastError; // eax
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-248h] BYREF
  DWORD RequiredSize[3]; // [rsp+44h] [rbp-244h] BYREF
  BYTE PropertyBuffer[528]; // [rsp+50h] [rbp-238h] BYREF

  PropertyType = 1;
  RequiredSize[0] = 0;
  ModuleHandleW = GetModuleHandleW(L"pnpui.dll");
  v5 = ShellConstructMessageString(ModuleHandleW, (const unsigned __int16 *)0x25B);
  if ( v5 )
  {
    if ( SetupDiGetDevicePropertyW(
           DeviceInfoSet,
           DeviceInfoData,
           &DEVPKEY_NAME,
           &PropertyType,
           PropertyBuffer,
           0x208u,
           RequiredSize,
           0)
      && PropertyType == 18
      && RequiredSize[0] > 2 )
    {
      v8 = ShellConstructMessageString(ModuleHandleW, (const unsigned __int16 *)0x25C, PropertyBuffer);
    }
    else
    {
      v8 = ShellConstructMessageString(ModuleHandleW, (const unsigned __int16 *)0x25D);
    }
    v11 = (unsigned __int16 *)v8;
    if ( v8 )
    {
      v7 = ShowNotifyToast(v5, v8, v9, v10);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    LocalFree(v5);
    if ( v11 )
      LocalFree(v11);
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x18000b710  mov     [rsp+arg_10], rbx
0x18000b715  push    rbp
0x18000b716  push    rsi
0x18000b717  push    rdi
0x18000b718  sub     rsp, 270h
0x18000b71f  mov     rax, cs:__security_cookie
0x18000b726  xor     rax, rsp
0x18000b729  mov     [rsp+288h+var_28], rax
0x18000b731  mov     rdi, rcx
0x18000b734  mov     rbp, rdx
0x18000b737  lea     rcx, ModuleName; "pnpui.dll"
0x18000b73e  call    cs:__imp_GetModuleHandleW
0x18000b744  mov     edx, 25Bh; unsigned __int16 *
0x18000b749  mov     [rsp+288h+PropertyType], 1
0x18000b751  mov     rcx, rax; HINSTANCE
0x18000b754  mov     [rsp+288h+var_244], 0
0x18000b75c  mov     rbx, rax
0x18000b75f  call    ?ShellConstructMessageString@@YAPEAGPEAUHINSTANCE__@@PEBGZZ; ShellConstructMessageString(HINSTANCE__ *,ushort const *,...)
0x18000b764  mov     rsi, rax
0x18000b767  test    rax, rax
0x18000b76a  jnz     short loc_18000B78A
0x18000b76c  call    cs:__imp_GetLastError
0x18000b772  mov     ebx, eax
0x18000b774  test    eax, eax
0x18000b776  jle     loc_18000B83C
0x18000b77c  movzx   ebx, ax
0x18000b77f  or      ebx, 80070000h
0x18000b785  jmp     loc_18000B83C
0x18000b78a  mov     [rsp+288h+Flags], 0; Flags
0x18000b792  lea     rax, [rsp+288h+var_244]
0x18000b797  mov     [rsp+288h+RequiredSize], rax; RequiredSize
0x18000b79c  lea     r9, [rsp+288h+PropertyType]; PropertyType
0x18000b7a1  lea     rax, [rsp+288h+var_238]
0x18000b7a6  mov     [rsp+288h+PropertyBufferSize], 208h; unsigned __int16 *
0x18000b7ae  lea     r8, DEVPKEY_NAME; PropertyKey
0x18000b7b5  mov     [rsp+288h+PropertyBuffer], rax; unsigned __int16 *
0x18000b7ba  mov     rdx, rbp; DeviceInfoData
0x18000b7bd  mov     rcx, rdi; DeviceInfoSet
0x18000b7c0  call    cs:__imp_SetupDiGetDevicePropertyW
0x18000b7c6  test    eax, eax
0x18000b7c8  jz      short loc_18000B7EC
0x18000b7ca  cmp     [rsp+288h+PropertyType], 12h
0x18000b7cf  jnz     short loc_18000B7EC
0x18000b7d1  cmp     [rsp+288h+var_244], 2
0x18000b7d6  jbe     short loc_18000B7EC
0x18000b7d8  lea     r8, [rsp+288h+var_238]
0x18000b7dd  mov     edx, 25Ch; unsigned __int16 *
0x18000b7e2  mov     rcx, rbx; HINSTANCE
0x18000b7e5  call    ?ShellConstructMessageString@@YAPEAGPEAUHINSTANCE__@@PEBGZZ; ShellConstructMessageString(HINSTANCE__ *,ushort const *,...)
0x18000b7ea  jmp     short loc_18000B7F9
0x18000b7ec  mov     edx, 25Dh; unsigned __int16 *
0x18000b7f1  mov     rcx, rbx; HINSTANCE
0x18000b7f4  call    ?ShellConstructMessageString@@YAPEAGPEAUHINSTANCE__@@PEBGZZ; ShellConstructMessageString(HINSTANCE__ *,ushort const *,...)
0x18000b7f9  mov     rdi, rax
0x18000b7fc  test    rax, rax
0x18000b7ff  jnz     short loc_18000B818
0x18000b801  call    cs:__imp_GetLastError
0x18000b807  mov     ebx, eax
0x18000b809  test    eax, eax
0x18000b80b  jle     short loc_18000B825
0x18000b80d  movzx   ebx, ax
0x18000b810  or      ebx, 80070000h
0x18000b816  jmp     short loc_18000B825
0x18000b818  mov     rdx, rdi; unsigned __int16 *
0x18000b81b  mov     rcx, rsi; unsigned __int16 *
0x18000b81e  call    ?ShowNotifyToast@@YAJPEBG00000@Z; ShowNotifyToast(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000b823  mov     ebx, eax
0x18000b825  mov     rcx, rsi; hMem
0x18000b828  call    cs:__imp_LocalFree
0x18000b82e  test    rdi, rdi
0x18000b831  jz      short loc_18000B83C
0x18000b833  mov     rcx, rdi; hMem
0x18000b836  call    cs:__imp_LocalFree
0x18000b83c  mov     eax, ebx
0x18000b83e  mov     rcx, [rsp+288h+var_28]
0x18000b846  xor     rcx, rsp; StackCookie
0x18000b849  call    __security_check_cookie
0x18000b84e  mov     rbx, [rsp+288h+arg_10]
0x18000b856  add     rsp, 270h
0x18000b85d  pop     rdi
0x18000b85e  pop     rsi
0x18000b85f  pop     rbp
0x18000b860  retn
```
