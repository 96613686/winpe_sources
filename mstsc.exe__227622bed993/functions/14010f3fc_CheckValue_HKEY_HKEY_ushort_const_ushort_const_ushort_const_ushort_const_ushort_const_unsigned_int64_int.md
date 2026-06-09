# CheckValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,int *)

- ea: `0x14010f3fc`
- end: `0x14010f757`
- name: `?CheckValue@@YAJPEAUHKEY__@@0PEBG1111_KPEAH@Z`
- size: `859`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, LPCWSTR lpValueName, const unsigned __int16 *, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14010f2d8`

## callees

- `0x140040474`
- `0x14010f3fc`
- `0x14010f760`
- `0x14010fa48`
- `0x14010fb2c`
- `0x140111220`

## import_xrefs

- `msvcrt!wcsncat_s` at `0x14010f659`
- `msvcrt!wcsncat_s` at `0x14010f659`
- `msvcrt!wcsncpy_s` at `0x14010f63b`
- `msvcrt!wcsncpy_s` at `0x14010f63b`
- `ADVAPI32!RegOpenKeyExW` at `0x14010f511`
- `ADVAPI32!RegOpenKeyExW` at `0x14010f67d`
- `ADVAPI32!RegOpenKeyExW` at `0x14010f511`
- `ADVAPI32!RegOpenKeyExW` at `0x14010f67d`
- `ADVAPI32!RegCloseKey` at `0x14010f71c`
- `ADVAPI32!RegCloseKey` at `0x14010f72c`
- `ADVAPI32!RegCloseKey` at `0x14010f71c`
- `ADVAPI32!RegCloseKey` at `0x14010f72c`
- `ADVAPI32!RegQueryValueExW` at `0x14010f4b1`
- `ADVAPI32!RegQueryValueExW` at `0x14010f59e`
- `ADVAPI32!RegQueryValueExW` at `0x14010f4b1`
- `ADVAPI32!RegQueryValueExW` at `0x14010f59e`

## pseudocode

```c
__int64 __fastcall CheckValue(
        HKEY hKey,
        HKEY a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        LPCWSTR lpValueName,
        wchar_t *String2,
        unsigned __int64 a8,
        int *a9)
{
  wchar_t *v10; // rbx
  LSTATUS v12; // eax
  signed int v13; // edi
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  HKEY v16; // r13
  rsize_t v17; // rsi
  LSTATUS v18; // eax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v25; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-A8h]
  HKEY hKeya; // [rsp+60h] [rbp-A0h]
  wchar_t Destination[256]; // [rsp+70h] [rbp-90h] BYREF

  v10 = a3;
  v27 = a5;
  hKeya = a2;
  v26 = 0;
  phkResult = 0;
  v25 = 0;
  v23 = 0;
  *a9 = 0;
  if ( !hKey || !a3 )
    goto LABEL_23;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  v12 = RegQueryValueExW(hKey, a3, 0, &Type, Data, &cbData);
  v13 = v12;
  if ( v12 != 2 )
  {
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v13 < 0 )
      goto LABEL_46;
    if ( Type != 4 )
    {
LABEL_8:
      v13 = -2147024883;
      goto LABEL_46;
    }
    if ( !*(_DWORD *)Data )
      goto LABEL_45;
  }
  v14 = RegOpenKeyExW(hKey, v10, 0, 0x20019u, &phkResult);
  v13 = v14;
  if ( v14 == 2 )
    goto LABEL_23;
  if ( v14 > 0 )
    v13 = (unsigned __int16)v14 | 0x80070000;
  if ( v13 >= 0 )
  {
    v13 = QueryForMatch(phkResult, String2, a8, a9);
    if ( v13 >= 0 && !*a9 && lpValueName )
    {
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      v15 = RegQueryValueExW(hKey, lpValueName, 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData);
      v13 = v15;
      if ( v15 == 2 )
        goto LABEL_23;
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      if ( v13 >= 0 )
      {
        if ( *(_DWORD *)Data != 4 )
          goto LABEL_8;
        if ( Type )
        {
LABEL_23:
          v13 = IsDomainJoinedNetapi32(&v23);
          if ( v13 < 0 )
            goto LABEL_46;
          v16 = hKeya;
          if ( v23 )
            a4 = v27;
          if ( hKeya && v10 )
          {
            if ( v23 )
            {
              v17 = -1;
              do
                ++v17;
              while ( v10[v17] );
              wcsncpy_s(Destination, 0x100u, v10, v17);
              wcsncat_s(Destination, 256 - v17, L"Domain", 6u);
              v10 = Destination;
            }
            v18 = RegOpenKeyExW(v16, v10, 0, 0x20019u, &v25);
            if ( v18 )
            {
              if ( v18 != 2 )
              {
                if ( v18 > 0 )
                  v13 = (unsigned __int16)v18 | 0x80070000;
                else
                  v13 = v18;
                goto LABEL_46;
              }
            }
            else
            {
              v13 = QueryForMatch(v25, String2, a8, a9);
              if ( v13 < 0 || *a9 )
                goto LABEL_46;
            }
          }
          if ( !a4 )
          {
LABEL_45:
            v13 = 0;
            goto LABEL_46;
          }
          if ( !String2 )
          {
            *a9 = 1;
            goto LABEL_46;
          }
          v13 = StringCchLengthW(a4, 0x400u, &v26);
          if ( v13 >= 0 )
          {
            *a9 = CompareValue(String2, a8, a4, v26);
            goto LABEL_45;
          }
        }
      }
    }
  }
