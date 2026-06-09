# WriteLoginOpts

- ea: `0x1800106fc`
- end: `0x18001096a`
- name: `WriteLoginOpts`
- size: `622`
- prototype: `LSTATUS __fastcall(HKEY hKey, wchar_t *Source, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c738`
- `0x180010bec`

## callees

- `0x1800106fc`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180010786`
- `msvcrt!wcscat_s` at `0x180010786`
- `msvcrt!wcscpy_s` at `0x18001076a`
- `msvcrt!wcscpy_s` at `0x1800107e9`
- `msvcrt!wcscpy_s` at `0x18001076a`
- `msvcrt!wcscpy_s` at `0x1800107e9`
- `ADVAPI32!RegCreateKeyExW` at `0x1800107c8`
- `ADVAPI32!RegCreateKeyExW` at `0x1800107c8`
- `ADVAPI32!RegSetValueExW` at `0x1800108a0`
- `ADVAPI32!RegSetValueExW` at `0x1800108df`
- `ADVAPI32!RegSetValueExW` at `0x180010907`
- `ADVAPI32!RegSetValueExW` at `0x18001092f`
- `ADVAPI32!RegSetValueExW` at `0x1800108a0`
- `ADVAPI32!RegSetValueExW` at `0x1800108df`
- `ADVAPI32!RegSetValueExW` at `0x180010907`
- `ADVAPI32!RegSetValueExW` at `0x18001092f`
- `ADVAPI32!RegCloseKey` at `0x180010940`
- `ADVAPI32!RegCloseKey` at `0x180010940`

## pseudocode

```c
LSTATUS __fastcall WriteLoginOpts(HKEY hKey, wchar_t *Source, __int64 a3)
{
  LSTATUS result; // eax
  __int64 v7; // rbx
  int v8; // r8d
  int i; // r9d
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  unsigned __int16 v13; // cx
  __int64 v14; // rax
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[526]; // [rsp+62h] [rbp-9Eh] BYREF
  wchar_t Destination[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t v20[264]; // [rsp+480h] [rbp+380h] BYREF

  hKeya = 0;
  dwDisposition = 0;
  *(_WORD *)Data = 0;
  memset_0(v18, 0, 0x206u);
  Destination[259] = 0;
  wcscpy_s(Destination, 0x104u, Source);
  wcscat_s(Destination, 0x104u, L"\\Auth");
  result = RegCreateKeyExW(hKey, Destination, 0, 0, 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
  if ( !result )
  {
    wcscpy_s(v20, 0x104u, (const wchar_t *)(a3 + 16));
    v7 = -1;
    v8 = 259;
    for ( i = 0; ; ++i )
    {
      v10 = -1;
      do
        ++v10;
      while ( v20[v10] );
      v11 = 259;
      if ( (int)v10 < 259 )
        v11 = v10;
      if ( i >= v11 )
        break;
      v12 = i;
      v13 = v20[i] + 128;
      if ( v13 > 0xFFu )
        v13 = v20[i] - 127;
      *(_WORD *)&Data[2 * v12] = v13;
    }
    v14 = -1;
    if ( (int)v10 < 259 )
      v8 = v10;
    *(_WORD *)&Data[2 * v8] = 0;
    do
      ++v14;
    while ( *(_WORD *)&Data[2 * v14] );
    RegSetValueExW(hKeya, L"User", 0, 3u, Data, 2 * v14 + 2);
    do
      ++v7;
    while ( *(_WORD *)(a3 + 1064 + 2 * v7) );
    RegSetValueExW(hKeya, L"PCNFSDServer", 0, 1u, (const BYTE *)(a3 + 1064), 2 * v7 + 2);
    RegSetValueExW(hKeya, L"NISDomain", 0, 1u, 0, 0);
    RegSetValueExW(hKeya, L"NISServer", 0, 1u, 0, 0);
    return RegCloseKey(hKeya);
  }
  return result;
}

```

## disassembly

```asm
0x1800106fc  push    rbp
0x1800106fe  push    rbx
0x1800106ff  push    rsi
0x180010700  push    rdi
0x180010701  push    r14
0x180010703  lea     rbp, [rsp-5A0h]
0x18001070b  sub     rsp, 6A0h
0x180010712  mov     rax, cs:__security_cookie
0x180010719  xor     rax, rsp
0x18001071c  mov     [rbp+5C0h+var_30], rax
0x180010723  xor     r14d, r14d
0x180010726  mov     rsi, r8
0x180010729  mov     rbx, rdx
0x18001072c  mov     [rsp+6C0h+hKey], r14
0x180010731  mov     rdi, rcx
0x180010734  mov     [rsp+6C0h+dwDisposition], r14d
0x180010739  xor     edx, edx; Val
0x18001073b  mov     word ptr [rsp+6C0h+Data], r14w
0x180010741  mov     r8d, 206h; Size
0x180010747  lea     rcx, [rsp+6C0h+var_65E]; void *
0x18001074c  call    memset_0
0x180010751  mov     r8, rbx; Source
0x180010754  mov     [rbp+5C0h+var_24A], r14w
0x18001075c  mov     ebx, 104h
0x180010761  lea     rcx, [rbp+5C0h+Destination]; Destination
0x180010768  mov     edx, ebx; SizeInWords
0x18001076a  call    cs:__imp_wcscpy_s
0x180010771  nop     dword ptr [rax+rax+00h]
0x180010776  lea     r8, aAuth; "\\Auth"
0x18001077d  mov     edx, ebx; SizeInWords
0x18001077f  lea     rcx, [rbp+5C0h+Destination]; Destination
0x180010786  call    cs:__imp_wcscat_s
0x18001078d  nop     dword ptr [rax+rax+00h]
0x180010792  lea     rax, [rsp+6C0h+dwDisposition]
0x180010797  xor     r9d, r9d; lpClass
0x18001079a  mov     [rsp+6C0h+lpdwDisposition], rax; lpdwDisposition
0x18001079f  lea     rdx, [rbp+5C0h+Destination]; lpSubKey
0x1800107a6  lea     rax, [rsp+6C0h+hKey]
0x1800107ab  xor     r8d, r8d; Reserved
0x1800107ae  mov     [rsp+6C0h+phkResult], rax; phkResult
0x1800107b3  mov     rcx, rdi; hKey
0x1800107b6  mov     [rsp+6C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800107bb  mov     [rsp+6C0h+samDesired], 0F003Fh; samDesired
0x1800107c3  mov     [rsp+6C0h+dwOptions], r14d; dwOptions
0x1800107c8  call    cs:__imp_RegCreateKeyExW
0x1800107cf  nop     dword ptr [rax+rax+00h]
0x1800107d4  test    eax, eax
0x1800107d6  jnz     loc_18001094C
0x1800107dc  lea     r8, [rsi+10h]; Source
0x1800107e0  mov     edx, ebx; SizeInWords
0x1800107e2  lea     rcx, [rbp+5C0h+var_240]; Destination
0x1800107e9  call    cs:__imp_wcscpy_s
0x1800107f0  nop     dword ptr [rax+rax+00h]
0x1800107f5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800107f9  mov     r8d, 103h
0x1800107ff  mov     r9d, r14d
0x180010802  lea     edi, [rbx+2]
0x180010805  lea     r10d, [r8-4]
0x180010809  lea     rax, [rbp+5C0h+var_240]
0x180010810  mov     rcx, rbx
0x180010813  inc     rcx
0x180010816  cmp     [rax+rcx*2], r14w
0x18001081b  jnz     short loc_180010813
0x18001081d  cmp     ecx, r8d
0x180010820  mov     eax, r8d
0x180010823  cmovl   eax, ecx
0x180010826  cmp     r9d, eax
0x180010829  jge     short loc_180010854
0x18001082b  movsxd  rdx, r9d
0x18001082e  mov     ecx, 80h
0x180010833  add     cx, [rbp+rdx*2+5C0h+var_240]
0x18001083b  movzx   eax, cx
0x18001083e  sub     ax, r10w
0x180010842  cmp     cx, r10w
0x180010846  cmova   cx, ax
0x18001084a  add     r9d, edi
0x18001084d  mov     word ptr [rsp+rdx*2+6C0h+Data], cx
0x180010852  jmp     short loc_180010809
0x180010854  cmp     ecx, r8d
0x180010857  mov     rax, rbx
0x18001085a  cmovl   r8d, ecx
0x18001085e  movsxd  rcx, r8d
0x180010861  mov     word ptr [rsp+rcx*2+6C0h+Data], r14w
0x180010867  lea     rcx, [rsp+6C0h+Data]
0x18001086c  inc     rax
0x18001086f  cmp     [rcx+rax*2], r14w
0x180010874  jnz     short loc_18001086C
0x180010876  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18001087b  lea     eax, ds:2[rax*2]
0x180010882  mov     [rsp+6C0h+samDesired], eax; cbData
0x180010886  lea     rdx, aUser; "User"
0x18001088d  lea     rax, [rsp+6C0h+Data]
0x180010892  mov     r9d, 3; dwType
0x180010898  xor     r8d, r8d; Reserved
0x18001089b  mov     qword ptr [rsp+6C0h+dwOptions], rax; lpData
0x1800108a0  call    cs:__imp_RegSetValueExW
0x1800108a7  nop     dword ptr [rax+rax+00h]
0x1800108ac  lea     rcx, [rsi+428h]
0x1800108b3  inc     rbx
0x1800108b6  cmp     [rcx+rbx*2], r14w
0x1800108bb  jnz     short loc_1800108B3
0x1800108bd  lea     eax, ds:2[rbx*2]
0x1800108c4  mov     r9d, edi; dwType
0x1800108c7  mov     [rsp+6C0h+samDesired], eax; cbData
0x1800108cb  lea     rdx, aPcnfsdserver; "PCNFSDServer"
0x1800108d2  mov     qword ptr [rsp+6C0h+dwOptions], rcx; lpData
0x1800108d7  xor     r8d, r8d; Reserved
0x1800108da  mov     rcx, [rsp+6C0h+hKey]; hKey
0x1800108df  call    cs:__imp_RegSetValueExW
0x1800108e6  nop     dword ptr [rax+rax+00h]
0x1800108eb  mov     rcx, [rsp+6C0h+hKey]; hKey
0x1800108f0  lea     rdx, aNisdomain; "NISDomain"
0x1800108f7  mov     r9d, edi; dwType
0x1800108fa  mov     [rsp+6C0h+samDesired], r14d; cbData
0x1800108ff  xor     r8d, r8d; Reserved
0x180010902  mov     qword ptr [rsp+6C0h+dwOptions], r14; lpData
0x180010907  call    cs:__imp_RegSetValueExW
0x18001090e  nop     dword ptr [rax+rax+00h]
0x180010913  mov     rcx, [rsp+6C0h+hKey]; hKey
0x180010918  lea     rdx, aNisserver; "NISServer"
0x18001091f  mov     r9d, edi; dwType
0x180010922  mov     [rsp+6C0h+samDesired], r14d; cbData
0x180010927  xor     r8d, r8d; Reserved
0x18001092a  mov     qword ptr [rsp+6C0h+dwOptions], r14; lpData
0x18001092f  call    cs:__imp_RegSetValueExW
0x180010936  nop     dword ptr [rax+rax+00h]
0x18001093b  mov     rcx, [rsp+6C0h+hKey]; hKey
0x180010940  call    cs:__imp_RegCloseKey
0x180010947  nop     dword ptr [rax+rax+00h]
0x18001094c  mov     rcx, [rbp+5C0h+var_30]
0x180010953  xor     rcx, rsp; StackCookie
0x180010956  call    __security_check_cookie
0x18001095b  add     rsp, 6A0h
0x180010962  pop     r14
0x180010964  pop     rdi
0x180010965  pop     rsi
0x180010966  pop     rbx
0x180010967  pop     rbp
0x180010968  retn
```
