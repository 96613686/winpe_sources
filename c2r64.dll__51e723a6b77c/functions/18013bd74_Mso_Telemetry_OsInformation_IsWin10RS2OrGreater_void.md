# Mso::Telemetry::OsInformation::IsWin10RS2OrGreater(void)

- ea: `0x18013bd74`
- end: `0x18013be6f`
- name: `?IsWin10RS2OrGreater@OsInformation@Telemetry@Mso@@YA_NXZ`
- size: `251`
- prototype: `bool __fastcall(Mso::Telemetry::OsInformation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18013bb20`

## callees

- `0x18003e690`
- `0x180052cd0`
- `0x18013bd74`
- `0x180146090`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18013bdce`
- `KERNEL32!GetProcAddress` at `0x18013bdce`
- `KERNEL32!FreeLibrary` at `0x18013be33`
- `KERNEL32!FreeLibrary` at `0x18013be42`
- `KERNEL32!FreeLibrary` at `0x18013be33`
- `KERNEL32!FreeLibrary` at `0x18013be42`
- `KERNEL32!LoadLibraryExW` at `0x18013bda7`
- `KERNEL32!LoadLibraryExW` at `0x18013bda7`

## string_xrefs

- `0x18013bda0`: `Ntdll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Mso::Telemetry::OsInformation::IsWin10RS2OrGreater(Mso::Telemetry::OsInformation *this)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  char v3; // di
  FARPROC ProcAddress; // rsi
  _DWORD v6[72]; // [rsp+20h] [rbp-138h] BYREF

  Library = LoadLibraryExW(L"Ntdll", 0, 0x1000u);
  v2 = Library;
  v3 = 0;
  if ( !Library )
    CrashWithRecovery(0x170684Du, 0);
  ProcAddress = GetProcAddress(Library, "RtlGetVersion");
  if ( !ProcAddress )
    CrashWithRecovery(0x170684Eu, 0);
  memset(&v6[1], 0, 0x110u);
  v6[0] = 276;
  if ( ((unsigned int (__fastcall *)(_DWORD *))ProcAddress)(v6) )
  {
    FreeLibrary(v2);
    return 0;
  }
  else
  {
    if ( v6[1] == 10 && v6[3] >= 0x3A34u || v6[1] >= 0xBu )
      v3 = 1;
    FreeLibrary(v2);
    return v3;
  }
}

```

## disassembly

```asm
0x18013bd74  mov     [rsp+arg_0], rbx
0x18013bd79  mov     [rsp+arg_8], rsi
0x18013bd7e  push    rdi
0x18013bd7f  sub     rsp, 150h
0x18013bd86  mov     rax, cs:__security_cookie
0x18013bd8d  xor     rax, rsp
0x18013bd90  mov     [rsp+158h+var_18], rax
0x18013bd98  xor     edx, edx; hFile
0x18013bd9a  mov     r8d, 1000h; dwFlags
0x18013bda0  lea     rcx, aNtdll; "Ntdll"
0x18013bda7  call    cs:__imp_LoadLibraryExW
0x18013bdad  mov     rbx, rax
0x18013bdb0  xor     edi, edi
0x18013bdb2  test    rax, rax
0x18013bdb5  jnz     short loc_18013BDC4
0x18013bdb7  xor     edx, edx; struct CrashContext *
0x18013bdb9  mov     ecx, 170684Dh; unsigned int
0x18013bdbe  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013bdc4  lea     rdx, aRtlgetversion; "RtlGetVersion"
0x18013bdcb  mov     rcx, rbx; hModule
0x18013bdce  call    cs:__imp_GetProcAddress
0x18013bdd4  mov     rsi, rax
0x18013bdd7  test    rax, rax
0x18013bdda  jnz     short loc_18013BDE9
0x18013bddc  xor     edx, edx; struct CrashContext *
0x18013bdde  mov     ecx, 170684Eh; unsigned int
0x18013bde3  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013bde9  xor     edx, edx; Val
0x18013bdeb  mov     r8d, 110h; Size
0x18013bdf1  lea     rcx, [rsp+158h+var_134]; void *
0x18013bdf6  call    memset
0x18013bdfb  mov     [rsp+158h+var_138], 114h
0x18013be03  lea     rcx, [rsp+158h+var_138]
0x18013be08  mov     rax, rsi
0x18013be0b  call    cs:__guard_dispatch_icall_fptr
0x18013be11  test    eax, eax
0x18013be13  jnz     short loc_18013BE3F
0x18013be15  cmp     [rsp+158h+var_134], 0Ah
0x18013be1a  jnz     short loc_18013BE26
0x18013be1c  cmp     [rsp+158h+var_12C], 3A34h
0x18013be24  jnb     short loc_18013BE2D
0x18013be26  cmp     [rsp+158h+var_134], 0Bh
0x18013be2b  jb      short loc_18013BE30
0x18013be2d  mov     dil, 1
0x18013be30  mov     rcx, rbx; hLibModule
0x18013be33  call    cs:__imp_FreeLibrary
0x18013be39  nop
0x18013be3a  mov     al, dil
0x18013be3d  jmp     short loc_18013BE4A
0x18013be3f  mov     rcx, rbx; hLibModule
0x18013be42  call    cs:__imp_FreeLibrary
0x18013be48  xor     al, al
0x18013be4a  mov     rcx, [rsp+158h+var_18]
0x18013be52  xor     rcx, rsp; StackCookie
0x18013be55  call    __security_check_cookie
0x18013be5a  lea     r11, [rsp+158h+var_8]
0x18013be62  mov     rbx, [r11+10h]
0x18013be66  mov     rsi, [r11+18h]
0x18013be6a  mov     rsp, r11
0x18013be6d  pop     rdi
0x18013be6e  retn
```
