# CCompRC::LoadLibrary(HINSTANCE__ * *)

- ea: `0x140012c84`
- end: `0x140012df3`
- name: `?LoadLibrary@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(CCompRC *__hidden this, HINSTANCE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400124f8`

## callees

- `0x14001281c`
- `0x140012c84`
- `0x140013200`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140012cca`
- `KERNEL32!GetLastError` at `0x140012cca`
- `KERNEL32!GetModuleFileNameW` at `0x140012cc0`
- `KERNEL32!GetModuleFileNameW` at `0x140012cc0`
- `ucrtbase_clr0400!wcscat_s` at `0x140012d9d`
- `ucrtbase_clr0400!wcscat_s` at `0x140012db5`
- `ucrtbase_clr0400!wcscat_s` at `0x140012d9d`
- `ucrtbase_clr0400!wcscat_s` at `0x140012db5`
- `mscoree!GetRequestedRuntimeInfo` at `0x140012d7c`
- `mscoree!GetRequestedRuntimeInfo` at `0x140012d7c`

## string_xrefs

- `0x140012d1d`: `mscorrc.dll`

## pseudocode

```c
__int64 __fastcall CCompRC::LoadLibrary(CCompRC *this, HINSTANCE *a2)
{
  unsigned int v4; // r9d
  signed int LastError; // ecx
  __int64 result; // rax
  unsigned int v7; // r9d
  int v8; // [rsp+60h] [rbp-278h] BYREF
  _BYTE v9[4]; // [rsp+64h] [rbp-274h] BYREF
  wchar_t Source[36]; // [rsp+68h] [rbp-270h] BYREF
  WCHAR Filename[264]; // [rsp+B0h] [rbp-228h] BYREF

  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    result = CCompRC::LoadLibraryHelper(this, a2, Filename, v4);
    if ( (_DWORD)result == -2147024882 )
    {
      return 2147942414LL;
    }
    else if ( (int)result < 0 && *((wchar_t **)this + 6) == L"mscorrc.dll" )
    {
      result = GetRequestedRuntimeInfo(0, L"v4.0.30319", 0, 0, 193, Filename, 260, v9, Source, 30, &v8);
      if ( (int)result >= 0 )
      {
        if ( v8 )
        {
          wcscat_s(Filename, 0x104u, Source);
          wcscat_s(Filename, 0x104u, L"\\");
        }
        return CCompRC::LoadLibraryHelper(this, a2, Filename, v7);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      result = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
    else
    {
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012c84  mov     [rsp+arg_10], rbx
0x140012c89  mov     [rsp+arg_18], rsi
0x140012c8e  push    rdi
0x140012c8f  sub     rsp, 2D0h
0x140012c96  mov     rax, cs:__security_cookie
0x140012c9d  xor     rax, rsp
0x140012ca0  mov     [rsp+2D8h+var_18], rax
0x140012ca8  mov     rdi, rdx
0x140012cab  mov     rbx, rcx
0x140012cae  mov     esi, 104h
0x140012cb3  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x140012cbb  mov     r8d, esi; nSize
0x140012cbe  xor     ecx, ecx; hModule
0x140012cc0  call    cs:__imp_GetModuleFileNameW
0x140012cc6  test    eax, eax
0x140012cc8  jnz     short loc_140012CF2
0x140012cca  call    cs:__imp_GetLastError
0x140012cd0  mov     ecx, eax
0x140012cd2  test    eax, eax
0x140012cd4  jnz     short loc_140012CE0
0x140012cd6  mov     eax, 80004005h
0x140012cdb  jmp     loc_140012DCE
0x140012ce0  movzx   eax, cx
0x140012ce3  or      eax, 80070000h
0x140012ce8  test    ecx, ecx
0x140012cea  cmovle  eax, ecx
0x140012ced  jmp     loc_140012DCE
0x140012cf2  lea     r8, [rsp+2D8h+Filename]; unsigned __int16 *
0x140012cfa  mov     rdx, rdi; HINSTANCE *
0x140012cfd  mov     rcx, rbx; this
0x140012d00  call    ?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z; CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)
0x140012d05  mov     ecx, 8007000Eh
0x140012d0a  cmp     eax, ecx
0x140012d0c  jnz     short loc_140012D15
0x140012d0e  mov     eax, ecx
0x140012d10  jmp     loc_140012DCE
0x140012d15  test    eax, eax
0x140012d17  jns     loc_140012DCE
0x140012d1d  lea     rcx, aMscorrcDll; "mscorrc.dll"
0x140012d24  cmp     [rbx+30h], rcx
0x140012d28  jnz     loc_140012DCE
0x140012d2e  lea     rax, [rsp+2D8h+var_278]
0x140012d33  xor     r9d, r9d
0x140012d36  mov     [rsp+2D8h+var_288], rax
0x140012d3b  lea     rdx, aV4030319; "v4.0.30319"
0x140012d42  mov     [rsp+2D8h+var_290], 1Eh
0x140012d4a  lea     rax, [rsp+2D8h+Source]
0x140012d4f  mov     [rsp+2D8h+var_298], rax
0x140012d54  xor     r8d, r8d
0x140012d57  lea     rax, [rsp+2D8h+var_274]
0x140012d5c  xor     ecx, ecx
0x140012d5e  mov     [rsp+2D8h+var_2A0], rax
0x140012d63  lea     rax, [rsp+2D8h+Filename]
0x140012d6b  mov     [rsp+2D8h+var_2A8], esi
0x140012d6f  mov     [rsp+2D8h+var_2B0], rax
0x140012d74  mov     [rsp+2D8h+var_2B8], 0C1h
0x140012d7c  call    cs:__imp_GetRequestedRuntimeInfo
0x140012d82  test    eax, eax
0x140012d84  js      short loc_140012DCE
0x140012d86  cmp     [rsp+2D8h+var_278], 0
0x140012d8b  jbe     short loc_140012DBB
0x140012d8d  lea     r8, [rsp+2D8h+Source]; Source
0x140012d92  mov     rdx, rsi; SizeInWords
0x140012d95  lea     rcx, [rsp+2D8h+Filename]; Destination
0x140012d9d  call    cs:__imp_wcscat_s
0x140012da3  lea     r8, asc_14001F158; "\\"
0x140012daa  mov     rdx, rsi; SizeInWords
0x140012dad  lea     rcx, [rsp+2D8h+Filename]; Destination
0x140012db5  call    cs:__imp_wcscat_s
0x140012dbb  lea     r8, [rsp+2D8h+Filename]; unsigned __int16 *
0x140012dc3  mov     rdx, rdi; HINSTANCE *
0x140012dc6  mov     rcx, rbx; this
0x140012dc9  call    ?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z; CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)
0x140012dce  mov     rcx, [rsp+2D8h+var_18]
0x140012dd6  xor     rcx, rsp; StackCookie
0x140012dd9  call    __security_check_cookie
0x140012dde  lea     r11, [rsp+2D8h+var_8]
0x140012de6  mov     rbx, [r11+20h]
0x140012dea  mov     rsi, [r11+28h]
0x140012dee  mov     rsp, r11
0x140012df1  pop     rdi
0x140012df2  retn
```
