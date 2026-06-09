# GetL2tpConfigParams

- ea: `0x180076ea0`
- end: `0x180077142`
- name: `GetL2tpConfigParams`
- size: `674`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b60`
- `0x180083de8`

## callees

- `0x180076420`
- `0x180076ea0`
- `0x180077148`
- `0x18007717c`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180077078`
- `ADVAPI32!RegOpenKeyExW` at `0x180077078`
- `ADVAPI32!RegQueryValueExW` at `0x180076f8f`
- `ADVAPI32!RegQueryValueExW` at `0x180076fe1`
- `ADVAPI32!RegQueryValueExW` at `0x1800770ef`
- `ADVAPI32!RegQueryValueExW` at `0x180076f8f`
- `ADVAPI32!RegQueryValueExW` at `0x180076fe1`
- `ADVAPI32!RegQueryValueExW` at `0x1800770ef`
- `ADVAPI32!RegCloseKey` at `0x1800770a6`
- `ADVAPI32!RegCloseKey` at `0x1800770a6`

## pseudocode

```c
__int64 __fastcall GetL2tpConfigParams(HKEY hKey, char a2, __int64 a3, unsigned int a4)
{
  unsigned int v6; // ebx
  bool v8; // cf
  unsigned int v9; // esi
  const WCHAR **v10; // rdi
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  __int128 v13; // xmm0
  __int64 v14; // xmm1_8
  __int64 v15; // xmm1_8
  void *v16; // rdi
  void *v17; // rsi
  HKEY v18; // rcx
  LSTATUS v19; // eax
  BYTE *v20; // r14
  BYTE *lpData; // [rsp+20h] [rbp-49h]
  DWORD cbData; // [rsp+30h] [rbp-39h] BYREF
  DWORD Type; // [rsp+34h] [rbp-35h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-31h] BYREF
  __int128 v26; // [rsp+40h] [rbp-29h] BYREF
  __int64 v27; // [rsp+50h] [rbp-19h]
  _QWORD v28[6]; // [rsp+58h] [rbp-11h] BYREF

  v28[0] = L"idleTimeout";
  v6 = 0;
  v28[1] = &v26;
  v28[2] = L"saLifeTime";
  v28[3] = (char *)&v26 + 8;
  v28[4] = L"saDataSize";
  v28[5] = (char *)&v26 + 12;
  v27 = 0;
  v26 = 0;
  if ( a2 != 1 && a2 != 2 )
  {
    if ( a2 == 3 || a2 == 4 )
    {
      v8 = a4 < 0x18;
    }
    else
    {
      if ( a2 != 5 )
        return 50;
      v8 = a4 < 0x20;
    }
    if ( v8 )
      return 87;
    v9 = 0;
    v10 = (const WCHAR **)v28;
    do
    {
      v11 = *v10;
      lpData = (BYTE *)v10[1];
      cbData = 4;
      Type = 4;
      v6 = RegQueryValueExW(hKey, v11, 0, &Type, lpData, &cbData);
      if ( v6 )
        return v6;
      ++v9;
      v10 += 2;
    }
    while ( v9 < 3 );
    if ( a2 >= 5
      && (cbData = 4,
          Type = 4,
          v12 = RegQueryValueExW(hKey, L"mmSaLifeTime", 0, &Type, (LPBYTE)(a3 + 24), &cbData),
          (v6 = v12) != 0) )
    {
      if ( v12 != 2 )
        return v6;
      v13 = v26;
      *(_DWORD *)(a3 + 24) = 28800;
      v14 = v27;
      *(_OWORD *)a3 = v13;
      *(_QWORD *)(a3 + 16) = v14;
    }
    else
    {
      v15 = v27;
      *(_OWORD *)a3 = v26;
      *(_QWORD *)(a3 + 16) = v15;
      if ( a2 < 3 )
        return v6;
    }
    v16 = (void *)MprCommonAlloc(24);
    v17 = v16;
    if ( !v16 )
      return 8;
    v18 = 0;
    phkResult = 0;
    if ( hKey )
    {
      v19 = RegOpenKeyExW(hKey, L"L2TPCustomPolicy", 0, 0x20019u, &phkResult);
      v18 = phkResult;
      v6 = v19;
      if ( !v19 )
      {
        GetCustomPolicyRegParams(phkResult, v16);
        v18 = phkResult;
      }
    }
    else
    {
      v6 = 87;
    }
    if ( v18 )
      RegCloseKey(v18);
    if ( v6 )
    {
      if ( v6 != 2 )
      {
LABEL_34:
        MprCommonFree(v16);
        return v6;
      }
      v17 = 0;
    }
    else
    {
      v16 = 0;
    }
    *(_QWORD *)(a3 + 16) = v17;
    v20 = (BYTE *)(a3 + 4);
    cbData = 4;
    Type = 4;
    v6 = RegQueryValueExW(hKey, L"EncryptionType", 0, &Type, v20, &cbData);
    if ( v6 == 2 )
    {
      v6 = 0;
      *(_DWORD *)v20 = 1;
    }
    if ( v16 )
      goto LABEL_34;
  }
  return v6;
}

```

