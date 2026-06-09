# BluetoothConnection::GetBTConnectionProperties(tagBTPAN_CONNECTION_PROPERTIES * *)

- ea: `0x180027c40`
- end: `0x180027eb0`
- name: `?GetBTConnectionProperties@BluetoothConnection@@UEAAJPEAPEAUtagBTPAN_CONNECTION_PROPERTIES@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(BluetoothConnection *__hidden this, struct tagBTPAN_CONNECTION_PROPERTIES **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180002320`
- `0x180004c00`
- `0x18000538c`
- `0x180027c40`
- `0x18002926c`
- `0x18003060c`
- `0x180036010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180027d72`
- `KERNEL32!FreeLibrary` at `0x180027e7b`
- `KERNEL32!FreeLibrary` at `0x180027d72`
- `KERNEL32!FreeLibrary` at `0x180027e7b`
- `KERNEL32!LoadLibraryExW` at `0x180027d09`
- `KERNEL32!LoadLibraryExW` at `0x180027d09`
- `KERNEL32!GetProcAddress` at `0x180027d64`
- `KERNEL32!GetProcAddress` at `0x180027d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027dbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027df3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027dbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027df3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027e59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027e59`

## string_xrefs

- `0x180027cfe`: `BluetoothApis.dll`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::GetBTConnectionProperties(BluetoothConnection *this, LPVOID *a2)
{
  unsigned int IsConnectedToRemote; // ebx
  HMODULE Library; // rax
  HMODULE v6; // rsi
  unsigned int Win32Error; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  FARPROC ProcAddress; // rax
  int v12; // eax
  _OWORD *v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  _DWORD *v16; // rcx
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int8 v18[4]; // [rsp+24h] [rbp-DCh] BYREF
  __int16 v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+38h] [rbp-C8h]
  __int16 v22; // [rsp+3Ch] [rbp-C4h]
  int v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+44h] [rbp-BCh]
  int v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 v27[248]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(&v20, 0, 0x230u);
  v17 = 0;
  if ( *((_DWORD *)this + 18) )
  {
    if ( !a2 )
      return (unsigned int)-2147467261;
    *a2 = 0;
    IsConnectedToRemote = BluetoothConnection::HrIsConnectedToRemote(
                            (BluetoothConnection *)((char *)this - 32),
                            &v17,
                            v18);
    if ( IsConnectedToRemote )
      return IsConnectedToRemote;
    if ( !v17 )
      return 1;
    memset_0(&v20, 0, 0x230u);
    v21 = *(_DWORD *)v18;
    v22 = v19;
    v20 = 560;
    Library = LoadLibraryExW(L"BluetoothApis.dll", 0, 0);
    v6 = Library;
    if ( !Library )
    {
      Win32Error = HrFromLastWin32Error();
      if ( (Win32Error & 0x80000000) == 0 )
        return Win32Error;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return Win32Error;
      v9 = 56;
LABEL_12:
      WPP_SF_d(v8[2], v9, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, Win32Error);
      return Win32Error;
    }
    ProcAddress = GetProcAddress(Library, "BluetoothGetDeviceInfo");
    if ( !ProcAddress )
    {
      FreeLibrary(v6);
      Win32Error = HrFromLastWin32Error();
      if ( (Win32Error & 0x80000000) == 0 )
        return Win32Error;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return Win32Error;
      v9 = 57;
      goto LABEL_12;
    }
    v12 = ((__int64 (__fastcall *)(_QWORD, int *))ProcAddress)(0, &v20);
    if ( v12 )
    {
      if ( v12 > 0 )
        IsConnectedToRemote = (unsigned __int16)v12 | 0x80070000;
      else
        IsConnectedToRemote = v12;
      goto LABEL_30;
    }
    v13 = CoTaskMemAlloc(0x20u);
    *a2 = v13;
    if ( v13 )
    {
      *v13 = 0;
      v13[1] = 0;
      v14 = -1;
      do
        ++v14;
      while ( v27[v14] );
      v15 = v14 + 1;
      *((_QWORD *)*a2 + 3) = CoTaskMemAlloc(2 * (v14 + 1));
      if ( *((_QWORD *)*a2 + 3) )
      {
        StringCchCopyW(*((unsigned __int16 **)*a2 + 3), v15, v27);
        *(_DWORD *)*a2 = v23;
        *((_DWORD *)*a2 + 1) = v24;
        *((_DWORD *)*a2 + 2) = v25;
        *((_DWORD *)*a2 + 3) = v26;
        v16 = *a2;
        v16[4] = v21;
        *((_WORD *)v16 + 10) = v22;
LABEL_30:
        FreeLibrary(v6);
        return IsConnectedToRemote;
      }
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
    IsConnectedToRemote = -2147024882;
    goto LABEL_30;
  }
  return (unsigned int)-2147418113;
}

