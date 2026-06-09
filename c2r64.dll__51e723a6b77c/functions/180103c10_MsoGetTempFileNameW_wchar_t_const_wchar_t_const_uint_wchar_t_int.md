# MsoGetTempFileNameW(wchar_t const *,wchar_t const *,uint,wchar_t *,int)

- ea: `0x180103c10`
- end: `0x180103d26`
- name: `?MsoGetTempFileNameW@@YAIPEB_W0IPEA_WH@Z`
- size: `278`
- prototype: `unsigned int __fastcall(const wchar_t *, const wchar_t *, unsigned int, wchar_t *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180140690`

## callees

- `0x1800264b4`
- `0x180027150`
- `0x18003e690`
- `0x18003f5a0`
- `0x180103c10`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180103cdc`
- `KERNEL32!DeleteFileW` at `0x180103cdc`
- `KERNEL32!GetTempFileNameW` at `0x180103c72`
- `KERNEL32!GetTempFileNameW` at `0x180103ca6`
- `KERNEL32!GetTempFileNameW` at `0x180103c72`
- `KERNEL32!GetTempFileNameW` at `0x180103ca6`

## pseudocode

```c
UINT __fastcall MsoGetTempFileNameW(const wchar_t *a1, const wchar_t *a2, __int64 a3, wchar_t *a4, int a5)
{
  UINT TempFileNameW; // esi
  __int64 v8; // rcx
  WCHAR TempFileName[2088]; // [rsp+20h] [rbp-1068h] BYREF

  if ( a5 <= 0 )
    return 0;
  if ( a4 != a1 )
    *a4 = 0;
  if ( a5 >= 2084 )
    return GetTempFileNameW(a1, L"mso", 0, a4);
  memset(TempFileName, 0, 4168);
  TempFileNameW = GetTempFileNameW(a1, L"mso", 0, TempFileName);
  if ( TempFileNameW )
  {
    v8 = -1;
    do
      ++v8;
    while ( TempFileName[v8] );
    if ( (int)v8 >= a5 )
    {
      MsoShipAssertTagProc(50643358);
      DeleteFileW(TempFileName);
      return 0;
    }
    _mm_lfence();
    MsoWzCopy(TempFileName, a4, a5);
  }
  return TempFileNameW;
}

```

## disassembly

```asm
0x180103c10  mov     [rsp+arg_8], rbx
0x180103c15  mov     [rsp+arg_10], rbp
0x180103c1a  push    rsi
0x180103c1b  mov     eax, 1080h
0x180103c20  call    _alloca_probe
0x180103c25  sub     rsp, rax
0x180103c28  mov     rax, cs:__security_cookie
0x180103c2f  xor     rax, rsp
0x180103c32  mov     [rsp+1088h+var_18], rax
0x180103c3a  xor     ebp, ebp
0x180103c3c  mov     rbx, r9
0x180103c3f  mov     rsi, rcx
0x180103c42  cmp     [rsp+1088h+arg_20], ebp
0x180103c49  jg      short loc_180103C52
0x180103c4b  xor     eax, eax
0x180103c4d  jmp     loc_180103D01
0x180103c52  cmp     rbx, rsi
0x180103c55  jz      short loc_180103C5B
0x180103c57  mov     [r9], bp
0x180103c5b  cmp     [rsp+1088h+arg_20], 824h
0x180103c66  jl      short loc_180103C7D
0x180103c68  xor     r8d, r8d; uUnique
0x180103c6b  lea     rdx, PrefixString; "mso"
0x180103c72  call    cs:__imp_GetTempFileNameW
0x180103c78  jmp     loc_180103D01
0x180103c7d  xor     edx, edx; Val
0x180103c7f  mov     [rsp+1088h+TempFileName], bp
0x180103c84  mov     r8d, 1046h; Size
0x180103c8a  lea     rcx, [rsp+1088h+var_1066]; void *
0x180103c8f  call    memset
0x180103c94  lea     r9, [rsp+1088h+TempFileName]; lpTempFileName
0x180103c99  xor     r8d, r8d; uUnique
0x180103c9c  lea     rdx, PrefixString; "mso"
0x180103ca3  mov     rcx, rsi; lpPathName
0x180103ca6  call    cs:__imp_GetTempFileNameW
0x180103cac  mov     esi, eax
0x180103cae  test    eax, eax
0x180103cb0  jz      short loc_180103CFF
0x180103cb2  lea     rax, [rsp+1088h+TempFileName]
0x180103cb7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180103cbb  inc     rcx
0x180103cbe  cmp     [rax+rcx*2], bp
0x180103cc2  jnz     short loc_180103CBB
0x180103cc4  cmp     ecx, [rsp+1088h+arg_20]
0x180103ccb  jl      short loc_180103CE7
0x180103ccd  mov     ecx, 304C19Eh
0x180103cd2  call    MsoShipAssertTagProc
0x180103cd7  lea     rcx, [rsp+1088h+TempFileName]; lpFileName
0x180103cdc  call    cs:__imp_DeleteFileW
0x180103ce2  jmp     loc_180103C4B
0x180103ce7  lfence
0x180103cea  mov     r8d, [rsp+1088h+arg_20]; int
0x180103cf2  lea     rcx, [rsp+1088h+TempFileName]; Source
0x180103cf7  mov     rdx, rbx; Destination
0x180103cfa  call    ?MsoWzCopy@@YAPEA_WPEB_WPEA_WH@Z; MsoWzCopy(wchar_t const *,wchar_t *,int)
0x180103cff  mov     eax, esi
0x180103d01  mov     rcx, [rsp+1088h+var_18]
0x180103d09  xor     rcx, rsp; StackCookie
0x180103d0c  call    __security_check_cookie
0x180103d11  lea     r11, [rsp+1088h+var_8]
0x180103d19  mov     rbx, [r11+18h]
0x180103d1d  mov     rbp, [r11+20h]
0x180103d21  mov     rsp, r11
0x180103d24  pop     rsi
0x180103d25  retn
```
