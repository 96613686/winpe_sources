# PuQueryAccessPathsToVolume(ushort *,ushort * *)

- ea: `0x1801a6264`
- end: `0x1801a6400`
- name: `?PuQueryAccessPathsToVolume@@YAHPEAGPEAPEAG@Z`
- size: `412`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18019e954`
- `0x1801a36b4`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x1800298d0`
- `0x18002b5e4`
- `0x1801a6264`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a6325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a6325`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a63c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a63c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a6348`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a63a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a6348`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a63a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a6365`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a6365`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a6317`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a638b`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a6317`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a638b`

## pseudocode

```c
__int64 __fastcall PuQueryAccessPathsToVolume(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int64 v4; // r9
  __int64 v5; // r11
  BOOL VolumePathNamesForVolumeNameW; // ebx
  DWORD LastError; // eax
  unsigned int v8; // ebx
  __int64 v9; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  unsigned __int16 *v12; // rdi
  HANDLE v13; // rax
  unsigned int v14; // edx
  DWORD cchReturnLength; // [rsp+20h] [rbp-E0h] BYREF
  DWORD v17[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR szVolumeName[264]; // [rsp+30h] [rbp-D0h] BYREF

  cchReturnLength = 0;
  v17[0] = 0;
  *a2 = 0;
  if ( !a1 )
    return 1;
  memset_0(szVolumeName, 0, 0x208u);
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  StringCchCopyNW(szVolumeName, 0x104u, a1, v4);
  do
    ++v5;
  while ( szVolumeName[v5] );
  if ( *((_WORD *)&v17[2] + v5 + 1) != 92 )
    szVolumeName[v5] = 92;
  VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, &cchReturnLength);
  LastError = GetLastError();
  if ( !VolumePathNamesForVolumeNameW && LastError != 234 )
    return 0;
  v9 = cchReturnLength;
  ProcessHeap = GetProcessHeap();
  if ( !ProcessHeap || (v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * v9), (v12 = v11) == 0) )
  {
    SetLastError(8u);
    return 0;
  }
  v8 = GetVolumePathNamesForVolumeNameW(szVolumeName, v11, cchReturnLength, v17);
  if ( v8 )
  {
    *a2 = v12;
  }
  else
  {
    v13 = GetProcessHeap();
    PmHeapFree(v13, v14, v12);
  }
  return v8;
}

