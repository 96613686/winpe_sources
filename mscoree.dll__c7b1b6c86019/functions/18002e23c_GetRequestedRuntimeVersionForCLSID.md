# GetRequestedRuntimeVersionForCLSID

- ea: `0x18002e23c`
- end: `0x18002e487`
- name: `GetRequestedRuntimeVersionForCLSID`
- size: `587`
- prototype: `__int64 __fastcall(struct _GUID *, wchar_t *Destination, rsize_t SizeInWords, unsigned int *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800257e0`

## callees

- `0x180003840`
- `0x180008710`
- `0x180009af4`
- `0x18000c1a8`
- `0x18000d264`
- `0x18000d614`
- `0x180029774`
- `0x18002e23c`
- `0x180039620`
- `0x180041ac0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002e354`
- `ADVAPI32!RegOpenKeyExW` at `0x18002e354`
- `ADVAPI32!RegQueryValueExW` at `0x18002e382`
- `ADVAPI32!RegQueryValueExW` at `0x18002e382`
- `ADVAPI32!RegCloseKey` at `0x18002e43e`
- `ADVAPI32!RegCloseKey` at `0x18002e43e`

## string_xrefs

- `0x18002e303`: `CLSID\`

## pseudocode

```c
__int64 __fastcall GetRequestedRuntimeVersionForCLSID(
        struct _GUID *a1,
        wchar_t *Destination,
        rsize_t SizeInWords,
        unsigned int *a4,
        int a5)
{
  rsize_t v5; // r12
  __int64 v6; // r14
  unsigned __int16 *v10; // rdi
  struct _GUID v11; // xmm0
  int v12; // ebx
  unsigned int v13; // esi
  int VersionForCLSID; // eax
  unsigned __int16 *v15; // r8
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+70h] [rbp-90h]
  __int128 v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+98h] [rbp-68h]
  __int64 v27; // [rsp+A0h] [rbp-60h]
  int v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  __int64 v31; // [rsp+C0h] [rbp-40h]
  int v32; // [rsp+C8h] [rbp-38h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
  struct _GUID v34; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t Source[64]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t Destinationa[128]; // [rsp+170h] [rbp+70h] BYREF

  v5 = (unsigned int)SizeInWords;
  v6 = -1;
  v26 = 0;
  v27 = 0;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 1;
  v28 = 1;
  v10 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = -1;
  v19 = 0;
  hKey = 0;
  if ( !a4 )
    goto LABEL_26;
  v11 = *a1;
  Type = 0;
  cbData = 0;
  v34 = v11;
  if ( (unsigned int)GuidToLPWSTR(&v34, Source, SizeInWords) )
  {
    wcscpy_s(Destinationa, 0x80u, L"CLSID\\");
    wcscat_s(Destinationa, 0x80u, Source);
    wcscat_s(Destinationa, 0x80u, L"\\InprocServer32");
    v13 = 0;
    if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, Destinationa, 0, 0x20019u, &hKey)
      || RegQueryValueExW(hKey, 0, 0, &Type, 0, &cbData)
      || Type != 1
      || !cbData )
    {
      v12 = -2147221164;
      goto LABEL_22;
    }
    if ( !a5 )
      goto LABEL_13;
    if ( a5 != 1 )
      goto LABEL_3;
    VersionForCLSID = FindVersionForCLSID(a1, &v19);
    v10 = v19;
    v12 = VersionForCLSID;
    if ( VersionForCLSID >= 0 )
    {
      v15 = 0;
      if ( v19 )
        v15 = v19;
    }
    else
    {
LABEL_13:
      DWORD2(v24) = 1;
      v12 = RuntimeRequest::ComputeVersionString(v21, 1);
      if ( v12 < 0 )
      {
LABEL_20:
        *a4 = v13;
        goto LABEL_22;
      }
      v15 = v21[0];
    }
    do
      ++v6;
    while ( v15[v6] );
    v13 = v6 + 1;
    if ( (int)v6 + 1 > (unsigned int)v5 )
    {
      v12 = -2147024774;
      goto LABEL_20;
    }
    if ( Destination )
    {
      wcsncpy_s(Destination, v5, v15, v13);
      goto LABEL_20;
    }
LABEL_26:
    v12 = -2147467261;
    goto LABEL_27;
  }
LABEL_3:
  v12 = -2147024809;
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 )
    operator delete(v10);
LABEL_27:
  RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002e23c  push    rbp