```

## disassembly

```asm
0x180027c40  mov     [rsp-8+arg_10], rbx
0x180027c45  push    rbp
0x180027c46  push    rsi
0x180027c47  push    rdi
0x180027c48  push    r14
0x180027c4a  push    r15
0x180027c4c  lea     rbp, [rsp-170h]
0x180027c54  sub     rsp, 270h
0x180027c5b  mov     rax, cs:__security_cookie
0x180027c62  xor     rax, rsp
0x180027c65  mov     [rbp+190h+var_30], rax
0x180027c6c  mov     rdi, rdx
0x180027c6f  mov     rbx, rcx
0x180027c72  mov     esi, 230h
0x180027c77  lea     rcx, [rsp+290h+var_260]; void *
0x180027c7c  mov     r8d, esi; Size
0x180027c7f  xor     edx, edx; Val
0x180027c81  call    memset_0
0x180027c86  xor     r15d, r15d
0x180027c89  lea     rcx, [rbx-20h]; this
0x180027c8d  mov     [rsp+290h+var_270], r15d
0x180027c92  cmp     [rcx+68h], r15d
0x180027c96  jnz     short loc_180027CA2
0x180027c98  mov     ebx, 8000FFFFh
0x180027c9d  jmp     loc_180027E88
0x180027ca2  test    rdi, rdi
0x180027ca5  jnz     short loc_180027CB1
0x180027ca7  mov     ebx, 80004003h
0x180027cac  jmp     loc_180027E88
0x180027cb1  lea     r8, [rsp+290h+var_26C]; unsigned __int8 *
0x180027cb6  mov     [rdi], r15
0x180027cb9  lea     rdx, [rsp+290h+var_270]; int *
0x180027cbe  call    ?HrIsConnectedToRemote@BluetoothConnection@@AEAAJPEAHQEAE@Z; BluetoothConnection::HrIsConnectedToRemote(int *,uchar * const)
0x180027cc3  mov     ebx, eax
0x180027cc5  test    eax, eax
0x180027cc7  jnz     loc_180027E88
0x180027ccd  cmp     [rsp+290h+var_270], r15d
0x180027cd2  jz      loc_180027E83
0x180027cd8  mov     r8, rsi; Size
0x180027cdb  lea     rcx, [rsp+290h+var_260]; void *
0x180027ce0  xor     edx, edx; Val
0x180027ce2  call    memset_0
0x180027ce7  mov     ecx, dword ptr [rsp+290h+var_26C]
0x180027ceb  xor     r8d, r8d; dwFlags
0x180027cee  mov     [rsp+290h+var_258], ecx
0x180027cf2  xor     edx, edx; hFile
0x180027cf4  movzx   ecx, [rsp+290h+var_268]
0x180027cf9  mov     [rsp+290h+var_254], cx
0x180027cfe  lea     rcx, aBluetoothapisD; "BluetoothApis.dll"
0x180027d05  mov     [rsp+290h+var_260], esi
0x180027d09  call    cs:__imp_LoadLibraryExW
0x180027d0f  mov     rsi, rax
0x180027d12  test    rax, rax
0x180027d15  jnz     short loc_180027D5A
0x180027d17  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180027d1c  mov     edi, eax
0x180027d1e  test    eax, eax
0x180027d20  jns     short loc_180027D53
0x180027d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d29  lea     rax, WPP_GLOBAL_Control
0x180027d30  cmp     rcx, rax
0x180027d33  jz      short loc_180027D53
0x180027d35  lea     ebx, [rsi+1]
0x180027d38  test    [rcx+1Ch], bl
0x180027d3b  jz      short loc_180027D53
0x180027d3d  lea     edx, [rsi+38h]
0x180027d40  mov     rcx, [rcx+10h]
0x180027d44  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180027d4b  mov     r9d, edi
0x180027d4e  call    WPP_SF_d
0x180027d53  mov     eax, edi
0x180027d55  jmp     loc_180027E8A
0x180027d5a  lea     rdx, aBluetoothgetde; "BluetoothGetDeviceInfo"
0x180027d61  mov     rcx, rsi; hModule
0x180027d64  call    cs:__imp_GetProcAddress
0x180027d6a  test    rax, rax
0x180027d6d  jnz     short loc_180027DA5
0x180027d6f  mov     rcx, rsi; hLibModule
0x180027d72  call    cs:__imp_FreeLibrary
0x180027d78  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180027d7d  mov     edi, eax
0x180027d7f  test    eax, eax
0x180027d81  jns     short loc_180027D53
0x180027d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d8a  lea     rax, WPP_GLOBAL_Control
0x180027d91  cmp     rcx, rax
0x180027d94  jz      short loc_180027D53
0x180027d96  mov     ebx, 1
0x180027d9b  test    [rcx+1Ch], bl
0x180027d9e  jz      short loc_180027D53
0x180027da0  lea     edx, [rbx+38h]
0x180027da3  jmp     short loc_180027D40
0x180027da5  lea     rdx, [rsp+290h+var_260]
0x180027daa  xor     ecx, ecx
0x180027dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027db1  test    eax, eax
0x180027db3  jnz     loc_180027E69
0x180027db9  lea     ecx, [rax+20h]; cb
0x180027dbc  call    cs:__imp_CoTaskMemAlloc
0x180027dc2  mov     [rdi], rax
0x180027dc5  test    rax, rax
0x180027dc8  jz      loc_180027E62
0x180027dce  xorps   xmm0, xmm0
0x180027dd1  lea     rcx, [rsp+290h+var_220]
0x180027dd6  movups  xmmword ptr [rax], xmm0
0x180027dd9  movups  xmmword ptr [rax+10h], xmm0
0x180027ddd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027de1  inc     rax
0x180027de4  cmp     [rcx+rax*2], r15w
0x180027de9  jnz     short loc_180027DE1
0x180027deb  lea     r14, [rax+1]
0x180027def  lea     rcx, [r14+r14]; cb
0x180027df3  call    cs:__imp_CoTaskMemAlloc
0x180027df9  mov     rcx, [rdi]
0x180027dfc  mov     [rcx+18h], rax
0x180027e00  mov     rcx, [rdi]; pv
0x180027e03  mov     rax, [rcx+18h]
0x180027e07  test    rax, rax
0x180027e0a  jz      short loc_180027E59
0x180027e0c  lea     r8, [rsp+290h+var_220]; unsigned __int16 *
0x180027e11  mov     rdx, r14; unsigned __int64
0x180027e14  mov     rcx, rax; unsigned __int16 *
0x180027e17  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027e1c  mov     eax, [rsp+290h+var_250]
0x180027e20  mov     r11, [rdi]
0x180027e23  mov     [r11], eax
0x180027e26  mov     rcx, [rdi]
0x180027e29  mov     eax, [rsp+290h+var_24C]
0x180027e2d  mov     [rcx+4], eax
0x180027e30  mov     rcx, [rdi]
0x180027e33  mov     eax, [rsp+290h+var_248]
0x180027e37  mov     [rcx+8], eax
0x180027e3a  mov     rcx, [rdi]
0x180027e3d  mov     eax, [rsp+290h+var_244]
0x180027e41  mov     [rcx+0Ch], eax
0x180027e44  mov     eax, [rsp+290h+var_258]
0x180027e48  mov     rcx, [rdi]
0x180027e4b  mov     [rcx+10h], eax
0x180027e4e  movzx   eax, [rsp+290h+var_254]
0x180027e53  mov     [rcx+14h], ax
0x180027e57  jmp     short loc_180027E78
0x180027e59  call    cs:__imp_CoTaskMemFree
0x180027e5f  mov     [rdi], r15
0x180027e62  mov     ebx, 8007000Eh
0x180027e67  jmp     short loc_180027E78
0x180027e69  jg      short loc_180027E6F
0x180027e6b  mov     ebx, eax
0x180027e6d  jmp     short loc_180027E78
0x180027e6f  movzx   ebx, ax
0x180027e72  or      ebx, 80070000h
0x180027e78  mov     rcx, rsi; hLibModule
0x180027e7b  call    cs:__imp_FreeLibrary
0x180027e81  jmp     short loc_180027E88
0x180027e83  mov     ebx, 1
0x180027e88  mov     eax, ebx
0x180027e8a  mov     rcx, [rbp+190h+var_30]
0x180027e91  xor     rcx, rsp; StackCookie
0x180027e94  call    __security_check_cookie
0x180027e99  mov     rbx, [rsp+290h+arg_10]
0x180027ea1  add     rsp, 270h
0x180027ea8  pop     r15
0x180027eaa  pop     r14
0x180027eac  pop     rdi
0x180027ead  pop     rsi
0x180027eae  pop     rbp
0x180027eaf  retn
```
