# DwzLoadSmallIcon(ushort const *,HICON__ * *)

- ea: `0x140041e30`
- end: `0x140042019`
- name: `?DwzLoadSmallIcon@@YAJPEBGPEAPEAUHICON__@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HICON *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140018f6c`
- `0x14002d660`
- `0x140030410`

## callees

- `0x140020420`
- `0x140041e30`
- `0x140042020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140041f40`
- `KERNEL32!GetLastError` at `0x140041f7f`
- `KERNEL32!GetLastError` at `0x140041f40`
- `KERNEL32!GetLastError` at `0x140041f7f`
- `KERNEL32!FreeLibrary` at `0x140041fc4`
- `KERNEL32!FreeLibrary` at `0x140041fc4`
- `KERNEL32!LoadLibraryExW` at `0x140041eb2`
- `KERNEL32!LoadLibraryExW` at `0x140041eb2`
- `USER32!LoadImageW` at `0x140041f21`
- `USER32!LoadImageW` at `0x140041f21`
- `USER32!GetSystemMetrics` at `0x140041ed4`
- `USER32!GetSystemMetrics` at `0x140041ee7`
- `USER32!GetSystemMetrics` at `0x140041ed4`
- `USER32!GetSystemMetrics` at `0x140041ee7`
- `msvcrt!_wtol` at `0x140041efa`
- `msvcrt!_wtol` at `0x140041efa`
- `OLEAUT32!__imp_SysFreeString` at `0x140041fdd`
- `OLEAUT32!__imp_SysFreeString` at `0x140041ff6`
- `OLEAUT32!__imp_SysFreeString` at `0x140041fdd`
- `OLEAUT32!__imp_SysFreeString` at `0x140041ff6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DwzLoadSmallIcon(const unsigned __int16 *a1, HICON *a2)
{
  int v3; // eax
  unsigned int v4; // esi
  HMODULE Library; // r14
  int cy; // edi
  int SystemMetrics; // ebx
  unsigned __int16 v8; // ax
  HICON ImageW; // rax
  signed int LastError; // eax
  signed int v11; // eax
  LPCWSTR lpLibFileName; // [rsp+60h] [rbp+18h] BYREF
  wchar_t *String; // [rsp+68h] [rbp+20h] BYREF

  lpLibFileName = 0;
  String = 0;
  v3 = DwzParseLocaleString(a1, (unsigned __int16 **)&lpLibFileName, &String);
  v4 = v3;
  if ( v3 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadSmallIcon", 430, v3);
    goto LABEL_16;
  }
  if ( v3 == 1 )
  {
    v4 = -2147024809;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadSmallIcon", 434, -2147024809);
    goto LABEL_16;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 2u);
  if ( (unsigned __int64)Library - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    cy = GetSystemMetrics(50);
    SystemMetrics = GetSystemMetrics(49);
    v8 = _wtol(String);
    ImageW = (HICON)LoadImageW(Library, (LPCWSTR)v8, 1u, SystemMetrics, cy, 0);
    if ( (unsigned __int64)ImageW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadSmallIcon", 450, v4);
    }
    else
    {
      *a2 = ImageW;
    }
LABEL_15:
    FreeLibrary(Library);
    goto LABEL_16;
  }
  v11 = GetLastError();
  v4 = v11;
  if ( v11 > 0 )
    v4 = (unsigned __int16)v11 | 0x80070000;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadSmallIcon", 438, v4);
  if ( Library )
    goto LABEL_15;
LABEL_16:
  if ( lpLibFileName )
    SysFreeString((BSTR)lpLibFileName);
  if ( String )
    SysFreeString(String);
  return v4;
}

```

## disassembly

