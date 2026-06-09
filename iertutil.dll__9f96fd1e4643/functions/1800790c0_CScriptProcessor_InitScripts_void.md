# CScriptProcessor::InitScripts(void)

- ea: `0x1800790c0`
- end: `0x180079350`
- name: `?InitScripts@CScriptProcessor@@IEAAJXZ`
- size: `656`
- prototype: `__int64 __fastcall(LPCWSTR lpLocaleName)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078f00`

## callees

- `0x180078fec`
- `0x1800790c0`
- `0x180083bc2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800791c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800791c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007922b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007922b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007921c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007921c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180079146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180079146`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007917d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007917d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800791a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800791a4`
- `ntdll!NtClose` at `0x180079330`
- `ntdll!NtClose` at `0x180079330`
- `KERNELBASE!OpenGlobalizationUserSettingsKey` at `0x180079106`
- `KERNELBASE!OpenGlobalizationUserSettingsKey` at `0x180079106`
- `KERNELBASE!GetUserDefaultLocaleName` at `0x1800791b4`
- `KERNELBASE!GetUserDefaultLocaleName` at `0x1800791b4`

## pseudocode

```c
__int64 __fastcall CScriptProcessor::InitScripts(WCHAR *lpLocaleName)
{
  unsigned int v2; // r14d
  int v3; // eax
  int v4; // eax
  __int64 v5; // rcx
  signed int v6; // edi
  int UserDefaultLocaleName; // eax
  signed int LastError; // eax
  __int64 v9; // r14
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  void *v12; // rax
  WCHAR *v13; // rbx
  WCHAR *i; // r8
  int v15; // r15d
  WCHAR v16; // cx
  WCHAR *v17; // rdx
  __int64 LocaleScripts; // rax
  __int128 v20; // [rsp+48h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+A8h] [rbp+48h] BYREF
  HKEY hkey; // [rsp+B0h] [rbp+50h] BYREF

  pcbData = 4096;
  hkey = 0;
  v2 = 2048;
  v20 = 0;
  v3 = OpenGlobalizationUserSettingsKey(131097, 0, (char *)&v20 + 8);
  if ( v3 )
  {
    v4 = v3 | 0x10000000;
    v5 = 0;
    if ( v4 < 0 )
      goto LABEL_6;
  }
  else
  {
    v4 = 0;
  }
  v5 = *((_QWORD *)&v20 + 1);
LABEL_6:
  if ( v4 )
    v5 = -2147483647;
  if ( RegOpenKeyExA((HKEY)v5, "Software\\Microsoft\\Internet Explorer\\International", 0, 0x20019u, &hkey) )
    goto LABEL_14;
  v6 = -2147467259;
  if ( !RegGetValueW(hkey, 0, L"AcceptLanguage", 2u, 0, lpLocaleName, &pcbData) && pcbData && *lpLocaleName )
  {
    v6 = 0;
    v2 = (pcbData >> 1) - 1;
  }
  RegCloseKey(hkey);
  if ( v6 < 0 )
  {
LABEL_14:
    UserDefaultLocaleName = GetUserDefaultLocaleName(lpLocaleName, v2);
    if ( UserDefaultLocaleName )
    {
      v2 = UserDefaultLocaleName - 1;
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_47;
    }
  }
  if ( !v2 || !*lpLocaleName )
  {
    v6 = -2147467259;
    goto LABEL_47;
  }
  v9 = v2 >> 1;
  *((_DWORD *)lpLocaleName + 1026) = 0;
  v10 = 8LL * (unsigned int)v9;
  if ( !is_mul_ok((unsigned int)v9, 8u) )
    v10 = -1;
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 8u, v10);
  *((_QWORD *)lpLocaleName + 512) = v12;
  if ( !v12 )
  {
    v6 = -2147024882;
LABEL_47:
    *lpLocaleName = 0;
    goto LABEL_48;
  }
  memset_0(v12, 0, 8 * v9);
  v13 = lpLocaleName;
  for ( i = lpLocaleName; *v13; i = v13 )
  {
    if ( *((_DWORD *)lpLocaleName + 1026) >= (unsigned int)v9 )
      break;
    while ( *v13 != 44 && *v13 )
      ++v13;
    if ( *v13 )
    {
      v15 = 0;
      *v13 = 0;
    }
    else
    {
      v15 = 1;
    }
    v16 = *i;
    v17 = i;
    while ( v16 != 59 && v16 )
      v16 = *++v17;
    if ( *v17 )
      *v17 = 0;
    LocaleScripts = GetLocaleScripts(i);
    if ( LocaleScripts )
      *(_QWORD *)(*((_QWORD *)lpLocaleName + 512) + 8LL * (unsigned int)(*((_DWORD *)lpLocaleName + 1026))++) = LocaleScripts;
    if ( v15 != 1 )
      ++v13;
  }
