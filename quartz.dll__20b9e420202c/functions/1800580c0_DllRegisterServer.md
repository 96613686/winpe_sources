# DllRegisterServer

- ea: `0x1800580c0`
- end: `0x1800582a5`
- name: `DllRegisterServer`
- size: `485`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800388a0`
- `0x180057d30`
- `0x180057f28`
- `0x1800580c0`
- `0x180058c94`
- `0x180058f3c`
- `0x180059124`
- `0x1800595dc`
- `0x18015e010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180058215`
- `KERNEL32!MultiByteToWideChar` at `0x180058215`
- `KERNEL32!GetModuleFileNameA` at `0x1800581ef`
- `KERNEL32!GetModuleFileNameA` at `0x1800581ef`
- `ADVAPI32!RegCreateKeyW` at `0x180058184`
- `ADVAPI32!RegCreateKeyW` at `0x180058184`
- `ADVAPI32!RegCloseKey` at `0x1800581bd`
- `ADVAPI32!RegCloseKey` at `0x1800581bd`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180058233`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180058233`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x18005824f`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x18005824f`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const struct _GUID *v0; // rdx
  const unsigned __int16 *v1; // rcx
  HRESULT v2; // ebx
  __int64 v3; // r8
  const struct _GUID *v4; // rsi
  unsigned int v5; // r14d
  unsigned int v6; // edi
  const struct _GUID *v7; // rcx
  const struct _GUID *v8; // rdx
  int v9; // eax
  unsigned int v10; // edi
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  CHAR Filename[272]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+150h] [rbp+50h] BYREF

  v2 = AMovieDllRegisterServer2(1u);
  if ( v2 >= 0 )
    v2 = RegisterExtension(v1, v0);
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( v2 >= 0 )
  {
    do
    {
      if ( v6 >= 0x11 )
        break;
      v7 = v4;
      v8 = (const struct _GUID *)*((_QWORD *)&off_18016AD70 + 2 * (int)v6);
      if ( v4 != v8 )
        v4 = (const struct _GUID *)*((_QWORD *)&off_18016AD70 + 2 * (int)v6);
      ++v5;
      if ( v7 != v8 )
        v5 = 0;
      v9 = SetMediaTypeFile(v7, v8, v3, (&off_18016AD78)[2 * (int)v6++], v5);
      v2 = v9;
    }
    while ( v9 >= 0 );
  }
  v10 = 0;
  if ( v2 >= 0 )
  {
    do
    {
      if ( v10 >= 5 )
        break;
      phkResult = 0;
      if ( RegCreateKeyW(HKEY_CLASSES_ROOT, off_18016AE80[v10], &phkResult) )
      {
        v2 = 0;
      }
      else
      {
        v2 = (unsigned int)WriteGUID(phkResult, L"Source Filter", &CLSID_URLReader) == 0 ? 0x80070005 : 0;
        RegCloseKey(phkResult);
      }
      ++v10;
    }
    while ( v2 >= 0 );
    if ( v2 >= 0 )
    {
      GetModuleFileNameA(g_hInst, Filename, 0x104u);
      MultiByteToWideChar(0, 0, Filename, -1, WideCharStr, 260);
      pptlib = 0;
      if ( LoadTypeLib(WideCharStr, &pptlib) >= 0 )
      {
        RegisterTypeLib(pptlib, WideCharStr, 0);
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        RemoveMCIWrapFilter();
        return SetupFilterRegistration();
      }
    }
  }
  RemoveMCIWrapFilter();
  if ( v2 >= 0 )
    return SetupFilterRegistration();
  return v2;
}

```

## disassembly

