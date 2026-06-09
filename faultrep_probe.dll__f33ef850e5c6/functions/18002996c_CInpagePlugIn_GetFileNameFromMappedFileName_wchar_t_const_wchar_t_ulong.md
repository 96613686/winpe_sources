# CInpagePlugIn::GetFileNameFromMappedFileName(wchar_t const *,wchar_t *,ulong)

- ea: `0x18002996c`
- end: `0x180029b59`
- name: `?GetFileNameFromMappedFileName@CInpagePlugIn@@AEAAJPEB_WPEA_WK@Z`
- size: `493`
- prototype: `int(CInpagePlugIn *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800297fc`

## callees

- `0x180002890`
- `0x180003474`
- `0x180006684`
- `0x18002996c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029ada`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029ada`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180029a9a`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180029a9a`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x180029a5f`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x180029a5f`

## pseudocode

```c
__int64 __fastcall CInpagePlugIn::GetFileNameFromMappedFileName(CInpagePlugIn *this, const wchar_t *a2, wchar_t *a3)
{
  unsigned __int64 v5; // rdi
  __int64 v6; // r10
  int v7; // ecx
  int v8; // r9d
  int v9; // r8d
  int v10; // edx
  __int64 result; // rax
  WCHAR v12; // ax
  WCHAR *p_Buffer; // r14
  unsigned __int64 v14; // rbx
  WCHAR DeviceName; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+32h] [rbp-CEh]
  WCHAR Buffer; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[526]; // [rsp+42h] [rbp-BEh] BYREF
  WCHAR TargetPath[264]; // [rsp+250h] [rbp+150h] BYREF

  Buffer = 0;
  memset_0(v19, 0, 0x206u);
  if ( !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 >= 0x18 )
  {
    if ( L"\\Device\\LanmanRedirector" == a2 )
    {
LABEL_14:
      result = StringCchPrintfW(a3, 0x104u, L"\\%s", a2 + 24);
      if ( (int)result < 0 )
        return result;
      return 0;
    }
    v6 = 0;
    while ( 1 )
    {
      v7 = a2[v6];
      v8 = aDeviceLanmanre[v6];
      v9 = v7 - 32;
      if ( (unsigned int)(v7 - 97) >= 0x1A )
        v9 = a2[v6];
      v10 = v8 - 32;
      if ( (unsigned int)(v8 - 97) >= 0x1A )
        v10 = aDeviceLanmanre[v6];
      if ( v10 != v9 )
        break;
      if ( ++v6 == 24 )
        goto LABEL_14;
    }
  }
  if ( !GetLogicalDriveStringsW(0x103u, &Buffer) )
    return 0;
  v12 = Buffer;
  p_Buffer = &Buffer;
  v17 = 58;
  TargetPath[0] = 0;
  while ( 1 )
  {
    DeviceName = v12;
    if ( QueryDosDeviceW(&DeviceName, TargetPath, 0x103u) )
    {
      v14 = -1;
      do
        ++v14;
      while ( TargetPath[v14] );
      if ( (!v14 || v14 <= v5 && CompareStringOrdinal(a2, v14, TargetPath, v14, 1) == 2) && v14 < v5 )
        break;
    }
    while ( *p_Buffer++ )
      ;
    v12 = *p_Buffer;
    if ( !*p_Buffer )
      return 0;
  }
  return StringCchPrintfW(a3, 0x104u, L"%s%s", &DeviceName, &a2[v14]);
}

