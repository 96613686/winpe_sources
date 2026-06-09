# DynCreateURLMoniker(IMoniker *,ushort const *,IMoniker * *)

- ea: `0x14000ccf8`
- end: `0x14000cd96`
- name: `?DynCreateURLMoniker@@YAJPEAUIMoniker@@PEBGPEAPEAU1@@Z`
- size: `158`
- prototype: `__int64 __fastcall(struct IMoniker *, const unsigned __int16 *, struct IMoniker **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ccb8`

## callees

- `0x14000ccf8`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000cd66`
- `KERNEL32!GetProcAddress` at `0x14000cd66`
- `KERNEL32!LoadLibraryExW` at `0x14000cd2f`
- `KERNEL32!LoadLibraryExW` at `0x14000cd2f`
- `KERNEL32!GetLastError` at `0x14000cd48`
- `KERNEL32!GetLastError` at `0x14000cd48`

## string_xrefs

- `0x14000cd22`: `urlmon.dll`
- `0x14000cd5c`: `CreateURLMonikerEx`

## pseudocode

```c
signed int __fastcall DynCreateURLMoniker(struct IMoniker *a1, const unsigned __int16 *a2, struct IMoniker **a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  signed int result; // eax

  ProcAddress = (FARPROC)qword_14001E9C8;
  if ( qword_14001E9C8 )
    return ((__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, struct IMoniker **, __int64))ProcAddress)(
             0,
             a2,
             a3,
             1);
  Library = Global::g_hURLMON;
  if ( Global::g_hURLMON || (Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u), (Global::g_hURLMON = Library) != 0) )
  {
    ProcAddress = GetProcAddress(Library, "CreateURLMonikerEx");
    qword_14001E9C8 = (__int64)ProcAddress;
    if ( ProcAddress )
      return ((__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, struct IMoniker **, __int64))ProcAddress)(
               0,
               a2,
               a3,
               1);
  }
  byte_14001E9D0 = 1;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14000ccf8  mov     [rsp+arg_0], rbx
0x14000ccfd  push    rdi
0x14000ccfe  sub     rsp, 30h
0x14000cd02  mov     rax, cs:qword_14001E9C8
0x14000cd09  mov     rbx, r8
0x14000cd0c  mov     rdi, rdx
0x14000cd0f  test    rax, rax
0x14000cd12  jnz     short loc_14000CD78
0x14000cd14  mov     rax, cs:?g_hURLMON@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hURLMON
0x14000cd1b  test    rax, rax
0x14000cd1e  jnz     short loc_14000CD5C
0x14000cd20  xor     edx, edx; hFile
0x14000cd22  lea     rcx, aUrlmonDll; "urlmon.dll"
0x14000cd29  mov     r8d, 800h; dwFlags
0x14000cd2f  call    cs:__imp_LoadLibraryExW
0x14000cd35  mov     cs:?g_hURLMON@Global@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Global::g_hURLMON
0x14000cd3c  test    rax, rax
0x14000cd3f  jnz     short loc_14000CD5C
0x14000cd41  mov     cs:byte_14001E9D0, 1
0x14000cd48  call    cs:__imp_GetLastError
0x14000cd4e  test    eax, eax
0x14000cd50  jle     short loc_14000CD8B
0x14000cd52  movzx   eax, ax
0x14000cd55  or      eax, 80070000h
0x14000cd5a  jmp     short loc_14000CD8B
0x14000cd5c  lea     rdx, aCreateurlmonik; "CreateURLMonikerEx"
0x14000cd63  mov     rcx, rax; hModule
0x14000cd66  call    cs:__imp_GetProcAddress
0x14000cd6c  mov     cs:qword_14001E9C8, rax
0x14000cd73  test    rax, rax
0x14000cd76  jz      short loc_14000CD41
0x14000cd78  mov     r9d, 1
0x14000cd7e  mov     r8, rbx
0x14000cd81  mov     rdx, rdi
0x14000cd84  xor     ecx, ecx
0x14000cd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd8b  mov     rbx, [rsp+38h+arg_0]
0x14000cd90  add     rsp, 30h
0x14000cd94  pop     rdi
0x14000cd95  retn
```
