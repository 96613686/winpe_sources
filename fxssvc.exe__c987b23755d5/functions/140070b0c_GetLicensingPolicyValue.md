# GetLicensingPolicyValue

- ea: `0x140070b0c`
- end: `0x140070ca0`
- name: `GetLicensingPolicyValue`
- size: `404`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000f700`
- `0x140024994`
- `0x140070a64`
- `0x140070e74`
- `0x140070f1c`

## callees

- `0x140004b30`
- `0x140066544`
- `0x140070b0c`
- `0x140070ca8`
- `0x140081872`
- `0x140085010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140070bde`
- `KERNEL32!FreeLibrary` at `0x140070bde`
- `KERNEL32!GetLastError` at `0x140070b97`
- `KERNEL32!GetLastError` at `0x140070b97`
- `KERNEL32!LoadLibraryW` at `0x140070b74`
- `KERNEL32!LoadLibraryW` at `0x140070b74`
- `KERNEL32!GetProcAddress` at `0x140070b8c`
- `KERNEL32!GetProcAddress` at `0x140070b8c`

## string_xrefs

- `0x140070c1d`: `Microsoft-Windows-Fax-Common-EnableServerPolicy`
- `0x140070c3e`: `Microsoft-Windows-Fax-Common-DeviceLimit`
- `0x140070b6d`: `slc.dll`

## pseudocode

```c
__int64 __fastcall GetLicensingPolicyValue(wchar_t *String1, int *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  DWORD LastError; // edi
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
    v6 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        LastError = ((__int64 (__fastcall *)(wchar_t *, int *))ProcAddress)(String1, a2);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
        }
      }
      FreeLibrary(v6);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
      }
      return 1157;
    }
    return LastError;
  }
  LastError = 0;
  if ( wcscmp_0(String1, L"Microsoft-Windows-Fax-Common-EnableServerPolicy") )
  {
    if ( wcscmp_0(String1, L"Microsoft-Windows-Fax-Common-DeviceLimit") )
      return LastError;
    v9 = 0;
    v10 = GetProductSKU() - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 2;
        if ( !v12 )
          goto LABEL_36;
        v13 = v12 - 4;
        if ( !v13 || (v14 = v13 - 8) == 0 )
        {
          v9 = -1;
          goto LABEL_33;
        }
        v15 = v14 - 16;
        if ( !v15 )
          goto LABEL_32;
        v16 = v15 - 32;
        if ( !v16 )
        {
LABEL_36:
          v9 = 4;
          goto LABEL_33;
        }
        if ( v16 != 64 )
        {
LABEL_33:
          *a2 = v9;
          return LastError;
        }
      }
    }
LABEL_32:
    v9 = 1;
    goto LABEL_33;
  }
  *a2 = GetProductSKU() & 0x5C;
  return LastError;
}

