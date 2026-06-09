# WspiapiLoad

- ea: `0x180125fdc`
- end: `0x1801261ae`
- name: `WspiapiLoad`
- size: `466`
- prototype: `FARPROC __stdcall(WORD wFunction)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800ee040`

## callees

- `0x1801200d0`
- `0x180125fdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x1801260a8`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x1801260fc`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x1801260a8`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x1801260fc`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180126094`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1801260e7`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180126094`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1801260e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801260c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18012611b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18012613b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801260c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18012611b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18012613b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801260d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180126152`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801260d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180126152`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x18012606f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x18012606f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1801260b3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180126107`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1801260b3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180126107`

## pseudocode

```c
FARPROC __stdcall WspiapiLoad(WORD wFunction)
{
  __int64 v1; // r15
  HMODULE LibraryA; // rax
  HMODULE v3; // rdi
  HMODULE v4; // rax
  int i; // esi
  FARPROC ProcAddress; // rax
  __int64 j; // rdx
  __int64 v8; // rcx
  LPCSTR lpProcName; // [rsp+20h] [rbp-E0h]
  _QWORD v11[5]; // [rsp+28h] [rbp-D8h]
  char Destination[272]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Buffer[272]; // [rsp+160h] [rbp+60h] BYREF

  v11[0] = WspiapiLegacyGetAddrInfo;
  v1 = wFunction;
  v11[1] = "getnameinfo";
  v11[2] = WspiapiLegacyGetNameInfo;
  v11[3] = "freeaddrinfo";
  v11[4] = WspiapiLegacyFreeAddrInfo;
  lpProcName = "getaddrinfo";
  if ( !`WspiapiLoad'::`2'::bInitialized )
  {
    if ( GetSystemDirectoryA(Buffer, 0x104u) )
    {
      strcpy_s(Destination, 0x10Cu, Buffer);
      _o_strcat_s(Destination, 268, "\\ws2_32");
      LibraryA = LoadLibraryA(Destination);
      v3 = LibraryA;
      if ( LibraryA )
      {
        if ( GetProcAddress(LibraryA, "getaddrinfo") )
          goto LABEL_8;
        FreeLibrary(v3);
      }
      strcpy_s(Destination, 0x10Cu, Buffer);
      _o_strcat_s(Destination, 268, "\\wship6");
      v4 = LoadLibraryA(Destination);
      v3 = v4;
      if ( v4 )
      {
        if ( GetProcAddress(v4, "getaddrinfo") )
        {
LABEL_8:
          for ( i = 0; i < 3; ++i )
          {
            ProcAddress = GetProcAddress(v3, (LPCSTR)v11[2 * i - 1]);
            v11[2 * i] = ProcAddress;
            if ( !ProcAddress )
              goto LABEL_12;
          }
          if ( v3 )
          {
            for ( j = 0; j != 3; ++j )
            {
              v8 = j;
              (&`WspiapiLoad'::`2'::rgtGlobal)[2 * v8 + 1] = (char *)v11[2 * v8];
            }
          }
          goto LABEL_16;
        }
LABEL_12:
        FreeLibrary(v3);
      }
    }
LABEL_16:
    `WspiapiLoad'::`2'::bInitialized = 1;
  }
  return (FARPROC)(&`WspiapiLoad'::`2'::rgtGlobal)[2 * v1 + 1];
}

```

## disassembly

```asm
0x180125fdc  push    rbp
0x180125fde  push    rbx
0x180125fdf  push    rsi
0x180125fe0  push    rdi
0x180125fe1  push    r14
0x180125fe3  push    r15
0x180125fe5  lea     rbp, [rsp-188h]
0x180125fed  sub     rsp, 288h
0x180125ff4  mov     rax, cs:__security_cookie
0x180125ffb  xor     rax, rsp
0x180125ffe  mov     [rbp+1B0h+var_40], rax
0x180126005  cmp     cs:?bInitialized@?1??WspiapiLoad@@9@4HA, 0; int `WspiapiLoad'::`2'::bInitialized
0x18012600c  lea     rax, WspiapiLegacyGetAddrInfo
0x180126013  mov     [rsp+2B0h+var_288], rax
0x180126018  lea     rbx, aGetaddrinfo; "getaddrinfo"
0x18012601f  lea     rax, aGetnameinfo; "getnameinfo"
0x180126026  movzx   r15d, cx
0x18012602a  mov     [rsp+2B0h+var_280], rax
0x18012602f  lea     rax, WspiapiLegacyGetNameInfo
0x180126036  mov     [rsp+2B0h+var_278], rax
0x18012603b  lea     rax, aFreeaddrinfo; "freeaddrinfo"
0x180126042  mov     [rsp+2B0h+var_270], rax
0x180126047  lea     rax, WspiapiLegacyFreeAddrInfo
0x18012604e  mov     [rsp+2B0h+var_268], rax
0x180126053  mov     [rsp+2B0h+lpProcName], rbx
0x180126058  jz      short loc_180126066
0x18012605a  lea     r14, ?rgtGlobal@?1??WspiapiLoad@@9@4PAUWSPIAPI_FUNCTION@@A; WSPIAPI_FUNCTION near * `WspiapiLoad'::`2'::rgtGlobal
0x180126061  jmp     loc_180126184
0x180126066  mov     edx, 104h; uSize
0x18012606b  lea     rcx, [rbp+1B0h+Buffer]; lpBuffer
0x18012606f  call    cs:__imp_GetSystemDirectoryA
0x180126075  lea     r14, ?rgtGlobal@?1??WspiapiLoad@@9@4PAUWSPIAPI_FUNCTION@@A; WSPIAPI_FUNCTION near * `WspiapiLoad'::`2'::rgtGlobal
0x18012607c  test    eax, eax
0x18012607e  jz      loc_18012617A
0x180126084  mov     esi, 10Ch
0x180126089  lea     r8, [rbp+1B0h+Buffer]; Source
0x18012608d  mov     edx, esi; SizeInBytes
0x18012608f  lea     rcx, [rsp+2B0h+Destination]; Destination
0x180126094  call    cs:__imp_strcpy_s
0x18012609a  lea     r8, aWs232; "\\ws2_32"
0x1801260a1  mov     edx, esi
0x1801260a3  lea     rcx, [rsp+2B0h+Destination]
0x1801260a8  call    cs:__imp__o_strcat_s
0x1801260ae  lea     rcx, [rsp+2B0h+Destination]; lpLibFileName
0x1801260b3  call    cs:__imp_LoadLibraryA
0x1801260b9  mov     rdi, rax
0x1801260bc  test    rax, rax
0x1801260bf  jz      short loc_1801260DB
0x1801260c1  mov     rdx, rbx; lpProcName
0x1801260c4  mov     rcx, rax; hModule
0x1801260c7  call    cs:__imp_GetProcAddress
0x1801260cd  test    rax, rax
0x1801260d0  jnz     short loc_180126126
0x1801260d2  mov     rcx, rdi; hLibModule
0x1801260d5  call    cs:__imp_FreeLibrary
0x1801260db  lea     r8, [rbp+1B0h+Buffer]; Source
0x1801260df  mov     rdx, rsi; SizeInBytes
0x1801260e2  lea     rcx, [rsp+2B0h+Destination]; Destination
0x1801260e7  call    cs:__imp_strcpy_s
0x1801260ed  lea     r8, aWship6; "\\wship6"
0x1801260f4  mov     rdx, rsi
0x1801260f7  lea     rcx, [rsp+2B0h+Destination]
0x1801260fc  call    cs:__imp__o_strcat_s
0x180126102  lea     rcx, [rsp+2B0h+Destination]; lpLibFileName
0x180126107  call    cs:__imp_LoadLibraryA
0x18012610d  mov     rdi, rax
0x180126110  test    rax, rax
0x180126113  jz      short loc_18012617A
0x180126115  mov     rdx, rbx; lpProcName
0x180126118  mov     rcx, rax; hModule
0x18012611b  call    cs:__imp_GetProcAddress
0x180126121  test    rax, rax
0x180126124  jz      short loc_18012614F
0x180126126  xor     esi, esi
0x180126128  cmp     esi, 3
0x18012612b  jge     short loc_18012615A
0x18012612d  movsxd  rbx, esi
0x180126130  mov     rcx, rdi; hModule
0x180126133  add     rbx, rbx
0x180126136  mov     rdx, [rsp+rbx*8+2B0h+lpProcName]; lpProcName
0x18012613b  call    cs:__imp_GetProcAddress
0x180126141  mov     [rsp+rbx*8+2B0h+var_288], rax
0x180126146  test    rax, rax
0x180126149  jz      short loc_18012614F
0x18012614b  inc     esi
0x18012614d  jmp     short loc_180126128
0x18012614f  mov     rcx, rdi; hLibModule
0x180126152  call    cs:__imp_FreeLibrary
0x180126158  jmp     short loc_18012617A
0x18012615a  test    rdi, rdi
0x18012615d  jz      short loc_18012617A
0x18012615f  xor     edx, edx
0x180126161  mov     rcx, rdx
0x180126164  inc     rdx
0x180126167  add     rcx, rcx
0x18012616a  mov     rax, [rsp+rcx*8+2B0h+var_288]
0x18012616f  mov     [r14+rcx*8+8], rax
0x180126174  cmp     rdx, 3
0x180126178  jnz     short loc_180126161
0x18012617a  mov     cs:?bInitialized@?1??WspiapiLoad@@9@4HA, 1; int `WspiapiLoad'::`2'::bInitialized
0x180126184  mov     rax, r15
0x180126187  add     rax, rax
0x18012618a  mov     rax, [r14+rax*8+8]
0x18012618f  mov     rcx, [rbp+1B0h+var_40]
0x180126196  xor     rcx, rsp; StackCookie
0x180126199  call    __security_check_cookie
0x18012619e  add     rsp, 288h
0x1801261a5  pop     r15
0x1801261a7  pop     r14
0x1801261a9  pop     rdi
0x1801261aa  pop     rsi
0x1801261ab  pop     rbx
0x1801261ac  pop     rbp
0x1801261ad  retn
```
