# IsSKUDirectAccessEnabled

- ea: `0x1800a51b4`
- end: `0x1800a52fc`
- name: `IsSKUDirectAccessEnabled`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180018278`

## callees

- `0x18008b5f0`
- `0x1800a51b4`
- `0x1800dc9e0`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a521b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a521b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a52a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a52a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5241`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5241`

## string_xrefs

- `0x1800a520e`: `slc.dll`

## pseudocode

```c
bool IsSKUDirectAccessEnabled()
{
  bool v0; // bl
  _BOOL8 v1; // r9
  __int64 v2; // rdx
  FARPROC ProcAddress; // rax
  unsigned int v4; // eax
  int v6; // [rsp+20h] [rbp-18h] BYREF

  v6 = 0;
  if ( dword_180112538 == -1 )
  {
    v0 = 0;
    if ( hLibModule || (hLibModule = LoadLibraryExW(L"slc.dll", 0, 0x800u)) != 0 )
    {
      ProcAddress = GetProcAddress(hLibModule, "SLGetWindowsInformationDWORD");
      if ( ProcAddress )
      {
        v4 = ((__int64 (__fastcall *)(const wchar_t *, int *))ProcAddress)(L"DNS-Client-license-DAPolicy", &v6);
        if ( v4 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_d(1035, 11, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, v4);
        }
        else if ( v6 )
        {
          v0 = 1;
        }
      }
    }
    dword_180112538 = v0;
    if ( hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      v2 = 12;
      v1 = v0;
      goto LABEL_16;
    }
  }
  else
  {
    v0 = dword_180112538 != 0;
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      v1 = v0;
      v2 = 10;
LABEL_16:
      WPP_SF_d(1035, v2, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, v1);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800a51b4  mov     [rsp+arg_0], rbx
0x1800a51b9  push    rdi
0x1800a51ba  sub     rsp, 30h
0x1800a51be  mov     rax, cs:__security_cookie
0x1800a51c5  xor     rax, rsp
0x1800a51c8  mov     [rsp+38h+var_10], rax
0x1800a51cd  mov     eax, cs:dword_180112538
0x1800a51d3  mov     [rsp+38h+var_18], 0
0x1800a51db  cmp     eax, 0FFFFFFFFh
0x1800a51de  jz      short loc_1800A5200
0x1800a51e0  test    eax, eax
0x1800a51e2  setnz   bl
0x1800a51e5  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a51ec  jz      loc_1800A52E1
0x1800a51f2  movzx   r9d, bl
0x1800a51f6  mov     edx, 0Ah
0x1800a51fb  jmp     loc_1800A52D0
0x1800a5200  xor     bl, bl
0x1800a5202  cmp     cs:hLibModule, 0
0x1800a520a  jnz     short loc_1800A5233
0x1800a520c  xor     edx, edx; hFile
0x1800a520e  lea     rcx, aSlcDll; "slc.dll"
0x1800a5215  mov     r8d, 800h; dwFlags
0x1800a521b  call    cs:__imp_LoadLibraryExW
0x1800a5222  nop     dword ptr [rax+rax+00h]
0x1800a5227  mov     cs:hLibModule, rax
0x1800a522e  test    rax, rax
0x1800a5231  jz      short loc_1800A5293
0x1800a5233  mov     rcx, cs:hLibModule; hModule
0x1800a523a  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x1800a5241  call    cs:__imp_GetProcAddress
0x1800a5248  nop     dword ptr [rax+rax+00h]
0x1800a524d  test    rax, rax
0x1800a5250  jz      short loc_1800A5293
0x1800a5252  lea     rdx, [rsp+38h+var_18]
0x1800a5257  lea     rcx, aDnsClientLicen; "DNS-Client-license-DAPolicy"
0x1800a525e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5263  test    eax, eax
0x1800a5265  jnz     short loc_1800A5271
0x1800a5267  cmp     [rsp+38h+var_18], eax
0x1800a526b  jz      short loc_1800A5293
0x1800a526d  mov     bl, 1
0x1800a526f  jmp     short loc_1800A5293
0x1800a5271  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a5278  jz      short loc_1800A5293
0x1800a527a  mov     edx, 0Bh
0x1800a527f  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x1800a5286  mov     ecx, 40Bh
0x1800a528b  mov     r9d, eax
0x1800a528e  call    WPP_SF_d
0x1800a5293  mov     rcx, cs:hLibModule; hLibModule
0x1800a529a  movzx   edi, bl
0x1800a529d  mov     cs:dword_180112538, edi
0x1800a52a3  test    rcx, rcx
0x1800a52a6  jz      short loc_1800A52BF
0x1800a52a8  call    cs:__imp_FreeLibrary
0x1800a52af  nop     dword ptr [rax+rax+00h]
0x1800a52b4  mov     cs:hLibModule, 0
0x1800a52bf  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a52c6  jz      short loc_1800A52E1
0x1800a52c8  mov     edx, 0Ch
0x1800a52cd  mov     r9d, edi
0x1800a52d0  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x1800a52d7  mov     ecx, 40Bh
0x1800a52dc  call    WPP_SF_d
0x1800a52e1  mov     al, bl
0x1800a52e3  mov     rcx, [rsp+38h+var_10]
0x1800a52e8  xor     rcx, rsp; StackCookie
0x1800a52eb  call    __security_check_cookie
0x1800a52f0  mov     rbx, [rsp+38h+arg_0]
0x1800a52f5  add     rsp, 30h
0x1800a52f9  pop     rdi
0x1800a52fa  retn
```
