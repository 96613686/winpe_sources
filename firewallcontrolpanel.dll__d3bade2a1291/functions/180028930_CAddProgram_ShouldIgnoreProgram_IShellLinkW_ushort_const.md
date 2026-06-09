# CAddProgram::ShouldIgnoreProgram(IShellLinkW *,ushort const *)

- ea: `0x180028930`
- end: `0x180028a69`
- name: `?ShouldIgnoreProgram@CAddProgram@@AEAAHPEAUIShellLinkW@@PEBG@Z`
- size: `313`
- prototype: `int(CAddProgram *__hidden this, struct IShellLinkW *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180027438`

## callees

- `0x180028930`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002896e`
- `msvcrt!_wcsicmp` at `0x180028a1f`
- `msvcrt!_wcsicmp` at `0x18002896e`
- `msvcrt!_wcsicmp` at `0x180028a1f`
- `SHLWAPI!PathFindExtensionW` at `0x180028955`
- `SHLWAPI!PathFindExtensionW` at `0x180028a0a`
- `SHLWAPI!PathFindExtensionW` at `0x180028955`
- `SHLWAPI!PathFindExtensionW` at `0x180028a0a`
- `msi!__imp_MsiGetProductInfoW` at `0x1800289fb`
- `msi!__imp_MsiGetProductInfoW` at `0x1800289fb`

## pseudocode

```c
__int64 __fastcall CAddProgram::ShouldIgnoreProgram(
        CAddProgram *this,
        struct IShellLinkW *a2,
        const unsigned __int16 *a3)
{
  const wchar_t *ExtensionW; // rax
  struct IShellLinkWVtbl *lpVtbl; // rax
  unsigned int v6; // ebx
  const wchar_t *v7; // rax
  DWORD pcchValueBuf; // [rsp+20h] [rbp-248h] BYREF
  __int64 v10; // [rsp+28h] [rbp-240h] BYREF
  __int64 v11; // [rsp+30h] [rbp-238h] BYREF
  WCHAR ValueBuf[264]; // [rsp+40h] [rbp-228h] BYREF

  ExtensionW = PathFindExtensionW(a3);
  if ( !ExtensionW || _wcsicmp(ExtensionW, L".exe") )
  {
    return 1;
  }
  else
  {
    lpVtbl = a2->lpVtbl;
    v11 = 0;
    v10 = 0;
    v6 = 0;
    if ( ((__int64 (__fastcall *)(struct IShellLinkW *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a2,
           &IID_IShellLinkDataList,
           &v10) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v10 + 32LL))(v10, 2684354566LL, &v11) >= 0 )
      {
        if ( v11 )
        {
          pcchValueBuf = 260;
          if ( !MsiGetProductInfoW((LPCWSTR)(v11 + 268), L"ProductName", ValueBuf, &pcchValueBuf) )
          {
            v7 = PathFindExtensionW(ValueBuf);
            if ( !v7 || _wcsicmp(v7, L".exe") )
              v6 = 1;
          }
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180028930  mov     [rsp+arg_0], rbx
0x180028935  push    rdi
0x180028936  sub     rsp, 260h
0x18002893d  mov     rax, cs:__security_cookie
0x180028944  xor     rax, rsp
0x180028947  mov     [rsp+268h+var_18], rax
0x18002894f  mov     rcx, r8; pszPath
0x180028952  mov     rdi, rdx
0x180028955  call    cs:__imp_PathFindExtensionW
0x18002895b  test    rax, rax
0x18002895e  jz      loc_180028A41
0x180028964  lea     rdx, aExe; ".exe"
0x18002896b  mov     rcx, rax; String1
0x18002896e  call    cs:__imp__wcsicmp
0x180028974  test    eax, eax
0x180028976  jnz     loc_180028A41
0x18002897c  mov     rax, [rdi]
0x18002897f  lea     r8, [rsp+268h+var_240]
0x180028984  lea     rdx, IID_IShellLinkDataList
0x18002898b  mov     [rsp+268h+var_238], 0
0x180028994  mov     rcx, rdi
0x180028997  mov     [rsp+268h+var_240], 0
0x1800289a0  xor     ebx, ebx
0x1800289a2  mov     rax, [rax]
0x1800289a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289aa  test    eax, eax
0x1800289ac  js      loc_180028A46
0x1800289b2  mov     rcx, [rsp+268h+var_240]
0x1800289b7  lea     r8, [rsp+268h+var_238]
0x1800289bc  mov     edx, 0A0000006h
0x1800289c1  mov     rax, [rcx]
0x1800289c4  mov     rax, [rax+20h]
0x1800289c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289cd  test    eax, eax
0x1800289cf  js      short loc_180028A2E
0x1800289d1  mov     rcx, [rsp+268h+var_238]
0x1800289d6  test    rcx, rcx
0x1800289d9  jz      short loc_180028A2E
0x1800289db  add     rcx, 10Ch; szProduct
0x1800289e2  mov     [rsp+268h+pcchValueBuf], 104h
0x1800289ea  lea     r9, [rsp+268h+pcchValueBuf]; pcchValueBuf
0x1800289ef  lea     r8, [rsp+268h+ValueBuf]; lpValueBuf
0x1800289f4  lea     rdx, szAttribute; "ProductName"
0x1800289fb  call    cs:__imp_MsiGetProductInfoW
0x180028a01  test    eax, eax
0x180028a03  jnz     short loc_180028A2E
0x180028a05  lea     rcx, [rsp+268h+ValueBuf]; pszPath
0x180028a0a  call    cs:__imp_PathFindExtensionW
0x180028a10  test    rax, rax
0x180028a13  jz      short loc_180028A29
0x180028a15  lea     rdx, aExe; ".exe"
0x180028a1c  mov     rcx, rax; String1
0x180028a1f  call    cs:__imp__wcsicmp
0x180028a25  test    eax, eax
0x180028a27  jz      short loc_180028A2E
0x180028a29  mov     ebx, 1
0x180028a2e  mov     rcx, [rsp+268h+var_240]
0x180028a33  mov     rax, [rcx]
0x180028a36  mov     rax, [rax+10h]
0x180028a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a3f  jmp     short loc_180028A46
0x180028a41  mov     ebx, 1
0x180028a46  mov     eax, ebx
0x180028a48  mov     rcx, [rsp+268h+var_18]
0x180028a50  xor     rcx, rsp; StackCookie
0x180028a53  call    __security_check_cookie
0x180028a58  mov     rbx, [rsp+268h+arg_0]
0x180028a60  add     rsp, 260h
0x180028a67  pop     rdi
0x180028a68  retn
```
