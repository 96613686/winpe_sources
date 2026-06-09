# DllForwarder::DllForwarder(ushort const *,ushort const *,ushort const *)

- ea: `0x180008334`
- end: `0x1800084bf`
- name: `??0DllForwarder@@QEAA@PEBG00@Z`
- size: `395`
- prototype: `DllForwarder *__fastcall(DllForwarder *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009d10`

## callees

- `0x180001ba0`
- `0x180001fb8`
- `0x180008334`
- `0x1800084c8`
- `0x180008d88`
- `0x180009d90`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008406`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000848f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008406`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000848f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800083e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000846f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800083e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000846f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008484`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000840e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008497`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000840e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008497`

## string_xrefs

- `0x180008468`: `domiprov.dll`

## pseudocode

```c
DllForwarder *__fastcall DllForwarder::DllForwarder(
        DllForwarder *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  uus::Session *v4; // rax
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  const WCHAR *v6; // rcx
  HMODULE Library; // r15
  HMODULE v8; // r14
  DWORD LastError; // ebx
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  HMODULE v11; // r15
  HMODULE v12; // r14
  DWORD v13; // ebx
  uus::Session *v15; // [rsp+28h] [rbp-60h]
  LPCWSTR lpLibFileName[4]; // [rsp+30h] [rbp-58h] BYREF

  try
  {
    qword_1800188E0 = 0;
    hLibModule = 0;
    v15 = (uus::Session *)operator new(0x10u);
    v4 = uus::Session::Session(v15, L"deliveryoptimization");
    v5 = (void (__fastcall ***)(_QWORD, __int64))qword_1800188E0;
    qword_1800188E0 = (__int64)v4;
    if ( v5 )
    {
      (**v5)(v5, 1);
      v4 = (uus::Session *)qword_1800188E0;
    }
    uus::Session::GetFullPath(v4, lpLibFileName);
    v6 = (const WCHAR *)lpLibFileName;
    if ( lpLibFileName[3] > (LPCWSTR)7 )
      v6 = lpLibFileName[0];
    Library = LoadLibraryExW(v6, 0, 0);
    v8 = hLibModule;
    if ( hLibModule )
    {
      LastError = GetLastError();
      FreeLibrary(v8);
      SetLastError(LastError);
    }
    hLibModule = Library;
    std::wstring::~wstring(lpLibFileName);
  }
  catch ( ... )
  {
  }
  if ( !hLibModule )
  {
    v10 = (void (__fastcall ***)(_QWORD, __int64))qword_1800188E0;
    qword_1800188E0 = 0;
    if ( v10 )
      (**v10)(v10, 1);
    v11 = LoadLibraryExW(L"domiprov.dll", 0, 0x800u);
    v12 = hLibModule;
    if ( hLibModule )
    {
      v13 = GetLastError();
      FreeLibrary(v12);
      SetLastError(v13);
    }
    hLibModule = v11;
  }
  return (DllForwarder *)&qword_1800188E0;
}

```

## disassembly

```asm
0x180008334  push    rbx
0x180008336  push    rsi
0x180008337  push    r14
0x180008339  push    r15
0x18000833b  sub     rsp, 68h
0x18000833f  mov     rax, cs:__security_cookie
0x180008346  xor     rax, rsp
0x180008349  mov     [rsp+88h+var_38], rax
0x18000834e  mov     rax, [rsp+88h+var_68]
0x180008353  mov     [rsp+88h+var_68], rax
0x180008358  lea     rsi, qword_1800188E0
0x18000835f  mov     [rsp+88h+var_68], rsi
0x180008364  mov     cs:qword_1800188E0, 0
0x18000836f  mov     cs:hLibModule, 0
0x18000837a  mov     ecx, 10h; Size
0x18000837f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008384  mov     [rsp+88h+var_60], rax
0x180008389  lea     rdx, aDeliveryoptimi; "deliveryoptimization"
0x180008390  mov     rcx, rax; this
0x180008393  call    ??0Session@uus@@QEAA@PEBG@Z; uus::Session::Session(ushort const *)
0x180008398  nop
0x180008399  mov     rcx, cs:qword_1800188E0
0x1800083a0  mov     cs:qword_1800188E0, rax
0x1800083a7  test    rcx, rcx
0x1800083aa  jz      short loc_1800083C3
0x1800083ac  mov     rax, [rcx]
0x1800083af  mov     edx, 1
0x1800083b4  mov     rax, [rax]
0x1800083b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083bc  mov     rax, cs:qword_1800188E0
0x1800083c3  lea     rdx, [rsp+88h+lpLibFileName]
0x1800083c8  mov     rcx, rax
0x1800083cb  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEBG@Z; uus::Session::GetFullPath(ushort const *)
0x1800083d0  lea     rcx, [rsp+88h+lpLibFileName]
0x1800083d5  cmp     [rsp+88h+var_40], 7
0x1800083db  cmova   rcx, [rsp+88h+lpLibFileName]; lpLibFileName
0x1800083e1  xor     r8d, r8d; dwFlags
0x1800083e4  xor     edx, edx; hFile
0x1800083e6  call    cs:__imp_LoadLibraryExW
0x1800083ec  mov     r15, rax
0x1800083ef  mov     r14, cs:hLibModule
0x1800083f6  test    r14, r14
0x1800083f9  jz      short loc_180008414
0x1800083fb  call    cs:__imp_GetLastError
0x180008401  mov     ebx, eax
0x180008403  mov     rcx, r14; hLibModule
0x180008406  call    cs:__imp_FreeLibrary
0x18000840c  mov     ecx, ebx; dwErrCode
0x18000840e  call    cs:__imp_SetLastError
0x180008414  mov     cs:hLibModule, r15
0x18000841b  lea     rcx, [rsp+88h+lpLibFileName]
0x180008420  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008425  nop
0x180008426  jmp     short loc_18000842F
0x180008428  lea     rsi, qword_1800188E0
0x18000842f  cmp     cs:hLibModule, 0
0x180008437  jnz     short loc_1800084A4
0x180008439  mov     rcx, cs:qword_1800188E0
0x180008440  mov     cs:qword_1800188E0, 0
0x18000844b  test    rcx, rcx
0x18000844e  jz      short loc_180008460
0x180008450  mov     rax, [rcx]
0x180008453  mov     edx, 1
0x180008458  mov     rax, [rax]
0x18000845b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008460  xor     edx, edx; hFile
0x180008462  mov     r8d, 800h; dwFlags
0x180008468  lea     rcx, LibFileName; "domiprov.dll"
0x18000846f  call    cs:__imp_LoadLibraryExW
0x180008475  mov     r15, rax
0x180008478  mov     r14, cs:hLibModule
0x18000847f  test    r14, r14
0x180008482  jz      short loc_18000849D
0x180008484  call    cs:__imp_GetLastError
0x18000848a  mov     ebx, eax
0x18000848c  mov     rcx, r14; hLibModule
0x18000848f  call    cs:__imp_FreeLibrary
0x180008495  mov     ecx, ebx; dwErrCode
0x180008497  call    cs:__imp_SetLastError
0x18000849d  mov     cs:hLibModule, r15
0x1800084a4  mov     rax, rsi
0x1800084a7  mov     rcx, [rsp+88h+var_38]
0x1800084ac  xor     rcx, rsp; StackCookie
0x1800084af  call    __security_check_cookie
0x1800084b4  add     rsp, 68h
0x1800084b8  pop     r15
0x1800084ba  pop     r14
0x1800084bc  pop     rsi
0x1800084bd  pop     rbx
0x1800084be  retn
```
