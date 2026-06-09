# DwzLoadIcon(ushort const *,HICON__ * *)

- ea: `0x140041a90`
- end: `0x140041c4e`
- name: `?DwzLoadIcon@@YAJPEBGPEAPEAUHICON__@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HICON *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000ecf0`
- `0x140028060`

## callees

- `0x140020420`
- `0x140041a90`
- `0x140042020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140041b78`
- `KERNEL32!GetLastError` at `0x140041bb7`
- `KERNEL32!GetLastError` at `0x140041b78`
- `KERNEL32!GetLastError` at `0x140041bb7`
- `KERNEL32!FreeLibrary` at `0x140041bfc`
- `KERNEL32!FreeLibrary` at `0x140041bfc`
- `KERNEL32!LoadLibraryExW` at `0x140041b0f`
- `KERNEL32!LoadLibraryExW` at `0x140041b0f`
- `USER32!LoadImageW` at `0x140041b5a`
- `USER32!LoadImageW` at `0x140041b5a`
- `msvcrt!_wtol` at `0x140041b31`
- `msvcrt!_wtol` at `0x140041b31`
- `OLEAUT32!__imp_SysFreeString` at `0x140041c15`
- `OLEAUT32!__imp_SysFreeString` at `0x140041c2e`
- `OLEAUT32!__imp_SysFreeString` at `0x140041c15`
- `OLEAUT32!__imp_SysFreeString` at `0x140041c2e`

## pseudocode

