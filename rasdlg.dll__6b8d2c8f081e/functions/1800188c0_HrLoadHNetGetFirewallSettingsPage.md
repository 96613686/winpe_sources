# HrLoadHNetGetFirewallSettingsPage

- ea: `0x1800188c0`
- end: `0x180018a29`
- name: `HrLoadHNetGetFirewallSettingsPage`
- size: `361`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c2cc`

## callees

- `0x1800188c0`
- `0x18004d0d2`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001899c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001899c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001892f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001892f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018962`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018991`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018991`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800189cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800189cf`

## string_xrefs

- `0x180018955`: `hnetcfg.dll`

## pseudocode

```c
__int64 __fastcall HrLoadHNetGetFirewallSettingsPage(__int64 a1, __int64 a2)
{
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  HRESULT v9; // eax
  unsigned int v10; // ebx
  HMODULE Library; // rax
  HMODULE v12; // rsi
  signed int v13; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v22; // [rsp+20h] [rbp-39h] BYREF
  __int128 v23; // [rsp+30h] [rbp-29h]
  __int128 v24; // [rsp+40h] [rbp-19h]
  __int128 v25; // [rsp+50h] [rbp-9h]
  __int128 v26; // [rsp+60h] [rbp+7h]
  __int128 v27; // [rsp+70h] [rbp+17h]
  __int64 v28; // [rsp+80h] [rbp+27h]

  memset_0((char *)&v22 + 4, 0, 0x64u);
  v4 = v23;
  LODWORD(v22) = 104;
  *(_OWORD *)a1 = v22;
  v5 = v24;
  *(_OWORD *)(a1 + 16) = v4;
  v6 = v25;
  *(_OWORD *)(a1 + 32) = v5;
  v7 = v26;
  *(_OWORD *)(a1 + 48) = v6;
  v8 = v27;
  *(_OWORD *)(a1 + 64) = v7;
  *(_QWORD *)&v7 = v28;
  *(_OWORD *)(a1 + 80) = v8;
  *(_QWORD *)(a1 + 96) = v7;
  v9 = CoInitializeEx(0, 6u);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( v9 != -2147417850 )
      goto LABEL_14;
  }
  else
  {
    *(_DWORD *)(a2 + 952) = 1;
  }
  Library = LoadLibraryExW(L"hnetcfg.dll", 0, 0x800u);
  v12 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "HNetGetFirewallSettingsPage");
    if ( ProcAddress )
    {
      v10 = ((__int64 (__fastcall *)(__int128 *, _QWORD))ProcAddress)(&v22, *(_QWORD *)(*(_QWORD *)(a2 + 872) + 464LL));
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    FreeLibrary(v12);
  }
  else
  {
    v13 = GetLastError();
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
  }
  if ( !v10 )
  {
    v16 = v23;
    *(_OWORD *)a1 = v22;
    v17 = v24;
    *(_OWORD *)(a1 + 16) = v16;
    v18 = v25;
    *(_OWORD *)(a1 + 32) = v17;
    v19 = v26;
    *(_OWORD *)(a1 + 48) = v18;
    v20 = v27;
    *(_OWORD *)(a1 + 64) = v19;
    *(_QWORD *)&v19 = v28;
    *(_OWORD *)(a1 + 80) = v20;
    *(_QWORD *)(a1 + 96) = v19;
  }
LABEL_14:
  *(_DWORD *)(a2 + 956) = v10;
  return v10;
}