```asm
0x140041e30  mov     rax, rsp
0x140041e33  mov     [rax+8], rbx
0x140041e37  mov     [rax+10h], rsi
0x140041e3b  push    rdi
0x140041e3c  push    r13
0x140041e3e  push    r14
0x140041e40  sub     rsp, 30h
0x140041e44  mov     r13, rdx
0x140041e47  mov     qword ptr [rax+18h], 0
0x140041e4f  lea     rdx, [rax+18h]; unsigned __int16 **
0x140041e53  mov     qword ptr [rax+20h], 0
0x140041e5b  lea     r8, [rax+20h]; unsigned __int16 **
0x140041e5f  call    ?DwzParseLocaleString@@YAJPEBGPEAPEAG1@Z; DwzParseLocaleString(ushort const *,ushort * *,ushort * *)
0x140041e64  mov     esi, eax
0x140041e66  test    eax, eax
0x140041e68  jns     short loc_140041E91
0x140041e6a  mov     [rsp+48h+cy], eax
0x140041e6e  mov     r9d, 1AEh
0x140041e74  lea     r8, aDwzloadsmallic; "DwzLoadSmallIcon"
0x140041e7b  mov     ecx, 1; Level
0x140041e80  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041e87  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041e8c  jmp     loc_140041FD0
0x140041e91  cmp     eax, 1
0x140041e94  jnz     short loc_140041EA7
0x140041e96  mov     esi, 80070057h
0x140041e9b  mov     r9d, 1B2h
0x140041ea1  mov     [rsp+48h+cy], esi
0x140041ea5  jmp     short loc_140041E74
0x140041ea7  mov     rcx, [rsp+48h+lpLibFileName]; lpLibFileName
0x140041eac  xor     edx, edx; hFile
0x140041eae  lea     r8d, [rdx+2]; dwFlags
0x140041eb2  call    cs:__imp_LoadLibraryExW
0x140041eb9  nop     dword ptr [rax+rax+00h]
0x140041ebe  mov     r14, rax
0x140041ec1  lea     rcx, [rax-1]
0x140041ec5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140041ec9  ja      loc_140041F7F
0x140041ecf  mov     ecx, 32h ; '2'; nIndex
0x140041ed4  call    cs:__imp_GetSystemMetrics
0x140041edb  nop     dword ptr [rax+rax+00h]
0x140041ee0  mov     ecx, 31h ; '1'; nIndex
0x140041ee5  mov     edi, eax
0x140041ee7  call    cs:__imp_GetSystemMetrics
0x140041eee  nop     dword ptr [rax+rax+00h]
0x140041ef3  mov     rcx, [rsp+48h+String]; String
0x140041ef8  mov     ebx, eax
0x140041efa  call    cs:__imp__wtol
0x140041f01  nop     dword ptr [rax+rax+00h]
0x140041f06  mov     [rsp+48h+fuLoad], 0; fuLoad
0x140041f0e  mov     r9d, ebx; cx
0x140041f11  movzx   edx, ax; name
0x140041f14  mov     r8d, 1; type
0x140041f1a  mov     rcx, r14; hInst
0x140041f1d  mov     [rsp+48h+cy], edi; cy
0x140041f21  call    cs:__imp_LoadImageW
0x140041f28  nop     dword ptr [rax+rax+00h]
0x140041f2d  lea     rcx, [rax-1]
0x140041f31  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140041f35  ja      short loc_140041F40
0x140041f37  mov     [r13+0], rax
0x140041f3b  jmp     loc_140041FC1
0x140041f40  call    cs:__imp_GetLastError
0x140041f47  nop     dword ptr [rax+rax+00h]
0x140041f4c  mov     esi, eax
0x140041f4e  test    eax, eax
0x140041f50  jle     short loc_140041F5B
0x140041f52  movzx   esi, ax
0x140041f55  or      esi, 80070000h
0x140041f5b  mov     r9d, 1C2h
0x140041f61  mov     [rsp+48h+cy], esi
0x140041f65  lea     r8, aDwzloadsmallic; "DwzLoadSmallIcon"
0x140041f6c  mov     ecx, 1; Level
0x140041f71  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041f78  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041f7d  jmp     short loc_140041FC1
0x140041f7f  call    cs:__imp_GetLastError
0x140041f86  nop     dword ptr [rax+rax+00h]
0x140041f8b  mov     esi, eax
0x140041f8d  test    eax, eax
0x140041f8f  jle     short loc_140041F9A
0x140041f91  movzx   esi, ax
0x140041f94  or      esi, 80070000h
0x140041f9a  mov     r9d, 1B6h
0x140041fa0  mov     [rsp+48h+cy], esi
0x140041fa4  lea     r8, aDwzloadsmallic; "DwzLoadSmallIcon"
0x140041fab  mov     ecx, 1; Level
0x140041fb0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041fb7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041fbc  test    r14, r14
0x140041fbf  jz      short loc_140041FD0
0x140041fc1  mov     rcx, r14; hLibModule
0x140041fc4  call    cs:__imp_FreeLibrary
0x140041fcb  nop     dword ptr [rax+rax+00h]
0x140041fd0  cmp     [rsp+48h+lpLibFileName], 0
0x140041fd6  jz      short loc_140041FE9
0x140041fd8  mov     rcx, [rsp+48h+lpLibFileName]; bstrString
0x140041fdd  call    cs:__imp_SysFreeString
0x140041fe4  nop     dword ptr [rax+rax+00h]
0x140041fe9  cmp     [rsp+48h+String], 0
0x140041fef  jz      short loc_140042002
0x140041ff1  mov     rcx, [rsp+48h+String]; bstrString
0x140041ff6  call    cs:__imp_SysFreeString
0x140041ffd  nop     dword ptr [rax+rax+00h]
0x140042002  mov     rbx, [rsp+48h+arg_0]
0x140042007  mov     eax, esi
0x140042009  mov     rsi, [rsp+48h+arg_8]
0x14004200e  add     rsp, 30h
0x140042012  pop     r14
0x140042014  pop     r13
0x140042016  pop     rdi
0x140042017  retn
```