LABEL_48:
  if ( *((_QWORD *)&v20 + 1) && *((_QWORD *)&v20 + 1) != -2147483647 )
    NtClose(*((HANDLE *)&v20 + 1));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800790c0  mov     [rsp-38h+arg_0], rbx
0x1800790c5  push    rbp
0x1800790c6  push    rsi
0x1800790c7  push    rdi
0x1800790c8  push    r12
0x1800790ca  push    r13
0x1800790cc  push    r14
0x1800790ce  push    r15
0x1800790d0  mov     rbp, rsp
0x1800790d3  sub     rsp, 60h
0x1800790d7  mov     ebx, 20019h
0x1800790dc  mov     [rbp+arg_8], 1000h
0x1800790e3  mov     rsi, rcx
0x1800790e6  mov     [rbp+var_20], ebx
0x1800790e9  xorps   xmm0, xmm0
0x1800790ec  lea     r8, [rbp+Handle]
0x1800790f0  xor     r13d, r13d
0x1800790f3  mov     ecx, ebx
0x1800790f5  xor     edx, edx
0x1800790f7  mov     [rbp+hkey], r13
0x1800790fb  mov     r14d, 800h
0x180079101  movdqu  xmmword ptr [rbp-18h], xmm0
0x180079106  call    cs:__imp_OpenGlobalizationUserSettingsKey
0x18007910c  test    eax, eax
0x18007910e  jz      short loc_18007911C
0x180079110  or      eax, 10000000h
0x180079115  mov     ecx, r13d
0x180079118  jl      short loc_180079123
0x18007911a  jmp     short loc_18007911F
0x18007911c  mov     eax, r13d
0x18007911f  mov     rcx, [rbp+Handle]
0x180079123  test    eax, eax
0x180079125  mov     rdx, 0FFFFFFFF80000001h
0x18007912c  lea     rax, [rbp+hkey]
0x180079130  mov     r9d, ebx; samDesired
0x180079133  cmovnz  rcx, rdx; hKey
0x180079137  mov     [rsp+60h+phkResult], rax; phkResult
0x18007913c  xor     r8d, r8d; ulOptions
0x18007913f  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Internet Explorer"...
0x180079146  call    cs:__imp_RegOpenKeyExA
0x18007914c  mov     ebx, 80004005h
0x180079151  test    eax, eax
0x180079153  jnz     short loc_1800791AE
0x180079155  mov     rcx, [rbp+hkey]; hkey
0x180079159  lea     rax, [rbp+arg_8]
0x18007915d  mov     [rsp+60h+pcbData], rax; pcbData
0x180079162  lea     r8, aAcceptlanguage; "AcceptLanguage"
0x180079169  mov     [rsp+60h+pvData], rsi; pvData
0x18007916e  mov     r9d, 2; dwFlags
0x180079174  xor     edx, edx; lpSubKey
0x180079176  mov     [rsp+60h+phkResult], r13; pdwType
0x18007917b  mov     edi, ebx
0x18007917d  call    cs:__imp_RegGetValueW
0x180079183  test    eax, eax
0x180079185  jnz     short loc_1800791A0
0x180079187  mov     ecx, [rbp+arg_8]
0x18007918a  test    ecx, ecx
0x18007918c  jz      short loc_1800791A0
0x18007918e  cmp     r13w, [rsi]
0x180079192  jz      short loc_1800791A0
0x180079194  mov     r14d, ecx
0x180079197  mov     edi, r13d
0x18007919a  shr     r14d, 1
0x18007919d  dec     r14d
0x1800791a0  mov     rcx, [rbp+hkey]; hKey
0x1800791a4  call    cs:__imp_RegCloseKey
0x1800791aa  test    edi, edi
0x1800791ac  jns     short loc_1800791E4
0x1800791ae  mov     edx, r14d; cchLocaleName
0x1800791b1  mov     rcx, rsi; lpLocaleName
0x1800791b4  call    cs:__imp_GetUserDefaultLocaleName
0x1800791ba  test    eax, eax
0x1800791bc  jz      short loc_1800791C7
0x1800791be  lea     r14d, [rax-1]
0x1800791c2  mov     edi, r13d
0x1800791c5  jmp     short loc_1800791E4
0x1800791c7  call    cs:__imp_GetLastError
0x1800791cd  mov     edi, eax
0x1800791cf  test    eax, eax
0x1800791d1  jle     short loc_1800791DC
0x1800791d3  movzx   edi, ax
0x1800791d6  or      edi, 80070000h
0x1800791dc  test    edi, edi
0x1800791de  js      loc_18007931A
0x1800791e4  test    r14d, r14d
0x1800791e7  jz      loc_180079318
0x1800791ed  cmp     [rsi], r13w
0x1800791f1  jz      loc_180079318
0x1800791f7  shr     r14d, 1
0x1800791fa  mov     r12d, 8
0x180079200  mov     r15d, r14d
0x180079203  mov     eax, r12d
0x180079206  mul     r15
0x180079209  mov     [rsi+1008h], r13d
0x180079210  mov     rbx, rax
0x180079213  lea     rax, [r12-9]
0x180079218  cmovb   rbx, rax
0x18007921c  call    cs:__imp_GetProcessHeap
0x180079222  mov     r8, rbx; dwBytes
0x180079225  mov     edx, r12d; dwFlags
0x180079228  mov     rcx, rax; hHeap
0x18007922b  call    cs:__imp_HeapAlloc
0x180079231  mov     [rsi+1000h], rax
0x180079238  test    rax, rax
0x18007923b  jnz     short loc_180079247
0x18007923d  mov     edi, 8007000Eh
0x180079242  jmp     loc_18007931A
0x180079247  lea     r8, ds:0[r14*8]; Size
0x18007924f  xor     edx, edx; Val
0x180079251  mov     rcx, rax; void *
0x180079254  call    memset_0
0x180079259  mov     rbx, rsi
0x18007925c  mov     r8, rsi
0x18007925f  cmp     r13w, [rsi]
0x180079263  jz      loc_180079312
0x180079269  mov     r12d, 2Ch ; ','
0x18007926f  lea     r9d, [r12+0Fh]
0x180079274  cmp     [rsi+1008h], r14d
0x18007927b  jnb     loc_180079312
0x180079281  jmp     short loc_18007928D
0x180079283  cmp     r13w, cx
0x180079287  jz      short loc_180079296
0x180079289  add     rbx, 2
0x18007928d  movzx   ecx, word ptr [rbx]
0x180079290  cmp     r12w, cx
0x180079294  jnz     short loc_180079283
0x180079296  cmp     r13w, [rbx]
0x18007929a  jz      short loc_1800792A5
0x18007929c  mov     r15d, r13d
0x18007929f  mov     [rbx], r13w
0x1800792a3  jmp     short loc_1800792AB
0x1800792a5  mov     r15d, 1
0x1800792ab  movzx   ecx, word ptr [r8]
0x1800792af  mov     rdx, r8
0x1800792b2  jmp     short loc_1800792C1
0x1800792b4  cmp     r13w, cx
0x1800792b8  jz      short loc_1800792C7
0x1800792ba  add     rdx, 2
0x1800792be  movzx   ecx, word ptr [rdx]
0x1800792c1  cmp     r9w, cx
0x1800792c5  jnz     short loc_1800792B4
0x1800792c7  cmp     r13w, [rdx]
0x1800792cb  jz      short loc_1800792D1
0x1800792cd  mov     [rdx], r13w
0x1800792d1  mov     rcx, r8; lpLocaleName
0x1800792d4  call    GetLocaleScripts
0x1800792d9  test    rax, rax
0x1800792dc  jz      short loc_1800792F5
0x1800792de  mov     edx, [rsi+1008h]
0x1800792e4  mov     rcx, [rsi+1000h]
0x1800792eb  mov     [rcx+rdx*8], rax
0x1800792ef  inc     dword ptr [rsi+1008h]
0x1800792f5  cmp     r15d, 1
0x1800792f9  jz      short loc_1800792FF
0x1800792fb  add     rbx, 2
0x1800792ff  mov     r8, rbx
0x180079302  mov     r9d, 3Bh ; ';'
0x180079308  cmp     r13w, [rbx]
0x18007930c  jnz     loc_180079274
0x180079312  test    edi, edi
0x180079314  jns     short loc_18007931E
0x180079316  jmp     short loc_18007931A
0x180079318  mov     edi, ebx
0x18007931a  mov     [rsi], r13w
0x18007931e  mov     rcx, [rbp+Handle]; Handle
0x180079322  test    rcx, rcx
0x180079325  jz      short loc_180079336
0x180079327  cmp     rcx, 0FFFFFFFF80000001h
0x18007932e  jz      short loc_180079336
0x180079330  call    cs:__imp_NtClose
0x180079336  mov     rbx, [rsp+60h+arg_0]
0x18007933e  mov     eax, edi
0x180079340  add     rsp, 60h
0x180079344  pop     r15
0x180079346  pop     r14
0x180079348  pop     r13
0x18007934a  pop     r12
0x18007934c  pop     rdi
0x18007934d  pop     rsi
0x18007934e  pop     rbp
0x18007934f  retn
```
