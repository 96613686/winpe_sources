# ceLoadSystem32Library(ushort const *)

- ea: `0x180006518`
- end: `0x180006624`
- name: `?ceLoadSystem32Library@@YAPEAUHINSTANCE__@@PEBG@Z`
- size: `268`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000550c`

## callees

- `0x1800053bc`
- `0x1800064e0`
- `0x180006518`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000656e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000656e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800065ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800065ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006534`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000658b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006534`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000658b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000660c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000660c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800065e2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800065e2`

## pseudocode

```c
HINSTANCE __fastcall ceLoadSystem32Library(const unsigned __int16 *a1)
{
  HMODULE LibraryW; // rsi
  UINT SystemDirectoryW; // eax
  UINT v4; // ebp
  DWORD v5; // ebx
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r14
  WCHAR *v9; // rax
  unsigned __int16 *v10; // rdi

  LibraryW = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v4 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    v5 = ceHLastError();
LABEL_17:
    SetLastError(v5);
    return LibraryW;
  }
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v8 = v7 + SystemDirectoryW + 1;
  v9 = (WCHAR *)LocalAlloc(0, 2 * v8 + 2);
  v10 = v9;
  if ( !v9 )
  {
    v5 = -2147024882;
    goto LABEL_17;
  }
  if ( v4 == GetSystemDirectoryW(v9, v4) )
  {
    do
      ++v6;
    while ( v10[v6] );
    if ( v10[v6 - 1] != 92 )
      StringCchCatW(v10, v8 + 1, L"\\");
    StringCchCatW(v10, v8 + 1, a1);
    LibraryW = LoadLibraryW(v10);
    if ( LibraryW )
      v5 = 0;
    else
      v5 = ceHLastError();
  }
  else
  {
    v5 = ceHLastError();
    if ( !v5 )
      v5 = -2147024785;
  }
  LocalFree(v10);
  if ( !LibraryW )
    goto LABEL_17;
  return LibraryW;
}

```

## disassembly

```asm
0x180006518  push    rbx
0x18000651a  push    rbp
0x18000651b  push    rsi
0x18000651c  push    rdi
0x18000651d  push    r12
0x18000651f  push    r14
0x180006521  push    r15
0x180006523  sub     rsp, 20h
0x180006527  mov     r15, rcx
0x18000652a  xor     r12d, r12d
0x18000652d  xor     ecx, ecx; lpBuffer
0x18000652f  xor     edx, edx; uSize
0x180006531  mov     esi, r12d
0x180006534  call    cs:__imp_GetSystemDirectoryW
0x18000653a  mov     ebp, eax
0x18000653c  test    eax, eax
0x18000653e  jnz     short loc_18000654C
0x180006540  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x180006545  mov     ebx, eax
0x180006547  jmp     loc_18000660A
0x18000654c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006550  mov     rdx, rbx
0x180006553  inc     rdx
0x180006556  cmp     [r15+rdx*2], r12w
0x18000655b  jnz     short loc_180006553
0x18000655d  lea     r14d, [rax+1]
0x180006561  xor     ecx, ecx; uFlags
0x180006563  add     r14, rdx
0x180006566  lea     rdx, ds:2[r14*2]; uBytes
0x18000656e  call    cs:__imp_LocalAlloc
0x180006574  mov     rdi, rax
0x180006577  test    rax, rax
0x18000657a  jnz     short loc_180006586
0x18000657c  mov     ebx, 8007000Eh
0x180006581  jmp     loc_18000660A
0x180006586  mov     edx, ebp; uSize
0x180006588  mov     rcx, rdi; lpBuffer
0x18000658b  call    cs:__imp_GetSystemDirectoryW
0x180006591  cmp     ebp, eax
0x180006593  jz      short loc_1800065A7
0x180006595  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x18000659a  mov     ebx, eax
0x18000659c  test    eax, eax
0x18000659e  jnz     short loc_1800065FC
0x1800065a0  mov     ebx, 8007006Fh
0x1800065a5  jmp     short loc_1800065FC
0x1800065a7  inc     rbx
0x1800065aa  cmp     [rdi+rbx*2], r12w
0x1800065af  jnz     short loc_1800065A7
0x1800065b1  mov     eax, 5Ch ; '\'
0x1800065b6  cmp     ax, [rdi+rbx*2-2]
0x1800065bb  jz      short loc_1800065D0
0x1800065bd  lea     rdx, [r14+1]; unsigned __int64
0x1800065c1  mov     rcx, rdi; unsigned __int16 *
0x1800065c4  lea     r8, asc_18000C410; "\\"
0x1800065cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800065d0  lea     rdx, [r14+1]; unsigned __int64
0x1800065d4  mov     r8, r15; unsigned __int16 *
0x1800065d7  mov     rcx, rdi; unsigned __int16 *
0x1800065da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800065df  mov     rcx, rdi; lpLibFileName
0x1800065e2  call    cs:__imp_LoadLibraryW
0x1800065e8  mov     rsi, rax
0x1800065eb  test    rax, rax
0x1800065ee  jnz     short loc_1800065F9
0x1800065f0  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x1800065f5  mov     ebx, eax
0x1800065f7  jmp     short loc_1800065FC
0x1800065f9  mov     ebx, r12d
0x1800065fc  mov     rcx, rdi; hMem
0x1800065ff  call    cs:__imp_LocalFree
0x180006605  test    rsi, rsi
0x180006608  jnz     short loc_180006612
0x18000660a  mov     ecx, ebx; dwErrCode
0x18000660c  call    cs:__imp_SetLastError
0x180006612  mov     rax, rsi
0x180006615  add     rsp, 20h
0x180006619  pop     r15
0x18000661b  pop     r14
0x18000661d  pop     r12
0x18000661f  pop     rdi
0x180006620  pop     rsi
0x180006621  pop     rbp
0x180006622  pop     rbx
0x180006623  retn
```
