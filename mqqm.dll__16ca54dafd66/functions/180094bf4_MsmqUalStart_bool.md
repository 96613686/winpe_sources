# MsmqUalStart(bool)

- ea: `0x180094bf4`
- end: `0x180094e2d`
- name: `?MsmqUalStart@@YAX_N@Z`
- size: `569`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002cd84`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x180094730`
- `0x180094bf4`
- `0x1800d6e56`
- `0x1800d6ea0`
- `0x1800e4010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180094c27`
- `KERNEL32!LoadLibraryExW` at `0x180094c27`
- `KERNEL32!GetLastError` at `0x180094c5b`
- `KERNEL32!GetLastError` at `0x180094c5b`
- `KERNEL32!GetProcAddress` at `0x180094c8d`
- `KERNEL32!GetProcAddress` at `0x180094ca4`
- `KERNEL32!GetProcAddress` at `0x180094cbb`
- `KERNEL32!GetProcAddress` at `0x180094c8d`
- `KERNEL32!GetProcAddress` at `0x180094ca4`
- `KERNEL32!GetProcAddress` at `0x180094cbb`

## string_xrefs

- `0x180094c20`: `ualapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MsmqUalStart()
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  DWORD LastError; // eax
  int (*ProcAddress)(struct tagUAL_DATA_BLOB *); // rax
  int v4; // eax
  HMODULE v5[2]; // [rsp+20h] [rbp-2D8h] BYREF
  int v6; // [rsp+30h] [rbp-2C8h] BYREF
  __int128 v7; // [rsp+34h] [rbp-2C4h]
  _BYTE v8[668]; // [rsp+44h] [rbp-2B4h] BYREF

  Library = LoadLibraryExW(L"ualapi.dll", 0, 0x800u);
  v1 = Library;
  v5[0] = Library;
  if ( !Library )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ac4bc4fa026435587f530d6adca8a796_Traceguids, LastError);
    }
    goto LABEL_21;
  }
  pfnUalStart = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(Library, "UalStart");
  pfnUalStop = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(v1, "UalStop");
  ProcAddress = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(v1, "UalInstrument");
  pfnUalInstrument = ProcAddress;
  if ( !pfnUalStart || !pfnUalStop || !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ac4bc4fa026435587f530d6adca8a796_Traceguids);
    goto LABEL_20;
  }
  if ( g_fUalStarted )
    goto LABEL_21;
  memset_0(v8, 0, sizeof(v8));
  v6 = 688;
  v7 = SumGuid_MSMQ;
  v4 = ((__int64 (__fastcall *)(int *))pfnUalStart)(&v6);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_ac4bc4fa026435587f530d6adca8a796_Traceguids,
        (unsigned int)v4);
LABEL_20:
    pfnUalStart = 0;
    pfnUalStop = 0;
    pfnUalInstrument = 0;
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ac4bc4fa026435587f530d6adca8a796_Traceguids);
  g_fUalStarted = 1;
  v5[0] = 0;
  g_hUalLib = v1;
LABEL_21:
  CAutoFreeLibrary::~CAutoFreeLibrary((CAutoFreeLibrary *)v5);
}

```

## disassembly