```

## disassembly

```asm
0x18002996c  mov     [rsp-8+arg_0], rbx
0x180029971  mov     [rsp-8+arg_18], rsi
0x180029976  push    rbp
0x180029977  push    rdi
0x180029978  push    r12
0x18002997a  push    r14
0x18002997c  push    r15
0x18002997e  lea     rbp, [rsp-370h]
0x180029986  sub     rsp, 470h
0x18002998d  mov     rax, cs:__security_cookie
0x180029994  xor     rax, rsp
0x180029997  mov     [rbp+390h+var_30], rax
0x18002999e  mov     r15, r8
0x1800299a1  lea     rcx, [rsp+490h+var_44E]; void *
0x1800299a6  mov     rsi, rdx
0x1800299a9  xor     r12d, r12d
0x1800299ac  xor     edx, edx; Val
0x1800299ae  mov     [rsp+490h+Buffer], r12w
0x1800299b4  mov     r8d, 206h; Size
0x1800299ba  call    memset_0
0x1800299bf  test    rsi, rsi
0x1800299c2  jz      loc_180029B29
0x1800299c8  test    r15, r15
0x1800299cb  jz      loc_180029B29
0x1800299d1  mov     [r15], r12w
0x1800299d5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800299d9  inc     rdi
0x1800299dc  cmp     [rsi+rdi*2], r12w
0x1800299e1  jnz     short loc_1800299D9
0x1800299e3  cmp     rdi, 18h
0x1800299e7  jb      short loc_180029A55
0x1800299e9  mov     r11, cs:off_18004D990; "\\Device\\LanmanRedirector"
0x1800299f0  cmp     r11, rsi
0x1800299f3  jz      short loc_180029A2D
0x1800299f5  mov     r10, r12
0x1800299f8  movzx   ecx, word ptr [rsi+r10*2]
0x1800299fd  movzx   r9d, word ptr [r11+r10*2]
0x180029a02  lea     eax, [rcx-61h]
0x180029a05  cmp     eax, 1Ah
0x180029a08  lea     r8d, [rcx-20h]
0x180029a0c  lea     eax, [r9-61h]
0x180029a10  cmovnb  r8d, ecx
0x180029a14  lea     edx, [r9-20h]
0x180029a18  cmp     eax, 1Ah
0x180029a1b  cmovnb  edx, r9d
0x180029a1f  cmp     edx, r8d
0x180029a22  jnz     short loc_180029A55
0x180029a24  inc     r10
0x180029a27  cmp     r10, 18h
0x180029a2b  jnz     short loc_1800299F8
0x180029a2d  lea     r9, [rsi+30h]
0x180029a31  mov     edx, 104h; unsigned __int64
0x180029a36  lea     r8, aS_2; "\\%s"
0x180029a3d  mov     rcx, r15; wchar_t *
0x180029a40  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180029a45  test    eax, eax
0x180029a47  js      loc_180029B2E
0x180029a4d  mov     eax, r12d
0x180029a50  jmp     loc_180029B2E
0x180029a55  lea     rdx, [rsp+490h+Buffer]; lpBuffer
0x180029a5a  mov     ecx, 103h; nBufferLength
0x180029a5f  call    cs:__imp_GetLogicalDriveStringsW
0x180029a65  test    eax, eax
0x180029a67  jz      short loc_180029A4D
0x180029a69  movzx   eax, [rsp+490h+Buffer]
0x180029a6e  lea     r14, [rsp+490h+Buffer]
0x180029a73  mov     [rsp+490h+var_45E], 3Ah ; ':'
0x180029a7b  mov     [rbp+390h+TargetPath], r12w
0x180029a83  mov     r8d, 103h; ucchMax
0x180029a89  mov     [rsp+490h+DeviceName], ax
0x180029a8e  lea     rdx, [rbp+390h+TargetPath]; lpTargetPath
0x180029a95  lea     rcx, [rsp+490h+DeviceName]; lpDeviceName
0x180029a9a  call    cs:__imp_QueryDosDeviceW
0x180029aa0  test    eax, eax
0x180029aa2  jz      short loc_180029AEA
0x180029aa4  lea     rax, [rbp+390h+TargetPath]
0x180029aab  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180029aaf  inc     rbx
0x180029ab2  cmp     [rax+rbx*2], r12w
0x180029ab7  jnz     short loc_180029AAF
0x180029ab9  test    rbx, rbx
0x180029abc  jz      short loc_180029AE5
0x180029abe  cmp     rbx, rdi
0x180029ac1  ja      short loc_180029AEA
0x180029ac3  mov     r9d, ebx; cchCount2
0x180029ac6  mov     [rsp+490h+bIgnoreCase], 1; bIgnoreCase
0x180029ace  lea     r8, [rbp+390h+TargetPath]; lpString2
0x180029ad5  mov     edx, ebx; cchCount1
0x180029ad7  mov     rcx, rsi; lpString1
0x180029ada  call    cs:__imp_CompareStringOrdinal
0x180029ae0  cmp     eax, 2
0x180029ae3  jnz     short loc_180029AEA
0x180029ae5  cmp     rbx, rdi
0x180029ae8  jb      short loc_180029B05
0x180029aea  movzx   eax, word ptr [r14]
0x180029aee  add     r14, 2
0x180029af2  test    ax, ax
0x180029af5  jnz     short loc_180029AEA
0x180029af7  movzx   eax, word ptr [r14]
0x180029afb  test    ax, ax
0x180029afe  jnz     short loc_180029A83
0x180029b00  jmp     loc_180029A4D
0x180029b05  lea     rax, [rsi+rbx*2]
0x180029b09  mov     edx, 104h; unsigned __int64
0x180029b0e  lea     r9, [rsp+490h+DeviceName]
0x180029b13  mov     qword ptr [rsp+490h+bIgnoreCase], rax
0x180029b18  lea     r8, aSS_1; "%s%s"
0x180029b1f  mov     rcx, r15; wchar_t *
0x180029b22  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180029b27  jmp     short loc_180029B2E
0x180029b29  mov     eax, 80070057h
0x180029b2e  mov     rcx, [rbp+390h+var_30]
0x180029b35  xor     rcx, rsp; StackCookie
0x180029b38  call    __security_check_cookie
0x180029b3d  lea     r11, [rsp+490h+var_20]
0x180029b45  mov     rbx, [r11+30h]
0x180029b49  mov     rsi, [r11+48h]
0x180029b4d  mov     rsp, r11
0x180029b50  pop     r15
0x180029b52  pop     r14
0x180029b54  pop     r12
0x180029b56  pop     rdi
0x180029b57  pop     rbp
0x180029b58  retn
```
