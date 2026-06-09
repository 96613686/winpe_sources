# Windows::Internal::String::Initialize<ushort *>(ushort * const &,Windows::Internal::_StringDetail::dummy_t)

- ea: `0x18002a188`
- end: `0x18002a20f`
- name: `??$Initialize@PEAG@String@Internal@Windows@@QEAAJAEBQEAGUdummy_t@_StringDetail@12@@Z`
- size: `135`
- prototype: `__int64 __fastcall(HSTRING *, const WCHAR **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004b710`
- `0x18004de90`

## callees

- `0x18002a188`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a1e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a1e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002a1c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002a1c5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize<unsigned short *>(HSTRING *a1, const WCHAR **a2)
{
  const WCHAR *v3; // rcx
  unsigned __int64 v4; // rdx
  HRESULT v5; // ebx
  HSTRING v6; // rcx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  v3 = *a2;
  if ( *a2 )
  {
    string = 0;
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
    if ( v4 > 0xFFFFFFFF )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v5 = WindowsCreateString(v3, v4, &string);
      if ( v5 >= 0 )
      {
        v6 = *a1;
        *a1 = string;
        WindowsDeleteString(v6);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a188  mov     [rsp+arg_0], rbx
0x18002a18d  mov     [rsp+arg_10], rsi
0x18002a192  push    rdi
0x18002a193  sub     rsp, 20h
0x18002a197  mov     rdi, rcx
0x18002a19a  xor     esi, esi
0x18002a19c  mov     rcx, [rdx]; sourceString
0x18002a19f  test    rcx, rcx
0x18002a1a2  jz      short loc_18002A1F7
0x18002a1a4  mov     [rsp+28h+string], rsi
0x18002a1a9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a1ad  inc     rdx; length
0x18002a1b0  cmp     [rcx+rdx*2], si
0x18002a1b4  jnz     short loc_18002A1AD
0x18002a1b6  mov     eax, 0FFFFFFFFh
0x18002a1bb  cmp     rdx, rax
0x18002a1be  ja      short loc_18002A1F0
0x18002a1c0  lea     r8, [rsp+28h+string]; string
0x18002a1c5  call    cs:__imp_WindowsCreateString
0x18002a1cc  nop     dword ptr [rax+rax+00h]
0x18002a1d1  mov     ebx, eax
0x18002a1d3  test    eax, eax
0x18002a1d5  js      short loc_18002A1FC
0x18002a1d7  mov     rdx, [rsp+28h+string]
0x18002a1dc  mov     rcx, [rdi]; string
0x18002a1df  mov     [rdi], rdx
0x18002a1e2  call    cs:__imp_WindowsDeleteString
0x18002a1e9  nop     dword ptr [rax+rax+00h]
0x18002a1ee  jmp     short loc_18002A1FC
0x18002a1f0  mov     ebx, 80070216h
0x18002a1f5  jmp     short loc_18002A1FC
0x18002a1f7  mov     ebx, 80004003h
0x18002a1fc  mov     rsi, [rsp+28h+arg_10]
0x18002a201  mov     eax, ebx
0x18002a203  mov     rbx, [rsp+28h+arg_0]
0x18002a208  add     rsp, 20h
0x18002a20c  pop     rdi
0x18002a20d  retn
```
