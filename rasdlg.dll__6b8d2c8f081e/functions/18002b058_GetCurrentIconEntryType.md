# GetCurrentIconEntryType

- ea: `0x18002b058`
- end: `0x18002b198`
- name: `GetCurrentIconEntryType`
- size: `320`
- prototype: `HICON __fastcall(int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a268`
- `0x18001c2cc`

## callees

- `0x18002b058`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b0d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b0d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b0f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b0f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b128`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b128`
- `USER32!GetIconInfo` at `0x18002b16c`
- `USER32!GetIconInfo` at `0x18002b16c`
- `USER32!CreateIconIndirect` at `0x18002b17b`
- `USER32!CreateIconIndirect` at `0x18002b17b`
- `USER32!LoadIconW` at `0x18002b159`
- `USER32!LoadIconW` at `0x18002b159`

## string_xrefs

- `0x18002b0cb`: `netshell.dll`

## pseudocode

```c
HICON __fastcall GetCurrentIconEntryType(int a1, int a2)
{
  unsigned int v2; // ebp
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  unsigned int v8; // ebx
  unsigned int v9; // esi
  int v10; // edi
  HMODULE Library; // rax
  HMODULE v12; // r14
  int v13; // r15d
  FARPROC ProcAddress; // rax
  HICON result; // rax
  HICON IconW; // rax
  ICONINFO piconinfo; // [rsp+40h] [rbp-58h] BYREF
  HICON v18; // [rsp+B0h] [rbp+18h] BYREF

  v18 = 0;
  v2 = a2 != 0 ? 0xFFFFFFF0 : 0;
  v3 = a1 - 1;
  if ( !v3 )
  {
LABEL_13:
    v9 = 4;
    goto LABEL_14;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v9 = 5;
    goto LABEL_14;
  }
  v5 = v4 - 3;
  if ( !v5 )
  {
    v9 = 6;
LABEL_14:
    v10 = 0;
    v8 = 7;
    goto LABEL_15;
  }
  v6 = v5 - 4091;
  if ( !v6 )
  {
    v8 = 0x80000000;
    goto LABEL_10;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v8 = -2147483647;
    goto LABEL_10;
  }
  if ( v7 != 1 )
    goto LABEL_13;
  v8 = -2147483646;
LABEL_10:
  v9 = 0;
  v10 = -1;
LABEL_15:
  Library = LoadLibraryExW(L"netshell.dll", 0, 0x800u);
  v12 = Library;
  if ( !Library )
    goto LABEL_20;
  v13 = -2147467259;
  ProcAddress = GetProcAddress(Library, "HrGetIconFromMediaType");
  if ( ProcAddress )
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, int, HICON *))ProcAddress)(
            v2 + 32,
            v9,
            0,
            v8,
            v10,
            &v18);
  FreeLibrary(v12);
  if ( v13 < 0 || (result = v18) == 0 )
  {
LABEL_20:
    memset(&piconinfo, 0, sizeof(piconinfo));
    IconW = LoadIconW(g_hinstDll, (LPCWSTR)0x233);
    if ( IconW && GetIconInfo(IconW, &piconinfo) )
      return CreateIconIndirect(&piconinfo);
    else
      return v18;
  }
  return result;
}

```

## disassembly

