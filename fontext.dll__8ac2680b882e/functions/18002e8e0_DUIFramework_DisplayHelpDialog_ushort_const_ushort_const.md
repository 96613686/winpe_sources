# DUIFramework_DisplayHelpDialog(ushort const *,ushort const *)

- ea: `0x18002e8e0`
- end: `0x18002ea0e`
- name: `?DUIFramework_DisplayHelpDialog@@YAJPEBG0@Z`
- size: `302`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020200`

## callees

- `0x180006598`
- `0x180006624`
- `0x18002e8e0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e961`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e978`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e978`
- `ntdll!WinSqmAddToStream` at `0x18002e935`
- `ntdll!WinSqmAddToStream` at `0x18002e935`
- `USER32!LoadCursorW` at `0x18002e8fb`
- `USER32!LoadCursorW` at `0x18002e8fb`
- `USER32!SetCursor` at `0x18002e904`
- `USER32!SetCursor` at `0x18002e9f6`
- `USER32!SetCursor` at `0x18002e904`
- `USER32!SetCursor` at `0x18002e9f6`

## pseudocode

```c
__int64 __fastcall DUIFramework_DisplayHelpDialog(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HCURSOR CursorW; // rax
  HCURSOR v3; // rsi
  HRESULT v4; // ebx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  unsigned int v7; // r11d
  int v9; // [rsp+30h] [rbp-18h] BYREF
  const wchar_t *v10; // [rsp+38h] [rbp-10h]
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  ppv = a2;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v9 = 2;
  v3 = SetCursor(CursorW);
  v10 = L"FONTS_CPL_SHOW_AND_HIDE_FONTS";
  WinSqmAddToStream(0, 911, 1, &v9);
  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v4 >= 0 )
  {
    v5 = (unsigned __int16 *)LocalAlloc(0, 0x74u);
    v6 = v5;
    if ( v5 )
    {
      v4 = StringCchCopyW(v5, 0x3Au, L"mshelp://windows/?id=");
      if ( v4 >= 0 )
      {
        v4 = StringCchCatW(v6, v7, L"bca086fa-c391-4794-8f05-330b9d2ae50d");
        if ( v4 >= 0 )
          v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, v6);
      }
      LocalFree(v6);
    }
    else
    {
      v4 = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  SetCursor(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002e8e0  mov     [rsp+arg_0], rbx
0x18002e8e5  mov     [rsp+arg_10], rsi
0x18002e8ea  mov     [rsp+arg_8], rdx
0x18002e8ef  push    rdi
0x18002e8f0  sub     rsp, 40h
0x18002e8f4  mov     edx, 7F02h; lpCursorName
0x18002e8f9  xor     ecx, ecx; hInstance
0x18002e8fb  call    cs:__imp_LoadCursorW
0x18002e901  mov     rcx, rax; hCursor
0x18002e904  call    cs:__imp_SetCursor
0x18002e90a  mov     ebx, 1
0x18002e90f  mov     [rsp+48h+var_18], 2
0x18002e917  mov     rsi, rax
0x18002e91a  lea     r9, [rsp+48h+var_18]
0x18002e91f  lea     rax, aFontsCplShowAn; "FONTS_CPL_SHOW_AND_HIDE_FONTS"
0x18002e926  mov     r8d, ebx
0x18002e929  mov     edx, 38Fh
0x18002e92e  mov     [rsp+48h+var_10], rax
0x18002e933  xor     ecx, ecx
0x18002e935  call    cs:__imp_WinSqmAddToStream
0x18002e93b  lea     rax, [rsp+48h+arg_8]
0x18002e940  mov     [rsp+48h+arg_8], 0
0x18002e949  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x18002e950  mov     [rsp+48h+ppv], rax; ppv
0x18002e955  mov     r8d, ebx; dwClsContext
0x18002e958  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x18002e95f  xor     edx, edx; pUnkOuter
0x18002e961  call    cs:__imp_CoCreateInstance
0x18002e967  mov     ebx, eax
0x18002e969  test    eax, eax
0x18002e96b  js      loc_18002E9F3
0x18002e971  mov     edx, 74h ; 't'; uBytes
0x18002e976  xor     ecx, ecx; uFlags
0x18002e978  call    cs:__imp_LocalAlloc
0x18002e97e  mov     rdi, rax
0x18002e981  test    rax, rax
0x18002e984  jz      short loc_18002E9DD
0x18002e986  mov     r11d, 3Ah ; ':'
0x18002e98c  lea     r8, aMshelpWindowsI_0; "mshelp://windows/?id="
0x18002e993  mov     edx, r11d; unsigned __int64
0x18002e996  mov     rcx, rax; unsigned __int16 *
0x18002e999  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e99e  mov     ebx, eax
0x18002e9a0  test    eax, eax
0x18002e9a2  js      short loc_18002E9D2
0x18002e9a4  lea     r8, aBca086faC39147; "bca086fa-c391-4794-8f05-330b9d2ae50d"
0x18002e9ab  mov     edx, r11d; unsigned __int64
0x18002e9ae  mov     rcx, rdi; unsigned __int16 *
0x18002e9b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e9b6  mov     ebx, eax
0x18002e9b8  test    eax, eax
0x18002e9ba  js      short loc_18002E9D2
0x18002e9bc  mov     rcx, [rsp+48h+arg_8]
0x18002e9c1  mov     rdx, rdi
0x18002e9c4  mov     rax, [rcx]
0x18002e9c7  mov     rax, [rax+18h]
0x18002e9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9d0  mov     ebx, eax
0x18002e9d2  mov     rcx, rdi; hMem
0x18002e9d5  call    cs:__imp_LocalFree
0x18002e9db  jmp     short loc_18002E9E2
0x18002e9dd  mov     ebx, 8007000Eh
0x18002e9e2  mov     rcx, [rsp+48h+arg_8]
0x18002e9e7  mov     rax, [rcx]
0x18002e9ea  mov     rax, [rax+10h]
0x18002e9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9f3  mov     rcx, rsi; hCursor
0x18002e9f6  call    cs:__imp_SetCursor
0x18002e9fc  mov     rsi, [rsp+48h+arg_10]
0x18002ea01  mov     eax, ebx
0x18002ea03  mov     rbx, [rsp+48h+arg_0]
0x18002ea08  add     rsp, 40h
0x18002ea0c  pop     rdi
0x18002ea0d  retn
```
