# XPerfCore::CComServerProxy::LoadAddIn(XPerfCore::CAddInManager *,ushort const *)

- ea: `0x18002b760`
- end: `0x18002b9bf`
- name: `?LoadAddIn@CComServerProxy@XPerfCore@@SAJPEAVCAddInManager@2@PEBG@Z`
- size: `607`
- prototype: `__int64 __fastcall(struct XPerfCore::CAddInManager *this, wchar_t *String)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005a3d0`

## callees

- `0x18002b760`
- `0x1800427c0`
- `0x18005a880`
- `0x1800d6010`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18002b917`
- `msvcrt!_wcsdup` at `0x18002b917`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b9ab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b9ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002b7af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002b7af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b806`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b806`

## string_xrefs

- `0x18002b7f7`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall XPerfCore::CComServerProxy::LoadAddIn(struct XPerfCore::CAddInManager *this, wchar_t *String)
{
  struct XPerfCore::CComServerProxy *v5; // rdi
  int v6; // ebx
  FARPROC ProcAddress; // rax
  FARPROC v8; // r15
  wchar_t *v9; // rax
  __int64 v10; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v11[7]; // [rsp+40h] [rbp-38h] BYREF
  struct XPerfCore::CComServerProxy *v12; // [rsp+90h] [rbp+18h] BYREF
  HMODULE phModule; // [rsp+98h] [rbp+20h] BYREF

  if ( !this )
    return 2147942487LL;
  phModule = 0;
  if ( !String && !GetModuleHandleExW(4u, (LPCWSTR)XPerfCore::CComServerProxy::LoadAddIn, &phModule) )
    phModule = 0;
  if ( !phModule )
    return 2147500037LL;
  v11[0] = 0;
  v5 = 0;
  v12 = 0;
  v10 = 0;
  v6 = -2147467259;
  ProcAddress = GetProcAddress(phModule, "DllGetClassObject");
  v8 = ProcAddress;
  v11[1] = ProcAddress;
  if ( ProcAddress )
  {
    v6 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
           &GUID_efbbb548_5325_4cd4_ba4e_6aa635af7528,
           &GUID_00000001_0000_0000_c000_000000000046,
           &v10);
    if ( v6 >= 0 )
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD *))(*(_QWORD *)v10 + 24LL))(
             v10,
             0,
             &GUID_907996db_eb88_4806_aeb8_bf161c0d2de2,
             v11);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v6 >= 0 )
    {
      v6 = ATL::CComObject<XPerfCore::CComServerProxy>::CreateInstance(&v12);
      v5 = v12;
      if ( v6 >= 0 )
      {
        if ( v12
          && (((*(void (__fastcall **)(struct XPerfCore::CComServerProxy *))(*(_QWORD *)v12 + 8LL))(v12),
               *((_QWORD *)v5 + 2) = phModule,
               v9 = _wcsdup(String),
               *((_QWORD *)v5 + 3) = v9,
               !String)
           || v9) )
        {
          *((_QWORD *)v5 + 4) = v8;
          *((_QWORD *)v5 + 5) = this;
          v6 = (*(__int64 (__fastcall **)(_QWORD, struct XPerfCore::CComServerProxy *))(*(_QWORD *)v11[0] + 24LL))(
                 v11[0],
                 v5);
          if ( v6 < 0 )
            XPerfCore::CAddInManager::UnregisterClassesOfProxy(this, v5);
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
  }
  if ( v11[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
  if ( v5 )
    (*(void (__fastcall **)(struct XPerfCore::CComServerProxy *))(*(_QWORD *)v5 + 16LL))(v5);
  else
    FreeLibrary(phModule);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002b760  mov     [rsp+arg_8], rdx
0x18002b765  mov     [rsp+arg_0], rcx
0x18002b76a  push    rbx
0x18002b76b  push    rsi
0x18002b76c  push    rdi
0x18002b76d  push    r14
0x18002b76f  push    r15
0x18002b771  sub     rsp, 50h
0x18002b775  mov     r14, rdx
0x18002b778  mov     rsi, rcx
0x18002b77b  test    rcx, rcx
0x18002b77e  jnz     short loc_18002B78A
0x18002b780  mov     eax, 80070057h
0x18002b785  jmp     loc_18002B9B3
0x18002b78a  mov     [rsp+78h+phModule], 0
0x18002b796  test    rdx, rdx
0x18002b799  jnz     short loc_18002B7C5
0x18002b79b  lea     r8, [rsp+78h+phModule]; phModule
0x18002b7a3  lea     rdx, ?LoadAddIn@CComServerProxy@XPerfCore@@SAJPEAVCAddInManager@2@PEBG@Z; lpModuleName
0x18002b7aa  mov     ecx, 4; dwFlags
0x18002b7af  call    cs:__imp_GetModuleHandleExW
0x18002b7b5  test    eax, eax
0x18002b7b7  jnz     short loc_18002B7C5
0x18002b7b9  mov     [rsp+78h+phModule], 0
0x18002b7c5  cmp     [rsp+78h+phModule], 0
0x18002b7ce  jnz     short loc_18002B7DA
0x18002b7d0  mov     eax, 80004005h
0x18002b7d5  jmp     loc_18002B9B3
0x18002b7da  mov     [rsp+78h+var_38], 0
0x18002b7e3  xor     edi, edi
0x18002b7e5  mov     [rsp+78h+arg_10], rdi
0x18002b7ed  mov     [rsp+78h+var_40], rdi
0x18002b7f2  mov     ebx, 80004005h
0x18002b7f7  lea     rdx, ProcName; "DllGetClassObject"
0x18002b7fe  mov     rcx, [rsp+78h+phModule]; hModule
0x18002b806  call    cs:__imp_GetProcAddress
0x18002b80c  mov     r15, rax
0x18002b80f  mov     [rsp+78h+var_30], rax
0x18002b814  test    rax, rax
0x18002b817  jz      loc_18002B977
0x18002b81d  lea     r8, [rsp+78h+var_40]
0x18002b822  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x18002b829  lea     rcx, _GUID_efbbb548_5325_4cd4_ba4e_6aa635af7528
0x18002b830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b835  mov     ebx, eax
0x18002b837  mov     [rsp+78h+var_48], eax
0x18002b83b  test    eax, eax
0x18002b83d  js      short loc_18002B864
0x18002b83f  mov     rcx, [rsp+78h+var_40]
0x18002b844  mov     rax, [rcx]
0x18002b847  lea     r9, [rsp+78h+var_38]
0x18002b84c  lea     r8, _GUID_907996db_eb88_4806_aeb8_bf161c0d2de2
0x18002b853  xor     edx, edx
0x18002b855  mov     rax, [rax+18h]
0x18002b859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b85e  mov     ebx, eax
0x18002b860  mov     [rsp+78h+var_48], eax
0x18002b864  jmp     short loc_18002B88C
0x18002b866  mov     ebx, 80004005h
0x18002b86b  mov     [rsp+78h+var_48], ebx
0x18002b86f  mov     r14, [rsp+78h+arg_8]
0x18002b877  mov     rsi, [rsp+78h+arg_0]
0x18002b87f  mov     rdi, [rsp+78h+arg_10]
0x18002b887  mov     r15, [rsp+78h+var_30]
0x18002b88c  mov     rcx, [rsp+78h+var_40]
0x18002b891  test    rcx, rcx
0x18002b894  jz      short loc_18002B8C6
0x18002b896  mov     rax, [rcx]
0x18002b899  mov     rax, [rax+10h]
0x18002b89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8a2  jmp     short loc_18002B8C6
0x18002b8a4  mov     ebx, 80004005h
0x18002b8a9  mov     r14, [rsp+78h+arg_8]
0x18002b8b1  mov     rsi, [rsp+78h+arg_0]
0x18002b8b9  mov     rdi, [rsp+78h+arg_10]
0x18002b8c1  mov     r15, [rsp+78h+var_30]
0x18002b8c6  test    ebx, ebx
0x18002b8c8  js      loc_18002B977
0x18002b8ce  lea     rcx, [rsp+78h+arg_10]
0x18002b8d6  call    ?CreateInstance@?$CComObject@VCComServerProxy@XPerfCore@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<XPerfCore::CComServerProxy>::CreateInstance(ATL::CComObject<XPerfCore::CComServerProxy> * *)
0x18002b8db  mov     ebx, eax
0x18002b8dd  mov     rdi, [rsp+78h+arg_10]
0x18002b8e5  test    eax, eax
0x18002b8e7  js      loc_18002B977
0x18002b8ed  test    rdi, rdi
0x18002b8f0  jnz     short loc_18002B8F9
0x18002b8f2  mov     ebx, 8007000Eh
0x18002b8f7  jmp     short loc_18002B977
0x18002b8f9  mov     rax, [rdi]
0x18002b8fc  mov     rcx, rdi
0x18002b8ff  mov     rax, [rax+8]
0x18002b903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b908  mov     rax, [rsp+78h+phModule]
0x18002b910  mov     [rdi+10h], rax
0x18002b914  mov     rcx, r14; String
0x18002b917  call    cs:__imp__wcsdup
0x18002b91d  mov     [rdi+18h], rax
0x18002b921  test    r14, r14
0x18002b924  jz      short loc_18002B92B
0x18002b926  test    rax, rax
0x18002b929  jz      short loc_18002B8F2
0x18002b92b  mov     [rdi+20h], r15
0x18002b92f  mov     [rdi+28h], rsi
0x18002b933  mov     rcx, [rsp+78h+var_38]
0x18002b938  mov     rax, [rcx]
0x18002b93b  mov     rdx, rdi
0x18002b93e  mov     rax, [rax+18h]
0x18002b942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b947  mov     ebx, eax
0x18002b949  mov     [rsp+78h+var_48], eax
0x18002b94d  jmp     short loc_18002B968
0x18002b94f  mov     ebx, 80004005h
0x18002b954  mov     [rsp+78h+var_48], ebx
0x18002b958  mov     rsi, [rsp+78h+arg_0]
0x18002b960  mov     rdi, [rsp+78h+arg_10]
0x18002b968  test    ebx, ebx
0x18002b96a  jns     short loc_18002B977
0x18002b96c  mov     rdx, rdi; struct XPerfCore::CComServerProxy *
0x18002b96f  mov     rcx, rsi; this
0x18002b972  call    ?UnregisterClassesOfProxy@CAddInManager@XPerfCore@@QEAAJPEAVCComServerProxy@2@@Z; XPerfCore::CAddInManager::UnregisterClassesOfProxy(XPerfCore::CComServerProxy *)
0x18002b977  mov     rcx, [rsp+78h+var_38]
0x18002b97c  test    rcx, rcx
0x18002b97f  jz      short loc_18002B98D
0x18002b981  mov     rax, [rcx]
0x18002b984  mov     rax, [rax+10h]
0x18002b988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b98d  test    rdi, rdi
0x18002b990  jz      short loc_18002B9A3
0x18002b992  mov     rax, [rdi]
0x18002b995  mov     rcx, rdi
0x18002b998  mov     rax, [rax+10h]
0x18002b99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9a1  jmp     short loc_18002B9B1
0x18002b9a3  mov     rcx, [rsp+78h+phModule]; hLibModule
0x18002b9ab  call    cs:__imp_FreeLibrary
0x18002b9b1  mov     eax, ebx
0x18002b9b3  add     rsp, 50h
0x18002b9b7  pop     r15
0x18002b9b9  pop     r14
0x18002b9bb  pop     rdi
0x18002b9bc  pop     rsi
0x18002b9bd  pop     rbx
0x18002b9be  retn
```
