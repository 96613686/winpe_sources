# CreateWicImagingFactory(IWICImagingFactory * *)

- ea: `0x1800a5dbc`
- end: `0x1800a5ec6`
- name: `?CreateWicImagingFactory@@YAJPEAPEAUIWICImagingFactory@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(struct IWICImagingFactory **)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a5d00`
- `0x1800a5d30`
- `0x1800a5d60`
- `0x1800a5d90`
- `0x18014e8f0`
- `0x18014e960`

## callees

- `0x1800a5dbc`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5e9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5e9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a5e70`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a5e70`

## string_xrefs

- `0x1800a5e67`: `WindowsCodecs.dll`
- `0x1800a5e94`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall CreateWicImagingFactory(struct IWICImagingFactory **a1)
{
  __int64 (__fastcall *v2)(GUID *, GUID *, __int64 *); // rax
  unsigned int v3; // ebx
  HMODULE v5; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  if ( a1 )
  {
    *a1 = 0;
    v2 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))qword_1801B3D38;
    if ( !qword_1801B3D38 )
    {
      v5 = hModule;
      if ( hModule )
        goto LABEL_14;
      Library = LoadLibraryExW(L"WindowsCodecs.dll", 0, 0);
      if ( Library )
        _InterlockedExchange64((volatile __int64 *)&hModule, (__int64)Library);
      v5 = hModule;
      if ( hModule )
      {
LABEL_14:
        ProcAddress = GetProcAddress(v5, "DllGetClassObject");
        if ( ProcAddress )
          _InterlockedExchange64(&qword_1801B3D38, (__int64)ProcAddress);
      }
      v2 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))qword_1801B3D38;
    }
    v3 = -2147467259;
    if ( !v2 )
      return v3;
    v8 = 0;
    v3 = v2(&CLSID_WICImagingFactory2, &IID_IClassFactory, &v8);
    if ( (v3 & 0x80000000) == 0 )
    {
      if ( !v8 )
        return v3;
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IWICImagingFactory **))(*(_QWORD *)v8 + 24LL))(
             v8,
             0,
             &IID_IWICImagingFactory,
             a1);
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    return v3;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800a5dbc  mov     [rsp+arg_8], rbx
0x1800a5dc1  push    rdi
0x1800a5dc2  sub     rsp, 30h
0x1800a5dc6  mov     rdi, rcx
0x1800a5dc9  test    rcx, rcx
0x1800a5dcc  jz      loc_1800A5EBF
0x1800a5dd2  and     qword ptr [rcx], 0
0x1800a5dd6  mov     rax, cs:qword_1801B3D38
0x1800a5ddd  test    rax, rax
0x1800a5de0  jz      short loc_1800A5E58
0x1800a5de2  mov     ebx, 80004005h
0x1800a5de7  test    rax, rax
0x1800a5dea  jz      short loc_1800A5E4A
0x1800a5dec  and     [rsp+38h+arg_0], 0
0x1800a5df2  lea     r8, [rsp+38h+arg_0]
0x1800a5df7  lea     rdx, IID_IClassFactory
0x1800a5dfe  lea     rcx, CLSID_WICImagingFactory2
0x1800a5e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5e0a  mov     ebx, eax
0x1800a5e0c  test    eax, eax
0x1800a5e0e  js      short loc_1800A5E34
0x1800a5e10  mov     rcx, [rsp+38h+arg_0]
0x1800a5e15  test    rcx, rcx
0x1800a5e18  jz      short loc_1800A5E4A
0x1800a5e1a  mov     rax, [rcx]
0x1800a5e1d  lea     r8, IID_IWICImagingFactory
0x1800a5e24  mov     r9, rdi
0x1800a5e27  xor     edx, edx
0x1800a5e29  mov     rax, [rax+18h]
0x1800a5e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5e32  mov     ebx, eax
0x1800a5e34  mov     rcx, [rsp+38h+arg_0]
0x1800a5e39  test    rcx, rcx
0x1800a5e3c  jz      short loc_1800A5E4A
0x1800a5e3e  mov     rax, [rcx]
0x1800a5e41  mov     rax, [rax+10h]
0x1800a5e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5e4a  mov     eax, ebx
0x1800a5e4c  mov     rbx, [rsp+38h+arg_8]
0x1800a5e51  add     rsp, 30h
0x1800a5e55  pop     rdi
0x1800a5e56  retn
0x1800a5e58  mov     rcx, cs:hModule
0x1800a5e5f  test    rcx, rcx
0x1800a5e62  jnz     short loc_1800A5E94
0x1800a5e64  xor     r8d, r8d; dwFlags
0x1800a5e67  lea     rcx, aWindowscodecsD; "WindowsCodecs.dll"
0x1800a5e6e  xor     edx, edx; hFile
0x1800a5e70  call    cs:__imp_LoadLibraryExW
0x1800a5e77  nop     dword ptr [rax+rax+00h]
0x1800a5e7c  test    rax, rax
0x1800a5e7f  jz      short loc_1800A5E88
0x1800a5e81  xchg    rax, cs:hModule
0x1800a5e88  mov     rcx, cs:hModule; hModule
0x1800a5e8f  test    rcx, rcx
0x1800a5e92  jz      short loc_1800A5EB3
0x1800a5e94  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x1800a5e9b  call    cs:__imp_GetProcAddress
0x1800a5ea2  nop     dword ptr [rax+rax+00h]
0x1800a5ea7  test    rax, rax
0x1800a5eaa  jz      short loc_1800A5EB3
0x1800a5eac  xchg    rax, cs:qword_1801B3D38
0x1800a5eb3  mov     rax, cs:qword_1801B3D38
0x1800a5eba  jmp     loc_1800A5DE2
0x1800a5ebf  mov     eax, 80070057h
0x1800a5ec4  jmp     short loc_1800A5E4C
```