```asm
0x180094bf4  push    rbx
0x180094bf6  sub     rsp, 2F0h
0x180094bfd  mov     rax, cs:__security_cookie
0x180094c04  xor     rax, rsp
0x180094c07  mov     [rsp+2F8h+var_18], rax
0x180094c0f  mov     [rsp+2F8h+var_2D8], 0
0x180094c18  xor     edx, edx; hFile
0x180094c1a  mov     r8d, 800h; dwFlags
0x180094c20  lea     rcx, aUalapiDll; "ualapi.dll"
0x180094c27  call    cs:__imp_LoadLibraryExW
0x180094c2d  mov     rbx, rax
0x180094c30  mov     [rsp+2F8h+var_2D8], rax
0x180094c35  test    rax, rax
0x180094c38  jnz     short loc_180094C83
0x180094c3a  lea     rax, WPP_GLOBAL_Control
0x180094c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180094c48  cmp     rcx, rax
0x180094c4b  jz      loc_180094E0A
0x180094c51  test    byte ptr [rcx+1Ch], 4
0x180094c55  jz      loc_180094E0A
0x180094c5b  call    cs:__imp_GetLastError
0x180094c61  lea     edx, [rbx+0Ah]
0x180094c64  mov     r9d, eax
0x180094c67  lea     r8, WPP_ac4bc4fa026435587f530d6adca8a796_Traceguids
0x180094c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180094c75  mov     rcx, [rcx+10h]
0x180094c79  call    WPP_SF_d
0x180094c7e  jmp     loc_180094E0A
0x180094c83  lea     rdx, aUalstart; "UalStart"
0x180094c8a  mov     rcx, rbx; hModule
0x180094c8d  call    cs:__imp_GetProcAddress
0x180094c93  mov     cs:?pfnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*pfnUalStart)(tagUAL_DATA_BLOB *)
0x180094c9a  lea     rdx, aUalstop; "UalStop"
0x180094ca1  mov     rcx, rbx; hModule
0x180094ca4  call    cs:__imp_GetProcAddress
0x180094caa  mov     cs:?pfnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*pfnUalStop)(tagUAL_DATA_BLOB *)
0x180094cb1  lea     rdx, aUalinstrument; "UalInstrument"
0x180094cb8  mov     rcx, rbx; hModule
0x180094cbb  call    cs:__imp_GetProcAddress
0x180094cc1  mov     cs:?pfnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*pfnUalInstrument)(tagUAL_DATA_BLOB *)
0x180094cc8  cmp     cs:?pfnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*pfnUalStart)(tagUAL_DATA_BLOB *)
0x180094cd0  jz      loc_180094DBB
0x180094cd6  cmp     cs:?pfnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*pfnUalStop)(tagUAL_DATA_BLOB *)
0x180094cde  jz      loc_180094DBB
0x180094ce4  test    rax, rax
0x180094ce7  jz      loc_180094DBB
0x180094ced  cmp     cs:?g_fUalStarted@@3HA, 0; int g_fUalStarted
0x180094cf4  jnz     loc_180094E0A
0x180094cfa  xor     edx, edx; Val
0x180094cfc  mov     r8d, 29Ch; Size
0x180094d02  lea     rcx, [rsp+2F8h+var_2B4]; void *
0x180094d07  call    memset_0
0x180094d0c  mov     [rsp+2F8h+var_2C8], 2B0h
0x180094d14  movups  xmm0, cs:SumGuid_MSMQ
0x180094d1b  movdqu  [rsp+2F8h+var_2C4], xmm0
0x180094d21  lea     rcx, [rsp+2F8h+var_2C8]
0x180094d26  mov     rax, cs:?pfnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA; long (*pfnUalStart)(tagUAL_DATA_BLOB *)
0x180094d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094d32  mov     r9d, eax
0x180094d35  test    eax, eax
0x180094d37  jns     short loc_180094D71
0x180094d39  lea     rax, WPP_GLOBAL_Control
0x180094d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180094d47  cmp     rcx, rax
0x180094d4a  jz      loc_180094DE9
0x180094d50  test    byte ptr [rcx+1Ch], 4
0x180094d54  jz      loc_180094DE9
0x180094d5a  mov     edx, 0Ch
0x180094d5f  lea     r8, WPP_ac4bc4fa026435587f530d6adca8a796_Traceguids
0x180094d66  mov     rcx, [rcx+10h]
0x180094d6a  call    WPP_SF_d
0x180094d6f  jmp     short loc_180094DE9
0x180094d71  lea     rax, WPP_GLOBAL_Control
0x180094d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180094d7f  cmp     rcx, rax
0x180094d82  jz      short loc_180094D9F
0x180094d84  test    byte ptr [rcx+1Ch], 4
0x180094d88  jz      short loc_180094D9F
0x180094d8a  mov     edx, 0Dh
0x180094d8f  lea     r8, WPP_ac4bc4fa026435587f530d6adca8a796_Traceguids
0x180094d96  mov     rcx, [rcx+10h]
0x180094d9a  call    WPP_SF_
0x180094d9f  mov     cs:?g_fUalStarted@@3HA, 1; int g_fUalStarted
0x180094da9  mov     [rsp+2F8h+var_2D8], 0
0x180094db2  mov     cs:?g_hUalLib@@3VCAutoFreeLibrary@@A, rbx; CAutoFreeLibrary g_hUalLib
0x180094db9  jmp     short loc_180094E0A
0x180094dbb  lea     rax, WPP_GLOBAL_Control
0x180094dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180094dc9  cmp     rcx, rax
0x180094dcc  jz      short loc_180094DE9
0x180094dce  test    byte ptr [rcx+1Ch], 4
0x180094dd2  jz      short loc_180094DE9
0x180094dd4  mov     edx, 0Bh
0x180094dd9  lea     r8, WPP_ac4bc4fa026435587f530d6adca8a796_Traceguids
0x180094de0  mov     rcx, [rcx+10h]
0x180094de4  call    WPP_SF_
0x180094de9  mov     cs:?pfnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*pfnUalStart)(tagUAL_DATA_BLOB *)
0x180094df4  mov     cs:?pfnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*pfnUalStop)(tagUAL_DATA_BLOB *)
0x180094dff  mov     cs:?pfnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*pfnUalInstrument)(tagUAL_DATA_BLOB *)
0x180094e0a  lea     rcx, [rsp+2F8h+var_2D8]; this
0x180094e0f  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x180094e14  mov     rcx, [rsp+2F8h+var_18]
0x180094e1c  xor     rcx, rsp; StackCookie
0x180094e1f  call    __security_check_cookie
0x180094e24  add     rsp, 2F0h
0x180094e2b  pop     rbx
0x180094e2c  retn
```
