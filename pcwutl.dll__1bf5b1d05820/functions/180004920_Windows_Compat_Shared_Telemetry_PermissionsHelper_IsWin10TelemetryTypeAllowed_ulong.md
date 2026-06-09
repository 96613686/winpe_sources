# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x180004920`
- end: `0x180004a25`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `261`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800039c8`

## callees

- `0x180004920`
- `0x18001a010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800049f7`
- `KERNEL32!FreeLibrary` at `0x180004a05`
- `KERNEL32!FreeLibrary` at `0x180004a13`
- `KERNEL32!FreeLibrary` at `0x1800049f7`
- `KERNEL32!FreeLibrary` at `0x180004a05`
- `KERNEL32!FreeLibrary` at `0x180004a13`
- `KERNEL32!LoadLibraryExW` at `0x18000493f`
- `KERNEL32!LoadLibraryExW` at `0x18000498b`
- `KERNEL32!LoadLibraryExW` at `0x18000493f`
- `KERNEL32!LoadLibraryExW` at `0x18000498b`
- `KERNEL32!GetProcAddress` at `0x180004957`
- `KERNEL32!GetProcAddress` at `0x1800049a3`
- `KERNEL32!GetProcAddress` at `0x1800049cd`
- `KERNEL32!GetProcAddress` at `0x180004957`
- `KERNEL32!GetProcAddress` at `0x1800049a3`
- `KERNEL32!GetProcAddress` at `0x1800049cd`
- `KERNEL32!LoadLibraryW` at `0x1800049b5`
- `KERNEL32!LoadLibraryW` at `0x1800049b5`

## pseudocode

```c
bool __fastcall Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(int a1)
{
  HMODULE v1; // rbx
  HMODULE Library; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rax
  int v5; // eax
  HMODULE v6; // rdi
  bool v7; // bp
  HMODULE v8; // rax
  FARPROC v9; // rax
  HMODULE LibraryW; // rax
  int v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = a1;
  v1 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelIsTelemetryTypeAllowed");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
      if ( v5 >= 0 )
      {
        v6 = 0;
        v7 = v5 == 0;
LABEL_12:
        FreeLibrary(v3);
        goto LABEL_13;
      }
    }
  }
  v12 = 0;
  v7 = 0;
  v8 = LoadLibraryExW(L"Aepic", 0, 0x800u);
  v6 = v8;
  if ( v8 && (v9 = GetProcAddress(v8, "GetPrivacyLevel")) != 0
    || (LibraryW = LoadLibraryW(L"Devinv"), (v1 = LibraryW) != 0)
    && (v9 = GetProcAddress(LibraryW, "GetPrivacyLevel")) != 0 )
  {
    if ( ((int (__fastcall *)(int *))v9)(&v12) >= 0 )
      v7 = v12 != 0;
  }
  if ( v3 )
    goto LABEL_12;
LABEL_13:
  if ( v6 )
    FreeLibrary(v6);
  if ( v1 )
    FreeLibrary(v1);
  return v7;
}

```

## disassembly

```asm
0x180004920  mov     [rsp+arg_0], ecx
0x180004924  push    rbx
0x180004925  push    rbp
0x180004926  push    rsi
0x180004927  push    rdi
0x180004928  sub     rsp, 28h
0x18000492c  mov     edi, 800h
0x180004931  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x180004938  mov     r8d, edi; dwFlags
0x18000493b  xor     edx, edx; hFile
0x18000493d  xor     ebx, ebx
0x18000493f  call    cs:__imp_LoadLibraryExW
0x180004945  mov     rsi, rax
0x180004948  test    rax, rax
0x18000494b  jz      short loc_180004978
0x18000494d  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180004954  mov     rcx, rax; hModule
0x180004957  call    cs:__imp_GetProcAddress
0x18000495d  test    rax, rax
0x180004960  jz      short loc_180004978
0x180004962  lea     ecx, [rbx+1]
0x180004965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000496a  test    eax, eax
0x18000496c  js      short loc_180004978
0x18000496e  xor     edi, edi
0x180004970  test    eax, eax
0x180004972  setz    bpl
0x180004976  jmp     short loc_1800049F4
0x180004978  mov     r8d, edi; dwFlags
0x18000497b  mov     [rsp+48h+arg_0], ebx
0x18000497f  xor     edx, edx; hFile
0x180004981  lea     rcx, aAepic; "Aepic"
0x180004988  xor     bpl, bpl
0x18000498b  call    cs:__imp_LoadLibraryExW
0x180004991  mov     rdi, rax
0x180004994  test    rax, rax
0x180004997  jz      short loc_1800049AE
0x180004999  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800049a0  mov     rcx, rax; hModule
0x1800049a3  call    cs:__imp_GetProcAddress
0x1800049a9  test    rax, rax
0x1800049ac  jnz     short loc_1800049D8
0x1800049ae  lea     rcx, aDevinv; "Devinv"
0x1800049b5  call    cs:__imp_LoadLibraryW
0x1800049bb  mov     rbx, rax
0x1800049be  test    rax, rax
0x1800049c1  jz      short loc_1800049EF
0x1800049c3  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800049ca  mov     rcx, rax; hModule
0x1800049cd  call    cs:__imp_GetProcAddress
0x1800049d3  test    rax, rax
0x1800049d6  jz      short loc_1800049EF
0x1800049d8  lea     rcx, [rsp+48h+arg_0]
0x1800049dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049e2  test    eax, eax
0x1800049e4  js      short loc_1800049EF
0x1800049e6  cmp     [rsp+48h+arg_0], 1
0x1800049eb  setnb   bpl
0x1800049ef  test    rsi, rsi
0x1800049f2  jz      short loc_1800049FD
0x1800049f4  mov     rcx, rsi; hLibModule
0x1800049f7  call    cs:__imp_FreeLibrary
0x1800049fd  test    rdi, rdi
0x180004a00  jz      short loc_180004A0B
0x180004a02  mov     rcx, rdi; hLibModule
0x180004a05  call    cs:__imp_FreeLibrary
0x180004a0b  test    rbx, rbx
0x180004a0e  jz      short loc_180004A19
0x180004a10  mov     rcx, rbx; hLibModule
0x180004a13  call    cs:__imp_FreeLibrary
0x180004a19  mov     al, bpl
0x180004a1c  add     rsp, 28h
0x180004a20  pop     rdi
0x180004a21  pop     rsi
0x180004a22  pop     rbp
0x180004a23  pop     rbx
0x180004a24  retn
```