```

## disassembly

```asm
0x1800188c0  push    rbp
0x1800188c2  push    rbx
0x1800188c3  push    rsi
0x1800188c4  push    rdi
0x1800188c5  push    r14
0x1800188c7  lea     rbp, [rsp-37h]
0x1800188cc  sub     rsp, 90h
0x1800188d3  mov     r14, rdx
0x1800188d6  mov     rdi, rcx
0x1800188d9  xor     edx, edx; Val
0x1800188db  lea     rcx, [rbp+57h+var_90+4]; void *
0x1800188df  lea     r8d, [rdx+64h]; Size
0x1800188e3  call    memset_0
0x1800188e8  movaps  xmm1, [rbp+57h+var_80]
0x1800188ec  mov     edx, 6; dwCoInit
0x1800188f1  mov     dword ptr [rbp+57h+var_90], 68h ; 'h'
0x1800188f8  xor     ecx, ecx; pvReserved
0x1800188fa  movaps  xmm0, [rbp+57h+var_90]
0x1800188fe  movaps  xmmword ptr [rdi], xmm0
0x180018901  movaps  xmm0, [rbp+57h+var_70]
0x180018905  movaps  xmmword ptr [rdi+10h], xmm1
0x180018909  movaps  xmm1, [rbp+57h+var_60]
0x18001890d  movaps  xmmword ptr [rdi+20h], xmm0
0x180018911  movaps  xmm0, [rbp+57h+var_50]
0x180018915  movaps  xmmword ptr [rdi+30h], xmm1
0x180018919  movaps  xmm1, [rbp+57h+var_40]
0x18001891d  movaps  xmmword ptr [rdi+40h], xmm0
0x180018921  movsd   xmm0, [rbp+57h+var_30]
0x180018926  movaps  xmmword ptr [rdi+50h], xmm1
0x18001892a  movsd   qword ptr [rdi+60h], xmm0
0x18001892f  call    cs:__imp_CoInitializeEx
0x180018935  mov     ebx, eax
0x180018937  test    eax, eax
0x180018939  js      short loc_180018948
0x18001893b  mov     dword ptr [r14+3B8h], 1
0x180018946  jmp     short loc_180018953
0x180018948  cmp     eax, 80010106h
0x18001894d  jnz     loc_180018A12
0x180018953  xor     edx, edx; hFile
0x180018955  lea     rcx, LibFileName; "hnetcfg.dll"
0x18001895c  mov     r8d, 800h; dwFlags
0x180018962  call    cs:__imp_LoadLibraryExW
0x180018968  mov     rsi, rax
0x18001896b  test    rax, rax
0x18001896e  jnz     short loc_180018987
0x180018970  call    cs:__imp_GetLastError
0x180018976  mov     ebx, eax
0x180018978  test    eax, eax
0x18001897a  jle     short loc_1800189D5
0x18001897c  movzx   ebx, ax
0x18001897f  or      ebx, 80070000h
0x180018985  jmp     short loc_1800189D5
0x180018987  lea     rdx, ProcName; "HNetGetFirewallSettingsPage"
0x18001898e  mov     rcx, rsi; hModule
0x180018991  call    cs:__imp_GetProcAddress
0x180018997  test    rax, rax
0x18001899a  jnz     short loc_1800189B3
0x18001899c  call    cs:__imp_GetLastError
0x1800189a2  mov     ebx, eax
0x1800189a4  test    eax, eax
0x1800189a6  jle     short loc_1800189CC
0x1800189a8  movzx   ebx, ax
0x1800189ab  or      ebx, 80070000h
0x1800189b1  jmp     short loc_1800189CC
0x1800189b3  mov     rdx, [r14+368h]
0x1800189ba  lea     rcx, [rbp+57h+var_90]
0x1800189be  mov     rdx, [rdx+1D0h]
0x1800189c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189ca  mov     ebx, eax
0x1800189cc  mov     rcx, rsi; hLibModule
0x1800189cf  call    cs:__imp_FreeLibrary
0x1800189d5  test    ebx, ebx
0x1800189d7  jnz     short loc_180018A12
0x1800189d9  movaps  xmm0, [rbp+57h+var_90]
0x1800189dd  movaps  xmm1, [rbp+57h+var_80]
0x1800189e1  movaps  xmmword ptr [rdi], xmm0
0x1800189e4  movaps  xmm0, [rbp+57h+var_70]
0x1800189e8  movaps  xmmword ptr [rdi+10h], xmm1
0x1800189ec  movaps  xmm1, [rbp+57h+var_60]
0x1800189f0  movaps  xmmword ptr [rdi+20h], xmm0
0x1800189f4  movaps  xmm0, [rbp+57h+var_50]
0x1800189f8  movaps  xmmword ptr [rdi+30h], xmm1
0x1800189fc  movaps  xmm1, [rbp+57h+var_40]
0x180018a00  movaps  xmmword ptr [rdi+40h], xmm0
0x180018a04  movsd   xmm0, [rbp+57h+var_30]
0x180018a09  movaps  xmmword ptr [rdi+50h], xmm1
0x180018a0d  movsd   qword ptr [rdi+60h], xmm0
0x180018a12  mov     [r14+3BCh], ebx
0x180018a19  mov     eax, ebx
0x180018a1b  add     rsp, 90h
0x180018a22  pop     r14
0x180018a24  pop     rdi
0x180018a25  pop     rsi
0x180018a26  pop     rbx
0x180018a27  pop     rbp
0x180018a28  retn
```