```

## disassembly

```asm
0x1801a6264  mov     [rsp-8+arg_10], rbx
0x1801a6269  mov     [rsp-8+arg_18], rsi
0x1801a626e  push    rbp
0x1801a626f  push    rdi
0x1801a6270  push    r14
0x1801a6272  lea     rbp, [rsp-150h]
0x1801a627a  sub     rsp, 250h
0x1801a6281  mov     rax, cs:__security_cookie
0x1801a6288  xor     rax, rsp
0x1801a628b  mov     [rbp+160h+var_20], rax
0x1801a6292  xor     r14d, r14d
0x1801a6295  mov     rsi, rdx
0x1801a6298  mov     [rsp+260h+cchReturnLength], r14d
0x1801a629d  mov     rbx, rcx
0x1801a62a0  mov     [rsp+260h+var_23C], r14d
0x1801a62a5  mov     [rdx], r14
0x1801a62a8  test    rcx, rcx
0x1801a62ab  jz      loc_1801A63D1
0x1801a62b1  xor     edx, edx; Val
0x1801a62b3  lea     rcx, [rsp+260h+szVolumeName]; void *
0x1801a62b8  mov     r8d, 208h; Size
0x1801a62be  call    memset_0
0x1801a62c3  or      r11, 0FFFFFFFFFFFFFFFFh
0x1801a62c7  mov     r9, r11
0x1801a62ca  inc     r9; unsigned __int64
0x1801a62cd  cmp     [rbx+r9*2], r14w
0x1801a62d2  jnz     short loc_1801A62CA
0x1801a62d4  mov     r8, rbx; unsigned __int16 *
0x1801a62d7  lea     rcx, [rsp+260h+szVolumeName]; unsigned __int16 *
0x1801a62dc  mov     edx, 104h; unsigned __int64
0x1801a62e1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801a62e6  lea     rax, [rsp+260h+szVolumeName]
0x1801a62eb  inc     r11
0x1801a62ee  cmp     [rax+r11*2], r14w
0x1801a62f3  jnz     short loc_1801A62EB
0x1801a62f5  mov     eax, 5Ch ; '\'
0x1801a62fa  cmp     [rsp+r11*2+260h+var_232], ax
0x1801a6300  jz      short loc_1801A6308
0x1801a6302  mov     [rsp+r11*2+260h+szVolumeName], ax
0x1801a6308  lea     r9, [rsp+260h+cchReturnLength]; lpcchReturnLength
0x1801a630d  xor     r8d, r8d; cchBufferLength
0x1801a6310  xor     edx, edx; lpszVolumePathNames
0x1801a6312  lea     rcx, [rsp+260h+szVolumeName]; lpszVolumeName
0x1801a6317  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1801a631e  nop     dword ptr [rax+rax+00h]
0x1801a6323  mov     ebx, eax
0x1801a6325  call    cs:__imp_GetLastError
0x1801a632c  nop     dword ptr [rax+rax+00h]
0x1801a6331  test    ebx, ebx
0x1801a6333  jnz     short loc_1801A6344
0x1801a6335  cmp     eax, 0EAh
0x1801a633a  jz      short loc_1801A6344
0x1801a633c  mov     ebx, r14d
0x1801a633f  jmp     loc_1801A63D6
0x1801a6344  mov     ebx, [rsp+260h+cchReturnLength]
0x1801a6348  call    cs:__imp_GetProcessHeap
0x1801a634f  nop     dword ptr [rax+rax+00h]
0x1801a6354  test    rax, rax
0x1801a6357  jz      short loc_1801A63BB
0x1801a6359  lea     r8, [rbx+rbx]; dwBytes
0x1801a635d  mov     edx, 8; dwFlags
0x1801a6362  mov     rcx, rax; hHeap
0x1801a6365  call    cs:__imp_HeapAlloc
0x1801a636c  nop     dword ptr [rax+rax+00h]
0x1801a6371  mov     rdi, rax
0x1801a6374  test    rax, rax
0x1801a6377  jz      short loc_1801A63BB
0x1801a6379  mov     r8d, [rsp+260h+cchReturnLength]; cchBufferLength
0x1801a637e  lea     r9, [rsp+260h+var_23C]; lpcchReturnLength
0x1801a6383  mov     rdx, rax; lpszVolumePathNames
0x1801a6386  lea     rcx, [rsp+260h+szVolumeName]; lpszVolumeName
0x1801a638b  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1801a6392  nop     dword ptr [rax+rax+00h]
0x1801a6397  mov     ebx, eax
0x1801a6399  test    eax, eax
0x1801a639b  jz      short loc_1801A63A2
0x1801a639d  mov     [rsi], rdi
0x1801a63a0  jmp     short loc_1801A63D6
0x1801a63a2  call    cs:__imp_GetProcessHeap
0x1801a63a9  nop     dword ptr [rax+rax+00h]
0x1801a63ae  mov     rcx, rax; void *
0x1801a63b1  mov     r8, rdi; void *
0x1801a63b4  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a63b9  jmp     short loc_1801A63D6
0x1801a63bb  mov     ecx, 8; dwErrCode
0x1801a63c0  call    cs:__imp_SetLastError
0x1801a63c7  nop     dword ptr [rax+rax+00h]
0x1801a63cc  jmp     loc_1801A633C
0x1801a63d1  mov     ebx, 1
0x1801a63d6  mov     eax, ebx
0x1801a63d8  mov     rcx, [rbp+160h+var_20]
0x1801a63df  xor     rcx, rsp; StackCookie
0x1801a63e2  call    __security_check_cookie
0x1801a63e7  lea     r11, [rsp+260h+var_10]
0x1801a63ef  mov     rbx, [r11+30h]
0x1801a63f3  mov     rsi, [r11+38h]
0x1801a63f7  mov     rsp, r11
0x1801a63fa  pop     r14
0x1801a63fc  pop     rdi
0x1801a63fd  pop     rbp
0x1801a63fe  retn
```
