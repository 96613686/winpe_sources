# StartEtwKernelTracing

- ea: `0x180037e2c`
- end: `0x180037f9a`
- name: `StartEtwKernelTracing`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180037d20`

## callees

- `0x180002890`
- `0x180003438`
- `0x180003474`
- `0x180037afc`
- `0x180037e2c`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037e8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037e8e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037e75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037e75`

## string_xrefs

- `0x180037e68`: `api-ms-win-eventing-controller-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall StartEtwKernelTracing(int a1, unsigned int a2, __int128 *a3)
{
  char v5; // ebx^2
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int64 v11; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v12[18]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+A4h] [rbp-5Ch]
  wchar_t Destination[32]; // [rsp+A8h] [rbp-58h] BYREF
  int v16; // [rsp+E8h] [rbp-18h]
  _BYTE v17[36]; // [rsp+ECh] [rbp-14h] BYREF

  v11 = 0;
  v5 = BYTE2(a1);
  Library = LoadLibraryExW(L"api-ms-win-eventing-controller-l1-1-0.dll", 0, 0x800u);
  if ( !Library )
    return 50;
  ProcAddress = GetProcAddress(Library, "StartTraceW");
  if ( !ProcAddress )
    return 50;
  memset_0(v12, 0, 0xE0u);
  v12[0] = 224;
  v12[11] = 0x20000;
  v14 = 120;
  wcscpy_s(Destination, 0x20u, L"Microsoft-OCA-IPT");
  v8 = a3[1];
  v13 = 0x80000000;
  memset(v17, 0, 32);
  v12[13] = 1;
  v9 = *a3;
  v12[16] = -2113928192;
  BYTE2(v13) = -1;
  v12[12] = (((unsigned int)(1 << ((v5 & 0xF) + 12)) >> 7) + 1023) >> 10;
  LOWORD(v13) = 184;
  v16 = 65546;
  *(_DWORD *)v17 = 65545;
  *(_OWORD *)&v17[4] = v9;
  *(_OWORD *)&v17[20] = v8;
  if ( a2 > 1 )
    SetupAutoLogger((unsigned __int16 *)v12);
  return ((__int64 (__fastcall *)(__int64 *, wchar_t *, _DWORD *))ProcAddress)(&v11, Destination, v12);
}

```

## disassembly

```asm
0x180037e2c  mov     [rsp-8+arg_8], rbx
0x180037e31  mov     [rsp-8+arg_18], rsi
0x180037e36  push    rbp
0x180037e37  push    rdi
0x180037e38  push    r14
0x180037e3a  lea     rbp, [rsp-20h]
0x180037e3f  sub     rsp, 120h
0x180037e46  mov     rax, cs:__security_cookie
0x180037e4d  xor     rax, rsp
0x180037e50  mov     [rbp+30h+var_20], rax
0x180037e54  mov     rsi, r8
0x180037e57  mov     [rsp+130h+var_110], 0
0x180037e60  mov     r14d, edx
0x180037e63  mov     rbx, rcx
0x180037e66  xor     edx, edx; hFile
0x180037e68  lea     rcx, aApiMsWinEventi_0; "api-ms-win-eventing-controller-l1-1-0.d"...
0x180037e6f  mov     r8d, 800h; dwFlags
0x180037e75  call    cs:__imp_LoadLibraryExW
0x180037e7b  test    rax, rax
0x180037e7e  jz      loc_180037F71
0x180037e84  lea     rdx, aStarttracew; "StartTraceW"
0x180037e8b  mov     rcx, rax; hModule
0x180037e8e  call    cs:__imp_GetProcAddress
0x180037e94  mov     rdi, rax
0x180037e97  test    rax, rax
0x180037e9a  jz      loc_180037F71
0x180037ea0  xor     edx, edx; Val
0x180037ea2  lea     rcx, [rsp+130h+var_100]; void *
0x180037ea7  mov     r8d, 0E0h; Size
0x180037ead  call    memset_0
0x180037eb2  lea     r8, aMicrosoftOcaIp; "Microsoft-OCA-IPT"
0x180037eb9  mov     [rsp+130h+var_100], 0E0h
0x180037ec1  mov     edx, 20h ; ' '; SizeInWords
0x180037ec6  mov     [rsp+130h+var_D4], 20000h
0x180037ece  lea     rcx, [rbp+30h+Destination]; Destination
0x180037ed2  mov     [rbp+30h+var_8C], 78h ; 'x'
0x180037ed9  call    wcscpy_s
0x180037ede  movups  xmm1, xmmword ptr [rsi+10h]
0x180037ee2  shr     ebx, 10h
0x180037ee5  mov     edx, 1
0x180037eea  xorps   xmm0, xmm0
0x180037eed  mov     [rsp+130h+var_B8], 80000000h
0x180037ef5  movups  [rbp+30h+var_44], xmm0
0x180037ef9  and     ebx, 0Fh
0x180037efc  mov     eax, edx
0x180037efe  movups  [rbp+30h+var_34], xmm0
0x180037f02  mov     [rsp+130h+var_CC], edx
0x180037f06  movups  xmm0, xmmword ptr [rsi]
0x180037f09  lea     ecx, [rbx+0Ch]
0x180037f0c  mov     [rsp+130h+var_C0], 82000400h
0x180037f14  shl     eax, cl
0x180037f16  shr     eax, 7
0x180037f19  add     eax, 3FFh
0x180037f1e  mov     byte ptr [rsp+130h+var_B8+2], 0FFh
0x180037f23  shr     eax, 0Ah
0x180037f26  mov     [rsp+130h+var_D0], eax
0x180037f2a  mov     eax, 0B8h
0x180037f2f  mov     word ptr [rsp+130h+var_B8], ax
0x180037f34  mov     [rbp+30h+var_48], 1000Ah
0x180037f3b  mov     dword ptr [rbp+30h+var_44], 10009h
0x180037f42  movaps  [rbp+30h+var_44+4], xmm0
0x180037f46  movaps  [rbp+30h+var_34+4], xmm1
0x180037f4a  cmp     r14d, edx
0x180037f4d  jbe     short loc_180037F59
0x180037f4f  lea     rcx, [rsp+130h+var_100]
0x180037f54  call    SetupAutoLogger
0x180037f59  lea     r8, [rsp+130h+var_100]
0x180037f5e  mov     rax, rdi
0x180037f61  lea     rdx, [rbp+30h+Destination]
0x180037f65  lea     rcx, [rsp+130h+var_110]
0x180037f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f6f  jmp     short loc_180037F76
0x180037f71  mov     eax, 32h ; '2'
0x180037f76  mov     rcx, [rbp+30h+var_20]
0x180037f7a  xor     rcx, rsp; StackCookie
0x180037f7d  call    __security_check_cookie
0x180037f82  lea     r11, [rsp+130h+var_10]
0x180037f8a  mov     rbx, [r11+28h]
0x180037f8e  mov     rsi, [r11+38h]
0x180037f92  mov     rsp, r11
0x180037f95  pop     r14
0x180037f97  pop     rdi
0x180037f98  pop     rbp
0x180037f99  retn
```
