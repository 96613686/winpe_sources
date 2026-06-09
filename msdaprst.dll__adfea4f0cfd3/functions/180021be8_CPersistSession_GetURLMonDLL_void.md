# CPersistSession::GetURLMonDLL(void)

- ea: `0x180021be8`
- end: `0x180021caf`
- name: `?GetURLMonDLL@CPersistSession@@AEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(CPersistSession *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022240`
- `0x180022d50`

## callees

- `0x180021be8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180021c43`
- `KERNEL32!GetProcAddress` at `0x180021c65`
- `KERNEL32!GetProcAddress` at `0x180021c87`
- `KERNEL32!GetProcAddress` at `0x180021c43`
- `KERNEL32!GetProcAddress` at `0x180021c65`
- `KERNEL32!GetProcAddress` at `0x180021c87`
- `KERNEL32!GetLastError` at `0x180021c1f`
- `KERNEL32!GetLastError` at `0x180021c1f`
- `KERNEL32!LoadLibraryExW` at `0x180021c0b`
- `KERNEL32!LoadLibraryExW` at `0x180021c0b`

## string_xrefs

- `0x180021bfe`: `urlmon.dll`
- `0x180021c5b`: `CreateURLMoniker`
- `0x180021c7d`: `CreateAsyncBindCtx`

## pseudocode

```c
signed int __fastcall CPersistSession::GetURLMonDLL(CPersistSession *this)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed int result; // eax

  if ( CPersistSession::m_hURLMON )
    return 0;
  Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    CPersistSession::m_pIsValidURL = (int (*)(struct IBindCtx *, const unsigned __int16 *, unsigned int))GetProcAddress(Library, "IsValidURL");
    if ( CPersistSession::m_pIsValidURL )
    {
      CPersistSession::m_pCreateURLMoniker = (int (*)(struct IMoniker *, unsigned __int16 *, struct IMoniker **))GetProcAddress(v2, "CreateURLMoniker");
      if ( CPersistSession::m_pCreateURLMoniker )
      {
        CPersistSession::m_pCreateAsyncBindCtx = (int (*)(unsigned int, struct IBindStatusCallback *, struct IEnumFORMATETC *, struct IBindCtx **))GetProcAddress(v2, "CreateAsyncBindCtx");
        if ( CPersistSession::m_pCreateAsyncBindCtx )
        {
          CPersistSession::m_hURLMON = v2;
          return 0;
        }
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180021be8  push    rbx
0x180021bea  sub     rsp, 20h
0x180021bee  cmp     cs:?m_hURLMON@CPersistSession@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CPersistSession::m_hURLMON
0x180021bf6  jnz     loc_180021CA6
0x180021bfc  xor     edx, edx; hFile
0x180021bfe  lea     rcx, aUrlmonDll; "urlmon.dll"
0x180021c05  mov     r8d, 800h; dwFlags
0x180021c0b  call    cs:__imp_LoadLibraryExW
0x180021c12  nop     dword ptr [rax+rax+00h]
0x180021c17  mov     rbx, rax
0x180021c1a  test    rax, rax
0x180021c1d  jnz     short loc_180021C39
0x180021c1f  call    cs:__imp_GetLastError
0x180021c26  nop     dword ptr [rax+rax+00h]
0x180021c2b  test    eax, eax
0x180021c2d  jle     short loc_180021CA8
0x180021c2f  movzx   eax, ax
0x180021c32  or      eax, 80070000h
0x180021c37  jmp     short loc_180021CA8
0x180021c39  lea     rdx, aIsvalidurl; "IsValidURL"
0x180021c40  mov     rcx, rbx; hModule
0x180021c43  call    cs:__imp_GetProcAddress
0x180021c4a  nop     dword ptr [rax+rax+00h]
0x180021c4f  mov     cs:?m_pIsValidURL@CPersistSession@@0P6AJPEAUIBindCtx@@PEBGK@ZEA, rax; long (*CPersistSession::m_pIsValidURL)(IBindCtx *,ushort const *,ulong)
0x180021c56  test    rax, rax
0x180021c59  jz      short loc_180021C1F
0x180021c5b  lea     rdx, aCreateurlmonik; "CreateURLMoniker"
0x180021c62  mov     rcx, rbx; hModule
0x180021c65  call    cs:__imp_GetProcAddress
0x180021c6c  nop     dword ptr [rax+rax+00h]
0x180021c71  mov     cs:?m_pCreateURLMoniker@CPersistSession@@0P6AJPEAUIMoniker@@PEAGPEAPEAU2@@ZEA, rax; long (*CPersistSession::m_pCreateURLMoniker)(IMoniker *,ushort *,IMoniker * *)
0x180021c78  test    rax, rax
0x180021c7b  jz      short loc_180021C1F
0x180021c7d  lea     rdx, aCreateasyncbin; "CreateAsyncBindCtx"
0x180021c84  mov     rcx, rbx; hModule
0x180021c87  call    cs:__imp_GetProcAddress
0x180021c8e  nop     dword ptr [rax+rax+00h]
0x180021c93  mov     cs:?m_pCreateAsyncBindCtx@CPersistSession@@0P6AJKPEAUIBindStatusCallback@@PEAUIEnumFORMATETC@@PEAPEAUIBindCtx@@@ZEA, rax; long (*CPersistSession::m_pCreateAsyncBindCtx)(ulong,IBindStatusCallback *,IEnumFORMATETC *,IBindCtx * *)
0x180021c9a  test    rax, rax
0x180021c9d  jz      short loc_180021C1F
0x180021c9f  mov     cs:?m_hURLMON@CPersistSession@@0PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * CPersistSession::m_hURLMON
0x180021ca6  xor     eax, eax
0x180021ca8  add     rsp, 20h
0x180021cac  pop     rbx
0x180021cad  retn
```
