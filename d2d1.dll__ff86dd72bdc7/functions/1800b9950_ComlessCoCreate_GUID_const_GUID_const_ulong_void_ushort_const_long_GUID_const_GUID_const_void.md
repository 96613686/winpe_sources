# ComlessCoCreate(_GUID const &,_GUID const &,ulong,void * *,ushort const *,long (*&)(_GUID const &,_GUID const &,void * *))

- ea: `0x1800b9950`
- end: `0x1800b9a3d`
- name: `?ComlessCoCreate@@YAJAEBU_GUID@@0KPEAPEAXPEBGAEAP6AJ001@Z@Z`
- size: `237`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, unsigned int, void **, const unsigned __int16 *, int (**)(const struct _GUID *, const struct _GUID *, void **))`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b97bc`
- `0x1800b9a88`
- `0x1800b9edc`
- `0x1802122cc`
- `0x18023e0d8`

## callees

- `0x18001fd58`
- `0x1800b9950`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b9a22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b9a22`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b9a09`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b9a09`

## string_xrefs

- `0x1800b9a18`: `DllGetClassObject`
- `0x1800b99fc`: `WindowsCodecs.dll`

## pseudocode

```c
__int64 __fastcall ComlessCoCreate(const struct _GUID *a1, const struct _GUID *a2, __int64 a3, void **a4)
{
  unsigned int v5; // ebx
  int v6; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  *a4 = 0;
  v10 = 0;
  if ( !qword_1805DBF50 )
  {
    Library = LoadLibraryExW(L"WindowsCodecs.dll", 0, 0x800u);
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "DllGetClassObject");
      if ( ProcAddress )
        _InterlockedExchange64((volatile __int64 *)&qword_1805DBF50, (__int64)ProcAddress);
    }
  }
  v5 = -2147467259;
  if ( qword_1805DBF50 )
  {
    v6 = qword_1805DBF50(&CLSID_WICImagingFactory2, &IID_IClassFactory, &v10);
    v5 = v6;
    if ( v6 < 0
      || (v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, void **))(*(_QWORD *)v10 + 24LL))(
                 v10,
                 0,
                 &IID_IWICImagingFactory,
                 a4),
          v5 = v6,
          v6 < 0) )
    {
      DoStackCapture(v6);
    }
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return v5;
}

```

## disassembly

```asm
0x1800b9950  mov     [rsp+arg_0], rbx
0x1800b9955  mov     [rsp+arg_8], rdx
0x1800b995a  push    rdi
0x1800b995b  sub     rsp, 30h
0x1800b995f  mov     qword ptr [r9], 0
0x1800b9966  mov     rdi, r9
0x1800b9969  cmp     cs:qword_1805DBF50, 0
0x1800b9971  mov     [rsp+38h+arg_8], 0
0x1800b997a  jz      short loc_1800B99FA
0x1800b997c  mov     rax, cs:qword_1805DBF50
0x1800b9983  mov     ebx, 80004005h
0x1800b9988  test    rax, rax
0x1800b998b  jz      short loc_1800B99CE
0x1800b998d  lea     r8, [rsp+38h+arg_8]
0x1800b9992  lea     rdx, IID_IClassFactory
0x1800b9999  lea     rcx, CLSID_WICImagingFactory2
0x1800b99a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b99a5  mov     ebx, eax
0x1800b99a7  test    eax, eax
0x1800b99a9  js      short loc_1800B99F1
0x1800b99ab  mov     rcx, [rsp+38h+arg_8]
0x1800b99b0  lea     r8, IID_IWICImagingFactory
0x1800b99b7  mov     r9, rdi
0x1800b99ba  xor     edx, edx
0x1800b99bc  mov     rax, [rcx]
0x1800b99bf  mov     rax, [rax+18h]
0x1800b99c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b99c8  mov     ebx, eax
0x1800b99ca  test    eax, eax
0x1800b99cc  js      short loc_1800B99F1
0x1800b99ce  mov     rcx, [rsp+38h+arg_8]
0x1800b99d3  test    rcx, rcx
0x1800b99d6  jz      short loc_1800B99E4
0x1800b99d8  mov     rdx, [rcx]
0x1800b99db  mov     rax, [rdx+10h]
0x1800b99df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b99e4  mov     eax, ebx
0x1800b99e6  mov     rbx, [rsp+38h+arg_0]
0x1800b99eb  add     rsp, 30h
0x1800b99ef  pop     rdi
0x1800b99f0  retn
0x1800b99f1  mov     ecx, eax; int
0x1800b99f3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b99f8  jmp     short loc_1800B99CE
0x1800b99fa  xor     edx, edx; hFile
0x1800b99fc  lea     rcx, LibFileName; "WindowsCodecs.dll"
0x1800b9a03  mov     r8d, 800h; dwFlags
0x1800b9a09  call    cs:__imp_LoadLibraryExW
0x1800b9a0f  test    rax, rax
0x1800b9a12  jz      loc_1800B997C
0x1800b9a18  lea     rdx, ProcName; "DllGetClassObject"
0x1800b9a1f  mov     rcx, rax; hModule
0x1800b9a22  call    cs:__imp_GetProcAddress
0x1800b9a28  test    rax, rax
0x1800b9a2b  jz      loc_1800B997C
0x1800b9a31  xchg    rax, cs:qword_1805DBF50
0x1800b9a38  jmp     loc_1800B997C
```
