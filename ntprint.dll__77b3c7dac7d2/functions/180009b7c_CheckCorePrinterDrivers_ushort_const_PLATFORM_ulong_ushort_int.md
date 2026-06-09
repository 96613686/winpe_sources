# CheckCorePrinterDrivers(ushort const *,PLATFORM,ulong,ushort * *,int *)

- ea: `0x180009b7c`
- end: `0x180009d5e`
- name: `?CheckCorePrinterDrivers@@YAJPEBGW4PLATFORM@@KPEAPEAGPEAH@Z`
- size: `482`
- prototype: `int __high(const unsigned __int16 *, enum PLATFORM, unsigned int, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800093a4`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x180009b7c`
- `0x18000b11c`
- `0x18000d290`
- `0x180012b28`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009c55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009c55`
- `WINSPOOL!GetCorePrinterDriversW` at `0x180009cca`
- `WINSPOOL!GetCorePrinterDriversW` at `0x180009cca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009cda`

## pseudocode

```c
__int64 __fastcall CheckCorePrinterDrivers(
        const WCHAR *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int16 **a4,
        _DWORD *a5)
{
  int v7; // r8d
  __int64 v8; // r9
  HLOCAL v9; // rsi
  int v10; // ebx
  unsigned __int64 v11; // r13
  __int64 v12; // rdi
  const unsigned __int16 *v13; // rcx
  unsigned __int64 v14; // rbx
  __int64 v15; // r11
  HRESULT CorePrinterDriversW; // eax
  unsigned __int64 v19; // [rsp+38h] [rbp-290h] BYREF
  LPCWSTR pszServer; // [rsp+40h] [rbp-288h]
  struct _CORE_PRINTER_DRIVERW pCorePrinterDrivers; // [rsp+50h] [rbp-278h] BYREF

  pszServer = a1;
  if ( !(unsigned int)ValidPlatform(a2) || !v7 || !v8 || !a5 || *a5 )
    return (unsigned int)-2147024809;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  while ( (unsigned int)v12 < a3 )
  {
    v13 = a4[v12];
    if ( !v13 )
      goto LABEL_21;
    v19 = 0;
    v10 = StringCchLengthW(v13, 0x7FFFFFFFu, &v19);
    if ( v10 < 0 )
      goto LABEL_21;
    v14 = v19 + 2;
    if ( v11 < v19 + 2 )
    {
      if ( v9 )
        LocalFree(v9);
      v9 = LocalAlloc(0x40u, (unsigned int)(2 * v14));
      if ( !v9 )
        return (unsigned int)-2147024882;
      v11 = v14;
    }
    v10 = StringCchCopyW((unsigned __int16 *)v9, v11, a4[v12]);
    if ( v10 < 0 )
      goto LABEL_21;
    *((_WORD *)v9 + v15 + 1) = 0;
    pCorePrinterDrivers.CoreDriverGUID.Data1 = 0;
    memset_0(&pCorePrinterDrivers.CoreDriverGUID.Data2, 0, 0x224u);
    CorePrinterDriversW = GetCorePrinterDriversW(
                            pszServer,
                            (LPCWSTR)PlatformEnv[a2],
                            (LPCWSTR)v9,
                            1u,
                            &pCorePrinterDrivers);
    v10 = CorePrinterDriversW;
    if ( CorePrinterDriversW >= 0 )
    {
      CoTaskMemFree(a4[v12]);
      a4[v12] = 0;
      goto LABEL_18;
    }
    if ( (_WORD)CorePrinterDriversW == 1168 )
    {
      v10 = 0;
LABEL_18:
      v12 = (unsigned int)(v12 + 1);
    }
    else
    {
LABEL_21:
      v12 = (unsigned int)(v12 + 1);
      if ( v10 < 0 )
        break;
    }
  }
  if ( v9 )
    LocalFree(v9);
  if ( v10 >= 0 )
    *a5 = FoundAllCommonDrivers(a3, a4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009b7c  mov     [rsp+arg_10], rbx
0x180009b81  push    rbp
0x180009b82  push    rsi
0x180009b83  push    rdi
0x180009b84  push    r12
0x180009b86  push    r13
0x180009b88  push    r14
0x180009b8a  push    r15
0x180009b8c  sub     rsp, 290h
0x180009b93  mov     rax, cs:__security_cookie
0x180009b9a  xor     rax, rsp
0x180009b9d  mov     [rsp+2C8h+var_48], rax
0x180009ba5  mov     r15, [rsp+2C8h+arg_20]
0x180009bad  mov     r14, r9
0x180009bb0  mov     [rsp+2C8h+pszServer], rcx
0x180009bb5  mov     r12d, r8d
0x180009bb8  mov     ecx, edx
0x180009bba  mov     [rsp+2C8h+var_298], edx
0x180009bbe  call    ValidPlatform
0x180009bc3  test    eax, eax
0x180009bc5  jz      loc_180009D2C
0x180009bcb  test    r8d, r8d
0x180009bce  jz      loc_180009D2C
0x180009bd4  test    r9, r9
0x180009bd7  jz      loc_180009D2C
0x180009bdd  test    r15, r15
0x180009be0  jz      loc_180009D2C
0x180009be6  cmp     dword ptr [r15], 0
0x180009bea  jnz     loc_180009D2C
0x180009bf0  xor     esi, esi
0x180009bf2  xor     ebx, ebx
0x180009bf4  xor     r13d, r13d
0x180009bf7  xor     edi, edi
0x180009bf9  cmp     edi, r12d
0x180009bfc  jnb     loc_180009D03
0x180009c02  mov     rcx, [r14+rdi*8]; unsigned __int16 *
0x180009c06  test    rcx, rcx
0x180009c09  jz      loc_180009CF9
0x180009c0f  lea     r8, [rsp+2C8h+var_290]; unsigned __int64 *
0x180009c14  mov     [rsp+2C8h+var_290], 0
0x180009c1d  mov     edx, 7FFFFFFFh; unsigned __int64
0x180009c22  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180009c27  mov     ebx, eax
0x180009c29  test    eax, eax
0x180009c2b  js      loc_180009CF9
0x180009c31  mov     r11, [rsp+2C8h+var_290]
0x180009c36  lea     rbx, [r11+2]
0x180009c3a  cmp     r13, rbx
0x180009c3d  jnb     short loc_180009C6F
0x180009c3f  test    rsi, rsi
0x180009c42  jz      short loc_180009C4D
0x180009c44  mov     rcx, rsi; hMem
0x180009c47  call    cs:__imp_LocalFree
0x180009c4d  lea     edx, [rbx+rbx]; uBytes
0x180009c50  mov     ecx, 40h ; '@'; uFlags
0x180009c55  call    cs:__imp_LocalAlloc
0x180009c5b  mov     rsi, rax
0x180009c5e  test    rax, rax
0x180009c61  jz      loc_180009D25
0x180009c67  mov     r11, [rsp+2C8h+var_290]
0x180009c6c  mov     r13, rbx
0x180009c6f  mov     r8, [r14+rdi*8]; unsigned __int16 *
0x180009c73  mov     rdx, r13; unsigned __int64
0x180009c76  mov     rcx, rsi; unsigned __int16 *
0x180009c79  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009c7e  mov     ebx, eax
0x180009c80  test    eax, eax
0x180009c82  js      short loc_180009CF9
0x180009c84  xor     eax, eax
0x180009c86  lea     rcx, [rsp+2C8h+var_278.CoreDriverGUID.Data2]; void *
0x180009c8b  xor     edx, edx; Val
0x180009c8d  mov     [rsi+r11*2+2], ax
0x180009c93  mov     r8d, 224h; Size
0x180009c99  mov     [rsp+2C8h+var_278.CoreDriverGUID.Data1], eax
0x180009c9d  call    memset_0
0x180009ca2  movsxd  rdx, [rsp+2C8h+var_298]
0x180009ca7  lea     rcx, PlatformEnv
0x180009cae  lea     rax, [rsp+2C8h+var_278]
0x180009cb3  mov     r9d, 1; cCorePrinterDrivers
0x180009cb9  mov     r8, rsi; pszzCoreDriverDependencies
0x180009cbc  mov     [rsp+2C8h+pCorePrinterDrivers], rax; pCorePrinterDrivers
0x180009cc1  mov     rdx, [rcx+rdx*8]; pszEnvironment
0x180009cc5  mov     rcx, [rsp+2C8h+pszServer]; pszServer
0x180009cca  call    cs:__imp_GetCorePrinterDriversW
0x180009cd0  mov     ebx, eax
0x180009cd2  test    eax, eax
0x180009cd4  js      short loc_180009CEF
0x180009cd6  mov     rcx, [r14+rdi*8]; pv
0x180009cda  call    cs:__imp_CoTaskMemFree
0x180009ce0  mov     qword ptr [r14+rdi*8], 0
0x180009ce8  inc     edi
0x180009cea  jmp     loc_180009BF9
0x180009cef  cmp     ax, 490h
0x180009cf3  jnz     short loc_180009CF9
0x180009cf5  xor     ebx, ebx
0x180009cf7  jmp     short loc_180009CE8
0x180009cf9  inc     edi
0x180009cfb  test    ebx, ebx
0x180009cfd  jns     loc_180009BF9
0x180009d03  test    rsi, rsi
0x180009d06  jz      short loc_180009D11
0x180009d08  mov     rcx, rsi; hMem
0x180009d0b  call    cs:__imp_LocalFree
0x180009d11  test    ebx, ebx
0x180009d13  js      short loc_180009D31
0x180009d15  mov     rdx, r14; unsigned __int16 **
0x180009d18  mov     ecx, r12d; unsigned int
0x180009d1b  call    ?FoundAllCommonDrivers@@YAHKPEAPEAG@Z; FoundAllCommonDrivers(ulong,ushort * *)
0x180009d20  mov     [r15], eax
0x180009d23  jmp     short loc_180009D31
0x180009d25  mov     ebx, 8007000Eh
0x180009d2a  jmp     short loc_180009D31
0x180009d2c  mov     ebx, 80070057h
0x180009d31  mov     eax, ebx
0x180009d33  mov     rcx, [rsp+2C8h+var_48]
0x180009d3b  xor     rcx, rsp; StackCookie
0x180009d3e  call    __security_check_cookie
0x180009d43  mov     rbx, [rsp+2C8h+arg_10]
0x180009d4b  add     rsp, 290h
0x180009d52  pop     r15
0x180009d54  pop     r14
0x180009d56  pop     r13
0x180009d58  pop     r12
0x180009d5a  pop     rdi
0x180009d5b  pop     rsi
0x180009d5c  pop     rbp
0x180009d5d  retn
```