```asm
0x1800580c0  push    rbp
0x1800580c2  push    rbx
0x1800580c3  push    rsi
0x1800580c4  push    rdi
0x1800580c5  push    r14
0x1800580c7  push    r15
0x1800580c9  lea     rbp, [rsp-278h]
0x1800580d1  sub     rsp, 378h
0x1800580d8  mov     rax, cs:__security_cookie
0x1800580df  xor     rax, rsp
0x1800580e2  mov     [rbp+2A0h+var_40], rax
0x1800580e9  mov     ecx, 1
0x1800580ee  call    AMovieDllRegisterServer2
0x1800580f3  mov     ebx, eax
0x1800580f5  test    eax, eax
0x1800580f7  js      short loc_180058100
0x1800580f9  call    ?RegisterExtension@@YAJPEBGPEBU_GUID@@@Z; RegisterExtension(ushort const *,_GUID const *)
0x1800580fe  mov     ebx, eax
0x180058100  xor     esi, esi
0x180058102  lea     r15, __ImageBase
0x180058109  xor     r14d, r14d
0x18005810c  xor     edi, edi
0x18005810e  test    ebx, ebx
0x180058110  js      short loc_180058155
0x180058112  cmp     edi, 11h
0x180058115  jnb     short loc_180058155
0x180058117  mov     rcx, rsi
0x18005811a  movsxd  r9, edi
0x18005811d  add     r9, r9
0x180058120  mov     rdx, ds:rva off_18016AD70[r15+r9*8]
0x180058128  mov     r9, ds:rva off_18016AD78[r15+r9*8]; "0, 16, FFFFFFFFF100010001800001FFFFFFFF"... ...
0x180058130  cmp     rsi, rdx
0x180058133  cmovnz  rsi, rdx
0x180058137  xor     eax, eax
0x180058139  inc     r14d
0x18005813c  cmp     rcx, rdx
0x18005813f  cmovnz  r14d, eax
0x180058143  mov     dword ptr [rsp+3A0h+lpWideCharStr], r14d
0x180058148  call    SetMediaTypeFile
0x18005814d  inc     edi
0x18005814f  mov     ebx, eax
0x180058151  test    eax, eax
0x180058153  jns     short loc_180058112
0x180058155  xor     edi, edi
0x180058157  test    ebx, ebx
0x180058159  js      loc_180058273
0x18005815f  cmp     edi, 5
0x180058162  jnb     short loc_1800581D3
0x180058164  movsxd  rdx, edi
0x180058167  lea     r8, [rsp+3A0h+phkResult]; phkResult
0x18005816c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180058173  mov     [rsp+3A0h+phkResult], 0
0x18005817c  mov     rdx, ds:rva off_18016AE80[r15+rdx*8]; lpSubKey
0x180058184  call    cs:__imp_RegCreateKeyW
0x18005818b  nop     dword ptr [rax+rax+00h]
0x180058190  test    eax, eax
0x180058192  jnz     short loc_1800581CB
0x180058194  mov     rcx, [rsp+3A0h+phkResult]; hKey
0x180058199  lea     r8, CLSID_URLReader; rguid
0x1800581a0  lea     rdx, aSourceFilter; "Source Filter"
0x1800581a7  call    ?WriteGUID@@YAHPEAUHKEY__@@PEBGPEBU_GUID@@@Z; WriteGUID(HKEY__ *,ushort const *,_GUID const *)
0x1800581ac  mov     rcx, [rsp+3A0h+phkResult]; hKey
0x1800581b1  neg     eax
0x1800581b3  sbb     ebx, ebx
0x1800581b5  not     ebx
0x1800581b7  and     ebx, 80070005h
0x1800581bd  call    cs:__imp_RegCloseKey
0x1800581c4  nop     dword ptr [rax+rax+00h]
0x1800581c9  jmp     short loc_1800581CD
0x1800581cb  xor     ebx, ebx
0x1800581cd  inc     edi
0x1800581cf  test    ebx, ebx
0x1800581d1  jns     short loc_18005815F
0x1800581d3  test    ebx, ebx
0x1800581d5  js      loc_180058273
0x1800581db  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x1800581e2  lea     rdx, [rsp+3A0h+Filename]; lpFilename
0x1800581e7  mov     edi, 104h
0x1800581ec  mov     r8d, edi; nSize
0x1800581ef  call    cs:__imp_GetModuleFileNameA
0x1800581f6  nop     dword ptr [rax+rax+00h]
0x1800581fb  lea     rax, [rbp+2A0h+WideCharStr]
0x1800581ff  mov     [rsp+3A0h+cchWideChar], edi; cchWideChar
0x180058203  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180058207  mov     [rsp+3A0h+lpWideCharStr], rax; lpWideCharStr
0x18005820c  lea     r8, [rsp+3A0h+Filename]; lpMultiByteStr
0x180058211  xor     edx, edx; dwFlags
0x180058213  xor     ecx, ecx; CodePage
0x180058215  call    cs:__imp_MultiByteToWideChar
0x18005821c  nop     dword ptr [rax+rax+00h]
0x180058221  lea     rdx, [rsp+3A0h+pptlib]; pptlib
0x180058226  mov     [rsp+3A0h+pptlib], 0
0x18005822f  lea     rcx, [rbp+2A0h+WideCharStr]; szFile
0x180058233  call    cs:__imp_LoadTypeLib
0x18005823a  nop     dword ptr [rax+rax+00h]
0x18005823f  test    eax, eax
0x180058241  js      short loc_180058273
0x180058243  mov     rcx, [rsp+3A0h+pptlib]; ptlib
0x180058248  lea     rdx, [rbp+2A0h+WideCharStr]; szFullPath
0x18005824c  xor     r8d, r8d; szHelpDir
0x18005824f  call    cs:__imp_RegisterTypeLib
0x180058256  nop     dword ptr [rax+rax+00h]
0x18005825b  mov     rcx, [rsp+3A0h+pptlib]
0x180058260  mov     rax, [rcx]
0x180058263  mov     rax, [rax+10h]
0x180058267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005826c  call    RemoveMCIWrapFilter
0x180058271  jmp     short loc_18005827C
0x180058273  call    RemoveMCIWrapFilter
0x180058278  test    ebx, ebx
0x18005827a  js      short loc_180058283
0x18005827c  call    ?SetupFilterRegistration@@YAJXZ; SetupFilterRegistration(void)
0x180058281  mov     ebx, eax
0x180058283  mov     eax, ebx
0x180058285  mov     rcx, [rbp+2A0h+var_40]
0x18005828c  xor     rcx, rsp; StackCookie
0x18005828f  call    __security_check_cookie
0x180058294  add     rsp, 378h
0x18005829b  pop     r15
0x18005829d  pop     r14
0x18005829f  pop     rdi
0x1800582a0  pop     rsi
0x1800582a1  pop     rbx
0x1800582a2  pop     rbp
0x1800582a3  retn
```
