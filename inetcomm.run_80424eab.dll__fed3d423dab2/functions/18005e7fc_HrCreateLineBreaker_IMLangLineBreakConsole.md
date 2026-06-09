# HrCreateLineBreaker(IMLangLineBreakConsole * *)

- ea: `0x18005e7fc`
- end: `0x18005e8c8`
- name: `?HrCreateLineBreaker@@YAJPEAPEAUIMLangLineBreakConsole@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(struct IMLangLineBreakConsole **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a260`

## callees

- `0x180002098`
- `0x18005e7fc`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x18005e839`
- `KERNEL32!LoadLibraryA` at `0x18005e839`
- `KERNEL32!GetProcAddress` at `0x18005e85c`
- `KERNEL32!GetProcAddress` at `0x18005e85c`
- `KERNEL32!LeaveCriticalSection` at `0x18005e8ab`
- `KERNEL32!LeaveCriticalSection` at `0x18005e8ab`
- `KERNEL32!EnterCriticalSection` at `0x18005e820`
- `KERNEL32!EnterCriticalSection` at `0x18005e820`

## string_xrefs

- `0x18005e832`: `MLANG.DLL`
- `0x18005e852`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall HrCreateLineBreaker(struct IMLangLineBreakConsole **a1)
{
  HMODULE LibraryA; // rax
  int v3; // ebx
  FARPROC ProcAddress; // rax
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  v6 = 0;
  EnterCriticalSection(&g_csMLANG);
  LibraryA = g_hinstMLANG;
  if ( (g_hinstMLANG || (LibraryA = LoadLibraryA("MLANG.DLL"), (g_hinstMLANG = LibraryA) != 0))
    && (ProcAddress = GetProcAddress(LibraryA, "DllGetClassObject")) != 0 )
  {
    v3 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
           &CLSID_CMultiLanguage,
           &IID_IClassFactory,
           &v6);
    if ( v3 >= 0 )
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IMLangLineBreakConsole **))(*(_QWORD *)v6 + 24LL))(
             v6,
             0,
             &IID_IMLangLineBreakConsole,
             a1);
  }
  else
  {
    v3 = -2147467259;
  }
  LeaveCriticalSection(&g_csMLANG);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005e7fc  mov     [rsp+arg_8], rbx
0x18005e801  push    rdi
0x18005e802  sub     rsp, 30h
0x18005e806  mov     rdi, rcx
0x18005e809  mov     qword ptr [rcx], 0
0x18005e810  lea     rcx, ?g_csMLANG@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e817  mov     [rsp+38h+arg_0], 0
0x18005e820  call    cs:__imp_EnterCriticalSection
0x18005e826  mov     rax, cs:?g_hinstMLANG@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstMLANG
0x18005e82d  test    rax, rax
0x18005e830  jnz     short loc_18005E852
0x18005e832  lea     rcx, LibFileName; "MLANG.DLL"
0x18005e839  call    cs:__imp_LoadLibraryA
0x18005e83f  mov     cs:?g_hinstMLANG@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstMLANG
0x18005e846  test    rax, rax
0x18005e849  jnz     short loc_18005E852
0x18005e84b  mov     ebx, 80004005h
0x18005e850  jmp     short loc_18005E8A4
0x18005e852  lea     rdx, ProcName; "DllGetClassObject"
0x18005e859  mov     rcx, rax; hModule
0x18005e85c  call    cs:__imp_GetProcAddress
0x18005e862  test    rax, rax
0x18005e865  jz      short loc_18005E84B
0x18005e867  lea     r8, [rsp+38h+arg_0]
0x18005e86c  lea     rdx, IID_IClassFactory
0x18005e873  lea     rcx, CLSID_CMultiLanguage
0x18005e87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e87f  mov     ebx, eax
0x18005e881  test    eax, eax
0x18005e883  js      short loc_18005E8A4
0x18005e885  mov     rcx, [rsp+38h+arg_0]
0x18005e88a  lea     r8, IID_IMLangLineBreakConsole
0x18005e891  mov     r9, rdi
0x18005e894  xor     edx, edx
0x18005e896  mov     rax, [rcx]
0x18005e899  mov     rax, [rax+18h]
0x18005e89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8a2  mov     ebx, eax
0x18005e8a4  lea     rcx, ?g_csMLANG@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e8ab  call    cs:__imp_LeaveCriticalSection
0x18005e8b1  lea     rcx, [rsp+38h+arg_0]
0x18005e8b6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18005e8bb  mov     eax, ebx
0x18005e8bd  mov     rbx, [rsp+38h+arg_8]
0x18005e8c2  add     rsp, 30h
0x18005e8c6  pop     rdi
0x18005e8c7  retn
```
