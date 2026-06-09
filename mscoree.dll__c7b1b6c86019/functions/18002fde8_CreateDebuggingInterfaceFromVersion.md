# CreateDebuggingInterfaceFromVersion

- ea: `0x18002fde8`
- end: `0x18002ff1b`
- name: `CreateDebuggingInterfaceFromVersion`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800240f0`

## callees

- `0x180002710`
- `0x18002a7c8`
- `0x18002f88c`
- `0x18002fde8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002fe49`
- `KERNEL32!GetProcAddress` at `0x18002fe6e`
- `KERNEL32!GetProcAddress` at `0x18002fe49`
- `KERNEL32!GetProcAddress` at `0x18002fe6e`
- `KERNEL32!FreeLibrary` at `0x18002fef6`
- `KERNEL32!FreeLibrary` at `0x18002fef6`

## string_xrefs

- `0x18002fe67`: `DllGetClassObjectInternal`
- `0x18002fe29`: `mscordbi.dll`
- `0x18002fe42`: `CreateCordbObject`

## pseudocode

```c
__int64 __fastcall CreateDebuggingInterfaceFromVersion(int a1, wchar_t *a2, _QWORD *a3)
{
  FARPROC ProcAddress; // rax
  int LastError; // eax
  int (*v7)(const struct _GUID *, const struct _GUID *, void **); // rax
  int (*v8)(const struct _GUID *, const struct _GUID *, void **); // rbp
  int LegacyCorDebug; // ebx
  void *v10; // rcx
  void *v12; // [rsp+48h] [rbp+10h] BYREF
  HMODULE hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  v12 = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    if ( (int)LoadLibraryShim_0((wchar_t *)L"mscordbi.dll", a2, (__int64)a3, &hModule) >= 0 )
    {
      ProcAddress = GetProcAddress(hModule, "CreateCordbObject");
      if ( ProcAddress )
      {
        LastError = ((__int64 (__fastcall *)(_QWORD, void **))ProcAddress)((unsigned int)a1, &v12);
        goto LABEL_8;
      }
      v7 = (int (*)(const struct _GUID *, const struct _GUID *, void **))GetProcAddress(
                                                                           hModule,
                                                                           "DllGetClassObjectInternal");
      v8 = v7;
      if ( !v7 )
      {
        LastError = HRESULT_FROM_GetLastError();
LABEL_8:
        LegacyCorDebug = LastError;
        if ( LastError >= 0 )
          goto LABEL_19;
        goto LABEL_15;
      }
      if ( a1 >= 3 )
      {
        LegacyCorDebug = GetLegacyCorDebug(v7, &stru_1800504F8, &v12);
        if ( LegacyCorDebug >= 0 )
          goto LABEL_19;
      }
      if ( a1 >= 1 )
      {
        LegacyCorDebug = GetLegacyCorDebug(v8, &stru_180050508, &v12);
        if ( LegacyCorDebug >= 0 )
          goto LABEL_19;
      }
    }
    LegacyCorDebug = -2147024809;
LABEL_15:
    v10 = v12;
    if ( v12 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      v10 = 0;
      v12 = 0;
    }
    if ( !hModule )
      goto LABEL_20;
    FreeLibrary(hModule);
LABEL_19:
    v10 = v12;
LABEL_20:
    *a3 = v10;
    return (unsigned int)LegacyCorDebug;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002fde8  mov     rax, rsp
0x18002fdeb  mov     [rax+8], rbx
0x18002fdef  push    rbp
0x18002fdf0  push    rsi
0x18002fdf1  push    r14
0x18002fdf3  sub     rsp, 20h
0x18002fdf7  mov     qword ptr [rax+20h], 0
0x18002fdff  mov     r14, r8
0x18002fe02  mov     qword ptr [rax+10h], 0
0x18002fe0a  mov     esi, ecx
0x18002fe0c  test    rdx, rdx
0x18002fe0f  jz      loc_18002FF08
0x18002fe15  test    r8, r8
0x18002fe18  jz      loc_18002FF08
0x18002fe1e  lea     r9, [rax+20h]
0x18002fe22  mov     qword ptr [r8], 0
0x18002fe29  lea     rcx, aMscordbiDll; "mscordbi.dll"
0x18002fe30  call    LoadLibraryShim_0
0x18002fe35  test    eax, eax
0x18002fe37  js      loc_18002FEC7
0x18002fe3d  mov     rcx, [rsp+38h+hModule]; hModule
0x18002fe42  lea     rdx, aCreatecordbobj; "CreateCordbObject"
0x18002fe49  call    cs:__imp_GetProcAddress
0x18002fe4f  test    rax, rax
0x18002fe52  jz      short loc_18002FE62
0x18002fe54  lea     rdx, [rsp+38h+arg_8]
0x18002fe59  mov     ecx, esi
0x18002fe5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe60  jmp     short loc_18002FE81
0x18002fe62  mov     rcx, [rsp+38h+hModule]; hModule
0x18002fe67  lea     rdx, aDllgetclassobj_1; "DllGetClassObjectInternal"
0x18002fe6e  call    cs:__imp_GetProcAddress
0x18002fe74  mov     rbp, rax
0x18002fe77  test    rax, rax
0x18002fe7a  jnz     short loc_18002FE89
0x18002fe7c  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002fe81  mov     ebx, eax
0x18002fe83  test    eax, eax
0x18002fe85  jns     short loc_18002FEFC
0x18002fe87  jmp     short loc_18002FECC
0x18002fe89  cmp     esi, 3
0x18002fe8c  jl      short loc_18002FEA8
0x18002fe8e  lea     r8, [rsp+38h+arg_8]; void **
0x18002fe93  mov     rcx, rbp; int (*)(const struct _GUID *, const struct _GUID *, void **)
0x18002fe96  lea     rdx, stru_1800504F8; struct _GUID *
0x18002fe9d  call    ?GetLegacyCorDebug@@YAJP6AJAEBU_GUID@@0PEAPEAX@Z01@Z; GetLegacyCorDebug(long (*)(_GUID const &,_GUID const &,void * *),_GUID const &,void * *)
0x18002fea2  mov     ebx, eax
0x18002fea4  test    eax, eax
0x18002fea6  jns     short loc_18002FEFC
0x18002fea8  cmp     esi, 1
0x18002feab  jl      short loc_18002FEC7
0x18002fead  lea     r8, [rsp+38h+arg_8]; void **
0x18002feb2  mov     rcx, rbp; int (*)(const struct _GUID *, const struct _GUID *, void **)
0x18002feb5  lea     rdx, stru_180050508; struct _GUID *
0x18002febc  call    ?GetLegacyCorDebug@@YAJP6AJAEBU_GUID@@0PEAPEAX@Z01@Z; GetLegacyCorDebug(long (*)(_GUID const &,_GUID const &,void * *),_GUID const &,void * *)
0x18002fec1  mov     ebx, eax
0x18002fec3  test    eax, eax
0x18002fec5  jns     short loc_18002FEFC
0x18002fec7  mov     ebx, 80070057h
0x18002fecc  mov     rcx, [rsp+38h+arg_8]
0x18002fed1  test    rcx, rcx
0x18002fed4  jz      short loc_18002FEE9
0x18002fed6  mov     rax, [rcx]
0x18002fed9  mov     rax, [rax+10h]
0x18002fedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fee2  xor     ecx, ecx
0x18002fee4  mov     [rsp+38h+arg_8], rcx
0x18002fee9  cmp     [rsp+38h+hModule], 0
0x18002feef  jz      short loc_18002FF01
0x18002fef1  mov     rcx, [rsp+38h+hModule]; hLibModule
0x18002fef6  call    cs:__imp_FreeLibrary
0x18002fefc  mov     rcx, [rsp+38h+arg_8]
0x18002ff01  mov     [r14], rcx
0x18002ff04  mov     eax, ebx
0x18002ff06  jmp     short loc_18002FF0D
0x18002ff08  mov     eax, 80070057h
0x18002ff0d  mov     rbx, [rsp+38h+arg_0]
0x18002ff12  add     rsp, 20h
0x18002ff16  pop     r14
0x18002ff18  pop     rsi
0x18002ff19  pop     rbp
0x18002ff1a  retn
```
