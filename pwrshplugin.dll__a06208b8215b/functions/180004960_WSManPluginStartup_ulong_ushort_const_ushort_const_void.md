# WSManPluginStartup(ulong,ushort const *,ushort const *,void * *)

- ea: `0x180004960`
- end: `0x180004a12`
- name: `?WSManPluginStartup@@YAKKPEBG0PEAPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, struct PwrshPlugIn **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x180001098`
- `0x180002fac`
- `0x180004370`
- `0x180004960`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800049de`
- `KERNEL32!GetProcAddress` at `0x1800049de`
- `KERNEL32!GetModuleHandleW` at `0x1800049c9`
- `KERNEL32!GetModuleHandleW` at `0x1800049c9`

## string_xrefs

- `0x1800049c2`: `ntdll`

## pseudocode

```c
__int64 __fastcall WSManPluginStartup(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct PwrshPlugIn **a4)
{
  PwrshPlugInMediator *v7; // rcx
  struct PwrshPlugIn *v8; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  _QWORD *v12; // rbx
  __int64 v13; // [rsp+28h] [rbp-10h] BYREF
  unsigned __int16 *v14; // [rsp+58h] [rbp+20h] BYREF

  *a4 = 0;
  try
  {
    PwrshPlugInMediator::GetPwrshPlugInMediator(a3);
    v14 = 0;
    PwrshPlugInMediator::VerifyAndStoreExtraInfo(v7, a3, &v14);
    v8 = (struct PwrshPlugIn *)operator new(0x10u);
    if ( v8 )
    {
      *(_QWORD *)v8 = a2;
      *((_QWORD *)v8 + 1) = v14;
    }
    g_pPluginContext = v8;
    *a4 = v8;
    ModuleHandleW = GetModuleHandleW(L"ntdll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "WinSqmSetDWORD");
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 12246, 1);
    }
    result = 0;
  }
  catch ( PlugInException *v13 )
  {
    LODWORD(v14) = 1101;
    v12 = (_QWORD *)v13;
    if ( v13 )
    {
      LODWORD(v14) = *(_DWORD *)v13;
      if ( *(_QWORD *)(v13 + 8) )
      {
        operator delete[](*(void **)(v13 + 8));
        v12[1] = 0;
      }
      operator delete(v12);
    }
    return (unsigned int)v14;
  }
  PwrshPlugInMediator::GetPwrshPlugInMediator(a3);
}

```

## disassembly

```asm
0x180004960  mov     [rsp+arg_0], rbx
0x180004965  mov     [rsp+arg_8], rsi
0x18000496a  push    rdi
0x18000496b  sub     rsp, 30h
0x18000496f  mov     rdi, r9
0x180004972  mov     rbx, r8
0x180004975  mov     rsi, rdx
0x180004978  mov     qword ptr [r9], 0
0x18000497f  mov     rcx, rbx; unsigned __int16 *
0x180004982  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x180004987  mov     [rsp+38h+arg_18], 0
0x180004990  lea     r8, [rsp+38h+arg_18]; unsigned __int16 **
0x180004995  mov     rdx, rbx; unsigned __int16 *
0x180004998  call    ?VerifyAndStoreExtraInfo@PwrshPlugInMediator@@QEAAXPEBGPEAPEAG@Z; PwrshPlugInMediator::VerifyAndStoreExtraInfo(ushort const *,ushort * *)
0x18000499d  mov     ecx, 10h; Size
0x1800049a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800049a7  test    rax, rax
0x1800049aa  jz      short loc_1800049B8
0x1800049ac  mov     [rax], rsi
0x1800049af  mov     rcx, [rsp+38h+arg_18]
0x1800049b4  mov     [rax+8], rcx
0x1800049b8  mov     cs:?g_pPluginContext@@3PEAVPwrshPlugIn@@EA, rax; PwrshPlugIn * g_pPluginContext
0x1800049bf  mov     [rdi], rax
0x1800049c2  lea     rcx, ModuleName; "ntdll"
0x1800049c9  call    cs:__imp_GetModuleHandleW
0x1800049cf  test    rax, rax
0x1800049d2  jz      short loc_1800049F9
0x1800049d4  lea     rdx, ProcName; "WinSqmSetDWORD"
0x1800049db  mov     rcx, rax; hModule
0x1800049de  call    cs:__imp_GetProcAddress
0x1800049e4  test    rax, rax
0x1800049e7  jz      short loc_1800049F9
0x1800049e9  mov     edx, 2FD6h
0x1800049ee  xor     ecx, ecx
0x1800049f0  lea     r8d, [rcx+1]
0x1800049f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f9  xor     eax, eax
0x1800049fb  jmp     short loc_180004A01
0x1800049fd  mov     eax, dword ptr [rsp+38h+arg_18]
0x180004a01  mov     rbx, [rsp+38h+arg_0]
0x180004a06  mov     rsi, [rsp+38h+arg_8]
0x180004a0b  add     rsp, 30h
0x180004a0f  pop     rdi
0x180004a10  retn
```
