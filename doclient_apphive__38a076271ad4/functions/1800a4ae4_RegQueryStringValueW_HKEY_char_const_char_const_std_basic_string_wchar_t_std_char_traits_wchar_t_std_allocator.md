# RegQueryStringValueW(HKEY__ *,char const *,char const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800a4ae4`
- end: `0x1800a4cad`
- name: `?RegQueryStringValueW@@YAJPEAUHKEY__@@PEBD1AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800a11a0`

## callees

- `0x180008b1c`
- `0x18000ef98`
- `0x18001dffc`
- `0x1800a4ae4`
- `0x1800a5978`
- `0x1800a979c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4b47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4c8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4b47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4c8b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a4bd0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a4c30`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a4bd0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a4c30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4b26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4b26`

## pseudocode

```c
__int64 __fastcall RegQueryStringValueW(HKEY a1, __int64 a2, __int64 a3, void **a4)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  const WCHAR *v9; // rdi
  LSTATUS ValueW; // eax
  void *pvData; // rax
  unsigned int v12; // eax
  _WORD *v13; // rax
  __int64 v14; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-49h]
  _BYTE v16[32]; // [rsp+40h] [rbp-29h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-1h] BYREF
  __int128 v19; // [rsp+70h] [rbp+7h] BYREF
  __m128i si128; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  hKey = 0;
  v6 = RegOpenKeyExW(a1, 0, 0, 0x20019u, &hKey);
  if ( v6 )
  {
    v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 <= 0 )
      v7 = v6;
    goto LABEL_4;
  }
  v19 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  v9 = 0;
  if ( a3 )
  {
    UTF8toWstr(v16, a3, 0);
    std::wstring::operator=(&v19, v16);
    std::wstring::~wstring(v16);
    v9 = (const WCHAR *)&v19;
    if ( si128.m128i_i64[1] > 7uLL )
      v9 = (const WCHAR *)v19;
  }
  pcbData = 0;
  ValueW = RegGetValueW(hKey, 0, v9, 2u, 0, 0, &pcbData);
  if ( ValueW )
  {
    v7 = (unsigned __int16)ValueW | 0x80070000;
    if ( ValueW <= 0 )
      v7 = ValueW;
    goto LABEL_13;
  }
  std::wstring::resize(a4);
  pvData = a4;
  if ( (unsigned __int64)a4[3] > 7 )
    pvData = *a4;
  v12 = RegGetValueW(hKey, 0, v9, 2u, 0, pvData, &pcbData);
  if ( v12 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x4B,
           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\RegUtil.cpp",
           (const char *)v12,
           phkResult);
LABEL_13:
    std::wstring::~wstring(&v19);
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  v13 = a4;
  if ( (unsigned __int64)a4[3] > 7 )
    v13 = *a4;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  std::wstring::resize(a4);
  std::wstring::~wstring(&v19);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800a4ae4  push    rbp