```

## disassembly

```asm
0x140070b0c  push    rbx
0x140070b0e  push    rbp
0x140070b0f  push    rsi
0x140070b10  push    rdi
0x140070b11  push    r15
0x140070b13  sub     rsp, 20h
0x140070b17  mov     rsi, rdx
0x140070b1a  mov     rbp, rcx
0x140070b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140070b24  lea     r15, WPP_GLOBAL_Control
0x140070b2b  cmp     rcx, r15
0x140070b2e  jz      short loc_140070B51
0x140070b30  test    byte ptr [rcx+1Ch], 2
0x140070b34  jz      short loc_140070B51
0x140070b36  cmp     byte ptr [rcx+19h], 5
0x140070b3a  jb      short loc_140070B51
0x140070b3c  mov     rcx, [rcx+10h]
0x140070b40  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x140070b47  mov     edx, 1Ch
0x140070b4c  call    WPP_SF_
0x140070b51  test    rsi, rsi
0x140070b54  jnz     short loc_140070B60
0x140070b56  mov     eax, 80070057h
0x140070b5b  jmp     loc_140070C89
0x140070b60  call    LonghornOrMore
0x140070b65  test    eax, eax
0x140070b67  jz      loc_140070C1D
0x140070b6d  lea     rcx, LibFileName; "slc.dll"
0x140070b74  call    cs:__imp_LoadLibraryW
0x140070b7a  mov     rbx, rax
0x140070b7d  test    rax, rax
0x140070b80  jz      short loc_140070BE9
0x140070b82  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x140070b89  mov     rcx, rax; hModule
0x140070b8c  call    cs:__imp_GetProcAddress
0x140070b92  test    rax, rax
0x140070b95  jnz     short loc_140070BCE
0x140070b97  call    cs:__imp_GetLastError
0x140070b9d  mov     edi, eax
0x140070b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140070ba6  cmp     rcx, r15
0x140070ba9  jz      short loc_140070BDB
0x140070bab  test    byte ptr [rcx+1Ch], 2
0x140070baf  jz      short loc_140070BDB
0x140070bb1  cmp     byte ptr [rcx+19h], 2
0x140070bb5  jb      short loc_140070BDB
0x140070bb7  mov     rcx, [rcx+10h]
0x140070bbb  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x140070bc2  mov     edx, 1Dh
0x140070bc7  call    WPP_SF_
0x140070bcc  jmp     short loc_140070BDB
0x140070bce  mov     rdx, rsi
0x140070bd1  mov     rcx, rbp
0x140070bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070bd9  mov     edi, eax
0x140070bdb  mov     rcx, rbx; hLibModule
0x140070bde  call    cs:__imp_FreeLibrary
0x140070be4  jmp     loc_140070C87
0x140070be9  mov     rcx, cs:WPP_GLOBAL_Control
0x140070bf0  cmp     rcx, r15
0x140070bf3  jz      short loc_140070C16
0x140070bf5  test    byte ptr [rcx+1Ch], 2
0x140070bf9  jz      short loc_140070C16
0x140070bfb  cmp     byte ptr [rcx+19h], 2
0x140070bff  jb      short loc_140070C16
0x140070c01  mov     rcx, [rcx+10h]
0x140070c05  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x140070c0c  mov     edx, 1Eh
0x140070c11  call    WPP_SF_
0x140070c16  mov     edi, 485h
0x140070c1b  jmp     short loc_140070C87
0x140070c1d  lea     rdx, aMicrosoftWindo; "Microsoft-Windows-Fax-Common-EnableServ"...
0x140070c24  mov     rcx, rbp; String1
0x140070c27  xor     edi, edi
0x140070c29  call    wcscmp_0
0x140070c2e  test    eax, eax
0x140070c30  jnz     short loc_140070C3E
0x140070c32  call    GetProductSKU
0x140070c37  and     eax, 5Ch
0x140070c3a  mov     [rsi], eax
0x140070c3c  jmp     short loc_140070C87
0x140070c3e  lea     rdx, aMicrosoftWindo_1; "Microsoft-Windows-Fax-Common-DeviceLimi"...
0x140070c45  mov     rcx, rbp; String1
0x140070c48  call    wcscmp_0
0x140070c4d  test    eax, eax
0x140070c4f  jnz     short loc_140070C87
0x140070c51  xor     ebx, ebx
0x140070c53  call    GetProductSKU
0x140070c58  sub     eax, 1
0x140070c5b  jz      short loc_140070C80
0x140070c5d  sub     eax, 1
0x140070c60  jz      short loc_140070C80
0x140070c62  sub     eax, 2
0x140070c65  jz      short loc_140070C99
0x140070c67  sub     eax, 4
0x140070c6a  jz      short loc_140070C94
0x140070c6c  sub     eax, 8
0x140070c6f  jz      short loc_140070C94
0x140070c71  sub     eax, 10h
0x140070c74  jz      short loc_140070C80
0x140070c76  sub     eax, 20h ; ' '
0x140070c79  jz      short loc_140070C99
0x140070c7b  cmp     eax, 40h ; '@'
0x140070c7e  jnz     short loc_140070C85
0x140070c80  mov     ebx, 1
0x140070c85  mov     [rsi], ebx
0x140070c87  mov     eax, edi
0x140070c89  add     rsp, 20h
0x140070c8d  pop     r15
0x140070c8f  pop     rdi
0x140070c90  pop     rsi
0x140070c91  pop     rbp
0x140070c92  pop     rbx
0x140070c93  retn
0x140070c94  or      ebx, 0FFFFFFFFh
0x140070c97  jmp     short loc_140070C85
0x140070c99  mov     ebx, 4
0x140070c9e  jmp     short loc_140070C85
```
