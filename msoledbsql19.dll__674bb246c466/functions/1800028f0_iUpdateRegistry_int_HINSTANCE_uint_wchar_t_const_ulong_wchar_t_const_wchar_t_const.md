# iUpdateRegistry(int,HINSTANCE__ *,uint,wchar_t const *,ulong,wchar_t const * *,wchar_t const * *)

- ea: `0x1800028f0`
- end: `0x180002bc4`
- name: `?iUpdateRegistry@@YAJHPEAUHINSTANCE__@@IPEB_WKPEAPEB_W2@Z`
- size: `724`
- prototype: `int(int, HINSTANCE, unsigned int, const wchar_t *, unsigned int, const wchar_t **, const wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180002d10`
- `0x180002d70`

## callees

- `0x1800028f0`
- `0x180003d20`
- `0x180003d80`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetShortPathNameW` at `0x1800029d9`
- `KERNEL32!GetShortPathNameW` at `0x1800029d9`
- `KERNEL32!GetModuleFileNameW` at `0x18000296e`
- `KERNEL32!GetModuleFileNameW` at `0x18000296e`
- `KERNEL32!GetModuleHandleW` at `0x1800029bd`
- `KERNEL32!GetModuleHandleW` at `0x1800029bd`
- `ole32!CoCreateInstance` at `0x1800029a8`
- `ole32!CoCreateInstance` at `0x1800029a8`

## string_xrefs

- `0x180002b65`: `REGISTRY`

## pseudocode

```c
HRESULT __fastcall iUpdateRegistry(
        int a1,
        HINSTANCE a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        const wchar_t **a6,
        const wchar_t **a7)
{
  const wchar_t **v8; // rdi
  HRESULT result; // eax
  unsigned int v12; // ebx
  DWORD ShortPathNameW; // eax
  WCHAR *v14; // rsi
  __int64 v15; // rax
  __int64 v16; // r8
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  __int64 v22; // rax
  WCHAR *v23; // rdx
  WCHAR *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // ebx
  __int64 v28; // rax
  unsigned int v29; // [rsp+30h] [rbp+0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp+8h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp+10h] BYREF
  WCHAR szShortPath[264]; // [rsp+250h] [rbp+220h] BYREF

  v8 = a6;
  v29 = a3;
  if ( a5 && (!a6 || !a7) )
    return -2147024809;
  v12 = 0;
  ppv = 0;
  if ( !GetModuleFileNameW(a2, Filename, 0x103u) )
    return -2147467259;
  Filename[259] = 0;
  result = CoCreateInstance(&CLSID_Registrar, 0, 1u, &IID_IRegistrar, &ppv);
  if ( result < 0 )
    goto LABEL_44;
  if ( a2 && a2 != GetModuleHandleW(0) )
    goto LABEL_16;
  ShortPathNameW = GetShortPathNameW(Filename, szShortPath, 0x104u);
  if ( ShortPathNameW == 260 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return -2147024882;
  }
  if ( !ShortPathNameW || (v14 = szShortPath, ShortPathNameW == 87) )
LABEL_16:
    v14 = Filename;
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  v16 = (int)v15;
  v17 = 4LL * (int)v15 + 2;
  v18 = v17 + 15;
  if ( v17 + 15 < v17 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
  v20 = alloca(v19);
  v21 = alloca(v19);
  v22 = 2 * v16 + 1;
  v23 = v14;
  v24 = (WCHAR *)&v29;
  do
  {
    if ( !*v23 )
      goto LABEL_28;
    *v24 = *v23;
    --v22;
    ++v24;
    if ( *v23 == 39 )
    {
      if ( !v22 )
        goto LABEL_43;
      *v24++ = 39;
      --v22;
    }
    ++v23;
  }
  while ( v22 );
  if ( *v23 )
  {
LABEL_43:
    result = -2147024774;
    goto LABEL_44;
  }
LABEL_28:
  if ( !v22 )
    goto LABEL_43;
  *v24 = 0;
  result = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, unsigned int *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             L"Module",
             &v29);
  if ( result < 0 )
    goto LABEL_44;
  if ( a5 )
  {
    while ( 1 )
    {
      result = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 *v8,
                 *(const wchar_t **)((char *)v8 + (char *)a7 - (char *)a6));
      if ( result < 0 )
        break;
      ++v12;
      ++v8;
      if ( v12 >= a5 )
        goto LABEL_33;
    }
LABEL_44:
    _mm_lfence();
    return result;
  }
LABEL_33:
  if ( a4 )
  {
    v25 = *(_QWORD *)ppv;
    if ( a1 )
      v26 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(v25 + 72))(ppv, a4);
    else
      v26 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(v25 + 80))(ppv, a4);
  }
  else
  {
    _mm_lfence();
    _mm_lfence();
    v28 = *(_QWORD *)ppv;
    if ( a1 )
      v26 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, _QWORD, const wchar_t *))(v28 + 88))(ppv, v14, v29, L"REGISTRY");
    else
      v26 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, _QWORD, const wchar_t *))(v28 + 96))(ppv, v14, v29, L"REGISTRY");
  }
  v27 = v26;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v27;
}