```c
__int64 __fastcall DwzLoadIcon(const unsigned __int16 *a1, HICON *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  HMODULE Library; // rsi
  unsigned __int16 v6; // ax
  HICON ImageW; // rax
  signed int LastError; // eax
  signed int v9; // eax
  LPCWSTR lpLibFileName; // [rsp+50h] [rbp+18h] BYREF
  wchar_t *String; // [rsp+58h] [rbp+20h] BYREF

  lpLibFileName = 0;
  String = 0;
  v3 = DwzParseLocaleString(a1, (unsigned __int16 **)&lpLibFileName, &String);
  v4 = v3;
  if ( v3 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadIcon", 499, v3);
    goto LABEL_16;
  }
  if ( v3 == 1 )
  {
    v4 = -2147024809;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadIcon", 503, -2147024809);
    goto LABEL_16;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 2u);
  if ( (unsigned __int64)Library - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v6 = _wtol(String);
    ImageW = (HICON)LoadImageW(Library, (LPCWSTR)v6, 1u, 0, 0, 0x40u);
    if ( (unsigned __int64)ImageW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadIcon", 519, v4);
    }
    else
    {
      *a2 = ImageW;
    }
LABEL_15:
    FreeLibrary(Library);
    goto LABEL_16;
  }
  v9 = GetLastError();
  v4 = v9;
  if ( v9 > 0 )
    v4 = (unsigned __int16)v9 | 0x80070000;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadIcon", 507, v4);
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
0x140041a90  mov     rax, rsp
0x140041a93  mov     [rax+8], rbx
0x140041a97  mov     [rax+10h], rsi
0x140041a9b  push    r15
0x140041a9d  sub     rsp, 30h
0x140041aa1  mov     r15, rdx
0x140041aa4  mov     qword ptr [rax+18h], 0
0x140041aac  lea     rdx, [rax+18h]; unsigned __int16 **
0x140041ab0  mov     qword ptr [rax+20h], 0
0x140041ab8  lea     r8, [rax+20h]; unsigned __int16 **
0x140041abc  call    ?DwzParseLocaleString@@YAJPEBGPEAPEAG1@Z; DwzParseLocaleString(ushort const *,ushort * *,ushort * *)
0x140041ac1  mov     ebx, eax
0x140041ac3  test    eax, eax
0x140041ac5  jns     short loc_140041AEE
0x140041ac7  mov     [rsp+38h+cy], eax
0x140041acb  mov     r9d, 1F3h
0x140041ad1  lea     r8, aDwzloadicon; "DwzLoadIcon"
0x140041ad8  mov     ecx, 1; Level
0x140041add  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041ae4  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041ae9  jmp     loc_140041C08
0x140041aee  cmp     eax, 1
0x140041af1  jnz     short loc_140041B04
0x140041af3  mov     ebx, 80070057h
0x140041af8  mov     r9d, 1F7h
0x140041afe  mov     [rsp+38h+cy], ebx
0x140041b02  jmp     short loc_140041AD1
0x140041b04  mov     rcx, [rsp+38h+lpLibFileName]; lpLibFileName
0x140041b09  xor     edx, edx; hFile
0x140041b0b  lea     r8d, [rdx+2]; dwFlags
0x140041b0f  call    cs:__imp_LoadLibraryExW
0x140041b16  nop     dword ptr [rax+rax+00h]
0x140041b1b  mov     rsi, rax
0x140041b1e  lea     rcx, [rax-1]
0x140041b22  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140041b26  ja      loc_140041BB7
0x140041b2c  mov     rcx, [rsp+38h+String]; String
0x140041b31  call    cs:__imp__wtol
0x140041b38  nop     dword ptr [rax+rax+00h]
0x140041b3d  xor     r9d, r9d; cx
0x140041b40  mov     [rsp+38h+fuLoad], 40h ; '@'; fuLoad
0x140041b48  movzx   edx, ax; name
0x140041b4b  mov     rcx, rsi; hInst
0x140041b4e  mov     [rsp+38h+cy], 0; cy
0x140041b56  lea     r8d, [r9+1]; type
0x140041b5a  call    cs:__imp_LoadImageW
0x140041b61  nop     dword ptr [rax+rax+00h]
0x140041b66  lea     rcx, [rax-1]
0x140041b6a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140041b6e  ja      short loc_140041B78
0x140041b70  mov     [r15], rax
0x140041b73  jmp     loc_140041BF9
0x140041b78  call    cs:__imp_GetLastError
0x140041b7f  nop     dword ptr [rax+rax+00h]
0x140041b84  mov     ebx, eax
0x140041b86  test    eax, eax
0x140041b88  jle     short loc_140041B93
0x140041b8a  movzx   ebx, ax
0x140041b8d  or      ebx, 80070000h
0x140041b93  mov     r9d, 207h
0x140041b99  mov     [rsp+38h+cy], ebx
0x140041b9d  lea     r8, aDwzloadicon; "DwzLoadIcon"
0x140041ba4  mov     ecx, 1; Level
0x140041ba9  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041bb0  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041bb5  jmp     short loc_140041BF9
0x140041bb7  call    cs:__imp_GetLastError
0x140041bbe  nop     dword ptr [rax+rax+00h]
0x140041bc3  mov     ebx, eax
0x140041bc5  test    eax, eax
0x140041bc7  jle     short loc_140041BD2
0x140041bc9  movzx   ebx, ax
0x140041bcc  or      ebx, 80070000h
0x140041bd2  mov     r9d, 1FBh
0x140041bd8  mov     [rsp+38h+cy], ebx
0x140041bdc  lea     r8, aDwzloadicon; "DwzLoadIcon"
0x140041be3  mov     ecx, 1; Level
0x140041be8  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041bef  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041bf4  test    rsi, rsi
0x140041bf7  jz      short loc_140041C08
0x140041bf9  mov     rcx, rsi; hLibModule
0x140041bfc  call    cs:__imp_FreeLibrary
0x140041c03  nop     dword ptr [rax+rax+00h]
0x140041c08  cmp     [rsp+38h+lpLibFileName], 0
0x140041c0e  jz      short loc_140041C21
0x140041c10  mov     rcx, [rsp+38h+lpLibFileName]; bstrString
0x140041c15  call    cs:__imp_SysFreeString
0x140041c1c  nop     dword ptr [rax+rax+00h]
0x140041c21  cmp     [rsp+38h+String], 0
0x140041c27  jz      short loc_140041C3A
0x140041c29  mov     rcx, [rsp+38h+String]; bstrString
0x140041c2e  call    cs:__imp_SysFreeString
0x140041c35  nop     dword ptr [rax+rax+00h]
0x140041c3a  mov     rsi, [rsp+38h+arg_8]
0x140041c3f  mov     eax, ebx
0x140041c41  mov     rbx, [rsp+38h+arg_0]
0x140041c46  add     rsp, 30h
0x140041c4a  pop     r15
0x140041c4c  retn
```
