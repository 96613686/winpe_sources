# PopupUnenrollmentUI(ushort *)

- ea: `0x18003ba2c`
- end: `0x18003bbd5`
- name: `?PopupUnenrollmentUI@@YAJPEAG@Z`
- size: `425`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013830`

## callees

- `0x1800026d0`
- `0x18003b9f0`
- `0x18003ba2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003bb99`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003bb99`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003babf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003bb06`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003babf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003bb06`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ba72`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ba72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bacf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bacf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb37`
- `DMCmnUtils!DmRaiseToastNotification` at `0x18003bb88`
- `DMCmnUtils!DmRaiseToastNotification` at `0x18003bb88`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003bba5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003bba5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003ba4f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003ba4f`

## string_xrefs

- `0x18003bb63`: `protocol`
- `0x18003ba65`: `Windows.Internal.Management.dll`

## pseudocode

```c
HRESULT __fastcall PopupUnenrollmentUI(unsigned __int16 *a1)
{
  HRESULT result; // eax
  HMODULE Library; // rax
  HMODULE v3; // rbx
  signed int v4; // eax
  signed int v5; // edi
  signed int v6; // eax
  signed int LastError; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-648h] BYREF
  WCHAR v9[264]; // [rsp+240h] [rbp-438h] BYREF
  unsigned __int16 v10[264]; // [rsp+450h] [rbp-228h] BYREF

  result = CoInitializeEx(0, 0);
  if ( result >= 0 )
  {
    Library = LoadLibraryExW(L"Windows.Internal.Management.dll", 0, 0x800u);
    v3 = Library;
    if ( Library )
    {
      if ( LoadStringW(Library, 0x66u, Buffer, 260) && LoadStringW(v3, 0x67u, v9, 260) )
      {
        if ( (unsigned int)_snwprintf_s<260>(v10, 260, v9, Buffer) )
          goto LABEL_13;
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 >= 0 )
LABEL_13:
          v5 = DmRaiseToastNotification(
                 L"Windows.SystemToast.DeviceEnrollmentActivity",
                 L"DeviceEnrollment",
                 L"ms-settings:workplace",
                 L"protocol",
                 0,
                 v10);
      }
      else
      {
        v6 = GetLastError();
        v5 = v6;
        if ( v6 > 0 )
          v5 = (unsigned __int16)v6 | 0x80070000;
      }
      FreeLibrary(v3);
    }
    else
    {
      v4 = GetLastError();
      v5 = v4;
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
    }
    CoUninitialize();
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18003ba2c  mov     [rsp+arg_0], rbx
0x18003ba31  push    rdi
0x18003ba32  sub     rsp, 670h
0x18003ba39  mov     rax, cs:__security_cookie
0x18003ba40  xor     rax, rsp
0x18003ba43  mov     [rsp+678h+var_18], rax
0x18003ba4b  xor     edx, edx; dwCoInit
0x18003ba4d  xor     ecx, ecx; pvReserved
0x18003ba4f  call    cs:__imp_CoInitializeEx
0x18003ba56  nop     dword ptr [rax+rax+00h]
0x18003ba5b  test    eax, eax
0x18003ba5d  js      loc_18003BBB3
0x18003ba63  xor     edx, edx; hFile
0x18003ba65  lea     rcx, aWindowsInterna; "Windows.Internal.Management.dll"
0x18003ba6c  mov     r8d, 800h; dwFlags
0x18003ba72  call    cs:__imp_LoadLibraryExW
0x18003ba79  nop     dword ptr [rax+rax+00h]
0x18003ba7e  mov     rbx, rax
0x18003ba81  test    rax, rax
0x18003ba84  jnz     short loc_18003BAAA
0x18003ba86  call    cs:__imp_GetLastError
0x18003ba8d  nop     dword ptr [rax+rax+00h]
0x18003ba92  mov     edi, eax
0x18003ba94  test    eax, eax
0x18003ba96  jle     loc_18003BBA5
0x18003ba9c  movzx   edi, ax
0x18003ba9f  or      edi, 80070000h
0x18003baa5  jmp     loc_18003BBA5
0x18003baaa  mov     edi, 104h
0x18003baaf  lea     r8, [rsp+678h+Buffer]; lpBuffer
0x18003bab4  mov     r9d, edi; cchBufferMax
0x18003bab7  mov     edx, 66h ; 'f'; uID
0x18003babc  mov     rcx, rbx; hInstance
0x18003babf  call    cs:__imp_LoadStringW
0x18003bac6  nop     dword ptr [rax+rax+00h]
0x18003bacb  test    eax, eax
0x18003bacd  jnz     short loc_18003BAF3
0x18003bacf  call    cs:__imp_GetLastError
0x18003bad6  nop     dword ptr [rax+rax+00h]
0x18003badb  mov     edi, eax
0x18003badd  test    eax, eax
0x18003badf  jle     loc_18003BB96
0x18003bae5  movzx   edi, ax
0x18003bae8  or      edi, 80070000h
0x18003baee  jmp     loc_18003BB96
0x18003baf3  mov     r9d, edi; cchBufferMax
0x18003baf6  lea     r8, [rsp+678h+var_438]; lpBuffer
0x18003bafe  mov     edx, 67h ; 'g'; uID
0x18003bb03  mov     rcx, rbx; hInstance
0x18003bb06  call    cs:__imp_LoadStringW
0x18003bb0d  nop     dword ptr [rax+rax+00h]
0x18003bb12  test    eax, eax
0x18003bb14  jz      short loc_18003BACF
0x18003bb16  lea     r9, [rsp+678h+Buffer]
0x18003bb1b  mov     rdx, rdi
0x18003bb1e  lea     r8, [rsp+678h+var_438]
0x18003bb26  lea     rcx, [rsp+678h+var_228]
0x18003bb2e  call    ??$_snwprintf_s@$0BAE@@@YAHAEAY0BAE@G_KPEBGZZ; _snwprintf_s<260>(ushort (&)[260],unsigned __int64,ushort const *,...)
0x18003bb33  test    eax, eax
0x18003bb35  jnz     short loc_18003BB56
0x18003bb37  call    cs:__imp_GetLastError
0x18003bb3e  nop     dword ptr [rax+rax+00h]
0x18003bb43  mov     edi, eax
0x18003bb45  test    eax, eax
0x18003bb47  jle     short loc_18003BB52
0x18003bb49  movzx   edi, ax
0x18003bb4c  or      edi, 80070000h
0x18003bb52  test    edi, edi
0x18003bb54  js      short loc_18003BB96
0x18003bb56  lea     rax, [rsp+678h+var_228]
0x18003bb5e  mov     [rsp+678h+var_650], rax
0x18003bb63  lea     r9, aProtocol; "protocol"
0x18003bb6a  lea     r8, aMsSettingsWork; "ms-settings:workplace"
0x18003bb71  mov     [rsp+678h+var_658], 0
0x18003bb7a  lea     rdx, aDeviceenrollme; "DeviceEnrollment"
0x18003bb81  lea     rcx, aWindowsSystemt; "Windows.SystemToast.DeviceEnrollmentAct"...
0x18003bb88  call    cs:__imp_?DmRaiseToastNotification@@YAJPEBG00000@Z; DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18003bb8f  nop     dword ptr [rax+rax+00h]
0x18003bb94  mov     edi, eax
0x18003bb96  mov     rcx, rbx; hLibModule
0x18003bb99  call    cs:__imp_FreeLibrary
0x18003bba0  nop     dword ptr [rax+rax+00h]
0x18003bba5  call    cs:__imp_CoUninitialize
0x18003bbac  nop     dword ptr [rax+rax+00h]
0x18003bbb1  mov     eax, edi
0x18003bbb3  mov     rcx, [rsp+678h+var_18]
0x18003bbbb  xor     rcx, rsp; StackCookie
0x18003bbbe  call    __security_check_cookie
0x18003bbc3  mov     rbx, [rsp+678h+arg_0]
0x18003bbcb  add     rsp, 670h
0x18003bbd2  pop     rdi
0x18003bbd3  retn
```
