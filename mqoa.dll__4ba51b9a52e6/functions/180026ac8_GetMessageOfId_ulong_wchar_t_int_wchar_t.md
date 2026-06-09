# GetMessageOfId(ulong,wchar_t *,int,wchar_t * *)

- ea: `0x180026ac8`
- end: `0x180026bba`
- name: `?GetMessageOfId@@YAHKPEA_WHPEAPEA_W@Z`
- size: `242`
- prototype: `__int64 __fastcall(UINT uID, LPCWSTR lpLibFileName, int, wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012e80`
- `0x18002678c`

## callees

- `0x180026ac8`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180026b44`
- `KERNEL32!FormatMessageW` at `0x180026b44`
- `KERNEL32!FreeLibrary` at `0x180026b7e`
- `KERNEL32!FreeLibrary` at `0x180026b7e`
- `KERNEL32!LoadLibraryW` at `0x180026b09`
- `KERNEL32!LoadLibraryW` at `0x180026b09`
- `USER32!LoadStringW` at `0x180026b5c`
- `USER32!LoadStringW` at `0x180026b5c`
- `OLEAUT32!__imp_SysAllocString` at `0x180026b6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180026b6d`

## pseudocode

```c
_BOOL8 __fastcall GetMessageOfId(UINT uID, LPCWSTR lpLibFileName, int a3, wchar_t **a4)
{
  HMODULE LibraryW; // rbx
  DWORD v8; // ecx
  DWORD StringW; // eax
  DWORD v10; // edi
  WCHAR Buffer[1024]; // [rsp+40h] [rbp-828h] BYREF

  *a4 = 0;
  if ( lpLibFileName )
  {
    LibraryW = LoadLibraryW(lpLibFileName);
    if ( !LibraryW )
      return 0;
    v8 = 2303;
  }
  else
  {
    LibraryW = 0;
    v8 = 4351;
  }
  if ( a3 )
    StringW = FormatMessageW(v8, LibraryW, uID, 0, Buffer, 0x400u, 0);
  else
    StringW = LoadStringW(LibraryW, uID, Buffer, 1024);
  v10 = StringW;
  if ( StringW )
    *a4 = SysAllocString(Buffer);
  if ( LibraryW )
    FreeLibrary(LibraryW);
  return v10 && *a4;
}

```

## disassembly

```asm
0x180026ac8  mov     [rsp+arg_10], rbx
0x180026acd  push    rbp
0x180026ace  push    rsi
0x180026acf  push    rdi
0x180026ad0  sub     rsp, 850h
0x180026ad7  mov     rax, cs:__security_cookie
0x180026ade  xor     rax, rsp
0x180026ae1  mov     [rsp+868h+var_28], rax
0x180026ae9  mov     qword ptr [r9], 0
0x180026af0  mov     rsi, r9
0x180026af3  mov     edi, r8d
0x180026af6  mov     ebp, ecx
0x180026af8  test    rdx, rdx
0x180026afb  jnz     short loc_180026B06
0x180026afd  xor     ebx, ebx
0x180026aff  mov     ecx, 10FFh
0x180026b04  jmp     short loc_180026B1C
0x180026b06  mov     rcx, rdx; lpLibFileName
0x180026b09  call    cs:__imp_LoadLibraryW
0x180026b0f  mov     rbx, rax
0x180026b12  test    rax, rax
0x180026b15  jz      short loc_180026B95
0x180026b17  mov     ecx, 8FFh; dwFlags
0x180026b1c  test    edi, edi
0x180026b1e  jz      short loc_180026B4C
0x180026b20  mov     [rsp+868h+Arguments], 0; Arguments
0x180026b29  lea     rax, [rsp+868h+Buffer]
0x180026b2e  mov     [rsp+868h+nSize], 400h; nSize
0x180026b36  xor     r9d, r9d; dwLanguageId
0x180026b39  mov     r8d, ebp; dwMessageId
0x180026b3c  mov     [rsp+868h+lpBuffer], rax; lpBuffer
0x180026b41  mov     rdx, rbx; lpSource
0x180026b44  call    cs:__imp_FormatMessageW
0x180026b4a  jmp     short loc_180026B62
0x180026b4c  mov     r9d, 400h; cchBufferMax
0x180026b52  lea     r8, [rsp+868h+Buffer]; lpBuffer
0x180026b57  mov     edx, ebp; uID
0x180026b59  mov     rcx, rbx; hInstance
0x180026b5c  call    cs:__imp_LoadStringW
0x180026b62  mov     edi, eax
0x180026b64  test    eax, eax
0x180026b66  jz      short loc_180026B76
0x180026b68  lea     rcx, [rsp+868h+Buffer]; psz
0x180026b6d  call    cs:__imp_SysAllocString
0x180026b73  mov     [rsi], rax
0x180026b76  test    rbx, rbx
0x180026b79  jz      short loc_180026B84
0x180026b7b  mov     rcx, rbx; hLibModule
0x180026b7e  call    cs:__imp_FreeLibrary
0x180026b84  test    edi, edi
0x180026b86  jz      short loc_180026B95
0x180026b88  cmp     qword ptr [rsi], 0
0x180026b8c  jz      short loc_180026B95
0x180026b8e  mov     eax, 1
0x180026b93  jmp     short loc_180026B97
0x180026b95  xor     eax, eax
0x180026b97  mov     rcx, [rsp+868h+var_28]
0x180026b9f  xor     rcx, rsp; StackCookie
0x180026ba2  call    __security_check_cookie
0x180026ba7  mov     rbx, [rsp+868h+arg_10]
0x180026baf  add     rsp, 850h
0x180026bb6  pop     rdi
0x180026bb7  pop     rsi
0x180026bb8  pop     rbp
0x180026bb9  retn
```
