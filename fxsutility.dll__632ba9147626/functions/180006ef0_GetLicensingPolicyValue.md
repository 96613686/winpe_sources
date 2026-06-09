# GetLicensingPolicyValue

- ea: `0x180006ef0`
- end: `0x180007016`
- name: `GetLicensingPolicyValue`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800071e8`

## callees

- `0x180005eac`
- `0x180006ef0`
- `0x18000701c`
- `0x180007288`
- `0x180017010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180006fc2`
- `KERNEL32!FreeLibrary` at `0x180006fc2`
- `KERNEL32!GetProcAddress` at `0x180006f6c`
- `KERNEL32!GetProcAddress` at `0x180006f6c`
- `KERNEL32!GetLastError` at `0x180006f77`
- `KERNEL32!GetLastError` at `0x180006f77`
- `KERNEL32!LoadLibraryW` at `0x180006f54`
- `KERNEL32!LoadLibraryW` at `0x180006f54`

## string_xrefs

- `0x180006fb1`: `Microsoft-Windows-Fax-Common-EnableServerPolicy`
- `0x180006f4d`: `slc.dll`

## pseudocode

```c
__int64 __fastcall GetLicensingPolicyValue(__int64 a1, _DWORD *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rsi
  FARPROC ProcAddress; // rax
  DWORD LastError; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
  }
  if ( !a2 )
    return 2147942487LL;
  if ( (unsigned int)LonghornOrMore() )
  {
    LibraryW = LoadLibraryW(L"slc.dll");
    v5 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        LastError = ((__int64 (__fastcall *)(const wchar_t *, _DWORD *))ProcAddress)(
                      L"Microsoft-Windows-Fax-Common-EnableServerPolicy",
                      a2);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
        }
      }
      FreeLibrary(v5);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
      }
      return 1157;
    }
  }
  else
  {
    LastError = 0;
    *a2 = GetProductSKU() & 0x5C;
  }
  return LastError;
}

```

## disassembly

```asm
0x180006ef0  push    rbx
0x180006ef2  push    rsi
0x180006ef3  push    rdi
0x180006ef4  push    r14
0x180006ef6  sub     rsp, 28h
0x180006efa  mov     rdi, rdx
0x180006efd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f04  lea     r14, WPP_GLOBAL_Control
0x180006f0b  cmp     rcx, r14
0x180006f0e  jz      short loc_180006F31
0x180006f10  test    byte ptr [rcx+1Ch], 2
0x180006f14  jz      short loc_180006F31
0x180006f16  cmp     byte ptr [rcx+19h], 5
0x180006f1a  jb      short loc_180006F31
0x180006f1c  mov     rcx, [rcx+10h]
0x180006f20  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x180006f27  mov     edx, 1Ch
0x180006f2c  call    WPP_SF_
0x180006f31  test    rdi, rdi
0x180006f34  jnz     short loc_180006F40
0x180006f36  mov     eax, 80070057h
0x180006f3b  jmp     loc_18000700C
0x180006f40  call    LonghornOrMore
0x180006f45  test    eax, eax
0x180006f47  jz      loc_180006FFE
0x180006f4d  lea     rcx, aSlcDll; "slc.dll"
0x180006f54  call    cs:__imp_LoadLibraryW
0x180006f5a  mov     rsi, rax
0x180006f5d  test    rax, rax
0x180006f60  jz      short loc_180006FCA
0x180006f62  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x180006f69  mov     rcx, rax; hModule
0x180006f6c  call    cs:__imp_GetProcAddress
0x180006f72  test    rax, rax
0x180006f75  jnz     short loc_180006FAE
0x180006f77  call    cs:__imp_GetLastError
0x180006f7d  mov     ebx, eax
0x180006f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f86  cmp     rcx, r14
0x180006f89  jz      short loc_180006FBF
0x180006f8b  test    byte ptr [rcx+1Ch], 2
0x180006f8f  jz      short loc_180006FBF
0x180006f91  cmp     byte ptr [rcx+19h], 2
0x180006f95  jb      short loc_180006FBF
0x180006f97  mov     rcx, [rcx+10h]
0x180006f9b  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x180006fa2  mov     edx, 1Dh
0x180006fa7  call    WPP_SF_
0x180006fac  jmp     short loc_180006FBF
0x180006fae  mov     rdx, rdi
0x180006fb1  lea     rcx, aMicrosoftWindo; "Microsoft-Windows-Fax-Common-EnableServ"...
0x180006fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fbd  mov     ebx, eax
0x180006fbf  mov     rcx, rsi; hLibModule
0x180006fc2  call    cs:__imp_FreeLibrary
0x180006fc8  jmp     short loc_18000700A
0x180006fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fd1  cmp     rcx, r14
0x180006fd4  jz      short loc_180006FF7
0x180006fd6  test    byte ptr [rcx+1Ch], 2
0x180006fda  jz      short loc_180006FF7
0x180006fdc  cmp     byte ptr [rcx+19h], 2
0x180006fe0  jb      short loc_180006FF7
0x180006fe2  mov     rcx, [rcx+10h]
0x180006fe6  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x180006fed  mov     edx, 1Eh
0x180006ff2  call    WPP_SF_
0x180006ff7  mov     ebx, 485h
0x180006ffc  jmp     short loc_18000700A
0x180006ffe  xor     ebx, ebx
0x180007000  call    GetProductSKU
0x180007005  and     eax, 5Ch
0x180007008  mov     [rdi], eax
0x18000700a  mov     eax, ebx
0x18000700c  add     rsp, 28h
0x180007010  pop     r14
0x180007012  pop     rdi
0x180007013  pop     rsi
0x180007014  pop     rbx
0x180007015  retn
```
