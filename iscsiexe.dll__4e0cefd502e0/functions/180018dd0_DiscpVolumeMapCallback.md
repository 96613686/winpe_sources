# DiscpVolumeMapCallback

- ea: `0x180018dd0`
- end: `0x180018e7a`
- name: `DiscpVolumeMapCallback`
- size: `170`
- prototype: `DWORD __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x180003198`
- `0x18000325c`
- `0x180018dd0`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180018dfe`
- `ISCSIUM!DiscpAllocMemory` at `0x180018dfe`
- `ISCSIUM!DiscpFreeMemory` at `0x180018e58`
- `ISCSIUM!DiscpFreeMemory` at `0x180018e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e62`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180018e42`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180018e42`

## pseudocode

```c
DWORD __fastcall DiscpVolumeMapCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  unsigned int v6; // ebp
  __int64 v7; // rax
  WCHAR *v8; // rdi
  wchar_t *v9; // rbx

  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(*(_QWORD *)(a4 + 80) + 2 * v4 + 4) );
  v6 = v4 + 2;
  v7 = DiscpAllocMemory((unsigned int)(2 * (v4 + 2) + 520));
  v8 = (WCHAR *)v7;
  if ( !v7 )
    return 8;
  v9 = (wchar_t *)(v7 + 520);
  StringCchCopyW((STRSAFE_LPWSTR)(v7 + 520), v6, (STRSAFE_LPCWSTR)(*(_QWORD *)(a4 + 80) + 4LL));
  StringCchCatW(v9, v6, L"\\");
  if ( GetVolumeNameForVolumeMountPointW(v9, v8, 0x104u) )
  {
    *(_QWORD *)(a4 + 88) = v8;
    return 0;
  }
  else
  {
    DiscpFreeMemory(v8);
    *(_QWORD *)(a4 + 88) = 0;
    return GetLastError();
  }
}

```

## disassembly

```asm
0x180018dd0  push    rbx
0x180018dd2  push    rbp
0x180018dd3  push    rsi
0x180018dd4  push    rdi
0x180018dd5  push    r14
0x180018dd7  sub     rsp, 20h
0x180018ddb  mov     rcx, [r9+50h]
0x180018ddf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018de3  xor     r14d, r14d
0x180018de6  mov     rsi, r9
0x180018de9  inc     rax
0x180018dec  cmp     [rcx+rax*2+4], r14w
0x180018df2  jnz     short loc_180018DE9
0x180018df4  lea     ebp, [rax+2]
0x180018df7  lea     ecx, ds:208h[rbp*2]
0x180018dfe  call    cs:__imp_DiscpAllocMemory
0x180018e04  mov     rdi, rax
0x180018e07  test    rax, rax
0x180018e0a  jz      short loc_180018E6A
0x180018e0c  mov     r8, [rsi+50h]
0x180018e10  lea     rbx, [rax+208h]
0x180018e17  add     r8, 4; pszSrc
0x180018e1b  mov     edx, ebp; cchDest
0x180018e1d  mov     rcx, rbx; pszDest
0x180018e20  call    StringCchCopyW
0x180018e25  lea     r8, asc_180020E70; "\\"
0x180018e2c  mov     edx, ebp; cchDest
0x180018e2e  mov     rcx, rbx; pszDest
0x180018e31  call    StringCchCatW
0x180018e36  mov     r8d, 104h; cchBufferLength
0x180018e3c  mov     rdx, rdi; lpszVolumeName
0x180018e3f  mov     rcx, rbx; lpszVolumeMountPoint
0x180018e42  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180018e48  test    eax, eax
0x180018e4a  jz      short loc_180018E55
0x180018e4c  mov     [rsi+58h], rdi
0x180018e50  mov     eax, r14d
0x180018e53  jmp     short loc_180018E6F
0x180018e55  mov     rcx, rdi
0x180018e58  call    cs:__imp_DiscpFreeMemory
0x180018e5e  mov     [rsi+58h], r14
0x180018e62  call    cs:__imp_GetLastError
0x180018e68  jmp     short loc_180018E6F
0x180018e6a  mov     eax, 8
0x180018e6f  add     rsp, 20h
0x180018e73  pop     r14
0x180018e75  pop     rdi
0x180018e76  pop     rsi
0x180018e77  pop     rbp
0x180018e78  pop     rbx
0x180018e79  retn
```
