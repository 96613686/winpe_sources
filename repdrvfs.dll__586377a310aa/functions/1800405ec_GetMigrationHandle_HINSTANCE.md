# GetMigrationHandle(HINSTANCE__ * &)

- ea: `0x1800405ec`
- end: `0x1800406bb`
- name: `?GetMigrationHandle@@YAJAEAPEAUHINSTANCE__@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041230`

## callees

- `0x180013f90`
- `0x1800405ec`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180040603`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180040603`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180040645`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004066b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800406a2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180040645`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004066b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800406a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180040623`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180040623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004062d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004068a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004062d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004068a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004067c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004067c`

## string_xrefs

- `0x18004064e`: `\migration\WmiMigrationPlugin.dll`

## pseudocode

```c
__int64 __fastcall GetMigrationHandle(HINSTANCE *a1)
{
  WCHAR *v2; // rax
  unsigned __int16 *v3; // rdi
  signed int v5; // eax
  signed int v6; // ebx
  HMODULE Library; // rax
  signed int LastError; // eax

  v2 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x24Cu);
  v3 = v2;
  if ( !v2 )
    return 2147749894LL;
  if ( GetSystemDirectoryW(v2, 0x105u) )
  {
    v6 = StringCchCatW(v3, 0x126u, L"\\migration\\WmiMigrationPlugin.dll");
    if ( v6 >= 0 )
    {
      Library = LoadLibraryExW(v3, 0, 0);
      *a1 = Library;
      if ( !Library )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  CWin32DefaultArena::WbemMemFree(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800405ec  mov     [rsp+arg_0], rbx
0x1800405f1  mov     [rsp+arg_8], rsi
0x1800405f6  push    rdi
0x1800405f7  sub     rsp, 20h
0x1800405fb  mov     rsi, rcx
0x1800405fe  mov     ecx, 24Ch
0x180040603  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180040609  mov     rdi, rax
0x18004060c  test    rax, rax
0x18004060f  jnz     short loc_18004061B
0x180040611  mov     eax, 80041006h
0x180040616  jmp     loc_1800406AB
0x18004061b  mov     edx, 105h; uSize
0x180040620  mov     rcx, rdi; lpBuffer
0x180040623  call    cs:__imp_GetSystemDirectoryW
0x180040629  test    eax, eax
0x18004062b  jnz     short loc_18004064E
0x18004062d  call    cs:__imp_GetLastError
0x180040633  mov     ebx, eax
0x180040635  test    eax, eax
0x180040637  jle     short loc_180040642
0x180040639  movzx   ebx, ax
0x18004063c  or      ebx, 80070000h
0x180040642  mov     rcx, rdi
0x180040645  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18004064b  nop
0x18004064c  jmp     short loc_1800406A9
0x18004064e  lea     r8, aMigrationWmimi; "\\migration\\WmiMigrationPlugin.dll"
0x180040655  mov     edx, 126h; unsigned __int64
0x18004065a  mov     rcx, rdi; unsigned __int16 *
0x18004065d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180040662  mov     ebx, eax
0x180040664  test    eax, eax
0x180040666  jns     short loc_180040674
0x180040668  mov     rcx, rdi
0x18004066b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180040671  nop
0x180040672  jmp     short loc_1800406A9
0x180040674  xor     r8d, r8d; dwFlags
0x180040677  xor     edx, edx; hFile
0x180040679  mov     rcx, rdi; lpLibFileName
0x18004067c  call    cs:__imp_LoadLibraryExW
0x180040682  mov     [rsi], rax
0x180040685  test    rax, rax
0x180040688  jnz     short loc_18004069F
0x18004068a  call    cs:__imp_GetLastError
0x180040690  mov     ebx, eax
0x180040692  test    eax, eax
0x180040694  jle     short loc_18004069F
0x180040696  movzx   ebx, ax
0x180040699  or      ebx, 80070000h
0x18004069f  mov     rcx, rdi
0x1800406a2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800406a8  nop
0x1800406a9  mov     eax, ebx
0x1800406ab  mov     rbx, [rsp+28h+arg_0]
0x1800406b0  mov     rsi, [rsp+28h+arg_8]
0x1800406b5  add     rsp, 20h
0x1800406b9  pop     rdi
0x1800406ba  retn
```