0x1800a4ae6  push    rbx
0x1800a4ae7  push    rsi
0x1800a4ae8  push    rdi
0x1800a4ae9  push    r14
0x1800a4aeb  lea     rbp, [rsp-37h]
0x1800a4af0  sub     rsp, 0A0h
0x1800a4af7  mov     rax, cs:__security_cookie
0x1800a4afe  xor     rax, rsp
0x1800a4b01  mov     [rbp+57h+var_30], rax
0x1800a4b05  mov     rbx, r9
0x1800a4b08  mov     rsi, r8
0x1800a4b0b  xor     r14d, r14d
0x1800a4b0e  mov     [rbp+57h+hKey], r14
0x1800a4b12  lea     rax, [rbp+57h+hKey]
0x1800a4b16  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800a4b1b  mov     r9d, 20019h; samDesired
0x1800a4b21  xor     r8d, r8d; ulOptions
0x1800a4b24  xor     edx, edx; lpSubKey
0x1800a4b26  call    cs:__imp_RegOpenKeyExW
0x1800a4b2c  test    eax, eax
0x1800a4b2e  jz      short loc_1800A4B54
0x1800a4b30  movzx   ebx, ax
0x1800a4b33  or      ebx, 80070000h
0x1800a4b39  test    eax, eax
0x1800a4b3b  cmovle  ebx, eax
0x1800a4b3e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a4b42  test    rcx, rcx
0x1800a4b45  jz      short loc_1800A4B4D
0x1800a4b47  call    cs:__imp_RegCloseKey
0x1800a4b4d  mov     eax, ebx
0x1800a4b4f  jmp     loc_1800A4C93
0x1800a4b54  xorps   xmm0, xmm0
0x1800a4b57  movups  [rbp+57h+var_50], xmm0
0x1800a4b5b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800a4b63  movdqu  [rbp+57h+var_40], xmm1
0x1800a4b68  mov     word ptr [rbp+57h+var_50], r14w
0x1800a4b6d  mov     rdi, r14
0x1800a4b70  test    rsi, rsi
0x1800a4b73  jz      short loc_1800A4BA8
0x1800a4b75  xor     r8d, r8d
0x1800a4b78  mov     rdx, rsi
0x1800a4b7b  lea     rcx, [rbp+57h+var_80]
0x1800a4b7f  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800a4b84  lea     rdx, [rbp+57h+var_80]
0x1800a4b88  lea     rcx, [rbp+57h+var_50]
0x1800a4b8c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a4b91  lea     rcx, [rbp+57h+var_80]
0x1800a4b95  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a4b9a  lea     rdi, [rbp+57h+var_50]
0x1800a4b9e  cmp     qword ptr [rbp+57h+var_40+8], 7
0x1800a4ba3  cmova   rdi, qword ptr [rbp+57h+var_50]
0x1800a4ba8  mov     [rbp+57h+var_60], r14d
0x1800a4bac  lea     rax, [rbp+57h+var_60]
0x1800a4bb0  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800a4bb5  mov     [rsp+0C0h+pvData], r14; pvData
0x1800a4bba  mov     [rsp+0C0h+phkResult], r14; pdwType
0x1800a4bbf  mov     esi, 2
0x1800a4bc4  mov     r9d, esi; dwFlags
0x1800a4bc7  mov     r8, rdi; lpValue
0x1800a4bca  xor     edx, edx; lpSubKey
0x1800a4bcc  mov     rcx, [rbp+57h+hKey]; hkey
0x1800a4bd0  call    cs:__imp_RegGetValueW
0x1800a4bd6  test    eax, eax
0x1800a4bd8  jz      short loc_1800A4BF6
0x1800a4bda  movzx   ebx, ax
0x1800a4bdd  or      ebx, 80070000h
0x1800a4be3  test    eax, eax
0x1800a4be5  cmovle  ebx, eax
0x1800a4be8  lea     rcx, [rbp+57h+var_50]
0x1800a4bec  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a4bf1  jmp     loc_1800A4B3E
0x1800a4bf6  mov     edx, [rbp+57h+var_60]
0x1800a4bf9  shr     rdx, 1
0x1800a4bfc  mov     rcx, rbx; Src
0x1800a4bff  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800a4c04  mov     rax, rbx
0x1800a4c07  cmp     qword ptr [rbx+18h], 7
0x1800a4c0c  jbe     short loc_1800A4C11
0x1800a4c0e  mov     rax, [rbx]
0x1800a4c11  lea     rcx, [rbp+57h+var_60]
0x1800a4c15  mov     [rsp+0C0h+pcbData], rcx; pcbData
0x1800a4c1a  mov     [rsp+0C0h+pvData], rax; pvData
0x1800a4c1f  mov     [rsp+0C0h+phkResult], r14; unsigned int
0x1800a4c24  mov     r9d, esi; dwFlags
0x1800a4c27  mov     r8, rdi; lpValue
0x1800a4c2a  xor     edx, edx; lpSubKey
0x1800a4c2c  mov     rcx, [rbp+57h+hKey]; hkey
0x1800a4c30  call    cs:__imp_RegGetValueW
0x1800a4c36  test    eax, eax
0x1800a4c38  jz      short loc_1800A4C56
0x1800a4c3a  mov     rcx, [rbp+5Fh]; this
0x1800a4c3e  mov     r9d, eax; char *
0x1800a4c41  lea     r8, aCW1SSrcDeliver_92; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a4c48  mov     edx, 4Bh ; 'K'; void *
0x1800a4c4d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a4c52  mov     ebx, eax
0x1800a4c54  jmp     short loc_1800A4BE8
0x1800a4c56  mov     rax, rbx
0x1800a4c59  cmp     qword ptr [rbx+18h], 7
0x1800a4c5e  jbe     short loc_1800A4C63
0x1800a4c60  mov     rax, [rbx]
0x1800a4c63  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a4c67  inc     rdx
0x1800a4c6a  cmp     [rax+rdx*2], r14w
0x1800a4c6f  jnz     short loc_1800A4C67
0x1800a4c71  mov     rcx, rbx; Src
0x1800a4c74  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800a4c79  lea     rcx, [rbp+57h+var_50]
0x1800a4c7d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a4c82  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a4c86  test    rcx, rcx
0x1800a4c89  jz      short loc_1800A4C91
0x1800a4c8b  call    cs:__imp_RegCloseKey
0x1800a4c91  xor     eax, eax
0x1800a4c93  mov     rcx, [rbp+57h+var_30]
0x1800a4c97  xor     rcx, rsp; StackCookie
0x1800a4c9a  call    __security_check_cookie
0x1800a4c9f  add     rsp, 0A0h
0x1800a4ca6  pop     r14
0x1800a4ca8  pop     rdi
0x1800a4ca9  pop     rsi
0x1800a4caa  pop     rbx
0x1800a4cab  pop     rbp
0x1800a4cac  retn
```
