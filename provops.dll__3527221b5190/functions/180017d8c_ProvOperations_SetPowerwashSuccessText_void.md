# ProvOperations::SetPowerwashSuccessText(void)

- ea: `0x180017d8c`
- end: `0x180017ef1`
- name: `?SetPowerwashSuccessText@ProvOperations@@CAJXZ`
- size: `357`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180011884`

## callees

- `0x180007654`
- `0x180007674`
- `0x180017d8c`
- `0x180029f08`
- `0x180033e9a`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017db9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017db9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017e98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017ecd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017e98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017ecd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017e0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017e0c`

## string_xrefs

- `0x180017dac`: `MgmtRefreshCredProv.dll`

## pseudocode

```c
__int64 ProvOperations::SetPowerwashSuccessText(void)
{
  HMODULE Library; // rbx
  const char *v1; // r9
  const char *v3; // r9
  unsigned int LastError; // edi
  __int64 v5; // rcx
  WCHAR *v6; // rax
  int v7; // eax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  Library = LoadLibraryExW(L"MgmtRefreshCredProv.dll", 0, 0x800u);
  if ( !Library )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4A9,
             (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
             v1);
  memset_0(Buffer, 0, 0x208u);
  if ( LoadStringW(Library, 0xCFu, Buffer, 260) )
  {
    v5 = 260;
    v6 = Buffer;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    LastError = v5 == 0 ? 0x80070057 : 0;
    if ( v5 )
    {
      if ( ((2 * (260 - v5)) & (unsigned __int64)-(__int64)(v5 != 0)) <= 0xFFFFFFFF )
      {
        v7 = ProvWriteAndTrackLockScreenText((BYTE *)Buffer);
        LastError = v7;
        if ( v7 >= 0 )
        {
          FreeLibrary(Library);
          return 0;
        }
        v8 = (unsigned int)v7;
        v9 = 1204;
        goto LABEL_16;
      }
      LastError = -2147024362;
      v9 = 1202;
    }
    else
    {
      v9 = 1201;
    }
    v8 = LastError;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)v8);
    goto LABEL_17;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x4AD,
                (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
                v3);
LABEL_17:
  FreeLibrary(Library);
  return LastError;
}

```

## disassembly

```asm
0x180017d8c  push    rbx
0x180017d8e  push    rbp
0x180017d8f  push    rsi
0x180017d90  push    rdi
0x180017d91  sub     rsp, 248h
0x180017d98  mov     rax, cs:__security_cookie
0x180017d9f  xor     rax, rsp
0x180017da2  mov     [rsp+268h+var_38], rax
0x180017daa  xor     edx, edx; hFile
0x180017dac  lea     rcx, LibFileName; "MgmtRefreshCredProv.dll"
0x180017db3  mov     r8d, 800h; dwFlags
0x180017db9  call    cs:__imp_LoadLibraryExW
0x180017dbf  xor     ebp, ebp
0x180017dc1  mov     rbx, rax
0x180017dc4  test    rax, rax
0x180017dc7  jnz     short loc_180017DE7
0x180017dc9  mov     rcx, [rsp+268h]; this
0x180017dd1  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180017dd8  mov     edx, 4A9h; void *
0x180017ddd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017de2  jmp     loc_180017ED5
0x180017de7  xor     edx, edx; Val
0x180017de9  lea     rcx, [rsp+268h+Buffer]; void *
0x180017dee  mov     r8d, 208h; Size
0x180017df4  call    memset_0
0x180017df9  mov     esi, 104h
0x180017dfe  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180017e03  mov     r9d, esi; cchBufferMax
0x180017e06  mov     rcx, rbx; hInstance
0x180017e09  lea     edx, [rsi-35h]; uID
0x180017e0c  call    cs:__imp_LoadStringW
0x180017e12  test    eax, eax
0x180017e14  jnz     short loc_180017E36
0x180017e16  mov     rcx, [rsp+268h]; this
0x180017e1e  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180017e25  mov     edx, 4ADh; void *
0x180017e2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017e2f  mov     edi, eax
0x180017e31  jmp     loc_180017ECA
0x180017e36  mov     rcx, rsi
0x180017e39  lea     rax, [rsp+268h+Buffer]
0x180017e3e  cmp     [rax], bp
0x180017e41  jz      short loc_180017E4D
0x180017e43  add     rax, 2
0x180017e47  sub     rcx, 1
0x180017e4b  jnz     short loc_180017E3E
0x180017e4d  mov     rax, rcx
0x180017e50  neg     rax
0x180017e53  sbb     edi, edi
0x180017e55  not     edi
0x180017e57  and     edi, 80070057h
0x180017e5d  test    rcx, rcx
0x180017e60  jz      short loc_180017EAE
0x180017e62  sub     rsi, rcx
0x180017e65  add     rsi, rsi
0x180017e68  neg     rcx
0x180017e6b  mov     ecx, 0FFFFFFFFh
0x180017e70  sbb     rax, rax
0x180017e73  and     rax, rsi
0x180017e76  cmp     rax, rcx
0x180017e79  ja      short loc_180017EA2
0x180017e7b  lea     rcx, [rsp+268h+Buffer]; lpData
0x180017e80  call    ?ProvWriteAndTrackLockScreenText@@YAJPEBG@Z; ProvWriteAndTrackLockScreenText(ushort const *)
0x180017e85  mov     edi, eax
0x180017e87  test    eax, eax
0x180017e89  jns     short loc_180017E95
0x180017e8b  mov     r9d, eax
0x180017e8e  mov     edx, 4B4h
0x180017e93  jmp     short loc_180017EB6
0x180017e95  mov     rcx, rbx; hLibModule
0x180017e98  call    cs:__imp_FreeLibrary
0x180017e9e  xor     eax, eax
0x180017ea0  jmp     short loc_180017ED5
0x180017ea2  mov     edi, 80070216h
0x180017ea7  mov     edx, 4B2h
0x180017eac  jmp     short loc_180017EB3
0x180017eae  mov     edx, 4B1h; void *
0x180017eb3  mov     r9d, edi; char *
0x180017eb6  mov     rcx, [rsp+268h]; this
0x180017ebe  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180017ec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017eca  mov     rcx, rbx; hLibModule
0x180017ecd  call    cs:__imp_FreeLibrary
0x180017ed3  mov     eax, edi
0x180017ed5  mov     rcx, [rsp+268h+var_38]
0x180017edd  xor     rcx, rsp; StackCookie
0x180017ee0  call    __security_check_cookie
0x180017ee5  add     rsp, 248h
0x180017eec  pop     rdi
0x180017eed  pop     rsi
0x180017eee  pop     rbp
0x180017eef  pop     rbx
0x180017ef0  retn
```