```asm
0x18002b058  mov     rax, rsp
0x18002b05b  push    rbx
0x18002b05c  push    rbp
0x18002b05d  push    rsi
0x18002b05e  push    rdi
0x18002b05f  push    r14
0x18002b061  push    r15
0x18002b063  sub     rsp, 68h
0x18002b067  neg     edx
0x18002b069  mov     qword ptr [rax+18h], 0
0x18002b071  sbb     ebp, ebp
0x18002b073  and     ebp, 0FFFFFFF0h
0x18002b076  sub     ecx, 1
0x18002b079  jz      short loc_18002B0BF
0x18002b07b  sub     ecx, 1
0x18002b07e  jz      short loc_18002B0B8
0x18002b080  sub     ecx, 3
0x18002b083  jz      short loc_18002B0B1
0x18002b085  sub     ecx, 0FFBh
0x18002b08b  jz      short loc_18002B0A5
0x18002b08d  sub     ecx, 1
0x18002b090  jz      short loc_18002B09E
0x18002b092  cmp     ecx, 1
0x18002b095  jnz     short loc_18002B0BF
0x18002b097  mov     ebx, 80000002h
0x18002b09c  jmp     short loc_18002B0AA
0x18002b09e  mov     ebx, 80000001h
0x18002b0a3  jmp     short loc_18002B0AA
0x18002b0a5  mov     ebx, 80000000h
0x18002b0aa  xor     esi, esi
0x18002b0ac  or      edi, 0FFFFFFFFh
0x18002b0af  jmp     short loc_18002B0C9
0x18002b0b1  mov     esi, 6
0x18002b0b6  jmp     short loc_18002B0C4
0x18002b0b8  mov     esi, 5
0x18002b0bd  jmp     short loc_18002B0C4
0x18002b0bf  mov     esi, 4
0x18002b0c4  xor     edi, edi
0x18002b0c6  lea     ebx, [rdi+7]
0x18002b0c9  xor     edx, edx; hFile
0x18002b0cb  lea     rcx, aNetshellDll; "netshell.dll"
0x18002b0d2  mov     r8d, 800h; dwFlags
0x18002b0d8  call    cs:__imp_LoadLibraryExW
0x18002b0de  mov     r14, rax
0x18002b0e1  test    rax, rax
0x18002b0e4  jz      short loc_18002B140
0x18002b0e6  lea     rdx, aHrgeticonfromm; "HrGetIconFromMediaType"
0x18002b0ed  mov     rcx, rax; hModule
0x18002b0f0  mov     r15d, 80004005h
0x18002b0f6  call    cs:__imp_GetProcAddress
0x18002b0fc  test    rax, rax
0x18002b0ff  jz      short loc_18002B125
0x18002b101  lea     rcx, [rsp+98h+arg_10]
0x18002b109  mov     r9d, ebx
0x18002b10c  mov     [rsp+98h+var_70], rcx
0x18002b111  xor     r8d, r8d
0x18002b114  lea     ecx, [rbp+20h]
0x18002b117  mov     [rsp+98h+var_78], edi
0x18002b11b  mov     edx, esi
0x18002b11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b122  mov     r15d, eax
0x18002b125  mov     rcx, r14; hLibModule
0x18002b128  call    cs:__imp_FreeLibrary
0x18002b12e  test    r15d, r15d
0x18002b131  js      short loc_18002B140
0x18002b133  mov     rax, [rsp+98h+arg_10]
0x18002b13b  test    rax, rax
0x18002b13e  jnz     short loc_18002B18B
0x18002b140  mov     rcx, cs:g_hinstDll; hInstance
0x18002b147  xorps   xmm0, xmm0
0x18002b14a  mov     edx, 233h; lpIconName
0x18002b14f  movups  xmmword ptr [rsp+98h+piconinfo.fIcon], xmm0
0x18002b154  movups  xmmword ptr [rsp+98h+piconinfo.hbmMask], xmm0
0x18002b159  call    cs:__imp_LoadIconW
0x18002b15f  test    rax, rax
0x18002b162  jz      short loc_18002B183
0x18002b164  lea     rdx, [rsp+98h+piconinfo]; piconinfo
0x18002b169  mov     rcx, rax; hIcon
0x18002b16c  call    cs:__imp_GetIconInfo
0x18002b172  test    eax, eax
0x18002b174  jz      short loc_18002B183
0x18002b176  lea     rcx, [rsp+98h+piconinfo]; piconinfo
0x18002b17b  call    cs:__imp_CreateIconIndirect
0x18002b181  jmp     short loc_18002B18B
0x18002b183  mov     rax, [rsp+98h+arg_10]
0x18002b18b  add     rsp, 68h
0x18002b18f  pop     r15
0x18002b191  pop     r14
0x18002b193  pop     rdi
0x18002b194  pop     rsi
0x18002b195  pop     rbp
0x18002b196  pop     rbx
0x18002b197  retn
```
