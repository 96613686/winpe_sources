# ReportAppCompatError(ushort *,...)

- ea: `0x18000b1f0`
- end: `0x18000b31b`
- name: `?ReportAppCompatError@@YAXPEAGZZ`
- size: `299`
- prototype: `void(wchar_t *Format, ...)`
- caller_count: `10`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ac2c`
- `0x18000af8c`
- `0x1800325d4`
- `0x180032a80`
- `0x180032c00`
- `0x180033274`
- `0x180033304`
- `0x180033604`
- `0x18003378c`
- `0x1800337bc`

## callees

- `0x18000b1f0`
- `0x18000dfa8`
- `0x180028c04`
- `0x1800324ac`
- `0x180041ac0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b2af`
- `KERNEL32!GetProcAddress` at `0x18000b2af`
- `KERNEL32!LoadLibraryExW` at `0x18000b28c`
- `KERNEL32!LoadLibraryExW` at `0x18000b28c`
- `ADVAPI32!RegisterEventSourceA` at `0x18000b261`
- `ADVAPI32!RegisterEventSourceA` at `0x18000b261`

## string_xrefs

- `0x18000b285`: `advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void ReportAppCompatError(wchar_t *Format, ...)
{
  HANDLE v1; // rbx
  HMODULE Library; // rcx
  FARPROC ProcAddress; // rax
  wchar_t *v4; // [rsp+58h] [rbp-B0h] BYREF
  HMODULE v5; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v6; // [rsp+68h] [rbp-A0h]
  HANDLE v7; // [rsp+70h] [rbp-98h] BYREF
  BOOL v8; // [rsp+78h] [rbp-90h]
  wchar_t Buffer[256]; // [rsp+88h] [rbp-80h] BYREF
  va_list va; // [rsp+2C0h] [rbp+1B8h] BYREF

  va_start(va, Format);
  v4 = Buffer;
  vsnwprintf_s(Buffer, 0xFFu, 0xFFFFFFFFFFFFFFFFuLL, Format, va);
  v1 = RegisterEventSourceA(0, ".NET Runtime");
  v7 = v1;
  v8 = v1 != 0;
  if ( v1 )
  {
    Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
    v5 = Library;
    LODWORD(v6) = Library != 0;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "ReportEventW");
      if ( ProcAddress )
        ((void (__fastcall *)(HANDLE, __int64, _QWORD, __int64, _QWORD, __int16, _DWORD, wchar_t **, _QWORD))ProcAddress)(
          v1,
          1,
          0,
          1024,
          0,
          1,
          0,
          &v4,
          0);
    }
    Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v5);
  }
  Wrapper<void *,&void DoNothing<void *>(void *),&void HolderDeregisterEventSource(void *),0,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void HolderDeregisterEventSource(void *),0,&int CompareDefault<void *>(void *,void *),2>(&v7);
}

```

## disassembly

```asm
0x18000b1f0  mov     rax, rsp
0x18000b1f3  mov     [rax+8], rcx
0x18000b1f7  mov     [rax+10h], rdx
0x18000b1fb  mov     [rax+18h], r8
0x18000b1ff  mov     [rax+20h], r9
0x18000b203  push    rbp
0x18000b204  push    rbx
0x18000b205  push    rsi
0x18000b206  lea     rbp, [rax-1A8h]
0x18000b20d  sub     rsp, 290h
0x18000b214  mov     rax, cs:__security_cookie
0x18000b21b  xor     rax, rsp
0x18000b21e  mov     [rbp+1A0h+var_20], rax
0x18000b225  mov     [rsp+2A0h+var_250], 0
0x18000b22e  lea     rdx, [rbp+1A0h+arg_8]
0x18000b235  lea     rax, [rbp+1A0h+Buffer]
0x18000b239  mov     [rsp+2A0h+var_250], rax
0x18000b23e  mov     [rsp+2A0h+ArgList], rdx; ArgList
0x18000b243  mov     r9, rcx; Format
0x18000b246  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000b24a  mov     edx, 0FFh; BufferCount
0x18000b24f  lea     rcx, [rbp+1A0h+Buffer]; Buffer
0x18000b253  call    _vsnwprintf_s
0x18000b258  lea     rdx, SourceName; ".NET Runtime"
0x18000b25f  xor     ecx, ecx; lpUNCServerName
0x18000b261  call    cs:__imp_RegisterEventSourceA
0x18000b267  mov     rbx, rax
0x18000b26a  mov     [rsp+2A0h+var_238], rax
0x18000b26f  xor     eax, eax
0x18000b271  lea     esi, [rax+1]
0x18000b274  test    rbx, rbx
0x18000b277  cmovnz  eax, esi
0x18000b27a  mov     [rsp+2A0h+var_230], eax
0x18000b27e  jz      short loc_18000B2F7
0x18000b280  xor     r8d, r8d; dwFlags
0x18000b283  xor     edx, edx; hFile
0x18000b285  lea     rcx, LibFileName; "advapi32.dll"
0x18000b28c  call    cs:__imp_LoadLibraryExW
0x18000b292  mov     rcx, rax; hModule
0x18000b295  mov     [rsp+2A0h+var_248], rax
0x18000b29a  xor     eax, eax
0x18000b29c  test    rcx, rcx
0x18000b29f  cmovnz  eax, esi
0x18000b2a2  mov     dword ptr [rsp+2A0h+var_240], eax
0x18000b2a6  jz      short loc_18000B2EC
0x18000b2a8  lea     rdx, aReporteventw_0; "ReportEventW"
0x18000b2af  call    cs:__imp_GetProcAddress
0x18000b2b5  test    rax, rax
0x18000b2b8  jz      short loc_18000B2EC
0x18000b2ba  xor     r8d, r8d
0x18000b2bd  mov     edx, esi
0x18000b2bf  mov     [rsp+40h], r8
0x18000b2c4  lea     rcx, [rsp+2A0h+var_250]
0x18000b2c9  mov     [rsp+2A0h+var_268], rcx
0x18000b2ce  mov     dword ptr [rsp+2A0h+var_270], r8d
0x18000b2d3  mov     word ptr [rsp+2A0h+var_278], si
0x18000b2d8  mov     [rsp+2A0h+ArgList], r8
0x18000b2dd  mov     r9d, 400h
0x18000b2e3  mov     rcx, rbx
0x18000b2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2eb  nop
0x18000b2ec  lea     rcx, [rsp+2A0h+var_248]
0x18000b2f1  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x18000b2f6  nop
0x18000b2f7  lea     rcx, [rsp+2A0h+var_238]
0x18000b2fc  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?HolderDeregisterEventSource@@YAX0@Z$0A@$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&HolderDeregisterEventSource(void *),0,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&HolderDeregisterEventSource(void *),0,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b301  mov     rcx, [rbp+1A0h+var_20]
0x18000b308  xor     rcx, rsp; StackCookie
0x18000b30b  call    __security_check_cookie
0x18000b310  add     rsp, 290h
0x18000b317  pop     rsi
0x18000b318  pop     rbx
0x18000b319  pop     rbp
0x18000b31a  retn
```
