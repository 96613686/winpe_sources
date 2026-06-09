# FormatServerNameForMprCfgApis

- ea: `0x18001833c`
- end: `0x180018469`
- name: `FormatServerNameForMprCfgApis`
- size: `301`
- prototype: `__int64 __fastcall(LPCWSTR lpString1)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800265c0`

## callees

- `0x180016c40`
- `0x18001833c`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800183f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800183f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018405`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018405`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800183bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800183bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800183d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800183d5`

## pseudocode

```c
DWORD __fastcall FormatServerNameForMprCfgApis(LPCWSTR lpString1, unsigned int a2, unsigned __int16 **a3)
{
  LPCWSTR v4; // rdi
  __int64 v6; // rsi
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  DWORD nSize[4]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR Buffer[512]; // [rsp+30h] [rbp-428h] BYREF

  v4 = lpString1;
  if ( !lpString1 || !*lpString1 )
    goto LABEL_18;
  if ( *lpString1 == 92 && a2 >= 3 )
  {
    if ( !lpString1[1] )
      return 11;
    v4 = lpString1 + 2;
    if ( lpString1[2] == 92 || !*v4 )
      return 11;
  }
  nSize[0] = 512;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize) )
    return GetLastError();
  if ( lstrcmpiW(v4, Buffer) )
  {
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( v4[v7] );
    ProcessHeap = GetProcessHeap();
    v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v7 + 6);
    v10 = v9;
    if ( !v9 )
      return 8;
    do
      ++v6;
    while ( v4[v6] );
    StringCchPrintfW(v9, v6 + 3, L"\\\\%s", v4);
    *a3 = v10;
  }
  else
  {
LABEL_18:
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001833c  mov     [rsp+arg_8], rbx
0x180018341  mov     [rsp+arg_18], rbp
0x180018346  push    rsi
0x180018347  push    rdi
0x180018348  push    r14
0x18001834a  sub     rsp, 440h
0x180018351  mov     rax, cs:__security_cookie
0x180018358  xor     rax, rsp
0x18001835b  mov     [rsp+458h+var_28], rax
0x180018363  xor     ebp, ebp
0x180018365  mov     r14, r8
0x180018368  mov     rdi, rcx
0x18001836b  test    rcx, rcx
0x18001836e  jz      loc_18001843C
0x180018374  cmp     [rcx], bp
0x180018377  jz      loc_18001843C
0x18001837d  cmp     word ptr [rcx], 5Ch ; '\'
0x180018381  jnz     short loc_1800183A7
0x180018383  cmp     edx, 3
0x180018386  jb      short loc_1800183A7
0x180018388  cmp     [rcx+2], bp
0x18001838c  jz      short loc_18001839D
0x18001838e  add     rdi, 4
0x180018392  cmp     word ptr [rdi], 5Ch ; '\'
0x180018396  jz      short loc_18001839D
0x180018398  cmp     [rdi], bp
0x18001839b  jnz     short loc_1800183A7
0x18001839d  mov     eax, 0Bh
0x1800183a2  jmp     loc_180018441
0x1800183a7  lea     r8, [rsp+458h+nSize]; nSize
0x1800183ac  mov     [rsp+458h+nSize], 200h
0x1800183b4  lea     rdx, [rsp+458h+Buffer]; lpBuffer
0x1800183b9  xor     ecx, ecx; NameType
0x1800183bb  call    cs:__imp_GetComputerNameExW
0x1800183c1  test    eax, eax
0x1800183c3  jnz     short loc_1800183CD
0x1800183c5  call    cs:__imp_GetLastError
0x1800183cb  jmp     short loc_180018441
0x1800183cd  lea     rdx, [rsp+458h+Buffer]; lpString2
0x1800183d2  mov     rcx, rdi; lpString1
0x1800183d5  call    cs:__imp_lstrcmpiW
0x1800183db  test    eax, eax
0x1800183dd  jz      short loc_18001843C
0x1800183df  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800183e3  mov     rbx, rsi
0x1800183e6  inc     rbx
0x1800183e9  cmp     [rdi+rbx*2], bp
0x1800183ed  jnz     short loc_1800183E6
0x1800183ef  lea     rbx, ds:6[rbx*2]
0x1800183f7  call    cs:__imp_GetProcessHeap
0x1800183fd  mov     r8, rbx; dwBytes
0x180018400  xor     edx, edx; dwFlags
0x180018402  mov     rcx, rax; hHeap
0x180018405  call    cs:__imp_HeapAlloc
0x18001840b  mov     rbx, rax
0x18001840e  test    rax, rax
0x180018411  jnz     short loc_180018418
0x180018413  lea     eax, [rbx+8]
0x180018416  jmp     short loc_180018441
0x180018418  inc     rsi
0x18001841b  cmp     [rdi+rsi*2], bp
0x18001841f  jnz     short loc_180018418
0x180018421  lea     rdx, [rsi+3]; unsigned __int64
0x180018425  mov     r9, rdi
0x180018428  lea     r8, aS_0; "\\\\%s"
0x18001842f  mov     rcx, rbx; unsigned __int16 *
0x180018432  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018437  mov     [r14], rbx
0x18001843a  jmp     short loc_18001843F
0x18001843c  mov     [r14], rbp
0x18001843f  xor     eax, eax
0x180018441  mov     rcx, [rsp+458h+var_28]
0x180018449  xor     rcx, rsp; StackCookie
0x18001844c  call    __security_check_cookie
0x180018451  lea     r11, [rsp+458h+var_18]
0x180018459  mov     rbx, [r11+28h]
0x18001845d  mov     rbp, [r11+38h]
0x180018461  mov     rsp, r11
0x180018464  pop     r14
0x180018466  pop     rdi
0x180018467  pop     rsi
0x180018468  retn
```