```

## disassembly

```asm
0x1800028f0  push    rbp
0x1800028f2  push    rsi
0x1800028f3  push    rdi
0x1800028f4  push    r12
0x1800028f6  push    r13
0x1800028f8  push    r14
0x1800028fa  push    r15
0x1800028fc  sub     rsp, 470h
0x180002903  lea     rbp, [rsp+30h]
0x180002908  mov     [rbp+470h+arg_0], rbx
0x18000290f  mov     rax, cs:__security_cookie
0x180002916  xor     rax, rbp
0x180002919  mov     [rbp+470h+var_40], rax
0x180002920  mov     r14d, [rbp+470h+arg_20]
0x180002927  mov     r12, r9
0x18000292a  mov     rdi, [rbp+470h+arg_28]
0x180002931  mov     rsi, rdx
0x180002934  mov     r15, [rbp+470h+arg_30]
0x18000293b  mov     r13d, ecx
0x18000293e  mov     [rbp+470h+var_470], r8d
0x180002942  test    r14d, r14d
0x180002945  jz      short loc_18000295B
0x180002947  test    rdi, rdi
0x18000294a  jz      short loc_180002951
0x18000294c  test    r15, r15
0x18000294f  jnz     short loc_18000295B
0x180002951  mov     eax, 80070057h
0x180002956  jmp     loc_180002B9B
0x18000295b  xor     ebx, ebx
0x18000295d  lea     rdx, [rbp+470h+Filename]; lpFilename
0x180002961  mov     r8d, 103h; nSize
0x180002967  mov     [rbp+470h+var_468], rbx
0x18000296b  mov     rcx, rsi; hModule
0x18000296e  call    cs:__imp_GetModuleFileNameW
0x180002974  test    eax, eax
0x180002976  jnz     short loc_180002982
0x180002978  mov     eax, 80004005h
0x18000297d  jmp     loc_180002B9B
0x180002982  lea     rax, [rbp+470h+var_468]
0x180002986  mov     [rbp+470h+var_25A], bx
0x18000298d  lea     r9, IID_IRegistrar; riid
0x180002994  mov     [rsp+4A0h+ppv], rax; ppv
0x180002999  xor     edx, edx; pUnkOuter
0x18000299b  lea     rcx, CLSID_Registrar; rclsid
0x1800029a2  mov     r8d, 1; dwClsContext
0x1800029a8  call    cs:__imp_CoCreateInstance
0x1800029ae  test    eax, eax
0x1800029b0  js      loc_180002B98
0x1800029b6  test    rsi, rsi
0x1800029b9  jz      short loc_1800029C8
0x1800029bb  xor     ecx, ecx; lpModuleName
0x1800029bd  call    cs:__imp_GetModuleHandleW
0x1800029c3  cmp     rsi, rax
0x1800029c6  jnz     short loc_180002A16
0x1800029c8  mov     r8d, 104h; cchBuffer
0x1800029ce  lea     rdx, [rbp+470h+szShortPath]; lpszShortPath
0x1800029d5  lea     rcx, [rbp+470h+Filename]; lpszLongPath
0x1800029d9  call    cs:__imp_GetShortPathNameW
0x1800029df  cmp     eax, 104h
0x1800029e4  jnz     short loc_180002A06
0x1800029e6  mov     rcx, [rbp+470h+var_468]
0x1800029ea  test    rcx, rcx
0x1800029ed  jz      short loc_1800029FC
0x1800029ef  mov     rax, [rcx]
0x1800029f2  mov     rax, [rax+10h]
0x1800029f6  call    cs:__guard_dispatch_icall_fptr
0x1800029fc  mov     eax, 8007000Eh
0x180002a01  jmp     loc_180002B9B
0x180002a06  test    eax, eax
0x180002a08  jz      short loc_180002A16
0x180002a0a  lea     rsi, [rbp+470h+szShortPath]
0x180002a11  cmp     eax, 57h ; 'W'
0x180002a14  jnz     short loc_180002A1A
0x180002a16  lea     rsi, [rbp+470h+Filename]
0x180002a1a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002a21  inc     rax
0x180002a24  cmp     [rsi+rax*2], bx
0x180002a28  jnz     short loc_180002A21
0x180002a2a  movsxd  r8, eax
0x180002a2d  lea     rax, ds:2[r8*4]
0x180002a35  lea     rcx, [rax+0Fh]
0x180002a39  cmp     rcx, rax
0x180002a3c  ja      short loc_180002A48
0x180002a3e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180002a48  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180002a4c  mov     rax, rcx
0x180002a4f  call    _alloca_probe
0x180002a54  sub     rsp, rcx
0x180002a57  lea     rax, ds:1[r8*2]
0x180002a5f  mov     rdx, rsi
0x180002a62  lea     r9, [rsp+4A0h+var_470]
0x180002a67  mov     rcx, r9
0x180002a6a  nop     word ptr [rax+rax+00h]
0x180002a70  movzx   r8d, word ptr [rdx]
0x180002a74  test    r8w, r8w
0x180002a78  jz      short loc_180002AB2
0x180002a7a  mov     [rcx], r8w
0x180002a7e  dec     rax
0x180002a81  add     rcx, 2
0x180002a85  cmp     word ptr [rdx], 27h ; '''
0x180002a89  jnz     short loc_180002AA0
0x180002a8b  test    rax, rax
0x180002a8e  jz      loc_180002B93
0x180002a94  mov     word ptr [rcx], 27h ; '''
0x180002a99  add     rcx, 2
0x180002a9d  dec     rax
0x180002aa0  add     rdx, 2
0x180002aa4  test    rax, rax
0x180002aa7  jnz     short loc_180002A70
0x180002aa9  cmp     [rdx], bx
0x180002aac  jnz     loc_180002B93
0x180002ab2  test    rax, rax
0x180002ab5  jz      loc_180002B93
0x180002abb  mov     [rcx], bx
0x180002abe  lea     rdx, aModule; "Module"
0x180002ac5  mov     rcx, [rbp+470h+var_468]
0x180002ac9  mov     r8, r9
0x180002acc  mov     rax, [rcx]
0x180002acf  mov     rax, [rax+18h]
0x180002ad3  call    cs:__guard_dispatch_icall_fptr
0x180002ad9  test    eax, eax
0x180002adb  js      loc_180002B98
0x180002ae1  test    r14d, r14d
0x180002ae4  jz      short loc_180002B1B
0x180002ae6  sub     r15, rdi
0x180002ae9  nop     dword ptr [rax+00000000h]
0x180002af0  mov     rcx, [rbp+470h+var_468]
0x180002af4  mov     r8, [r15+rdi]
0x180002af8  mov     rdx, [rdi]
0x180002afb  mov     rax, [rcx]
0x180002afe  mov     rax, [rax+18h]
0x180002b02  call    cs:__guard_dispatch_icall_fptr
0x180002b08  test    eax, eax
0x180002b0a  js      loc_180002B98
0x180002b10  inc     ebx
0x180002b12  add     rdi, 8
0x180002b16  cmp     ebx, r14d
0x180002b19  jb      short loc_180002AF0
0x180002b1b  test    r12, r12
0x180002b1e  jz      short loc_180002B5B
0x180002b20  mov     rcx, [rbp+470h+var_468]
0x180002b24  mov     rdx, r12
0x180002b27  mov     rax, [rcx]
0x180002b2a  test    r13d, r13d
0x180002b2d  jz      short loc_180002B35
0x180002b2f  mov     rax, [rax+48h]
0x180002b33  jmp     short loc_180002B39
0x180002b35  mov     rax, [rax+50h]
0x180002b39  call    cs:__guard_dispatch_icall_fptr
0x180002b3f  mov     rcx, [rbp+470h+var_468]
0x180002b43  mov     ebx, eax
0x180002b45  test    rcx, rcx
0x180002b48  jz      short loc_180002B57
0x180002b4a  mov     rax, [rcx]
0x180002b4d  mov     rax, [rax+10h]
0x180002b51  call    cs:__guard_dispatch_icall_fptr
0x180002b57  mov     eax, ebx
0x180002b59  jmp     short loc_180002B9B
0x180002b5b  lfence
0x180002b5e  lfence
0x180002b61  mov     rcx, [rbp+470h+var_468]
0x180002b65  lea     r9, aRegistry; "REGISTRY"
0x180002b6c  mov     r8d, [rbp+470h+var_470]
0x180002b70  mov     rdx, rsi
0x180002b73  mov     rax, [rcx]
0x180002b76  test    r13d, r13d
0x180002b79  jz      short loc_180002B87
0x180002b7b  mov     rax, [rax+58h]
0x180002b7f  call    cs:__guard_dispatch_icall_fptr
0x180002b85  jmp     short loc_180002B3F
0x180002b87  mov     rax, [rax+60h]
0x180002b8b  call    cs:__guard_dispatch_icall_fptr
0x180002b91  jmp     short loc_180002B3F
0x180002b93  mov     eax, 8007007Ah
0x180002b98  lfence
0x180002b9b  mov     rcx, [rbp+470h+var_40]
0x180002ba2  xor     rcx, rbp; StackCookie
0x180002ba5  call    __security_check_cookie
0x180002baa  mov     rbx, [rbp+470h+arg_0]
0x180002bb1  lea     rsp, [rbp+440h]
0x180002bb8  pop     r15
0x180002bba  pop     r14
0x180002bbc  pop     r13
0x180002bbe  pop     r12
0x180002bc0  pop     rdi
0x180002bc1  pop     rsi
0x180002bc2  pop     rbp
0x180002bc3  retn
```
