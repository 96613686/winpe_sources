# InitWinRTStatus(void)

- ea: `0x180035a64`
- end: `0x180035b8e`
- name: `?InitWinRTStatus@@YAXXZ`
- size: `298`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021810`

## callees

- `0x180035a64`
- `0x18003dc30`
- `0x18003e73c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180035b14`
- `KERNEL32!LoadLibraryExW` at `0x180035b14`
- `KERNEL32!FreeLibrary` at `0x180035b55`
- `KERNEL32!FreeLibrary` at `0x180035b55`
- `KERNEL32!GetSystemDirectoryW` at `0x180035ada`
- `KERNEL32!GetSystemDirectoryW` at `0x180035ada`
- `KERNEL32!GetProcAddress` at `0x180035b3f`
- `KERNEL32!GetProcAddress` at `0x180035b3f`
- `ucrtbase_clr0400!wcscat_s` at `0x180035b00`
- `ucrtbase_clr0400!wcscat_s` at `0x180035b00`

## string_xrefs

- `0x180035a98`: `\combase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void InitWinRTStatus(void)
{
  int v0; // ebx
  UINT SystemDirectoryW; // eax
  HMODULE Library; // rax
  HMODULE v3; // rdi
  BOOL v4; // esi
  _BYTE Source[40]; // [rsp+30h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+58h] [rbp-B0h] BYREF

  v0 = 1;
  wcscpy((wchar_t *)&Source[8], L"\\combase.dll");
  memset_0(Buffer, 0, 0x20Au);
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW
    && 261 - (unsigned __int64)SystemDirectoryW >= 0xD
    && !wcscat_s(Buffer, 0x105u, (const wchar_t *)&Source[8]) )
  {
    Library = LoadLibraryExW(Buffer, 0, 0);
    v3 = Library;
    v4 = Library != 0;
    if ( Library && GetProcAddress(Library, "RoInitialize") )
      v0 = 2;
    if ( v4 )
      FreeLibrary(v3);
  }
  gWinRTStatus = v0;
}

```

## disassembly

```asm
0x180035a64  mov     rax, rsp
0x180035a67  mov     [rax+8], rbx
0x180035a6b  mov     [rax+10h], rsi
0x180035a6f  mov     [rax+18h], rdi
0x180035a73  push    rbp
0x180035a74  lea     rbp, [rax-178h]
0x180035a7b  sub     rsp, 270h
0x180035a82  mov     rax, cs:__security_cookie
0x180035a89  xor     rax, rsp
0x180035a8c  mov     [rbp+170h+var_10], rax
0x180035a93  mov     ebx, 1
0x180035a98  movups  xmm0, xmmword ptr cs:aCombaseDll; "\\combase.dll"
0x180035a9f  movups  xmmword ptr [rsp+270h+Source+8], xmm0
0x180035aa4  movsd   xmm1, qword ptr cs:aCombaseDll+10h; ".dll"
0x180035aac  movsd   qword ptr [rsp+270h+var_230], xmm1
0x180035ab2  movzx   eax, word ptr cs:aCombaseDll+18h; ""
0x180035ab9  mov     word ptr [rsp+270h+var_228], ax
0x180035abe  xor     edx, edx; Val
0x180035ac0  mov     r8d, 20Ah; Size
0x180035ac6  lea     rcx, [rsp+270h+Buffer]; void *
0x180035acb  call    memset_0
0x180035ad0  mov     edx, 104h; uSize
0x180035ad5  lea     rcx, [rsp+270h+Buffer]; lpBuffer
0x180035ada  call    cs:__imp_GetSystemDirectoryW
0x180035ae0  test    eax, eax
0x180035ae2  jz      short loc_180035B60
0x180035ae4  mov     ecx, eax
0x180035ae6  mov     edx, 105h; SizeInWords
0x180035aeb  mov     eax, edx
0x180035aed  sub     rax, rcx
0x180035af0  cmp     rax, 0Dh
0x180035af4  jb      short loc_180035B60
0x180035af6  lea     r8, [rsp+270h+Source+8]; Source
0x180035afb  lea     rcx, [rsp+270h+Buffer]; Destination
0x180035b00  call    cs:__imp_wcscat_s
0x180035b06  test    eax, eax
0x180035b08  jnz     short loc_180035B60
0x180035b0a  xor     r8d, r8d; dwFlags
0x180035b0d  xor     edx, edx; hFile
0x180035b0f  lea     rcx, [rsp+270h+Buffer]; lpLibFileName
0x180035b14  call    cs:__imp_LoadLibraryExW
0x180035b1a  mov     rdi, rax
0x180035b1d  mov     qword ptr [rsp+270h+var_250], rax
0x180035b22  and     dword ptr [rsp+270h+Source], 0
0x180035b27  xor     esi, esi
0x180035b29  test    rax, rax
0x180035b2c  cmovnz  esi, ebx
0x180035b2f  mov     dword ptr [rsp+270h+Source], esi
0x180035b33  jz      short loc_180035B4E
0x180035b35  lea     rdx, aRoinitialize_0; "RoInitialize"
0x180035b3c  mov     rcx, rax; hModule
0x180035b3f  call    cs:__imp_GetProcAddress
0x180035b45  lea     ecx, [rbx+1]
0x180035b48  test    rax, rax
0x180035b4b  cmovnz  ebx, ecx
0x180035b4e  test    esi, esi
0x180035b50  jz      short loc_180035B60
0x180035b52  mov     rcx, rdi; hLibModule
0x180035b55  call    cs:__imp_FreeLibrary
0x180035b5b  and     dword ptr [rsp+270h+Source], 0
0x180035b60  mov     cs:?gWinRTStatus@@3W4WinRTStatusEnum@@A, ebx; WinRTStatusEnum gWinRTStatus
0x180035b66  mov     rcx, [rbp+170h+var_10]
0x180035b6d  xor     rcx, rsp; StackCookie
0x180035b70  call    __security_check_cookie
0x180035b75  lea     r11, [rsp+270h+var_s0]
0x180035b7d  mov     rbx, [r11+10h]
0x180035b81  mov     rsi, [r11+18h]
0x180035b85  mov     rdi, [r11+20h]
0x180035b89  mov     rsp, r11
0x180035b8c  pop     rbp
0x180035b8d  retn
```
