# LoadLibraryResource(HINSTANCE__ *,bool)

- ea: `0x18002dcc4`
- end: `0x18002dd7d`
- name: `?LoadLibraryResource@@YAPEAUHINSTANCE__@@PEAU1@_N@Z`
- size: `185`
- prototype: `HINSTANCE __fastcall(HINSTANCE, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180014ad0`

## callees

- `0x180009ffc`
- `0x18002dcc4`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002dd18`
- `msvcrt!wcsrchr` at `0x18002dd18`
- `KERNEL32!GetModuleFileNameW` at `0x18002dcfe`
- `KERNEL32!GetModuleFileNameW` at `0x18002dcfe`
- `KERNEL32!LoadLibraryExW` at `0x18002dd54`
- `KERNEL32!LoadLibraryExW` at `0x18002dd54`

## string_xrefs

- `0x18002dd2b`: `r.dll`

## pseudocode

```c
HINSTANCE __fastcall LoadLibraryResource(HINSTANCE a1)
{
  wchar_t *v1; // rax
  WCHAR Filename[272]; // [rsp+20h] [rbp-238h] BYREF

  Filename[264] = 0;
  if ( g_hInstancePersistMain
    && GetModuleFileNameW(g_hInstancePersistMain, Filename, 0x105u)
    && (v1 = wcsrchr(Filename, 0x2Eu)) != 0
    && (*(v1 - 1) = 0, (int)StringCchCatW(Filename, 0x109u, L"r.dll") >= 0) )
  {
    return LoadLibraryExW(Filename, 0, 8u);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18002dcc4  sub     rsp, 258h
0x18002dccb  mov     rax, cs:__security_cookie
0x18002dcd2  xor     rax, rsp
0x18002dcd5  mov     [rsp+258h+var_18], rax
0x18002dcdd  mov     rcx, cs:?g_hInstancePersistMain@@3PEAUHINSTANCE__@@EA; hModule
0x18002dce4  xor     eax, eax
0x18002dce6  mov     [rsp+258h+var_28], ax
0x18002dcee  test    rcx, rcx
0x18002dcf1  jz      short loc_18002DD62
0x18002dcf3  mov     r8d, 105h; nSize
0x18002dcf9  lea     rdx, [rsp+258h+Filename]; lpFilename
0x18002dcfe  call    cs:__imp_GetModuleFileNameW
0x18002dd05  nop     dword ptr [rax+rax+00h]
0x18002dd0a  test    eax, eax
0x18002dd0c  jz      short loc_18002DD62
0x18002dd0e  mov     edx, 2Eh ; '.'; Ch
0x18002dd13  lea     rcx, [rsp+258h+Filename]; Str
0x18002dd18  call    cs:__imp_wcsrchr
0x18002dd1f  nop     dword ptr [rax+rax+00h]
0x18002dd24  test    rax, rax
0x18002dd27  jz      short loc_18002DD62
0x18002dd29  xor     ecx, ecx
0x18002dd2b  lea     r8, aRDll; "r.dll"
0x18002dd32  mov     [rax-2], cx
0x18002dd36  mov     edx, 109h; unsigned __int64
0x18002dd3b  lea     rcx, [rsp+258h+Filename]; unsigned __int16 *
0x18002dd40  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dd45  test    eax, eax
0x18002dd47  js      short loc_18002DD62
0x18002dd49  xor     edx, edx; hFile
0x18002dd4b  lea     rcx, [rsp+258h+Filename]; lpLibFileName
0x18002dd50  lea     r8d, [rdx+8]; dwFlags
0x18002dd54  call    cs:__imp_LoadLibraryExW
0x18002dd5b  nop     dword ptr [rax+rax+00h]
0x18002dd60  jmp     short loc_18002DD64
0x18002dd62  xor     eax, eax
0x18002dd64  mov     rcx, [rsp+258h+var_18]
0x18002dd6c  xor     rcx, rsp; StackCookie
0x18002dd6f  call    __security_check_cookie
0x18002dd74  add     rsp, 258h
0x18002dd7b  retn
```