0x18002e23e  push    rbx
0x18002e23f  push    rsi
0x18002e240  push    rdi
0x18002e241  push    r12
0x18002e243  push    r13
0x18002e245  push    r14
0x18002e247  push    r15
0x18002e249  lea     rbp, [rsp-188h]
0x18002e251  sub     rsp, 288h
0x18002e258  mov     rax, cs:__security_cookie
0x18002e25f  xor     rax, rsp
0x18002e262  mov     [rbp+1C0h+var_50], rax
0x18002e269  xor     esi, esi
0x18002e26b  mov     r12d, r8d
0x18002e26e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002e272  mov     [rbp+1C0h+var_228], esi
0x18002e275  mov     [rbp+1C0h+var_220], rsi
0x18002e279  xorps   xmm0, xmm0
0x18002e27c  movdqa  xmmword ptr [rsp+2C0h+var_270], xmm0
0x18002e282  xorps   xmm1, xmm1
0x18002e285  movdqa  [rsp+2C0h+var_260], xmm1
0x18002e28b  mov     eax, 1
0x18002e290  movdqa  [rsp+2C0h+var_250], xmm0
0x18002e296  mov     r13, r9
0x18002e299  movdqa  [rbp+1C0h+var_240], xmm1
0x18002e29e  mov     r15, rdx
0x18002e2a1  mov     [rbp+1C0h+var_230], rax
0x18002e2a5  mov     rbx, rcx
0x18002e2a8  mov     [rbp+1C0h+var_218], eax
0x18002e2ab  mov     edi, esi
0x18002e2ad  mov     [rbp+1C0h+var_210], rsi
0x18002e2b1  mov     [rbp+1C0h+var_208], rsi
0x18002e2b5  mov     [rbp+1C0h+var_200], rsi
0x18002e2b9  mov     [rbp+1C0h+var_1F8], esi
0x18002e2bc  mov     [rbp+1C0h+var_1F0], r14
0x18002e2c0  mov     [rsp+2C0h+var_288], rsi
0x18002e2c5  mov     [rsp+2C0h+hKey], rsi
0x18002e2ca  test    r9, r9
0x18002e2cd  jz      loc_18002E453
0x18002e2d3  movups  xmm0, xmmword ptr [rcx]
0x18002e2d6  lea     rdx, [rbp+1C0h+Source]; unsigned __int16 *
0x18002e2da  mov     [rsp+2C0h+Type], esi
0x18002e2de  lea     rcx, [rbp+1C0h+var_1E0]; struct _GUID
0x18002e2e2  mov     [rsp+2C0h+cbData], esi
0x18002e2e6  movdqu  xmmword ptr [rbp+1C0h+var_1E0.Data1], xmm0
0x18002e2eb  call    ?GuidToLPWSTR@@YAHU_GUID@@PEAGK@Z; GuidToLPWSTR(_GUID,ushort *,ulong)
0x18002e2f0  test    eax, eax
0x18002e2f2  jnz     short loc_18002E2FE
0x18002e2f4  mov     ebx, 80070057h
0x18002e2f9  jmp     loc_18002E434
0x18002e2fe  mov     esi, 80h
0x18002e303  lea     r8, aClsid; "CLSID\\"
0x18002e30a  mov     edx, esi; SizeInWords
0x18002e30c  lea     rcx, [rbp+1C0h+Destination]; Destination
0x18002e310  call    wcscpy_s
0x18002e315  lea     r8, [rbp+1C0h+Source]; Source
0x18002e319  mov     edx, esi; SizeInWords
0x18002e31b  lea     rcx, [rbp+1C0h+Destination]; Destination
0x18002e31f  call    wcscat_s
0x18002e324  lea     r8, aInprocserver32; "\\InprocServer32"
0x18002e32b  mov     edx, esi; SizeInWords
0x18002e32d  lea     rcx, [rbp+1C0h+Destination]; Destination
0x18002e331  call    wcscat_s
0x18002e336  lea     rax, [rsp+2C0h+hKey]
0x18002e33b  mov     r9d, 20019h; samDesired
0x18002e341  xor     r8d, r8d; ulOptions
0x18002e344  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18002e349  lea     rdx, [rbp+1C0h+Destination]; lpSubKey
0x18002e34d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002e354  call    cs:__imp_RegOpenKeyExW
0x18002e35a  xor     esi, esi
0x18002e35c  test    eax, eax
0x18002e35e  jnz     loc_18002E42F
0x18002e364  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18002e369  lea     rax, [rsp+2C0h+cbData]
0x18002e36e  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x18002e373  lea     r9, [rsp+2C0h+Type]; lpType
0x18002e378  xor     r8d, r8d; lpReserved
0x18002e37b  mov     [rsp+2C0h+phkResult], rsi; lpData
0x18002e380  xor     edx, edx; lpValueName
0x18002e382  call    cs:__imp_RegQueryValueExW
0x18002e388  test    eax, eax
0x18002e38a  jnz     loc_18002E42F
0x18002e390  cmp     [rsp+2C0h+Type], 1
0x18002e395  jnz     loc_18002E42F
0x18002e39b  cmp     [rsp+2C0h+cbData], esi
0x18002e39f  jz      loc_18002E42F
0x18002e3a5  mov     ecx, [rbp+1C0h+arg_20]
0x18002e3ab  test    ecx, ecx
0x18002e3ad  jz      short loc_18002E3DD
0x18002e3af  cmp     ecx, 1
0x18002e3b2  jnz     loc_18002E2F4
0x18002e3b8  lea     rdx, [rsp+2C0h+var_288]; unsigned __int16 **
0x18002e3bd  mov     rcx, rbx; struct _GUID *
0x18002e3c0  call    ?FindVersionForCLSID@@YAJAEBU_GUID@@PEAPEAG@Z; FindVersionForCLSID(_GUID const &,ushort * *)
0x18002e3c5  mov     rdi, [rsp+2C0h+var_288]
0x18002e3ca  mov     ebx, eax
0x18002e3cc  test    eax, eax
0x18002e3ce  js      short loc_18002E3DD
0x18002e3d0  mov     r8d, esi
0x18002e3d3  test    rdi, rdi
0x18002e3d6  jz      short loc_18002E3FC
0x18002e3d8  mov     r8, rdi
0x18002e3db  jmp     short loc_18002E3FC
0x18002e3dd  mov     eax, 1
0x18002e3e2  lea     rcx, [rsp+2C0h+var_270]; this
0x18002e3e7  mov     edx, eax; int
0x18002e3e9  mov     dword ptr [rbp+1C0h+var_240+8], eax
0x18002e3ec  call    ?ComputeVersionString@RuntimeRequest@@QEAAJH@Z; RuntimeRequest::ComputeVersionString(int)
0x18002e3f1  mov     ebx, eax
0x18002e3f3  test    eax, eax
0x18002e3f5  js      short loc_18002E429
0x18002e3f7  mov     r8, [rsp+2C0h+var_270]; Source
0x18002e3fc  inc     r14
0x18002e3ff  cmp     [r8+r14*2], si
0x18002e404  jnz     short loc_18002E3FC
0x18002e406  lea     esi, [r14+1]
0x18002e40a  cmp     esi, r12d
0x18002e40d  jbe     short loc_18002E416
0x18002e40f  mov     ebx, 8007007Ah
0x18002e414  jmp     short loc_18002E429
0x18002e416  test    r15, r15
0x18002e419  jz      short loc_18002E453
0x18002e41b  mov     r9d, esi; MaxCount
0x18002e41e  mov     rdx, r12; SizeInWords
0x18002e421  mov     rcx, r15; Destination
0x18002e424  call    wcsncpy_s
0x18002e429  mov     [r13+0], esi
0x18002e42d  jmp     short loc_18002E434
0x18002e42f  mov     ebx, 80040154h
0x18002e434  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18002e439  test    rcx, rcx
0x18002e43c  jz      short loc_18002E444
0x18002e43e  call    cs:__imp_RegCloseKey
0x18002e444  test    rdi, rdi
0x18002e447  jz      short loc_18002E458
0x18002e449  mov     rcx, rdi; void *
0x18002e44c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002e451  jmp     short loc_18002E458
0x18002e453  mov     ebx, 80004003h
0x18002e458  lea     rcx, [rsp+2C0h+var_270]; this
0x18002e45d  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18002e462  mov     eax, ebx
0x18002e464  mov     rcx, [rbp+1C0h+var_50]
0x18002e46b  xor     rcx, rsp; StackCookie
0x18002e46e  call    __security_check_cookie
0x18002e473  add     rsp, 288h
0x18002e47a  pop     r15
0x18002e47c  pop     r14
0x18002e47e  pop     r13
0x18002e480  pop     r12
0x18002e482  pop     rdi
0x18002e483  pop     rsi
0x18002e484  pop     rbx
0x18002e485  pop     rbp
0x18002e486  retn
```
