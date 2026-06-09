# InitFeatures(void)

- ea: `0x1800491f8`
- end: `0x18004937f`
- name: `?InitFeatures@@YAXXZ`
- size: `391`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800491ac`

## callees

- `0x1800491f8`
- `0x180049388`
- `0x1800966e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18004926e`
- `ADVAPI32!RegOpenKeyExA` at `0x18004929f`
- `ADVAPI32!RegOpenKeyExA` at `0x18004926e`
- `ADVAPI32!RegOpenKeyExA` at `0x18004929f`
- `ADVAPI32!RegCloseKey` at `0x180049332`
- `ADVAPI32!RegCloseKey` at `0x180049351`
- `ADVAPI32!RegCloseKey` at `0x180049332`
- `ADVAPI32!RegCloseKey` at `0x180049351`
- `ADVAPI32!RegQueryValueExA` at `0x180049304`
- `ADVAPI32!RegQueryValueExA` at `0x180049304`

## pseudocode

```c
void InitFeatures(void)
{
  struct FeatureEntry near **v0; // rbx
  int v1; // edi
  bool v2; // zf
  HKEY v3; // rcx
  int v4; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  CHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF

  if ( (unsigned int)GetModuleNameA(SubKey) )
    return;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  phkResult = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\Windows Script\\Features", 0, 1u, &hKey) )
    return;
  RegOpenKeyExA(hKey, SubKey, 0, 1u, &phkResult);
  v0 = &g_arFeatures;
  v1 = 5;
  do
  {
    v2 = (*(_BYTE *)v0 & 1) == 0;
    *(_DWORD *)Data = *((_DWORD *)v0 + 5);
    Type = 4;
    cbData = 4;
    if ( v2 )
    {
      v3 = hKey;
    }
    else
    {
      v3 = phkResult;
      if ( !phkResult )
        goto LABEL_10;
    }
    if ( !RegQueryValueExA(v3, (LPCSTR)v0[1], 0, &Type, Data, &cbData) )
    {
      v4 = *(_DWORD *)Data;
      *(_DWORD *)v0 |= 0x1000000u;
      *((_DWORD *)v0 + 4) = v4;
    }
LABEL_10:
    v0 += 3;
    --v1;
  }
  while ( v1 );
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x1800491f8  mov     [rsp-8+arg_0], rbx
0x1800491fd  mov     [rsp-8+arg_8], rdi
0x180049202  push    rbp
0x180049203  lea     rbp, [rsp-70h]
0x180049208  sub     rsp, 170h
0x18004920f  mov     rax, cs:__security_cookie
0x180049216  xor     rax, rsp
0x180049219  mov     [rbp+70h+var_10], rax
0x18004921d  lea     rcx, [rsp+170h+SubKey]; Filename
0x180049222  call    GetModuleNameA
0x180049227  test    eax, eax
0x180049229  jnz     loc_18004935D
0x18004922f  mov     [rsp+170h+Type], eax
0x180049233  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows Script\\Fe"...
0x18004923a  mov     dword ptr [rsp+170h+Data], eax
0x18004923e  mov     r9d, 1; samDesired
0x180049244  mov     [rsp+170h+cbData], eax
0x180049248  xor     r8d, r8d; ulOptions
0x18004924b  lea     rax, [rsp+170h+hKey]
0x180049250  mov     [rsp+170h+hKey], 0
0x180049259  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049260  mov     [rsp+170h+phkResult], rax; phkResult
0x180049265  mov     [rsp+170h+var_128], 0
0x18004926e  call    cs:__imp_RegOpenKeyExA
0x180049275  nop     dword ptr [rax+rax+00h]
0x18004927a  test    eax, eax
0x18004927c  jnz     loc_18004935D
0x180049282  mov     rcx, [rsp+170h+hKey]; hKey
0x180049287  lea     rax, [rsp+170h+var_128]
0x18004928c  mov     r9d, 1; samDesired
0x180049292  mov     [rsp+170h+phkResult], rax; phkResult
0x180049297  xor     r8d, r8d; ulOptions
0x18004929a  lea     rdx, [rsp+170h+SubKey]; lpSubKey
0x18004929f  call    cs:__imp_RegOpenKeyExA
0x1800492a6  nop     dword ptr [rax+rax+00h]
0x1800492ab  lea     rbx, ?g_arFeatures@@3PAUFeatureEntry@@A; FeatureEntry near * g_arFeatures
0x1800492b2  mov     edi, 5
0x1800492b7  test    byte ptr [rbx], 1
0x1800492ba  mov     eax, [rbx+14h]
0x1800492bd  mov     dword ptr [rsp+170h+Data], eax
0x1800492c1  mov     [rsp+170h+Type], 4
0x1800492c9  mov     [rsp+170h+cbData], 4
0x1800492d1  jz      short loc_1800492DF
0x1800492d3  mov     rcx, [rsp+170h+var_128]
0x1800492d8  test    rcx, rcx
0x1800492db  jnz     short loc_1800492E4
0x1800492dd  jmp     short loc_18004931F
0x1800492df  mov     rcx, [rsp+170h+hKey]; hKey
0x1800492e4  mov     rdx, [rbx+8]; lpValueName
0x1800492e8  lea     rax, [rsp+170h+cbData]
0x1800492ed  mov     [rsp+170h+lpcbData], rax; lpcbData
0x1800492f2  lea     r9, [rsp+170h+Type]; lpType
0x1800492f7  lea     rax, [rsp+170h+Data]
0x1800492fc  xor     r8d, r8d; lpReserved
0x1800492ff  mov     [rsp+170h+phkResult], rax; lpData
0x180049304  call    cs:__imp_RegQueryValueExA
0x18004930b  nop     dword ptr [rax+rax+00h]
0x180049310  test    eax, eax
0x180049312  jnz     short loc_18004931F
0x180049314  mov     eax, dword ptr [rsp+170h+Data]
0x180049318  bts     dword ptr [rbx], 18h
0x18004931c  mov     [rbx+10h], eax
0x18004931f  add     rbx, 18h
0x180049323  sub     edi, 1
0x180049326  jnz     short loc_1800492B7
0x180049328  mov     rcx, [rsp+170h+hKey]; hKey
0x18004932d  test    rcx, rcx
0x180049330  jz      short loc_180049347
0x180049332  call    cs:__imp_RegCloseKey
0x180049339  nop     dword ptr [rax+rax+00h]
0x18004933e  mov     [rsp+170h+hKey], 0
0x180049347  mov     rcx, [rsp+170h+var_128]; hKey
0x18004934c  test    rcx, rcx
0x18004934f  jz      short loc_18004935D
0x180049351  call    cs:__imp_RegCloseKey
0x180049358  nop     dword ptr [rax+rax+00h]
0x18004935d  mov     rcx, [rbp+70h+var_10]
0x180049361  xor     rcx, rsp; StackCookie
0x180049364  call    __security_check_cookie
0x180049369  lea     r11, [rsp+170h+var_s0]
0x180049371  mov     rbx, [r11+10h]
0x180049375  mov     rdi, [r11+18h]
0x180049379  mov     rsp, r11
0x18004937c  pop     rbp
0x18004937d  retn
```
