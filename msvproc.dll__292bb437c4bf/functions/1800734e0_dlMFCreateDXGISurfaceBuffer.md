# dlMFCreateDXGISurfaceBuffer

- ea: `0x1800734e0`
- end: `0x180073553`
- name: `dlMFCreateDXGISurfaceBuffer`
- size: `115`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180025ef0`
- `0x1800387dc`
- `0x18003c230`
- `0x18003d0d4`
- `0x18005342c`

## callees

- `0x180059fac`
- `0x1800734e0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800734f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800734f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073500`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180073500`

## string_xrefs

- `0x1800734e6`: `MFPlat.dll`
- `0x1800734f9`: `MFCreateDXGISurfaceBuffer`
- `0x18007350e`: `Invalid pointer: MFCREATEDXGISURFACEBUFFER`
- `0x18007351a`: `dlMFCreateDXGISurfaceBuffer`

## pseudocode

```c
__int64 __fastcall dlMFCreateDXGISurfaceBuffer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  ModuleHandleW = GetModuleHandleW(L"MFPlat.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "MFCreateDXGISurfaceBuffer");
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(GUID *, __int64, _QWORD, _QWORD, __int64))ProcAddress)(
             &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
             a2,
             0,
             0,
             a5);
  else
    return XvpOriginateError<43>(
             "dlMFCreateDXGISurfaceBuffer",
             2147500037LL,
             L"Invalid pointer: MFCREATEDXGISURFACEBUFFER");
}

```

## disassembly

```asm
0x1800734e0  push    rbx
0x1800734e2  sub     rsp, 30h
0x1800734e6  lea     rcx, aMfplatDll; "MFPlat.dll"
0x1800734ed  mov     rbx, rdx
0x1800734f0  call    cs:__imp_GetModuleHandleW
0x1800734f6  mov     rcx, rax; hModule
0x1800734f9  lea     rdx, aMfcreatedxgisu_0; "MFCreateDXGISurfaceBuffer"
0x180073500  call    cs:__imp_GetProcAddress
0x180073506  mov     r10, rax
0x180073509  test    rax, rax
0x18007350c  jnz     short loc_18007352B
0x18007350e  lea     r8, aInvalidPointer_1; "Invalid pointer: MFCREATEDXGISURFACEBUF"...
0x180073515  mov     edx, 80004005h
0x18007351a  lea     rcx, aDlmfcreatedxgi; "dlMFCreateDXGISurfaceBuffer"
0x180073521  add     rsp, 30h
0x180073525  pop     rbx
0x180073526  jmp     ??$XvpOriginateError@$0CL@@@YAJQEADJAEAY0CL@$$CBG@Z; XvpOriginateError<43>(char * const,long,ushort const (&)[43])
0x18007352b  mov     rax, [rsp+38h+arg_20]
0x180073530  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x180073537  mov     [rsp+38h+var_18], rax
0x18007353c  xor     r9d, r9d
0x18007353f  mov     rax, r10
0x180073542  xor     r8d, r8d
0x180073545  mov     rdx, rbx
0x180073548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007354d  add     rsp, 30h
0x180073551  pop     rbx
0x180073552  retn
```
