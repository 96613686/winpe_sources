# LoadImageFromSystemDirectory(ushort const *,HINSTANCE__ * *)

- ea: `0x18001eb5c`
- end: `0x18001ec57`
- name: `?LoadImageFromSystemDirectory@@YAJPEBGPEAPEAUHINSTANCE__@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001adb4`

## callees

- `0x18000f970`
- `0x1800103e8`
- `0x1800165a0`
- `0x18001eb5c`
- `0x180021828`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ec1f`
- `KERNEL32!GetLastError` at `0x18001ec1f`
- `KERNEL32!LoadLibraryExW` at `0x18001ec09`
- `KERNEL32!LoadLibraryExW` at `0x18001ec09`
- `KERNEL32!GetSystemDirectoryW` at `0x18001ebb8`
- `KERNEL32!GetSystemDirectoryW` at `0x18001ebb8`

## string_xrefs

- `0x18001ebe2`: `compstui.dll`

## pseudocode

```c
__int64 __fastcall LoadImageFromSystemDirectory(const unsigned __int16 *a1, HINSTANCE *a2)
{
  size_t v3; // rdx
  STRSAFE_PCNZWCH v4; // rcx
  unsigned __int64 SystemDirectoryW; // rdx
  int v6; // ebx
  signed int LastError; // eax
  size_t pcchLength[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  pcchLength[0] = 0;
  *a2 = 0;
  if ( StringLengthWorkerW(v4, v3, pcchLength) < 0 )
    goto LABEL_8;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW - 1 > 0x101 || SystemDirectoryW + pcchLength[0] >= 0x103 )
  {
    v6 = -2147467259;
  }
  else
  {
    Buffer[SystemDirectoryW] = 92;
    v6 = StringCchCatW(Buffer, SystemDirectoryW, L"compstui.dll");
    if ( v6 >= 0 )
      *a2 = LoadLibraryExW(Buffer, 0, 2u);
  }
  if ( !*a2 )
  {
LABEL_8:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001eb5c  mov     [rsp+arg_0], rbx
0x18001eb61  push    rdi
0x18001eb62  sub     rsp, 250h
0x18001eb69  mov     rax, cs:__security_cookie
0x18001eb70  xor     rax, rsp
0x18001eb73  mov     [rsp+258h+var_18], rax
0x18001eb7b  mov     rdi, rdx
0x18001eb7e  lea     rcx, [rsp+258h+Buffer]; void *
0x18001eb83  xor     edx, edx; Val
0x18001eb85  mov     r8d, 208h; Size
0x18001eb8b  call    memset_0
0x18001eb90  lea     r8, [rsp+258h+pcchLength]; pcchLength
0x18001eb95  mov     [rsp+258h+pcchLength], 0
0x18001eb9e  mov     qword ptr [rdi], 0
0x18001eba5  call    StringLengthWorkerW
0x18001ebaa  test    eax, eax
0x18001ebac  js      short loc_18001EC1F
0x18001ebae  mov     edx, 104h; uSize
0x18001ebb3  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18001ebb8  call    cs:__imp_GetSystemDirectoryW
0x18001ebbe  mov     edx, eax; unsigned __int64
0x18001ebc0  lea     rax, [rdx-1]
0x18001ebc4  cmp     rax, 101h
0x18001ebca  ja      short loc_18001EC14
0x18001ebcc  mov     rcx, [rsp+258h+pcchLength]
0x18001ebd1  add     rcx, rdx
0x18001ebd4  cmp     rcx, 103h
0x18001ebdb  jnb     short loc_18001EC14
0x18001ebdd  mov     eax, 5Ch ; '\'
0x18001ebe2  lea     r8, aCompstuiDll; "compstui.dll"
0x18001ebe9  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x18001ebee  mov     [rsp+rdx*2+258h+Buffer], ax
0x18001ebf3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ebf8  mov     ebx, eax
0x18001ebfa  test    eax, eax
0x18001ebfc  js      short loc_18001EC19
0x18001ebfe  xor     edx, edx; hFile
0x18001ec00  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x18001ec05  lea     r8d, [rdx+2]; dwFlags
0x18001ec09  call    cs:__imp_LoadLibraryExW
0x18001ec0f  mov     [rdi], rax
0x18001ec12  jmp     short loc_18001EC19
0x18001ec14  mov     ebx, 80004005h
0x18001ec19  cmp     qword ptr [rdi], 0
0x18001ec1d  jnz     short loc_18001EC34
0x18001ec1f  call    cs:__imp_GetLastError
0x18001ec25  mov     ebx, eax
0x18001ec27  test    eax, eax
0x18001ec29  jle     short loc_18001EC34
0x18001ec2b  movzx   ebx, ax
0x18001ec2e  or      ebx, 80070000h
0x18001ec34  mov     eax, ebx
0x18001ec36  mov     rcx, [rsp+258h+var_18]
0x18001ec3e  xor     rcx, rsp; StackCookie
0x18001ec41  call    __security_check_cookie
0x18001ec46  mov     rbx, [rsp+258h+arg_0]
0x18001ec4e  add     rsp, 250h
0x18001ec55  pop     rdi
0x18001ec56  retn
```
