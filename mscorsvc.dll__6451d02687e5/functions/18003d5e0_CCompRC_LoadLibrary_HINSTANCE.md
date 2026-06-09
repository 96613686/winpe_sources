# CCompRC::LoadLibrary(HINSTANCE__ * *)

- ea: `0x18003d5e0`
- end: `0x18003d754`
- name: `?LoadLibrary@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(CCompRC *__hidden this, HINSTANCE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ce54`

## callees

- `0x18003d178`
- `0x18003d5e0`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18003d621`
- `KERNEL32!GetModuleFileNameW` at `0x18003d621`
- `KERNEL32!GetLastError` at `0x18003d62b`
- `KERNEL32!GetLastError` at `0x18003d62b`
- `ucrtbase_clr0400!wcscat_s` at `0x18003d6fe`
- `ucrtbase_clr0400!wcscat_s` at `0x18003d716`
- `ucrtbase_clr0400!wcscat_s` at `0x18003d6fe`
- `ucrtbase_clr0400!wcscat_s` at `0x18003d716`
- `mscoree!GetRequestedRuntimeInfo` at `0x18003d6dd`
- `mscoree!GetRequestedRuntimeInfo` at `0x18003d6dd`

## string_xrefs

- `0x18003d67e`: `mscorrc.dll`

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

  if ( GetModuleFileNameW(g_hInst, Filename, 0x104u) )
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
0x18003d5e0  mov     [rsp+arg_10], rbx
0x18003d5e5  mov     [rsp+arg_18], rsi
0x18003d5ea  push    rdi
0x18003d5eb  sub     rsp, 2D0h
0x18003d5f2  mov     rax, cs:__security_cookie
0x18003d5f9  xor     rax, rsp
0x18003d5fc  mov     [rsp+2D8h+var_18], rax
0x18003d604  mov     rdi, rdx
0x18003d607  mov     rbx, rcx
0x18003d60a  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18003d611  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x18003d619  mov     esi, 104h
0x18003d61e  mov     r8d, esi; nSize
0x18003d621  call    cs:__imp_GetModuleFileNameW
0x18003d627  test    eax, eax
0x18003d629  jnz     short loc_18003D653
0x18003d62b  call    cs:__imp_GetLastError
0x18003d631  mov     ecx, eax
0x18003d633  test    eax, eax
0x18003d635  jnz     short loc_18003D641
0x18003d637  mov     eax, 80004005h
0x18003d63c  jmp     loc_18003D72F
0x18003d641  movzx   eax, cx
0x18003d644  or      eax, 80070000h
0x18003d649  test    ecx, ecx
0x18003d64b  cmovle  eax, ecx
0x18003d64e  jmp     loc_18003D72F
0x18003d653  lea     r8, [rsp+2D8h+Filename]; unsigned __int16 *
0x18003d65b  mov     rdx, rdi; HINSTANCE *
0x18003d65e  mov     rcx, rbx; this
0x18003d661  call    ?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z; CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)
0x18003d666  mov     ecx, 8007000Eh
0x18003d66b  cmp     eax, ecx
0x18003d66d  jnz     short loc_18003D676
0x18003d66f  mov     eax, ecx
0x18003d671  jmp     loc_18003D72F
0x18003d676  test    eax, eax
0x18003d678  jns     loc_18003D72F
0x18003d67e  lea     rcx, aMscorrcDll; "mscorrc.dll"
0x18003d685  cmp     [rbx+30h], rcx
0x18003d689  jnz     loc_18003D72F
0x18003d68f  lea     rax, [rsp+2D8h+var_278]
0x18003d694  xor     r9d, r9d
0x18003d697  mov     [rsp+2D8h+var_288], rax
0x18003d69c  lea     rdx, aV4030319; "v4.0.30319"
0x18003d6a3  mov     [rsp+2D8h+var_290], 1Eh
0x18003d6ab  lea     rax, [rsp+2D8h+Source]
0x18003d6b0  mov     [rsp+2D8h+var_298], rax
0x18003d6b5  xor     r8d, r8d
0x18003d6b8  lea     rax, [rsp+2D8h+var_274]
0x18003d6bd  xor     ecx, ecx
0x18003d6bf  mov     [rsp+2D8h+var_2A0], rax
0x18003d6c4  lea     rax, [rsp+2D8h+Filename]
0x18003d6cc  mov     [rsp+2D8h+var_2A8], esi
0x18003d6d0  mov     [rsp+2D8h+var_2B0], rax
0x18003d6d5  mov     [rsp+2D8h+var_2B8], 0C1h
0x18003d6dd  call    cs:__imp_GetRequestedRuntimeInfo
0x18003d6e3  test    eax, eax
0x18003d6e5  js      short loc_18003D72F
0x18003d6e7  cmp     [rsp+2D8h+var_278], 0
0x18003d6ec  jbe     short loc_18003D71C
0x18003d6ee  lea     r8, [rsp+2D8h+Source]; Source
0x18003d6f3  mov     rdx, rsi; SizeInWords
0x18003d6f6  lea     rcx, [rsp+2D8h+Filename]; Destination
0x18003d6fe  call    cs:__imp_wcscat_s
0x18003d704  lea     r8, asc_180049544; "\\"
0x18003d70b  mov     rdx, rsi; SizeInWords
0x18003d70e  lea     rcx, [rsp+2D8h+Filename]; Destination
0x18003d716  call    cs:__imp_wcscat_s
0x18003d71c  lea     r8, [rsp+2D8h+Filename]; unsigned __int16 *
0x18003d724  mov     rdx, rdi; HINSTANCE *
0x18003d727  mov     rcx, rbx; this
0x18003d72a  call    ?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z; CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)
0x18003d72f  mov     rcx, [rsp+2D8h+var_18]
0x18003d737  xor     rcx, rsp; StackCookie
0x18003d73a  call    __security_check_cookie
0x18003d73f  lea     r11, [rsp+2D8h+var_8]
0x18003d747  mov     rbx, [r11+20h]
0x18003d74b  mov     rsi, [r11+28h]
0x18003d74f  mov     rsp, r11
0x18003d752  pop     rdi
0x18003d753  retn
```
