# DRMOS::GetModuleVersion(ushort const *,ulong *)

- ea: `0x18003816c`
- end: `0x1800382cf`
- name: `?GetModuleVersion@DRMOS@@YAJPEBGPEAK@Z`
- size: `355`
- prototype: `__int64 __fastcall(DRMOS *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000cbb0`
- `0x18001bff0`

## callees

- `0x180001244`
- `0x180001284`
- `0x18003816c`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381c7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800381bc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800381bc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1800381f3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1800381f3`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180038250`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180038250`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18003827a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18003827a`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18003820c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18003820c`

## string_xrefs

- `0x1800381b5`: `msdrm.dll`

## pseudocode

```c
__int64 __fastcall DRMOS::GetModuleVersion(DRMOS *this, unsigned __int16 *a2, unsigned int *a3)
{
  void *v4; // rdi
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  DWORD FileVersionInfoSize; // eax
  void *lpData; // rax
  unsigned __int16 *v10; // rdx
  DWORD dwHandle; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-C0h] BYREF

  dwHandle = 0;
  v4 = 0;
  lpBuffer = 0;
  memset_0(Filename, 0, 0x208u);
  ModuleHandleW = GetModuleHandleW(L"msdrm.dll");
  if ( ModuleHandleW && GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
  {
    FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, Filename, &dwHandle);
    dwHandle = FileVersionInfoSize;
    if ( !FileVersionInfoSize )
    {
      v7 = -2147168506;
      goto LABEL_12;
    }
    lpData = operator new(FileVersionInfoSize);
    v4 = lpData;
    if ( !lpData )
    {
      v7 = -2147024882;
      goto LABEL_12;
    }
    if ( GetFileVersionInfoExW(3u, Filename, 0, dwHandle, lpData) )
    {
      dwHandle = 52;
      if ( VerQueryValueW(v4, L"\\", &lpBuffer, &dwHandle) )
      {
        v10 = (unsigned __int16 *)lpBuffer;
        v7 = 0;
        *(_DWORD *)a2 = *((unsigned __int16 *)lpBuffer + 5);
        *((_DWORD *)a2 + 1) = v10[4];
        *((_DWORD *)a2 + 2) = v10[7];
        *((_DWORD *)a2 + 3) = v10[6];
        goto LABEL_12;
      }
    }
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  operator delete(v4);
  return v7;
}

```

## disassembly

```asm
0x18003816c  push    rbp
0x18003816e  push    rbx
0x18003816f  push    rsi
0x180038170  push    rdi
0x180038171  lea     rbp, [rsp-168h]
0x180038179  sub     rsp, 268h
0x180038180  mov     rax, cs:__security_cookie
0x180038187  xor     rax, rsp
0x18003818a  mov     [rbp+180h+var_30], rax
0x180038191  mov     rsi, rdx
0x180038194  mov     [rsp+280h+dwHandle], 0
0x18003819c  xor     edi, edi
0x18003819e  lea     rcx, [rsp+280h+Filename]; void *
0x1800381a3  xor     edx, edx; Val
0x1800381a5  mov     [rsp+280h+lpBuffer], rdi
0x1800381aa  mov     r8d, 208h; Size
0x1800381b0  call    memset_0
0x1800381b5  lea     rcx, ?g_wszMODULENAME@@3QBGB; "msdrm.dll"
0x1800381bc  call    cs:__imp_GetModuleHandleW
0x1800381c2  test    rax, rax
0x1800381c5  jnz     short loc_1800381E5
0x1800381c7  call    cs:__imp_GetLastError
0x1800381cd  mov     ebx, eax
0x1800381cf  test    eax, eax
0x1800381d1  jle     loc_1800382AA
0x1800381d7  movzx   ebx, ax
0x1800381da  or      ebx, 80070000h
0x1800381e0  jmp     loc_1800382AA
0x1800381e5  mov     r8d, 104h; nSize
0x1800381eb  lea     rdx, [rsp+280h+Filename]; lpFilename
0x1800381f0  mov     rcx, rax; hModule
0x1800381f3  call    cs:__imp_GetModuleFileNameW
0x1800381f9  test    eax, eax
0x1800381fb  jz      short loc_1800381C7
0x1800381fd  lea     r8, [rsp+280h+dwHandle]; lpdwHandle
0x180038202  mov     ecx, 1; dwFlags
0x180038207  lea     rdx, [rsp+280h+Filename]; lpwstrFilename
0x18003820c  call    cs:__imp_GetFileVersionInfoSizeExW
0x180038212  mov     [rsp+280h+dwHandle], eax
0x180038216  test    eax, eax
0x180038218  jnz     short loc_180038224
0x18003821a  mov     ebx, 8004CF06h
0x18003821f  jmp     loc_1800382AA
0x180038224  mov     ecx, eax; Size
0x180038226  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003822b  mov     rdi, rax
0x18003822e  test    rax, rax
0x180038231  jnz     short loc_18003823A
0x180038233  mov     ebx, 8007000Eh
0x180038238  jmp     short loc_1800382AA
0x18003823a  mov     r9d, [rsp+280h+dwHandle]; dwLen
0x18003823f  lea     rdx, [rsp+280h+Filename]; lpwstrFilename
0x180038244  xor     r8d, r8d; dwHandle
0x180038247  mov     [rsp+280h+lpData], rdi; lpData
0x18003824c  lea     ecx, [r8+3]; dwFlags
0x180038250  call    cs:__imp_GetFileVersionInfoExW
0x180038256  test    eax, eax
0x180038258  jz      loc_1800381C7
0x18003825e  lea     r9, [rsp+280h+dwHandle]; puLen
0x180038263  mov     [rsp+280h+dwHandle], 34h ; '4'
0x18003826b  lea     r8, [rsp+280h+lpBuffer]; lplpBuffer
0x180038270  mov     rcx, rdi; pBlock
0x180038273  lea     rdx, SubBlock; "\\"
0x18003827a  call    cs:__imp_VerQueryValueW
0x180038280  test    eax, eax
0x180038282  jz      loc_1800381C7
0x180038288  mov     rdx, [rsp+280h+lpBuffer]
0x18003828d  xor     ebx, ebx
0x18003828f  movzx   ecx, word ptr [rdx+0Ah]
0x180038293  mov     [rsi], ecx
0x180038295  movzx   ecx, word ptr [rdx+8]
0x180038299  mov     [rsi+4], ecx
0x18003829c  movzx   ecx, word ptr [rdx+0Eh]
0x1800382a0  mov     [rsi+8], ecx
0x1800382a3  movzx   ecx, word ptr [rdx+0Ch]
0x1800382a7  mov     [rsi+0Ch], ecx
0x1800382aa  mov     rcx, rdi; Block
0x1800382ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800382b2  mov     eax, ebx
0x1800382b4  mov     rcx, [rbp+180h+var_30]
0x1800382bb  xor     rcx, rsp; StackCookie
0x1800382be  call    __security_check_cookie
0x1800382c3  add     rsp, 268h
0x1800382ca  pop     rdi
0x1800382cb  pop     rsi
0x1800382cc  pop     rbx
0x1800382cd  pop     rbp
0x1800382ce  retn
```