## disassembly

```asm
0x180076ea0  mov     [rsp-8+arg_8], rbx
0x180076ea5  push    rbp
0x180076ea6  push    rsi
0x180076ea7  push    rdi
0x180076ea8  push    r12
0x180076eaa  push    r13
0x180076eac  push    r14
0x180076eae  push    r15
0x180076eb0  lea     rbp, [rsp-27h]
0x180076eb5  sub     rsp, 90h
0x180076ebc  mov     rax, cs:__security_cookie
0x180076ec3  xor     rax, rsp
0x180076ec6  mov     [rbp+57h+var_38], rax
0x180076eca  lea     rax, aIdletimeout; "idleTimeout"
0x180076ed1  movsx   r12d, dl
0x180076ed5  mov     [rbp+57h+var_68], rax
0x180076ed9  mov     r15, rcx
0x180076edc  lea     rax, [rbp+57h+var_80]
0x180076ee0  xor     ebx, ebx
0x180076ee2  mov     [rbp+57h+var_60], rax
0x180076ee6  mov     ecx, r12d
0x180076ee9  lea     rax, aSalifetime; "saLifeTime"
0x180076ef0  xorps   xmm0, xmm0
0x180076ef3  mov     [rbp+57h+var_58], rax
0x180076ef7  mov     r14, r8
0x180076efa  lea     rax, [rbp+57h+var_80+8]
0x180076efe  mov     [rbp+57h+var_50], rax
0x180076f02  lea     rax, aSadatasize; "saDataSize"
0x180076f09  mov     [rbp+57h+var_48], rax
0x180076f0d  lea     rax, [rbp+57h+var_80+0Ch]
0x180076f11  mov     [rbp+57h+var_40], rax
0x180076f15  xor     eax, eax
0x180076f17  mov     [rbp+57h+var_70], rax
0x180076f1b  movups  [rbp+57h+var_80], xmm0
0x180076f1f  sub     ecx, 1
0x180076f22  jz      loc_180077118
0x180076f28  sub     ecx, 1
0x180076f2b  jz      loc_180077118
0x180076f31  sub     ecx, 1
0x180076f34  jz      short loc_180076F58
0x180076f36  sub     ecx, 1
0x180076f39  jz      short loc_180076F58
0x180076f3b  cmp     ecx, 1
0x180076f3e  jz      short loc_180076F48
0x180076f40  lea     ebx, [rax+32h]
0x180076f43  jmp     loc_180077118
0x180076f48  cmp     r9d, 20h ; ' '
0x180076f4c  jnb     short loc_180076F5E
0x180076f4e  mov     ebx, 57h ; 'W'
0x180076f53  jmp     loc_180077118
0x180076f58  cmp     r9d, 18h
0x180076f5c  jmp     short loc_180076F4C
0x180076f5e  xor     esi, esi
0x180076f60  lea     rdi, [rbp+57h+var_68]
0x180076f64  lea     r13d, [rsi+4]
0x180076f68  mov     rdx, [rdi]; lpValueName
0x180076f6b  lea     rax, [rbp+57h+cbData]
0x180076f6f  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180076f74  lea     r9, [rbp+57h+Type]; lpType
0x180076f78  mov     rax, [rdi+8]
0x180076f7c  xor     r8d, r8d; lpReserved
0x180076f7f  mov     rcx, r15; hKey
0x180076f82  mov     [rsp+0C0h+lpData], rax; lpData
0x180076f87  mov     [rbp+57h+cbData], r13d
0x180076f8b  mov     [rbp+57h+Type], r13d
0x180076f8f  call    cs:__imp_RegQueryValueExW
0x180076f96  nop     dword ptr [rax+rax+00h]
0x180076f9b  mov     ebx, eax
0x180076f9d  test    eax, eax
0x180076f9f  jnz     loc_180077118
0x180076fa5  inc     esi
0x180076fa7  add     rdi, 10h
0x180076fab  cmp     esi, 3
0x180076fae  jb      short loc_180076F68
0x180076fb0  cmp     r12b, 5
0x180076fb4  jl      short loc_180077017
0x180076fb6  lea     rax, [rbp+57h+cbData]
0x180076fba  mov     [rbp+57h+cbData], r13d
0x180076fbe  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180076fc3  lea     rdi, [r14+18h]
0x180076fc7  lea     r9, [rbp+57h+Type]; lpType
0x180076fcb  mov     [rsp+0C0h+lpData], rdi; lpData
0x180076fd0  xor     r8d, r8d; lpReserved
0x180076fd3  mov     [rbp+57h+Type], r13d
0x180076fd7  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x180076fde  mov     rcx, r15; hKey
0x180076fe1  call    cs:__imp_RegQueryValueExW
0x180076fe8  nop     dword ptr [rax+rax+00h]
0x180076fed  mov     ebx, eax
0x180076fef  test    eax, eax
0x180076ff1  jz      short loc_180077017
0x180076ff3  cmp     eax, 2
0x180076ff6  jnz     loc_180077118
0x180076ffc  movups  xmm0, [rbp+57h+var_80]
0x180077000  mov     dword ptr [rdi], 7080h
0x180077006  movsd   xmm1, [rbp+57h+var_70]
0x18007700b  movups  xmmword ptr [r14], xmm0
0x18007700f  movsd   qword ptr [r14+10h], xmm1
0x180077015  jmp     short loc_180077034
0x180077017  movsd   xmm1, [rbp+57h+var_70]
0x18007701c  movups  xmm0, [rbp+57h+var_80]
0x180077020  movups  xmmword ptr [r14], xmm0
0x180077024  movsd   qword ptr [r14+10h], xmm1
0x18007702a  cmp     r12b, 3
0x18007702e  jl      loc_180077118
0x180077034  mov     ecx, 18h
0x180077039  call    MprCommonAlloc
0x18007703e  mov     rdi, rax
0x180077041  mov     rsi, rax
0x180077044  test    rax, rax
0x180077047  jnz     short loc_180077051
0x180077049  lea     ebx, [rax+8]
0x18007704c  jmp     loc_180077118
0x180077051  xor     ecx, ecx; hKey
0x180077053  mov     [rbp+57h+phkResult], rcx
0x180077057  test    r15, r15
0x18007705a  jz      short loc_18007709C
0x18007705c  lea     rax, [rbp+57h+phkResult]
0x180077060  mov     r9d, 20019h; samDesired
0x180077066  xor     r8d, r8d; ulOptions
0x180077069  mov     [rsp+0C0h+lpData], rax; phkResult
0x18007706e  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x180077075  mov     rcx, r15; hKey
0x180077078  call    cs:__imp_RegOpenKeyExW
0x18007707f  nop     dword ptr [rax+rax+00h]
0x180077084  mov     rcx, [rbp+57h+phkResult]
0x180077088  mov     ebx, eax
0x18007708a  test    eax, eax
0x18007708c  jnz     short loc_1800770A1
0x18007708e  mov     rdx, rdi
0x180077091  call    GetCustomPolicyRegParams
0x180077096  mov     rcx, [rbp+57h+phkResult]
0x18007709a  jmp     short loc_1800770A1
0x18007709c  mov     ebx, 57h ; 'W'
0x1800770a1  test    rcx, rcx
0x1800770a4  jz      short loc_1800770B2
0x1800770a6  call    cs:__imp_RegCloseKey
0x1800770ad  nop     dword ptr [rax+rax+00h]
0x1800770b2  test    ebx, ebx
0x1800770b4  jz      short loc_1800770BF
0x1800770b6  cmp     ebx, 2
0x1800770b9  jnz     short loc_180077110
0x1800770bb  xor     esi, esi
0x1800770bd  jmp     short loc_1800770C1
0x1800770bf  xor     edi, edi
0x1800770c1  mov     [r14+10h], rsi
0x1800770c5  lea     rax, [rbp+57h+cbData]
0x1800770c9  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x1800770ce  lea     r9, [rbp+57h+Type]; lpType
0x1800770d2  add     r14, r13
0x1800770d5  mov     [rbp+57h+cbData], r13d
0x1800770d9  xor     r8d, r8d; lpReserved
0x1800770dc  mov     [rsp+0C0h+lpData], r14; lpData
0x1800770e1  lea     rdx, aEncryptiontype; "EncryptionType"
0x1800770e8  mov     [rbp+57h+Type], r13d
0x1800770ec  mov     rcx, r15; hKey
0x1800770ef  call    cs:__imp_RegQueryValueExW
0x1800770f6  nop     dword ptr [rax+rax+00h]
0x1800770fb  mov     ebx, eax
0x1800770fd  cmp     eax, 2
0x180077100  jnz     short loc_18007710B
0x180077102  xor     ebx, ebx
0x180077104  mov     dword ptr [r14], 1
0x18007710b  test    rdi, rdi
0x18007710e  jz      short loc_180077118
0x180077110  mov     rcx, rdi; lpMem
0x180077113  call    MprCommonFree
0x180077118  mov     eax, ebx
0x18007711a  mov     rcx, [rbp+57h+var_38]
0x18007711e  xor     rcx, rsp; StackCookie
0x180077121  call    __security_check_cookie
0x180077126  mov     rbx, [rsp+0C0h+arg_8]
0x18007712e  add     rsp, 90h
0x180077135  pop     r15
0x180077137  pop     r14
0x180077139  pop     r13
0x18007713b  pop     r12
0x18007713d  pop     rdi
0x18007713e  pop     rsi
0x18007713f  pop     rbp
0x180077140  retn
```