LABEL_46:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v25 )
    RegCloseKey(v25);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14010f3fc  push    rbp
0x14010f3fe  push    rbx
0x14010f3ff  push    rsi
0x14010f400  push    rdi
0x14010f401  push    r12
0x14010f403  push    r13
0x14010f405  push    r14
0x14010f407  push    r15
0x14010f409  lea     rbp, [rsp-188h]
0x14010f411  sub     rsp, 288h
0x14010f418  mov     rax, cs:__security_cookie
0x14010f41f  xor     rax, rsp
0x14010f422  mov     [rbp+1C0h+var_50], rax
0x14010f429  mov     rax, [rbp+1C0h+arg_20]
0x14010f430  mov     r15, r9
0x14010f433  mov     r14, [rbp+1C0h+arg_40]
0x14010f43a  mov     rbx, r8
0x14010f43d  mov     r13, [rbp+1C0h+lpValueName]
0x14010f444  mov     rsi, rcx
0x14010f447  mov     r12, [rbp+1C0h+String2]
0x14010f44e  mov     [rsp+2C0h+var_268], rax
0x14010f453  xor     eax, eax
0x14010f455  mov     [rsp+2C0h+hKey], rdx
0x14010f45a  mov     [rsp+2C0h+var_270], rax
0x14010f45f  mov     [rsp+2C0h+phkResult], rax
0x14010f464  mov     [rsp+2C0h+var_278], rax
0x14010f469  mov     [rsp+2C0h+var_284], eax
0x14010f46d  mov     [r14], eax
0x14010f470  test    rcx, rcx
0x14010f473  jz      loc_14010F5DF
0x14010f479  test    rbx, rbx
0x14010f47c  jz      loc_14010F5DF
0x14010f482  mov     dword ptr [rsp+2C0h+Data], eax
0x14010f486  lea     r9, [rsp+2C0h+Type]; lpType
0x14010f48b  mov     [rsp+2C0h+Type], eax
0x14010f48f  xor     r8d, r8d; lpReserved
0x14010f492  lea     rax, [rsp+2C0h+cbData]
0x14010f497  mov     [rsp+2C0h+cbData], 4
0x14010f49f  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x14010f4a4  mov     rdx, rbx; lpValueName
0x14010f4a7  lea     rax, [rsp+2C0h+Data]
0x14010f4ac  mov     [rsp+2C0h+lpData], rax; lpData
0x14010f4b1  call    cs:__imp_RegQueryValueExW
0x14010f4b7  mov     edi, eax
0x14010f4b9  cmp     eax, 2
0x14010f4bc  jz      short loc_14010F4F8
0x14010f4be  xor     ecx, ecx
0x14010f4c0  test    eax, eax
0x14010f4c2  jle     short loc_14010F4CD
0x14010f4c4  movzx   edi, ax
0x14010f4c7  or      edi, 80070000h
0x14010f4cd  test    edi, edi
0x14010f4cf  js      loc_14010F712
0x14010f4d5  cmp     [rsp+2C0h+Type], 4
0x14010f4da  jz      short loc_14010F4E6
0x14010f4dc  mov     edi, 8007000Dh
0x14010f4e1  jmp     loc_14010F712
0x14010f4e6  cmp     dword ptr [rsp+2C0h+Data], ecx
0x14010f4ea  jz      loc_14010F710
0x14010f4f0  test    edi, edi
0x14010f4f2  js      loc_14010F712
0x14010f4f8  lea     rax, [rsp+2C0h+phkResult]
0x14010f4fd  mov     r9d, 20019h; samDesired
0x14010f503  xor     r8d, r8d; ulOptions
0x14010f506  mov     [rsp+2C0h+lpData], rax; phkResult
0x14010f50b  mov     rdx, rbx; lpSubKey
0x14010f50e  mov     rcx, rsi; hKey
0x14010f511  call    cs:__imp_RegOpenKeyExW
0x14010f517  mov     edi, eax
0x14010f519  cmp     eax, 2
0x14010f51c  jz      loc_14010F5DF
0x14010f522  test    eax, eax
0x14010f524  jle     short loc_14010F52F
0x14010f526  movzx   edi, ax
0x14010f529  or      edi, 80070000h
0x14010f52f  test    edi, edi
0x14010f531  js      loc_14010F712
0x14010f537  mov     r8, [rbp+1C0h+arg_38]; unsigned __int64
0x14010f53e  mov     r9, r14; int *
0x14010f541  mov     rcx, [rsp+2C0h+phkResult]; HKEY
0x14010f546  mov     rdx, r12; String2
0x14010f549  call    ?QueryForMatch@@YAJPEAUHKEY__@@PEBG_KPEAH@Z; QueryForMatch(HKEY__ *,ushort const *,unsigned __int64,int *)
0x14010f54e  xor     ecx, ecx
0x14010f550  mov     edi, eax
0x14010f552  test    eax, eax
0x14010f554  js      loc_14010F712
0x14010f55a  cmp     [r14], ecx
0x14010f55d  jnz     loc_14010F712
0x14010f563  test    r13, r13
0x14010f566  jz      loc_14010F712
0x14010f56c  lea     rax, [rsp+2C0h+cbData]
0x14010f571  mov     [rsp+2C0h+Type], ecx
0x14010f575  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x14010f57a  lea     r9, [rsp+2C0h+Data]; lpType
0x14010f57f  lea     rax, [rsp+2C0h+Type]
0x14010f584  mov     dword ptr [rsp+2C0h+Data], ecx
0x14010f588  xor     r8d, r8d; lpReserved
0x14010f58b  mov     [rsp+2C0h+lpData], rax; lpData
0x14010f590  mov     rdx, r13; lpValueName
0x14010f593  mov     [rsp+2C0h+cbData], 4
0x14010f59b  mov     rcx, rsi; hKey
0x14010f59e  call    cs:__imp_RegQueryValueExW
0x14010f5a4  mov     edi, eax
0x14010f5a6  cmp     eax, 2
0x14010f5a9  jz      short loc_14010F5DF
0x14010f5ab  xor     ecx, ecx
0x14010f5ad  test    eax, eax
0x14010f5af  jle     short loc_14010F5BA
0x14010f5b1  movzx   edi, ax
0x14010f5b4  or      edi, 80070000h
0x14010f5ba  test    edi, edi
0x14010f5bc  js      loc_14010F712
0x14010f5c2  cmp     dword ptr [rsp+2C0h+Data], 4
0x14010f5c7  jnz     loc_14010F4DC
0x14010f5cd  cmp     [rsp+2C0h+Type], ecx
0x14010f5d1  jz      loc_14010F712
0x14010f5d7  test    edi, edi
0x14010f5d9  js      loc_14010F712
0x14010f5df  lea     rcx, [rsp+2C0h+var_284]; int *
0x14010f5e4  call    ?IsDomainJoinedNetapi32@@YAJPEAH@Z; IsDomainJoinedNetapi32(int *)
0x14010f5e9  xor     ecx, ecx
0x14010f5eb  mov     edi, eax
0x14010f5ed  test    eax, eax
0x14010f5ef  js      loc_14010F712
0x14010f5f5  mov     eax, [rsp+2C0h+var_284]
0x14010f5f9  test    eax, eax
0x14010f5fb  mov     r13, [rsp+2C0h+hKey]
0x14010f600  cmovnz  r15, [rsp+2C0h+var_268]
0x14010f606  test    r13, r13
0x14010f609  jz      loc_14010F6C9
0x14010f60f  test    rbx, rbx
0x14010f612  jz      loc_14010F6C9
0x14010f618  test    eax, eax
0x14010f61a  jz      short loc_14010F664
0x14010f61c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14010f620  inc     rsi
0x14010f623  cmp     [rbx+rsi*2], cx
0x14010f627  jnz     short loc_14010F620
0x14010f629  mov     r8, rbx; Source
0x14010f62c  lea     rcx, [rsp+2C0h+Destination]; Destination
0x14010f631  mov     ebx, 100h
0x14010f636  mov     r9, rsi; MaxCount
0x14010f639  mov     edx, ebx; SizeInWords
0x14010f63b  call    cs:__imp_wcsncpy_s
0x14010f641  sub     rbx, rsi
0x14010f644  lea     r8, aDomain; "Domain"
0x14010f64b  mov     rdx, rbx; SizeInWords
0x14010f64e  lea     rcx, [rsp+2C0h+Destination]; Destination
0x14010f653  mov     r9d, 6; MaxCount
0x14010f659  call    cs:__imp_wcsncat_s
0x14010f65f  lea     rbx, [rsp+2C0h+Destination]
0x14010f664  lea     rax, [rsp+2C0h+var_278]
0x14010f669  mov     r9d, 20019h; samDesired
0x14010f66f  xor     r8d, r8d; ulOptions
0x14010f672  mov     [rsp+2C0h+lpData], rax; phkResult
0x14010f677  mov     rdx, rbx; lpSubKey
0x14010f67a  mov     rcx, r13; hKey
0x14010f67d  call    cs:__imp_RegOpenKeyExW
0x14010f683  xor     ecx, ecx
0x14010f685  test    eax, eax
0x14010f687  jnz     short loc_14010F6AF
0x14010f689  mov     r8, [rbp+1C0h+arg_38]; unsigned __int64
0x14010f690  mov     r9, r14; int *
0x14010f693  mov     rcx, [rsp+2C0h+var_278]; HKEY
0x14010f698  mov     rdx, r12; String2
0x14010f69b  call    ?QueryForMatch@@YAJPEAUHKEY__@@PEBG_KPEAH@Z; QueryForMatch(HKEY__ *,ushort const *,unsigned __int64,int *)
0x14010f6a0  xor     ecx, ecx
0x14010f6a2  mov     edi, eax
0x14010f6a4  test    eax, eax
0x14010f6a6  js      short loc_14010F712
0x14010f6a8  cmp     [r14], ecx
0x14010f6ab  jnz     short loc_14010F712
0x14010f6ad  jmp     short loc_14010F6C9
0x14010f6af  cmp     eax, 2
0x14010f6b2  jz      short loc_14010F6C9
0x14010f6b4  test    eax, eax
0x14010f6b6  jg      short loc_14010F6BC
0x14010f6b8  mov     edi, eax
0x14010f6ba  jmp     short loc_14010F6C5
0x14010f6bc  movzx   edi, ax
0x14010f6bf  or      edi, 80070000h
0x14010f6c5  test    edi, edi
0x14010f6c7  js      short loc_14010F712
0x14010f6c9  test    r15, r15
0x14010f6cc  jz      short loc_14010F710
0x14010f6ce  test    r12, r12
0x14010f6d1  jnz     short loc_14010F6DC
0x14010f6d3  mov     dword ptr [r14], 1
0x14010f6da  jmp     short loc_14010F712
0x14010f6dc  lea     r8, [rsp+2C0h+var_270]; unsigned __int64 *
0x14010f6e1  mov     edx, 400h; unsigned __int64
0x14010f6e6  mov     rcx, r15; unsigned __int16 *
0x14010f6e9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14010f6ee  mov     edi, eax
0x14010f6f0  test    eax, eax
0x14010f6f2  js      short loc_14010F712
0x14010f6f4  mov     r9, [rsp+2C0h+var_270]; unsigned __int64
0x14010f6f9  mov     r8, r15; unsigned __int16 *
0x14010f6fc  mov     rdx, [rbp+1C0h+arg_38]; unsigned __int64
0x14010f703  mov     rcx, r12; String2
0x14010f706  call    ?CompareValue@@YAHPEBG_K01@Z; CompareValue(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x14010f70b  mov     [r14], eax
0x14010f70e  xor     ecx, ecx
0x14010f710  mov     edi, ecx
0x14010f712  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x14010f717  test    rcx, rcx
0x14010f71a  jz      short loc_14010F722
0x14010f71c  call    cs:__imp_RegCloseKey
0x14010f722  mov     rcx, [rsp+2C0h+var_278]; hKey
0x14010f727  test    rcx, rcx
0x14010f72a  jz      short loc_14010F732
0x14010f72c  call    cs:__imp_RegCloseKey
0x14010f732  mov     eax, edi
0x14010f734  mov     rcx, [rbp+1C0h+var_50]
0x14010f73b  xor     rcx, rsp; StackCookie
0x14010f73e  call    __security_check_cookie
0x14010f743  add     rsp, 288h
0x14010f74a  pop     r15
0x14010f74c  pop     r14
0x14010f74e  pop     r13
0x14010f750  pop     r12
0x14010f752  pop     rdi
0x14010f753  pop     rsi
0x14010f754  pop     rbx
0x14010f755  pop     rbp
0x14010f756  retn
```
